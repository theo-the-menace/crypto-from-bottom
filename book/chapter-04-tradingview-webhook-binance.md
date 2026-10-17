# Chapter 4 — From TradingView Script to a Binance Order

Chapter 3 explained how to form a trade hypothesis, size a position, and place a simulated order. This chapter connects those pieces into an automated workflow:

```text
TradingView chart → Pine Script condition → TradingView alert
→ HTTPS webhook → your server → Binance API → order and logs
```

Automation does not make a weak strategy stronger. It only makes the strategy act faster and more consistently. A wrong condition, an unprotected endpoint, a duplicated webhook, or an incorrect contract setting can lose money without waiting for a human to notice. Build and test the whole path with virtual funds before enabling real orders.

## 1. Write the TradingView script

TradingView scripts use **Pine Script**. An indicator calculates and displays information. A strategy can also simulate entries and exits in TradingView's broker emulator, which is useful for research but is not a Binance order.

Start with one explicit, closed-candle condition. For example, the script below creates a moving-average crossover and sends a JSON alert only after the candle closes:

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
    alert('{"secret":"replace-me","action":"sell","symbol":"BTCUSDT","timeframe":"' + timeframe.period + '","bar_time":' + str.tostring(time) + ',"price":' + str.tostring(close) + '}', alert.freq_once_per_bar_close)
```

This is a learning example, not a complete strategy. A crossover is a lagging signal and can fail repeatedly in a range. A production script should also define the market, timeframe, one-position rule, exit conditions, and a way to avoid sending the same signal again.

Use `barstate.isconfirmed` when the rule is meant to use a closed candle. Otherwise, a condition can appear and disappear while the candle is still forming. TradingView's [Pine Script alert documentation](https://www.tradingview.com/pine-script-docs/concepts/alerts/) explains the difference between `alert()`, `alertcondition()`, and strategy order-fill alerts. Test the script visually: mark the bars where it would signal and compare them with the rule you wrote before connecting a webhook.

### 1.1 Backtest before creating an alert

If the idea is a strategy, use `strategy()` and include fees, slippage, position sizing, and exits in the TradingView test. Check the result on more than one symbol and timeframe. Compare it with buy-and-hold and inspect the worst losing streak, maximum drawdown, and behavior in a sideways market. A good-looking equity curve is not enough.

Keep the signal payload small. Send an action, symbol, timeframe, closed-bar timestamp, signal price, and a shared secret or signed token. Never put a Binance API key, secret key, password, or withdrawal credential in the alert message. TradingView explicitly warns against transmitting credentials in webhook bodies.

## 2. Create an HTTPS webhook server

A webhook is an HTTP POST request. TradingView sends the alert body to a public HTTPS URL when the alert fires. Your server must authenticate the request, validate the data, decide whether the action is allowed, and only then pass a normalized order instruction to the Binance adapter.

A minimal Flask receiver for testing might look like this:

```python
import os
from flask import Flask, request, jsonify

app = Flask(__name__)
WEBHOOK_SECRET = os.environ["WEBHOOK_SECRET"]

@app.post("/tradingview")
def tradingview_webhook():
    payload = request.get_json(silent=True)
    if not payload or payload.get("secret") != WEBHOOK_SECRET:
        return jsonify({"error": "unauthorized"}), 401

    required = {"action", "symbol", "timeframe", "bar_time"}
    if not required.issubset(payload):
        return jsonify({"error": "missing field"}), 400
    if payload["action"] not in {"buy", "sell"}:
        return jsonify({"error": "invalid action"}), 400
    if payload["symbol"] != "BTCUSDT":
        return jsonify({"error": "symbol not enabled"}), 400

    # In production: validate timestamp, deduplicate, check risk limits,
    # and enqueue the order. Do not place a live order in this route yet.
    return jsonify({"accepted": True, "signal": payload}), 202
