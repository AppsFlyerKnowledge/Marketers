---
title: Compare ROI360 ad revenue data with partner data
metadata:
  keywords:
    - ad revenue
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2023-10-11T17:40:51Z'
  edited_at: '2024-12-10T09:48:46Z'
  id: 19287636823953
  locale: en-us
  section: Revenue analysis
  section_id: 6551069075089
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/19287636823953-Compare-ROI360-ad-revenue-data-with-partner-data
---
> **At a glance:** Compare AppsFlyer ROI360 ad revenue data with mediation and user acquisition partner data.

Data needs to be received and processed before it becomes available in dashboards and reports. The time it takes for data to become available depends on the ROI360 package you have, as well as partner integration type, data freshness, and report type.

The following sections explain when and how to compare ROI360 ad revenue data in AppsFlyer reports to the data you may see in partner dashboards and reports.

<div id="comparing-appsflyer-data-with-mediation-partner-data" />

<Accordion title="Compare AppsFlyer data with mediation partner data">

| Integration type | Data type | What data can be compared to what |
| --- | --- | --- |
| S2S API | Device-level | <ul><li>Compare the total revenue displayed in the AppsFlyer activity dashboard or the total revenue displayed in the single version ad revenue reports via Data Locker to the mediation partner total revenue data.</li><li>Wait until the day after the revenue event (Day 0+1) to compare data, so that both AppsFlyer and the mediation partner have time to process the data.</li><li>Don't compare ad revenue event counts (reported in af\_ad revenue events) with impression counts.</li></ul> |
| SDK | Device-level | <ul><li>Compare the total revenue displayed in the AppsFlyer activity dashboard or the total revenue displayed in the single version ad revenue reports via Data Locker to the mediation partner total revenue data.</li><li>Wait until the day after the revenue event (Day 0+1) to compare data, so that both AppsFlyer and the mediation partner have time to process the data.</li><li>Don't compare ad revenue event counts (reported in af\_ad revenue events) with impression counts.</li></ul>**Note**: Since ad revenue data is mutable and it's possible that not all app users updated to the latest version with the ad revenue SDK connector, comparing AppsFlyer data to mediation partner data may result in differences. |
| SDK | Impression-level | Compare data in the mediation partner revenue dashboard to:<ul><li>The impression-level revenue report in Data Locker.<ul><li>Compare on the day of the revenue event (Day 0).</li><li>Relevant only for ROI360 Advanced customers.</li></ul></li><li>Device-level ad revenue in the single version ad revenue reports via Data Locker.<ul><li>Wait until the day after the revenue event (Day 0+1) to compare data, so that both AppsFlyer and the mediation partner have time to process the data.</li></ul></li><li>Aggregated revenue displayed in the activity dashboard.<ul><li>Wait until the day after the revenue event (Day 0+1) to compare data, so that both AppsFlyer and the mediation partner have time to process the data.</li></ul></li></ul> |
| SDK and S2S (freshness to accuracy) | Impression-level (via SDK) | Compare data in the mediation partner revenue dashboard to:<ul><li>Revenue displayed in the activity dashboard or the total revenue displayed in the single version ad revenue reports via Data Locker.<ul><li>Wait until the day after the revenue event (Day 0+1) to compare data, so that both AppsFlyer and the mediation partner have time to process the data.</li></ul></li><li>The impression-level revenue report in Data Locker.<ul><li>Compare on the day of the revenue event (Day 0).</li><li>Relevant only for ROI360 Advanced customers.</li></ul></li></ul>**Note**: Since ad revenue data is mutable and it's possible that not all app users updated to the latest version with the ad revenue SDK connector, comparing AppsFlyer data to mediation partner data may result in differences. |
| SDK and S2S (freshness to accuracy) | Device-level (via S2S API) | <ul><li>Compare the total revenue displayed in the AppsFlyer activity dashboard or the total revenue displayed in the single version ad revenue report via Data Locker to the mediation partner total revenue data.</li><li>Wait until the day after the revenue event (Day 0+1) to compare data, so that both AppsFlyer and the mediation partner have time to process the data.</li><li>Don't compare ad revenue event counts (reported in af\_ad revenue events) with impression counts.</li></ul> |

