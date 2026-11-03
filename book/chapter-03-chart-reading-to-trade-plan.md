# Chapter 3 — From Chart Reading to a Trade Plan

After learning K-lines, market structure, and indicators, many beginners enter a difficult stage: a few small wins, followed by one or two much larger losses. This usually happens because a chart observation was mistaken for a complete trading plan. Indicators can describe a market, but they do not decide how much to risk, where an idea becomes wrong, or how to exit.

This chapter turns chart reading into a safer process. We will move from evidence to a trade hypothesis, from the hypothesis to position size, and from position size to a simulated order. The aim is to build skills before adding real money.

A trade signal is an observable event that changes the decision from “observe” to “consider an entry.” It is not a feeling and it is not an indicator name. A complete signal states the location, the market context, the trigger, and the invalidation. For example: “On the 4-hour chart, BTC is in a higher-high and higher-low structure; after a close above resistance, I will consider a small spot position if the pullback holds that level; a close below the retest low invalidates the idea.”

The order of this chapter is deliberate: describe the market first, define the trade second, calculate the size third, and only then send a simulated order. The companion [philosophy of opening a trade](advanced/philosophy-of-opening-a-trade.md) article explains the same process in more detail; the working checklist belongs here.

## 1. The learning period: why small wins can become large losses

A beginner can make money by luck, by entering during a strong trend, or by following a signal that happens to work. A profitable trade does not prove that the method is sound. If there is no written rule for risk, a trader may increase size after a win and keep holding after a loss. A single move against the position can then erase many earlier gains.

Treat this period as training. Study experienced traders whose reasoning, records, and losses are visible. Use their work to learn questions and methods, not to copy entries. An analyst, influencer, or AI can be wrong, can use a different timeframe, or can hide the risk behind a confident explanation. Your account still needs its own limits.

## 2. Personal lessons from trading

The following lessons are easy to say and difficult to practice. They are more valuable than another isolated indicator because they protect the decisions made around every indicator.

### Do not chase the high or the low

Do not open a long position simply because price has just surged to a high. Do not open a short position simply because price has just fallen to a low. The move may continue, but the entry often has poor risk-to-reward and leaves no clear place for a protective stop. Wait for a structure, a pullback, or a defined breakout rule. Missing a move is frustrating; turning a missed move into a large loss is avoidable. Do not follow someone else's entry just because it sounds confident. It is better to earn less than to lose more.

### Do not keep opening positions

Repeatedly adding or reopening a position can make a trader feel active while quietly increasing exposure. In perpetual futures, every additional order can add trading fees, funding payments, slippage, liquidation risk, and emotional pressure. Even in spot, repeated entries can use all available cash before the market has confirmed the idea. Decide the maximum exposure before the first order. Add only if the written strategy explicitly allows it and the total risk remains within the limit.

### A low win rate can still be a valid model

Trading is mathematics, not gambling, when the rules and risk are defined before the outcome. A method can lose often and still make money if its winners are sufficiently larger than its losers. For example, a method that wins 30% of trades at +3R and loses 70% at -1R has an expectancy of `0.30 × 3R − 0.70 × 1R = +0.20R` before fees and slippage. Here, **R** is the amount planned to lose if the stop is hit.

This example is not evidence that the method works. The win rate, average win, losing streak, drawdown, and costs must come from a large enough sample. A low-win-rate method is reasonable only if the trader can survive its losing streaks and follow the rules without changing them after a loss. Without a defined edge and controlled risk, “high reward” is only a story told after the trade.

### Follow the exit plan when emotion becomes loud

Seeing an unrealized loss can create an urge to sell immediately, move the stop, or wait for a miracle. The answer should already be in the plan. If the invalidation level is reached, execute the stop and record the loss. If the take-profit or trailing rule is reached, follow that rule as well. A planned loss is a business cost; an unmanaged loss can become a threat to the whole account.

### Trading reveals the trader

Trading is a long contest with greed, fear, impatience, and the need to be right. The chart becomes a mirror: chasing a candle reveals urgency, repeated entries reveal discomfort with waiting, and refusing a stop reveals attachment to a prediction. This is not a moral judgment. It is useful information about which rule the process needs to strengthen.

