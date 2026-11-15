# 🧩 Developer API

<figure><video src=".gitbook/assets/clip-devapi.mp4" title="Formion Data API: key, request, JSON response"></video><figcaption><p>Send your fom_live_… key as a Bearer token: /api/v1/meta confirms it, /api/v1/screener returns the Formion Screener (who is trending, how strong, since when) as JSON, with rate-limit headers in every response.</p></figcaption></figure>

The Formion Data API gives programmatic access to the same Formion Screener you see in the app — which markets are trending, in which direction, how strong, since when and in which phase — over a simple authenticated REST endpoint. It is designed for quants, bot builders and desks who want that trend context inside their own systems. It is market context, never an entry, stop or target.

> **Status:** available on request. Keys are issued manually by the Formion team. Self-serve personal API tokens are on the roadmap — the API access card in **Profile → License** shows *Coming soon*. Contact **support@formion.ai** to request a key.

## Authentication

Every request carries your API key as a bearer token:

```bash
curl "https://app.formion.ai/api/v1/screener?tf=1d&limit=25" \
  -H "Authorization: Bearer fom_live_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

- Keys look like `fom_live_…`. Treat them like a password — anyone with the key can call the API as you.
- The key is shown **once** when issued and stored only as a hash on our side. If you lose it, we revoke and re-issue — we cannot recover it.
- You can also pass the key as `?api_key=…` for quick testing, but the `Authorization` header is preferred.

If your key is missing, wrong or revoked you get:

```json
{ "ok": false, "error": "unauthorized", "hint": "Send a valid key as 'Authorization: Bearer fom_live_…'. Request access at support@formion.ai." }
```
with HTTP `401`.

## Rate limits

Each key has a per-minute budget set by the key's API tier (assigned when the key is issued):

| Tier | Requests / minute |
|---|---|
| Free | 60 |
| Pro | 600 |
| Institutional | 6 000 |

Every response includes standard headers so you can self-throttle:

```
X-RateLimit-Limit: 600
X-RateLimit-Remaining: 594
X-RateLimit-Reset: 1789200000     # unix seconds when the window resets
```

Over budget returns HTTP `429` with `{ "ok": false, "error": "rate_limited", "tier": "…" }` and a `Retry-After` header (seconds). Back off and retry.

## Versioning

All endpoints live under `/api/v1/`. Each response names its contract in `schema` (today `formion-screener-2026-11`). New fields may be **added** at any time; a field is removed or changes meaning only with a new `schema` value, announced in the [changelog](changelog.md) and in `/api/v1/meta`.

> **Changed November 2026:** `/api/v1/screener` now serves the Formion Screener. The old fields `score`, `win_probability`, `category`, `rsi_1d` and `tags` were removed. The old `minScore` parameter still works and is read as `minStrength`.

---

## Endpoints

### `GET /api/v1/meta`

Confirms your key works and lists what it can reach.

```bash
curl https://app.formion.ai/api/v1/meta -H "Authorization: Bearer fom_live_…"
```

```json
{
  "ok": true,
  "api_version": "v1",
  "key": { "tier": "pro", "rate_per_min": 600, "label": "Acme backtest bot" },
  "endpoints": [
    { "path": "/api/v1/meta", "method": "GET", "desc": "This key's tier + endpoint list." },
    {
      "path": "/api/v1/screener", "method": "GET",
      "desc": "Formion Screener: who is trending, how strong, since when and in which phase (trend context, never an entry, stop or target). Query: tf, limit, side, market, phase, minStrength.",
      "schema": "formion-screener-2026-11",
      "fields": { "symbol": "Market id (e.g. BTCUSDT, XAUUSD)", "…": "…" }
    }
  ],
  "docs": "https://docs.formion.ai/api",
  "support": "support@formion.ai"
}
```

### `GET /api/v1/screener`

The Formion Screener — the same engine that powers the app's [Screener](screener.md). Every row is one market on one timeframe that is in a trend right now, sorted by trend strength.

**Query parameters**

| Param | Default | Description |
|---|---|---|
| `tf` | `1d` | Timeframe: `5m`, `15m`, `1h`, `4h`, `1d` |
| `limit` | `100` | Rows to return (max 500) |
| `side` | `all` | `long` (uptrends), `short` (downtrends) or `all` |
| `market` | `all` | `crypto`, `metals`, `oil`, `stocks`, `indices`, `forex`, `agri` or `all` |
| `phase` | `all` | `fresh`, `running`, `pullback`, `exhausted` or `all` |
| `minStrength` | `0` | Only rows with trend strength ≥ this (0–100). `minScore` is accepted as an alias |

**Example**

```bash
curl "https://app.formion.ai/api/v1/screener?tf=4h&limit=1&minStrength=60" \
  -H "Authorization: Bearer fom_live_…"
