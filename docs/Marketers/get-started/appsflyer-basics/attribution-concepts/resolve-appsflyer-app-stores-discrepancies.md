---
title: "Resolve AppsFlyer App stores discrepancies"
excerpt: "Understand the leading causes of attribution discrepancies between AppsFlyer and app stores, and learn how to minimize them."
x-zendesk:
  id: 207040726
  url: https://support.appsflyer.com/hc/en-us/articles/207040726-Resolve-AppsFlyer-App-stores-discrepancies
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Attribution concepts
  section_id: 6551394235409
  position: 14
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-moran-davida, Marketers, Mobile Attribution]
  labels: [Google Play, AppsFlyer, iTunes, installs, Discrepancies, App Stre, Compare, Account, Advertisers, app store, appstore, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2015-12-24T12:52:53Z'
  edited_at: '2025-04-05T12:49:42Z'
---
Find the leading causes of attribution discrepancies between AppsFlyer and app stores, as well as tips to minimize these discrepancies.

## Attribution discrepancies

There are inherent differences in the attribution models used by all players in the mobile attribution ecosystem. The same applies to AppsFlyer and the main app stores: (iOS) App Store and (Android) Google Play. **Note**: In this article, the two stores are referred to as app store or app stores.

Because of the differences in attribution models, in some instances, the app store records more installs than AppsFlyer. In other instances, AppsFlyer records more installs than the app store.

![AF_vs_app_stores.png](https://files.readme.io/6f81aac30cdf1ab2331cd08e7a221c154e1f7104c15d47c47690baabaace856a-34114275895825.png)

> 📘 Note
>
> Discrepancies do not affect the accuracy of the **non-organic** installs count because the AppsFlyer attribution model credits one install per ad click. This is true even for a specific user with more than one device registered in the app store.

### Why AppsFlyer attributes less

The following are reasons for under-attribution by AppsFlyer:

| Cause | App stores | AppsFlyer | AppsFlyer tip |
| --- | --- | --- | --- |
| **Install definitions** | App stores record installs after the user downloads and installs the app, whether the user later launches the app or not. | AppsFlyer records new installs only after the first launch. <br />**Users that never launch are not counted in AppsFlyer**, even if they download and install (according to the App Store definition). | About 90% of mobile app downloads result in at least one launch, but this can vary significantly in different geos and verticals. |
| **Install record date** | App stores record the date of the download as the day of install. | AppsFlyer records the date of the first launch as the day of install. | In AppsFlyer, use longer periods of time as your queried date range to minimize this discrepancy. |
| **Time zones** | Data displays according to the local time zone of the advertiser. | By default, data displays using UTC±00:00 time zone. | You can set the app-preferred time zone to reduce this discrepancy ( [details here](/docs/changing-app-time-zone-settings)). |
| **Android user uninstalls and re-installs within the defined re-attribution window** | In some views, Google Play shows **two** **unique installs** for the same user, regardless of the time that elapsed from the first install. Other views show **unique users** and therefore are more closely aligned with AppsFlyer. | Inside the re-attribution window (by default 3 months) from the original install time, the user is not considered as new in AppsFlyer when re-installing. | You can [set the re-attribution window](/docs/set-up-re-attribution-window) from 1 to 24 months. |
| **iOS user uninstalls and re-installs inside the defined re-attribution window** | iTunes counts a new install every time the user uninstalls and re-installs. | Inside the re-attribution window (by default 3 months) from the original install time, the user is not considered as new in AppsFlyer when re-installing. | You can [set the re-attribution window](/docs/set-up-re-attribution-window) from 1 to 24 months. |

### Why AppsFlyer attributes more

The following are reasons for over-attribution by AppsFlyer:

| Cause | App stores | AppsFlyer | AppsFlyer tip |
| --- | --- | --- | --- |
| **Upgrading an existing app install from a version that did not contain the AppsFlyer SDK to a version that contains the AppsFlyer SDK** | The app stores regard this as the same user; not as a new install. | AppsFlyer shows the upgrade as organic installs. | - This peak usually drops after a few days as most users finish upgrading the app.<br />- New accounts may wish to [migrate their existing users](/docs/migration-to-appsflyer-from-other-vendors#device-migration%E2%80%94optional) to AppsFlyer to prevent this peak |
| **Device ID reset and Limit Ad Tracking Fraud** | App stores regard this as the same user; not as a new install. | AppsFlyer sees it as a new install on a new device. | AppsFlyer [Protect360 anti-fraud solution](/docs/protect360-anti-fraud-guide) detects if your app is suffering from these types of fraud. |
| **Installs coming from [out of store markets](/docs/set-up-multi-store-android-attribution) and [pre-installs](/docs/appsflyer-factory-preinstall-using-manifest-android)** | Google Play does not record these installs. | AppsFlyer counts these installs. | If you're advertising in an [Out-of-store Android market](/docs/set-up-multi-store-android-attribution), consult the documentation for the correct setup. |
| **Android user uninstalls and re-installs after the defined re-attribution window expires** | In some views, Google Play shows unique users (regardless of the time that elapsed from the first install), while other views show two unique installs for the same user and therefore are more closely aligned with AppsFlyer. | Once the re-attribution window (by default 3 months) expires, the re-install is considered as a new regular install in AppsFlyer. This means the same user is counted twice. | You can [set the re-attribution window](/docs/set-up-re-attribution-window) from 1 to 24 months. |