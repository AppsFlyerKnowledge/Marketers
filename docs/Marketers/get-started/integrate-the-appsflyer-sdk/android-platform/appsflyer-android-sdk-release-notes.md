---
title: AppsFlyer Android SDK release notes
metadata:
  keywords:
    - Advertisers
    - Release Notes
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2017-03-09T20:17:19Z'
  edited_at: '2026-09-09T15:39:15Z'
  id: 115001256006
  locale: en-us
  section: Android platform
  section_id: 6551190827921
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115001256006-AppsFlyer-Android-SDK-release-notes
---
**At a glance:** Check out the SDK release notes for a quick overview of the latest changes to the Android SDK. Developers looking for more comprehensive details should review [the Android Release Notes on the Dev Hub](https://dev.appsflyer.com/hc/docs/android-release-notes).

**Legacy SDK versions for iOS and Android will stop being supported on a fixed six-month cycle.** This cycle is designed to provide advanced notice, helping teams plan ahead and maintain full app functionality without disruption. Upgrading to the latest SDK ensures access to the newest features, improved stability, and ongoing support.

> 📘 **Important!**
>
> To ensure a smooth transition, app developers are encouraged to update to the latest SDK version before the End-of-Support date.

## End of support vs. Deprecated

AppsFlyer distinguishes between **Deprecated** and **End-of-Support** SDK versions to clarify the level of support and impact on data measurement.

* **Deprecated versions:** SDK versions that are no longer recommended due to known issues, such as critical bugs. These versions can still send data to AppsFlyer, but continued use is discouraged. and upgrading to a supported version is strongly advised.
* **End-of-Support versions:** SDK versions for which measurement is fully stopped across all platforms. For both Android and iOS, installs, sessions, and in-app events will not be measured. Any traffic from these versions (unless specifically excluded by the Product team) will receive a 400 status code, meaning the SDK will attempt to send API calls as usual, but AppsFlyer servers will reject them, and the data will not be processed.

## Android SDK Releases

The table below provides release notes for supported Android SDK versions, including release dates and key updates for developers. For developer information, see [Android SDK integration guide for developers](https://dev.appsflyer.com/hc/docs/android-sdk).

| Version | Release date | Notes |
| --- | --- | --- |
| 7.0.1 | 2026-07-22 | <ul><li>Apps can now provide a hashed customer email, phone number, name, and Facebook login ID to the SDK for sharing with ad network partners. The SDK doesn't collect this information itself. The app provides it, and only hashed values are sent, never plain text.</li><li>Removed the `setUserEmails` and `setPhoneNumber` methods. Developers using these must switch to `setUserEmail` and `setUserPhone`</li></ul> |
| 6.18.1 | 2026-05-25 | <ul><li>Fixed an issue in the Purchase Connector where purchase validations that failed due to connectivity problems were cached and not retried, which could result in missing purchase data.</li></ul> |
| 6.18.0 | 2026-03-17 | <ul><li>Stability improvements and fixes.</li></ul> |
| 6.17.6 | 2026-03-11 | <ul><li>Fixed an issue where the value of AF\_STORE set by the app was not being sent by the SDK.</li></ul> |
| 6.17.5 | 2025-11-26 | <ul><li>Stability improvements and fixes.</li><li>New purchase validation API (validate and log purchase) is now generally available.</li></ul> |
| 6.17.4 | 2025-10-15 | <ul><li>Updated the integration between the SDK and the Advanced Security Module. This version is compatible with Security Module v2.0.0 and above.</li><li>If you are using the Advanced Security Module and would like to update the SDK to v6.17.4 - you must update the Security Module to v2.0.0 as well.</li></ul> |
| 6.17.3 | 2025-08-18 | <ul><li>Technical update: Stability and performance improvements.</li></ul> |
| 6.17.2 | 2025-08-05 | <ul><li>Technical update: Updated to targetSDKVersion 35</li></ul> |
| 6.17.1 | 2025-07-28 | <ul><li>Updated the `validateAndLogInAppPurchase` API for in-app purchase validation API (currently in Beta)</li><li>Added integration with Google Play Integrity API  to enable device‑integrity verification through Google Play</li></ul> |
| 6.17.0 | 2025-04-24 | <ul><li>Added support for collecting AppSet ID. See [developer instructions](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).</li></ul> |
| 6.16.2 | 2025-03-02 | <ul><li>Fixed an issue that could cause build errors when integrating the SDK.</li></ul> |
| 6.16.1 | 2025-02-17 | <ul><li>Updated the API for manually sending DMA Consent data to AppsFlyer.</li></ul> |
| 6.16.0 | 2024-12-17 | <ul><li>Added support for Samsung preload attribution. [Learn more](/docs/set-up-appsflyer-preload-referrer-attribution#samsung-preload-referrer).</li><li>Added support for revenue measurement in the Privacy Sandbox attribution API (closed beta).</li><li>Updated Dexguard to v9.8.12 to resolve stability issues and enhance security.</li></ul> |
| 6.15.2 | 2024-10-10 | <ul><li>Stability improvements and fixes</li><li>Internal updates related to Privacy Sandbox Attribution API</li></ul> |
| 6.15.1 | 2024-08-28 | Versions upgrade:<ul><li>targetSDKVersion: v34</li><li>Gradle: v8.7</li><li>Java: v17</li></ul> |
| 6.15.0 | 2024-07-31 | <ul><li>Added the `logAdRevenue` method to send ad revenue data to AppsFlyer. **Note:** Starting with this version, the AdRevenue Connector should no longer be used; it must be replaced by the `logAdRevenue`method. [Learn more](https://dev.appsflyer.com/hc/docs/ad-revenue-1)</li></ul> |
| 6.14.2 | 2024-06-10 | <ul><li>Fixed an issue with fetching Meta Install Referrer on apps built with Unity.</li></ul> |
| 6.14.1 | 2024-05-29 | SDK maintenance |
| 6.14.0 | 2024-04-18 | <ul><li>Added support for the updated Purchase Validation flow. This feature is currently in closed beta. Learn more.</li><li>Updated Huawei Referrer integration. [Learn more](https://dev.appsflyer.com/hc/docs/install-android-sdk#huawei-install-referrer).</li></ul> |
| 6.13.1 | 2024-04-03 | SDK maintenance |
| 6.13.0 | 2024-02-08 | <ul><li>Added support for Google's new EU consent policy (DMA)</li></ul> |

## Unsupported SDK versions

The following SDK versions have reached **End-of-Support** status. These versions can no longer send data to AppsFlyer, and any traffic from them will be rejected.

| Version | Release Date | Notes |
| --- | --- | --- |
| 6.12.6 | 2024-01-29 | SDK maintenance |
| 6.12.5 | 2023-12-18 | <ul><li>Added the `original_link` parameter to the deep linking callback in the ESP resolution flow.</li></ul> |
| 6.12.4 | 2023-10-25 | <ul><li>Dexguard updated to version 9.4.16 to improve SDK stability.</li></ul> |
| 6.12.3 | 2023-08-31 | SDK maintenance |
| 6.12.2 | 2023-08-02 | <ul><li>Fixed a bug that could cause the app to crash on some devices in Android 8.1.0 and Android 11.</li></ul> |
| 6.12.1 | 2023-06-29 | <ul><li>Fixed an issue where the Play Store launch was delayed in cross promotion.</li><li>Fixed a bug causing the app to crash on some devices.</li></ul> |
| 6.12.0 | 2023-06-28 | <ul><li>Deprecated - please use version 6.12.1.</li></ul> |
| 6.11.2 | 2023-06-29 | <ul><li>Fixed a bug causing the app to crash on some devices.</li></ul> |
| 6.11.1 | 2023-06-6 | <ul><li>Deprecated - please use version 6.12.1.</li><li>Fixed a bug where the app sometimes crashed after initializing the SDK.</li></ul> |
| 6.11.0 | 2023-05-16 | <ul><li>Fixed an issue that sometimes caused the app to freeze on some devices when the SDK attempted to obtain the Google Play Referrer</li></ul> |
| 6.10.3 | 2023-04-25 | SDK maintenance |
| 6.10.2 (Deprecated) |  | Deprecated |
| 6.10.1 | 2023-03-01 | <ul><li>Fixed an issue that sometimes caused apps on Samsung devices to close when initializing the SDK. This issue affected apps with SDK V6.6.0 and above.</li></ul> |
| 6.10.0 | 2023-02-13 | <ul><li>New AppsFlyer domain for communication between the SDK and AppsFlyer servers.</li><li>Changed setHost API when empty or null values are sent. [Learn more](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#sethost)</li></ul> |
| 6.9.4  <br />End of support:  <br />2025-09-08 | 2022-12-6 | <ul><li>Fixed an issue where sending an ad revenue event from the ad revenue SDK connector triggered a call to the conversion listener.</li><li>Fixed an issue that sometimes caused apps to freeze when an ad revenue event was sent from the ad revenue SDK connector.</li></ul> |
| 6.9.3  <br />End of support:  <br />2025-09-08 | 2022-11-28 | <ul><li>Updated the internal request structure for Get Conversion Data (GCD). **Note**: Response data remains the same.</li><li>Fixed an issue where the SDK triggered a GCD request when the app had the ConversionListener set to null.</li></ul> |
| 6.9.2  <br />End of support:  <br />2025-09-08 | 2022-10-02 | <ul><li>Fixed an issue related to a delay in requesting a purchase validation using the validateAndLogInAppPurchase API.</li></ul> |
| 6.9.1  <br />End of support:  <br />2025-09-08 | 2022-09-19 | SDK maintenance |
| 6.9.0  <br />End of support:  <br />2025-09-08 | 2022-09-12 | <ul><li>Added support for Xiaomi GetApps Store Referrer.</li><li>Updated the internal API for ad revenue reporting. Starting this version, only the [generic ad revenue SDK connector](https://dev.appsflyer.com/hc/docs/ad-revenue-1) is supported.</li></ul> |
| 6.8.2  <br />End of support:  <br />2025-09-08 | 2022-08-29 | <ul><li>Fixed a critical issue with the caching mechanism of the SDK introduced in V6.7.0, causing cached events to be sent multiple times.</li></ul> |
| 6.8.1  <br />(Deprecated)  <br />End of support:  <br />2025-09-08 | 2022-08-24 | <ul><li>**Deprecated.** Please use V6.8.2.</li></ul> |
| 6.8.0  <br />(Deprecated)  <br />End of support:  <br />2025-09-08 | 2022-07-18 | <ul><li>**Deprecated.** Please use V6.8.2.</li><li>Removed the [`enableLocationCollection`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#enablelocationcollection) API from the SDK. The app can still report the user’s location data by passing it to the SDK directly via the [`logLocation`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#loglocation) API.</li><li>Added the `com.google.android.gms.permission.AD_ID` permission to the SDK's `AndroidManifest.xml`. Read more about it [here](/docs/bulletin-the-android-sdk-adds-the-ad-id-permission).</li><li>Fixed an issue related to optimization and obfuscation using R8.</li></ul> |
| 6.7.0  <br />(Deprecated)  <br />End of support:  <br />2025-09-08 | 2022-06-19 | <ul><li>**Deprecated.** Please use V6.8.2.</li><li>Changed how the SDK handles requests to the AppsFlyer servers. Following this change, the request for reporting the first app open (conversion) will be prioritized over in-app events and other types of requests. Read more about it [here](/docs/bulletin-adding-a-priority-queue-to-the-android-sdk).</li><li>**New API:** [`setDisableNetworkData`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisablenetworkdata) to opt-out from collecting the information about the cellular network (carrier name, operator name).</li></ul> |
| 6.6.1  <br />End of support:  <br />2025-03-03 | 2022-05-16 | SDK maintenance |
| 6.6.0  <br />End of support:  <br />2025-03-03 | 2022-05-01 | <ul><li>Added more parameters to UDL's `onDeepLinking` callback for Direct Deep Linking flow (existing users). [For more information](/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users).</li></ul> |
| 6.5.4  <br />End of support:  <br />2025-03-03 | 2022-03-23 | SDK maintenance |
| 6.5.3  <br />End of support:  <br />2025-03-03 | 2022-03-09 | <ul><li>**Bugfix:** Fixed issue with the creation of user-invite links that contain non-English characters.</li></ul> |
| 6.5.2  <br />End of support:  <br />2025-03-03 | 2022-01-26 | <ul><li>Fixed issue when resolving URL for deferred deep linking in UDL.</li><li>Updated to DexGuard 9.2</li><li>Refactoring and internal changes.</li></ul> |
| 6.5.1  <br />End of support:  <br />2025-03-03 | 2021-12-29 | <ul><li>Deeplink resolution with UDL for apps that use the [out-of-Store with Channel option](/docs/set-up-multi-store-android-attribution#channel-name)</li></ul> |
| 6.5.0  <br />End of support:  <br />2025-03-03 | 2021-12-07 | <ul><li>Refactoring and internal changes.</li></ul> |
| 6.4.3  <br />End of support:  <br />2025-03-03 | 2021-11-14 | <ul><li>Fixed a bug introduced in  `V6.4.2`with `LinkGenerator` causing the creation of links with missing URL parameters.</li></ul> |
| 6.4.2  <br />End of support:  <br />2025-03-03 | 2021-10-24 | The following were resolved:<ul><li>`pid` parameter being appended twice to custom URLs generated by `LinkGenerator`.</li><li>Extra `/` was added to the `af_dp` value when using `LinkGenerator` to create custom URI schemes.</li><li>Both IMEI and AndroidID were collected, if the app triggered the collection of only one of them.</li></ul> |
| 6.4.1  <br />End of support:  <br />2025-03-03 | 2021-10-17 | Resolved compilation error when using Gradle version earlier than V3.5.4. |
| 6.4.0  <br />End of support:  <br />2025-03-03 | 2021-09-12 | **New API:** [`setSharingFilterForPartners`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners) lets you configure which partners the SDK should exclude from data-sharing.<br /><br />As of this version, [`setSharingFilter`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilter) and [`setSharingFilterForAllPartners`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforallpartners) are deprecated. |
| 6.3.2<br /><br />End of support: 2024-08-31 | 2021-06-06 | **New API**: [`setDisableAdvertisingIdentifiers`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers) |
| 6.3.1  <br />End of support: 2024-08-31 | 2021-05-26 | <ul><li>**New API**: [`performOnDeepLinking`](https://dev.appsflyer.com/hc/docs/conversion-data)</li><li>Added the ability to trigger the [User Invite API](/docs/user-invite-attribution#procedures) before calling `start`/after calling `stop`</li><li>**Bugfix**: Fixed an issue where a call to `waitForCustomerUserId` wasn't released even after calling `setCustomerUserId`</li></ul> |
| 6.3.0  <br />End of support: 2024-08-31 | 2021-04-29 | <ul><li>**Bugfix**: Wrong invocation of `onConversionDataFail` upon in-app event send request failure</li><li>**Bugfix**: motion sensor metric collection (for fraud detection)</li><li>**Bugfix**: Obfuscation-related fix to [UDL](https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl)</li><li>Technical update to the OneLink API</li></ul> |
| 6.2.3  <br />End of support: 2024-08-31 | 2021-03-04 | SDK maintenance |
| 6.2.0  <br />End of support: 2024-08-31 | 2021-02-07 | <ul><li>**New API**: [`setPartnerData`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setpartnerdata)</li></ul> |
| 6.1.4  <br />End of support: 2024-08-31 | 2021-01-12 | <ul><li>Added support for DexGuard V9</li></ul> |
| 6.1.3  <br />End of support: 2024-08-31 | 2020-12-24 | <ul><li>**New API**: [`addPushNotificationDeepLinkPath`](/docs/additional-sdk-integration-guide#record-push-notifications) (supports Movable Ink)</li></ul> |
| 6.1.1  <br />End of support: 2024-08-31 | 2020-12-03 | <ul><li>Added support Samsung Galaxy Store referrer</li><li>Minor bug fixes and performance improvements.</li></ul> |
| 6.1.0  <br />End of support: 2024-08-31 | 2020-11-09 | <ul><li>Added support for [Unified deep linking API](https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl)</li></ul> |
| 6.0.1  <br />End of support: 2024-08-31 | 2020-10-28 | SDK maintenance |
| 6.0.0  <br />End of support: 2024-08-31 | 2020-10-14 | <ul><li>Major changes to SDK functionality and API including deprecation and method name changes. [Learn more](/docs/appsflyer-android-sdk-release-notes#android-v600-release-notes)</li></ul> |

> 📘 **See also**
>
> * [AppsFlyer SDK version control policy](/docs/appsflyer-sdk-version-control-policy)

<div data-zendesk-anchors="h_01JVHFG6PN34YFWNZKX2CYHJV8=important h_01JVHEKR4MTFV0FDHMTQW00BCS=end-of-support-vs-deprecated android-sdk-v6=android-sdk-releases h_01H9ZPCP8RWF24WAZ6YYMA1GS0=android-sdk-releases deprecated-versions=unsupported-sdk-versions 01JHFAXXV51DHADQ7P2Q6RHFX0=unsupported-sdk-versions h_01HDNZ774ME3SVT89JS7R4MSKE=see-also" />
