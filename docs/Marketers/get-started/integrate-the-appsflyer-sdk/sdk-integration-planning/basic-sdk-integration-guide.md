---
title: "Basic SDK integration guide"
excerpt: "Work with your mobile or CTV app developer to integrate and install the SDK into Android or iOS apps. Once basic integration tasks are complete, your app is ready for install attribution and in-app event measurement."
x-zendesk:
  id: 207032066
  url: https://support.appsflyer.com/hc/en-us/articles/207032066-Basic-SDK-integration-guide
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: SDK integration planning
  section_id: 6551182964369
  position: 1
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [sdk, iOS, Android, SDK, Integration, Advertisers, appuid, anonymous, kakao, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2013-08-22T16:09:08Z'
  edited_at: '2026-08-13T12:39:14Z'
---
## **Implementing the dev key in your app**

AppsFlyer uses the dev key to uniquely identify your account. The dev key is mandatory because it allows the SDK to securely send and retrieve data that belongs to your account. Your developer should install and integrate the SDK, and embed the dev key.

#### Retrieve the dev key

Before your developer can install and integrate the SDK, you must retrieve the dev key.

1. In AppsFlyer, from the side menu, select **Settings** > **App Settings** > **Dev Key Management**.
2. Copy your dev key, and send it to your mobile developer.

   ![](https://files.readme.io/5078fdabbcce4d3977f3d32351b61bacbc8af406a68911f2c6b4cdca458712a5-30603573703057.png)

#### Provide the Dev key to your developer

Provide the Dev Key, App ID, and AppsFlyer API v2 token to your mobile developer with instructions to:

* Use the [SDK integration wizard](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration) for automated SDK installation and integration.
* Use the step-by-step instructions to [install](https://dev.appsflyer.com/hc/docs/sdk-installation) and [integrate the SDK](https://dev.appsflyer.com/hc/docs/sdk-integration).

## **Where to start the SDK?**

When planning the integration of the AppsFlyer SDK, the first decision you must make is where to initialize and start the SDK within your application launch flow.

The basic rule of thumb is to have the SDK start sending data as soon as possible after launching the application. **This ensures that the SDK captures the install event and all other in-app events occurring in the session.**

However, to comply with privacy-preserving regulations such as GDPR and CCPA, it is often necessary to delay sending data to AppsFlyer until users consent to share their information.

<Accordion title="Android native">


Starting the SDK in Android native
SELECT IN WHAT CLASS TO START THE SDK
Select whether to start the SDK in the global Application class or the Activity class:


Start the SDK in the global Application class: Generally, initializing the SDK in the global Application class/subclass is a good practice because the Application class is loaded and initialized before any app UI is displayed. This ensures that the SDK can start in any scenario, including deep linking.

Start the SDK in an Activity class (deferred start) to allow users to opt-in to data sharing. This is because obtaining user consent requires a user interface (UI) rendered in an Activity class.

ANDROID DEVELOPER INSTRUCTIONS

Inform the developer of your decision on the following:
In what class - Application or Activity - to start the SDK?
Which opt-in/opt-out scenario to use?

Send your developer the following reference link:```[`How to perform deferred start](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#starting-the-android-sdk)

</Accordion>

<Accordion title="iOS native">


Starting the SDK in iOS native
DELAY THE SDK START IN IOS
An important consideration when planning how to start the SDK is whether to delay start until user consent is granted.
The SDK provides the waitForATTUserAuthorization method, which enables you to configure how long the SDK should wait for user consent before sending data to the AppsFlyer servers.
For more information on the method data flow and its interaction with the iOS ATT framework, see the `[`Configure App Tracking Transparency (ATT) support](/docs/basic-sdk-integration-guide#waitforattuserauthorization-overview) section.
IOS DEVELOPER INSTRUCTIONS
Share with your developer the following information:

How long in seconds is the timeout before sending data to AppsFlyer?
Developer Links:

`[`Starting the iOS SDK](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#starting-the-ios-sdk) for developer guide and reference on how to start the SDK.

`[`Configure App Tracking Transparency (ATT) support](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support) for information on the waitForATTUserAuthorization method data flow and how it interacts with the iOS ATT framework

`[`Enabling App Tracking Transparency (ATT) support](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support) for developer guide and reference on waitForATTUserAuthorization

</Accordion>

<Accordion title="Unity">


Starting the SDK in Unity
Send your developer `[`this Dev Hub article](https://dev.appsflyer.com/hc/docs/basicintegration#manual-integration) on how to start the SDK.

</Accordion>

<Accordion title="React Native">


Starting the SDK in React Native
Send your developer `[`this Dev Hub article](https://dev.appsflyer.com/hc/docs/rn_api#startsdk) on how to start the SDK.

</Accordion>

## Select your privacy preserving strategy

Select**how to preserve user privacy.** For example, select between stopping the SDK at installation, preventing data sharing with third parties, anonymizing user data or disabling specific identifiers.

For more information on the different privacy-preserving methods available, see [Privacy preserving methods in the SDK](/docs/apply-privacy-preserving-sdk-methods).

## **Attribution**

The SDK collects [identifiers](/docs/about-device-identifiers) for attribution purposes. To ensure that installs are recorded and attributed correctly, review and follow these guidelines.

**All platforms**

<Accordion title="Unique identifier for installs">


An AppsFlyer ID is automatically created for every new app install. No action is required by the marketer.
You can use this identifier to perform the following actions:

Send `[`server-to-server in-app events](/docs/server-to-server-events-api-for-mobile-s2s-mobile).
Match the AppsFlyer ID with user records in your backend systems.
Download the `[`raw data in-app event report](/docs/raw-data-reporting-overview) and use appsflyer_id to analyze user behavior and journeys.

