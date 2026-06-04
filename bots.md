# 🦾 Bots & Automation

Formion runs a large catalog of automated strategies. Some are **live** on real or demo accounts, some run **paper-first** for validation. Every strategy's trades flow into the unified **Trade History** hub so you can compare them side by side (KPIs, equity curve, win-rate, per-strategy analytics).

{% hint style="info" %}
**Live execution** requires a **Pro** plan (5 live bots) or **Institutional** (unlimited). The free tier runs unlimited **paper** bots. You can build your own bot from a strategy, and automate TradingView alerts — see **[TradingView Automation](how-to-automate-trades-tradingview-alerts.md)**.
{% endhint %}

## Bot building blocks

| Bot | What it does |
|---|---|
| **DCA** | Dollar-cost-averages into a position on a schedule / multi-level entry ladder. |
| **Grid** | Places a grid of orders within a price range (optional martingale). |
| **Indicator** | Triggers from a TradingView alert or built-in indicator (long / close-long / short / close-short). |
| **Trailing** | Trailing stop with multi-step ratchet. |
| **Funding-arb** | Scans cross-CEX funding and captures delta-neutral carry (long spot + short perp). |
| **Alarm** | Conditional alerts (price / RSI / MA cross) → push, no execution. |
| **TradingView webhook** | Your TradingView alert → a real order on your connected CEX/DEX. |

## Strategy catalog

The platform tracks 35+ curated strategies. Highlights by category:

### Crypto perps & screener

| Strategy | Summary |
|---|---|
| **Screener** | Pattern scanner (bear-rally, downtrend, sweep, accumulation). |
| **Mechanical** | 9-signal bias fusion (RSI, 24h Δ, VWAP, funding, OI Δ, top L/S, TPO, footprint Δ, GEX). |
| **Bias Map Confluence** | Fires when ≥4 of 5 timeframes + anchor score align. |
| **Funding Fade** | Fades overheated funding spikes (mean-reversion). |
| **Divergence** | RSI/MACD/OBV regular + hidden divergences on top perps. |
| **OI Surge** | Open-interest spike + price continuation. |
| **GMGN Smart Money** | Smart-money cluster signals (paper → live after validation). |
| **HL TP/SL** | Hyperliquid whale TP/SL engine (imbalance bias, stop-hunt, TP-magnet, whale-conviction). |
| **Confluence** | BTC 1m strong-spike fader (transfer + liquidation + volume-delta). |

### Gold & commodities

| Strategy | Summary |
|---|---|
| **Gold FRVP** | XAU/XAG 5m mean-reversion (fixed-range volume profile), POC + VAL/VAH dual take-profit. |
| **Gold DCA v1.0** | XAUUSD 5m DCA with multi-component RSI scoring + HTF trend / VWAP gating. |
| **Gold DCA v2.z** | Adaptive Z-RSI zones + trend-gated martingale DCA (buy-only). |

### Options & prediction markets

| Strategy | Summary |
|---|---|
| **Options · Deribit** | 10 options structures (iron condor, strangle, calendar, spreads…) scored from DVOL + IV-RV + term structure. |
| **Polymarket Edge** | Black-Scholes fair-value vs market YES price; trades the mispricing (paper + live). |
| **PolyScalp / Latency / Kalshi cross-arb** | Order-book mispricing, exchange-latency and cross-venue event arbitrage. |

### Forex & stocks (signal bridges)

| Strategy | Summary |
|---|---|
| **Lorin** | MT5 master forex crossovers on FP Markets via signal bridge. |
| **Neurix Crypto / Stocks** | Elite RSI 70/30 + 4h-trend + ADX setups on crypto perps and US equities. |
| **Liqra v1 / v2** | Liquidation-cluster signal executors. |
| **DCA MUSDT / GRID-DCA MUSDT** | Position-scaling DCA and grid-DCA strategies. |
| **VIP / Jasmine / NextPips** | Pattern-breakout and curated setups forwarded to broker executors. |
| **News (WTI)** | Trades WTI around scheduled events (EIA, API, CPI) on actual-vs-forecast bias. |

## Tracking performance

Open **Trade History** in the app (Backtest → All Trades) and filter by bot to see its KPIs, equity curve, win-rate, hold-time buckets, and per-symbol / per-session breakdowns. Every new bot automatically inherits the full analytics dashboard.
