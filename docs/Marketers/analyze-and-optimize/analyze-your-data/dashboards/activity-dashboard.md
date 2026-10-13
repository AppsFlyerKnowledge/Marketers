---
title: "Activity dashboard"
excerpt: "See app activity, engagement, and in-app metrics during a given period with real-time updates for current day metrics."
x-zendesk:
  id: 207602503
  url: https://support.appsflyer.com/hc/en-us/articles/207602503-Activity-dashboard
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Dashboards
  section_id: 6550925337873
  position: 9
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-nohar-avigal, Marketers, Marketing Analytics]
  labels: [activity report, Advertisers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2016-01-12T15:50:15Z'
  edited_at: '2025-11-24T09:07:15Z'
---
**At a glance:** See app activity, engagement, and in-app metrics during a given period. Current day metrics update in real-time.

![ActivityDB.png](https://files.readme.io/8150eafc018c83ae2b1030702129bda12419dfac60eb8664187c2acd66136df3-4420170646289.png)

## Activity dashboard

* Contains organic and non-organic traffic
* Date range relates to the event date and isn't [LTV-based.](/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports)
* Data freshness:
  * **Current day**: [Continuous](/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime). Example: DAU, sessions, revenue
  * **Average:** Daily. Example: MAU, Average DAU, Average MAU
* Geo filter relates to the user location at install time

> 📘 **Tip**
>
> Want to know more about the Activity dashboard? Check out this short, informative[course on the AppsFlyer Learning Portal](https://elevate.appsflyer.com/learn/course/7802/play/18621/the-activity-dashboard).


## Dashboard features and layout

### Metric definitions



<table><thead><tr><th>Metric</th><th>Description</th></tr></thead><tbody><tr><td>DAU</td><td><ul><li>Daily active users: The number of unique users who opened the app at least once during the day.</li><li>DAU is based on sessions.</li><li><a href="./unique-users">Learn more about unique users</a></li></ul></td></tr><tr><td>Average DAU</td><td><p>Average number of daily active users, per day, during the selected period.</p><p>Example: Calculating average DAU</p>CALLSTART::Note::<figure><table><thead><tr><th> </th><th>Sunday </th><th>Monday</th><th>Tuesday</th></tr></thead><tbody><tr><td>Daily active unique users</td><td>10</td><td>12</td><td>8</td></tr></tbody></table></figure><p><strong>Average DAU </strong>= (10+12+8)/3= 10. </p>CALLEND::</td></tr><tr><td>MAU</td><td><p>Monthly active users: </p><ul><li><strong>Detailed: </strong>Number of unique users (counted only once) who opened the app at least once during the previous 31 days.</li><li><strong>High-level: </strong>Number of unique users (counted only once) who opened the app at least once during the calendar month.</li></ul></td></tr><tr><td>DAU/MAU rate</td><td><ul><li>This metric presents a view of the rate of returning users. A DAU/MAU rate of 50% means that the average user opened the app on 15 out of the previous 31 days.</li><li>The DAU/MAU rate is a measure of user stickiness and provides a snapshot of user retention. </li></ul></td></tr><tr><td>Revenue</td><td>Revenue generated for the selected period. Revenue consists of in-app purchases (if reported) and ad revenue. </td></tr><tr><td>ARPDAU</td><td><p>Average revenue per daily active user.<br/>Formula: Sum of (Revenue on day [n] / DAU on day [n])]/Number of days.</p>CALLSTART::Note::<h4> Example: Calculation of ARPDAU</h4><figure><table><thead><tr><th>Day</th><th>Revenue ($) on day </th><th>DAU</th><th>Average daily user revenue ($)</th></tr></thead><tbody><tr><td>Day 1</td><td>10</td><td>5</td><td>2</td></tr><tr><td>Day 2</td><td>16</td><td>4</td><td>4</td></tr><tr><td>Day 3</td><td>30</td><td>5</td><td>6</td></tr><tr><td> </td><td> </td><td>Total:</td><td>12</td></tr><tr><td> </td><td> </td><td>Number of days</td><td>3</td></tr><tr><td> </td><td> </td><td><strong>ARPDAU</strong></td><td>4</td></tr></tbody></table></figure>CALLEND::</td></tr><tr><td>Sessions</td><td>Sessions during the selected date range (if reported by the app)</td></tr><tr><td>Installs</td><td>Number of installs during the specified date range</td></tr><tr><td>Average eCPI</td><td>Average cost per install. Note: Installs are UA installs and cost is unified (UA and retargeting).</td></tr><tr><td>Conversion rate</td><td>Rate of installs from clicks. <strong>Note</strong>: Installs are UA installs and clicks are unified (UA and retargeting).</td></tr></tbody></table>



### Detailed tab

The detailed analysis tab is divided into sections: headline metrics, activity trend, and activity summary.



<table><tbody><tr><td colspan="2"><h4><strong>Headline metrics</strong></h4></td></tr><tr><td> </td><td><img alt="ActivityHeadLines_us-en__1_.png" src="https://files.readme.io/a4f1a5316eeacf0f635bbeadf52d490dd0276bb8a1fe9c0e32db7008d11d044b-360012584838.png"/></td></tr><tr><td> </td><td><p><strong>Average active users</strong></p><ul><li>Average DAU: the average number of daily active users in the specified time range.</li><li>Average MAU: the average number of monthly active users in the specified time range. This is calculated as a moving average of the days in the selected range where each day looks back 31 days. Note: To see a given month's MAU value, like March, set the date range to the last day of that month (for example, March 31st) and look at the Average MAU value.</li></ul></td></tr><tr><td> </td><td><strong>Total installs:</strong> Number of installs divided into organic and non-organic installs</td></tr><tr><td> </td><td><strong>Total sessions</strong>: Number of sessions divided into sessions by organic and non-organic users</td></tr><tr><td> </td><td><strong>Total revenue</strong>: Revenue, divided into revenue attributable to organic and non-organic users</td></tr><tr><td colspan="2"><h4><br/><strong>Activity trends</strong><br/> </h4></td></tr><tr><td> </td><td><p><strong> Trend line with comparison</strong></p><p><img alt="TrendLinWithComp_us-en.png" src="https://files.readme.io/b9edb3e409dc13bc72aebdccdc499fa2dcd9abf4549fb0170bf0cdc7036eee15-360012507997.png"/></p><ul><li>Trend chart displays KPIs or in-app-event-related measurements.</li><li>An optional comparison trend line can be added by enabling the <strong>Compare with the previous </strong>time frame (day, week, month, quarter, year).</li><li>For example, if you select "month", it means that for a given day in the chart, the comparison is to the same day of the previous month. </li></ul><p>KPIs available are:</p><ul><li><span>DAU</span></li><li><span>MAU</span></li><li><span>Revenue</span></li><li><span>ARPDAU</span></li><li><span>Sessions</span></li><li><span>DAU/MAU rate</span></li></ul><p><span>In-app event measures available are: </span></p><ul><li><span>Count</span></li><li><span>Unique users</span></li><li><span>Revenue</span></li></ul></td></tr><tr><td colspan="2"><h4><br/><strong>Activity summary table</strong></h4></td></tr><tr><td> </td><td><p>The Activity summary table:</p><ul><li>Displays up to 50 media sources with data relating to impressions, clicks, installs, etc. (To get all data, use <a href="./master-api-user-acquisition-metrics-via-api">Master API</a> or <a href="./pivot-table-user-metrics">Pivot.)</a></li><li>Is sorted by the number of sessions.</li><li>Gives you the ability to drill down to the campaign level (it's not possible to drill down beyond this level.)</li><li>Is a good way to see how many DAUs are new and how many are existing users (DAUs minus Installs).</li></ul><p><span>To use the summary table:</span></p><ul><li><span>Refine the data displayed by using the Filter by and Group by fields.</span></li><li><span>Table columns can be sorted by clicking on a column header.</span></li><li>Filter by <strong>In-app events</strong> to limit the display to specific in-app events.</li><li>Switch between different view types:<ul><li><strong>Summary: </strong>The total for all in-app events selected</li><li><strong>In</strong>-<strong>App events: </strong>Broken down by in-app event</li></ul></li></ul></td></tr></tbody></table>



### High-level tab: previous twelve-months

![ActivityHiLevel.png](https://files.readme.io/42636f5b13dca3a2209ea295c02e784175dfc92a2523c861220b87baed859541-4420194466065.png)

The tab contains a twelve-month historical overview of app activity performance and has the following charts: 

* Active users and revenue
* Monthly gross profit: revenue, cost, gross profit

## Specifications and limitations



| Spec | Remarks |
| --- | --- |
| Data freshness | * **Metrics:** Real-time. See image that follows.<br />* **Average metrics**: Daily. See image that follows. **Note**: Average metrics aren't calculated in real-time to avoid distorting the average with data from incomplete days. If the date range includes the current day, then the following occurs:<br />  * If the date range is for the current day only: average results are not displayed.<br />  * If the date range is for a period that includes the current day: the average is calculated without including data from the current day.<br />* **Data processing for previous day:** Data processing initiates at midnight UTC for the preceding day's data. For applications operating in time zones behind UTC (UTC-), this means that their local day may still be in progress when processing begins, potentially leading to initially incomplete data. The remaining data is processed and incorporated the following day.<br />* **Ad revenue:** [Recorded with a lag](/docs/roi360-guide-ad-revenue-attribution#data-freshness) and reported under the following date:<br />  * Aggregate-level data: under Day 1 (the day the data is pulled).<br />  * User-level data: under Day 0 (the day the ad displays).<br /><br />[![Whats_realtime.png](https://files.readme.io/39969fe7395e1b22910aed5d6ca61f6b5603171650f0d0ce88218a2491c02cc5-4407209143953.png)](https://files.readme.io/39969fe7395e1b22910aed5d6ca61f6b5603171650f0d0ce88218a2491c02cc5-4407209143953.png) |
| Uninstalls | Not supported |
| Retargeting | As of February 1, 2025, all activity metrics are unified data (UA and retargeting together). However, prior to February 1, 2025, the following metrics include only UA traffic data:<br /><br />* Total sessions<br />* DAU<br />* MAU<br />* DAU/MAU<br />* ARPDAU<br />* Cost<br />* Clicks<br />* Impressions<br />* Conversion rate<br />* eCPI<br /><br />Unified is the only view available; users aren't able to switch to just UA or retargeting. |
| ARPDAU | There may be discrepancies between ARPDAU in the Activity dashboard and Pivots. |
| Historical data | * 3 years<br />* High-level tab: 1 year |
| Display range | * Maximum 2 months. If a longer period is specified, the range is reduced to two months and a message is displayed. |
| Group by geo | * Aggregation by geo is based on the geo where the install occurred.<br />* Displays up to 62 geos (ranked by top activity sessions). |
| Group by campaign | This grouping is only available after selecting specific media sources. |
| Dimension values | Values for dimensions such as media source, campaign name, and asset name are case-sensitive. For example, this means that "Facebook" and "facebook" will be treated as separate entities when filtering results. To view results without considering case sensitivity, utilize the [Pivot table](/docs/pivot-table-user-metrics). |
| Agencies | Agencies don't have access to the Activity dashboard. [Learn more](/docs/manage-data-access-permissions) |
| Average DAU and Average MAU | Average DAU and Average MAU metrics may count the same user under multiple groupings. For example, if a user installs an app via Network A and later engages with it through Network B, they will appear under both networks when grouping by Media Source or Campaign. As a result, summing these values directly may lead to duplication. To obtain the accurate total Average DAU or Average MAU, refer to the KPI metric instead of aggregating the table values. |
| Ad networks | For certain ad networks, the Activity Table may display two rows instead of one. In such cases:<br /><br />* Impressions, Clicks, Cost, and Conversions should be calculated as the sum of both rows.<br />* Activity Sessions, Activity Revenue, Average DAU, Average MAU, Average DAU/MAU Rate, and ARPDAU should be taken from only one of the rows. |
| Legacy unattributed organic in-apps mode | If your app uses the legacy **Unattributed organic in-apps** mode, real-time **organic Active Users** may appear lower than expected. Values correct automatically after the current day completes. For the most accurate real-time view, we recommend switching to **first-install mode**.  <br />Learn more about [Unattributed organic in-apps mode](/docs/measure-reinstalls#unattributed-organic-inapps) and [first-install mode](/docs/measure-reinstalls#attributed-to-the-first-install). |