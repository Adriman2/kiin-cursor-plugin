# Pipedrive — repo vs Railway (do not Send to review yet)

## Production (Railway + MCP)

- Env: `PIPEDRIVE_CLIENT_ID`, `PIPEDRIVE_CLIENT_SECRET` on `kiin-mcp` production
- HTTP: `/auth/pipedrive/authorize` and `/auth/pipedrive/callback` respond (400 without state)
- MCP tools exposed: `connect_pipedrive`, `create_pipedrive_connect_link`, `sync_pipedrive_now`

## GitHub `Adriman2/kiin-mcp` main (2026-09-18)

- `src/crm/` contains **only** `attio/` and `hubspot/` — **no** `pipedrive/` tree
- Docs: `docs/ATTIO.md` states “Pipedrive is **not** implemented in this repo”
- No `docs/PIPEDRIVE.md`

## Conclusion

Deployed surface and source-of-truth repo disagree. Before Pipedrive Marketplace “Send to review”: either land Pipedrive adapter + docs in `kiin-mcp` main, or document that production is ahead of main and reconcile the branch Phil ships from. Do not submit with docs that say “not implemented.”
