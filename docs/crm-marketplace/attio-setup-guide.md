# Connect Attio to LinkedIn Ads Sync (powered by Kiin)

**Public URL to publish before Attio App Store Publish:**  
`https://kiin.co/integrations/attio`  
(Status as of 2026-09-18: path not live yet on kiin.co. Paste this page, then use that URL in Configure.)

**App name:** LinkedIn Ads Sync — powered by Kiin  
**Developer:** Kiin Intelligence  
**Product:** Match LinkedIn Ads company engagement to Attio people, companies, and deals for influenced-pipeline reporting in Claude, Cursor, and other MCP clients.

This is not an official LinkedIn product.

---

## What you get

- One-time OAuth connect from Attio to Kiin
- Nightly (and on-demand) sync of Attio companies, people, deals, and owners into Kiin
- Influenced-pipeline and coverage reports next to your LinkedIn Ads data

## What Kiin reads (read-only)

Kiin requests **read-only** Attio access:

- `record_permission:read`
- `object_configuration:read`
- optional `user_management:read` (deal owner names)

Kiin does **not** create, edit, or delete Attio records. Writes stay on the LinkedIn Ads side inside Kiin (preview-then-confirm), not in Attio.

## Prerequisites

1. A Kiin account with at least one LinkedIn Ads account connected: [Start / connect](https://mcp.kiin.co/start) (opens Kiin web connect).
2. Permission to authorize an Attio workspace (or a client who can open a shareable connect link).
3. Claude, Cursor, or another MCP client with [LinkedIn Ads MCP — powered by Kiin](https://mcp.kiin.co) installed (optional for OAuth; required to ask for reports).

## Setup (you own Attio)

1. Sign in to Kiin and confirm the LinkedIn Ads account you want to attribute.
2. In your MCP client, run **connect Attio** for that account (or open the authorize link Kiin returns).
3. On the Attio consent screen, approve the read scopes.
4. Wait for the first sync, or ask a Kiin admin to run **sync Attio now**.
5. Confirm under **list CRM connections**, then ask for influenced pipeline or deal coverage.

Authorize URL pattern (account-bound):  
`https://mcp.kiin.co/auth/attio/authorize?account_id=<your Kiin account>`

## Setup (client owns Attio)

Agencies often cannot log into the client’s Attio. Use a shareable invite:

1. In your MCP client, run **create Attio connect link** for the LinkedIn Ads account.
2. Send the link (`https://mcp.kiin.co/connect/attio/<token>`) to the client.
3. They approve Attio OAuth once; no Kiin login required on their side.
4. Link expires (default 14 days, max 90). You can mint another if needed.

## After connect

- Nightly sync keeps the Attio mirror fresh.
- Company matching uses Attio company names against LinkedIn company engagement.
- Attio has no HubSpot-style UTM fields, so contact-level attribution stays unattributed. Deal influence still comes from LinkedIn exposure before the deal was created.
- Disconnect / reconnect: connect Attio again for the same account, or ask support to revoke the connection.

## Privacy and support

- Privacy: https://kiin.co/privacy-policy  
- Terms: https://web.kiin.co/terms  
- Support: adrian@kiin.co · phil@kiin.co  
- Website: https://kiin.co  

## FAQ

**Is Attio data written back?** No. Read-only on Attio.

**Do I need the Attio App Store install and MCP?** App Store listing is for discovering and trusting the Attio OAuth app. Reporting runs through Kiin in your AI client after LinkedIn Ads + Attio are connected.

**Unapproved app warning?** Unpublished or newly published Attio apps may show a warning until review completes. The connect still works with the scopes you approve.
