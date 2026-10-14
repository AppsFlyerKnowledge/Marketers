---
title: Troubleshooting discrepancies in AppsFlyer dashboards and reports
excerpt: >-
  Understand why there can be differences and discrepancies when comparing data
  from different dashboards and reports. Often, this may be because data in one
  place is lifetime value (LTV) data and in another it's activity data. LTV data
  is related to installs that occurred during a specified date range. Activity
  data is events that occurred during a specified date range.
metadata:
  keywords:
    - dashboard
    - activity
    - Advertisers
    - ltv
    - life time value
    - lifetime value
    - lifetime
    - Agencies
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2017-11-07T12:42:27Z'
  edited_at: '2025-12-18T00:01:08Z'
  id: 115005600889
  locale: en-us
  section: Dashboards
  section_id: 6550925337873
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115005600889-Troubleshooting-discrepancies-in-AppsFlyer-dashboards-and-reports
---
## About data differences and discrepancies

When comparing data from different dashboards and reports, the general reason for discrepancies is that you may not be comparing the same data to the same data. The following is a quick checklist to help you make sure you're comparing same to same:

* Are the app platforms the same (Android, iOS, CTV, etc.)?
* Are the app IDs the same?
* Are the dashboard/data filters the same?
* Are the currencies the same?
* Are the timezones the same?
* Is the [data freshness](/docs/about-data-freshness-and-timezone-support) the same?
* Is the data [aggregate data](/docs/aggregated-and-analytics-reporting-overview#toolapi-comparison) or [raw data](/docs/raw-data-reporting-overview)?
* Is the data LTV or activity?

One of the most common reasons for differences in data is due to comparing an LTV dashboard or report to an activity dashboard or report. See the following sections to learn more about LTV vs activity.

## LTV vs. Activity

There are two methods for analyzing user event data. Event data relates to actions performed by users post-installation, such as in-app purchases, registrations, and level completions. In AppsFlyer, event data is available grouped by the user acquisition date or the event date.

* Post-install event data grouped by user acquisition date is referred to as lifetime value (LTV).
* Post-install event data grouped by event date is referred to as activity.

**Note**: Installs are neither LTV nor activity.

Advertisers find both types of data useful but for different purposes. For this reason, both are available.

### LTV data

* LTV data are the events performed during the lifetime of a user who converted/installed the app in a specific date range. The date range refers to users who installed during the time period and shows how valuable they are during their time as customers. If a user converted/installed the app before the specified date, then even if events occurred during the specified date range, they don't show in LTV dashboards and reports.
* LTV data is a tool that shows the **quality of users** from different media sources. Campaign optimization depends on LTV data.

### Activity data

* Activity data shows what users did during a specified date range. meaning what events were performed by active app users during a specified date range. It doesn't matter if the users converted/installed the app outside of the date range.
* Because activity data shows a breakdown of chronological events, it's useful for measuring the overall performance of media sources during specific date ranges. For example, use activity data to see how many purchase events were performed by all app users during a specific month.
* Use activity data to compare user behavior in the current month relative to a previous month.

> 📘 **The train analogy**
>
> This analogy will help you understand the difference between activity and LTV data.
>
> **Activity:** Imagine you're watching a passing train. As the train passes, you see only the actions performed by the passengers on the train as they pass by. This is activity data.
>
> ![activity_data.jpg](https://files.readme.io/70a37d5dc16f0817d137f9011be9af5360bd7c4d2469a8abf9430fe69b2671c3-360002436957.jpg)
>
> **LTV**: Now imagine, that you board a train as an observer. The train is divided into railroad cars.
>
> * You board the car with other passengers at the departure platform. This is the install.
> * During the journey, you're able to observe all the actions performed by the passengers in the car. You observe the actions of these passengers until a passenger deboards the train, this is an uninstall.
> * You aren't able to view the actions of passengers in other railroad cars because they boarded the train before or after you. This then is LTV.
>
> ![ltv_data.jpg](https://files.readme.io/78925644f263b6d5ea5630a09e0b2155d153ce2c4b3060be5c8d7cb9ba0ce4e6-360002436977.jpg)

### AppsFlyer dashboards and reports—LTV or activity?

The dashboards enable marketers to optimize their non-organic traffic. Most of the dashboards are LTV-based, as marketers typically measure performance on an LTV basis. All aggregated data reports are LTV-based, and all raw data reports are activity-based.

The following table shows which dashboards and reports are LTV and which are activity.

| Data source | Data type |
| --- | --- |
| Overview dashboard | LTV |
| My Dashboards | LTV |
| SKAN Overview | LTV |
| Protect360 installs | LTV |
| Protect360 in-app events | Activity |
| Activity dashboard | Activity |
| Events dashboard | LTV |
| Custom dashboard | LTV |
| Retention | LTV |
| Cohort | LTV |
| Aggregate data performance reports | LTV |
| Raw data reports | Activity |
| Retargeting reports | LTV |
| Protect360 fraud prevention reports | Activity |
| Master API—campaign performance KPIs | Both |
| Pivot table | Both |

## Compare data between different dashboards and reports

The following sections explain how you can compare data between different dashboards and reports while effectively mitigating and troubleshooting the reasons why you might see differences or discrepancies in the data.

<div id="compare-ltv-and-activity-data-in-appsflyer" />

<Accordion title="Compare LTV and activity data in AppsFlyer">

When comparing AppsFlyer data, consider that when comparing LTV data and activity data, there are 2 differences to consider:

1. Activity data includes events from **installs that happened before** the date range.
2. LTV data includes **events that happened after** the date range.

To compare the two types of data correctly we need to neutralize the differences. This can be achieved by retrieving LTV data from activity data or vice versa. **Note**: Minor differences between similar sources are still possible due to differences in report generation time.

#### To retrieve LTV data out of raw activity data:

1. In AppsFlyer, from the side menu, select **Report** > **Raw Data Export.**
2. Set the **current day as the last day** of the date range (difference 2 solved).
3. Download the raw in-app events report.
4. Use the **Install time** column to filter out installs prior to the first day of the date range (difference 1 solved).

#### To retrieve activity data out of LTV data:

1. **Select media sources that started sending installs within the specified date range in AppsFlyer** (difference 1 solved).  
   This ensures the activity data does not include events performed within the date range that belong to installs that happened prior to the date range.
2. **Set the current day as the last day of the date range** (difference 2 solved).  
   This ensures the LTV data does not include events performed after the date range that belong to installs that happened within the date range.

</Accordion>

<div id="compare-different-appsflyer-aggregated-data-dashboards-and-reports" />

<Accordion title="Compare different AppsFlyer aggregated data dashboards and reports">

When comparing data between different AppsFlyer aggregated data dashboards and reports, LTV vs, activity may be the reason for discrepancies.

If you're aggregating data by geo, another reason for discrepancies could be that in AppsFlyer dashboards, aggregating by geo means the geo where the install occurred, while in raw data reports, it means the geo where the event occurred.

However, consider that there may be other reasons as well. [See the aggregated reporting method comparison for more information](/docs/aggregated-and-analytics-reporting-overview#toolapi-comparison)

</Accordion>

<div id="compare-appsflyer-data-with-external-data" />

<Accordion title="Compare AppsFlyer data with external data">

The vast majority of data sources, including Google and Apple, display activity data, that aren't LTV data. Therefore, to compare data from external sources with AppsFlyer data, you would usually use AppsFlyer activity data available in the raw data reports.

Consider that Meta Ads offers partial LTV data, limited to 28 days following the install.

There may also be other reasons for discrepancies between AppsFlyer data and external data. See also:

* [Google analytics discrepancies](/docs/google-analytics-integration-discrepancies)
* [Meta Ads discrepancies](/docs/meta-ads-discrepancies)
* [Snapchat discrepancies](/docs/snapchat-integration-discrepancies)
* [Google Ads discrepancies](/docs/google-ads-adwords-faq-and-discrepancies)
* [X Ads discrepancies](/docs/x-ads-formerly-twitter-ads-faq-and-discrepancies)
* [TikTok discrepancies](/docs/attribution-discrepancies-between-tiktok-for-business-and-appsflyer)
* [App store discrepancies](/docs/resolve-appsflyer-app-stores-discrepancies)
* [Third-party platform discrepancies](/docs/discrepancies-between-appsflyer-and-third-party-platforms)

</Accordion>

<div id="compare-inapp-event-raw-data-with-the-activity-view" />

<Accordion title="Compare in-app event raw data with the Activity view">

In-app events appear in both the LTV and Activity view in the dashboard. However, each employs a different counting logic.  
When reconciling event counts with raw data, always compare them against the Activity dashboard or the Activity view in My Dashboards, as these views represent event occurrences on the day they occurred.

Differences often arise when raw data isn’t filtered correctly, especially for retargeting events.

#### **Reconcile raw data with Activity event metrics**

To compare in-app event totals:

1. **Extract the required raw data reports:**

* Non-organic in-app events
* Retargeting in-app events
* Organic in-app events

2. **Filter retargeting events to avoid double-counting.**  
   In retargeting scenarios, double attribution occurs. An in-app event will be attributed to both:

* The retargeting media source (**primary attribution**)
* The media source that drove the original install (**secondary attribution**)

To avoid counting the same event twice across your reports, filter the field **Is primary attribution = True** in your raw data.  
Apply this filter before aggregating the UA reports so that only the primary attribution instance is included. This prevents duplicated retargeting events from inflating totals.

3. **Aggregate the event totals.**  
   Sum the events across the filtered sets.
4. **Compare the aggregated total** with the event count displayed in the **Activity dashboard**.

</Accordion>

<div data-zendesk-anchors="ltv-vs-activity=about-data-differences-and-discrepancies h_01HKA0R42YZMAM5Y20B7T2JCDZ=about-data-differences-and-discrepancies h_01J5WGZ13WPMNSB1NA0SMA77WJ=ltv-vs-activity h_01HKA0R42YQ2CJS67MDQSJHKEW=ltv-data h_01HKA0R42Y987PJRM70M7DFJ98=activity-data h_01J5WGZ13W5W8NJ1CRZQPHY939=the-train-analogy appsflyer-dashboards%E2%80%94ltv-or-activity=appsflyer-dashboards-and-reportsltv-or-activity h_01HKA0R42Y558BQ45Y9MFZHZM0=appsflyer-dashboards-and-reportsltv-or-activity h_01J5WKA06A7XYFN07V60VQ4FY5=compare-data-between-different-dashboards-and-reports h_01J5WHVQSNEA2WK83RBRDM1GT3=compare-ltv-and-activity-data-in-appsflyer retrieving-ltv-data-out-of-raw-activity-data=to-retrieve-ltv-data-out-of-raw-activity-data h_01HKA0R42Z3ZSMEM7T5F0V3VM7=to-retrieve-ltv-data-out-of-raw-activity-data retrieving-activity-data-out-of-ltv-data=to-retrieve-activity-data-out-of-ltv-data h_01HKA0R42ZHFM4RHG78GE51XK3=to-retrieve-activity-data-out-of-ltv-data h_01J5WK0AEN2N6J4P06CC3DMWPJ=compare-different-appsflyer-aggregated-data-dashboards-and-reports h_01J5WHVQSNZW66CQ4VGQGAKZB1=compare-appsflyer-data-with-external-data h_01KCNZWKFAWQ3KBJPCXP4BP8RM=compare-inapp-event-raw-data-with-the-activity-view h_01KCNZXRJKTGPH104H5Y1QNTM9=reconcile-raw-data-with-activity-event-metrics" />
