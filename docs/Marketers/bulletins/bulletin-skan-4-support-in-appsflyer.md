---
title: 'Bulletin: SKAN 4 support in AppsFlyer'
metadata:
  keywords:
    - iOS
    - Marketers
    - SKAN
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2023-01-05T12:36:02Z'
  edited_at: '2023-08-20T06:59:16Z'
  id: 11938810583825
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/11938810583825-Bulletin-SKAN-4-support-in-AppsFlyer
---
| **Headline** | The AppsFlyer SKAdNetwork Solution now supports SKAN 4. This includes major changes to SKAN Conversion Studio, as well as SKAN dashboards and reports. |
| --- | --- |
| **Effective Date** | <ul><li>February 15, 2023: With native iOS SDK V6.10+</li><li>We recommend updating to the newest version V6.12+ even if you are using V6.10 since February<ul><li>You can see the list of changes <Anchor target="_blank" href="/marketers/docs/appsflyer-ios-sdk-release-notes">here</Anchor></li></ul></li><li>Coming soon: Support for other AppsFlyer SDKs and plugins</li></ul> |
| **Prerequisites** | For SKAN 4 iOS data to be properly recorded, the following is needed:<ul><li><Anchor target="_blank" href="/marketers/docs/appsflyer-ios-sdk-release-notes">AppsFlyer SDK version V6.12.1+</Anchor></li><li>The ad network must generate an ad signature for SKAdNetwork V4.</li><li>For ads that display in an app, the app must be built with iOS 16.1 SDK or later.</li><li>For web ads, the ad needs Safari 16.1 or later.</li><li>The advertised app must be App Store-signed and be running on a device with iOS 16.1 or later.</li></ul> |
| **Required actions** | <ul><li>Upgrade your <Anchor target="_blank" href="/marketers/docs/appsflyer-ios-sdk-release-notes">AppsFlyer SDK to V6.12.1+</Anchor></li><li>In AppsFlyer SKAN Conversion Studio, upgrade to the <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio#skan-4">SKAN 4 measurement mode</Anchor> and configure CVs for the 3 SKAN windows (or keep the default settings).</li></ul>**Note:** Once you upgrade to SKAN 4:<ul><li>The activity timer for pre-SKAN 4 installs is 48 hours.</li><li>You can't revert back to an earlier SKAN version.</li></ul> |
| **Changes in <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio#skan-4">SKAN Conversion Studio</Anchor>** | New SKAN 4 measurement mode to configure the 3 SKAN windows |
| **Changes in <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">dashboards</Anchor>** | <ul><li>SKAN overview dashboard includes new fields (available in the table settings) for event counts and revenue during the 3 SKAN windows:<ul><li>Event count D0-D2</li><li>Event count D0-D2 (modeled)</li><li>Event count D3-D7</li><li>Event count D8-D35</li><li>Revenue D0-D2 ($)</li><li>Revenue D0-D2 ($) (modeled)</li><li>Revenue D3-D7 ($)</li><li>Revenue D8-D35 ($)</li></ul></li><li>SSOT dashboard view displays D2 data fields, instead of Activity Window (AW). For SKAN 3 data, this field shows all activity window data, even if the window is longer or shorter than 2 days.</li></ul> |
| **Changes in <Anchor target="_blank" href="/marketers/docs/skan-raw-data-reports">reports</Anchor>** | <ul><li>SKAdNetwork reports include the following new fields to support SKAN 4:<ul><li>**skad\_postback\_sequence\_index**: Value is an integer that represents the SKAN window, either`0`,`1`, or`2`. For SKAN 3 the value is`0`.</li><li>**skad\_coarse\_conversion\_value**: Value can be`low`,`medium`, or`high`. For SKAN 3 the value is`null`.</li><li>**skad\_source\_identifier**: Value is a string up to 4 digits. For SKAN 3 the value is`null`.</li><li>**skad\_source\_domain**: Value is a string that represents the source of attributable web ads. For SKAN 3 the value is`null`.</li><li>**ad\_network\_creative**: Value is a string based on data enrichment received from the ad network. For SKAN 3 the value is empty.</li></ul></li><li>The following Data Locker and Push API reports are affected:</li></ul><ul><li>**skad\_installs** (via Data Locker and Push API)</li><li>**skad\_redownloads** (via Data Locker and Push API)</li><li>**skad\_inapps** (via Data Locker and Push API)</li><li>**skad\_postbacks** (via Data Locker)</li><li>**skad\_postbacks\_copy** (doesn't include the ad\_network\_creative field) (via Data Locker)</li><li><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQJzfkXrrdYU15SkRoEx2HlgezlNar76MHFMP1JWqNnGrtYuHFNz4Mf8u0diflSx-5-k0zfsMEzsuLS/pub?output=xlsx">See sample report schemas</Anchor></li></ul><ul><li>SKAN aggregated postback arrival date API and SKAN aggregated performance report API contain SKAN 4 fields. **Note**: You must use the path for V2 API token for SKAN 4.</li></ul> |