# David Trullás: MACD-Led Divergence with Scaled Position Sizing

## Who is David Trullás?

David Trullás Vila is a physiotherapist, osteopath, and professional intraday futures trader from Manresa, Spain. He founded **Live in Trading**, a Spanish trading education company offering courses, live sessions, and mentorship. Trullás has won multiple World Cup Trading Championship quarterly competitions in the Futures Day Trading Division:

| Period | Return | Rank |
|--------|--------|------|
| Q2 2026 | 2,222.6% | 1st |
| Q3 2026 | 1,350.8% (pending audit) | 1st |
| Q1 2026 | 585.4% | 1st |
| Q4 2025 | 930.7% | 1st |
| Q3 2025 | 800.6% | 1st |
| Q2 2025 | 712.1% | 1st |
| Q1 2025 | 291% | 2nd |

These results are independently verified by the World Cup Trading Championships, which requires broker statement confirmation.

Trullás is also the author of *Bienvenidos al mundo real de la bolsa* (Welcome to the Real World of the Stock Market, Plataforma Editorial, 2016), a beginner's guide covering market basics, technical analysis, and trading psychology.

At a Rankia conference in Valencia, Spain in May 2026, he gave a live demonstration of his strategy, bringing students on stage to execute real-time trades. The session was recorded and posted on YouTube. The material in this article draws primarily from that demonstration.

---

## Core Philosophy

Trullás describes his approach in deliberately simple terms:

> "Volume, Fibonacci, MACD, RSI. How simple, and it works! This is the basis of the championships with the percentages you've seen, and it's not a deception."

> "This is so simple, so silly, so basic, so archaic. But it works. So why would I want to complicate my life?"

He is a physiotherapist by training, and he frames trading the way he frames physical therapy: you need to understand anatomy (structure) and physiology (function) to treat a patient. In trading, structure is price and market context; function is momentum (MACD, RSI) and participation (volume). When function diverges from structure, exhaustion is near.

He does not claim a specific win rate. When asked in the demonstration, he said: "I have no idea because I'm not a big fan of statistics." His focus is on process — following the rules — not on predicting outcomes.

---

## The Core Strategy

### MACD is the pillar; RSI and Volume scale the position

**MACD is mandatory. Without it, there is no trade.**

In his own words from the demonstration:

> "MACD is my friend. It's my DNA. If MACD doesn't give me the image I want to see, I don't operate. Neither RSI, nor volume, nor order flow, nor pending orders, nor big trades... If this one [MACD] is there, the others will come in. This is my pillar. He's the one in charge."

RSI gives "very quick reactions" and is the first confirmation. Volume gives "the strength" and is the final confirmation. Both confirm what MACD has already identified. If you do not have MACD divergence, there is nothing to confirm.

### What divergence means

**Bearish divergence (setup for a short):**
- Price makes a higher high
- MACD histogram makes a lower high (momentum is weakening)
- RSI makes a lower high
- Volume decreases into the high (fewer buyers at the top)

**Bullish divergence (setup for a long):**
- Price makes a lower low
- MACD histogram makes a higher low (selling pressure is exhausting)
- RSI makes a higher low
- Volume decreases into the low (fewer sellers at the bottom)

On volume, Trullás explains:

> "When the price reaches new highs, what should the volume do at those new highs? It has to increase. If it's lower, it means the volume doesn't match the price."

This is basic Dow Theory: new highs should have expanding participation. When they do not, the move is losing conviction.

### Scaled position sizing: the key differentiator

Most traders using multiple indicators wait for all three to align, then enter with a fixed position size. Trullás does not. He enters when MACD diverges — with a small position — and then adds contracts as each additional confirmation appears.

His own description from the demonstration:

> "I risk my money based on what I see. If I have MACD [divergence], one [contract]. If I have MACD and RSI, two. If I have MACD and RSI outside of overbought [zone], another contract. If I have [enough] volume, another contract."

| Confirmed signals | Position size |
|-------------------|---------------|
| MACD divergence only | 1 contract |
| MACD + RSI divergence | 2 contracts |
| MACD + RSI + Volume divergence | 3 contracts |

Each contract carries a base risk. A 3-contract trade is 3× that base. This is not "1% fixed risk per trade" — it is **signal-strength-based sizing**. High conviction setups get more size. This is the mechanism behind his championship returns.

A student asked in the demonstration whether David always bets the same percentage. He interrupted: "No, no, no, no, no."

### Entry: 23-25% Fibonacci retracement

Many secondary sources claim Trullás enters at 61.8%. This is wrong. 61.8% is a target, not an entry.

