# LinkedIn Ads MCP — powered by Kiin

Cursor / Grok Bot plugin for the hosted **LinkedIn Ads MCP**. Read campaign performance **and** write changes (pause/enable, budgets, targeting, creatives, saved audiences, new campaigns as DRAFT). Every write is **preview-then-confirm**, then LinkedIn must accept the change.

Connect: [mcp.kiin.co/start](https://mcp.kiin.co/start)

## Install

### Cursor Marketplace (once published)

Search for **LinkedIn Ads MCP** / `linkedin-ads-mcp-kiin`, or:

```text
/add-plugin linkedin-ads-mcp-kiin
```

### From this repo (local / review)

1. Clone into `~/.cursor/plugins/local/linkedin-ads-mcp-kiin`
2. Reload the Cursor window
3. Connect the **kiin** MCP server and complete OAuth

### Manual remote MCP (without the plugin)

```json
{
  "mcpServers": {
    "kiin": {
      "url": "https://mcp.kiin.co/mcp"
    }
  }
}
```

Auth is OAuth (dynamic client registration). No API tokens or client secrets belong in config.

## Auth

1. Install / enable the plugin (or add the remote MCP URL above)
2. Start a chat and connect **kiin** when prompted
3. Complete Kiin sign-in at [mcp.kiin.co/start](https://mcp.kiin.co/start)
4. Connect LinkedIn Ads (and optionally CRM) in onboarding

The MCP advertises OAuth protected-resource metadata and a `registration_endpoint` (`/register`). Scope: `mcp:tools`.

## What you can do

**Read**
- Accounts, campaigns, campaign groups, ads, creatives
- Spend, CTR, CPL, impressions, clicks, period comparisons
- CRM-linked revenue after connecting a CRM in Kiin

**Write** (paid/trial; every mutation is preview-then-confirm)
- Pause / enable campaigns and ads
- Change budgets and targeting
- Creatives and saved audiences
- Create new campaigns as **DRAFT** (LinkedIn must accept)

Never apply a write silently — show the preview, wait for explicit confirm, then call the apply tool.

## Links

- Connect / onboarding: https://mcp.kiin.co/start
- MCP: https://mcp.kiin.co
- Product: https://kiin.co
- Submit: https://cursor.com/marketplace/publish
- Community: https://cursor.directory

## Repo contents

```text
.cursor-plugin/plugin.json   # Cursor plugin manifest
mcp.json                     # Remote MCP → https://mcp.kiin.co/mcp
skills/kiin-linkedin-ads/    # Agent guidance (read + write)
assets/logo.png              # Kiin brand mark (marketplace)
assets/favicon.png           # Brand favicon
```

No secrets. Credentials stay in the OAuth session.
