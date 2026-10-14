---
title: "Bulletin: Activity data update in Master API and Pivot"
table_of_contents: false
x-zendesk:
  id: 49896622875537
  url: https://support.appsflyer.com/hc/en-us/articles/49896622875537-Bulletin-Activity-data-update-in-Master-API-and-Pivot
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 0
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: []
  labels: []
  promoted: false
  comments_disabled: true
  created_at: '2026-08-17T07:26:26Z'
  edited_at: '2026-09-17T11:36:13Z'
---
| Section | Details |
| --- | --- |
| What's new? | Master API and Pivot are moving to use the same Activity data that already powers My Dashboards, the AppsFlyer MCP and AI Assistant, and Agents, so Activity metrics match everywhere you look.<br /><br />Some underlying values used for filtering and grouping in Activity data are changing See below for details.<br /><br />Most customers don't need to do anything. |
| Effective date | October 15, 2026 |
| Who this affects | <ul><li>All Master API and Pivot customers analyzing Activity metrics: `activity_average_dau`, `activity_average_dau_mau_rate`, `activity_average_arpdau`, `activity_sessions`, `activity_revenue`, `activity_event_counter_[event_name]`, `activity_sales_in_usd_[event_name]`, `activity_average_unique_users_[event_name]`.</li></ul>Note: `activity_average_mau` isn't affected.<ul><li>Cohort, LTV, Retention, and other data types aren't changing. If you combine Activity with them in the same report, some values, especially media source / `pid`, may not match until those data types adopt the same changes.</li></ul> |
| Required actions | This change happens automatically and most customers don't need to take any action.<br /><br />If you filter or group Activity reports by any value listed below, review those filters after October 15, 2026. Old values may return different or no results. |
| What you should know | Keep the following changes in mind:<ul><li>**Metric values may show minor variance after the update.** Activity data is moving to a new data pipeline, so metric values may shift slightly. For Unique Users, DAU, and related metrics, expect up to a 3% difference. This is expected as part of the pipeline change, not a data error.</li><li>**"Pre-install" and "preload" now roll up into "download"** for the `attributed_touch_type` grouping. Filtering or grouping Master API's `attributed_touch_type` by "pre-install" or "preload" no longer returns separate results. That traffic now appears under "download."</li><li>**Nulls are replaced with empty strings.** This includes organic/None media source (`pid` in Master API, Media source in Pivot), which now comes through as an empty string.</li><li>**Two media source names are changing:** `facebook` becomes `Facebook Ads`, and `twitter` and `twitter_int` become `Twitter`. All other media source names are unchanged.</li><li>**New field truncation limits apply:**<ul><li>`ad_id` (250 characters)</li><li>`ad_name` (256)</li><li>`event_name` (100)</li><li>`app_version` (64)</li><li>`agency` (32)</li><li>`keywords` (90)</li><li>`install_app_store` (50)</li><li>`os_version` (20)</li></ul></li></ul>This migration moves Activity data to a more modern, scalable infrastructure that improves reliability and performance and supports future product improvements. |