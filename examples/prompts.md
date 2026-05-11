# PaidSync example prompts

Paste any of these into Claude, ChatGPT, Gemini, or Cursor once PaidSync is connected.

This file is organized by **workflow type** and **audience**. DTC brands and B2B agencies use PaidSync differently. Both are covered.

---

## Cross-channel work

```
Compare ROAS across Google, Meta, LinkedIn, and TikTok for the last 30 days.
Pause the worst-performing campaign on each platform.
```

```
My Meta Ads ROAS just dropped 20%. Pull TikTok ROAS for the same date range
and product set. Should I shift budget?
```

```
Build me a weekly cross-channel report. Spend, conversions, ROAS, and best-performing
ad per platform. Email me the summary every Monday.
```

```
Show me where I have overlapping audiences across Meta and Google. Where am I
paying for the same user twice in one week?
```

```
What was my total ad spend across all 4 platforms last month? Break it down by
platform, then by campaign, then by ad group. Show me the top 10 line items
by spend.
```

```
Across Meta, Google, LinkedIn, and TikTok, which campaigns had the biggest
week-over-week ROAS drop? Pause anything that fell more than 30%.
```

---

## End-to-end conversion tracking (PaidSync-only)

```
Set up purchase conversion tracking. Create the GA4 event, build the GTM tag
and trigger, and link it to Google Ads as a primary conversion.
```

```
Set up the TikTok Pixel purchase event in GTM, fire it on /thank-you,
link it back to my TikTok ad account as the optimization event.
```

```
Build a lead form conversion event in GA4 for the demo-request button.
Build the GTM tag, trigger on click of #book-demo-cta, link it to LinkedIn Ads
and Google Ads as a primary conversion.
```

```
Audit my current conversion tracking across Google Ads, Meta, LinkedIn, and
TikTok. Tell me where I have duplicate events firing, missing events, or
events that are firing but not getting credit.
```

```
Set up a server-side Meta CAPI conversion for purchase. Mirror the existing
client-side Pixel event. Use the same event_id so they deduplicate.
```

---

## Account audits

```
Run a full audit on my Google Ads, Meta Ads, and LinkedIn Ads accounts.
Tell me where I am wasting budget on each.
```

```
Audit my GTM container. Find tags that are not firing, triggers without tags,
and any GA4 events not flowing through.
```

```
Run a Google Ads quality score audit. List every keyword below 5 with the
matching ad copy. Suggest fixes.
```

```
Audit my Meta account structure. Flag ad sets with audience overlap, broken
Pixel events, and any ad set where CPM has risen more than 50% in the last
14 days.
```

```
Find every Google Ads ad group with zero conversions in the last 30 days
but more than $200 in spend. Pause them and tell me the total savings.
```

```
Scan my LinkedIn campaigns for cost-per-lead anomalies. Flag any campaign
where CPL is more than 2x the account average.
```

---

## Paid plus organic blends

```
Show me Google Ads keywords I am paying for that I already rank organically
for in Search Console. Pause them if they are not converting.
```

```
List the top 20 organic queries in GSC that are NOT in my Google Ads keyword
list. Suggest which ones to add as paid bids.
```

```
For every keyword where I rank position 1 to 3 organically, calculate how
much I am wasting on Google Ads paid clicks for the same query.
```

---

## Google Ads

```
Pause all ad groups with CPA above $50 and less than 5 conversions
in the last 30 days.
```

```
Add the top 20 negative keywords from last week's search terms report
across all campaigns.
```

```
Open my PMax black box. Which asset groups are rated Poor and which
audience signals are driving them?
```

```
Build a search campaign for "AI ad management" keywords. Target conversions.
$50/day. Use my existing "Software Buyers - US" audience signal.
```

```
Show me the auction insights for my top spending campaign. Which competitors
are outranking me most often?
```

```
Find my Performance Max campaigns where the listing group shows one or two
products eating 80% of the budget. Tell me the offer IDs to exclude.
```

```
List every Google Ads campaign with a target CPA but no recent conversions.
Switch them to Manual CPC until conversion volume returns.
```

```
Pull my top 50 search terms from the last 30 days, sort by spend, flag any
that are not in my keyword list as candidates to add or block.
```

