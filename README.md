# PaidSync. The MCP for Running Ads with AI

> **The only MCP server that runs Google, Meta, LinkedIn, and TikTok ads with full edit access.** Plus GTM, GA4, and GSC. 380+ tools across 7 platforms in one conversation.

[![Meta Business Partner](https://img.shields.io/badge/Meta-Business%20Partner-1877F2)](https://paidsync.ai/meta-ads-mcp)
[![LinkedIn Marketing Partner](https://img.shields.io/badge/LinkedIn-Marketing%20Partner-0A66C2)](https://paidsync.ai/linkedin-ads-mcp)
[![TikTok Marketing Partner](https://img.shields.io/badge/TikTok-Marketing%20Partner-000000)](https://paidsync.ai/tiktok-ads-mcp)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

[paidsync.ai](https://paidsync.ai) · [Run Ads with AI](https://paidsync.ai/run-ads-with-ai) · [Compare](https://paidsync.ai/compare) · [Docs](https://paidsync.ai/docs)

---

## What this is

Most MCP servers for ads are read-only. Google's native Google Ads MCP is read-only. ppc.io is read-only. GoMarble is read-only with write in private beta. Meta's AI Ads Connector edits Meta, nothing else.

PaidSync is the one MCP that lets AI act. Across four ad platforms (Google, Meta, LinkedIn, TikTok), three tracking platforms (Google Tag Manager, Google Analytics 4, Google Search Console), in one conversation.

That means your AI assistant does not just describe your campaigns. It pauses them. Creates them. Builds audiences. Sets up conversion tracking end to end. Compares ROAS across all four channels. In one chat.

## Supported platforms

| Platform | Tools | Access | Partner status |
|---|---:|---|---|
| Google Ads | 200+ | Full edit (incl. MCC) | Founder is Google Premier Partner (top 3% globally) |
| Meta Ads (Facebook + Instagram) | 70+ | Full edit (incl. Business Manager system user tokens) | **Meta Business Partner** |
| LinkedIn Ads | 30+ | Full WRITE access (most MCPs are read-only) | **LinkedIn Marketing Partner** |
| TikTok Ads | full | Full edit (incl. advertiser switching) | **TikTok Marketing Partner** |
| Google Tag Manager | 40+ | Full edit (tags, triggers, variables, workspaces) | n/a |
| Google Analytics 4 | 25+ | Full edit (conversion events, audiences, custom dimensions) | n/a |
| Google Search Console | 10+ | Read access (paid + organic blend reporting) | n/a |

**Total: 380+ executable tools** in a single MCP endpoint.

## Quick start

### 1. Sign up

Create a free account at [paidsync.ai/signup](https://paidsync.ai/signup). Free tier includes 15 API calls/month, enough to run your first audit and test the connection.

### 2. Copy your MCP URL

From the [PaidSync dashboard](https://paidsync.ai/dashboard), copy your unique MCP server URL. It looks like:

```
https://mcp.paidsync.ai/mcp?key=YOUR_API_KEY
```

### 3. Add to your AI assistant

PaidSync uses the open [Model Context Protocol (MCP)](https://modelcontextprotocol.io). Any MCP-compatible AI client works. Pick yours below.

#### Claude Desktop

Edit `claude_desktop_config.json` (Settings, Developer, Edit Config on Mac/Windows):

```json
{
  "mcpServers": {
    "paidsync": {
      "url": "https://mcp.paidsync.ai/mcp?key=YOUR_API_KEY"
    }
  }
}
```

Restart Claude Desktop. PaidSync appears as a connected tool.

#### claude.ai (web)

Settings, Integrations, Add MCP Server. Name: `PaidSync`. URL: `https://mcp.paidsync.ai/mcp?key=YOUR_API_KEY`. Requires Claude Pro, Max, Team, or Enterprise.

#### Claude Code (CLI)

```bash
claude mcp add paidsync https://mcp.paidsync.ai/mcp?key=YOUR_API_KEY
```

#### ChatGPT

Settings, Connected Tools, Add MCP Server. Name: `PaidSync`. URL: `https://mcp.paidsync.ai/mcp?key=YOUR_API_KEY`. Requires ChatGPT Plus or Pro.

#### Gemini

Settings, Extensions, Add MCP Server. Name: `PaidSync`. URL: `https://mcp.paidsync.ai/mcp?key=YOUR_API_KEY`.

#### Cursor

Edit `.cursor/mcp.json` in your workspace:

```json
{
  "mcpServers": {
    "paidsync": {
      "url": "https://mcp.paidsync.ai/mcp?key=YOUR_API_KEY"
    }
  }
}
```

#### Windsurf

Edit `~/.codeium/windsurf/mcp_config.json`:

```json
{
  "mcpServers": {
    "paidsync": {
      "url": "https://mcp.paidsync.ai/mcp?key=YOUR_API_KEY"
    }
  }
}
```

### 4. Connect your ad accounts

Inside the PaidSync dashboard, connect Google Ads, Meta Ads, LinkedIn Ads, TikTok Ads, GTM, GA4, and GSC via OAuth. Each connection takes about 30 seconds. Agency users connect MCC and Business Manager once and gain access to every client account from chat.

---

## Why edit access matters

A read-only MCP can tell you that 17 ad groups have CPA over $50. It cannot pause them. You log in to the ad platform and click 17 times.

PaidSync pauses them. It also tells you the estimated monthly savings. It also flags the keywords driving the high CPA. It also offers to pause those.

The category of "AI for ads" is shifting from describing your data to running your account. PaidSync was built for the second category.

---

## Example prompts

Once PaidSync is connected, paste any of these into Claude, ChatGPT, Gemini, or Cursor:

**Cross-channel work**

```
Compare ROAS across Google, Meta, LinkedIn, and TikTok for the last 30 days.
Pause the worst-performing campaign on each platform.
```

```
My Meta Ads ROAS just dropped 20%. Pull TikTok ROAS for the same date range
and product set. Should I shift budget?
```

**Conversion tracking setup (only PaidSync does this)**

```
Set up purchase conversion tracking. Create the GA4 event, build the GTM tag
and trigger, and link it to Google Ads as a primary conversion.
```

**Account audits**

```
Run a full audit on my Google Ads, Meta Ads, and LinkedIn Ads accounts.
Tell me where I am wasting budget on each.
```

**Paid plus organic blends**

```
Show me Google Ads keywords I am paying for that I already rank organically
for in Search Console. Pause them if they are not converting.
```

**TikTok**

```
Pause every TikTok ad group with CPA over $40 and less than 3 conversions
in the last 14 days.
```

**LinkedIn B2B**

```
Compare LinkedIn cost-per-lead to Google Ads CPL for the same audience this quarter.
Where am I getting more in-target leads?
```

**Agency workflow**

```
Switch to my client Google Ads MCC account, audit it, and email me a summary
of the top 3 issues by Monday morning.
```

---

## How PaidSync compares

| | PaidSync | Google native MCP | Meta AI Ads Connector | ppc.io | Pipeboard | Adspirer | Ryze AI |
|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| Google Ads edit | yes | no, read-only | no | no, read-only | yes | yes | yes |
| Meta Ads edit | yes | no | yes Meta-only | no | yes | yes | yes |
| LinkedIn Ads edit | yes | no | no | no | no | yes | partial |
| TikTok Ads edit | yes | no | no | no | no | yes | no |
| GTM edit | yes | no | no | no | no | no | no |
| GA4 edit | yes | no | no | no | no | no | partial |
| End-to-end conversion tracking | yes | no | no | no | no | no | no |
| Wasted-spend plus PMax audits | yes | no | no | no | no | no | partial |
| MCP-based (any AI client) | yes | yes | yes | yes | yes | yes | no |
| Free tier | yes | yes | yes | unknown | trial | trial | no |

Full comparison: [paidsync.ai/compare](https://paidsync.ai/compare)

---

## Pricing

| Plan | Monthly | Annual | API calls/mo |
|---|---:|---:|---:|
| Limited | Free | n/a | 15 |
| Plus | $49 | $490 | 150 |
| Pro | $99 | $999 | 600 |
| Max | $199 | $2,000 | 4,000 |

All platforms (Google, Meta, LinkedIn, TikTok, GTM, GA4, GSC), MCC support, and Business Manager system user tokens are included on every plan, including free.

[Start free at paidsync.ai/signup](https://paidsync.ai/signup)

---

## Why PaidSync is different

1. **Edit access on every channel that matters.** Google's native MCP is read-only. Most competitors stop at one or two platforms. PaidSync runs four ad platforms plus GTM plus GA4 with full edit.

2. **Conversion tracking by chat.** No other MCP server lets AI set up conversion tracking end to end. PaidSync's composite tools create the GA4 event, build the GTM tag and trigger, and link the conversion to Google Ads in one prompt.

3. **Audit layer that finds money.** Scored account health, wasted-spend detection, PMax asset-group breakdowns, Quality Score analysis, anomaly detection, paid plus organic cannibalization checks against GSC. Built in. No other MCP offers this.

4. **Built for paid media at scale.** Google Ads MCC, Meta Business Manager system user tokens, LinkedIn Marketing Partner write access, TikTok advertiser switching. Agency-grade across every channel.

5. **Open MCP, not proprietary UI.** Use PaidSync from Claude, ChatGPT, Gemini, Cursor, Windsurf, Claude Code, Perplexity. Your AI tool of choice. We do not lock you in to a dashboard.

---

## Partner credentials

- **Meta Business Partner**, verified via Meta Marketing Partner Program
- **LinkedIn Marketing Partner**, full WRITE access (most MCPs do not have this)
- **TikTok Marketing Partner**, verified TikTok integration
- Founder Ahmed Ashraf, **Google Premier Partner** (top 3% globally), $500M+ in ad spend managed across a decade in paid media

---

## Documentation and resources

- [Run Ads with AI](https://paidsync.ai/run-ads-with-ai), the pillar page for the dominance positioning
- [Google Ads MCP details](https://paidsync.ai/google-ads-mcp)
- [Meta Ads MCP details](https://paidsync.ai/meta-ads-mcp)
- [LinkedIn Ads MCP details](https://paidsync.ai/linkedin-ads-mcp)
- [TikTok Ads MCP details](https://paidsync.ai/tiktok-ads-mcp)
- [Comparison: PaidSync vs every MCP ad server](https://paidsync.ai/compare)
- [Blog (60+ articles on AI ad management)](https://paidsync.ai/blog)
- [Docs](https://paidsync.ai/docs)
- [Book a demo](https://paidsync.ai/book-demo)
- [Changelog](https://paidsync.ai/changelog)
- [llms.txt for AI engines](https://paidsync.ai/llms.txt) and [llms-full.txt](https://paidsync.ai/llms-full.txt)

---

## Connect

- Website: [paidsync.ai](https://paidsync.ai)
- Email: [support@paidsync.ai](mailto:support@paidsync.ai)
- LinkedIn: [PaidSync](https://www.linkedin.com/company/paidsync-ai/)
- Instagram: [@paidsync](https://www.instagram.com/paidsync)
- Founder LinkedIn: [Ahmed Ashraf](https://www.linkedin.com/in/ahmedashrafppc/)

---

## License

MIT. See [LICENSE](LICENSE).

The PaidSync MCP service itself is a proprietary managed service. This repository documents how to use it, with example configurations and integration guides. No source code for the hosted server is included.

---

**Maintained by [PaidSync](https://paidsync.ai). Operated by Advanced Technology Labs LLC (Wyoming, USA).**
