# 🎛️ Chart Indicators

Chart Pro (**app.formion.ai/chart**) has a second set of indicators next to the classic grid: **Formion indicators**. They read Formion's own data — trader calls, positioning, market-wide state — and draw it on your chart. Every indicator on this page works on both chart engines, **Swift** and **Velocity** (see [Chart Pro](chart-pro.md)).

{% hint style="info" %}
None of these indicators gives a buy or sell signal, and none draws levels of ours. Where a level is shown, it is the trader's own level, exactly as he wrote it. Each card shows its **measured status** — **Verified**, **Collecting data** or **Context signal** — so you know how much weight it can carry.
{% endhint %}

## Formion indicators gallery

Open it with the **Formion indicators** button in the tools row above the chart (the number next to it = how many are on).

<figure><img src=".gitbook/assets/shot-chart-indicators-gallery.jpg" alt="Formion indicators gallery: Volatility Ahead, Swarm Verified Calls, Smart Money Flow, Rotation Meter and Positioning Heat cards, each with its status, where it draws and Customize with FORA"><figcaption><p>The gallery: every card says what it shows, where it draws, which markets it covers and its measured status.</p></figcaption></figure>

Every card shows:

* an icon, the name and one line on what it shows;
* where it draws — **On price**, **Lower pane** or **Time axis** — and which markets it covers;
* its status (hover the pill for the explanation);
* an on / off switch;
* **Customize with FORA** on the ready-made indicators — it opens [FORA](fora.md) with a ready prompt and the indicator's source code. Nothing is sent until you finish the sentence; FORA then builds **your own copy**.

There are two kinds of cards:

* **Chart layers** you already know — **Market Bias**, **Liquidation pressure** and **Events** — are only switched on and off from here. Events carries a **Calendar** tag instead of a status: it is a calendar of releases, not a measured signal.
* **Ready-made Formion indicators** — turning one on saves a copy into your indicator library, so it needs sign-in and is remembered on your account (you also find it in **My indicators**). They are computed on the server from Formion data aligned to each candle's close — no look-ahead.

| Indicator | Where | What it shows | Status |
| --- | --- | --- | --- |
| **Volatility Ahead** | Lower pane | The odds (%) that price leaves a band of ±1.5 ATR within the next 12 candles, from our live move model. **It does not predict direction.** Amber line = "Big move expected", teal line = "Quiet expected". BTC 1h and gold (XAU) 15m / 1h / 4h only. | Collecting data |
| **Pulse Consensus** | Lower pane | Net long vs short of followed traders' **active** calls on this coin, from public posts — green columns while net long, red while net short. Details below. | Context signal |
| **Swarm Verified Calls** | On price | Calls posted on [Swarm](swarm.md) by authors with FRS ≥ 300 and at least 10 graded calls — members and **Formion AI** — with the caller's own entry, stop and target while the call is open. | Collecting data |
| **Smart Money Flow** | Lower pane | Hyperliquid: whales' net position change per candle (purple histogram) and proven directional traders' net over the last 20 candles (amber line). Complete UTC days only — today is empty. Hyperliquid coins, 5m and up. | Context signal |
| **Rotation Meter** | Lower pane | % change of BTC dominance, TOTAL3 and USDT dominance, plus a **Rotation score**: above 0 = money moving toward alts, below 0 = toward BTC or stablecoins. The same on every symbol. | Context signal |
| **Positioning Heat** | Lower pane | z-score of funding (columns, amber beyond ±2) and of the open-interest change (line), each against its own last 200 candles. Dashed ±2 levels; the pane tints amber while either is beyond ±2 (crowded). Crypto perps. | Context signal |
| **Liquidity Sweep** | On price | Candles whose wick goes through a significant swing low or high and closes back inside — the stops beyond that swing were taken. Markers **Low swept** / **High swept**; dotted lines = active swing levels; optional labels show how deep the wick went in ATR. From the chart's own candles; swings are confirmed only after N candles, so nothing repaints. Any market. | Context signal |
| **Session Levels** | On price | Daily VWAP (from 00:00 UTC) with a ±1σ band and ±2σ lines, prior-day high / low and prior-week high / low. From the chart's own candles and volume. Intraday timeframes. | Context signal |
| **Crowding Risk** | Lower pane | One score for one-sided positioning: the average z-score of funding, open-interest change and top traders' long %. Red columns at +1.5 and above = crowded long, green at −1.5 and below = crowded short; the pane tints while crowded. Crypto perps. | Context signal |
| **Order Flow Delta** | Lower pane | Aggressive buy minus sell volume per candle. Amber = **absorption** (very large delta, the candle barely moved), violet = **trapped delta** (strong buying that closed near the low, or the reverse). Crypto. | Context signal |
| **Liquidation Levels** | On price | The nearest strong level above and below from our recorded liquidation map, with **Broke up / Broke down** and **Rejected** markers. 40 coins, history since August 2026. | Collecting data |