His actual words from the demonstration:

> "My entry point is usually around 23-25% of this segment."

**How to draw the Fibonacci:**
- **100%** = the divergence extreme (the high where bearish divergence occurred, or the low where bullish divergence occurred)
- **0%** = the origin of the move (the swing low before the rally, or the swing high before the fall)

Wait for price to begin retracing from the divergence extreme. Then enter with a limit order in the 23-25% zone. Do not enter on the divergence candle itself.

**Why 23-25% and not 61.8%:**
- The stop sits just beyond the 100% level (the divergence extreme). Entering at 23% keeps the stop close, which gives a favorable risk-reward even with small targets.
- Price often reaches 38% reliably. From 23% entry to 38% target with a stop just beyond 100% gives roughly 2:1 or better risk-reward on the first target alone.
- In intraday futures (5-minute charts), price moves fast. Entering early captures the move before it reverses.

**On the Fibonacci measurement itself:** Joan, one of his students, describes it in the demonstration:

> "We would draw a Fibonacci from the highest point to the lowest point of the divergence and from here we would launch the operation up to 66%, up to the second third."

Joan is describing the full setup correctly: origin to divergence extreme, entry near the start of the retracement, target at two-thirds of the measured segment.

### Stop-loss placement

The stop goes just beyond the divergence extreme. For a long (bullish divergence at a low), the stop goes below that low. For a short (bearish divergence at a high), the stop goes above that high.

In intraday futures, Trullás uses tick-precise placement. He did not disclose the exact distance from the extreme. For BTC, add a buffer for wicks (discussed below).

Do not move the stop farther away after entry to avoid taking a loss. If the divergence extreme is broken, the trade thesis is invalid.

### Take-profit targets

**Target 1 — 38% Fibonacci (beginner default)**

Student Carmen's explanation from the demonstration:

> "At the beginning, when we don't know much, we should try the Fibonacci retracement level at 23 and reach the take profit at 38. We shouldn't try to make more money, especially to first learn the routine from 23 to 38, because many times we want to reach 50 after 38, and often the price reverses."

For beginners, take full profit at 38% and exit. Accept the smaller gain, build the habit of following through. Carmen adds: "If it's 200 dollars, straight into the pocket, right? And goodbye."

**Target 2 — 66% Fibonacci (two-thirds mark)**

This is the standard target from Dow Theory. Trullás's reference to "every rebound or correction usually goes to the two-thirds mark of that stretch" is the basis for using 66% as the larger target. After reaching 38%, move the stop to breakeven and let the remaining position run to 66%.

**Target 3 — 0% Fibonacci (full retracement)**

Price returns to the origin of the measured move. This is the maximum extension case, appropriate when the divergence is strong and momentum confirms continuation through 66%.

### Hidden divergence (trend continuation)

Trullás also trades hidden divergence. A student in the demonstration explains:

> "The hidden divergence is when the price goes up and the indicators go down. We have several entries, this is the hidden one, so when we get this pattern... at the lowest price the Fibonacci is drawn all the way up, quite clear and marked entry and profits."

Hidden divergence signals trend continuation, not reversal. The same entry logic applies: 23-25% Fibonacci, same targets, same position scaling.

### Timeframe

Trullás uses 5-minute charts for entry execution and 15-minute charts for identifying divergence and context. In the Valencia demonstration, he briefly used a 5-second chart for the live trades — not because that is his normal setup, but because the audience was watching in real time and he wanted the market to move while they watched.

Trades last from 30 minutes to a few hours. World Cup intraday rules require closing all positions by end of day; Trullás exits every day and does not hold overnight.

### Instruments

Trullás primarily trades stock index and commodity futures: S&P 500 (ES), Nasdaq (NQ), DAX (FDAX), Gold (COMEX futures), and IBEX 35.

On gold specifically, when asked in the demonstration: "For gold, I always prefer the regulated market; I don't like XAU/USD, okay? I always go to the future, always, because it's a regulated market."

On flexibility: "You can look at any asset you want... a stock, a futures contract, Forex, it doesn't matter to me. In a timeframe that you want, I don't care, a minute, five minutes, an hour, daily, I don't care."

---

## What This Strategy Does Not Do

- Does not predict direction — it reacts to exhaustion signals and trades the retracement
- Does not trade breakouts — entry is on the retracement after the exhaustion, not on the initial move
- Does not hold overnight — intraday rules apply; he exits by end of day
- Does not add to a losing position — scaling up applies only when new confirmation signals appear before entry, not after a loss
- Does not require multiple timeframe alignment or complex filter systems — MACD is the gate; the rest follows

---

