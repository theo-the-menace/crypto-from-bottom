# Chapter 1 — Foundations: from crypto to a real trading decision

## Chapter map

1. [What is crypto?](#1-what-is-crypto)
2. [What a real CEX looks like](#2-what-a-real-cex-looks-like)
3. [Foundations: reading K-lines and market structure](#3-foundations-reading-k-lines-and-market-structure)
4. [The essence of making money](#4-the-essence-of-making-money)
5. [Binance app field guide](#5-binance-app-field-guide)

This chapter answers a simple question: what exactly are you looking at when you open Binance? A token, an account balance, an order book, a derivative, and a wallet transaction are different things. Confusing them is one of the fastest ways for a beginner to lose money.

---

## 1. What is crypto?

### 1.1 A useful definition

“Crypto” is a broad name for digital assets and networks that use cryptographic techniques to control ownership, authorize transactions, and coordinate a shared ledger. It is not one asset class with one behavior. Bitcoin, a stablecoin, an exchange token, a governance token, an NFT, and a perpetual future can all appear in a crypto app while carrying different economic and technical risks.

Separate four layers:

1. **Network:** the distributed system that records state and validates transactions (for example Bitcoin, Ethereum, Solana, or BNB Smart Chain).
2. **Asset:** a native coin or token represented on that network.
3. **Application:** a wallet, exchange, lending protocol, game, bridge, or other software that uses the network.
4. **Claim or contract:** an off-chain account balance, tokenized exposure, option, future, or perpetual whose value depends on an issuer or venue.

The same ticker can be misleading. BTC held in a Binance Exchange account is a custodial account claim until withdrawn; BTC held in a self-custody wallet is controlled by whoever can sign the transaction; BTCUSD perpetual exposure is a derivative and does not give ownership of BTC.

### 1.2 Why this matters for the market

Knowing what the thing is tells you what can make or destroy its value:

- A **spot token** is exposed to price, liquidity, custody, contract, and network risks.
- A **stablecoin** seeks a stable reference value but has reserve, issuer, redemption, de-peg, regulatory, and liquidity risks.
- A **perpetual future** adds leverage, funding, mark-price, liquidation, counterparty, and basis risks.
- A **DeFi position** adds smart-contract, oracle, bridge, governance, and wallet-approval risks.
- An **exchange balance** adds platform solvency, account-security, withdrawal, and jurisdiction risks.

Markets are prices formed by participants trading these exposures. The chart is only the visible output. The cause may be new information, forced liquidation, funding pressure, a token unlock, a change in liquidity, a protocol failure, or a change in risk appetite. If you cannot name the exposure, you cannot interpret the chart responsibly.

### 1.3 A beginner’s identification checklist

Before researching a symbol, write:

- What is the exact product: spot, margin, perpetual, dated future, option, earn product, or on-chain token?
- What is the base asset and what is the quote/collateral asset?
- Who controls custody and who can stop withdrawals?
- What creates demand for the asset or contract?
- What creates new supply, dilution, funding payments, or forced selling?
- Which risks can make the position untradeable, not just cheaper?

This is not paperwork. It prevents the common error of using a spot intuition on a leveraged derivative or treating a marketing label as fundamental information.

---

## 2. What a real CEX looks like

A **centralized exchange (CEX)** is a company-operated venue that normally combines account management, custody, asset transfer, price discovery, order matching, settlement, and risk controls. Binance is a large example, but the same anatomy appears on other exchanges. A CEX is convenient because it hides blockchain mechanics; that convenience creates custody and platform dependence.

### 2.1 The account and wallet layer

The app may show Exchange, Spot, Funding, Futures, Earn, and other subaccounts. These are internal ledgers maintained by the exchange. Moving assets between them is usually an internal transfer, not a blockchain transaction. A withdrawal to a network address is different: it needs a chain, a destination address, a network fee, and confirmation.

The exchange can credit a balance instantly in its internal ledger, but an on-chain withdrawal waits for network processing and may be delayed, reviewed, or suspended. Always check the destination network. Sending an asset through the wrong network can make recovery difficult or impossible.

### 2.2 The market-data layer

A trading screen is assembled from several feeds:

- **Last price:** the most recent matched trade; it is not necessarily executable for your size.
- **Bid/ask:** the best currently displayed buying and selling prices.
- **Spread:** ask minus bid; it is an immediate execution cost for crossing the book.
- **Order book/depth:** resting limit orders at different prices. Displayed liquidity can disappear.
- **Candles:** time-bucketed OHLC summaries, often with volume.
- **Mark/index price:** derivative reference prices used under product rules for risk and liquidation.
- **24-hour change/volume:** a rolling or venue-defined summary, not a prediction.

A chart compresses these streams into visual history. It does not show your likely fill, the amount of hidden liquidity, or whether a displayed order will remain.

### 2.3 The matching layer

When you submit an order, the exchange validates account permissions, minimum quantity, tick size, available balance, and product rules. An order then enters a matching engine or triggers another order. The engine matches compatible bids and asks under its priority rules. Your result may be one fill, many partial fills, a rejection, or an order that stays open.

**Maker** orders add liquidity to the book; **taker** orders remove existing liquidity. Fees often differ. A limit order is not automatically a maker order: if it crosses existing liquidity, it can execute immediately as a taker.

### 2.4 The risk and settlement layer

Spot settlement transfers the exchange’s internal claim from one balance to another. Derivatives settlement continuously calculates collateral, unrealized PNL, fees, funding, maintenance margin, and liquidation risk. The risk engine may cancel orders, reduce positions, or liquidate according to contract rules. Read the contract specification instead of inferring behavior from a screenshot.

### 2.5 The interface anatomy

Most CEX screens contain:

1. **Navigation:** Markets, Trade, Futures, Assets, Earn, P2P, and account/security settings.
2. **Instrument selector:** symbol, quote currency, contract type, and sometimes settlement asset.
3. **Chart:** timeframe, indicators, drawings, and price scale.
4. **Order book and recent trades:** current displayed liquidity and matched activity.
5. **Order ticket:** side, order type, price, quantity, time-in-force, and optional TP/SL.
6. **Open orders and history:** what is waiting, what filled, and what was cancelled.
7. **Margin/balance panel:** available funds, locked funds, collateral, and estimated liquidation data.

Read the ticket from top to bottom before submitting: product, symbol, side, order type, trigger source, price, amount, leverage/margin mode, reduce-only, fee estimate, and final confirmation.

### 2.6 What a CEX cannot promise

A CEX cannot promise that a market order fills at the number on your chart, that a stop-limit exits during a gap, that a displayed order-book wall is real support, or that a yield product preserves principal. It also cannot remove the risk of phishing, API-key leakage, account takeover, or a chain/network mistake. Convenience is not certainty.

---

## 3. Foundations: reading K-lines and market structure

A K-line (candlestick) records four prices for one interval: **open, high, low, close (OHLC)**. The body connects open and close; the upper and lower wicks reach the high and low. A candle is a description of what happened, not a cause and not a command to buy or sell.

![Anatomy of a K-line](assets/kline-anatomy.svg)

### 3.1 Timeframe is a lens

A 5-minute candle and a 1-day candle can describe the same market while answering different questions. Use a higher timeframe for context, an intermediate timeframe for the setup, and a lower timeframe only for execution detail. A candle that is still open can change its body and wick until the interval closes.

### 3.2 Structure: higher highs and lower lows

Market structure is a sequence of meaningful swing points, not every tiny fluctuation. A simple uptrend has a **higher high (HH)** followed by a **higher low (HL)**. A simple downtrend has a **lower high (LH)** followed by a **lower low (LL)**. A range alternates around boundaries without a reliable directional sequence.

![Higher highs and lower lows](assets/market-structure.svg)

A break of a prior swing can be informative, but it is not automatically a trend change. Ask whether the break closed beyond the level, whether volume/liquidity supported it, whether the move was quickly rejected, and whether the next pullback holds.

### 3.3 Divergence

A divergence occurs when price and a chosen indicator disagree. For example, price can print a lower low while an oscillator prints a higher low: **bullish divergence**. Price can print a higher high while the oscillator prints a lower high: **bearish divergence**.

![Bullish and bearish divergence](assets/divergence.svg)

Divergence is a change in momentum, not a guaranteed reversal. Strong trends can produce several divergences before price turns. Define the confirmation and invalidation in advance: a structure break, a close back above a level, or another rule you can test. Never use an indicator’s divergence without specifying which swing points and which oscillator settings count.

### 3.4 Context before patterns

A long wick near a well-tested range boundary means something different from the same wick in the middle of a trend. Before naming a pattern, record:

- trend, range, or transition;
- location relative to prior highs/lows and volume zones;
- volatility and liquidity conditions;
- news or scheduled events;
- invalidation level and position size;
- what would confirm or disprove the idea.

Use indicators sparingly. One trend measure, one volatility measure, and volume are enough to begin. Adding correlated indicators can make a chart look certain while adding no independent information.

### 3.5 A reading exercise

Open a historical chart with the future hidden. Mark the last five meaningful swing highs and lows. Label each as HH, HL, LH, or LL. Add the timeframe, current regime, nearest invalidation level, and one alternative interpretation. Only after writing those notes reveal the next candles. This trains observation without hindsight.

---

## 4. The essence of making money

### 4.1 Can we really predict the market?

Usually we cannot predict the next price with certainty. A trading strategy can still make money if it has positive expectancy: across many trades, its average outcome after fees and slippage is positive. The useful question is not “Will this candle go up?” but “Under what conditions does this rule have a small, repeatable advantage, and how much can I lose while testing it?”

A strategy can win with a low win rate if winners are sufficiently larger than losers. It can also lose with a high win rate if one large loss erases many small wins. This is why expectancy, drawdown, risk of ruin, and execution costs matter more than a screenshot of a winning trade.

### 4.2 Analyst and K-line reading

Chart analysis is a way to form conditional hypotheses about trend, liquidity, momentum, and risk. It is useful when the rules are explicit and tested. It fails when a person retrofits a story to a completed chart, changes the pattern definition after each loss, or treats a familiar shape as a law of nature.

Write the setup before the outcome: instrument, timeframe, entry, invalidation, exit, size, and what would make you skip the trade. If two analysts cannot tell whether the rule triggered, it is not yet a strategy.

### 4.3 News and fundamentals

News can change the distribution of outcomes, but a headline alone does not tell you whether the market already priced it in, how crowded the trade is, or how liquidity will behave. Follow primary sources where possible: protocol releases, governance decisions, filings, official exchange notices, token-unlock schedules, and macroeconomic data. Record the timestamp and the market’s reaction rather than trading the headline’s emotional tone.

Fundamental research asks what supports value or demand: network usage, fees, security, supply schedule, treasury, competition, governance, regulation, and dependency on an issuer or venue. Fundamentals can be slow-moving while price is driven by leverage and positioning in the short term.

### 4.4 Quantitative research

Quant is not a magic prediction machine. It is a disciplined way to turn a hypothesis into data, rules, tests, and execution assumptions. A beginner can start with a simple moving-average trend rule or volatility filter. A professional workflow usually includes clean timestamped data, a benchmark, train/validation/test separation, realistic fees and slippage, walk-forward testing, paper trading, monitoring, and a kill switch.

Machine learning comes late. A model can memorize noise, leak future information, exploit bad data, or produce signals that cannot be executed. A simple strategy that survives unseen data and realistic costs is more valuable than a complex model with an impressive backtest.

### 4.5 Where returns actually come from

A sustainable edge must come from a reason participants pay you to take risk or provide a service. Examples include bearing inventory risk as a market maker, supplying liquidity, harvesting a documented risk premium, reacting faster to public information, or exploiting a temporary behavioral/structural inefficiency. Every edge competes with fees, slippage, adverse selection, other traders, changing regimes, and your own operational mistakes.

The complete money-making equation is:

`net result = signal edge − fees − spread − slippage − funding/borrow − errors − taxes (where applicable)`

Risk management does not create an edge, but it determines whether you remain alive long enough to learn whether an edge exists.

### 4.6 Four questions before every trade

1. What is the product and what exactly do I own or owe?
2. What is my testable reason for entering now?
3. Where am I wrong, how much will that cost, and how will execution behave?
4. What evidence will make me stop, reduce size, or retire the idea?

If the answer is “because it is going up,” you have described recent price action, not a complete strategy.

---


Crypto From Bottom is a structured, practice-first path for people who are new to crypto, have lost money, and want to build durable skills instead of chasing signals.

> **Scope:** education only. Crypto is volatile, leveraged products can lose more than the initial deposit, and no section of this project is a promise of returns. Start with paper trading and money you can afford to lose.

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
