---
title: "OneSignal Integration with AppsFlyer"
excerpt: "Learn how to integrate OneSignal with AppsFlyer to send user attribution data and trigger push notifications based on install campaigns."
---
OneSignal is the market-leading push notification and in-app messaging provider, supporting over 1 million developers and marketers with a best-of-breed engagement platform.

![onesignal-logo-stack__3_.png](https://files.readme.io/49c50c481c00391f25cf8cc7eb2c35cc166f6a88a10db9120769a7d11affa26a-13013733757841.png)

OneSignal delivers 8 billion messages every day across the globe. Powered by superior architecture and an easy-to-use platform, the OneSignal delivers messages faster, more efficiently, and at a greater scale than any other solution in the world. Learn more at [onesignal.com](https://onesignal.com/?utm_medium=partner&utm_source=appsflyer)

> ❗️ Important!
>
> [Some media sources](https://support.appsflyer.com/hc/articles/360006868017-Raw-data-content-restriction-media-source-or-user-identifiers#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up OneSignal

The integration with OneSignal includes inserting a few lines of code to the AppsFlyer SDK in your app and then activating the integration in AppsFlyer.

### Set up the AppsFlyer SDK

When using Android, integrating with OneSignal requires that the OneSignal Player ID (OneSignal unique user identifier) is populated in AppsFlyer Android SDK. This parameter is sent with every postback and enables the identification of each user.

**To set up the AppsFlyer Android SDK:**

1. Make sure that the SDK version you use is 2.3.1.18 and above.
2. Insert the following lines of code in your app's code - [after OneSignal SDK was launched](https://documentation.onesignal.com/docs/android-sdk-setup) and before the initialization code for AppsFlyer SDK.

<Tabs>
<Tab title="Android (SDK 3.x.x)">

```java
AutoOSPermissionSubscriptionState status = OneSignal.getPermissionSubscriptionState();

          String deviceId = status.getSubscriptionStatus().getUserId();

            customData.put("onesignalCustomerId", deviceId);
```

</Tab>
<Tab title="Unity SDK">

```csharp
Autovar status = OneSignal.GetPermissionSubscriptionState();

          String deviceId = status.subscriptionStatus.userId;

            customData.put("onesignalCustomerId", deviceId);
```

</Tab>
<Tab title="Android (Native SDK 4+)">

```java
AutoOSDeviceState device = OneSignal.getDeviceState();

          String deviceId = device.getUserId();

            customData.put("onesignalCustomerId", deviceId);
```

</Tab>
</Tabs>

**To set up the AppsFlyer iOS SDK:**

1. Make sure that the SDK version you use is 2.3.1.18 and above.
2. Insert the following lines of code in your app's code - [after OneSignal SDK was launched](https://documentation.onesignal.com/docs/android-sdk-setup) and before the initialization code for AppsFlyer SDK.

<Tabs>
<Tab title="iOS (SDK 2.x.x) - Swift">

```swift
Autolet status: OSPermissionSubscriptionState = OneSignal.getPermissionSubscriptionState()
if let deviceId = status.subscriptionStatus.userId{
    customData.put("onesignalCustomerId", deviceId);
```

</Tab>
<Tab title="iOS (SDK 2.x.x) - Objective-C">

```objectivec
AutoOSPermissionSubscriptionState* status = [OneSignal getPermissionSubscriptionState];
NSDictionary* CustomDataMap = [[NSDictionary alloc] initWithObjectsAndKeys:status.subscriptionStatus.userId, @"onesignalCustomerId", nil];
[[AppsFlyerLib shared] setAdditionalData:CustomDataMap];
```

</Tab>
<Tab title="iOS (Native SDK 3+) - Swift">

```swift
Autoif let deviceState = OneSignal.getDeviceState() {
    let deviceId = deviceState.userId
    customData.put("onesignalCustomerId", deviceId);
```

</Tab>
<Tab title="iOS (Native SDK 3+) - Objective-C">

```objectivec
AutoOSDeviceState *deviceState = [OneSignal getDeviceState];
NSString *deviceId = deviceState.userId;
NSDictionary* CustomDataMap = [[NSDictionary alloc] initWithObjectsAndKeys:deviceId, @"onesignalCustomerId", nil];
[[AppsFlyerLib shared] setAdditionalData:CustomDataMap];
```

</Tab>
</Tabs>

> 📘 Prerequisite
>
> An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

> 📘 Note
>
> The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)

5. Complete the configuration using the relevant tabs, as described below:

### Integration tab

![onesignal-integration-tab.png](https://files.readme.io/95ec88041360d492367ed383aa3242bebe1cd5c5abcff8fba64e7888f0a9c052-360017329277.png)

The Integration Tab is divided into different sections as described below.

#### Activate partner

Must be enabled for as long as you work with the partner.

Learn more about [partner activation](https://support.appsflyer.com/hc/articles/360000844778#activating-a-partner).

#### General settings

##### OneSignal AppID

To connect your OneSignal account with AppsFlyer, enter your app ID in **OneSignal AppID** field.

Your OneSignal app ID is available in the OneSignal platform under **Settings** > **Keys & IDs**.

![onesignal-app-id-en_us.png](https://files.readme.io/2801bce8ea7ef4be731d8429bd0408f432d4b5600fbd359e989b0013da56b93e-360015238678.png)

#### Default postbacks

![onesignal-default-postbacks_en-us.png](https://files.readme.io/07e40365685543a318be8a16c9ea83638634d4a60333338eca0f76d140f84bef-360014377697.png)

AppsFlyer can send automatic postbacks to OneSignal following user installs. Use this section to define the source of the users that the postbacks are sent to for each event.

Learn more about [default postbacks](https://support.appsflyer.com/hc/articles/4410395957521#default%20postbacks).

**To send postbacks for any user that downloads the app to OneSignal**, select **All media sources, including organic**.

**To complete the integration configuration,** click **Save Integration**.

Although all events are sent by AppsFlyer, organic installs are not counted by OneSignal and therefore are ignored by OneSignal API.

Once you have saved the configuration, AppsFlyer sends the following data to OneSignal for every organic and non-organic install:

- Media source
- Campaign name
- Device ID
- Ad ID

### Attribution link tab

Attribution Links are not available for this partner.

### Cost tab

Cost data is not applicable in the integration with this partner.

### Ad revenue tab

Ad Revenue is not applicable in the integration with this partner.

### Permissions tab

Permissions are not available for this partner.

## View user attribution data in OneSignal

You can view attribution in the Segment Editor under the OneSignal tags either as the individual device level or when creating a segment to use in a campaign.

![onesignal-view-attribution_en-us.png](https://files.readme.io/ac23c9310cad560f692598127f3e9efb7c2b905efb6fd5de21efabe90bf58eea-360014377737.png)