---
title: SDK information (version & consent) dashboard
excerpt: >-
  Dashboard view of SDK, operating system (iOS, Android) adoption rates, and iOS
  ATT consent metrics.
metadata:
  keywords:
    - SDK Information
    - Advertisers
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
  created_at: '2017-02-15T09:32:15Z'
  edited_at: '2023-12-28T19:15:00Z'
  id: 115000805366
  locale: en-us
  section: Dashboards
  section_id: 6550925337873
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115000805366-SDK-information-version-consent-dashboard
---
## Version adoption and ATT consent dashboard

Data in the dashboard is derived from the af\_open (session) event and isn't related to install events. The dashboard has the following main sections: 

* SDK version information; available for all platforms (Android and  iOS)
* ATT consent metrics and iOS 16.1+ adoption (which provides the potential for SKAN 4 data)

**To view the SDK information dashboard**:

1. In AppsFlyer, from the side menu, select **Settings** > **SDK Information**.
2. Set the activity date range.   
   The metrics displayed are described in the sections that follow.

<div id="sdk-information-ios-and-android" />

<Accordion title="SDK information (iOS and Android)">

The following shows the version metrics available for iOS and Android apps using the most recent app open (launch) date

| Users by | Example |
| --- | --- |
| App version | Notice the introduction of app version V1.4.28 on May 20, 2021<br /><br />[![UsersByAppVersion__1_.png](https://files.readme.io/87bbf8aba8295e44430098c7c6fe4dc290cafca229e271a4185c763c609e9833-4402595560337.png)](https://files.readme.io/87bbf8aba8295e44430098c7c6fe4dc290cafca229e271a4185c763c609e9833-4402595560337.png) |
| SDK version | Notice the introduction of SDK V6.1.4 on May 20, 2021<br /><br />[![UsersBySDKVersion.png](https://files.readme.io/df7b4a1f380cd10162b3a13efc5da1ccc4b96e47d994e4c42b2674bfd4930bb6-4402589094033.png)](https://files.readme.io/df7b4a1f380cd10162b3a13efc5da1ccc4b96e47d994e4c42b2674bfd4930bb6-4402589094033.png) |
| Operating system version | [![UsersByOsVersion.png](https://files.readme.io/d56f8b43155bb226adaa1a276e00634fe721a01b74b5114d273ae66e74034dd9-4402589093521.png)](https://files.readme.io/d56f8b43155bb226adaa1a276e00634fe721a01b74b5114d273ae66e74034dd9-4402589093521.png) |
| Device type | [![UsersByDevice.png](https://files.readme.io/2f320f91d6a5a9f4bca0e3715cd33dfff2ac971af29e961592b4494bafe721f0-4402595560977.png)](https://files.readme.io/2f320f91d6a5a9f4bca0e3715cd33dfff2ac971af29e961592b4494bafe721f0-4402595560977.png) |

</Accordion>

<div id="att-metrics-ios-14" />

<Accordion title="iOS and ATT metrics">

The iOS version your users adopt can make a difference into what sort of data is available. For example, if users have iOS 16.1+, SKAN 4 data is potentially available.

The [ATT status](/docs/att-implications-ios-14-and-deprecation-of-lat) is set by iOS and reported to AppsFlyer by your app. The possible ATT status values are:

* **Authorized**: The user granted explicit agreement to be tracked
* **Denied**: The user explicitly didn't agree to be tracked, or LAT was on before the user upgraded to iOS 14+
* **Not determined**: The ATT prompt was not displayed, or the user didn't respond
* **Restricted**: Apple doesn't permit the user to be tracked

**Consider:**

* Chart metrics are calculated using unique user app-open events on a given date. Meaning, if a user didn't open the app on a given date that user isn't counted in the metrics of that date.
* iOS and ATT metrics only include the [ATT values defined by Apple](/docs/att-implications-ios-14-and-deprecation-of-lat#att-values-defined-by-apple); not additional values defined by AppsFlyer.
* Consent rate metrics are calculated using the formula: Authorized / (Authorized + Denied) x 100

#### ATT and iOS adoption metrics for iOS apps

| Chart | Example and remarks |
| --- | --- |
| ATT status of app opens | [![AttStatusByDate.png](https://files.readme.io/8e41e1602125903267e91a71b49305d43ca018aec77a2a991d0af08cb396825a-4402691807377.png)](https://files.readme.io/8e41e1602125903267e91a71b49305d43ca018aec77a2a991d0af08cb396825a-4402691807377.png)<br /><br />Relates to users having iOS 14+ who open the app on a given date. This means that the metrics display the user's ATT status on the given date. |
| Consent by app version | [![ATTAppVersion.png](https://files.readme.io/1f19917998f142180d0fdfb5448c90b280b2d6536844c63ce630d3656719f656-4402589092113.png)](https://files.readme.io/1f19917998f142180d0fdfb5448c90b280b2d6536844c63ce630d3656719f656-4402589092113.png) |
| Consent trend | [![ConsentTrend.png](https://files.readme.io/bae0c55c603e83b87fa50ba6d16c628443d565417c1aceee4536a5b96dd9435e-4402589093265.png)](https://files.readme.io/bae0c55c603e83b87fa50ba6d16c628443d565417c1aceee4536a5b96dd9435e-4402589093265.png) |
| iOS 16.1 user adoption rate | [![iso_user_adoption_rate.png](https://files.readme.io/2a29749fd968354f9836595cf20f07954be1aedce97df140d1d14452eb7306b3-15478514320529.png)](https://files.readme.io/2a29749fd968354f9836595cf20f07954be1aedce97df140d1d14452eb7306b3-15478514320529.png) |

</Accordion>

<div data-zendesk-anchors="h_01HGX98Q4FRVS2B35BVT683D5W=version-adoption-and-att-consent-dashboard h_01HGX98Q4F8PQYRSC0J2WE4RQX=sdk-information-ios-and-android h_01HGX98Q4FKWD5496P446FB31B=att-metrics-ios-14 h_01HGX98Q4G0C4XTC1DSVP96M19=att-and-ios-adoption-metrics-for-ios-apps" />
