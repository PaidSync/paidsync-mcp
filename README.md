# PaidSync. The MCP for Running Ads with AI

> **The only MCP server that runs Google, Meta, LinkedIn, and TikTok ads with full edit access.** Plus GTM, GA4, and GSC. 309 tools across 8 platforms in one conversation.

[![Google Premier Partner](https://img.shields.io/badge/Google-Premier%20Partner-4285F4)](https://paidsync.ai/google-ads-mcp)
[![Meta Business Partner](https://img.shields.io/badge/Meta-Business%20Partner-1877F2)](https://paidsync.ai/meta-ads-mcp)
[![LinkedIn Marketing Partner](https://img.shields.io/badge/LinkedIn-Marketing%20Partner-0A66C2)](https://paidsync.ai/linkedin-ads-mcp)
[![TikTok Marketing Partner](https://img.shields.io/badge/TikTok-Marketing%20Partner-000000)](https://paidsync.ai/tiktok-ads-mcp)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Star History Chart](https://api.star-history.com/svg?repos=paidsync/paidsync-mcp&type=Date)](https://star-history.com/#paidsync/paidsync-mcp&Date)

[paidsync.ai](https://paidsync.ai) · [Run Ads with AI](https://paidsync.ai/run-ads-with-ai) · [Compare](https://paidsync.ai/compare) · [Docs](https://paidsync.ai/docs) · [Pricing](https://paidsync.ai/pricing)

---

## What this is

Most MCP servers for ads are read-only. Google's native Google Ads MCP is read-only. ppc.io is read-only. GoMarble is read-only with write in private beta. Meta's AI Ads Connector edits Meta, nothing else.

PaidSync is the one MCP that lets AI act. Across four ad platforms (Google, Meta, LinkedIn, TikTok), three tracking platforms (Google Tag Manager, Google Analytics 4, Google Search Console), in one conversation.

That means your AI assistant does not just describe your campaigns. It pauses them. Creates them. Builds audiences. Sets up conversion tracking end to end. Compares ROAS across all four channels. In one chat.

---

## Who PaidSync is for

PaidSync was built for both ends of the paid media market.

**DTC and ecommerce brands** running their own ad spend across Meta, Google, and TikTok. One operator managing four ad platforms is a recipe for tab fatigue. PaidSync collapses the workflow. Ask Claude to audit, pause, and rebalance. Done in one chat.

**B2B agencies and consultants** managing 5 to 100+ client accounts. Multi-Client-Center support on Google Ads. Business Manager system user tokens on Meta. Advertiser switching on TikTok. Identity-walk authentication so one user can manage every account across multiple OAuth identities.

**In-house marketing teams** at SaaS, lead-gen, and high-consideration B2B brands who need conversion tracking across LinkedIn, Google, and Meta synchronized through GTM and GA4.

If you are running real ad spend and tired of switching tools to do basic optimization work, PaidSync is for you.

---

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

**Total: 309 executable tools** in a single MCP endpoint.

---

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

Once PaidSync is connected, paste any of these into Claude, ChatGPT, Gemini, or Cursor. See [examples/prompts.md](examples/prompts.md) for 30+ more.

### Cross-channel work

```
Compare ROAS across Google, Meta, LinkedIn, and TikTok for the last 30 days.
Pause the worst-performing campaign on each platform.
```

```
My Meta Ads ROAS just dropped 20%. Pull TikTok ROAS for the same date range
and product set. Should I shift budget?
```

### Conversion tracking setup (only PaidSync does this)

```
Set up purchase conversion tracking. Create the GA4 event, build the GTM tag
and trigger, and link it to Google Ads as a primary conversion.
```

### Account audits

```
Run a full audit on my Google Ads, Meta Ads, and LinkedIn Ads accounts.
Tell me where I am wasting budget on each.
```

### Paid plus organic blends

```
Show me Google Ads keywords I am paying for that I already rank organically
for in Search Console. Pause them if they are not converting.
```

### TikTok

```
Pause every TikTok ad group with CPA over $40 and less than 3 conversions
in the last 14 days.
```

### LinkedIn B2B

```
Compare LinkedIn cost-per-lead to Google Ads CPL for the same audience this quarter.
Where am I getting more in-target leads?
```

### Agency workflow

```
Switch to my client Google Ads MCC account, audit it, and email me a summary
of the top 3 issues by Monday morning.
```

---

## Real customer workflows

### DTC ecommerce brand, $80k/month Meta + Google spend

> Every Monday morning, I ask Claude to pull the previous week's spend, conversions, and ROAS across Meta and Google, broken down by campaign. Then I ask it to flag any campaigns where ROAS dropped 15% week over week, and to pause ad groups under 1.5x ROAS. Used to take 2 hours of clicking. Now takes 8 minutes.

### B2B SaaS, multi-touch attribution

> We run LinkedIn for awareness, Google Search for capture, and Meta retargeting. Conversion tracking used to be a disaster because nobody could see the full picture. PaidSync set up the GA4 events, built the GTM tags, and linked the conversions back to each ad platform. End to end, in one Claude conversation. Saved a week of dev work.

### Agency, 23 active clients across Google Ads MCC

> The identity walk is the killer feature. I log in to Claude once, and I have access to every client's Google Ads account through my MCC. Audit time per client used to be an hour. Now I run a multi-client audit prompt before my Wednesday strategy call and get all 23 reports back in ten minutes.

### Performance Max optimization

> PMax was a black box. PaidSync's PMax tools open up the asset group data, surface listing-group performance, and let me exclude underperforming products by offer ID directly from chat. Lifted ROAS from 4.1 to 5.7 over six weeks just by reading the asset group reports nobody was reading before.

---

## How PaidSync compares

| | PaidSync | Google native MCP | Meta AI Ads Connector | ppc.io | Pipeboard | Adspirer | Ryze AI | Flyweel |
|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| Google Ads edit | yes | no, read-only | no | no, read-only | yes | yes | yes | yes |
| Meta Ads edit | yes | no | yes Meta-only | no | yes | yes | yes | yes |
| LinkedIn Ads edit | yes | no | no | no | no | yes | partial | no |
| TikTok Ads edit | yes | no | no | no | no | yes | no | no |
| GTM edit | yes | no | no | no | no | no | no | no |
| GA4 edit | yes | no | no | no | no | no | partial | no |
| Search Console blend | yes | no | no | no | no | no | no | no |
| End-to-end conversion tracking | yes | no | no | no | no | no | no | no |
| Wasted-spend audits | yes | no | no | no | no | no | partial | no |
| PMax asset-group insights | yes | no | no | no | no | no | partial | no |
| Agency MCC support | yes | no | no | no | partial | yes | yes | no |
| MCP-based (any AI client) | yes | yes | yes | yes | yes | yes | no | yes |
| Free tier | yes | yes | yes | unknown | trial | trial | no | yes |

Full comparison: [paidsync.ai/compare](https://paidsync.ai/compare)

---

## Pricing

| Plan | Monthly | Annual | API calls/mo |
|---|---:|---:|---:|
| Free | $0 | n/a | 15 |
| Plus | $49 | $490 | 150 |
| Pro | $99 | $999 | 600 |
| Max | $199 | $2,000 | 4,000 |
| Team | Quote | Quote | Custom |
| Enterprise | Quote | Quote | Custom |

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

## Architecture

PaidSync is delivered as a hosted streamable-HTTP MCP server. The actual integrations sit on Google Cloud Run with session-affinity routing and per-platform OAuth identity stores in Firestore. The MCP endpoint is the single entry point. Every AI client speaks the same protocol.

### How a request flows

1. AI client (Claude, ChatGPT, Gemini) sends a tool call to `https://mcp.paidsync.ai/mcp`
2. PaidSync validates the API key, identifies the user, walks all connected OAuth identities for the target platform
3. The platform-specific client (Google Ads, Meta, LinkedIn, TikTok) executes against the user's active account or MCC
4. Mutating calls require explicit confirmation in the chat before the API mutation runs
5. Result returned to AI client, which surfaces it back to the user in natural language

### Per-platform notes

- **Google Ads**: Uses the Google Ads API with both `google-ads-api` library and `restQuery` / `restMutate` paths for resources the library does not support. Customer ID is required for every call. MCC walking is supported.
- **Meta (Facebook + Instagram)**: Long-lived tokens (~60 days). System User tokens supported alongside OAuth user tokens. All IDs are strings (Meta IDs are 18 digits and exceed JS safe integer range).
- **LinkedIn**: Refresh token model (60-day access, 365-day refresh). Pairs objective with `cost_type` at the campaign level.
- **TikTok**: Advertiser switching supported. App approval status is checked before write operations.
- **GTM**: Workspace-based change model. Tag, trigger, variable creates happen in a draft workspace, then `publish_gtm_version` ships the change.
- **GA4**: Property-level edit access. Audience and conversion-event mutations supported.
- **GSC**: Read-only by design. Used for paid plus organic blending against Google Ads keyword data.

### Confirmation flow

Every mutating tool (anything that creates, updates, pauses, or deletes) requires a confirmation step in the chat. The AI assistant cannot run a mutation without user approval. This is enforced server-side, not client-side.

### Security and authentication

- API keys (`ps_...`) for PaidSync dashboard users
- OAuth flows per platform with state validation
- Tokens encrypted at rest with AES-256-GCM
- Session affinity on Cloud Run (MCP is stateful per session)
- Per-platform scope hygiene: GTM dropped the `delete.containers` scope to shrink the consent screen
- No PaidSync employee can access user OAuth tokens (encrypted with per-environment keys)

Full technical docs at [paidsync.ai/docs](https://paidsync.ai/docs).

---

## Frequently asked questions

### Does PaidSync work with ChatGPT, or only Claude?

Both. PaidSync uses the open Model Context Protocol. It works with Claude (Desktop, web, Code), ChatGPT (Plus, Pro), Gemini, Cursor, Windsurf, Claude Code, and any future MCP-compatible AI assistant.

### Is there a free tier?

Yes. 15 API calls per month, all platforms included. Free tier is enough to test the connection and run a couple of audits. Paid plans start at $49/mo.

### Can the AI run wild and burn my ad spend?

No. Every mutating action (pause, create, update, delete) requires explicit confirmation in the chat. The AI proposes the action. You approve. The action runs. No mutations without your green light.

### Can I use PaidSync for client accounts as an agency?

Yes. Google Ads MCC, Meta Business Manager with System User tokens, LinkedIn Marketing Partner, TikTok advertiser switching. You connect once and access every client account from chat.

### What is the Model Context Protocol (MCP)?

MCP is an open standard, originally introduced by Anthropic, that lets AI assistants talk to external tools through a standardized interface. PaidSync is an MCP server. Your AI client is an MCP client. The standard means PaidSync works with any AI client that speaks MCP, not just Claude.

### How is PaidSync different from Adspirer or Ryze AI?

Adspirer covers Google, Meta, LinkedIn at a basic feature level. Ryze AI covers similar ground plus TikTok. PaidSync covers all four ad platforms plus end-to-end conversion tracking through GTM and GA4, plus paid + organic blending through Search Console. PaidSync is the only one with full LinkedIn write access. See the comparison table above or [paidsync.ai/compare](https://paidsync.ai/compare).

### How is PaidSync different from Google's native Google Ads MCP?

Google's native Google Ads MCP is read-only. PaidSync has full edit access on Google Ads (plus Meta, LinkedIn, TikTok, GTM, GA4). Read-only means the AI can describe what is wrong. PaidSync means the AI can also fix it.

### Can PaidSync set up conversion tracking?

Yes, end to end. Tell Claude what you want to track and on which page. PaidSync creates the GA4 event, builds the GTM tag and trigger, publishes the workspace, and links the conversion back to Google Ads (and Meta, LinkedIn, TikTok if applicable). No other MCP server does this.

### What about TikTok? Most MCPs skip it.

TikTok is a first-class platform in PaidSync. Full edit access, advertiser switching, performance reporting across age, gender, country, device, placement, and time. We are a TikTok Marketing Partner.

### Is my data safe?

Tokens are encrypted at rest with AES-256-GCM. OAuth state is validated. No PaidSync employee can access raw OAuth tokens. The product is built and audited by Ahmed Ashraf, a Google Premier Partner (top 3% globally) with a decade in paid media.

### Can I use it for a single brand or only for agencies?

Both. DTC brands managing their own spend get the same toolset as agencies managing 100+ clients. The agency-grade features (MCC, Business Manager, advertiser switching) are included in every plan, including free.

### What happens if PaidSync goes down?

PaidSync runs on Google Cloud Run with auto-scaling and session affinity. Status at status.paidsync.ai. Your ad accounts are unaffected. PaidSync is a layer on top of the platform APIs, not a replacement.

### Is there an API I can use without an AI assistant?

PaidSync is an MCP server. The MCP interface is the API. If you want raw HTTP access, you can call the MCP endpoint directly with any HTTP client. The underlying ad platform APIs are also accessible via PaidSync's `run_gaql_query` (Google Ads) and similar passthrough tools.

### How does PaidSync handle multiple ad accounts under one OAuth identity?

Identity walking. When you connect Google Ads, PaidSync discovers every account accessible via that OAuth identity, including all sub-accounts under any MCC. When you connect Meta, it discovers every ad account in every Business Manager you have access to. When you connect TikTok, every advertiser. You switch active account from chat (`set_active_account`, `set_active_tiktok_advertiser`, etc.) or run cross-account audits without switching.

---

## Roadmap

What is in development. No fixed dates, in priority order.

- **Operator agent**: a fully autonomous brand onboarding flow that takes a URL and stands up a complete paid media stack (Google + Meta + tracking) with approval gates. In beta at operator.paidsync.ai.
- **Pinterest Ads**: scoping the partner application
- **X (Twitter) Ads**: scoping
- **Reddit Ads**: scoping
- **Snapchat Ads**: scoping
- **More verticals in the audit layer**: real estate, automotive, fintech
- **Multi-brand workspaces**: shared API key with role-based access for agency teams
- **Self-hosted deployment**: enterprise plan, run PaidSync in your own cloud

---

## Acknowledgments

PaidSync builds on the open Model Context Protocol introduced by Anthropic. The MCP ecosystem is growing fast. We respect the other servers in this space, including:

- Google's native [Google Ads MCP](https://github.com/google-ads/google-ads-mcp)
- [Adspirer](https://www.adspirer.com/)
- [Ryze AI](https://www.get-ryze.ai/)
- [Flyweel](https://www.flyweel.co/)
- [Pipeboard](https://www.pipeboard.co/)
- [ppc.io](https://www.ppc.io/)
- [Synter](https://syntermedia.ai/)
- [Markifact](https://markifact.com/)

If you maintain an MCP server for ads or marketing and would like to be listed, open a PR.

---

## Partner credentials

- **Google Premier Partner**, founder Ahmed Ashraf (top 3% globally), $500M+ in ad spend managed across a decade in paid media
- **Meta Business Partner**, verified via Meta Marketing Partner Program
- **LinkedIn Marketing Partner**, full WRITE access (most MCPs do not have this)
- **TikTok Marketing Partner**, verified TikTok integration
- PaidSync is the only MCP server for advertising that holds verified status across all four ad platforms concurrently

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
- [Changelog](CHANGELOG.md) and [paidsync.ai/changelog](https://paidsync.ai/changelog)
- [llms.txt for AI engines](https://paidsync.ai/llms.txt) and [llms-full.txt](https://paidsync.ai/llms-full.txt)

---

## Connect

- Website: [paidsync.ai](https://paidsync.ai)
- Email: [support@paidsync.ai](mailto:support@paidsync.ai)
- LinkedIn: [PaidSync](https://www.linkedin.com/company/paidsync-ai/)
- Instagram: [@paidsync](https://www.instagram.com/paidsync)
- Founder LinkedIn: [Ahmed Ashraf](https://www.linkedin.com/in/ahmedashrafppc/)

---

## Contributing

This repo documents the hosted PaidSync MCP service. The MCP server code itself is closed source, but the example configurations, prompt library, and integration guides in this repo are open for contributions. See [CONTRIBUTING.md](CONTRIBUTING.md) for how to add a new client integration example, a prompt recipe, or a bug fix in the docs.

---

## License

MIT. See [LICENSE](LICENSE).

The PaidSync MCP service itself is a proprietary managed service. This repository documents how to use it, with example configurations and integration guides. No source code for the hosted server is included.

---

**Maintained by [PaidSync](https://paidsync.ai). Operated by Advanced Technology Labs LLC (Wyoming, USA).**
