# 📡 Formion Pulse — Market Narrative

<figure><img src=".gitbook/assets/s2-pulse.jpg" alt="Formion Pulse — Pulse Score gauge, BTC bias, source filter and sentiment-vs-price history"><figcaption>Formion Pulse: one score from many voices.</figcaption></figure>

<figure><video src=".gitbook/assets/rec-pulse-scroll.mp4" title="Live recording: Pulse Score and BTC bias, the source filter, Pulse vs market history and the X Influencer Desk."></video><figcaption><p>Live recording: Pulse Score and BTC bias, the source filter, Pulse vs market history and the X Influencer Desk.</p></figcaption></figure>

Formion Pulse answers one question other tools ignore: **what are the big voices and the crowd actually *saying* right now?**

It is deliberately different from a Fear & Greed gauge or a long/short ratio (those measure *positioning*). Pulse reads the **narrative** — crypto X (Twitter) traders, YouTube influencers, social chatter and headlines — and blends it with price into a single **Pulse Score (0–100)**, where 50 = balanced, higher = more bullish narrative.

Find it at **app.formion.ai → Coins Hub → Pulse** (also linked from the Analytics strip).

```mermaid
flowchart LR
  X["𝕏 Influencer Desk"] --> P(("Pulse Score 0–100"))
  Y["▶ YouTube Desk"] --> P
  C["📣 Crowd & Social"] --> P
  F["😨 Fear & Greed"] --> P
  B["₿ BTC Bias"] --> P
  P --> S["📈 Sentiment-vs-Price history"]
```

## What it watches

* **𝕏 Influencer Desk** — recent posts from a curated roster of crypto traders, each classified **bull / bear / neutral** with a one-line thesis and the coin it refers to. When an influencer posts a bare **chart screenshot**, a vision model *reads the chart itself* — drawn levels, arrows, long/short annotations — and labels it (**"CHART READ"** badge).
* **▶ YouTube Desk** — the latest videos from top crypto channels, each scored bull / bear / neutral by title + description.
* **📣 Crowd & Social** — recent market headlines and social chatter, synthesised into a short read with a bull/bear split and a mood (fearful → euphoric).
* **😨 Fear & Greed** and **₿ BTC Bias** — global mood plus BTC price and multi-horizon momentum (24h / 7d / vs 50-period SMA).

<figure><img src=".gitbook/assets/s4-pu-desk.jpg" alt="X Influencer Desk"><figcaption><p>The X Influencer Desk — tracked posts, each classified bullish, bearish or neutral.</p></figcaption></figure>

## Sentiment history & filtering

* **Sentiment-vs-Price history** — the Pulse Score plotted against the BTC price over the last 30 days, so you can see how the narrative moved relative to the market.
* **Source filter** — mute or un-mute any account or channel. The **Pulse Score and desks recompute instantly for you** — so you can see the market through only the voices *you* trust. Your selection is remembered on your device.

<figure><img src=".gitbook/assets/s4-pu-history.jpg" alt="Pulse vs market history"><figcaption><p>Pulse vs market — the Pulse Score plotted against BTC over time.</p></figcaption></figure>

## Quantum Pulse — who is actually right

Quantum Pulse adds measured records on top of the narrative: what the followed traders, the crowd, prediction markets and any X account said — and what price did afterwards. Quantum Pulse is in **beta** and is opened step by step; **Market Narrative** is open to everyone.

| Tab | What it shows |
| --- | --- |
| **Market Narrative** | The Pulse Score, BTC bias, desks, source filter and history described above. |
| **Pulse Shift** | The exact moment the Pulse Score changed regime (held for two readings), with BTC / ETH / SOL / HYPE prices at the first signal and at confirmation, and the best / worst price move afterwards (4 h / 24 h / 7 d). Context, not a signal. |
| **Following** | The traders you follow and your alerts when one of them posts a new idea, flips bias or an idea changes status — on Telegram (via @formiontradingbot) and Web Push, with quiet hours in your time zone. An alert is information about *his* post, never an order. |
| **Crowd Pulse** | What the followed X accounts say per coin: an index 0–100 (50 = neutral) for today and 7 days, and per horizon short / mid / long (a horizon only from the trader's own evidence). Crowd talk vs positioning, stance timelines (green dot = bull call, red dot = bear call; hover for his post, click to open it on X) and the Quantum Crowd indicator (line width = number of votes, brightness = how one-sided the crowd is). Everything is *Collecting data* until it holds on new days. |
| **Prediction Markets** | What Kalshi and Polymarket post about crypto on X, and what their monthly "how low / how high" markets price. Each post is measured from the minute it was posted: **1)** direction right and how far (best move their way, worst against) vs a control, **2)** the close, **3)** their level reached, **4)** calibration of "X % chance" posts. Example: price 75,000, they call 70,000 this month, price drops to 73,000 → a good direction call even though 70,000 was never reached. |
| **X Lens** | Type any X account: Formion keeps only posts where the author himself states a price forecast (BTC, ETH, SOL, XRP, gold, silver, oil, S&P 500, NASDAQ) and measures each one the same way — direction and best / worst move first, then the close, the level and the calibration. A dot sits on the candle of each post (green = direction right, red = wrong, grey = open); hover shows the post, click pins the card. X Lens does **not** feed the Pulse Score or any trader record. |
| **My Calls** | Your own up / down calls on a market and horizon, scored on real prices against the asset's own drift, with a community leaderboard (nicknames only). A call cannot be edited afterwards. |
| **Community Vote** | One vote per market per UTC day: up / down / sideways, shown next to the X crowd and what price actually did. A measurement of opinion, not a signal. |