## Limitations

**1. MACD-only setups have lower conviction**

A trade with only MACD divergence gets one contract. That is a smaller position, accepted at lower confidence. Over time, MACD-only setups may have a lower success rate than triple-confirmation setups. You are not betting the same amount on every trade.

**2. Entry at 23-25% can be missed**

If price retraces sharply and immediately continues, it may not reach 23-25% before reversing. Trullás accepts missing those trades. He waits for the retracement to come to him.

**3. Championship sizing is not suitable for retail**

In competitions, Trullás sizes aggressively. With 3 contracts at 3-5% risk each, a triple-divergence trade carries 9-15% account risk. A two-trade losing streak at that size loses 18-30%. Retail traders using 0.5% per contract (1.5% total for 3 contracts) will produce far more modest returns.

**4. Requires screen time**

Trullás watches the market and reacts in minutes. This is not an alert-and-execute system for part-time traders. For BTC (24/7 market), this constraint is significant.

**5. Divergence does not always resolve quickly**

Divergence can persist through several more highs or lows before a retracement occurs. You may enter at 23-25% and the trade works slowly, or price may break the divergence extreme and invalidate the setup.

---

## Can This Strategy Be Applied to BTC?

Trullás does not trade crypto publicly. The following adaptations are necessary to apply his method to BTC/USDT perpetual futures.

### Why BTC requires changes

| Factor | Traditional futures (Trullás) | BTC perpetuals |
|--------|-------------------------------|----------------|
| Trading hours | 8-16 hrs/day (session-based) | 24/7 |
| Daily volatility | 0.5-2% | 3-10% |
| Liquidity | Deep institutional book | Thinner, prone to flash wicks |
| Volume source | Single regulated exchange | Fragmented across exchanges |
| Overnight risk | Forced exit (intraday rules) | Optional but carries gap + funding risk |
| Spreads | 1-2 ticks, negligible | 0.01-0.05%, meaningful |

### Adaptation 1: Timeframe — 1-hour instead of 5-minute

BTC's 24/7 nature and thinner liquidity make 5-minute divergence signals unreliable. Too many wicks, too much noise from wash trading and thin-book manipulation. Use 1-hour charts for divergence identification and entry execution, with 4-hour charts for context.

Fewer setups appear on 1-hour charts than on 5-minute, but quality is higher. Accept the lower frequency.

### Adaptation 2: Add funding rate as fourth confirmation (perp futures)

Perpetual futures have a funding rate that resets every 8 hours. When funding is extremely positive (+0.3% to +0.5% per 8h), the market is overcrowded with longs. A bearish divergence in that environment is reinforced — longs will eventually unwind or get liquidated.

- Bearish divergence + extreme positive funding = stronger short setup
- Bullish divergence + extreme negative funding = stronger long setup

Check Binance Futures, Bybit, or Coinglass for real-time funding data.

### Adaptation 3: Stop placement — divergence extreme ± 3%

In regulated futures, Trullás places stops 1 tick beyond the divergence extreme. BTC wicks through levels by 1-2% routinely, especially on weekends and low-liquidity hours. Place the stop 3% beyond the divergence extreme, not 1 tick.

This wider stop increases dollar risk per position, so reduce the number of contracts accordingly.

### Adaptation 4: Position sizing — 0.25-0.5% risk per contract

Trullás's championship base risk per contract is 3-5%. For retail BTC trading, use 0.25-0.5% per contract. With 3 contracts (triple divergence), total risk is 0.75-1.5% of account. This is survivable through losing streaks.

**Example:**
- Account: $10,000
- Risk per contract: 0.5% = $50
- Triple divergence (3 contracts): total risk $150
- Entry: $82,600 (23% Fibonacci)
- Stop: $78,570 (divergence low at $81,000 - 3%)
- Risk per BTC: $82,600 - $78,570 = $4,030
- Position size: $150 / $4,030 = **0.037 BTC** (~$3,060 notional)

### Adaptation 5: Volume — use CVD or aggregated data

BTC volume is fragmented across Binance, Bybit, Coinbase, and OKX. Raw exchange volume on a single platform understates or misrepresents participation.

Use **Cumulative Volume Delta (CVD)** on TradingView: it tracks buy volume minus sell volume and shows whether buyers or sellers are dominant into a price extreme. Declining CVD into a lower low (bullish divergence) is a stronger signal than raw volume alone.

### Adaptation 6: Always use exchange stop-loss orders

Trullás watches the screen during trading hours and can exit manually. BTC runs 24/7. Flash crashes happen at 3am UTC. Use stop-market orders on Binance or Bybit with mark price as the trigger source (not last price, which can be moved by a single wick).

