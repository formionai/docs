# 🧬 FORA Neurons

**FORA Neurons** are your always-on FORA watchers at **app.formion.ai → Neurons**. They keep looking while you are away and tell you in the app and on Telegram (the chat you linked under Alerts).

{% hint style="info" %}
A Neuron never trades by itself — a proposal opens only when you tap it, on a DEMO account (Bybit for crypto, cTrader for gold and FX). Planner and KOL watch plans are never executed for you: you buy in your own wallet and confirm every swap.
{% endhint %}

Active Neurons per plan: **Neural (Free) 2 · Pro 25 · Institutional unlimited** (a FOM boost adds more — see **[FOM token](fom-token.md)**). Pricing details: **[Pricing & Tiers](pricing.md)**.

## Neuron types

| Neuron | What it watches |
|---|---|
| **Price level** | Tells you when price crosses a level. |
| **Fast move** | A % move within N minutes. |
| **Extreme funding** | Perp funding beyond a threshold. |
| **Open interest** | OI changes by % over a window. |
| **Volatility spike** | Range jumps vs its usual size. |
| **News watch** | Headlines with your words or coins. |
| **Social watch** | New posts from X, Telegram and YouTube accounts you pick. |
| **Several conditions** | Price, move, funding, open interest and news together (all or any). |
| **Macro playbook** | Before and after CPI, PPI, FOMC, NFP: how gold and BTC reacted since 2020, and the plan. |
| **Trader coach** (Pro+) | Reads your own trades, finds where you lose, tests strategies on 6 months. |
| **Price action** | Market structure on closed bars: CHoCH / BOS, swings, previous-day sweeps, order blocks, FVG, daily EMA 200, divergences, candle patterns. |
| **Daily brief** | Prices and mood at your time. |
| **Research watch** (Pro+) | Deep research on a topic; tells you only when it changes. |
| **Position guard** | Stop, liquidation and funding watch on your open positions. |
| **My strategy signal** | Your saved strategy runs live on its own data and tells you on a new signal. Never trades. |
| **Liquidity alerts** | Strong liquidation zones near price, order-book holes and third-party setups — each with our own measured record. |
| **Liquidation level** | Price near a strong level of our liquidation model, then a confirmed break or a rejection, with the context. Context, not a signal. |
| **KOL watch** (Pro+) | Follows the KOLs you choose (or the best measured ones) and proposes, watches or skips each new call — see below. |
| **Spot scout** (Pro+) | Daily or weekly: which spot coins to buy, short and long term, each source weighted by its measured record. |

***

## My plan — the FORA planner

At the top of the Neurons page, **My plan — FORA planner** answers four questions for the token calls Formion researches: **when** to act, **what** to pick, **how much** to put in and **how** to exit — from your own settings and our measured data. The same planner answers in FORA chat ("what should I buy today?", "how much X?", "make me a plan for $500", "when do I sell?"), on the KOL watch card and in the Dossier Telegram message.

<figure><img src=".gitbook/assets/shot-fora-planner-panel.jpg" alt="My plan — FORA planner panel: What FORA knows about you (bankroll, risk level, caps, chains) and Today for you with three ranked plans"><figcaption><p>Neurons → My plan: your settings on top, today's plans ranked for you below (Docs Demo account, live data).</p></figcaption></figure>

<figure><video src=".gitbook/assets/clip-fora-planner.mp4" title="FORA planner: your settings, today's plans, how much, I bought — follow this plan, do this now messages and the Monday summary (DEMO values)."></video><figcaption><p>From your settings to "do this now": the whole planner flow in 17 seconds (sample token, DEMO values).</p></figcaption></figure>

### 1. What FORA knows about you

You set it once in **What FORA knows about you** (or tell FORA in chat). When something is missing, FORA asks **once**; after that it uses the defaults and tells you which ones it used.

* **Bankroll for these tokens** — the money you want planned, in USD.
* **Risk level** — Low, Medium or High (Medium is used until you pick).
* **Max per token**, **Max open positions**, **Daily loss brake** and **Stop under entry** — your own caps.
* **Chains** — Solana, Base, BNB Chain, Ethereum, Arbitrum.

Each risk level starts from OUR preset (you can override every number):

| | Low | Medium | High |
|---|---|---|---|
| **Size per plan** | 3 % of bankroll | 6 % | 10 % |
| **Max per token** | 5 % | 10 % | 20 % |
| **Max open positions** | 3 | 5 | 8 |
| **Max total exposure** | 25 % | 40 % | 60 % |
| **Daily loss brake** | 5 % | 10 % | 20 % |
| **Minimum Dossier score** | 70 | 60 | 55 |

FORA also reads what you already hold through Formion — plans you follow, Dossier entries you logged and the Dossier Autopilot book — to see your exposure, today's P&L and how your past plans did (the strip **Open now · Exposure · Today · Plans you followed**).

### 2. Today for you — what and when

Candidates are the Dossier's quality first calls (up to 48 hours old) and KOL calls that passed the **KOL watch** chain (up to 24 hours old). FORA ranks them for **you** and fills your portfolio in order, so a small account gets fewer plans, not all of them. Each plan gets one decision:

