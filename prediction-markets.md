# 🎲 Prediction Markets

<figure><img src=".gitbook/assets/polymarket.jpg" alt="Polymarket hot markets, analytics and whale tracking"><figcaption></figcaption></figure>

Formion brings **Polymarket, Kalshi and Limitless** into the same terminal as your charts and bots — browse hot markets, track the whales, read the analytics, and (on supported venues) connect and trade.

{% hint style="info" %}
Browsing and analytics are open to everyone. **Live execution** of prediction-market strategies is an **Institutional** feature.
{% endhint %}

## Browse & analyze
* **Hot markets** by 24h volume, with YES odds, liquidity and volume
* **Leaderboard** and **whale ledger** — who's positioned where
* **Prediction analytics** — odds movement, mispricing vs fair value

## Connect & trade
Connect a supported prediction-market account to place positions from inside Formion and see your open bets alongside the rest of your portfolio.

## In-house engines
Formion runs its own prediction-market engines (tracked in **[Trade History](journal.md)**):

| Engine | What it does |
|---|---|
| **Polymarket Edge** | Black-Scholes / IV fair-value vs market YES price — trades the mispricing (**live, real funds**) |
| **Hourly crypto arb** | BTC hourly markets across Polymarket / Kalshi, oracle-band tuned |
| **PolyScalp / Latency / Kalshi cross-arb** | Order-book mispricing, exchange-latency and cross-venue event arbitrage |

These are the same verified, auditable engines documented in **[Bots & Automation](bots.md)** — prediction markets are a first-class market in Formion, not an afterthought.
