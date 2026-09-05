# ChatGPT Apps / Plugins Directory — LinkedIn Ads MCP (Kiin)

**Product:** same hosted MCP only — `https://mcp.kiin.co`  
**Display name:** LinkedIn Ads MCP — powered by Kiin  
**Preference:** point ChatGPT at the hosted remote MCP (Universal URL). Build a full Apps SDK UI wrapper only if OpenAI review requires interactive UI beyond tools.

## Paths

| Path | Who | Notes |
| --- | --- | --- |
| Custom connector (Developer Mode) | Personal / Team testing | Paste MCP URL in ChatGPT Plugins / Developer Mode — not public distribution |
| Apps SDK → App Directory + Codex Plugins | Public listing | https://developers.openai.com/apps-sdk/deploy/submission · https://developers.openai.com/plugins/deploy/submission |

## Public listing requirements (research summary)

From OpenAI Apps SDK / plugin submission docs:

1. MCP on a public HTTPS domain (ours: `https://mcp.kiin.co`)
2. Choose **Universal** MCP URL (one endpoint for all users) — not per-tenant template
3. OAuth configured; provide reviewer demo credentials
4. Domain verification if portal challenges: host token at `/.well-known/openai-apps-challenge` on `mcp.kiin.co` or parent
5. Define CSP for any UI fetches (required for Apps SDK UI submission)
6. Complete form: name, logo, description, company, privacy URL, MCP/tool info, screenshots, test prompts, localization
7. Scan Tools → fix metadata → Submit for review → after approval, **Publish** from Platform Dashboard
8. Approved app also feeds Codex plugin directory

## Listing metadata (draft)

| Field | Draft |
| --- | --- |
| App / plugin name | LinkedIn Ads MCP — powered by Kiin |
| Short description | Read and write LinkedIn Ads (preview-then-confirm) via Kiin MCP |
| Long description | Manage LinkedIn advertising from ChatGPT: performance, budgets, creatives, targeting, saved audiences, and DRAFT campaigns. Writes always preview then confirm. Sign in with OAuth — no pasted API keys. |
| MCP Server URL | https://mcp.kiin.co |
| Auth | OAuth 2.0 (DCR) |
| Logo | https://raw.githubusercontent.com/Adriman2/kiin-cursor-plugin/main/assets/logo.png |
| Company | Kiin Intelligence · https://kiin.co |
| Privacy | https://kiin.co/privacy-policy |
| Terms | https://web.kiin.co/terms |
| Support | adrian@kiin.co |
| Homepage / docs | https://mcp.kiin.co/start |
| Example prompts | "Top LinkedIn campaigns by CPL last 30 days"; "Preview pausing campaign X"; "Draft a new LinkedIn campaign for …" |

## Minimal wrapper policy

- **Default:** no new server — Universal URL to existing Kiin MCP  
- **If Apps SDK requires UI:** add a thin Apps SDK project later that still calls `https://mcp.kiin.co` (not a fork)  
- **Do not** ship a second LinkedIn Ads backend

## Pre-submit checklist

- [ ] Developer Mode smoke test: connect `https://mcp.kiin.co`, OAuth OK, sample read + write preview  
- [ ] Domain verification token on mcp.kiin.co if prompted  
- [ ] Tool titles / annotations clean for Scan Tools  
- [ ] Screenshots + test prompts prepared  
- [ ] Reviewer LinkedIn Ads account credentials ready  
- [ ] Confirm OpenAI OAuth redirect URIs allowlisted on Kiin if static registration is required  

## Apply steps (human)

1. OpenAI Platform Dashboard → Apps SDK / plugin submission  
2. Universal MCP URL `https://mcp.kiin.co`  
3. Fill metadata from table above  
4. Scan tools → submit → wait for Case ID email  
5. After approval, Publish for App Directory + Codex plugin listing  

References:

- https://developers.openai.com/apps-sdk/deploy/submission  
- https://developers.openai.com/plugins/deploy/submission  