## 3. Money management comes before the order

Money management answers a question that indicators cannot: **how much can this idea lose without damaging the account?** Decide the risk before looking for an entry.

A simple starting rule is to risk a small fixed fraction of account equity on one trade. For example, with a 1,000 USDT account and a 0.5% risk limit, the planned loss is 5 USDT. This is a planning example, not a universal percentage; a smaller limit is reasonable while learning, and leverage does not change the amount you should be willing to lose.

The position size follows from the stop distance:

```text
position size = allowed loss / (entry price - stop price)
```

If a BTC spot idea buys at 100,000 USDT and the invalidation stop is 98,000 USDT, the distance is 2,000 USDT per BTC. With 5 USDT of planned risk, the maximum size is 0.0025 BTC before fees and slippage. In practice, reduce it to leave room for trading fees, spread, slippage, and an imperfect fill. If the required size is too small to make the trade worthwhile, the answer is to skip the trade, not to move the stop closer.

Keep separate limits for one trade, one day, and the whole account. Do not average down simply because the price moved against you. Do not increase leverage to recover a loss. A written loss limit protects your future decisions when emotion is strongest.

## 4. How to analyze a possible trade

Use the same order every time. The order prevents a fast indicator from overriding the larger context.

### 4.1 Start with price and timeframe

Choose the instrument and timeframe first. Use the daily or weekly chart to identify the broad regime and major support or resistance. Use the 4-hour or 1-hour chart to describe the current setup. Use a lower timeframe only to improve execution after the higher-timeframe idea is clear.

Write the observation without a prediction: “BTC is making higher highs and higher lows,” “BTC is below a falling MA(25),” or “price is inside a 57,000–67,000 range.” This keeps the chart description separate from the decision.

### 4.2 Use indicators to answer different questions

Do not ask every indicator whether to buy. Give each one a job:

| Question | Evidence to inspect | Example interpretation |
| --- | --- | --- |
| What direction is price taking? | HH/HL, LH/LL, support and resistance, MA/EMA | A rising EMA(25) with price holding above it supports an upward context. |
| Is the move gaining or losing momentum? | RSI or MACD | Price makes a new high while RSI or MACD makes a lower high: momentum is not confirming the high. |
| Is there participation? | Volume or OBV | A breakout with clearly higher volume has stronger participation evidence than a thin wick. |
| How large is normal movement? | ATR or Bollinger Band width | A high ATR means a tight stop may sit inside ordinary noise. Narrow bands mean compression, not a guaranteed breakout direction. |
| What would prove the idea wrong? | A protected swing, key level, or volatility boundary | A long idea may be invalid if price closes below the higher low that supported it. |

The indicators are related because many are calculated from the same candles. MA, RSI, and MACD agreeing is useful context, but it is not three independent votes. Structure and risk still control the decision.

### 4.3 Turn the reading into a hypothesis

A usable hypothesis has four parts:

1. **Context:** the market is trending, ranging, or transitioning on a named timeframe.
2. **Trigger:** the exact event that would allow an entry, such as a candle closing above resistance and holding it on a pullback.
3. **Invalidation:** the price or condition that proves the idea wrong.
4. **Risk and exit:** the position size, stop, target or trailing rule, and maximum time in the trade.

Example: “On the 4-hour chart, BTC is in an HH/HL structure. I will consider a long only after a close above 84,000 and a pullback that holds 84,000 as support. A close below the new higher low invalidates the idea. I will risk no more than 5 USDT and will not widen the stop.” This is a hypothesis, not a prediction.

### 4.4 Why markets crash through support vs. bounce: reading follow-through

One of the most frustrating experiences for a beginner is watching price approach a support level with perfect chart logic—only to see it slice straight through and keep falling. Or the opposite: you wait for confirmation after a support touch, and by the time you enter, the bounce is already halfway to resistance and the risk-reward is poor.

Understanding **why** some support levels hold and others fail will help you choose better entry timing. The difference is not random, and it is not “manipulated by whales.” It comes down to **participation, liquidity, and structural context**.

#### When support holds and bounces

