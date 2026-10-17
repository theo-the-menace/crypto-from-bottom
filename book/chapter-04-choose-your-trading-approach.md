# Chapter 4 — Choose Your Trading Approach

Chapter 1 introduced the exchange, products, and the emotional cost of trading. Chapter 2 taught us to read K-lines, market structure, timeframes, and indicators. Chapter 3 added money management, position sizing, stops, and simulated execution. The next decision is not which indicator to add. It is deciding what kind of trader you are going to be.

A strategy is a repeatable answer to five questions:

1. **What market and product will I trade?**
2. **What condition gives me a reason to enter?**
3. **Where am I wrong, and where will I exit?**
4. **How much can I lose on one attempt?**
5. **How will I record and review the result?**

A high-return method cannot be selected in advance with certainty. High expected return usually comes with larger drawdowns, more losing trades, more leverage, or a greater chance of ruin. The useful target is a method with positive expectancy that you can survive and follow. Return comes after risk, evidence, and repetition.

## 1. What matters most: news, K-lines, or divergence?

These sources answer different questions, so ranking them as if they were competing signals creates confusion.

| Evidence | What it tells you | How a retail trader should use it | Main limit |
| --- | --- | --- | --- |
| **Market news and events** | What may change the environment: regulation, rates, exchange incidents, unlocks, or a major protocol event. | Use it as a risk and regime filter. Reduce size, avoid opening just before a known high-impact event, and investigate an unusual move. | News can be incomplete, late, misinterpreted, or already priced in. A headline does not tell you the exact entry or stop. |
| **K-lines and market structure** | What buyers and sellers actually did: HH, HL, LH, LL, ranges, breaks, and failed breaks. | Make structure the primary chart language. Decide whether the market is trending, ranging, or unclear before looking for an entry. | Structure is clearest after the move. A single wick or small swing does not prove a new trend. |
| **Volume and volatility** | Whether participation and movement changed during a breakout or reversal. | Check whether a price move has enough participation and whether the stop distance is realistic. | Volume can be distorted by venue, product, and liquidation activity; volatility does not give direction. |
| **MA, MACD, and RSI** | Smoothed direction and momentum: whether recent movement is strengthening, weakening, or diverging from price. | Use them as confirmation and timing tools after structure gives a hypothesis. | They are calculated from price history and often repeat the same information. They can be late or fail in a range. |
| **Divergence** | Price and an indicator are no longer moving with the same strength. | Treat it as a warning to reduce confidence, wait for structure confirmation, or manage an existing position. | Divergence can persist while price continues in the original direction. It is not an automatic reversal signal. |

For most retail traders, the priority is therefore **risk and market structure first, context from news second, and indicators as supporting evidence**. This does not mean ignoring news. It means using each kind of information for the job it can actually do. A headline may explain why volatility expanded; the chart still has to show where the trade is invalidated.

## 2. Select one simple starting style

Do not begin by trying to trade every coin, timeframe, and product. Select one market, one product, and one holding period long enough to collect comparable results.

### 2.1 Long-term spot trend following

Buy a limited number of liquid assets in spot and hold through a broad trend, adding only according to a written plan. A trader might use the weekly chart for regime, the daily chart for structure, and a fixed allocation rather than leverage.

This style needs fewer decisions and has no liquidation from leverage, but it can experience large drawdowns and long periods of waiting. It suits someone who cannot watch charts continuously.

### 2.2 Swing pullback trading

Trade a move that lasts several days to several weeks. For example, BTC is making HH and HL on the daily chart, price pulls back toward a rising EMA(25) on the 4-hour chart, volume contracts during the pullback, and momentum turns up again. The entry is valid only if the planned stop below the structure fits the risk limit.

This is a reasonable learning style because the chart has enough information without requiring second-by-second execution. It still produces losing trades when a trend becomes a range or news changes the regime.

### 2.3 Breakout trading

Enter after price closes beyond a well-defined range or resistance and shows evidence that the break is being accepted. A trader may wait for the first pullback to hold above the broken level rather than chase the first candle.

Breakouts can produce large winners, but false breaks are common. The key question is not “did price touch above resistance?” but “did it close beyond the level, attract participation, and hold the next test?”

### 2.4 Range trading

Buy near a clearly established support area and reduce or exit near resistance while the range remains intact. This requires a defined invalidation level because a range eventually breaks.

Range trading can work when trend indicators repeatedly fail, but it is dangerous to keep fading a move after a genuine breakout. Do not use a range strategy and a breakout strategy at the same time without stating which condition has priority.

### 2.5 Systematic or automated trading

Convert a fully specified rule into code, test it, and execute it consistently. Chapter 5 explains the TradingView-to-webhook-to-Binance pipeline.

Automation is a delivery method, not a source of edge. A coded bad idea remains a bad idea, with faster and more repeatable losses.

## 3. A practical beginner default

If you do not yet have evidence for another style, start with a **BTC spot swing approach**:

