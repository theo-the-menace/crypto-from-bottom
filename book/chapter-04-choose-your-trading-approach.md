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

## 2. The two foundational approaches

For a beginner, the first product decision is usually between **spot** and **futures**. The chart may look similar, but the position, cash flows, and failure modes are different.

### 2.1 Spot trading: own the asset

In a BTC/USDT spot trade, you exchange USDT for BTC. If the order fills, the BTC belongs to the spot account and there is no liquidation price caused by leverage. You can hold it for hours, days, or months, and you can sell it later. A falling price can still create a large loss, but the position does not automatically close just because a margin threshold was reached.

Spot is easiest to understand in a broad bullish market. A simple plan might buy after a daily pullback holds a prior support level and sell at a planned target or invalidation. In a range, a spot trader can buy near support and reduce near resistance. In a bear market, a spot trader can stay in USDT, reduce exposure, or use a long-term allocation plan instead of forcing a long trade. Staying out is a valid spot decision.

Spot does not remove risk. BTC can fall for a long time, the opportunity cost of idle capital can be high, and an unplanned “I will hold until it comes back” decision can turn a trade into an accidental investment. Define the reason for holding, the invalidation, and the maximum allocation before buying.

### 2.2 Futures trading: trade a contract

A perpetual futures position gives long or short exposure to a contract. You do not receive the same BTC as a spot purchase. You post margin, and leverage makes the position larger than the margin. Funding payments, fees, mark-price rules, liquidation, and the contract's collateral asset affect the result.

A long benefits when the contract price rises; a short benefits when it falls. This makes it possible to trade a bear market, but it also makes a wrong move expensive. A position can be liquidated before the trader's long-term view is proven right. A high leverage setting is not a risk plan; it only reduces the price movement needed to damage the margin.

For a beginner who has not yet produced a stable spot record, futures should remain a simulated exercise. If futures are eventually used, start with isolated margin, low leverage, one small position, a written liquidation check, and a hard loss limit. Never add to a losing position simply to avoid admitting that the first idea failed.

### 2.3 The same chart can produce different decisions

Suppose BTC is trading below a falling daily EMA(25) after making LH and LL:

- A **spot trader** may wait in USDT until a daily structure improves, or use only a small planned allocation.
- A **futures trader** may consider a short after a lower-timeframe rejection, but only if the stop, funding, liquidation distance, and maximum loss are acceptable.
- A **beginner** can study both ideas in Demo Trading without sending either order.

The chart does not choose the product for you. The product changes what “being right” costs while you wait.

## 3. Match the approach to the market regime

The same setup should not be used in every environment. First label the regime; then choose whether to trade, wait, or reduce exposure.

| Market regime | Spot approach | Futures approach | What to watch |
| --- | --- | --- | --- |
| **Bull trend**: daily or weekly HH/HL, price holding above rising averages | Buy a planned pullback or breakout retest; avoid chasing an extended candle. | Long only when the structure and risk support it; a short against the trend needs stronger evidence and smaller size. | Daily/weekly structure, support, volume, and whether momentum is expanding or fading. |
| **Bear trend**: daily or weekly LH/LL, price below falling averages | Stay in USDT, reduce exposure, or wait for a base. Do not assume a cheap price is a bottom. | A short can express the trend, but funding, squeeze risk, and liquidation must be checked first. | Lower highs, failed rebounds, resistance, open interest, and sudden news risk. |
| **Range**: repeated rejection between clear support and resistance | Buy near support only with an invalidation below the range; reduce near resistance. | Range trades can be quickly invalidated by a breakout; lower leverage and smaller size are essential. | Closes at the boundaries, volume on the break, and whether ATR is expanding. |
| **Transition or unclear**: mixed structure and conflicting timeframes | Wait for clarity or use a small allocation. | Avoid forcing a directional trade; a transition is where many false signals occur. | Higher-timeframe levels, CHoCH/BOS confirmation, and whether the next pullback holds. |

A single 15-minute move does not overturn a weekly trend. Conversely, a weekly trend can remain intact while a 1-hour trade fails. Use the higher timeframe to define the environment and the lower timeframe only to refine an entry.

## 4. Match the holding period to the timeframe

A timeframe is the amount of time represented by one candle. It is not a measure of accuracy. A 5-minute chart gives more entries and more noise; a daily chart gives fewer decisions and larger distances between entry and invalidation.

- **Minutes to 1 hour:** scalping or day trading. Requires constant attention, fast execution, and a plan for spread, fees, and sudden volatility. It is a poor starting point for most beginners.
- **4-hour to daily:** swing trading. A position may last from several days to several weeks. This is a practical learning range because the structure is visible and the trader does not need to react to every tick.
- **Weekly:** position or long-term allocation. It is useful for the broad regime and major levels, but a stop can be far away and a signal can take weeks to complete.

Use a consistent pair such as **daily for context and 4-hour for execution** while learning. If the daily chart says bull trend but the 4-hour chart is pulling back, that is a pullback inside a larger context—not automatically a new bear market. If the daily chart is unclear, a perfect 5-minute crossover does not create a high-quality long-term trade.

## 5. Choose a starting route, then test it

