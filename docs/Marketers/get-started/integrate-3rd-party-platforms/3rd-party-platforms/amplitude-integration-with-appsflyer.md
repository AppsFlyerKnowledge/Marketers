---
title: "Amplitude integration with AppsFlyer"
excerpt: "Integrate AppsFlyer with Amplitude to share user attribution data and event analytics for better insights into user engagement, retention, and revenue."
x-zendesk:
  id: 211200306
  url: https://support.appsflyer.com/hc/en-us/articles/211200306-Amplitude-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: 3rd-party platforms
  section_id: 6551199962257
  position: 3
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Ad Networks]
  labels: [Advertisers, Ad Networks, Amplitude, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2016-08-02T05:18:03Z'
  edited_at: '2026-09-09T13:59:07Z'
---
Integrate AppsFlyer with Amplitude to share user attribution data and event analytics for better insights into user engagement, retention, and revenue. Choose between **two integration versions, V1 or V2**, depending on your use case and analytics needs.

## About the integration

Amplitude, an AppsFlyer integrated partner, is a product analytics platform used by product, growth, and marketing teams to understand user behavior across mobile and web. The integration allows AppsFlyer to send key event data to Amplitude post-install, enabling comprehensive user-level analysis.

There are two Amplitude integration versions:

- **Amplitude V1:**

This version uses Amplitude's Attribution API. AppsFlyer sends install data collected after the integration is complete. Amplitude uses Ad ID as the identifier and discards the data if no matching user event is logged within 72 hours. [Learn more](https://amplitude.com/docs/apis/analytics/attribution)
- **Amplitude V2 :**

This version uses Amplitude's HTTP V2 API. AppsFlyer sends both installs and in-app event data after the integration is complete. Identifiers are prioritized (user\_id and device\_id), and if matching fails, a new user is logged. [Learn more](https://amplitude.com/docs/apis/analytics/http-v2)

**Integration versions:**

| Version | API used | Identifiers used | Event coverage |
| --- | --- | --- | --- |
| **V1** | Attribution API | Advertising ID (AdID) | Installs only |
| **V2** | HTTP V2 API | `user_id`, `device_id` (fallback logic) | Installs and in-app events |

> ❗️ Important!
>
> Choose either the Amplitude V1 or V2 integration. **Do not use both** simultaneously. Using both versions at the same time may result in duplicate events being sent to Amplitude.
>
> Some media sources restrict data sharing with third parties. Postbacks for restricted events won't be sent to this partner, even if configured.

## Prerequisites

**Before you begin:**

- Contact Amplitude to create an account if you don't already have one.
- Decide whether you will set up the Amplitude **V1** or **V2** integration.
- Make sure you avoid sending the same events from both the Amplitude SDK and AppsFlyer to prevent duplication.
- See the additional prerequisite for the Amplitude V2 integration.

### Additional prerequisites for the Amplitude V2 integration

The V2 integration requires setup of the:

- [Amplitude device ID](/docs/amplitude-integration-with-appsflyer#amplitude-device-id)
- [Customer user ID](/docs/amplitude-integration-with-appsflyer#customer-user-id)
- [Amplitude session ID](/docs/amplitude-integration-with-appsflyer#amplitude-session-id)

#### Amplitude device ID

To enable user-level attribution, you must pass the Amplitude Device ID into the AppsFlyer SDK. This value is sent with each postback.

<Tabs>
<Tab title="Android">

```java
JavaAppsFlyerLib.getInstance().setAdditionalData("AmplitudeDeviceId", amplitude.getDeviceId())
```

**Language:** Java/Kotlin

**Documentation:** [Android SDK reference](https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata), [Amplitude](https://amplitude.com/docs/sdks/analytics/android/android-kotlin-sdk#get-device-id)

</Tab>
<Tab title="iOS (Objective-C)">

```objectivec
Objective-C[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeDeviceId": [[Amplitude instance] getDeviceId]}];
```

**Language:** Objective-C

**Documentation:** [iOS SDK reference](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata), [Amplitude](https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id)

</Tab>
<Tab title="iOS (Swift)">

```swift
SwiftAppsFlyerLib.shared().customData = ["AmplitudeDeviceId": Amplitude.instance().getDeviceId()]
```

**Language:** Swift

**Documentation:** [iOS SDK reference](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata), [Amplitude](https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id)

</Tab>
<Tab title="Unity">

```csharp
C#Dictionary<string, string> customData = new Dictionary<string, string>();
customData.Add("AmplitudeDeviceId", Amplitude.getInstance().getDeviceId());
AppsFlyer.setAdditionalData(customData);
```

**Language:** C#

**Documentation:** [Unity SDK reference](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>
<Tab title="React Native">

```javascript
JavaScriptappsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()},
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
JavaScriptappsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()});
```

**Language:** JavaScript

**Documentation:** N/A

</Tab>
<Tab title="Flutter">

```auto
Autovar data = {"AmplitudeDeviceId": amplitude.getDeviceId()};
appsFlyerSdk.setAdditionalData(data);
```

**Language:** Dart

**Documentation:** [Flutter SDK reference](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

#### Customer user ID

Set up the Customer User ID (CUID). This is a unique identifier typically generated and set

by the app owner during user registration. [Learn more](/docs/customer-user-id-field-cuid)

#### Amplitude session ID

Set up the Amplitude session ID and pass it to AppsFlyer. [Learn more](https://amplitude.com/docs/data/sources/instrument-track-sessions)

<Tabs>
<Tab title="Android">

```java
JavaAppsFlyerLib.getInstance().setAdditionalData("AmplitudeSessionId", amplitude.getSessionId())
```

**Language:** Java/Kotlin

**Documentation:** [Android SDK reference](https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata)

</Tab>
<Tab title="iOS (Objective-C)">

```objectivec
Objective-C[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeSessionId": [[Amplitude instance] getSessionId]}];
```

**Language:** Objective-C

**Documentation:** [iOS SDK reference](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>
<Tab title="iOS (Swift)">

```swift
SwiftAppsFlyerLib.shared().customData = ["AmplitudeSessionId": Amplitude.instance().getSessionId()]
```

**Language:** Swift

**Documentation:** [iOS SDK reference](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>
<Tab title="Unity">

```csharp
C#Dictionary<string, string> customData = new Dictionary<string, string>();
customData.Add("AmplitudeSessionId", Amplitude.getInstance().getSessionId());
AppsFlyer.setAdditionalData(customData);
```

**Language:** C#

**Documentation:** [Unity SDK reference](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>
<Tab title="React Native">

```javascript
JavaScriptappsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()},
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
JavaScriptappsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()});
```

**Language:** JavaScript

**Documentation:** N/A

</Tab>
<Tab title="Flutter">

```auto
Autovar data = {"AmplitudeSessionId": amplitude.getSessionId()};
appsFlyerSdk.setAdditionalData(data);
```

**Language:** Dart

**Documentation:** [Flutter SDK reference](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

## Set up the integration

**To set up the integration:**

1. In AppsFlyer, go to **Collaborate** > **Partner Integrations > Marketplace** tab.
2. To set up the Amplitude V1 integration, select **Amplitude V1** (Tech partner).

<Image src="https://files.readme.io/71721bb1a48dda061ce2a099522edf9baed39ef2d67edad8ac14277b42cd2d70-36713632837777.png" alt="Select Amplitude V1 doctored.png" />

To set up the Amplitude V2 integration, select **Amplitude V2**(Tech partner).

<Image src="https://files.readme.io/4bbf57727a2b6e16e5205505b459a78f8642f02d1bb1c4e8f72e26b3bd9e1bd3-36713631187857.png" alt="Select Amplitude V2.png" />
3. Once you've selected your Amplitude version, click **Set up integration**.

<Image src="https://files.readme.io/c13fef10fb4cf0ea12f44d56f8c3b64936376ce181a1d12c9f096ad6103c29a6-36713632857617.png" alt="Click set up integration.png" />
4. In the **Integration** tab:
   - Select your app.
   - Turn on the **Activate partner** toggle.

     <Image src="https://files.readme.io/5e0e7ae537cd89b2c561c8561de9ebc160f6d6eb0fedc5c7ba0c761ddb73632a-36713631194641.png" alt="Activate partner blurred.png" />
5. Complete the configuration in the remaining tabs:

Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to turn **Activate Partner** on to enable setup of the integration tab's parameters. The toggle must be on for as long as you work with the partner.

Learn more about [partner activation](/docs/partner-activation-deactivation).

### General settings

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

#### Amplitude EU Data Center

When **Amplitude EU Data Center** is off, install postbacks are sent to the US data center.

To send install postbacks to Amplitude's EU data center, turn Amplitude EU Data Center on.

#### API Key

Amplitude connects with AppsFlyer via a unique API Key. If you don't already have it, you must obtain it from Amplitude to continue with the integration or follow the steps below.

**Obtaining the API key from Amplitude**

> 📘 Note
>
> Only users who have the Admin or Manager role on Amplitude can access the API Key.

1. Log in to your Amplitude account.
2. From the top right of the page, click the settings icon > **Organization Settings**.
<Image src="https://files.readme.io/214df773c045239924b65a4a1e6b0a1957f6b7ea09e225af80d83ffa0a469c26-16258070772625.png" alt="Amplitude" />
3. Click **Projects** and select the project from which to send data to AppsFlyer.
<Image src="https://files.readme.io/eaf158e4505f47f8da0fdae4f97be773ab32910352b50cab5ca5d4de3e8782ac-16335170399505.png" alt="amplitude" />
4. From the **Project** tab, copy your API key.
<Image src="https://files.readme.io/cf65648a9a8c122febe2b36fd4bd0b9f7f436cac49cfeec7f41870f614a16c6c-16258070773649.png" alt="Amplitude" />
5. Proceed to configure Amplitude in AppsFlyer Dashboard.

### Default postbacks

AppsFlyer can send automatic postbacks to Amplitude following user installs, including both installs and re-engagements (including re-attributions). Re-engagements occur when a user who already has the app installed opens it after clicking through a campaign. Learn more about [default postbacks](/docs/set-up-an-integrated-partner#default%20postbacks).

<Image src="https://files.readme.io/3454ca573ee63ea076251459a9c619a747fc5640862e83582b2d10a985c2489a-41748033847953.png" alt="Screenshot 2025-12-03 at 1.57.03 PM.png" />

### In-app event settings

- Enter the API Key.
- When **Amplitude Data Center** is off, in-app events postbacks are sent to the US data center.

**To send in-app events postbacks to Amplitude's EU data center, turn Amplitude Data Center on.**

Once you have saved the configuration, AppsFlyer sends the following data to Amplitude:

- Device ID (IDFV/Google Advertising ID)
- Media Source
- Campaign name

Sending IDFA for iOS devices is subject to [ATT consent by the user and to Advanced Privacy settings](/docs/apply-aggregated-advanced-privacy-framework).

### In-app event postbacks

[Configure sending in-app event postbacks](/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration) to Amplitude.

Attribution link tab

Attribution Links are not available for Amplitude.

Cost tab

Cost data is not supported in the integration with this partner.

Ad revenue tab

Ad Revenue is not supported in the integration with this partner.

Permissions tab

Permissions are not available for Amplitude.

## Viewing attribution data in the Amplitude console

Attribution data sent from AppsFlyer to Amplitude is displayed in your dashboards as events and properties prefixed with **[AppsFlyer]**:

<Image src="https://files.readme.io/bf52831ea6060172ce251136f47962ffb7f1ec9ffce13b9e35c614c4178e77f1-360009623597.png" alt="amplitude-properties.png" />

> ❗️ Important!
>
> In some cases, Amplitude shows data coming from AppsFlyer as "Blocked". If you can't see AppsFlyer data in Amplitude, check if it's defined as a blocked event.

## Sending Amplitude events to AppsFlyer

The integration also allows sending your Amplitude events to AppsFlyer via a Server-to-server API. See [Amplitude documentation](https://www.docs.developers.amplitude.com/data/destinations/appsflyer/) on how to do this.