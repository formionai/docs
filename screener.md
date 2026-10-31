# 📈 Screener

<figure><img src=".gitbook/assets/s2-screener.jpg" alt="Formion Screener — ranked, scored market table with timeframe and signal columns"><figcaption>The Screener — every market, ranked by Formion's native scoring.</figcaption></figure>

<figure><video src=".gitbook/assets/rec-screener-scroll.mp4" title="Live recording: scrolling the Screener — market chips, live feed, the ranked table, then a row's chart opened inline."></video><figcaption><p>Live recording: scrolling the Screener — market chips, live feed, the ranked table, then a row's chart opened inline.</p></figcaption></figure>

The **Screener** is Formion's home view and the engine the rest of the app is built on: a ranked, sortable table of crypto, stock and forex markets, each scored by **native signals** rather than a single indicator.

Open it at **[app.formion.ai](https://app.formion.ai/?utm_source=docs&utm_medium=referral&utm_campaign=docs)** — it's the first thing you see.

## How scoring works

<figure><video src=".gitbook/assets/clip-screener.mp4" title="How a setup surfaces in the Screener"></video><figcaption><p>Trend, momentum, volume, volatility and signal tags combine into one score and a bull / bear / neutral bias.</p></figcaption></figure>

Every symbol gets one composite score:

* **Trend, momentum, volume and volatility** — live prices are scored on all four, then deduplicated across timeframes into **one number per symbol**
* **Signal tags** — structure and flow events such as FVG / order-block entries, VWAP reclaims and rejections, break of structure / CHoCH, regime changes, Wyckoff springs and Adaptive-RSI turns
* **Bias** — each row is classed bull, bear or neutral

The table shows score, price, 24h change, the strongest signals and a mini sparkline per row. Sort by any column and filter by asset class (crypto, stocks, forex), bias and signal, so you can jump straight to "what's set up *right now*".

## Sub-tools

```mermaid
flowchart LR
  SC["📈 Screener"] --> BM["🗺️ Bias Map"]
  SC --> RD["📡 Radar"]
  SC --> HU["🎯 Hunt"]
  SC --> CO["🤝 Consensus"]
  SC --> WL["⭐ Watchlist"]
  SC --> MO["➕ Patterns · Trend · Arbitrage · Order Book · Heatmaps"]
```

<figure><video src=".gitbook/assets/rec-screener-subtabs.mp4" title="Live recording: switching between Bias Map, Radar, Hunt, Consensus and Watchlist."></video><figcaption><p>Live recording: switching between Bias Map, Radar, Hunt, Consensus and Watchlist.</p></figcaption></figure>

### 🗺️ Bias Map

<figure><img src=".gitbook/assets/s3-sc-bias.jpg" alt="Bias Map — market-wide directional bias heatmap"><figcaption><p>Bias Map: green = long bias, red = short, by timeframe.</p></figcaption></figure>

A market-wide **directional bias heatmap** across 5 timeframes (5m → 1d) with a selectable anchor timeframe. Green = long bias, red = short, yellow = neutral. Twelve views (Mosaic, Matrix, Grid, Quadrant, 3D, Strength, Confluence, Treemap, Sector, Sunburst, History, Quality) and a Min-Score slider let you read the whole market's lean at a glance.

### 📡 Radar

<figure><img src=".gitbook/assets/s3-sc-radar.jpg" alt="Radar — TradingView preset scans as signal cards"><figcaption><p>Radar: preset scans rendered as signal cards.</p></figcaption></figure>

30+ TradingView preset scans (movers, breakouts, trend shifts, volume…) rendered as signal cards, across crypto, forex, indices/CFDs and stock markets (US, Canada, UK, Germany, France, Japan, Hong Kong, India, Australia). Subscribe to a preset to be alerted on fresh matches.

### 🎯 Hunt

<figure><img src=".gitbook/assets/s3-sc-hunt.jpg" alt="Hunt — top-down US-equities setup funnel"><figcaption><p>Hunt: market regime → top sectors → top industries → setup candidates.</p></figcaption></figure>

A top-down **US-equities** setup funnel (long-only): market regime (SPY/QQQ vs their 21/50 EMAs) → strongest sectors → strongest industries → ignition-and-flag and 8/21-EMA pullback setups, each with entry, stop and a 2R target.

### 🤝 Consensus

<figure><img src=".gitbook/assets/s3-sc-consensus.jpg" alt="Consensus — multi-signal confluence"><figcaption><p>Consensus: symbols ranked by how many engines agree on the same direction.</p></figcaption></figure>

Multi-signal confluence: symbols ranked by how many of Formion's engines and indicators agree on the same direction.

### ⭐ Watchlist

<figure><img src=".gitbook/assets/s3-sc-watchlist.jpg" alt="Watchlist — saved symbols with live scores"><figcaption><p>Watchlist: your saved symbols with live bias, price and volume.</p></figcaption></figure>

Your saved symbols with live scores and signals, plus a workspace to curate the list against a live multi-timeframe bias matrix.

### ➕ More lenses

**Patterns** (chart-formation detector), **Trend** (single-timeframe trend-strength scan), **Arbitrage** (cross-exchange price spreads and funding carry), **Order Book** (depth, walls and imbalance), **VWAP Bubble**, **RSI Heat**, **MACD Heat** and **EMA Cloud**.

<figure><img src=".gitbook/assets/s3-sc-heatmap.jpg" alt="RSI heatmap"><figcaption><p>RSI Heatmap — every symbol coloured by RSI.</p></figcaption></figure>

<figure><img src=".gitbook/assets/s3-sc-patterns.jpg" alt="Patterns — chart-formation detector with forward test"><figcaption><p>Patterns: detected formations, regime radar and a forward-tested track record by pattern.</p></figcaption></figure>

<figure><img src=".gitbook/assets/s3-sc-trend.jpg" alt="Trend — regime decision and trend board"><figcaption><p>Trend: regime decision plus a trend board across crypto, commodities and US stocks.</p></figcaption></figure>

<figure><img src=".gitbook/assets/s3-sc-orderbook.jpg" alt="Order Book — depth, walls and imbalance"><figcaption><p>Order Book: depth, walls and bid/ask imbalance per symbol.</p></figcaption></figure>


## Logos & live data everywhere

Every symbol carries its asset logo, and rows update live. Click any row to open its full chart and analysis in **Chart Pro**.

{% hint style="info" %}
On the free **Neural** tier the Screener covers crypto as a **3-row preview** (last 7 days of history; signals are delayed 30 minutes). **Pro** and **Institutional** get the full real-time screener on all markets — crypto, stocks, commodities and forex — see **[Pricing & Tiers](pricing.md)**.
{% endhint %}