How to read them:

* **Volatility Ahead** — "big move expected" means expect range expansion (breakouts, wider stops); "quiet expected" means expect a range. A value appears only once the hourly model has written it, and it lasts for its 12-candle horizon.
* **Smart Money Flow** — trader classes are set from the 3 previous days only. It is context, not a copy or entry signal.
* **Positioning Heat** — above +2 = longs crowded and paying a lot, below −2 = shorts crowded. Extremes can last; it is not a reversal signal on its own.
* **Liquidity Sweep** and **Session Levels** — show where stops sat and where the session's fair value and yesterday's extremes are. On their own they did not predict the next move.
* **Crowding Risk** — risk of a squeeze, not a direction. Fading the crowd worked in one period and lost in the next.
* **Order Flow Delta** — who was aggressive, and where that aggression did not move price.
* **Liquidation Levels** — price reaches these levels more often than random levels at the same distance; whether it bounces or breaks there is still being measured.

<figure><img src=".gitbook/assets/shot-chart-indicators-v2-gallery.jpg" alt="Formion indicators gallery: Liquidity Sweep, Session Levels and Crowding Risk cards with their Context signal status"><figcaption><p>The new cards in the gallery, each with its measured status.</p></figcaption></figure>

<figure><img src=".gitbook/assets/shot-chart-indicators-v2-price.jpg" alt="BTC 1h with Session Levels (daily VWAP, ±1σ band, ±2σ lines, prior-day and prior-week high and low) and Liquidity Sweep markers Low swept and High swept"><figcaption><p>BTC 1h: Session Levels (VWAP with bands, prior-day and prior-week high / low) and Liquidity Sweep markers.</p></figcaption></figure>

<figure><img src=".gitbook/assets/shot-chart-indicators-v2-lower.jpg" alt="ETH 1h with Order Flow Delta and Crowding Risk in two lower panes, dashed ±1.5 levels"><figcaption><p>ETH 1h: Order Flow Delta (aggressive buy minus sell per candle) and Crowding Risk with its ±1.5 levels.</p></figcaption></figure>

<figure><img src=".gitbook/assets/shot-chart-indicators-v2-liq.jpg" alt="SOL 1h with Liquidation Levels: strong level above in red, below in green, and Rejected markers"><figcaption><p>SOL 1h: Liquidation Levels — the nearest strong level above and below, with Rejected and break markers.</p></figcaption></figure>

### How we measured them

Every ready-made indicator was measured before its status was set (17 November 2026):

* 20 crypto perpetuals, 1h candles, October 2025 → October 2026 (Pulse indicators: BTC, ETH, SOL, HYPE).
* The rules were written down before any result, then checked on a first period and once on a later period the search never saw.
* Results are after trading costs, with confidence intervals, a correction for testing many rules, and split by long / short, market phase and coin group.
* None passed: the best rules in the first period turned negative in the later one. That is why they say **Context signal** and not **Verified**.
* The measurement keeps running on every new day; a status changes only when new data proves it.

<figure><img src=".gitbook/assets/shot-chart-indicators-presets.jpg" alt="ETH 4h with Market Bias day bands, Positioning Heat, Pulse Consensus and Rotation Meter in lower panes"><figcaption><p>ETH 4h: Market Bias bands behind the candles, then Positioning Heat (amber columns = crowded funding), Pulse Consensus and Rotation Meter.</p></figcaption></figure>