- Trade BTC spot only; avoid leverage while learning.
- Use the daily chart to identify the broad regime and the 4-hour chart to plan an entry.
- Require a clear structure: a trend with HH/HL, a range with defined boundaries, or a confirmed breakout.
- Use one trend reference such as EMA(25), plus volume and one momentum tool such as RSI or MACD.
- Place the stop where the trade idea is invalidated, not at an arbitrary percentage.
- Risk a small fixed fraction of account equity on one trade. The exact fraction belongs in your written plan; the important rule is that a normal loss must not change your life or your emotions.
- Take screenshots and record the hypothesis, entry, stop, exit, fees, and whether you followed the plan.

This is a starting framework, not a guaranteed profitable recipe. After enough logged trades, you can compare it with a long-term approach, a range approach, or a coded system using evidence rather than imagination.

## 4. Turn observations into a trade hypothesis

Use the sequence below before pressing Buy or Sell:

### 4.1 Describe the environment

State the product, timeframe, and market regime. For example: “BTC spot, daily trend still above a rising EMA(99), but the 4-hour chart is ranging between support and resistance.” If you cannot describe the environment in one or two sentences, wait.

### 4.2 Define the trigger

Write the event that changes the idea from observation to a possible trade. Examples include a daily close above resistance followed by a holding pullback, or a rejection at range resistance with a lower high. “The indicator looks good” is not a trigger.

### 4.3 Define invalidation and exit

A stop belongs beyond the price point that proves the hypothesis wrong. A target can be the next resistance, a measured risk multiple, or a rule-based trailing exit. Decide before entering. A divergence may tell you to tighten an existing stop; it does not tell you to move a losing stop farther away.

### 4.4 Size the position

The distance from entry to stop determines the position size. If the stop is wide, the position must be smaller. Include fees, slippage, and contract rules. Never choose a size first and then move the stop to make the position fit.

### 4.5 Decide what evidence would change your mind

Write the condition that cancels the trade and the condition that would make the idea stronger. This prevents a trader from explaining every new candle as support for a position already held.

## 5. How to combine the tools from Chapters 1–3

A useful order of analysis is:

1. **Product and risk:** spot or derivatives, collateral, leverage, maximum loss, and liquidation risk.
2. **Higher-timeframe context:** weekly or daily direction, major support and resistance, and known event risk.
3. **Market structure:** HH/HL, LH/LL, range, BOS, CHoCH, or failed breakout.
4. **Participation and movement:** volume, ATR, and whether the move is expanding or losing energy.
5. **Momentum timing:** MA/EMA, MACD, RSI, or divergence as supporting evidence.
6. **Execution:** entry type, stop, target, size, and what happens if the order is only partly filled.

Do not count EMA(7), EMA(25), a moving-average crossover, and MACD as four independent confirmations. They all use price history. A stronger case usually comes from different evidence: a meaningful structural level, a close and hold, increased participation, and a risk plan that remains acceptable.

## 6. A worked example

Assume BTC has made a daily HH and HL and remains above a rising EMA(99). On the 4-hour chart, price pulls back into a prior resistance area that may now act as support. Volume is lower during the pullback, ATR shows that a normal candle is large enough to require a wider stop, and RSI recovers from below 50 without reaching an extreme. MACD turns upward, but the signal is only useful because the structure and level were identified first.

The hypothesis is: “If BTC closes back above the reclaimed level and the next pullback holds, the daily uptrend may continue.” The invalidation is a decisive close below the higher low. The trader calculates a small spot position from the entry-to-stop distance, places the order, and accepts that the setup can fail. If a sudden headline causes a fast break below the level, the stop is executed and the trade is recorded as a planned loss.

This example does not predict the next candle. It defines a testable idea with a known cost.

## 7. What “high return” should mean

A high return is meaningful only after fees, slippage, losing streaks, and drawdown. A strategy with a spectacular backtest but a 60% drawdown may be impossible for its owner to follow. A strategy with modest returns and controlled losses may be more valuable because it can be repeated.

Evaluate a method with questions such as:

- Does it have positive expectancy after realistic costs?
- How many losses can occur in a row?
- What is the largest historical drawdown?
- Does it work only in one market regime or one symbol?
- Can I follow it when the last five trades lost?
- What evidence would make me stop using it?

The objective is not to find a magic signal. It is to find a process that preserves capital while you learn whether an edge exists.

## 8. Build your own written playbook

Write one page before you expand the system:

- **Market:** BTC spot, or another precisely named product.
- **Timeframes:** one context timeframe and one execution timeframe.
- **Setups:** the one or two structures you will trade.
- **Evidence:** the exact role of news, structure, volume, volatility, and momentum.
- **Entry:** the candle-close or pullback condition.
- **Invalidation:** the price event that proves the idea wrong.
- **Risk:** maximum loss per trade, maximum daily loss, and maximum open exposure.
- **Review:** the information you will log and the date when you will evaluate the sample.

Do not add more indicators to avoid making a decision. Add a tool only when you can state what question it answers and what action it changes.

After this playbook has been tested with historical examples and simulated orders, Chapter 5 shows how to automate a defined process with TradingView, a webhook server, and Binance. Automation belongs after the rules are clear, not before.
