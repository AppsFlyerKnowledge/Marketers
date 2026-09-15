---
title: "Pivot table—user metrics"
excerpt: "Learn how to view and customize user metrics like LTV, activity, Protect360, and retention using AppsFlyer Pivot reports."
---
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

### Pivot page—controls and options



| Column/option | Description |
| --- | --- |
| Name | Select a report name to view the associated pivot. |
| Column click | Some columns, as indicated in the interface, are sorted by clicking on the column name. |
| Last modified | Last time the report structure was modified. |
| Modified by | Name of the user who modified the pivot. |
| App name | * If one app included: the app name<br />* If multiple apps are included: the number of apps |
| Actions | \| Action \| Remarks \|<br />\| --- \| --- \|<br />\| Duplicate \| Copy an existing pivot report. \|<br />\| Rename \| Change the name of the report. \|<br />\| View history log \| See who handled the report structure, what was done, and when. \|<br />\| Copy Master API link \| Generate a URL to pull the data via [Master API](/docs/master-api-user-acquisition-metrics-via-api). To use Master API, your need to get the [API token](/docs/managing-appsflyer-tokens) (admin permissions required) to use in the authentication header. \|<br />\| Delete \| Delete the selected pivot. \| |
| Action | Remarks |
| Duplicate | Copy an existing pivot report. |
| Rename | Change the name of the report. |
| View history log | See who handled the report structure, what was done, and when. |
| Copy Master API link | Generate a URL to pull the data via [Master API](/docs/master-api-user-acquisition-metrics-via-api). To use Master API, your need to get the [API token](/docs/managing-appsflyer-tokens) (admin permissions required) to use in the authentication header. |
| Delete | Delete the selected pivot. |



### Add a pivot report

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
| Dimensions | [![](https://support.appsflyer.com/hc/article_attachments/360002246845)](https://support.appsflyer.com/hc/article_attachments/360002246845)<br /><br />Use dimensions to group, structure, and sort your pivot reports.<br /><br />**To select dimensions**:<br /><br />1. Click **Dimensions.**<br />2. Select a dimension, then drag it to a section. Dimensions have the following impact on the Pivot:<br />   * **Rows**: Dimensions placed in rows determine the group-by hierarchy.<br />   * **Columns**: Dimensions placed in columns multiply the entire table result according to the dimension values. |
| KPIs | [![](https://support.appsflyer.com/hc/article_attachments/360000640109)](https://support.appsflyer.com/hc/article_attachments/360000640109)<br /><br />KPIs are grouped according to type as follows:<br /><br />* LTV<br />* [Activity](/docs/activity-dashboard#specifications-and-limitations)<br />* Retention: Retention day, Retention rate. **Note**: Scroll-down in the retention section to select Retention rates and Protect360 (for accounts that have Protect360 enabled.)<br />* [About the metrics.](/docs/master-api-user-acquisition-metrics-via-api#kpis)<br /><br />Most times, place KPIs in the value section. If needed, KPIs can be used as a dimension.<br /><br />Drag and drop the KPI to the relevant section. |
| Values | For each KPI, set the calculation method by selecting an operator:<br /><br />* Sum<br />* Count<br />* Max<br />* Min<br />* Rate<br />* Average |
| Filters | Place the required filters in the filters section. Configure how filters are set:<br /><br />* Text<br />* Multi-select |



### View a pivot report

[![](https://support.appsflyer.com/hc/article_attachments/360002246865)](https://support.appsflyer.com/hc/article_attachments/360002246865)

**To view a pivot report**:

* Select a report in the Pivot page to display it.
* Report display options:



| Section | Description |
| --- | --- |
| (1) Selected dimensions | The first column holds the dimensions selected for the groupings of the report. The dimensions are grouped according to the order in the pivot edit page. In the example above, the primary dimension is the app name, followed by the media source, and ending with the install date. |
| (2) Metrics | The rest of the columns are the KPIs selected as **Values** in the pivot edit page. In the example above, the first KPI is impressions, followed by clicks, installs, etc. |
| (3) Filters | The filters set for the report in the pivot edit page appear here. You can type your filtering string or select multiple items with the drop-down boxes.<br /><br />[**![](https://support.appsflyer.com/hc/article_attachments/115004149786)**](https://support.appsflyer.com/hc/article_attachments/115004149786) |
| (4) Date selected | Use the Date Selector to refine your search to specific dates. Select your own custom date range or use one of the preset date range buttons. |
| (5) Actions | You can access the same actions per pivot report as available in the [pivot reports list](/docs/pivot-table-user-metrics#view-a-pivot-report). |



## Traits and limitations

### Traits and limitations



| Trait | Remarks |
| --- | --- |
| Ad network access to report | No |
| Agency access | No |
| Agency transparency | Yes |
| App-specific time zone | Yes<br /><br />Exception: In all of the following cases, AppsFlyer ignores the app-specific time zone and uses the default time zone UTC +0:<br /><br />* The report contains data from multiple apps, and the apps have different time zones.<br />* The apps all have the same time zone, and the time zone for at least one of the apps changed during the cohort report period. To determine the report period:<br />  * Start date: The first date in the conversion date range.<br />  * End date: Calculated by adding the number of days in the display duration to the last date in the conversion date range. Example: Last date: Jan 1, 2019. Report duration: 30 days. End date: Jan 31, 2019. |
| App-specific currency | Results always return in USD. |
| Organic data | Included |
| Non-organic data | Included |
| Data freshness | Data freshness: Daily. The data freshness is equivalent to that of [Master API](/docs/master-api-user-acquisition-metrics-via-api). |
| Account user access | Yes |
| Retargeting revenue | Included |
| Campaign name changes | Pivot doesn't align the campaign name cost to the most recent campaign name reported. This means that each campaign name used will have a cost associated with it. |
| Retargeting data | * In general, use [Cohort](/docs/cohort-and-retention-dashboard) to view retargeting data.<br />* Activity KPIs for traffic from after February 1, 2025 include unified data (UA and retargeting together). |
| Cost data | AppsFlyer gets cost data primarily via cost API. Data is provided by the integrated partners. [List of dimensions per integrated partner.](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) |
| Retention rate | To get retention rate, include installs in the report. |
| Maximum rows per report | 200K |
| Historical data | * LTV data: 25 months (2 years + 1 month)<br />* Activity data: 3 years |
| Average DAU and Average MAU | When using Average DAU or Average MAU with the Sum aggregation across any grouping (e.g., Media Source or Campaign), the totals may include duplicate user counts. This occurs when a user performs both an install and a re-engagement within the selected period, causing them to appear under multiple groupings. |