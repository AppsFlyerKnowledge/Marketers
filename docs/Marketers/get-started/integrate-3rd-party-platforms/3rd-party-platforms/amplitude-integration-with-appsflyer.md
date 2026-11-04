---
title: Amplitude integration with AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Amplitude
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-08-02T05:18:03Z'
  edited_at: '2026-09-09T13:59:07Z'
  id: 211200306
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/211200306-Amplitude-integration-with-AppsFlyer
---
> **At a glance:** Integrate AppsFlyer with Amplitude to share user attribution data and event analytics for better insights into user engagement, retention, and revenue. Choose between **two integration versions, V1 or V2**, depending on your use case and analytics needs.

<div id="about-the-integration" />

## About the integration

Amplitude, an AppsFlyer integrated partner, is a product analytics platform used by product, growth, and marketing teams to understand user behavior across mobile and web. The integration allows AppsFlyer to send key event data to Amplitude post-install, enabling comprehensive user-level analysis.

There are two Amplitude integration versions:

* **Amplitude V1:**  
  This version uses Amplitude's Attribution API. AppsFlyer sends install data collected after the integration is complete. Amplitude uses Ad ID as the identifier and discards the data if no matching user event is logged within 72 hours. <Anchor target="_blank" href="https://amplitude.com/docs/apis/analytics/attribution">Learn more</Anchor>
* **Amplitude V2 :**  
  This version uses Amplitude's HTTP V2 API. AppsFlyer sends both installs and in-app event data after the integration is complete. Identifiers are prioritized (user\_id and device\_id), and if matching fails, a new user is logged. <Anchor target="_blank" href="https://amplitude.com/docs/apis/analytics/http-v2">Learn more</Anchor>

<span id="h_01JSE81SX1FR182N1CZJ5CQP5N"></span>**<span id="integration-methods"></span>Integration versions:**

| Version | API used | Identifiers used | Event coverage |
| --- | --- | --- | --- |
| **V1** | Attribution API | Advertising ID (AdID) | Installs only |
| **V2** | HTTP V2 API | `user_id`, `device_id` (fallback logic) | Installs and in-app events |

<div id="important" />

> 🚧 **Important**
>
> * Choose either the Amplitude V1 or V2 integration. **Do not use both** simultaneously. Using both versions at the same time may result in duplicate events being sent to Amplitude.
> * Some media sources restrict data sharing with third parties. Postbacks for restricted events won't be sent to this partner, even if configured.

<div id="prerequisites" />

## Prerequisites

**Before you begin:**

* Contact Amplitude to create an account if you don't already have one.
* Decide whether you will set up the Amplitude **V1** or **V2** integration.
* Make sure you avoid sending the same events from both the Amplitude SDK and AppsFlyer to prevent duplication.
* See the additional prerequisite for the Amplitude V2 integration.

<div id="additional-prerequisites-for-the-amplitude-v2-integration" />

### Additional prerequisites for the Amplitude V2 integration

The V2 integration requires setup of the:

