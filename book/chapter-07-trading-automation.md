# Chapter 7 — Trading automation (optional)

**This chapter is optional.** Automation is not a requirement for profitable trading. Many successful traders execute manually for years. Read this chapter only if you:

- Have a profitable strategy that you have tested manually for 50+ trades
- Want to remove emotional interference and execute with consistency
- Want to trade 24/7 without watching the screen
- Have some programming or technical skills (or are willing to learn)

**Do not automate a strategy that is not yet profitable manually.** Automation will only make you lose money faster and more consistently.

---

## Introduction: what automation can and cannot do

Automation connects a signal (e.g., a TradingView alert when your setup triggers) to an order execution system (e.g., Binance API) without manual intervention. The workflow typically looks like this:

```
TradingView chart → Pine Script condition → TradingView alert
→ HTTPS webhook → your server → Binance API → order placement → logs
```

**What automation can do:**

- Execute your strategy exactly as written, without hesitation or second-guessing
- Trade 24/7, including while you sleep
- Remove emotional decisions (fear, greed, revenge trading)
- Scale to multiple symbols or timeframes
- Keep detailed logs for every signal and order

**What automation cannot do:**

- Turn a losing strategy into a winning one
- Predict the market better than you can manually
- Protect you from bugs, misconfigurations, or exchange outages
- Eliminate risk (you can still lose money, faster and more consistently than manual trading)

**The golden rule:** Automation makes a good process faster and more consistent. It makes a bad process lose money faster. Do not automate until you are confident that your strategy works.

---

## 1. Prerequisites before automating

Before writing any code, ensure you have:

**1. A tested, profitable strategy**
- 50+ manual trades with positive expectancy after fees
- Written rules: clear entry, exit, stop, position sizing logic
- Verified on multiple market conditions (trending, ranging, volatile, quiet)

**2. Understanding of execution mechanics**
- You know the difference between limit, market, and stop orders (see Chapter 6)
- You have manually placed orders on Binance and understand slippage, fees, and order book behavior
- You have checked the spread, depth, and liquidity before (see Advanced — Liquidity chapter)

**3. Basic technical skills**
- Comfortable reading and editing code (Python, JavaScript, or similar)
- Can set up a simple web server
- Understand environment variables, API keys, and HTTPS

If you do not meet these prerequisites, **skip this chapter** and keep trading manually until you do.

---

## 2. The automation workflow

The typical setup:

1. **TradingView** runs your Pine Script strategy on a chart
2. When a condition triggers, TradingView sends a **webhook alert** (HTTPS POST request) to your server
3. Your **server** receives the alert, validates it, calculates position size, checks risk limits
4. Your server sends an order request to **Binance API**
5. Binance fills the order (or rejects it), and your server logs the result

Each step must be built carefully. A mistake at any stage can result in duplicated orders, missed stops, or unprotected exposure.

---

## 3. Write the TradingView Pine Script

TradingView scripts use **Pine Script**. An **indicator** calculates and displays information on the chart. A **strategy** can simulate trades in TradingView's backtester.

For automation, you will write an indicator (or strategy) that sends an alert when your condition triggers.

### 3.1 Basic Pine Script example

This example creates a simple moving-average crossover indicator and sends a JSON alert when the condition triggers:

```pine
//@version=6
indicator("Learning webhook example", overlay=true)

fast = ta.ema(close, 7)
slow = ta.ema(close, 25)
longSignal = ta.crossover(fast, slow) and barstate.isconfirmed
shortSignal = ta.crossunder(fast, slow) and barstate.isconfirmed

plot(fast, "EMA 7", color=color.yellow)
plot(slow, "EMA 25", color=color.purple)

if longSignal
    alert('{"secret":"replace-me","action":"buy","symbol":"BTCUSDT","timeframe":"' + timeframe.period + '","bar_time":' + str.tostring(time) + ',"price":' + str.tostring(close) + '}', alert.freq_once_per_bar_close)

if shortSignal
    alert('{"secret":"replace-me","action":"sell","symbol":"BTCUSDT","timeframe":"' + timeframe.period + ',"bar_time":' + str.tostring(time) + ',"price":' + str.tostring(close) + '}', alert.freq_once_per_bar_close)
```

**Important notes:**