---

## Meta Ads (Facebook + Instagram)

```
Audit my Meta Ads account. Find ad sets with high CPM and zero conversions
in the last 14 days. Pause them.
```

```
Build a 1% lookalike on Meta from my top 10% LTV customer list. Then create
a 3% expansion lookalike from the same source.
```

```
Find creative fatigue on my Instagram ads. Which ads had strong CTR week one
but dropped 30%+ by week three?
```

```
Switch my Meta Advantage+ Shopping campaign to use a higher daily budget.
Increase from $200 to $400. Confirm before applying.
```

```
Show me Meta ad sets where the audience overlap with another active ad set
is over 30%. Tell me which one to consolidate.
```

```
List every Meta campaign currently running, sort by spend, show me the top
3 ads in each. Flag any where ROAS is below 1.5x.
```

```
Audit my Meta Pixel events. Are purchase, add-to-cart, and initiate-checkout
all firing on the right pages? Are there duplicate events?
```

```
Build a Meta retargeting ad set for site visitors who viewed the pricing
page in the last 14 days but did not sign up. Use Advantage placements.
$50/day budget.
```

---

## LinkedIn Ads

```
Show me my LinkedIn campaign performance for Q2. Sort by cost-per-lead.
Pause anything above $200 CPL with no closed deals.
```

```
Build a LinkedIn campaign group for SaaS founders at companies with 10-50
employees in the US. Job title: Founder, CEO. $500/day budget.
```

```
Compare LinkedIn cost-per-lead to Google Ads cost-per-lead for the same
audience this quarter. Where am I getting more in-target leads?
```

```
List every LinkedIn campaign where the LinkedIn Insight Tag is not firing
the conversion event. Tell me which campaigns have broken tracking.
```

```
Build a LinkedIn lead gen form for my "Enterprise Demo Request" offer.
Standard fields: name, email, company size, job title.
```

```
Show me LinkedIn ad creative performance broken down by industry. Which
creative variants work for software companies vs financial services?
```

---

## TikTok Ads

```
Show me my TikTok performance for the last 30 days. Which ad groups have
the lowest CPA?
```

```
Pause every TikTok ad group with CPA over $40 and less than 3 conversions
in the last 14 days.
```

```
Switch to my client TikTok advertiser account, list active campaigns, and pause
anything spending more than $200/day with no conversions this week.
```

```
Break down my TikTok ad performance by age, gender, and country. Which
demographic is driving the best ROAS?
```

```
List every TikTok ad group where the optimization event is "click" but I
have purchase conversions tracking. Switch to "complete payment" optimization
where it makes sense.
```

```
Build a TikTok Spark Ads campaign promoting my top organic post from last
week. Use my existing custom audience of website visitors.
```

---

## DTC brand workflows

```
Every Monday: pull total spend, conversions, ROAS, and ROAS by platform
for last week vs the week before. Show me the deltas. Pause anything
that dropped 20%+ in ROAS.
```

```
I am running a 25% off sale on Black Friday. Build the campaigns:
Google Search for branded + non-branded, Meta retargeting for cart
abandoners, TikTok for cold acquisition. Use my existing conversion
events. $500/day budget total.
```

```
My average order value just changed from $80 to $120. Update my ROAS
targets across Meta, Google, and TikTok to maintain a 4x return on
new gross margin.
```

```
Find my top 10 best-selling products in Shopify (assume Merchant Center
sync is connected). Then check which of those products are getting the
most ad impressions across Meta and Google. Are they aligned?
```

---

## B2B SaaS workflows

```
I am a B2B SaaS company. Build my full conversion tracking from scratch.
Free trial signup is the primary event. Demo request is secondary. Paid
plan upgrade is the lifetime value event. Wire it all through GA4 and GTM.
Link the conversions back to Google Ads, LinkedIn, and Meta.
```

```
Across LinkedIn, Google Ads, and Meta retargeting, which channel is bringing
in the most demo requests this month? Calculate cost-per-demo and cost-per-
qualified-lead for each. Flag any channel where the qualified-lead rate is
below 10%.
```

