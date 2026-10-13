---
title: "Bulletin: Activity data update in Master API and Pivot"
excerpt: "Master API and Pivot are moving to a new Activity data pipeline to ensure metrics match across all AppsFlyer dashboards and tools."
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
| Who this affects | * All Master API and Pivot customers analyzing Activity metrics: `activity_average_dau`, `activity_average_dau_mau_rate`, `activity_average_arpdau`, `activity_sessions`, `activity_revenue`, `activity_event_counter_[event_name]`, `activity_sales_in_usd_[event_name]`, `activity_average_unique_users_[event_name]`.<br /><br />Note: `activity_average_mau` isn't affected.<br /><br />* Cohort, LTV, Retention, and other data types aren't changing. If you combine Activity with them in the same report, some values, especially media source / `pid`, may not match until those data types adopt the same changes. |
| Required actions | This change happens automatically and most customers don't need to take any action.<br /><br />If you filter or group Activity reports by any value listed below, review those filters after October 15, 2026. Old values may return different or no results. |
| What you should know | Keep the following changes in mind:<br /><br />* **Metric values may show minor variance after the update.** Activity data is moving to a new data pipeline, so metric values may shift slightly. For Unique Users, DAU, and related metrics, expect up to a 3% difference. This is expected as part of the pipeline change, not a data error.<br />* **"Pre-install" and "preload" now roll up into "download"** for the `attributed_touch_type` grouping. Filtering or grouping Master API's `attributed_touch_type` by "pre-install" or "preload" no longer returns separate results. That traffic now appears under "download."<br />* **Nulls are replaced with empty strings.** This includes organic/None media source (`pid` in Master API, Media source in Pivot), which now comes through as an empty string.<br />* **Two media source names are changing:** `facebook` becomes `Facebook Ads`, and `twitter` and `twitter_int` become `Twitter`. All other media source names are unchanged.<br />* **New field truncation limits apply:**<br />  * `ad_id` (250 characters)<br />  * `ad_name` (256)<br />  * `event_name` (100)<br />  * `app_version` (64)<br />  * `agency` (32)<br />  * `keywords` (90)<br />  * `install_app_store` (50)<br />  * `os_version` (20)<br /><br />This migration moves Activity data to a more modern, scalable infrastructure that improves reliability and performance and supports future product improvements. |