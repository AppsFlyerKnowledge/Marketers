---
title: Basic SDK integration guide
metadata:
  keywords:
    - sdk
    - iOS
    - Android
    - Integration
    - Advertisers
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2013-08-22T16:09:08Z'
  edited_at: '2026-08-13T12:39:14Z'
  id: 207032066
  locale: en-us
  section: SDK integration planning
  section_id: 6551182964369
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207032066-Basic-SDK-integration-guide
---
> **At a glance:** Work with your mobile or CTV app developer to integrate and install the SDK into Android or iOS apps. Once basic integration tasks are complete, your app is ready for install attribution and in-app event measurement.

## **Implementing the dev key in your app**

AppsFlyer uses the dev key to uniquely identify your account. The dev key is mandatory because it allows the SDK to securely send and retrieve data that belongs to your account. Your developer should install and integrate the SDK, and embed the dev key.

#### Retrieve the dev key

Before your developer can install and integrate the SDK, you must retrieve the dev key.

1. In AppsFlyer, from the side menu, select **Settings** > **App Settings** > **Dev Key Management**.
2. Copy your dev key, and send it to your mobile developer.

   ![](https://files.readme.io/5078fdabbcce4d3977f3d32351b61bacbc8af406a68911f2c6b4cdca458712a5-30603573703057.png)

#### Provide the Dev key to your developer

Provide the Dev Key, App ID, and AppsFlyer API v2 token to your mobile developer with instructions to:

* Use the <Anchor target="_blank" href="https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration">SDK integration wizard</Anchor> for automated SDK installation and integration.
* Use the step-by-step instructions to <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">install</Anchor> and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-integration">integrate the SDK</Anchor>.

## **Where to start the SDK?**

When planning the integration of the AppsFlyer SDK, the first decision you must make is where to initialize and start the SDK within your application launch flow.

The basic rule of thumb is to have the SDK start sending data as soon as possible after launching the application. **This ensures that the SDK captures the install event and all other in-app events occurring in the session.**

However, to comply with privacy-preserving regulations such as GDPR and CCPA, it is often necessary to delay sending data to AppsFlyer until users consent to share their information.

<Tabs>
<Tab title="Android native">

### Starting the SDK in Android native

#### SELECT IN WHAT CLASS TO START THE SDK

Select whether to start the SDK in the global `Application` class or the `Activity` class:

* **Start the SDK in the global** `Application` **class:** Generally, initializing the SDK in the global `Application` class/subclass is a good practice because the `Application` class is loaded and initialized before any app UI is displayed. This ensures that the SDK can start in any scenario, including deep linking.
* **Start the SDK in an** `Activity` **class (deferred start)** to allow users to opt-in to data sharing. This is because obtaining user consent requires a user interface (UI) rendered in an `Activity` class.

#### ANDROID DEVELOPER INSTRUCTIONS

* Inform the developer of your decision on the following:
  * In what class - `Application` or `Activity` - to start the SDK?
  * Which opt-in/opt-out scenario to use?
* Send your developer the following reference link:
  * [How to perform deferred start](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#starting-the-android-sdk)

</Tab>

<Tab title="iOS native">

<div id="starting-the-sdk-in-ios" />

### Starting the SDK in iOS native

<div id="delay-the-sdk-start-in-ios" />

#### DELAY THE SDK START IN IOS

An important consideration when planning how to start the SDK is whether to delay `start` until user consent is granted.

The SDK provides the `waitForATTUserAuthorization` method, which enables you to **configure how long the SDK should wait for user consent before sending data to the AppsFlyer servers**.

For more information on the method data flow and its interaction with the iOS ATT framework, see the [Configure App Tracking Transparency (ATT) support](/docs/basic-sdk-integration-guide#waitforattuserauthorization-overview) section.

<div id="ios-developer-instructions" />

#### IOS DEVELOPER INSTRUCTIONS

Share with your developer the following information:

* How long in seconds is the timeout before sending data to AppsFlyer?
* Developer Links:
  * [Starting the iOS SDK](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#starting-the-ios-sdk) for developer guide and reference on how to start the SDK.
  * [Configure App Tracking Transparency (ATT) support](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support) for information on the `waitForATTUserAuthorization` method data flow and how it interacts with the iOS ATT framework
  * [Enabling App Tracking Transparency (ATT) support](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support) for developer guide and reference on `waitForATTUserAuthorization`

</Tab>

<Tab title="Unity">

<div id="starting-the-sdk-in-Unity" />

### Starting the SDK in Unity

Send your developer <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#manual-integration">this Dev Hub article</Anchor> on how to start the SDK.

</Tab>

<Tab title="React Native">

<div id="starting-the-sdk-in-react" />

### Starting the SDK in React Native

Send your developer <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#startsdk">this Dev Hub article</Anchor> on how to start the SDK.

</Tab>
</Tabs>

## Select your privacy preserving strategy

Select **how to preserve user privacy.** For example, select between stopping the SDK at installation, preventing data sharing with third parties, anonymizing user data or disabling specific identifiers.

For more information on the different privacy-preserving methods available, see <Anchor target="_blank" href="/marketers/docs/apply-privacy-preserving-sdk-methods">Privacy preserving methods in the SDK</Anchor>.

## **Attribution**

The SDK collects <Anchor target="_blank" href="/marketers/docs/about-device-identifiers">identifiers</Anchor> for attribution purposes. To ensure that installs are recorded and attributed correctly, review and follow these guidelines.

**All platforms**

<Accordion title="Unique identifier for installs">

An AppsFlyer ID is automatically created for every new app install. No action is required by the marketer.

You can use this identifier to perform the following actions:

* Send <Anchor target="_blank" href="/marketers/docs/server-to-server-events-api-for-mobile-s2s-mobile">server-to-server in-app events</Anchor>.
* Match the AppsFlyer ID with user records in your backend systems.
* Download the <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-overview">raw data in-app event report</Anchor> and use **appsflyer\_id** to analyze user behavior and journeys.

</Accordion>

<Accordion title="Integrate unique identifiers from your BI system with AppsFlyer">

Set your own Customer user ID (CUID) in the AppsFlyer SDK to cross-reference the unique ID from your BI system with the AppsFlyer ID and other identifiers. The CUID is available in AppsFlyer <Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary">raw data</Anchor> reports. You can also use it in postback APIs for cross-referencing with your internal IDs.

To learn more about CUID, see <Anchor target="_blank" href="/marketers/docs/customer-user-id-field-cuid">this article.</Anchor>

</Accordion>

**Android only**

The following sections describe attribution considerations for Google Play Store or third-party app stores.

<Accordion title="Attribute apps published on Google Play">

#### GOOGLE PLAY INSTALL REFERRER

The [Google Play Install Referrer API](https://developer.android.com/google/play/installreferrer) improves <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model#attribution-methods">attribution</Anchor> accuracy, protects from install fraud, and allows secure retrieval of referral data from Google Play (for example, the app's version at the time when the app was first installed).

It is recommended that you provide your developer with [instructions to add the Google Play Install Referrer API](https://developer.android.com/google/play/installreferrer/library).

#### GAID

Starting with SDK V4.8.0, AppsFlyer automatically collects this device identifier.

</Accordion>

<Accordion title="Attribute apps in third-party app stores">

With AppsFlyer, you can <Anchor target="_blank" href="/marketers/docs/set-up-multi-store-android-attribution">attribute installs originating from third-party app stores</Anchor>, such as Amazon, Opera, GetJar, Baidu, and Huawei. This allows you to promote your apps and reach larger audiences in markets where the Google Play Store is not available.

AppsFlyer supports attribution in the context of third-party app stores as follows:

* **IMEI or Android ID:** The SDK doesn't automatically collect the IMEI or Android ID. However, if there is a need to collect these identifiers (for example, for <Anchor target="_blank" href="/marketers/docs/measure-attribution-in-the-chinese-domestic-market#attribution-android-apps-in-the-chinese-domestic-market">apps in the Chinese domestic market</Anchor>) your developer can implement one of the following collection types:
  * Manual collection: The app passes the IMEI or Android ID to the SDK using the `setImeiData` or `setAndroidIdData` API (see function reference in the tabs below). The SDK sends the data to AppsFlyer servers.

    <Tabs>
    <Tab title="Android native">

    See the Android SDK reference for:

    * [`setImeiData`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setimeidata)
    * [`setAndroidIdData`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setandroididdata)

    </Tab>

    <Tab title="Unity">

    See the Unity SDK reference for:

    * [`setImeiData`](https://dev.appsflyer.com/hc/docs/api#setimeidata)
    * [`setAndroidIdData`](https://dev.appsflyer.com/hc/docs/api#setandroididdata)

    </Tab>
    </Tabs>

  * Opt-in to device ID collection: Forces the SDK to collect the IMEI or Android ID using setCollectIMEI and setCollectAndroidID (see function reference in the tabs below).

    <Tabs>
    <Tab title="Android native">

    See the Android SDK reference for:

    * [`setCollectIMEI`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei)
    * [`setCollectAndroidID`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid)

    </Tab>

    <Tab title="Unity">

    See the Unity SDK reference for:

    * [`setCollectIMEI`](https://dev.appsflyer.com/hc/docs/api#setcollectimei)
    * [`setCollectAndroidID`](https://dev.appsflyer.com/hc/docs/api#setcollectandroidid)

    </Tab>

    <Tab title="React Native">

    See the React Native reference for:

    * [`setCollectIMEI`](https://dev.appsflyer.com/hc/docs/rn_api#setcollectimei)
    * [`setCollectAndroidID`](https://dev.appsflyer.com/hc/docs/rn_api#setcollectandroidid)

    </Tab>
    </Tabs>

* **OAID:** Attributes installs from third-party Android app stores. For more information, see the <Anchor target="_blank" href="/marketers/docs/android-oaid-implementation-in-the-sdk">guide to implementing OAID</Anchor>.
* **Install referrers:** The SDK supports retrieval of referral data from Samsung Gallery and Huawei AppGallery.

</Accordion>

**iOS only**

The following sections include important information about support for iOS 14+ devices.

<Accordion title="Configure App Tracking Transparency (ATT) support">

**BACKGROUND**

Starting with iOS 14.5, IDFA collection requires user consent. Practically, it means IDFA access is governed by the [**App Tracking Transparency**](https://developer.apple.com/documentation/apptrackingtransparency) (ATT) framework. On iOS 14+ devices, the SDK uses the ATT framework to obtain access to the device IDFA. For an introduction to ATT, see <Anchor target="_blank" href="/marketers/docs/about-att-and-skan#att-principles">ATT principles</Anchor>.

<Tabs>
<Tab title="iOS native">

See the Dev Hub for <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support">developer instructions for implementing ATT</Anchor>.

</Tab>

<Tab title="Unity">

See the Dev Hub for <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager">developer instructions for implementing ATT</Anchor>.

</Tab>
</Tabs>

When attribution occurs using IDFA, it's important IDFA is sent on the **first launch.** For this reason, the SDK provides the `waitForATTUserAuthorization` method.

#### waitForATTUserAuthorization overview

> 🚧 **Important**
>
> Don't call waitForATTUserAuthorization if you don't intend to invoke the ATT prompt.

`waitForATTUserAuthorization` enables you to configure how long the SDK should defer and wait for ATT status before sending data to the AppsFlyer servers.

![](https://files.readme.io/a41e66c5aa23d2c673aba5b06589dcc24d34175e90900a8232343272ecca427c-30603573710993.png)

When a user launches the app, ATT status is **notDetermined.** During the `waitForATTUserAuthorization` timeout, the SDK queues the launch event and consecutive in-app events in-memory, similar to the way in which [offline events are recorded](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#offline-in-app-events):

* If the user **consents** to the ATT prompt (IDFA collection):
  * The SDK adds the IDFA to cached events.
  * The SDK starts and sends cached events with IDFA (without waiting for the timeout to end).
* If the user **declines** the ATT prompt: The SDK starts and sends cached events without IDFA (without waiting for the timeout to end).
* If the timeout ends and ATT status remains **notDetermined:** The SDK starts and sends cached events without IDFA.

**Considerations**

* Calling [`requestTrackingAuthorization`](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/3547037-requesttrackingauthorization) without setting `waitForATTUserAuthorization` will result in launches and events being sent without IDFA for iOS 14+ devices.
* If the user moves the app to the background during the timeout:
  * The timer pauses until the app returns to the foreground.
  * Events are cached in-memory.
* If the user shuts down the app, it is killed during the timeout:
  * The timer is restarted on the next app launch.
  * Cached events are lost.

</Accordion>

<Accordion title="Customize ATT consent dialog">

You can customize the ATT prompt. A message that clearly states the purpose of the request could help increase the opt-in rates for users.

Consider the following when creating your message:

* Use wording that best explains to your users why the app is asking for user consent.
* Inform users about how their data will be used. [Learn more about user privacy and data use.](https://developer.apple.com/app-store/user-privacy-and-data-use/)

Once your message is complete, provide your developer with the text and implementation instructions.

<Tabs>
<Tab title="iOS native">

See the Dev Hub for <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#customizing-the-att-consent-dialog">developer instructions for customizing the ATT consent dialog</Anchor>.

</Tab>

<Tab title="Unity">

See the Dev Hub for [developer instructions for customizing the ATT consent dialog](https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager).

</Tab>
</Tabs>

</Accordion>

<Accordion title="Support for SKAN attribution">

> 📘 **Note**
>
> To fully support SKAN attribution, upgrade to iOS SDK V6.2.3+.

SKAN is a class used by iOS to validate advertiser-driven app installations. The app install validation process involves the source app and the advertised app.

A source app is an app that participates in ad campaigns by displaying ads from an ad network. Configuring your app to display ads is not within the scope of the AppsFlyer SDK. To configure, follow the [Apple instructions](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app).

For the advertised app (the app with the AppsFlyer SDK), the AppsFlyer <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide">SKAN solution</Anchor> uses SKAN to provide the attribution postback while AppsFlyer collects, translates, and aggregates the data while maintaining user privacy. When the app is launched for the first time, the AppsFlyer platform uses the configuration set by the marketer to instruct the SDK on how to set the SKAN conversion value.

To use the SKAN solution:

* The marketer needs to configure SKAN measurement in AppsFlyer. The developer does not have to perform any tasks.
* The AppsFlyer SDK automatically calls the necessary SKAN APIs.
* Make sure to disable SKAN calls in other SDKs if you rely on AppsFlyer for SKAN attribution.
* There is no other action or registration process required by either the developer or the marketer in the App Store.

To disable SKAN attribution, instruct your developer to disable it in the SDK.

<Tabs>
<Tab title="iOS native">

To disable SKAN attribution use [`disableSKAdNetwork`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableskadnetwork)

</Tab>

<Tab title="Unity">

To disable SKAN attribution use [`disableSKAdNetwork`](https://dev.appsflyer.com/hc/docs/api#disableskadnetwork)

</Tab>

<Tab title="React Native">

To disable SKAN attribution use [`disableSKAd`](https://dev.appsflyer.com/hc/docs/rn_api#disableskad)

</Tab>
</Tabs>

</Accordion>

## **Recording in-app events**

In-app events (IAE) provide insight into what is happening in your app. Recording in-app events helps you measure KPIs like Return on Investment (ROI) and Lifetime Value (LTV). We recommend taking the time to define the events that you want to record.

Once you determine the in-app events you want to measure, send the event names and parameters to your developer, and include a link to:

* The [SDK installation wizard](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration) which has a dedicated journey for in-app events.
* <Anchor target="_blank" href="http://dev.appsflyer.com/hc/docs/in-app-events-sdk">The step by step implementation instructions for in-app events in the SDK</Anchor>.

To learn how to define in-app events and send them to your developer, see our <Anchor target="_blank" href="/marketers/docs/in-app-events-overview">Rich in-app events guide</Anchor>.

**All platforms**

<Accordion title="Record revenue">

You can send revenue with any in-app event. Make sure you use the **af\_revenue** parameter to include revenue. It is the only event parameter that AppsFlyer counts as real revenue on the dashboard and in raw data reports. <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#revenue-in-in-app-events">Learn more</Anchor>.

<Tabs>
<Tab title="Android native">

For developer instructions on defining revenue events see [here](https://dev.appsflyer.com/hc/docs/in-app-events-android#logging-revenue).

</Tab>

<Tab title="iOS native">

For developer instructions on defining revenue events see [here](https://dev.appsflyer.com/hc/docs/in-app-events-ios#logging-revenue).

</Tab>

<Tab title="Unity">

* For developer instructions on in-app events in general see [here](https://dev.appsflyer.com/hc/docs/inappevents#send-event).
* For specific instructions for revenue in iOS and Android see the Android and iOS tabs.

</Tab>
</Tabs>

</Accordion>

<Accordion title="Validate in-app purchases">

The AppsFlyer SDK provides server verification for in-app purchases. Validating an in-app purchase automatically sends an in-app purchase event to AppsFlyer. Sending this event yourself creates duplicate event reporting.

</Accordion>

<Accordion title="Industry verticals">

See our <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#recommended-events-by-business-vertical">list of recommended in-app events per vertical</Anchor>, for example, travel, gaming, or eCommerce.

</Accordion>

## **Deep linking with OneLink**

OneLink is the AppsFlyer solution for multi-platform attribution, **redirection, and deep linking**.

**All platforms**

<Accordion title="Device detection and redirection">

For users without your app installed, OneLink detects the device type and redirects them to the correct destination (for example, Google Play, Apple App Store, third-party app store, or web page). This is based on your OneLink template settings. <Anchor target="_blank" href="/marketers/docs/create-a-onelink-template">Learn more</Anchor>

</Accordion>

<Accordion title="Deep linking">

For users with your app installed, OneLink opens the app. In addition to opening the app, you can also deep link users to a specific activity or page within the app. This requires your developer to implement Unified Deep Linking (UDL) using:

* The [SDK installation wizard](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration) which has a dedicated journey for deep linking implementation, or
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">The step by step SDK implementation instructions for unified deep linking</Anchor>.

**Note**:

* UDL requires SDK V6.1+.
* Customers already using OneLink for deep linking may be using the [legacy method](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking), instead of UDL.

See our guide on setting <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">Deep linking and deferred deep linking</Anchor>.

</Accordion>

<Accordion title="Deferred deep linking">

For users without your app installed, OneLink detects the device type and redirects them to the correct destination: Google Play, Apple App Store, third-party app store, or web page. Once the user launches the app, you can use deferred deep linking to redirect them to a specific activity or page within the app.

This requires your developer to implement deferred deep linking using:

* The [SDK installation wizard](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration) which has a dedicated journey for deep linking implementation, or
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking">The step by step SDK implementation instructions for deferred deep linking</Anchor>.

**Note**:

* UDL requires SDK V6.1+.
* Customers already using OneLink for deferred deep linking might be using the [legacy method](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking), instead of UDL.

See our guide on setting <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">Deep linking and deferred deep linking</Anchor>.

</Accordion>

## **Accessing attribution and deep linking data**

The following table describes the available methods for retrieving attribution and deep linking data:

| Method | Who is involved? | Return results | Retrieval method | Attribution data | Deep linking data | Availability |
| --- | --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/docs/push-api-streaming-raw-data">**Push API**</Anchor> | • Marketer • Back-end developer | Typically within minutes | Backend | Y | N | Premium |
| <Anchor target="_blank" href="/marketers/docs/pull-api-raw-data">**Pull API**</Anchor> | • Marketer • Back-end developer | • Periodic (not real-time). • You can schedule raw-data report downloads. | Backend | Y | Y | Premium for raw-data reports |
| <Anchor target="_blank" href="/marketers/docs/data-locker-for-marketers">**Data Locker**</Anchor> | • Marketer • Back-end developer | Hourly reports are available within 1 - 3 hours | Cloud storage via one of the following options: • AppsFlyer-owned bucket on AWS • Storage owned by you (AWS or GCS) | Y | Y | Premium |
| <Anchor target="_blank" href="/marketers/docs/conversion-data-payloads-and-scenarios#overview">**Get conversion data (GCD)**</Anchor> | • Marketer • Mobile  developer <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking">See developer documentation</Anchor> | Up to 5 seconds | SDK | Y | Y | All accounts |
| <Anchor target="_blank" href="/marketers/docs/create-a-onelink-template">**Unified Deep Linking (UDL)**</Anchor> | • Marketer • Mobile developer <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">See developer documentation</Anchor> | Up to 1 second | SDK | N | Y | All accounts |

Note the following for iOS 14.5+ non-consenting users:

* When using UDL for paid and owned media, deep linking data is available.
* When using GCD for paid media, the data is limited and does not include attribution and deep linking details.

> 👍 **Tip**
>
> We recommend the following:
>
> * Use Push API to retrieve attribution data and send it to your servers for further processing. This method waits for the data to become available, and therefore is highly accurate and close to real-time. GCD returns data in real-time, but may be inaccurate when final attribution decisions are determined after more than 5 seconds.
> * Use Pull API to periodically (for example, daily) supplement real-time attribution data, and to compensate for any communication errors that might occur.

## **Testing your SDK integration**

Once the SDK integration is complete, you can go to the AppsFlyer dashboard, and from the SDK Integration Tests page, test organic and non-organic installs, in-app events, and deep linking (retargeting). This ensures that installs and in-app events are recorded and attributed correctly.

For testing scenarios and instructions, see <Anchor target="_blank" href="/marketers/docs/testing-the-sdk-integration-for-marketers">SDK integration testing</Anchor>.

**Note:** When performing attribution tests, <Anchor target="_blank" href="/marketers/docs/registering-test-devices">register a test device</Anchor> (Android or iOS) to make sure each install is recorded as a new install. A registered test device prevents installs from being recorded as reinstalls.

> 📘 **Note**
>
> **See also**
>
> * CTV, PC, and console platform overview

<div data-zendesk-anchors="retrieving-the-dev-key=implementing-the-dev-key-in-your-app h_01HAWCK9K4QBRE74JAS8Q7MEXW=implementing-the-dev-key-in-your-app h_01HHHKTARNPQTBXQ6CQGEHMJRG=retrieve-the-dev-key embed-the-dev-key=provide-the-dev-key-to-your-developer h_01HHHKXMBGV6EM0CCW842RQQZ6=provide-the-dev-key-to-your-developer h_01HAWCK9K4MBS0F0HE6QE1W1AN=where-to-start-the-sdk starting-the-sdk-in-android=starting-the-sdk-in-android-native h_01HAWCK9K45HCJEDRW761WHKES=starting-the-sdk-in-android-native h_01HAWCK9K428SDFBFCCSZ15X9J=select-in-what-class-to-start-the-sdk h_01HAWCK9K4XR1HZHP7Y15Q2Q4N=android-developer-instructions h_01HAWCK9K4693729EX1WYFR6XT=starting-the-sdk-in-ios h_01HAWCK9K4QSBP874RX2ZRA7EB=delay-the-sdk-start-in-ios h_01HAWCK9K4VHDFB9CYHC144BZN=ios-developer-instructions h_01JQ73M8DWMVQ98V1DQMPT0316=starting-the-sdk-in-Unity h_01JQ73M8DW350GBH9P52W4516V=starting-the-sdk-in-react select-the-optoutin-scenario::ae4c6e25=select-your-privacy-preserving-strategy h_01HAWCK9K4EXBA2F0BPVBXFAMG=select-your-privacy-preserving-strategy h_01HAWCK9K41T5GGWDB3ABYGRHW=attribution h_01HAWCK9K4V91MPQHXDZBD0HKR=google-play-install-referrer h_01HAWCK9K4YD8CYQDB2YRA8W1F=gaid h_01HAWCK9K5JHDWS8KTBTTGSS9G=waitforattuserauthorization-overview recording-inapp-events=recording-in-app-events h_01HAWCK9K5ZZYQR8KPCWANZEA5=recording-in-app-events h_01HAWCK9K5PK9RE7WZQVCY97KC=deep-linking-with-onelink h_01HAWCK9K5ACPZ2WKBTVR3VVTD=accessing-attribution-and-deep-linking-data h_01HAWCK9K6JQ33T32RYKYH20P1=testing-your-sdk-integration" />