* [Amplitude device ID](/docs/amplitude-integration-with-appsflyer#amplitude-device-id)
* [Customer user ID](/docs/amplitude-integration-with-appsflyer#customer-user-id)
* [Amplitude session ID](/docs/amplitude-integration-with-appsflyer#amplitude-session-id)

<div id="amplitude-device-id" />

#### Amplitude device ID

To enable user-level attribution, you must pass the Amplitude Device ID into the AppsFlyer SDK. This value is sent with each postback.

<Tabs>
<Tab title="Android">

```java
AppsFlyerLib.getInstance().setAdditionalData("AmplitudeDeviceId", amplitude.getDeviceId())
```

**Language:** Java/Kotlin

**Documentation:** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata">Android SDK reference</Anchor>, <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/android/android-kotlin-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="iOS (Objective-C)">

```objectivec
[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeDeviceId": [[Amplitude instance] getDeviceId]}];
```

**Language:** Objective-C

**Documentation:** [iOS SDK reference](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata), <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="iOS (Swift)">

```swift
AppsFlyerLib.shared().customData = ["AmplitudeDeviceId": Amplitude.instance().getDeviceId()]
```

**Language:** Swift

**Documentation:** [iOS SDK reference](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata), <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> customData = new Dictionary<string, string>();
customData.Add("AmplitudeDeviceId", Amplitude.getInstance().getDeviceId());
AppsFlyer.setAdditionalData(customData);
```

**Language:** C#

**Documentation:** [Unity SDK reference](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>

<Tab title="React Native">

```javascript
appsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()},
(res) => {
//...
}
);
```

**Language:** JavaScript

**Documentation:** [React Native SDK reference](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin)

</Tab>

<Tab title="Cordova">

```javascript
appsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()});
```

**Language:** JavaScript

**Documentation:** N/A

</Tab>

<Tab title="Flutter">

```
var data = {"AmplitudeDeviceId": amplitude.getDeviceId()};
appsFlyerSdk.setAdditionalData(data);
```

**Language:** Dart

**Documentation:** [Flutter SDK reference](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

<div id="customer-user-id" />

#### Customer user ID

Set up the Customer User ID (CUID). This is a unique identifier typically generated and set  
by the app owner during user registration. <Anchor target="_blank" href="/marketers/docs/customer-user-id-field-cuid?utm_source=chatgpt.com">Learn more</Anchor>

<div id="amplitude-session-id" />

#### Amplitude session ID

Set up the Amplitude session ID and pass it to AppsFlyer. <Anchor target="_blank" href="https://amplitude.com/docs/data/sources/instrument-track-sessions">Learn more</Anchor>

<Tabs>
<Tab title="Android">

```java
AppsFlyerLib.getInstance().setAdditionalData("AmplitudeSessionId", amplitude.getSessionId())
```

**Language:** Java/Kotlin

**Documentation:** [Android SDK reference](https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata)

</Tab>

<Tab title="iOS (Objective-C)">

```objectivec
[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeSessionId": [[Amplitude instance] getSessionId]}];
```

**Language:** Objective-C

**Documentation:** [iOS SDK reference](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>

<Tab title="iOS (Swift)">

```swift
AppsFlyerLib.shared().customData = ["AmplitudeSessionId": Amplitude.instance().getSessionId()]
```

**Language:** Swift

**Documentation:** [iOS SDK reference](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> customData = new Dictionary<string, string>();
customData.Add("AmplitudeSessionId", Amplitude.getInstance().getSessionId());
AppsFlyer.setAdditionalData(customData);
```

**Language:** C#

**Documentation:** [Unity SDK reference](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>

<Tab title="React Native">

```javascript
appsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()},
(res) => {
//...
}
);
```

**Language:** JavaScript

**Documentation:** [React Native SDK reference](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin)

</Tab>

<Tab title="Cordova">

```javascript
appsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()});
```

**Language:** JavaScript

**Documentation:** N/A

</Tab>

<Tab title="Flutter">

```
var data = {"AmplitudeSessionId": amplitude.getSessionId()};
appsFlyerSdk.setAdditionalData(data);
```

**Language:** Dart

**Documentation:** [Flutter SDK reference](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

<div id="set-up-the-integration" />

## Set up the integration

**To set up the integration:**

1. In AppsFlyer, go to **Collaborate** > **Partner Integrations > Marketplace** tab.
2. To set up the Amplitude V1 integration, select **Amplitude V1** (Tech partner).

   <Image alt="Select Amplitude V1 doctored.png" src="https://files.readme.io/71721bb1a48dda061ce2a099522edf9baed39ef2d67edad8ac14277b42cd2d70-36713632837777.png" width="511px" />

   To set up the Amplitude V2 integration, select **Amplitude V2** (Tech partner).

   <Image alt="Select Amplitude V2.png" src="https://files.readme.io/4bbf57727a2b6e16e5205505b459a78f8642f02d1bb1c4e8f72e26b3bd9e1bd3-36713631187857.png" width="503px" />
3. Once you've selected your Amplitude version, click **Set up integration**.

   ![Click set up integration.png](https://files.readme.io/c13fef10fb4cf0ea12f44d56f8c3b64936376ce181a1d12c9f096ad6103c29a6-36713632857617.png)
4. In the **Integration** tab:
   * Select your app.
   * Turn on the **Activate partner** toggle.

     <Image alt="Activate partner blurred.png" src="https://files.readme.io/5e0e7ae537cd89b2c561c8561de9ebc160f6d6eb0fedc5c7ba0c761ddb73632a-36713631194641.png" width="521px" />
5. Complete the configuration in the remaining tabs:

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

<div id="activate-partner" />

### Activate partner

On the **first visit** here, you will need to turn **Activate Partner** on to enable setup of the integration tab's parameters. The toggle must be on for as long as you work with the partner.  
Learn more about <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">partner activation</Anchor>.

<div id="general-settings" />

### General settings

<div id="advanced-data-sharing" />

#### Advanced data sharing

To share additional install information with Amplitude, turn on **Advanced data sharing**. When turned on, Amplitude receives the following data for installs (not in-app events) mapped to the listed Amplitude Property:

| Amplitude Property | AppsFlyer Data Point |
| --- | --- |
| sub\_publisher | af\_siteid |
| network\_name | pid |
| adgroup\_name | af\_adset |
| creative\_name | af\_ad\_id |
| installed\_at | install\_timestamp |
| search\_term | af\_keywords |
| channel | af\_channel |
| user\_id | af\_customer\_user\_id |
| af\_sub1 | af\_sub1 |
| af\_sub2 | af\_sub2 |
| af\_sub3 | af\_sub3 |
| af\_sub4 | af\_sub4 |
| af\_sub5 | af\_sub5 |
| app\_version | app\_version |

<div id="amplitude-eu-data-center" />

#### Amplitude EU Data Center

When **Amplitude EU Data Center** is off, install postbacks are sent to the US data center.  
To send install postbacks to Amplitude's EU data center, turn Amplitude EU Data Center on.

<div id="api-key" />

#### API Key

Amplitude connects with AppsFlyer via a unique API Key. If you don't already have it, you must obtain it from Amplitude to continue with the integration or follow the steps below.

<span id="obtaining-the-api-key-from-amplitude"></span>**Obtaining the API key from Amplitude**

**Note**: Only users who have the Admin or Manager role on Amplitude can access the API Key.

1. Log in to your Amplitude account.
2. From the top right of the page, click the settings icon > **Organization Settings**.

   <Image alt="Amplitude" src="https://files.readme.io/214df773c045239924b65a4a1e6b0a1957f6b7ea09e225af80d83ffa0a469c26-16258070772625.png" width="240px" />
3. Click **Projects** and select the project from which to send data to AppsFlyer.

   ![amplitude](https://files.readme.io/eaf158e4505f47f8da0fdae4f97be773ab32910352b50cab5ca5d4de3e8782ac-16335170399505.png)
4. From the **Project** tab, copy your API key.

   <Image alt="Amplitude" src="https://files.readme.io/cf65648a9a8c122febe2b36fd4bd0b9f7f436cac49cfeec7f41870f614a16c6c-16258070773649.png" width="648px" />
5. Proceed to configure Amplitude in AppsFlyer Dashboard.

<div id="default-postbacks" />

### Default postbacks

AppsFlyer can send automatic postbacks to Amplitude following user installs, including both installs and re-engagements (including re-attributions). Re-engagements occur when a user who already has the app installed opens it after clicking through a campaign. Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#default-postbacks">default postbacks</Anchor>.

<Image alt="Screenshot 2025-12-03 at 1.57.03 PM.png" src="https://files.readme.io/3454ca573ee63ea076251459a9c619a747fc5640862e83582b2d10a985c2489a-41748033847953.png" width="703px" />

<div id="in-app-event-settings" />

### In-app event settings

* Enter the API Key.
* When **Amplitude Data Center** is off, in-app events postbacks are sent to the US data center.  
  **To send in-app events postbacks to Amplitude's EU data center, turn Amplitude Data Center on.**

Once you have saved the configuration, AppsFlyer sends the following data to Amplitude:

* Device ID (IDFV/Google Advertising ID)
* Media Source
* Campaign name

Sending IDFA for iOS devices is subject to <Anchor target="_blank" href="/marketers/docs/apply-aggregated-advanced-privacy-framework">ATT consent by the user and to Advanced Privacy settings</Anchor>.

<div id="in-app-event-postbacks" />

### In-app event postbacks

<Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">Configure sending in-app event postbacks</Anchor> to Amplitude.

</Accordion>

<Accordion title="Attribution link tab">

Attribution Links are not available for Amplitude.

</Accordion>

<Accordion title="Cost tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<Accordion title="Permissions tab">

Permissions are not available for Amplitude.

</Accordion>

<div id="viewing-attribution-data-in-the-amplitude-console" />

## Viewing attribution data in the Amplitude console

Attribution data sent from AppsFlyer to Amplitude is displayed in your dashboards as events and properties prefixed with **[AppsFlyer]**:

![amplitude-properties.png](https://files.readme.io/bf52831ea6060172ce251136f47962ffb7f1ec9ffce13b9e35c614c4178e77f1-360009623597.png)

<div id="important-1" />

> 🚧 **Important**
>
> In some cases, Amplitude shows data coming from AppsFlyer as "Blocked". If you can't see AppsFlyer data in Amplitude, check if it's defined as a blocked event.

<div id="sending-amplitude-events-to-appsflyer" />

## Sending Amplitude events to AppsFlyer

The integration also allows sending your Amplitude events to AppsFlyer via a Server-to-server API. See <Anchor target="_blank" href="https://www.docs.developers.amplitude.com/data/destinations/appsflyer/">Amplitude documentation</Anchor> on how to do this.

<div data-zendesk-anchors="h_01JSE81SX1B1RH978Y08W1XXX8=about-the-integration set-up-the-integration=prerequisites h_01JSE958V510B9P6VEQTXC55S7=prerequisites additional-prerequisites-for-the-v2-integration=additional-prerequisites-for-the-amplitude-v2-integration h_01JSKEMMEB00PERVQWPYNF5V2E=additional-prerequisites-for-the-amplitude-v2-integration h_01JSKFH7KPSE5P0CRPVJ3FJ2WN=amplitude-device-id h_01JSKFK4BFH3PP98XAZ0W8GG11=customer-user-id h_01JSKFQXPPJVCW68C4H9B4EJ76=amplitude-session-id set-up-the-integration::45aa5acf=set-up-the-integration h_01JSKFQAZ8Q76KF1JJKZTAPVBQ=set-up-the-integration 01H8KPA9JKDRA680Y0WPZ172EM=activate-partner 01H8KPA9JKF4VCA4S22SYT40WT=general-settings 01H8KPA9JKJ2XN1AEPV74QVJYZ=advanced-data-sharing amplitude-data-center=amplitude-eu-data-center 01H8KPA9JKP0T0FDND97VA23EY=amplitude-eu-data-center 01H8KPA9JKDYDPDGRXZSH2BAV8=api-key 01H8KPA9JK510YKV47816DT7E7=obtaining-the-api-key-from-amplitude 01H8KRBGYQ973CT3H8GHZ8R0BH=default-postbacks inapp-event-settings=in-app-event-settings 01H8KPA9JKM4S79160BEYN3B6V=in-app-event-settings inapp-event-postbacks=in-app-event-postbacks 01H8KSQ76XE9Z191P1RMANF6EQ=in-app-event-postbacks 01H8KPA9JK75TA0H8T4P65BMSE=viewing-attribution-data-in-the-amplitude-console h_01HPYFZDX1WWDWJEBZ4DK706B4=sending-amplitude-events-to-appsflyer" />
