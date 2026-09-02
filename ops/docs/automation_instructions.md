# Cursor automation — Greed_V3_Ops

Repo: `KNB1080p/Greed_V3_Ops` · Branch: `main`

## Triggers

1. **GitHub push** to `main`
2. **Schedule:** daily 05:00 UTC

## Loop guards

| Commit prefix | Action |
|---------------|--------|
| `ops: pulse` | noop — own commit |
| `ops: news` | noop — own commit |
| `test:` | full pulse handshake |
| `test: news` | full news refresh only |
| push to `ops/calendar/*` | news refresh |

---

## News refresh (complete in under 60s)

1. `git pull origin main`
2. Read `ops/calendar/ff_calendar.csv`
3. For each row: Country EUR or USD; Impact High or Medium
4. Classify tier (see `ops/docs/news_contract.md`)
5. Parse Date (MM-DD-YYYY) + Time as **UTC** → ISO-8601
6. Compute blockStart/blockEnd per tier
7. Merge same-minute clusters (e.g. NFP + Unemployment + AHE)
8. Write `ops/runtime/news.json` with new `versionId` (UTC ISO)
9. Append `ops/logs/automation_agent.csv`: `utc,versionId,action,branch,windowCount`
10. `git add ops/runtime/news.json ops/logs/automation_agent.csv`
11. `git commit -m "ops: news <versionId>"`
12. `git push origin main`
13. Reply: `NEWS_OK versionId=… windows=N commit=<hash>`

---

## Pulse handshake (unchanged)

See `ops/docs/pulse_contract.md`. Loop guard on `ops: pulse`.
