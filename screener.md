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

Multi-signal confluence: symbols ranked by how many of Formion's engine **families** agree on the same direction.

* **Status: Context signal · Collecting data.** Engines agreeing is context next to your own levels and trend — our study has not shown that agreement alone trades better, so Consensus is not a buy/sell signal.
* **Counted by family, not by variant.** Several variants of one engine count as one vote, so one engine with many versions cannot inflate the score. The rows still list every variant.
<figure><img src=".gitbook/assets/shot-consensus-status.jpg" alt="Consensus status note"><figcaption><p>The status note on the Consensus page: Context signal · Collecting data, votes counted per engine family, Talos counted once.</p></figcaption></figure>

* **Talos is counted once.** The Talos copy trades used to reach Consensus through two readers; they are now one family and one trade.

### ⭐ Watchlist

<figure><img src=".gitbook/assets/s3-sc-watchlist.jpg" alt="Watchlist — saved symbols with live scores"><figcaption><p>Watchlist: your saved symbols with live bias, price and volume.</p></figcaption></figure>

Your saved symbols with live scores and signals, plus a workspace to curate the list against a live multi-timeframe bias matrix.

### ➕ More lenses

**Patterns** (chart-formation detector; **Live chart** on a card opens the Formion chart with the pattern's own levels, see below), **Trend** (trend-strength scan, see below), **Zone Hunter** (rule screener measured on a paper book, see below), **Arbitrage** (cross-exchange price spreads and funding carry), **Order Book** (resting bids vs asks near price and walls, see below), **VWAP Bubble**, **RSI Heat**, **MACD Heat** and **EMA Cloud**.

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


### 📍 Zone Hunter

**Zone Hunter** (Screener → Zone Hunter, beta) is a rule screener that is measured on a paper book — not a signal service. Every rule is frozen before measuring, uses **closed candles only**, and every number on the page comes from its paper book.

<figure><img src=".gitbook/assets/shot-zone-hunter.jpg" alt="Zone Hunter — Buy the dip list with the zone chart, plan (entry, stop, targets), regime and status of each setup, and the paper book below"><figcaption><p>Zone Hunter → Buy the dip: each row shows the zone on its chart, the plan from the rule, the 1D regime and the backtest status; the paper book is below the list.</p></figcaption></figure>

| Section | What it shows |
|---|---|
| **Buy the dip** | 1D uptrend, then a 4H pullback into a zone where two of Fib 0.382–0.618, the EMA20–50 band and a prior resistance turned support overlap. Limit at the zone top. |
| **Sell the top** | Range-top rejection and trend exhaustion — research only, no proven advantage yet. Never shorted within 3% of the all-time or 52-week high. |
| **S/R Flip (1D)** | Crypto daily level break, limit back at the level. Paper forward test. |
| **Trend Shift** | An established trend flips and a close breaks its last swing (CHoCH), on 1H / 4H / 1D. Side and time only — the bias is measured forward on every row. |
| **Adaptive brain** | Which strategies the selector switches on this week and why, per market regime. Shadow only — nothing trades from it. |

* **Status** — every setup and paper book reads **Collecting data** until it has enough trades and days; the page never shows a profit promise.
* **Chart** — the **Chart** button opens the Formion chart with the asset logo and the exchange logo in the title (Bybit for crypto, FP Markets for forex, gold, oil and indices), the **Chart settings** gear, a yellow **ENTRY** circle on the candle where the limit filled and a square on the exit candle. The zone, limit, stop and targets are only the row's own levels.
* **"New signal · not filled"** — every row in the **Trades** table is its own setup (own signal candle and zone). A row marked **New signal · not filled** is a newer signal recorded after an earlier trade of the same asset closed; its limit was never reached before the deadline, so no trade was opened. It is not the same trade twice — it counts in the fill rate, not in R.

**What each plan sees**

| | Markets | Full rows per section | Sections | Paper book |
|---|---|---|---|---|
| 🆓 **Free** | Crypto | 3 | Buy the dip, Sell the top | Status + last 7 days of trades |
| 🪙 **Free + FOM Hold** | Crypto | 5 | + S/R Flip | Last 14 days |
| 🔒 **Free + FOM Lock** | Crypto | All crypto rows | + Trend Shift | Last 30 days |
| 💎 **Pro** | All (crypto, forex, gold, silver, oil, indices) | All | + Adaptive brain | Full (win rate, average R, CI, sum R) |
| 💎 **Pro + FOM Lock** | All | All | All | Full + per-trade MFE / MAE |
| 🏛️ **Institutional** | All | All | All | Full + CSV export |

The chart opens for every row your plan shows. Rows your plan does not include appear as blurred locked rows with the unlock options; their content is never sent to your browser. See **[Pricing & Tiers](pricing.md)** and **[FOM Hold vs Lock](fom-hold-vs-lock.md)**.


## Context data — Volume z and Volatility regime

Two extra readings sit next to the strength of every crypto row. They are **context data**: they describe the state of the market right now. They are **not buy or sell signals** and they are **not part of the strength score** — the ranking, phases and counts are exactly the same with or without them.

| Reading | What it is | How it is measured |
|---|---|---|
| **Volume z** | How unusual the volume of the last closed bar is | (volume of the last closed bar − average of the **previous 20 closed bars**) ÷ their standard deviation, on the screener timeframe you picked. **+2** means about two standard deviations above normal; **−1** means quieter than usual |
| **Volatility regime** | How wild the coin is now compared with **its own** recent past | 24 h realized volatility (1 h bars, annualised) as a **percentile of the coin's own last 30 days**: **Compressed** below P20 · **Normal** P20–P80 · **Elevated** above P80 · **Extreme** above P95. Hover the P number for the realized and Parkinson volatility |

<figure><img src=".gitbook/assets/shot-screener-context-details.jpg" alt="A screener card on a phone with Details open — Context data block with Volume z and Volatility regime" width="360"><figcaption><p>Details on a phone: the Context data block with Volume z on the screener timeframe (here −0.2 on 1h) and the Volatility regime (here Normal, P75 of the last 30 days).</p></figcaption></figure>

### Where you see them

* **Details** — open a row (desktop) or tap **Details** on a card or a phone row. The **Context data** block shows both readings with their timeframe, for example `Volume z · 1h` and `Volatility · 1h · 30d`.
* **Columns** — the **Columns** button adds **Volume z** and **Volatility** as optional table columns. They are **off by default**; your choice is remembered in this browser, like the view and the number of rows.
* **More filters · context data** — in the filter panel (closed by default). Filter by **Volume z ≥ 2**, **Volume z ≥ 3** or **Volume z ≤ −1**, and by regime: **Compressed**, **Normal**, **Elevated**, **Extreme** or **Elevated + Extreme**. Rows without a fresh value are left out while a filter is on, and the up/down counters follow the filter.

<figure><img src=".gitbook/assets/shot-screener-columns.jpg" alt="Columns picker — optional Volume z and Volatility columns, off by default" width="240"><figcaption><p>Columns: the two optional context columns, off until you switch them on.</p></figcaption></figure>

<figure><img src=".gitbook/assets/shot-screener-more-filters.jpg" alt="More filters · context data — Volume z and Volatility filter chips"><figcaption><p>More filters · context data: Volume z and Volatility regime filters.</p></figcaption></figure>

### Good to know

* **Coverage:** both readings are measured on **Bybit perpetual candles**, so they exist for about 88 % of crypto rows. A market without them (for example a coin listed only on Binance) shows **—** with an explanation. A new coin needs at least 7 days of hourly history before it gets a regime (**Collecting**).
* **No stale numbers:** a Volume z older than 3 bars or a regime older than 3 hours is not shown.
* **Information only:** we measured whether the volatility regime makes signals better when used as a filter — it **does not**. Use it to understand the market you are looking at (a quiet coin vs a coin in an extreme move), not as a reason to enter or skip a trade.

## Logos & live data everywhere

Every symbol carries its asset logo, and rows update live. Click any row to open its full chart and analysis in **Chart Pro**.

{% hint style="info" %}
On the free **Neural** tier the Screener covers crypto as a **3-row preview** (last 7 days of history; signals are delayed 30 minutes). **Pro** and **Institutional** get the full real-time screener on all markets — crypto, stocks, commodities and forex — see **[Pricing & Tiers](pricing.md)**.
{% endhint %}

## One Formion chart behind every table

When a table or card opens a chart — **Patterns → Live chart**, **Signals → Signal Desk → Live chart**, **Zone Hunter → Chart** and **Multi-Chart** — you get the **same Formion chart** with our own candles (crypto from Binance, Bybit or OKX; forex, gold, oil and indices from FP Markets cTrader), not an embedded TradingView widget.

<figure><img src=".gitbook/assets/shot-patterns-live-chart.jpg" alt="A Patterns card with its live chart open — UNI with the asset logo and the Binance USD-M logo in the title, a Chart settings button, Stop and Entry ref lines and a circle on the breakout candle" width="380"><figcaption><p>Patterns → Live chart: asset and exchange logo in the title, Chart settings, the pattern's own Stop and Entry ref, and a circle on the breakout candle.</p></figcaption></figure>

* **Title** — the asset logo, the symbol and the exchange logo, so you always know which market and which venue's candles you are looking at.
* **Chart settings** — the gear button, the same one as in Chart Pro: candles, wicks, grid and background. A change applies to **all charts** in the app by default; pick **This chart** to change only the chart in front of you.
* **Entry marker** — a yellow circle sits on the candle where the signal triggered, at that price (the breakout candle on Patterns, the alert candle on Signal Desk).
* **Levels only from the signal** — the zone, limit, stop and targets drawn on the chart are exactly the ones the row or card states (only those the signal has). The chart never adds levels of its own.
* **No candles for a symbol?** If our feed has no candles for that market, the chart falls back to TradingView and says so in a visible note — you never get an empty chart.

{% hint style="info" %}
The **Radar** scans and **Strategy Lab** still show TradingView charts.
{% endhint %}
