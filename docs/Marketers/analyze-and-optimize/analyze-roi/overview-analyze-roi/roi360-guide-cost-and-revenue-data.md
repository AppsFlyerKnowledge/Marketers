---
title: "ROI360 guide - cost and revenue data"
excerpt: "Get a complete picture of your return on ad spend and return on investment with ROI360's suite of cost and revenue reporting tools."
x-zendesk:
  id: 10515748254609
  url: https://support.appsflyer.com/hc/en-us/articles/10515748254609-ROI360-guide-cost-and-revenue-data
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Overview
  section_id: 15173289016593
  position: 0
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-michael-talapov, Marketers, ROI360]
  labels: [cost, Advertisers, Premium, Marketers, revenue, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2022-11-10T13:52:03Z'
  edited_at: '2026-01-14T14:48:46Z'
---
**At a glance**: Get cost and revenue data to understand your total ROI and ROAS.

![M_emptyState.png](https://files.readme.io/5eec5be77bf0b72afdd95b1957642cc67ba509000bc756ac68d87da5e96ed08e-11832563913489.png)

## Overview

ROI360 is a suite of unique cost and revenue reporting tools that provide you with the most accurate data, as fast as possible.

With the combined cost and revenue insights, you get the complete picture of your return on ad spend (ROAS) and return on investment (ROI).

### Cost tools

Previously known as Xpend, the ROI360 cost tools aggregate and report cost data. The full suite of cost tools and features is outlined in the table that follows. Click the links to learn more about each feature.

| Tool | Description |
| --- | --- |
| [Attributed cost](/docs/roi360-cost-aggregation-overview) | Cost data tied to attribution, clicks, and impressions at the most granular level available.<br />This includes access to more than 80 API integrations, enabling you to easily connect to global or local ad networks. |
| [File import](/docs/import-cost-data) | Cost Import to record cost data not received via API. |
| [Agency fees](/docs/incorporate-agency-fees-into-campaign-costs) | Agency fee calculations included in your cost. |
| [Cost ETL\*](/docs/set-up-and-use-roi360-cost-etl-reports) | Delivers campaign cost data, updated 4 times daily, to your AWS S3 or GCS bucket ready for loading into advertiser BI systems. |
| \* Available with ROI360 advanced package | |

> 📘 Note
>
> You can also aggregate [cost data reported on the attribution link](/docs/view-aggregated-cost-data-for-attribution-links) without ROI360. However, this method is only for the CPI cost model, not for other models, such as CPA, CPC, and CPM.

### Revenue tools

The ROI360 revenue tools aggregate and report revenue data, taking into account in-app purchases, subscriptions, and ad revenue. Taxes and app store commissions are also included in revenue metrics. The full suite of revenue tools and features is outlined in the table that follows. Click the links to learn more about each feature.

| Tool | Description |
| --- | --- |
| [In-app purchases](/docs/purchase-and-subscription-validation-overview) | Automatic reporting of validated in-app purchases, including data for follow-up transactions such as refunds or cancellations. |
| [Subscription revenue](/docs/purchase-and-subscription-validation-overview) | Automatic reporting of subscriptions, including changes, cancellations, and family sharing. |
| [Ad revenue](/docs/roi360-guide-ad-revenue-attribution) | Access to more than 20 ad revenue partners that connect via API or SDK that provide superior accuracy and data freshness. |
| [Revenue ETL](/docs/revenue-etl-reports)\* | Delivers revenue data to your AWS S3 or GCS bucket ready for loading into advertiser BI systems. |
| \* Available with ROI360 advanced package | |

> 📘 Note
>
> There are also some basic revenue measurement tools that aren't included in ROI360. Unlike the tools included in ROI360, these tools require a substantial amount of configuration by your developers:
>
> * [In-app purchase receipt validation](/docs/about-receipt-validation)
> * [Subscription revenue measurement](/docs/purchase-and-subscription-validation-overview)
> * [Revenue recording via customized in-app events](/docs/roi360-revenue-attribution-overview)