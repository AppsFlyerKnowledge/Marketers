---
title: "Cohort and retention dashboard"
excerpt: "The Cohort and retention dashboard (also referred to as simply \"Cohort\") groups app users by acquisition date. Perform performance analysis across user life cycles (LTV). Use the dashboard to gain insights as to how campaign differences alter campaign metrics."
x-zendesk:
  id: 207040496
  url: https://support.appsflyer.com/hc/en-us/articles/207040496-Cohort-and-retention-dashboard
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Dashboards
  section_id: 6550925337873
  position: 5
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-nohar-avigal, Marketers, Marketing Analytics]
  labels: [Cohort, Cohort Report, Advertisers, Marketers, Loc In Prog]
  promoted: false
  comments_disabled: true
  created_at: '2015-12-24T10:20:01Z'
  edited_at: '2026-06-03T07:45:58Z'
---
[![cohort main (2).png](https://files.readme.io/5a9307f4220a5bc41b5cebefe345a9b93165ac3874dd4faaed184d0309e92615-small-32127933337873.png)](https://files.readme.io/5a9307f4220a5bc41b5cebefe345a9b93165ac3874dd4faaed184d0309e92615-small-32127933337873.png)

## Cohort and retention dashboard

Related reading: [Differences between Cohort flavors](/docs/aggregated-and-analytics-reporting-overview#cohort-flavors)

To use Cohort and retention, select users from one or more apps and segment them by conversion time. Cohort metrics like revenue, ROI, and event conversion rates are available. Break the cohort down, for comparison purposes, into dimensions like campaign or media source. Doing so can uncover patterns or changes in performance over user or campaign life cycles. See [Cohort use cases](https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689).

> 📘 **Tip**
>
> Want to know more about cohort reports? Check out this short, informative [course on the AppsFlyer Learning Portal](https://elevate.appsflyer.com/learn/course/7804/play/18625/your-users-journey-with-retention-and-cohort-reports).

## Using Cohort

<div id="setting-up-an-analysis" />

<Accordion title="Setting up an analysis">

1. In AppsFlyer, from the side menu, select **Analyze** >**Cohort & Retention**.  
   The Cohort dashboard opens. The granularity and conversion date range display.  
   ![mceclip0__1_.png](https://files.readme.io/4113fd619422979d6a26004a55c009ebc48eef59d10ddc7c3e5becd2a758e6d4-32127949494417.png)
2. Select the [cohort period granularity](/docs/cohort-and-retention-dashboard#cohort-periods):
   * Hours
   * Days
   * Weeks
   * Months
3. Set the attribution period (user acquisition or retargeting engagement). Data relating to the most recent dates can result in [partial data](/docs/cohort-and-retention-dashboard#partial-data) indicated by dashes in charts and tables.
4. Click **Edit Cohort**.  
   The Cohort setup window opens.  
   ![CohortSetup.jpg](https://files.readme.io/f09cc190770d16a2ddf60e1f210f458114ac43d4c19fc5507fb50b0d1d2f5c77-32127949495825.jpg)
5. Complete the following:
   * [**Cohort view type**](/docs/cohort-and-retention-dashboard#view-types):
     * **User acquisition.**
     * **Retargeting**
     * **Unified:** Includes the in-app events of both user attribution and retargeting attributions. **Note**: Retargeting events take precedence over user acquisition events meaning the report contains events where [is\_primary\_attribution=true](/docs/raw-data-reporting-overview).
   * [**Trend type**](/docs/cohort-and-retention-dashboard#trend-types):
     * **User lifetime performance**.
     * **KPI by attribution time**.
   * **Users of**: Select 1 or more apps. **All** means the top 100 apps in your account. **Note**: Agencies can only select one app.
   * **Grouped by**:Select one or more [dimensions](/docs/cohort-and-retention-dashboard#list-of-dimensions-for-grouping-and-filtering) [Default: Media Source].
   * **Minimum cohort size**: Set the minimum cohort size. This avoids cluttering your report with insignificant (small) cohorts. [Default=1]
   * Optional fields:
     * **Filtered by**: Select one or more [dimensions](/docs/cohort-and-retention-dashboard#list-of-dimensions-for-grouping-and-filtering) to filter by. There are no default filters.
6. Click **Apply changes**.
7. Select the metric (KPI) you want to perform cohort analysis on. For in-app events, you select the in-app event and metric.
8. Select the cohort periods you want to view data for. Meaning which hours, days, weeks, or months post-conversion. The number of cohort periods you can select depends on your selected trend type.
9. Select whether to include **partial data** or to only show **complete data** (data for cohort periods that already ended).
10. Select whether to show **Cumulative** or **On day** (hour/day/week/month) data:
    * **Cumulative**: The cumulative or running total of the metric. Meaning Cohort 3 shows totals for Cohort periods 0-3.
    * **On day**: The value of the metric for that day only. Meaning Cohort 3 shows the metrics of Cohort period 3 only; not counting what happened in the periods before.
11. Select whether to display the **Heat map**.
12. Select whether to view the data as a table or chart. If you select table, you can select how many rows of data to see, either 25, 50, 100, or 200.
13. [Optional] [Managing saved cohort reports](/docs/cohort-and-retention-dashboard#using-my-reports-save-and-select-reports).

</Accordion>

<div id="using-my-reports-save-and-select-reports" />

<Accordion title="Using My reports—Save and select reports">

* My reports enable you to save the current dashboard settings for future use.
* Select a saved report to display the most current cohort data available.
* You can save one or more reports.
* Only you can access your My reports.

| Feature | Description |
| --- | --- |
| My reports | ![MyReports.png](https://files.readme.io/8f49c0e6dee55427bf3a64149ac48f67547967b8cd24aa8de3e34b760708f992-32127933340305.png)<br /><br />Select a report to display the most current data available. |
| Save changes | Save the report. Note: The currently selected report is overwritten. |
| Action options (![Elipse.png](https://files.readme.io/14b74dc6e733867bd16b6a3594f5f0856d7437462b2e0cf7c12adf11cfa295b3-32127949499409.png)) | <ul><li>**Save as new**<ul><li>Save the report using a different report name</li><li>[Option] Make this report default report</li></ul></li><li>**Rename**: Change the report name</li><li>**Set as default**: Make the report the default report. When you open Cohort this is the report that displays initially</li><li>**Delete**: Delete the report</li></ul> |

</Accordion>

<div id="export-the-cohort-to-a-csv-file" />

<Accordion title="Export the cohort to a CSV file">

* Cohort reports can be exported to CSV files.
* Columns names having a [partial suffix is the equivalent of dashes that display on charts and tables in the user interface.](/docs/cohort-and-retention-dashboard#partial-data)

**To export cohort reports to CSV files:**

* In the upper-right side of the Cohort reports window, click ![Download.png](https://files.readme.io/50af9c6cde00dada58a1bb89a9eb3e566f316c0e7336af68f4ce403584047a5b-32127933341969.png) (export).  
  The cohort report CSV file is downloaded.

</Accordion>

## Cohort concepts

<div id="cohort-periods" />

<Accordion title="Cohort periods">

Cohort periods work as follows: The conversion period is referred to as 0 (Hour 0, Day 0, Week 0, or Month 0). The next period after the conversion is referred to as 1 (Hour 1, Day 1, Week 1, or Month 1), and so on.

The number of periods available depends on the period granularity selected:

* For hour granularity the maximum number of post-conversion hours is 72.
* For day granularity the maximum number of post-conversion days is 180.
* For week granularity the maximum number of post-conversion weeks is 156
* For month granularity the maximum number of post-conversion months is 36

**Note**: In AppsFlyer a cohort period doesn't take into account the specific install timestamp. Rather, cohort hours are rounded down to the nearest hour, and cohort days, weeks, and months are based on the calendar day, week, or month. This may cause discrepancies when comparing AppsFlyer cohort data to the cohort data of other networks, where all cohort periods are determined by the specific install timestamp (meaning an hour is 60 minutes post-install timestamp, a day is the 24-hour post-install period after the install timestamp, etc.).

</Accordion>

<div id="view-types" />

<Accordion title="View types">

There are 3 cohort view types:

* **Unified**:
  * The combined performance of user acquisition and retargeting campaigns (including cost and revenue).
  * If an event is attributed to both conversion types, only the retargeting event is included. Meaning, the report is generated using the actual last touch media source. If you are familiar with raw data, it means events where [is\_primary\_attribution=true](/docs/raw-data-reporting-overview).
* **User acquisition:** Performance data from installs (reinstalls excluded unless [specially enabled](/docs/measure-reinstalls#attributed-to-the-first-install))
* **Retargeting: P**erformance data from re-attributions or re-engagements

[![OV.png](https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png)](https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png)

</Accordion>

<div id="trend-types" />

<Accordion title="Trend types">

There are 2 cohort trend types:

* **User lifetime performance**
* **KPI by attribution time**

#### **User lifetime performance**

* Each column in the table or point in the chart represents another cohort period (hour/day/week/month). The conversion period is referred to as cohort period 0. The first post-conversion period is cohort period 1 and so on. This enables you to compare user performance post-conversion, starting with the conversion period.
* You can select which cohort periods to get data for, up to the maximum for each granularity option (hour/day/week/month).

#### **KPI by attribution time**

* Each column in the table or point in the chart represents a cohort period (hours/days/weeks/months) on a period of the selected date range. This enables you to evaluate campaign performance over time and to view campaign KPIs relative to the conversion dates.
* The maximum number of cohort periods you can select to get data for is 5.
* If you select to view data as a chart instead of as a table, the chart displays only 1 cohort period (the lowest period selected).

#### Example: User lifetime performance trend vs. KPI by attribution time trend

In this example, the same raw data is used to generate the two cohort trend types. The raw data table contains attribution events related to different users A, B, C, and D. The users engage with an ad, install the app, and post-conversion make one or more purchases. Cohort day 0 is the install day.

[![CohortExample_en-us1.png](https://files.readme.io/013f6ebe78e8a94e7dcc36e62f73ad151ecd9a88c5b32e5e41ffa52f1567f744-38187655867025.png)](https://files.readme.io/7542605e2bb3972dc90fb12c9d6a328ff52ec65f0694a79752380d548e72e286-32127949500817.jpg)

</Accordion>

<div id="partial-data" />

<Accordion title="Partial data vs. complete data">

For a given day in the conversion data range, if the number of days that have elapsed since the conversion date is less than the cohort day, that cohort day contains partial data. Meaning partial data occurs on any day where the cohort day > current date-conversion date.

Use the partial/complete data control to select the data display mode:

* [Default] **Partial:**
  * Attribution data updates continuously in real-time, including revenue.
  * Cost data updates 6 times a day on average every four hours.
  * Partial data (indicated by dashes in the table and charts) is included.
* **Complete:** Data is updated daily and available a few minutes after midnight. Data of partial days doesn't display.

</Accordion>

<div id="list-of-dimensions-for-grouping-and-filtering" />

<Accordion title="Dimensions for grouping and filtering">

| Dimension | Comments | Group by | Filter by |
| --- | --- | --- | --- |
| <span id="ad"></span>Ad |  | **✓** | **✓** |
| <span id="ad-id"></span>Ad ID |  | **✓** | **✓** |
| <span id="adset"></span>Adset |  | **✓** | **✓** |
| <span id="adset-id"></span>Adset ID |  | **✓** | **✓** |
| <span id="agency"></span>Agency |  | **✓** | **✓** |
| <span id="apps"></span>Apps | Relevant when the report contains multiple apps | **✓** | **x** |
| <span id="attributed-touchtype"></span>Attributed touch-type | Values: Click, impression, or NA (organic) | **✓** | **✓** |
| <span id="campaign"></span>Campaign |  | **✓** | **✓** |
| <span id="campaign-id"></span>Campaign ID |  | **✓** | **✓** |
| <span id="channel"></span>Channel |  | **✓** | **✓** |
| <span id="conversion-type"></span>Conversion type | Cohort type dependant:<ul><li>**User acquisition**: Install</li><li>**Retargeting**: Re-engagement, Re-attribution</li></ul> | **✓** | **✓** |
| <span id="country-geo"></span>Geo | Based on user IP address | **✓** | **✓** |
| <span id="time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year"></span>Time. In the case of:<ul><li>Daily granularity is the date</li><li>Hourly granularity is the hour of the day</li><li>Weekly granularity is the week of the year</li><li>Monthly granularity is the month of the year</li></ul> | Cohort type dependant:<ul><li>**User acquisition and unified**: The time the app was launched for the first time.</li><li>**Retargeting**: The time the app was launched for the first time after re-engagement.</li></ul> | **✓** | **x** |
| <span id="install-app-store"></span>Install app store | Relevant for apps implementing Android [multi-store attribution.](/docs/set-up-multi-store-android-attribution)Reach out to your CSM to enable this dimension. | **✓** | **✓** |
| <span id="keywords"></span>Keywords | Search keywords provided by the integrated partners | **✓** | **✓** |
| <span id="media-source"></span>Media source |  | **✓** | **✓** |
| <span id="revenue-type"></span>Revenue type | In-app purchase or Ad revenue | **x** | **✓** |
| <span id="site-id"></span>Site Id |  | **✓** | **✓** |
| <span id="sub-param-1"></span>Sub Param 1 |  | **✓** | **✓** |

</Accordion>

<div id="metrics-available" />

<Accordion title="Metrics available">

| Metric | Description |
| --- | --- |
| Installs | Number of installs during the selected time range |
| Retargeting conversions | Number of retargeting conversions (re-attributions and re-engagements) during the selected time range |
| Attributions | Number of installs, re-engagements, and re-attributions during the selected time range |
| Cost | <ul><li>Campaign cost reported to AppsFlyer via click or API</li><li>Not available when:<ul><li>View type is retargeting.</li><li>Granularity is hours.</li></ul></li></ul> |
| Average eCPI | Average effective cost per install (attribution): Cost / attributions |
| Revenue | Revenue reported to AppsFlyer (cumulative or on day, depending on your setting) |
| Revenue count | Number of times revenue event occurred (cumulative or on day, depending on your setting) |
| ARPU | Average revenue per user: Revenue / unique users |
| Average revenue count | Average revenue event count reported to AppsFlyer (cumulative or on day, depending on your setting) |
| Sessions count (cumulative) | Cumulative number of times the app is launched, brought to the device foreground, or other measurement set by the developer |
| Average sessions (cumulative) | Average number of times per user the app is launched, brought to the device foreground, or other measurement set by the developer (cumulative) |
| Sessions count (on day) | On day number of times the app is launched, brought to the device foreground, or other measurement set by the developer |
| Average sessions (on day) | Average number of times per user the app is launched, brought to the device foreground, or other measurement set by the developer (on day) |
| Retention | Retention rate: On day number of unique users who opened the app / conversions * 100 |
| ROI | <ul><li>Return on investment: (Revenue - cost) / cost * 100</li><li>Not available when:<ul><li>View type is retargeting.</li><li>Granularity is hours.</li></ul></li></ul> |
| ROAS | <ul><li>Return on ad spend: Revenue / cost * 100</li><li>Not available when:<ul><li>View type is retargeting.</li><li>Granularity is hours.</li></ul></li></ul> |
| Uninstalls count | <ul><li>Number of app users who install the app and later uninstall the app (relevant for user acquisition only).</li><li>Not available when:<ul><li>View type is retargeting or unified.</li><li>Granularity is hours.</li></ul></li></ul> |
| Average uninstalls count | <ul><li>Average number of app users who install the app and later uninstall the app (relevant for user acquisition only)</li><li>Not available when:<ul><li>View type is retargeting or unified.</li><li>Granularity is hours.</li></ul></li></ul> |
| IAE count | Number of times the in-app event was performed (cumulative or on day, depending on your setting) |
| Average IAE count | Average number of times the in-app event was performed (cumulative or on day, depending on your setting) |
| IAE revenue | Revenue generated from the in-app event (cumulative or on day, depending on your setting) |
| Average IAE revenue | Average revenue generated from the in-app event (cumulative or on day, depending on your setting) |
| IAE unique users | Number of unique users who perform the in-app event (cumulative or on day, depending on your setting) |
| IAE conversions (cumulative) | In-app event conversion rate: Cumulative number of unique users performing the IAE / conversions * 100 |
| IAE conversions (on day) | In- app event conversion rate: On day number of unique users performing the IAE / conversions * 100 |
| eCPA | Effective cost per action (event): Cost / Cumulative number of unique users performing the InApp event |

</Accordion>

## Additional information

<div id="cohort-for-agencies" />

<Accordion title="Cohort for agencies">

* The advertiser needs to grant the agency permission to use Cohort.
  * To grant permission to an agency, the advertiser need to:
    1. In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations.**
    2. Select the agency.
    3. Go to the permissions tab, enable **Allow access to your retention and cohort reports.**
* Agencies are limited to accessing data of traffic generated by the agency. They can't see data related to organic traffic or non-organic traffic generated elsewhere.

</Accordion>

<div id="use-cases" />

<Accordion title="Use cases">

#### Revenue sum by geo

**Chart: Cumulative revenue per user**

[![Screenshot 2023-10-31 at 16.56.31.png](https://files.readme.io/cde4e25a051e159cd4e1a1f192eda79df1d3df6f5891fcda2c24a01e0baa462b-small-32127949501201.png)](https://files.readme.io/cde4e25a051e159cd4e1a1f192eda79df1d3df6f5891fcda2c24a01e0baa462b-small-32127949501201.png)

**Table: Revenue per day**

[![cohort use case 2.2.png](https://files.readme.io/be3949a33cdf489eb7735acbf06c7abbecfd46f84a20d463e50ddfe815cc3368-small-32127949501969.png)](https://files.readme.io/be3949a33cdf489eb7735acbf06c7abbecfd46f84a20d463e50ddfe815cc3368-small-32127949501969.png)

#### In-app event conversion

An advertiser defines the in-app event af\_purchase. The cohort table displays the percentage of app users in the cohort who made a purchase. We can see on day 10 for instance that 36.27% of the cohort users attributed to the Facebook Ads media source performed a purchase[.](https://files.readme.io/e365c6b930d765d97155b1fd4384a608cb7eb0339b2b61e4598ee2d5d17d3249-32127949502481.png)

[![cohort use case 3.png](https://files.readme.io/d2709ec30a9f6cc3fe55503af557153b6a2677948d0ca0b9a477af9e47746c33-small-32127933347089.png)](https://files.readme.io/d2709ec30a9f6cc3fe55503af557153b6a2677948d0ca0b9a477af9e47746c33-small-32127933347089.png)

</Accordion>

<div id="faq" />

<Accordion title="FAQ">

| Question | Answer |
| --- | --- |
| Can I view Apple Search Ads [keyword Cost and ROI](/docs/apple-ads-integration-setup#analyze-keyword-cost)? | Yes, you can.  <br />Apple Search Ads provides us with the cost for each keyword per day broken down by Campaign/Adset/Ad. **Note:** Breakdown by geo is not available. |
| For a given media source, why does the same campaign name display more than once? | <ul><li>If you use the same campaign name with campaigns having different campaign IDs then the name displays more than once.</li><li>You should allocate campaign IDs unique names</li><li>When changing campaign names, data is aligned to the last name used.</li></ul> |
| Can I view organic users? | Organic users, by default, are included in Cohort reports.<br /><br />**To limit the Cohort report to organic users only:**<ol><li>In the **Cohort dashboard**, click the **Edit cohort** button.</li><li>In the Cohort setup window set **Filter by** > **Media source** is **Organic**: [![cohort_setup_filtered_by_media_source_is_organic.png](https://files.readme.io/ba95397eac2b66a365a2aabb2f56587e78624be5ecd06dd6c0463e19dfe9e26a-32127949503889.png)](https://files.readme.io/ba95397eac2b66a365a2aabb2f56587e78624be5ecd06dd6c0463e19dfe9e26a-32127949503889.png)</li><li>Click **Apply changes**</li></ol> |
| Can I see data from deleted installs? | Deleted installs, such as installs from SRNs that were deleted due to data retention policies or GDPR deleted installs, can not be seen in the cohort dashboard.<br /><br />For more information [click here.](/docs/user-level-data-retention#partner-data-retention-periods) |
| Can I compare data for daily view to data in weekly or monthly views? | It’s not easy to compare data from a daily granularity to a weekly or monthly granularity, because the cohort LTVs don't align.<br /><br />When viewing cohorts in daily granularity, **Day 0** displays data for the day of the installs. Day 1 is the day after the install, Day 2 is 2 days post-install, etc.<br /><br />When viewing cohorts in weekly granularity, data displays for all installs made in the **entire Week 0**. Week 1 is the week after the install, Week 2 is 2 weeks post-install, etc.<br /><br />When viewing cohorts in monthly granularity, data displays for all installs made in the **entire Month 0**. Month 1 is the month after the install, Month 2 is 2 months post-install, etc.<br /><br />This means the LTV timelines don’t align. For example, if you look at data for January 9-15: If you use daily granularity, **Day 0** contains data for the first day of all **installs made January 9-15.** And **Day 6** contains data for the first 6 days post-install of all installs made **January 9-15**. Meanwhile, in **weekly granularity**, **Week 0** contains data for the **entire period** for all installs **made January 9-15**. So for installs on **January 9**, the data is like **Day 6**. But for installs on **January 15**, it’s like **Day 0**. |
| Why is there a decrease in the cumulative revenue from between cohort periods? | Usually, cumulative revenue increases with each cohort period, for example, D2 is higher than D1. However, sometimes it actually decreases because of negative revenue, for example, from return events. You can verify this by checking the on day (hour/day/week/month) data to see whether there's negative revenue for a specific cohort period. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Ad network access to Cohort | Not available |
| Agency access | Available:<ul><li>Limited to one app.</li><li>Hybrid accounts can't access Cohort.</li><li>Require access permission on an app-by-app basis.</li><li>Can't select multiple apps.</li><li>Access to organic data isn't possible.</li></ul> |
| Agency transparency | Available starting January 10, 2021 |
| App-specific time zone | <ul><li>Available</li><li>Exception: In all of the following cases, AppsFlyer ignores the app-specific time zone and uses the default time zone being UTC +0:<ul><li>The cohort report contains data from multiple apps, and the apps have different time zones.</li><li>The apps all have the same time zone, and the time zone for at least one of the apps changed during the cohort report period. To determine the report period:<ul><li>Start date: The first date in the conversion date range</li><li>End date: Is calculated by adding the number of days in the display duration to the last date in the conversion date range. Example: Last date: Jan 1, 2019. Report duration: 30 days. End date: Jan 31, 2019</li></ul></li><li>Weekly and monthly data will be displayed in UTC timezone</li></ul></li></ul> |
| Cost | <ul><li>In Cohort, cost data is included only if there is an associated attribution (install, re-engagement, or re-attribution). In other words, if a campaign incurs cost based on clicks and impressions but has no attributions the cost isn't included in cohort reports. This principle holds true for all levels of the advertising hierarchy.</li><li>AppsFlyer doesn't report cost data for keywords that contain uppercase letters in the cohort report or cohort API.</li></ul> |
| App-specific currency | <ul><li>Available</li><li>Exception: All apps need to use the same currency. If they don't, USD is used.</li></ul> |
| CSV file download | <ul><li>Maximum 10,000 rows.</li><li>Only available for user lifetime performance reports. Not available for the KPI by attribution time trend.</li><li>Limit of 10 CSV exports per minute and 100 per day (per user).</li></ul> |
| Charts | Charts display the top 5 or 10 ranked by the number of app users in the cohort. This is irrespective of the dimension displayed. |
| Table | Tables display up to 200 rows. Installs, retargeting conversions, or attributions (depending on the cohort view type), cost, and average eCPI (effective cost per install) always display irrespective of the metric selected. |
| Reinstalls | <ul><li>If post-reinstall events are considered unattributed organic:<ul><li>They're included only as of May 26, 2024. [Learn more](/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events)</li><li>The install time is based on the [device\_download\_time](/docs/raw-data-field-dictionary#device-info::dfd9504e) field.</li><li>They aren't counted toward unique user and retention measurements.</li></ul></li><li>If post-reinstall events are attributed to the first install, they're always included. [Learn more](/docs/unique-users)</li></ul> |
| Data queries | Limit of 20 data queries per minute and 500 per day (per user). Changing time period, grouping, KPI, etc. is considered a new query. |
| Organic data | Included |
| Non-organic data | Included |
| Data freshness | <ul><li>[Real-time](/docs/about-data-freshness-and-timezone-support#eod)</li><li>Exceptions:<ul><li>Daily cohorts:<ul><li>Cost, ad revenue, and uninstall metrics update Daily.</li><li>Uninstalls are calculated once a day using the UTC clock.</li></ul></li><li>Weekly and monthly cohorts:<ul><li>Real-time data is not available. The data will only show after it has been completed (meaning at the end of the week or month).<br />However, data, where some of the install data has been completed, such as some data has finished (post-install time) and others haven't started yet, will be displayed.</li></ul></li></ul></li></ul> |
| Historical data | <ul><li>Daily cohort: 2 years</li><li>Weekly/monthly cohorts: 3 years</li></ul> |
| Geo | <ul><li>Available</li><li>When geo is unknown (N/A), ad revenue data doesn't display when grouping by geo.</li></ul> |
| Session count | Session count for Day 0 in the Retargeting view might be lower than the user count.<br />There are a few reasons this can happen. The most common are:<ul><li>The  re-engagement session has already been attributed before the re-engagement is recorded. In this case, it will not be attributed to retargeting session</li><li>Filtering by other settings such as the **Minimum time between sessions**. In this case, the re-engagement is recorded. However, the sessions are filtered and won’t be recorded</li></ul> |
| Retargeting and Unified data | Monthly session data is only available from the first of September 2021 onwards |
| Ad revenue | <ul><li>Not available when viewing cohorts with hourly granularity.</li><li>There may be discrepancies between the ad revenue amounts displayed in the Cohort and Overview dashboards. This occurs when networks report revenue in UTC and the apps have a different timezone setting.</li><li>For af\_ad\_revenue events, the unique users metric isn't available when the aggregation type is:<ul><li>"Cumulative".</li><li>"On day," for dates between October 5, 2022-February 16, 2023.</li></ul></li></ul> |
| Week and month granularity | <ul><li>Week and month granularity is only available on the Cohort dashboard.</li><li>**Unique users**, **retention** and **conversion rate** metrics are not available if the data includes installs from before November 2022.</li><li>Historical data is only available from the year 2021 and on.</li><li>Days post-install: For cohorts that include installs for January, 2021-December, 2022, post-install time is limited to a year (meaning 52 weeks or 12 months). For cohorts that include later installs, [post-install data is available for up to 3 years (meaning 156 weeks or 36 months).</li></ul> |
| Cohort period | <ul><li>The conversion period is referred to as 0 (Hour 0, Day 0, Week 0, or Month 0). The next period after the conversion is referred to as 1 (Hour 1, Day 1, Week 1, or Month 1), and so on.</li><li>In AppsFlyer a cohort period doesn't take into account the specific install timestamp. Rather, cohort hours are rounded down to the nearest hour, and cohort days, weeks, and months are based on the calendar day, week, or month. This may cause discrepancies when comparing AppsFlyer cohort data to the cohort data of other networks, where all cohort periods are determined by the specific install timestamp (meaning an hour is 60 minutes post-install timestamp, a day is the 24-hour post-install period after the install timestamp, etc.).</li><li>The max cohort period (time range) query is 60 days for daily granularity, 60 hour for hourly, 12 months for monthly, and 26 weeks for weekly.</li></ul> |
| In-app event name | Recommended: Choose descriptive names for your in-app events, not simply "Revenue". An in-app event called "Revenue" can sometimes be confused and interfere with other revenue metrics. |
| Filters | When filtering by campaigns, you can select up to 100 values. |
| Partial data | Partial data is only available for daily timeframes; not for hourly, weekly, or monthly. |
| Events | The top 1,000 in-app events (by event count) are displayed alphabetically in the dropdown in the cohort analysis setup. |

</Accordion>

<div data-zendesk-anchors="cohort-dashboard=cohort-and-retention-dashboard 01H7T5AGP75A36TVWSM7H81E8P=cohort-and-retention-dashboard 01H7T5AGP7SGPZNK8VTDYBTY2B=tip 01H7T5AGP7XDKN85TR0J4V8TP3=using-cohort 01H7T5AGP7FDZNVM9PDBQJPMA0=setting-up-an-analysis using-my-reports%E2%80%94save-and-select-reports=using-my-reports-save-and-select-reports 01H7T5AGP8KRZ9207DCYGRGGC0=using-my-reports-save-and-select-reports 01H7T5AGP84HVD2BQ9Z8S13D5K=export-the-cohort-to-a-csv-file 01H8K817ZPJTRBP1KK90FVV57T=cohort-concepts 01H8K817ZPZTG476KZ83F6Z460=cohort-periods h_01JJH967X8P2NF3AFBSNMBD7B4=view-types 01H8K817ZPBVTGT5R18XGQHYT2=trend-types 01H8VNMYN0149T418BXM8RGBN9=user-lifetime-performance 01H8VNRGMWS8SSDM5KX08EDAS2=kpi-by-attribution-time 01H8K98XE9T23QGB440GHRB8E8=example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend 01H7T5AGP8PN12P2C4RGGQ0R95=partial-data 01H7T5AGP8XNG1CW2FPJSEEJ45=list-of-dimensions-for-grouping-and-filtering time-in-the-case-of%0A%20%20%0A%20%20daily-granularity-is-the-date%0A%20%20hourly-granularity-is-the-hour-of-the-day%0A%20%20weekly-granularity-is-the-week-of-the-year%0A%20%20monthly-granularity-is-the-month-of-the-year=time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year 01H7T5AGP708H7JGTS1RJ07H27=metrics-available information=additional-information 01H7T5AGP8J9AQ1BREYZ0JWWZ4=additional-information 01H7T5AGP83FRX1H9WVMS485MT=cohort-for-agencies 01H7T5AGP8JF0EAX8WEFNSEKM9=use-cases revenue-sum-by-country=revenue-sum-by-geo 01H7T5AGP8R6913GPXWM6DGASF=revenue-sum-by-geo inapp-event-conversion=in-app-event-conversion 01H7T5AGP80W5J1VEZ40MHGPPF=in-app-event-conversion 01H7T5AGP85T7H25863GXJCVCW=faq 01H7T5AGP90NADB7YXTFEMTSAX=traits-and-limitations" />
