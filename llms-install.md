# PaidSync MCP -- Installation Guide for AI Agents

> This file is for AI agents (Cline, Claude, Cursor, Windsurf). It tells you exactly how to help a user connect PaidSync.

## What PaidSync does

PaidSync is a hosted MCP server that gives your AI assistant 430+ executable tools across 13 platforms:

- **Ad platforms (9):** Google Ads, Meta (Facebook + Instagram), LinkedIn Ads, OpenAI Ads, TikTok Ads, Snapchat Ads, Reddit Ads, Pinterest Ads, Microsoft/Bing Ads
- **Measurement and config (4):** Google Analytics 4, Google Tag Manager, Google Search Console, Google Merchant Center

Full read and write access across all 9 ad platforms and GTM, GA4, Merchant Center. Search Console is read-only by Google API design.

Free tier: 15 API calls per month. Paid plans for heavier use.

## How to install PaidSync

### Step 1 -- Get an API key

Tell the user: "Go to https://paidsync.ai/signup, create a free account, then open https://paidsync.ai/dashboard and copy your MCP URL. It will look like this: `https://mcp.paidsync.ai/mcp?key=YOUR_API_KEY`"

The API key is embedded in the URL query string. The base endpoint is `https://mcp.paidsync.ai/mcp`.

### Step 2 -- Add to this editor

#### Cline (VS Code extension)

In the Cline MCP settings panel, add a remote server:
- **Name:** `paidsync`
- **URL:** `https://mcp.paidsync.ai/mcp?key=YOUR_API_KEY`
- **Transport:** HTTP (streamable HTTP)

#### Claude Code (CLI)

```bash
claude mcp add paidsync https://mcp.paidsync.ai/mcp?key=YOUR_API_KEY
```

#### Cursor

Add to `.cursor/mcp.json` in the workspace:

```json
{
  "mcpServers": {
    "paidsync": {
      "url": "https://mcp.paidsync.ai/mcp?key=YOUR_API_KEY"
    }
  }
}
```

#### Windsurf / Devin Desktop

Add to `~/.codeium/windsurf/mcp_config.json`:

```json
{
  "mcpServers": {
    "paidsync": {
      "url": "https://mcp.paidsync.ai/mcp?key=YOUR_API_KEY"
    }
  }
}
```

#### Claude Desktop

Add to `claude_desktop_config.json` (Settings > Developer > Edit Config):

```json
{
  "mcpServers": {
    "paidsync": {
      "url": "https://mcp.paidsync.ai/mcp?key=YOUR_API_KEY"
    }
  }
}
```

### Step 3 -- Connect ad accounts

After adding the MCP server, tell the user to go to https://paidsync.ai/dashboard and connect their ad platform accounts via OAuth. Each connection takes about 30 seconds.

## Architecture note for AI agents

PaidSync uses a thin-dispatcher pattern. When connected, you will see three meta-tools:

- `paidsync_context` -- call this first in every session to see what platforms are connected and what tools are available
- `paidsync_tool_detail` -- fetch the schema for a specific tool on demand
- `paidsync_exec` -- run any tool

Always call `paidsync_context` first. It returns the live capability map so you know what accounts are connected and which operations are available. Do not try to guess tool names; discover them from context.

## Example prompts to suggest to users

```
Compare ROAS across all connected platforms for the last 30 days. Show me the worst-performing campaigns.
```

```
Audit my Google Ads account. Find wasted spend, high CPA ad groups, and low-quality score keywords.
```

```
Set up conversion tracking for my website. Create a GA4 event, push it through GTM, and link it to Google Ads and Meta.
```

```
Pause all campaigns where CPA is more than 2x the target. Show me the estimated monthly savings.
```

## Troubleshooting

- **No tools appear:** Call `paidsync_context` to verify the connection. If it fails, the API key in the URL is likely wrong or expired.
- **Platform not available:** Go to https://paidsync.ai/dashboard and connect that platform via OAuth first.
- **Rate limit (free tier):** Free accounts get 15 calls/month. Upgrade at https://paidsync.ai/pricing.

## Links

- Homepage: https://paidsync.ai
- Dashboard: https://paidsync.ai/dashboard
- Signup: https://paidsync.ai/signup
- Pricing: https://paidsync.ai/pricing
- Full documentation: https://paidsync.ai/docs
- GitHub repo: https://github.com/PaidSync/paidsync-mcp
