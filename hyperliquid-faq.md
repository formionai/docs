# 🌊 Hyperliquid in Formion Wallet — Help & FAQ

Formion Wallet lets you trade **perps and spot on Hyperliquid** from your own wallet, move money there in one click from almost any asset you hold, and take profits back in the token and network you choose. This page answers what people usually ask.

<figure><video src=".gitbook/assets/clip-hyperliquid.mp4" title="Hyperliquid in Formion Wallet in 5 steps: add funds, review, arrives, trade, withdraw"></video><figcaption><p>Fund, trade and withdraw in 16 seconds: add funds → review → USDC arrives → trade → withdraw in the token you choose (demo values; example cost from 28 Oct 2026).</p></figcaption></figure>

{% hint style="info" %}
**Live numbers are in the wallet.** Fees, borrow rates and limits change. Open **wallet.formion.ai → Perps → Help & FAQ**: every number there is read live (Circle, Unit, Hyperliquid and Formion's own config). The examples below are from 28 October 2026.
{% endhint %}

## What is Hyperliquid?

Hyperliquid is a public blockchain with its own exchange for **perpetual futures (perps)** and **spot**. Your account there is simply your wallet address. Formion only gives you the screen and signs with your own key in your browser.

## Is it self-custody?

Yes. Your keys never leave your browser. Formion cannot move, freeze or withdraw your funds. Every transfer and order is shown to you and signed by you — or by **Auto-move**, only if you switch it on (see below).

## What does "Beta" mean?

It is live with real money, but still being built and tested. Formion sets **no amount limits**. Start with a small amount until you know the flow.

## Which tokens and networks can fund Hyperliquid?

Tap **Perps → Add funds** (or the small **→ Hyperliquid** button on any asset in your Overview):

| You hold | Network | How it gets to Hyperliquid |
| --- | --- | --- |
| USDC | Base | Circle CCTP straight to your Hyperliquid account |
| FOM, ETH, cbBTC | Base | swapped to USDC (a **sale**), then Circle CCTP |
| USDC, ETH | Arbitrum, Ethereum | bridged/swapped to USDC on Base, then Circle CCTP |
| USDC, SOL | Solana | (SOL swapped to USDC) → Circle CCTP to Base → Hyperliquid |
| ETH | Ethereum | **or** Unit: native ETH → UETH on Hyperliquid, sold for USDC |
| SOL | Solana | **or** Unit: native SOL → USOL on Hyperliquid, sold for USDC |
| BTC | Bitcoin | Unit: native BTC → **UBTC** on Hyperliquid (keep it, use it as collateral, or sell it) |

When two routes exist, the wallet compares them, shows **both costs**, and pre-selects the one that leaves **more USDC** on Hyperliquid. One review screen shows the total cost, the arrival time and the minimum you will receive; then every step runs by itself. If you close the page, **Continue** picks up from where your funds are.

**Typical costs (28 Oct 2026):** Circle fast transfer ≈ 0.013 % + ≈ 0.09 USDC forward fee per transfer (≈ 0.26 USDC for 20 USDC); swaps ≈ 0.3–1 % (FOM pool fee 1 %); Unit network fee ≈ 0.00002 BTC, ≈ 0.0005 ETH, ≈ 0.013 SOL per deposit. **Formion takes no fee on deposits or withdrawals.**

{% hint style="warning" %}
**Converting FOM, ETH, SOL or cbBTC to USDC is a sale.** After it you no longer hold that token — if its price goes up later, you will not have it.
{% endhint %}

## Can I receive straight into Hyperliquid, e.g. from an exchange?

Yes — **Perps → Deposit** is your *Hyperliquid deposit wallet*:

* **Direct Unit addresses for BTC, ETH and SOL.** Native coins sent there arrive on your Hyperliquid account (as UBTC / UETH / USOL). Each address is proven by Unit's guardian signatures for **your** Hyperliquid address before the wallet shows it. Minimums: 0.0003 BTC, 0.007 ETH, 0.12 SOL. Only send the native coin on its own network.
* **Your own USDC addresses on Base, Arbitrum and Solana** (with QR codes). Withdraw USDC from an exchange there, then move it with one click — or turn on Auto-move.

## What is Auto-move?

An opt-in switch per network (Base, Arbitrum, Solana), **off by default**. When USDC **arrives** on a network you turned on and your wallet is open and unlocked, the wallet moves exactly that amount to your Hyperliquid account, signed with your own key in your browser, within the **minimum** and **daily cap** you set. Your own swaps and withdrawals never trigger it. While the wallet is locked nothing is signed: you get a notification *"USDC arrived — tap to move it to Hyperliquid"* (needs incoming-payment alerts). Formion's servers never sign anything.

## Does my own USDC earn or cost interest?

No. Your own USDC on Hyperliquid earns no interest and costs nothing to hold.

## Why does borrowing have interest?

When you borrow USDC against BTC or HYPE you use someone else's USDC, so you pay them interest. It is charged **hourly, only on the borrowed amount and only while it is borrowed**. Example: at 5 % a year, borrowing 1,000 USDC for 30 days costs about 4.12 USDC.

## What is liquidation of a loan?

Your loan (debt) is backed by your collateral (BTC or HYPE). If the collateral's price falls until the debt is too large for it, Hyperliquid sells collateral to repay the loan. **Perps → Collateral** shows the exact BTC price where this happens. To move it further away: borrow less, add collateral, or repay.

## What is liquidation of a perp position?

A perp position uses leverage. If the price moves against you until your margin falls below the **maintenance margin** (half of the initial margin at maximum leverage), Hyperliquid closes the position. Lower leverage = liquidation price further away. The order ticket shows the liquidation price before you trade.

## What is the funding rate?

Perps have no expiry, so longs and shorts pay each other a small fee every hour to keep the perp price close to the spot price. Positive funding: longs pay shorts. Negative: shorts pay longs. Each market shows its live rate.

## Which collateral does Hyperliquid accept?

Today: **BTC as UBTC (max loan-to-value 50 %)** and **HYPE (65 %)**. ETH, SOL and FOM are **not** accepted as borrow collateral — to use them on Hyperliquid they must be sold for USDC first.

## What is Portfolio Margin?

An account mode for accounts of **at least 10,000 USDC** where Hyperliquid borrows USDC against your collateral automatically when a trade needs margin. Smaller accounts borrow by hand in the Collateral tab.

## Which fees apply when I trade?

The Hyperliquid trading fee (base tier 0.045 % taker / 0.015 % maker; the wallet shows your own live rate). Formion fee: none today (if a builder fee is ever set, it is shown before you approve it, and you approve it once). Transfers: Circle and Unit fees above, plus network gas.

## How do I withdraw, and in which token?

Tap **Withdraw** and choose the **token and network**: USDC on Base, Arbitrum or Solana; FOM, ETH or cbBTC on Base; or native BTC. The wallet pre-selects what you deposited with. One review, then every step runs by itself. Buying FOM, ETH, cbBTC or BTC with your USDC is a purchase at that day's price.

## What if Formion is down?

Your funds stay on Hyperliquid in your own account. Import the same recovery phrase into any wallet (for example MetaMask) and use **app.hyperliquid.xyz** — same address, same funds.

## Can I use it from any country?

Hyperliquid does not serve some countries (including the US, Canada and sanctioned regions). From those, the wallet allows only closing positions and withdrawing.

## Is this financial advice?

No. Perps and borrowing are risky and you can lose money. Nothing here is a recommendation.