Every followed trader also has a **[trader profile](pulse-trader-profile.md)**: the three numbers, what he gets right, how Formion would follow him, where we would exit, and a follower simulation with Spot | Perp, leverage, liquidation and funding.

## Trader records and badges

### Measured since 2026-11-01

Live tracking started on **2026-11-01** (00:00 UTC). Every idea a trader posts from that day on is followed from the moment it is posted. Ideas posted **before** that date are marked **Archive**: they are still shown and clearly labelled. The badge and every measured number use calls **measured since 1 Oct 2025** (00:00 UTC); older posts are kept only as **History (not measured)** to describe the trader's style and are never part of the badge. The profile shows the live part separately ("Live since 2026-11-01"), so archive ideas never inflate the live number.

### What counts as a call

A **counted call** is measured on the trader's own terms, each idea once:

* **His plan outcome** — when his entry actually traded, the result of *his* plan: his take-profit or stop-loss, whichever came first on the price path, or the exit he announced himself.
* **Otherwise, direction on his horizon** — if he gave no exit, the price move in his direction over his own typical holding time (the median of his earlier closed trades; 3 days until he has 5 closed trades), counted from the moment his entry traded.
* Every number is **after costs** (0.12 % round trip). An idea whose entry never traded is not a trade and is not counted. Only levels the trader wrote or drew are used — Formion never adds an entry, stop or target of its own.

Next to these two, **Beyond the trend** (his move minus the asset's own drift) is shown as a **control** — it answers "did he add anything beyond the market?", never "was he right?". Why the three numbers can differ is explained on the [trader profile](pulse-trader-profile.md#measured-on-his-own-terms-the-three-numbers) page.

### Badge rules

| Badge | Rule |
| --- | --- |
| **Verified** | At least **30** counted calls, the lower bound of the 95 % confidence interval of the average result per call is **above 0**, a multiple-testing check across all traders (Benjamini–Hochberg) passes, **and** his newest third of calls — never used for the decision — is above zero |
| **Collecting data** | Everything else — too few calls, or the result is not yet clear |

A badge is never negative: Pulse never labels a trader as bad. A badge describes measured past calls only; it is not a promise of future results.

### Labels on single ideas

* **Timeframe is our reading** — he wrote "close above / below a level" without a timeframe; the level is his, the 1h and 1d readings of that close are ours, and the weaker number is shown.
* **Uncertain outcome (1h vs 1d)** — the same case, but the 1h and the 1d reading give a different outcome. The idea is never left out: the **weaker** of the two outcomes is used. If only one reading's entry traded and that trade gained, the weaker outcome is "no trade", so the idea is shown as not triggered.

## Plans

Limits are enforced on the server. FOM Lock levels unlock plans as well: **FORA Agent** includes Pro and **Agent Pro** includes Institutional (see [FOM token](fom-token.md)). A **FOM Holder** gets a little more than the plan, never less.

| Pulse feature | 🆓 Free | 💎 Pro | 🏛️ Institutional | 🪙 FOM Holder (on top of the plan) |
| --- | --- | --- | --- | --- |
| **Market Narrative** | ✅ | ✅ | ✅ | — |
| **Trader profile** | Header, badge and the three numbers | Full profile, segments, charts | Same as Pro | — |
| **If you follow him** (simulation) | 🔒 | ✅ | ✅ | — |
| **Following** | 1 trader · daily digest (08:00) | 10 traders · instant alerts (up to 50 / day) | Unlimited | +1 trader |
| **Pulse Shift history** | 7 days | Full | Full | 30 days on Free |
| **Crowd Pulse** | Combined index | + per horizon, opinion map, stance timelines | + crowd vs smart money and exchange positioning, regimes, Quantum Crowd indicator, CSV export | — |
| **Prediction Markets** | Live forecast, accuracy cards, 5 newest posts | All posts + study "Are the markets right?" | Same as Pro | — |
| **X Lens** | Example account only | Example account only | Full **with FOM** (hold FOM or a FOM Lock) · 5 new accounts / day | — |
| **My Calls** (open at once) | 3 | 20 | Unlimited | — |
| **Community Vote** | ✅ | ✅ | ✅ | — |
| **History** | 30 days | 365 days | Full | — |
| **FORA Pulse questions** | 3 / day | Unlimited | Unlimited | — |
| **Strategies built from Pulse traders** (saved) | 0 | 3 | Unlimited | — |
| **FORA Neurons Pulse tools** | — | — | ✅ | — |

{% hint style="info" %}
Pulse reads what people *say*. It is a sentiment and research tool, not a signal to act on blindly — pair it with your own analysis before trusting any voice.
{% endhint %}

## Use Pulse with the current workspace

Open a [trader profile](pulse-trader-profile.md) for the full record of one trader. Compare narrative context with [News and macro events](news.md), ask [FORA](fora.md) to explain the market context, and review trader calls in [Swarm](swarm.md). Pulse sentiment is an analytical input, not an instruction to execute.
