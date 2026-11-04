# 🗺️ Liquidity Map

<figure><img src=".gitbook/assets/shot-liquidity-map-heatmap.jpg" alt="Liquidity Map — recorded resting liquidity over time and price, with the traded price line"><figcaption><p>The resting liquidity map: time left to right, price bottom to top, brighter = more resting USD in the order books.</p></figcaption></figure>

<figure><video src=".gitbook/assets/rec-liquidity-map-read.mp4" title="Live recording: pick a coin (ETH) and a range (6h), switch on the Persistent walls filter, hover the map to read a price row, then the Liquidity Tracker with H 25 bp and H 100 bp, the per-venue ladder and pull/stack. Dark vertical gaps are minutes that were not recorded — they are never filled in."></video><figcaption><p>Live recording: pick a coin (ETH) and a range (6h), switch on the Persistent walls filter, hover the map to read a price row, then the Liquidity Tracker with H 25 bp and H 100 bp, the per-venue ladder and pull/stack. Dark vertical gaps are minutes that were not recorded — they are never filled in.</p></figcaption></figure>

The **Liquidity Map** (app.formion.ai → Data Hub → **Liquidity Map**, `/liquidity-map`) shows where buyers and sellers had orders **resting** in the order books, minute by minute — summed across **11 markets**, recorded by Formion and kept for 30 days. It replaces the old **Heatmap** and **Agg Heatmap** pages; their links now open the Liquidity Map.

{% hint style="info" %}
The Liquidity Map is a **Context signal**. It describes what was in the books — it does not predict price and it never gives an entry, stop or target. Resting orders can be pulled at any moment, and in book data a fill and a cancel look the same.
{% endhint %}

## What is recorded

| | |
|---|---|
| **Coins** | BTC, ETH, SOL and HYPE |
| **Markets (11)** | Binance perp + spot, Bybit perp + spot, OKX perp + spot, Bitget perp + spot, Coinbase, Hyperliquid, Deribit |
| **How** | Every order book is sampled every **5 seconds** and averaged per minute; resting orders within **±5 %** of price are kept |
| **History** | **Recording since 2 Nov 2026**, kept for 30 days. A range longer than what has been recorded shows only the recorded part (with the % covered) — empty areas are never filled in |
| **Ranges** | 1h · 6h · 24h · 7d · 30d |

## The 7 panels

### 1. Resting liquidity map

<figure><img src=".gitbook/assets/shot-liquidity-map-heatmap.jpg" alt="Resting liquidity map panel"><figcaption><p>Bright horizontal bands = price levels where large orders stayed resting; the line is the traded price.</p></figcaption></figure>

* **What it shows:** time on the horizontal axis, price on the vertical axis; each cell is the resting USD at that price in that time bin (log colour scale, darker → brighter = less → more). The line is the traded price.
* **Controls:** **Venue** (all 11 markets summed, or one market), **Persistent walls** (shows only liquidity that stayed at least 5 minutes on 1h / 6h, or for the whole time bin on longer ranges — this hides orders that flash in and out), and **Contrast**. Hover a cell to read its price row, time and USD.
* **Gaps:** minutes with no recording (for example during a restart) stay empty as dark vertical stripes — nothing is filled in.
* **How to read it:** a bright band that stays in place while price approaches is liquidity that was really sitting there; a band that disappears before price gets to it was pulled.
* **What it is NOT:** not a support/resistance promise and not a forecast — a band can vanish at any moment.

### 2. Liquidity Tracker

<figure><img src=".gitbook/assets/shot-liquidity-map-tracker.jpg" alt="Liquidity Tracker panel — bids vs asks over time, imbalance and share within ±0.25 / ±1 / ±5 %"><figcaption><p>Bids vs asks over time, the imbalance line and the bid/ask share near price.</p></figcaption></figure>

* **What it shows:** bid liquidity vs ask liquidity of all venues over the range, where each order is weighted by its distance from that venue's own best price. **H 25 bp / H 100 bp** is the half-life: an order this many basis points away counts half. Next to it, the **imbalance** (bid − ask) / total in %, and a table with the bid/ask **share within ±0.25 %, ±1 % and ±5 %** of price for the last minute.
* **How to read it:** H 25 bp focuses on the book right next to price; H 100 bp includes deeper orders. A positive imbalance means more resting bids than asks.
* **What it is NOT:** a lean in the book is not a direction call — the book can change in seconds.

### 3. Per-venue ladder