</Accordion>

<Accordion title="Integrate unique identifiers from your BI system with AppsFlyer">


Set your own Customer user ID (CUID) in the AppsFlyer SDK to cross-reference the unique ID from your BI system with the AppsFlyer ID and other identifiers. The CUID is available in AppsFlyer `[`raw data](/docs/raw-data-field-dictionary) reports. You can also use it in postback APIs for cross-referencing with your internal IDs.
To learn more about CUID, see `[`this article.](/docs/customer-user-id-field-cuid)

</Accordion>

**Android only**

The following sections describe attribution considerations for Google Play Store or third-party app stores.

<Accordion title="Attribute apps published on Google Play">


GOOGLE PLAY INSTALL REFERRER
The `[`Google Play Install Referrer API ](https://developer.android.com/google/play/installreferrer)improves `[`attribution](/docs/appsflyer-attribution-model#attribution-methods) accuracy, protects from install fraud, and allows secure retrieval of referral data from Google Play (for example, the app's version at the time when the app was first installed).
It is recommended that you provide your developer with `[`instructions to add the Google Play Install Referrer API](https://developer.android.com/google/play/installreferrer/library).
GAID
Starting with SDK V4.8.0, AppsFlyer automatically collects this device identifier.

</Accordion>

<Accordion title="Attribute apps in third-party app stores">


With AppsFlyer, you can `[`attribute installs originating from third-party app stores](/docs/set-up-multi-store-android-attribution), such as Amazon, Opera, GetJar, Baidu, and Huawei. This allows you to promote your apps and reach larger audiences in markets where the Google Play Store is not available.
AppsFlyer supports attribution in the context of third-party app stores as follows:


IMEI or Android ID: The SDK doesn't automatically collect the IMEI or Android ID. However, if there is a need to collect these identifiers (for example, for `[`apps in the Chinese domestic market](/docs/measure-attribution-in-the-chinese-domestic-market#attribution-android-apps-in-the-chinese-domestic-market)) your developer can implement one of the following collection types:

Manual collection: The app passes the IMEI or Android ID to the SDK using the setImeiData or setAndroidIdData API (see function reference in the tabs below). The SDK sends the data to AppsFlyer servers.


<Accordion title="Android native">


See the Android SDK reference for:

`[`setImeiData](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setimeidata)

`[`setAndroidIdData](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setandroididdata) 

</Accordion>
<Accordion title="Unity">


See the Unity SDK reference for:

`[`setImeiData](https://dev.appsflyer.com/hc/docs/api#setimeidata)
`[`setAndroidIdData](https://dev.appsflyer.com/hc/docs/api#setandroididdata)

</Accordion>


Opt-in to device ID collection: Forces the SDK to collect the IMEI or Android ID using setCollectIMEI and setCollectAndroidID (see function reference in the tabs below).

<Accordion title="Android native">


See the Android SDK reference for:

`[`setCollectIMEI](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei)
`[`setCollectAndroidID](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid)

