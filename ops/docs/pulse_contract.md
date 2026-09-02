# Ops pulse contract (greed_ops_pulse/v1)

**Public repo:** `KNB1080p/Greed_V3_Ops` · branch `main`

Cursor automation writes `ops/runtime/pulse.json` and pushes.

GREED_V3 polls:

`https://raw.githubusercontent.com/KNB1080p/Greed_V3_Ops/main/ops/runtime/pulse.json`

## pulse.json

```json
{
  "schema": "greed_ops_pulse/v1",
  "pulseId": "2026-09-02T12:45:00Z",
  "writtenUtc": "2026-09-02T12:45:00Z",
  "source": "cursor_automation",
  "message": "handshake ok"
}
```

`pulseId` must change each run (UTC ISO-8601).

## Loop guard (automation)

- Commit starts with `ops: pulse` → noop (own commit).
- Commit starts with `test:` → always run full handshake.

## Bot ack

`Automation_GREED_V3_{Symbol}_{TF}_{date}_{time}_{RunId}.csv` in cBot data root.

Columns: `utc,pulseId,schema,source,message,botVersion,equity,ack`
