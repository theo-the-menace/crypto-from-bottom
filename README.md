# Crypto From Bottom

Crypto From Bottom is a structured, practice-first path for people who are new to crypto, have lost money, and want to build durable skills instead of chasing signals.

> **Scope:** education only. Crypto is volatile, leveraged products can lose more than the initial deposit, and no section of this project is a promise of returns. Start with paper trading and money you can afford to lose.

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

## 1. Foundations you should know first

### Assets and market structure

- **Bitcoin, tokens and stablecoins:** understand native assets, utility/governance tokens, and the risks of stablecoin de-pegs.
- **Spot, margin and perpetual futures:** spot has no liquidation from leverage; derivatives add funding, liquidation, basis and counterparty risk.
- **Centralized and decentralized exchanges:** compare custody, smart-contract risk, liquidity, fees and withdrawal controls.
- **Wallets and custody:** seed phrases, hardware wallets, phishing, approvals, withdrawal allowlists and the rule that an API key should never have withdrawal permission.
- **Market orders and limit orders:** a market order prioritizes execution; a limit order prioritizes price and may not fill.
- **Bid, ask, spread and order book:** the spread is the gap between the best bid and ask; visible liquidity can be cancelled and is not a guarantee of support.
- **Fees and execution:** maker/taker fees, funding, slippage, latency and partial fills change the result of every strategy.

### Candlesticks (K-lines)

For each candle, **open, high, low, close** (OHLC) describe one interval. The body is open-to-close; wicks show the extremes. A green candle does not mean “buy”: interpret it in context.

Learn to mark:

1. timeframe and session context;
2. swing highs and lows;
3. trend, range and transition;
4. support/resistance as zones, not exact lines;
5. volume and volatility expansion/contraction;
6. invalidation: the price level that proves the idea wrong.

Indicators summarize price; they do not create certainty. Start with one trend measure (for example, moving average), one volatility measure (ATR), and volume. Avoid stacking correlated indicators.

### Risk vocabulary

- **R:** the amount lost if the stop is hit. Express results in R so trades are comparable.
- **Position size:** `size = account risk / stop distance`; calculate before entry.
- **Expectancy:** `win rate × average win − loss rate × average loss`.
- **Drawdown:** peak-to-trough loss. Set a maximum daily and total drawdown before trading.
- **Risk of ruin:** repeated losses and leverage can make recovery mathematically impossible. A small fixed risk per trade and a hard leverage limit matter more than a clever entry.

## 2. Books and study material

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

# Binance app field guide (beginner edition)

The screenshots in this project show several very different products inside one app. A shared interface does **not** mean shared risk: buying BTC on Spot, exchanging through Convert, holding BTC in a wallet, and opening a BTC perpetual future are different actions with different rights, costs and failure modes. Menu names and availability vary by country, account and app version. Check the current order preview and product terms before confirming anything.

## First: identify which product you are looking at

| Screen / label | What it does | Beginner interpretation |
| --- | --- | --- |
| **Markets** | Lists assets, prices, 24-hour changes and trading pairs | Discovery and comparison, not a recommendation list |
| **Convert** | Quotes an asset-for-asset exchange | Convenient quote; compare its rate and spread with Spot before accepting |
| **Spot** | Buys/sells the asset itself against another asset, such as BTC/USDT | Start here to learn orders; there is no futures liquidation, though the asset can lose value |
| **Futures: USDⓈ-M** | Derivatives margined/settled in a stablecoin such as USDT | Leverage, funding, margin and liquidation; advanced and high risk |
| **Futures: COIN-M** | Derivatives margined/settled in a crypto asset | Collateral value can fall at the same time as the position; advanced and high risk |
| **Assets / Exchange** | Account balances held with the exchange | Custodial: access depends on the exchange and account |
| **Wallet** | On-chain, self-custody wallet interface | You control signing; transactions and smart-contract approvals can be irreversible |
| **P2P** | Users trade directly, with platform escrow/processes | Payment and counterparty rules matter; follow the platform flow and never release crypto outside it |
| **Earn** | Product family that may lend, stake or otherwise deploy assets | Yield is compensation for risk, not a bank deposit or guaranteed return |

Do not assume the app’s green PNL figure is cash already secured. A portfolio value, “today’s PNL,” and unrealized PNL can move with price, exchange rates, fees and the app’s calculation method. Learn where the number comes from before using it to judge performance.

## A. Home and account overview

The Home screenshot combines estimated total value, today’s PNL, quick actions (Add Funds, Send, Transfer, Earn, P2P, Convert, API Management) and promotional or discovery cards. Treat this as a navigation dashboard, not a neutral research feed.

