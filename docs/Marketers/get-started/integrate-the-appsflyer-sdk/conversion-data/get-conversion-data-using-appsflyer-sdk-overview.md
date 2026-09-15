---
title: "Get Conversion Data Using AppsFlyer SDK Overview"
excerpt: "Learn how to use conversion data from the AppsFlyer SDK to customize user experiences and identify conversion scenarios."
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
  - Unity: [loadConversionData](https://support.appsflyer.com/hc/articles/4412863162897#get-conversion-data)
- `onAppOpenAttribution`: For re-engagement conversions