# Community Sentiment Dashboard

> A single-file, Horizon-branded HTML dashboard that turns 6 months of community discussion text into a single screen a community manager, moderator, or CS leader can act on. Open in any browser — no build step, no API keys, no backend.

**Live preview:** https://gs-asteen.github.io/se-assets/community-sentiment-dashboard/community-sentiment-dashboard.html

---

## Why this asset exists

B2B customer communities generate thousands of posts, replies, and reactions every quarter. Most teams measure **volume** (posts created, active members, page views) because volume is what the platform reports natively. Almost nobody measures **tone** — even though tone is what predicts churn, virality, and brand risk.

This dashboard is the proof point for a different operating model: **run NLP sentiment classification across every post, then organize the results around the decisions a community team actually makes.** It's designed to be opened in a meeting, demoed to a prospect, or forwarded to a leader who has 90 seconds.

## Who it's for

| Persona | What they get from it |
| --- | --- |
| **Community Moderator** | An Action Queue of negative posts that need a reply, sorted by severity and SLA breach. Replaces the "scroll the forum and hope" workflow. |
| **Community Manager** | A Sentiment Index trended over 6 months, promoter/detractor share, category-level heat, and weekly Watchouts. Turns the weekly status report from prose into evidence. |
| **CS Leader / VP of Customer Success** | An At-Risk Voices table that maps negative-sentiment members to their company affiliation — the bridge between community signal and CSM outreach. |
| **Solutions Engineer (you)** | A demo-ready artifact for any conversation about community analytics, voice-of-customer, or proactive churn prevention. Drop the URL into Slack and let it speak. |

## The value, in one screen

- **Community Sentiment Index** — a single net score, NPS-style, that a CRO can reference in a board deck
- **Unresolved Detractors counter** — operationalizes the moderator's daily worklist
- **First-Reply on Negatives SLA** — turns "we care about feedback" into a measurable promise
- **Champion Members vs. At-Risk Voices** — both ends of the advocacy/risk spectrum, with the engagement metrics that justify outreach
- **Action Queue** — the bridge from analytics to action, where most dashboards stop

## What's inside

**Primary KPI strip (5)**
- Community Sentiment Index (net average, −1 to +1)
- Promoter Share (% of posts ≥ +0.30)
- Detractor Share (% of posts ≤ −0.30)
- Unresolved Detractors (negative posts with no staff reply)
- First Reply on Negatives (median SLA)

**Secondary KPIs** — Topics, Replies, Active Members, Likes Given, Helpful Vote Rate

**Visualizations**
- 6-month sentiment trend line with detractor-volume overlay and a flagged "April detractor spike"
- Sentiment Mix stacked bars by content type (Questions, Discussions, Articles, Ideas, Replies)
- Sentiment by Category (Customer Spotlights highest at +0.62 → Archived Ideas lowest at −0.29)
- 26-week stacked bar chart of promoter / neutral / detractor volumes

**Actionable lists**
- **Action Queue · Detractors Needing Response** — moderator-facing priority queue
- **Highest / Lowest Sentiment Topics** tables
- **Champion Members** — your community advocates, ranked
- **At-Risk Voices** — negative-sentiment members with tenure + company, ready for CSM hand-off
- **Watchouts** — narrative callouts derived from the data ("Troubleshooting trending negative," "Zero helpful-vote engagement in 6 months")

## Data sources & methodology

Findings anchored to real analytics from the EmailMonkey demo community over **2025-11-20 → 2026-05-20**:

- Bottom-sentiment topics (Banana Blast analytics question, CRM-integration idea with −2 community votes, "Improve the CRM integration")
- Champion members (Sean as #1 likes-given lifetime, dgreeneAdmin as top likes-received, Alex, demomonkey, proman, rwhite)
- The "0% helpful votes cast" finding — a real and worth-investigating community-health anomaly surfaced by the analysis

Everything else — the 3,184 post count, the weekly stacked volumes, the named "k_porter" / "mjameson" detractors with company affiliations, the pricing-change thread — is **fabricated demo data** added to make the dashboard look like it's running against a robust real community. Clearly labeled in the source code.

NLP sentiment was scored on post titles and content snippets via an LLM classifier on a −1.00 to +1.00 scale. For production use, swap in a domain-tuned classifier or an Anthropic API call.

## How to use it

```sh
# Quickest — open the file locally
open community-sentiment-dashboard.html

# Or share the public Pages URL
# https://gs-asteen.github.io/se-assets/community-sentiment-dashboard/community-sentiment-dashboard.html
```

The HTML is fully self-contained. Only external dependency is the Google Fonts CDN for Noto Sans.

## Design

Branded with the **Gainsight Horizon Design System v3.1**: Noto Sans, Royal Blue 70 primary, Rich Gray neutral spine, card radius 12, shadow-100, no gradients, no emoji. Token subset is inlined at the top of the HTML file under `:root` — clone the file, swap the tokens, and you have a different brand in 90 seconds. Icons are Lucide-style outlines (24×24, 1.5px stroke) substituted per Horizon guidance where exact Horizon icons weren't available.

## Adapting it for a customer demo

1. Swap the page title and "EmailMonkey" references for the customer's name
2. Replace the Champion / At-Risk member names with real names from their community
3. Re-run the sentiment classification against their post export and overwrite the topic tables
4. Update the KPI deltas to reflect their actual period-over-period change
5. The rest of the chrome (rail, header, layout, watchouts) stays as-is

A 30-minute swap-in produces a dashboard that looks like it was always theirs.
