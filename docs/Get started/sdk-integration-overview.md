---
title: "SDK integration overview"
excerpt: "Learn about the AppsFlyer SDK functionalities that are available and determine which APIs you want your Android or iOS app to use."
---
## About the SDK

Watch this video to get the big picture of SDK integration.

<Embed title="SDK integration planning for marketers" typeOfEmbed="youtube" url="https://www.youtube.com/embed/9d97a9c6e8ebf816440e435c719ac827b02489abdba6f7da7c79490a00d315e0" />

The SDK provides app installation and event recording functionality. You can record installs, sessions, and in-app events. In-app events include, for example, in-app purchases or leveling up in a game. Recording these events can help you evaluate ROI and user quality.

This article describes the process for the SDK V6+ integration and helps advertisers (app owners) and product managers plan the AppsFlyer SDK integration with their Android or iOS app.

Additional documentation includes the following:

<Tabs>
<Tab title="Android native">

- [SDK installation documentation for developers](https://dev.appsflyer.com/hc/docs/install-android-sdk)
- [Release notes](https://support.appsflyer.com/hc/articles/115001256006)
- [SDK reference documentation for developers](https://dev.appsflyer.com/hc/docs/android-sdk-reference)
- [Data safety section on Google Play](https://support.appsflyer.com/hc/articles/4417197430289)

</Tab>
<Tab title="iOS native">

- [Updating to iOS SDK V6](https://support.appsflyer.com/hc/articles/360011571778). Note that iOS SDK V5.4.4 is fully operational with iOS 14. However, we recommend adopting SDK V6.X to ensure compatibility with future iOS releases.
- [SDK installation documentation for developers](https://dev.appsflyer.com/hc/docs/install-ios-sdk)
- [Release notes](https://support.appsflyer.com/hc/articles/115001224823#ios-v600-release-notes)
- [SDK reference documentation for developers](https://dev.appsflyer.com/hc/docs/ios-sdk-reference)
- [Preparing for the App Store review, nutrition labels](/docs/preparing-for-the-app-store-review-nutrition-labels)

</Tab>
<Tab title="Unity">

- [SDK installation documentation for developers](https://dev.appsflyer.com/hc/docs/installation)
- [SDK reference documentation for developers](https://dev.appsflyer.com/hc/docs/api)

</Tab>
<Tab title="React Native">

- [SDK installation documentation for developers](https://dev.appsflyer.com/hc/docs/installation)
- [SDK reference documentation for developers](https://dev.appsflyer.com/hc/docs/rn_api)

</Tab>
</Tabs>

## SDK compatibility

The AppsFlyer SDK is compatible with the following platforms:

<Tabs>
<Tab title="Android">

- Starting Android V4.0
- Non-mobile Android-based platforms, such as Smart TVs (including Amazon Fire TV). [See CTV overview](https://support.appsflyer.com/hc/articles/4404083608849)
- [Out-of-store markets](https://support.appsflyer.com/hc/articles/207447023) for Android apps, such as Amazon and Baidu

</Tab>
<Tab title="iOS">

- iOS 9+ (iPhone, iPod, iPad)
- tvOS 9+ (Apple TV)
- Complies with Apple [IPv6 DNS64/NAT64](https://developer.apple.com/library/content/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/UnderstandingandPreparingfortheIPv6Transition/UnderstandingandPreparingfortheIPv6Transition.html#//apple_ref/doc/uid/TP40010220-CH213-SW1) networks

</Tab>
</Tabs>

The SDK supports [multiple attribution methods](https://support.appsflyer.com/hc/articles/207447053). The attribution methods that are used depend on the following:

- The iOS version installed on the user's device
- The iOS SDK version installed in the app

| Attribution methods supported | iOS version | iOS SDK support | Notes |
| --- | --- | --- | --- |
| Probabilistic modeling | 8 – 14.4 | 5.0.0+ |  |
| 14.5+ | 6.0.3+ | Probabilistic modeling is limited to the context of owned media, cross-promotion, and consented web-to-app flows. |
| ID matching | 8 - 13 | 5.0.0+ | Users can opt out using Limit Ad Tracking (LAT). |
| 14.5+ | 6.0.3+ | App Tracking Transparency (ATT) and user consent is required. For more information, see [configure the iOS SDK to support ATT](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support). |
| [SKAdNetwork](https://support.appsflyer.com/hc/articles/360011420698) | 11.3 - 13 | 6.2.3 | The SKAdNetwork (SKAN) solution is limited to install attribution in accordance with the [SKAN](https://developer.apple.com/documentation/storekit/skadnetwork) specification, meaning there is no conversion value. |
| 14+ | - SKAN is always available at the iOS and SDK levels irrespective of the ATT setting.<br>- The marketer enables SKAN in the AppsFlyer dashboard. |

Starting from SDK V6.0.8, [Apple App Clips attribution](/docs/apple-app-clips-integration-guide) is available. You can also read our [blog post](https://www.appsflyer.com/resources/others/apple-app-clips) about Apple App Clips.

## SDK integration

The process of installing and integrating the SDK requires the product manager and mobile developer to work together. **Before** integrating the SDK with your app, review all of the integration tasks and consider the functionalities that you want your app to use.

### SDK planning checklist

To get you started, we've prepared a [downloadable checklist](https://docs.google.com/spreadsheets/d/e/2PACX-1vTD4OimHC93iw2AJCcAY45yAc9lOBfJe8PskI_0NFZTnWnrIq1hjPBvCztkbom9acMDDd4d1d5mMFfi/pub?output=xlsx) to help guide you through the planning process. For each task, there are links to the marketer and developer documentation.

### SDK integration tasks

The basic SDK integration includes the following tasks. Time estimates are intended as general guidance only.

| Basic SDK integration tasks | Planning time |
| --- | --- |
| Retrieve the [AppsFlyer dev key](https://support.appsflyer.com/hc/articles/207032066#retrieving-the-dev-key) and send the link along with installation and integration instructions to your developer. | 15 mins |
| Review the [attribution considerations](https://support.appsflyer.com/hc/articles/207032066#attribution), and determine which device identifiers to collect. | 30 mins |
| Determine the [in-app events](https://support.appsflyer.com/hc/articles/207032066#recording-inapp-events) that you want to measure, and send the event names and event parameters to the developer. | 1 hour |
| Determine the [deep linking methods](https://support.appsflyer.com/hc/articles/207032066#deep-linking-with-onelink) to use. | 30 mins |
| Determine the methods for [accessing attribution data](https://support.appsflyer.com/hc/articles/207032066#accessing-attribution-and-deep-linking-data). | 30 mins |
| Once the basic integration is complete, any account user with access to the AppsFlyer dashboard can perform [basic testing](https://support.appsflyer.com/hc/articles/207032066#testing-your-sdk-integration).<br>Developers can utilize debug logs in the [development environment](https://support.appsflyer.com/hc/articles/360001559405#testing-in-the-development-environment). | 1 hour |

You can work with your mobile developers to implement these additional APIs in the SDK.

| Additional SDK integration tasks | Planning time |
| --- | --- |
| Determine if your app requires [additional attribution](https://support.appsflyer.com/hc/articles/4408735106193#additional-attribution-methods) setup (for example, uninstall measurement or install attribution for third-party app stores). | 30 mins |
| Determine [user session reporting](https://support.appsflyer.com/hc/articles/4408735106193#sessions). | 30 mins |
| Determine the attribution methods to use for [owned media sources](https://support.appsflyer.com/hc/articles/4408735106193#owned-media). | 1 hour |
| Manage [user privacy](https://support.appsflyer.com/hc/articles/4408735106193#user-privacy) policies to make sure your app complies with privacy regulations (GDPR, CCPA). | 1 hour |

<Cards>
<Card title="CTV, PC, and console platform overview" href="https://support.appsflyer.com/hc/articles/4404083608849">
Learn more about CTV, PC, and console platform integration.
</Card>
</Cards>