</Accordion>
<Accordion title="Unity">


See the Unity SDK reference for:

`[`setCollectIMEI](https://dev.appsflyer.com/hc/docs/api#setcollectimei)
`[`setCollectAndroidID](https://dev.appsflyer.com/hc/docs/api#setcollectandroidid)

</Accordion>
<Accordion title="React Native">


See the React Native reference for:

`[`setCollectIMEI](https://dev.appsflyer.com/hc/docs/rn_api#setcollectimei)
`[`setCollectAndroidID](https://dev.appsflyer.com/hc/docs/rn_api#setcollectandroidid)

</Accordion>


OAID: Attributes installs from third-party Android app stores. For more information, see the `[`guide to implementing OAID](/docs/android-oaid-implementation-in-the-sdk).

Install referrers: The SDK supports retrieval of referral data from Samsung Gallery and Huawei AppGallery.

</Accordion>

**iOS only**

The following sections include important information about support for iOS 14+ devices.
<Accordion title="Configure App Tracking Transparency (ATT) support">


BACKGROUND
Starting with iOS 14.5, IDFA collection requires user consent. Practically, it means IDFA access is governed by the `[`App Tracking Transparency](https://developer.apple.com/documentation/apptrackingtransparency) (ATT) framework. On iOS 14+ devices, the SDK uses the ATT framework to obtain access to the device IDFA. For an introduction to ATT, see `[`ATT principles](/docs/about-att-and-skan#att-principles).

<Accordion title="iOS native">

See the Dev Hub for `[`developer instructions for implementing ATT](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support).

</Accordion>
<Accordion title="Unity">

See the Dev Hub for `[`developer instructions for implementing ATT](https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager).

</Accordion>

When attribution occurs using IDFA, it's important IDFA is sent on the first launch. For this reason, the SDK provides the waitForATTUserAuthorization method.
waitForATTUserAuthorization overview

Don't call waitForATTUserAuthorization if you don't intend to invoke the ATT prompt.

waitForATTUserAuthorization enables you to configure how long the SDK should defer and wait for ATT status before sending data to the AppsFlyer servers.
 
`![](https://files.readme.io/a41e66c5aa23d2c673aba5b06589dcc24d34175e90900a8232343272ecca427c-30603573710993.png)`
 
When a user launches the app, ATT status is notDetermined. During the waitForATTUserAuthorization timeout, the SDK queues the launch event and consecutive in-app events in-memory, similar to the way in which `[`offline events are recorded](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#offline-in-app-events):

If the user consents to the ATT prompt (IDFA collection):
The SDK adds the IDFA to cached events.
The SDK starts and sends cached events with IDFA (without waiting for the timeout to end).

If the user declines the ATT prompt: The SDK starts and sends cached events without IDFA (without waiting for the timeout to end).
If the timeout ends and ATT status remains notDetermined: The SDK starts and sends cached events without IDFA.

Considerations

Calling `[`requestTrackingAuthorization](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/3547037-requesttrackingauthorization) without setting waitForATTUserAuthorization will result in launches and events being sent without IDFA for iOS 14+ devices.
If the user moves the app to the background during the timeout:
The timer pauses until the app returns to the foreground.
Events are cached in-memory.

If the user shuts down the app, it is killed during the timeout:
The timer is restarted on the next app launch.
Cached events are lost.

</Accordion>

<Accordion title="Customize ATT consent dialog">


You can customize the ATT prompt. A message that clearly states the purpose of the request could help increase the opt-in rates for users.
Consider the following when creating your message:

Use wording that best explains to your users why the app is asking for user consent.
Inform users about how their data will be used. `[`Learn more about user privacy and data use.](https://developer.apple.com/app-store/user-privacy-and-data-use/)

Once your message is complete, provide your developer with the text and implementation instructions.


<Accordion title="iOS native">

See the Dev Hub for `[`developer instructions for customizing the ATT consent dialog](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#customizing-the-att-consent-dialog).

</Accordion>

<Accordion title="Unity">

See the Dev Hub for `[`developer instructions for customizing the ATT consent dialog](https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager).

