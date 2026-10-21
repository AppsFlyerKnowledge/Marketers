---
title: SKAN aggregated performance report API
metadata:
  keywords:
    - Advertisers
    - SKAD
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-08T09:45:03Z'
  edited_at: '2024-02-08T08:56:21Z'
  id: 360014104157
  locale: en-us
  section: SKAN solution
  section_id: 6552135379985
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360014104157-SKAN-aggregated-performance-report-API
---
**At a glance:** SKAN performance enriched with additional data points. Similar to the data in the SKAdNetwork dashboard. Aggregate using either the install date or postback arrival date.

## SKAN aggregated performance report API

The API returns attribution metrics reported by Apple SKAdNetwork (real data) and other data points using the install or postback arrival date. The report is similar in structure to the data presented in the <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN dashboard</Anchor>. 

<div id="using-skan-aggregated-performance-report-api" />

<Accordion title="Using SKAN aggregated performance report API">

**To use SKAN aggregated performance report API**:

1. Get the API token. An admin needs to retrieve the token.
2. Give your developer the API token to be used in the authentication header.
3. Give your developers the parameters to input when they make the API call, as described in the section that follow. The parameters determine what the report focuses on, how it's organized, and provide a reporting timeframe.
4. Tell your developer to follow their <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-agg-performance-report-api-get">SKAN aggregated performance report API</Anchor> in the developer hub.

#### Parameters