**What you observe:**
- Price approaches a known support level (previous low, round number, major moving average)
- Volume increases as price reaches the level
- A strong rejection candle forms (long lower wick, closes near the high)
- Price quickly recovers above the level

**Why it happens:**
1. **Buyers are waiting there.** Limit buy orders are stacked at the support level. When price touches it, those orders absorb the selling pressure.
2. **Shorts start covering.** Traders who shorted above support now take profit by buying, adding to the bounce.
3. **Structural alignment:** The support level aligns with higher-timeframe structure. For example, it is not just a 4-hour support but also a daily higher low or a weekly demand zone.
4. **Low selling pressure:** Sellers are exhausted or waiting for a higher price to sell. There is no urgent reason to sell below support.

**Observable clues before the bounce:**
- **Volume increasing into support:** More participants are engaging, not ignoring the level.
- **Order book shows depth:** Large bid walls appear near the support (though these can be spoofed, so treat as one signal among many).
- **RSI or other oscillators show oversold + divergence:** Suggests selling pressure is weakening.
- **Higher-timeframe trend is still bullish:** The overall structure says “this is a dip to buy,” not “this is a breakdown.”

**Entry timing:**
- **Conservative:** Wait for the rejection candle to close, then enter on the first pullback that holds above support (retest).
- **Aggressive:** Enter on the wick touch itself, with a tight stop below the level. Higher risk but better entry price.

**Example:**
BTC is in a daily uptrend (HH/HL). Price pulls back to 82,000, which is a previous 4-hour higher low. Volume picks up as it approaches. A 1-hour candle drops to 81,950, wicks down, and closes at 82,100. This is a rejection. A conservative entry is at 82,200 on the next candle, stop at 81,800. Risk is 400 USDT per BTC, and target is the next higher high at 84,000 (1,800 USDT reward, 4.5:1 ratio).

#### When support breaks and keeps falling

**What you observe:**
- Price approaches support
- Instead of bouncing, it closes below the level decisively
- The next candle continues lower, often accelerating
- Attempts to recover are weak (small bounces that fail quickly)

**Why it happens:**
1. **No buyers left.** The limit orders at support were already consumed, or traders pulled their bids when they saw weakness.
2. **Forced liquidations.** Many leveraged longs had stops or liquidation prices just below support. When price breaks it, those forced sells create a cascade.
3. **Structural breakdown:** The support was not aligned with higher timeframes. Breaking it signals a shift from uptrend to downtrend (CHoCH: Change of Character).
4. **High selling pressure:** New sellers appear (panic, news, institutional flows). The reason to sell is stronger than the reason to buy at support.
5. **Thin liquidity:** Weekend, holiday, or a thinly traded altcoin. A modest sell order can punch through support easily.

**Observable clues before the breakdown:**
- **Volume decreasing into support:** Fewer participants care about the level. It is being ignored, not defended.
- **Order book is thin:** Few bids below current price. A breakdown will have little support.
- **No divergence on oscillators:** RSI falls along with price, showing selling pressure is strong and sustained.
- **Higher-timeframe trend is weak or bearish:** The support is a lower high in a downtrend, not a higher low in an uptrend.
- **Multiple failed bounces:** Price has tested the level 3-4 times already. Each bounce is weaker than the last (lower highs forming below resistance).

**Entry timing (for shorts or avoiding longs):**
- **Do NOT enter a long just because price touched support.** Wait for confirmation that it holds first.
- **For a short:** Enter after the break is confirmed (daily close below support) and the first retest fails (price tries to recover but gets rejected).
- **If already long:** Tighten your stop or exit before the break confirms. Do not hold hoping for a miracle.

**Example:**
BTC is in a daily downtrend (LH/LL). Price bounces to 83,000, forms a lower high, and starts falling. It approaches the previous low at 81,500. Volume is declining. When price reaches 81,500, there is a small wick but the candle closes at 81,400. The next candle drops to 80,800. This is a breakdown. A short entry is at 81,300 on the retest (if it happens), stop at 81,800. Target is the next support at 79,000.

#### How to tell the difference **before** it happens

You cannot predict with certainty, but you can weigh probabilities:

