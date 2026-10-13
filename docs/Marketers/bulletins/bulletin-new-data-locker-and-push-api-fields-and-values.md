---
title: "Bulletin: New Data Locker and Push API fields and values"
excerpt: "Learn about the new SKAdNetwork 4 fields and Meta ads media source updates coming to Data Locker and Push API reports."
table_of_contents: false
x-zendesk:
  id: 11135475316113
  url: https://support.appsflyer.com/hc/en-us/articles/11135475316113-Bulletin-New-Data-Locker-and-Push-API-fields-and-values
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 40
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-rona-einat, Marketers, Data Locker]
  labels: [Data Locker, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2022-12-04T20:34:01Z'
  edited_at: '2024-08-11T07:59:54Z'
---
| **What's new** | * SKAdNetwork reports via Data Locker and Push API contain new fields to support SKAN 4:<br />  * **skad\_postback\_sequence\_index**: Value is an integer that represents the SKAN window, either `0`,`1`, or `2`. For SKAN 3 the value is `0`.<br />  * **skad\_coarse\_conversion\_value**: Value can be `low`, `medium`, or `high`. For SKAN 3 the value is `null`.<br />  * **skad\_source\_identifier**: Value is a string up to 4 digits. For SKAN 3 the value is `null`.<br />  * **skad\_source\_domain**: Value is a string that represents the source of attributable web ads. For SKAN 3 the value is `null`.<br />  * **ad\_network\_creative**: Value is a string based on data enrichment received from the ad network. For SKAN 3 the value is `null`.<br />* When the media source is Meta ads, all reports display the value `Facebook Ads` (not Facebook). |
| --- | --- |
| **Effective date** | Report schema changes on January 9, 2023. Data population of those fields begins as part of the AppsFlyer SKAN 4 release (coming soon). |
| **Where** | The following reports are affected:<br /><br />* New SKAN 4 fields:<br />  * **skad\_installs** (via Data Locker and Push API)<br />  * **skad\_redownloads** (via Data Locker and Push API)<br />  * **skad\_inapps** (via Data Locker and Push API)<br />  * **skad\_postback****s** (via Data Locker)<br />  * **skad\_postbacks\_copy** (doesn't include the ad\_network\_creative field) (via Data Locker)<br />  * [See sample report schemas](https://docs.google.com/spreadsheets/d/e/2PACX-1vQJzfkXrrdYU15SkRoEx2HlgezlNar76MHFMP1JWqNnGrtYuHFNz4Mf8u0diflSx-5-k0zfsMEzsuLS/pub?output=xlsx)<br />* Meta ads media source: All reports |