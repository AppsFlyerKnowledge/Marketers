---
title: ROI360 guide - cost and revenue data
metadata:
  keywords:
    - cost
    - Advertisers
    - Premium
    - Marketers
    - revenue
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-11-10T13:52:03Z'
  edited_at: '2026-01-14T14:48:46Z'
  id: 10515748254609
  locale: en-us
  section: Overview
  section_id: 15173289016593
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/10515748254609-ROI360-guide-cost-and-revenue-data
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance**: Get cost and revenue data to understand your total ROI and ROAS.

![M_emptyState.png](https://files.readme.io/5eec5be77bf0b72afdd95b1957642cc67ba509000bc756ac68d87da5e96ed08e-11832563913489.png)

<div id="overview" />

## Overview

ROI360 is a suite of unique cost and revenue reporting tools that provide you with the most accurate data, as fast as possible.

With the combined cost and revenue insights, you get the complete picture of your return on ad spend (ROAS) and return on investment (ROI).

<div id="cost-tools" />

### Cost tools

Previously known as Xpend, the ROI360 cost tools aggregate and report cost data. The full suite of cost tools and features is outlined in the table that follows. Click the links to learn more about each feature.

<table><thead><tr><th>Tool</th><th>Description</th></tr></thead><tbody><tr><td><a href="./roi360-cost-aggregation-overview" target="_blank">Attributed cost</a></td><td><p><span>Cost data tied to attribution, clicks, and impressions at the most granular level available.</span></p><p><span>This includes access to more than 80 API integrations, enabling you to easily connect to global or local ad networks.</span></p></td></tr><tr><td><a href="./import-cost-data" target="_blank">File import</a></td><td><span>Cost Import to record cost data not received via API.</span></td></tr><tr><td><a href="./incorporate-agency-fees-into-campaign-costs" target="_blank">Agency fees</a></td><td><span>Agency fee calculations included in your cost.</span></td></tr><tr><td><a href="./set-up-and-use-roi360-cost-etl-reports" target="_blank">Cost ETL\*</a></td><td>Delivers campaign cost data, updated 4 times daily, to your AWS S3 or GCS bucket ready for loading into advertiser BI systems.</td></tr><tr><td colspan="2">\* Available with ROI360 advanced package</td></tr></tbody></table>

**Note**: You can also aggregate <Anchor target="_blank" href="/marketers/docs/view-aggregated-cost-data-for-attribution-links">cost data reported on the attribution link</Anchor> without ROI360. However, this method is only for the CPI cost model, not for other models, such as CPA, CPC, and CPM.

<div id="revenue-tools" />

### Revenue tools

The ROI360 revenue tools aggregate and report revenue data, taking into account in-app purchases, subscriptions, and ad revenue. Taxes and app store commissions are also included in revenue metrics. The full suite of revenue tools and features is outlined in the table that follows. Click the links to learn more about each feature.

<table><thead><tr><th>Tool</th><th>Description</th></tr></thead><tbody><tr><td><a href="./purchase-and-subscription-validation-overview" target="_blank">In-app purchases</a></td><td><span>Automatic reporting of validated in-app purchases, including data for follow-up transactions such as refunds or cancellations.</span></td></tr><tr><td><a href="./purchase-and-subscription-validation-overview" target="_blank">Subscription revenue</a></td><td><span>Automatic reporting of subscriptions, including changes, cancellations, and family sharing.</span></td></tr><tr><td><a href="./roi360-guide-ad-revenue-attribution" target="_blank">Ad revenue</a></td><td>Access to more than 20 ad revenue partners that connect via API or SDK that provide superior accuracy and data freshness.</td></tr><tr><td><a href="./revenue-etl-reports" target="_blank">Revenue ETL</a>\*</td><td>Delivers revenue data to your AWS S3 or GCS bucket ready for loading into advertiser BI systems.</td></tr><tr><td colspan="2">\* Available with ROI360 advanced package</td></tr></tbody></table>

**Note**: There are also some basic revenue measurement tools that aren't included in ROI360. Unlike the tools included in ROI360, these tools require a substantial amount of configuration by your developers:

* <Anchor target="_blank" href="/marketers/docs/about-receipt-validation">In-app purchase receipt validation</Anchor>
* <Anchor target="_blank" href="/marketers/docs/purchase-and-subscription-validation-overview">Subscription revenue measurement</Anchor>
* <Anchor target="_blank" href="/marketers/docs/roi360-revenue-attribution-overview">Revenue recording via customized in-app events</Anchor>

<div data-zendesk-anchors="h_01HKHGX9JJQQCKF9SDZRSCM1XJ=overview h_01HKHGX9JJRWDP9PMYP9CFA7MQ=cost-tools h_01HKHGX9JJFQ9ZM6J3B2D5G6C5=revenue-tools" />
