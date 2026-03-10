# Dataset Description: Ad Campaign Performance Data 2024

## Overview
This is a synthetic dataset designed to replicate the structure and statistical properties
of real digital advertising campaign data from a North American e-commerce brand.

**Scale:** 21,508 rows | 220 campaigns | 4 channels | Full year 2024 (campaign-day level)

The data structure mirrors campaign-level reporting aggregates commonly found in platforms
such as Google Ads, Meta Ads Manager, and agency reporting tools (e.g., DoubleClick/CM360).

## Data Generation Methodology
All KPI distributions are calibrated against publicly available North American
digital advertising benchmarks (WordStream, Nielsen, eMarketer 2023-2024):

| Channel     | CTR Benchmark | CVR Benchmark | Typical ROAS |
|-------------|--------------|---------------|--------------|
| Search      | 3.5–5.5%     | 2.5–4.0%      | 6–12x        |
| Paid Social | 0.8–1.6%     | 1.3–2.3%      | 1.5–2.5x     |
| Display     | 0.1–0.3%     | 0.5–1.1%      | 0.3–0.6x     |
| Video       | 0.4–0.9%     | 0.8–1.6%      | 0.7–1.1x     |

## Embedded Anomaly Events (for analysis practice)
The dataset contains 5 realistic anomaly events intentionally embedded for analytical discovery:

1. **Search CTR Drop** (Jul 8–28): ~38% CTR decline → simulates creative fatigue
2. **Display Tracking Issue** (Mar 5–15): ~95% CVR drop → simulates pixel/tracking failure
3. **Paid Social Spend Spike** (Sep 10–17): ~2x overspend → simulates budget misconfiguration
4. **Video Creative Refresh** (May 1 onward): ~28% CTR improvement → simulates creative optimization
5. **Post-Holiday Fatigue** (Dec 27–31): ~45% CTR drop across all channels → simulates seasonal falloff

## Seasonality
Spend and performance reflect realistic NA e-commerce seasonality:
Black Friday/Cyber Monday (+180%), Holiday Season (+150%), Valentine's Day (+50%),
Mother's Day (+30%), Back-to-School (+20%), Post-New Year slump (-40%)

## Schema

| Column         | Type    | Description                                      |
|----------------|---------|--------------------------------------------------|
| date           | date    | Campaign activity date (YYYY-MM-DD)              |
| campaign_id    | string  | Unique campaign identifier (CMP_XXXX)            |
| campaign_name  | string  | Descriptive name: product_objective_channel_region |
| objective      | string  | brand_awareness / consideration / conversion / retargeting |
| channel        | string  | Search / Paid Social / Display / Video           |
| region         | string  | Northeast / West / Southeast / Midwest / Southwest |
| product_line   | string  | HomeGoods / Electronics / Apparel / Beauty / Sports / Toys |
| creative_type  | string  | Channel-specific creative format                 |
| daily_budget   | float   | Allocated daily budget (USD), seasonally adjusted |
| spend          | float   | Actual daily spend (USD)                         |
| impressions    | integer | Total ad impressions served                      |
| clicks         | integer | Total clicks                                     |
| conversions    | integer | Total tracked conversions                        |
| revenue        | float   | Attributed revenue (USD)                         |
| ctr            | float   | Click-through rate = clicks / impressions        |
| cvr            | float   | Conversion rate = conversions / clicks           |
| cpa            | float   | Cost per acquisition = spend / conversions (null if 0 conversions) |
| roas           | float   | Return on ad spend = revenue / spend             |
| cpc            | float   | Cost per click = spend / clicks (null if 0 clicks) |

## How to Cite in Your README
> "Synthetic dataset modeled after real campaign reporting structures from North American
> e-commerce advertising. KPI distributions calibrated to industry benchmarks
> (WordStream 2024, eMarketer 2024). Anomaly events reflect common real-world
> campaign issues encountered in agency analytics workflows."
