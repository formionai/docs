# 📰 News 24/7 & Macro

<figure><img src=".gitbook/assets/s2-news.jpg" alt="News 24/7 & Macro"><figcaption><p>Formion — News 24/7 & Macro</p></figcaption></figure>

<figure><video src=".gitbook/assets/rec-news-tour.mp4" title="Live recording: the Economic Calendar, then AI Impact News, Macro Impact and the Crypto News Feed."></video><figcaption><p>Live recording: the Economic Calendar, then AI Impact News, Macro Impact and the Crypto News Feed.</p></figcaption></figure>

The **News** hub combines scheduled economic releases, AI impact analysis, historical macro reactions and crypto events/headlines. Use it to identify what may affect the instrument you are researching and when that information became available.

## What you see

* **Economic Calendar** — economic events with day-range and impact filters, grouped by date.
* **AI Impact News** — news analysis for market context.
* **Macro Impact** — historical macro-event impact review.
* **Crypto Calendar** — coin events when this view is available; the tab is hidden when unavailable.
* **Crypto News Feed** — crypto headlines with freshness and availability information.

## 🎛️ Economic Calendar — Classic · Visual

Above the calendar list a **Classic · Visual** switch opens the **Macro shock timeline**, drawn from the same events and filters (Impact, Range, Measured):

* One time axis over your Range: left of **Now** = prints already released, right = upcoming.
* Each measured event is a pin; height = its measured typical 15-minute move of the currency basket vs a normal 15 minutes (1×–5×, since 2021). Red = Strong mover, accent = Moderate, muted = Calm; unmeasured events are small ticks.
* The sweep sends a shock ring for every released measured print; the next event measured at 1.5× or more gets a countdown.

<figure><img src=".gitbook/assets/shot-visual-news-shock.jpg" alt="Economic Calendar in Visual: macro shock timeline"><figcaption><p>Economic Calendar → Visual: measured reaction size of released and upcoming events.</p></figcaption></figure>

The height is the historical typical size of the reaction — never a forecast of direction or of this print — **Context signal · not a signal**. Same data as Classic, same plan limits; **Auto** (the default in [Settings → Visual mode](settings.md)) starts it in Classic — one click on **Visual** switches, and the panel remembers it.

## Prepare for an event

1. Open Economic Calendar and select the day range and impact level relevant to your trading horizon.
2. Read the event time, country and available release values. Confirm the displayed timezone before planning around a release.
3. Use AI Impact News for interpretation and Macro Impact for available historical reaction context.
4. For a coin-specific catalyst, check Crypto Calendar when present, then read the related headlines in Crypto News Feed.
5. Inspect timestamps and any freshness or availability notice. Open the article for its full context where a link is provided.
6. Compare the event with the instrument in [Chart Pro](chart-pro.md) and [Data Hub](data-hub.md), then record the catalyst in your [Journal](journal.md).

## Practical tips

An empty calendar can reflect the chosen filters or available event coverage. Widen the impact filter or date range before treating it as “nothing scheduled”. If a pane reports unavailable or older data, use that state when judging the freshness of the analysis.

Distinguish a scheduled release from a headline discussing an earlier event. AI impact is an interpretation; price reaction also depends on expectations and the wider market regime.

{% hint style="info" %}
Use event time and headline publication time together. A fresh article about an old release can have different trading relevance from a new announcement.
{% endhint %}

Related: [Markets](markets.md) · [Pulse](pulse.md) · [AI Advisor](smart-trading.md).

```mermaid
flowchart LR
  A[Economic Calendar filters] --> B[Release time and available values]
  B --> C[AI Impact News]
  C --> D[Macro Impact history]
  E[Crypto Calendar and News Feed] --> F[Chart Pro instrument review]
  D --> F
  F --> G[Journal catalyst notes]
```
