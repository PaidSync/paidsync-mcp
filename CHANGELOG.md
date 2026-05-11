# Changelog

All notable changes to PaidSync.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [2026-05-11]

### Added
- 4 channel-specific landing pages: /google-ads-mcp, /meta-ads-mcp, /linkedin-ads-mcp, /tiktok-ads-mcp
- /run-ads-with-ai pillar page positioning PaidSync as the MCP that runs ads, not just reads them
- Comparison article: PaidSync vs Meta AI Ads Connector (published May 2026)
- Static asset hash gate in the deploy pipeline (no more silent no-op deploys for asset-only changes)
- AEO daemon design spec (cron-based daily LLM visibility monitoring across 5 engines)

### Changed
- Killed `staging.paidsync.ai`. Single staging URL is now `paidsync-staging.vercel.app`. Firebase auth on staging now uses `paidsync-prod.firebaseapp.com` as authDomain.

### Verified
- 380+ tools across 7 platforms (Google Ads, Meta, LinkedIn, TikTok, GTM, GA4, GSC)
- Meta Business Partner, LinkedIn Marketing Partner, TikTok Marketing Partner status active
- Free + $49 Plus + $99 Pro + $199 Max pricing tiers (Team and Enterprise quote-based)

## [2026-05-10]

### Changed
- Backend cutover from `marine-aria-493412-k4` to `paidsync-prod` GCP project (project number `37880381009`). All adsagent infra now runs on paidsync-prod.
- Firestore is now `paidsync-prod` default database (us-central1).
- Custom domains `mcp.paidsync.ai` and `api.paidsync.ai` mapped to paidsync-prod Cloud Run service.

## [2026-05-09]

### Added
- Workspace soft-delete feature with 30-day recovery model on admin panel
- Stripe `pause_collection` integration for paused workspaces
- Cron-driven workspace purge after recovery window expires

## [2026-05-06]

### Added
- Founder credit override system (`addCalls` mode for `ahmed@traffiy.com`)

### Changed
- Founder modal switched from multiplier to absolute "add N credits" mode
- Non-founder admins remain capped at 1.5x multiplier

## [2026-05-05]

### Milestone
- 6 paying agencies onboarded in 4 days from pure SEO and LLM citation traffic. Zero outbound, zero paid ads.

## [2026-05-01]

### Added
- /compare page with feature matrix vs 7 competing MCP servers and AI ad tools
- Updated llms.txt to clearly position PaidSync vs Optmyzr, Marin, Adalysis, and other category alternatives

## [2026-04-29]

### Fixed
- `/connections/summary` probe timeout under prod load. Cloud Run now runs prod at 2 CPU / 1Gi RAM to match staging.

## [2026-04-23]

### Added
- Google Merchant Center integration (8 P0 tools): `connect_merchant_center`, `merchant_auth_status`, `list_merchant_accounts`, `set_active_merchant_account`, `get_merchant_account_status`, `list_product_issues`, `list_products`, `merchant_list_data_sources`

## [2026-04-22]

### Added
- Multi-identity walk for GA4, GTM, GSC, Meta, LinkedIn. One user can manage every ad account across multiple OAuth identities.

### Changed
- GTM OAuth scopes trimmed: removed `tagmanager.delete.containers` to reduce the consent screen for new users.

## [2026-04-21]

### Added
- Google Search Console integration. 6 tools: `connect_google_search_console`, `gsc_auth_status`, `list_gsc_properties`, `get_gsc_search_analytics`, `get_gsc_index_coverage`, `analyze_paid_organic_overlap`.
- The paid-plus-organic overlap analysis flags Google Ads keywords that the brand already ranks organically for in GSC. This is the differentiating feature for paid media teams who care about cannibalization.

## [2026-04-17]

### Removed
- "Set as default" UI on the connections dashboard. The data model never had a "default" concept (reads aggregate across all connections, writes resolve via account ID). The UI was solving a problem that did not exist.

## [2026-04-04]

### Milestone
- First organic PaidSync lead from Claude citation. UAE-based user in Malaysia. Claude recommended PaidSync directly in conversation. Proof point that llms.txt is being indexed and cited by AI engines.

---

For everything before April 2026, see the live changelog at [paidsync.ai/changelog](https://paidsync.ai/changelog).