```

Run the receiver behind a real TLS certificate on port 443. TradingView's webhook service accepts ports 80 and 443, can cancel a request that takes longer than three seconds, and may occasionally fail to deliver a request. The [TradingView webhook guide](https://www.tradingview.com/support/solutions/43000529348-how-to-configure-webhook-alerts/) documents these limits. Return quickly, put order work on a queue, and keep a delivery log.

### 2.1 Controls the server must add

Before the server can place an order, add these controls:

- **Authentication:** use a strong secret, HTTPS, and a separate endpoint; never rely on an obscure URL alone.
- **Schema validation:** reject unknown symbols, actions, timeframes, quantities, and prices.
- **Replay protection:** use a unique signal ID such as `symbol + timeframe + bar_time + action`; reject a signal already processed.
- **Risk limits:** cap order size, daily loss, open positions, leverage, and number of orders per hour.
- **State checks:** query the current position and open orders before creating a new order.
- **Idempotency:** give every order a client ID and record the result so a retry cannot double the position.
- **Kill switch:** one configuration change must stop all new orders.
- **Audit logs:** store the received payload, validation result, order request, exchange response, fill, and error.
- **Monitoring:** alert when TradingView delivery, the server, the exchange, or reconciliation fails.

A server that simply converts `buy` into a market order is not a trading system. It is an unprotected button exposed to the internet.

## 3. Connect the server to Binance

Create a Binance API key only after the demo flow works. Restrict the key to the required product and permissions. Disable withdrawals. Use IP restrictions where possible, keep the secret in an environment variable or secret manager, and never commit it to Git. The API key is an account credential; treat it like a password that can place orders.

Choose the exact product before coding:

- **Spot:** the order exchanges USDT and BTC; a filled buy creates a BTC balance.
- **USDⓈ-M perpetual:** the order creates leveraged contract exposure settled in a supported stablecoin.
- **COIN-M:** the margin and settlement rules use the coin-margined contract specification.

The symbol, quantity unit, price tick, minimum quantity, leverage, margin mode, and order parameters differ by product. Read the current Binance contract or exchange information instead of assuming that `BTCUSDT` and `BTCUSD_PERP` accept the same request.

For research and early integration, use Binance Demo Trading or the official Spot Testnet/Futures Demo environment. Binance's [Demo Trading guide](https://www.binance.com/en-NG/learn/binance-demo-trading) and [testnet/demo FAQ](https://www.binance.com/en/support/faq/detail/ab78f9a1b8824cf0a106b4229c76496d) describe the current access route. The API documentation for [Spot trading endpoints](https://developers.binance.com/docs/binance-spot-api-docs/rest-api/trading-endpoints), [request security](https://developers.binance.com/docs/binance-spot-api-docs/rest-api/request-security), and [USDⓈ-M Futures new orders](https://developers.binance.com/docs/derivatives/usds-margined-futures/trade/rest-api/New-Order) explains signed requests, order parameters, and product differences.

A direct signed request normally contains a timestamp and signature made with the API secret. Do not implement signing from memory. Use the current official Binance connector or SDK for the product you selected, and test it against the demo environment.

Conceptually, the Binance adapter should receive a safe internal instruction, not the raw webhook:

```text
{
  signal_id: "BTCUSDT-1h-1700000000000-buy",
  product: "spot",
  symbol: "BTCUSDT",
  side: "BUY",
  order_type: "LIMIT",
  quantity: 0.002,
  price: 100000,
  stop_price: 98000
}
```

The adapter then checks exchange filters, available balance, current position, and risk limits; submits the order; records the exchange order ID; and reconciles the actual fill. The server must not trust a quantity or price supplied by a public alert without recalculating or checking it.

## 4. Connect the complete workflow

Use this staged rollout:

### Stage 1: chart-only

Write the Pine Script and create a TradingView alert that sends a notification to a test endpoint. Confirm that alerts occur only on the intended closed candles. Compare the alert timestamp and price with the chart.

### Stage 2: webhook logging

Deploy the HTTPS receiver. It should authenticate and validate alerts, then log them without placing orders. Send deliberately malformed, duplicated, old, and unsupported messages to confirm that they are rejected.

### Stage 3: simulated orders

Connect the validated signal to Binance Demo Trading. Calculate the position size on the server from the account risk limit and the stop distance. Record simulated order requests, fills, fees, and stops. Compare the result with TradingView's broker-emulator result; differences are expected because fills, data, fees, and timing differ.

### Stage 4: shadow mode

For a sustained period, calculate what a live order would have been but do not send it. Check whether the webhook arrived in time, whether the symbol mapping was correct, whether the position state was understood, and whether the calculated size respected the risk limit.

### Stage 5: tiny live deployment

Only after the previous stages are reliable, use the smallest practical live size, with withdrawals disabled, strict daily loss limits, and a manual kill switch. Reconcile every order against Binance's actual status. A live system must be able to stop safely when TradingView, the server, the exchange, or the network behaves unexpectedly.

## 5. A complete example of the decision path

Suppose the TradingView script runs on BTCUSDT 1-hour candles. It observes an HH/HL context, a close above resistance, a rising EMA(25), improving MACD, and volume above its recent average. The alert sends a `buy` signal after the candle closes.

The server does not immediately buy. It checks that the signal ID is new, that the symbol is allowed, that no position is already open, and that the proposed stop is below the protected higher low. It calculates quantity from the account's allowed loss and the entry-to-stop distance, rounds the quantity to Binance's current filter, and rejects the order if the rounded size would exceed the risk limit. Only then does it send a demo order and log the response.

If the order fills, the system creates or records the exit plan. If the stop is hit, the position is closed and the signal ID is marked complete. If the webhook arrives twice, the second copy is ignored. If the exchange times out, the system queries order status before retrying. This sequence is the difference between an automated process and a script that blindly clicks Buy.

## 6. What to add next

The next practical addition is a set of annotated screenshots showing the TradingView Pine editor, the Create Alert dialog, the webhook request arriving at the server, Binance Demo Trading, and the resulting order and position history. Those images should be captured from the same product and account mode used in the examples, because Spot, USDⓈ-M, and COIN-M screens use different fields.

The technical pipeline is only one part of the strategy. Keep reviewing the original hypothesis, the risk, the fills, and the failure cases. Automation should make a tested process more consistent; it should never be used to avoid learning why a trade exists.
