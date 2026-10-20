---
title: 'Bulletin: New ad revenue SDK API for AppsFlyer SDK version 6.15+'
metadata:
  keywords:
    - Premium Feature
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
  created_at: '2024-07-24T08:59:01Z'
  edited_at: '2024-08-02T14:32:42Z'
  id: 26956998859153
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/26956998859153-Bulletin-New-ad-revenue-SDK-API-for-AppsFlyer-SDK-version-6-15
---
| **What's new** | Impression-level ad revenue is now available using the AdRevenue SDK API instead of via the ad revenue SDK connector. |
| --- | --- |
| **Starting** | AppsFlyer SDK version 6.15 |
| **What you need to know** | <ul><li>Until now, impression-level ad revenue has been available via the AppsFlyer ad revenue SDK **connector**. From the effective date, the integration will be via the AppsFlyer **SDK** itself (not a connector), using the ad revenue SDK API.</li><li>The ad revenue SDK connector will continue to work with:<ul><li>AppsFlyer Android SDK version 6.14.2 and below.</li><li>AppsFlyer iOS SDK version 6.14.6 and below.</li></ul></li></ul> |
| **What you need to do** | <ul><li>If you want to upgrade to AppsFlyer SDK version 6.15+ and you currently have the ad revenue SDK connector implemented, you need to remove the ad revenue SDK connector and integrate the ad revenue SDK API.</li><li>Developer required. See developer [ad revenue SDK API instructions](https://dev.appsflyer.com/hc/docs/ad-revenue).</li><li>Learn more about [impression-level ad revenue SDK API integration](/docs/integrate-the-roi360-ad-revenue-sdk-api).</li></ul> |