| Factor | Bounce likely | Breakdown likely |
|--------|---------------|------------------|
| **Higher-timeframe trend** | Uptrend (HH/HL), support aligns with higher low | Downtrend (LH/LL), support is a lower high |
| **Volume** | Increasing into support | Decreasing or flat |
| **Previous tests** | First or second test of support | Third or fourth test (support weakening) |
| **Oscillator divergence** | Bullish divergence (lower low on price, higher low on RSI) | No divergence or bearish divergence |
| **Order book depth** | Visible bid stacks near support | Thin bids, large asks above |
| **Time of day/week** | Active hours (UTC afternoon), weekday | Weekend, holiday, thin liquidity hours |
| **News/macro context** | Positive or neutral | Negative (Fed rates, regulation, hack) |
| **Funding rate (futures)** | Negative or neutral (longs not overcrowded) | Very positive (too many longs, squeeze risk) |

**The 3-step decision process:**

1. **Before price reaches support:**
   - Is the higher-timeframe trend bullish or bearish?
   - How many times has this level been tested recently?
   - Is volume increasing or decreasing?

2. **As price touches support:**
   - Does the candle close above or below support?
   - Is there a strong rejection wick, or does it slice through cleanly?
   - Does volume spike (participation) or stay quiet (no one cares)?

3. **After the initial reaction:**
   - **If it bounces:** Does the next candle confirm the bounce (higher close), or does it immediately fail?
   - **If it breaks:** Does price keep falling, or does it immediately recover above support (fake breakdown)?

**Conservative entry rule:**

Do not enter **on the touch**. Enter **after confirmation:**
- **For a bounce:** Wait for the rejection candle to close, then enter on the retest of support.
- **For a breakdown short:** Wait for a daily close below support, then enter on the first failed retest.

This means you miss the absolute best entry (the wick low), but you avoid the much worse scenario of entering a support that breaks and keeps falling 10%.

#### Why waiting for confirmation feels bad but works better

**Psychological trap:**
- You see price approach support.
- You think: “This is going to bounce! If I wait for confirmation, I will miss the entry!”
- You enter at support touch.
- Price slices through and keeps falling.
- You panic, hold, move your stop, or take a large loss.

**Reality:**
- If support holds, the bounce is usually not a V-shaped instant reversal. Most bounces retest support after the initial rejection. You get a second chance.
- If support breaks, waiting for confirmation saves you from a large loss.
- Over 50 trades, the losses avoided by waiting for confirmation outweigh the few trades where you missed the absolute perfect entry.

**Example of waiting for confirmation:**

BTC approaches 82,000 support. You want to go long.

- **Scenario A (enter on touch):** You buy at 82,000. Price wicks to 81,900, then falls to 81,000 the next day. You lose 1,000 USDT per BTC.
- **Scenario B (wait for confirmation):** You wait. Price wicks to 81,900, then closes at 82,150 (rejection). You enter at 82,200 on the next candle's retest. If it bounces, you are in. If it breaks, you did not enter yet. You lose 0.

Yes, you might miss the trade if it bounces and never retests. But you avoided the breakdown scenario, which is much more expensive.

#### Practical checklist for entry timing

Before entering at or near support:

- [ ] Higher-timeframe trend supports this direction (uptrend for long, downtrend for short)
- [ ] This is the 1st or 2nd test of support, not the 5th
- [ ] Volume is increasing as price approaches
- [ ] Oscillators show bullish divergence (for bounces)
- [ ] Order book shows depth near support (optional, can be spoofed)
- [ ] I am willing to wait for a rejection candle to close before entering
- [ ] My stop is placed below support with room for a wick (not at the exact level)
- [ ] I have calculated position size based on stop distance, not guessed

If most boxes are unchecked, **do not force the trade**. Wait for a clearer setup.

#### Summary: bounce vs. breakdown

- **Bounces happen** when buyers defend the level with volume, structure aligns across timeframes, and selling pressure is exhausted.
- **Breakdowns happen** when no one defends the level, forced liquidations cascade, and the higher-timeframe trend is already weak.
- **You cannot predict with certainty**, but you can read **participation (volume), structure (trend context), and reaction (candle closes)** to improve your odds.
- **Waiting for confirmation** means missing some perfect entries but avoiding far more painful false entries.

