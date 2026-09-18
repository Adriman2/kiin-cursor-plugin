# Pipedrive Marketplace — listing draft (Kiin)

**Path:** developers.pipedrive.com sandbox → Settings → Developer Hub → public app → Install/test → Preview → Send to review → Publish  
**Review:** ≤21 business days · marketplace.devs@pipedrive.com  
**Docs:** https://pipedrive.readme.io/docs/marketplace-app-approval-process

## OAuth (production)

- Callback to register: `https://mcp.kiin.co/auth/pipedrive/callback`
- Railway: `PIPEDRIVE_CLIENT_ID` / `PIPEDRIVE_CLIENT_SECRET` present
- Live handlers respond at `/auth/pipedrive/authorize` and `/auth/pipedrive/callback`
- MCP: `connect_pipedrive`, `create_pipedrive_connect_link`, `sync_pipedrive_now`

**Repo note:** `Adriman2/kiin-mcp` main currently has no `src/crm/pipedrive` module (docs still say not implemented) while Railway + MCP tools are live. Reconcile source of truth before review.

## Listing blurb (draft)

**Name:** Kiin LinkedIn Ads Sync  
**Tagline:** Match Pipedrive pipeline to LinkedIn Ads influence  
**Description:** Connect Pipedrive to Kiin so LinkedIn Ads engagement can be reported against companies and deals. One OAuth install, nightly sync, read-focused CRM mirror for influenced-pipeline analysis in MCP clients.

## Mandatory before Send to review

- [ ] Public app in Developer Hub with working HTTPS callback
- [ ] Install + uninstall flows tested
- [ ] Test account credentials for reviewers
- [ ] Walkthrough / demo video
- [ ] Support + legal URLs (privacy/terms above)
- [ ] Email confirmation for main contact

## Can do without Adrian

- Listing copy draft (this file)
- Callback URL + checklist
- Flag repo/docs lag for engineering fix

## Needs Adrian / Phil

- Pipedrive developer sandbox / Hub login
- Send to review + Publish
- Test company Pipedrive for uninstall/install demos
