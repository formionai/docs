# 🔌 Brokers & Connections

<figure><img src=".gitbook/assets/app-hero.jpg" alt="Formion workspace"><figcaption></figcaption></figure>

Formion works with **your** accounts — you never move funds to us. Connect at **formion.ai → Profile → Connections** or on your formion.ai dashboard (and for exchange API keys, see **[How to Start — API Connection](how-to-start-api-connection.md)**).

## What you can connect

```mermaid
flowchart TD
  U(("Your accounts")) --> CEX["🏦 CEX<br/>Binance · Bybit · KuCoin · MEXC · Bitget · Gate.io · Blofin · BingX"]
  U --> DEX["⚡ DEX perps<br/>Hyperliquid · AsterDex · Bluefin · Extended"]
  U --> CT["💱 cTrader<br/>FP Markets · IC Markets · Pepperstone — forex/CFD"]
  U --> W["👛 Wallets<br/>EVM · Solana · Sui · TON"]
  U --> PM["🎲 Prediction markets<br/>Polymarket · Kalshi · Limitless"]
```

* **CEX (API key):** spot + perps. OKX, Coinbase and Kraken are listed as coming soon. Binance and Bybit can also be linked as **demo** (testnet) accounts. Create a key with the permissions you want (read-only for tracking, trade for bots — **never enable withdrawals**) and paste it in. Step-by-step with screenshots on the **[API Connection](how-to-start-api-connection.md)** page.
* **cTrader (OAuth):** link a cTrader account at FP Markets, IC Markets, Pepperstone or another cTrader broker (demo + live) for forex, indices, metals and CFDs. OAuth means no API key or password to share — you authorise Formion from the broker. Neural allows 1 broker account, Pro 5, Institutional unlimited.
* **DEX perps:** Hyperliquid and other on-chain venues for perps; on-chain **swaps** route best-price across EVM, Solana and Sui.
* **Wallets:** view-only or trade-ready (encrypted) across EVM, Solana, Sui and TON.
* **Prediction markets:** link Polymarket, Kalshi or Limitless to place bets and see positions — see **[Prediction Markets](prediction-markets.md)**.

## Read-only vs full

| Mode | What it does | Use for |
|---|---|---|
| **Read-only** | imports balances, positions & trade history | the **[Journal](journal.md)**, analytics, tracking |
| **Full (trade)** | can place/manage orders you or a bot trigger | manual **[Trade](the-app.md)** dock, **[bots](bots.md)**, marketplace strategies |

{% hint style="warning" %}
Security first: scope API keys to the minimum needed, **disable withdrawals**, and prefer IP-whitelisting where the exchange supports it. Credentials are stored encrypted. See **[Security](security.md)**.
{% endhint %}

Once connected, your account flows into the **[Trading Journal](journal.md)** automatically and becomes a target for **[bots](bots.md)** and **[Strategy Lab](strategy-lab.md)** strategies.
