# Basis Trade: Perps/Futures/Spot
Selected Readings:


https://www.binance.com/en/academy/articles/what-is-basis-trading-and-how-does-it-work

https://www.binance.com/en/academy/articles/what-are-funding-rates-in-crypto-markets

https://www.binance.com/en/academy/articles/what-are-perpetual-futures-contracts

https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4301150

https://insights.glassnode.com/leverage-position-openings-and-closures/

https://www.paradigm.co/blog/back-to-the-basis-all-you-need-to-know-to-get-started-trading-basis-on-bybit

https://www.paradigm.co/blog/basis-basics-pt-2

https://www.paradigm.co/blog/defi-derivatives-yield-generation-strategies


# Crypto Market Map — Day 1

## 1. Instruments

### Spot

* Coins such as BTC / ETH that represent the underlying asset.
* Economically important as the **anchor asset** that derivatives reference.
* Key constraints:

  * Custody and settlement
  * Borrowing costs / availability
  * Fragmented liquidity across venues

**Mental model:** Spot is the reference layer; most speculative risk is expressed elsewhere.

---

### Perpetual Futures (Perps)

* A synthetic futures contract **without expiry**.
* Can be held indefinitely.
* Linkage to the spot index is maintained via **peer-to-peer funding transfers**.

Key nuances:

* Funding does *not* guarantee convergence to spot; it only penalizes deviations.
* Positions persist → imbalances can persist.

**Mental model:** Perps are futures where expiry is replaced by continuous funding.

---

### Futures

* Fixed-expiry futures (e.g. CME BTC futures).
* Typically **cash-settled**, not physically delivered.
* Converge to spot at expiry due to arbitrage, not delivery mechanics.

**Mental model:** Futures clear imbalances discretely at expiry; perps clear them continuously via funding.

---

## 2. Funding

### Why funding exists

* Perpetual contracts have no expiry, so longs and shorts can hold positions indefinitely.
* Funding acts as a **continuous substitute for expiry**, pulling perp prices toward spot over time.

---

### How funding works

* Funding is exchanged **between traders**, not paid to the exchange.
* When funding is positive:

  * Perp longs pay perp shorts
* When funding is negative:

  * Perp shorts pay perp longs
* Funding intervals vary by exchange (8h is common, but not universal).

---

### Who is usually paying

* Funding is usually positive.
* This implies perp **longs typically pay** perp shorts.

The deeper reason:

* There is persistent structural demand for **leveraged long exposure**.
* The marginal short requires compensation to absorb balance-sheet and liquidation risk.

---

## 3. Market Participants

### Retail

* Tends to go long perps.
* Motivations:

  * Capital efficiency
  * Easy access to leverage
  * No borrow or expiry management

---

### Funds / Arbitrageurs

* Often long spot and short perps.
* Objective:

  * Harvest funding and/or basis
  * Remain directionally neutral
* Constraint:

  * Balance-sheet usage and capital costs

---

### Market Makers

* Quote both sides of the order book.
* Earn from:

  * Bid–ask spread
  * Inventory and funding management
  * Volatility during liquidation cascades

---

## 4. Structural Takeaways on Funding

* Funding staying positive does **not** require price to keep rising.
* Funding reflects **imbalance and risk transfer**, not fair value.
* It can remain positive for extended periods because:

  * Demand for leveraged longs is persistent
  * Shorts are often hedgers or arbs, not directional traders
  * Liquidation convexity makes shorting perps riskier
  * There is no expiry forcing position reset

**Key insight:**
Funding prices who must absorb risk, not who is right about direction.

---

## 5. One-Sentence Insight

> “The biggest misconception I had about crypto derivatives was that leverage makes trading cheaper, when in reality it converts price risk into continuous funding and liquidation risk.”

# Crypto Market Map — Day 2

## Goal

Understand funding as a **risk-transfer and imbalance pricing mechanism**, not a directional signal.

---

## Core Principle

> **Funding is a rental fee for imbalance, not a forecast of returns.**

It reflects who must absorb risk and under what constraints, rather than who is "right" about price direction.

---

## Scenario Analysis

### 1. Bull Trend + Positive Funding

**Environment**

* Price trending up
* Funding persistently positive
* Moderate volatility

**Flows**

* Perp longs (mostly retail / momentum):

  * Pay funding
  * Earn price PnL
* Perp shorts (arbs / MMs):

  * Receive funding
  * Hedged or inventory-managed

**Why funding persists**

* Strong demand for leveraged long exposure
* Shorts cannot aggressively cover without worsening price impact

**Takeaway**
Positive funding reflects willingness to pay for leverage and immediacy.

---

### 2. Sideways Market + Positive Funding

**Environment**

* Range-bound price
* Low volatility
* Funding still positive

**Flows**

* Perp longs:

  * No price PnL
  * Continuous funding bleed
* Perp shorts (funding arbs):

  * Accumulate carry slowly
  * Capital tied up

**Why arbitrage doesn’t eliminate funding**

* Balance-sheet constraints
* Custody and borrow friction
* Exchange and operational risk

**Takeaway**
Funding can stay positive even without bullish price action due to limited arbitrage capacity.

