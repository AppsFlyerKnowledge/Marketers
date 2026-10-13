---
title: "Single Source of Truth (SSOT) Data Locker report for marketers"
excerpt: "The Single Source of Truth (SSOT) report in Data Locker offers a unified and accurate overview of app campaign performances by merging data from various attribution methods."
x-zendesk:
  id: 26542697382417
  url: https://support.appsflyer.com/hc/en-us/articles/26542697382417-Single-Source-of-Truth-SSOT-Data-Locker-report-for-marketers
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Data Locker
  section_id: 6550945728657
  position: 5
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, SKAdNetwork (SKAN)]
  labels: [Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2024-07-08T14:14:21Z'
  edited_at: '2026-05-20T11:20:13Z'
---
**At a glance:** The Single Source of Truth (SSOT) report in Data Locker offers a unified and accurate overview of app campaign performances by merging data from various attribution methods, such as ID matching and SKAN.  It provides a way to consume data into internal BI systems, enhancing your analysis and reporting capabilities.

Note: The SSOT Data Locker report contains LTV-based data, not activity-based data. This means the data reflects users’ lifetime value across all touchpoints, rather than their in-app or event activity

## What is Data Locker

Data Locker is a secure solution that delivers your data directly to main cloud platforms, such as AWS, GCS, and Snowflake. This allows marketers to easily integrate and consume data into their internal BI systems for comprehensive analysis and reporting. [Learn more](/docs/data-locker-advertiser-reports?query=data%20locker).

## What is Single Source of Truth (SSOT)

The Single Source of Truth (SSOT) solution aims to solve data fragmentation issues by offering a unified and accurate overview of app campaign performances by merging data from various attribution methods, such as ID matching and SKAN. [Learn more](/docs/single-source-of-truth-ssot-guide-for-ios-attribution).

## Benefits of SSOT reports in Data Locker

The Single Source of Truth report:

* **Get an accurate, complete attribution view:** SSOT handles the logic of merging data from different attribution methods, effectively preventing double-counting installs that were attribution by multiple attribution methods. This ensures the data is accurate and reflective of true user behavior and attribution.
* **Load data into your BI systems:** SSOT provides an efficient and accurate way to build your internal BI systems using aggregated data. This includes attributions, in-app events, and revenue data, covering all dimensions and metrics. By loading this data into your BI systems, you can enhance your campaign performance and optimization processes while maintaining user privacy.
* **Best granularity**: SSOT offers the highest level of granularity possible, even when modeling data gaps inherent in SKAN. This detailed data helps in making precise and informed decisions.

## Setting up Data Locker

To enable Single Source of Truth or SSOT reports, complete one of the following procedures.

| Do you currently get data via Data Locker? | Procedure |
| --- | --- |
| Yes | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/06f3ff8ccacda390fa259853b93e8b0e4ad01a692272f945fd71ca913e445bbb-30159015098129.png)To add the reports to Data Locker:<br /><br />1. In AppsFlyer, from the side menu, select **Export > Data Locker**.<br />2. Select all the reports you want to get.<br />3. Click **Save configuration**.   <br />   The reports will be available the next day. |
| No | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/06f3ff8ccacda390fa259853b93e8b0e4ad01a692272f945fd71ca913e445bbb-30159015098129.png)**To set up Data Locker**:<br /><br />1. Complete the first-time Data Locker ([advertiser](/docs/data-locker-for-marketers#set-up-data-locker) \| [partner](/docs/data-locker-for-partners)) setup.<br />2. Add the reports to Data Locker:<br />   1. In AppsFlyer, from the side menu, select **Export > Data Locker**.<br />   2. Select all the reports you want to get.<br />   3. Click **Save configuration**.   <br />      The reports will be available the next day. |

### SSOT report facts

| Name | Description |
| --- | --- |
| Reports available | The following reports are available:<br /><br />* User acquisition: attributes conversions to user acquisition channels. This includes post-install activity occurring during re-engagement windows.<br />* Retargeting: attributes conversions to retargeting channels for events occurring:<br />  * As a result of re-attributions<br />  * During a re-engagement window<br />* Unified: attributes conversions to the last touch channel, according to the AppsFlyer [double attribution](/docs/resolve-retargeting-double-attribution) rules. This means that post-install activity occurring during re-engagements displays under the retargeting media source and not under the UA media source. |
| Reporting period | The report provides cohort revenue metrics up to 30 days post-install (D7, D14, D21, D30). Note: Only revenue metrics are supported beyond D7. |
| Directory structure | The directory structure is organized by install date. Each install date folder includes multiple versions created daily. Each version reflects the updated cumulative data for this install date. This means you should only process the latest available report version. [Learn more](/docs/single-source-of-truth-ssot-data-locker-report-for-marketers#directory-structure) |
| Report structure | The schema of the report (the dimensions and metrics included) is fixed and can't be modified. |
| Timezone | UTC |
| Data freshness | * Daily.<br />* Metrics are calculated using data available at midnight UTC, which is the end of the day.<br />* SLA: New reports are available in Data Locker by 16:00 UTC. A new version is created for the last 15 install dates each day. [See more](/docs/single-source-of-truth-ssot-data-locker-report-for-marketers#report-folder-hierarchy) |

## Directory structure

### Report folder hierarchy

* The primary folders are organized by the report type. Possible
  values:
  * ssot\_unified
  * ssot\_retargeting
  * ssot\_user\_acquisition
* Within these folders, sub-folders are organized by the install
  date.

**Versioning**

* Each install date folder contains multiple versions, created
  daily.
* Each version reflects the updated cumulative data for that
  install date.
* Reports will include all available data for the install date.
  For example, on April 18, the latest version for each install
  date contains all data up to that point for April 18.
* Tip: Always process the latest available report version to
  ensure accuracy.

Each install date is limited to up to 31 versions. After 31 days,
all metrics are fully fixed and completed.
[Learn more](/docs/single-source-of-truth-ssot-data-locker-report-for-marketers#partial-data).

### Directory and filename structure

The path to the report consists of the following format:

``/t=/install\_date=``/version=/``

Example folder hierarchy in advertiser bucket:

```
bucket
|
└── t=ssot_unified
    |
    ├── install_date=2024-05-05
    |   |
    |   └── version=1714890235
    |   |    |
    |   |    ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    |
    |   |    ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    │
    |   |    └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |
    |   |
    |   └── version=1714890286
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |   |
    .   . 
    .   .
```

Legend:

* t: Report topic (type).
* install\_date: The installation date of the app. It means
  that post-install activity will appear based on the install
  date when the user downloaded the app, not the day the user
  action occurred.
* version: Unix timestamp indicating when the version was created.

## Report structure

The report is comprised of dimensions and metrics.

The metrics covers data of attributions, revenue, and the unique users performing an event. To calculate cost-related metrics (e.g. ROI, and ROAS) you need both revenue and cost metrics. Revenue metrics are in SSOT report, and cost metrics are provided by ROI360 Cost ETL.

[Download sample report](https://docs.google.com/spreadsheets/d/1e32M7XW7Lr7s7LTZUKO4EGwm4VrbbfwT/pub?output=xlsx)

### Field formats

| Format name | Description |
| --- | --- |
| String [n] | The maximum length of the string. We don't usually enforce field length limitations on receipt of the data, but data may be truncated thereafter. |
| Time string | Strings have the format,<br /><br />```<br />yyyy-mm-dd hh:mm:ss.<br />```<br /><br />For example,<br /><br />```<br />2019-09-17 00:09:25<br />``` |
| Enum [n] | Enum fields can only contain specific values. For example, selected\_currency has 3 characters and can contain only currency codes as specified. |
| Timestamp | 10-digit UNIX timestamp. Example:  <br />August 4, 2020, 07:25 UTC translates to<br /><br />```<br /> "timestamp": "1596525944"<br />``` |
| Boolean | The value of the field can be either *TRUE* or *FALSE* |
| Integer | Integer |
| Float | Real floating number that can have a decimal point and values after the decimal point. |

### Dimensions

| Field name | Description | Format |
| --- | --- | --- |
| af\_ad\_id | Ad identifier. Campaign hierarchy. | string |
| af\_ad | Ad name. | string |
| af\_adset\_id | Ad-set identifier. Campaign hierarchy. | string |
| af\_adset | Ad-set name. | string |
| app\_id | App ID (advertiser app) with prefix ID. | string |
| attribution\_method | The mechanism used for attributing the event. Examples of such mechanisms include AppsFlyer methods, SKAdNetwork (SKAN), and organic. | string |
| attributed\_touch\_type | Possible values: click impression, null. | string |
| campaign | Campaign name reported by the ad network to AppsFlyer. | string |
| af\_c\_id | Campaign identifier. | string |
| days\_post\_attribution | The number of days elapsed since the conversion date (not the specific conversion timestamp). Tip! Use this to calculate retention and KPI days. | int |
| event\_name | Identifies the event. Some event names have a specific meaning while others relate to in-app events set by the advertiser in the app.   | event\_name | What did the user do | | --- | --- | | af\_conversion | User converted. Use conversion\_type to identify if it is an install, re-download, re-attribution. or re-engagement. | | Advertiser defined in-app event | Performed an in-app event in the app | | af\_ssot\_organic | Used to aggregate organic revenue from all events.  Note:af\_ssot\_organic is a system-generated event that aggregates all organic revenue data for apps using the SKAN Overall revenue measurement schema. This event appears when granular revenue by specific in-app events isn’t available due to SKAN limitations. It ensures that total organic revenue is still visible, even when attributed events can't be individually reported. | |
stringgeoThe ISO country code. Derived from the user IP address in AppsFlyer classic attribution methods, while in SKAN the data is either enriched from ad-networks or modeled.stringinstall_dateThe installation date of the app. <br/><br/>SKAN: Estimated by AppsFlyer based on the postback arrival time. <br/><br/>AppsFlyer attribution methods: <br/>• User acquisition: First launch after install <br/>• Retargeting: First launch after re-engagement or re-attribution <br/><br/>Note: install_date is available as a column only for data warehouse connections, such as BigQuery and Snowflake.stringis_primary_attributionUA: TrueRetargeting: During a re-engagement window, we attribute to both the original media source (before the re-engagement) and to the re-engagement media source. While the event is within the re-engagement window. The original media source will be FALSE (not primary attribution). The re-engagement media source will be TRUE.boolmedia_sourceAd network attributed to an event.stringselected_currency3-letter currency code (USD, EUR) set by you in the app settings. Format ISO-4217. This is the same currency used to display revenue in SSOT user interface.stringconversion_typePossible values:<br/>Install: User downloads and opens an app for the first time.<br/>Re-attribution: User reinstalls and is attributed to a new campaign.<br/>Re-download (SKAN): User installs the app again after uninstalling.<br/>Re-engagement: Re-engagement: User reopens the app after interacting with a retargeting ad.string

### Metrics

| chosen dl name | Description | Format |
| --- | --- | --- |
| revenue\_selected\_currency | The cumulative revenue amount in the selected currency. Maximum of two places after the decimal point.  <br />Example: For event\_name=purchase with days\_post\_attribution=2, the value reflects the total revenue from purchase events within two days post-install (not only on the second day). | double |
| revenue\_usd | The cumulative revenue amount in USD.  <br />Example: For event\_name=purchase with days\_post\_attribution=2, the value reflects the total revenue from purchase events within two days post-install (not only on the second day). | double |
| skan\_duplicates | Installs simultaneously attributed by SKAN and other AF methods are then removed to prevent double counting in SSOT data. | long |
| uninstalls\_count | Number of app users installing the app who subsequently uninstall (delete) the app (relevant for User Acquisition only) | long |
| unique\_users | The number of distinct users performing an event. Values are cumulative.  <br />Example: For event\_name=purchase with days\_post\_attribution=2, the value reflects unique users who made purchases within two days post-install (not only on the second day). | int |

### Modeled data

AppsFlyer models data that basic SKAdNetwork reporting cannot provide.

* Null Conversion Values (CV): In SKAN, Apple may replace actual data with a "Null" value to maintain user privacy. To ensure no data is omitted, these null values are modeled in SSOT. [Learn more](/docs/skan-modeled-data#null-conversion-values).
* Longer Post-Install Metrics: SKAN's data granularity for post-install periods beyond the first two days is limited, which may lead to inaccuracies. To maintain high data quality, we model revenue and unique in-app event users for days\_post\_attribution greater than 2. [Learn more](/docs/skan-modeled-data#revenue-ltv).

Geo Data: SKAN limits data granularity, often making geo data unavailable. In such cases, we model the data to enable efficient performance analysis. [Learn more](/docs/skan-modeled-data#geo).

**Organic geo in the first report version**

* SSOT Data Locker reports are generated in **versions** for the same `install_date`.
* In the **first version**, **organic geo may be** `null` because the modeled geo distribution may not be available yet.
* In **subsequent versions**, organic geo may populate after additional SKAN postbacks are processed and the modeled geo distribution becomes available.

### Partial data

When analyzing recent install days, metrics for extended post-install periods (e.g., 7 days) might not be fully matured. In such cases, the metrics will still be available but will reflect partial data.

Some rules of thumb:

* The report shows any available data as soon as it is available.
* After 5 days, metrics for two days post-install are completed*.
* After 7 days, metrics for seven days post-install are completed. Up to 15 days post-install, the model might refine this value.

Reasons for Partial Data:

* Data maturity: When the time since the install date is shorter than the days being analyzed, the data is still accumulating and not yet complete.
* SKAN delays: SKAN data is received with a random delay. For example, post-install activity for the first two days can be received up to 96 hours (4 days) after installation.
* Modeled data timing: SKAN data for periods greater than 2 days post-install is modeled. Our models generate the first estimated value after 7 days. During this period (days 2 to 7), data from AppsFlyer's classic attribution methods is available, while SKAN modeled data isn’t.

Examples (assuming an install date of January 1st):

* On January 2nd: SKAN data has yet to be received. Data for 2 days post-install will equal data under 7 days post-install, and both are partial, consisting of data from AppsFlyer's classic attribution methods.
* On January 3rd: SKAN data is partially received. Data for 2 days post-install will still be partial, now partially containing SKAN data. Data for 7 days post-install will not include any modeled SKAN data yet (the first modeled value is available after 7 days from installation). Therefore, between 2 to 7 days post-install, we might see a lower value for 7 days post-install relative to 2 days post-install.
* On January 6th: SKAN data for the first two days post-install was fully received, including postbacks with the maximum possible delay. Metrics for two days post-installs are completed. At this point, metrics for 7 days post-installs aren’t completed yet.
* On January 8th: SKAN modeled data for 7 days post-installs is completed. Our model will keep refining the value up to January 16th.

Note: The same logic applies to SKAN data for days 14, 21, and 30. This means that day[X] metrics (where [X] can be 7, 14, 21, or 30) becomes available only after [X] days have passed since the installation date.

## BI developer considerations

**Scope of data in the report:**

The reports contain data on user acquisition installs, retargeting re-attributions (re-downloads in SKAN), and re-engagements, along with their related in-app events.

### Loading reports

You can load unified, user acquisition, and retargeting reports separately or together into your BI system. If you load them together and want to filter views on your own:

* Unified reports: Use is\_primary\_attribution=true or null field.
* User acquisition reports: Use conversion\_type=Install.
* Retargeting reports: Use conversion\_type=re-engagement or re-attribution.
* Unified View: If you use the unified view in your data loading process, you can split the data between campaign types:

* Use conversion\_type=install, re-engagement, or re-attribution (re-downloads in SKAN).
* Refer to [Double attribution of retargeting events](/docs/resolve-retargeting-double-attribution) for more details

### Days post-attribution

> 📘 **Important!**
>
> The report includes a dimension, days\_post\_attribution, which associates revenue and unique user data with the specific number of days post-install

* For attributions (installs, re-engagements, etc.), the value is 0.
* For revenue and in-app events, the data is categorized into predefined cohorts, currently limited to “2” days and “7” days post-install.

**To accurately analyze in-app events and revenue, you should apply a filter for the days\_post\_attribution dimension.** See the example query below.

An example of a common mistake is to apply a simplified logic that sums the revenue column for a specific set of dimensions. This approach results in incorrect numbers because some revenue data is counted twice (once for days\_post\_install=2 and again for days\_post\_install=7). This example is also relevant when analyzing unique users for specific in-app events.

### Tips

* Latest Version: Always retrieve the highest version number available for each install date, as it represents the most recent data. The version number is in Unix timestamp format, so the highest value indicates the latest version. This ensures your analysis uses the most accurate and up-to-date information.
* Revenue calculation: Revenue in USD is calculated using the exchange rate on the event day.
* Analyze attributions: Records where event\_name=af\_conversion reflect attributions (installs, re-attributions (re-downloads in SKAN), and re-engagements). The count of attributions appears under the unique users metric, and the revenue metrics for these fields will be empty. The value under days\_post\_attribution will be 0.
* Dashboard comparison: When comparing Data Locker data with dashboard installs, sum both `install` and `re-download` conversion types. The dashboard includes both conversion types in the install metric. To get both conversion types from separate Data Locker reports, use the user acquisition report for `install` conversions and the retargeting report for SKAN `re-download` conversions.
* Analyze in-app events: Records where event\_name does not equal ‘af\_conversion’ reflect in-app events. The count of unique users performing the event appears under the unique users metric, while the revenue generated from these events appears under the revenue metrics.
* Conversion type: Differentiate user acquisition and retargeting conversions using this dimension. Note that an additional break for SKAN data is available (installs vs. re-downloads). When comparing data to the SSOT dashboard, both types are considered as installs.
* Ad Revenue Events: These are included where available.
* Data Segregation: All app data is provided in a single file. Use the App ID field to segregate data per app, or set Data Locker to segregate by app.
* Pre-attribution data such as cost, clicks, and impressions, should be taken from the cost ETL report.

### Example use cases

The following are examples of some popular, practical applications of the data that BI developers can extract via Data Locker. Each example is illustrated by an SQL statement and a sample Excel visual.

### Calculating total attributions per campaign

In this query, we:

* Sum the total unique attributions per campaign for each install date.
* Filter for conversions with the event name 'af\_conversion' and a specific campaign ID (af\_c\_id).

```
SELECT install_date, SUM(unique_users) AS total_attributions
FROM ssot_unified
WHERE event_name = 'af_conversion'
    AND af_c_id = '4475903638579'  -- Change to your specific campaign
    AND app_id = 'YOUR_APP'
GROUP BY install_date;
```

### Calculating conversions (installs & re-downloads) to compare with dashboard installs

In this query, we:

* Count conversions distinguishing between new installs and re-downloads per unique campaign and install date.
* Compare installs to the dashboard install metric, which merge conversion types 'install' and 're-download'.

```
SELECT install_date, conversion_type, SUM(unique_users) AS total_conversions
FROM ssot_unified
WHERE event_name = 'af_conversion'
    AND af_c_id = '4475903638579'  -- Change to your specific campaign
    AND conversion_type IN ('install', 're-download')  
-- The dashboard sums both under the install field
    AND app_id = 'YOUR_APP'
GROUP BY install_date, conversion_type;
```

Note: When comparing Data Locker data with dashboard installs, include both install and re-download conversion types. The dashboard install metric includes both new installs and SKAN re-downloads. In separate SSOT Data Locker reports, the user acquisition report includes conversion\_type=install, and SKAN re-downloads are available in the retargeting report. To compare separate reports with dashboard installs, fetch both the user acquisition and retargeting reports.

### Calculating retargeting conversions per geo

In this query, we:

* Count conversions from retargeting campaigns broken down by geographic location.
* By considering types 're-attribution' and 're-engagement' for these conversions.

```
SELECT install_date, conversion_type, geo, SUM(unique_users) AS total_conversions
FROM ssot_unified
WHERE event_name = 'af_conversion'
    AND conversion_type IN ('re-attribution', 're-engagement')  
-- Both types are relevant for re-targeting
    AND app_id = 'YOUR_APP'
GROUP BY install_date, conversion_type, geo;
```

### Calculating installs by attribution method per media source

In this query, we:

* Count installs by attribution methods (SKAN, AppsFlyer methods, and organic) and break it by media source.
* Filter based on 'af\_conversion' events with a conversion type of 'install'.

```
SELECT install_date, attribution_method, media_source, SUM(unique_users) 
AS total_installs
FROM ssot_unified
WHERE event_name = 'af_conversion'
    AND conversion_type = 'install'
    AND app_id = 'YOUR_APP'
GROUP BY install_date, attribution_method, media_source;
```

### Calculating cumulative revenue of 30 days post-install for Facebook per ad-set

In this query, we measure the accumulated revenue within a 30-day period post-install for ads served on Facebook.

```
SELECT install_date,
       af_adset,
       SUM(revenue_usd) AS total_revenue_day_30
FROM ssot_unified
WHERE media_source = 'facebook'
    AND days_post_attribution = 30  -- Choose a specific post-install period (cohort)
    AND app_id = 'YOUR_APP'
GROUP BY install_date, af_adset;
```

### Calculating cumulative revenue for selected post-install periods

In this query, we:

* Calculate cumulative revenue for multiple selected days after installation, breaking out sums for day 2 and day 7.
* Please note that when analyzing installs from the past 7 days, the data for 7 days post-install may be incomplete. [Learn more](/docs/single-source-of-truth-ssot-data-locker-report-for-marketers#partial-data)

```
SELECT install_date,
       SUM(IF(days_post_attribution = 2, revenue_usd, 0)) AS total_revenue_day2,
       SUM(IF(days_post_attribution = 7, revenue_usd, 0)) AS total_revenue_day7
FROM ssot_unified
WHERE app_id = 'YOUR_APP'
GROUP BY install_date;
```

### Calculating revenue from a specific in-app event (purchase) per media source

In this query, we:

* Measure revenue value from a specific in-app event (like 'af\_purchase') and sum that data by media source.
* Filter selected days post-install to make sure data isn’t double-counted.

```
SELECT install_date, media_source, SUM(revenue_usd) AS total_purchase_revenue
FROM ssot_unified
WHERE event_name = 'af_purchase'  -- Change to your specific event
    AND days_post_attribution = 7  -- Choose a specific post-install period (cohort)
    AND app_id = 'YOUR_APP'
GROUP BY install_date, media_source;
```

### Calculating in-app event conversion rate for 2 days post-installs

In this query, we calculate the conversion rate of a specific in-app event (such as 'af\_complete\_tutorial') in relation to all installations.

```
SELECT install_date,
  SUM(IF(days_post_attribution = 2 AND 
event_name = 'af_complete_tutorial', unique_users, 0)) 
  / SUM(IF(event_name = 'af_conversion', unique_users, 0)) 
AS conversion_rate_day2_af_tutorial_conversion
FROM ssot_unified
WHERE conversion_type = 'install'  
-- Choose the conversion types for the sample group you want to measure
    AND app_id = 'YOUR_APP'
GROUP BY install_date;
```

### Calculating ARPU for 7 days and 2 days post-install per campaign ID

In this query, we:

* Calculate the Average Revenue Per User (ARPU) for day 2 and day 7 post-install across campaigns.
* Please note that when analyzing installs from the past 7 days, the data for 7 days post-install may be incomplete. [Learn more](/docs/single-source-of-truth-ssot-data-locker-report-for-marketers#partial-data)

```
SELECT install_date,
       af_c_id,
       SUM(IF(days_post_attribution = 2, revenue_usd, 0)) 
       / SUM(IF(event_name = 'af_conversion', unique_users, 0)) AS ARPU_day2,
       SUM(IF(days_post_attribution = 7, revenue_usd, 0)) 
       / SUM(IF(event_name = 'af_conversion', unique_users, 0)) AS ARPU_day7
FROM ssot_unified
WHERE conversion_type = 'install'  
       -- Choose the conversion types for the sample group you want to measure
    AND app_id = 'YOUR_APP'
GROUP BY install_date, af_c_id;
```

### Calculating Amount of Duplicates per Media Source In this query

In this query, we count the total number of duplicated user attributions by media source and install date, to highlight media channels that may have higher duplication in user attribution.

```
SELECT install_date, media_source, SUM(skan_duplicates)
FROM ssot_unified
WHERE app_id = 'YOUR_APP'
    AND event_name = 'af_conversion'
GROUP BY install_date, media_source;
```

```
SELECT install_date, media_source, SUM(skan_duplicates)
FROM ssot_unified
WHERE app_id = 'YOUR_APP'
GROUP BY install_date, media_source;
```

### Non-organic D7 revenue

Returns the total Day 7 revenue for non-organic installs (`AF Model` + `SKAN`), grouped by install date.

```
SELECT install_date,
       SUM(revenue_usd) AS total_revenue_day_7
FROM ssot_unified
WHERE attribution_method IN ('AF Model','SKAN')
  AND days_post_attribution = 7 
  AND app_id = 'YOUR_APP'
GROUP BY install_date;
```

### Organic D7 revenue

Returns the total Day 7 revenue for organic installs, grouped by install date.  
You can use either query below—both return the same result.

**Option 1: Using** `attribution_method`

```
SELECT install_date,
       SUM(revenue_usd) AS total_revenue_day_7
FROM ssot_unified
WHERE attribution_method = 'Organic'
  AND days_post_attribution = 7 
  AND app_id = 'YOUR_APP'
GROUP BY install_date;
```

**Option 2: Using** `event_name`

```
SELECT install_date,
       SUM(revenue_usd) AS total_revenue_day_7
FROM ssot_unified
WHERE event_name = 'af_ssot_organic'
  AND days_post_attribution = 7 
  AND app_id = 'YOUR_APP'
GROUP BY install_date;
```

### Traits and limitations

| Name | Description |
| --- | --- |
| Cost data | * Cost data is not available. [Cost ETL](/docs/set-up-and-use-roi360-cost-etl-reports) can be used instead.<br />* To add the cost to the SSOT report, merge the Cost ETL data using the **Campaign ID** dimension. |
| Report availability per day | Only installation days where the SSOT toggle was turned on at the end of the day will have an SSOT report for that day |
| Two days post-install metrics | * For SKAN 4 in Conversion Studio: Data is for 2 days post-install.<br />* For SKAN 3 in Conversion Studio: Data is based on the defined SKAN activity window.  <br />  Example: If the activity window is 24 hours, events occurring within this window (even on Day X+1) are counted. |
| In-app events availability | Available only for events that occurred during the Window 1 period. |
| SKAN redownload breakdown | Available. In the SSOT dashboard, this breakdown is unavailable and both installs and redownloads are included in the installs metric. |
| SKAN Conversion Studio configuration changes | Changing the SKAN Conversion Studio configuration may cause inaccuracies in SSOT data for approximately 96 hours, as postbacks from installs encoded with the previous schema still arrive. |
| Timezone | App-specific timezone is not available. |
| Organic data | * Available for 30 days (D7-D30) post-install metrics. |
| Days post-conversion (install, re-attribution, re-engagement) data | Revenue metrics available for D7, D14, D21, D30. D14-D30 are delivered only via the SSOT Data Locker report. |
| Agency transparency | Supported. X Ads and Meta ads data is always transparent. |
| Campaign name changes | Not supported. Use campaign ID for grouping and filtering if campaign names were changed. |
| Ad networks | * Can access SSOT DataLocker reports to see data attributed to their media source if:<br />  * The advertiser has SSOT turned on in Conversion Studio.<br />  * The ad network is running SKAN campaigns.<br />  * The ad network has the required [permissions](/docs/set-up-an-integrated-partner#permissions-tab) from the advertiser to access aggregate data. |
| Agency access | Not available. Agency users can view SSOT data in the SSOT dashboard. |
| D7 metrics | * D7 metrics for organic traffic are available starting February 16, 2025.<br />* May be missing or less than D2 metrics if:<br />  * The date range includes dates for which 8 days haven't passed.<br />  * Modeled data isn't available (e.g., fewer than 14 days of revenue data). [Learn more](/docs/skan-modeled-data#revenue-ltv).<br />  * SKAN Conversion Studio configuration changed in the past 14 days.<br />  * There are fewer than 10 installs for a given date. |
| Predefined event name | Since the event name ‘af\_conversion’ is used to indicate different types of conversions, apps that have an event specifically named ‘af\_conversion’ will see their original event renamed to ‘af\_conversion\_event’. |
| Local currency difference | As the SSOT dashboard and SSOT DataLocker report are not calculated simultaneously, minor discrepancies may occur when comparing revenue in local currency on the dashboard to the selected currency in the report. This is due to the slightly different currency rates used at the times the data were calculated. |
| SKAN D7 partial data | As SKAN D7 data is modeled and the initial version is ready 7 days post-install, when analyzing D7 metrics for days within the last 7 days, the D7 data will be partial. For records where the attribution method is SKAN, the D7 metrics will be lower than the D2 metrics. |
| Limited granularity for D7 revenue and in-app event metrics | Revenue and unique user event metrics for 7 days post-install are not available at the ad-set, ad, and conversion type levels of granularity. Since this level of detail is typically unavailable in SKAN, the model does not account for these dimensions. |
| Ad revenue data freshness | Ad revenue data has a delay of one day.<br /><br />For example, a report created on the morning of July 3 will include ad revenue data up to and including July 1. |
| Event metrics | Only revenue metrics are supported beyond D7. |
| SSOT Dashboard | The dashboard only shows D2 and D7 revenue. Long-term revenue cohorts (Day 14/21/30 ) are currently available only in the SSOT Data Locker export. |