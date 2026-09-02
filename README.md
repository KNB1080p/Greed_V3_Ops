# Greed_V3_Ops

Public ops channel for the **GREED_V3** cTrader bot. Private strategy code lives in [Greed_V3](https://github.com/KNB1080p/Greed_V3).

## Bot read URL

```
https://raw.githubusercontent.com/KNB1080p/Greed_V3_Ops/main/ops/runtime/pulse.json
```

GREED_V3 polls this URL (v3.18.6+) and acks new pulses in `Automation_*.csv` on the cBot data folder.

## Layout

```
ops/
  runtime/pulse.json       ← Cursor automation writes; bot reads
  logs/automation_agent.csv ← automation audit trail
```

## Contract

See `ops/docs/pulse_contract.md`.
