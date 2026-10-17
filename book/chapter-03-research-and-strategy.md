# Chapter 3 — Welcome to the Crypto World

Learning to read K-lines and indicators is only the beginning. Many beginners go through a period of small wins followed by much larger losses. That pattern does not mean the market has a secret rule against them; it often means that a chart idea was used without a position-size rule, a loss limit, or enough testing.

Before trying to make more money, learn how to keep one bad trade from damaging your account. Build a simple money-management plan, study people whose methods are transparent and testable, and keep your own records. Learning from experienced traders can shorten the path, but no expert, influencer, or AI can remove uncertainty or take responsibility for your account.

This chapter turns those lessons into a repeatable research and strategy process. The goal is not to rush from an indicator to a trading bot. The goal is to build enough technical support, risk control, and evidence that a decision remains reasonable when the next trade loses.

## The learning path

The order matters. Risk and market mechanics come before indicators, and research comes before automation.

| Stage | Outcome | Suggested evidence of learning |
| --- | --- | --- |
| 0. Safety and habits | Avoid preventable loss | Written risk limits, wallet security checklist, trade journal |
| 1. Market foundations | Explain what is being traded | A one-page glossary and a labelled spot/futures order |
| 2. Reading price | Read candles, structure, volume and liquidity | Annotate 30 historical charts without making a trade |
| 3. Research and data | Turn a question into a test | Reproducible notebook with clean data and a benchmark |
| 4. Strategy design | Define rules and risk before entry | One-page strategy specification and paper-trading log |
| 5. Validation | Detect overfitting and execution problems | Out-of-sample report including fees and slippage |
| 6. Small-scale operation | Monitor, review and improve | Weekly review; no increase in size until evidence supports it |

## 1. Study material



Read selectively and take notes; none of these books is a signal service.

- **The Bitcoin Standard — Saifedean Ammous:** monetary history and Bitcoin’s thesis; treat its claims as one viewpoint.
- **Mastering Bitcoin — Andreas M. Antonopoulos:** technical Bitcoin foundations; useful even for non-developers.
- **Cryptoassets — Chris Burniske and Jack Tatar:** an older framework for valuing crypto networks; verify examples against today’s market.
- **Technical Analysis of the Financial Markets — John J. Murphy:** broad reference for charting and market structure.
- **Trading in the Zone — Mark Douglas:** process, uncertainty and discipline.
- **Systematic Trading — Robert Carver:** position sizing, diversification and portfolio-level thinking.
- **Advances in Financial Machine Learning — Marcos López de Prado:** research design and leakage/overfitting warnings; read after basic statistics and programming.

Free references: [Bitcoin developer documentation](https://developer.bitcoin.org/), [Binance Academy topics](https://academy.binance.com/en/articles), and exchange documentation for the venue you actually use.

## 3. A practical quant toolkit

Use the smallest stack that answers the question.

| Need | Starting tool | Why |
| --- | --- | --- |
| Learn Python/data | Python, Jupyter, pandas, NumPy, matplotlib | Transparent and widely supported |
| Get exchange data | Exchange REST/WebSocket API; CCXT for a common interface | CCXT provides a unified API across many exchanges ([docs](https://docs.ccxt.com/docs/)) |
| Indicators | pandas plus a small indicator library | Keep formulas inspectable; avoid black boxes |
| Fast research/backtests | vectorbt | Vectorized pandas/NumPy backtesting with Numba/Rust acceleration ([docs](https://vectorbt.dev/)) |
| Event-driven simulation/live framework | LEAN/QuantConnect | Explicit securities, orders, fees, slippage and crypto datasets ([docs](https://www.quantconnect.com/docs/v2/writing-algorithms)) |
| Storage | Parquet files first; PostgreSQL/TimescaleDB later | Cheap, reproducible history before adding infrastructure |
| Monitoring | Git, experiment metadata, logs and a simple dashboard | Every result must be reproducible |

Minimum research hygiene:

- timestamp everything in UTC and record the exchange, symbol and contract type;
- separate training, validation and final test periods;
- include fees, funding, spread, slippage, rejected/partial orders and downtime;
- compare with buy-and-hold and a cash benchmark;
- keep a frozen test set and do not tune against it;
- use paper trading before live keys, and keep live keys unable to withdraw.

## 4. What professional quant teams generally do

The goal is not to imitate a bank’s infrastructure. Learn the research loop:

1. **Data engineering:** normalize trades, candles, quotes, funding, open interest and on-chain data; detect gaps and bad prints.
2. **Signal research:** test hypotheses such as trend/momentum, cross-sectional relative strength, mean reversion, volatility or market-making inventory signals.
3. **Portfolio construction:** combine signals, cap exposure by asset/sector/venue, and size positions by volatility and risk budget.
4. **Execution:** choose order types, split orders, model market impact, monitor latency and reconcile fills.
5. **Risk and controls:** liquidation buffers, concentration limits, kill switches, key management, independent monitoring and incident logs.
6. **Validation and deployment:** walk-forward tests, out-of-sample evaluation, shadow/paper deployment, canary sizing, then gradual rollout.

Machine learning belongs late in this sequence. A simple, stable signal with realistic execution is more valuable than a high-scoring model that leaks future information.

## 5. Building your own strategy

Choose a holding period that fits your life, capital, costs and temperament:

- **Long-term allocation:** monthly/quarterly review; thesis, custody and rebalancing matter more than chart entries.
- **Swing/trend:** days to weeks; define regime, entry, stop, target/exit and overnight/event risk.
- **Short-term/systematic:** minutes to days; requires reliable data, low costs, execution discipline and time to monitor.

Write the following before looking at recent results:

```text
Hypothesis: What repeatable behavior might create an edge?
Universe: Which symbols/contracts are eligible, and why?
Regime: When is the strategy allowed to trade?
Entry: Exact, testable conditions.
Exit: Stop/invalidation, profit-taking, time stop and emergency exit.
Sizing: Risk per trade, leverage cap and portfolio exposure cap.
Costs: Fees, spread, slippage, funding, borrow and taxes where applicable.
Evaluation: Benchmark, expectancy, Sharpe/Sortino, max drawdown, turnover,
            profit factor, exposure, number of trades and worst streak.
Failure plan: What result or operational event disables the strategy?
```

Then run: historical test → walk-forward/out-of-sample test → paper trading → tiny controlled deployment → scheduled review. Change one assumption at a time, record it, and retire a strategy when its invalidation conditions are met.

## A 12-week beginner project

1. Weeks 1–2: security, custody, spot vs derivatives, orders, fees and a glossary.
2. Weeks 3–4: annotate candles, market structure, volume and volatility on 30 charts.
3. Weeks 5–6: Python basics; download BTC/ETH spot candles; clean and visualize them.
4. Weeks 7–8: code one simple trend or mean-reversion rule; compare it with buy-and-hold.
5. Weeks 9–10: add realistic fees/slippage, out-of-sample testing and a trade journal.
6. Weeks 11–12: paper trade, review execution and risk, and decide whether the strategy deserves further research.

## Suggested repository structure

```text
data/          # downloaded data, never hand-edited
notebooks/     # exploratory research
src/           # reusable data, signals, sizing and execution code
strategies/    # versioned strategy specifications
reports/       # backtest and weekly review output
docs/          # glossary, checklists and lessons
```

The first useful contribution is a glossary, a reproducible notebook, and a strategy specification—not a trading bot.

---