- **`barstate.isconfirmed`** ensures the alert only fires after the candle closes. Without this, the signal can appear and disappear while the candle is forming, causing false alerts.
- **`alert.freq_once_per_bar_close`** prevents multiple alerts for the same bar.
- The alert payload is a JSON string containing: action, symbol, timeframe, timestamp, and price.
- **Never put your Binance API key or secret in the alert message.** TradingView explicitly warns against this.

### 3.2 Backtest before creating the alert

If your strategy is more complex, use `strategy()` instead of `indicator()` to backtest it:

```pine
//@version=6
strategy("My Strategy", overlay=true, commission_type=strategy.commission.percent, commission_value=0.1, slippage=2)

// Entry logic
fast = ta.ema(close, 7)
slow = ta.ema(close, 25)
longCondition = ta.crossover(fast, slow)
shortCondition = ta.crossunder(fast, slow)

if longCondition
    strategy.entry("Long", strategy.long)

if shortCondition
    strategy.entry("Short", strategy.short)
```

**Critical settings:**

- **Commission:** set to at least 0.1% (0.05% each side) for spot, or 0.05-0.10% for futures
- **Slippage:** set to 1-5 ticks
- Without these, your backtest is unrealistic.

Test the strategy on:
- Multiple symbols (BTC, ETH, a major altcoin)
- Multiple timeframes (1h, 4h, daily)
- Different periods (bull market, bear market, sideways)

If it only works on one symbol in one period, it is overfit. Do not automate it.

### 3.3 Create the TradingView alert

