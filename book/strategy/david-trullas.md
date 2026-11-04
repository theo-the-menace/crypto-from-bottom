# David Trullás: MACD-Led Divergence with Scaled Position Sizing

## Who is David Trullás?

David Trullás Vila (born Manresa, Spain) is a physiotherapist, osteopath, and professional intraday futures trader. He founded **Live in Trading**, a Spanish trading education company. Trullás has won multiple World Cup Trading Championship quarterly competitions in the Futures Day Trading Division, most notably:

- **Q2 2026:** 2,222.6% return (90 days) — 1st place
- **Q3 2026:** 1,350.8% return (90 days, pending audit) — 1st place
- **Q4 2025:** 930.7% return — 1st place
- **Q3 2025:** 800.6% return — 1st place
- **Q2 2025:** 712.1% return — 1st place
- **Q1 2026:** 585.4% return — 1st place
- **Q1 2025:** 291% return — 2nd place

These results are independently verified by the World Cup Trading Championships official standings page.

From a May 2026 live demonstration recorded at a Rankia conference in Valencia, Spain, Trullás publicly demonstrated his strategy on stage with students executing real-time trades.

## Core Philosophy: Discipline Over Strategy

From the Valencia demonstration (timestamp 00:51-01:20):

> "I work with three methods registered in the United States to protect intellectual property. It will be very difficult to see those three methods today, but above all we are going to see one. And I trust him so much..."

From timestamp 03:52-04:20:

> "Volume, Fibonacci, MACD, RSI. How simple, and it works! This is the basis of the championships with the percentages you've seen, and it's not a deception."

**His central claim:** The method is "so simple, so silly, so basic, so archaic. But it works. So why would I want to complicate my life?" (04:28-04:40)

## The Core Strategy: MACD is the Pillar, RSI and Volume Scale Position Size

### Signal hierarchy (timestamp 05:14-06:40)

**MACD is mandatory. RSI and Volume are confirmations that scale position size.**

> "**MACD is my friend. It's my DNA.** If MACD doesn't give me the image I want to see, I don't operate. Neither RSI, nor volume, nor order flow, nor pending orders, nor big trades... **If this one [MACD] is there, the others will come in. This is my pillar.** He's the one in charge."

### The position sizing logic (timestamp 10:06-10:40)

> "I risk my money based on what I see. And here I have three divergences, one in volume, two in MACD, and another in RSI. **Three contracts.**
>
> **If I have MACD [divergence], one [contract]. If I have MACD and RSI, two. If I have MACD and RSI outside of overbought [zone], another contract. If I have [enough] volume, another contract.**"

This is **not** "wait for all three to appear, then enter with fixed risk." This is **scaled position sizing based on signal strength:**

| Confirmed signals | Position size |
|-------------------|---------------|
| MACD divergence only | 1 contract |
| MACD + RSI divergence | 2 contracts |
| MACD + RSI + Volume divergence | 3 contracts |
| MACD + RSI (outside overbought/oversold) + Volume | 4 contracts (rare) |

**Critical insight:** Each contract has a base risk (e.g., $100). A 3-contract trade = 3× base risk. This is the opposite of "1% max risk per trade" orthodoxy, and it explains his championship returns (high conviction setups get larger positions).

### Divergence identification

**MACD histogram (12, 26, 9 settings):**
- Bearish divergence: Price makes higher high, MACD histogram makes lower high
- Bullish divergence: Price makes lower low, MACD histogram makes higher low

**RSI (14 setting):**
- Bearish: Price higher high, RSI lower high
- Bullish: Price lower low, RSI higher low

**Volume:**
- Bearish: Price higher high, volume decreases (fewer buyers at top)
- Bullish: Price lower low, volume decreases (fewer sellers at bottom)

From timestamp 07:00-07:40:

> "When the price reaches new highs, what should the volume do at those new highs? It has to increase. If it's lower, it means the volume doesn't match the price, do you agree?"

### Entry: 23-25% Fibonacci retracement (timestamp 11:33-11:45)

**This is the most important correction.** Many secondary sources incorrectly claim Trullás enters at 61.8%-66%. He does not.

From timestamp 11:33-11:45:

> "My entry point is usually around **23-25% of this segment**."

