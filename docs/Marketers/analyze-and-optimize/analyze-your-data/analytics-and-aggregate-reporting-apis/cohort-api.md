---
title: Cohort API
metadata:
  keywords:
    - API
    - Advertisers
    - Partners
    - Developer
    - Premium
    - Gray
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2020-01-14T07:04:32Z'
  edited_at: '2026-05-04T15:23:53Z'
  id: 360004799057
  locale: en-us
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/en-us/articles/360004799057-Cohort-API
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

**At a glance:** Cohort API provides advertisers a programmatic way to get Cohort data. Use the API to integrate Cohort data into BI and marketing automation systems.

## Cohort API

The Cohort API is used to get cohorted campaign performance data from the AppsFlyer platform. It is functionally equivalent to the <Anchor target="_blank" href="/marketers/docs/cohort-and-retention-dashboard">Cohort dashboard</Anchor>.

To use Cohort and retention, you define the data that you want to view. You select users from an app and segment them by conversion time. Cohort metrics like revenue, ROI, and event conversion rates are available. Break the cohort down, for comparison purposes, into dimensions like campaign or media source. The result returns as a CSV or JSON file. You can use the results to uncover patterns or changes in performance over user or campaign life cycles.

See <Anchor target="_blank" href="https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689">Cohort use cases</Anchor>.

