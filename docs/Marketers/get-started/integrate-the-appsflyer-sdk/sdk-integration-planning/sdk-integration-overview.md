---
title: "SDK integration overview"
excerpt: "Learn about the AppsFlyer SDK functionalities that are available and determine which APIs you want your Android or iOS app to use."
---
Learn about the AppsFlyer SDK functionalities that are available and determine which APIs you want your Android or iOS app to use.

## About the SDK

Watch this video to get the big picture of SDK integration.

![](https://fast.wistia.com/embed/medias/4iybquc6q3/swatch)

The SDK provides app installation and event recording functionality. You can record installs, sessions, and in-app events. In-app events include, for example, in-app purchases or leveling up in a game. Recording these events can help you evaluate ROI and user quality.

This article describes the process for the SDK V6+ integration and helps advertisers (app owners) and product managers plan the AppsFlyer SDK integration with their Android or iOS app.

Additional documentation includes the following:
<Accordion title="Android native">

``
```[`SDK installation documentation for developers](https://dev.appsflyer.com/hc/docs/install-android-sdk)
```[`Release notes](/docs/appsflyer-android-sdk-release-notes)
``
`[`SDK reference documentation for developers](https://dev.appsflyer.com/hc/docs/android-sdk-reference) 
```[`Data safety section on Google Play](/docs/fill-out-google-safety-section-form)

</Accordion>
<Accordion title="iOS native">

``
``
`[`Updating to iOS SDK V6](/docs/updating-to-ios-sdk-v6-and-plugins). Note that iOS SDK V5.4.4 is fully operational with iOS 14. However, we recommend adopting SDK V6.X to ensure compatibility with future iOS releases. 
```[`SDK installation documentation for developers](https://dev.appsflyer.com/hc/docs/install-ios-sdk)
```[`Release notes](/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes)
```[`SDK reference documentation for developers ](https://dev.appsflyer.com/hc/docs/ios-sdk-reference)
```[`Preparing for the App Store review, nutrition labels](/docs/preparing-for-the-app-store-review-nutrition-labels)

</Accordion>
<Accordion title="Unity">

``
```[`SDK installation documentation for developers](https://dev.appsflyer.com/hc/docs/installation)
```[`SDK reference documentation for developers ](https://dev.appsflyer.com/hc/docs/api)

</Accordion>
<Accordion title="React Native">

``
```[`SDK installation documentation for developers](https://dev.appsflyer.com/hc/docs/installation)
```[`SDK reference documentation for developers ](https://dev.appsflyer.com/hc/docs/rn_api)

</Accordion>

## SDK compatibility

The AppsFlyer SDK is compatible with the following platforms:
<Accordion title="Android">

``
``Starting Android V4.0
``Non-mobile Android-based platforms, such as Smart TVs (including Amazon Fire TV). `[`See CTV overview](/docs/ctv-pc-and-console-platform-attribution-concepts)

``
`[`Out-of-store markets](/docs/set-up-multi-store-android-attribution) for Android apps, such as Amazon and Baidu

</Accordion>
<Accordion title="iOS">

``

``iOS 9+ (iPhone, iPod, iPad)
``tvOS 9+ (Apple TV)
``Complies with Apple`[` IPv6 DNS64/NAT64](https://developer.apple.com/library/content/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/UnderstandingandPreparingfortheIPv6Transition/UnderstandingandPreparingfortheIPv6Transition.html#//apple_ref/doc/uid/TP40010220-CH213-SW1) networks

The SDK supports `[`multiple attribution methods](/docs/appsflyer-attribution-model). The attribution methods that are used depend on the following:

``The iOS version installed on the user's device
``The iOS SDK version installed in the app

``

| Attribution methods supported | iOS version | iOS SDK support | Notes |
| --- | --- | --- | --- |
| Probabilistic modeling | 8 – 14.4 | 5.0.0+ |  |
| 14.5+ | 6.0.3+ | Probabilistic modeling is limited to the context of owned media, cross-promotion, and consented web-to-app flows. |
| ID matching | 8 - 13 | 5.0.0+ | Users can opt out using Limit Ad Tracking (LAT). |
| 14.5+ | 6.0.3+ | App Tracking Transparency (ATT) and user consent is required. For more information, see [configure the iOS SDK to support ATT](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support). |
| [SKAdNetwork](/docs/skadnetwork-skan-solution-guide) | 11.3 - 13 | 6.2.3 | The SKAdNetwork (SKAN) solution is limited to install attribution in accordance with the [SKAN](https://developer.apple.com/documentation/storekit/skadnetwork) specification, meaning there is no conversion value. |
| 14+ | * SKAN is always available at the iOS and SDK levels irrespective of the ATT setting. * The marketer enables SKAN in the AppsFlyer dashboard. |

Starting from SDK V6.0.8, `[`Apple App Clips attribution](/docs/apple-app-clips-integration-guide) is available. You can also read our `[`blog post](https://www.appsflyer.com/resources/others/apple-app-clips) about Apple App Clips. 

</Accordion>

## SDK integration

The process of installing and integrating the SDK requires the product manager and mobile developer to work together. **Before** integrating the SDK with your app, review all of the integration tasks and consider the functionalities that you want your app to use.

### SDK planning checklist

To get you started, we've prepared a [downloadable checklist](https://docs.google.com/spreadsheets/d/e/2PACX-1vTD4OimHC93iw2AJCcAY45yAc9lOBfJe8PskI_0NFZTnWnrIq1hjPBvCztkbom9acMDDd4d1d5mMFfi/pub?output=xlsx) to help guide you through the planning process. For each task, there are links to the marketer and developer documentation.

### SDK integration tasks

The basic SDK integration includes the following tasks. Time estimates are intended as general guidance only.

| Basic SDK integration tasks | Planning time |
| --- | --- |
| Retrieve the [AppsFlyer dev key](/docs/basic-sdk-integration-guide#retrieving-the-dev-key) and send the link along with installation and integration instructions to your developer. | 15 mins |
| Review the [attribution considerations](/docs/basic-sdk-integration-guide#attribution), and determine which device identifiers to collect. | 30 mins |
| Determine the [in-app events](/docs/basic-sdk-integration-guide#recording-inapp-events) that you want to measure, and send the event names and event parameters to the developer. | 1 hour |
| Determine the[deep linking methods](/docs/basic-sdk-integration-guide#deep-linking-with-onelink) to use. | 30 mins |
| Determine the methods for [accessing attribution data](/docs/basic-sdk-integration-guide#accessing-attribution-and-deep-linking-data). | 30 mins |
| Once the basic integration is complete, any account user with access to the AppsFlyer dashboard can perform [basic testing](/docs/basic-sdk-integration-guide#testing-your-sdk-integration).<br /><br />Developers can utilize debug logs in the [development environment](/docs/testing-the-sdk-integration-for-marketers#testing-in-the-development-environment). | 1 hour |

You can work with your mobile developers to implement these additional APIs in the SDK.

| Additional SDK integration tasks | Planning time |
| --- | --- |
| Determine if your app requires [additional attribution](/docs/additional-sdk-integration-guide#additional-attribution-methods) setup (for example, uninstall measurement or install attribution for third-party app stores). | 30 mins |
| Determine [user session reporting](/docs/additional-sdk-integration-guide#sessions). | 30 mins |
| Determine the attribution methods to use for [owned media sources](/docs/additional-sdk-integration-guide#owned-media). | 1 hour |
| Manage [user privacy](/docs/additional-sdk-integration-guide#user-privacy) policies to make sure your app complies with privacy regulations (GDPR, CCPA). | 1 hour |

**See also**

* CTV, PC, and console platform overview