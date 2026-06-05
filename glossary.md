# 📖 Glossary

<figure><img src=".gitbook/assets/glossary.jpg" alt=""><figcaption></figcaption></figure>

Plain-English definitions of terms used across Formion.

### Platform

* **FORA** — Formion's conversational AI assistant (Telegram + web) that can analyze, scan and place trades on your connected accounts. See **[FORA](fora.md)**.
* **AI Advisor** — the in-app AI hub: Quick Advisor (ranked ideas), AI Chat, Track Record and Trade Vision. See **[AI Advisor](smart-trading.md)**.
* **Multi-AI Consensus** — cross-checking a question across several AI models (Claude, GPT, Gemini, Kimi) and surfacing agreement/disagreement.
* **BYOK** — *Bring Your Own Key*: connect your own AI provider key for unlimited AI usage.
* **Non-custodial** — Formion never holds your funds; it connects via API and can't withdraw.
* **Paper trading** — simulated trading with no real money, used to validate a strategy.
* **FOM** — the Formion ecosystem's native utility token (🚧 coming soon).

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

### Strategy & performance

* **Backtest** — running a strategy over historical data to estimate performance.
* **Walk-forward** — validating a strategy on unseen data after optimizing on a prior window (guards against overfitting).
* **Prop-firm simulator** — estimates the pass-rate of a strategy against funded-account (FTMO-style) rules.
* **Win rate** — % of trades that are profitable. **Profit factor** — gross profit ÷ gross loss.
* **Expectancy** — average profit/loss per trade. **Equity curve** — your balance over time.
