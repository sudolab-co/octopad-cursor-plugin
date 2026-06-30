# Octopad — Cursor plugin

The back-office workspace for your team's AIs: shared **tasks, knowledge, and context** over MCP.

This repository packages Octopad as a [Cursor Marketplace](https://cursor.com/marketplace) plugin. Octopad is a **remote MCP server** — installing the plugin registers the hosted endpoint and Cursor walks you through OAuth on first connect. There is nothing to run locally.

## What you get

Installing this plugin connects Cursor to the Octopad MCP server (`https://mcp.octopad.app/mcp`), exposing Octopad's tools for working with your organization's tasks, work streams, goals, pages/knowledge, files, and sessions directly from the agent.

## Install

From the Cursor Marketplace, search for **Octopad** and install. On first use, Cursor opens the Octopad sign-in (OAuth 2.0 + PKCE) — authorize once and the tools become available.

To connect manually instead, add to your Cursor `mcp.json`:

```json
{
  "mcpServers": {
    "octopad": { "url": "https://mcp.octopad.app/mcp" }
  }
}
```

## Learn more

- Website: https://octopad.ai
- App: https://www.octopad.app

## Repository layout

```
.cursor-plugin/marketplace.json   # marketplace manifest (one plugin: octopad)
plugins/octopad/
  .cursor-plugin/plugin.json       # plugin manifest
  mcp.json                         # remote MCP server definition
  assets/avatar.png                # plugin logo (1:1 PNG with background plate)
scripts/validate-template.mjs      # Cursor template validator
```

Validate before submitting:

```bash
node scripts/validate-template.mjs
```
