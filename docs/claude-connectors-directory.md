# Claude Connectors Directory — LinkedIn Ads MCP (Kiin)

**Product:** same hosted MCP only — `https://mcp.kiin.co`  
**Display name:** LinkedIn Ads MCP — powered by Kiin  
**Type:** Remote MCP server (Streamable HTTP + OAuth 2.0 DCR)

## Where to apply

- Portal: Claude.ai → Organization settings → Directory (Team or Enterprise; Owner / Directory permission)
- Docs: https://claude.com/docs/connectors/building/submission
- Checklist: https://claude.com/docs/connectors/building/review-criteria
- Escalations: mcp-review@anthropic.com
- Desktop MCPB (not our path): separate form — we submit **remote** only

Individual Claude plans cannot open the portal. Need Team/Enterprise org with Directory access.

## Listing copy (draft)

| Field | Draft |
| --- | --- |
| Server name (≤100) | LinkedIn Ads MCP — powered by Kiin |
| Tagline (≤55) | Read & write LinkedIn Ads from Claude |
| Description (≤2000) | Connect Claude to your LinkedIn Ads accounts via Kiin. Query campaigns, budgets, creatives, and CRM-linked revenue. On paid/trial, pause or enable ads, change budgets and targeting, manage creatives and saved audiences, and create campaigns as DRAFT. Every write is preview-then-confirm before LinkedIn accepts the change. OAuth sign-in — no API keys in chat. |
| Categories | Marketing, Advertising, Analytics (adjust to portal options) |
| Docs URL | https://mcp.kiin.co/start · https://github.com/Adriman2/kiin-cursor-plugin |
| Privacy policy | https://kiin.co/privacy-policy |
| Support | adrian@kiin.co (or support@kiin.co if preferred) |
| Icon | https://raw.githubusercontent.com/Adriman2/kiin-cursor-plugin/main/assets/logo.png |
| Company | Kiin Intelligence · https://kiin.co |
| MCP URL | https://mcp.kiin.co |
| Transport | Streamable HTTP |
| Auth | OAuth 2.0 + dynamic client registration; scope `mcp:tools` |
| Use cases | Performance analysis; budget/status changes; creative review; CRM attribution |
| Reads / writes | Both — writes gated, preview-then-confirm |
| Test account | Provide populated LinkedIn Ads + Kiin trial/paid reviewer account (Adrian) |

## OAuth notes for Claude

- Register redirect: `https://claude.ai/api/mcp/auth_callback`
- Claude Code may use loopback `http://localhost:<port>/…` — DCR should accept loopback if we want Code support
- Protected resource metadata live at `https://mcp.kiin.co/.well-known/oauth-protected-resource` (`resource`: `https://mcp.kiin.co/`)
- Prefer root URL `https://mcp.kiin.co` (matches resource metadata)

## Pre-submit checklist (server)

- [ ] Every tool has `title` + `readOnlyHint` or `destructiveHint`
- [ ] Read and write tools are separate (no catch-all method tool)
- [ ] Exercise all tools via MCP Inspector + Claude custom connector
- [ ] Reviewer test account fully populated
- [ ] Public docs / start page ready
- [ ] Confirm Claude OAuth callback is allowlisted in Kiin DCR / OAuth app settings if required
- [ ] No secrets in this plugin repo

## Apply steps (human)

1. Sign into Claude.ai on a Team/Enterprise org with Directory access  
2. Organization settings → Directory → submit remote MCP  
3. Connect `https://mcp.kiin.co`, complete OAuth, sync tools  
4. Paste listing copy above; upload logo; attach test credentials  
5. Acknowledge policy checkboxes; submit  
6. Track status in submissions dashboard  

**Do not invent a second MCP server.** Same endpoint as Cursor / Agent Plugins.
