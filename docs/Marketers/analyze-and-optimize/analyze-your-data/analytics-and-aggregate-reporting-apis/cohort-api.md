---
title: "Cohort API"
excerpt: "The Cohort API provides advertisers with a programmatic way to retrieve cohorted campaign performance data from the AppsFlyer platform."
x-zendesk:
  id: 360004799057
  url: https://support.appsflyer.com/hc/en-us/articles/360004799057-Cohort-API
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  position: 6
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-nohar-avigal, Marketers, Marketing Analytics]
  labels: [API, Advertisers, Partners, Developer, Premium, Gray, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2020-01-14T07:04:32Z'
  edited_at: '2026-05-04T15:23:53Z'
---
**At a glance:** Cohort API provides advertisers a programmatic way to get Cohort data. Use the API to integrate Cohort data into BI and marketing automation systems.

## Cohort API

The Cohort API is used to get cohorted campaign performance data from the AppsFlyer platform. It is functionally equivalent to the [Cohort dashboard](/docs/cohort-and-retention-dashboard).

To use Cohort and retention, you define the data that you want to view. You select users from an app and segment them by conversion time. Cohort metrics like revenue, ROI, and event conversion rates are available. Break the cohort down, for comparison purposes, into dimensions like campaign or media source. The result returns as a CSV or JSON file. You can use the results to uncover patterns or changes in performance over user or campaign life cycles.

See [Cohort use cases](https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689).

**To use Cohort API**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/8b676172a491d1cea655002549ae49f6d974a15e4865ea90392121d22ce95426-32131110605713.png) Get the [API token](/docs/managing-appsflyer-tokens). An admin needs to retrieve the token.
2. Give your developer the API token to be used in the authentication header.
3. Give your developers the [parameters](/docs/cohort-api#filtering-and-grouping-parameters) to input when they make the API call, as described in the sections that follow. The parameters determine what the report focuses on, how it's organized, and provide a reporting timeframe.
4. Tell your developer to follow their [Cohort API instructions](https://dev.appsflyer.com/hc/reference/post_app-id) in the developer hub.

### Cohort API parameters

Use the following parameters to get the necessary data.

| Parameter name | Description | Mandatory |
| --- | --- | --- |
| bearer | API token used in the API authentication header. | Yes |
| cohort \_type | Cohort attribution (conversion) type is one of the following: `user_acquisition`, `retargeting`, `unified`<br />- Unified combines the performance of user acquisition and retargeting campaigns.<br />- If an event is attributed to both retargeting and user acquisition campaigns, only the retargeting event is included in KPIs returned, meaning is\_primary=true.<br />- Format: String<br />- Example: `"cohort_type": "user_acquisition"` | Yes |
| min\_cohort\_size | Minimum cohort size is used to reduce the number of records returned by excluding cohorts having few users. This means that the "users" KPI has a value equal or greater to that specified. <br />- Format: Integer<br />- Minimum value allowed: 1. Don't send 0 (Zero)<br />- Default: 1 <br />- Example: `"min_cohort_size": 50` | No |
| from | Lower bound of the LTV attribution date range. The earliest date supported is 720 days before the current date. <br />- Format: String yyyy-mm-dd<br />- Example: `"from": "2020-01-02"` | Yes |
| to | Higher bound of the LTV attribution date range<br />- Number of the days in the range: 1-31 days<br />- For a single day: `from` and `to` values are identical. <br />- Format: yyyy-mm-dd<br />- Example: `"from": "2020-01-01", "to": 2020-01-31` is 31 days. | Yes |
| granularity | Hourly granularity for the previous 72 hours by setting  `"granularity": "hour"` and setting the `from` and `to` range to include the time of day.<br />- Format: yyyy-mm-dd hh:mm:ss<br />- Example:<br />`"granularity": "hour", "from": "2021-12-01 14:00:00", "to": "2021-12-03 11:00:00",` | No |
| partial\_data | To avoid data distortion and misinterpretation Cohort returns data of complete days. However, the data of partial days can be useful. <br />The number of complete cohort days for a query is calculated as the difference between today's date and the _to_ date.<br />- [Default] If false, complete days return.<br />- If true, up to 180 cohort days return, including days having incomplete data. <br />- Format: Boolean<br />- Platform UI version: false<br />**Example**: On May 10, the number of complete cohort days for users converting during April 1-30, is 10. <br />- If false [default], cohort days 0-9, return. This is the number of days (10) between the last conversion date and today. <br />- If true, cohort days 1-40 return. Days 11-40 contain partial data and do not return. For example, since April 20, only 20 days have elapsed, and so on.<br />**Note**: Partial data is only allowed when the aggregation type is cumulative. | No |
| filters | Filter the data and period days returned. Select filters from the [filter dimensions list](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).<br />- Format: Strings in a nested JSON. Values need to be in an array.<br />- **Example limit to specific Geos:**`"filters": {"geo": ["US"]}` includes only users attributed to the United States. <br />- **Example period (cohort) days**: The `period` filter sets the days for which measures are returned. The possible values are: 0-180. <br />- Default: If no period filter is set the days 0-30, 60, 90, and 180 return. [Example filter with period](/docs/cohort-api#using-period-filters) | No |
| groupings | - Use grouping parameters to include additional columns and make your reports less granular.<br />- Select 1-7 groupings from the [grouping dimensions list](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).<br />- Format: Strings in an array<br />- Example: `"groupings": ["af_ad", "c", "af_c_id", "af_prt"]` | Yes |
| kpis | KPIs are the metrics used for gaining insights into the behavior of your app. [Learn how to select and format KPIs](/docs/cohort-api#selecting-and-formatting-kpis) | Yes |
| preferred\_currency | A parameter that sets the format of the KPIs returned. [Learn how to format KPIs](/docs/cohort-api#presentation-of-kpi-functions) | No |
| preferred\_timezone | A parameter that sets the format of the KPIs returned. [Learn how to format KPIs](/docs/cohort-api#presentation-of-kpi-functions) | No |
| aggregation\_type | A parameter that sets the format of the KPIs returned. [Learn how to format KPIs](/docs/cohort-api#presentation-of-kpi-functions) | Yes |
| per\_user | A parameter that sets the format of the KPIs returned. [Learn how to format KPIs](/docs/cohort-api#presentation-of-kpi-functions) | No |

### Selecting and formatting KPIs

- The table lists the KPIs available and their associated functions. When you call a KPI, all its functions return.
- The following KPIs always return: users, ecpi, and cost
- Select one additional KPI per call.
- For each KPI requested, all functions are returned.
- Format: Strings in an array
  - Example A: `"kpis": ["sessions"]`
  - Example B: `"kpis": ["event_name"]`

| Default/ Optional | KPI (Dimensions name) | Count | cvr (conversion rate) | Rate | Sum | Unique users |
| --- | --- | --- | --- | --- | --- | --- |
| | | Number | Percentage | Percentage | Number | Number |
| Always | users | Y | - | - | - | - |
| Always | ecpi | - | - | - | Y | - |
| Always | cost | - | - | - | Y | - |
| Optional | `"event_name"`(4) | Y | Y | - | Y (3) | Y |
| Optional | revenue | Y | - | - | Y | - |
| Optional | roas | - | - | Y | - | - |
| Optional | roi | - | - | Y | - | - |
| Optional | sessions | Y | - | Y | - | Y(1) |
| Optional | uninstalls (2) | Y | - | Y | - | - |

(1) Unique sessions returns when _aggregation\_type=on\_day_<br />(2) Not available when cohort\_type=unified <br />(3) Sum means the total revenue generated by the event. In the report, this is denoted by `sum_event_name"`<br />(4) Note! Event names are case-sensitive

#### Formatting KPI functions

The following parameters set the format of the KPIs returned.

| Parameter | Values | Mandatory |
| --- | --- | --- |
| preferred\_currency | KPI revenue currency<br />- If true, revenue is returned using the [app-specific currency](/docs/app-settings#localization-currency) set in the platform. <br />- [Default] If false, results return in USD.<br />- Format: Boolean <br />- Platform UI version: true | No |
| preferred\_timezone | **Time zone of data ranges**<br />- If true, times are expressed using the [app-specific timezone](/docs/app-settings#localization-time-zone) set in the platform.<br />- [Default] If false, times are expressed using UTC time zone.<br />- Format: Boolean <br />- Platform UI version: true | No |
| aggregation\_type | - `cumulative`<br />- `on_day`<br />`"aggregation_type": "cumulative"`<br />`Format: String` | Yes |
| per\_user | Divide the KPI function by the number of app users. Applies only to relevant KPIs.<br />- If true, KPI values are divided by the number of users in the cohort.<br />- If false, KPI values are not divided by the number of users.<br />- Format: Boolean <br />- Example if true: total revenue is $1000, the number of app users is 500, the value returned is $2. | No |

### Group by and filter dimensions

| Dimension name | Dimension API value | Groupings | Filters |
| --- | --- | --- | --- |
| Ad | af\_ad | Y | Y |
| Ad ID | af\_ad\_id | Y | Y |
| Campaign | c | Y | Y |
| Campaign ID | af\_c\_id | Y | Y |
| Channel | af\_channel | Y | Y |
| Media Source | pid | Y | Y |
| Sub Param 1 | af\_sub1 | Y | Y |
| Keywords | af\_keywords | Y | Y |
| Agency | af\_prt | Y | Y |
| Conversion Type (1) | cohort\_type | Y | Y |
| Site ID | site\_id | Y | Y |
| Revenue Type (2) | revenue\_type | x | Y |
| Attributed Touch Type (3) | attributed\_touch\_type | Y | Y |
| Adset | af\_adset | Y | Y |
| Adset ID | af\_adset\_id | Y | Y |
| Country | geo | Y | Y |
| Date (install/re-attribution/re-engagement date in the context of the cohort\_type selected) | date | Y | x |
| Period | period<br />[Detailed explanation](/docs/cohort-api#using-period-filters) | x | Y |

Notes: <br />Dimension options:<br />(1) Conversion Type:  `user_acquisition`, `retargeting`(`re-engagement` and `re-attribution`), `unified`<br />- When exporting:<br />  - `re-engagement` will show as `retargeting`<br />  - `re-attribution` will show as `reattr`<br />(2) Revenue Type: `regular`, `ad_monetization`<br />(3) Attributed Touch Type: `click`, `impression`, `TV`, `pre-installed`

## Additional information

### Using period filters

Period refers to the day post-attribution, where period 0 is the attribution day. For example, a user installs the app on January 1. This is the attribution day. A purchase made on period 0 means it was made on January 1. A purchase made on period 3 means it was made on January 4. Similarly, a user who installs on January 11, this is period 0. A purchase made on January 14 would be period 3.

If your report date range is January 1 to January 11 users who attributed (installed) during this period are included in the report. No other data is included.

- The value of the period can be one or more of the following 0-180. For example, 0, 1, 2, 30, 180.
- If no period is specified, the default values of 0, 1, 2, and so on to 30, 60, 90, and 180 return.

#### Example period filter

- This example contains the JSON query parameters, raw data, and resulting CSV file.
- The query _filters period_ of 0, 1, and 2 and the KPI selected is _revenue_.
- The query specifies the aggregation type as "cumulative". Change to "on\_day" if you want on-day data.
- As a result, the data returned contains:
  - The measures of users, cost, and ecpi which always return
  - Revenue measures consisting of sum and count for each period meaning periods 0, 1, and 2.

**Query**

```json
{
    "cohort_type": "user_acquisition",
    "min_cohort_size": 1,
    "preferred_timezone": false,
    "from": "2019-12-01",
    "to": "2020-01-01",
    "filters": {
        "period": [
            0,
            1,
            2
        ]
    },
    "aggregation_type": "cumulative",
    "per_user": false,
    "groupings": [
        "pid"
    ],
    "kpis": [
        "revenue"
    ]
}
```

**Raw data**

![mceclip1.png](https://files.readme.io/846aade481d3b5fa72536817533bc3edad721f1ce6015edcb48bd500461342b9-32131110606865.png)

**Results**

![mceclip0.png](https://files.readme.io/c284e5133e4e811b9416c850e399ddefb3c5bfcfcf879f469556b7a6bc0062c6-32131110607249.png)

### Traits and limitations

| Trait | Remarks |
| --- | --- |
| Ad network access | No |
| Agency access | No |
| App-specific time zone | Yes |
| App-specific currency | Yes |
| Size limitations | None |
| Rate limitation | - API call-rate limit: 60 calls per minute and 50,000 calls a day per account<br />- Queries return up to 30,000 rows |
| Organic data | Available |
| Non-organic data | Available |
| Cost data limitation | - Cost data is only for campaigns with at least 1 recorded install.<br />- AppsFlyer does not report cost data for keywords that contain uppercase letters in the cohort report or cohort API<br />- You can't combine some groupings combinations with cost. For example, Meta ads can have either geo or channel groupings but not both. The exact combination of groupings is ad network dependent. |
| Data freshness | Data freshness depends on [partial\_data](/docs/cohort-api#partial_data) as follows: <br />- [Default] If false, [Daily](/docs/about-data-freshness-and-timezone-support#daily)<br />- If true, [Continuous (real-time)](/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime)<br />- Cost and uninstall metrics update daily in all instances |
| Historical data | Daily cohort: 2 years |
| Account user access | The authorization token is available to admin users in the dashboard |
| Ad revenue | For af\_ad\_revenue events, the unique users metric isn't available when the aggregation type is:<br />- Cumulative.<br />- "On day," for dates between October 5, 2022-February 16, 2023. |
| Weekly and monthly groupings | Weekly and monthly dimension groupings aren't available with the Cohort API. Use the Cohort dashboard. |
| Cohort API period | - The conversion period is referred to as 0 (Hour 0 or Day 0). The next period after the conversion is referred to as 1 (Hour 1 or Day 1), and so on.<br />- In AppsFlyer a cohort period doesn't take into account the specific install timestamp. Rather, cohort hours are rounded down to the nearest hour, and cohort days, are based on the calendar day. This may cause discrepancies when comparing AppsFlyer cohort data to the cohort data of other networks, where all cohort periods are determined by the specific install timestamp (meaning an hour is 60 minutes post-install timestamp, and a day is the 24-hour post-install period after the install timestamp). |
| Dates | - Dates or date ranges refer to lifetime value ( [LTV)](/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports) dates, meaning the date the user attributed (converted) and not the date of the activity itself.<br />- Earliest date supported: 730 days before the current date. Meaning 2 years<br />- Maximum query range: 60 days. |
| Reinstalls | - If post-reinstall events are considered unattributed organic:<br />  - They're included only as of May 26, 2024. [Learn more](/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events)<br />  - The install time is based on the [device\_download\_time](/docs/raw-data-field-dictionary#device-info::dfd9504e) field.<br />  - They aren't counted toward unique user and retention measurements.<br />- If post-reinstall events are attributed to the first install, they're always included. [Learn more](/docs/unique-users) |
| Cohort API for partners | Access to the Cohort API for marketing partners is being deprecated as of September 15th, 2024. Marketing partners are encouraged to [enable Data Locker](/docs/data-locker-reports-for-api-partners) to ensure continued access to customer data. |