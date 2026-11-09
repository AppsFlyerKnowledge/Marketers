---
title: About data freshness and timezone support
metadata:
  keywords:
    - Reports
    - Advertisers
    - Agencies
    - Ad Networks
    - timezone
    - data freshness
    - data
    - Developers
    - Gray
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2018-02-19T15:57:01Z'
  edited_at: '2026-10-28T09:38:48Z'
  id: 360000310629
  locale: en-us
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360000310629-About-data-freshness-and-timezone-support
---
> **At a glance:** Data freshness is the period of time between event occurrence and data availability in the platform.

**Time zones**

<Image align="center" alt="TimeZoneMap.jpg" src="https://files.readme.io/eddfa3df4d43fed82ba5e867eb1278466d1ba51f9fbc2970f62fa61c6659d340-360005463738.jpg" />

## Data freshness and support for app-specific time zones

### Data freshness

The AppsFlyer platform utilizes different [types of data freshness,](/docs/about-data-freshness-and-timezone-support#data-freshness-types) such as daily and real-time. They are used to present and make data available. Each has its own [data freshness rate](/docs/about-data-freshness-and-timezone-support#data-freshness-rates-and-timezone-support).

Example: Data freshness rates on the Events dashboard:

* Metric KPI: real-time
* Average KPI: daily

### Time zones

In the AppsFlyer platform, a day starts at 00:01 and ends at 24:00. The default time zone is UTC (GMT). You can modify the default by setting an <Anchor target="_blank" href="/marketers/id/docs/changing-app-time-zone-settings">app-specific time zone.</Anchor>

<Accordion title="Date and time-zone principles">

UTC time is constant and doesn't have summer/winter times.

Hemispheres

* Eastern: Time zones designated as UTC+ are those located to the east of UTC.
* Western: Time zones designated as UTC - are those located to the west of UTC.

#### App-specific time zone

You can set an app-specific time zone. This means that the data is grouped into days using local time instead of UTC.

Example:

**Beijing:** If the app-specific time zone is set to Beijing (UTC +8), then the day starts at 16:01 UTC and ends at 16:00 UTC the following day.

**Los Angeles**: If the app-specific time zone is set to Los Angeles (UTC -8), then the day starts at 08:01 UTC and ends at 08:00 UTC the following day.

#### Time-zone guidelines

* Align your app-specific time zone with the time zone you set for other attribution service providers such as Google and Meta ads.
* If you have more than one app, the best practice is to set all apps to the same time zone. To view an app's time zone setting, go to **Settings** > **App Settings.**
* Most reports and data extraction tools support app-specific time zones. This includes multi-app reports if all apps are set to the same app-specific time zone.

#### Daily processing

Some reports and pull-down lists are processed once a day, this is referred to as daily freshness or daily processing. These are the principles of daily processing:

* Data belonging to a specific day, for example, Monday, is collected in a *bucket*. The day begins at 00:01 and ends at 24:00 using the app-specific time.
* Data received up to two hours after midnight is included in the day's bucket. Data received up to 02:00 on Tuesday is included in Monday's bucket.
* At 02:00 local time, the bucket is closed, and no more data can be added to it.
* Data received after 02:00 is placed in the next available bucket, irrespective of the event date.
* Daily processing of the closed bucket begins two hours after midnight UTC irrespective of the app-specific time zone. For the sake of simplicity, we state that processing starts at midnight UTC. This means that, depending on the local time zone, the bucket needs to wait until midnight UTC before processing begins.

**Eastern hemisphere and UTC time zone**:

![[NEEDS DESCRIPTIVE ALT TEXT — CONFIRM]: diagram of daily-processing wait times for Eastern hemisphere time zones](https://files.readme.io/cbea9d910695b39f59b342da6f56fa51df76afc910c4eea60f6dd49fbee2a0d6-8272818122769.png)

* Up to 11 hours can pass from the time the day ends (local time) until processing begins. For example:
  * Beijing (UTC+8): Need to wait eight hours before processing begins
  * Berlin (UTC +1): Need to wait one hour before processing begins
  * UTC: No waiting time.
* Depending on the report type, the data is available 8-20 hours after the start of the processing. For example, Beijing data is available from 16:00 local time. Berlin data is available from 09:00.

**Western hemisphere:**

![[NEEDS DESCRIPTIVE ALT TEXT — CONFIRM]: diagram of daily-processing wait times for Western hemisphere time zones](https://files.readme.io/ac5e3046b3f55916bb73732801c7e0bdef714cc45b89b6c4d70bbc2009cd64c8-8272698121489.png)

* Up to 23 hours can pass from the time the day ends until processing begins. For example:
  * Los Angeles (UTC -8): Need to wait 16 hours before processing begins
  * New York (UTC -5): Need to wait 19 hours before processing begins
* Depending on the report type the processed data is available 8-20 hours after the start of the processing begins. For example, Los Angeles data is available from 00:01 local time two days after the event. New York data is available from 03:01 local time two days after the event.
* Example:
  * Events take place on Monday Los Angeles time (UTC -8), the daily processing begins at midnight UTC Tuesday. This is Los Angeles Tuesday 16:01.
  * Eight hours later, on Wednesday 00:01 Los Angeles time, the data processing is complete. In practical terms, data from Monday is available to advertisers in Los Angeles when they begin work on Wednesday morning.

</Accordion>

<Accordion title="Data freshness types">

| Rate | Availability | Description |
| --- | --- | --- |
| Continuous (AKA real-time) | 15–60 minutes after event occurrence | Data processing is continuous. This term distinguishes it from batch processing which takes place, for example, daily. Continuous data is updated with a lag of 15–60 minutes after an event occurs as follows:<ul><li>Attributions (installs, re-attributions, and re-engagements): 15–30 minutes.</li><li>In-app events: 30–60 minutes.</li></ul> |
| Real-time report | Few minutes after requesting a report | Data is updated within minutes of the event occurring. |
| Daily | **UTC zone**: 8 hours after midnight UTC on the day of the event<br /><br />**Eastern hemisphere**: 9-20 hours after midnight UTC on the day of the event<br /><br />**Western hemisphere**: 21-32 hours after midnight UTC on the day of the event | <ul><li>Data is processed daily</li><li>The availability of this data differs depending on the app-specific time zone</li><li>Data types that don't support app-specific time zones use UTC time</li><li>Data availability times can vary from day-to-day or as indicated in specific articles</li></ul> |
| EOD | Daily at the end of the day app-specific timezone | At the end of the calendar day. Meaning 00:01 of the following day. Example: Data recorded on Monday is available starting from Tuesday at 00:01 irrespective of the app-specific timezone. |
| Intraday (during the day) | Every 4 hours on average | <ul><li>Data is collected six times a day, on average every four hours.</li><li>SRN click and impression data for customers without ROI360 is collected 3 times a day.</li><li>Cost ETL data is sent 4 times per day, on average every 6 hours.</li></ul> |
| Ad revenue | Depends on integration type and report | <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution#data-freshness">See ad revenue article for details</Anchor>. |
| PBA Daily | Data is available 11-12 hours after the end of the day UTC. | <ul><li>PBA dashboard and reports update [Daily](/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles) using the UTC timezone.</li><li>Daily processing includes events received during the previous day.</li><li>During the first seven days after conversion, PBA may identify additional events relating to a conversion. This can change KPIs and media source attribution retroactively.</li><li>After seven days, the paths are frozen, and no more changes take place.</li><li>Raw data reports include the field *final\_data.* When true data is final.</li><li><Anchor target="_blank" href="/marketers/id/docs/using-pba-dashboards#traits-and-limitations">Detailed example</Anchor></li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">See about timing</Anchor> from postback arrival time until data availability in dashboards and reports. | Postbacks received on a given day are processed at the end of the day UTC. Data is available by 10:00 UTC of the following day. Meaning iOS postbacks received Monday are available in reports and dashboards on Tuesday morning. Similarly, postbacks to partners are sent on Tuesday morning.<br /><br />The install date in reports and dashboards is derived from the postback arrival time as detailed in the <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio#activity-window">SKAN conversion studio article</Anchor>. |
| Data Locker Daily | Data is available 8–10 hours after the end of the day UTC | <ul><li>Data is processed daily.</li><li>Data is contained in the h=23 folder on the event date. For example, Monday's data is available in Monday's h=23 folder on Tuesday 08:00–10:00 UTC.</li><li>SKAN data may arrive a bit later (see SKAN info above).</li></ul> |

</Accordion>

<Accordion title="Data freshness rates and time-zone support">

<table><thead><tr><th>Related data</th><th>How presented</th><th>Data freshness rate<br/>(See the preceding section for the key to the rates)</th><th>Data displays using app-specific time zone</th></tr></thead><tbody><tr><td>Installs</td><td>KPI</td><td><p>Continuous</p><p>Exceptions to note:</p><ul><li>Protect360<ul><li>Updated daily at 16:00 UTC</li></ul></li></ul></td><td><span>✓</span></td></tr><tr><td>Sessions, clicks, impressions, loyal users</td><td>KPI</td><td><ul><li>Attribution links: Continuous</li><li>SRNs: Intraday</li></ul></td><td><span>✓</span></td></tr><tr><td>Revenue in-app events</td><td>KPI</td><td>Continuous</td><td><span>✓</span></td></tr><tr><td>Ad revenue</td><td>KPI</td><td>Ad revenue</td><td><span>✓</span></td></tr><tr><td>Ad spend (cost)</td><td>KPI</td><td><ul><li>Attribution link: Continuous (maximum up to 2 hours after click)</li><li>API: Intraday</li><li>Ad Spend Ingestion: Up to 4 hours after ingestion</li></ul></td><td><span>✓</span></td></tr><tr><td>Uninstalls</td><td>KPI</td><td>Daily. AppsFlyer pings app stores every 24 hours. The event time of the uninstall represents the time AppsFlyer pinged the silent push notification and discovered the app was uninstalled. This is not the actual time of the uninstall.</td><td><span><strong>x</strong></span></td></tr><tr><td>In-app events in the interface</td><td>Pull-down list</td><td><p>In-app event names that display in pull-down lists update Daily.</p><p>This does not impact the data freshness rate of the data itself.</p><p><strong>Examples:</strong> Pull-down in-app event lists in Push API, dashboards, and audiences.</p></td><td><span>✓</span></td></tr><tr><td>Overview dashboard</td><td>Page</td><td>Continuous</td><td><span>✓</span></td></tr><tr><td>Protect360 dashboard</td><td>Page</td><td>Daily</td><td> <span>✓ </span>(1)</td></tr><tr><td>SKAN dashboard</td><td>Page</td><td>Daily</td><td><span><strong>x</strong></span></td></tr><tr><td>Activity page</td><td>Page</td><td><ul><li>KPIs: Continuous</li><li>Averages: At midnight app-specific time zone</li></ul></td><td><p><span>✓</span></p><p>Exception: MAU data is UTC</p></td></tr><tr><td>Events page</td><td>Page</td><td>Continuous</td><td><span>✓</span></td></tr><tr><td> </td><td> </td><td>(This row has been left blank intentionally)</td><td> </td></tr><tr><td>Retention</td><td>Page</td><td><p>Retention KPIs are available having daily and weekly granularity. The data freshness for each is different.</p><ul><li>Daily retention KPIs: Daily</li><li>Weekly retention KPIs: The week begins on Monday and ends on Sunday. Retention is calculated on Monday 12:00 UTC. The lack of app-specific timezone support for the weekly KPI results in a negligible difference.</li></ul></td><td><p>Daily: <span>✓</span></p><p>Weekly: <span><strong>x</strong></span></p></td></tr><tr><td>Cohort</td><td>Page</td><td>Continuous</td><td> <span>✓ </span>(2)</td></tr><tr><td>Custom dashboard</td><td>Page</td><td>Continuous</td><td> <span>✓ </span>(3)</td></tr><tr><td>Audiences</td><td>Page</td><td><ul><li>Updates are pushed to partners every 24 hours.</li><li>User-base is updated daily and holds up to 90 days of device data</li></ul></td><td><span>✓</span></td></tr><tr><td>SDK information page</td><td>Page</td><td>Daily</td><td><span><strong>x</strong></span></td></tr><tr><td>Export data</td><td>Page</td><td><p>Continuous</p><p>Exceptions to note:</p><ul><li>Ad revenue raw data: Daily</li><li>Protect360:<ul><li>Aggregate reports: Daily</li><li>Blocked raw data: Continuous</li><li>Post-attribution raw data: Daily</li></ul></li><li>Organic in-app events: Update with a lag of several hours.</li></ul></td><td><span>✓</span></td></tr><tr><td>Pull API</td><td>API</td><td>Pull API data freshness is the same as the Export data.</td><td><p><span>✓</span></p><p><span>Default UTC</span></p></td></tr><tr><td>Pivot</td><td>Page</td><td>Daily</td><td><p><span>✓</span></p><p>Weekly retention KPIs: <strong>x</strong></p></td></tr><tr><td>Master API</td><td>API</td><td>Daily</td><td> <span>✓ </span>(3)</td></tr><tr><td>Data Locker</td><td>API</td><td>See the <a href="./data-locker-advertiser-reports#data-freshness-explanations" target="_blank">Data Locker article</a>.</td><td><p><span><strong>x</strong></span></p><p><span><strong>UTC</strong></span></p></td></tr><tr><td>Postbacks</td><td>API</td><td>Continuous</td><td>N/A</td></tr><tr><td>Push API</td><td>API</td><td>Continuous (4)</td><td><p><span>✓</span></p><p><span><strong>Both</strong></span></p></td></tr><tr><td>Server-to-server in-app events</td><td>API</td><td>Continuous</td><td>N/A</td></tr><tr><td colspan="4"><p>Notes:</p><p>(1) All apps the user has permission to must use the same app-specific time zone. If not, the time zone reverts to UTC.</p><p>(2) See <a href="./cohort-and-retention-dashboard#traits-and-limitations" target="_blank">Cohort traits and limitations</a> when the time zone will revert to UTC.</p><p>(3) All selected apps must use the same app-specific time zone. If not, the time zone reverts to UTC.</p><p>(4) SKAN report data will be available daily between 08:00 -10:00 UTC.</p></td></tr></tbody></table>

> 📘 **Exception: My Dashboards Cohort and Activity metrics**
>
> These metrics have their own data freshness:
>
> * **Cohort metrics (web, CTV, PC, and console apps):** Same-day data becomes available the following day, after daily processing completes.
> * **Activity metrics (Classic attribution):** Data freshness depends on the app type:
>   * **Web apps:** Up to 3.5 hours
>   * **CTV, PC, and console apps:** Up to 50 minutes
>   * **Mobile apps:** Up to 70 minutes
> * **Cross-platform attribution:** The update applies to Classic attribution only. Cross-platform data freshness in My Dashboards remains daily.
>
> See <Anchor target="_blank" href="/marketers/id/docs/my-dashboards#traits-and-limitations">My Dashboards traits and limitations</Anchor> for details.

</Accordion>

<div data-zendesk-anchors="data-freshness-and-support-for-appspecific-time-zones=data-freshness-and-support-for-app-specific-time-zones 01EDBBPAH96ADJ56FRNB34K3VB=data-freshness-and-support-for-app-specific-time-zones 01EDBBPAH9M5KQRXJ1TNN3RJAX=data-freshness 01EDBBPAH92JJVVGXN61N4SV89=time-zones appspecific-time-zone=app-specific-time-zone 01EDBBPAH9WHDY875Y913PV00Z=app-specific-time-zone timezone-guidelines=time-zone-guidelines 01EDBBPAH9TRH8HBB0JAX2369H=time-zone-guidelines 01EDBBPAH98F0641D934W9NJD8=daily-processing h_01M2MJESA4EG1BEVM5T6N9FH0D=exception-my-dashboards-cohort-and-activity-metrics" />
