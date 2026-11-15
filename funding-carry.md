# ⚖️ Funding Carry

<figure><video src=".gitbook/assets/clip-funding-carry.mp4" title="Funding Carry — long on one venue, short on another, funding vs round-trip cost"></video><figcaption><p>A carry pair collects the funding gap every interval; it must first cover the cost of entering and closing both legs, and funding can reverse before break-even.</p></figcaption></figure>

**Funding Carry** researches the difference in perpetual funding between venues for the same asset. A pair combines a long on one venue and a short on another. Its value depends on funding collected over the holding period relative to the costs of entering and closing both legs.

## What you see

The hub contains the **Scanner**, **All Markets**, **Venues**, **Execution Cost**, **RWA** markets and the **Paper Book**. All Markets is a coverage view; the scanner is where pairs are compared for a potential trade. RWA instruments are separated from crypto because the same ticker can refer to different underlying assets.

Scanner rows include the venue pair, net annualised rate at the chosen holding period, historical 24-hour/7-day/30-day windows, carry per hour, round-trip cost, projected break-even time, historical cost coverage, adverse-funding periods, volume and open interest. A rate on one leg’s notional differs from a rate on the capital needed for both legs.

## Research a pair

1. Use All Markets or RWA to locate the asset and confirm that both venues refer to the same underlying instrument.
2. Open the Scanner and select venues, position size and holding period. Search by ticker and use the volume and venue filters to narrow the list.
3. Choose the execution assumption: **maker/maker**, **maker entry with taker exit**, or **taker/taker**. Maker fills are an assumption, not a certainty.
4. Compare net carry and round-trip cost. Review the historical windows and how often funding actually covered the cost, alongside projected break-even.
5. Open the pair detail and use Execution Cost to examine measured book costs at the relevant size. Check venue fees and the available samples.
6. Follow the **Funding Carry Paper Book** in [Trades History](trades-history.md) to inspect simulated positions and outcomes.

## Interpret the numbers

The current spread is a snapshot. Historical cost coverage and adverse periods help judge persistence; neither establishes future funding. Funding may reverse before break-even, and the two legs retain separate margin, liquidation, basis and venue risks.

### When does carry pay?

* We measured BTC/ETH cash-and-carry (spot long + perp short) from 2020 to October 2026, after fees and slippage on both entry and exit.
* When the market-wide median funding rate sits at the **base rate (about 0.01 % per 8 h, ≈ 11 % a year) or lower**, this carry earned **roughly nothing after costs** in **Oct 2024 – Oct 2026** (about +0.003 % a day, not different from zero).
* It paid only in periods of **high funding (2020–2024)**.
* Altcoin carry (top 20 by funding) lost money in the same test period.
* Status: **Collecting data** — a paper measurement of the market funding regime runs daily, with no orders. FORA can tell you the current state.

### Extreme negative funding — don't buy the dip at once

After a settlement of **−0.5 % or lower per interval**, the coin's price usually drops by about the funding amount right away and tends to keep falling for **1–4 hours**. It is not a short signal — just a reason to wait before buying that dip. Measured 21 Aug – 12 Nov 2026, 4,337 settlements. Status: **Context signal**.

{% hint style="warning" %}
The paper book is a simulation. It does not demonstrate that both legs filled live at the displayed prices. Recheck size, execution assumptions and the holding horizon before comparing pairs.
{% endhint %}

Related: [Data Hub](data-hub.md) · [Markets](markets.md) · [Bots](bots.md) · [Trades History](trades-history.md).

```mermaid
flowchart LR
  A[All Markets or RWA] --> B[Scanner venue pair]
  B --> C[Position size and holding period]
  C --> D[Maker or taker assumptions]
  D --> E[Execution Cost and historical coverage]
  E --> F[Funding Carry Paper Book]
```
