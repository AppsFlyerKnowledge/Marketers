---
title: "iOS Metrics in the Overview Dashboard"
excerpt: "View and compare SKAdNetwork (SKAN) and AppsFlyer attribution framework metrics side-by-side to optimize your iOS 14+ campaigns."
---
**At a glance**: View metrics of SKAdNetwork (SKAN) and AppsFlyer attribution frameworks side-by-side in the [Overview](https://support.appsflyer.com/hc/articles/360014697157-Overview-dashboard-V2) dashboard. Identify the framework with the best campaign performance metric for you, then leverage it to gain insights and optimize campaigns.

**Attribution metrics display side-by-side in the Overview V2.0 dashboard**

![SBSDB.png](https://files.readme.io/550c465c329eac484d2b2e5a65c8f48831c350c3c4b967315e3b2059ab95a36d-4409263804049.png)

## Finding the best iOS 14+ campaign performance metrics

Starting iOS 14+, both SKAN attribution and [AppsFlyer attribution](https://support.appsflyer.com/hc/articles/207447053) frameworks generate campaign performance metrics. They attribute differently, have different traits and limitations, and discrepancies between them often occur. For example, SKAN now contains metrics of Apple Ads (Search Ads) campaigns but not that of owned media. Conversely, AppsFlyer metrics from SRNs don't include installs of non-consenting users. Furthermore, SKAN measures performance during an initial post-install window of 1-3 days, whereas AppsFlyer measures lifetime value ( [LTV](https://support.appsflyer.com/hc/articles/115005600889)).

In side-by-side, you view campaign performance using data provided by both frameworks. Compare the metrics of each framework and decide which metric best represents the actual campaign performance.

> 📘 Data sharing limitation
>
> SKAN metrics in the Overview dashboard aren't available to ad networks and agencies.

If SKAN metrics don't display in the dashboard, you must update the [table settings](https://support.appsflyer.com/hc/articles/4404976682257#display-skan-metrics-in-the-table).

The side-by-side view provides insights into campaign metrics. Use it to evaluate campaign performance metrics in terms of:

- [Precision](https://support.appsflyer.com/hc/articles/4404976682257#campaign-precision):
  - How many installs did a campaign bring?
  - Why do the SKAN and AppsFlyer metrics differ?
- [Effectiveness:](https://support.appsflyer.com/hc/articles/4404976682257#campaign-effectiveness) How many users converted and what is the ROI?
- [Efficiency](https://support.appsflyer.com/hc/articles/4404976682257#campaign-efficiency): What is the campaign eCPI?

This article contains guidance based on our market knowledge and observations on how to interpret the data and gain actionable insights from it. Consider that the marketing landscape of each app is different, and validate our guidance in the context of your app.

**Terminology**

- **Install**:
  - AppsFlyer: New installs and re-attributions
  - SKAN: New installs and re-downloads
- **Actual:** Actual means the metric best representing the data, even though it may not include all data.
- **Consenting user:** An iOS 14+ user who grants [ATT authorization](https://support.appsflyer.com/hc/articles/360011890298-Quickstart-guide-FAQ-to-iOS-14-ATT-and-SKAdNetwork#att-principles) in both the publisher and advertised app.

### Campaign precision

| | |
| --- | --- |
| **Question** | How many actual installs are attributed to a campaign? |
| **Symptom** | Install metrics differ between the frameworks. Each framework counts some of the installs, and there may be overlaps and discrepancies between the frameworks. |
| **Remedy** | - Compare the install metrics of the frameworks at the campaign level. <br>- The framework reporting the most installs is regarded as having the most precise metric, even though this metric may not include 100% of attributions. |
| **Example** | ![S2Sinstalls.png](https://files.readme.io/9599ef8ac37aa1bc0da46112c1a7d6b4c42f3ff82efda0d0e4b47b8bddc6b52a-4406110225425.png)<br>In the table, the framework bringing the most installs is highlighted. This is the actual number of installs brought by the campaign. |
| **Tip** | You can automate the process of establishing which metric is higher by importing the table into a spreadsheet. Use the @max function and conditional formatting to identify the framework reporting the most installs. |

| | |
| --- | --- |
| **Question** | Why do the SKAN and AppsFlyer metrics differ? |
| **Symptom** | Install metrics differ. |
| **Explanation** | - The AppsFlyer framework determines installs according to the AppsFlyer [attribution model](https://support.appsflyer.com/hc/articles/207447053) covering different campaign types and attribution methods, whereas SKAN measures installs in the context of paid app-to-app campaigns. <br>- Typically, SKAN metrics of SRN campaign installs are higher than those of AppsFlyer, because AppsFlyer only records consenting users.<br>- In the case of non-SRN networks (click networks), there is often a much closer alignment between the metrics per framework. |

### Campaign effectiveness

| | |
| --- | --- |
| **Question** | How many users converted, and what is the ROI? |
| **Considerations** | - Determining revenue and conversion rate metrics requires that user performance be measured over time. <br>- SKAN limits measurement to 12-72 hours post-install, whereas AppsFlyer measurement is unlimited (LTV).<br>- AppsFlyer attribution only contains metrics of consenting users. |
| **Remedy** | Consider whether the AppsFlyer attribution metrics accurately represent the entire user population (including users reported via SKAN). If so, use them to extrapolate campaign effectiveness metrics like ROI and conversion rate metrics.<br>**To calculate the number of users that converted:**<br>1. Use the AppsFlyer conversion rate metric (per event). <br>2. Multiply the conversion rate by the actual number of users, derived as described in the campaign precision section. <br>**To calculate campaign revenue and ROI:**<br>1. Derive the actual number of users (a) as described in the campaign precision section.<br>2. Use the ARPU (b) metric provided by AppsFlyer attribution. <br>3. Calculate campaign revenue using the formula: a * b<br>4. Use the campaign cost as displayed in the dashboard.<br>5. ROI = (campaign revenue - campaign cost) / (campaign cost  * 100) |
| **Example** | **Calculating ROI**<br>![SBSCost.png](https://files.readme.io/052c862e0a93c4e938f84b22e04e8b088bf50acbf047b821ca6cd20f5b9eae57-4409270882577.png)<br>**Example ROI calculation for campaign a:**<br>1. Assumed number of users 2000<br>2. ARPU metric in the dashboard: $0.76<br>3. Campaign revenue = 2000 * $0.76 = $1520<br>4. Campaign cost: $905.88<br>5. ROI= ($1520 - $905.88) / ($905.88 * 100) = 68% |
| **Tip** | Use your BI product analysis tool to compare the performance of consenting users to the entire app user population. If the results differ, you must adjust the remedy calculation to account for this. |

### Campaign efficiency

| | |
| --- | --- |
| **Question** | What is the actual campaign eCPI? |
| **Symptom** | Campaign cost-related metrics like eCPI are misleading because they rely on a precise number of users. |
| **Remedy** | 1. Derive the actual number of users (a) as described in the campaign precision section.<br>2. Calculate eCPI using the following formula: eCPI = cost / (a) |
| **Example** | ![mceclip1.png](https://files.readme.io/98fc80d1e995ba8ef0cce267fa12f22d48a77d7e25db4add1108144c6de7136d-4406111715217.png)<br>- Actual installs is determined using the framework having the most installs.<br>- eCPI is calculated using the formula: cost/number of installs. |

## Using side-by-side

### Principles

- Contains installs reported by both attribution frameworks
- Use the unified view, in Overview V2.0, to ensure that all available data in the context of a campaign displays, and isn't inadvertently hidden by filtering
- SKAN data is the same as that available via the SKAN dashboard
- To reduce discrepancies due to timing differences between the frameworks, set a date range in the dashboard as follows:
  - Duration: Minimum 7 days
  - Most recent date:
    - 3–5 days before the current date. The range depends on your activity window
    - If you run Google Ads campaigns, the earliest date must be 8 days before the current date

### Display SKAN metrics in the table

**To display SKAN metrics in the table**:

1. Click **⚙** (table settings).

The metrics selection window opens.

![SelectSkan.png](https://files.readme.io/6b60fa8e2d10a1b61b1bfb4b7a968adb5ee16086d80c9cc8bc097b8e8ed77b51-4408473842833.png)

2. Click **SKAN attribution**.
3. Click **SKAN installs**.
4. Click **SKAN revenue**.
5. [Optional] To add or remove in-app event:   1. Select in-app events.
2. Add or remove the required in-app events.
6. Click **Apply**.

The selected metrics and in-app events display.

### Time-related differences

| Difference | AppsFlyer | SKAN |
| --- | --- | --- |
| Historical data | Available; no limitation | Available; no limitation. |
| Time zone | App-specific time zone | UTC |
| Data freshness | Updates continuously with a latency of up to 60 minutes | Updates daily by 08:00 UTC. <br>Latency depends on the duration of the activity window. Default: 2-5 days; in the case of campaigns run by Google Ads campaign—up to 13 days. |
| Install date | Date the install occurred | Derived from the postback arrival time. (1) |
| Measurement duration | Unlimited; LTV-based | Limited to the duration of the activity window of 12-72 hours. Default = 24 hours. |
| Attribution lookback window | - Determined by advertiser or SRN<br>- Click-to-open: 7 days | - Determined by Apple<br>- Click-to-download: 30 days<br>- Download-to-open: 60 days |
| Notes<br>(1) Google Ads data updates with a delay of up to 13 days. | | |

### Cost, clicks, and impressions

Ad networks provide cost, click, and impression metrics to AppsFlyer which are common to both frameworks. There is no segregation of these metrics by framework.

In the case of cost metrics, the following apply:

- Updates 6 times a day, on average every 4 hours.
- AppsFlyer records the first engagement (click or impression) associated with a campaign; thereafter, the campaign cost associated with the engagement displays.
- Because SKAN installs are reported 72–120 hours after the first app open, expect to see cost metrics some days before they are associated with installs.
- For installs from Google Ads, the delay can be up to 13 days.

### Data scope differences

| Difference | AppsFlyer | SKAN |
| --- | --- | --- |
| Platform | All | iOS |
| Attribution types | - Installs<br>- Re-engagements<br>- Re-attributions | - Installs<br>- Re-downloads |
| Ad revenue | Available | [Limited; depends on the mediation partner](https://support.appsflyer.com/hc/articles/360011420698-SKAdNetwork-Solution-guide#recording-ad-revenue). |
| Apple Ads (Search Ads) | Available | Supported for SKAN attribution |
| Owned media | Available | Not applicable to SKAN attribution |
| Web-to-app | Available | Available for SKAN 4 attribution |
| Currency | App-specific currency | USD |
| | | |

### Matching considerations

| Consideration | AppsFlyer | SKAN |
| --- | --- | --- |
| Agency transparency | Supported | Attributed to the media source bringing the install. Agencies can instruct media sources to prefix campaign names with their _[prt](https://support.appsflyer.com/hc/articles/360002381617),_ in which case you can identify agency-driven traffic. |
| Campaign name changes | - Supported<br>- The most recent name reported by the ad network determines the campaign name used for all installs associated with a given campaign ID. This includes previously recorded installs. | - Not supported<br>- The campaign name reported when the user installs the app is used. This doesn't change over time. Consequently, multiple names can be associated with a given campaign ID. |
| Dimensions supported | No limitation | **Available**: Geo, ad, ad ID, channel, adset, site ID.<br>**Agency:** Not currently.<br>If you select a dimension that isn't supported, SKAN data is displayed as none. |
| SRN install metrics | Limited to consenting users; as a result, expect the AppsFlyer-reported metrics to be lower than SKAN-reported metrics and the metrics provided by the SRN itself. | All SKAN-attributed installs. Usually higher than the AppsFlyer metric. |
| Hidden SKAN campaigns | The table in the dashboard contains a limited number of rows. The remaining rows are combined in the row designated _others_.<br>To view a breakdown of this row, export the entire table to a spreadsheet. | | |

### Dimensions available

The following dimensions are available in the side-by-side view:

- Media source
- Campaign name
- Campaign ID
- Date
- Attribution type