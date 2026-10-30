# 🌊 Order Flow & Microstructure

<figure><img src=".gitbook/assets/s2-order-flow.jpg" alt="Order Flow — significant trades tape, aggregation and liquidations"><figcaption></figcaption></figure>

See **what's happening inside the candle**. Formion ships a full market-microstructure suite — the order-book, the tape, large trades, liquidations and where the big resting orders sit — across multiple exchanges.

{% hint style="info" %}
The microstructure tools live both as dedicated pages under **Data Hub** and as panels inside **Chart Pro → Constructor**.
{% endhint %}

## The tools

| Tool | What it shows |
|---|---|
| **Order Flow** | Trades and liquidations streamed from Binance, Bybit, OKX and Coinbase, with an aggregated CVD and a **Significant Trades** feed |
| **Tape Feed** (Time & Sales) | Every print in real time (Constructor panel) |
| **DOM Pro** | A depth-of-market ladder with a size heatmap, a trade heatmap and VWAP / POC / VAH / VAL levels |
| **Order-Book Heatmap** / **Agg Heatmap** | Resting liquidity over time — for the Binance book, or summed across exchanges |
| **Footprint** | Bid/ask volume **inside** each candle by price tick (Constructor panel) |
| **Walls** | Live wall detector plus a history of confirmed, broken and pulled walls |
| **Liquidation Map** | Clustered liquidation levels over time — magnet levels, with a leverage filter |
| **Spoof / Iceberg detector** | Flags levels cancelled without being filled and levels that refill after being eaten (Constructor panel) |

<figure><img src=".gitbook/assets/s2-dom-pro.jpg" alt="DOM Pro depth-of-market ladder"><figcaption><p>DOM Pro — depth-of-market ladder with size and trade heatmaps.</p></figcaption></figure>

<figure><img src=".gitbook/assets/s2-liquidation-map.jpg" alt="Liquidation Map"><figcaption><p>Liquidation Map — clustered liquidation levels over time.</p></figcaption></figure>

## Why it matters

<figure><video src=".gitbook/assets/clip-order-flow.mp4" title="Order flow — footprint, delta, CVD, absorption, walls and liquidation magnets"></video><figcaption><p>Absorption, a resting wall and a liquidation cluster — the three patterns these tools help you read.</p></figcaption></figure>

Indicators lag; order flow is the cause, not the effect. Spotting absorption at a level, a wall that won't break, or a liquidation cluster acting as a magnet is the difference between guessing and reading the book. Formion puts that read in one place.