```
My MQL to SQL conversion rate dropped from 35% to 22% last month.
Cross-reference the leads with the source channel and creative variant.
Tell me where the quality dropped.
```

---

## Agency workflows

```
Switch to my client Google Ads MCC account, audit it, and email me a summary
of the top 3 issues by Monday morning.
```

```
List every TikTok campaign across all of my advertisers. Sort by spend descending.
```

```
Run a full audit across all of my agency client accounts. Rank them by
total wasted spend. Email me the top 5 issues per client.
```

```
For my client "AcmeCorp", pull last quarter's performance across Google
Ads, Meta, and LinkedIn. Build a one-page report I can send to their CMO.
```

```
Across all my MCC client accounts, find any campaign where the daily budget
has not changed in 30+ days but spend has grown more than 20%. Flag for
budget review.
```

```
Build a new client onboarding plan. Connect their Google Ads, Meta, and
LinkedIn. Run the initial audit. Generate the kickoff report. Schedule
the first optimization sprint.
```

```
List every active Meta campaign across all of my Business Manager accounts.
Sort by ROAS. Flag the bottom 10% for review.
```

```
I have a strategy call with one of my clients in 20 minutes. Pull their
top 3 wins from last week, top 3 issues this week, and the top 3 actions
I am proposing. Format it as a one-page memo.
```

---

## Reporting and ops

```
Build me a weekly Slack-ready summary: spend per platform, ROAS delta,
top performing creative, top issue flagged. Run every Monday at 8 AM UTC.
```

```
Generate a quarterly business review deck for "AcmeCorp" covering Q2.
Spend trends, ROAS by channel, top performing creative, conversion
attribution. Compare to Q1 and Q4 last year.
```

```
List every conversion goal in my Google Ads account and tell me which
ones are using "Maximize Conversions" but should be using "Target CPA"
based on recent volume.
```

---

## Debugging and troubleshooting

```
My Meta Pixel says purchase events stopped firing yesterday. Tell me which
specific events are missing and on which pages. Cross-check against GTM
to see if a tag was disabled.
```

```
A Google Ads campaign that ran fine last month is suddenly getting 0
impressions. Check the policy status, bid strategy, budget, and ad
group eligibility. Tell me what is broken.
```

```
LinkedIn says my campaign is "Active" but I see 0 spend in the last 5 days.
Check the daily budget, total budget, schedule, and audience size. What
is suppressing delivery?
```

```
Compare my Google Ads conversion count to my GA4 conversion count for the
same date range. Why is there a 30% discrepancy?
```

---

## Composite workflows (multi-step in one prompt)

```
End-of-day routine: pull today's spend across all 4 platforms. Compare to
the 30-day daily average. Flag anything more than 2 standard deviations
above or below. Pause any campaign where today's CPA is 50%+ above its
30-day average.
```

```
Quarterly cleanup: list every campaign across all platforms that spent
less than $50 in the last 90 days. List every keyword in Google Ads with
less than 10 impressions in 90 days. List every Meta ad set with zero
spend. Show me everything as candidates to archive.
```

```
New product launch: I am launching "Product X" next Tuesday. Build the
campaign on Google Search, Meta, and TikTok. Use my standard "New Launch"
templates. Set up the conversion event for purchases of Product X
specifically (filter by SKU). Wire the conversion through GTM and GA4
back to all 3 platforms. Schedule it to go live Tuesday 9 AM UTC.
```

---

## How to write your own

The pattern that works:

1. **State the trigger**: "Every Monday morning..." or "When ROAS drops 20%..."
2. **State the scope**: which platform, which date range, which campaigns
3. **State the action**: pause, create, audit, report
4. **State the safeguard**: "Confirm before applying" or "Show me first"

Avoid:

- Vague queries like "optimize my ads". AI cannot interpret that. Be specific about platforms, metrics, and thresholds.
- Open-ended commands without thresholds. "Pause underperformers" is fuzzy. "Pause ad groups with CPA above $50 and less than 5 conversions in 30 days" is actionable.
- Compound mutations without confirmation. Always include "Confirm before applying" or "Show me first" for high-impact actions.

See [paidsync.ai/docs/prompts](https://paidsync.ai/docs/prompts) for the full prompt library.