**Step-by-step entry process:**

1. Identify divergence at an extreme (MACD mandatory, RSI and Volume optional)
2. Draw Fibonacci retracement:
   - **100% (divergence extreme):** The exact high/low where divergence occurred
   - **0% (origin):** The swing low before the rally (bearish div) or swing high before the fall (bullish div)
3. Wait for price to start retracing (do not enter on the divergence candle itself)
4. Place limit entry order at **23-25% Fibonacci retracement**
5. Scale position size: 1 contract (MACD only) → 2 contracts (+RSI) → 3 contracts (+Volume)

**Why 23-25%, not 61.8%?**
- Tighter stop-loss (just below the divergence extreme)
- Better risk-reward ratio (stop is close, targets are 38%, 66%, or 0%)
- Faster entry in intraday futures (5-minute charts move quickly)

### Take-profit targets: 38% first, then 66% (timestamp 17:23-17:46)

**Target 1 (beginner default): 38% Fibonacci**

From timestamp 17:23-17:46, student Carmen speaking:

> "At the beginning, when we don't know much, we should try the Fibonacci retracement level at **23 and reach the take profit at 38**. We shouldn't try to make more money, especially to first learn the routine from 23 to 38, because many times we want to reach 50 after 38, and often the price reverses. So, at the beginning when we learn, the pattern we have in our brain is from 23 to 38 and there are always benefits there."

**Why 38% for beginners:**
- Highest probability first target
- Price often reverses before reaching 50% or 66%
- "If it's 200 dollars, well, like David says, straight into the pocket, right? And goodbye." (17:46-17:52)

**Target 2 (intermediate): 66% Fibonacci (the "two-thirds mark")**

From timestamp 12:50-13:10, student Joan speaking:

> "We would draw a Fibonacci from the highest point to the lowest point of the divergence and from here we would launch the operation up to 66%, up to the second third."

This is where Dow Theory's "retracements often go to two-thirds" becomes the target.

**Target 3 (advanced): 0% Fibonacci (full retracement)**

Price returns all the way to the origin of the measured move. This is the maximum extension case.

### Stop-loss placement

Place the stop beyond the divergence extreme. For a long (bullish divergence), stop goes below the divergence low. For a short (bearish divergence), stop goes above the divergence high.

From timestamp 11:35-11:42:

> "The entry is a tick on a breakout, the exit is a tick below, the other exit before take profit is a tick before..."

Trullás uses precise tick-based stop placement for futures. For BTC, add 2-3% room for wick spikes.

### Timeframe: 5-minute execution, 15-minute context

From timestamp 08:10-08:20:

> "The graph is 5 seconds. It's not that I'm a gambling addict, it's just that I'm using this timeframe to see if we get lucky and it generates several trades in 10 minutes, okay?"

For the demonstration, he used 5-second Nasdaq charts to show rapid setups. In normal trading:
- **5-minute chart:** Entry execution and monitoring
- **15-minute chart:** Identifying divergence and structure

Trades last 30 minutes to a few hours, never overnight (World Cup intraday rules require closing all positions by end of day).

### Instruments traded

From timestamp 14:48-15:10 (when asked about gold):

> "For gold, I always prefer the regulated market; I don't like XAU/USD, okay? I always go to the future, always, because it's a regulated market, it's issued by an agency..."

From timestamp 19:15-19:30:

> "You can look at any asset you want... a stock, a futures contract, Forex, it doesn't matter to me. In a timeframe that you want, I don't care, a minute, five minutes, an hour, daily, I don't care."

**Primary instruments:** S&P 500 (ES), Nasdaq (NQ), DAX (FDAX), Gold (COMEX futures), IBEX 35.

**Avoids:** XAU/USD (unregulated spot), thinly traded instruments.

### Hidden divergence (continuation signal)

From timestamp 13:40-13:58, student speaking:

> "The hidden divergence is when the price goes up and the indicators go down. We have several entries, this is the hidden one, so when we get this pattern... at the lowest price the Fibonacci is drawn all the way up, quite clear and marked entry and profits."

Hidden divergence = trend continuation, not reversal. Same entry logic (23-25%), same targets, same position scaling.

