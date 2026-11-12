# 📖 Glossary

<figure><img src=".gitbook/assets/ill-glossary.jpg" alt=""><figcaption></figcaption></figure>

Plain-English definitions of terms used across Formion.

### Platform

* **FORA** — Formion's conversational AI assistant (Telegram + web) that can analyze, scan and place trades on your connected accounts. See **[FORA](fora.md)**.
* **AI Advisor** — the in-app AI hub: Quick Advisor (ranked ideas), AI Chat, Track Record and Trade Vision. See **[AI Advisor](smart-trading.md)**.
* **Multi-AI Consensus** — a multi-agent AI pipeline that analyses a symbol from several angles and returns a combined BUY / HOLD / SELL view.
* **BYOK** — *Bring Your Own Key*: connect your own AI provider key for AI usage billed by your provider.
* **Non-custodial** — Formion never holds your funds; it connects via API and can't withdraw. Formion Wallet is self-custody (only you hold the key). Exception: Dossier Autopilot trades from a separate auto-trade wallet whose key is held by the Formion signer; withdrawals go only to your verified wallet.
* **Paper trading** — simulated trading with no real money, used to validate a strategy.
* **FOM** — Formion's ERC-20 token on Base, fixed supply of 1,000,000,000 (minted once); held in a verified wallet or locked for FORA Agent levels (the higher levels include a licence), paid monthly for Dossier Autopilot (50% burned), spent on agent credits and add-ons. See [FOM](fom-token.md).

### Markets & venues

* **CEX** — centralized exchange (Binance, Bybit, …). **DEX** — decentralized exchange (Hyperliquid, Bluefin, …).
* **Spot** — buying/selling the asset itself. **Futures / Perp** — a leveraged contract that tracks the price; a *perpetual* has no expiry.
* **Leverage** — trading a position larger than your margin (e.g. 5×). Amplifies gains **and** losses.
* **Funding rate** — periodic payment between long and short perp holders; extreme funding is a signal (and a carry opportunity).
* **Prediction market** — markets on real-world outcomes (Polymarket, Kalshi, Limitless).

### Orders & risk

* **Reduce-only** — an order that can only shrink/close a position, never open or flip one (used for safe exits).
* **Stop-loss (SL) / Take-profit (TP)** — orders that close a position at a loss limit / profit target.
* **DCA** — *Dollar-Cost Averaging*: entering in steps rather than all at once.
* **Grid** — placing a ladder of buy/sell orders across a price range.
* **Drawdown** — the drop from a peak to a trough in your equity.

### Analysis

* **SMC** — *Smart Money Concepts*: FVG (fair-value gap), Order Block, Liquidity Pool, Breaker, Mitigation.
* **FormionTSI** — Formion's proprietary True-Strength-Index–based indicator with a nightly tuner.
* **GEX** — *Gamma Exposure*: dealer options positioning that can pin or accelerate price.
* **Footprint / DOM** — order-flow views (volume traded at each price / the live order-book ladder).
* **Liquidity Map** — Formion's recording of resting order-book liquidity across 11 markets (BTC, ETH, SOL, HYPE), shown over time and price; a Context signal, not a forecast. See **[Liquidity Map](liquidity-map.md)**.
* **Liquidity Tracker** — bid vs ask liquidity weighted by distance from each venue's best price (half-life H 25 or 100 bp). See **[Liquidity Map](liquidity-map.md)**.

### Strategy & performance

* **Backtest** — running a strategy over historical data to estimate performance.
* **Walk-forward** — validating a strategy on unseen data after optimizing on a prior window (guards against overfitting).
* **Prop-firm simulator** — will estimate the pass-rate of a strategy against funded-account (FTMO-style) rules. **Coming soon** (Pro and Institutional).
* **Win rate** — % of trades that are profitable. **Profit factor** — gross profit ÷ gross loss.
* **Expectancy** — average profit/loss per trade. **Equity curve** — your balance over time.

### Formion-specific

* **Pulse Score** — Formion Pulse's 0–100 narrative-sentiment reading, blending X & YouTube influencers, crowd chatter, Fear & Greed and BTC bias. 50 = balanced; higher = more bullish. See **[Formion Pulse](pulse.md)**.
* **Bias Map** — the Screener's market-wide confluence heatmap across 5 timeframes (5m→1d) with an anchor score; green = long bias, red = short.
* **Strategy Finder** — AutoML in the Strategy Lab: enter only a symbol and it searches strategy families + parameters for what historically had an edge.
* **Edge Map** — per-signal expectancy view in Analytics — does this signal actually pay?
* **CHART READ** — a Pulse label for a stance derived by a vision model *reading the chart inside a screenshot*, not the post's text.
* **Accuracy Leaderboard** — Pulse's scoreboard of influencers, each call checked against real price at +24h / +72h / +7d.

### Quantum Pulse

* **Badge** — a Pulse trader's measured status from every counted call once (his plan outcome where he gave a plan, else direction on his horizon, after costs): **Verified** or **Collecting data**. Never negative, never a promise.
* **His plan** (plan outcome) — the result of the trader's own plan after his entry traded: his take-profit or stop, whichever came first, or the exit he announced — after 0.12 % costs. The main number on a [trader profile](pulse-trader-profile.md).
* **Direction on his horizon** — whether price moved the trader's way after his own typical holding time (or his exit), counted from activation, before costs.
* **Beyond trend (control)** — the trader's move minus the asset's own drift over his horizon. A check of whether he added anything beyond the market, never his accuracy.
* **MFE** (maximum favourable excursion) — the best move in the call's direction while it was open or within the measured window.
* **MAE** (maximum adverse excursion) — the worst move against the call in the same window.
* **Held typical time** — a trade where the trader posted no exit, held for his typical holding time. Formion's **assumption**, labelled so, and switchable in the simulation.
* **Our pick** — the exit Formion would use on the trader's entry, chosen walk-forward from a fixed list of 120 exits using only his earlier entries. **Our strategy, not his result.**
* **Liquidation (sim)** — in the *If you follow him* simulation on Perp, a trade whose worst move against it reaches 1 / leverage − 0.5 % (9.5 % at 10×) on the real hourly candles before his exit; its whole margin is lost.
* **Funding (sim)** — the perpetual funding paid or received over each simulated trade's hold, from real exchange settlements (the coin's average rate where history is missing).
* **Collecting data** — too few calls or an unclear result to call something Verified (for example fewer than 30 calls, or a confidence range that still includes zero). It is not a negative verdict.

* **cTrader** — broker connection for forex and CFD accounts through OAuth.
* **Command Center** — the dashboard launcher for FORA text and voice.
* **Funding Carry** — research into paired perpetual funding across venues.
* **Permit** — ERC-20 approval by signature supported by FOM.
