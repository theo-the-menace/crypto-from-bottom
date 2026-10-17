# Advanced — A Spot Trading Strategy

This article develops a spot trading strategy from market context to entry, position size, stop, exit, and review. It starts with BTC because a beginner should reduce unknowns before adding more assets.

## 1. Trading strategy analysis

A trading strategy is a set of rules for deciding when to buy, when to wait, how much to hold, and when to sell. No strategy guarantees profit. A historical result can disappear after fees, slippage, taxes, survivorship bias, or a change in market regime.

The strategies below have produced profitable results in some markets or historical samples. That makes them useful research starting points, not promises that a beginner can copy for guaranteed returns.

### 1.1 How to read recent strategy research

A reported return is useful only when we know how it was produced. The strongest recent evidence for a retail BTC reader comes from studies that control for data mining, use an out-of-sample period, and include realistic trading costs.

- A 2024 study by Ghent University tested **75,360 simple technical rules** on BTC data from 2012–2022. It selected rules after costs and tested combined portfolios out of sample. The authors found that simple rules could improve risk-adjusted performance against buy-and-hold, but the study also found that older periods were more favorable and that a no-short rule could not profit directly from falling prices. Read the [published study](https://doi.org/10.1016/j.iref.2024.05.003) and its [open university record](https://biblio.ugent.be/publication/01HY3C3S169G1N6QNYR55NZMFB).
- A [2025 *Finance Research Letters* paper](https://doi.org/10.1016/j.frl.2025.107879) tested risk-managed cryptocurrency momentum. Its reported average weekly return rose from 3.18% to 3.47%, with Sharpe ratio rising from 1.12 to 1.42. The design used a two-week formation period, a one-week holding period, quintile portfolios, and long-short positions. It is evidence that volatility management may matter, but it is not a ready-made BTC spot strategy.
- A [2025 *International Journal of Finance & Economics* paper](https://doi.org/10.1002/ijfe.70036) gives the necessary warning: it finds that the tail behavior of crypto momentum can make its mean and variance statistically unreliable, so apparently generous momentum premiums may be difficult to realize in practice. High backtest returns and high risk are part of the same story.
- A [2026 multi-horizon EMA study](https://doi.org/10.15388/batp.2026.1) using volatility normalization reports 31.96% annual return for one time-series momentum design, while its cross-sectional design had a 55% maximum drawdown. It is a recent research lead, not a settled fact: its data is not yet available for independent replication and the result depends on the chosen sample and parameters.

The lesson is not to pick the largest number. It is to prefer rules that remain understandable after costs, then test them on data the researcher did not use to choose the rule.

### 1.2 Dollar-cost averaging

**Dollar-cost averaging (DCA)** invests a fixed amount on a schedule instead of trying to choose one perfect entry. For example, a person might buy the same amount of BTC every week and keep a separate rule for when to stop, reduce, or sell.

DCA can reduce the emotional pressure of choosing one entry and spreads purchases across different prices. Binance's [DCA guide](https://www.binance.com/en/academy/articles/dollar-cost-averaging-dca-explained) explains this use while also warning that DCA does not remove loss risk. It can underperform a lump-sum purchase in a steadily rising market, and it cannot protect against a long decline. Frequent small orders can also add fees.

DCA is closer to a long-term accumulation plan than to active trading. It is useful for someone with regular income, a long holding horizon, and no need to predict the next few candles. It still needs an allocation limit, a review date, and an exit or rebalancing rule. “I will keep buying until it recovers” is not a complete strategy.

### 1.3 Trend following and time-series momentum

**Trend following** holds an asset when its own price trend is positive and reduces or leaves the position when the trend breaks. A simple version might compare BTC's daily close with a long moving average, while a more structured version might use a breakout and a volatility-adjusted stop.

The logic is that a strong move can persist longer than a trader expects. Trend following is a repeatable family of rules, not a promise that a trader can predict every turning point.

Trend following enters late by design. It can give back profit during a reversal and lose repeatedly when price moves sideways. It is a strong research candidate for BTC because the rules can be tested on daily or weekly candles without predicting an exact top or bottom.

### 1.4 Breakout and pullback

A **breakout and pullback strategy** waits for price to close beyond a clearly marked range or resistance level. Instead of buying the first fast candle, the trader waits to see whether the old resistance becomes support during a pullback.

For example, if BTC closes above a daily resistance level, the trader can wait for a 4-hour pullback that holds the level and forms a higher low. The entry is considered only after that condition; the stop goes below the structure that should hold if the idea is correct.

This approach is a practical way to implement trend following. It can produce a favorable risk-to-reward when the level is important, but false breakouts are common. A wick above resistance, weak volume, or an immediate close back inside the range is not confirmation. Chasing an extended candle usually creates a worse entry than waiting.

### 1.5 Range mean reversion

A **range mean-reversion strategy** buys near established support and reduces or exits near resistance while the range remains intact. It assumes that price will return toward the middle of the range after moving too far in one direction.

Mean reversion can appear at some short horizons, but the result depends heavily on the timeframe, market regime, and trading costs. Treat an oversold reading as a setup to investigate, not as a promise that price will bounce.

The main failure is a genuine breakout. A trader who keeps buying because price “looks cheap” can accumulate a large losing position while the old range becomes resistance. This strategy is better studied after the trader can identify a valid range, define its failure level, and stop trading it when volatility expands.

### 1.6 Cross-sectional momentum

**Cross-sectional momentum** compares several assets and buys the strongest liquid names instead of studying only one asset. A simple version might rank a selected watchlist by its recent return, then rebalance on a fixed schedule.

The 2025 risk-managed momentum study above is an example: it ranked cryptocurrencies into portfolios, bought the stronger group, and compared it with the weaker group over a fixed holding period. That design is useful for research, but it requires a defined universe, regular rebalancing, and long-short execution that a basic spot account does not provide.

This strategy is more complicated than BTC-only trading. It needs a clearly defined asset universe, liquidity filters, ranking dates, rebalancing rules, and protection against delisted or illiquid tokens. It can also concentrate risk in one market theme because many coins move with BTC. It is a later research project, not the first strategy a beginner should trade.

### 1.7 Cointegration pairs trading

**Pairs trading** looks for two assets whose prices have historically moved together. When their spread becomes unusually wide, the strategy buys the relatively weak asset and sells the relatively strong one, expecting the spread to narrow. In a spot-only account, the short leg is unavailable, so a practical version must use a long-only substitute or a different product; this makes the classic pairs trade more suitable for a later research project.

A [2025 *Journal of Futures Markets* study](https://onlinelibrary.wiley.com/doi/10.1002/fut.70018) reports a risk-adjusted advantage for an optimized pairs strategy after trading costs, but its own out-of-sample note says that only 13 of 37 tested cointegrated pairs were positive. Results also depended strongly on the lookback window and on liquid, established assets. Treat this as a research direction, not as a simple “buy the dip” rule.

### 1.8 Which strategy should we develop first?

For an ordinary person trading BTC spot, this book will develop a **regime-filtered trend and pullback strategy**. It combines the most teachable parts of the strategies above:

1. Use the weekly or daily chart to classify the environment.
2. In a clear bullish regime, look for a planned pullback or a confirmed breakout rather than chasing a rising candle.
3. Use the 4-hour chart to refine the entry and confirm that the relevant level holds.
4. Use MA, MACD, RSI, volume, and ATR as supporting evidence, not as independent promises.
5. Place the invalidation stop below the higher low or support that the hypothesis depends on.
6. Reduce exposure or stay in USDT when the higher-timeframe structure is bearish or unclear.

This approach is deliberately unexciting. It gives a spot trader a way to participate in a sustained bull trend, remain mostly in cash during a bear trend, and avoid treating every 5-minute movement as an opportunity. It will still lose during false breakouts and sideways markets. Its value must be measured by a journal and a realistic backtest, not by one successful BTC trade.

The evidence is not unanimous. Some recent studies report positive momentum or technical-rule results, while others show that heavy tails, drawdowns, parameter choices, and execution costs can make those profits difficult to realize. That disagreement is useful because it shows why a strategy must be tested out of sample instead of accepted because one paper or one backtest looks impressive.

## 2. What “profitable” must mean

A strategy is not proven by a high win rate or by one large gain. Measure expectancy after fees and slippage:

```text
expectancy = (win rate × average win)
           − (loss rate × average loss)
           − average trading costs
```

Also record the longest losing streak, maximum drawdown, number of trades, and the market regimes in which the method worked or failed. A strategy that earns money only during a bull market is not automatically broken; it may need a rule that keeps it out of bear markets. A strategy that works only after repeated parameter changes may be curve-fitted.

The next sections will turn the BTC trend-and-pullback idea into precise rules, test examples on historical charts, and compare it with DCA and range trading without pretending that any strategy can predict every market move.
