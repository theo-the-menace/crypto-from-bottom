# Chapter 4 — Moving-average and momentum tools

Chapter 2 introduced indicators as summaries of market data. This advanced chapter studies how moving averages, crossovers, MACD, and related momentum signals are used together. None of them is a prediction machine; each is a delayed view of what price has already done.

## 1. Moving-average combinations

A short moving average reacts quickly and a long moving average reacts slowly. Traders compare them to describe whether recent prices are becoming stronger or weaker than the longer background trend. The exact periods are choices, not universal laws. MA(7), MA(25), and MA(99) on a 15-minute chart describe roughly 105 minutes, 6 hours 15 minutes, and 24 hours 45 minutes of price history.

A **golden cross** is when a shorter average moves above a longer average. Traders often interpret it as improving trend momentum. A **death cross** is when a shorter average moves below a longer average. Traders often interpret it as weakening momentum. Both signals lag: by the time the crossing appears, much of the move may already have happened. In a sideways market they can cross repeatedly and produce losses.

Use a crossover as a filter, not an entry command. Ask whether the averages are sloping, whether price is making HH/HL or LH/LL, whether the move has volume, and where the idea is invalidated. A bullish crossover inside a broad downtrend is weaker than one supported by a higher-timeframe breakout and a successful pullback.

## 2. MACD in plain language

MACD compares a faster EMA with a slower EMA. The **MACD line** shows the gap between them. The **signal line** is a smoothed version of that gap. The **histogram** shows the distance between the two lines. When the histogram grows, the difference is widening; when it shrinks, momentum may be cooling.

A MACD line crossing above its signal line can support a bullish momentum hypothesis. A cross below can support a bearish one. A move above or below the zero line gives another trend reference. These are clues, not guarantees. MACD is built from moving averages, so it is delayed and can be noisy when price has no clear direction.

![MACD explained](assets/macd-explained.svg)

## 3. Combining signals without counting the same evidence twice

A practical example is: daily structure is bullish, the 1-hour price holds above a rising MA(25), a pullback reaches that average, volume returns on the rebound, and MACD turns upward. This is a complete hypothesis only after defining entry, stop, target, size, and invalidation. It is not stronger merely because several indicators flash green; MA and MACD both derive much of their information from price.

Avoid stacking SMA, EMA, MACD, RSI, and multiple crossover settings until the chart looks certain. Choose a small rule set, test it across many market regimes, include fees and slippage, and record losing examples. A signal that cannot be defined before the outcome cannot be tested honestly.

## 4. Common mistakes

- Treating a golden cross as proof that price must rise.
- Treating a death cross as proof that a short trade is safe.
- Using a crossover on a 1-minute chart to override a strong weekly trend.
- Calling RSI “overbought” and immediately selling without checking trend context.
- Counting MACD, EMA, and a moving-average crossover as three independent signals.
- Changing periods after seeing which setting would have worked in the past.

The advanced skill is not finding the perfect period. It is knowing what a signal measures, when it tends to fail, and how small the position must be while you learn.
