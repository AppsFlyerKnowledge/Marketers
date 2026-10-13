---
title: "Bulletin: SKAN 4 support in AppsFlyer"
excerpt: "An overview of AppsFlyer's support for SKAN 4, including required SDK updates, prerequisites, and changes to dashboards and reports."
table_of_contents: false
x-zendesk:
  id: 11938810583825
  url: https://support.appsflyer.com/hc/en-us/articles/11938810583825-Bulletin-SKAN-4-support-in-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 37
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, SKAdNetwork (SKAN)]
  labels: [iOS, Marketers, SKAN]
  promoted: false
  comments_disabled: true
  created_at: '2023-01-05T12:36:02Z'
  edited_at: '2023-08-20T06:59:16Z'
---
| | |
| --- | --- |
| **Headline** | The AppsFlyer SKAdNetwork Solution now supports SKAN 4. This includes major changes to SKAN Conversion Studio, as well as SKAN dashboards and reports. |
| **Effective Date** | - February 15, 2023: With native iOS SDK V6.10+<br />- We recommend updating to the newest version V6.12+ even if you are using V6.10 since February<br />  - You can see the list of changes [here](/docs/appsflyer-ios-sdk-release-notes)<br />- Coming soon: Support for other AppsFlyer SDKs and plugins |
| **Prerequisites** | For SKAN 4 iOS data to be properly recorded, the following is needed:<br />- [AppsFlyer SDK version V6.12.1+](/docs/appsflyer-ios-sdk-release-notes)<br />- The ad network must generate an ad signature for SKAdNetwork V4.<br />- For ads that display in an app, the app must be built with iOS 16.1 SDK or later. <br />- For web ads, the ad needs Safari 16.1 or later.<br />- The advertised app must be App Store-signed and be running on a device with iOS 16.1 or later. |
| **Required actions** | - Upgrade your [AppsFlyer SDK to V6.12.1+](/docs/appsflyer-ios-sdk-release-notes)<br />- In AppsFlyer SKAN Conversion Studio, upgrade to the [SKAN 4 measurement mode](/docs/skan-conversion-studio#skan-4) and configure CVs for the 3 SKAN windows (or keep the default settings).<br />**Note:** Once you upgrade to SKAN 4:<br />- The activity timer for pre-SKAN 4 installs is 48 hours.<br />- You can't revert back to an earlier SKAN version. |
| **Changes in [SKAN Conversion Studio](/docs/skan-conversion-studio#skan-4)** | New SKAN 4 measurement mode to configure the 3 SKAN windows |
| **Changes in [dashboards](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer)** | - SKAN overview dashboard includes new fields (available in the table settings) for event counts and revenue during the 3 SKAN windows:<br />  - Event count D0-D2<br />  - Event count D0-D2 (modeled)<br />  - Event count D3-D7<br />  - Event count D8-D35<br />  - Revenue D0-D2 ($)<br />  - Revenue D0-D2 ($) (modeled)<br />  - Revenue D3-D7 ($)<br />  - Revenue D8-D35 ($)<br />- SSOT dashboard view displays D2 data fields, instead of Activity Window (AW). For SKAN 3 data, this field shows all activity window data, even if the window is longer or shorter than 2 days. |
| **Changes in [reports](/docs/skan-raw-data-reports)** | - SKAdNetwork reports include the following new fields to support SKAN 4:<br />  - **skad\_postback\_sequence\_index**: Value is an integer that represents the SKAN window, either `0`, `1`, or `2`. For SKAN 3 the value is `0`.<br />  - **skad\_coarse\_conversion\_value**: Value can be `low`, `medium`, or `high`. For SKAN 3 the value is `null`.<br />  - **skad\_source\_identifier**: Value is a string up to 4 digits. For SKAN 3 the value is `null`. <br />  - **skad\_source\_domain**: Value is a string that represents the source of attributable web ads. For SKAN 3 the value is `null`.<br />  - **ad\_network\_creative**: Value is a string based on data enrichment received from the ad network. For SKAN 3 the value is empty.<br />- The following Data Locker and Push API reports are affected:<br />  - **skad\_installs** (via Data Locker and Push API)<br />    <br />  - **skad\_redownloads** (via Data Locker and Push API)<br />  - **skad\_inapps** (via Data Locker and Push API)<br />  - **skad\_postback** **s** (via Data Locker)<br />  - **skad\_postbacks\_copy** (doesn't include the ad\_network\_creative field) (via Data Locker)<br />  - [See sample report schemas](https://docs.google.com/spreadsheets/d/e/2PACX-1vQJzfkXrrdYU15SkRoEx2HlgezlNar76MHFMP1JWqNnGrtYuHFNz4Mf8u0diflSx-5-k0zfsMEzsuLS/pub?output=xlsx)<br />- SKAN aggregated postback arrival date API and SKAN aggregated performance report API contain SKAN 4 fields. **Note**: You must use the path for V2 API token for SKAN 4. |