## Market Bias layer

**Market Bias** is a button in the tools row (and a card in the gallery). It is off by default, works on every plan and shows **one market-wide state per day — the same on every chart**, because it reads the whole market, not the coin you are looking at.

* Translucent **day bands** behind the candles: 🟢 green = **Long bias**, 🔴 red = **Short bias**, 🟡 amber = **Transition** (detectors disagree or turning), grey = **Range**.
* Data: Formion's live market bias — 5 detectors on an index of 20 large alts plus BTC.
* The **ⓘ** button opens a card with the current state, how many detectors agree (for example **5/5**), since which day it holds, and the note *"Market-wide context from 20 large alts. Lags turns by ~1–2 weeks. Not an entry signal."*
* The optional strip **Alt index vs BTC** (off by default) shows the alt index and BTC, both set to 100 on the first visible day, for the last ~90 days. It is not drawn on phones or in a very low price pane, so the candles stay readable.
* A **Stale** tag appears when the data is older than 12 hours.

Status: **Context signal**. It confirms a trend after it started and lags turns by about 1–2 weeks; it has no levels and no buy / sell markers.

<figure><img src=".gitbook/assets/shot-chart-indicators-bias-card.jpg" alt="Market Bias card: state Short bias, detectors agreeing 5/5, since 2026-10-21, colour legend and the Alt index vs BTC switch"><figcaption><p>The ⓘ card: current state, detectors agreeing, since when, the colours and the Alt index vs BTC switch.</p></figcaption></figure>

## Pulse indicators

The gallery has its own section **Pulse · Followed traders**. These indicators draw what the traders followed in [Formion Pulse](pulse.md) actually called on this coin — and how it ended. **Pulse Consensus**, **Pulse Levels** and **Pulse Activity** are **Context signal** (measured on BTC, ETH, SOL and HYPE: they show attention and where traders placed their levels, but did not predict the next move, and price did not reach their zones more often than other levels). **Pulse Trader**, **Pulse Pending Setups** and **Pulse Outcomes** show single traders and stay **Collecting data**.

| Indicator | Where | What it shows |
| --- | --- | --- |
| **Pulse Consensus** | Lower pane | Net long − short (%) of active calls on this coin. One vote per trader, weighted by his win rate on **his own** closed plans known at that candle (only traders with at least 5 closed plans count). Optional **Top traders line (N)** — a second violet line with only the N heaviest traders — and **Markers on flip** where the consensus crosses 0. |
| **Pulse Trader** | On price | **One** trader on this coin: markers where his entry actually filled, his entry / stop / targets while his plan is active, how each plan ended (**Target hit**, **Stop hit**, **His exit**, with % on his plan) and a corner table with his closed plans and plan outcome. Under 5 closed plans the table says *Collecting data*. |
| **Pulse Levels** | On price | Where traders' own levels cluster: **Entry** zones (cyan), **Stop** zones (red — where their stop liquidity sits) and **Target** zones (green), with the number of traders in each zone. Only active plans count. |
| **Pulse Pending Setups** | On price | Setups still waiting for their trigger: a dashed line at his trigger price with *@handle long · waits*. The line ends when it fills, is cancelled or expires (at most 30 days). Not trades, not signals. |
| **Pulse Activity** | Lower pane | Attention on this coin: green columns = new long calls per candle, red columns = new short calls, violet line = traders with an active call. Not a direction signal. |
| **Pulse Outcomes** | On price | Every closed plan at the candle it closed — **Target hit** (green), **Stop hit** (red) or **His exit** (violet) — with *@handle +x.x %* on his plan. The original post is linked in his [trader profile](pulse-trader-profile.md). |

The rules are the same as everywhere in Pulse:

* **Only the trader's own levels.** Nothing is drawn where he gave no stop or target — we never invent one.
* **The clock starts at activation**, when his entry price actually traded — not when he posted.
* A call stays active until his own exit, at most for his typical hold (the median of his earlier closed plans).
* **Public posts only** — X, YouTube and public Telegram channels.

