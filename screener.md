# 📈 Quantum Screener

<figure><img src=".gitbook/assets/shot-qscreener-sections.jpg" alt="Quantum Screener section cards — Trends, Context, Confluence and Track record — with the note that strength and phase are not an entry signal, and the timeframe, side, market and phase filters"><figcaption><p>The four section cards at the top of the Quantum Screener, with the Trends filters below.</p></figcaption></figure>

<figure><video src=".gitbook/assets/rec-screener-quantum.mp4" title="Live recording: the Quantum Screener — switching sections, opening a row's Details (trend chart, age ring, score shape) and the Track record."></video><figcaption><p>Live recording: the Quantum Screener — switching sections, opening a row's Details (trend chart, age ring, score shape) and the Track record.</p></figcaption></figure>

The **Quantum Screener** is Formion's home view: it shows **which markets are trending, how strong and how mature each trend is**, across crypto, stocks & ETFs, metals, oil & gas, indices, forex and agriculture. Open it at **[app.formion.ai](https://app.formion.ai/?utm_source=docs&utm_medium=referral&utm_campaign=docs)** — it is the first thing you see (menu: **Find → Quantum Screener**).

The page has four sections. Click a card to switch; the section is kept in the address (for example `app.formion.ai/?view=context`), so you can bookmark or share it.

| Section | What it shows |
|---|---|
| 📈 **Trends** | The ranked table: who is trending, how strong, which phase — with **Details** for every row |
| 🧭 **Context** | The state of the market right now: BTC daily regime, breadth, volatility regime, trend phases and unusual volume. Facts, not signals |
| 🔗 **Confluence** | Combinations of the screener with other data that were tested on history, and the candidates now measured on paper |
| 📊 **Track record** | How the screener's past trend calls did, measured live, and **Does a higher score do better?** |

{% hint style="info" %}
**Strength and phase describe the trend — how strong and how mature it is. They are not an entry signal (Context signal).** On 2022–2026 history a trend call alone did not beat the market after costs. See **What the screener is and isn't** below.
{% endhint %}

## 📈 Trends — the table

Pick a **timeframe** (5m · scalp, 15m, 1h, 4h, 1D), a side (**Long & short**, **Uptrends**, **Downtrends**), a market class and a phase (**Fresh**, **In trend**, **Pullback**, **Exhausted**); each chip shows how many markets it holds. **More filters · context data** adds the Volume z and Volatility filters (see below). Every row is read on **closed bars only**.

| Column | How to read it |
|---|---|
| **Symbol** | Asset logo, symbol and the venue its prices come from (for example Bybit, Binance USD-M, FP Markets (cTrader)), with the age of the last update |
| **Class** | Crypto, Stocks, Metals, Forex, Indices… |
| **Price · 24h** | Last price and 24h change |
| **Trend** | A mini chart of the selected timeframe |
| **RSI** · **Zone** | RSI on that timeframe and where price sits (for example discount or premium zone) |
| **Bias · phase** | **Uptrend** or **Downtrend** and the phase of the trend |
| **Since · typical** | How long the trend has lasted and how long a trend typically lasts on this timeframe |
| **MFE** · **MAE** | The best and the worst move since the trend start (see **MFE / MAE** below) |
| **Strength** | 0–100: how strong the trend is now, built from weighted components (shown in Details) |
| **Reasons** · **Tags** | Short "why" chips, for example momentum rank, ADX + VWAP, strong trend, lower highs + lows |

The line above the table counts the markets and how many are in an uptrend and a downtrend, and shows the BTC daily regime. Markets with no price history at the source right now are counted in a note instead of shown with an empty row.

## More tools in the Quantum Screener hub

The second row of the Quantum Screener holds the other trend and setup tools, in three groups:

```mermaid
flowchart LR
  QS["📈 Quantum Screener"] --> T["Trend: Trend · Bias Map · Mechanical"]
  QS --> S["Setups: Patterns · Radar · Hunt · Divergences · Zone Hunter"]
  QS --> H["Heat: Heatmaps (VWAP Bubble · RSI · MACD · EMA Cloud)"]
```

**Moved out of the Screener (Nov 2026):**

| Tool | Where it is now |
|---|---|
| **Order Book** (Imbalance and Walls) | **Data Hub → Order Book** — views Book · DOM · Imbalance · Walls. See **[Order Flow & Microstructure](order-flow.md)** |
| **Watchlist** | Your account menu (top right) → **Watchlist** and **Watchlist Builder**. See **[Trading Terminal — The App](the-app.md)** |
| **Consensus** | **Signals → Consensus** (described below) |
| **Arbitrage** | **Data Hub → Funding & Arb → Spreads** |

The **Mechanical** board is described in **[Analytics](analytics.md)**.

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

**Classic · Visual — Preset rings.** Visual draws exactly the cards of the current preset, market and page (one preset at a time):

* Distance from the centre = RSI(14) — inside the inner ring under 30, middle ring 50, outside the outer ring over 70; cards without RSI sit on the dashed outer track.
* Angle = rank by 24 h change, strongest gainer at 12 o'clock, then clockwise to the weakest; green = up, red = down, bigger dot = bigger 24 h move.
* A sweep turns every 6 s and each dot pings as it passes.

<figure><img src=".gitbook/assets/shot-visual-preset-rings.jpg" alt="Radar in Visual: preset rings"><figcaption><p>Radar → Visual: the preset’s cards placed by RSI (distance) and 24 h rank (angle).</p></figcaption></figure>

