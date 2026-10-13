---
title: "Bulletin: OneLink redirection to third-party Android app stores"
excerpt: "OneLink templates now support direct redirection to third-party Android app stores including Huawei, Xiaomi, Samsung, Oppo, and Vivo."
table_of_contents: false
x-zendesk:
  id: 360019130678
  url: https://support.appsflyer.com/hc/en-us/articles/360019130678-Bulletin-OneLink-redirection-to-third-party-Android-app-stores
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 57
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-asaf-mashiah, Marketers, OneLink]
  labels: [Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2021-04-08T08:39:22Z'
  edited_at: '2024-03-21T08:54:40Z'
---
| What's new | OneLink templates provide an option to redirect users without your app to third-party Android app stores. |
| --- | --- |
| Effective date | May 19, 2021 |
| Where | [OneLink template setup](/docs/create-a-onelink-template) |
| What | Before the change: OneLink templates provided options for users without your app to be redirected to Apple App Store, Google Play, or a web URL.<br /><br />After the change: OneLink templates also provide options for users without your app to be redirected to the following third-party Android app stores:<br /><br />* Huawei AppGallery<br />* Xiaomi Market<br />* Samsung Galaxy Store<br />* Oppo App Market<br />* Vivo App Store |
| What you must know | * Redirecting to third-party Android app stores requires your app in the other stores to have the same package name as the Android app selected in your OneLink template.<br />* The APK package name (for example: com.shop.app) is used for the redirection, so make sure the APK package name exists in the third-party app store before you select it.<br />* Only the package name is extracted from the Android app to redirect users. For example, if the AppsFlyer name includes a channel as well, like com.shop.app-store, only com.shop.app is extracted. In such a case, redirection works, but attribution doesn't.<br />* If you select an Android app that is not in Google Play, you must enter a URL to which all Android users are redirected.  <br /><br />  [![](https://files.readme.io/5e9df9148e5059160401391ef857ad965d1154e1ee7516bc33804de6badc5cd9-4403341605265.png)](https://files.readme.io/5e9df9148e5059160401391ef857ad965d1154e1ee7516bc33804de6badc5cd9-4403341605265.png)<br />* If your Android app is available exclusively through a third-party store, [you must set its Google Play status to Published out of store when adding the app.](/docs/set-up-multi-store-android-attribution#dashboard-per-store%E2%80%94adding-the-app) Choosing any other status will prevent redirection to the third-party store and will result in an error message. |