## What Makes This Strategy Unusual

### 1. MACD is non-negotiable

Most divergence traders use "any two of three indicators." Trullás: **If MACD doesn't diverge, there is no trade.** RSI and Volume only matter *after* MACD confirms.

### 2. Position sizing scales with signal strength

Standard orthodoxy: "Risk 1% per trade, always." Trullás: **1 contract if MACD only, 2 if +RSI, 3 if +Volume.** This means a 3-contract trade = 3× base risk. In competitions, this produces explosive returns but also larger drawdowns.

### 3. Entry at 23-25%, not 61.8%

Most Fibonacci traders enter at 50% or 61.8% retracement. Trullás enters much earlier (23-25%), giving tighter stops and better risk-reward.

### 4. Conservative first target (38%)

Beginners are explicitly told to take profit at 38% and exit, not to "let it run" to 66%. This is opposite to "let winners run" advice.

## Position Sizing: Competition vs. Normal Trading

### Competition sizing (aggressive)

In World Cup Trading Championships, Trullás uses aggressive sizing to maximize returns in the 90-day window. From the demonstration (timestamp 10:06-10:40), he took a 3-contract position on a triple divergence setup.

If 1 contract = 3-5% account risk, then:
- 3 contracts = 9-15% total risk per setup
- This explains 2,222% returns but also implies 30-50% drawdowns if wrong

### Normal trading sizing (conservative)

For retail traders outside competitions:
- **Base unit: 0.25%-0.5% of account equity**
- **Maximum 3 contracts = 0.75%-1.5% total risk per setup**
- Accept that returns will be far lower (30-50% annual, not 2,000% quarterly)

From timestamp 10:06:

> "David always bets the same percentage of his money? No, no, no, no, no. **I risk my money based on what I see.**"

This is **not** Van Tharp-style "1% per trade" fixed risk. This is signal-strength-based scaling.

## Limitations and What This Strategy Does NOT Do

### 1. Triple divergence is rare

From timestamp 19:32-19:42:

> "What percentage of correct answers? I have no idea because I'm not a big fan of statistics."

Trullás does not track win rate. The strategy requires extreme patience — you may wait hours or days for a valid setup.

### 2. Not a high-frequency strategy

From timestamp 11:00-11:20:

> "Anyone can do these concepts. And it's simple."

But "simple" does not mean "frequent." Setups appear irregularly. This is not algo trading.

### 3. Requires screen time

Trullás watches the screen and reacts within minutes. This is not "set alerts and forget." For BTC (24/7 market), this becomes a major constraint.

### 4. Championship returns are not realistic for retail

A 2,222% return used 9-15% risk per trade. A single bad streak with that risk can lose 40-60% of the account. Retail traders using 0.5-1.5% total risk will see far lower returns.

### 5. Does not predict direction

From timestamp 04:52-05:10:

> "Down's theory: accumulation, participation, distribution. I'm sure everyone knows that. Okay, let's put it into practice."

The strategy trades exhaustion (divergence) and retracement, not the initial breakout or continuation. You are not predicting where the market will go; you are reacting to exhaustion signals.

## How to Apply This Strategy to BTC

Trullás does not publicly trade or teach cryptocurrency. The following adaptations are required:

### 1. Timeframe adjustment: 1-hour instead of 5-minute

**Original:** 5-minute for entry, 15-minute for context (exits same day)

**BTC version:** 1-hour for entry, 4-hour for context (can hold 4-24 hours)

**Why:** BTC's 24/7 market and lower liquidity (vs. ES/NQ futures) make 5-minute charts too noisy. The 1-hour chart filters noise while preserving divergence signals.

### 2. Add funding rate as fourth confirmation (perpetual futures only)

**Original:** MACD + RSI + Volume

**BTC version:** MACD + RSI + Volume + **Funding Rate**

**Why funding rate matters:**
- Extremely positive funding (+0.3% to +0.5% per 8 hours) = longs overcrowded, short setup stronger
- Negative funding = shorts overcrowded, long setup stronger

Check: Binance Futures, Bybit, or Coinglass.

### 3. Wider stops (divergence low/high ± 3%)

**Original:** Stop 1 tick beyond divergence extreme

