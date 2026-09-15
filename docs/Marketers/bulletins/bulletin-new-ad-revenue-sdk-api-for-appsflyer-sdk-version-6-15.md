---
title: "Bulletin: New ad revenue SDK API for AppsFlyer SDK version 6.15+"
excerpt: "Learn about the transition from the ad revenue SDK connector to the new AdRevenue SDK API starting in AppsFlyer SDK version 6.15."
table_of_contents: false
---
| | |
| --- | --- |
| **What's new** | Impression-level ad revenue is now available using the AdRevenue SDK API instead of via the ad revenue SDK connector. |
| **Starting** | AppsFlyer SDK version 6.15 |
| **What you need to know** | - Until now, impression-level ad revenue has been available via the AppsFlyer ad revenue SDK **connector**. From the effective date, the integration will be via the AppsFlyer **SDK** itself (not a connector), using the ad revenue SDK API.<br />- The ad revenue SDK connector will continue to work with:<br />  - AppsFlyer Android SDK version 6.14.2 and below.<br />  - AppsFlyer iOS SDK version 6.14.6 and below. |
| **What you need to do** | - If you want to upgrade to AppsFlyer SDK version 6.15+ and you currently have the ad revenue SDK connector implemented, you need to remove the ad revenue SDK connector and integrate the ad revenue SDK API.<br />- Developer required. See developer [ad revenue SDK API instructions](https://dev.appsflyer.com/hc/docs/ad-revenue).<br />- Learn more about [impression-level ad revenue SDK API integration](/docs/integrate-the-roi360-ad-revenue-sdk-api). |