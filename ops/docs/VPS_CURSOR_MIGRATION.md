# VPS Cursor — START HERE (Greed_V3_Ops)

You are on the **public ops** repo for GREED_V3. Full migration / product handoff lives in the private bot repo:

**Canonical doc:** [`Greed_V3` → `docs/VPS_CURSOR_MIGRATION.md`](https://github.com/KNB1080p/Greed_V3/blob/automation/docs/VPS_CURSOR_MIGRATION.md)

If that file is cloned locally:

`..\GREED_V3\docs\VPS_CURSOR_MIGRATION.md`

---

## Your job in this repo

1. Keep `ops/runtime/pulse.json` and `ops/runtime/news.json` fresh for the bot.
2. Follow **`ops/docs/automation_instructions.md`** for Cursor Automations.
3. Obey loop guards: never react to your own `ops: pulse` / `ops: news` commits.
4. Branch is always **`main`**.

## Clone both repos (VPS)

```powershell
$robots = Join-Path $env:USERPROFILE "Documents\cAlgo\Sources\Robots"
New-Item -ItemType Directory -Force -Path $robots | Out-Null
Set-Location $robots
git clone https://github.com/KNB1080p/Greed_V3.git GREED_V3
git -C GREED_V3 checkout automation
git clone https://github.com/KNB1080p/Greed_V3_Ops.git Greed_V3_Ops
```

## Quick links in this repo

| Doc | Purpose |
|-----|---------|
| `ops/docs/automation_instructions.md` | Paste into Cursor Automation |
| `ops/docs/pulse_contract.md` | pulse.json schema + ack |
| `ops/docs/news_contract.md` | news.json + tiers |
| `README.md` | Feed URLs |

## Bot poll URLs

- Pulse: `https://raw.githubusercontent.com/KNB1080p/Greed_V3_Ops/main/ops/runtime/pulse.json`
- News: `https://raw.githubusercontent.com/KNB1080p/Greed_V3_Ops/main/ops/runtime/news.json`

**Automation product must target this public repo (`Greed_V3_Ops`), not private `Greed_V3`.**