The goal is not to catch every move. The goal is to enter trades where the probability and risk-reward justify the position.

## 5. How to open a position

First choose the product. A spot purchase gives you the asset after the order fills. A perpetual futures position gives leveraged long or short exposure under the contract rules and can be liquidated. A beginner should understand the spot example before using futures; leverage changes the speed and size of losses, not the quality of an analysis.

Then choose the order type. A **market order** prioritizes execution but accepts the available prices and possible slippage. A **limit order** controls the worst acceptable price but may not fill. A **conditional order** waits for a trigger before submitting a market or limit order. A **post-only** order is intended to rest as a maker order and can be cancelled if it would execute immediately. Read the product's contract, margin mode, fees, and trigger-price rules before submitting.

Before pressing Buy, Sell, Open Long, or Open Short, check:

- the symbol, quote asset, and spot or futures product;
- the order side and whether it opens or closes a position;
- the order type, price, quantity, and time-in-force;
- the planned stop and take-profit orders;
- the margin mode and leverage, if using futures;
- the maximum account loss if the stop fills with slippage.

A trade is not complete when the entry fills. Record the fill price, fees, stop, reason for entry, and the condition that would make you exit.

## 6. How to choose a stop-loss location

A stop should sit where the trade idea is invalidated, with enough room for normal movement. It should not be chosen only because it creates a convenient position size.

For a long position, possible references include:

- below the higher low or support zone that the thesis depends on;
- below the breakout level after a confirmed breakout and retest;
- a multiple of ATR away, if that distance is consistent with the structure;
- beyond ordinary wick noise, while keeping the resulting position size within the risk limit.

For a short position, reverse the logic: the stop can sit above the protected lower high, resistance, or a volatility-adjusted invalidation level. A moving average or Bollinger Band is a reference, not automatically a valid stop. News, liquidation cascades, and thin liquidity can move through any line.

The correct order is **invalidation first, size second**. If the structural stop is too far away, reduce the position. Do not move the stop closer just to trade a larger amount, and do not move it farther away after entry to avoid accepting a loss. A stop is an exit rule, not a guarantee of an exact fill.

## 7. Practice a position on Binance without risking capital

Use Binance Demo Trading or the relevant official test environment before using real funds. Binance describes Demo Trading as a virtual interface for practicing Spot and Futures with virtual funds; availability and product access can vary by region and account. See [Binance's Demo Trading guide](https://www.binance.com/en-NG/learn/binance-demo-trading) and [Binance's Spot Testnet and Futures Demo FAQ](https://www.binance.com/en/support/faq/detail/ab78f9a1b8824cf0a106b4229c76496d).

The practice workflow is:

1. Open the official Binance Demo Trading environment and confirm that the balance is virtual.
2. Select BTC/USDT Spot first. Check the chart, timeframe, order book, and fee display.
3. Write the context, entry trigger, invalidation, planned risk, and order size before opening the ticket.
4. Place a small simulated limit or market order according to the written plan.
5. Immediately add the simulated stop and exit plan if the interface supports them; otherwise record the exact exit level and monitor it without changing the rule.
6. Record the fill, spread, fees, slippage, maximum favorable and adverse movement, and final result.
7. Review the trade only after it closes. Do not rewrite the original hypothesis to make it look correct.

We will add annotated Binance screenshots for this workflow in a later revision. The important lesson is already testable without them: practice the complete decision—analysis, size, entry, stop, exit, and review—not only the moment of clicking an order button.

## 8. A repeatable checklist

Before every simulated or live trade, answer these questions in writing:

- What is the higher-timeframe context?
- Which price level or structure makes the setup meaningful?
- Which indicator evidence supports the hypothesis, and which evidence conflicts with it?
- What exact event triggers the entry?
- At what price is the hypothesis invalidated?
- How much money is at risk after fees and slippage?
- What will I do if the order does not fill, the stop slips, or news changes the market?

If these answers are missing, waiting is a valid trading decision. The purpose of technical analysis is not to force a position. It is to make the decision understandable before money is exposed.
