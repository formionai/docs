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

**Patterns** (chart-formation detector), **Trend** (trend-strength scan, see below), **Arbitrage** (cross-exchange price spreads and funding carry), **Order Book** (resting bids vs asks near price and walls, see below), **VWAP Bubble**, **RSI Heat**, **MACD Heat** and **EMA Cloud**.

<figure><img src=".gitbook/assets/s3-sc-heatmap.jpg" alt="RSI heatmap"><figcaption><p>RSI Heatmap — every symbol coloured by RSI.</p></figcaption></figure>

<figure><img src=".gitbook/assets/s3-sc-patterns.jpg" alt="Patterns — chart-formation detector with forward test"><figcaption><p>Patterns: detected formations, regime radar and a forward-tested track record by pattern.</p></figcaption></figure>

### 📈 Trend

<figure><img src=".gitbook/assets/s3-sc-trend.jpg" alt="Trend — regime decision and trend board"><figcaption><p>Trend: regime decision plus a trend board across crypto, commodities and US stocks.</p></figcaption></figure>

<figure><img src=".gitbook/assets/shot-screener-trend-scanner.jpg" alt="Trend scanner — how-to-read cards, timeframe, bias, sort and count filters, and one card per coin with its trend score"><figcaption><p>Trend scanner: one card per coin with its score and bias, on closed candles only.</p></figcaption></figure>

The Trend scanner gives every coin (Binance USD-M perpetuals, top by 24h volume) a **trend score from −100 to +100** on the timeframe you pick (5m → 1d):

* **Score** — built from three parts, all in % of price: EMA9 vs EMA21 (up to ±50), how much EMA9 moved over the last 18 bars (up to ±30) and price vs EMA21 (up to ±20).
* **Bias** — **Long** from +25, **Short** from −25, **Neutral** in between. It describes the recent trend; it says nothing proven about what comes next.
* **Closed candles only** — the score, bias and change % move only when a candle closes, so a signal never repaints. The last candle on the chart and the price are live, but they do not count until that candle closes.
* **How far to compare** — because the score is in % of price, the same number is not comparable across timeframes or between a calm and a wild coin.
* **Renamed or dead symbols show no score** — a symbol whose market stopped trading or was renamed (for example **TON → GRAM**, MATIC → POL) shows no score and a "Renamed to …" note, never a fake "neutral 0".

**Trend backtesting (paper book).** The **Backtesting** sub-tab measures a paper book that takes trades from the trend score on 1h. Entries, stops and targets are **Formion's own rules** (ATR-based), not anyone's signal. How the book is measured:

* A signal fires only on a **just-closed** 1h candle.
* Entry is the real executable price at that moment (ask for long, bid for short).
* Exits are taken at the **real exchange price**: a stop fills at the first real trade after it is triggered, a target fills only when price trades **through** it, and a time expiry closes at the last real trade price.
* Results are shown after costs (editable) and include the funding actually charged.
* **Measurement restarted on 2 Nov 2026.** Old rows whose recorded outcome was contradicted by exchange data were removed, so the default view starts from the restart.
* Free users see the last 7 days, Pro and up the whole book. Until there are at least 30 trades over at least 14 days the status reads **Collecting data**.

### ⚖️ Order Book

<figure><img src=".gitbook/assets/shot-screener-orderbook.jpg" alt="Order Book — how-to-read cards, band and volume filters, and the table of imbalance, bid and ask depth, walls, spread and 24h volume per coin"><figcaption><p>Order Book: resting bids vs asks near price (5-minute average), walls, spread and volume for the top 80 coins.</p></figcaption></figure>

The Order Book tab shows how the **resting orders near the current price** are split between buyers and sellers, for the top 80 Binance USD-M perpetuals by 24h volume. It is a **Context signal**: it shows the state of the book now, not where price will go, and it never gives an entry, stop or target.

* **Imbalance** = (bid − ask) ÷ (bid + ask) × 100, in dollars of resting orders **within ±0.10 % of the mid price**. Switch to **±0.25 %** with the Band filter. That wider band is shown only when the book actually reaches it; otherwise the cell shows "—". Every coin is measured over the same price distance, so the numbers are comparable.
* **The main number is a 5-minute average**, not a single snapshot, because the book changes second by second. Until five readings exist, the row says "warming up".
* **Bid heavy** = +15 % or more (more resting buy orders near price), **Ask heavy** = −15 % or less, **Balanced** in between.
* **Wall** = one price level at least **6× the median level** within ±0.25 %, seen in **2 readings in a row**. If no level passes, the cell shows "—". The biggest level on its own is not called a wall.
* **Resting orders can be pulled at any time.** A wall or a heavy side describes the state of the book, not a direction.
* All users share one snapshot of the book. If it is older than about 2.5 minutes, the tab shows a **stale** warning instead of "Live".

#### 🧱 Walls Bot & Backtesting

The **Backtesting** sub-tab (also opened from **Walls Bot →**) measures what happens when price touches a wall:

* **Walls v2** has been measured from **2 Nov 2026** on Binance USD-M perpetuals with **real fills**. A trade exists only when a real trade print touches a confirmed wall. The entry is the first real print on the taking side, i.e. at the bid or ask, 1–6 s after the touch. The stop is checked on the real trade path and fills at the first real trade after it is hit. The target fills only when price trades through it. Results are **net** of fees, slippage and real funding.
* The stop and target levels are **Formion's own strategy rules** (based on 1-hour ATR), not levels from the book or from any trader.
* **v1 is an archive** (an older, simpler measurement). It is shown below v2 and labelled "archive v1, not directly takeable".
* **Filters** (side, session, days, coin and more) work over the whole book. Every filter shows a status:
  * **Too few data** — not enough trades or days yet
  * **Collecting data**
  * **Past only, fades recently** — positive in the past but not recently
  * **Holds in both halves** — positive after costs in both halves of the period and recently
* **The first verdict needs at least 30 trades and at least 14 days.** Until then, v2 reads **Collecting data**.
* **Who sees what:** you need to be logged in. Free users see the last 7 days, and Pro and up see the whole book.


## Logos & live data everywhere

Every symbol carries its asset logo, and rows update live. Click any row to open its full chart and analysis in **Chart Pro**.

{% hint style="info" %}
On the free **Neural** tier the Screener covers crypto as a **3-row preview** (last 7 days of history; signals are delayed 30 minutes). **Pro** and **Institutional** get the full real-time screener on all markets — crypto, stocks, commodities and forex — see **[Pricing & Tiers](pricing.md)**.
{% endhint %}