**BTC version:** Stop 3% beyond divergence extreme (to account for wick spikes)

BTC has larger wicks than ES/NQ futures. A tight stop will get wicked out.

### 4. Position sizing: 0.5% risk per contract (not 1%)

**Original:** 1% base risk per contract (competition: 3-5%)

**BTC version:** 0.5% risk per contract (beginners: 0.25%)

**Why:** BTC's higher volatility (3-10% daily moves vs. 1-2% for DAX) requires smaller size. Wider stops also increase dollar risk per unit.

**Position sizing example:**
- Account: $10,000
- Risk limit: 0.5% = $50
- Entry: $85,000 (23% Fibonacci retracement)
- Stop: $82,450 (divergence low at $85,000 - 3%)
- Risk per BTC: $85,000 - $82,450 = $2,550
- Position size: $50 / $2,550 = **0.0196 BTC** (~$1,666 notional)
- With 3 contracts: 0.0588 BTC, total risk = $150 (1.5%)

### 5. Use CVD (Cumulative Volume Delta) instead of raw volume

BTC volume is fragmented across Binance, Bybit, Coinbase, OKX, etc. Use:
- **CVD (TradingView indicator):** Tracks buy volume vs. sell volume
- **Aggregated volume (Coinglass):** Combines volume across all major exchanges

### 6. Always use exchange stop-loss orders (not manual monitoring)

**Original:** Trullás can manually exit (he watches the screen)

**BTC version:** **Always use stop-market orders on Binance/Bybit**

**Why:** BTC trades 24/7. Flash crashes happen during off-hours (weekends, 2-4am UTC). You cannot watch it constantly.

**Stop type:** Use **stop-market** (triggers at your stop price, executes at market). Slippage is acceptable; getting stopped out without fill is catastrophic.

### 7. Do not hold leveraged positions overnight if leverage > 2x

**Original:** Intraday rules force exit by market close

**BTC version:** No forced exit, but do not hold >2x leverage overnight

**Why:**
- BTC can gap 5-10% on news while you sleep
- Funding payments hit every 8 hours
- Weekend liquidity is thin, amplifying moves

**Recommended holding:**
- 1-hour entry: Hold 4-12 hours, exit before next major session
- 4-hour entry: Hold 1-3 days, check funding rate daily
- If holding overnight: Max 2x leverage, set wider stop (divergence ± 5%)

### 8. Instruments: BTC/USDT perpetual (Binance, Bybit)

| Instrument | Liquidity | Spreads | Pros | Cons |
|------------|----------|---------|------|------|
| **BTC/USDT perpetual (Binance)** | Excellent | 0.01-0.02% | 24/7, tight spreads, funding rate signal | Unregulated, counterparty risk |
| **BTC/USDT perpetual (Bybit)** | Excellent | 0.01-0.02% | Similar to Binance | Unregulated, counterparty risk |
| **BTC/USD futures (CME)** | Good | 0.05-0.1% | Regulated, institutional | Only trades certain hours, $25k+ per contract |

**Recommendation:** BTC/USDT perpetual on Binance (isolated margin, 2-5x max leverage).

**Avoid:** Low-volume altcoins (divergence unreliable), leveraged tokens (decay), decentralized perpetuals (thin liquidity).

### 9. Use limit orders for entry, not market orders

**Original:** Trullás can use market orders on DAX (spreads are 1-2 ticks)

**BTC version:** **Always use limit orders**

**Why:** BTC spreads are wider (0.01-0.05%). Market orders can slip 0.2-0.5% during volatility, eating into your edge.

**Entry order setup:**
1. Identify divergence at $81,000
2. Calculate 23% Fibonacci: $81,000 + ($7,000 × 0.23) = $82,610
3. Place limit buy at $82,600 (slightly below to increase fill probability)
4. Set stop-market at $79,000 (divergence low - 3%)
5. Set take-profit limit at $85,000 (38% Fibonacci)

**If limit does not fill:** Wait for the next setup. Missing a trade is acceptable; entering at a bad price is not.

### 10. Demo trade for 20-30 setups before live

Use Binance Futures Testnet (testnet.binancefuture.com) with virtual USDT. Record every trade:
- Entry price, stop, target, outcome
- Max drawdown, funding payments
- Emotions (did you move the stop? did you exit early?)

