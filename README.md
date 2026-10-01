# PaidSync. The MCP for Running Ads with AI

> PaidSync connects Claude, ChatGPT and other AI assistants to your ad accounts. It builds new campaigns on Google Ads, Meta, LinkedIn and ChatGPT Ads, and manages existing campaigns on TikTok, Microsoft, Snapchat, Reddit, Pinterest and X. Plus Google Analytics 4, Google Tag Manager, Search Console (read-only) and Merchant Center. 610+ tools across 14 platforms.

[![Google Partner](https://img.shields.io/badge/Google-Partner-4285F4)](https://paidsync.ai/google-ads-mcp)
[![Meta Business Partner](https://img.shields.io/badge/Meta-Business%20Partner-1877F2)](https://paidsync.ai/meta-ads-mcp)
[![TikTok Marketing Partner](https://img.shields.io/badge/TikTok-Marketing%20Partner-000000)](https://paidsync.ai/tiktok-ads-mcp)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Star History Chart](https://api.star-history.com/svg?repos=paidsync/paidsync-mcp&type=Date)](https://star-history.com/#paidsync/paidsync-mcp&Date)

[paidsync.ai](https://paidsync.ai) · [Run Ads with AI](https://paidsync.ai/run-ads-with-ai) · [Compare](https://paidsync.ai/compare) · [Docs](https://paidsync.ai/docs) · [Pricing](https://paidsync.ai/pricing)

---

## What this is

PaidSync is a hosted MCP server that lets your AI assistant act on your ad accounts, not just describe them. One connection covers ten ad platforms (Google Ads, Meta, LinkedIn, ChatGPT Ads, TikTok, Microsoft, Snapchat, Reddit, Pinterest and X) plus four measurement and tracking platforms (Google Analytics 4, Google Tag Manager, Google Search Console and Google Merchant Center).

On Google Ads, Meta, LinkedIn and ChatGPT Ads it builds new campaigns. On TikTok, Microsoft, Snapchat, Reddit, Pinterest and X it manages the campaigns you already run there. Search Console is read-only in PaidSync.

PaidSync changes campaign settings only. It never moves money or processes payments, and billing stays directly between you and each ad platform.

---

## Who PaidSync is for

PaidSync was built for both ends of the paid media market.

**DTC and ecommerce brands** running their own ad spend across Meta, Google, TikTok, Pinterest, and Snapchat. One operator managing that many ad platforms is a recipe for tab fatigue. PaidSync collapses the workflow. Ask Claude to audit, pause, and rebalance. Done in one chat.

**B2B agencies and consultants** managing 5 to 100+ client accounts. Multi-Client-Center support on Google Ads. Business Manager system user tokens on Meta. Advertiser switching on TikTok. Identity-walk authentication so one user can manage every account across multiple OAuth identities.

**In-house marketing teams** at SaaS, lead-gen, and high-consideration B2B brands who need conversion tracking across LinkedIn, Google, and Meta synchronized through GTM and GA4.

If you are running real ad spend and tired of switching tools to do basic optimization work, PaidSync is for you.

---

### Ad platforms (10)

| Platform | Tools | Capability | Partner status |
|---|---:|---|---|
| Google Ads | 152 | Builds new campaigns and manages existing ones (incl. MCC) | **Google Partner** |
| Meta Ads (Facebook + Instagram) | 83 | Builds new campaigns and manages existing ones (incl. Business Manager system user tokens) | **Meta Business Partner** |
| LinkedIn Ads | 34 | Builds new campaigns and manages existing ones (campaign groups, campaigns and Sponsored Content ads start as drafts) | n/a |
| ChatGPT Ads | 28 | Builds new campaigns and manages existing ones | n/a |
| TikTok Ads | 13 | Manages existing campaigns (create in TikTok Ads Manager) | **TikTok Marketing Partner** |
| Snapchat Ads | 15 | Manages existing campaigns (create in Snapchat Ads Manager) | n/a |
| Reddit Ads | 14 | Manages existing campaigns (create in Reddit Ads Manager) | n/a |
| Pinterest Ads | 14 | Manages existing campaigns (create in Pinterest Ads Manager) | n/a |
| X Ads | 14 | Manages existing campaigns (create in X Ads Manager) | n/a |
| Microsoft Ads (Bing) | 133 | Manages existing campaigns (create in Microsoft Ads) | n/a |

### Measurement and tracking platforms (4)

| Platform | Tools | Capability |
|---|---:|---|
| Google Analytics 4 | 26 | Reports, plus changes you ask for such as key events, custom dimensions and Google Ads links |
| Google Tag Manager | 39 | Reads and changes tags, triggers, variables and workspaces; publishes only when you confirm |
| Google Search Console | 6 | Read-only in PaidSync (paid plus organic reporting) |
| Google Merchant Center | 16 | Products, supplemental feeds and Google Ads links |

**Total: 610+ executable tools** across 14 platforms in a single MCP endpoint. The platform rows add up to fewer than 610 because some tools, such as connect, account and cross-channel report tools, belong to no single platform.

New campaigns are built on Google Ads, Meta, LinkedIn and ChatGPT Ads. On the other six ad platforms PaidSync manages the campaigns you create in their own ad managers. PaidSync is honest about the line so your AI assistant never promises an action the platform does not expose.

---

## Quick start

### In Claude

1. Open PaidSync in Claude's connector directory: [claude.ai/directory/connectors/paidsync-mcpp](https://claude.ai/directory/connectors/paidsync-mcpp) and click Connect.
2. Sign in to PaidSync (free, no card) and approve.
3. Connect your ad account and ask.

### In ChatGPT

1. Open Plugins in ChatGPT, search PaidSync and install: [PaidSync in ChatGPT](https://chatgpt.com/plugins/plugin_asdk_app_6a2da571f8f88191a20309aa4d11fdfc).
2. Sign in and approve.
3. Connect your ad account and ask.

### Any other MCP client

Add `https://mcp.paidsync.ai/mcp` as a custom connector (streamable HTTP) and sign in when your client asks. No API key is needed.

Free for 15 tasks a month with no credit card, then priced by usage, from $99 a month for 600 tasks.

---

## Agent-native architecture with a thin dispatcher

610+ tools is a lot of surface area. Loading every tool schema into the model's context the moment you connect would burn a large share of the context window before you have typed a single prompt.

PaidSync does the opposite. The whole catalog sits behind three meta-tools:

- **`paidsync_context`** returns the live map of what is connected and which capabilities are available.
- **`paidsync_tool_detail`** pulls the schema for one specific tool only when the model needs it.
- **`paidsync_exec`** runs the chosen tool.

The model discovers tools on demand and spends the rest of its context budget on your actual work, not on schema it will never call. The 610+ tools are real and executable. They are simply not all dumped into the conversation at once.

---

## Example prompts

Once PaidSync is connected, paste any of these into Claude, ChatGPT, Claude Code or Cursor. See [examples/prompts.md](examples/prompts.md) for 30+ more.

### Cross-channel work

```
Compare ROAS across Google, Meta, LinkedIn, and TikTok for the last 30 days.
Pause the worst-performing campaign on each platform.
```

```
My Meta Ads ROAS just dropped 20%. Pull TikTok ROAS for the same date range
and product set. Should I shift budget?
```

### Conversion tracking setup

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
Switch to my client Google Ads MCC account, audit it, and list the top 3 issues.
```

---

## How PaidSync compares

For a side-by-side view of PaidSync and other ad connectors, see [paidsync.ai/compare](https://paidsync.ai/compare).

---

## Pricing

| Plan | Price | Tasks a month |
|---|---:|---:|
| Free | $0, no credit card | 15 |
| Pro | $99 a month, $149 or $199 for larger tiers, or $999 billed yearly for 600 | 600, 1,200 or 4,000 |
| Team | from $249 a month | shared across seats |
| Done For You | Quote | Custom |

All 14 platforms (Google Ads, Meta, LinkedIn, ChatGPT Ads, TikTok, Microsoft, Snapchat, Reddit, Pinterest, X, GA4, GTM, Search Console, Merchant Center) are on every plan, including Free. MCC and Business Manager support start on Pro.

[Start free at paidsync.ai/signup](https://paidsync.ai/signup)

---

## Architecture

PaidSync is delivered as a hosted streamable-HTTP MCP server. The actual integrations sit on Google Cloud Run with session-affinity routing and per-platform OAuth identity stores in Firestore. The MCP endpoint is the single entry point. Every AI client speaks the same protocol.

### How a request flows

1. An AI client (for example Claude or ChatGPT) sends a tool call to `https://mcp.paidsync.ai/mcp`
2. PaidSync checks the signed-in user, then walks all connected OAuth identities for the target platform
3. The platform-specific client (Google Ads, Meta, LinkedIn, TikTok) executes against the account you named or your active account
4. Result returned to the AI client, which surfaces it back to the user in natural language

### Per-platform notes

- **Google Ads**: Uses the Google Ads API with both `google-ads-api` library and `restQuery` / `restMutate` paths for resources the library does not support. Customer ID is required for every call. MCC walking is supported.
- **Meta (Facebook + Instagram)**: Long-lived tokens (~60 days). System User tokens supported alongside OAuth user tokens. All IDs are strings (Meta IDs are 18 digits and exceed JS safe integer range).
- **LinkedIn**: Refresh token model (60-day access, 365-day refresh). Pairs objective with `cost_type` at the campaign level. New campaign groups, campaigns and Sponsored Content ads are created as drafts by default.
- **TikTok**: Advertiser switching supported. App approval status is checked before write operations.
- **GTM**: Workspace-based change model. Tag, trigger, variable creates happen in a draft workspace, then `publish_gtm_version` ships the change.
- **GA4**: Reads reports through the Data API and makes the admin changes you ask for, such as marking key events, through the Admin API.
- **Search Console**: Read-only in PaidSync. Used for paid plus organic blending against Google Ads keyword data.

### Changes and approvals

PaidSync changes campaign settings only. It never moves money or processes payments. New LinkedIn campaign groups, campaigns and Sponsored Content ads are created as drafts by default, so nothing spends until you turn it on. In Claude you can also set each PaidSync tool to "Needs approval" under Settings, Connectors, so every change waits for your click.

### Security and authentication

- OAuth 2.0 sign-in for AI clients; no API key to paste
- OAuth flows per platform with state validation
- Tokens encrypted at rest with AES-256-GCM
- Session affinity on Cloud Run (MCP is stateful per session)
- Per-platform scope hygiene: GTM dropped the `delete.containers` scope to shrink the consent screen

Full technical docs at [paidsync.ai/docs](https://paidsync.ai/docs).

---

## Frequently asked questions

### Does PaidSync work with ChatGPT, or only Claude?

Both. PaidSync is in Claude's connector directory and in ChatGPT's plugins. It uses the open Model Context Protocol, so it also works with other MCP clients such as Claude Code, Cursor and Codex.

### Is there a free tier?

Yes. Free for 15 tasks a month with no credit card, then priced by usage, from $99 a month for 600 tasks. All 14 platforms are included.

### Can the AI run wild and burn my ad spend?

PaidSync changes campaign settings only and never moves money. New LinkedIn campaign groups, campaigns and Sponsored Content ads start as drafts, so nothing spends until you turn it on. In Claude you can set each PaidSync tool to "Needs approval", so every change waits for your click.

### Can I use PaidSync for client accounts as an agency?

Yes. Google Ads MCC, Meta Business Manager with System User tokens, LinkedIn campaign building, TikTok advertiser switching. You connect once and access every client account from chat.

### What is the Model Context Protocol (MCP)?

MCP is an open standard, originally introduced by Anthropic, that lets AI assistants talk to external tools through a standardized interface. PaidSync is an MCP server. Your AI client is an MCP client. The standard means PaidSync works with any AI client that speaks MCP, not just Claude.

### How is PaidSync different from other ad connectors?

PaidSync covers ten ad platforms plus Google Analytics 4, Google Tag Manager, Search Console and Merchant Center in one connection, and builds new campaigns on Google Ads, Meta, LinkedIn and ChatGPT Ads. For a side-by-side view, see [paidsync.ai/compare](https://paidsync.ai/compare).

### How is PaidSync different from Google's native Google Ads MCP?

Google's native Google Ads MCP is read-only. PaidSync builds and changes Google Ads campaigns, and does the same on Meta, LinkedIn and ChatGPT Ads. Read-only means the AI can describe what is wrong. PaidSync means the AI can also fix it.

### Can PaidSync set up conversion tracking?

Yes. Tell Claude what you want to track and on which page. PaidSync creates the GA4 event, builds the GTM tag and trigger, publishes the workspace when you confirm, and links the conversion back to Google Ads.

### What about TikTok?

PaidSync manages existing TikTok campaigns with 13 tools (pause, enable, budgets, bids and names) next to Google, Meta and LinkedIn in one chat, with advertiser switching and performance reporting. We are a TikTok Marketing Partner.

### Is my data safe?

Tokens are encrypted at rest with AES-256-GCM, and OAuth state is validated. Changes run as a dry-run preview by default, and deletes and pauses need an explicit confirmation. PaidSync is built by Ahmed Ashraf, who has spent 10+ years in paid media.

### Can I use it for a single brand or only for agencies?

Both. DTC brands managing their own spend get the same toolset as agencies managing 100+ clients. MCC and Business Manager support start on the Pro plan.

### What happens if PaidSync goes down?

PaidSync runs on Google Cloud Run with auto-scaling and session affinity. Your ad accounts are unaffected. PaidSync is a layer on top of the platform APIs, not a replacement.

### Is there an API I can use without an AI assistant?

PaidSync is an MCP server. The MCP interface is the API. If you want raw HTTP access, you can call the MCP endpoint directly with any HTTP client. The underlying ad platform APIs are also accessible via PaidSync's `run_gaql_query` (Google Ads) and similar passthrough tools.

### How does PaidSync handle multiple ad accounts under one OAuth identity?

Identity walking. When you connect Google Ads, PaidSync discovers every account accessible via that OAuth identity, including all sub-accounts under any MCC. When you connect Meta, it discovers every ad account in every Business Manager you have access to. When you connect TikTok, every advertiser. You name the account in your question, switch the active account from chat (`set_active_account`, `set_active_tiktok_advertiser`, etc.), or run cross-account audits without switching.

---

## Acknowledgments

PaidSync builds on the open Model Context Protocol introduced by Anthropic. The MCP ecosystem is growing fast. We respect the other servers in this space, including:

- Google's native [Google Ads MCP](https://github.com/googleads/google-ads-mcp)
- [Adspirer](https://www.adspirer.com/)
- [Ryze AI](https://www.get-ryze.ai/)
- [Flyweel](https://www.flyweel.co/)
- [Pipeboard](https://www.pipeboard.co/)
- [ppc.io](https://www.ppc.io/)
- [Synter](https://syntermedia.ai/)
- [Markifact](https://markifact.com/)

---

## Partner credentials

- Founder Ahmed Ashraf is a **Google Premier Partner**, with $500M+ in ad spend managed across a decade in paid media
- PaidSync (the company) is a **Google Partner**
- **Meta Business Partner**
- **TikTok Marketing Partner**

---

## Documentation and resources

- [Run Ads with AI](https://paidsync.ai/run-ads-with-ai), the overview page
- [Google Ads MCP details](https://paidsync.ai/google-ads-mcp)
- [Meta Ads MCP details](https://paidsync.ai/meta-ads-mcp)
- [LinkedIn Ads MCP details](https://paidsync.ai/linkedin-ads-mcp)
- [TikTok Ads MCP details](https://paidsync.ai/tiktok-ads-mcp)
- [Comparison: PaidSync and other MCP ad servers](https://paidsync.ai/compare)
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
- Founder LinkedIn: [Ahmed Ashraf](https://www.linkedin.com/in/ahmeddashraaf/)

---

## Contributing

This repo documents the hosted PaidSync MCP service. The MCP server code itself is closed source, but the example configurations, prompt library, and integration guides in this repo are open for contributions. See [CONTRIBUTING.md](CONTRIBUTING.md) for how to add a new client integration example, a prompt recipe, or a bug fix in the docs.

---

## License

MIT. See [LICENSE](LICENSE).

The PaidSync MCP service itself is a proprietary managed service. This repository documents how to use it, with example configurations and integration guides. No source code for the hosted server is included.

---

**Maintained by [PaidSync](https://paidsync.ai). Operated by Advanced Technology Labs LLC (Wyoming, USA).**
