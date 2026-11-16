# 🗓️ Changelog

What is new in Formion and in these docs, newest first. Every entry has a short title, the changes in short lines, and a link to the page with the details.

## 17 November 2026

### Options — SOL, HYPE and Gold for everyone

* SOL, HYPE and Gold (XAUT) options are now on every plan, next to BTC and ETH.
* Strategy Builder: live chains from Deribit (SOL, HYPE) and Bybit (SOL, HYPE, XAUT), with a Liquidity column per leg.
* Data Hub → Options: index, ATM IV (own), term structure, 25Δ risk reversal, put / call OI, thin options near the money.
* **Thin market** warning when a leg has no bid / ask, a spread over 10 % or zero open interest.
* No setup, alert or trade idea for these assets — the weekly 16Δ rules run on paper only (**Collecting data**).
* Details: [Options & GEX → SOL, HYPE and Gold options](options.md)

## 16 November 2026

### Performance panels — Filters explained

* New docs section **Filters** for the bar above every Performance panel.
* Market, Side, Outcome, Setup, TF, Symbol and Period, each chip with its trade count.
* A filtered view can be shared as a link and never reads Verified on its own.
* Zone Hunter on Free and the FOM steps below Pro: crypto only.
* Details: [Quantum Screener → Filters](screener.md) · [Data Hub](data-hub.md)

### Zone Hunter — segment map and our SL variant

* **Where it works: setup × market** under Buy the dip: paper-book results next to the backtest for every setup and market, plus **Best right now**.
* Nothing is hidden — a weak segment is a filter.
* **Our SL variant (paper): behind liquidity** — a paper twin of every new dip-S1 idea with the stop behind the nearest swing low.
* Status **Collecting data** until 30 closed pairs and 14 days; the live stop does not change.
* Details: [Quantum Screener → Zone Hunter](screener.md)

## 15 November 2026

### Plan ladder — every step now gives more

* Whale Tracker: Institutional follows **100 tokens** (was 50, the same as Pro + FOM Lock).
* Wallet Insights MFE / MAE:
  * Free + FOM Hold: 1 buy from the last 7 days.
  * Free + FOM Lock: all tokens, last 30 days.
  * Pro: last 30 days + CSV export.
  * Pro + FOM Lock P3 and Institutional: full history.
* Market Intelligence AI review: Free + FOM Hold 1 a week, Free + FOM Lock 1 a day (Pro and up unchanged).
* Details: [Pricing](pricing.md) · [FOM token](fom-token.md)

### Options — Compare with a perp is now in Pro

* New mode in the Strategy Builder: **Compare with a perp**.
* Your own idea, stop and $ risk — side by side as a Bybit perp and as a long option on the live chain.
* Shows max loss, breakeven, funding, liquidation and three paths "on the way".
* Status **Keep refining** — a calculator, not advice.
* Pro and Institutional; Free sees what it does with a lock.
* Details: [Options & GEX](options.md)

### Options — clearer wording in setups and the regime Neuron

* When DVOL leaves the High state, the Options regime Neuron and FORA now say **Context signal** — no measured advantage now.
* Details: [Options & GEX](options.md) · [FORA Neurons](fora-neurons.md)

### Funding — two measured context rules

* After an extreme negative settlement (−0.5 % or lower per interval) the drop tends to continue for 1–4 h.
* So: don't buy that dip right away. Not a short signal. **Context signal**.
* Measured 21 Aug – 12 Nov 2026, 4,337 settlements.
* BTC/ETH cash-and-carry earned roughly nothing after costs when market funding sat at the base rate (≈ 11 % a year), Oct 2024 – Oct 2026.
* It paid only in high-funding periods (2020–2024). **Collecting data**.
* Details: [Data Hub](data-hub.md) · [Funding Carry](funding-carry.md)

### FORA Neurons — funding note on long ideas

* A long idea on a coin that settled funding at −0.5 % or lower in the last 4 h gets a short note.
* The note says the drop right after such a settlement tends to continue for 1–4 h.
* The idea itself is not changed. **Context signal**.
* Details: [FORA Neurons](fora-neurons.md)

### Developer API — screener endpoint now serves the Formion Screener

* `GET /api/v1/screener` returns the Formion Screener: direction, trend strength 0–100, phase, trend start, typical duration, best and worst move since the start.
* New filters: `side`, `market`, `phase`, `minStrength` (old `minScore` still works).
* Removed fields: `score`, `win_probability`, `category`, `rsi_1d`, `tags`.
* Each response names its contract in `schema` (`formion-screener-2026-11`).
* Details: [Developer API](developer-api.md)

