# Advanced — A Spot Trading Strategy

This article develops a spot trading strategy from market context to entry, position size, stop, exit, and review. It starts with BTC because a beginner should reduce unknowns before adding more assets.

## 1. Trading strategy analysis

A trading strategy is a set of rules for deciding when to buy, when to wait, how much to hold, and when to sell. No strategy guarantees profit. A historical result can disappear after fees, slippage, taxes, survivorship bias, or a change in market regime.

The strategies below have produced profitable results in some markets or historical samples. That makes them useful research starting points, not promises that a beginner can copy for guaranteed returns.

### 1.1 Dollar-cost averaging

**Dollar-cost averaging (DCA)** invests a fixed amount on a schedule instead of trying to choose one perfect entry. For example, a person might buy the same amount of BTC every week and keep a separate rule for when to stop, reduce, or sell.

DCA can reduce the emotional pressure of choosing one entry and spreads purchases across different prices. Binance's [DCA guide](https://www.binance.com/en/academy/articles/dollar-cost-averaging-dca-explained) explains this use while also warning that DCA does not remove loss risk. It can underperform a lump-sum purchase in a steadily rising market, and it cannot protect against a long decline. Frequent small orders can also add fees.

DCA is closer to a long-term accumulation plan than to active trading. It is useful for someone with regular income, a long holding horizon, and no need to predict the next few candles. It still needs an allocation limit, a review date, and an exit or rebalancing rule. “I will keep buying until it recovers” is not a complete strategy.

### 1.2 Trend following and time-series momentum

**Trend following** holds an asset when its own price trend is positive and reduces or leaves the position when the trend breaks. A simple version might compare BTC's daily close with a long moving average, while a more structured version might use a breakout and a volatility-adjusted stop.

The logic is that a strong move can persist longer than a trader expects. Trend following is a repeatable family of rules, not a promise that a trader can predict every turning point.

Trend following enters late by design. It can give back profit during a reversal and lose repeatedly when price moves sideways. It is a strong research candidate for BTC because the rules can be tested on daily or weekly candles without predicting an exact top or bottom.

### 1.3 Breakout and pullback

A **breakout and pullback strategy** waits for price to close beyond a clearly marked range or resistance level. Instead of buying the first fast candle, the trader waits to see whether the old resistance becomes support during a pullback.

For example, if BTC closes above a daily resistance level, the trader can wait for a 4-hour pullback that holds the level and forms a higher low. The entry is considered only after that condition; the stop goes below the structure that should hold if the idea is correct.

This approach is a practical way to implement trend following. It can produce a favorable risk-to-reward when the level is important, but false breakouts are common. A wick above resistance, weak volume, or an immediate close back inside the range is not confirmation. Chasing an extended candle usually creates a worse entry than waiting.

### 1.4 Range mean reversion

A **range mean-reversion strategy** buys near established support and reduces or exits near resistance while the range remains intact. It assumes that price will return toward the middle of the range after moving too far in one direction.

Short-horizon Bitcoin research has found periods of reversal or mean reversion, but the result depends heavily on the timeframe and trading costs. A study of Bitcoin returns from 2010–2019 found evidence of mean aversion in its sample, while other intraday research reports reversal at specific frequencies. These findings do not mean that every oversold reading will bounce.

The main failure is a genuine breakout. A trader who keeps buying because price “looks cheap” can accumulate a large losing position while the old range becomes resistance. This strategy is better studied after the trader can identify a valid range, define its failure level, and stop trading it when volatility expands.

### 1.5 Cross-sectional momentum

**Cross-sectional momentum** compares several assets and buys the strongest liquid names instead of studying only one asset. A simple version might rank a selected watchlist by its recent return, then rebalance on a fixed schedule.

Some research finds momentum among groups of cryptocurrencies in certain periods. For example, [Cross-sectional Momentum in Cryptocurrency Markets](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4322637) reports that recent winners sometimes continued to outperform recent losers in its sample.

This strategy is more complicated than BTC-only trading. It needs a clearly defined asset universe, liquidity filters, ranking dates, rebalancing rules, and protection against delisted or illiquid tokens. It can also concentrate risk in one market theme because many coins move with BTC. It is a later research project, not the first strategy a beginner should trade.

### 1.6 Which strategy should we develop first?

For an ordinary person trading BTC spot, this book will develop a **regime-filtered trend and pullback strategy**. It combines the most teachable parts of the strategies above:

1. Use the weekly or daily chart to classify the environment.
2. In a clear bullish regime, look for a planned pullback or a confirmed breakout rather than chasing a rising candle.
3. Use the 4-hour chart to refine the entry and confirm that the relevant level holds.
4. Use MA, MACD, RSI, volume, and ATR as supporting evidence, not as independent promises.
5. Place the invalidation stop below the higher low or support that the hypothesis depends on.
6. Reduce exposure or stay in USDT when the higher-timeframe structure is bearish or unclear.

This approach is deliberately unexciting. It gives a spot trader a way to participate in a sustained bull trend, remain mostly in cash during a bear trend, and avoid treating every 5-minute movement as an opportunity. It will still lose during false breakouts and sideways markets. Its value must be measured by a journal and a realistic backtest, not by one successful BTC trade.

The evidence is not unanimous. One study of 143 cryptocurrencies from 2014–2018 found no significant momentum payoff, while other studies found momentum in different periods and designs; see [Cryptocurrencies and Momentum](https://www.sciencedirect.com/science/article/pii/S0165176519301077). This disagreement is useful because it shows why a strategy must be tested out of sample instead of accepted because one paper or one backtest looks impressive.

## 2. What “profitable” must mean

A strategy is not proven by a high win rate or by one large gain. Measure expectancy after fees and slippage:

```text
expectancy = (win rate × average win)
           − (loss rate × average loss)
           − average trading costs
```

Also record the longest losing streak, maximum drawdown, number of trades, and the market regimes in which the method worked or failed. A strategy that earns money only during a bull market is not automatically broken; it may need a rule that keeps it out of bear markets. A strategy that works only after repeated parameter changes may be curve-fitted.

The next sections will turn the BTC trend-and-pullback idea into precise rules, test examples on historical charts, and compare it with DCA and range trading without pretending that any strategy can predict every market move.