```

```json
{
  "ok": true,
  "api_version": "v1",
  "tier": "pro",
  "schema": "formion-screener-2026-11",
  "timeframe": "4h",
  "scanned_at": 1794734897328,
  "rule_version": "trend-v1",
  "model_version": "v1.0",
  "count": 1,
  "total": 147,
  "data": [
    {
      "symbol": "KAVAUSDT",
      "display": "KAVA",
      "asset_class": "crypto",
      "market": "crypto",
      "venue": "bybit",
      "venue_name": "Bybit",
      "timeframe": "4h",
      "direction": "short",
      "trend_strength": 93,
      "phase": "exhausted",
      "trend_start": "2026-11-13T16:00:00.000Z",
      "bars_since_start": 10,
      "trend_age_ms": 149302364,
      "typical_duration_ms": 122400000,
      "momentum_percentile": 100,
      "mfe_pct": 63.171,
      "mae_pct": -1.015,
      "price": 0.03538,
      "change_24h": -48.0622,
      "price_at": 1794734880000,
      "market_closed": false
    }
  ]
}
```

**Field reference**

| Field | Meaning |
|---|---|
| `schema` | Contract name of this response (`formion-screener-2026-11`) |
| `scanned_at` | Unix ms of the engine snapshot (data can be up to a few minutes old) |
| `total` | Rows that matched your filters before `limit` |
| `symbol` / `display` | Market id (e.g. `BTCUSDT`, `XAUUSD`) / the ticker shown in the app |
| `asset_class` | `crypto`, `forex`, `stock`, `etf`, `index` or `commodity` |
| `market` | Group used by the `market` filter (`crypto`, `metals`, `oil`, `stocks`, `indices`, `forex`, `agri`) |
| `venue` / `venue_name` | Price source (`binance`, `bybit`, `hyperliquid`, `ctrader`) and its display name |
| `direction` | `long` (uptrend) or `short` (downtrend) |
| `trend_strength` | 0–100, how strong the trend is right now |
| `phase` | `fresh` (just started), `running`, `pullback` (moving against the trend for now) or `exhausted` (older than 1.5× its typical length) |
| `trend_start` | ISO time of the closed bar where the trend started |
| `bars_since_start` / `trend_age_ms` | Closed bars / milliseconds since the trend started |
| `typical_duration_ms` | Median length of this market's own past trends on this timeframe (`null` while collecting data) |
| `momentum_percentile` | 0–100, momentum rank within the same timeframe and direction |
| `mfe_pct` | Best move in the trend's direction since the start, in % (measured, not a target) |
| `mae_pct` | Worst move against the trend since the start, in % (0 or negative) |
| `price` / `change_24h` / `price_at` | Live price, 24 h change in %, and the time of that price (unix ms) |
| `market_closed` | `true` when the market's session is closed (stocks, forex, metals on weekends) |

If the engine is delayed, the endpoint answers HTTP `503` with `{ "ok": false, "error": "engine_unavailable" }` instead of serving old trend states. Retry after a minute.

How accurate the trend calls have been is shown in the Screener's **Track record** panel in the app (measured on new days, per timeframe).

These two endpoints (`/meta` and `/screener`) are the whole v1 API today. If you need other data, tell us what — there is no commitment to further endpoints yet.

---

## Good citizenship

- **Cache and poll sensibly.** The screener re-scans every few minutes; polling faster than that just burns your rate budget for identical data. Read `scanned_at` and skip if unchanged.
- **One key per system.** Don't share a key across clients — per-key metering is how we (and you) reason about usage.
- **Never ship a key to a browser or public repo.** If a key leaks, email us so we can revoke it and issue a new one.

## Getting a key

Email **support@formion.ai** with your use case and expected volume. We'll issue a key, set its tier, and help you get the first call working.
