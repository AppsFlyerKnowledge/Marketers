---
title: "Bulletin: New Data Locker and Push API fields and values"
excerpt: "Learn about the new SKAdNetwork 4 fields and Meta ads media source updates coming to Data Locker and Push API reports."
---
## What's new

* SKAdNetwork reports via Data Locker and Push API contain new fields to support SKAN 4:
  * **skad_postback_sequence_index**: Value is an integer that represents the SKAN window, either `0`, `1`, or `2`. For SKAN 3 the value is `0`.
  * **skad_coarse_conversion_value**: Value can be `low`, `medium`, or `high`. For SKAN 3 the value is `null`.
  * **skad_source_identifier**: Value is a string up to 4 digits. For SKAN 3 the value is `null`.
  * **skad_source_domain**: Value is a string that represents the source of attributable web ads. For SKAN 3 the value is `null`.
  * **ad_network_creative**: Value is a string based on data enrichment received from the ad network. For SKAN 3 the value is `null`.
* When the media source is Meta ads, all reports display the value `Facebook Ads` (not Facebook).

## Effective date

Report schema changes on January 9, 2023. Data population of those fields begins as part of the AppsFlyer SKAN 4 release (coming soon).

## Where

The following reports are affected:

* New SKAN 4 fields:
  * **skad_installs** (via Data Locker and Push API)
  * **skad_redownloads** (via Data Locker and Push API)
  * **skad_inapps** (via Data Locker and Push API)
  * **skad_postbacks** (via Data Locker)
  * **skad_postbacks_copy** (doesn't include the ad_network_creative field) (via Data Locker)
  * [See sample report schemas](https://docs.google.com/spreadsheets/d/e/2PACX-1vQJzfkXrrdYU15SkRoEx2HlgezlNar76MHFMP1JWqNnGrtYuHFNz4Mf8u0diflSx-5-k0zfsMEzsuLS/pub?output=xlsx)
* Meta ads media source: All reports