---
title: Pivot table—user metrics
metadata:
  keywords:
    - Pivot
    - Advertisers
    - 透视表
    - Premium
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2017-03-16T13:11:23Z'
  edited_at: '2026-03-19T11:52:08Z'
  id: 115001421846
  locale: en-us
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115001421846-Pivot-table-user-metrics
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

**At a glance**: View different user metrics—LTV, activity, Protect360, and retention. Download results to CSV files for ingestion by your BI systems. Pivot supports multiple apps in a single query. Use to generate Master API calls.

## About pivot reports page

Using Pivot, you generate customized reports containing user acquisition metrics. Pivot comes with a number of pre-defined reports to use as a base from which you create your customized reports. Reports created by a given account user are available to all users.

The pre-defined pivot reports available are:

* Media source by date
* Full hierarchy
* Cost analysis

**Note**: For campaign data to be visible in pivots, the campaigns must have installs.

## Pivot procedures

Create and modify existing pivots in the user interface. To do so, use the procedures in the sections that follow.

**To use Pivot**:

* In AppsFlyer, from the side menu, select **Analyze** > **Pivot**.  
  The list of currently defined reports displays.

<div id="pivot-page-controls-and-options" />

<Accordion title="Pivot page—controls and options">

| Column/option | Description |
| --- | --- |
| Name | Select a report name to view the associated pivot. |
| Column click | Some columns, as indicated in the interface, are sorted by clicking on the column name. |
| Last modified | Last time the report structure was modified. |
| Modified by | Name of the user who modified the pivot. |
| App name | <ul><li>If one app included: the app name</li><li>If multiple apps are included: the number of apps</li></ul> |
| Actions | <table><thead><tr><th>Action</th><th>Remarks</th></tr></thead><tbody><tr><td>Duplicate</td><td>Copy an existing pivot report.</td></tr><tr><td>Rename</td><td>Change the name of the report.</td></tr><tr><td>View history log</td><td>See who handled the report structure, what was done, and when.</td></tr><tr><td>Copy Master API link</td><td>Generate a URL to pull the data via <Anchor target="_blank" href="/marketers/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>. To use Master API, your need to get the <Anchor target="_blank" href="/marketers/docs/managing-appsflyer-tokens">API token</Anchor> (admin permissions required) to use in the authentication header.</td></tr><tr><td>Delete</td><td>Delete the selected pivot.</td></tr></tbody></table> |
| Action | Remarks |
| Duplicate | Copy an existing pivot report. |
| Rename | Change the name of the report. |
| View history log | See who handled the report structure, what was done, and when. |
| Copy Master API link | Generate a URL to pull the data via <Anchor target="_blank" href="/marketers/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>. To use Master API, your need to get the <Anchor target="_blank" href="/marketers/docs/managing-appsflyer-tokens">API token</Anchor> (admin permissions required) to use in the authentication header. |
| Delete | Delete the selected pivot. |

</Accordion>

<div id="add-a-pivot-report" />

<Accordion title="Add a pivot report">

**To add a pivot report**:

1. Click **Add pivot.**  
   The New pivot window opens.
2. Enter the pivot name.
3. Click **Submit.**  
   The Add pivot table window opens.
4. Select apps, dimensions, and metrics. Set filters and value display settings.