### Open tools: Free keeps everything, steps add extras

* Chart Pro, Data Hub, Order Flow, Journal and Coins Hub stay fully open on Free.
* New extras by plan step:
  * **Chart Pro** — active alerts 3 · 10 · 25 · 100 · 150–500 · unlimited; saved custom indicators 1 · 3 · 5 · unlimited; watermark can be switched off from Free + FOM Lock.
  * **Data Hub** — **Export CSV** of the current view and saved **Presets** (from Free + FOM Hold: 3 exports a day and 2 presets).
  * **Order Flow** — Walls book history 7 · 14 · 30 days, Pro the whole book.
  * **Journal** — **Report** button: PDF performance report on demand (from Free + FOM Hold: 1 a day); Trading Audit 1 a month on Hold, 1 a week on Lock.
  * **Coins Hub** — watchlists 20 × 60 for everyone, up to 100 × 1000 on Institutional.
* Every locked extra shows the shared lock with the **Next step**.
* Details: [Pricing & Tiers](pricing.md#the-plan-ladder--six-steps) · [FOM token](fom-token.md) · [Journal](journal.md)

## 14 November 2026

### Performance — Backtest and Forward test

* Every tool with a measured book has one **Performance** section with two sub-tabs.
* **Backtest** = history; **Forward test** = only new days after the rules were frozen — the real test.
* Inside: KPI tiles, equity curve (R, % or $), outcomes, R per trade, heatmap, by coin / side / segment, MFE vs MAE and the journal.
* **Verified** only from 30 closed forward-test trades; a tool without a measured book shows **Collecting data**.
* Details: [Quantum Screener](screener.md)

### Trade chart — status strip and Live

* A chart opened from a trade shows its status: Waiting, Active (live R), Won, Lost, Breakeven, Expired, Not filled or Closed.
* The yellow entry circle sits only on the real fill candle.
* **Chart settings** has the sections **Trade**, **Chart** and **Visuals**.
* **Follow live**: every trade chart moves — forming candle, **Last** line, view follows the newest candle.
* A closed trade's result stays frozen; **Live feed unavailable** when the feed does not answer.
* Details: [Chart Pro](chart-pro.md)

### Zone Hunter — Missed trades

* New card **Missed trades (not filled)** under Buy the dip.
* Shows why an order did not fill (for example **Ran away**) and how close price came to the limit.
* **Would have been** is a control, not the book's result; the rules are unchanged.
* Control totals on Pro and up.
* Details: [Quantum Screener](screener.md)

### Volatility scanner — new measurement

* The calculation for short signals was fixed; the scanner now gives long and short signals.
* Forward test restarted from zero on 13 Nov 2026 (**Collecting data**).
* The old book is kept as an archive marked **before the fix**.
* Details: [Data Hub](data-hub.md)

### Data Hub — chart settings

* Open Interest, Long/Short, Top Trader, Taker and Funding charts have **Chart settings → Series**.
* Draw as lines or bars, grid, legend, smooth lines and a colour per exchange.
* **All Lines** / **All Bars** switch every chart at once.
* Details: [Data Hub](data-hub.md)

## 14 November 2026

### Plan ladder — fixes

* **OI Surge** and the **Volatility** movers now follow the same delay as the other signal scanners:
  * Free 30 min · Free + FOM Hold 15 min · Free + FOM Lock 5 min · Pro real-time
* **Listings backtest:** the venue you open first is your venue for the whole UTC day (two on Free + FOM Lock).
* **Dossier → Our calls → My entries:** logging your entries works from Free + FOM Hold; the tracked price follows your delay.
* **Liquidity Map:** the Pro panels show the shared lock with the next step.
* **Wallet:** Whale Tracker, Insights MFE / MAE, the watchlist and FORA limits show the **Next step** line with the plan or FOM amount.
* **Wallet Insights:** MFE / MAE from Pro + FOM Lock (P3), and more FORA reviews a day with FOM Boost.
* Details: [Pricing & Tiers](pricing.md)

## 13 November 2026

### New menu order

* The top menu now follows four groups:
  * **Find** — Quantum Screener, Chart Pro, Signals, Pulse, Coins Hub
  * **Read** — Data Hub, Analytics, News, AI Advisor
  * **Act** — Trade, Bots, Neurons, and Dossier (Pro and Institutional)
  * **Review** — Strategies, Journal, Swarm, Predictions, Academy
* Desktop shows two rows; the phone menu shows the group names.
* **Backtest** is now called **Strategies**.
* Details: [Trading Terminal — The App](the-app.md)

### Quantum Screener

* The home page is now the **Quantum Screener**, with four sections:
  * **Trends**
  * **Context** — breadth, volatility, BTC regime, unusual volume
  * **Confluence** — 382 combinations tested on history: 0 Verified, five paper candidates *Collecting data*
  * **Track record** — with **Does a higher score do better?**
* New Details visuals: **Move since start** and **Score shape**.
* New sections: what MFE / MAE mean, and **What the screener is and isn't**.
* Details: [Quantum Screener](screener.md)

### Live Feed

* A **LIVE** dot shows the feed state: Live, Delayed or Offline.
* **Settings → Live Feed exchange**: Binance, Bybit, OKX, Bitget or Hyperliquid.
* Details: [Quantum Screener](screener.md) · [Trading Terminal — The App](the-app.md)

### Order Book and Watchlist moved

* Imbalance and Walls are now in **Data Hub → Order Book** (Book · DOM · Imbalance · Walls).
* The **Watchlist** is in your account menu, next to Journal.
* Details: [Order Flow & Microstructure](order-flow.md) · [Trading Terminal — The App](the-app.md)

### Zone Hunter

* The Adaptive brain shows the frozen **weekly decision** (with its date) next to **Market now** — the same rule on the last closed daily bar.
* The crypto regime is read three ways: **BTC**, **Altcoins** and **Crypto (all)**.
* Why **Sell the top** is often empty.
* The **Trend Shift** rule.
* The Long / Short pill, and the paper book below Pro.
* Details: [Screener](screener.md)

### Quantum Screener → Details

* A real candle chart with three moments:
  * **Move began** — seen in hindsight
  * **Trend start**
  * **Detected** — when our screener first recorded the trend live
* The Trend age ring.
* Forex, metals, oil and indices are labelled **FP Markets (cTrader)**.
* Details: [Screener](screener.md)

### Bias Map

* "Neutral" vs "no current read".
* The 5m / 15m fast lane.
* Coverage on Strength, Sector and Sunburst; session markets are scored on Monday.
* Accuracy restarted on 2 Nov 2026 and reads *Collecting data*.
* Details: [Screener](screener.md)

### Quantum Pulse is public

* Public since 12 Nov 2026, with six plan steps.
* **Request removal / correction** on every trader profile.
* Details: [Formion Pulse](pulse.md) · [Pulse Trader Profile](pulse-trader-profile.md)

### Mechanical board, Expectancy Map and Pairs

* How to read every column.
* The paper bots: 0.12 % cost per trade, funding not included.
* What each plan sees.
* Details: [Analytics](analytics.md)

### Liquidity Map

* Strongest levels with labels: Left, Right or On hover.
* All / Spot / Perp, pulled count per wall, flow by order size.
* **Level accuracy**.
* Partly recorded minutes are hatched, with a gap banner.
* FORA wall alerts and drawings.
* Details: [Liquidity Map](liquidity-map.md)

### Liquidation Map

* Every perpetual contract of Binance, Bybit and OKX in USD, plus Hyperliquid real positions.
* A per-contract picker.
* **Map accuracy** per contract — first verdict on 23 Nov 2026, *Collecting data* until then.
* Details: [Order Flow & Microstructure](order-flow.md)

### FORA Neurons

* New **Liquidity walls** neuron: approach, pulled, touch, reject, break.
* Details: [FORA Neurons](fora-neurons.md)

### Bots

* **Polymarket Edge · Live** replaces the retired Whale Copy beta.
* Details: [Bots & Automation](bots.md)

### Signalix archived

* The Signalix tracker was retired on 12 Nov 2026 and no longer produces signals.
* Details: [Trading Terminal — The App](the-app.md)

## 12 November 2026

### Zone Hunter is public

* Open by plan step, Free to Institutional, with the shared lock on hidden rows.
* Details: [Screener](screener.md) · [Pricing & Tiers](pricing.md)

### Plan ladder

* Six steps per service: Free, Free + FOM Hold, Free + FOM Lock, Pro, Pro + FOM Lock, Institutional.
* Details: [Pricing & Tiers](pricing.md) · [FOM Hold vs Lock](fom-hold-vs-lock.md)

### Options

* Signal Performance with status words, and option P&L on Deribit marks.
* Details: [Options & GEX](options.md)

### One Formion chart

* One chart behind Patterns, Signal Desk, Zone Hunter and Multi-Chart.
* Details: [Screener](screener.md) · [Chart Pro](chart-pro.md)
