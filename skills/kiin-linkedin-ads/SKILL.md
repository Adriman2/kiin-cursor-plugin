---
name: kiin-linkedin-ads
description: >-
  Use for LinkedIn Ads via Kiin MCP — read performance (campaigns, budgets,
  creatives, CRM-linked revenue) and write changes (pause/enable, budgets,
  targeting, creatives, saved audiences, DRAFT campaigns). Every write is
  preview-then-confirm. Prefer Kiin tools over guessing from memory or screenshots.
---

# LinkedIn Ads MCP — powered by Kiin

## When to use

- LinkedIn Ads accounts, campaigns, campaign groups, ads, creatives, budgets, spend, CTR, CPL, impressions, clicks
- Comparing periods, accounts, or creatives
- CRM-linked revenue / pipeline after CRM is connected in Kiin
- **Writes:** pause/enable, budget changes, targeting edits, creatives, saved audiences, creating campaigns as DRAFT

## How to work

1. Confirm the **kiin** MCP server is connected and OAuth is complete. If not, send the user to https://mcp.kiin.co/start for LinkedIn Ads (and optional CRM) onboarding.
2. Prefer read / analytics tools first when the ask is diagnostic. Summarize with account names and date ranges the user named (or ask once if missing).
3. For CRM joins, only claim revenue attribution when Kiin tools return it — do not invent CRM fields.
4. **Writes (critical):** paid/trial unlock mutating tools. Always run the preview / dry-run tool first, show the proposed change, and wait for **explicit user confirm** before applying. LinkedIn must still accept the change after apply. Never mutate spend, status, targeting, creatives, or audiences silently.
5. New campaigns should be created as **DRAFT** unless the user explicitly asks otherwise and the tool allows it.
6. Do not invent MCP URLs, OAuth client IDs, or bearer tokens. Live endpoint is `https://mcp.kiin.co` with OAuth DCR (no secrets in plugin config).

## Out of scope

- Premade / static site factory work
- Claiming write access when tools are missing (free / disconnected) — say what’s available and point to https://mcp.kiin.co/start
