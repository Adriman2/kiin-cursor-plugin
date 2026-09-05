# Kiin Intelligence — Cursor / Grok Bot plugin

Thin Cursor plugin that wraps the hosted [Kiin LinkedIn Ads MCP](https://mcp.kiin.co) so agents can query LinkedIn Ads (campaigns, budgets, creatives) and optional CRM revenue joins.

## Install

### Cursor Marketplace (once published)

Search for **Kiin** / **kiin-intelligence** in Cursor Plugins, or:

```text
/add-plugin kiin-intelligence
```

### From this repo (local / review)

1. Clone into `~/.cursor/plugins/local/kiin-intelligence`
2. Reload the Cursor window
3. Connect the **kiin** MCP server and complete OAuth

### Manual remote MCP (without the plugin)

Add a remote MCP server with URL:

```text
https://mcp.kiin.co
```

Auth is OAuth (dynamic client registration). No API tokens or client secrets belong in config.

## Auth

1. Install / enable the plugin (or add the remote MCP URL above)
2. Start a chat and connect **kiin** when prompted
3. Complete Kiin sign-in (LinkedIn or email) at [mcp.kiin.co/start](https://mcp.kiin.co/start)
4. Connect LinkedIn Ads (and optionally CRM) in the Kiin onboarding flow

The MCP resource advertises OAuth protected-resource metadata and a `registration_endpoint` (`/register`). Scope: `mcp:tools`.

## What you can ask

- Campaign / campaign-group performance and budgets
- Creative and ad-level breakdowns
- CRM-linked revenue and conversion context (after connecting a CRM in Kiin)
- Preview-then-confirm for any write / mutate tools

See `skills/kiin-linkedin-ads/SKILL.md` for agent guidance.

## Links

- Product / connect: https://mcp.kiin.co
- Onboarding: https://mcp.kiin.co/start
- Homepage: https://kiin.co
- Publish (Cursor): https://cursor.com/marketplace/publish
- Community listing: https://cursor.directory

## Repo contents

```text
.cursor-plugin/plugin.json   # Cursor plugin manifest
mcp.json                     # Remote MCP → https://mcp.kiin.co
skills/kiin-linkedin-ads/    # When / how to use Kiin tools
assets/logo.png              # Marketplace logo
```

No secrets. The plugin only points at the hosted MCP; all credentials stay in the OAuth session.