- **Estimated total value:** an estimate converted into a display currency. It is not a withdrawal quote and can change with market prices.
- **Today’s PNL:** a period-specific figure. Find the product’s definition, time boundary and whether it includes fees; do not confuse it with your total return.
- **Add funds / Send:** funding and withdrawals have network, address, minimum and possible compliance requirements. Always verify the chain and address; a correct token on the wrong chain can be unrecoverable.
- **Transfer:** often moves assets between internal account wallets. Internal transfer is not the same as an on-chain withdrawal.
- **API Management:** creates machine access. A key can give software authority over your account. Use the narrowest permissions, IP restrictions where available, no withdrawal permission, and revoke unused keys.
- **Earn / campaign / rewards:** read lockup, redemption, counterparty, token and loss terms. A reward banner is marketing, not an investment thesis.

Before depositing, check that the exchange entity and product are available in your jurisdiction, understand custody risk, enable strong account security, and test a small withdrawal if appropriate.

## B. Markets and the asset list

The Markets screen shows a search bar, categories, favorites/holdings, last price and 24-hour change. A 24-hour percentage is a rolling snapshot (or the app-defined daily window), not a forecast. A large move may mean higher volatility and worse execution, not a better opportunity.

For any coin, investigate before buying:

1. **Pair and quote asset:** BTC/USDT means the price is quoted in USDT per BTC; it is not BTC/USD exactly.
2. **Liquidity:** inspect 24-hour traded volume and the live bid/ask spread. A displayed volume number does not tell you how much you can sell near the shown price.
3. **Market depth:** the order book displays resting limit orders. Orders can be cancelled, and visible depth can change quickly.
4. **Supply and unlocks:** circulating supply, total/max supply, vesting and emissions can affect dilution. “Low price per coin” does not mean cheap valuation.
5. **Project and custody risks:** understand the network, token purpose, contract/address, governance, bridge exposure and exchange listing status.
6. **Your thesis and invalidation:** write why it belongs in your portfolio and what evidence would make you change your mind.

Avoid selecting assets only because they appear in Trending, Alpha, Prediction, Smart Money or a high-gain list. Those surfaces can amplify recency bias and illiquid assets.

## C. Convert: what the first screenshot is showing

The screenshot shows **Instant** selected, USDT in the “From” field and BTC in the “To” field. Convert asks for an input amount and previews how much of the output asset you would receive. The `>` amounts in the image indicate minimums/placeholder constraints in that screen state; they are not a promise of a trade price.

- **Instant:** accepts a quote that may be available only briefly. Review the quote and final received amount before confirming.
- **Recurring:** schedules repeated conversions. This automates timing, not risk; it can keep buying into a falling market and does not guarantee a good average price.
- **Limit:** sets a desired conversion price if the product supports it. An order may remain unfilled or be cancelled.
- **From / To:** check direction carefully. Swapping the fields changes what you sell and what you receive.
- **Preview:** compare the effective rate and received amount with the equivalent Spot order, including fees, spread, minimums and rounding.

Convert can be useful for simple swaps, but its convenience can obscure the execution rate. Do not assume “zero fee” means zero cost; the quote can include a spread. Confirm the exact received amount and any terms shown in the current app.

## D. Spot trading: the cleanest place to learn order mechanics

Spot means you exchange assets and receive/own the purchased asset in your exchange account. If you buy BTC with USDT, you now hold BTC whose value can fall. Spot avoids futures leverage and liquidation, but it does **not** protect you from price loss, exchange custody risk, stablecoin risk or mistakes.

### Read a pair and a basic order ticket

For **BTC/USDT**, BTC is the base asset and USDT is the quote asset. A buy spends quote asset to acquire base asset; a sell disposes of base asset to receive quote asset. Check the pair, side (Buy/Sell), order type, price, quantity and total before submitting.

- **Market:** seeks immediate execution against available orders. It guarantees neither the displayed last price nor a maximum slippage. Large size or thin liquidity can produce multiple fills at worse prices.
- **Limit:** you set a worst acceptable buy price or minimum acceptable sell price. It can fill at that price or better, but may not fill at all. A limit order priced through the market can execute immediately.
- **Stop-limit:** a trigger (“stop”) activates a limit order. The limit order can remain unfilled if the market moves through its price. It is not a guaranteed stop-loss.
- **Stop-market / stop-loss market (where available):** a trigger activates a market order. It prioritizes exit after triggering but the fill can be worse than the trigger in a fast market.
- **OCO (where available):** links a take-profit limit and a stop-limit condition; when one executes/triggers under the product’s rules, the other is cancelled. Understand the exact trigger behavior and partial fills.
- **Trailing stop / advanced order types:** rules and availability differ by product. Simulate with tiny size or paper trading before relying on them.

