# LinkedIn Ads MCP — powered by Kiin

Portable **Agent Plugins 1.0** package (skills + remote MCP) for the hosted LinkedIn Ads MCP. Works with Cursor (also ships `.cursor-plugin/` for marketplace), Claude custom connectors, and other Agent Plugins clients.

**Same MCP everywhere:** `https://mcp.kiin.co` (OAuth DCR, scope `mcp:tools`). No product forks.

Read campaign performance **and** write changes (pause/enable, budgets, targeting, creatives, saved audiences, new campaigns as DRAFT). Every write is **preview-then-confirm**, then LinkedIn must accept.

Connect: [mcp.kiin.co/start](https://mcp.kiin.co/start)

## Package layout

```text
plugin.json                 # Agent Plugins 1.0 manifest
mcp.json                    # streamable-http → https://mcp.kiin.co
skills/kiin-linkedin-ads/   # READ + WRITE guidance
.cursor-plugin/plugin.json  # Cursor marketplace extras (logo)
assets/logo.png             # Brand mark
```

## Install

### Cursor Marketplace

Search **LinkedIn Ads MCP** / `linkedin-ads-mcp-kiin` (submitted for review).

Local load:

```text
~/.cursor/plugins/local/linkedin-ads-mcp-kiin
```

### Agent Plugins clients

Point the client at this repo / directory. Root `plugin.json` + `mcp.json` conform to [Agent Plugins 1.0](https://agent-plugins.org/specification).

### Manual remote MCP

```json
{
  "mcpServers": {
    "kiin": {
      "type": "streamable-http",
      "url": "https://mcp.kiin.co"
    }
  }
}
```

OAuth only — no API tokens or client secrets in config.

## Auth

1. Connect the **kiin** MCP server
2. Complete Kiin sign-in at [mcp.kiin.co/start](https://mcp.kiin.co/start)
3. Connect LinkedIn Ads (and optionally CRM)

## What you can do

**Read** — accounts, campaigns, creatives, spend, CTR/CPL, CRM-linked revenue  

**Write** (paid/trial; preview-then-confirm) — pause/enable, budgets, targeting, creatives, saved audiences, DRAFT campaigns

## Directory submissions

- Cursor: submitted via marketplace (see repo history)
- Claude Connectors: draft in [`docs/claude-connectors-directory.md`](docs/claude-connectors-directory.md)
- ChatGPT Apps / Plugins: draft in [`docs/chatgpt-apps-sdk.md`](docs/chatgpt-apps-sdk.md)

## Legal

- Privacy: https://kiin.co/privacy-policy · https://web.kiin.co/privacy
- Terms: https://web.kiin.co/terms

## Links

- MCP: https://mcp.kiin.co
- Product: https://kiin.co
- Spec: https://agent-plugins.org/specification
