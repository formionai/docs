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
8 CEX you can link (Binance, Bybit, KuCoin, MEXC, Bitget, Gate, Blofin, BingX; OKX, Coinbase and Kraken are marked coming soon), 4 DEX perps venues (Hyperliquid, Asterdex, Bluefin, Extended), forex and CFDs through cTrader broker accounts (e.g. FP Markets, IC Markets, Pepperstone), prediction-market accounts (Polymarket, Kalshi, Limitless), plus market data and analysis for stocks, commodities and crypto options. See **[Markets](markets.md)**.

## Account & plans

**How much does it cost?**
There's a free **Neural** tier, **Pro** at $89/mo and **Institutional** at $499/mo. Every new signup gets **7 days of Pro free** (no card required). Full breakdown: **[Pricing & Tiers](pricing.md)**.

**How can I pay? Crypto, PayPal, card?**
At the formion.ai checkout you can pay in crypto — **USDT or USDC** on Ethereum, Base, Arbitrum, Optimism, Polygon, BSC or Solana, or **BTC** / **SOL** — or with **PayPal** on the same checkout page. You can also pay with **Telegram Crypto Pay** via `/license` in [@formiontradingbot](https://t.me/formiontradingbot), which gets an extra 3% discount. Card payments are not available. Licences are priced in USD and paid one-time per period (no auto-renewal); see **[Pricing](pricing.md)**.

**Can I get a refund?**
A licence is refunded within 7 days of the payment if the paid features did not work because of a problem on our side or you were charged by mistake (renewals and upgrades: 72 hours); duplicate payments and overpayments are always refunded, trading results never. Request it at [formion.ai/refunds](https://formion.ai/refunds) or support@formion.ai. Crypto refunds go out in USDC or USDT to the wallet you give us (same network you paid on), minus the network fee; PayPal payments are refunded through PayPal.

**What is BYOK?**
Bring Your Own Key — connect your own AI provider key (Anthropic, OpenAI, Gemini, xAI, DeepSeek, Moonshot/Kimi, Zhipu/GLM, MiniMax or OpenRouter) or your ChatGPT subscription on any tier, so AI usage is billed by that provider with no platform budget cap. Keys are encrypted at rest.

## Trading & bots

**What bots can I run?**
In the app's **Bots** hub you can follow Formion's catalog bots and create paper bots from a catalog strategy; in [@formiontradingbot](https://t.me/formiontradingbot) you can set up DCA, Grid, Trailing, Alarm, indicator-signal and funding bots; and **TradingView webhook bots** turn your chart alerts into orders. Live bots need Pro (5) or Institutional (unlimited); the free tier runs unlimited **paper** bots. Native Formion copy-trading is **coming soon**; today you can use your exchange's native copy trading. See **[Bots & Automation](bots.md)**.

**Can I automate my chart alerts?**
Yes — in **Profile → Connections → TradingView Automation** create a bot, copy its webhook URL and Open/Close messages into your alert, and it executes on your connected CEX/DEX. New bots start paused and live execution is being rolled out account by account; a linked Telegram is required. See **[Webhook Automation](how-to-automate-trades-tradingview-alerts.md)**.

**Can I build and backtest my own strategy?**
Yes (Pro and Institutional) — the no-code **Builder** in Strategy Lab with backtests on historical data, the **AI Agent** that turns a plain-language idea into a backtested strategy, and **Edge Finder**, which scans a symbol and brute-forces entry/stop/R:R variants with a locked holdout. Published strategies are forward-tracked, and you can attach them to a demo or live account from the Marketplace.

**How do I track performance?**
Formion's tracked bots, signals and published strategies are consolidated in **[Trades History](trades-history.md)** with win rate, profit factor, expectancy and equity curves; your own trades go in the **[Journal](journal.md)**.

## AI

**What can the AI do?**
Rank trade ideas (AI Advisor), turn a chart screenshot or sentence into a plan (Trade Vision), write sourced research (Research RAG-LLM), and answer/act in chat (FORA). Important calls can be cross-checked across multiple models (Multi-AI Consensus). See **[AI Advisor](smart-trading.md)** and **[FORA](fora.md)**.

**Is the AI giving financial advice?**
No. AI output is analysis and education. You stay in control — nothing executes unless you set up a bot or confirm a trade.

## Security

**How are my keys protected?**
AES-256-GCM encryption at rest, TLS in transit, 2FA with backup codes, an optional trading password, session management and sign-in alerts. Use trade-only keys with withdrawals disabled. See **[Security](security.md)**.

## FOM token

**Is FOM live?**
FOM is Formion's ERC-20 token on **Base** (Ethereum L2) with a fixed supply of **1,000,000,000**, minted once. There is no presale, no ICO and no public sale. It launches on **Uniswap (Base) on Wed 14 Oct 2026**; the contract address is published at launch — only trust the address from official Formion channels. Agent access levels, credits, eligible add-ons and marketplace uses roll out in phases. USD licences are separate. See **[FOM token](fom-token.md)** for launch, allocation, vesting and audit details.

## Sentiment & influencers

**What is Formion Pulse?**
A market-narrative hub that reads X & YouTube influencers, social chatter, Fear & Greed and BTC bias into one **Pulse Score (0–100)**. You can mute any source and the score recomputes from only the voices you keep. See **[Formion Pulse](pulse.md)**.

## Strategies & earning

**Can I sell a strategy I build?**
Yes. Build and prove it in the **[Strategy Lab](strategy-lab.md)**, pass the publish gate, then list it on the **Marketplace** for free or — once your Partner (KYC) application is approved — as a paid listing. Subscribers pay Formion; you receive your share after a 25% platform fee and a 14-day hold, paid monthly in USDC/USDT. Review the listing’s forward record, subscription terms and checkout before subscribing or publishing.

**Do I need to code to build a strategy?**
No. Use the no-code **Builder**, describe it to the **AI Agent**, or let **Edge Finder** search for an edge from just a symbol. See **[Build & publish a strategy](usecase-build-strategy.md)**.

## Support

**How do I get help?**
Email **support@formion.ai**, open a ticket at [formion.ai/support](https://formion.ai/support) or message [@FormionSupportBot](https://t.me/FormionSupportBot), or join our Telegram community [t.me/formionai](https://t.me/formionai). Documentation lives at **docs.formion.ai**.

**Can I talk to FORA by voice?**
Yes. Live two-way voice with FORA is available by plan, and its daily limits depend on your plan. On every plan you can type to FORA, and in the chart chat you can turn on microphone dictation and read-aloud replies, which use your browser's speech features. [Command Center](command-center.md) offers suggested commands, attachments and chat on the dashboard.

**Where do I find news and trader ideas?**
Use [News](news.md) for economic and crypto events and headlines, and [Swarm](swarm.md) for trader posts, signals and contributor review. [Funding Carry](funding-carry.md) has a separate venue-spread research workflow.

**Is Academy available?**
In app.formion.ai the **Academy** and **Predictions** (AI price projections) tabs are marked **Soon**. A few introductory lessons are already published at [formion.ai/academy](https://formion.ai/academy). Prediction-market tools (Polymarket browser, whale tracking, account connections) are live separately; see [Prediction Markets](prediction-markets.md).
