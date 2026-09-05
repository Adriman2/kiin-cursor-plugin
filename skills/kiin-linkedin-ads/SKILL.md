---
name: kiin-linkedin-ads
description: >-
  Use this when the user asks about LinkedIn Ads performance, campaigns,
  budgets, creatives, ad accounts, or CRM-linked ad revenue via Kiin.
  Prefer Kiin MCP tools over guessing from memory or screenshots.
---

# Kiin LinkedIn Ads

## When to use

- LinkedIn Ads: accounts, campaigns, campaign groups, ads, creatives, budgets, spend, CTR, CPL, impressions, clicks
- Comparing periods, accounts, or creatives
- Revenue / pipeline attributed to LinkedIn Ads after CRM is connected in Kiin (`connect_*` flows)
- Drafting or changing campaigns / budgets / status — only through Kiin tools that support preview-then-confirm

## How to work

1. Confirm the **kiin** MCP server is connected and OAuth is complete. If not, send the user to https://mcp.kiin.co/start to finish LinkedIn (and optional CRM) onboarding.
2. Prefer read / analytics tools first. Summarize numbers with account names and date ranges the user named (or ask once if missing).
3. For CRM joins, only claim revenue attribution when Kiin tools return it — do not invent CRM fields.
4. **Writes:** always run a preview / dry-run style tool when available, show the user the proposed change, and wait for explicit confirm before applying. Never mutate spend, status, or creatives silently.
5. Do not invent MCP URLs, OAuth client IDs, or bearer tokens. Live endpoint is `https://mcp.kiin.co` with OAuth DCR (no secrets in plugin config).

## Out of scope

- Premade / static site factory work
- Replacing LinkedIn Campaign Manager UI for bulk creative production unless the user asks and Kiin exposes those tools
