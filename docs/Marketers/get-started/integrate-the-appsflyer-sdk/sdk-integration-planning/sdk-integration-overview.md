---
title: SDK integration overview
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Integration
    - Advertisers
    - firetv
    - fire tv
    - Advertiser
    - Developer
    - appuid
    - anonymous
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2012-12-26T14:34:58Z'
  edited_at: '2026-08-13T12:37:40Z'
  id: 207032126
  locale: en-us
  section: SDK integration planning
  section_id: 6551182964369
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207032126-SDK-integration-overview
---
> **At a glance:** Learn about the AppsFlyer SDK functionalities that are available and determine which APIs you want your Android or iOS app to use.

## About the SDK

Watch this video to get the big picture of SDK integration.

<Embed title="SDK integration overview" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/4iybquc6q3" providerUrl="https://fast.wistia.com" />

The SDK provides app installation and event recording functionality. You can record installs, sessions, and in-app events. In-app events include, for example, in-app purchases or leveling up in a game. Recording these events can help you evaluate ROI and user quality.

This article describes the process for the SDK V6+ integration and helps advertisers (app owners) and product managers plan the AppsFlyer SDK integration with their Android or iOS app.

Additional documentation includes the following:

<Tabs>
<Tab title="Android native">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">SDK installation documentation for developers</Anchor>
* <Anchor target="_blank" href="/marketers/docs/appsflyer-android-sdk-release-notes">Release notes</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference">SDK reference documentation for developers</Anchor>
* <Anchor target="_blank" href="/marketers/docs/fill-out-google-safety-section-form">Data safety section on Google Play</Anchor>

</Tab>

<Tab title="iOS native">

* <Anchor target="_blank" href="/marketers/docs/updating-to-ios-sdk-v6-and-plugins">Updating to iOS SDK V6</Anchor>. Note that iOS SDK V5.4.4 is fully operational with iOS 14. However, we recommend adopting SDK V6.X to ensure compatibility with future iOS releases.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">SDK installation documentation for developers</Anchor>
* <Anchor target="_blank" href="/marketers/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes">Release notes</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference">SDK reference documentation for developers</Anchor>
* <Anchor target="_blank" href="/marketers/docs/preparing-for-the-app-store-review-nutrition-labels">Preparing for the App Store review, nutrition labels</Anchor>

</Tab>

<Tab title="Unity">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">SDK installation documentation for developers</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api">SDK reference documentation for developers</Anchor>

</Tab>

<Tab title="React Native">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">SDK installation documentation for developers</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api">SDK reference documentation for developers</Anchor>

</Tab>
</Tabs>

## SDK compatibility

The AppsFlyer SDK is compatible with the following platforms:

<Tabs>
<Tab title="Android">

* Starting Android V4.0
* Non-mobile Android-based platforms, such as Smart TVs (including Amazon Fire TV). <Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-attribution-concepts">See CTV overview</Anchor>
* <Anchor target="_blank" href="/marketers/docs/set-up-multi-store-android-attribution">Out-of-store markets</Anchor> for Android apps, such as Amazon and Baidu

</Tab>

<Tab title="iOS">

* iOS 9+ (iPhone, iPod, iPad)
* tvOS 9+ (Apple TV)
* Complies with Apple <Anchor target="_blank" href="https://developer.apple.com/library/content/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/UnderstandingandPreparingfortheIPv6Transition/UnderstandingandPreparingfortheIPv6Transition.html#//apple_ref/doc/uid/TP40010220-CH213-SW1">IPv6 DNS64/NAT64</Anchor> networks

The SDK supports <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model">multiple attribution methods</Anchor>. The attribution methods that are used depend on the following:

* The iOS version installed on the user's device
* The iOS SDK version installed in the app

<table><thead><tr><th>Attribution methods supported</th><th>iOS version</th><th>iOS SDK support</th><th>Notes</th></tr></thead><tbody><tr><td rowspan="2">Probabilistic modeling</td><td>8 – 14.4</td><td>5.0.0+</td><td> </td></tr><tr><td>14.5+</td><td>6.0.3+</td><td>Probabilistic modeling is limited to the context of owned media, cross-promotion, and consented web-to-app flows.</td></tr><tr><td rowspan="2">ID matching<br/><br/> </td><td>8 - 13</td><td>5.0.0+</td><td>Users can opt out using Limit Ad Tracking (LAT).</td></tr><tr><td>14.5+</td><td>6.0.3+</td><td>App Tracking Transparency (ATT) and user consent is required. For more information, see <a href="./basic-sdk-integration-guide#configure-app-tracking-transparency-att-support" target="_blank">configure the iOS SDK to support ATT</a>.</td></tr><tr><td rowspan="2"><a href="./skadnetwork-skan-solution-guide" target="_blank">SKAdNetwork</a></td><td>11.3 - 13</td><td rowspan="2">6.2.3<br/><br/> </td><td>The SKAdNetwork (SKAN) solution is limited to install attribution in accordance with the <a href="https://developer.apple.com/documentation/storekit/skadnetwork" target="_blank">SKAN</a> specification, meaning there is no conversion value.</td></tr><tr><td>14+</td><td><ul><li>SKAN is always available at the iOS and SDK levels irrespective of the ATT setting.</li><li>The marketer enables SKAN in the AppsFlyer dashboard.</li></ul></td></tr></tbody></table>

