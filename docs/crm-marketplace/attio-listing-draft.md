# Attio App Store — listing draft (for Bart review)

**Suggested app name:** LinkedIn Ads Sync — powered by Kiin  
**Developer account name:** Kiin Intelligence (no “Attio”, no “dev/test”)  
**Naming rules:** LinkedIn Ads–first; “powered by Kiin”; do **not** claim to be an official LinkedIn product or LinkedIn partner unless we have that.  
**Publish:** https://build.attio.com → Publish app  
**Docs:** https://docs.attio.com/share/publishing-to-the-app-store · https://docs.attio.com/share/app-listings  
**Review:** ~1 week; no install minimum  

## OAuth (already live)

- Redirect to register: `https://mcp.kiin.co/auth/attio/callback`  
  (also: `http://localhost:8080/auth/attio/callback` for local)
- Scopes on the Attio app (not on the authorize URL): `record_permission:read`, `object_configuration:read`, optional `user_management:read`
- Railway: `ATTIO_CLIENT_ID`, `ATTIO_CLIENT_SECRET`, `ATTIO_REDIRECT_URI` present on `kiin-mcp` production
- MCP: `connect_attio`, `create_attio_connect_link`, `sync_attio_now`, `list_crm_connections`

---

## Overview (paste candidate, ~650 chars)

LinkedIn Ads Sync — powered by Kiin — connects your Attio workspace to LinkedIn Ads reporting so you can see which companies and deals were influenced by your ads.

After a one-time OAuth connect, Kiin syncs people, companies, and deals from Attio on a nightly schedule and matches them to LinkedIn company engagement. You then ask for influenced-pipeline and coverage reports from Claude, Cursor, or any MCP client that has Kiin installed.

The Attio side is read-only: Kiin does not create or edit Attio records. Use this when you already run LinkedIn Ads and keep pipeline in Attio.

---

## How It Works (paste candidate)

1. Connect Kiin to the LinkedIn Ads account you want to attribute (https://mcp.kiin.co/start).
2. Connect Attio with a one-click OAuth link from Kiin, or share a client-facing connect invite if the Attio workspace belongs to someone else.
3. Approve read-only Attio access (people, companies, deals, and optional owners).
4. Kiin mirrors those records into its pipeline tables and refreshes them nightly. Admins can trigger an immediate sync.
5. In your AI client, ask for influenced pipeline, deal coverage, and company-level LinkedIn exposure versus Attio deals.

Company matching uses Attio company names against LinkedIn company engagement. Attio has no HubSpot-style UTM fields, so contact-level attribution stays unattributed; deal influence still comes from LinkedIn exposure before the deal was created.

---

## Configure (paste candidate)

1. Sign in to Kiin and connect LinkedIn Ads for the account you will attribute (https://mcp.kiin.co/start).
2. In Claude, Cursor, or another MCP client with Kiin, run connect Attio for that account — or open a create Attio connect link invite and send it to the Attio workspace owner.
3. On the Attio consent screen, approve the read scopes only.
4. Wait for the first sync, or ask an admin to sync Attio now.
5. Confirm the connection under list CRM connections, then ask for pipeline or influenced reports.

Privacy: https://kiin.co/privacy-policy  
Terms: https://web.kiin.co/terms  
Support: adrian@kiin.co · phil@kiin.co  
Website: https://kiin.co  
Documentation: https://mcp.kiin.co/start (replace with a dedicated Attio setup URL before Publish)

---

## Asset checklist

- [ ] Developer account logo — PNG ≥560×560, no transparency
- [ ] App logo — same specs
- [ ] 3–7 marketing images — 2960×1848, Attio + LinkedIn Ads influence story (not raw uncropped screenshots)
- [ ] Walkthrough video — see `attio-walkthrough-script.md`
- [ ] Stable public Attio setup guide URL (Configure section)
- [ ] Privacy + Terms URLs live (done)
- [ ] Redirect URI registered on build.attio.com to `https://mcp.kiin.co/auth/attio/callback`

---

## Needs Adrian / Phil to ship

- build.attio.com login → Publish
- Record walkthrough in a real Attio workspace
- Final display-name sign-off
