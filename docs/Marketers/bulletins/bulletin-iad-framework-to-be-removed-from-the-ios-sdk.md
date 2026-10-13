---
title: "Bulletin: iAd framework to be removed from the iOS SDK"
excerpt: "Important update regarding the removal of the deprecated iAd framework from the AppsFlyer iOS SDK to comply with Apple's future requirements."
table_of_contents: false
x-zendesk:
  id: 19329934807569
  url: https://support.appsflyer.com/hc/en-us/articles/19329934807569-Bulletin-iAd-framework-to-be-removed-from-the-iOS-SDK
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 31
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [Developers, Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2023-10-13T10:20:29Z'
  edited_at: '2024-01-07T07:33:43Z'
---
| | |
| --- | --- |
| **What's new** | Apple announced that any app that contains iAd framework code will no longer launch on iPhone and iPad in two years’ time. iAd framework was mandatory for iOS apps working with Apple Search Ads (ASA) in the past before it was replaced by the Apple Ads Attribution API.<br />Since version 6.10.1 the AppsFlyer iOS SDK has not been using the iAd framework and relied solely on the Apple Ads Attribution API. However, the framework code was still included in the SDK.<br />However, the next version of the AppsFlyer [iOS SDK](/docs/appsflyer-ios-sdk-release-notes) (6.12.3) will comply with Apple requirements and not contain any iAd framework code. Version 6.12.3 is expected in mid-November, and we strongly recommend adopting it.<br />**Please note that even if you don’t upgrade your SDK to 6.12.3, Apple provides a 2-year grace period before blocking your app from launching.** |
| **Effective date** | The future release date of iOS SDK 6.12.3 (November, 2023) |
| **What this impacts** | Attribution is not impacted. In fact, since v6.10.1 the AppsFlyer SDK uses the latest ASA AdServices framework and does not rely on the deprecated iAd framework. |