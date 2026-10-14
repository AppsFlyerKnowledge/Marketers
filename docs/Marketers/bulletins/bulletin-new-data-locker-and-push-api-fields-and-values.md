---
title: "Bulletin: New Data Locker and Push API fields and values"
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
| **What's new** | <ul><li>SKAdNetwork reports via Data Locker and Push API contain new fields to support SKAN 4:<ul><li>**skad\_postback\_sequence\_index**: Value is an integer that represents the SKAN window, either `0`,`1`, or `2`. For SKAN 3 the value is `0`.</li><li>**skad\_coarse\_conversion\_value**: Value can be `low`, `medium`, or `high`. For SKAN 3 the value is `null`.</li><li>**skad\_source\_identifier**: Value is a string up to 4 digits. For SKAN 3 the value is `null`.</li><li>**skad\_source\_domain**: Value is a string that represents the source of attributable web ads. For SKAN 3 the value is `null`.</li><li>**ad\_network\_creative**: Value is a string based on data enrichment received from the ad network. For SKAN 3 the value is `null`.</li></ul></li><li>When the media source is Meta ads, all reports display the value `Facebook Ads` (not Facebook).</li></ul> |
| --- | --- |
| **Effective date** | Report schema changes on January 9, 2023. Data population of those fields begins as part of the AppsFlyer SKAN 4 release (coming soon). |
| **Where** | The following reports are affected:<ul><li>New SKAN 4 fields:<ul><li>**skad\_installs** (via Data Locker and Push API)</li><li>**skad\_redownloads** (via Data Locker and Push API)</li><li>**skad\_inapps** (via Data Locker and Push API)</li><li>**skad\_postbacks** (via Data Locker)</li><li>**skad\_postbacks\_copy** (doesn't include the ad\_network\_creative field) (via Data Locker)</li><li>[See sample report schemas](https://docs.google.com/spreadsheets/d/e/2PACX-1vQJzfkXrrdYU15SkRoEx2HlgezlNar76MHFMP1JWqNnGrtYuHFNz4Mf8u0diflSx-5-k0zfsMEzsuLS/pub?output=xlsx)</li></ul></li><li>Meta ads media source: All reports</li></ul> |