<figure><img src=".gitbook/assets/shot-liquidity-map-ladder.jpg" alt="Per-venue ladder panel"><figcaption><p>Resting USD per price row, split by venue (colour), asks above and bids below the reference mid.</p></figcaption></figure>

* **What it shows:** resting USD per price row, averaged over the last recorded minute, with each bar split by venue. Rows on the wrong side of the current price (left over from earlier in that minute) are hidden.
* **How to read it:** see which venue a large level comes from — liquidity on one venue only is different from a level stacked on many.
* **What it is NOT:** not the live tick-by-tick book; it is a one-minute average.

### 4. Pull / stack near price

<figure><img src=".gitbook/assets/shot-liquidity-map-pullstack.jpg" alt="Pull / stack near price panel"><figcaption><p>Gross USD stacked and pulled per row within ±1 % of price, and the net change, over 1, 5 or 15 minutes.</p></figcaption></figure>

* **What it shows:** for each price row within ±1 % of price, the gross USD **added** (stacked) and **removed** (pulled) over the last **1, 5 or 15 minutes**, all venues together, and the net change. Every book update counts, so near price the gross numbers are large.
* **How to read it:** a net positive row is where orders were building; a net negative row is where they were leaving. Rows marked with the target icon were traded through in the window — there a fill and a cancel look the same.
* **What it is NOT:** "pulled" does not mean cancelled for sure where price traded.

### 5. Persistent walls

* **What it shows:** big resting levels (at least the top 5 % of their side of the book) that lived at least 60 seconds, listed **once they end**: price, side (Bid / Ask), maximum size, venues that held it, how long it lived, when it was seen (UTC) and the outcome — **Touched by price** or **Pulled before touch**. The header counts recorded walls, walls that lived 5 min+, and the share pulled before touch; **Persistent only** keeps the 5 min+ walls.
* **How to read it:** use it to see how often big walls near the market were actually reached, and how often they were removed before price got there.
* **What it is NOT:** a wall that is still standing appears only after it ends. A wall is context about the book, not a promise of support or resistance.

### 6. CVD per venue

<figure><img src=".gitbook/assets/shot-liquidity-map-cvd.jpg" alt="CVD per venue panel"><figcaption><p>Cumulative taker buys minus taker sells per venue, with taker buys, taker sells and net delta.</p></figcaption></figure>

* **What it shows:** cumulative taker buys minus taker sells (CVD) for each venue over the selected range, plus a table of taker buys, taker sells and net delta per venue. A venue with no recorded trades in the window is listed as such.
* **How to read it:** compare where aggressive buying or selling happened — for example perp venues vs spot venues.
* **What it is NOT:** executed flow, not resting orders; it does not tell you what comes next.

### 7. Hyperliquid liquidation levels

<figure><img src=".gitbook/assets/shot-liquidity-map-hlliq.jpg" alt="Hyperliquid liquidation levels panel"><figcaption><p>Where real open positions of tracked Hyperliquid accounts get liquidated, ±10 % of price.</p></figcaption></figure>

* **What it shows:** the **real liquidation prices of open positions** held by the Hyperliquid accounts Formion tracks (about the top 2,000 accounts), within ±10 % of price, refreshed every 10 minutes: price row, number of positions and notional, long vs short, with the snapshot time and mark price.
* **How to read it:** long and short liquidations are coloured separately (with their totals above the table); large rows show where tracked positions would be forced to close if price got there.
* **What it is NOT:** not a model or an estimate, and **not the whole market** — only the tracked accounts on Hyperliquid.

## Free vs Pro

| | Free | Pro / Institutional |
|---|---|---|
| Coins | BTC | BTC, ETH, SOL, HYPE |
| Range | Last 1 hour | Up to 30 days of recorded history |
| Panels | Resting liquidity map + Liquidity Tracker | All 7 panels |

Locked coins, ranges and panels never leave the server for a Free account. See **[Pricing & Tiers](pricing.md)**.

## FORA

FORA can read the Liquidity Map as **context** (the state of the book, which can be pulled) and quotes only the real recorded numbers — it never uses it as an entry, stop or target and never as a prediction. See **[FORA](fora.md)**.

## Related

* **[Data Hub](data-hub.md)** — the other derivatives and order-flow pages.
* **[Order Flow & Microstructure](order-flow.md)** — Order Flow, DOM Pro, Liquidation Map and Walls.
* **[Screener → Order Book](screener.md#order-book)** — the book imbalance and walls for the top Binance perpetuals.