**To use Cohort API**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/8b676172a491d1cea655002549ae49f6d974a15e4865ea90392121d22ce95426-32131110605713.png) Get the <Anchor target="_blank" href="/marketers/docs/managing-appsflyer-tokens">API token</Anchor>. An admin needs to retrieve the token.
2. Give your developer the API token to be used in the authentication header.
3. Give your developers the [parameters](#filtering-and-grouping-parameters) to input when they make the API call, as described in the sections that follow. The parameters determine what the report focuses on, how it's organized, and provide a reporting timeframe.
4. Tell your developer to follow their <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_app-id">Cohort API instructions</Anchor> in the developer hub.

<div id="filtering-and-grouping-parameters" />

<Accordion title="Cohort API parameters">

Use the following parameters to get the necessary data.

| Parameter name | Description | Mandatory |
| --- | --- | --- |
| <span id="bearer"></span>bearer | API token used in the API authentication header. | Yes |
| <span id="cohort-_type"></span>cohort \_type | Cohort attribution (conversion) type is one of the following: `user_acquisition`, `retargeting`, `unified`<ul><li>Unified combines the performance of user acquisition and retargeting campaigns.</li><li>If an event is attributed to both retargeting and user acquisition campaigns, only the retargeting event is included in KPIs returned, meaning is\_primary=true.</li><li>Format: String</li><li>Example: `"cohort_type": "user_acquisition"`</li></ul> | Yes |
| <span id="min_cohort_size"></span>min\_cohort\_size | Minimum cohort size is used to reduce the number of records returned by excluding cohorts having few users. This means that the "users" KPI has a value equal or greater to that specified.<ul><li>Format: Integer</li><li>Minimum value allowed: 1. Don't send 0 (Zero)</li><li>Default: 1</li><li>Example: `"min_cohort_size": 50`</li></ul> | No |
| <span id="from"></span>from | Lower bound of the LTV attribution date range. The earliest date supported is 720 days before the current date.<ul><li>Format: String yyyy-mm-dd</li><li>Example: `"from": "2020-01-02"`</li></ul> | Yes |
| <span id="to"></span>to | Higher bound of the LTV attribution date range<ul><li>Number of the days in the range: 1-31 days</li><li>For a single day: `from` and `to` values are identical.</li><li>Format: yyyy-mm-dd</li><li>Example: `"from": "2020-01-01", "to": 2020-01-31` is 31 days.</li></ul> | Yes |
| <span id="granularity"></span>granularity | Hourly granularity for the previous 72 hours by setting  `"granularity": "hour"` and setting the `from` and `to` range to include the time of day.<ul><li>Format: yyyy-mm-dd hh:mm:ss</li><li>Example:</li></ul>`"granularity": "hour", "from": "2021-12-01 14:00:00", "to": "2021-12-03 11:00:00",` | No |
| <span id="partial_data"></span>partial\_data | To avoid data distortion and misinterpretation Cohort returns data of complete days. However, the data of partial days can be useful.<br /><br />The number of complete cohort days for a query is calculated as the difference between today's date and the *to* date.<ul><li>[Default] If false, complete days return.</li><li>If true, up to 180 cohort days return, including days having incomplete data.</li><li>Format: Boolean</li><li>Platform UI version: false</li></ul>**Example**: On May 10, the number of complete cohort days for users converting during April 1-30, is 10.<ul><li>If false [default], cohort days 0-9, return. This is the number of days (10) between the last conversion date and today.</li><li>If true, cohort days 1-40 return. Days 11-40 contain partial data and do not return. For example, since April 20, only 20 days have elapsed, and so on.</li></ul>**Note**: Partial data is only allowed when the aggregation type is cumulative. | No |
| <span id="filters"></span>filters | Filter the data and period days returned. Select filters from the [filter dimensions list](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).<ul><li>Format: Strings in a nested JSON. Values need to be in an array.</li><li>**Example limit to specific Geos:** `"filters": {"geo": ["US"]}` includes only users attributed to the United States.</li><li>**Example period (cohort) days**: The `period` filter sets the days for which measures are returned. The possible values are: 0-180.</li><li>Default: If no period filter is set the days 0-30, 60, 90, and 180 return. [Example filter with period](/docs/cohort-api#using-period-filters)</li></ul> | No |
| <span id="groupings"></span>groupings | <ul><li>Use grouping parameters to include additional columns and make your reports less granular.</li><li>Select 1-7 groupings from the [grouping dimensions list](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).</li><li>Format: Strings in an array</li><li>Example: `"groupings": ["af_ad", "c", "af_c_id", "af_prt"]`</li></ul> | Yes |
| <span id="kpis"></span>kpis | KPIs are the metrics used for gaining insights into the behavior of your app. [Learn how to select and format KPIs](/docs/cohort-api#selecting-and-formatting-kpis) | Yes |
| <span id="preferred_currency"></span>preferred\_currency | A parameter that sets the format of the KPIs returned. [Learn how to format KPIs](/docs/cohort-api#formatting-kpi-functions) | No |
| <span id="preferred_timezone"></span>preferred\_timezone | A parameter that sets the format of the KPIs returned. [Learn how to format KPIs](/docs/cohort-api#formatting-kpi-functions) | No |
| <span id="aggregation_type"></span>aggregation\_type | A parameter that sets the format of the KPIs returned. [Learn how to format KPIs](/docs/cohort-api#formatting-kpi-functions) | Yes |
| <span id="per_user"></span>per\_user | A parameter that sets the format of the KPIs returned. [Learn how to format KPIs](/docs/cohort-api#formatting-kpi-functions) | No |

</Accordion>

<div id="selecting-and-formatting-kpis" />

<Accordion title="Selecting and formatting KPIs">

* The table lists the KPIs available and their associated functions. When you call a KPI, all its functions return.
* The following KPIs always return: users, ecpi, and cost
* Select one additional KPI per call.
* For each KPI requested, all functions are returned.
* Format: Strings in an array
  * Example A: `"kpis": ["sessions"]`
  * Example B: `"kpis": ["event_name"]`

<table><thead><tr><th> </th><th> </th><th colspan="5">Functions</th></tr><tr><th rowspan="2">Default/ Optional </th><th rowspan="2">KPI (Dimensions name) </th><th>Count</th><th>cvr (conversion rate)</th><th>Rate</th><th>Sum</th><th>Unique users</th></tr><tr><th>Number</th><th>Percentage</th><th>Percentage</th><th>Number</th><th>Number</th></tr></thead><tbody><tr><td>Always</td><td>users</td><td><span>Y</span></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>Always</td><td>ecpi</td><td>-</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>Always</td><td>cost</td><td>-</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>Optional</td><td><code>"event_name"</code>(4) </td><td><span>Y</span></td><td><span>Y</span></td><td>-</td><td><span>Y (3)</span></td><td><span>Y</span></td></tr><tr><td>Optional</td><td>revenue</td><td><span>Y</span></td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>Optional</td><td>roas</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>Optional</td><td>roi</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>Optional</td><td>sessions</td><td><span>Y</span></td><td>-</td><td><span>Y</span></td><td>-</td><td><span>Y(1)</span></td></tr><tr><td>Optional</td><td>uninstalls (2)</td><td><span>Y</span></td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td colspan="7"><p>(1) Unique sessions returns when <em>aggregation_type=on_day</em></p><p>(2) Not available when cohort_type=unified </p><p>(3) Sum means the total revenue generated by the event. In the report, this is denoted by <code>sum_event_name"</code></p><p>(4) Note! Event names are case-sensitive</p></td></tr></tbody></table>

#### Formatting KPI functions

The following parameters set the format of the KPIs returned.

| Parameter | Values | Mandatory |
| --- | --- | --- |
| preferred\_currency | KPI revenue currency<ul><li>If true, revenue is returned using the <Anchor target="_blank" href="/marketers/docs/app-settings#localization-currency">app-specific currency</Anchor> set in the platform.</li><li>[Default] If false, results return in USD.</li><li>Format: Boolean</li><li>Platform UI version: true</li></ul> | No |
| preferred\_timezone | **Time zone of data ranges**<ul><li>If true, times are expressed using the <Anchor target="_blank" href="/marketers/docs/app-settings#localization-time-zone">app-specific timezone</Anchor> set in the platform.</li><li>[Default] If false, times are expressed using UTC time zone.</li><li>Format: Boolean</li><li>Platform UI version: true</li></ul> | No |
| aggregation\_type | <ul><li>`cumulative`</li><li>`on_day`</li></ul>`"aggregation_type": "cumulative"`<br /><br />`Format: String` | Yes |
| per\_user | Divide the KPI function by the number of app users. Applies only to relevant KPIs.<ul><li>If true, KPI values are divided by the number of users in the cohort.</li><li>If false, KPI values are not divided by the number of users.</li><li>Format: Boolean</li><li>Example if true: total revenue is $1000, the number of app users is 500, the value returned is $2.</li></ul> | No |

</Accordion>

<div id="list-of-group-by-and-filter-by-dimensions" />

<Accordion title="Group by and filter dimensions">

<table><thead><tr><th>Dimension name </th><th>Dimension API value</th><th>Groupings</th><th>Filters</th></tr></thead><tbody><tr><td>Ad</td><td>af_ad</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Ad ID</td><td>af_ad_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Campaign</td><td>c</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Campaign ID</td><td>af_c_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Channel</td><td>af_channel</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Media Source</td><td>pid</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Sub Param 1</td><td>af_sub1</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Keywords</td><td>af_keywords</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Agency</td><td>af_prt</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Conversion Type (1) </td><td>cohort_type</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Site ID</td><td>site_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Revenue Type (2)</td><td>revenue_type</td><td><span>x </span></td><td><span>Y</span></td></tr><tr><td>Attributed Touch Type (3)</td><td>attributed_touch_type</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Adset</td><td>af_adset</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Adset ID</td><td>af_adset_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Country</td><td>geo</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Date (install/re-attribution/re-engagement date in the context of the cohort_type selected) </td><td>date</td><td><span>Y</span></td><td><span>x </span></td></tr><tr><td>Period</td><td><p>period</p><p><a href="./cohort-api#using-period-filters">Detailed explanation</a></p></td><td><span>x</span></td><td><span>Y</span></td></tr><tr><td colspan="4"><p>Notes: </p><p>Dimension options:</p><p>(1) Conversion Type:  <code>user_acquisition</code>, <code>retargeting</code>(<code>re-engagement</code> and <code>re-attribution</code>), <code>unified</code></p><ul><li>When exporting:<ul><li><code>re-engagement</code> will show as <code>retargeting</code></li><li><code>re-attribution</code> will show as <code>reattr</code></li></ul></li></ul><p>(2) Revenue Type: <code>regular</code>, <code>ad_monetization</code><span></span></p><p>(3) Attributed Touch Type: <code>click</code>, <code>impression</code>, <code>TV</code>, <code>pre-installed</code></p></td></tr></tbody></table>

</Accordion>

## Additional information

<div id="using-period-filters" />

<Accordion title="Using period filters">

Period refers to the day post-attribution, where period 0 is the attribution day. For example, a user installs the app on January 1. This is the attribution day. A purchase made on period 0 means it was made on January 1. A purchase made on period 3 means it was made on January 4. Similarly, a user who installs on January 11, this is period 0. A purchase made on January 14 would be period 3.

If your report date range is January 1 to January 11 users who attributed (installed) during this period are included in the report. No other data is included.

* The value of the period can be one or more of the following 0-180. For example, 0, 1, 2, 30, 180.
* If no period is specified, the default values of 0, 1, 2, and so on to 30, 60, 90, and 180 return.

> 📄 **Example period filter**
>
> * This example contains the JSON query parameters, raw data, and resulting CSV file.
> * The query *filters period* of 0, 1, and 2 and the KPI selected is *revenue*.
> * The query specifies the aggregation type as "cumulative". Change to "on\_day" if you want on-day data.
> * As a result, the data returned contains:
>   * The measures of users, cost, and ecpi which always return
>   * Revenue measures consisting of sum and count for each period meaning periods 0, 1, and 2.
>
> **Query**
>
> ```json
> {
>     "cohort_type": "user_acquisition",
>     "min_cohort_size": 1,
>     "preferred_timezone": false,
>     "from": "2019-12-01",
>     "to": "2020-01-01",
>     "filters": {
>         "period": [
>             0,
>             1,
>             2
>         ]
>     },
>     "aggregation_type": "cumulative",
>     "per_user": false,
>     "groupings": [
>         "pid"
>     ],
>     "kpis": [
>         "revenue"
>     ]
> }
> ```
>
> **Raw data**
>
> **![mceclip1.png](https://files.readme.io/846aade481d3b5fa72536817533bc3edad721f1ce6015edcb48bd500461342b9-32131110606865.png)**
>
> **Results**
>
> ![mceclip0.png](https://files.readme.io/c284e5133e4e811b9416c850e399ddefb3c5bfcfcf879f469556b7a6bc0062c6-32131110607249.png)

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Ad network access | No |
| Agency access | No |
| App-specific time zone | Yes |
| App-specific currency | Yes |
| Size limitations | None |
| Rate limitation | <ul><li>API call-rate limit: 60 calls per minute and 50,000 calls a day per account</li><li>Queries return up to 30,000 rows</li></ul> |
| Organic data | Available |
| Non-organic data | Available |
| Cost data limitation | <ul><li>Cost data is only for campaigns with at least 1 recorded install.</li><li>AppsFlyer does not report cost data for keywords that contain uppercase letters in the cohort report or cohort API</li><li>You can't combine some groupings combinations with cost. For example, Meta ads can have either geo or channel groupings but not both. The exact combination of groupings is ad network dependent.</li></ul> |
| Data freshness | Data freshness depends on [partial\_data](/docs/cohort-api#partial_data) as follows:<ul><li>[Default] If false, <Anchor target="_blank" href="/marketers/docs/about-data-freshness-and-timezone-support#daily-processing">Daily</Anchor></li><li>If true, <Anchor target="_blank" href="/marketers/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">Continuous (real-time)</Anchor></li><li>Cost and uninstall metrics update daily in all instances</li></ul> |
| Historical data | Daily cohort: 2 years |
| Account user access | The authorization token is available to admin users in the dashboard |
| Ad revenue | For af\_ad\_revenue events, the unique users metric isn't available when the aggregation type is:<ul><li>Cumulative.</li><li>"On day," for dates between October 5, 2022-February 16, 2023.</li></ul> |
| Weekly and monthly groupings | Weekly and monthly dimension groupings aren't available with the Cohort API. Use the Cohort dashboard. |
| Cohort API period | <ul><li>The conversion period is referred to as 0 (Hour 0 or Day 0). The next period after the conversion is referred to as 1 (Hour 1 or Day 1), and so on.</li><li>In AppsFlyer a cohort period doesn't take into account the specific install timestamp. Rather, cohort hours are rounded down to the nearest hour, and cohort days, are based on the calendar day. This may cause discrepancies when comparing AppsFlyer cohort data to the cohort data of other networks, where all cohort periods are determined by the specific install timestamp (meaning an hour is 60 minutes post-install timestamp, and a day is the 24-hour post-install period after the install timestamp).</li></ul> |
| Dates | <ul><li>Dates or date ranges refer to lifetime value (<Anchor target="_blank" href="/marketers/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV)</Anchor> dates, meaning the date the user attributed (converted) and not the date of the activity itself.</li><li>Earliest date supported: 730 days before the current date. Meaning 2 years</li><li>Maximum query range: 60 days.</li></ul> |
| Reinstalls | <ul><li>If post-reinstall events are considered unattributed organic:<ul><li>They're included only as of May 26, 2024. <Anchor target="_blank" href="/marketers/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">Learn more</Anchor></li><li>The install time is based on the <Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor> field.</li><li>They aren't counted toward unique user and retention measurements.</li></ul></li><li>If post-reinstall events are attributed to the first install, they're always included. <Anchor target="_blank" href="/marketers/docs/unique-users">Learn more</Anchor></li></ul> |
| Cohort API for partners | Access to the Cohort API for marketing partners is being deprecated as of September 15th, 2024. Marketing partners are encouraged to <Anchor target="_blank" href="/partners/docs/data-locker-reports-for-api-partners">enable Data Locker</Anchor> to ensure continued access to customer data. |

</Accordion>

<div data-zendesk-anchors="cohort-reporting-api=cohort-api 01H7WFZR41YAQX4MFPBMJD1MBP=cohort-api 01H7WFZR42H3CA0CSB4E3XED3H=filtering-and-grouping-parameters 01H7WFZR42XV4JY46GY11KT3CF=selecting-and-formatting-kpis presentation-of-kpi-functions=formatting-kpi-functions 01H7WFZR43HFF65TSWG1AN0JTB=formatting-kpi-functions 01H7WFZR43BJ8E6KVHSGV4CDDP=list-of-group-by-and-filter-by-dimensions h_01HMY09W324E54VPZWPJVS2KB8=additional-information 01H7WFZR440NTXWWQ2T4P2ANWK=using-period-filters 01H7WFZR44RCXA56CXSCEZ0KXH=example-period-filter 01H7WFZR45VC96KYW1W9A8PBFT=traits-and-limitations" />