Same data as Classic, same plan limits; **Auto** (the default in [Settings → Visual mode](settings.md)) starts it in Classic — one click on **Visual** switches, and the panel remembers it. A picture of what the preset matches right now — **Context signal · not a signal**.

### 🎯 Hunt

<figure><img src=".gitbook/assets/s3-sc-hunt.jpg" alt="Hunt — top-down US-equities setup funnel"><figcaption><p>Hunt: market regime → top sectors → top industries → setup candidates.</p></figcaption></figure>

A top-down **US-equities** setup funnel (long-only): market regime (SPY/QQQ vs their 21/50 EMAs) → strongest sectors → strongest industries → ignition-and-flag and 8/21-EMA pullback setups, each with entry, stop and a 2R target.

### 🤝 Consensus

<figure><img src=".gitbook/assets/s3-sc-consensus.jpg" alt="Consensus — multi-signal confluence"><figcaption><p>Consensus: symbols ranked by how many engines agree on the same direction.</p></figcaption></figure>

Now under **Signals → Consensus**. Multi-signal confluence: symbols ranked by how many of Formion's engine **families** agree on the same direction.

* **Status: Context signal · Collecting data.** Engines agreeing is context next to your own levels and trend — our study has not shown that agreement alone trades better, so Consensus is not a buy/sell signal.
* **Counted by family, not by variant.** Several variants of one engine count as one vote, so one engine with many versions cannot inflate the score. The rows still list every variant.
<figure><img src=".gitbook/assets/shot-consensus-status.jpg" alt="Consensus status note"><figcaption><p>The status note on the Consensus page: Context signal · Collecting data, votes counted per engine family, Talos counted once.</p></figcaption></figure>

* **Talos is counted once.** The Talos copy trades used to reach Consensus through two readers; they are now one family and one trade.

**Classic · Visual — Source vote.** Visual draws the same clusters as the cards: one half-circle ballot per symbol (desktop the first 12, phones 8), in the same order.

* Each engine family is a vote dot — long votes fill the arc in green from the left, short votes in red from the right; the needle settles on the long share.
* The label is the card's verdict: Strong long / Long / Mixed / Short / Strong short (Strong = 3+ families on one side, softly glowing).
* The vote replays only when the family counts change (the page reloads every 90 s or on Refresh).

<figure><img src=".gitbook/assets/shot-visual-consensus-vote.jpg" alt="Consensus in Visual: source vote"><figcaption><p>Consensus → Visual: one ballot per symbol; green long votes, red short votes.</p></figcaption></figure>

Same data as Classic, same plan limits; **Auto** (the default in [Settings → Visual mode](settings.md)) starts it in Classic — one click on **Visual** switches, and the panel remembers it. Agreement is not a measured signal and no entry, stop or target is drawn — **Context signal · not a signal**.

### 🏁 Strength Rank — Classic · Visual

**Strength Rank** (/screener/strength-rank) ranks every Bybit linear perp by trend strength (percentile, 100 = strongest). In the **Ranking** section a **Classic · Visual** switch sits above the table. **Visual** = **Strength race**: today's top 10 coins replayed day by day over the last 14 days (**Free: last 7 days**, same plan limit as Classic).

* Each coin is a lane with its real logo; bar length = that day's strength percentile; lanes re-order by that day's strength.
* A coin that climbed turns green with a glowing trail; a coin that fell fades red.
* Days are marked **snapshot** (taken that day) or **rebuilt** (reconstructed later). The race plays once and rests on the newest day; **Replay** restarts it.

<figure><img src=".gitbook/assets/shot-visual-strengthrace.jpg" alt="Strength Rank in Visual: strength race"><figcaption><p>Strength Rank → Visual: how today's top 10 got there, day by day.</p></figcaption></figure>

Strength describes the trend — it is a **Context signal**, not an entry signal.

### ⭐ Watchlist

The Watchlist is no longer part of the Screener: open it from your **account menu → Watchlist** (and **Watchlist Builder**). See **[Trading Terminal — The App](the-app.md)**.

### ➕ More lenses