### Candlesticks (K-lines) and chart controls

The Futures screenshot shows an 8-hour BTCUSD COIN-M perpetual chart with MA(7), MA(25), MA(99), a displayed last price and a price scale. A candle on an 8-hour chart summarizes eight hours; switching to 1h or 1d changes the question being answered. Historical candles are not predictions.

Each candle has **open, high, low, close (OHLC)**. The body shows open-to-close; the wicks show the high and low. On most charts, green means close above open and red means close below open, but colors can be configured. Candle volume is activity during the interval, not the number of buyers versus sellers (every trade has both).

Moving averages smooth past prices. MA(7) on an 8-hour chart is based on seven 8-hour observations, not seven days. It lags by construction. A moving-average cross is a rule one can test, not a reliable standalone signal.

Learn these chart concepts in order:

1. timeframe and completed vs still-forming candles;
2. swing highs/lows and trend versus range;
3. support/resistance zones and prior reaction areas;
4. volume, volatility and gaps in liquidity;
5. invalidation level and the amount at risk if wrong;
6. how the same chart looks on a higher timeframe (context) and lower timeframe (execution).

Never infer a trade solely from an MA line, a candle name, or a level that looks obvious after the fact. Mark the chart before knowing what happened next, then test the rule on unseen data.

## E. Assets and balances

The Assets screen in the screenshots shows an estimated total value denominated in BTC, today’s PNL, allocation, crypto holdings and buttons such as Add Funds, Send, Transfer, Earn and Trade. The portfolio screenshot shows BTC, a tiny USDT balance and unrealized PNL.

- **Balance/quantity:** number of tokens held; multiply by an appropriate executable price to estimate value.
- **Unrealized PNL:** not yet realized by closing/selling; it can shrink or reverse.
- **Realized PNL:** result from completed transactions under the app’s accounting rules; fees, funding and deposits/withdrawals affect interpretation.
- **Allocation:** concentration view. A portfolio dominated by one asset has concentrated exposure even if it contains multiple tokens with similar behavior.
- **Wallet tabs:** Exchange, Funding, Spot, Futures, Earn and other subaccounts may have separate balances. An asset shown in one wallet might need an internal transfer before use elsewhere.
- **BTC-denominated view:** when the display unit is BTC, a stablecoin balance can show a BTC equivalent that changes with BTC price. Use a consistent numeraire when measuring performance.

Keep a ledger of deposits, withdrawals, transfers, fees, conversions and trades. Otherwise a daily PNL snapshot cannot tell you whether a strategy made money.

## F. Futures: understand the danger before touching the controls

The Futures screenshot shows **COIN-M**, `BTCUSD CM Perp`, **Cross**, **125x**, a Limit order ticket, funding/countdown, order book, available balance and TP/SL controls. These are not beginner settings. The 125x label is leverage availability/setting, not a return multiplier you should target. High leverage leaves little room for adverse movement, fees and mark-price changes.

### USDⓈ-M vs COIN-M

- **USDⓈ-M:** contracts are margined/settled in a stablecoin such as USDT (exact contract rules vary).
- **COIN-M:** collateral and settlement are in a crypto asset. If BTC falls, the collateral’s value can fall while a position is losing.
- **Perpetual:** no ordinary expiry date; funding payments between long and short sides help keep the contract near its reference market. Funding rate and interval can change. You may pay or receive funding.
- **Delivery/dated future:** has an expiry and settlement rules. It is not the same instrument as a perpetual.

### Margin mode, leverage and liquidation

- **Isolated margin:** margin is assigned to that position under the product’s rules. It can limit the collateral exposed to that position, but liquidation can still lose the isolated margin and fees; verify settings and auto-add-margin options.
- **Cross margin:** eligible balance in the futures wallet may support positions collectively. A loss can consume much more of that wallet balance than the initial margin for one position.
- **Leverage:** not a way to make a weak strategy good. It magnifies exposure relative to collateral; losses, fees and funding are calculated on notional exposure.
- **Maintenance margin / liquidation:** if account equity falls below required maintenance levels, the exchange may liquidate. Liquidation is not necessarily at your stop price and can include fees or insurance-fund mechanics.
- **Mark price vs last price:** mark price is used in risk/liquidation calculations under contract rules; last traded price is the most recent match. A chart trigger source selector (Last/Mark) matters.
- **Funding:** periodic payment based on position notional and funding rate; holding through multiple intervals can materially change results.

### Futures order ticket anatomy

