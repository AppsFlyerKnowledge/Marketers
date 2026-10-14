---
title: "Activity metrics in My Dashboards"
x-zendesk:
  id: 38874924986001
  url: https://support.appsflyer.com/hc/en-us/articles/38874924986001-Activity-metrics-in-My-Dashboards
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Dashboards
  section_id: 6550925337873
  position: 2
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-maya-kahane, Marketers, Marketing Analytics, Ad Networks]
  labels: [Ad Networks, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2025-09-09T10:46:09Z'
  edited_at: '2026-08-06T06:38:18Z'
---
**At a glance:** Use Activity metrics in [My Dashboards](/docs/my-dashboards) to quickly assess app performance, spot engagement trends, analyze revenue, and detect issues early, across any date range, with improved accuracy and flexibility.

> 📘 **Note**
>
> Net revenue metrics roll out gradually to clients throughout July - August 2026. If you don't see them yet, no action is needed; they will become available for your account during this period. See [Bulletin: Cohort and Activity metrics update in My Dashboards](/docs/bulletin-cohort-and-activity-metrics-update-in-my-dashboards).

## About Activity metrics

The Activity metrics in My Dashboards allow users to analyze Activity, LTV, and Cohort data in one place. This allows you to monitor business performance and gain deeper insights by:

* Analyze **user Activity and stickiness** with real-time relevance.
* Measure **event performance, revenue, and session trends.**  
  Get unified visibility across **LTV, Actual, and Cohort** periods in a single dashboard.
* Customize reports using **daily or monthly** (Active users) breakdown.

Note: In My Dashboards, the term A**ctivity** has been renamed to **Actual**. This change clarifies that these metrics reflect real user actions during the selected date range and aren’t tied to LTV aggregation. Actual is also the default period for Sessions, Gross-Profit and Total Revenue.

## Dashboard information

**Activity View**

The **Activity view** template helps marketers quickly assess app performance, spot engagement trends, analyze revenue, and detect issues early, enabling faster, data-driven decisions across campaigns and platforms.

**Adding widgets to your dashboard**

You can add widgets to your dashboard by clicking the **+ Create new** button in the top-right of the dashboard,and select the type of widget you want to create: Table, KPI, Chart, in-app events table, in-app events chart, text, or Custom metric. More detailed instructions can be found [here](/docs/my-dashboards#add-widget).

**Adding metrics to your chart or table**

In the Chart Settings or Table Settings dialog,  click the Metrics + plus sign.

You can then add a Group by dimension and select Filters.

More detailed instructions can be found [here](/docs/my-dashboards#add-metric).

## Available Activity metrics

* All metrics besides Active users, Active users last 31 days, and DAU/MAU also support cohort periods and LTV.

| **Metric** | **Description** |
| --- | --- |
| Active Users | <ul><li>Number of unique Active users who opened the app at least once during the selected period, based on sessions, as per the selected time breakdown setting.</li><li>If daily is selected, it's shown as DAU.</li><li>If monthly is selected, it’s shown as MAU.</li><li>When viewed in line charts, column charts, or a table grouped by date, it is shown as DAU.</li><li>For information about querying raw data reports for DAU and MAU, see: [Calculate daily and monthly active users (DAU and MAU)](/docs/calculate-daily-and-monthly-active-users-dau-and-mau).</li></ul> |
| Active Users Last 31 Days | Number of unique users (counted only once) who opened the app at least once during the previous 31 days (Not based on calendar month). |
| DAU/MAU | The rate of returning users (stickiness).<br /><br />For example, a DAU/MAU rate of 50% means that the average user opened the app on 15 out of the previous 31 days.<br /><br />The DAU/MAU rate is a measure of user stickiness and provides a snapshot of user retention.<br /><br />Formula: Daily Active users / Active users in the last 31 days |
| Sessions | Sessions during the selected date range. |
| Total Revenue | Revenue generated for the selected period. Revenue consists of in-app purchases and ad revenue. |
| Net revenue | Net revenue for the selected period, aggregated from the af\_net\_revenue event parameter. For apps using ROI360 store revenue, this is gross revenue minus app store fees and taxes (Net = Gross - store fees - taxes); apps that send af\_net\_revenue themselves define the calculation. |
| First Visits | Number of first-time visits to a web app. Counted as rows where conversion\_name = first\_visit. Available for web apps only. |
| Re-visits | Number of non-organic returning visits to a web app. Counted as rows where conversion\_name = revisit. Available for web apps only. |
| User Acquisitions | Available for Cross-platform attribution or web apps. For web apps, User Acquisitions reflects First Visits unless a User Acquisition Event is configured. For mobile apps, User Acquisitions equals Installs. When viewing multiple apps together, User Acquisitions = Installs + First Visits (or the custom web event configured by the client). |

## Available In-app metrics

| **Metric** | **Description** |
| --- | --- |
| Conversion rate | Percentage of unique users (attributions) who perform the event. Formula: Event unique users / Attributions x 100 |
| Unique Users | Number of unique users (attributions) who perform the event |
| Average count | Average number of times this event was performed per attribution.<br /><br />Formula: Event count / Attributions |
| eCPA | Effective cost per action (event).<br /><br />Formula: Cost / Event unique users |
| Count | Number of times this event was performed |
| Revenue | Revenue generated by this specific event |
| ARPU | Average revenue per user.<br /><br />Formula: Revenue / Unique users (users = attributions) |
| Gross profit | Revenue - Cost |
| ROAS | Return on ad spend.<br /><br />Formula: Revenue / Cost * 100 |
| ROI | Return on investment.<br /><br />Formula: (Revenue - Cost) / Cost * 100 |
| Net revenue | Net revenue generated by this specific event (after app store fees and taxes). |
| Net ARPU | Average net revenue per user.<br /><br />Formula: Net revenue / Unique users (users = attributions) |
| Net profit | Net revenue - Cost |
| Net ROAS | Return on ad spend, based on net revenue.<br /><br />Formula: Net revenue / Cost * 100 |
| Net ROI | Return on investment, based on net revenue.<br /><br />Formula: (Net revenue - Cost) / Cost * 100 |

**Net revenue metrics**

Net metrics (Net revenue, Net ROI, Net ROAS, Net ARPU, Net profit) show net revenue instead of gross revenue. Net revenue is whatever value is sent in af\_net\_revenue, and the advertiser defines the calculation (for example, revenue after store fees and/or taxes, gross margin, or revenue after service fees). For apps using ROI360 store revenue, AppsFlyer calculates it as gross minus app store fees and taxes (Net = Gross - store fees - taxes).

The value comes from the af\_net\_revenue parameter of your in-app events, in the same way regular revenue metrics use af\_revenue. The value is in the transaction currency, expressed by af\_currency (default USD).

How the value is populated:

* If **ROI360 store revenue** is enabled for the app, AppsFlyer populates af\_net\_revenue automatically on the in-app purchase and subscription events it records.
* Otherwise, the value comes from the af\_net\_revenue parameter you send in the in-app event.
* If net revenue is not provided by either, the metric shows N/A.

See [About ROI360 store revenue](/docs/about-roi360-store-revenue) and [In-app events - Event structure](/docs/in-app-events-event-structure).

## Supported filter and group by dimensions

You can group and filter Activity metrics using:

* Daily time breakdown
  * Ad
  * Ad ID
  * Adset
  * Adset ID
  * App
  * Attribution type
  * Attributed touch type
  * Campaign
  * Campaign ID
  * Channel
  * Geo
  * Date
  * Keywords
  * Media source
  * Agency
  * Site ID
  * Platform
  * Sub param 1
  * Source
  * Engagement type
  * Engagement destination
  * Install app store
* Monthly time breakdown
  * App
  * Campaign
  * Campaign ID
  * Geo
  * Month
  * Media source
  * Agency

## Specifications and limitations

| **Spec** | **Remark** |
| --- | --- |
| Data freshness | Real-time is not supported for Web, CTV, or PC and console apps for Cohort and Activity metrics.<br /><br />**Note:** LTV metrics for CTV and PC and console apps are available in real-time — this limitation applies to Activity and Cohort data only. |
| Time granularity | For Web, CTV, and PC and console apps, Cohort and Activity data is available at daily granularity only. Weekly and monthly breakdowns aren't supported for these platforms. |
| Ad revenue | Real-time data is not supported. |
| Net revenue metrics - periods | Supported for Activity and Cohort metrics. Not supported for LTV. |
| Net revenue metrics - data freshness | Real-time is not supported. Data is available starting the next day. |
| Net revenue metrics - ad revenue | Ad revenue events are not included in net revenue metrics.<br /><br />**Tip:** To see net revenue that includes ad revenue, create a custom metric that adds ad revenue to net revenue, for example: Net revenue + Revenue (event: af\_ad\_revenue). See [Set up custom metrics in My Dashboards](/docs/beta-set-up-custom-metrics-in-my-dashboards). |
| Net revenue metrics - attribution source | Not supported for SKAN and SSOT. |
| Net revenue metrics - platforms | Android and iOS (mobile) only. |
| Timezones | All metrics are supported in local timezones except these that are UTC only:<ul><li>Active users last 31 days</li><li>DAU/MAU</li><li>Active users with a monthly grouping (MAU)</li></ul> |
| Charts | Currently supports **DAU** in line or column format |
| Widgets | KPI and table widgets support all Activity metrics. |
| Daily data range | Limited to 62 days per view |
| Uninstall events | Not included in Activity data |
| Historical data | Up to 3 years (daily) |
| Geo grouping | Based on geo at install time; limited to top 62 geos |
| Session metrics | <ul><li>Activity data is unified for UA and retargeting from February 1, 2025</li><li>You can see a Retargeting view by filtering **Attribution type** values by **Re-engagements** and **Re-attributions**.</li></ul> |
| Unified view metrics | All metrics are supported only in Unified view |
| Unique Users from in-app events and Active Users | **Unique Users from in-app events** and **Active Users** in My Dashboards are based on a statistical estimation algorithm that reduces duplicate counting and provides a consistent view of user Activity. |
| Active Users and Unique Users Actual | If the selected date range includes today and previous days, and the widget isn’t grouped by date, today’s data doesn’t appear. |

<div data-zendesk-anchors="h_01KXNJ1RB3ZWVG9SASCRNSS9N1=note h_01K4Q11V7F3KCHT69SC90J54Q6=about-activity-metrics h_01K4Q11V7MV95K09VC3D0190V3=dashboard-information h_01K4Q11V7QY8DB1FNRG3AJBDWR=available-activity-metrics available-inapp-metrics=available-in-app-metrics h_01K4Q11V7Z4Y4TWT5E2J0354JA=available-in-app-metrics h_01K4Q11V86S336QH6ZG5XS5AWG=supported-filter-and-group-by-dimensions h_01K4Q11V8DCBT4CY5MJZ44X7SX=specifications-and-limitations" />