</Accordion>

</Accordion>

<Accordion title="Support for SKAN attribution">


 

To fully support SKAN attribution, upgrade to iOS SDK V6.2.3+.

SKAN is a class used by iOS to validate advertiser-driven app installations. The app install validation process involves the source app and the advertised app.
A source app is an app that participates in ad campaigns by displaying ads from an ad network. Configuring your app to display ads is not within the scope of the AppsFlyer SDK. To configure, follow the `[`Apple instructions](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app).
For the advertised app (the app with the AppsFlyer SDK), the AppsFlyer `[`SKAN solution](/docs/skadnetwork-skan-solution-guide) uses SKAN to provide the attribution postback while AppsFlyer collects, translates, and aggregates the data while maintaining user privacy. When the app is launched for the first time, the AppsFlyer platform uses the configuration set by the marketer to instruct the SDK on how to set the SKAN conversion value.
To use the SKAN solution:

The marketer needs to configure SKAN measurement in AppsFlyer. The developer does not have to perform any tasks.
The AppsFlyer SDK automatically calls the necessary SKAN APIs.
Make sure to disable SKAN calls in other SDKs if you rely on AppsFlyer for SKAN attribution.
There is no other action or registration process required by either the developer or the marketer in the App Store.

To disable SKAN attribution, instruct your developer to disable it in the SDK.


<Accordion title="iOS native">

To disable SKAN attribution use `[`disableSKAdNetwork](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableskadnetwork)

</Accordion>

<Accordion title="Unity">

To disable SKAN attribution use `[`disableSKAdNetwork](https://dev.appsflyer.com/hc/docs/api#disableskadnetwork)

</Accordion>

<Accordion title="React Native">

To disable SKAN attribution use `[`disableSKAd](https://dev.appsflyer.com/hc/docs/rn_api#disableskad)

</Accordion>

</Accordion>

## **Recording in-app events**

In-app events (IAE) provide insight into what is happening in your app. Recording in-app events helps you measure KPIs like Return on Investment (ROI) and Lifetime Value (LTV). We recommend taking the time to define the events that you want to record.

Once you determine the in-app events you want to measure, send the event names and parameters to your developer, and include a link to:

* The [SDK installation wizard](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration) which has a dedicated journey for in-app events.
* [The step by step implementation instructions for in-app events in the SDK](http://dev.appsflyer.com/hc/docs/in-app-events-sdk).

To learn how to define in-app events and send them to your developer, see our [Rich in-app events guide](/docs/in-app-events-overview).

**All platforms**

<Accordion title="Record revenue">


You can send revenue with any in-app event. Make sure you use the af_revenue parameter to include revenue. It is the only event parameter that AppsFlyer counts as real revenue on the dashboard and in raw data reports. `[`Learn more](/docs/in-app-events-overview#revenue-events).


<Accordion title="Android native">

For developer instructions on defining revenue events see `[`here](https://dev.appsflyer.com/hc/docs/in-app-events-android#logging-revenue).

</Accordion>

<Accordion title="iOS native">

For developer instructions on defining revenue events see `[`here](https://dev.appsflyer.com/hc/docs/in-app-events-ios#logging-revenue).

</Accordion>

<Accordion title="Unity">

``
For developer instructions on in-app events in general see `[`here](https://dev.appsflyer.com/hc/docs/inappevents#send-event).
For specific instructions for revenue in iOS and Android see the Android and iOS tabs.

</Accordion>

</Accordion>
<Accordion title="Validate in-app purchases">

The AppsFlyer SDK provides server verification for in-app purchases. Validating an in-app purchase automatically sends an in-app purchase event to AppsFlyer. Sending this event yourself creates duplicate event reporting.

</Accordion>
<Accordion title="Industry verticals">

See our `[`list of recommended in-app events per vertical](/docs/in-app-events-overview#recommended-events-by-business-vertical), for example, travel, gaming, or eCommerce.

</Accordion>

## **Deep linking with OneLink**

OneLink is the AppsFlyer solution for multi-platform attribution, **redirection, and deep linking**.

**All platforms**
<Accordion title="Device detection and redirection">

For users without your app installed, OneLink detects the device type and redirects them to the correct destination (for example, Google Play, Apple App Store, third-party app store, or web page). This is based on your OneLink template settings. `[`Learn more](/docs/create-a-onelink-template)

</Accordion>
<Accordion title="Deep linking">


For users with your app installed, OneLink opens the app. In addition to opening the app, you can also deep link users to a specific activity or page within the app. This requires your developer to implement Unified Deep Linking (UDL) using:

The `[`SDK installation wizard](https://dj.dev.appsflyer.com/?utm_source=kb&amp;amp;utm_medium=kb-basic-sdk-integration) which has a dedicated journey for deep linking implementation, or

`[`The step by step SDK implementation instructions for unified deep linking](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl).

