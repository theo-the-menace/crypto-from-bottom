# Advanced — A Spot Trading Strategy

This article develops a spot trading strategy from market context to entry, position size, stop, exit, and review. It starts with BTC because a beginner should reduce unknowns before adding more assets.

The first question is not “which indicator makes money?” It is “which repeatable behavior has some evidence behind it, and can I execute it after costs and losses?” No strategy guarantees profit. A result that looked profitable in a historical sample can disappear after fees, slippage, taxes, survivorship bias, or a change in market regime.

## 1. What has evidence behind it?

Several strategy families have produced profitable historical results in some markets or samples. They are useful research starting points, not promises.

| Strategy family | Basic idea | Why it may work | What can go wrong | Fit for a beginner |
| --- | --- | --- | --- | --- |
| **Dollar-cost averaging (DCA)** | Invest a fixed amount on a schedule instead of choosing one perfect entry. | It reduces the need to time the market and spreads the entry price. Binance describes it as a way to reduce timing pressure, while also warning that it does not remove loss risk. | A long bear market can leave the position below cost for a long time. Frequent small orders can add fees, and DCA has no automatic exit by itself. | Good for a long-term allocation plan if the trader can accept large drawdowns and has a separate exit or review rule. |
| **Trend following / time-series momentum** | Hold BTC when its own trend is positive; reduce or leave the position when the trend breaks. | Trend persistence has been documented across many asset classes. Crypto studies also report time-series momentum, although results depend on the sample and costs. | It enters late, gives back profit during reversals, and can lose repeatedly in a sideways market. | A strong research candidate because the rules can be simple and tested on daily or weekly candles. |
| **Breakout and pullback** | Wait for price to close beyond a range or resistance, then buy only if the level holds on a pullback. | It attempts to participate after buyers have shown commitment instead of guessing the bottom. | False breakouts, news spikes, and chasing an extended candle can create poor entries. | Useful as a concrete version of trend following, with clear invalidation. |
| **Range mean reversion** | Buy near established support and reduce near resistance while the range remains intact. | Short-horizon Bitcoin research has found periods of reversal or mean reversion. | A real breakout can keep moving against the position. Transaction costs can consume a small edge, and “oversold” does not mean price must bounce. | Study only after learning to identify when a range is valid and when it has failed. |
| **Cross-sectional momentum** | Rank several assets by recent strength and hold the strongest liquid names. | Research has reported momentum among groups of cryptocurrencies in some samples. | It requires a universe, ranking rule, rebalancing, liquidity checks, and protection against delisted or illiquid tokens. | A later project; it is more complex than a BTC-only plan. |

The evidence is not unanimous. One study of 143 cryptocurrencies from 2014–2018 found no significant momentum payoff, while other studies found momentum in different periods and designs. That disagreement is useful: it shows why a strategy must be tested out of sample instead of accepted because one paper or backtest looks impressive. The [AQR century-long trend-following study](https://www.aqr.com/-/media/AQR/Documents/Insights/Journal-Article/AQR-JPM-Fall-2017.pdf) gives broad evidence for trend following across asset classes; crypto-specific studies such as [Dynamic time-series momentum of cryptocurrencies](https://www.sciencedirect.com/science/article/pii/S1062940821000590), [Bitcoin intraday time-series momentum](https://onlinelibrary.wiley.com/doi/abs/10.1111/fire.12290), and [Cryptocurrencies and momentum](https://www.sciencedirect.com/science/article/pii/S0165176519301077) use different samples and reach different conclusions.

For DCA, Binance's [DCA guide](https://www.binance.com/en/academy/articles/dollar-cost-averaging-dca-explained) is a practical explanation, not independent proof that DCA will be profitable. The guide itself says that DCA can underperform a lump-sum investment in a steadily rising market and cannot protect against a persistent decline.

## 2. The basic logic we will develop

For an ordinary person trading BTC spot, the most teachable starting point is a **regime-filtered trend and pullback strategy**:

1. **Use the weekly or daily chart to classify the environment.** If BTC has a clear upward structure and rising long-term averages, look only for planned long opportunities. If the structure is bearish or unclear, keep more capital in USDT instead of forcing a long trade.
2. **Wait for a pullback or a confirmed breakout.** Do not buy simply because a candle is already rising quickly. Mark the level that should hold if the idea is correct.
3. **Use the 4-hour chart for the entry decision.** Look for a higher low, a close back above the level, and participation that is not obviously absent. MA, RSI, MACD, and volume can support the reading; they do not replace the level and structure.
4. **Place the invalidation before the order.** For a long, the stop belongs below the higher low or support that the hypothesis depends on. If that distance makes the position too large or too small for the risk plan, change the size or skip the trade.
5. **Let winners run only under a written exit rule.** Use a target, a structure break, or a trailing rule. Do not turn a short-term trade into an unplanned long-term hold because the price moved against you.

This approach is deliberately unexciting. It gives a spot trader a way to participate in a sustained bull trend, remain mostly in cash during a bear trend, and avoid treating every 5-minute movement as an opportunity. It will still lose during false breakouts and sideways markets. Its value must be measured by a journal and a realistic backtest, not by one successful BTC trade.

## 3. What “profitable” must mean

A strategy is not proven by a high win rate or by one large gain. Measure expectancy after fees and slippage:

```text
expectancy = (win rate × average win)
           − (loss rate × average loss)
           − average trading costs
```

Also record the longest losing streak, maximum drawdown, number of trades, and the market regimes in which the method worked or failed. A strategy that earns money only during a bull market is not automatically broken; it may need a rule that keeps it out of bear markets. A strategy that works only after repeated parameter changes may be curve-fitted.

The next sections will turn this logic into precise BTC rules, test examples on historical charts, and show how to compare a trend-and-pullback method with DCA and range trading without pretending that any of them can predict every market move.
