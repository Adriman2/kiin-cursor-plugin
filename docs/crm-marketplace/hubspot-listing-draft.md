# HubSpot Marketplace — listing draft (Kiin)

**Type:** Technology Partner **Marketplace app** (CRM integration)  
**Not:** HubSpot Agent Marketplace / third-party connector to `mcp.kiin.co` (blocked pattern)  
**Path:** https://www.hubspot.com/partners/technology → list app  
**Reqs:** https://developers.hubspot.com/docs/apps/developer-platform/list-apps/listing-your-app/app-marketplace-listing-requirements  
**Contact:** technology-partners@hubspot.com

## OAuth (already live)

- Callback: `https://mcp.kiin.co/auth/hubspot/callback`
- Scopes: `crm.objects.companies.read`, `crm.objects.deals.read`, `crm.objects.contacts.read`, `crm.objects.owners.read`
- Railway: `HUBSPOT_CLIENT_ID` / `HUBSPOT_CLIENT_SECRET` / `HUBSPOT_REDIRECT_URI` present
- MCP: `connect_hubspot`, `create_hubspot_connect_link`, `sync_hubspot_now`, `get_crm_properties`, `get_pipeline_data`

## Gate (hard)

- ≥3 **unaffiliated production** HubSpot installs with successful API activity in last 30 days
- Public HubSpot-specific setup guide URL
- Demo video / walkthrough
- OAuth-only; matching public app ID; supported Projects platform version; no classic CRM cards
- Pricing on listing must match plans that include the integration

## Listing angle (draft)

**Name:** Kiin LinkedIn Ads  
**Use case:** Sync HubSpot companies/deals/contacts into Kiin for LinkedIn Ads influenced-pipeline reporting.  
**Install URL:** page that starts HubSpot OAuth / shareable `create_hubspot_connect_link`  
**Shared data:** companies, deals, contacts, owners — read from HubSpot → Kiin (document accurately in Shared data table)

## Setup guide outline (to publish on kiin.co)

1. Prerequisites (Kiin + LinkedIn Ads account)
2. Click Install / open connect link
3. Authorize HubSpot scopes
4. Verify connection + first sync
5. How to ask for influenced pipeline in Claude/Cursor
6. Disconnect / reconnect
7. Support contacts + privacy/terms

## Can do without Adrian

- This draft + setup guide markdown
- Shared-data table from scopes
- Hunt/create setup page content for Phil/Adrian to paste on kiin.co

## Needs Adrian / Phil

- Tech Partner signup / Super admin
- Confirm HubSpot public app ID == Railway client
- **3 customer installs** (longest pole)
- Demo video
- Submit listing (one app at a time)