---

### 3. Slow Grind-Down + Positive Funding

**Environment**

* Gradual price decline
* Funding remains positive
* Sharp downside spikes, weak bounces

**Flows**

* Perp longs:

  * Lose on price
  * Still pay funding
  * Liquidated mechanically on downside spikes
* Perp shorts:

  * Earn price PnL and funding
  * Remain exposed to squeeze tail risk

**Key asymmetry**

* Long liquidations: fast, mechanical, frequent, bounded loss
* Short squeezes: rare, slower, discretionary exits, unbounded loss

**Why funding stays positive**

* Shorts demand compensation for catastrophic tail risk, not frequency or speed

**Takeaway**
Funding prices tail risk and balance-sheet stress, not short-term trend.

---

## Structural Asymmetry (Lock This In)

* **Longs are killed by speed** (liquidations)
* **Shorts are killed by tails** (squeezes)

Funding compensates the side absorbing the more dangerous risk.

---

## Funding ≠ Direction

* Funding helps momentum traders when price trends strongly enough to dominate carry
* Funding hurts momentum traders in sideways or slow-decline regimes
* Funding creates opportunity for arbs when imbalance persists and risk is survivable
* Funding spikes before crashes because shorts hit balance-sheet limits first, forcing funding to rise, which leaves the market one-sided and fragile. 
---

## One-Line Summary

> Funding stays positive not because the market must go up, but because absorbing short exposure requires continuous compensation for unbounded tail risk.

# Day 3 Summary — Delta-Neutral Funding Capture

## 1. What the trade really is
- **Position**: Long spot + short perpetual (delta ≈ 0)
- **Economic role**: Selling leverage and renting out balance sheet
- **Income source**: Funding paid by crowded leveraged longs
- **Not** a directional bet or “free yield” strategy

---

## 2. Why the trade exists
- Persistent demand for leveraged long exposure
- Short capacity is scarce and balance-sheet constrained
- Funding is the price paid to transfer tail risk and imbalance

---

## 3. Why returns are small
- Funding yields are typically single-digit to low-teens annualized
- After fees, margin buffers, and stress capital, ROE is modest
- Edge comes from slow, persistent carry, not fast alpha

---

## 4. The core risk (most important)
> The trade is positive EV but path-dependent.

- Funding accrues slowly
- Losses from gaps or dislocations are immediate
- To amplify returns, traders lever up
- Leverage introduces liquidation and forced deleveraging risk
- Liquidation causes permanent capital loss

---

## 5. Why “delta-neutral” is misleading
- Delta ≈ 0 does not mean risk ≈ 0
- Exposures include:
  - Gap risk
  - Short squeeze tail risk (gap up)
  - Basis and liquidity dislocations
  - Exchange and operational risk

---

## 6. Gap risk asymmetry
- **Gap up (most dangerous)**:
  - Short losses are unbounded
  - Margin pressure increases as price rises
  - Forced exits can occur even if hedge is conceptually correct
- **Gap down (more common, usually survivable)**:
  - Short profits offset spot losses
  - Liquidations often help the hedge

---

## 7. When the trade works
- **Carry / calm imbalance regime**
  - Funding positive but stable
  - Price sideways or slow trend
  - Volatility low
  - Open interest not accelerating

---

## 8. When the trade fails
- **Balance-sheet stress regime**
  - Funding rising rapidly
  - Leverage building
  - Shorts constrained
  - Market fragile

High funding caused by stress is a warning, not yield.

---
## 9. Some thoughts
### Key Alpha in Delta-Neutral Funding Capture

- The alpha is **not** in earning funding.
- The alpha is in **avoiding periods when funding becomes toxic**.

---

### Why Avoidance Matters More Than Entry

- Funding is usually positive → entry timing matters less.
- Returns accrue slowly → missing a few days is irrelevant.
- Losses arrive suddenly via gaps, squeezes, or forced deleveraging.

**Conclusion:**  
Avoidance and early exit dominate entry optimization.

---

### When Funding Stops Being “Income”

Funding becomes dangerous when it compensates **stress**, not imbalance:
- Shorts are balance-sheet constrained
- Leverage is crowded
- Market becomes fragile

High funding ≠ high expected return  
High funding often = **high conditional risk**

---

### The Real Decision Points (Source of Alpha)

#### When NOT to open
- Funding rising rapidly
- Open interest accelerating
- Volatility compressing or starting to rise
- Price momentum flattening

#### When to stop adding
- Regime deteriorating despite positive funding
- Stress scenarios feel uncomfortable
- Temptation to size up because the trade “feels safe”

#### When to exit early
- Before liquidation risk is obvious
- Before funding spikes fully
- Before consensus agrees the trade is dangerous

Professionals exit **early and small**, not late and right.

---

### Mental Model to Keep

> Delta-neutral funding capture is a regime trade.  
> You make money by participating in calm imbalance and refusing to warehouse stress.


## One sentence to remember
> Delta-neutral funding capture fails not because it’s wrong, but because small, slow carry is overwhelmed by leverage-induced path dependence and balance-sheet constraints.