| Decision | Meaning |
|---|---|
| 🟢 **ENTER NOW (our plan)** | Fits your profile now — follow OUR plan or pass; you decide. |
| 🟡 **WAIT** | Worth watching, not buying yet (for example it already ran far above the Dossier decision price). |
| ⛔ **NOT TODAY** | It would break one of your limits: max open positions, same chain and class, or the daily loss brake. |
| 🔴 **SKIP** | Outside your risk level or score minimum, or the stake-back or stop level was already passed. |

Every reason comes from data: how far the token moved from the Dossier price, the verdict and risk, the age of the decision, the BTC regime (on Low risk), and your portfolio.

### 3. How much

The size is the **smallest** of: your max per token, the % for your risk level, the pool's liquidity (the buy may move the price at most 0.5 %, from the measured quote ladder, times a risk factor), your Dossier max per trade and your remaining exposure room — times the Dossier factor for the token's stage (for example half size when it pumped before the call). The math is shown in one line, e.g. *"$60 = min($100 10 % per token of $1000; $60 6 % for medium risk; $354 liquidity ≤ 0.5 % buy impact)"*. When the result is below a sensible minimum ticket ($15, Ethereum mainnet $100), it is raised to that minimum and you get **fewer positions** instead of tiny ones.

### 4. How — OUR exit plan

**Our plan, step by step** opens the steps: entry near the Dossier decision price, then OUR exit ladder measured on past calls of the same stage or class (for KOL calls the KOL plan), the stake-back step, the stop (−30 % on an hourly close, or your own stop) and a time exit after at most **7 days**, plus what FORA watches.

<figure><img src=".gitbook/assets/shot-fora-planner-steps.jpg" alt="One plan opened: OUR plan — a quarter at +20 %, stake back at +50 %, rest at +70 %, stop −30 % on an hourly close, time exit after 7 days, and what FORA watches"><figcaption><p>One plan opened: entry, OUR exit ladder, stop, time exit and the risk events FORA watches.</p></figcaption></figure>

### 5. I bought — FORA follows the plan

**Buy in my wallet (you confirm)** pre-fills the swap in **[Formion Wallet](wallet.md)** — you review and sign. FORA never buys. After you buy, tap **I bought — follow this plan** (or tell FORA in chat). From then on FORA checks every 5 minutes and sends **"do this now"** in the app and on Telegram for:

* each step of the exit ladder and the stake-back step;
* the stop, giving back half of the gain from the peak, and the 7-day time exit;
* risk events from the live Dossier tracker: liquidity pulled from the pool, the dev wallet selling, whales selling, a worse sell route (exit risk).

Each message is sent exactly once. A plan closes by itself on the stop, the time exit or when every step is done; **Yes, I sold — stop** ends it any time. Every **Monday** you get *"How your plans did this week"* — plans, closed and open, and the result of OUR plan steps as a paper estimate from your entries.

### Free vs Pro

**Neural (Free)** sees what FORA likes today and why — the token, the reasons and FORA's opinion — **without numbers** (no entry, size or exits). **Pro** and **Institutional** add the entry, the size for your bankroll, OUR exit steps and FORA following every step for you; the same unlock is available with **FOM Lock**. Up to 3 plans at a time on Free, 5 on Pro and 10 on Institutional.

***

## KOL watch Neuron

**KOL watch** (Pro and Institutional) follows KOLs on X and Telegram and lets FORA decide on every new call they post.

<figure><img src=".gitbook/assets/shot-neurons-kol-watch.jpg" alt="KOL watch settings: FORA picks the best or I choose the KOLs, the measured source list with scored calls and our plan result, chains, minimum Dossier score and delivery options"><figcaption><p>New Neuron → KOL watch: pick the sources, chains and minimum Dossier score (Docs Demo account).</p></figcaption></figure>

* **Which KOLs** — **FORA picks the best** (the sources with the best measured record: our plan on at least 5 of their past calls, never one marked *Keep refining*; the list updates itself) or **I choose the KOLs** from the measured list. Each source shows its scored calls, our plan's average with its range, and a status such as *Verified* or *Collecting data*.
* **The chain on every new call** — Dossier verdict and risk → fresh only (the Dossier decided at most 60 minutes after the post) → the KOL filter → the source's record. Then FORA decides **PROPOSE**, **WATCH** or **SKIP** and says why in one sentence.
* **A PROPOSE card** (app + Telegram) carries what we found, FORA's opinion and OUR plan: entry near the Dossier decision price, a size within your own max per trade, our exit ladder, the stop rule and at most 7 days — plus **Buy in my wallet**, which only pre-fills a swap you confirm. The card also carries your personal plan line from **My plan** (🧭 Your plan …).
* **Limits** — up to **5 proposals a day on Pro** and **20 on Institutional**; a FOM boost adds more.
* **Also show WATCH calls in the app** (optional) — calls that passed the Dossier but not every check. Never on Telegram.

### Free: one token of opportunity per week

Free users with active Neurons can get at most **one token of opportunity every 7 days** — and never a new one while the previous one is still open. It is only a call that passed the whole chain as PROPOSE, with the token, chain, why and FORA's opinion — **no entry, exit or amount**. The full plan is in Pro (7-day trial) or with FOM Lock.

{% hint style="warning" %}
Research, not financial advice — what we found + FORA's opinion. No profit is promised. Exits are OUR rule measured on past calls, never anyone's promise. Small samples are labelled *Collecting data*.
{% endhint %}
