## Week 1: Crypto market structure
Selected Readings:


https://www.binance.com/en/academy/articles/what-is-basis-trading-and-how-does-it-work
https://www.binance.com/en/academy/articles/what-are-funding-rates-in-crypto-markets
https://www.binance.com/en/academy/articles/what-are-perpetual-futures-contracts
https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4301150
https://insights.glassnode.com/leverage-position-openings-and-closures/


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

