---
title: Resolve AppsFlyer App stores discrepancies
metadata:
  keywords:
    - Google Play
    - AppsFlyer
    - iTunes
    - installs
    - Discrepancies
    - App Stre
    - Compare
    - Account
    - Advertisers
    - app store
    - appstore
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-12-24T12:52:53Z'
  edited_at: '2025-04-05T12:49:42Z'
  id: 207040726
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207040726-Resolve-AppsFlyer-App-stores-discrepancies
---
> **At a glance:** Find the leading causes of attribution discrepancies between AppsFlyer and app stores, as well as tips to minimize these discrepancies.

## Attribution discrepancies

There are inherent differences in the attribution models used by all players in the mobile attribution ecosystem. The same applies to AppsFlyer and the main app stores: (iOS) App Store and (Android) Google Play. **Note**: In this article, the two stores are referred to as app store or app stores.

Because of the differences in attribution models, in some instances, the app store records more installs than AppsFlyer. In other instances, AppsFlyer records more installs than the app store.

<Image alt="AF_vs_app_stores.png" src="https://files.readme.io/6f81aac30cdf1ab2331cd08e7a221c154e1f7104c15d47c47690baabaace856a-34114275895825.png" width="605px" />

> 📘 **Note**
>
> Discrepancies do not affect the accuracy of the **non-organic** installs count because the AppsFlyer attribution model credits one install per ad click. This is true even for a specific user with more than one device registered in the app store.

### Why AppsFlyer attributes less

The following are reasons for under-attribution by AppsFlyer:

| Cause | App stores | AppsFlyer | AppsFlyer tip |
| --- | --- | --- | --- |
| **Install definitions** | App stores record installs after the user downloads and installs the app, whether the user later launches the app or not. | AppsFlyer records new installs only after the first launch.<br /><br />**Users that never launch are not counted in AppsFlyer**, even if they download and install (according to the App Store definition). | About 90% of mobile app downloads result in at least one launch, but this can vary significantly in different geos and verticals. |
| **Install record date** | App stores record the date of the download as the day of install. | AppsFlyer records the date of the first launch as the day of install. | In AppsFlyer, use longer periods of time as your queried date range to minimize this discrepancy. |
| **Time zones** | Data displays according to the local time zone of the advertiser. | By default, data displays using UTC±00:00 time zone. | You can set the app-preferred time zone to reduce this discrepancy (<Anchor target="_blank" href="/marketers/fr/docs/changing-app-time-zone-settings">details here</Anchor>). |
| **Android user uninstalls and re-installs within the defined re-attribution window** | In some views, Google Play shows **two** **unique installs** for the same user, regardless of the time that elapsed from the first install. Other views show **unique users** and therefore are more closely aligned with AppsFlyer. | Inside the re-attribution window (by default 3 months) from the original install time, the user is not considered as new in AppsFlyer when re-installing. | You can <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window">set the re-attribution window</Anchor> from 1 to 24 months. |
| **iOS user uninstalls and re-installs inside the defined re-attribution window** | iTunes counts a new install every time the user uninstalls and re-installs. | Inside the re-attribution window (by default 3 months) from the original install time, the user is not considered as new in AppsFlyer when re-installing. | You can <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window">set the re-attribution window</Anchor> from 1 to 24 months. |

### Why AppsFlyer attributes more

The following are reasons for over-attribution by AppsFlyer:

| Cause | App stores | AppsFlyer | AppsFlyer tip |
| --- | --- | --- | --- |
| **Upgrading an existing app install from a version that did not contain the AppsFlyer SDK to a version that contains the AppsFlyer SDK** | The app stores regard this as the same user; not as a new install. | AppsFlyer shows the upgrade as organic installs. | <ul><li>This peak usually drops after a few days as most users finish upgrading the app.</li><li>New accounts may wish to <Anchor target="_blank" href="/marketers/fr/docs/migration-to-appsflyer-from-other-vendors#device-migrationoptional">migrate their existing users</Anchor> to AppsFlyer to prevent this peak</li></ul> |
| **Device ID reset and Limit Ad Tracking Fraud** | App stores regard this as the same user; not as a new install. | AppsFlyer sees it as a new install on a new device. | AppsFlyer <Anchor target="_blank" href="/marketers/fr/docs/protect360-anti-fraud-guide">Protect360 anti-fraud solution</Anchor> detects if your app is suffering from these types of fraud. |
| **Installs coming from <Anchor target="_blank" href="/marketers/fr/docs/set-up-multi-store-android-attribution">out of store markets</Anchor> and <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-factory-preinstall-using-manifest-android">pre-installs</Anchor>** | Google Play does not record these installs. | AppsFlyer counts these installs. | If you're advertising in an <Anchor target="_blank" href="/marketers/fr/docs/set-up-multi-store-android-attribution">Out-of-store Android market</Anchor>, consult the documentation for the correct setup. |
| **Android user uninstalls and re-installs after the defined re-attribution window expires** | In some views, Google Play shows unique users (regardless of the time that elapsed from the first install), while other views show two unique installs for the same user and therefore are more closely aligned with AppsFlyer. | Once the re-attribution window (by default 3 months) expires, the re-install is considered as a new regular install in AppsFlyer. This means the same user is counted twice. | You can <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window">set the re-attribution window</Anchor> from 1 to 24 months. |

<div data-zendesk-anchors="h_01HNWP7A6GQC5ZX6WKBW411DVG=attribution-discrepancies h_01HNWP7A6GZJS246548Q5AFPZR=note h_01HNWP7A6G85PR1R66Q3KCRPNW=why-appsflyer-attributes-less h_01HNWP7A6GVVWMV6HECXQFTJT6=why-appsflyer-attributes-more" />
