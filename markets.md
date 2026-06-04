# 🌍 Markets

Formion is multi-asset by design — the same AI tools, screeners, bots and journal work across every market below.

## 🪙 Crypto

The core market. Connect your accounts and trade spot or perps with full data, signals and bots.

* **CEX:** Binance, Bybit, KuCoin, MEXC, OKX, Bitget, Coinbase, Bitfinex.
* **DEX (perps):** Hyperliquid, AsterDex, Bluefin, Extended.
* **Wallets:** EVM, Solana, Sui, TON — read-only or full (encrypted).
* Deep data: open interest, funding, long/short, liquidations, order-flow / footprint, on-chain events and whale tracking.

## 💱 Forex (MT5)

Institutional-grade forex via **MetaTrader 5** (FP Markets master).

* Major / minor / cross pairs.
* Telegram signal bridges + manual `/forex` commands route to MT5 orders.
* **Master-trade replication** (Formion's master → your MT5) is an **Institutional** feature; **Pro** can link MT5 for viewing and alerting.

## 📈 Stocks

Equities data and signals across regions (Yahoo + TradingView data):

* **US:** NASDAQ, NYSE, major indices (SPY, QQQ).
* **EMEA:** BIST (Turkey), EGX (Egypt).
* **Asia:** HKEX (Hong Kong), SSE / SZSE (China), Bursa Malaysia.

## 🥇 Commodities

* **Gold (XAU)** — dedicated scanner + Gold DCA bots + tokenized gold (XAUT / PAXG) cross-venue.
* **Silver (XAG)**, **Oil (WTI / Brent)**, **Copper (HG)** — via MT5.

## 📐 Options (Deribit)

BTC / ETH / SOL options:

* **Regime detector** classifies the market (low-vol grind, breakout, panic, post-event compression).
* **Strategy scorer** rates structures (long call/put, short put, straddle, strangle, iron condor…) for the current regime.
* Full **Greeks** and expiry-chain views, plus an **events heatmap** (3-day on Free → 21-day on Pro+).

## 🎲 Prediction Markets

**Polymarket, Kalshi and Limitless**:

* **AI consensus predictions** (multi-model, Brier-scored leaderboard).
* **Whale tracker** for large positions.
* Arbitrage bots — order-book mispricing scalper, exchange-latency arb, and Kalshi cross-arb. **Pro** sees signals; **Institutional** can auto-execute.
* Every bot runs **paper-first** before live capital.

***

{% hint style="info" %}
Market and feature access depends on your plan — see **[Pricing & Tiers](pricing.md)**. Connect your accounts from **formion.ai → Profile → Connections** ([guide](how-to-start-api-connection.md)).
{% endhint %}
