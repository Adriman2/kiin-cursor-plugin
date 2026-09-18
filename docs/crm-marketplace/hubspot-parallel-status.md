# HubSpot parallel track — status (2026-09-18)

## Confirmed live

| Item | Status |
|------|--------|
| Railway `HUBSPOT_CLIENT_ID` / `HUBSPOT_CLIENT_SECRET` / `HUBSPOT_REDIRECT_URI` | Present on `kiin-mcp` production (values not readable via MCP) |
| Callback path | `https://mcp.kiin.co/auth/hubspot/callback` (handler responds; 400 without valid state) |
| Connect invite page shape | `/connect/hubspot/:token` returns branded invalid-link page for bad tokens (route live) |
| MCP | `connect_hubspot`, `create_hubspot_connect_link`, `sync_hubspot_now`, `list_crm_connections` |
| CRM connections on Kira session | **0** — need customer installs for marketplace gate |

## Docs drift to fix with Phil/Adrian

- `docs/HUBSPOT.md` example `HUBSPOT_REDIRECT_URI` still shows `*.up.railway.app`. Production should use `https://mcp.kiin.co/auth/hubspot/callback` (and that URI must be registered on the HubSpot app).
- Same doc embeds an example client id/secret. Treat as **stale doc risk**: confirm HubSpot developer portal public app ID equals Railway `HUBSPOT_CLIENT_ID` without pasting secrets into chat. Prefer scrubbing secrets from the markdown.

## Shareable install flow (for hunting ≥3 installs)

1. Agency/admin with Kiin access runs MCP `create_hubspot_connect_link` for the target LinkedIn Ads `account` (optional `expires_in_days`, default 14).
2. Tool returns `https://mcp.kiin.co/connect/hubspot/<token>`.
3. Client opens link → branded page → HubSpot OAuth → success; invite marked used.
4. Verify with `list_crm_connections` / sync.

Minting a live shareable link was blocked pending human approval in this session. When Adrian wants hunt links, approve one mint per prospect account (start with willing customers, not cold spam).

## Tech Partner / Marketplace

- Signup + Super admin: **unknown** without HubSpot partner portal access (Adrian/Phil).
- Framing: CRM sync for LinkedIn Ads attribution — **not** an Agent MCP connector dump of `mcp.kiin.co`.
- Hard gate remains ≥3 unaffiliated production installs + HubSpot-specific setup guide URL + demo video.