</Accordion>

<div id="comparing-appsflyer-data-with-user-acquisition-partner-data" />

<Accordion title="Comparing AppsFlyer data with user acquisition partner data">

ROI360 Advanced is required for user acquisition partners to have ad revenue data (via ad revenue postbacks or UA signals) available for comparison.

| Integration type | Data type | Partner data source | What data can be compared to what |
| --- | --- | --- | --- |
| S2S API | Device-level | UA signals | <ul><li>Compare the total revenue displayed in the AppsFlyer activity dashboard or the total revenue displayed in the single version ad revenue reports via Data Locker to the UA partner total revenue data.</li><li>Wait until the day after the revenue event (Day 0+1) to compare data.</li><li>Don't compare ad revenue event counts (reported in af\_ad revenue events) with impression counts.</li></ul> |
| SDK | Device-level | UA signals | <ul><li>Compare the total revenue displayed in the AppsFlyer activity dashboard or the total revenue displayed in the single version ad revenue reports via Data Locker to the UA partner total revenue data.</li><li>Wait until the day after the revenue event (Day 0+1) to compare data.</li><li>Don't compare ad revenue event counts (reported in af\_ad revenue events) with impression counts.</li></ul> |
| SDK | Impression-level | Ad revenue postbacks | Compare data in the user acquisition partner revenue dashboard to the:<ul><li>AppsFlyer cohort dashboard/report.<ul><li>Group data by the specific media source (UA partner).</li><li>Look at total revenue for af\_ad\_revenue events when filtering by a specific date. This allows comparing the ad revenue generated from installs that occurred on a certain reporting date to the ad revenue reported on postbacks related to those installs.</li><li>Wait until the day after the revenue event (Day 0+1) to compare data.</li></ul></li><li>AppsFlyer activity dashboard/single version ad revenue reports via Data Locker.<ul><li>Group data by the specific media source (UA partner).</li><li>Look at total revenue for af\_ad\_revenue events when filtering by a specific date. This allows comparing the ad revenue generated from installs that occurred on a certain reporting date to the ad revenue reported on postbacks related to those installs.</li><li>Wait until the day after the revenue event (Day 0+1) to compare data.</li></ul></li></ul> |
| SDK and S2S (freshness to accuracy) | Impression-level (via SDK) | Ad revenue postbacks | Compare data in the user acquisition partner revenue dashboard to the:<ul><li>ROI360 ETL Ad revenue SDK impression-level report.<ul><li>Wait until the day after the revenue event (Day 0+1) to compare data, so that both AppsFlyer and the mediation partner have time to process the data.</li></ul></li><li>Raw data postbacks in-app event report.<ul><li>Wait until the day after the revenue event (Day 0+1) to compare data, so that both AppsFlyer and the mediation partner have time to process the data.</li></ul></li></ul> |
| SDK and S2S (freshness to accuracy) | Device-level (via S2S API) | UA signals | <ul><li>Compare the total revenue displayed in the AppsFlyer activity dashboard or the total revenue displayed in the single version ad revenue reports via Data Locker to the UA partner total revenue data.</li><li>Wait until the day after the revenue event (Day 0+1) to compare data.</li><li>Don't compare ad revenue event counts (reported in af\_ad revenue events) with impression counts.</li></ul> |

</Accordion>

<div data-zendesk-anchors="h_01HCSS64Y99ZNAX64JRE5ZN3J7=comparing-appsflyer-data-with-mediation-partner-data h_01HCSS64Y9FDE00JN8XPWXG0CV=comparing-appsflyer-data-with-user-acquisition-partner-data" />
