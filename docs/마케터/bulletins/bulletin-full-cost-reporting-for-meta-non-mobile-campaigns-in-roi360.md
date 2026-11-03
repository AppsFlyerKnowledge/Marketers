---
title: 'Bulletin: Full cost reporting for Meta non-mobile campaigns in ROI360'
deprecated: false
hidden: false
metadata:
  keywords:
    - Cost
    - ROI360
    - Meta
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
  created_at: '2026-11-01T08:56:35Z'
  edited_at: '2026-11-02T08:47:17Z'
  id: 52545079276561
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/52545079276561-Bulletin-Full-cost-reporting-for-Meta-non-mobile-campaigns-in-ROI360
---
| **Section** | **Details** |
| --- | --- |
| **What's new** | After this update, ROI360 now reports the full cost of Meta non-mobile campaigns in the Channel and Geo reports, and the number of reported Meta clicks has increased. This change resolves the known discrepancy between Meta's dashboard and the Geo and Channel reports.<br /><br />Meta reports the cost of non-mobile campaigns without app IDs. ROI360 attributes this cost to apps that have attribution in AppsFlyer and splits it across those apps in proportion to each app's conversions. This approach applies to both the Geo and Channel reports. After the update:<ul><li>The cost at the campaign level is the same in the Geo and Channel reports because both reports include all costs Meta reports.</li><li>The app-level cost can differ between the Geo and Channel reports. ROI360 splits the cost across apps by matching the cost breakdown to the conversion breakdown. Because the two reports use different granularity (geo and channel), the conversion breakdown per app differs, so the cost allocated to each app differs too.</li></ul> |
| **Effective date** | November 9, 2026<br /><br />The changes go live gradually. They apply to new data going forward and backfill historical data for the last 7 days. |
| **What you need to do** | If you apply in-house logic to complete the cost from Meta in the Channel and Geo reports, remove this logic after the update goes live to avoid over-reporting the cost. |
| **What you should know** | **Channel report**<ul><li>Change: Today, ROI360 measures only the cost that clearly maps to a mobile app (iOS or Android). After this update, ROI360 reports the total cost of Meta non-mobile campaigns and resolves the apps using attribution data and cost-split logic. This closes the known discrepancy with Meta.</li><li>Impact: The total cost in the Channel report increases at the campaign and app levels to match your actual Meta spend.</li></ul>For an example, see the [Channel report example](#REPLACE_CHANNEL_EXAMPLE_ID).<br /><br />**Geo report**<ul><li>Change: Today, geo-level cost for Meta non-mobile campaigns is available only to beta customers. After this update, geo-level cost is available to all customers in the dashboard and in the Cost ETL Geo report. ROI360 allocates costs across geos and attributed apps using cost-split logic.</li><li>Impact: The total cost measured from Meta with Geo granularity increases at the campaign and app levels.</li></ul>For an example, see the [Geo report example](#REPLACE_GEO_EXAMPLE_ID).<br /><br />**Clicks metric**<ul><li>Change: **After this update, ROI360 uses a different Meta metric for clicks.** Today, ROI360 uses Meta's Inline clicks metric, which measures only the number of clicks on links to selected destinations or experiences, on or off Meta-owned properties. After this update, ROI360 uses Meta's clicks metric, which measures the total number of ad clicks. This can include inline link clicks, page likes, post comments, and event responses.</li><li>Impact: Reported clicks from Meta increase.</li></ul> |

## Examples

### Channel report example

**When the Meta dashboard shows cost by impression device:**

| **Impression device** | **Cost** |
| --- | --- |
| iPhone | $100 |
| Android | $200 |
| Desktop | $50 |
| **Total** | **$350** |

**Before the update, ROI360 reports partial cost:**

| **App ID** | **Cost** |
| --- | --- |
| id12345 | $100 |
| android.com | $200 |
| **Total** | **$300** |

ROI360 reports only the cost that clearly maps to mobile apps. It doesn't report the rest. In this example, that's the $50 that Meta returned with impression device = desktop.

**After the update, ROI360 reports all costs:**

| **App ID** | **Ratio** | **Cost** |
| --- | --- | --- |
| id12345 | 0.3 | $105 |
| android.com | 0.6 | $210 |
| www.test.com | 0.1 | $35 |
| **Total** |  | **$350** |

ROI360 reports all the cost at the campaign level, aligned with Meta reporting. It splits the cost across the attributed apps (mobile and non-mobile).

### Geo report example

**When the Meta dashboard shows cost by geo:**

| **Geo** | **Cost** |
| --- | --- |
| UK | $200 |
| BE | $150 |
| **Total** | **$350** |

**After the update, ROI360 reports cost by geo and app:**

| **Geo** | **App ID** | **Cost** |
| --- | --- | --- |
| UK | id12345 | $50 |
| UK | android.com | $150 |
| BE | id12345 | $50 |
| BE | android.com | $100 |
| **Total** |  | **$350** |

<div data-zendesk-anchors="h_01M6BT1WAPZBCJQMGSFEYNX4D4=examples h_01M6BT1WAPJHDGF5N5SACGDWAX=channel-report-example h_01M6BT1WAP2PW79ZZPM4WD7SKK=geo-report-example" />
