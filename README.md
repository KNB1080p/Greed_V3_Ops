# Greed_V3_Ops

Public ops channel for the **GREED_V3** cTrader bot. Private strategy code lives in [Greed_V3](https://github.com/KNB1080p/Greed_V3).

**New VPS / Cursor agent:** start at [`ops/docs/VPS_CURSOR_MIGRATION.md`](ops/docs/VPS_CURSOR_MIGRATION.md) (points to the full handoff in `Greed_V3`).

## Bot URLs

| Feed | URL |
|------|-----|
| Ops pulse | `https://raw.githubusercontent.com/KNB1080p/Greed_V3_Ops/main/ops/runtime/pulse.json` |
| News blackout | `https://raw.githubusercontent.com/KNB1080p/Greed_V3_Ops/main/ops/runtime/news.json` |

## Layout

```
ops/
  calendar/ff_calendar.csv   ← weekly ForexFactory CSV (UTC times)
  runtime/pulse.json         ← heartbeat / test ack
  runtime/news.json          ← tiered blackout windows (agent writes)
  logs/automation_agent.csv
  docs/
    VPS_CURSOR_MIGRATION.md     ← START HERE for new VPS Cursor
    pulse_contract.md
    news_contract.md
    automation_instructions.md  ← paste into Cursor automation
```

## Contracts

- VPS handoff: `ops/docs/VPS_CURSOR_MIGRATION.md`
- Pulse: `ops/docs/pulse_contract.md`
- News: `ops/docs/news_contract.md`
- Automation: `ops/docs/automation_instructions.md`
