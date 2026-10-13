---
title: "SKAN modeled data"
excerpt: "AppsFlyer models aggregate data that basic SKAdNetwork reporting is unable to provide, helping advertisers get a more complete picture of app and campaign LTV performance."
x-zendesk:
  id: 7086372479505
  url: https://support.appsflyer.com/hc/en-us/articles/7086372479505-SKAN-modeled-data
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: SKAN solution
  section_id: 6552135379985
  position: 3
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, SKAdNetwork (SKAN)]
  labels: [Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2022-06-23T12:02:02Z'
  edited_at: '2025-06-11T17:36:46Z'
---
AppsFlyer models aggregate data that basic SKAdNetwork reporting is unable to provide.

## Overview

SKAdNetwork (SKAN) reporting can be limited because:

- SKAN relies on conversion values (CVs) that are limited to 6 bits, resulting in 64 possible values (0-63).
- Apple sometimes withholds the actual CV (and returns data as "null") to preserve user privacy.
- Data is only available from within an activity window of between 12-72 hours and full lifetime value (LTV) isn't known.

SKAN modeled data solves these issues:

- AppsFlyer uses machine learning, Bayesian statistics, AppsFlyer-reported data, and SKAN data to model hidden data points.
- Advertisers get a more complete picture regarding app and campaign LTV performance

> 📘 Note
>
> When you change your conversion value schema, it takes 2 days for modeled data to become available.

## Modeled data types and availability

| Data type | Availability | Remarks |
| --- | --- | --- |
| Null conversion values | - Overview dashboard Single Source of Truth view<br />- SKAN dashboard<br />- SKAN aggregated performance report API<br />- SKAN aggregated postback arrival date API |  |
| Revenue LTV | Overview dashboard Single Source of Truth view | Up to 30 days in the SSOT Data Locker report (D7 still displayed in the dashboard) |
| In-app event LTV | Overview dashboard Single Source of Truth view | In-app LTV modeling is currently limited to 7 days |
| Geo | Overview dashboard Single Source of Truth view |  |

### Null conversion values

Sometimes the conversion value (CV) has a null value because Apple withholds the actual CV to preserve user privacy. In AppsFlyer, a null CV is counted as an install. Consider:

- Null and zero have different meanings:
  - Zero: The user installed the app but didn't perform any measurable action during the activity window. Consequently, the metric is accurate and isn't modeled.
  - Null: We don't know what the user did; Apple withheld the CV.
- Null CVs can distort your performance metrics. To overcome the distortion and provide a truer measure of app performance, null conversion values are modeled to conversion values between 0-63.  - Null modeling requires a minimum of two days of data out of the last 14 days.

Modeled conversion values:

- Use the distribution of SKAN installs with conversion values to model null installs. The algorithm used to model data is dynamic and takes into account several variables. See the following example of how it might work:  - There are 100 installs, 60 null, 10 with CV=1, 5 with CV=3, and 25 with CV=5.
  - This means that of the 40 installs with conversion values, 25% have CV=1, 12.5% have CV=3, and 62.5% have CV=5.
  - The 60 null installs get the same modeled distribution: 15 get CV=1, 7 get CV=3, and 38 get CV=5.
- Are included in the SKAN dashboard and API metrics. The original, unaltered metrics, that don't include modeled data, are available alongside these metrics and are marked as _unmodeled_.
- Use data from the following granularity levels: App, media source, campaign, and adset. If modeled data using those levels isn’t available, the value N/A displays.

Modeled metrics available based on the conversion value:

- Revenue
- Event occurrences
- eCPA
- ARPU
- ROI
- ROAS

### Revenue LTV

<Image src="https://files.readme.io/ec175800b52164844c56743a33fe412eef02c3b76975ca572819535bb5e5eff9-12183780248081.png" alt="modeled_d7.png" />

SKAN reporting on its own can only provide revenue based on the SKAN measurement window and CV configuration for revenue in Conversion Studio. SKAN modeling is able to model the revenue up to 30 days post-install.

**Benefits**:

For SKAN version 3 and earlier, the modeled data extends beyond the timeframe of the activity window.

For SKAN version 4+:

- Data freshness: Revenue LTV becomes available before the second SKAN postback arrives (the postback delay is between 24-144 hours).
- Measure more: You can use the coarse value configuration of the second and third postbacks for other metrics, like events and retention, and still get revenue LTV data by modeling.
- Data enrichment: If you use the second postback to measure revenue, data from the postback is used to improve the modeled revenue LTV data and provide revenue data at a more granular level than the 3 levels provided by the postback.

**Considerations**:

- Revenue LTV metrics display for apps with revenue configuration in SKAN Conversion Studio, for revenue that comes from in-app purchases and ad revenue.
- Revenue LTV requires at least 14 days of revenue data. Meaning, if you configure Overall revenue on November 1, 2022, the first install date for which modeled data is available is November 14, 2022. The data displays 8 days after that (November 22, 2022).
- Revenue LTV and other derived metrics are available in the SSOT dashboard (in the widgets, charts, and table) on the day after [X] (where [X] can be 7, 14, 21, or 30 days) post-install as follows:
  - Revenue D[X]
  - ARPU D[X]
  - Gross profit D[X]
  - ROI D[X]
  - ROAS D[X]

### In-app event LTV

The SKAN framework on its own provides limited insights into post-install in-app events. SKAN modeling extends in-app event analysis and provides in-app event metrics up to 7 days post-install.

**Benefits**:

For SKAN version 3 and earlier, the modeled data extends beyond the timeframe of the activity window.

For SKAN version 4+:

- Data freshness: In-app events LTV becomes available before the second SKAN postback arrives (the postback delay is between 24-144 hours).
- Measure more: You can use the coarse value configuration of the second and third postbacks to measure revenue, retention rates, etc., and still get in-app event LTV metrics by modeling.
- Data enrichment: If you use the second postback to measure in-app events, data from the postback is used to improve the accuracy of the modeled in-app event metrics, offering a more detailed measurement than what is provided by the SKAN coarse postback alone.

**Considerations**:

- Metrics are available from March 7, 2024.
- In-app events (as dimensions) and their metrics are available only for:
  - Events configured in SKAN Conversion Studio.
  - Events that occurred during the Window 1 SKAN period.
- In-app event D7 metrics require at least 14 days of in-app event data. For example, if you configure an in-app event in SKAN Conversion Studio on January 1, 2024, the first install date for which modeled data is available is January 14, 2024. The data displays 8 days after that (January 22, 2024).
- In-app event LTV metrics (currently limited to 7 days) and other derived metrics are available in the SSOT dashboard (in the widgets, charts, and table) on day 8 post-install as follows:
  - Event unique user D7
  - Event conversion D7
  - Event eCPA D7
  - Event revenue D7
- The Event unique user D2 count may be higher than the D7 count if not all dates within the selected range have reached Day 7, which restricts D7 metrics to AppsFlyer data. The “source” or "attribution method" hierarchy can be added to tables for visualization purposes.

### Geo

SKAN postbacks don't include a geo dimension. Therefore, SKAN data can't be grouped by geo using just SKAN postbacks. However, AppsFlyer is able to model SKAN install geos to provide the geo dimension and grouping for SKAN data.

When there is no AppsFlyer Classic attribution data available at the campaign level, geo-modeling does not estimate any geo distribution estimates on the SSOT view.

Modeled geos:

- Use machine learning tools that take into account the geo-distribution for campaign installs attributed via other AppsFlyer methods.
- Are available via the Geo dimension in the SSOT dashboard.

> 📘 Note
>
> If you group data by both Geo and Attributing method, you can see the data for each geo split between AF model and SKAN uniques. SKAN uniques are modeled.

Considerations:

- The accuracy of AppsFlyer geo-modeling is approximately 90%. If the geo can't be modeled, the SKAN install is grouped under None. None means the geo is unknown.