<figure><img src=".gitbook/assets/shot-chart-indicators-pulse-gallery.jpg" alt="Pulse section of the gallery: Pulse Consensus, Pulse Trader, Pulse Levels, Pulse Pending Setups, Pulse Activity and Pulse Outcomes, all Collecting data"><figcaption><p>The Pulse section of the gallery — six indicators built only from followed traders' own public calls.</p></figcaption></figure>

### Pulse settings

The Pulse indicators share one set of settings in **Settings → Inputs**, saved on your account. Each indicator shows the rows that apply to it — Pulse Trader, for example, has a single **Trader** picker instead of the trader list:

| Setting | What it does |
| --- | --- |
| **Traders** | All followed traders, or a picked list — each with avatar, @handle, calls on this coin, closed plans and measured style. Pulse Trader has a single **Trader** picker (empty = the trader with the most public calls on this coin). |
| **Sources** | X / YouTube / Telegram. |
| **Public posts only** | Always on (locked). |
| **Trader style** | Scalper / intraday / day trader / swing / position — measured from his own closed trades. Unmeasured traders drop out while a style is picked. |
| **Min closed plans** | His closed plans known at that candle. |
| **Weighting** | Win rate on his plans, or equal (Pulse Consensus). |
| **Include pending setups** | Off = the clock starts at his trigger fill; on = setups count from the post, shown as pending. |
| **Include projections** | Price targets that are not trades — off by default, labelled when on. |
| **Lookback (days)** | Only calls posted in the last N days; 0 = all. |
| **Display** | Show markers / levels / labels. |
| **Hide levels farther than %** | Pulse Trader, Pulse Levels and Pulse Pending Setups. Default 50 %. A level farther from the price than that is not drawn, so the candles stay readable; Pulse Trader lists it in its table as *His target (off chart)* with the price. Nothing is removed from the data. |

<figure><img src=".gitbook/assets/shot-chart-indicators-pulse-inputs.jpg" alt="Pulse Trader settings, Inputs tab: Trader @CrypNuevo, sources X, YouTube, Telegram, public posts only, hide levels farther than 50 %, display switches, pending setups, projections, lookback"><figcaption><p>Pulse Trader → Settings → Inputs: the trader picker, sources, display and calls options.</p></figcaption></figure>

A coin with no calls shows an empty state with an icon in the legend — not an error. You can also ask FORA in words, for example *"follow only CrypNuevo on the chart"*.

## Indicator styles

Your own indicators — Pine, TS, the ones FORA builds — and the Formion indicators can draw in the same looks traders know from Pine charts:

* **Plot types:** line, step line, area, histogram, columns, circles, cross — width 1–6, solid, dashed or dotted, with transparency.
* **A colour per candle** — for example a histogram green above 0 and red below.
* **hline** levels with a line style, and **fills** between two plots.
* **Background per candle** (`bgcolor`) in the indicator's own pane — or **on the price chart** (`force_overlay` in Pine, `onPrice` in TS).
* **Candle colours** (`barcolor`) — recolours the price candles.
* **Own candles** (`plotcandle` / `plotbar`) — for example CVD candles.
* **Labels, lines and boxes** (up to 500 of each) and a **table** in a chart corner (up to 12 × 6) — from TS.

Colours follow the theme by default (formion, dark, light…). A colour that would vanish on the background is swapped for a readable one.

<figure><img src=".gitbook/assets/shot-chart-indicators-style.jpg" alt="Settings, Style tab: plot type, colour, width and line style for each plot of Positioning Heat"><figcaption><p>Settings → Style: change the type, colour, width and line style of every plot — no code.</p></figcaption></figure>

## Indicator settings

Every custom indicator has a chip in the **legend** at the bottom left of the price chart — colour mark, name and a live value (green ↑ / red ↓). On Swift the legend sits behind one chip, **Indicator styles**. The **⋯** menu on a chip has:

* **Settings: inputs, style, placement** — the window below;
* **Move to: price chart (own scale)** — or back to its own pane;
* **Highlight on price chart…**;
* **Hide from the chart**.

