---
title: "AppsFlyer iOS SDK release notes"
x-zendesk:
  id: 115001224823
  url: https://support.appsflyer.com/hc/en-us/articles/115001224823-AppsFlyer-iOS-SDK-release-notes
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: iOS platform
  section_id: 6551263106577
  position: 1
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [Advertisers, Release Notes, Developers, Marketers, Loc Published]
  promoted: false
  comments_disabled: false
  created_at: '2017-03-09T19:49:54Z'
  edited_at: '2026-09-09T15:41:07Z'
---
**At a glance:** The SDK release notes provide a quick overview of the latest changes to the iOS SDK. Developers looking for more comprehensive details should review [the iOS Release Notes on the Dev Hub](https://dev.appsflyer.com/hc/docs/ios-release-notes).

**Legacy SDK versions for iOS and Android will stop being supported on a fixed six-month cycle.** This cycle is designed to provide advanced notice, helping teams plan ahead and maintain full app functionality without disruption. Upgrading to the latest SDK ensures access to the newest features, improved stability, and ongoing support.

> 📘 **Important!**
>
> To ensure a smooth transition, app developers are encouraged to update to the latest SDK version before the End-of-Support date.

## End of support vs. Deprecated

AppsFlyer distinguishes between **Deprecated** and **End-of-Support** SDK versions to clarify the level of support and impact on data measurement.

* **Deprecated versions:** SDK versions that are no longer recommended due to known issues, such as critical bugs. These versions can still send data to AppsFlyer, but continued use is discouraged. and upgrading to a supported version is strongly advised.
* **End-of-Support versions:** SDK versions for which measurement is fully stopped across all platforms. For both Android and iOS, installs, sessions, and in-app events will not be measured. Any traffic from these versions (unless specifically excluded by AppsFlyer) will receive a 400 status code, meaning the SDK will attempt to send API calls as usual, but AppsFlyer servers will reject them, and the data will not be processed.

## iOS SDK Release Notes

The table below provides release notes for supported iOS SDK versions, including release dates and key updates for developers. For developer information, see [iOS SDK integration guides for developers](https://dev.appsflyer.com/hc/docs/ios-sdk).

| Version | Release date | Notes |
| --- | --- | --- |
| 7.0.1 | 2026-07-22 | * Apps can now provide a hashed customer email, phone number, name, and Facebook login ID to the SDK for sharing with ad network partners. The SDK doesn't collect this information itself. The app provides it, and only hashed values are sent, never plain text.<br />* Removed the `setUserEmails` and `setPhoneNumber` methods. Developers using these must switch to `setUserEmail` and `setUserPhone` |
| 6.18.1 | 2026-05-25 | <ul><li>Fixed an issue where purchase validation requests from the Purchase Connector that failed due to a network error were permanently lost after the app restarted.</li></ul> |
| 6.18.0 | 2026-04-21 | <ul><li>Added support for fetching AppTransaction - a representation of an app's download, cryptographically signed by the app store.</li><li>Bug fixes and improvements</li></ul> |
| 6.17.9 | 2026-03-10 | <ul><li>Fixed an issue where the SDK could get stuck while attempting to fetch ODM data, preventing requests from being sent to the server.</li><li>Fixed an issue where Customer User ID set by the app would not be sent in the install event.</li></ul> |
| 6.17.8 | 2025-12-03 | <ul><li>New purchase validation API (validate and log purchase) is now generally available.</li></ul> |
| 6.17.7 | 2025-10-15 | <ul><li>Fixed an issue with fetching data from Google's ICM library</li></ul> |
| 6.17.6 | 2025-09-21 | <ul><li>Fixed an issue introduced in v6.17.3 that could cause a crash when the SDK attempts to send ICM data to AppsFlyer.</li></ul> |
| 6.17.5  <br />Deprecated | 2025-09-03 | <ul><li>**This version is deprecated and should not be used.**</li></ul> |
| 6.17.4  <br />Deprecated | 2025-08-27 | <ul><li>**This version is deprecated and should not be used.**</li><li>Fixed an issue where in rare cases the app would crash when the SDK is initialized.</li></ul> |
| 6.17.3  <br />Deprecated | 2025-08-21 | <ul><li>**This version is deprecated and should not be used.**</li><li>Updated logic for fetching data from Google's ICM library to improve accuracy.</li></ul> |
| 6.17.2 | 2025-07-15 | * Updated the`validateAndLogInAppPurchase` API (beta)<br />* Improved handling of Apple Search Ads (ASA) tokens for apps that collect ATT (AppTrackingTransparency) consent. |
| 6.17.1 | 2025-06-24 | <ul><li>Added support for [Google Integrated Conversion](https://support.google.com/google-ads/answer/16203286) (ICM) measurement.</li><li>Fixed an issue causing an App Store login popup to appear when running the SDK in a development environment.</li></ul> |
| 6.17.0 | 2025-04-23 | <ul><li>Stability and performance improvements</li></ul> |
| 6.16.2 | 2025-03-10 | <ul><li>Technical update required to release this version into plugins</li></ul> |
| 6.16.1 | 2025-02-18 | <ul><li>Updated the API for manually sending DMA Consent data to AppsFlyer.</li></ul> |
| 6.16.0 | 2025-01-19 | <ul><li>Added support for Apple’s StoreKit 2 APIs for Subscription and In-App Purchase reporting through the Purchase Connector. This feature is currently in closed beta.</li></ul> |
| 6.15.3 | 2024-09-23 | SDK Maintenance |
| 6.15.2 | 2024-08-28 | <ul><li>Fixed an issue with event transmission in the Purchase Connector. This fix does not affect any production versions of the Purchase Connector and is related to its update to version 6.15.x.</li></ul> |
| 6.15.1 | 2024-08-19 | <ul><li>Fixed an issue with Reinstall Detection that occurred when two or more apps from the same vendor were installed on the device.</li></ul> |
| 6.15.0 | 2024-08-06 | * Added the `logAdRevenue` API to send ad revenue data to AppsFlyer. **Note:** Starting with this version, the AdRevenue Connector should no longer be used; it must be replaced by the `logAdRevenue`method. For more details, see [here](https://dev.appsflyer.com/hc/docs/ad-revenue-2).<br />* Made internal updates related to the Purchase Connector. Apps that use the Purchase Connector and update to this SDK release must also update their Purchase Connector to v6.15.0. |
| 6.14.6 | 2024-07-24 | * Fixed an issue where the SDK was making redundant calls to the `getConversionData` API (GCD) when starting a new session; this does not impact measurement. |
| 6.14.5 | 2024-07-03 | <ul><li>Fixed an issue where the SDK would send the manual consent data that had been set by the app, even if the code for sending the manual consent had been removed.</li></ul> |
| 6.14.4 | 2024-06-10 | <ul><li>Updated Privacy Manifest for the [Strict-Mode  SDK](https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk).</li></ul> |
| 6.14.3 | 2024-04-26 | <ul><li>Fixed automated merging of the Privacy Manifest for apps utilizing Cocoapods.</li></ul> |
| 6.14.2 | 2024-04-19 | SDK Maintenance |
| 6.14.1 | 2024-04-18 | <ul><li>Added support for the updated Purchase Validation flow. This feature is currently in closed beta. Learn more.</li></ul> |
| 6.14.0 | 2024-04-07 | <ul><li>Added Privacy Manifest support. [Learn more about the Privacy Manifest in AppsFlyer](/docs/implement-privacy-manifest-in-your-app).</li><li>Added an XCFramework signature to the SDK, allowing developers using Xcode 15 to validate the SDK’s origin and authenticity.</li></ul> |
| 6.13.2 | 2024-03-26 | <ul><li>Fixed an issue that was causing the release of apps using SPM in Xcode 15.3 to fail. See the [developer release notes](https://dev.appsflyer.com/hc/docs/ios-release-notes#version-6132) for more information.</li></ul> |
| 6.13.1 | 2024-03-05 | <ul><li>Fixed an issue with sending consent data for non-GDPR users in a CMP consent flow (DMA).</li></ul> |
| 6.13.0   <br />Deprecated | 2024-02-08 | <ul><li>Added support for Google's new EU consent policy</li></ul> |

## Unsupported SDK Versions

The following SDK versions have reached **End-of-Support** status. These versions can no longer send data to AppsFlyer, and any traffic from them will be rejected.

| Version | Release date | Notes |
| --- | --- | --- |
| 6.12.3 | 2024-01-04 | * A new `original_link` parameter has been added to the Deep Linking callback within the Email Service Provider (ESP) resolving flow.<br />* All references to the iAd Framework have been removed. |
| 6.12.2 | 2023-08-24 | SDK Maintenance |
| 6.12.1 | 2023-07-20 | <ul><li>Fixed an issue in SKAdNetwork 4.0 causing the Coarse conversion value to be reported as "None"</li><li>Fixed a crash in the tvOS implementation</li></ul> |
| 6.12.0 | 2023-06-28 | Removed bitcode support from the SDK |
| 6.11.2 | 2023-06-13 | Fixed an issue introduced in v6.11.0, wherby calling  `validateAndLogInAppPurchase`  (the legacy API for Purchase Validation and logging) does not log the purchase event.   <br />  <br />**Important:** If you are using `v6.11.0`or `v6.11.1`, and the `validateAndLogInAppPurchase` API please upgrade to this version. |
| 6.11.1 | 2023-05-24 | SDK Maintenance |
| 6.11.0 | 2023-04-25 | <ul><li>A new AppsFlyer domain name in the URL used by the SDK to send requests to AppsFlyer servers.</li><li>Changed behaviour of the setHost API when empty or null values are sent. [Learn more](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#sethost)</li></ul> |
| 6.10.1 | 2023-04-02 | Added the `link` parameter to the UDL payload of Direct Deep Linkinig scenarios |
| 6.10.0 | 2023-02-15 | SKAdNetwork 4.0 support. [Learn more about the AppsFlyer SKAdNetwork solution](/docs/skadnetwork-skan-solution-guide) |
| 6.9.2  <br />End of support:  <br />2025-09-08 | 2023-01-31 | Updated the internal request structure for Get Conversion Data (GCD). **Note**: Response data remains the same. |
| 6.9.1  <br />End of support:  <br />2025-09-08 | 2022-11-28 | Updated the internal request structure for Get Conversion Data (GCD). **Note**: Response data remains the same. |
| 6.9.0  <br />End of support:  <br />2025-09-08 | 2022-11-06 | Updated the internal API for AdRevenue reporting. Starting this version, only the [Generic Connector for AdRevenue](https://dev.appsflyer.com/hc/docs/ad-revenue-2) is supported.<br /><br />This version of the SDK is compatible with AdRevenue Connector `V6.9.0`. |
| 6.8.1  <br />End of support:  <br />2025-09-08 | 2022-08-09 | **Reinstall Detection**: Improved the ability to detect and report re-installations of the app using on-device storage. This capability can be controlled in the AppsFlyer dashboard from the [Apps Setting page](/docs/app-settings). |
| 6.8.0  <br />End of support:  <br />2025-03-03 | 2022-07-19 | For Reinstall Detection, please use SDK V6.8.1+ |
| 6.7.0  <br />End of support:  <br />2025-03-03 | 2022-06-19 | Update the implementation for SKAdNetwork to use the updated Apple API `updatePostbackConversionValue`, introduced in iOS 15.4.<br /><br />This has no effect on the data sent from SKAdNetwork, and does not require any change to the app code. |
| 6.6.1  <br />End of support:  <br />2025-03-03 | 2022-05-16 | SDK Maintenance |
| 6.6.0  <br />End of support:  <br />2025-03-03 | 2022-05-01 | Added more parameters to UDL's `didResolveDeepLink` callback for Direct Deep Linking flow (existing users). [For more information](/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users). |
| 6.5.4  <br />End of support:  <br />2025-03-03 | 2022-03-23 | SDK Maintenance |
| 6.5.3  <br />End of support:  <br />2025-03-03 | 2022-03-02 | **Bugfix:** Fixed an issue with a double invocation of `didResolveDeepLink` on links based on URI scheme. |
| 6.5.2  <br />End of support:  <br />2025-03-03 | 2022-01-26 | SDK Maintenance |
| 6.5.1  <br />End of support:  <br />2025-03-03 | 2022-01-03 | SDK Maintenance |
| 6.5.0  <br />End of support:  <br />2025-03-03 | 2021-12-22 | Refactoring and internal changes. |
| 6.4.4  <br />End of support:  <br />2025-03-03 | 2021-12-12 | SDK Maintenance |
| 6.4.3  <br />End of support:  <br />2025-03-03 | 2021-11-30 | Stability fix for MacOS 10.14.6 with xcframework. |
| 6.4.2  <br />End of support:  <br />2025-03-03 | 2021-10-28 | SDK Maintenance |
| 6.4.1  <br />End of support:  <br />2025-03-03 | 2021-10-24 | Resolved stability in Unity apps. |
| 6.4.0  <br />End of support:  <br />2025-03-03 | 2021-09-12 | **Added API:** [`setSharingFilterForPartners`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners) lets you configure which partners the SDK should exclude from data-sharing.<br /><br />As of this version, `setSharingFilter` and [`setSharingFilterForAllPartners`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforallpartners) are deprecated. |
| 6.3.5  <br />End of support: 2024-08-31 | 2021-08-19 | **Added API**: [`setCurrentDeviceLanguage`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setcurrentdevicelanguage)<br /><br />Starting this version the language is no longer collected automatically by the SDK. |
| 6.3.4  <br />End of support: 2024-08-31 | 2021-07-21 | <ul><li>**Bugfix:** Fixed issue with running the SDK on XCode 12.5 Simulators</li><li>Minor fixes and updates.</li></ul> |
| 6.3.2  <br />End of support: 2024-08-31 | 2021-06-17 | Improved debug logs. |
| 6.3.1  <br />End of support: 2024-08-31 | 2021-06-02 | SDK Maintenance |
| 6.3.0  <br />End of support: 2024-08-31 | 2021-05-13 | * Apple Silicon support: Added support to run the SDK on a simulator using Mac machines with the M1 chipset<br />* Starting this version, the SDK supports iOS `9`+. iOS `8` is no longer supported.<br />* iOS Strict Mode SDK: Added support for Carthage dependency manager<br />* Technical update for the OneLink API |
| 6.2.6  <br />End of support: 2024-08-31 | 2021-04-25 | * Bugfix: SKAdNetwork rules didn't load when SDK initialization occurred after `didFinishLaunchingWithOptions`<br />* Bugfix: `waitForATTUserAuthorization` edge-case causing the launch event to be sent without IDFA, even if user consent is given<br />* Allow the SDK to run on iOS 8 devices<br />* Cleanup and removal of unused code and data |
| 6.2.5  <br />End of support: 2024-08-31 | 2021-04-06 | Refactoring, cleanup, removal of unused data from the SDK.<br /><br />Starting this version:<br /><br />* The `setShouldCollectDeviceName` method is deprecated and will not return the device name<br />* The `wifi` parameter sent from the SDK is set to `False` |
| 6.2.4  <br />End of support: 2024-08-31 | 2021-03-15 | Bugfix related to SKAdNetwork revenue measurement mode and in-app events that contain `AF_REVENUE`  parameter.<br /><br />Starting this version, in the case of revenue measurement: any event containing `AF_REVENUE` affects the conversion value. Prior to this change, the conversion value was set only if it was in the framework of the`AF_PURCHASE` event.<br /><br />**Note:** If you implement SKAdNetwork Revenue measurement, you must upgrade to this version. |
| 6.2.3  <br />End of support: 2024-08-31 | 2021-03-07 | Bugfix related to calling SKAdNetwork's `updateConversionValue`. |
| 6.2.2  <br />End of support: 2024-08-31 | 2021-02-18 | SDK Maintenance |
| 6.2.1  <br />End of support: 2024-08-31 | 2021-02-15 | Support [Event reporting by S2S](/docs/server-to-server-events-api-for-mobile-s2s-mobile) |
| 6.2.0  <br />End of support: 2024-08-31 | 2021-02-07 | Additional API: [setPartnerData](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setpartnerdata) |
| 6.1.4  <br />End of support: 2024-08-31 | 2021-01-12 | SDK Maintenance |
| 6.1.3  <br />End of support: 2024-08-31 | 2020-12-24 | * Additional API: [`addPushNotificationDeepLinkPath`](/docs/additional-sdk-integration-guide#record-push-notifications) (supports Movable Ink)<br />* Support [Apple AdServices Framework](https://developer.apple.com/documentation/adservices) |
| 6.1.2  <br />End of support: 2024-08-31 | 2020-12-03 | SDK Maintenance |
| 6.1.1  <br />End of support: 2024-08-31 | 2020-11-17 | Introduce [Strict mode SDK](https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk) |
| 6.1.0  <br />End of support: 2024-08-31 | 2020-11-09 | Support [Unified deep linking API](https://dev.appsflyer.com/docs/ios-unified-deep-linking) |
| 6.0.8  <br />End of support: 2024-08-31 | 2020-10-28 | Support [Apple App Clips](/docs/apple-app-clips-integration-guide) attribution |
| 6.0.7  <br />End of support: 2024-08-31 | 2020-10-21 | SDK Maintenance |
| 6.0.6  <br />End of support: 2024-08-31 | 2020-10-20 | SDK Maintenance |
| 6.0.5  <br />End of support: 2024-08-31 | 2020-10-08 | SDK Maintenance |
| 6.0.4  <br />End of support: 2024-08-31 | 2020-09-30 | Supports multiple redirects from ESPs |
| 6.0.3  <br />End of support: 2024-08-31 | 2020-09-06 | <ul><li>API name change:<br />waitForAdvertisingIdentifier --> waitForATTUserAuthorization</li><li>SDK collects IDFA by default for iOS 14 (as for earlier iOS versions)</li></ul> |
| 6.0.2   <br />End of support: 2024-08-31 | 2020-08-27 | <ul><li>API name change:<br />deviceLoggingDisabled --> anonymizeUser</li><li>AppTrackingTransparency (ATT) dialog is required to collect IDFA for iOS 14</li><li>Added support for IDFV cross-promotion attribution</li></ul> |
| 6.0.1 beta  <br />End of support: 2024-08-31 | 2020-08-06 | <ul><li>Support added for [SKAdNetwork attribution](/docs/skadnetwork-skan-solution-guide), to help advertisers measure campaign success while maintaining user privacy</li></ul> |
| 6.0.0 beta  <br />End of support: 2024-08-31 | 2020-08-04 | <ul><li>Extended debugging capabilities</li><li>Major changes to SDK functionality and API. [Learn more](/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes)</li></ul> |

> 📘 **See also**
>
> * [Quickstart guide to iOS 14, ATT, and SKAdNetwork](/docs/about-att-and-skan)