---
title: "Get conversion data using AppsFlyer SDK–Overview"
excerpt: "Use conversion data to identify various conversion scenarios, customize user experience, and more."
x-zendesk:
  id: 4410481069969
  url: https://support.appsflyer.com/hc/en-us/articles/4410481069969-Get-conversion-data-using-AppsFlyer-SDK-Overview
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Conversion data
  section_id: 6551287787537
  position: 2
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [Developers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2021-11-09T10:06:52Z'
  edited_at: '2025-11-09T07:54:23Z'
---
Use conversion data to:

- Send users to specific activities
- Serve them with customized content

> 🚧 Important!
>
> **Limitations of SDK conversion data**
>
> When using the AppsFlyer SDK callback `onConversionDataSuccess`, note that the callback can be triggered before the attribution process is complete. As a result, the data returned by the SDK might not match the data in AppsFlyer reports or APIs.
>
> **Recommendation:**
>
> Do not use the Get Conversion Data (GCD) method to collect or validate attribution data.
>
> To obtain accurate and complete attribution results, use AppsFlyer dashboards, reports, or APIs.

## Get conversion data

The AppsFlyer SDK returns conversion data using the following:

- `onConversionDataSuccess`: User Acquisition (UA) and re-attribution conversions  - Android: [onConversionDataSuccess](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerconversionlistener#onconversiondatasuccess)
  - iOS: [onConversionDataSuccess](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlibdelegate#onconversiondatasuccess)
  - Unity: loadConversionData
- `onAppOpenAttribution`: For re-engagement conversions