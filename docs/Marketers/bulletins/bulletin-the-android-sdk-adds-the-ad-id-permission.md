---
title: "Bulletin: The Android SDK adds the AD_ID permission"
excerpt: "Starting with AppsFlyer Android SDK V6.8.0, the AD_ID permission is declared in the SDK's AndroidManifest.xml."
table_of_contents: false
x-zendesk:
  id: 7569900844689
  url: https://support.appsflyer.com/hc/en-us/articles/7569900844689-Bulletin-The-Android-SDK-adds-the-AD-ID-permission
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 46
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2022-07-12T08:57:45Z'
  edited_at: '2023-08-28T09:44:20Z'
---
| | |
| --- | --- |
| **Background** | In early 2022, Google announced a change to the behavior of Google Play Services and fetching of the Android Advertising ID.<br />According to the [announcement](https://support.google.com/googleplay/android-developer/answer/6048248?hl=en), apps targeting Android 13 (API 33) and above will have to declare a Google Play services normal permission in their manifest file in order to get access to the device’s Advertising ID.<br />The permission is granted to the app at install time and does not trigger any user interaction. |
| **What's changing** | Starting with AppsFlyer Android SDK V6.8.0, the AD_ID permission is declared in the SDK's AndroidManifest.xml. When the app is built, the SDK’s manifest merges with your app’s manifest by default, and the permission is added even if the app doesn’t explicitly declare the permission. If the permission exists in both the app and the SDK, this works just fine–there will be no collision. |
| **What you must know** | - If you are using SDK V6.8.0 and have the AD_ID permission in your app’s Manifest, you can optionally remove it from the manifest and let the SDK add it for you.<br />- If you are using SDK version **older** than V6.8.0, and your app is targeting Android 13 (API 33) and above, you should add the AD_ID permission to your app in order to allow the SDK to gain access to the Advertising ID.<br />- **Child-directed apps:** According to [Google’s Policy](https://support.google.com/googleplay/android-developer/answer/11043825?hl=en), apps that target children must not transmit the Advertising ID. If you're building an app for children and you are using SDK V6.8.0 and above, you must revoke the AD_ID permission. See developer instructions [here](https://dev.appsflyer.com/hc/docs/install-android-sdk#revoking-the-ad_id-permission). |