### Adaptation 7: Holding period and leverage

Trullás exits same day. BTC has no forced close. Recommended holding limits:
- 1-hour entry: 4-12 hours, exit before the next major session open
- 4-hour entry: 1-3 days, check funding rate daily

If holding overnight: max 2x leverage. At higher leverage, a 5-10% overnight gap can trigger liquidation before your stop fires.

### Adaptation 8: Instruments — BTC/USDT perpetual on Binance or Bybit

Both have tight spreads (0.01-0.02%), high liquidity, small minimum sizes (0.001 BTC), and visible funding rates. Use isolated margin mode so one bad trade cannot affect other positions.

Avoid: leveraged tokens (BTCUP/BTCDOWN), low-volume altcoins, and decentralized perpetuals.

### Adaptation 9: Limit orders for entry

DAX and ES futures have negligible spreads. BTC spreads are 0.01-0.05%, and during volatility can widen further. Market orders slip. Place a limit order at 23-25% Fibonacci and wait for the market to come to you. If it does not fill, skip the trade.

### Adaptation 10: Practice on testnet first

Use Binance Futures Testnet (testnet.binancefuture.com) for at least 20 trades before using real capital. Focus on:
- Finding divergence on 1-hour BTC charts
- Placing limit orders at 23-25%
- Following the stop without moving it
- Exiting at 38% and not "waiting for more"

Record every trade. After 20 trades, review: are results consistent? Did you follow the rules each time?

---

## BTC Trade Example

**Setup:**
- BTC falls from $88,000 to $81,000 on the 1-hour chart over 12 hours
- MACD histogram: lower low in price, higher low in MACD (bullish divergence)
- RSI: lower low in price, higher low in RSI (bullish divergence)
- Volume: decreasing into the $81,000 low (fewer sellers)
- Funding rate: -0.05% per 8h (shorts overcrowded)
- Triple divergence with funding confirmation

**Fibonacci setup:**
- 100% = $81,000 (divergence low)
- 0% = $88,000 (swing high before the fall)
- Range = $7,000

**Entry:**
- 23% retracement: $81,000 + ($7,000 × 0.23) = $82,610
- Limit buy order at $82,600

**Stop-loss:**
- Divergence low - 3%: $81,000 × 0.97 = $78,570
- Risk per BTC: $82,600 - $78,570 = $4,030

**Position size (3 contracts):**
- Base risk: 0.5% × $10,000 = $50 per contract
- Total risk: $150
- Size: $150 / $4,030 = 0.037 BTC

**Targets:**
- First target (38%): $81,000 + ($7,000 × 0.38) = $83,660 → take 50% off, move stop to breakeven
- Second target (66%): $81,000 + ($7,000 × 0.66) = $85,620 → exit remaining position

**Outcome:**
- Stopped out: -$150 (1.5% of account)
- First target hit: +$39.5 on 0.0185 BTC = +$42 per contract, ×3 = ~+$126 partial
- Both targets hit: total ~+$210 on the full position

---

## References

### Primary sources

