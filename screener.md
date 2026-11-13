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

**How to read the Bias Map**

* **Neutral vs no current read** — a **neutral** cell is a real read without a direction (no score). **No current read** means the read is stale or missing; it is not counted and is not treated as neutral.
* **Fast lane for 5m and 15m** — the short timeframes have their own priority lane: a closed candle is read starting about 10 seconds after it closes (closed candles only), and the cell usually updates within a minute.
* **Averages use current reads only** — Strength, Sector and Sunburst average only the current reads and show their **coverage** (how many markets have a current read).
* **Weekends** — forex, CFD and stock instruments (48 session instruments) are scored again on Monday; the weekend is not counted for them.
* **Accuracy: Collecting data** — measurement restarted on **2 Nov 2026** (a new measurement period), so the measured accuracy reads **Collecting data** until enough new data exists.
* **Segments** view — pre-registered segments (for example short bias on 4h, strong flips with a score of 60+, timeframes agreeing) are measured forward only from 9 Nov 2026; each reads **Collecting data** until it has at least 30 events over 14 days. The whole map stays a **Context signal**.
* **Context signal only** — no bot or filter built on the Bias Map has been proven. FORA reads it as market context and never gives an entry, stop or target from it.
* **History** — the Bias Map grid keeps the last 7 days for everyone (see **[Pricing & Tiers](pricing.md)**).

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

#### 🧠 Adaptive brain — weekly decision vs Market now

The Adaptive brain (Pro and up) shows two different things, kept apart on purpose:

* **Weekly decision** — the frozen decision of the selector for the week, with its exact decision date and time (for example *decision 2026-11-09*), the date of the last weekly run and whether it was **OK** or **Failed**. The ON lists and regimes below it belong to that decision.
* **Market now — last closed daily candle** — the same regime rule recomputed on the newest closed daily candle, for BTC, Altcoins, Crypto (all), forex, gold and indices. It is context only: the selector keeps its frozen decision and never reads these labels. Each row carries a pill:
  * **Same as decision** — the current label matches the weekly decision
  * **Changed since decision** — the market has moved to another regime since the decision (the weekly label is shown next to it)
  * **Data old** — the newest daily candle is too old to trust
  * **No current data** — the candles are missing; no label is shown instead of a guess
* **Data not current** — a red banner appears when the weekly decision is **older than 8 days** or the **latest weekly run failed**. The regimes and ON lists then stay on the page only as history, marked "Not current", until the next weekly run succeeds.

Regime labels use closed daily candles only: **Uptrend** when the close is above the 50-day EMA and the 90-day return is positive, **Downtrend** when both are negative, otherwise **Range** (also when ADX is under 18).

**Crypto is measured three ways**, because BTC and the altcoins often move differently:

| Row | What it measures |
|---|---|
| **BTC** | The BTC regime |
| **Altcoins** | An equal-weight basket of **49 altcoins** (no BTC), plus the share of altcoins trading above their EMA50 |
| **Crypto (all)** | The whole crypto class, shown for context |

* **Spec versions:** the selector's crypto specs show **v1 Retired** (the old specs that read the BTC regime for every crypto market; kept in the history) and **v2 Starts next week**. From **16 Nov 2026**, v2 judges **BTC setups in the BTC regime** and **altcoin setups in the Altcoins regime**. Its rules were written down before any result; it counts forward only.
* **The detectors never read the brain.** Buy the dip, Sell the top and S/R Flip read only the coin's **own candles** — never BTC, never the Altcoins basket and never the Adaptive brain. The brain only decides which strategies it would switch on; it trades nothing (shadow only).

#### 🔻 Sell the top — why it is often 0

An empty Sell the top list is usually **not a fault: the rule is strict**, and the empty state on the page says why. Over 30 days, 62 markets and about 10,500 4H candles:

* **Range path** — candles in a low-ADX range → at the range top → a rejection bar → **at least 2 touches of both the top and the bottom of the range**. That last step left **0**.
* **Exhaustion path** — above the 1D EMA50 → stretched at least 2.5 ATR → a red trigger bar → **a new 20-bar high**. That last step left **0**.

Historically the same rule fired about **10 times in ~166 days**; the last signal was on **28 Sep 2026**. Shorts are also never taken within 3 % of the all-time or 52-week high.

#### 🔄 Trend Shift

**Trend Shift** looks for a trend reversal on **1H, 4H and 1D**, on **49 Bybit crypto markets** and **13 FP Markets (cTrader)** markets (forex, gold, silver, oil, indices).