Starting from SDK V6.0.8, <Anchor target="_blank" href="/marketers/docs/apple-app-clips-integration-guide">Apple App Clips attribution</Anchor> is available. You can also read our <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/apple-app-clips">blog post</Anchor> about Apple App Clips.

</Tab>
</Tabs>

## SDK integration

The process of installing and integrating the SDK requires the product manager and mobile developer to work together. **Before** integrating the SDK with your app, review all of the integration tasks and consider the functionalities that you want your app to use.

### SDK planning checklist

To get you started, we've prepared a <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTD4OimHC93iw2AJCcAY45yAc9lOBfJe8PskI_0NFZTnWnrIq1hjPBvCztkbom9acMDDd4d1d5mMFfi/pub?output=xlsx">downloadable checklist</Anchor> to help guide you through the planning process. For each task, there are links to the marketer and developer documentation.

### SDK integration tasks

The basic SDK integration includes the following tasks. Time estimates are intended as general guidance only.

| Basic SDK integration tasks | Planning time |
| --- | --- |
| Retrieve the <Anchor target="_blank" href="/marketers/docs/basic-sdk-integration-guide#implementing-the-dev-key-in-your-app">AppsFlyer dev key</Anchor> and send the link along with installation and integration instructions to your developer. | 15 mins |
| Review the <Anchor target="_blank" href="/marketers/docs/basic-sdk-integration-guide#attribution">attribution considerations</Anchor>, and determine which device identifiers to collect. | 30 mins |
| Determine the <Anchor target="_blank" href="/marketers/docs/basic-sdk-integration-guide#recording-in-app-events">in-app events</Anchor> that you want to measure, and send the event names and event parameters to the developer. | 1 hour |
| Determine the <Anchor target="_blank" href="/marketers/docs/basic-sdk-integration-guide#deep-linking-with-onelink">deep linking methods</Anchor> to use. | 30 mins |
| Determine the methods for <Anchor target="_blank" href="/marketers/docs/basic-sdk-integration-guide#accessing-attribution-and-deep-linking-data">accessing attribution data</Anchor>. | 30 mins |
| Once the basic integration is complete, any account user with access to the AppsFlyer dashboard can perform <Anchor target="_blank" href="/marketers/docs/basic-sdk-integration-guide#testing-your-sdk-integration">basic testing</Anchor>.<br /><br />Developers can utilize debug logs in the <Anchor target="_blank" href="/marketers/docs/testing-the-sdk-integration-for-marketers#testing-in-the-development-environment">development environment</Anchor>. | 1 hour |

You can work with your mobile developers to implement these additional APIs in the SDK.

| Additional SDK integration tasks | Planning time |
| --- | --- |
| Determine if your app requires <Anchor target="_blank" href="/marketers/docs/additional-sdk-integration-guide#additional-attribution-methods">additional attribution</Anchor> setup (for example, uninstall measurement or install attribution for third-party app stores). | 30 mins |
| Determine <Anchor target="_blank" href="/marketers/docs/additional-sdk-integration-guide#sessions">user session reporting</Anchor>. | 30 mins |
| Determine the attribution methods to use for <Anchor target="_blank" href="/marketers/docs/additional-sdk-integration-guide#owned-media">owned media sources</Anchor>. | 1 hour |
| Manage <Anchor target="_blank" href="/marketers/docs/additional-sdk-integration-guide#user-privacy">user privacy</Anchor> policies to make sure your app complies with privacy regulations (GDPR, CCPA). | 1 hour |

> 📘 **Note**
>
> **See also**
>
> * CTV, PC, and console platform overview

<div data-zendesk-anchors="h_01H9FHRVKE6BHGW05G6YMKF737=about-the-sdk h_01H9FHRVKEQ837Q0GFECNPPAN2=sdk-compatibility h_01H9FHRVKEN0MMGTSD362FTWPS=sdk-integration h_01H9FHRVKE468M1RTMF7VTYV1R=sdk-planning-checklist h_01H9FHRVKERHXY19R97EN86EGP=sdk-integration-tasks" />