**Patterns** (chart-formation detector; **Live chart** on a card opens the Formion chart with the pattern's own levels, see below), **Trend** (trend-strength scan, see below), **Divergences**, **Zone Hunter** (rule screener measured on a paper book, see below) and **Heatmaps** with the views **VWAP Bubble**, **RSI**, **MACD** and **EMA Cloud**.

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

### ⚖️ Order Book → moved to Data Hub

Order book imbalance, walls and the Walls Bot paper book now live in **Data Hub → Order Book** (views **Imbalance** and **Walls**). The old addresses still open the same pages. See **[Order Flow & Microstructure](order-flow.md)**.

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

**Classic · Visual — Trend shift replay.** Above **Shifts detected** a **Classic · Visual** switch replays one shift (the latest 12 as chips, with the section's filters) on its closed candles in about 9 s:

* The old trend is shaded, the swing the close broke (**CHoCH** — the rule's only level) is marked, a dotted line marks the bar where the trend flipped and a pulse marks the detection close (with the volume ratio when volume confirmed).
* An RSI divergence line appears only when the row has a divergence.
* At the end every horizon shows the measured move after detection against the asset's own drift — the number Classic shows — or how many bars are left.

<figure><img src=".gitbook/assets/shot-visual-tshift-replay.jpg" alt="Trend Shift in Visual: trend shift replay"><figcaption><p>Zone Hunter → Trend Shift → Visual: old trend, the broken swing (CHoCH), the flip and the detection close.</p></figcaption></figure>

No entry, stop or target — **Collecting data · not a signal**. Same data as Classic, same plan limits; **Auto** (the default in [Settings → Visual mode](settings.md)) starts it in Classic — one click on **Visual** switches, and the panel remembers it.

#### Reading the rows and the paper book

* **Long / Short pill** — the side of a setup is always shown with the same pill and an icon (one shared pill across the app), never as bare text.
* **FP Markets (cTrader)** — forex, gold, silver, oil and index rows name their venue **FP Markets (cTrader)** with the FP Markets logo; crypto rows show Bybit.
* **No fill labels** — when a limit was never reached, the row reads **No fill · expired** (the deadline passed) or **No fill · cancelled** (a cancel rule hit, e.g. price closed above the impulse high before filling). An expired order is never labelled cancelled.
* **Below Pro** the paper book shows **Closed** and **Status**, and a lock teaser (unlock with Pro, the 7-day trial or FOM Lock) instead of Win rate, Avg R and Sum R. Locked numbers are never sent to your browser and never shown as fake zeros; on Pro and up a missing value shows as "—".
* **Where it works: setup × market** — under Buy the dip, one row per setup (dip-S1, dip-S2) and market (Crypto, Commodities, Forex, Indices & stocks): the paper book's own closed trades, Avg R, 95 % range and status next to the backtest result. Every setup and market stays visible — a weak one is a filter, not hidden. **Best right now** names a segment only when the paper book proves it; until then it names the strongest backtest cell and says it is still collecting data.
* **Our SL variant (paper): behind liquidity** — our own stop rule, not the setup's result. Every new dip-S1 idea gets a paper twin with the same entry, targets and costs, but the stop just behind the nearest significant swing low under the zone (0.1 ATR below it), where the backtest showed stops often get swept. The card shows closed pairs, the R difference (twin minus live), its 95 % range and days measured. It stays **Collecting data** until 30 closed pairs and 14 days; the live stop does not change.

#### ⏳ Missed trades (not filled)

Below the Buy the dip performance a card **Missed trades (not filled)** shows what happened to limit orders that never filled. They count in the fill rate, not in the book's P&L.

<figure><img src=".gitbook/assets/shot-zone-hunter-missed.jpg" alt="Missed trades (not filled) card — Not filled count, closest approach, control total and average, why not filled, would have been (control), per market and per idea"><figcaption><p>Missed trades (not filled): why each order did not fill, how close price came to the limit, and the control — labelled "Control · not the book result".</p></figcaption></figure>

* **Why not filled** — the reason per idea:
  * **Ran away** — a 4H candle closed above the cancel level (the first target) before the limit was touched, so the order was cancelled.
  * **Expired** — 12 4H candles passed without touching the limit.
* **Closest approach** — how close price came to the limit, in %, R and ATR.
* **Would have been (control)** — the same idea bought **at market** right after the signal, with its own stop, targets and time exit, net of costs. This is a **control, not the book's result** — the rules are unchanged.
* **Read the control with care** — "Ran away" means price had already gone past the first target, so a market entry on exactly these ideas looks good almost by construction. Our pre-registered test of a market entry on every signal did not confirm it, which is why the limit rule stays.
* **Control totals** (total, average and per market) are part of the full book statistics on **Pro** and up.
* In the Journal, hover a **Not filled** row for its reason and closest distance.

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


## 🎛️ Classic · Visual — screener views

Each view below has a **Classic · Visual** switch. Visual draws the **same answer** the page already loaded — nothing new is fetched, and your plan limits are the same as in Classic. **Auto** (the default in [Settings → Visual mode](settings.md)) starts these panels in Classic; one click on **Visual** switches, and the panel remembers it.

* **Trends** (home page) — **Trend orbit**: the BTC daily regime in the core, every trending market a body with its logo on a ring by trend strength (inner ring 85+, outer under 60). Green = uptrend, red = downtrend; orbit speed = momentum percentile, size = the 24 h move; pulsing halo = fresh trend, dashed outline = exhausted.
* **Trend** — **Trend pulse wall**: one tile per perp with its trend score (−100…+100, closed bars only); green long from +25, red short from −25, amber neutral. A strong trend pulses fast and deep, a weak one barely moves.
* **Regime Detector** — **Regime barometer**: one dial per asset class (Crypto, Forex, Metals, Energy, Indices, Stocks & ETFs) from Bear through Distribution, Range and Accumulation to Bull; the needle = average trend bias of the class. Recent regime changes replay as trails. Regimes come from closed candles and arrive late by construction.
* **Bias Map** — **Bias field**: the most-traded instruments × timeframes (5m … 1d); green long, red short, amber neutral, grey = no current read. Only tiles whose bias changed flip again on a refresh. Side boxes: long/short split per timeframe and the measured direction hit rate before costs (still collecting data).
* **Heatmaps → RSI / MACD** — **Breathing heatmap**: one cell per market; green above neutral, red below, deeper = further from neutral; a solid ring = RSI ≥ 70 / ≤ 30 or a strong MACD histogram; a ripple = a fresh MACD signal-line cross. Click a cell to open its chart.
* **Heatmaps → VWAP Bubble** — **Floating bubbles**: left–right = distance from the 24 h VWAP, up–down = 24 h change, size = 24 h volume, colour = funding sign. Dashed lines = ±1σ of all markets in view.
* **Heatmaps → EMA Cloud** — **Trend cloud**: every perp placed against its own EMA 8/13/21/34/55 cloud (above all five, inside, below all five); colour = ribbon alignment score from +4 green to −4 red.
* **Zone Hunter** — **Zone magnet**: one lane per setup; the magnet is the study's own zone or limit, the coin is the price at its real distance from it. Closer = stronger field; setups at the level glow. Every setup is an unproven paper study — **Collecting data**.
* **Hunt** — **Hunt scope**: the stored daily US-stock snapshot as a funnel (market gate Go / Halt from SPY and QQQ, universe, liquid stocks, top sectors and industries, setups), then one card per candidate with its book status. A rule-built watchlist, not a buy signal.
* **Divergences** — **Divergence draws itself**: for the selected divergence the candles and the detector's own indicator reveal bar by bar, then the price line and the indicator line A→B draw together — the slopes disagree, which is the divergence; the bars after pivot B show the move since.
* **Patterns** — **Pattern draws itself**: the detector's reading replayed on the card's closed candles — touch points, pattern lines, breakout bar, then the rule's entry zone, stop and targets exactly as the detector returned them. **Ghosts of history**: our forward record of closed setups per pattern type × timeframe — green ghosts rise (closed in profit), red ghosts sink (closed at a loss), the bar = average R after costs. Both are **Collecting data**.
* **Watchlist** — **Ticker wall**: every pair of your list as a board tile with logo, price, 24 h change, volume, a 24 × 1 h sparkline and the 1 h screener trend; tiles flip green or red when the price changes.

<figure><img src=".gitbook/assets/shot-visual-market-galaxy.jpg" alt="Trends in Visual: trend orbit"><figcaption><p>Trends → Visual: markets orbit the BTC regime by trend strength; green uptrend, red downtrend.</p></figcaption></figure>

<figure><img src=".gitbook/assets/shot-visual-regime-barometer.jpg" alt="Regime Detector in Visual: regime barometer"><figcaption><p>Regime Detector → Visual: one dial per asset class from Bear to Bull.</p></figcaption></figure>

<figure><img src=".gitbook/assets/shot-visual-bias-field.jpg" alt="Bias Map in Visual: bias field"><figcaption><p>Bias Map → Visual: closed-bar bias of each instrument on every timeframe.</p></figcaption></figure>

<figure><img src=".gitbook/assets/shot-visual-heat-breathe-rsi.jpg" alt="RSI Heatmap in Visual: breathing heatmap"><figcaption><p>RSI Heatmap → Visual: the further from neutral, the deeper the colour and the faster the cell breathes.</p></figcaption></figure>

<figure><img src=".gitbook/assets/shot-visual-vwap-bubbles.jpg" alt="VWAP Bubble in Visual: floating bubbles"><figcaption><p>VWAP Bubble → Visual: distance from the 24 h VWAP against the 24 h change.</p></figcaption></figure>

<figure><img src=".gitbook/assets/shot-visual-trend-wall.jpg" alt="Trend in Visual: trend pulse wall"><figcaption><p>Trend → Visual: one breathing tile per perp with its trend score.</p></figcaption></figure>

<figure><img src=".gitbook/assets/shot-visual-hunt-scope.jpg" alt="Hunt in Visual: hunt scope"><figcaption><p>Hunt → Visual: the daily US-stock funnel and its candidates.</p></figcaption></figure>

<figure><img src=".gitbook/assets/shot-visual-divergence-draw.jpg" alt="Divergences in Visual: divergence draws itself"><figcaption><p>Divergences → Visual: price and indicator lines from pivot A to pivot B.</p></figcaption></figure>

<figure><img src=".gitbook/assets/shot-visual-patterns-draw.jpg" alt="Patterns in Visual: pattern draws itself"><figcaption><p>Patterns → Visual: the detector’s pattern, breakout and rule levels drawn on the candles.</p></figcaption></figure>

Every view is labelled **Context signal · not a signal** (Zone Hunter and Patterns: **Collecting data · not a signal**) — a drawing of the table, never an entry, stop or target.

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

### Move since start and Score shape

<figure><img src=".gitbook/assets/shot-qscreener-details.jpg" alt="Details for BTC on 1h — score components with the Score shape radar, fact lines, the trend chart, the Trend age ring (33h of 12h typical), Move since start (Worst −0.4 %, Now +7.3 %, Best +8.7 %) and Context data"><figcaption><p>Details: Score shape next to the components, the Trend age ring and the Move since start bar on the right.</p></figcaption></figure>

* **Move since start** — a bar from **Worst** (left) through **Start** (0 %) to **Best** (right), with a **Now** marker where price is today. It is the same best and worst move as the MFE / MAE columns, drawn on one line.
* **Score shape** — a radar of the strength components (market context, structure, ADX, trend, momentum) next to the component bars, so you see at a glance whether a high strength comes from one part or from all of them.
* **Trend age ring** colours — calm while the trend is younger than typical, warmer above **100 %** and **150 %** of the typical length. Weekends and closed sessions do not age a trend, because age counts closed bars.

### MFE / MAE — what Best and Worst move mean

* **Measured from the trend start** — the close of the **first closed bar of the trend**, on the timeframe you picked.
* **Closed bars only** — the live, unfinished bar is not counted.
* **Direction** — for an **uptrend** it is the long view (MFE = highest move up, MAE = deepest move down); for a **downtrend** it is the short view (MFE = deepest move down, MAE = highest move up).
* **They describe the move, they are not an entry, a stop or a target.** Nobody could have entered exactly at the trend start, and the numbers never tell you where to place an order.

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

## 🧭 Context — the state of the market

<figure><img src=".gitbook/assets/shot-qscreener-context.jpg" alt="Quantum Screener Context section — BTC daily regime, breadth, volatility regime, trend phases, unusual volume, breadth by market, heatmap links and measured trend facts"><figcaption><p>Context on 1h: BTC daily regime, breadth (uptrend / no trend / downtrend), volatility regime, trend phases, unusual volume, breadth by market and the measured trend facts.</p></figcaption></figure>

**Context** reads the same closed-bar rows as the Trends section and shows only facts — no entries, stops, targets or buy / sell calls. Use it to see whether the market is broad or narrow, calm or wild. Pick the timeframe (15m, 1h, 4h, 1D) at the top.

* **BTC daily regime** — the trend rule on BTC's closed daily bars (Uptrend, Downtrend or No trend).
* **Breadth** — how many markets are in an uptrend, in no trend and in a downtrend, and the same **by market** (crypto, stocks, forex, indices, metals, oil & gas, agriculture).
* **Volatility regime** — how many crypto markets are Compressed, Normal, Elevated or Extreme against their own last 30 days.
* **Trend phases** — how many trends are Fresh, In trend, in a Pullback or Exhausted. Phases describe maturity; on history none of them sorted outcomes on its own.
* **Unusual volume** — markets whose last closed bar has a **volume z of 2 or more**: unusual activity, not a direction.
* **Heatmaps** — shortcuts to VWAP Bubble, RSI, MACD and EMA Cloud.
* **Measured 2022–2026, not a signal** — the facts in the next section.

## 🔗 Confluence — measured combinations

<figure><img src=".gitbook/assets/shot-qscreener-confluence.jpg" alt="Quantum Screener Confluence section — History test 382, Verified 0, next review 23 Nov to 7 Dec 2026, paper candidates with Collecting data status and the Tested on history table"><figcaption><p>Confluence: 382 combinations tested on history, 0 Verified, five paper candidates (Collecting data) and what each tested use means.</p></figcaption></figure>

**Confluence** shows only measured combinations of the screener with other data. **Nothing here is a signal unless it shows Verified — and today none does.**

* **History test** — **382** combinations were written down in advance and tested on **2022–2026** history (611 Binance perpetuals incl. delisted coins, costs and funding included; discovery 2022 – Apr 2025, then a once-only holdout to Oct 2026, corrected for testing many combinations). **0** were Verified.
* **Paper candidates** — five combinations are now measured on **new days** with frozen rules (weekly long the 10 strongest 1D uptrends / short the 10 strongest 1D downtrends, 4h calls against the BTC daily regime, 4h uptrends on top-20 coins while BTC is in a daily downtrend, 1D downtrends with taker selling, 1D downtrends held until the screener ends the trend). Each reads **Collecting data**; it can become **Verified** only with at least **30 results over 14 days**, a range above zero and a net positive result. The first look is planned for **23 Nov – 7 Dec 2026**; the weekly book needs about 30 weeks.
* **Tested on history** — what each use of the screener showed:

| What was tested | Status |
|---|---|
| A trend call on its own (direction) | Context signal |
| Strength 0–100 at the trend start | Context signal |
| Phase (fresh / in trend / pullback / exhausted) | Context signal |
| Why-chips (structure, ADX + VWAP, higher timeframe, sweep, zone) | Context signal |
| + funding, open interest, taker flow, top-trader L/S, RSI, VWAP, volume z | Context signal |
| Our exits (trend end, ATR trail, typical length, fade) | Keep refining |
| Screener as a filter for Patterns setups | Context signal |
| Screener as a filter for Pulse plans (1D agrees) | Collecting data (needs at least 100 plans) |

## 📊 Track record — how past calls did

<figure><img src=".gitbook/assets/shot-qscreener-track-record.jpg" alt="Track record of 1h trend calls — uptrend and downtrend cards with calls judged, direction right, beat the market, average vs market, typical length and median best / worst, all Collecting data"><figcaption><p>Track record for 1h calls: uptrend and downtrend calls measured live since 8 Nov 2026, each card reading Collecting data.</p></figcaption></figure>

Every trend call is recorded when it starts on a closed bar and judged after a fixed horizon (for example **1 day** for 1h calls): did price move the called way, and did it **beat the equal-weight market of its class**? Pick the timeframe and side at the top.

* **Cards per side** — **Calls judged**, **Direction right**, **Beat the market**, **Avg vs market / call**, **Typical length** and **Median best / worst**. Results are averages per call with 95 % ranges, never a sum.
* **By trend phase** and **By side, BTC regime and coin group** — the same measurement split into segments.
* **Status** — a segment shows **Verified** only with at least **30 calls over 14 days**, a range above the market **and** above the asset's own recent drift, and only if it still holds after correcting for the many segments tested. Until then it reads **Collecting data**. The live measurement started on **8 Nov 2026**.
* Markets that were closed at the horizon (weekend, session break) are judged at their last close before it.

### Does a higher score do better?

<figure><img src=".gitbook/assets/shot-qscreener-calibration.jpg" alt="Does a higher score do better? — calls grouped by strength at the trend start (under 50, 50–70, 70–85, 85 and up) with calls judged, direction right, average vs market and status Collecting data"><figcaption><p>Calibration: calls grouped by their strength at the trend start, all Collecting data so far.</p></figcaption></figure>

This table groups calls by their **strength at the trend start** (**<50**, **50–70**, **70–85**, **≥85**) and by phase, judged exactly like the calls above, plus the change **per +10 score points**. A higher score counts as better only when it measurably beats the market more, with at least 30 calls over 14 days. **Today it reads Collecting data**: most trends start with a strength below 50. Until it is proven, the score is a **ranking of trend quality, not a better chance of profit**.

## 🔍 Indicator scan — your indicator on every coin

<figure><img src=".gitbook/assets/shot-qscreener-indicator-scan.jpg" alt="Quantum Screener Indicator scan — an EMA indicator with the condition Fast is above Slow on 1h, the table of matching coins with logo, value, true since, last event and a chart link"><figcaption><p>Indicator scan: one condition of your own indicator, judged on the last closed candle of every coin.</p></figcaption></figure>

**Indicator scan** runs **any indicator from your library** — Formion indicators (Pulse Consensus, Liquidity Sweep …), your Pine scripts and your TS / FORA indicators — over many coins at once. Open it from the section card, or from the ⋯ menu of an indicator on the chart → **Scan all coins**.

1. Pick the **indicator** and the **timeframe** (15m, 1h, 4h, 1D).
2. Pick **one condition** on one of its plots — the same conditions as [indicator alerts](chart-indicators.md): crosses up / down, is above / below a value or another plot, turns positive / negative, changes colour, a marker appears, a background turns on, a new value appears.
3. Pick how many **coins** (Binance perpetuals ranked by 24h volume; gold, oil and stocks perpetuals optional) and, for events, how recent they must be (**last candle … last 10 candles**). Press **Scan coins**.

* The condition is judged on the **last closed candle** — never a forming one, so the table does not repaint.
* **Table**: coin logo and symbol, **Match**, **Value** (the plot on the last closed candle), **True since** (for "is above / is on") or **Event** (when it happened), **Last event** (the last time the condition became true — when an alert would have fired) and **Open** (the chart). Sort by any column; **Matches only** hides the rest.
* **Refresh on candle close**: the table updates itself after the next candle closes. The same scan again is free.
* **Create alert for all matches**: one server alert per matching coin, with the same condition (counts against your alert limit).
* The scan runs in a separate background worker, so the app stays fast; a big list shows its progress.

| Plan | Coins per scan | New scans a day |
| --- | --- | --- |
| Free | top 20 | 1 |
| Free + FOM Hold | top 30 | 2 |
| Free + FOM Lock | top 50 (+ gold, oil, stocks) | 3 |
| Pro | top 100 | 30 |
| Pro + FOM Lock | top 150 | 60 |
| Institutional | all (up to 300) | unlimited |

### 🧪 Measure this indicator

<figure><img src=".gitbook/assets/shot-qscreener-indicator-measure.jpg" alt="Measure this indicator result — the verdict word, discovery and unseen results after costs and beyond drift, and the segment map by side, BTC regime, coin group and timeframe"><figcaption><p>Measure: your condition as entries on many coins, judged on a part of history it never saw.</p></figcaption></figure>

<figure><img src=".gitbook/assets/shot-qscreener-indicator-segments.jpg" alt="Where it works — and where not: segments by side, BTC regime, coin group and timeframe with unseen trades, average after costs, beyond drift, 95% range, win rate and status"><figcaption><p>The segment map: where the condition held on the unseen part and where it did not.</p></figcaption></figure>

**Measure** tests **your own condition** on many coins and up to 1,500 closed candles each (switch **Scan coins → Measure**, or ⋯ → **Measure this indicator** on the chart).

* **Entries**: long and / or short when your condition becomes true on a closed candle; filled at the **open of the next candle**. One position per coin and side.
* **Exits — only yours**: **Hold N candles**, **Stop / target %** (+ close after N candles) or **Exit condition**. Formion never adds a stop or a target. Fixed holds of 1, 6 and 24 candles are shown as a **control**.
* **Costs**: 7 bps per side by default (fee + slippage), you can change it.
* **Unseen part**: the last 40 % of the time span is kept aside and judged only at the end.
* **Beyond drift**: each trade minus the coin's own average move with the same exit (did the condition add anything?).
* **Where it works — and where not**: segments by **side × BTC regime** (BTC above / below its EMA 200) **× coin group × timeframe**. A segment counts only if the older part chose it and it then held on the unseen part after a correction for testing many segments.
* **Best right now**: the segments that held up in **today's** BTC regime.
* **Look-ahead check**: the indicator is recomputed from only the candles that existed at four points in time; if the answer changes, the measurement is **refused** — the script peeks into the future or repaints.
* **Result word**: **Keep refining** (does not make money on the unseen part after costs), **Market-driven** (only as good as the coins moved on their own) or **Collecting data** (too few trades, not strong enough yet, or segments that held — the next proof is new candles). Never a promise.
* Every result has its own link; FORA can start a measurement and read the result for you.

| Plan | Measurements a day | Coins | Timeframes |
| --- | --- | --- | --- |
| Free, Free + FOM Hold | — | — | — |
| Free + FOM Lock | 1 | 10 | 1 |
| Pro | 3 | 30 | 2 |
| Pro + FOM Lock | 5 | 40 | 3 |
| Institutional | 10 | 60 | 3 |

## 🧾 What the screener is and isn't

**It is** a clear, live map of which markets trend, how strongly and for how long — measured context you can read in seconds. **It isn't** an entry signal: a trend call, its strength and its phase are a **Context signal**.

Measured on 2022–2026 history (the same trend rule replayed on closed 1h / 4h / 1D bars of 611 Binance perpetuals, delisted coins included):

* **Typical trend length** — **13–16 closed bars on every timeframe** (1h ≈ 13 h, 4h ≈ 60 h, 1D ≈ 16 days).
* **Time spent in a trend** — about **85 %** of the time. Being in a trend alone does not single a market out; strength, age and phase matter more.
* **"Exhausted" is not the end** — 12 bars later, **70 %** of 1h trends that turned exhausted were still alive, vs **52 %** after a fresh start. That is a survival statistic (an exhausted trend is already an old trend that survived), **not a reason to enter** and not a "stronger trend".
* **Median best move from the start** — +2.2 % (1h) · +4.8 % (4h) · +13.5 % (1D). **Median worst move** — −1.8 % (1h) · −3.8 % (4h) · −10.0 % (1D).

## 🟢 Live Feed — the LIVE dot and your exchange

<figure><img src=".gitbook/assets/shot-livefeed-live.jpg" alt="Live Feed strip — seven crypto cards with the green LIVE dot, the Binance logo, price, 24h change, 24h sparkline and 24h low / high"><figcaption><p>The Live Feed strip with the green LIVE pill and a live dot on every card.</p></figcaption></figure>

The **Live Feed** strip on the home page (and above the chart in Chart Pro) streams price, 24h change, the 24h low / high and a 24h hourly sparkline.

| Dot / pill | Meaning |
|---|---|
| 🟢 **Live** (glowing, pulsing ring) | The last tick arrived less than **10 s** ago |
| 🟡 **Delayed** | **10–60 s** without a tick |
| ⚪ **Offline** | More than **60 s** without a tick, or the connection dropped. When the network is back it turns **Live** again at once |

With reduced motion switched on, the dot glows without pulsing. The header shows the exchange and market (for example **Binance · USDT perp**). Choose the exchange in **Settings → Live Feed exchange** (see **[Trading Terminal — The App](the-app.md)**): Binance (default), Bybit, OKX, Bitget or Hyperliquid. Every number on a card comes from the chosen exchange only — a coin it does not list shows **Not listed on …** with the exchange name (for example *Not listed on Hyperliquid*), never another exchange's price.

## 📊 Performance — Backtest and Forward test

Every tool that keeps a measured book of trades now has the same **Performance** section with two sub-tabs. It shows only trades the tool's own book stored — the entry, stop and targets of each row are the tool's own levels, never numbers we add afterwards.

| Sub-tab | What it holds | How to read it |
|---|---|---|
| **Backtest** | History: the pre-registered backtest (where the tool has one) plus every closed paper trade of its book | Background only. It shows how the rule behaved before; it is not the verdict |
| **Forward test** | **Only new days after the rules were frozen** ("measuring since …"), open and closed trades | The real test. The status word is judged here |

<figure><img src=".gitbook/assets/shot-performance-panel.jpg" alt="Zone Hunter Buy the dip performance — Forward test with KPI tiles, equity curve in R, outcomes donut, R per trade histogram, heatmap, by coin, by side, by segment and the journal"><figcaption><p>Performance → Forward test (Zone Hunter · Buy the dip): KPI tiles, the equity curve, outcomes, R per trade, the heatmap, the breakdowns and the journal.</p></figcaption></figure>

**What is inside each sub-tab**

* **KPI tiles** — Closed, Win rate, Avg R (with its 95 % CI), Profit factor, MFE median, MAE median, Open / skipped, Max drawdown and Period. The line below says how many more closed trades are needed before the first judgement.
* **Equity curve** — an area curve in **R**, **%** or **$** (the switch in its corner). Books that store no stop show **%** only. **Chart settings → Performance**: chart type (Area, Line, Step), colours above and below zero, grid, drawdown shading, zero line and log scale for $.
* **Outcomes** — a donut of Won, Lost, Breakeven, Not filled and the other end states.
* **R per trade** — a histogram of results.
* **When it worked** — a heatmap **Month × day** or **Hour × day**, as a sum or an average.
* **By coin**, **By side** and **By segment** — where the result came from.
* **MFE vs MAE** — how far each trade went for you and against you (shown where your plan includes per-trade MFE / MAE).
* **Journal** — every trade with the asset and exchange logo, side, status, entry and exit time and price, result and MFE / MAE. Filter **All · Open · Closed · Not taken**. Click **Chart** on a row to open that trade on the Formion chart (see **[Chart Pro → Trade chart](chart-pro.md)**).

### 🔎 Filters

<figure><img src=".gitbook/assets/shot-perf-filter-bar.jpg" alt="The filter bar of the Performance panel on Zone Hunter — Market, Outcome and Period chips with their trade counts, and the Symbol search"><figcaption><p>The filter bar above the Performance panel: each chip shows how many trades it holds with the other filters applied.</p></figcaption></figure>

Every Performance panel has the same filter bar above it. Pick a filter and the tiles, curve, charts and journal show only those trades. **Outcome** and **Period** are always there; **Market**, **Side**, **Setup** and **TF** appear only when the book holds more than one choice (for example **Side** only when it has both longs and shorts).

* **Market** — All, Crypto, Forex, Commodities, Indices, Stocks. Only the markets the book really holds (a market your plan does not include shows a lock).
* **Side** — All, Long, Short.
* **Outcome** — All, Won, Lost, Breakeven, Open, Not filled, Skipped: what came in and what did not.
* **Setup** — when the book has more than one setup or section.
* **TF** — when the book has more than one timeframe.
* **Symbol** — type a symbol to see only that asset.
* **Period** — All time, 7d, 30d, 90d.

How it works:

* **Counts** — each chip shows its number of trades with the other filters already applied, so you see right away whether a filter leaves enough trades. Where your plan does not include the book's numbers, the chips show no counts.
* **Filtered line** — above the panel: what is filtered and **n** = closed trades left. **Reset** clears all filters.
* **Shareable link** — the choice is saved in the page address (`?pf=…`) and in your browser, so a link opens the same filtered view.
* **Status of a filtered view** — a subset was never tested on its own, so it never reads **Verified**. Under 30 closed trades it reads **Collecting data**; with 30+ closed trades and a 95 % range fully below zero it reads **Keep refining**.
* **One filter per page** — where the page has its own market chips (Zone Hunter), they and the panel's **Market** chips are the same filter: you pick once.
* **Plans** — on Zone Hunter, Free and the FOM steps below Pro show **crypto only**; forex, metals, oil and indices are part of Pro. Locked trades are never sent to your browser.

Where you find it: Zone Hunter, Bias Map → Backtesting, Patterns, Trend → Backtesting, Hunt and Data Hub → Volatility (and every other tool listed below).

**Status words**

* **Verified** — only from **30 closed trades** in the forward test, and only when the measurement holds up. Below 30 closed trades a book never shows Verified.
* **Collecting data** — not enough new trades yet. A tool without a measured book also shows **Collecting data**, never invented numbers.
* **Context signal** — useful to understand the market, not shown to work as a trade on its own.
* **Keep refining** — the rule as it stands has not held up.

**Where you find it**

* **Bias Map → Backtesting** — paper book with its own R curve.
* **Zone Hunter** — Buy the dip, S/R Flip and Trend Shift (Trend Shift test rule TR1 in %).
* **Patterns** — the pattern book.
* **Hunt** — US-equities setups.
* **Trend → Backtesting** — the trend book, in %.
* **Divergences**, **OI Surge**, **Funding** and **Arbitrage** scanners in the Data Hub.
* **Walls** in Data Hub → Order Book.
* **Signal Desk** — reads **Collecting data** (no frozen book yet).

Plan limits are the same as before: what your plan does not include stays locked and its numbers are never sent to your browser. See **[Pricing & Tiers](pricing.md)**.

## Logos & live data everywhere

Every symbol carries its asset logo, and rows update live. Click a row to open **Details** below it; the **Chart** button opens the full chart in **Chart Pro**.

{% hint style="info" %}
On the free **Neural** tier the Quantum Screener covers **crypto (top 50)** with **3 full rows**; the other rows appear as locked rows with the unlock options. **Pro** and **Institutional** get the full real-time screener on **all markets** — crypto, stocks & ETFs, metals, oil & gas, indices, forex and agriculture — see **[Pricing & Tiers](pricing.md)**.
{% endhint %}

## One Formion chart behind every table

When a table or card opens a chart — **Patterns → Live chart**, **Signals → Signal Desk → Live chart**, **Zone Hunter → Chart** and **Multi-Chart** — you get the **same Formion chart** with our own candles (crypto from Binance, Bybit or OKX; forex, gold, oil and indices from FP Markets cTrader), not an embedded TradingView widget.

<figure><img src=".gitbook/assets/shot-patterns-live-chart.jpg" alt="A Patterns card with its live chart open — UNI with the asset logo and the Binance USD-M logo in the title, a Chart settings button, Stop and Entry ref lines and a circle on the breakout candle" width="380"><figcaption><p>Patterns → Live chart: asset and exchange logo in the title, Chart settings, the pattern's own Stop and Entry ref, and a circle on the breakout candle.</p></figcaption></figure>

* **Title** — the asset logo, the symbol and the exchange logo, so you always know which market and which venue's candles you are looking at.
* **Chart settings** — the gear button, the same one as in Chart Pro: candles, wicks, grid and background. A change applies to **all charts** in the app by default; pick **This chart** to change only the chart in front of you.
* **Entry marker** — a yellow circle sits on the candle where the signal triggered, at that price (the breakout candle on Patterns, the alert candle on Signal Desk).
* **Levels only from the signal** — the zone, limit, stop and targets drawn on the chart are exactly the ones the row or card states (only those the signal has). The chart never adds levels of its own.
* **Status strip** — a chart opened from a trade row shows that trade's status (Waiting, Active with the live R, Won, Lost, Breakeven, Expired, Not filled, Closed), its side and its result. The yellow entry circle is drawn only on the real fill candle — never for a trade that did not fill.
* **Live** — **Chart settings → Trade → Follow live** keeps the chart moving: the forming candle, a **Last** price line and the view follows the newest candle. A closed trade's result stays frozen. See **[Chart Pro → Trade chart](chart-pro.md)**.
* **No candles for a symbol?** If our feed has no candles for that market, the chart falls back to TradingView and says so in a visible note — you never get an empty chart.

{% hint style="info" %}
The **Radar** scans and **Strategy Lab** still show TradingView charts.
{% endhint %}
