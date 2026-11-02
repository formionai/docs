# 🌊 Order Flow & Microstructure

<figure><img src=".gitbook/assets/s2-order-flow.jpg" alt="Order Flow — significant trades tape, aggregation and liquidations"><figcaption></figcaption></figure>

<figure><video src=".gitbook/assets/rec-order-flow-tour.mp4" title="Live recording: Data Hub → Order Flow, Orderbook Heatmap, DOM Pro, Liquidation Map and Walls."></video><figcaption><p>Live recording: Data Hub → Order Flow, Orderbook Heatmap, DOM Pro, Liquidation Map and Walls.</p></figcaption></figure>

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
| **Walls** | Live wall detector plus a history of confirmed, broken and pulled walls. A wall is resting liquidity that can be pulled at any time, so it is context, not a support or resistance promise. The **Walls Bot** paper book (v2, real fills, measured from 2 Nov 2026) and its Backtesting filters are described under **[Screener → Order Book](screener.md#order-book)** |
| **Liquidation Map** | Clustered liquidation levels over time — magnet levels, with a leverage filter |
| **Spoof / Iceberg detector** | Flags levels cancelled without being filled and levels that refill after being eaten (Constructor panel) |

<figure><img src=".gitbook/assets/s2-dom-pro.jpg" alt="DOM Pro depth-of-market ladder"><figcaption><p>DOM Pro — depth-of-market ladder with size and trade heatmaps.</p></figcaption></figure>

<figure><img src=".gitbook/assets/s2-liquidation-map.jpg" alt="Liquidation Map"><figcaption><p>Liquidation Map — clustered liquidation levels over time.</p></figcaption></figure>

<figure><video src=".gitbook/assets/rec-order-flow-constructor.mp4" title="Live recording: Chart Pro → Constructor — chart + volume profile, tape feed and liquidations side by side, then the Heatmap Focus preset."></video><figcaption><p>Live recording: Chart Pro → Constructor — chart + volume profile, tape feed and liquidations side by side, then the Heatmap Focus preset.</p></figcaption></figure>

## Why it matters

<figure><video src=".gitbook/assets/clip-order-flow.mp4" title="Order flow — footprint, delta, CVD, absorption, walls and liquidation magnets"></video><figcaption><p>Absorption, a resting wall and a liquidation cluster — the three patterns these tools help you read.</p></figcaption></figure>

Indicators lag; order flow is the cause, not the effect. Seeing absorption at a level, where large resting orders sit, or where liquidations cluster helps you read what the market is doing right now. Resting orders can be pulled at any time, so treat walls as context about the current book, not as a promise of support or resistance. Formion puts that read in one place.