* **Rule:** a trend (measured by the same trend rule as the Quantum Screener, on closed bars) that lasted **at least 20 bars** flips side — directly or after **at most 12 bars without a trend** — and **within 6 bars** a close breaks the old trend's last swing (a change of character, **CHoCH**).
* **Detection** = that first breaking close. It is computed only from closed bars ending on that bar, so a detection **never repaints**.
* **No entry, stop or target.** A Trend Shift row gives side and time only. What is measured is the **move after detection minus the market's own drift** — over **24 h on 1H, 2 days on 4H, 7 days on 1D** — plus the best and worst move (**MFE / MAE**).
* **Test rule TR1** is **our** time exit (enter at the next open, exit at the close of that horizon, after costs). It is Formion's own test rule, not part of the signal.
* **Status:** every segment reads **Collecting data** until it has **30 rows over 14 days**; the forward book started on the day Trend Shift went live. The history before that was in-sample and **proved nothing** for any timeframe or side, so it is not used for the status.
* Each row has a chart of the detection with the CHoCH level; click it for a large zoomable chart.

#### Reading the rows and the paper book

* **Long / Short pill** — the side of a setup is always shown with the same pill and an icon (one shared pill across the app), never as bare text.
* **FP Markets (cTrader)** — forex, gold, silver, oil and index rows name their venue **FP Markets (cTrader)** with the FP Markets logo; crypto rows show Bybit.
* **No fill labels** — when a limit was never reached, the row reads **No fill · expired** (the deadline passed) or **No fill · cancelled** (a cancel rule hit, e.g. price closed above the impulse high before filling). An expired order is never labelled cancelled.
* **Below Pro** the paper book shows **Closed** and **Status**, and a lock teaser (unlock with Pro, the 7-day trial or FOM Lock) instead of Win rate, Avg R and Sum R. Locked numbers are never sent to your browser and never shown as fake zeros; on Pro and up a missing value shows as "—".

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


## 🔎 Details — trend chart and the three moments

Click a row in the table, a card, or a phone row to open **Details** right below it. Chart Pro opens only from the chart button, so a click never takes you away from the list.

<figure><img src=".gitbook/assets/shot-screener-details-chart.jpg" alt="Quantum Screener Details for BTC on 1h — score components, fact lines with Detected and Move began, the trend chart with Trend start, Detected and Move began markers and Best / Worst move lines, the Trend age ring and Context data"><figcaption><p>Details for BTC on 1h: Move began (amber, hindsight), Trend start (dashed line), Detected (violet), Best / Worst move since the start, and the Trend age ring (32h of 12h typical).</p></figcaption></figure>

* **Trend chart** — a real candle chart on the row's timeframe, closed candles only: price on the Y axis, time on the X axis. The time axis shows the candle's **open** time (like TradingView); the labels say "bar closed …" where the close time matters. Hover (mouse) or touch a candle to see its open, high, low and close. The dashed **Best move** and **Worst move** lines show the best and worst price move since the trend start, with % and price (the row's MFE / MAE).
* **Score components** — each part of the strength score with its value and weight, and the score shape next to it.

### The three moments

| Moment | What it is | How to read it |
|---|---|---|
| **Move began** | The last swing extreme in the trend-start bar and the **48 closed bars before it**: the highest high before a downtrend, the lowest low before an uptrend | **Hindsight** — it can only be seen afterwards. It is never a signal, an entry, a stop or a level |
| **Trend start** | The bar where our trend rule (closed bars only) first calls the trend. Example: a downtrend starts when the close is below **EMA50 − 0.25 × ATR** and **EMA20 is below EMA50** | The structural start of the trend on this timeframe |
| **Detected** | The moment our screener **live** first recorded the trend (violet marker) | Recorded at that time and never changed, never back-filled or estimated. If it was not recorded, Details says **Detection time not recorded**. It is usually within about 5 minutes of the trend-start bar's close |

Short fact lines in the box under the score components put numbers on the three moments, for example:

* **"N bars before the trend start · x % in the trend direction"** — how far Move began lies before the trend start, and how much price had already moved in the trend direction by then.
* **"x % of the move … before we detected it"** (or "before the trend start") — the share of the move from Move began to the last close that was already done at that moment.
* **Best / worst from detection** next to best / worst from the start, so you can see what was still left after the screener caught the trend.

### Trend age ring

The ring shows how old the trend is (for example **3d** in the centre). Below it: the **typical** trend duration on this timeframe (for example "of 18h typical"), the age as % of typical and a status. Age is counted in closed bars of trading time, not wall-clock time.

* **Venue** — the price source is named in Details and on the row; forex, metals, oil and index rows read **FP Markets (cTrader)** with the real FP Markets logo.
* **Not a forecast** — Details shows measured facts about a trend. It never gives an entry, stop or target.

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
