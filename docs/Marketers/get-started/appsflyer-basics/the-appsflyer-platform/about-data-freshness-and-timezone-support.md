---
title: "About data freshness and timezone support"
excerpt: "Learn how AppsFlyer handles data freshness rates and app-specific time zones across different dashboards, reports, and APIs."
---
Data freshness is the period of time between event occurrence and data availability in the platform.

**Time zones**

![TimeZoneMap.jpg](https://files.readme.io/eddfa3df4d43fed82ba5e867eb1278466d1ba51f9fbc2970f62fa61c6659d340-360005463738.jpg)

## Data freshness and support for app-specific time zones

### Data freshness

The AppsFlyer platform utilizes different [types of data freshness,](https://support.appsflyer.com/hc/articles/360000310629#data-freshness-types) such as daily and real-time. They are used to present and make data available. Each has its own [data freshness rate](https://support.appsflyer.com/hc/articles/360000310629#data-freshness-rates-and-timezone-support).

Example: Data freshness rates on the Events dashboard:

- Metric KPI: real-time
- Average KPI: daily

### Time zones

In the AppsFlyer platform, a day starts at 00:01 and ends at 24:00. The default time zone is UTC (GMT). You can modify the default by setting an [app-specific time zone.](https://support.appsflyer.com/hc/articles/115000306786-Changing-Time-Zone-for-Existing-Apps)

### Date and time-zone principles

UTC time is constant and doesn't have summer/winter times.

Hemispheres

- Eastern: Time zones designated as UTC **+** are those located to the east of UTC.
- Western: Time zones designated as UTC - are those located to the west of UTC.

#### App-specific time zone

You can set an app-specific time zone. This means that the data is grouped into days using local time instead of UTC.

Example:

**Beijing:** If the app-specific time zone is set to Beijing (UTC +8), then the day starts at 16:01 UTC and ends at 16:00 UTC the following day.

**Los Angeles**: If the app-specific time zone is set to Los Angeles (UTC -8), then the day starts at 08:01 UTC and ends at 08:00 UTC the following day.

#### Time-zone guidelines

- Align your app-specific time zone with the time zone you set for other attribution service providers such as Google and Meta ads.
- If you have more than one app, the best practice is to set all apps to the same time zone. To view an app's time zone setting, go to **Settings** > **App Settings.**
- Most reports and data extraction tools support app-specific time zones. This includes multi-app reports if all apps are set to the same app-specific time zone.

#### Daily processing

Some reports and pull-down lists are processed once a day, this is referred to as daily freshness or daily processing. These are the principles of daily processing:

- Data belonging to a specific day, for example, Monday, is collected in a _bucket_. The day begins at 00:01 and ends at 24:00 using the app-specific time.
- Data received up to two hours after midnight is included in the day's bucket. Data received up to 02:00 on Tuesday is included in Monday's bucket.
- At 02:00 local time, the bucket is closed, and no more data can be added to it.
- Data received after 02:00 is placed in the next available bucket, irrespective of the event date.
- Daily processing of the closed bucket begins two hours after midnight UTC irrespective of the app-specific time zone. For the sake of simplicity, we state that processing starts at midnight UTC. This means that, depending on the local time zone, the bucket needs to wait until midnight UTC before processing begins.

**Eastern hemisphere and UTC time zone**:

![mceclip9b.png](https://files.readme.io/c4ecf07082aba2751e06b1d3b2ade7ac45b5e9140e11e7b43f3fe74e0bc9ba59-8272818122769.png)

- Up to 11 hours can pass from the time the day ends (local time) until processing begins. For example:
  - Beijing (UTC+8): Need to wait eight hours before processing begins
  - Berlin (UTC +1): Need to wait one hour before processing begins
  - UTC: No waiting time.
- Depending on the report type, the data is available 8-20 hours after the start of the processing. For example, Beijing data is available from 16:00 local time. Berlin data is available from 09:00.

**Western hemisphere:**

![mceclip7a.png](https://files.readme.io/6d668febe61a407d20488ea6efeae4baf320c3925d162ac76497932dde7d9c4d-8272698121489.png)

- Up to 23 hours can pass from the time the day ends until processing begins. For example:
  - Los Angeles (UTC -8): Need to wait 16 hours before processing begins
  - New York (UTC -5): Need to wait 19 hours before processing begins
- Depending on the report type the processed data is available 8-20 hours after the start of the processing begins. For example, Los Angeles data is available from 00:01 local time two days after the event. New York data is available from 03:01 local time two days after the event.
- Example:
  - Events take place on Monday Los Angeles time (UTC -8), the daily processing begins at midnight UTC Tuesday. This is Los Angeles Tuesday 16:01.
  - Eight hours later, on Wednesday 00:01 Los Angeles time, the data processing is complete. In practical terms, data from Monday is available to advertisers in Los Angeles when they begin work on Wednesday morning.

### Data freshness types

| Rate | Availability | Description |
| --- | --- | --- |
| Continuous (AKA real-time) | 15–60 minutes after event occurrence | Data processing is continuous. This term distinguishes it from batch processing which takes place, for example, daily. Continuous data is updated with a lag of 15–60 minutes after an event occurs as follows: <br/>- Attributions (installs, re-attributions, and re-engagements): 15–30 minutes.<br/>- In-app events: 30–60 minutes. |
| Real-time report | Few minutes after requesting a report | Data is updated within minutes of the event occurring. |
| Daily | **UTC zone**: 8 hours after midnight UTC on the day of the event<br/>**Eastern hemisphere**: 9-20 hours after midnight UTC on the day of the event<br/>**Western hemisphere**: 21-32 hours after midnight UTC on the day of the event | - Data is processed daily<br/>- The availability of this data differs depending on the app-specific time zone<br/>- Data types that don't support app-specific time zones use UTC time<br/>- Data availability times can vary from day-to-day or as indicated in specific articles |
| EOD | Daily at the end of the day app-specific timezone | At the end of the calendar day. Meaning 00:01 of the following day. Example: Data recorded on Monday is available starting from Tuesday at 00:01 irrespective of the app-specific timezone. |
| Intraday (during the day) | Every 4 hours on average | - Data is collected six times a day, on average every four hours.<br/>- SRN click and impression data for customers without ROI360 is collected 3 times a day.<br/>- Cost ETL data is sent 4 times per day, on average every 6 hours. |
| Ad revenue | Depends on integration type and report | [See ad revenue article for details](https://support.appsflyer.com/hc/articles/217490046#data-freshness). |
| PBA Daily | Data is available 11-12 hours after the end of the day UTC. | - PBA dashboard and reports update [Daily](https://support.appsflyer.com/hc/articles/360000310629-Data-freshness-and-time-zone-support#date-and-timezone-principles) using the UTC timezone.<br/>- Daily processing includes events received during the previous day. <br/>- During the first seven days after conversion, PBA may identify additional events relating to a conversion. This can change KPIs and media source attribution retroactively. <br/>- After seven days, the paths are frozen, and no more changes take place.<br/>- Raw data reports include the field _final\_data._ When true data is final.<br/>- [Detailed example](https://support.appsflyer.com/hc/articles/360007630318#traits-and-limitations) |
| SKAN | [See about timing](https://support.appsflyer.com/hc/articles/36011420698#timing-from-app-install-until-dashboard-and-reports-update) from postback arrival time until data availability in dashboards and reports. | Postbacks received on a given day are processed at the end of the day UTC. Data is available by 10:00 UTC of the following day. Meaning iOS postbacks received Monday are available in reports and dashboards on Tuesday morning. Similarly, postbacks to partners are sent on Tuesday morning. <br/>The install date in reports and dashboards is derived from the postback arrival time as detailed in the [SKAN conversion studio article](https://support.appsflyer.com/hc/articles/4403727223185-SKAN-Conversion-Studio-SKAdNetwork-settings-#activity-window). |
| Data Locker Daily | Data is available 8–10 hours after the end of the day UTC | - Data is processed daily.<br/>- Data is contained in the h=23 folder on the event date. For example, Monday's data is available in Monday's h=23 folder on Tuesday 08:00–10:00 UTC.<br/>- SKAN data may arrive a bit later (see SKAN info above). |

### Data freshness rates and time-zone support

| Related data | How presented | Data freshness rate<br/>(See the preceding section for the key to the rates) | Data displays using app-specific time zone |
| --- | --- | --- | --- |
| Installs | KPI | Continuous<br/>Exceptions to note:<br/>- Protect360<br/>  - Updated daily at 16:00 UTC | **✓** |
| Sessions, clicks, impressions, loyal users | KPI | - Attribution links: Continuous<br/>- SRNs: Intraday | **✓** |
| Revenue in-app events | KPI | Continuous | **✓** |
| Ad revenue | KPI | Ad revenue | **✓** |
| Ad spend (cost) | KPI | - Attribution link: Continuous (maximum up to 2 hours after click)<br/>- API: Intraday<br/>- Ad Spend Ingestion: Up to 4 hours after ingestion | **✓** |
| Uninstalls | KPI | Daily. AppsFlyer pings app stores every 24 hours. The event time of the uninstall represents the time AppsFlyer pinged the silent push notification and discovered the app was uninstalled. This is not the actual time of the uninstall. | **x** |
| In-app events in the interface | Pull-down list | In-app event names that display in pull-down lists update Daily. <br/>This does not impact the data freshness rate of the data itself. <br/>**Examples:** Pull-down in-app event lists in Push API, dashboards, and audiences. | **✓** |
| Overview dashboard | Page | Continuous | **✓** |
| Protect360 dashboard | Page | Daily | **✓**(1) |
| SKAN dashboard | Page | Daily | **x** |
| Activity page | Page | - KPIs: Continuous<br/>- Averages: At midnight app-specific time zone | **✓**<br/>Exception: MAU data is UTC |
| Events page | Page | Continuous | **✓** |
| (blank row) |  | (This row has been left blank intentionally) |  |
| Retention | Page | Retention KPIs are available having daily and weekly granularity. The data freshness for each is different. <br/>- Daily retention KPIs: Daily<br/>- Weekly retention KPIs: The week begins on Monday and ends on Sunday. Retention is calculated on Monday 12:00 UTC. The lack of app-specific timezone support for the weekly KPI results in a negligible difference. | Daily: **✓**<br/>Weekly: **x** |
| Cohort | Page | Continuous | **✓**(2) |
| Custom dashboard | Page | Continuous | **✓**(3) |
| Audiences | Page | - Updates are pushed to partners every 24 hours.<br/>- User-base is updated daily and holds up to 90 days of device data | **✓** |
| SDK information page | Page | Daily | **x** |
| Export data | Page | Continuous<br/>Exceptions to note:<br/>- Ad revenue raw data: Daily <br/>- Protect360:<br/>  - Aggregate reports: Daily<br/>  - Blocked raw data: Continuous<br/>  - Post-attribution raw data: Daily<br/>- Organic in-app events: Update with a lag of several hours. | **✓** |
| Pull API | API | Pull API data freshness is the same as the Export data. | **✓**<br/>Default UTC |
| Pivot | Page | Daily | **✓**<br/>Weekly retention KPIs: **x** |
| Master API | API | Daily | **✓**(3) |
| Data Locker | API | See the [Data Locker article](/docs/data-locker-advertiser-reports#data-freshness-explanations). | **x**<br/>**UTC** |
| Postbacks | API | Continuous | N/A |
| Push API | API | Continuous (4) | **✓**<br/>**Both** |
| Server-to-server in-app events | API | Continuous | N/A |
| Notes:<br/>(1) All apps the user has permission to must use the same app-specific time zone. If not, the time zone reverts to UTC.<br/>(2) See [Cohort traits and limitations](https://support.appsflyer.com/hc/articles/207040496-Cohort-dashboard#traits-and-limitations) when the time zone will revert to UTC.<br/>(3) All selected apps must use the same app-specific time zone. If not, the time zone reverts to UTC.<br/>(4) SKAN report data will be available daily between 08:00 -10:00 UTC. | | | |