# PaidSync MCP -- Installation Guide for AI Agents

> This file is for AI agents (Claude, Claude Code, Cursor and other MCP clients). It tells you exactly how to help a user connect PaidSync.

## What PaidSync does

PaidSync is a hosted MCP server that gives your AI assistant 610+ tools across 14 platforms:

- **Ad platforms (10):** Google Ads, Meta (Facebook + Instagram), LinkedIn Ads, ChatGPT Ads, TikTok Ads, Snapchat Ads, Reddit Ads, Pinterest Ads, Microsoft (Bing) Ads, X Ads
- **Measurement and config (4):** Google Analytics 4, Google Tag Manager, Google Search Console, Google Merchant Center

PaidSync builds new campaigns on Google Ads, Meta, LinkedIn and ChatGPT Ads, and manages existing campaigns on TikTok, Microsoft, Snapchat, Reddit, Pinterest and X. It reads and changes GA4, Google Tag Manager and Merchant Center. Search Console is read-only in PaidSync.

Free for 15 tasks a month with no credit card, then priced by usage, from $99 a month for 600 tasks.

## How to install PaidSync

No API key is needed. The server URL is `https://mcp.paidsync.ai/mcp` (streamable HTTP). The user signs in to PaidSync when the client asks (free account, no card), then connects their ad accounts.

### Claude (web, desktop and mobile)

Tell the user: open PaidSync in Claude's connector directory (https://claude.ai/directory/connectors/paidsync-mcpp), click Connect, sign in to PaidSync and approve, then connect an ad account and ask.

### ChatGPT

Tell the user: open Plugins in ChatGPT, search for PaidSync and install it, sign in and approve, then connect an ad account and ask.

### Claude Code (CLI)

```bash
claude mcp add --transport http paidsync https://mcp.paidsync.ai/mcp
```

Then run `/mcp` in Claude Code and sign in with the PaidSync login.

### Cursor

Add to `.cursor/mcp.json` in the workspace (or `~/.cursor/mcp.json` for all projects), then open Cursor Settings, MCP, and sign in with the PaidSync login:

```json
{
  "mcpServers": {
    "paidsync": {
      "url": "https://mcp.paidsync.ai/mcp"
    }
  }
}
```

### Other MCP clients

Add `https://mcp.paidsync.ai/mcp` as a remote (streamable HTTP) server and sign in when the client asks. For headless runs that cannot sign in, send the user's PaidSync API key in a header (`Authorization: Bearer <key>`), never in the URL, where it would end up in logs.

### Connect ad accounts

After the server is added, the user connects each ad platform through its own sign-in, from the chat or at https://paidsync.ai/dashboard.

## Architecture note for AI agents

PaidSync uses a thin-dispatcher pattern. When connected, you will see a small set of meta-tools, including:

- `paidsync_context` -- call this first in every session to see what platforms are connected and what tools are available
- `paidsync_tool_detail` -- fetch the schema for a specific tool on demand
- `paidsync_read` -- run a read-only tool without an approval prompt
- `paidsync_exec` -- run any tool, including changes

Always call `paidsync_context` first. It returns the live capability map so you know what accounts are connected and which operations are available. Do not guess tool names; discover them from context.

## Example prompts to suggest to users

```
Compare ROAS across all connected platforms for the last 30 days. Show me the worst-performing campaigns.
```

```
Audit my Google Ads account. Find wasted spend, high CPA ad groups, and low Quality Score keywords.
```

```
Set up conversion tracking for my website. Create a GA4 event, push it through GTM, and link it to Google Ads.
```

```
Find the keywords that spent the most last month with no conversions, and preview pausing them.
```

## Troubleshooting

- **No tools appear:** call `paidsync_context` to verify the connection. If sign-in did not finish, remove the server and add it again, then sign in.
- **Platform not available:** connect that platform first, from the chat or at https://paidsync.ai/dashboard.
- **Out of tasks (free plan):** the free plan includes 15 tasks a month. Upgrade at https://paidsync.ai/pricing.

## Links

- Homepage: https://paidsync.ai
- Dashboard: https://paidsync.ai/dashboard
- Signup: https://paidsync.ai/signup
- Pricing: https://paidsync.ai/pricing
- Full documentation: https://paidsync.ai/docs
- GitHub repo: https://github.com/PaidSync/paidsync-mcp