A beginner can study the two routes without trading both at once:

1. **Start with BTC spot swing trading:** use daily context, 4-hour entries, no leverage, a fixed allocation, and a structural stop.
2. **Run the same ideas in futures Demo Trading:** compare how funding, leverage, liquidation distance, and short exposure change the result.
3. **Keep separate records:** spot and futures are different products and must not be mixed into one performance number.
4. **Only consider a small live futures position after a stable simulated and spot record:** the product should be earned through evidence, not selected because it looks faster.

The goal is not to choose the product with the largest possible return. It is to choose the product whose risks you understand well enough to follow a written plan.

## 6. A practical beginner default

If you do not yet have evidence for another style, start with a **BTC spot swing approach**:

- Trade BTC spot only; avoid leverage while learning.
- Use the daily chart to identify the broad regime and the 4-hour chart to plan an entry.
- Require a clear structure: a trend with HH/HL, a range with defined boundaries, or a confirmed breakout.
- Use one trend reference such as EMA(25), plus volume and one momentum tool such as RSI or MACD.
- Place the stop where the trade idea is invalidated, not at an arbitrary percentage.
- Risk a small fixed fraction of account equity on one trade. The exact fraction belongs in your written plan; the important rule is that a normal loss must not change your life or your emotions.
- Take screenshots and record the hypothesis, entry, stop, exit, fees, and whether you followed the plan.

This is a starting framework, not a guaranteed profitable recipe. After enough logged trades, you can compare it with a long-term approach, a range approach, or a coded system using evidence rather than imagination.

## 7. Turn observations into a trade hypothesis

Use the sequence below before pressing Buy or Sell:

### 7.1 Describe the environment

State the product, timeframe, and market regime. For example: “BTC spot, daily trend still above a rising EMA(99), but the 4-hour chart is ranging between support and resistance.” If you cannot describe the environment in one or two sentences, wait.

### 7.2 Define the trigger

Write the event that changes the idea from observation to a possible trade. Examples include a daily close above resistance followed by a holding pullback, or a rejection at range resistance with a lower high. “The indicator looks good” is not a trigger.

### 7.3 Define invalidation and exit

A stop belongs beyond the price point that proves the hypothesis wrong. A target can be the next resistance, a measured risk multiple, or a rule-based trailing exit. Decide before entering. A divergence may tell you to tighten an existing stop; it does not tell you to move a losing stop farther away.

### 7.4 Size the position

The distance from entry to stop determines the position size. If the stop is wide, the position must be smaller. Include fees, slippage, and contract rules. Never choose a size first and then move the stop to make the position fit.

### 7.5 Decide what evidence would change your mind

Write the condition that cancels the trade and the condition that would make the idea stronger. This prevents a trader from explaining every new candle as support for a position already held.

## 8. How to combine the tools from Chapters 1–3

A useful order of analysis is:

1. **Product and risk:** spot or derivatives, collateral, leverage, maximum loss, and liquidation risk.
2. **Higher-timeframe context:** weekly or daily direction, major support and resistance, and known event risk.
3. **Market structure:** HH/HL, LH/LL, range, BOS, CHoCH, or failed breakout.
4. **Participation and movement:** volume, ATR, and whether the move is expanding or losing energy.
5. **Momentum timing:** MA/EMA, MACD, RSI, or divergence as supporting evidence.
6. **Execution:** entry type, stop, target, size, and what happens if the order is only partly filled.

Do not count EMA(7), EMA(25), a moving-average crossover, and MACD as four independent confirmations. They all use price history. A stronger case usually comes from different evidence: a meaningful structural level, a close and hold, increased participation, and a risk plan that remains acceptable.

## 9. A worked example

Assume BTC has made a daily HH and HL and remains above a rising EMA(99). On the 4-hour chart, price pulls back into a prior resistance area that may now act as support. Volume is lower during the pullback, ATR shows that a normal candle is large enough to require a wider stop, and RSI recovers from below 50 without reaching an extreme. MACD turns upward, but the signal is only useful because the structure and level were identified first.

The hypothesis is: “If BTC closes back above the reclaimed level and the next pullback holds, the daily uptrend may continue.” The invalidation is a decisive close below the higher low. The trader calculates a small spot position from the entry-to-stop distance, places the order, and accepts that the setup can fail. If a sudden headline causes a fast break below the level, the stop is executed and the trade is recorded as a planned loss.

This example does not predict the next candle. It defines a testable idea with a known cost.

## 10. What “high return” should mean

A high return is meaningful only after fees, slippage, losing streaks, and drawdown. A strategy with a spectacular backtest but a 60% drawdown may be impossible for its owner to follow. A strategy with modest returns and controlled losses may be more valuable because it can be repeated.

Evaluate a method with questions such as:

- Does it have positive expectancy after realistic costs?
- How many losses can occur in a row?
- What is the largest historical drawdown?
- Does it work only in one market regime or one symbol?
- Can I follow it when the last five trades lost?
- What evidence would make me stop using it?

The objective is not to find a magic signal. It is to find a process that preserves capital while you learn whether an edge exists.

## 11. Build your own written playbook

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
