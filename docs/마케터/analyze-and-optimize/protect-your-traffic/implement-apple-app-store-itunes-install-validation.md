---
title: Implement Apple App Store (itunes) install validation
metadata:
  keywords:
    - Validation
    - iTunes
    - Apple
    - Store Install
    - Advertisers
    - app store
    - appstore
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2017-07-02T08:36:31Z'
  edited_at: '2026-10-13T00:19:20Z'
  id: 115003285626
  locale: ko
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ko/articles/115003285626
---
> **At a glance:** Prevent attribution of fraudulent activities by using the Apple install validation service for any iOS install (both organic and non-organic).

## Receipt validation flow

The receipt validation flow is as follows:

1. The AppsFlyer SDK gathers the Apple install receipt data and sends it with the launch message to the AppsFlyer servers.
2. The AppsFlyer servers validate this receipt data via the Apple install validation service.
3. If the Apple install validation service responds with error codes indicating that the install is invalid:
   * The install is rejected and does not appear in our dashboard
   * The ad network does not receive a postback or API call for the invalidated install
   * The install and all the corresponding in-app events are logged in the Protect360 Raw Data Reports: Installs and Blocked in-app events.

> 📘 **Notes**
>
> * The AppsFlyer iOS SDK version must be 6.9.2+
> * iOS devices with iOS version 7+ are supported for Install validation.
> * There are cases where Apple does not provide install receipt data and as such, AppsFlyer considers this a valid install in terms of app store install validation. However, Protect360 can block this install due to other fraud reasons.

<div data-zendesk-anchors="h_01JR7ST09GNZ2NTMP8D2YQ1DCH=receipt-validation-flow h_01JR7ST09G5QFHFTWK98NCJE97=notes" />
