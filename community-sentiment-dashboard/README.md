# Community Sentiment Dashboard

A single-file HTML dashboard summarizing 6 months of community sentiment for a sample B2B customer community (EmailMonkey). Built against the **Gainsight Horizon Design System v3.1** — Noto Sans, Royal Blue 70 primary, Rich Gray neutral spine, card radius 12, shadow-100.

## How to view

Open `community-sentiment-dashboard.html` in any modern browser. The file is fully self-contained — the only external dependency is the Google Fonts CDN for Noto Sans, so it works offline once the font is cached.

```sh
open community-sentiment-dashboard.html
```

To share with your team without a browser preview, host it via GitHub Pages (Settings → Pages → Deploy from `main`) and the file will render at a public URL.

## What's in it

**Primary KPIs** — the row a community manager scans first:
- Community Sentiment Index (net average, NPS-style)
- Promoter Share (posts ≥ +0.30)
- Detractor Share (posts ≤ −0.30)
- Unresolved Detractors (the moderator's worklist counter — negative posts with no staff reply)
- First Reply on Negatives (median SLA)

**Sections**
- Sentiment trend line over 6 months, with detractor-volume overlay
- Sentiment mix stacked bars by content type
- Sentiment by category (highest → lowest)
- Action Queue — moderator-facing priority list of negative posts needing response
- Highest / Lowest Sentiment Topics tables
- Champion Members (positive sentiment leaders — community advocates)
- At-Risk Voices (negative sentiment members with company affiliation — CSM hand-off candidates)
- Weekly stacked bar chart of promoter / neutral / detractor volumes
- Watchouts card with narrative callouts

## Data sources

The findings anchored to real analytics from the EmailMonkey community over **2025-11-20 → 2026-05-20**:

- Bottom-sentiment topics (Banana Blast analytics question, CRM-integration idea with −2 community votes, customer spotlight)
- Champion members (Sean as top likes-given, dgreeneAdmin as top likes-received, Alex, demomonkey, proman, rwhite)
- The "0% helpful votes cast" anomaly — a real and worth-investigating finding

Everything else — the 3,184 post count, the weekly stacked volumes, the named "k_porter" and "mjameson" detractors with company affiliations, the pricing-change thread — is **fabricated demo data** to make the dashboard look like it's running against a robust real community.

## Design system

Branded with [Gainsight Horizon Design System v3.1](https://www.gainsight.com/). Token subset is inlined at the top of the HTML file under `:root`. Icon set substituted with Lucide-style outlines (24×24, 1.5px stroke) per Horizon guidance when exact icons weren't available.

## Persona use cases

- **Community moderator** — Action Queue + Unresolved Detractors KPI + First-Reply SLA
- **Community manager** — Sentiment Index + Promoter/Detractor share + Category trends + Watchouts
- **CS leader** — At-Risk Voices table (member ↔ company mapping for outreach), Champion Members for advocacy programs