| Parameter name | Format | Mandatory |
| --- | --- | --- |
| `date_type` | The date type used in the date range bounded by `start_date` and `end_date`<br /><br />Options:<ul><li>[Default] `install`: The install date derived by AppsFlyer using the postback arrival time and after considering the measurement period.</li><li>`arrival`: The postback arrival time. Note: Organic install metrics have the value N/A.</li></ul>Google Ads data: The install and arrival dates are the same due to the Google Ads reporting methodology. | No |
| `start_date` | The install date range is bounded by start\_date and end\_date. Note! Install date differs from postback arrival date.<ul><li>Earliest install date having format YYYY-MM-DD</li><li>Earliest date permitted: 2020-11-01<br />Example: `2020-11-05`</li></ul> | Yes |
| `end_date` | <ul><li>Most recent install date having format YYYY-MM-DD</li><li>Maximum number of days per report call: 90 days</li><li>Example: `2020-11-12`</li></ul> | Yes |
| `view_type` | Filter the installs by type as follows:<ul><li>`acquisition`: Installs</li><li>`retargeting`: Redownloads</li><li>`unified`: Acquisition and redownloads combined.</li><li>[Default] `unified`</li><li>Cost, click, and impression metrics return when `view_type=unified`</li></ul> | No |
| `modeled_conversion_values` | <ul><li>Only available from V2</li><li>Value can be either `true` or `false`</li><li>If true, the postback includes the modeled data when populating the decoded metric columns. [See available fields](/docs/skan-aggregated-performance-report-api#report-structure-and-example)</li><li>If `false`, the postback presents decoded data as received by raw SKAN postbacks, without modeled data.</li><li>Default value is `false`.</li></ul> | No |

</Accordion>

<div id="report-structure-and-example" />

<Accordion title="Report structure and example">

The API returns a CSV file.

* The fields and metrics available in the report are listed in the table that follows.
* Some metrics (revenue, engagement, conversion) depend on the SKAN <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio">performance measurement settings.</Anchor>
* The report includes only the in-app events that users performed during the reporting period. As such, the number and sequence of in-app event columns can change from report to report. Don't rely on column sequence in designing your data import process.
* Examples: [V1](https://docs.google.com/spreadsheets/d/e/2PACX-1vSmnyUITQjRxNp6-rz8Xzscu-Rr4Kn2DW1du2VppS-QrpyQSZ0GKQ_qZdWNdNoLuwJAmgh2O-bWiuU3/pub?gid=0&single=true&output=csv) | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQogLd4w3xgrjQBmEiHLfcvz1e9dtWez_Rdg1OxV8bSRHRE-wxZJItfT6azLr4iZAgsW2Vxr_WVmEYo/pub?gid=0&single=true&output=csv">V2</Anchor>

#### Report fields

| Field name | Dimension or metric | Available with API V1 token | Available with API V2 token | Available with API V2 token (for SKAN 4) | Available with modeled data only filter |
| --- | --- | --- | --- | --- | --- |
| Date<br /><br />The data is according to the selected date\_type. | Dimension | N | Y | Y | Y |
| Media Source (pid) | Dimension | Y | Y | Y | Y |
| Campaign (c) | Dimension | Y | Y | Y | Y |
| Campaign ID | Dimension | Y | Y | Y | Y |
| Site ID | Dimension | Y | Y | Y | N |
| Adset | Dimension | N | Y | Y | Y |
| Adset ID | Dimension | N | Y | Y | Y |
| Ad | Dimension | N | Y | Y | N |
| Ad ID | Dimension | N | Y | Y | N |
| Country | Dimension | Y | Y | Y | N |
| AF Attribution Flag<br /><br />See: <Anchor target="_blank" href="/marketers/docs/single-source-of-truth-ssot-guide-for-ios-attribution">SSOT guide</Anchor> | Dimension | N | Y | Y | Y |
| Postback sequence index | Dimension | N | N | Y | Y |
| Creative | Dimension | N | N | Y | N |
| Channel | Dimension | N | N | Y | N |
| Impressions | Metric | Y | Y | Y | Y |
| Clicks | Metric | Y | Y | Y | Y |
| CTR | Metric | Y | Y | Y | Y |
| Installs | Metric | Y | Y | Y | Y |
| Click Through Installs (fidelity\_type = 1) | Metric | Y | Y | Y | Y |
| View Through Installs<br /><br />(fidelity\_type = 0) | Metric | Y | Y | Y | Y |
| Null Conversion Value Rate<br /><br />[Available starting Jan 23, 2022] | Metric | N | Y | Y | Y |
| Conversion Rate | Metric | Y | Y | Y | Y |
| Converted Users | Metric | Y | Y | Y | Y |
| Converted Users/Installs | Metric | Y | Y | Y | Y |
| Total Revenue | Revenue metric | Y | Y | Y | Y |
| Total Cost | Metric | Y | Y | Y | Y |
| ROI | Revenue metric | Y | Y | Y | Y |
| ARPU | Revenue metric | Y | Y | Y | Y |
| Average eCPI | Metric | Y | Y | Y | Y |
| `{af_skad_revenue}` (Unique users) | Revenue metric | Y | Y | Y | Y |
| `{af_skad_revenue}` (Event counter) | Revenue metric | Y | Y | Y | Y |
| `{your in-app event name}` (Unique users) | Metric | Y | Y | Y | Y |
| `{your in-app event name}` (Event counter) | Metric | Y | Y | Y | Y |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Specifications and limitations">

| Spec | Remarks |
| --- | --- |
| Data freshness | Data availability is according to the <Anchor target="_blank" href="/marketers/docs/about-data-freshness-and-timezone-support#skan">SKAN</Anchor> data freshness rate. |
| Date range | <ul><li>When setting the date range the most recent date should be the current date UTC time zone minus 3 days. Meaning on March 31, use March 28.</li><li>Earliest date supported: November 1, 2020</li><li>Maximum query range: 90 days</li></ul> |
| Rate limits | <ul><li>Queries return up to 250K rows</li><li>10 calls per minute</li></ul> |
| SRNs | <ul><li>Meta ads: data is available.</li><li>Google Ads: Installs can be recorded up to 45 days post-install due to the Google click-time methodology. If you query Google data for the last 45 days every day, this provides the coverage needed for Google SKAN data.</li></ul> |
| Ad network access | If you are an analytics partner, ask the advertiser to grant you permission. |
| Agency access | Not available |
| App-specific time zone | UTC only |
| App-specific currency | Always USD |
| Organic data | Calculated as the difference between all data reported by SDK directly to AppsFlyer less non-organic data reported by SKAN postbacks |
| Non-organic data | Calculated using SKAN postbacks received by AppsFlyer |
| Historical data | Earliest conversion data (install or retarget) supported: November 1, 2020 |
| Account user access | The authorization token is available to an admin user in the dashboard. |
| Total cost | SKAN API may not include the total cost metric if the regular attribution (regular Overview) contains SKAN campaigns that in the lowest granularity level (for example: ad, country, or site ID) have more than 50K rows. |

</Accordion>

<div data-zendesk-anchors="skadnetwork-postback-arrival-date-aggregation-reporting-api=skan-aggregated-performance-report-api h_01HH9WHP1SDQ3TJPZ931R9KWKH=skan-aggregated-performance-report-api h_01HH9WHP1S7PWJHKAKHN434G7Y=using-skan-aggregated-performance-report-api h_01HH9WHP1SZQZGSZ4WEPAAFNV7=parameters h_01HH9WHP1SYEHGJBBWSMS2XQP0=report-structure-and-example skadnetwork-aggregate-report-structure=report-fields h_01HH9WHP1STYNJK3DRESDF23DG=report-fields h_01HH9WHP1T4NEMW56XVYKM3KHM=specifications-and-limitations" />