| Section | Description |
| --- | --- |
| Apps | Select 1 or more apps to include in the pivot. |
| Dimensions | [<Image alt="" src="https://files.readme.io/9b0fda106b5de3401a71ceaeb45bac5cc4215b164e263a1422bf6097a9320553-360002246845.png" width="221px" />](https://files.readme.io/9b0fda106b5de3401a71ceaeb45bac5cc4215b164e263a1422bf6097a9320553-360002246845.png)<br /><br />Use dimensions to group, structure, and sort your pivot reports.<br /><br />**To select dimensions**:<ol><li>Click **Dimensions.**</li><li>Select a dimension, then drag it to a section. Dimensions have the following impact on the Pivot:<ul><li>**Rows**: Dimensions placed in rows determine the group-by hierarchy.</li><li>**Columns**: Dimensions placed in columns multiply the entire table result according to the dimension values.</li></ul></li></ol> |
| KPIs | [<Image alt="" src="https://files.readme.io/6b210b1bdc38ee96ef8b73dcacbac3389b914aaef76a680604e41d4becbad807-360000640109.png" width="294px" />](https://files.readme.io/6b210b1bdc38ee96ef8b73dcacbac3389b914aaef76a680604e41d4becbad807-360000640109.png)<br /><br />KPIs are grouped according to type as follows:<ul><li>LTV</li><li><Anchor target="_blank" href="/marketers/docs/activity-dashboard#specifications-and-limitations">Activity</Anchor></li><li>Retention: Retention day, Retention rate. **Note**: Scroll-down in the retention section to select Retention rates and Protect360 (for accounts that have Protect360 enabled.)</li><li><Anchor target="_blank" href="/marketers/docs/master-api-user-acquisition-metrics-via-api#kpis">About the metrics.</Anchor></li></ul>Most times, place KPIs in the value section. If needed, KPIs can be used as a dimension.<br /><br />Drag and drop the KPI to the relevant section. |
| Values | For each KPI, set the calculation method by selecting an operator:<ul><li>Sum</li><li>Count</li><li>Max</li><li>Min</li><li>Rate</li><li>Average</li></ul> |
| Filters | Place the required filters in the filters section. Configure how filters are set:<ul><li>Text</li><li>Multi-select</li></ul> |

</Accordion>

<div id="view-a-pivot-report" />

<Accordion title="View a pivot report">

[![](https://files.readme.io/cb549ba9b17e75f05d723cdb56335232dd40c419ebfe7ecad08b80a71be46296-360002246865.png)](https://files.readme.io/cb549ba9b17e75f05d723cdb56335232dd40c419ebfe7ecad08b80a71be46296-360002246865.png)

**To view a pivot report**:

* Select a report in the Pivot page to display it.
* Report display options:

| Section | Description |
| --- | --- |
| (1) Selected dimensions | The first column holds the dimensions selected for the groupings of the report. The dimensions are grouped according to the order in the pivot edit page. In the example above, the primary dimension is the app name, followed by the media source, and ending with the install date. |
| (2) Metrics | The rest of the columns are the KPIs selected as **Values** in the pivot edit page. In the example above, the first KPI is impressions, followed by clicks, installs, etc. |
| (3) Filters | The filters set for the report in the pivot edit page appear here. You can type your filtering string or select multiple items with the drop-down boxes.<br /><br />[**![](https://files.readme.io/e7f16a6e848b8e9f6942615dd14257b3c0e358cefabbdcfe86c498612fcaae26-115004149786.png)**](https://files.readme.io/e7f16a6e848b8e9f6942615dd14257b3c0e358cefabbdcfe86c498612fcaae26-115004149786.png) |
| (4) Date selected | Use the Date Selector to refine your search to specific dates. Select your own custom date range or use one of the preset date range buttons. |
| (5) Actions | You can access the same actions per pivot report as available in the [pivot reports list](/docs/pivot-table-user-metrics#view-a-pivot-report). |

</Accordion>

## Traits and limitations

<div id="traits-and-limitations::e6883df" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Ad network access to report | No |
| Agency access | No |
| Agency transparency | Yes |
| App-specific time zone | Yes<br /><br />Exception: In all of the following cases, AppsFlyer ignores the app-specific time zone and uses the default time zone UTC +0:<ul><li>The report contains data from multiple apps, and the apps have different time zones.</li><li>The apps all have the same time zone, and the time zone for at least one of the apps changed during the cohort report period. To determine the report period:<ul><li>Start date: The first date in the conversion date range.</li><li>End date: Calculated by adding the number of days in the display duration to the last date in the conversion date range. Example: Last date: Jan 1, 2019. Report duration: 30 days. End date: Jan 31, 2019.</li></ul></li></ul> |
| App-specific currency | Results always return in USD. |
| Organic data | Included |
| Non-organic data | Included |
| Data freshness | Data freshness: Daily. The data freshness is equivalent to that of <Anchor target="_blank" href="/marketers/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>. |
| Account user access | Yes |
| Retargeting revenue | Included |
| Campaign name changes | Pivot doesn't align the campaign name cost to the most recent campaign name reported. This means that each campaign name used will have a cost associated with it. |
| Retargeting data | <ul><li>In general, use <Anchor target="_blank" href="/marketers/docs/cohort-and-retention-dashboard">Cohort</Anchor> to view retargeting data.</li><li>Activity KPIs for traffic from after February 1, 2025 include unified data (UA and retargeting together).</li></ul> |
| Cost data | AppsFlyer gets cost data primarily via cost API. Data is provided by the integrated partners. <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">List of dimensions per integrated partner.</Anchor> |
| Retention rate | To get retention rate, include installs in the report. |
| Maximum rows per report | 200K |
| Historical data | <ul><li>LTV data: 25 months (2 years + 1 month)</li><li>Activity data: 3 years</li></ul> |
| Average DAU and Average MAU | When using Average DAU or Average MAU with the Sum aggregation across any grouping (e.g., Media Source or Campaign), the totals may include duplicate user counts. This occurs when a user performs both an install and a re-engagement within the selected period, causing them to appear under multiple groupings. |

</Accordion>

<div data-zendesk-anchors="pivot-reports-page=about-pivot-reports-page h_01HJR8389QPFKR9X6V52N7PHMM=about-pivot-reports-page h_01HJR8389QPNRX8Y26VQWN0ZXP=pivot-procedures pivot-page%E2%80%94controls-and-options=pivot-page-controls-and-options h_01HJR8389QDDWR8ZKCSDZGVAGP=pivot-page-controls-and-options h_01HJR8389R2C1E42JN9NFMS4CJ=add-a-pivot-report h_01HJR8389SQ40HZ8EXQME4807S=view-a-pivot-report h_01HJR8389SPJZG6AYGABB17V1N=traits-and-limitations h_01HJR8389S19TVMVR60ZYAJMAA=traits-and-limitations::e6883df" />
