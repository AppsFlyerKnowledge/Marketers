---
title: 'Bulletin: OneLink redirection to third-party Android app stores'
metadata:
  keywords:
    - Marketers
    - OneLink
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2021-04-08T08:39:22Z'
  edited_at: '2024-03-21T08:54:40Z'
  id: 360019130678
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360019130678-Bulletin-OneLink-redirection-to-third-party-Android-app-stores
---
| What's new | OneLink templates provide an option to redirect users without your app to third-party Android app stores. |
| --- | --- |
| Effective date | May 19, 2021 |
| Where | [OneLink template setup](/docs/create-a-onelink-template) |
| What | Before the change: OneLink templates provided options for users without your app to be redirected to Apple App Store, Google Play, or a web URL.<br /><br />After the change: OneLink templates also provide options for users without your app to be redirected to the following third-party Android app stores:<ul><li>Huawei AppGallery</li><li>Xiaomi Market</li><li>Samsung Galaxy Store</li><li>Oppo App Market</li><li>Vivo App Store</li></ul> |
| What you must know | <ul><li>Redirecting to third-party Android app stores requires your app in the other stores to have the same package name as the Android app selected in your OneLink template.</li><li>The APK package name (for example: com.shop.app) is used for the redirection, so make sure the APK package name exists in the third-party app store before you select it.</li><li>Only the package name is extracted from the Android app to redirect users. For example, if the AppsFlyer name includes a channel as well, like com.shop.app-store, only com.shop.app is extracted. In such a case, redirection works, but attribution doesn't.</li><li>If you select an Android app that is not in Google Play, you must enter a URL to which all Android users are redirected.</li></ul>[![](https://files.readme.io/5e9df9148e5059160401391ef857ad965d1154e1ee7516bc33804de6badc5cd9-4403341605265.png)](https://files.readme.io/5e9df9148e5059160401391ef857ad965d1154e1ee7516bc33804de6badc5cd9-4403341605265.png)<ul><li>If your Android app is available exclusively through a third-party store, [you must set its Google Play status to Published out of store when adding the app.](/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app) Choosing any other status will prevent redirection to the third-party store and will result in an error message.</li></ul> |