- **Open / Close:** choose whether an order increases or reduces exposure. Check reduce-only/close-position behavior when available.
- **Limit / Market:** same trade-off as Spot, with derivative-specific contract sizing and margin consequences.
- **Price and Amount (Cont):** contract count may not equal BTC quantity or USDT notional. Read the contract specification and estimated notional.
- **Order book:** red asks and green bids represent resting liquidity, not guaranteed future support/resistance.
- **TP/SL:** take-profit and stop-loss conditions. Verify trigger source (Last/Mark), order type after trigger, quantity, reduce-only behavior and whether both are attached to the whole position.
- **Available balance / Max Open:** an interface limit, not a suggested position size.

Before any derivatives exposure, be able to calculate notional, initial/maintenance margin, fees, funding, stop loss in account currency and worst plausible gap/slippage. Use testnet or paper simulation first. This guide does not recommend opening a Futures position.

## G. P2P, Earn and other home-screen products

- **P2P:** inspect advertiser history, payment method and local rules. Pay only using the exact method and name required by the offer; do not accept off-platform arrangements. Never release crypto based on a screenshot or message—verify settled payment in your bank/payment account and follow the platform dispute process.
- **Earn:** distinguish flexible vs locked products and understand whether returns arise from lending, staking, validators, counterparties or promotional incentives. Check redemption delay, slashing, asset de-peg, platform and smart-contract risk. Yield can be variable and principal can be at risk.
- **Prediction / Alpha / Smart Money / trending:** these labels are product or discovery categories, not evidence of expected return. Identify whether the product is a token, derivative, game, prediction contract or curated listing before interacting.
- **Stocks / tokenized exposures:** establish the legal instrument, issuer, rights, trading hours, redemption mechanism and jurisdiction. A similar price chart does not mean you own the underlying share.

## H. Binance Wallet / Wallet tab and on-chain basics

The final screenshot is the app’s Wallet side, with “Set Up Wallet,” chain filters and trending tokens. This is an on-chain discovery and self-custody surface, separate from the exchange account balance. Product design (for example MPC/key recovery) can change; read the current wallet documentation and recovery flow rather than assuming it works like a seed-phrase wallet.

Before an on-chain transaction:

1. confirm the exact chain (Ethereum, Solana, BNB Smart Chain, etc.) and token contract/address;
2. confirm recipient address and whether the destination supports that asset/network;
3. understand network/gas fees and leave enough native token for future transactions;
4. inspect the transaction simulation and each permission/approval requested;
5. be wary of unlimited token approvals, fake tokens, airdrops, copied addresses and urgent messages;
6. make a small test transfer when appropriate, then verify on the correct block explorer;
7. secure recovery credentials and never share a seed phrase, private key, recovery code or screen share with a stranger.

Swaps and bridge transactions can be irreversible and add smart-contract, liquidity, bridge, MEV and token risks. “Trending” can include newly created, manipulated or malicious tokens. Do not connect a wallet or sign a transaction just to claim an unsolicited reward.

## I. Practice with the screenshots (no money required)

Use screenshots or a demo/testnet environment to answer these before you ever submit a real order:

1. Which screen represents ownership of BTC, and which represents a BTC derivative?
2. On Convert, how many BTC will the preview deliver for a fixed USDT amount, and what effective rate does that imply?
3. On Spot, what happens if a buy limit is above the current ask? What happens if it is below and the market never reaches it?
4. What is the timeframe of the chart candle? Are you reading a closed candle or one still moving?
5. In the Futures ticket, what does Cross mean, where is the collateral, and what price source triggers liquidation?
6. Which wallet/subaccount contains the funds? Is a transfer internal or on-chain?
7. What exact risks and permissions would a Wallet swap or API key introduce?

If any answer is unclear, stop at the preview screen and look up the relevant product documentation. The skill is knowing what the button will do before pressing it.

## Official Binance references

Interface details and product availability change. These official references are starting points, not a replacement for the terms and order preview shown in your own account:

- [Binance Spot trading guide](https://academy.binance.com/en/articles/your-guide-to-binance-spot-trading)
- [Binance Spot order types](https://www.binance.com/en/support/faq/different-order-types-in-spot-trading-8a2973eef1de429dbfad38ab878aa3eb)
- [Binance Academy: order types](https://academy.binance.com/en/articles/what-order-types-can-you-use-on-binance)
- [Binance developer: Spot glossary](https://developers.binance.com/en/docs/products/spot/faqs/spot_glossary)
- [Binance Academy: Binance Wallet](https://academy.binance.com/en/articles/what-is-binance-web3-wallet-and-how-does-it-work)
- [Binance Support: Coin-M leverage and margin](https://www.binance.com/en/support/faq/detail/be2c7d9d95b04a7e8044ed02dd7dfe5c)

This guide explains interface concepts; it is not affiliated with Binance and does not recommend any specific asset, product or trade.
