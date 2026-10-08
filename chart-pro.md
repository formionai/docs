# 📊 Chart Pro

<figure><img src=".gitbook/assets/chart-pro.jpg" alt="Formion Chart Pro — professional chart with indicators, order flow and replay"><figcaption>A professional charting workspace with an order-flow layer most platforms charge extra for.</figcaption></figure>

**Chart Pro** (app.formion.ai → Chart Pro) is Formion's full charting workspace — live data, deep indicators, custom scripts and a complete order-flow toolkit.

## Charting

* **Live OHLCV** across crypto, forex, stocks, commodities and indices
* **12 timeframes** (1m → 1W), plus custom minute timeframes (e.g. 17m) on crypto
* **100+ indicators**, including the proprietary **FormionTSI**
* **Drawing tools**, multi-chart **split view**, and saved **layouts**
* **Replay mode** — step through history bar-by-bar to practice or study a setup

## User Indicator Studio

Upload your own **Pine scripts** and render them on the chart — a Pine-subset compiler handles common scripts, with an AI translation fallback for the rest; both run through the same sandboxed pipeline. Your custom indicators sit alongside the built-ins.

## Order-flow Constructor

```mermaid
flowchart LR
  W["🔬 Constructor"] --> VP["📊 Chart + Volume Profile"]
  W --> FP["👣 Footprint"]
  W --> DOM["🪜 DOM Ladder"]
  W --> OB["🔥 Orderbook Heatmap"]
  W --> LT["🧾 Tape + Liquidations"]
  W --> SP["🥷 Spoofing / Iceberg"]
```

The **Constructor** tab (Chart Pro → Constructor) is a dockable, resizable multi-panel layout with order-flow presets. It exposes microstructure usually reserved for paid terminals:

* **Volume Profile** & **Footprint** — where volume and delta actually traded
* **Order book**, **multi-source order book** (Binance, Bybit, OKX, Hyperliquid), **DOM ladder** & **Orderbook heatmap** — resting liquidity and walls
* **Tape feed** (every print), **liquidations** feed and **spoofing / iceberg** detection — spot manipulation and absorption

{% hint style="info" %}
Open any **[Screener](screener.md)** row straight into Chart Pro to go from "this scored well" to "here's exactly where I'd enter" in one click.
{% endhint %}

{% hint style="info" %}
On the free **Neural** tier charting covers 5 symbols, 4 timeframes (1H, 4H, 1D, 1W), 2 indicators and 3 drawings, without SMC zones or replay. **Pro** and **Institutional** unlock all symbols, timeframes, indicators and drawings, SMC zones and replay mode — see **[Pricing & Tiers](pricing.md)**.
{% endhint %}
