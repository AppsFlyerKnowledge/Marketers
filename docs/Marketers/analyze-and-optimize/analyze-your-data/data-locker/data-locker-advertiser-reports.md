---
title: "Data Locker advertiser reports"
excerpt: "Aggregate and raw data reports available via Data Locker"
x-zendesk:
  id: 4410643856657
  url: https://support.appsflyer.com/hc/en-us/articles/4410643856657-Data-Locker-advertiser-reports
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Data Locker
  section_id: 6550945728657
  position: 1
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-rona-einat, Marketers, Data Locker]
  labels: [Advertisers, Premium Feature, Marketers, Loc In Prog, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2021-11-11T09:48:51Z'
  edited_at: '2026-10-14T12:22:43Z'
---
## Reports available via Data Locker for advertisers

<table><colgroup><col/><col/><col/></colgroup><thead><tr><th>Data type</th><th>Report group</th><th>Data Locker subscription required</th></tr></thead><tbody><tr><td>Raw</td><td>User journey—raw data</td><td>Yes (2)</td></tr><tr><td>Raw</td><td>Protect360</td><td>Yes</td></tr><tr><td>Raw</td><td>People-Based Attribution (PBA) </td><td>No </td></tr><tr><td>Raw</td><td>Incrementality</td><td>No </td></tr><tr><td>Raw</td><td>SKAN</td><td>No (1)</td></tr><tr><td>Raw</td><td>Revenue</td><td><p>Ad revenue single version report requires a Data Locker subscription.</p><p>All other reports require a ROI360 Advanced package subscription.</p></td></tr><tr><td>Raw</td><td>CTV, PC, and console apps</td><td>Yes</td></tr><tr><td>Aggregated</td><td>Cohort analytics</td><td>No (1)</td></tr><tr><td>Advanced aggregated</td><td>Cohort analytics</td><td>No (3)</td></tr><tr><td>Aggregated</td><td>Creative Optimization</td><td><p>No (1)</p><p>Requires a Creative Optimization Premium subscription plan.</p></td></tr><tr><td>Aggregated</td><td>SSOT</td><td>No (1)</td></tr><tr><td colspan="3"><p>(1) If you don't have a Data Locker subscription, you must provide <a href="./data-locker-for-marketers#storage-options">storage owned by you</a>.</p><p>(2) Except for Cross-platform engagements.</p><p>(3) Available with Data Locker subscription or with analytics API suite.</p></td></tr></tbody></table>

<div id="data-freshness-explanations" />

<Accordion title="Data freshness">

Data Locker report availability varies by report type. Depending on the report, data is delivered using an hourly, daily, or versioned freshness model. For more information on how these freshness intervals map to the Data Locker folder hierarchy, see [Folder structure](/docs/data-locker-for-marketers/live_preview/01KKER5X9ZVJNR5RWJ08ZN1P8Y#folder-structure).

| Data Freshness | Description | Report Example |
| --- | --- | --- |
| Hourly | Reports that are updated throughout the day and written to hourly `h` folders based on when AppsFlyer receives the data. | [In-app events report](/docs/in-app-events-overview) |
| Daily | Reports that are generated once per day rather than updated continuously throughout the day. | [Uninstall report](/docs/measure-uninstalls) |
| Versioned | Reports in which the same day's data can be published multiple times as newer or more complete data becomes available, with the latest version being the most accurate. | [Attributed ad revenue report](/docs/revenue-etl-reports#ad-revenue-versioned) |

</Accordion>

## Raw data reports

<div id="user-journey" />

<Accordion title="User journey">

For a description of the report types, see [user journey reports](/docs/raw-data-reporting-overview).

| Category | Report type (topic) | Data freshness | Organic/Non-organic | Unique to Data Locker |
| --- | --- | --- | --- | --- |
| User acquisition | Clicks | 1-3 hours | N/A | **✓** |
| Retargeting | Clicks | 1-3 hours | N/A | **✓** |
| User acquisition | Impressions | 1-3 hours | N/A | **✓** |
| Retargeting | Impressions | 1-3 hours | N/A | **✓** |
| User acquisition | Installs | 1-3 hours | Both |  |
| User acquisition | In-app events | 1-3 hours | Both |  |
| User acquisition | Attributed ad revenue | Daily+1 | Non-organic |  |
| User acquisition | Organic ad revenue | Daily+1 | Organic |  |
| Retargeting | Retargeting ad revenue | Daily+1 | Non-organic |  |
| Retargeting | Conversions | 1-3 hours | Non-organic |  |
| Retargeting | In-app events | 1-3 hours | Non-organic |  |
| Retargeting | Sessions | 1-3 hours | Both | **✓** |
| User acquisition | Sessions | 1-3 hours | Both | **✓** |
| User acquisition | Uninstalls | Daily-uninstall | Non-organic |  |
| User acquisition | Organic uninstalls | Daily-uninstall | Organic |  |
| Reinstalls | Reinstalls | 1-3 hours | Non-organic |  |
| Reinstalls | Organic reinstalls | 1-3 hours | Organic |  |
| User acquisition | Cross-platform engagements | Hourly | Both | **✓** |

</Accordion>

<div id="protect360" />

<Accordion title="Protect360">

See [about Protect360 reports](/docs/protect360-raw-data-reports)

| Report type (topic) | Data freshness |
| --- | --- |
| Blocked installs | 1-3 hours |
| Blocked in-app events | 1-3 hours |
| Blocked clicks | 1-3 hours |
| Post-attribution installs | Daily<br /><br />Each day's report contains post-attribution installs reported on the previous day. For example, the report for data generated on Monday is in the Tuesday report. |

</Accordion>

<div id="peoplebased-attribution" />

<Accordion title="People-Based Attribution">

**Data freshness**

Daily available 10-12 hours after the end of the previous day UTC. For example, data received on a Monday is processed after the end of the day and is available in the Monday h=23 folder. The data is available by 12:00 UTC on Tuesday

**Considerations**

* The data of all PBA brand bundles in the account is always provided without considering the app filter.
* Data segregation by app isn't available.

| Report type (topic) |
| --- |
| [Website visits](/docs/pba-raw-data-reports#website-visits-and-website-events) |
| [Website events](/docs/pba-raw-data-reports#website-visits-and-website-events) |
| [Website-assisted installs](/docs/pba-raw-data-reports#websiteassisted-installs::7e12586d) |
| [Conversion Paths](/docs/pba-raw-data-reports#conversion-paths) |

</Accordion>

<div id="incrementality" />

<Accordion title="Incrementality">

See [Incrementality reports](/docs/incrementality-for-remarketing-overview#available-reports)

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

About [SKAN raw data reports](/docs/skan-raw-data-reports)

**Data freshness**

* Data is available on the day following the day the postback is received by AppsFlyer or the data reported to AppsFlyer by API
* Data is contained in the h=23 folder of the date the data is received by AppsFlyer. Example: If the postback was received on Monday, it is processed after the end of the day. Processing is completed, by 12:00 UTC Tuesday, the data is made available in the Monday h=23 folder.

| Report type (topic) |
| --- |
| Postbacks |
| Postbacks copy (sent directly by iOS to AppsFlyer) |
| Installs |
| Redownloads |
| In-app events |
| SRN advertising dimensions |

</Accordion>

<div id="ad-revenue" />

<Accordion title="Revenue">

See [Revenue ETL Data Locker reports](/docs/revenue-etl-reports)

See [ad revenue raw data](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data)

</Accordion>

<div id="ctv" />

<Accordion title="CTV, PC, and console platform data">

See [CTV, PC, and console platform data via Data Locker](/docs/ctv-pc-and-console-data-via-data-locker)

</Accordion>

## Advanced raw data reports (Beta)

Advanced Reports introduce a new generation of raw data reports designed to provide structured, validated, and **AI-ready datasets**. They enable the ingestion and analysis of the **entire user journey, from the first engagement to conversion and post-install activity, using just three reports**.  
Built with **typed fields**, **refined field naming**, and a consistent schema across all datasets, these reports ensure clarity, accuracy, and ease of use. The unified structure simplifies joins between datasets, **reduces ETL and downstream processing complexity**, and delivers data that supports advanced analytics and gives you the flexibility to work with your data however you need. For more information, see [About Data Locker Advanced Reports](/docs/about-data-locker-advanced-reports).

<div id="advanced-reports" />

<Accordion title="Raw engagements report">

The Raw engagements report consolidates click and impression data across user acquisition and retargeting activities from both mobile and connected TV (CTV) platforms. By providing a unified view of user interactions with your ads, this report enables in-depth analysis of top-of-funnel performance and helps marketers identify which creatives and channels drive meaningful engagement. It also supports cost and reach optimization at the engagement level, providing a solid foundation for evaluating marketing exposure and traffic quality. For more information, see [Raw engagements report](/docs/about-data-locker-advanced-reports#engagements) in About Data Locker Advanced Reports.

| Category | Report type (topic) | Data freshness | Unique to Data Locker |
| --- | --- | --- | --- |
| User acquisition and retargeting | Clicks and impressions | 1–3 hours | ✅ |

</Accordion>

<div id="conversion-report" />

<Accordion title="Conversion report">

The Conversions report provides a comprehensive view of all app installations, including organic and non-organic sources across mobile and connected TV (CTV) platforms. By centralizing conversion data, marketers can perform comprehensive growth analysis using a single, streamlined dataset. Use this report to precisely measure and optimize marketing performance. For more information, see [Conversion report](/docs/about-data-locker-advanced-reports#conversions) in About Data Locker Advanced Reports.

| Category | Report type (topic) | Data freshness | Unique to Data Locker |
| --- | --- | --- | --- |
| User acquisition and retargeting | Conversions | 1–3 hours | ✅ |

> 📘 **Note**
>
> * Reinstalls are not included in this report.
> * For extended platform apps, including CTV, PC, and console, retargeting conversion events are not included.

</Accordion>

<div id="h_01K9CROSSPLATFORMREPORT" />

<Accordion title="End-user events report">

The End User Events report captures detailed in-app event data, including sessions, purchases, registrations, and level completions, across mobile and CTV platforms. Each event is enriched with a full attribution context, enabling detailed analysis of user behavior, retention, and lifetime value while ensuring complete attribution traceability. For more information, see [End-user events report](#enduser-events) in About Data Locker Advanced Reports.

| Category | Report type (topic) | Data freshness | Unique to Data Locker |
| --- | --- | --- | --- |
| User acquisition and retargeting | End user events | 1–3 hours | ✅ |

> 📘 **Note**
>
> For extended platform apps, including CTV, PC, and console, retargeting end-user events are not included.

</Accordion>

## Aggregated reports

<div id="cohort-analytics" />

<Accordion title="Cohort analytics">

**Data freshness**

The reports are typically available by 12:00 UTC in the folder of the preceding day. For example, if processing is completed by 12:00 UTC Tuesday, the data is made available in the Monday folder.

| Report type (topic) |
| --- |
| [Cohort unified](/docs/cohort-analytics-via-data-locker) |
| [Cohort user acquisition](/docs/cohort-analytics-via-data-locker) |
| [Cohort retargeting](/docs/cohort-analytics-via-data-locker) |

</Accordion>

<div id="advanced-aggregated-reports" />

<Accordion title="Advanced aggregated reports">

Advanced aggregated reports in Data Locker contain aggregated data with optimal data freshness, accuracy, granularity, and unlimited volume. [Learn more](/docs/advanced-aggregated-reports-in-data-locker)

</Accordion>

<div id="creative-optimization-etl" />

<Accordion title="Creative Optimization ETL">

Creative Optimization ETL reports equip your data analysts with all the information they need for creative performance analysis. Full asset-level performance reporting is provided, including all key performance indicators (KPIs), upper and lower funnel KPIs, attribution data, and creative asset data. [Learn more](/docs/creative-optimization-etl-reporting)

</Accordion>

<div data-zendesk-anchors="01H7WFZN6P1S49NYX8Q0W55P0B=reports-available-via-data-locker-for-advertisers 01H7WFZN6PQWASTMXM9V72QZER=data-freshness-explanations 01H7WFZN6P94YW1V79NT3HV5G4=raw-data-reports 01H7WFZN6PD75S557PDB5PSFFR=user-journey 01H7WFZN6QY2GV69N464EE196M=protect360 01H7WFZN6QW72FDBTMW2ZD7NZQ=peoplebased-attribution 01H7WFZN6QZ1B7BS6E59RVAF30=incrementality 01H7WFZN6Q0P99DCFA7MZQTVSX=skan 01H7WFZN6Q717F9Z1HG38JVBG3=ad-revenue 01H7WFZN6QMJGSAJR00MHYJB6Z=ctv Unified%20raw-data-reports=advanced-raw-data-reports-beta h_01JX9T0PGE93JNJ3S4NDP0C2YW=advanced-raw-data-reports-beta h_01K85EE8DA4E8D4SVHYV2PE42E=conversion-report h_01K85EE8DAWY52B7RJQ33MJ59B=note cross-platform-end-user-events-report=h_01K9CROSSPLATFORMREPORT h_01KMD3WY9MQABBWFCTJYVWG66S=note-1 01H7WFZN6Q90AT8N0VY5PKQ407=aggregated-reports 01H7WFZN6QNKXTRM7G6VFANSZ7=cohort-analytics h_01J0K1MEKEEAQBXF1YRZTG8V0X=advanced-aggregated-reports h_01J0TQ88VNSFZJ27T3E2P3MVE6=creative-optimization-etl" />
