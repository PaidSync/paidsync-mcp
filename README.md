# PaidSync.ai - MCP Server for Ads

Manage Google Ads, Meta Ads, LinkedIn Ads, TikTok Ads, and Google Tag Manager through AI. 240+ tools for account audits, campaign management, wasted spend detection, PMax insights, conversion tracking setup, and more.

Works with **Claude**, **ChatGPT**, **Gemini**, **Claude Code**, **Cursor**, and **Windsurf**.

## Quick Start

### 1. Sign up

Create a free account at [paidsync.ai/signup](https://paidsync.ai/signup) and copy your MCP URL from the dashboard.

### 2. Connect to your AI assistant

**Claude Desktop / claude.ai**

Add to your Claude MCP settings:

```json
{
  "mcpServers": {
    "paidsync": {
      "url": "https://adsagent-805936384842.us-central1.run.app/mcp?key=YOUR_API_KEY"
    }
  }
}
```

**Claude Code (CLI)**

```bash
claude mcp add paidsync https://adsagent-805936384842.us-central1.run.app/mcp?key=YOUR_API_KEY
```

**ChatGPT**

Go to ChatGPT Settings > MCP Servers > Add Server > paste your MCP URL.

**Cursor / Windsurf**

Add to your MCP config (`.cursor/mcp.json` or equivalent):

```json
{
  "mcpServers": {
    "paidsync": {
      "url": "https://adsagent-805936384842.us-central1.run.app/mcp?key=YOUR_API_KEY"
    }
  }
}
```

### 3. Connect your ad accounts

Once connected, tell your AI:

- `"Connect my Google Ads account"` - starts OAuth flow
- `"Connect my Facebook Ads"` - starts Meta OAuth flow

### 4. Start managing ads

Try these:

- `"Audit my Google Ads account"`
- `"Find wasted spend in the last 30 days"`
- `"List all my campaigns and their performance"`
- `"What is my PMax campaign actually doing?"`
- `"Create a search campaign for my new product"`
- `"Pause all ad groups with CPA above $50"`

## What's Included

### Google Ads (126+ tools)
- Campaign management (Search, Display, Video, Shopping, PMax, Demand Gen)
- Keyword research and management
- Ad creation (RSA, RDA)
- Bidding strategies
- Audience targeting
- Extensions and assets
- Conversion tracking
- Performance Max insights
- **Account audit with scoring**
- **Wasted spend detection**
- **Quality Score analysis**
- **Impression share analysis**
- **Anomaly detection**
- **Search term n-gram analysis**

### Meta Ads (57+ tools)
- Campaign, ad set, and ad management
- Audience creation (custom, lookalike, engagement)
- Performance reporting with breakdowns
- Creative management
- Budget pacing
- Automated rules

### LinkedIn Ads (27+ tools)
- Campaign and campaign group management
- Creative management with image/video upload
- Conversion tracking
- Audience targeting with full RestLI 2.0 support
- Performance reporting with dimension breakdowns
- **Full write access** (competitors only offer read)

### Google Tag Manager (38 tools)
- Container audit and management
- Tag, trigger, and variable CRUD
- Workspace and version management
- Publishing and environment control
- **Composite tools**: setup_google_ads_conversion, setup_ga4_event, setup_form_tracking
- **Only MCP server with GTM + Ads in one integration**

### TikTok Ads (Coming Soon)
- Campaign management
- Creative management
- Performance reporting

## Agency Features

- **Google Ads MCC**: Connect your manager account and switch between client accounts
- **Meta Business Manager**: Use system user tokens for permanent access to all client accounts
- **Bulk operations**: Manage multiple accounts in one conversation

## Pricing

| Plan | Price | Tool Calls/Month |
|------|-------|-----------------|
| Limited | Free | 15 |
| Plus | $49/mo | 150 |
| Pro | $99/mo | 600 |
| Max | $199/mo | 4,000 |

## Links

- Website: [paidsync.ai](https://paidsync.ai)
- Documentation: [paidsync.ai/docs](https://paidsync.ai/docs)
- Compare: [paidsync.ai/compare](https://paidsync.ai/compare)
- Google Ads MCP: [paidsync.ai/google-ads-mcp](https://paidsync.ai/google-ads-mcp)
- Blog: [paidsync.ai/blog](https://paidsync.ai/blog)
- Book a Demo: [paidsync.ai/book-demo](https://paidsync.ai/book-demo)

## Support

- Email: support@paidsync.ai
- Website: [paidsync.ai](https://paidsync.ai)
