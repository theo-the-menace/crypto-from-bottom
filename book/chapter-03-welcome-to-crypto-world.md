# Chapter 3 — Welcome to the Crypto World

After learning K-lines, market structure, and indicators, many beginners enter a difficult stage: a few small wins, followed by one or two much larger losses. This usually happens because a chart observation was mistaken for a complete trading plan. Indicators can describe a market, but they do not decide how much to risk, where an idea becomes wrong, or how to exit.

This chapter turns chart reading into a safer process. We will move from evidence to a trade hypothesis, from the hypothesis to position size, and from position size to a simulated order. The aim is to build skills before adding real money.

## 1. The learning period: why small wins can become large losses

A beginner can make money by luck, by entering during a strong trend, or by following a signal that happens to work. A profitable trade does not prove that the method is sound. If there is no written rule for risk, a trader may increase size after a win and keep holding after a loss. A single move against the position can then erase many earlier gains.

Treat this period as training. Study experienced traders whose reasoning, records, and losses are visible. Use their work to learn questions and methods, not to copy entries. An analyst, influencer, or AI can be wrong, can use a different timeframe, or can hide the risk behind a confident explanation. Your account still needs its own limits.

## 2. Money management comes before the order

Money management answers a question that indicators cannot: **how much can this idea lose without damaging the account?** Decide the risk before looking for an entry.

A simple starting rule is to risk a small fixed fraction of account equity on one trade. For example, with a 1,000 USDT account and a 0.5% risk limit, the planned loss is 5 USDT. This is a planning example, not a universal percentage; a smaller limit is reasonable while learning, and leverage does not change the amount you should be willing to lose.

The position size follows from the stop distance:

```text
position size = allowed loss / (entry price - stop price)
```

If a BTC spot idea buys at 100,000 USDT and the invalidation stop is 98,000 USDT, the distance is 2,000 USDT per BTC. With 5 USDT of planned risk, the maximum size is 0.0025 BTC before fees and slippage. In practice, reduce it to leave room for trading fees, spread, slippage, and an imperfect fill. If the required size is too small to make the trade worthwhile, the answer is to skip the trade, not to move the stop closer.

Keep separate limits for one trade, one day, and the whole account. Do not average down simply because the price moved against you. Do not increase leverage to recover a loss. A written loss limit protects your future decisions when emotion is strongest.

## 3. How to analyze a possible trade

Use the same order every time. The order prevents a fast indicator from overriding the larger context.

### 3.1 Start with price and timeframe

Choose the instrument and timeframe first. Use the daily or weekly chart to identify the broad regime and major support or resistance. Use the 4-hour or 1-hour chart to describe the current setup. Use a lower timeframe only to improve execution after the higher-timeframe idea is clear.

Write the observation without a prediction: “BTC is making higher highs and higher lows,” “BTC is below a falling MA(25),” or “price is inside a 57,000–67,000 range.” This keeps the chart description separate from the decision.

### 3.2 Use indicators to answer different questions

Do not ask every indicator whether to buy. Give each one a job:

| Question | Evidence to inspect | Example interpretation |
| --- | --- | --- |
| What direction is price taking? | HH/HL, LH/LL, support and resistance, MA/EMA | A rising EMA(25) with price holding above it supports an upward context. |
| Is the move gaining or losing momentum? | RSI or MACD | Price makes a new high while RSI or MACD makes a lower high: momentum is not confirming the high. |
| Is there participation? | Volume or OBV | A breakout with clearly higher volume has stronger participation evidence than a thin wick. |
| How large is normal movement? | ATR or Bollinger Band width | A high ATR means a tight stop may sit inside ordinary noise. Narrow bands mean compression, not a guaranteed breakout direction. |
| What would prove the idea wrong? | A protected swing, key level, or volatility boundary | A long idea may be invalid if price closes below the higher low that supported it. |

The indicators are related because many are calculated from the same candles. MA, RSI, and MACD agreeing is useful context, but it is not three independent votes. Structure and risk still control the decision.

### 3.3 Turn the reading into a hypothesis

A usable hypothesis has four parts:

1. **Context:** the market is trending, ranging, or transitioning on a named timeframe.
2. **Trigger:** the exact event that would allow an entry, such as a candle closing above resistance and holding it on a pullback.
3. **Invalidation:** the price or condition that proves the idea wrong.
4. **Risk and exit:** the position size, stop, target or trailing rule, and maximum time in the trade.

Example: “On the 4-hour chart, BTC is in an HH/HL structure. I will consider a long only after a close above 84,000 and a pullback that holds 84,000 as support. A close below the new higher low invalidates the idea. I will risk no more than 5 USDT and will not widen the stop.” This is a hypothesis, not a prediction.

## 4. How to open a position

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

## 5. How to choose a stop-loss location

A stop should sit where the trade idea is invalidated, with enough room for normal movement. It should not be chosen only because it creates a convenient position size.

For a long position, possible references include:

- below the higher low or support zone that the thesis depends on;
- below the breakout level after a confirmed breakout and retest;
- a multiple of ATR away, if that distance is consistent with the structure;
- beyond ordinary wick noise, while keeping the resulting position size within the risk limit.

For a short position, reverse the logic: the stop can sit above the protected lower high, resistance, or a volatility-adjusted invalidation level. A moving average or Bollinger Band is a reference, not automatically a valid stop. News, liquidation cascades, and thin liquidity can move through any line.

The correct order is **invalidation first, size second**. If the structural stop is too far away, reduce the position. Do not move the stop closer just to trade a larger amount, and do not move it farther away after entry to avoid accepting a loss. A stop is an exit rule, not a guarantee of an exact fill.

## 6. Practice a position on Binance without risking capital

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

## 7. A repeatable checklist

Before every simulated or live trade, answer these questions in writing:

- What is the higher-timeframe context?
- Which price level or structure makes the setup meaningful?
- Which indicator evidence supports the hypothesis, and which evidence conflicts with it?
- What exact event triggers the entry?
- At what price is the hypothesis invalidated?
- How much money is at risk after fees and slippage?
- What will I do if the order does not fill, the stop slips, or news changes the market?

If these answers are missing, waiting is a valid trading decision. The purpose of technical analysis is not to force a position. It is to make the decision understandable before money is exposed.
