---
title: >-
  iOS metrics in the Overview dashboard (SKAN and AppsFlyer metrics
  side-by-side)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-08-02T07:18:18Z'
  edited_at: '2025-05-28T09:43:16Z'
  id: 4404976682257
  locale: en-us
  section: Dashboards
  section_id: 6550925337873
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4404976682257-iOS-metrics-in-the-Overview-dashboard-SKAN-and-AppsFlyer-metrics-side-by-side
---
> **At a glance**: View metrics of SKAdNetwork (SKAN) and AppsFlyer attribution frameworks side-by-side in the Overview dashboard. Identify the framework with the best campaign performance metric for you, then leverage it to gain insights and optimize campaigns.

**Attribution metrics display side-by-side in the Overview V2.0 dashboard**

![SBSDB.png](https://files.readme.io/550c465c329eac484d2b2e5a65c8f48831c350c3c4b967315e3b2059ab95a36d-4409263804049.png)

## Finding the best iOS 14+ campaign performance metrics

Starting iOS 14+, both SKAN attribution and <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model">AppsFlyer attribution</Anchor> frameworks generate campaign performance metrics. They attribute differently, have different traits and limitations, and discrepancies between them often occur. For example, SKAN now contains metrics of Apple Ads (Search Ads) campaigns but not that of owned media. Conversely, AppsFlyer metrics from SRNs don't include installs of non-consenting users. Furthermore, SKAN measures performance during an initial post-install window of 1-3 days, whereas AppsFlyer measures lifetime value (<Anchor target="_blank" href="/marketers/vi/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV</Anchor>).

In side-by-side, you view campaign performance using data provided by both frameworks. Compare the metrics of each framework and decide which metric best represents the actual campaign performance.

**Data sharing limitation**: SKAN metrics in the Overview dashboard aren't available to ad networks and agencies.

<mark>If SKAN metrics don't display in the dashboard, you must update the [table settings](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#display-skan-metrics-in-the-table).</mark>

The side-by-side view provides insights into campaign metrics. Use it to evaluate campaign performance metrics in terms of:

* [Precision](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#campaign-precision):
  * How many installs did a campaign bring?
  * Why do the SKAN and AppsFlyer metrics differ?
* [Effectiveness:](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#campaign-effectiveness) How many users converted and what is the ROI?
* [Efficiency](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#campaign-efficiency): What is the campaign eCPI?

This article contains guidance based on our market knowledge and observations on how to interpret the data and gain actionable insights from it. Consider that the marketing landscape of each app is different, and validate our guidance in the context of your app.

**Terminology**

* **Install**:
  * AppsFlyer: New installs and re-attributions
  * SKAN: New installs and re-downloads
* **Actual:** Actual means the metric best representing the data, even though it may not include all data.
* **Consenting user:** An iOS 14+ user who grants <Anchor target="_blank" href="/marketers/vi/docs/about-att-and-skan#att-principles">ATT authorization</Anchor> in both the publisher and advertised app.

<div id="campaign-precision" />

<Accordion title="Campaign precision">

| Question | How many actual installs are attributed to a campaign? |
| --- | --- |
| Symptom | Install metrics differ between the frameworks. Each framework counts some of the installs, and there may be overlaps and discrepancies between the frameworks. |
| Remedy | <ul><li>Compare the install metrics of the frameworks at the campaign level.</li><li>The framework reporting the most installs is regarded as having the most precise metric, even though this metric may not include 100% of attributions.</li></ul> |
| Example | ![S2Sinstalls.png](https://files.readme.io/9599ef8ac37aa1bc0da46112c1a7d6b4c42f3ff82efda0d0e4b47b8bddc6b52a-4406110225425.png)<br /><br />In the table, the framework bringing the most installs is highlighted. This is the actual number of installs brought by the campaign. |
| Tip | You can automate the process of establishing which metric is higher by importing the table into a spreadsheet. Use the @max function and conditional formatting to identify the framework reporting the most installs. |

| Question | Why do the SKAN and AppsFlyer metrics differ? |
| --- | --- |
| Symptom | Install metrics differ. |
| Explanation | <ul><li>The AppsFlyer framework determines installs according to the AppsFlyer <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model">attribution model</Anchor> covering different campaign types and attribution methods, whereas SKAN measures installs in the context of paid app-to-app campaigns.</li><li>Typically, SKAN metrics of SRN campaign installs are higher than those of AppsFlyer, because AppsFlyer only records consenting users.</li><li>In the case of non-SRN networks (click networks), there is often a much closer alignment between the metrics per framework.</li></ul> |

</Accordion>

<div id="campaign-effectiveness" />

<Accordion title="Campaign effectiveness">

| Question | How many users converted, and what is the ROI? |
| --- | --- |
| Considerations | <ul><li>Determining revenue and conversion rate metrics requires that user performance be measured over time.</li><li>SKAN limits measurement to 12-72 hours post-install, whereas AppsFlyer measurement is unlimited (LTV).</li><li>AppsFlyer attribution only contains metrics of consenting users.</li></ul> |
| Remedy | Consider whether the AppsFlyer attribution metrics accurately represent the entire user population (including users reported via SKAN). If so, use them to extrapolate campaign effectiveness metrics like ROI and conversion rate metrics.<br /><br />**To calculate the number of users that converted:**<ol><li>Use the AppsFlyer conversion rate metric (per event).</li><li>Multiply the conversion rate by the actual number of users, derived as described in the campaign precision section.</li></ol>**To calculate campaign revenue and ROI:**<ol><li>Derive the actual number of users (a) as described in the campaign precision section.</li><li>Use the ARPU (b) metric provided by AppsFlyer attribution.</li><li>Calculate campaign revenue using the formula: a * b</li><li>Use the campaign cost as displayed in the dashboard.</li><li>ROI = (campaign revenue - campaign cost) / (campaign cost  * 100)</li></ol> |
| Example | **Calculating ROI**<br /><br />![SBSCost.png](https://files.readme.io/052c862e0a93c4e938f84b22e04e8b088bf50acbf047b821ca6cd20f5b9eae57-4409270882577.png)<br /><br />**Example ROI calculation for campaign a:**<ol><li>Assumed number of users 2000</li><li>ARPU metric in the dashboard: $0.76</li><li>Campaign revenue = 2000 * $0.76 = $1520</li><li>Campaign cost: $905.88</li><li>ROI= ($1520 - $905.88) / ($905.88 * 100) = 68%</li></ol> |
| Tip | Use your BI product analysis tool to compare the performance of consenting users to the entire app user population. If the results differ, you must adjust the remedy calculation to account for this. |

</Accordion>

<div id="campaign-efficiency" />

<Accordion title="Campaign efficiency">

| Question | What is the actual campaign eCPI? |
| --- | --- |
| Symptom | Campaign cost-related metrics like eCPI are misleading because they rely on a precise number of users. |
| Remedy | <ol><li>Derive the actual number of users (a) as described in the campaign precision section.</li><li>Calculate eCPI using the following formula: eCPI = cost / (a)</li></ol> |
| Example | ![mceclip1.png](https://files.readme.io/98fc80d1e995ba8ef0cce267fa12f22d48a77d7e25db4add1108144c6de7136d-4406111715217.png)<ul><li>Actual installs is determined using the framework having the most installs.</li><li>eCPI is calculated using the formula: cost/number of installs.</li></ul> |

</Accordion>

## Using side-by-side

<div id="principles" />

<Accordion title="Principles">

* Contains installs reported by both attribution frameworks
* Use the unified view, in Overview V2.0, to ensure that all available data in the context of a campaign displays, and isn't inadvertently hidden by filtering
* SKAN data is the same as that available via the SKAN dashboard
* To reduce discrepancies due to timing differences between the frameworks, set a date range in the dashboard as follows:
  * Duration: Minimum 7 days
  * Most recent date:
    * 3–5 days before the current date. The range depends on your activity window
    * If you run Google Ads campaigns, the earliest date must be 8 days before the current date

</Accordion>

<div id="display-skan-metrics-in-the-table" />

<Accordion title="Display SKAN metrics in the table">

**To display SKAN metrics in the table**:

1. Click ⚙ (table settings).   
   The metrics selection window opens.

   ![SelectSkan.png](https://files.readme.io/6b60fa8e2d10a1b61b1bfb4b7a968adb5ee16086d80c9cc8bc097b8e8ed77b51-4408473842833.png)
2. Click **SKAN attribution**.
3. Click **SKAN installs**.
4. Click **SKAN revenue**.
5. [Optional] To add or remove in-app event:
   1. Select in-app events.
   2. Add or remove the required in-app events.
6. Click **Apply**.   
   The selected metrics and in-app events display.

</Accordion>

<div id="timerelated-differences" />

<Accordion title="Time-related differences">

<table><thead><tr><th>Difference</th><th>AppsFlyer</th><th>SKAN</th></tr></thead><tbody><tr><td>Historical data</td><td><p>Available; no limitation</p></td><td><p>Available; no limitation. </p></td></tr><tr><td>Time zone</td><td><p>App-specific time zone</p></td><td>UTC </td></tr><tr><td>Data freshness </td><td>Updates continuously with a latency of up to 60 minutes</td><td><p>U<span>pdates daily by 08:00 UTC. </span></p><p><span>Latency depends on the duration of the activity window. Default: 2-5 days; in the case of campaigns run by Google Ads campaign—up to 13 days.</span></p></td></tr><tr><td>Install date</td><td>Date the install occurred </td><td>Derived from the postback arrival time. (1) </td></tr><tr><td>Measurement duration</td><td>Unlimited; LTV-based</td><td><p>Limited to the duration of the activity window of 12-72 hours. Default = 24 hours.</p></td></tr><tr><td>Attribution lookback window</td><td><ul><li>Determined by advertiser or SRN</li><li>Click-to-open: 7 days</li></ul></td><td><ul><li>Determined by Apple</li><li>Click-to-download: 30 days</li><li>Download-to-open: 60 days</li></ul></td></tr><tr><td colspan="3"><p>Notes</p><p>(1) Google Ads data updates with a delay of up to 13 days.</p></td></tr></tbody></table>

</Accordion>

<div id="cost-clicks-and-impressions" />

<Accordion title="Cost, clicks, and impressions">

Ad networks provide cost, click, and impression metrics to AppsFlyer which are common to both frameworks. There is no segregation of these metrics by framework.

In the case of cost metrics, the following apply:

* Updates 6 times a day, on average every 4 hours.
* AppsFlyer records the first engagement (click or impression) associated with a campaign; thereafter, the campaign cost associated with the engagement displays.
* Because SKAN installs are reported 72–120 hours after the first app open, expect to see cost metrics some days before they are associated with installs.
* For installs from Google Ads, the delay can be up to 13 days.

</Accordion>

<div id="data-scope-differences" />

<Accordion title="Data scope differences">

| Difference | AppsFlyer | SKAN |
| --- | --- | --- |
| Platform | All | iOS |
| Attribution types | <ul><li>Installs</li><li>Re-engagements</li><li>Re-attributions</li></ul> | <ul><li>Installs</li><li>Re-downloads</li></ul> |
| Ad revenue | Available | <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">Limited; depends on the mediation partner</Anchor>. |
| Apple Ads (Search Ads) | Available | Supported for SKAN attribution |
| Owned media | Available | Not applicable to SKAN attribution |
| Web-to-app | Available | Available for SKAN 4 attribution |
| Currency | App-specific currency | USD |

</Accordion>

<div id="matching-considerations" />

<Accordion title="Matching considerations">

<table><thead><tr><th>Consideration</th><th>AppsFlyer</th><th>SKAN</th></tr></thead><tbody><tr><td>Agency transparency</td><td>Supported</td><td><p>Attributed to the media source bringing the install. Agencies can instruct media sources to prefix campaign names with their <em><a href="/partners/vi/docs/getting-started-agency-onboarding" target="_blank">prt</a>,</em> in which case you can identify agency-driven traffic.</p></td></tr><tr><td>Campaign name changes</td><td><ul><li>Supported</li><li>The most recent name reported by the ad network determines the campaign name used for all installs associated with a given campaign ID. This includes previously recorded installs. </li></ul></td><td><ul><li>Not supported</li><li>The campaign name reported when the user installs the app is used. This doesn't change over time. Consequently, multiple names can be associated with a given campaign ID. </li></ul></td></tr><tr><td>Dimensions supported</td><td>No limitation</td><td><p><strong>Available</strong>: Geo, ad, ad ID, channel, adset, site ID.</p><p><strong>Agency:</strong> Not currently.</p><p>If you select a dimension that isn't supported, SKAN data is displayed as none.</p></td></tr><tr><td>SRN install metrics</td><td>Limited to consenting users; as a result, expect the AppsFlyer-reported metrics to be lower than SKAN-reported metrics and the metrics provided by the SRN itself. </td><td>All SKAN-attributed installs. Usually higher than the AppsFlyer metric. </td></tr><tr><td>Hidden SKAN campaigns</td><td colspan="2"><p>The table in the dashboard contains a limited number of rows. The remaining rows are combined in the row designated <em>others</em>.</p><p>To view a breakdown of this row, export the entire table to a spreadsheet. </p></td></tr></tbody></table>

</Accordion>

<div id="dimensions-available" />

<Accordion title="Dimensions available">

The following dimensions are available in the side-by-side view:

* Media source
* Campaign name
* Campaign ID
* Date
* Attribution type

</Accordion>

<div data-zendesk-anchors="h_01HYAQAR84BP9MRRXP7BPPDJ4N=finding-the-best-ios-14-campaign-performance-metrics h_01HYAQAR856G6VARSH746SJB5Z=campaign-precision h_01HYAQAR856JT2JX28SE3QY7VZ=campaign-effectiveness h_01HYAQAR85GZN1RZYNV2MV7DAP=campaign-efficiency using-sidebyside=using-side-by-side h_01HYAQAR85FY6K8R574GWFQW91=using-side-by-side h_01HYAQAR85Z09SXSE8JGTG5AMF=principles h_01HYAQAR85V6CD29T9AY9XYX0Z=display-skan-metrics-in-the-table h_01HYAQAR85QSTB8QZPGMEV6MR9=timerelated-differences h_01HYAQAR85A03KNAHC5TEAZAZK=cost-clicks-and-impressions h_01HYAQAR85SPYQKDFP3CRGW5FN=data-scope-differences h_01HYAQAR85FSAXQ25X16N6XQEW=matching-considerations h_01HYAQAR85XF7CEG6F7PC44F1C=dimensions-available" />
