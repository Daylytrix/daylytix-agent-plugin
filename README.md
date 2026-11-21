# Daylytix for AI agents

This repository is the Daylytix plugin for Claude Code, Codex and Cursor. It connects the agent to the Daylytix MCP server (`https://app.daylytix.com/mcp`) and adds six skills: ready workflows that tell the agent how to use the Daylytix tools for one job.

| Skill | What it does |
|---|---|
| `audit-review` | Turns a Daylytix audit into the 3 to 5 fixes that matter most, each checked on the live page and in Search Console |
| `ai-visibility` | Shows whether AI answers name the brand, which pages they cite, the traffic AI assistants send, and what blocks AI crawlers |
| `keyword-plan` | Builds a page-by-page keyword plan from the site's own Search Console data first, then competitors |
| `client-report` | Writes a plain monthly report from Search Console, Google Analytics, the audit and AI answers |
| `local-seo` | Checks name, address, phone, local markup and local searches for a local business |
| `project-setup` | Saves the business, goals, competitors and key pages, checks Google, runs the first audit |

## What you need

A Daylytix account (the 7-day trial works). The agent signs in to Daylytix the first time it uses a tool. To let it start audits and save notes, allow actions when you sign in.

Search Console and Google Analytics answers need a Google account connected in Daylytix: Settings > Google Services. Competitor and keyword research uses your own DataForSEO login, set in Daylytix.

## Install

**Claude Code**: add this repository as a marketplace, then install the plugin:

```
/plugin marketplace add Daylytrix/daylytix-agent-plugin
/plugin install daylytix@daylytix
```

**Codex and Cursor**: the plugin folder `plugins/daylytix` has a manifest for each (`.codex-plugin/plugin.json`, `.cursor-plugin/plugin.json`).

**Claude.ai and ChatGPT**: add Daylytix as a connector with the URL `https://app.daylytix.com/mcp`. The skills are plain text: paste the one you need into a project's instructions.

More on the MCP server and its tools: https://daylytix.com/kb/integrations-mcp

## License

MIT. See `LICENSE`. The license covers the files in this repository. The Daylytix service itself is not open source.
