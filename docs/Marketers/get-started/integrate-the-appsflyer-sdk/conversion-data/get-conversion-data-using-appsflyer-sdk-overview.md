---
title: Get conversion data using AppsFlyer SDK–Overview
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:06:52Z'
  edited_at: '2025-11-09T07:54:23Z'
  id: 4410481069969
  locale: en-us
  section: Conversion data
  section_id: 6551287787537
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4410481069969-Get-conversion-data-using-AppsFlyer-SDK-Overview
---
**At a glance:** Use conversion data to identify various conversion scenarios, customize user experience, and more.

Use conversion data to:

* Send users to specific activities
* Serve them with customized content

> 🚧 **Important!**
>
> **Limitations of SDK conversion data**
>
> When using the AppsFlyer SDK callback `onConversionDataSuccess`, note that the callback can be triggered before the attribution process is complete. As a result, the data returned by the SDK might not match the data in AppsFlyer reports or APIs.
>
> **Recommendation:**
> Do not use the Get Conversion Data (GCD) method to collect or validate attribution data.
> To obtain accurate and complete attribution results, use AppsFlyer dashboards, reports, or APIs.

## Get conversion data

The AppsFlyer SDK returns conversion data using the following:

* * `onConversionDataSuccess`: User Acquisition (UA) and re-attribution conversions
    * Android: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerconversionlistener#onconversiondatasuccess">onConversionDataSuccess</Anchor>
    * iOS: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlibdelegate#onconversiondatasuccess">onConversionDataSuccess</Anchor>
    * Unity: loadConversionData
  * `onAppOpenAttribution`: For re-engagement conversions

<div data-zendesk-anchors="h_01K9KSQQDVDEACFRXS0M4JNW9M=important h_01HTZ6M409RPZAQM66R0H5HA16=get-conversion-data" />
