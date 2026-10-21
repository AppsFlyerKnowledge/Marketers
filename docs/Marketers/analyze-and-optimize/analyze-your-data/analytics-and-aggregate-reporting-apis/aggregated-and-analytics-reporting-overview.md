---
title: Aggregated and analytics reporting overview
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
    - Ad Networks
  created_at: '2020-02-04T09:38:14Z'
  edited_at: '2026-09-07T09:56:56Z'
  id: 360005437257
  locale: en-us
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360005437257-Aggregated-and-analytics-reporting-overview
---
> **At a glance:** Description and comparison of aggregated and analytics attribution reports, tools, and APIs available.

## Aggregated and analytics performance reporting overview

Aggregated analytic tools in the platform provide advertisers with metrics enabling them to assess the performance of their apps, campaigns, and users.

The tools differ in the way data is presented. Some report lifetime value (LTV) metrics for campaigns, while others, like Cohort, are used to analyze user engagement over time.

The tools detailed in this article relate to data that can be exported from the platform. Use the tool comparison table that follows to understand the main function and differences between the tools.

<Accordion title="Reporting method comparison">

The following table describes the different reporting methods and dashboards to get aggregate data.

[**Download the table as a CSV file**](https://docs.google.com/spreadsheets/d/e/2PACX-1vSICicxcvD0996RT59fTLDJvdGUKxqPqr47f5SMD8BmsbZtrWIoxRxJEo7tAXTBBmnIbiH097VtK6L9/pub?output=xlsx) **to see additional fields that explain various specs and limitations to help you compare and contrast the different reporting methods.**

The additional spec fields in the downloadable CSV file include:

* <Anchor target="_blank" href="/marketers/docs/about-data-freshness-and-timezone-support">Data freshness</Anchor>: The period of time between the event occurrence and data becoming available via the reporting method.
* <Anchor target="_blank" href="/marketers/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV/activity</Anchor>: Whether data is LTV or activity.
* <Anchor target="_blank" href="/marketers/docs/retargeting-attribution-guide">Retargeting</Anchor>: Whether retargeting (re-engagement and re-attribution) data is displayed.
* <Anchor target="_blank" href="/marketers/docs/measure-reinstalls#attributed-to-the-first-install">Re-install events attribution to first install</Anchor>: Whether events after a reinstall can be attributed to the original install.
* <Anchor target="_blank" href="/marketers/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles">Timezone</Anchor>: What timezone (UTC or app-selected) is used to display data.
* <Anchor target="_blank" href="/marketers/docs/measure-reinstalls#unattributed-organic-inapps">Unattributed events</Anchor>: Whether events that aren't attributed after a re-install are displayed.
* <Anchor target="_blank" href="/marketers/docs/campaign-name-changes?">Campaign name changes</Anchor>: Whether you can change campaign names without creating duplicate displays.

| Reporting method | Description |
| --- | --- |
| <Anchor target="_blank" href="/marketers/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>  <br />(Premium feature) | Selected LTV, activity, retention, cohort, and Protect360 campaign performance KPIs by API, in CSV or JSON format. |
| <Anchor target="_blank" href="/marketers/docs/pull-api-aggregate-data">Pull API - aggregate reports</Anchor> | Lifetime value (LTV) of users who install, re-engage, or re-attribute in CSV files. UA and retargeting data is separate; there isn't a unified option. |
| <Anchor target="_blank" href="/marketers/docs/aggregated-data-export-page">Export data page - aggregate reports</Anchor> | Lifetime value (LTV) of users who install, re-engage, or re-attribute in CSV files. UA and retargeting data is separate; there isn't a unified option. |
| <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN overview</Anchor> | Metrics reported via iOS SKAN postbacks and additional data points during initial user measurement windows. |
| <Anchor target="_blank" href="/marketers/docs/skan-aggregated-performance-report-api">SKAN Aggregate data APIs</Anchor> | Metrics reported via iOS SKAN postbacks and additional data points during initial user measurement windows. |
| <Anchor target="_blank" href="/marketers/docs/protect360-dashboard">Protect360 dashboard</Anchor> | Metrics and insights relating to fraudulent traffic.  <br />LTV-based data for installs, and activity-based data for in-app events. |
| <Anchor target="_blank" href="/marketers/docs/cohort-and-retention-dashboard">Cohort dashboard</Anchor> | Various cohorted LTV user metrics for each day post-install. |
| <Anchor target="_blank" href="/marketers/docs/cohort-api">Cohort API</Anchor>  <br />(Premium feature) | Various cohorted LTV user metrics for each day post-install. Also includes event-level activity by event\_date for users whose conversion occurred within 365 days. |
| <Anchor target="_blank" href="/marketers/docs/cohort-analytics-via-data-locker">Cohort Data Locker</Anchor>  <br />(Premium feature) | Various cohorted LTV user metrics for each day post-install. Also includes event-level activity by event\_date for users whose conversion occurred within 1,095 days. |
| <Anchor target="_blank" href="/marketers/docs/advanced-aggregated-reports-in-data-locker">Advanced aggregated reports</Anchor>  <br />(Premium feature) | Versioned aggregated data reports. LTV. |
| <Anchor target="_blank" href="/marketers/docs/custom-dashboards">Custom dashboard</Anchor> | Customized dashboard with LTV user acquisition metrics. |
| <Anchor target="_blank" href="/marketers/docs/pivot-table-user-metrics">Pivot reports</Anchor>  <br />(Premium feature) | Selected LTV, activity, retention, and Protect360 campaign performance KPIs, in the dashboard or via CSV. |
| <Anchor target="_blank" href="/marketers/docs/set-up-and-use-roi360-cost-etl-reports">Cost ETL</Anchor> | Campaign cost data with the best granularity available per media source. |
| Usage report | A combination of all usage-based features in AppsFlyer that impact contract obligations during billing cycles timeframes. |
| <Anchor target="_blank" href="/marketers/docs/creative-optimization-guide">Creative Optimization dashboard</Anchor> | LTV performance data about creatives. Meaning the metrics are for conversions that occurred from creatives during the selected date range. |

</Accordion>

<Accordion title="Cohort data delivery methods">

Cohort is available via a number of different delivery methods: <Anchor target="_blank" href="/marketers/docs/cohort-and-retention-dashboard">Cohort dashboard</Anchor>, <Anchor target="_blank" href="/marketers/docs/cohort-api">Cohort API</Anchor>, and <Anchor target="_blank" href="/marketers/docs/cohort-analytics-via-data-locker">Cohort analytics via Data Locker</Anchor>. The table that follows lists the differences.

| Characteristic | Cohort analytics in Data Locker | Advanced aggregated reports in Data Locker | Cohort Dashboard | Cohort API |
| --- | --- | --- | --- | --- |
| Multi or single app | Multi. Data is grouped per app in a single file or segregated into separate files per app. | Multi. Data is grouped per app in a single file or segregated into separate files per app. | Multi. Combined performance or grouped by app options. | Single |
| Groupings | Full campaign hierarchy and event names. Approx. 20 groupings | Full campaign hierarchy and event names. Approx. 20 groupings | 4 groupings | 7 groupings |
| Metrics available | All metrics | All metrics | 1 selectable metric and 3 fixed metrics per view | 1 selectable metric and 3 fixed metrics per call |
| Days post-attribution available (cohort days) | 365 | 1095 | 180 | 180 |
| Data export limitations | Entire data set is available | Entire data set is available | Manual download and settings | Rate and response size limited |
| Customizable request | No | No | Yes | Yes |

Differences between cohort data delivery methods

</Accordion>

### User journey reports

The reports described are available via the Export Data page or by using Pull API aggregate.

They are <Anchor target="_blank" href="/marketers/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">Lifetime value (LTV)</Anchor> reports. Therefore:

* The earliest reporting date available is the first app attribution date.
* The reporting date range relates to the attribution date:
  * Install date for UA and Protect360 reports.
  * Re-attribution or re-engagement date in the case of retargeting reports.

<Accordion title="UA LTV aggregate data reports containing non-organic and organic users">

<table><thead><tr><th>Report name</th><th>Grouped by</th></tr></thead><tbody><tr><td>Partners (media sources)</td><td>Agency, media source, campaign</td></tr><tr><td>Partners by date</td><td>Date, agency, media source, campaign</td></tr><tr><td>Daily activity</td><td>Date, agency, media source, campaign</td></tr><tr><td>Geo</td><td>Country, agency, media source, campaign</td></tr><tr><td>Geo by date</td><td>Date, country, agency, media source, campaign</td></tr><tr><td>View-through attribution (VTA) KPIs</td><td><a href="./pull-api-aggregate-data" target="_blank">VTA reports are available by Pull API</a></td></tr><tr><td colspan="2"><strong>Note</strong>: If Meta ads is the <em>media source</em> selected then additional columns are included: Adgroup ID, Adgroup name, Adset ID, Adset name</td></tr></tbody></table>

Date fields in the CSV files have the format yyyy-mm-dd. When you open a CSV file in Excel, date fields are formatted using your computer's date and time settings. Be sure to select the appropriate date display in <Anchor target="_blank" href="https://support.office.com/en-us/article/format-a-date-the-way-you-want-8e10019e-d5d8-47a1-ba95-db95123d273e#ID0EAACAAA=Windows">Excel.</Anchor>

#### Examples of aggregate reports

[Report examples in a spreadsheet](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmzRons779Dk5QWVoPsOF8E7yJLwNPB1IF87shZr6rcMJLjszlSNIbAMVcdeQLysr8Bc4QAby5QB4u/pub?output=xlsx)

#### Fields in UA aggregate reports

<table><thead><tr><th rowspan="2">Field</th><th rowspan="2">Description</th><th colspan="5">Report name</th></tr><tr><th>Partner (media source)</th><th>Partner by date</th><th>Daily</th><th>Geo</th><th>Geo by date</th></tr></thead><tbody><tr><td>Country</td><td>Install country</td><td></td><td></td><td></td><td>✓</td><td>✓</td></tr><tr><td>Date</td><td>Attribution date</td><td></td><td>✓</td><td></td><td></td><td>✓</td></tr><tr><td>Agency/PMD (af_prt)</td><td>Agency/partner name</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Media Source (pid)</td><td>Media source bringing the user (pid=media source)</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Campaign</td><td>Campaign name (c= campaign name)</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Campaign ID</td><td>Meta campaign ID</td><td>Meta ads only</td><td>Meta ads only</td><td>Meta ads only</td><td>Meta ads only</td><td>Meta ads only</td></tr><tr><td>Adgroup ID</td><td>Meta ad group ID or Ad ID</td><td>Meta ads only</td><td>Meta ads only</td><td>Meta ads only</td><td>Meta ads only</td><td>Meta ads only</td></tr><tr><td>Adgroup Name</td><td>Meta ad group</td><td>Meta ads only</td><td>Meta ads only</td><td>Meta ads only</td><td>Meta ads only</td><td>Meta ads only</td></tr><tr><td>Adset ID</td><td>Meta adset ID</td><td>Meta ads only</td><td>Meta ads only</td><td>Meta ads only</td><td>Meta ads only</td><td>Meta ads only</td></tr><tr><td>Adset Name</td><td>Meta adset name</td><td>Meta ads only</td><td>Meta ads only</td><td>Meta ads only</td><td>Meta ads only</td><td>Meta ads only</td></tr><tr><td>ARPU</td><td>Average revenue per user</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>Average eCPI</td><td>Average eCPI</td><td></td><td>✓</td><td></td><td></td><td></td></tr><tr><td>Clicks</td><td>Number of clicks</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Conversion Rate</td><td>Number of installs/number of clicks</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>CTR</td><td>Click-through rate</td><td></td><td>✓</td><td>✓</td><td></td><td></td></tr><tr><td>`{your event name}(Unique users)</td><td>Number of unique users who performed the event</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>{your event name} (Event counter)</td><td>Event counter</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>{your event name}` (Sales in XXX)</td><td>Event sales in XXX where XXX is the app-selected currency</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>Impressions</td><td>Number of impressions</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>Installs</td><td>Number of installs</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Loyal Users</td><td>[default] User who opens the app more than 3 times</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Loyal Users/Installs</td><td>Loyal users rate</td><td>✓</td><td>✓</td><td></td><td></td><td></td></tr><tr><td>ROI</td><td>Return on investment</td><td>✓</td><td>✓</td><td></td><td></td><td></td></tr><tr><td>Sessions</td><td><ul><li>Number of non-organic app opens</li><li>Organic and non-organic sessions are available in Cohort analytics</li></ul></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Total Cost</td><td>-</td><td>✓</td><td>✓</td><td></td><td></td><td></td></tr><tr><td>Total revenue</td><td>Total revenue generated from the media source and campaign</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td colspan="7"><strong>Note:</strong> Columns showing "Meta ads only" are included when selecting Meta ads as the only media source.</td></tr></tbody></table>

</Accordion>

<Accordion title="Retargeting aggregate data reports">

Retargeting reports consist of users who engaged with a <Anchor target="_blank" href="/marketers/docs/retargeting-attribution-guide#retargeting-reports-and-raw-data">retargeting campaign</Anchor> and performed a re-engagement or re-attribution.

In retargeting reports, there is no distinction between organic and non-organic users.

To get retargeting reports via Pull API, append the *&reattr=true* parameter to performance reports URIs.

#### Aggregate LTV retargeting reports

| Report name | Grouped by |
| --- | --- |
| Partners (media sources) | Agency, media source, campaign |
| Partners by date | Date, agency, media source, campaign |
| Activity by date | Date, agency, media source, campaign |
| Country | Country, agency, media source, campaign |
| Country by date | Date, country, agency, media source, campaign |

#### Aggregate LTV retargeting reports

| Field | Description | Partners | Daily | Partners by date | Geo by date | Geo |
| --- | --- | --- | --- | --- | --- | --- |
| Date | Conversion date | - | - | ✓ | ✓ | - |
| Country |  | - | ✓ |  | ✓ | ✓ |
| Agency/PMD (af\_prt) | Agency/partner name | ✓ | ✓ | ✓ | ✓ | ✓ |
| Media Source (pid) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Campaign (c) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Clicks |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversions |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversion Type | Re-attribution or re-engagement | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversion Rate | Conversions/clicks | ✓ | ✓ | ✓ | ✓ | ✓ |
| Sessions |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Loyal Users |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Loyal Users/Installs |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Total Cost |  | - | - | - | - | - |
| Average eCPI |  | - | - | - | - | - |
| Total Revenue |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| ROI |  | - | - | - | - | - |
| ARPU |  | ✓ | ✓ | ✓ | - | ✓ |

</Accordion>

## Feature reports

<Accordion title="SKAdNetwork">

<Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide#reporting-options">SKAdNetwork aggregate reports</Anchor>

</Accordion>

<Accordion title="Protect360—blocked fraud">

![Protect360 blocked fraud report example](https://theme.zdassets.com/theme_assets/245528/ffbbc473bb0e74b9fb636ed735f69e9af6a25a18.png)

Blocked fraud aggregate reports provide details of events blocked by <Anchor target="_blank" href="/marketers/docs/protect360-anti-fraud-guide">Protect360</Anchor>.

The reports are available via Pull API. These reports aren't available via the Export Data page.

The date range relates to the install date.

#### Aggregate Protect360 reports available via Pull API

| Report name |
| --- |
| Partners (media sources) |
| Partners by date |
| Geo |
| Geo by date |
| Partner's campaign report |

**Limitation:** The blocking reason **Bots** displays even in cases where the reason should be **app version** or **missing customer user id**.

</Accordion>

#### See also

* <Anchor target="_blank" href="/marketers/docs/configuring-meta-campaign-management-partners">Meta campaign management partners configuration</Anchor>
* <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-overview">Raw data reporting overview</Anchor>

<div data-zendesk-anchors="aggregated-and-analytics-performance-reporting%E2%80%94tools-and-reports=aggregated-and-analytics-performance-reporting-overview 01EWA9VQ2HH93525BMK6WN0P6S=aggregated-and-analytics-performance-reporting-overview 01ED4D7W8CVAQ9V2GCEX1G6KD7=user-journey-reports 01ED4D7W8C3ZNBYR3CMHJF3QSE=examples-of-aggregate-reports h_01HDNYFR9KTQ7ZF35C7E7M7AF1=fields-in-ua-aggregate-reports h_01HDNYFR9MSJWCP3JA4M1WXN1H=aggregate-ltv-retargeting-reports aggregate-ltv-retargeting-reports::b2093953=aggregate-ltv-retargeting-reports-1 h_01HDNYFR9MSK9VQQ0Q889Z55TN=aggregate-ltv-retargeting-reports-1 h_01HDNYFR9MYXVZ5BA9FDZ6D82M=feature-reports h_01HDNYFR9MSZ9K8F283J0WBHCZ=aggregate-protect360-reports-available-via-pull-api h_01HDNYYJXVY9XHX87K06NXYQNS=see-also" />