Note:

UDL requires SDK V6.1+.
Customers already using OneLink for deep linking may be using the `[`legacy method](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking), instead of UDL.

See our guide on setting `[`Deep linking and deferred deep linking](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking).

</Accordion>
<Accordion title="Deferred deep linking">


For users without your app installed, OneLink detects the device type and redirects them to the correct destination: Google Play, Apple App Store, third-party app store, or web page. Once the user launches the app, you can use deferred deep linking to redirect them to a specific activity or page within the app.
This requires your developer to implement deferred deep linking using:

The `[`SDK installation wizard](https://dj.dev.appsflyer.com/?utm_source=kb&amp;amp;utm_medium=kb-basic-sdk-integration) which has a dedicated journey for deep linking implementation, or

`[`The step by step SDK implementation instructions for deferred deep linking](https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking).

Note:

UDL requires SDK V6.1+.
Customers already using OneLink for deferred deep linking might be using the `[`legacy method](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking), instead of UDL.

See our guide on setting `[`Deep linking and deferred deep linking](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking).

</Accordion>

## **Accessing attribution and deep linking data**

The following table describes the available methods for retrieving attribution and deep linking data:

| Method | Who is involved? | Return results | Retrieval method | Attribution data | Deep linking data | Availability |
| --- | --- | --- | --- | --- | --- | --- |
| [**Push API**](/docs/push-api-streaming-raw-data) | • Marketer • Back-end developer | Typically within minutes | Backend | Y | N | Premium |
| [**Pull API**](/docs/pull-api-raw-data) | • Marketer • Back-end developer | • Periodic (not real-time). • You can schedule raw-data report downloads. | Backend | Y | Y | Premium for raw-data reports |
| [**Data Locker**](/docs/data-locker-for-marketers) | • Marketer • Back-end developer | Hourly reports are available within 1 - 3 hours | Cloud storage via one of the following options: • AppsFlyer-owned bucket on AWS • Storage owned by you (AWS or GCS) | Y | Y | Premium |
| [**Get conversion data (GCD)**](/docs/conversion-data-payloads-and-scenarios#overview) | • Marketer • Mobile  developer [See developer documentation](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking) | Up to 5 seconds | SDK | Y | Y | All accounts |
| [**Unified Deep Linking (UDL)**](/docs/create-a-onelink-template) | • Marketer • Mobile developer [See developer documentation](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl) | Up to 1 second | SDK | N | Y | All accounts |

Note the following for iOS 14.5+ non-consenting users:

* When using UDL for paid and owned media, deep linking data is available.
* When using GCD for paid media, the data is limited and does not include attribution and deep linking details.

We recommend the following:

* Use Push API to retrieve attribution data and send it to your servers for further processing. This method waits for the data to become available, and therefore is highly accurate and close to real-time. GCD returns data in real-time, but may be inaccurate when final attribution decisions are determined after more than 5 seconds.
* Use Pull API to periodically (for example, daily) supplement real-time attribution data, and to compensate for any communication errors that might occur.

## **Testing your SDK integration**

Once the SDK integration is complete, you can go to the AppsFlyer dashboard, and from the SDK Integration Tests page, test organic and non-organic installs, in-app events, and deep linking (retargeting). This ensures that installs and in-app events are recorded and attributed correctly.

For testing scenarios and instructions, see [SDK integration testing](/docs/testing-the-sdk-integration-for-marketers).

**Note:** When performing attribution tests, [register a test device](/docs/registering-test-devices) (Android or iOS) to make sure each install is recorded as a new install. A registered test device prevents installs from being recorded as reinstalls.

**See also**

* CTV, PC, and console platform overview