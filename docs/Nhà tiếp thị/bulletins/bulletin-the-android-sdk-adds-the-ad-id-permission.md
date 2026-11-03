---
title: 'Bulletin: The Android SDK adds the AD_ID permission'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-07-12T08:57:45Z'
  edited_at: '2023-08-28T09:44:20Z'
  id: 7569900844689
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/7569900844689-Bulletin-The-Android-SDK-adds-the-AD-ID-permission
---
> **At a glance:** Starting with AppsFlyer Android SDK V6.8.0, the AD\_ID permission is declared in the SDK's AndroidManifest.xml.

| **Background** | In early 2022, Google announced a change to the behavior of Google Play Services and fetching of the Android Advertising ID.<br /><br />According to the <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6048248?hl=en">announcement</Anchor>, apps targeting Android 13 (API 33) and above will have to declare a Google Play services normal permission in their manifest file in order to get access to the device’s Advertising ID.<br /><br />The permission is granted to the app at install time and does not trigger any user interaction. |
| --- | --- |
| **What's changing** | Starting with AppsFlyer Android SDK V6.8.0, the AD\_ID permission is declared in the SDK's AndroidManifest.xml. When the app is built, the SDK’s manifest merges with your app’s manifest by default, and the permission is added even if the app doesn’t explicitly declare the permission. If the permission exists in both the app and the SDK, this works just fine–there will be no collision. |
| **What you must know** | <ul><li>If you are using SDK V6.8.0 and have the AD\_ID permission in your app’s Manifest, you can optionally remove it from the manifest and let the SDK add it for you.</li><li>If you are using SDK version **older** than V6.8.0, and your app is targeting Android 13 (API 33) and above, you should add the AD\_ID permission to your app in order to allow the SDK to gain access to the Advertising ID.</li><li>**Child-directed apps:** According to <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/11043825?hl=en">Google’s Policy</Anchor>, apps that target children must not transmit the Advertising ID. If you're building an app for children and you are using SDK V6.8.0 and above, you must revoke the AD\_ID permission. See developer instructions <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#revoking-the-ad_id-permission">here</Anchor>.</li></ul> |