1. **David Trullás, live demonstration at Rankia conference, Valencia, Spain, May 2026**  
   URL: [youtube.com/watch?v=0W7EYXrDRBc](https://www.youtube.com/watch?v=0W7EYXrDRBc)  
   This is the primary source for all strategy details in this article: MACD as mandatory pillar, position scaling (1/2/3 contracts), entry at 23-25%, first target at 38%, second target at 66%, hidden divergence, and the Dow Theory 2/3 retracement principle. Student demonstrations of Joan and Carmen are also from this session. English subtitles are available.

2. **World Cup Trading Championships — official standings**  
   URL: [worldcupchampionships.com/world-cup-trading-championship-standings](https://www.worldcupchampionships.com/world-cup-trading-championship-standings)  
   Verifies Trullás's quarterly results in the Futures Day Trading Division (Q1 2025 through Q4 2026). All results are confirmed against broker statements. The returns stated in the article come directly from this page.

3. **Speculation Lab (投机实验室), Binance Square, 2026**  
   URL: [binance.com/en/square/post/382028636347244](https://www.binance.com/en/square/post/382028636347244)  
   Third-party analysis of Trullás's method after his Q2 2026 championship. Describes the strategy as "a major divergence strategy combining volume, Fibonacci, MACD, and RSI" and notes that "if MACD doesn't show divergence, he won't take a trade." Confirms the 2/3 retracement target. Does not describe the 23-25% entry detail — that is only stated in the video itself.

4. **David Trullás Vila**, *Bienvenidos al mundo real de la bolsa*, Plataforma Editorial, 2016.  
   ISBN: 978-84-16429-11-0. Available at [Plataforma Editorial](https://www.plataformaeditorial.com/libro/4807-bienvenidos-al-mundo-real-de-la-bolsa) and Spanish bookstores.  
   His book covering market basics, technical analysis, and trading psychology. Trullás mentioned in the demonstration that the book is now 10 years old and was written when "pool trading and Ultramans" dominated Spanish trading culture.

5. **Rankia conference materials (2014)**  
   URL: [rankia.com/blog/opiniones/2202148-especulando-macd-fibonacci-conferencia-david-trullas-iv-foro-finanzas-personales](https://www.rankia.com/blog/opiniones/2202148-especulando-macd-fibonacci-conferencia-david-trullas-iv-foro-finanzas-personales)  
   Early public presentation of the MACD + Fibonacci divergence strategy at the IV Foro de Finanzas Personales, 2014. The core method (MACD + Fibonacci + discipline) described in 2014 is the same as demonstrated in 2026 — 12 years of consistency.

### Technical analysis validation

6. **Investopedia: Dow Theory**  
   URL: [investopedia.com/terms/d/dowtheory.asp](https://www.investopedia.com/terms/d/dowtheory.asp)  
   Explains Dow Theory's principle that corrections and retracements "typically retrace one-third to two-thirds of the prior move." Trullás explicitly references Dow Theory in the 2026 demonstration to explain his 66% target. The 2/3 rule is a 100+ year-old technical framework, not a modern invention.

7. **Investopedia: Fibonacci Retracement Levels**  
   URL: [investopedia.com/articles/active-trading/091114/strategies-trading-fibonacci-retracements.asp](https://www.investopedia.com/articles/active-trading/091114/strategies-trading-fibonacci-retracements.asp)  
   Explains the 23.6%, 38.2%, 50%, and 61.8% levels as common zones. Supports Trullás's use of 23-25% as an entry zone and 38% as a first target.

8. **BabyPips: Divergence Trading**  
   URL: [babypips.com/learn/forex/divergence-trading](https://www.babypips.com/learn/forex/divergence-trading)  
   Explains regular divergence (reversal signal) vs. hidden divergence (continuation signal) using MACD and RSI. Warns that divergence alone is not a trade signal — confirmation is required. Matches Trullás's approach: divergence identifies exhaustion, the Fibonacci retracement entry confirms the move has begun.

9. **StockCharts: MACD Histogram**  
   URL: [stockcharts.com/school/doku.php?id=chart_school:technical_indicators:macd-histogram](https://stockcharts.com/school/doku.php?id=chart_school:technical_indicators:macd-histogram)  
   Technical documentation of the MACD histogram and its use for divergence detection. Confirms that Trullás uses the MACD histogram (not the MACD line or signal line crossover) as his primary divergence indicator.

10. **Investing.com Academy: How to Use RSI and MACD Together**  
    URL: [investing.com/academy/analysis/how-to-use-rsi-and-macd-together/](https://www.investing.com/academy/analysis/how-to-use-rsi-and-macd-together/)  
    Explains how MACD and RSI reinforce each other as divergence tools. Relevant to Trullás's use of both indicators: MACD as mandatory gate, RSI as first confirmation.

11. **Van K. Tharp**, *Trade Your Way to Financial Freedom*, McGraw-Hill, 1999.  
    ISBN: 978-0071478151.  
    Standard reference for position sizing theory. Trullás's method departs from Van Tharp's fixed-percentage approach: rather than risk the same amount per trade regardless of signal strength, Trullás sizes proportionally to the number of confirmed signals. His explicit rejection of fixed sizing ("No, no, no, no, no") in the demonstration is the contrast worth understanding.

---

## A note on secondary sources

Several third-party analyses of Trullás's method — including posts on Binance Square and trading forums — describe the strategy as "entering at 61.8%-66% Fibonacci." This is wrong. Those sources confused the entry with the target. Trullás enters at 23-25% and targets 38% first, then 66%. The 66% figure is where he expects price to go, not where he gets in.

His competition returns (585%-2,222% per quarter) are independently verified by the World Cup Trading Championships, which requires broker statement confirmation. The method has been publicly described since at least 2014 — the Rankia conference materials from that year describe the same MACD + Fibonacci + discipline framework still in use today.

---

**Disclaimer:** This article is for educational purposes only. Trullás's championship results used aggressive position sizing that is not suitable for most retail traders. The strategy described here is based on publicly available information and may not reflect his complete methodology. Past performance does not guarantee future results.