1. Apply your script to a chart
2. Click **Alert** (clock icon at top right)
3. Set:
   - **Condition:** your script name + "alert() function calls only"
   - **Message:** leave as `{{strategy.order.alert_message}}` or the default (your script's alert message will be sent)
   - **Webhook URL:** your server's HTTPS endpoint (e.g., `https://yourdomain.com/tradingview`)
4. Click **Create**

Now, every time your script's condition triggers, TradingView will send an HTTPS POST request to your webhook URL.

---

## 4. Create an HTTPS webhook server

A webhook is an HTTP POST request that TradingView sends to a public URL you control. Your server must:

1. Authenticate the request (verify it came from your TradingView alert, not a random attacker)
2. Validate the data (check required fields, reject invalid symbols/actions)
3. Calculate position size (based on account balance, risk limit, and stop distance)
4. Send the order to Binance
5. Log everything

### 4.1 Minimal Flask webhook receiver (Python example)

```python
import os
from flask import Flask, request, jsonify

app = Flask(__name__)
WEBHOOK_SECRET = os.environ["WEBHOOK_SECRET"]

@app.post("/tradingview")
def tradingview_webhook():
    payload = request.get_json(silent=True)
    
    # 1. Authentication
    if not payload or payload.get("secret") != WEBHOOK_SECRET:
        return jsonify({"error": "unauthorized"}), 401

    # 2. Validation
    required = {"action", "symbol", "timeframe", "bar_time"}
    if not required.issubset(payload):
        return jsonify({"error": "missing field"}), 400
    if payload["action"] not in {"buy", "sell"}:
        return jsonify({"error": "invalid action"}), 400
    if payload["symbol"] != "BTCUSDT":
        return jsonify({"error": "symbol not enabled"}), 400

    # 3. In production: calculate position size, deduplicate, check risk limits,
    #    enqueue the order. Do NOT place a live order here yet.
    
    # For now, just log and return
    print(f"Received signal: {payload}")
    return jsonify({"accepted": True, "signal": payload}), 202

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=443, ssl_context="adhoc")
```

**Important:**

- Run this behind a proper TLS certificate (Let's Encrypt, Cloudflare, etc.)
- TradingView only accepts ports 80 and 443
- TradingView will cancel requests that take longer than 3 seconds → respond quickly, then process asynchronously
- Keep a log of every webhook received

### 4.2 Essential server controls

Before connecting to Binance, add these protections:

**Authentication:**
- Use a strong, random secret (not "replace-me")
- Store it in an environment variable, not in the code

**Schema validation:**
- Reject unknown symbols
- Reject unknown actions
- Check that timeframe, price, and timestamp are sensible

**Replay protection:**
- Create a unique signal ID: `symbol + timeframe + bar_time + action`
- Store processed signal IDs in a database or cache
- Reject duplicates (TradingView may resend if your server was slow to respond)

**Risk limits:**
- Cap maximum position size per trade
- Cap maximum daily loss
- Cap maximum open positions
- Cap maximum orders per hour

**State checks:**
- Query Binance for current open positions before creating a new order
- Do not open a new long if you already have a long open (unless your strategy allows pyramiding)

**Idempotency:**
- Assign each order a unique `newClientOrderId`
- If the server crashes after sending the order but before logging the response, restarting and retrying will not duplicate the order

**Kill switch:**
- One environment variable or config file change must stop all new orders
- Useful during exchange maintenance, strategy debugging, or unexpected behavior

**Audit logs:**
- Log: webhook payload, validation result, calculated position size, Binance request, Binance response, fill details, errors
- Store logs in a database or structured log file (not just `print()`)

**Monitoring:**
- Alert yourself (email, SMS, Slack) when:
  - Webhook delivery fails
  - Server crashes
  - Binance API returns errors
  - Daily loss limit is approaching
  - Open position count exceeds limit

---

## 5. Connect the server to Binance

### 5.1 Create API keys

Do NOT create API keys until your demo flow works. When you do:

1. Go to Binance → Account → API Management
2. Create a new API key
3. **Restrict permissions:**
   - Enable: **Spot trading** or **Futures trading** (whichever you use)
   - Disable: **Withdrawals**
4. **IP whitelist (if possible):** restrict the key to your server's IP
5. **Store the secret securely:**
   - Save it in an environment variable or secret manager (AWS Secrets Manager, HashiCorp Vault, etc.)
   - Never commit it to Git
   - Treat it like a password

### 5.2 Choose the correct product

**Spot** (BTC/USDT): exchanges USDT for BTC, creates a BTC balance, no leverage, no liquidation

**USDⓈ-M Futures** (BTCUSDT Perp): leveraged contract settled in stablecoin, has funding fees, has liquidation price

**COIN-M Futures** (BTCUSD Perp): leveraged contract with BTC as margin, double exposure (BTC price risk + position risk)

Do NOT assume that `BTCUSDT` Spot and `BTCUSDT` Perp use the same API parameters. Read the Binance API documentation for your chosen product:

- [Binance Spot API — New Order](https://developers.binance.com/docs/binance-spot-api-docs/rest-api/trading-endpoints/new-order)
- [Binance USDⓈ-M Futures API — New Order](https://developers.binance.com/docs/derivatives/usds-margined-futures/trade/rest-api/New-Order)

### 5.3 Use Binance demo/testnet first

Do NOT test on your live account. Use:

- **Binance Demo Trading** (simulated environment with fake funds)
- **Binance Spot Testnet / Futures Testnet** (separate test environment)

Check [Binance Demo Trading guide](https://www.binance.com/en-NG/learn/binance-demo-trading) and [testnet FAQ](https://www.binance.com/en/support/faq/detail/ab78f9a1b8824cf0a106b4229c76496d).

### 5.4 Example: placing a Binance Spot order (Python)

```python
import os
import hashlib
import hmac
import time
import requests

API_KEY = os.environ["BINANCE_API_KEY"]
API_SECRET = os.environ["BINANCE_API_SECRET"]
BASE_URL = "https://api.binance.com"

def create_signature(params):
    query_string = "&".join([f"{k}={v}" for k, v in params.items()])
    return hmac.new(API_SECRET.encode(), query_string.encode(), hashlib.sha256).hexdigest()

def place_spot_order(symbol, side, quantity):
    endpoint = "/api/v3/order"
    timestamp = int(time.time() * 1000)
    
    params = {
        "symbol": symbol,
        "side": side,  # "BUY" or "SELL"
        "type": "MARKET",
        "quantity": quantity,
        "timestamp": timestamp,
    }
    params["signature"] = create_signature(params)
    
    headers = {"X-MBX-APIKEY": API_KEY}
    response = requests.post(BASE_URL + endpoint, headers=headers, params=params)
    return response.json()

# Example usage
result = place_spot_order("BTCUSDT", "BUY", 0.001)
print(result)
```

**Never run this on live funds without testing in Demo first.**

For production use, use the official Binance Python connector instead of writing your own:
- [python-binance](https://github.com/sammchardy/python-binance) (community library, widely used)
- [binance-connector-python](https://github.com/binance/binance-connector-python) (official library)

---

## 6. Staged rollout: test before going live

Do NOT connect TradingView → webhook → Binance live immediately. Follow this staged process:

### Stage 1: Chart-only

- Apply your Pine Script to a TradingView chart
- Create an alert that sends to a test endpoint (e.g., [webhook.site](https://webhook.site))
- Confirm that alerts fire only on closed candles
- Compare alert timestamps with the chart

### Stage 2: Webhook logging

- Deploy your HTTPS webhook server
- Update TradingView alert to point to your server
- Server should authenticate, validate, and log—but NOT place orders
- Send deliberately malformed alerts (wrong secret, missing fields, old timestamp) and confirm they are rejected

### Stage 3: Simulated orders (Binance Demo)

- Connect your server to Binance Demo Trading
- Calculate position size dynamically (based on account balance, risk%, stop distance)
- Place demo orders
- Log: request sent, response received, fill price, fees
- Run for 1-2 weeks, compare with TradingView backtest

### Stage 4: Shadow mode

- Calculate what a live order would be, but do NOT send it
- Log: "Would have placed BUY 0.05 BTC at 83,000"
- Check: did the webhook arrive on time? Was the position size correct? Would the stop have been placed correctly?
- Run for another 1-2 weeks

### Stage 5: Tiny live deployment

- Only after Stage 4 succeeds, use the smallest practical position size on live funds
- Start with 10-25% of your intended size
- Keep withdrawals disabled on the API key
- Set strict daily loss limits
- Monitor every single trade manually for the first week

**If anything breaks, stop immediately.** Do not "let it run and see what happens."

---

## 7. Common automation mistakes

**Mistake 1: Automating an untested strategy**

- You built a TradingView script that looks good in backtest, never paper-traded it, and connected it to live funds.
- **Result:** The strategy had lookahead bias or was overfit. You lose money immediately.

**Mistake 2: No replay protection**

- TradingView sends the same alert twice (network retry, or you edited the alert and it re-fired)
- Your server places two orders for the same signal
- **Result:** Double position size, double risk

**Mistake 3: No kill switch**

- Your strategy starts losing consistently. You are asleep. It keeps trading, hitting your daily loss limit.
- **Result:** Significant loss before you wake up and notice

**Mistake 4: Trusting the webhook payload for position size**

- Your TradingView alert sends `"quantity": 1.0` BTC
- Your server blindly places a 1.0 BTC order
- **Result:** You risk 10x more than intended because you did not recalculate based on account size and stop distance

**Mistake 5: Not logging**

- An order fails. You do not know why. No logs, no error messages, no audit trail.
- **Result:** You cannot debug, cannot improve, and repeat the same mistake

---

## 8. What to add next (for advanced users)

Once your basic automation is stable, consider:

- **Multiple symbols:** apply the same strategy to BTC, ETH, and 3-5 major altcoins (add symbol whitelist, per-symbol position limits)
- **Multiple timeframes:** run the strategy on 1h, 4h, and daily charts simultaneously (deduplicate signals, manage correlated positions)
- **Risk aggregation:** track total portfolio exposure, not just per-trade risk
- **Exchange outage handling:** if Binance API is down, queue the order and retry, or skip the trade and log it
- **Backtesting vs. live reconciliation:** compare live results with what the backtest predicted; if they diverge significantly, investigate
- **Automated reporting:** daily P&L summary sent to your email or Slack

---

## Summary

- Automation does NOT make a bad strategy good. Only automate after 50+ profitable manual trades.
- The workflow: TradingView → webhook → your server → Binance API
- Build with safety: authentication, validation, deduplication, risk limits, kill switch, logs, monitoring
- Test in stages: chart-only → webhook logging → demo trading → shadow mode → tiny live
- Do NOT skip stages. Do NOT go live until demo and shadow modes succeed for weeks.

Automation is powerful but dangerous. Treat it like handing your money to a robot: the robot will do exactly what you programmed it to do, including lose all your money if you programmed it incorrectly.

If in doubt, keep trading manually. There is no shame in manual execution. Many profitable traders never automate.
