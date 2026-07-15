# 🧩 Developer API

The Formion Data API gives programmatic access to the same signals you see in the app — the ranked screener, calibrated win-probabilities, and more — over a simple authenticated REST endpoint. It is designed for quants, bot builders and desks who want Formion's edge inside their own systems.

> **Status:** available on request. The API is billed separately from the app licence — contact **support@formion.ai** to get a key and discuss a plan.

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
{ "ok": false, "error": "unauthorized" }
```
with HTTP `401`.

## Rate limits

Each key has a per-minute budget by tier:

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

Over budget returns HTTP `429` with a `Retry-After` header (seconds). Back off and retry.

## Versioning

All endpoints live under `/api/v1/`. We treat the `v1` response shape as a stable contract — new fields may be **added**, but existing fields won't change meaning or disappear without a new version (`/api/v2/`). Build against `v1` with confidence.

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
    { "path": "/api/v1/screener", "method": "GET", "desc": "Ranked multi-market screener with Formion score + P(win)." }
  ]
}
```

### `GET /api/v1/screener`

The ranked multi-market screener — the same engine that powers the app's Screener tab.

**Query parameters**

| Param | Default | Description |
|---|---|---|
| `tf` | `1d` | Timeframe: `5m`, `15m`, `1h`, `4h`, `1d` |
| `limit` | `100` | Rows to return (max 500) |
| `minScore` | `0` | Only return rows with score ≥ this |

**Example**

```bash
curl "https://app.formion.ai/api/v1/screener?tf=4h&limit=5&minScore=60" \
  -H "Authorization: Bearer fom_live_…"
```

```json
{
  "ok": true,
  "api_version": "v1",
  "tier": "pro",
  "timeframe": "4h",
  "scanned_at": 1789199400000,
  "count": 5,
  "data": [
    {
      "symbol": "SOLUSDT",
      "asset_class": "crypto",
      "category": "bull-pullback",
      "direction": "long",
      "score": 74,
      "win_probability": 0.58,
      "rsi_1d": 61,
      "tags": ["at-bull-fvg", "bos-up-1d", "arsi-turn-up-4h"]
    }
  ]
}
```

**Field reference**

| Field | Meaning |
|---|---|
| `symbol` | Exchange pair or ticker |
| `asset_class` | `crypto`, `stock`, `index`, `commodity` |
| `category` | Setup class (`bull`, `bear-rally`, `sweep-confirmed`, …) |
| `direction` | `long`, `short`, or `null` |
| `score` | Composite Formion score, 0–100 |
| `win_probability` | Calibrated model probability the call is right at the timeframe's horizon, or `null` if the model hasn't cleared its accuracy bar |
| `rsi_1d` | Daily RSI(14) |
| `tags` | Structural + momentum tags (FVG, BoS/CHoCH, VWAP, Adaptive-RSI turns, …) |
| `scanned_at` | Unix ms of the underlying scan (data can be up to a few minutes old) |

More endpoints (trade history, patterns, order-book aggregates) are added on request as demand grows — tell us what you need.

---

## Good citizenship

- **Cache and poll sensibly.** The screener re-scans every few minutes; polling faster than that just burns your rate budget for identical data. Read `scanned_at` and skip if unchanged.
- **One key per system.** Don't share a key across clients — per-key metering is how we (and you) reason about usage.
- **Never ship a key to a browser or public repo.** If a key leaks, email us and we'll rotate it immediately.

## Getting a key

Email **support@formion.ai** with your use case and expected volume. We'll issue a key, set the right tier, and help you get the first call working.
