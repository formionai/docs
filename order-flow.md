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
| **Liquidity Map** | Recorded resting liquidity over time, summed across 11 markets, with tracker, ladder, pull/stack, walls, CVD and Hyperliquid liquidation levels. It replaces the old Order-Book Heatmap and Agg Heatmap pages — see **[Liquidity Map](liquidity-map.md)** |
| **Footprint** | Bid/ask volume **inside** each candle by price tick (Constructor panel) |
| **Walls** | Live wall detector plus a history of confirmed, broken and pulled walls. A wall is resting liquidity that can be pulled at any time, so it is context, not a support or resistance promise. The **Walls Bot** paper book (v2, real fills, measured from 2 Nov 2026) and its Backtesting filters are described under **[Screener → Order Book](screener.md#order-book)** |
| **Liquidation Map** | A model estimate of where leveraged positions would be force-closed, over time — magnet levels, with a leverage filter. See **[Liquidation Map](#liquidation-map)** below |
| **Spoof / Iceberg detector** | Flags levels cancelled without being filled and levels that refill after being eaten (Constructor panel) |

<figure><img src=".gitbook/assets/s2-dom-pro.jpg" alt="DOM Pro depth-of-market ladder"><figcaption><p>DOM Pro — depth-of-market ladder with size and trade heatmaps.</p></figcaption></figure>

<figure><img src=".gitbook/assets/s2-liquidation-map.jpg" alt="Liquidation Map"><figcaption><p>Liquidation Map — clustered liquidation levels over time.</p></figcaption></figure>

## Liquidation Map

The **Liquidation Map** (Data Hub → **Liquidation Map**, `/liquidation-map`) is a **model estimate**: from open interest and positions opened over the chosen window it estimates **where leveraged positions would be force-closed**. The source is Binance USDⓈ-M (optionally Bybit coin-margined). Sizes are **relative strength, not dollars**. **Heatmap** shows the levels over time with candles, **Map** shows them by price and leverage group.

* **Full screen:** the **Full screen** button above the chart (or the **F** key) opens the whole panel — chart with its price axis, the lower pane, the legend and Appearance — on the whole screen; **Esc**, **F** or the button closes it. On iPhone it fills the browser window.
* **What it is NOT:** these are not orders in the book and not a forecast — they only show where forced orders could appear if price gets there.

### Liquidity Map vs Liquidation Map

| | **[Liquidity Map](liquidity-map.md)** | **Liquidation Map** |
|---|---|---|
| **What it is** | **Real resting limit orders** that Formion records from 11 venues | A **model estimate** of where leveraged positions would be force-closed |
| **What you see** | Where orders sit now and where they sat before, in **real USD** | Where forced orders could appear — **relative strength, not dollars** |
| **Source** | Order books of 11 markets (Binance, Bybit, OKX, Bitget perp + spot, Coinbase, Hyperliquid, Deribit) | Binance USDⓈ-M (optionally Bybit coin-margined) |
| **Can it change?** | Yes — any order can be **pulled** at any moment | Yes — the estimate moves as positions open and close |

The Liquidity Map also shows **real Hyperliquid liquidation levels** — actual liquidation prices of open positions, but **only of the Hyperliquid accounts we track**.

<figure><video src=".gitbook/assets/rec-order-flow-constructor.mp4" title="Live recording: Chart Pro → Constructor — chart + volume profile, tape feed and liquidations side by side, then the Heatmap Focus preset."></video><figcaption><p>Live recording: Chart Pro → Constructor — chart + volume profile, tape feed and liquidations side by side, then the Heatmap Focus preset.</p></figcaption></figure>

## Why it matters

<figure><video src=".gitbook/assets/clip-order-flow.mp4" title="Order flow — footprint, delta, CVD, absorption, walls and liquidation magnets"></video><figcaption><p>Absorption, a resting wall and a liquidation cluster — the three patterns these tools help you read.</p></figcaption></figure>

Indicators lag; order flow is the cause, not the effect. Seeing absorption at a level, where large resting orders sit, or where liquidations cluster helps you read what the market is doing right now. Resting orders can be pulled at any time, so treat walls as context about the current book, not as a promise of support or resistance. Formion puts that read in one place.
