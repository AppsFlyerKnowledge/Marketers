---
title: "Aggregated and analytics reporting overview"
excerpt: "A comprehensive guide and comparison of the aggregated and analytics attribution reports, tools, and APIs available in AppsFlyer."
---
Aggregated analytic tools in the platform provide advertisers with metrics enabling them to assess the performance of their apps, campaigns, and users.

The tools differ in the way data is presented. Some report lifetime value (LTV) metrics for campaigns, while others, like Cohort, are used to analyze user engagement over time.

The tools detailed in this article relate to data that can be exported from the platform. Use the tool comparison table that follows to understand the main function and differences between the tools.

### Reporting method comparison

The following table describes the different reporting methods and dashboards to get aggregate data.

> 📘 Compare specs and limitations
>
> [Download the table as a CSV file](https://docs.google.com/spreadsheets/d/e/2PACX-1vSICicxcvD0996RT59fTLDJvdGUKxqPqr47f5SMD8BmsbZtrWIoxRxJEo7tAXTBBmnIbiH097VtK6L9/pub?output=xlsx) to see additional fields that explain various specs and limitations to help you compare and contrast the different reporting methods.

The additional spec fields in the downloadable CSV file include:

* [Data freshness](/docs/about-data-freshness-and-timezone-support): The period of time between the event occurrence and data becoming available via the reporting method.
* [LTV/activity](/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports): Whether data is LTV or activity.
* [Retargeting](/docs/retargeting-attribution-guide): Whether retargeting (re-engagement and re-attribution) data is displayed.
* [Re-install events attribution to first install](/docs/measure-reinstalls#attributed-to-the-first-install): Whether events after a reinstall can be attributed to the original install.
* [Timezone](/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles): What timezone (UTC or app-selected) is used to display data.
* [Unattributed events](/docs/measure-reinstalls#unattributed-organic-inapps): Whether events that aren't attributed after a re-install are displayed.
* [Campaign name changes](/docs/campaign-name-changes): Whether you can change campaign names without creating duplicate displays.

| Reporting method | Description |
| --- | --- |
| [Master API](/docs/master-api-user-acquisition-metrics-via-api)<br />(Premium feature) | Selected LTV, activity, retention, cohort, and Protect360 campaign performance KPIs by API, in CSV or JSON format. |
| [Pull API - aggregate reports](/docs/pull-api-aggregate-data) | Lifetime value (LTV) of users who install, re-engage, or re-attribute in CSV files. UA and retargeting data is separate; there isn't a unified option. |
| [Export data page - aggregate reports](/docs/aggregated-data-export-page) | Lifetime value (LTV) of users who install, re-engage, or re-attribute in CSV files. UA and retargeting data is separate; there isn't a unified option. |
| [SKAN overview](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer) | Metrics reported via iOS SKAN postbacks and additional data points during initial user measurement windows. |
| [SKAN Aggregate data APIs](/docs/skan-aggregated-performance-report-api) | Metrics reported via iOS SKAN postbacks and additional data points during initial user measurement windows. |
| [Protect360 dashboard](/docs/protect360-dashboard) | Metrics and insights relating to fraudulent traffic.<br />LTV-based data for installs, and activity-based data for in-app events. |
| [Cohort dashboard](/docs/cohort-and-retention-dashboard) | Various cohorted LTV user metrics for each day post-install. |
| [Cohort API](/docs/cohort-api)<br />(Premium feature) | Various cohorted LTV user metrics for each day post-install. Also includes event-level activity by event\_date for users whose conversion occurred within 365 days. |
| [Cohort Data Locker](/docs/cohort-analytics-via-data-locker)<br />(Premium feature) | Various cohorted LTV user metrics for each day post-install. Also includes event-level activity by event\_date for users whose conversion occurred within 1,095 days. |
| [Advanced aggregated reports](/docs/advanced-aggregated-reports-in-data-locker)<br />(Premium feature) | Versioned aggregated data reports. LTV. |
| [Custom dashboard](/docs/custom-dashboards) | Customized dashboard with LTV user acquisition metrics. |
| [Pivot reports](/docs/pivot-table-user-metrics)<br />(Premium feature) | Selected LTV, activity, retention, and Protect360 campaign performance KPIs, in the dashboard or via CSV. |
| [Cost ETL](/docs/set-up-and-use-roi360-cost-etl-reports) | Campaign cost data with the best granularity available per media source. |
| Usage report | A combination of all usage-based features in AppsFlyer that impact contract obligations during billing cycles timeframes. |
| [Creative Optimization dashboard](/docs/creative-optimization-guide) | LTV performance data about creatives. Meaning the metrics are for conversions that occurred from creatives during the selected date range. |

### Cohort data delivery methods

Cohort is available via a number of different delivery methods: [Cohort dashboard](/docs/cohort-and-retention-dashboard), [Cohort API](/docs/cohort-api), and [Cohort analytics via Data Locker](/docs/cohort-analytics-via-data-locker). The table that follows lists the differences.

| Characteristic | Cohort analytics in Data Locker | Advanced aggregated reports in Data Locker | Cohort Dashboard | Cohort API |
| --- | --- | --- | --- | --- |
| Multi or single app | Multi. Data is grouped per app in a single file or segregated into separate files per app. | Multi. Data is grouped per app in a single file or segregated into separate files per app. | Multi. Combined performance or grouped by app options. | Single |
| Groupings | Full campaign hierarchy and event names. Approx. 20 groupings | Full campaign hierarchy and event names. Approx. 20 groupings | 4 groupings | 7 groupings |
| Metrics available | All metrics | All metrics | 1 selectable metric and 3 fixed metrics per view | 1 selectable metric and 3 fixed metrics per call |
| Days post-attribution available (cohort days) | 365 | 1095 | 180 | 180 |
| Data export limitations | Entire data set is available | Entire data set is available | Manual download and settings | Rate and response size limited |
| Customizable request | No | No | Yes | Yes |

### User journey reports

The reports described are available via the Export Data page or by using Pull API aggregate.

They are [Lifetime value (LTV)](/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports) reports. Therefore:

* The earliest reporting date available is the first app attribution date.
* The reporting date range relates to the attribution date:
  * Install date for UA and Protect360 reports.
  * Re-attribution or re-engagement date in the case of retargeting reports.

#### UA LTV aggregate data reports containing non-organic and organic users

| Report name | Grouped by |
| --- | --- |
| Partners (media sources) | Agency, media source, campaign |
| Partners by date | Date, agency, media source, campaign |
| Daily activity | Date, agency, media source, campaign |
| Geo | Country, agency, media source, campaign |
| Geo by date | Date, country, agency, media source, campaign |
| View-through attribution (VTA) KPIs | [VTA reports are available by Pull API](/docs/pull-api-aggregate-data) |

> 📘 Note
>
> If Meta ads is the *media source* selected then additional columns are included: Adgroup ID, Adgroup name, Adset ID, Adset name

Date fields in the CSV files have the format yyyy-mm-dd. When you open a CSV file in Excel, date fields are formatted using your computer's date and time settings. Be sure to select the appropriate date display in [Excel.](https://support.office.com/en-us/article/format-a-date-the-way-you-want-8e10019e-d5d8-47a1-ba95-db95123d273e#ID0EAACAAA=Windows)

#### Examples of aggregate reports

[Report examples in a spreadsheet](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmzRons779Dk5QWVoPsOF8E7yJLwNPB1IF87shZr6rcMJLjszlSNIbAMVcdeQLysr8Bc4QAby5QB4u/pub?output=xlsx)

#### Fields in UA aggregate reports

| Field | Description | Report name | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| Partner (media source) | Partner by date | Daily | Geo | Geo by date | | |
| Country | Install country | | | | ✓ | ✓ |
| Date | Attribution date | | ✓ | | | ✓ |
| Agency/PMD (af\_prt) | Agency/partner name | ✓ | ✓ | ✓ | ✓ | ✓ |
| Media Source (pid) | Media source bringing the user (pid=media source) | ✓ | ✓ | ✓ | ✓ | ✓ |
| Campaign | Campaign name (c= campaign name) | ✓ | ✓ | ✓ | ✓ | ✓ |
| Campaign ID | Meta campaign ID | Meta ads only | Meta ads only | Meta ads only | Meta ads only | Meta ads only |
| Adgroup ID | Meta ad group ID or Ad ID | Meta ads only | Meta ads only | Meta ads only | Meta ads only | Meta ads only |
| Adgroup Name | Meta ad group | Meta ads only | Meta ads only | Meta ads only | Meta ads only | Meta ads only |
| Adset ID | Meta adset ID | Meta ads only | Meta ads only | Meta ads only | Meta ads only | Meta ads only |
| Adset Name | Meta adset name | Meta ads only | Meta ads only | Meta ads only | Meta ads only | Meta ads only |
| ARPU | Average revenue per user | ✓ | ✓ | | ✓ | ✓ |
| Average eCPI | Average eCPI | | ✓ | | | |
| Clicks | Number of clicks | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversion Rate | Number of installs/number of clicks | ✓ | ✓ | ✓ | ✓ | ✓ |
| CTR | Click-through rate | | ✓ | ✓ | | |
| `\{your event name\}`(Unique users) | Number of unique users who performed the event | ✓ | ✓ | | ✓ | ✓ |
| `\{your event name\}` (Event counter) | Event counter | ✓ | ✓ | | ✓ | ✓ |
| `\{your event name\}` (Sales in XXX) | Event sales in XXX where XXX is the app-selected currency | ✓ | ✓ | | ✓ | ✓ |
| Impressions | Number of impressions | ✓ | ✓ | | ✓ | ✓ |
| Installs | Number of installs | ✓ | ✓ | ✓ | ✓ | ✓ |
| Loyal Users | [default] User who opens the app more than 3 times | ✓ | ✓ | ✓ | ✓ | ✓ |
| Loyal Users/Installs | Loyal users rate | ✓ | ✓ | | | |
| ROI | Return on investment | ✓ | ✓ | | | |
| Sessions | - Number of non-organic app opens<br />- Organic and non-organic sessions are available in Cohort analytics | ✓ | ✓ | ✓ | ✓ | ✓ |
| Total Cost | - | ✓ | ✓ | | | |
| Total revenue | Total revenue generated from the media source and campaign | ✓ | ✓ | | ✓ | ✓ |

> 📘 Note
>
> Columns showing "Meta ads only" are included when selecting Meta ads as the only media source.

#### Retargeting aggregate data reports

Retargeting reports consist of users who engaged with a [retargeting campaign](/docs/retargeting-attribution-guide#retargeting-reports-and-raw-data) and performed a re-engagement or re-attribution.

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

#### Aggregate LTV retargeting reports fields

| Field | Description | Partners | Daily | Partners by date | Geo by date | Geo |
| --- | --- | --- | --- | --- | --- | --- |
| Date | Conversion date | - | - | ✓ | ✓ | - |
| Country | | - | ✓ | | ✓ | ✓ |
| Agency/PMD (af\_prt) | Agency/partner name | ✓ | ✓ | ✓ | ✓ | ✓ |
| Media Source (pid) | | ✓ | ✓ | ✓ | ✓ | ✓ |
| Campaign (c) | | ✓ | ✓ | ✓ | ✓ | ✓ |
| Clicks | | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversions | | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversion Type | Re-attribution or re-engagement | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversion Rate | Conversions/clicks | ✓ | ✓ | ✓ | ✓ | ✓ |
| Sessions | | ✓ | ✓ | ✓ | ✓ | ✓ |
| Loyal Users | | ✓ | ✓ | ✓ | ✓ | ✓ |
| Loyal Users/Installs | | ✓ | ✓ | ✓ | ✓ | ✓ |
| Total Cost | | - | - | - | - | - |
| Average eCPI | | - | - | - | - | - |
| Total Revenue | | ✓ | ✓ | ✓ | ✓ | ✓ |
| ROI | | - | - | - | - | - |
| ARPU | | ✓ | ✓ | ✓ | - | ✓ |

## Feature reports

### SKAdNetwork

[SKAdNetwork aggregate reports](/docs/skadnetwork-skan-solution-guide#reporting-options)

### Protect360—blocked fraud

<Image src="https://files.readme.io/70e5cd93b94c8bf512caa7294a2556628875e9436db93abb854ce2982585d6fc-ffbbc473bb0e74b9fb636ed735f69e9af6a25a18.png" alt="Protect360 blocked fraud report example" />

Blocked fraud aggregate reports provide details of events blocked by [Protect360](/docs/protect360-anti-fraud-guide).

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

> 🚧 Limitation
>
> The blocking reason **Bots** displays even in cases where the reason should be **app version** or **missing customer user id**.

### See also

<Cards>
  <Card title="Meta campaign management partners configuration" href="/docs/configuring-meta-campaign-management-partners" />
  <Card title="Raw data reporting overview" href="/docs/raw-data-reporting-overview" />
</Cards>