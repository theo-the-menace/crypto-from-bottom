# Chapter 2 — K-line analysis and market structure

This chapter explains how to read price action, structure, indicators, and chart-based hypotheses without treating them as guaranteed predictions.

## K-lines and market structure

A K-line (candlestick) records four prices for one interval: **open, high, low, close (OHLC)**. The body connects open and close; the upper and lower wicks reach the high and low. A candle is a description of what happened, not a cause and not a command to buy or sell.

![Anatomy of a K-line](assets/kline-anatomy.svg)

The interval matters. On a 5-minute BTC chart, one candle compresses five minutes of trades; on a daily chart, it compresses a full day. The open is the first matched price in that interval, the close is the last, and the high and low are the extremes reached in between. A long upper wick says that buyers pushed higher but sellers rejected part of the move. It does not, by itself, say that the next candle must fall. Candle color is only a convention: always read the four prices and the surrounding structure.

Why learn K-lines? They give every trader the same compact record of price, make risk levels visible, and let us compare behavior across timeframes and markets. They help us ask precise questions: where did price fail, which level was accepted, and where is the trade idea invalidated? They do not reveal who will trade next or guarantee a direction.

### 1 Timeframe is a lens

A 5-minute candle and a 1-day candle can describe the same market while answering different questions. Use a higher timeframe for context, an intermediate timeframe for the setup, and a lower timeframe only for execution detail. A candle that is still open can change its body and wick until the interval closes.

### 2 Structure: higher highs and lower lows

Market structure is a sequence of meaningful swing points, not every tiny fluctuation. A simple uptrend has a **higher high (HH)** followed by a **higher low (HL)**. A simple downtrend has a **lower high (LH)** followed by a **lower low (LL)**. A range alternates around boundaries without a reliable directional sequence.

![Higher highs and lower lows](assets/market-structure.svg)

A break of a prior swing can be informative, but it is not automatically a trend change. Ask whether the break closed beyond the level, whether volume/liquidity supported it, whether the move was quickly rejected, and whether the next pullback holds.

### 3 Divergence

A divergence occurs when price and a chosen indicator disagree. For example, price can print a lower low while an oscillator prints a higher low: **bullish divergence**. Price can print a higher high while the oscillator prints a lower high: **bearish divergence**.

![Bullish and bearish divergence](assets/divergence.svg)

Divergence is a change in momentum, not a guaranteed reversal. Strong trends can produce several divergences before price turns. Define the confirmation and invalidation in advance: a structure break, a close back above a level, or another rule you can test. Never use an indicator’s divergence without specifying which swing points and which oscillator settings count.

### 4 The core indicator families

Indicators are transformations of price, volume, or derivatives data. They organize evidence; they do not add certainty. Start with one tool from each useful family rather than stacking five versions of the same signal.

| Family | Common tools | What it helps you ask | Main limit |
|---|---|---|---|
| **Trend and direction** | Moving averages (SMA/EMA), VWAP, ADX | Is price generally above or below its recent average? Is a trend strong enough to follow? | They lag and can whipsaw in a range. |
| **Momentum** | RSI, MACD, Stochastic | Is the recent move accelerating, weakening, overextended, or crossing a reference level? | “Overbought” can stay overbought in a strong trend. |
| **Volatility** | ATR, Bollinger Bands, historical volatility | How large are normal moves, and where should a stop or position size sit? | Volatility measures movement, not direction. |
| **Volume and participation** | Volume bars, volume moving average, OBV, volume profile | Is a move supported by activity, and where did trading concentrate? | Exchange volume is fragmented and can be distorted; it is not proof of intent. |
| **Market structure and levels** | Swing highs/lows, support/resistance, pivots, Fibonacci retracements | Where are decisions, invalidation points, and likely liquidity clusters? | Levels are zones, not magic lines; everyone can interpret them differently. |
| **Derivatives and sentiment** | Open interest, funding rate, liquidation data, basis | Is leverage crowded, and are futures traders paying to hold one side? | Data is exchange-specific and can change quickly. |

For a first chart, a practical set is **price structure + one moving average or VWAP + ATR + volume**. Add RSI or MACD when you have a specific momentum question. Add funding and open interest only when you are actually studying perpetual futures. Do not treat an indicator crossing as a trade by itself; write the market regime, entry trigger, stop, and exit rule first.

### 5 Context before patterns

A long wick near a well-tested range boundary means something different from the same wick in the middle of a trend. Before naming a pattern, record:

- trend, range, or transition;
- location relative to prior highs/lows and volume zones;
- volatility and liquidity conditions;
- news or scheduled events;
- invalidation level and position size;
- what would confirm or disprove the idea.

Use indicators sparingly. One trend measure, one volatility measure, and volume are enough to begin. Adding correlated indicators can make a chart look certain while adding no independent information.

### 6 A reading exercise

Open a historical chart with the future hidden. Mark the last five meaningful swing highs and lows. Label each as HH, HL, LH, or LL. Add the timeframe, current regime, nearest invalidation level, and one alternative interpretation. Only after writing those notes reveal the next candles. This trains observation without hindsight.

### 7 Can K-lines predict the market?

K-lines can support a **conditional forecast**, not a certain prediction. Higher highs and higher lows may support a trend-following idea; a rejection wick at a well-tested level may define a possible entry and a nearby invalidation. The advantage is that the observation is visible, repeatable, and testable. The limit is that the same pattern can fail when the regime, liquidity, news, or leverage changes.

Treat every chart idea as a probability statement: “If price holds this level and the next candle closes with this confirmation, I will risk a defined amount toward this target.” Measure the rule over many examples, including fees, slippage, missed fills, and losing streaks. Learning K-lines improves observation and risk planning; it does not reveal the next candle in advance.

---
