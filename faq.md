---
description: Frequently Asked Questions (FAQ)
---

# 📄 FAQ

<figure><img src=".gitbook/assets/faq.jpg" alt=""><figcaption></figcaption></figure>

## General

**What is Formion AI?**
A multi-asset, AI-powered trading platform — crypto, forex, stocks, commodities, options and prediction markets in one place. It combines AI analysis, automated bots, deep market data, backtesting, copy trading and a trading journal, accessible from the web app ([app.formion.ai](https://app.formion.ai)) and from Telegram (FORA). See **[The App](the-app.md)**.

**Does Formion hold my money?**
No. Formion is **non-custodial** — it connects to your exchange via API keys (trade-only, no withdrawal) and your funds stay on your own exchange. See **[Security](security.md)**.

**Which exchanges and markets are supported?**
8 CEX (Binance, Bybit, KuCoin, MEXC, OKX, Bitget, Coinbase, Bitfinex), 4 DEX (Hyperliquid, AsterDex, Bluefin, Extended), forex and CFDs through cTrader broker accounts, stocks (US + international), commodities, Crypto options and prediction markets (Polymarket, Kalshi, Limitless). See **[Markets](markets.md)**.

## Account & plans

**How much does it cost?**
There's a free **Neural** tier, **Pro** at $89/mo and **Institutional** at $499/mo. Every new signup gets **7 days of Pro free** (no card required). Full breakdown: **[Pricing & Tiers](pricing.md)**.

**Can I pay with crypto?**
Yes — payments are **crypto only**. On formion.ai checkout you can pay **USDT or USDC** on Ethereum, Base, Arbitrum, Optimism, Polygon, BSC or Solana, or **BTC** / **SOL**. You can also pay with **Telegram Crypto Pay** via `/license` in [@formiontradingbot](https://t.me/formiontradingbot), which gets an extra 3% discount. Card payments are not offered. Licences are priced in USD; see **[Pricing](pricing.md)** and **[FOM token](fom-token.md)**.

**What is BYOK?**
Bring Your Own Key — connect your own AI provider key (Anthropic / OpenAI / OpenRouter / Gemini) on any tier for AI usage billed by that provider and subject to its limits. Keys are encrypted at rest.

## Trading & bots

**What bots can I run?**
DCA, Grid, Indicator, Trailing, Funding-arb and Alarm bots, plus **chart-alert webhook automation**. Live bots need Pro (5) or Institutional (unlimited); the free tier runs unlimited **paper** bots. For copy trading you can use your exchange's native copy trading today (e.g. Bybit); native Formion bot copy-trading is **coming soon**. See **[Bots & Automation](bots.md)**.

**Can I automate my chart alerts?**
Yes — create a chart-alert bot, copy its webhook URL + tokens into your alert, and it executes on your connected CEX/DEX. See **[Webhook Automation](how-to-automate-trades-tradingview-alerts.md)**.

**Can I build and backtest my own strategy?**
Yes — a no-code Strategy Builder with 5-year backtests, walk-forward validation and a prop-firm simulator. Strategies can be paper-traded then deployed as bots.

**How do I track performance?**
Every bot/strategy flows into a unified **Trade History** with win-rate, profit factor, expectancy and equity curves, plus the per-trade **[Journal](journal.md)**.

## AI

**What can the AI do?**
Rank trade ideas (AI Advisor), turn a chart screenshot or sentence into a plan (Trade Vision), write sourced research (Research RAG-LLM), and answer/act in chat (FORA). Important calls can be cross-checked across multiple models (Multi-AI Consensus). See **[AI Advisor](smart-trading.md)** and **[FORA](fora.md)**.

**Is the AI giving financial advice?**
No. AI output is analysis and education. You stay in control — nothing executes unless you set up a bot or confirm a trade.

## Security

**How are my keys protected?**
AES-256-GCM encryption at rest, TLS in transit, 2FA, IP-whitelisting and session management. Use trade-only keys with withdrawals disabled. See **[Security](security.md)**.

## FOM token

**Is FOM live?**
FOM is Formion's ERC-20 token on **Base** (Ethereum L2) with a fixed supply of **1,000,000,000**, minted once. There is no presale, no ICO and no public sale. It launches on **Uniswap (Base) on Wed 14 Oct 2026**; the contract address is published at launch — only trust the address from official Formion channels. Agent access levels, credits, eligible add-ons and marketplace uses roll out in phases. USD licences are separate. See **[FOM token](fom-token.md)** for launch, allocation, vesting and audit details.

## Sentiment & influencers

**What is Formion Pulse?**
A market-narrative hub that reads X & YouTube influencers, social chatter and BTC bias into one **Pulse Score (0–100)** — and scores each voice against real price moves on an **accuracy leaderboard**, so you can see who actually calls it right. You can add your own accounts and filter the score to only the voices you trust. See **[Formion Pulse](pulse.md)**.

**Can I track my own X / YouTube accounts?**
Yes — add them in Pulse → **My Watchlist** (an `@handle`, a link, or a channel ID). They get the same AI scoring on a personal desk, and you can mute any source to reshape your Pulse Score.

## Strategies & earning

**Can I sell a strategy I build?**
Yes. Build and prove it in the **[Strategy Lab](strategy-lab.md)**, then publish to the **Marketplace** — others subscribe (paid or free) and you earn from subscriptions. Review the listing’s available forward record, author options, subscription terms and checkout before subscribing or publishing.

**Do I need to code to build a strategy?**
No. Use the no-code **Builder**, describe it to the **AI Strategist**, or let **Edge Finder** (AutoML) find an edge from just a symbol. See **[Build & publish a strategy](usecase-build-strategy.md)**.

## Support

**How do I get help?**
Email **support@formion.ai** or join our Telegram community. Documentation lives at **docs.formion.ai**.

**Can I talk to FORA by voice?**
Yes. FORA supports text and realtime voice conversation. [Command Center](command-center.md) offers suggested commands, attachments and chat on the dashboard.

**Where do I find news and trader ideas?**
Use [News](news.md) for economic and crypto events and headlines, and [Swarm](swarm.md) for trader posts, signals and contributor review. [Funding Carry](funding-carry.md) has a separate venue-spread research workflow.

**Is Academy available?**
Academy and the Predictions entry are marked coming soon in the public app. Other prediction-market research surfaces have their own availability; see [Prediction Markets](prediction-markets.md).