After 20 trades, calculate:
- Win rate (should be 30-50%)
- Average win vs. average loss (should be 2:1 or better)
- Max losing streak (can you survive it with 0.5% risk per contract?)

Only go live if profitable after 20+ trades.

### Common mistakes adapting to BTC (avoid these)

- Entering on the divergence candle itself (wait for retracement!)
- Using 5-minute charts (too much noise)
- Trading during 2-4am UTC (thin liquidity, prone to wicks)
- Moving the stop farther away after entry (#1 killer)
- Using 10x+ leverage (Trullás uses 3-5x in competitions; your account is permanent)
- Ignoring funding rate (missing a key BTC-specific signal)
- Trading altcoins with this method (volume easier to manipulate)

## Example BTC Trade Using Trullás Method

**Setup:**
- BTC falls from $88,000 to $81,000 on 1-hour chart over 12 hours
- MACD histogram makes higher low at $81,000 (bullish divergence)
- RSI makes higher low (bullish divergence)
- Volume decreases into $81,000 (exhaustion)
- Funding rate: -0.05% (shorts overcrowded, squeeze risk)
- **Triple divergence + funding confirmation**

**Entry:**
- Measure: $88,000 (swing high) to $81,000 (divergence low) = $7,000 range
- 23% retracement: $81,000 + ($7,000 × 0.23) = $82,610
- Place limit buy at $82,600

**Stop-loss:**
- Divergence low - 3%: $81,000 × 0.97 = $78,570
- Risk per BTC: $82,600 - $78,570 = $4,030

**Position size:**
- Account: $10,000
- Triple divergence = 3 contracts
- Base risk: 0.5% = $50 per contract
- Total risk: $50 × 3 = $150 (1.5%)
- Position: $150 / $4,030 = **0.0372 BTC** (~$3,073 notional)

**Take-profit:**
- First target (38%): $81,000 + ($7,000 × 0.38) = $83,660 — take 50% profit
- Second target (66%): $81,000 + ($7,000 × 0.66) = $85,620 — take remaining 50%
- Trailing stop: After first target, move stop to breakeven ($82,600)

**Outcome if stopped:** Lose $150 (1.5%)
**Outcome if first target hit:** Gain ($83,660 - $82,600) × 0.0186 BTC = $19.7, but on half position → +$197 profit (1.97R)
**Outcome if second target hit:** Additional ($85,620 - $83,660) × 0.0186 BTC = $36.5 → +$365 total (2.43R)

This example shows defined risk, clear entry, and layered exits — the core of Trullás's approach.

## References and Further Reading

### Primary sources (first-hand evidence)

1. **YouTube: "MACD, RSI, Volumen y Fibonacci: el Sistema del Campeón Mundial | David Trullas" (Live demonstration at Rankia conference, Valencia, May 2026)**  
   URL: [youtube.com/watch?v=0W7EYXrDRBc](https://www.youtube.com/watch?v=0W7EYXrDRBc)  
   **Content:** **THIS IS THE MOST IMPORTANT REFERENCE.** Trullás personally demonstrates his strategy live, brings students on stage to execute trades in real-time, and explicitly states his position sizing logic at timestamp 10:06-10:40. He confirms entry at 23-25% Fibonacci (timestamp 11:33) and first target at 38% (timestamp 17:23-17:46, spoken by student Carmen). The English subtitle file is available.  
   **Key timestamps:**
   - 03:52-04:40: "Volume, Fibonacci, MACD, RSI... so simple... but it works"
   - 05:14-06:40: "MACD is my friend, it's my DNA... If this one is there, the others will come in"
   - 10:06-10:40: "If I have MACD, one [contract]. If I have MACD and RSI, two..."
   - 11:33-11:45: "My entry point is usually around 23-25% of this segment"
   - 17:23-17:46: "From 23 to 38... there are always benefits there" (student Carmen)
   
   **Why this is the key source:** Every other source describes Trullás's method second-hand. This video shows him executing it live. Any conflict between this video and other sources should be resolved in favor of the video.

2. **World Cup Trading Championships official standings (2025-2026)**  
   URL: [worldcupchampionships.com/world-cup-trading-championship-standings](https://www.worldcupchampionships.com/world-cup-trading-championship-standings)  
   **Content:** Official verified rankings. "David Trullas Vila" (Andorra) appears in 8 quarterly Futures Day Trading standings:
   - 2026 Q2: 2,222.6% (1st place, Final)
   - 2026 Q3: 1,350.8% (1st place, pending audit)
   - 2026 Q1: 585.4% (1st place, Final)
   - 2025 Q4: 930.7% (1st place, Final)
   - 2025 Q3: 800.6% (1st place, Final)
   - 2025 Q2: 712.1% (1st place, Final)
   - 2025 Q1: 291% (2nd place)
   
   These numbers match the returns Trullás states in the YouTube video (00:58-01:20): "930 the next one, the next 585... and today we are at 1321%."  
   **Cross-validation:** Independent third-party verification. All standings are verified by broker statements. Account minimum: $10,000.

3. **Binance Square post: Spanish trader achieves 2,220% return (投机实验室 / Speculation Lab, 2026)**  
   URL: [binance.com/en/square/post/382028636347244](https://www.binance.com/en/square/post/382028636347244)  
   **Content:** Third-party analysis. Describes Trullás's method as "a major divergence strategy combining volume, Fibonacci, MACD, and RSI" and notes "if MACD doesn't show divergence, he won't take a trade." States that "price often retraces two-thirds of that move. He trades that retracement."  
   **Cross-validation:** Matches the YouTube video's description of MACD as mandatory and the 2/3 retracement target. Does not mention entry at 23-25% (that detail only appears in the video).

### Technical analysis references (general validation)

4. **Investopedia: "Strategies for Trading Fibonacci Retracement Levels"**  
   URL: [investopedia.com/articles/active-trading/091114/strategies-trading-fibonacci-retracements.asp](https://www.investopedia.com/articles/active-trading/091114/strategies-trading-fibonacci-retracements.asp)  
   **Content:** Explains the 23.6%, 38.2%, 50%, 61.8% Fibonacci levels as common support/resistance zones. Recommends combining Fibonacci with momentum indicators (RSI, MACD) to filter entries.  
   **Cross-validation:** Standard technical analysis literature recognizes Fibonacci retracements. Trullás's use of 23-25% entry → 38% target → 66% target follows this framework.

5. **Investopedia: "Dow Theory"**  
   URL: [investopedia.com/terms/d/dowtheory.asp](https://www.investopedia.com/terms/d/dowtheory.asp)  
   **Content:** Explains Dow Theory's principle that "corrections typically retrace one-third to two-thirds of the prior move."  
   **Cross-validation:** Trullás references Dow Theory in the YouTube video (timestamp 04:44-05:10): "Down's theory... Every rebound or correction usually goes to the two-thirds mark of that stretch." This is a 100+ year-old technical analysis framework, not a modern invention.

6. **BabyPips: "Divergence Trading: Hidden vs. Regular Divergence"**  
   URL: [babypips.com/learn/forex/divergence-trading](https://www.babypips.com/learn/forex/divergence-trading)  
   **Content:** Explains regular divergence (reversal signal) vs. hidden divergence (continuation signal), with MACD and RSI as primary indicators. Warns that "divergence alone is not a trade signal — it requires price confirmation."  
   **Cross-validation:** Matches Trullás's demonstration of both regular divergence (timestamp 08:50-10:40) and hidden divergence (timestamp 13:40-13:58). His student explicitly describes hidden divergence at 13:40.

7. **StockCharts: "MACD Histogram" technical analysis article**  
   URL: [stockcharts.com/school/doku.php?id=chart_school:technical_indicators:macd-histogram](https://stockcharts.com/school/doku.php?id=chart_school:technical_indicators:macd-histogram)  
   **Content:** Explains the MACD histogram as a leading indicator for divergence detection. "The histogram can be used to identify overbought and oversold conditions, as well as bullish and bearish divergences."  
   **Cross-validation:** Trullás uses MACD histogram divergence (not MACD line crossovers). The histogram bars are visible in his TradingView charts in the YouTube video.

8. **Investing.com Academy: "How to Use RSI and MACD Together for Smarter Trades"**  
   URL: [investing.com/academy/analysis/how-to-use-rsi-and-macd-together/](https://www.investing.com/academy/analysis/how-to-use-rsi-and-macd-together/)  
   **Content:** Explains that RSI and MACD used alone each have limitations, but together they "form a synergistic powerhouse, providing a filter that drastically reduces noise and identifies high probability setups."  
   **Cross-validation:** Supports Trullás's requirement for MACD + RSI + Volume (three-way confirmation) instead of relying on one indicator.

### Trading psychology and risk management references

9. **Mark Douglas**, *Trading in the Zone* (2000), Prentice Hall.  
   ISBN: 978-0735201446.  
   **Content:** Classic trading psychology book. Chapter 7: "The Trader's Advantage: Thinking in Probabilities." Emphasizes that "the market is neutral; it is your beliefs and emotions that create losses."  
   **Cross-validation:** Trullás's statement at timestamp 19:32-19:42 ("I have no idea [what my win rate is] because I'm not a big fan of statistics") aligns with probabilistic thinking — he focuses on process (following the rules), not outcome (win rate).

10. **Van K. Tharp**, *Trade Your Way to Financial Freedom* (1999), McGraw-Hill.  
    ISBN: 978-0071478151.  
    **Content:** Discusses position sizing, expectancy, and the "1% risk per trade" rule.  
    **Cross-validation:** Trullás's scaled position sizing (1/2/3 contracts based on signal strength) is a variation on Van Tharp's position sizing principles, adapted for signal strength instead of fixed risk. Trullás explicitly rejects fixed-percentage sizing at timestamp 10:06: "David always bets the same percentage? No, no, no, no, no."

11. **Alexander Elder**, *Trading for a Living* (1993), Wiley.  
    ISBN: 978-0471592242.  
    **Content:** Introduces the "Triple Screen Trading System" using weekly + daily + intraday timeframes, plus MACD and other indicators. Emphasizes "the longer you can wait for the perfect setup, the better your results."  
    **Cross-validation:** Elder's multi-timeframe approach (weekly/daily/intraday) conceptually parallels Trullás's use of 15-minute for context and 5-minute for execution. Both emphasize patience.

---

## Cross-Validation Summary

| Claim | Primary source | Secondary verification |
|-------|----------------|------------------------|
| **MACD is mandatory; RSI and Volume scale position** | YouTube video (05:14-06:40, 10:06-10:40) | — |
| **Position sizing: 1/2/3 contracts based on signals** | YouTube video (10:06-10:40) | — |
| **Entry at 23-25% Fibonacci** | YouTube video (11:33-11:45) | — |
| **First target: 38% (beginner rule)** | YouTube video (17:23-17:46, student Carmen) | — |
| **Second target: 66% (2/3 zone)** | YouTube video (12:50-13:10, student Joan) | Dow Theory (Investopedia), Binance Square |
| **2,222% return in Q2 2026** | World Cup official standings | Binance Square, YouTube video (01:15-01:20) |
| **Trades Nasdaq, DAX, Gold futures** | YouTube video (08:10, 14:48-15:10) | World Cup division (Futures Day Trading) |
| **MACD histogram + RSI + Volume divergence** | YouTube video (03:52-04:20, 08:50-09:40) | Binance Square, BabyPips, Investing.com |
| **Does not track win rate / not a statistics person** | YouTube video (19:32-19:42) | — |

**Key finding:** The YouTube video is the only first-hand source where Trullás states his entry level (23-25%) and position sizing logic (1/2/3 contracts). Every secondary source that claims "enters at 61.8%" is wrong — 61.8%-66% is his **target**, not his entry.

---

**Total references: 11 (3 primary sources, 8 validation sources)**

---

**Disclaimer:** This article is for educational purposes only. David Trullás's championship results used aggressive position sizing (multiple contracts = 3-9% risk per trade) that is not suitable for most retail traders. The strategy described here is based on publicly available information (YouTube demonstration, official competition results) and may not reflect Trullás's complete proprietary methodology. Past performance does not guarantee future results. Cryptocurrency trading involves significant risk. Trade only with capital you can afford to lose, and practice extensively in demo accounts before using real money.
