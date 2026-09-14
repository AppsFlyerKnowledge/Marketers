---
title: "Activity dashboard"
excerpt: "See app activity, engagement, and in-app metrics during a given period with real-time updates for current day metrics."
---
At a glance: See app activity, engagement, and in-app metrics during a given period. Current day metrics update in real-time.

![ActivityDB.png](https://files.readme.io/8150eafc018c83ae2b1030702129bda12419dfac60eb8664187c2acd66136df3-4420170646289.png)

## Activity dashboard

- Contains organic and non-organic traffic
- Date range relates to the event date and isn't [LTV-based.](https://support.appsflyer.com/hc/articles/115005600889-LTV-vs-Activity)
- Data freshness:
  - **Current day**: [Continuous](https://support.appsflyer.com/hc/articles/360000310629-Data-freshness-and-time-zone-support#continuous-aka-realtime). Example: DAU, sessions, revenue
  - **Average:** Daily. Example: MAU, Average DAU, Average MAU
- Geo filter relates to the user location at install time

> 👍 Tip
>
> Want to know more about the Activity dashboard? Check out this short, informative [course on the AppsFlyer Learning Portal](https://elevate.appsflyer.com/learn/course/7802/play/18621/the-activity-dashboard).

## Dashboard features and layout

### Metric definitions

| Metric | Description |
| --- | --- |
| DAU | - Daily active users: The number of unique users who opened the app at least once during the day.<br>- DAU is based on sessions.<br>- [Learn more about unique users](https://support.appsflyer.com/hc/articles/27435981457553) |
| Average DAU | Average number of daily active users, per day, during the selected period.<br><br>Example: Calculating average DAU<br><br>\| \| Sunday \| Monday \| Tuesday \|<br>\| --- \| --- \| --- \| --- \|<br>\| Daily active unique users \| 10 \| 12 \| 8 \|<br><br>**Average DAU** = (10+12+8)/3= 10. |
| MAU | Monthly active users:<br>- **Detailed:** Number of unique users (counted only once) who opened the app at least once during the previous 31 days.<br>- **High-level:** Number of unique users (counted only once) who opened the app at least once during the calendar month. |
| DAU/MAU rate | - This metric presents a view of the rate of returning users. A DAU/MAU rate of 50% means that the average user opened the app on 15 out of the previous 31 days.<br>- The DAU/MAU rate is a measure of user stickiness and provides a snapshot of user retention. |
| Revenue | Revenue generated for the selected period. Revenue consists of in-app purchases (if reported) and ad revenue. |
| ARPDAU | Average revenue per daily active user.<br><br>Formula: Sum of (Revenue on day [n] / DAU on day [n])]/Number of days.<br><br>Example: Calculation of ARPDAU<br><br>\| Day \| Revenue ($) on day \| DAU \| Average daily user revenue ($) \|<br>\| --- \| --- \| --- \| --- \|<br>\| Day 1 \| 10 \| 5 \| 2 \|<br>\| Day 2 \| 16 \| 4 \| 4 \|<br>\| Day 3 \| 30 \| 5 \| 6 \|<br>\| \| \| Total: \| 12 \|<br>\| \| \| Number of days \| 3 \|<br>\| \| \| **ARPDAU** \| 4 \| |
| Sessions | Sessions during the selected date range (if reported by the app) |
| Installs | Number of installs during the specified date range |
| Average eCPI | Average cost per install. Note: Installs are UA installs and cost is unified (UA and retargeting). |
| Conversion rate | Rate of installs from clicks. **Note**: Installs are UA installs and clicks are unified (UA and retargeting). |

### Detailed tab

The detailed analysis tab is divided into sections: headline metrics, activity trend, and activity summary.

|     |     |
| --- | --- |
| **Headline metrics** | |
|  | ![ActivityHeadLines_us-en__1_.png](https://files.readme.io/a4f1a5316eeacf0f635bbeadf52d490dd0276bb8a1fe9c0e32db7008d11d044b-360012584838.png) |
|  | **Average active users**<br>- Average DAU: the average number of daily active users in the specified time range.<br>- Average MAU: the average number of monthly active users in the specified time range. This is calculated as a moving average of the days in the selected range where each day looks back 31 days. Note: To see a given month's MAU value, like March, set the date range to the last day of that month (for example, March 31st) and look at the Average MAU value. |
|  | **Total installs:** Number of installs divided into organic and non-organic installs |
|  | **Total sessions**: Number of sessions divided into sessions by organic and non-organic users |
|  | **Total revenue**: Revenue, divided into revenue attributable to organic and non-organic users |
| **Activity trends** | |
|  | **Trend line with comparison**<br>![TrendLinWithComp_us-en.png](https://files.readme.io/b9edb3e409dc13bc72aebdccdc499fa2dcd9abf4549fb0170bf0cdc7036eee15-360012507997.png)<br>- Trend chart displays KPIs or in-app-event-related measurements.<br>- An optional comparison trend line can be added by enabling the **Compare with the previous** time frame (day, week, month, quarter, year).<br>- For example, if you select "month", it means that for a given day in the chart, the comparison is to the same day of the previous month.<br>KPIs available are:<br>- DAU<br>- MAU<br>- Revenue<br>- ARPDAU<br>- Sessions<br>- DAU/MAU rate<br>In-app event measures available are:<br>- Count<br>- Unique users<br>- Revenue |
| **Activity summary table** | |
|  | The Activity summary table:<br>- Displays up to 50 media sources with data relating to impressions, clicks, installs, etc. (To get all data, use [Master API](https://support.appsflyer.com/hc/articles/213223166-Master-API-Customizable-Aggregated-Data-API-) or [Pivot.)](https://support.appsflyer.com/hc/articles/115001421846-AppsFlyer-Pivot-)<br>- Is sorted by the number of sessions.<br>- Gives you the ability to drill down to the campaign level (it's not possible to drill down beyond this level.)<br>- Is a good way to see how many DAUs are new and how many are existing users (DAUs minus Installs).<br>To use the summary table:<br>- Refine the data displayed by using the Filter by and Group by fields.<br>- Table columns can be sorted by clicking on a column header.<br>- Filter by **In-app events** to limit the display to specific in-app events.<br>- Switch between different view types:<br>  - **Summary:** The total for all in-app events selected<br>  - **In-App events:** Broken down by in-app event |

### High-level tab: previous twelve-months

![ActivityHiLevel.png](https://files.readme.io/42636f5b13dca3a2209ea295c02e784175dfc92a2523c861220b87baed859541-4420194466065.png)

The tab contains a twelve-month historical overview of app activity performance and has the following charts:

- Active users and revenue
- Monthly gross profit: revenue, cost, gross profit

## Specifications and limitations

| Spec | Remarks |
| --- | --- |
| Data freshness | - **Metrics:** Real-time. See image that follows.<br>- **Average metrics**: Daily. See image that follows. **Note**: Average metrics aren't calculated in real-time to avoid distorting the average with data from incomplete days. If the date range includes the current day, then the following occurs:<br>  - If the date range is for the current day only: average results are not displayed.<br>  - If the date range is for a period that includes the current day: the average is calculated without including data from the current day.<br>- **Data processing for previous day:** Data processing initiates at midnight UTC for the preceding day's data. For applications operating in time zones behind UTC (UTC-), this means that their local day may still be in progress when processing begins, potentially leading to initially incomplete data. The remaining data is processed and incorporated the following day.<br>- **Ad revenue:** [Recorded with a lag](https://support.appsflyer.com/hc/articles/217490046-Ad-revenue-attribution-guide#data-freshness) and reported under the following date:<br>  - Aggregate-level data: under Day 1 (the day the data is pulled).<br>  - User-level data: under Day 0 (the day the ad displays).<br>![Whats_realtime.png](https://files.readme.io/39969fe7395e1b22910aed5d6ca61f6b5603171650f0d0ce88218a2491c02cc5-4407209143953.png) |
| Uninstalls | Not supported |
| Retargeting | As of February 1, 2025, all activity metrics are unified data (UA and retargeting together). However, prior to February 1, 2025, the following metrics include only UA traffic data:<br>- Total sessions<br>- DAU<br>- MAU<br>- DAU/MAU<br>- ARPDAU<br>- Cost<br>- Clicks<br>- Impressions<br>- Conversion rate<br>- eCPI<br>Unified is the only view available; users aren't able to switch to just UA or retargeting. |
| ARPDAU | There may be discrepancies between ARPDAU in the Activity dashboard and Pivots. |
| Historical data | - 3 years<br>- High-level tab: 1 year |
| Display range | - Maximum 2 months. If a longer period is specified, the range is reduced to two months and a message is displayed. |
| Group by geo | - Aggregation by geo is based on the geo where the install occurred.<br>- Displays up to 62 geos (ranked by top activity sessions). |
| Group by campaign | This grouping is only available after selecting specific media sources. |
| Dimension values | Values for dimensions such as media source, campaign name, and asset name are case-sensitive. For example, this means that "Facebook" and "facebook" will be treated as separate entities when filtering results. To view results without considering case sensitivity, utilize the [Pivot table](https://support.appsflyer.com/hc/articles/115001421846). |
| Agencies | Agencies don't have access to the Activity dashboard. [Learn more](https://support.appsflyer.com/hc/articles/115005972889) |
| Average DAU and Average MAU | Average DAU and Average MAU metrics may count the same user under multiple groupings. For example, if a user installs an app via Network A and later engages with it through Network B, they will appear under both networks when grouping by Media Source or Campaign. As a result, summing these values directly may lead to duplication. To obtain the accurate total Average DAU or Average MAU, refer to the KPI metric instead of aggregating the table values. |
| Ad networks | For certain ad networks, the Activity Table may display two rows instead of one. In such cases:<br>- Impressions, Clicks, Cost, and Conversions should be calculated as the sum of both rows.<br>- Activity Sessions, Activity Revenue, Average DAU, Average MAU, Average DAU/MAU Rate, and ARPDAU should be taken from only one of the rows. |
| Legacy unattributed organic in-apps mode | If your app uses the legacy **Unattributed organic in-apps** mode, real-time **organic Active Users** may appear lower than expected. Values correct automatically after the current day completes. For the most accurate real-time view, we recommend switching to **first-install mode**.<br>Learn more about [Unattributed organic in-apps mode](/docs/measure-reinstalls#unattributed-organic-inapps) and [first-install mode](/docs/measure-reinstalls#attributed-to-the-first-install). |