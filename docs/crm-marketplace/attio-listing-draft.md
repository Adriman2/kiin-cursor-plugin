# Attio App Store — listing draft (Kiin)

**App name (suggested):** Kiin LinkedIn Ads Sync  
**Developer account:** Kiin Intelligence (no “Attio”, no “dev/test” in name)  
**Publish:** https://build.attio.com → Publish app  
**Docs:** https://docs.attio.com/share/publishing-to-the-app-store · https://docs.attio.com/share/app-listings  
**Review:** ~1 week; no install minimum  

## OAuth (already live)

- Redirect: `https://mcp.kiin.co/auth/attio/callback`
- Also register localhost for dev: `http://localhost:8080/auth/attio/callback`
- Scopes: `record_permission:read`, `object_configuration:read` (+ optional `user_management:read`)
- Railway: `ATTIO_CLIENT_ID` / `ATTIO_CLIENT_SECRET` present
- MCP: `connect_attio`, `create_attio_connect_link`, `sync_attio_now`, `list_crm_connections`

## Overview (draft, 100–3000 chars)

Kiin connects Attio to LinkedIn Ads so you can see which companies and deals were influenced by your ads. After a one-time OAuth connect, Kiin syncs people, companies, and deals nightly and matches them to LinkedIn engagement for influenced-pipeline reporting inside Claude, Cursor, and other MCP clients.

Use Kiin when you already run LinkedIn Ads and keep pipeline in Attio. The integration is read-only on Attio: it does not create or edit records. Writes stay on the LinkedIn Ads side (preview-then-confirm) via the Kiin MCP.

## How It Works (draft)

1. Install / open Kiin and pick the LinkedIn Ads account to attribute.
2. Run connect Attio (or share a client-facing connect link) and authorize read access.
3. Kiin mirrors Attio companies, people, deals, and owners into its pipeline tables.
4. Nightly sync keeps the mirror fresh; admins can trigger an immediate sync.
5. Ask your AI client for influenced pipeline, deal coverage, and company-level LinkedIn exposure vs Attio deals.

Matching uses company names against LinkedIn company engagement. Attio has no HubSpot-style UTM fields, so contact attribution is unattributed while deal influence still comes from LinkedIn exposure before deal creation.

## Configure (draft)

1. Have a Kiin account with LinkedIn Ads connected (https://mcp.kiin.co/start).
2. In your AI client, call connect Attio for the account (or open a create_attio_connect_link invite).
3. Approve the Attio OAuth prompt (read scopes only).
4. Wait for the initial sync, or ask an admin to sync Attio now.
5. Confirm the connection under list CRM connections, then query pipeline / influenced reports.

Privacy: https://kiin.co/privacy-policy  
Terms: https://web.kiin.co/terms  
Support: adrian@kiin.co / phil@kiin.co  
Website: https://kiin.co  
Documentation: https://mcp.kiin.co/start (expand with Attio-specific setup page before submit)

## Assets still needed

- [ ] Developer account logo (PNG ≥560×560, no transparency)
- [ ] App logo (same specs)
- [ ] 3–7 marketing images 2960×1848 (Attio integration focused, not raw screenshots)
- [ ] Walkthrough video: install → Attio OAuth → sync → sample report in Attio/Kiin context
- [ ] Dedicated Attio setup doc URL (stable public page)

## Can do without Adrian

- This listing copy (done)
- Storyboard for video + image shot list
- Confirm callback URL + scopes against build.attio.com **if** portal access exists on a shared login

## Needs Adrian / Phil

- build.attio.com login / Publish
- Record walkthrough with a real Attio workspace
- Final app display name approval
