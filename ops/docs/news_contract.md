# Ops news contract (greed_ops_news/v1)

**Public repo:** `KNB1080p/Greed_V3_Ops` · branch `main`

Bot polls:

`https://raw.githubusercontent.com/KNB1080p/Greed_V3_Ops/main/ops/runtime/news.json`

## news.json

```json
{
  "schema": "greed_ops_news/v1",
  "versionId": "2026-09-02T12:00:00Z",
  "writtenUtc": "2026-09-02T12:00:00Z",
  "symbol": "EURUSD",
  "windows": [
    {
      "eventUtc": "2026-09-04T12:30:00Z",
      "blockStartUtc": "2026-09-04T11:45:00Z",
      "blockEndUtc": "2026-09-04T14:00:00Z",
      "tier": 1,
      "impact": "High",
      "currencies": ["USD"],
      "title": "Non-Farm Employment Change + ..."
    }
  ]
}
```

## Blackout tiers (agent computes blockStart/blockEnd)

| Tier | Before / After event | Events |
|------|---------------------|--------|
| 1 | -45 min / +90 min | NFP cluster, US CPI, FOMC/ECB rate + presser |
| 2 | -15 min / +45 min | ISM PMI, ADP, US Retail Sales, PCE, GDP, JOLTS, Claims |

**Skip:** Low, Holiday, Member Speaks, non-EUR/USD countries.

## Calendar source

`ops/calendar/ff_calendar.csv` — replace weekly (ForexFactory export). Times are **UTC**.

## Bot behavior

- Blocks **new** grid arms and adds only (existing baskets keep managing TP/SL).
- Fail-safe: pause new exposure if feed fetch/parse fails (`News pause on feed failure`).