<figure><img src=".gitbook/assets/shot-chart-indicators-menu.jpg" alt="Legend chip menu: Settings, Create alert, Create bot from this indicator, Move to price chart, Highlight on price chart, Hide from the chart"><figcaption><p>The ⋯ menu on a legend chip.</p></figcaption></figure>

**Settings** opens a window with four tabs. Your choices are saved per indicator on your account.

| Tab | What you set |
| --- | --- |
| **Inputs** | Every input the indicator declares: numbers with min / max / step, a choice from a list, on / off switches, multi-choice and — for Pulse — the trader pickers. **Apply** recomputes the indicator at once; **Reset to defaults** restores the declared values. |
| **Style** | Per plot: type, colour, width, line style, show / hide. |
| **Placement** | As the script says, **Price chart** or **Own pane**. On the price chart it gets its own left scale or no scale, so the candles are never squashed. Pane height. |
| **Highlight** | **Highlight on price chart**: paint the price chart green while a plot is above X and red while below Y, with a strength — no code. |

<figure><img src=".gitbook/assets/shot-chart-indicators-highlight.jpg" alt="Settings, Highlight tab: Highlight on price chart switch, plot choice, Green above and Red below levels, strength"><figcaption><p>Settings → Highlight: paint the price chart green above a level and red below another, with the strength you choose.</p></figcaption></figure>

## Alerts and bots from an indicator

Every indicator on the chart can send you an alert or run a bot — Formion indicators (Pulse Trader, Pulse Consensus …), your Pine scripts and your TS / FORA indicators. Open the ⋯ menu on its legend chip (or the bell in its Settings).

### Create alert

<figure><img src=".gitbook/assets/shot-chart-indicators-alert.jpg" alt="Create alert on Pulse Consensus: condition Net long − short % turns positive, trigger every time it becomes true, channels in-app, Telegram and web push, and the server preview of how often it would have fired"><figcaption><p>Create alert: a condition on one plot, the trigger, the channels and the server's honest preview.</p></figcaption></figure>

1. **Condition** — pick one of the indicator's plots and what should happen:
   * crosses up / down / crosses a value or another plot, is above / below;
   * turns positive / negative, changes sign, changes colour;
   * a marker appears (for example Pulse Trader **Long (his entry filled)**, **Target hit**, **Stop hit**; Pulse Consensus **Consensus flips long**);
   * a background turns on or is on;
   * a new value appears (for example **Any pending setup** = a new pending setup of a followed trader on this coin).
2. **Trigger** — **Every time it becomes true**, **Once per bar close** or **Only once**.
3. **Channels** — **In-app** (toast and sound), **Telegram** (@formiontradingbot, your linked chat) and **Web push** (one click enables this browser).

* The alert is judged on the server at every **candle close** — never on a forming candle, so it does not repaint, and it works with the tab closed.
* Before you save, the server shows how often it **would have fired** on the last closed candles — past behaviour, not a forecast.
* It counts against your active alerts (Free 3, Pro 100, Institutional unlimited). Pause or delete it in [Alerts](alerts.md).
* FORA can set it from a sentence: "alert me when Pulse Trader shows a long on BTC 1h".

### Create bot from this indicator

<figure><img src=".gitbook/assets/shot-chart-indicators-bot.jpg" alt="Create bot from Pulse Trader: long and short entries are his fills, exits are his exit, stop and target are his own levels, risk per trade left for the user"><figcaption><p>A bot from Pulse Trader: his fills, his stop, target and exit — the risk per trade is yours to set.</p></figcaption></figure>

* **Entries and exits** use the same conditions as alerts (long entry, short entry, close long, close short).
* **Stop loss, take profit and size come only from you**: % from entry, × ATR(14), a price from one of the indicator's plots, or none; risk % per trade.
* **Pulse Trader** is pre-filled with HIS fills and HIS stop, target and exit — never levels of ours.
* The bot starts on **paper** (no real orders) on the chart's symbol and timeframe.
* **Run backtest**: up to 5,000 candles, commission and slippage, an in-sample / out-of-sample split and stress tests. The result says **Keep refining** (it loses on the unseen part after costs) or **Collecting data** (too few trades, or positive — the paper bot on new candles decides).
* Live trading is switched on later on the [Bots](bots.md) page, within your plan's live-bot limit and only after you confirm.

