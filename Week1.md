## Week 1: Crypto market structure
Learning Plan:
1. Spot vs Perps vs Futures
2. Funding rate mechanics (who pays whom and why)
3. Order book basics (maker/taker, slippage)
4. Major venues: Binance, OKX, Bybit, Deribit
5. Key concepts:
  * Perps ≈ futures + funding
  * Funding ≈ price of leverage + imbalance
  * Liquidity ≠ volume


https://www.binance.com/en/academy/articles/what-is-basis-trading-and-how-does-it-work
https://www.binance.com/en/academy/articles/what-are-funding-rates-in-crypto-markets
https://www.binance.com/en/academy/articles/what-are-perpetual-futures-contracts
https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4301150




### Section1 : Basis Trade
Basic Idea:
1. Profit from the difference of spot price and future price
2. Trade spot ETF vs CME BTC future to capture the basis
3. Risk is the divergence of spot of future


### Section 2: Perpetual Futures
Funding rate: positive means long position pay to short position, vice versa. Funding rate makes sure that the furture price and spot price goes with each other.Funding rate is a market sentiment measurement

1. interest rate: difference between funding cost of BTC and USD
2. premium index: difference between the perpetual contract price and the spot price of the underlying asset
3. Funding rate is paid every 8 hours, and the bid ask spread is impacted by this payment schedul.
4. When market is bullish, premium index tend to be higher.
5. Retails would use perpetual to gain leverage when trading.
6. Institutions/participants that long spot tend to us perpetual shorts as a hedge.
7. Market makers would quote on both side to collect bid ask spread.



Summary:
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