## Build your own: Indicator Lab, FORA and ctx data

Indicators you write or FORA builds for you can read the same Formion data as the presets. A TS indicator is a function `indicator(candles, inputs, ctx)` that returns plots; every `ctx` call is aligned to each candle's close (no look-ahead). Test any indicator against random entries in **Indicator Lab** (**app.formion.ai/my-indicators**).

### Formion data sources

| Call | What it returns |
| --- | --- |
| `ctx.swarm(mode, opts)` | Swarm trade calls on this symbol. Modes: `net` (FRS-weighted long − short of open calls, −1…+1), `count` (open calls), `top` (like `net`, only authors with FRS ≥ `minFrs`, default 300, and ≥ `minCalls`, default 10), `signal` (+1 / −1 at the candle a qualifying call was posted), `level` (the author's own `entry` / `stop` / `target` of the newest open call via `field`; empty when he gave none). `ai`: 1 everyone (default), 0 members only, 2 Formion AI only. A call counts from its post time; FRS is recomputed per day only from calls graded before that day. |
| `ctx.pe('move')` / `ctx.pe('label')` | Volatility Ahead: `move` = odds 0…1 that price leaves ±1.5 ATR within 12 candles; `label` = +1 big move expected, −1 quiet expected, 0 undecided. BTC and gold (XAU) only. |
| `ctx.calls('*', { field: 'consensus' })` | Pulse Consensus, −1…+1 (`count` = active traders, `weight` = summed weight). The same filters as the Pulse settings (`traders`, `src`, `style`, `minClosed`, `weight`, `pending`, `proj`, `lookback`). |
| `ctx.calls('<handle>', { field })` | One followed trader's own calls: `signal` (+1 / −1 at a new call), `side`, `entry`, `sl`, `tp`, `tp2` (his levels while his call is active, empty when he gave none), `exit`. |

The other sources — `ctx.hl(…)`, `ctx.market(…)`, `ctx.funding()`, `ctx.oi()`, `ctx.bias()`, `ctx.regime(…)` — are explained by FORA when you ask for an indicator.

Example — the Swarm top-author stance as a coloured column histogram:

```js
function indicator(candles, inputs, ctx) {
  var s = ctx.swarm("top", { minFrs: 300, minCalls: 10 });
  return { overlay: false, plots: [
    { kind: "columns", title: "Swarm top net", data: s,
      colors: s.map(function (v) { return isNaN(v) ? null : (v >= 0 ? "up" : "down"); }) },
    { kind: "hline", title: "Zero", color: "muted", style: "dotted", data: s.map(function () { return 0; }) }
  ] };
}
```

### Plot styles in TS

* `kind`: `line`, `step`, `area`, `histogram`, `columns`, `circles`, `cross`, `hline`, `marker`, `fill`, `bgcolor`, `barcolor`, `candle`, `bar` (give `open` / `high` / `low` / `close` arrays for own candles).
* Every plot may carry `colors: […]` (one colour per candle, `null` = none), `width` 1–6, `style` `"solid"` / `"dashed"` / `"dotted"`, `base` (area / columns baseline) and `onPrice: true` (draw this plot or background on the price chart).
* Colours: `#rrggbb`, `#rrggbbaa`, `rgba()`, or theme tokens `up`, `down`, `accent`, `violet`, `amber`, `muted`, `text` — add `@0.2` for 20 % opacity (`"up@0.15"`). Prefer tokens: they look right in every theme.
* Shorthands next to `plots`: `bg: [{ color: "up@0.12", data: [1/0 per candle], onPrice: true }]` and `barColors: […]`.
* Drawings: `labels: [{ t, price, text, color, style }]`, `lines: [{ t1, p1, t2, p2, color, width, style, extend }]`, `boxes: [{ t1, t2, top, bottom, color, border, text }]`, `table: { position: "top_right", rows: [[{ text, color, bg, bold }]] }` (up to 12 × 6). `t` is the candle time in seconds.
* `pane: { height: 48–600 }` sets the pane height.
* Inputs for the **Inputs** tab: a comment line `// formion:input len {"type":"int","title":"Length","default":24,"min":2,"max":500}` (types `int`, `float`, `bool`, `select`, `multi`, `traders`, `trader`), read as `inputs.len`.

Example — colour the price chart green while a ratio is above 0.3:

```js
return { overlay: false,
  plots: [{ kind: "line", title: "Ratio", data: r }],
  bg: [{ color: "up@0.12", data: r.map(function (v) { return v > 0.3 ? 1 : 0; }), onPrice: true }] };
```

### Plot styles in Pine

The Pine subset supports the same looks:

```pine
plot(d, "Hist", color = d > 0 ? color.green : color.red, style=plot.style_histogram)
plot(d, "Cols", color = color.new(color.green, 20), style=plot.style_columns, histbase=0)
plot(m, "Step", color=color.orange, style=plot.style_stepline, linewidth=2, linestyle=plot.linestyle_dashed)
hline(0, "Zero", color=color.gray, linestyle=hline.style_dotted)
bgcolor(d > 3 ? color.new(color.green, 85) : na, force_overlay=true)
barcolor(d > 2 ? color.lime : na)
plotcandle(open, high, low, close, "Own candles", color = close > open ? color.teal : color.maroon)
```

Also supported: `plot.style_area`, `plot.style_circles`, `plot.style_cross`, `plot.linestyle_dotted`, `color.new(c, transparency)`, `color.rgb(r, g, b, t)`, colour variables, `plotbar`, and `na` as a gap. Pine `input.int` / `input.float` / `input.bool` fields show up in the **Inputs** tab with their titles and min / max / step.


### Drawings in Pine — labels, lines, boxes, tables

Pine scripts can now draw on the chart, the same as TS indicators, on both engines:

* `label.new`, `line.new`, `box.new`, `table.new` + `table.cell`, `linefill.new` (a zone between two levels).
* Change and remove them: `label.set_*`, `line.set_*`, `box.set_*`, `*.delete`, `*.get_*`, `chart.point`.
* Script logic: `var`, `:=`, `+=`, `if / else if / else`, `switch`, `for` loops, your own functions (`f(x) => …`), arrays (`array.new_line()`, `push`, `shift`, `get`, `size` …).
* Positions: `xloc.bar_index` or `xloc.bar_time`, `yloc.abovebar` / `belowbar`, text with `str.tostring` / `str.format`.
* Pine limits are kept: `max_labels_count` / `max_lines_count` / `max_boxes_count` (default 50, at most 500 each — the oldest goes first), a table shows at most 12 rows × 6 columns.

```pine
//@version=5
indicator("Pivot labels", overlay=true, max_labels_count=100)
ph = ta.pivothigh(high, 5, 5)
var line last = na
if not na(ph)
    label.new(bar_index - 5, ph, "PH " + str.tostring(ph, "#.##"), style=label.style_label_down)
    line.delete(last)
    last := line.new(bar_index - 5, ph, bar_index, ph, extend=extend.right, style=line.style_dashed)
var table t = table.new(position.top_right, 2, 1)
if barstate.islast
    table.cell(t, 0, 0, "Close")
    table.cell(t, 1, 0, str.tostring(close, format.mintick))
```

**Higher timeframe:** `request.security(syminfo.tickerid, "D", close)` works for the same symbol and a higher timeframe (minutes, `D`, `W`, `M`). It uses only **closed** higher-timeframe candles, so a value never comes from the future; the still-forming day / week is not used.

{% hint style="warning" %}
Not supported yet: user types (`type`, `method`), `import` of libraries, `while` loops, `matrix` / `map`, and `request.security` on another symbol or a lower timeframe. The editor names the line it cannot read. A very heavy script runs on the most recent candles only, so the chart stays fast.
{% endhint %}

Related: [Chart Pro](chart-pro.md) · [Formion Pulse](pulse.md) · [Swarm](swarm.md) · [FORA](fora.md) · [Strategy Lab](strategy-lab.md)
