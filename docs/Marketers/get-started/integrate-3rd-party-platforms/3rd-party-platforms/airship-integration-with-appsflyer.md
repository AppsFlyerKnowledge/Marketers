---
title: "Airship integration with AppsFlyer"
excerpt: "Learn how to integrate Airship with AppsFlyer to share attribution data and target audiences with greater specificity."
---
At a glance: Airship, an AppsFlyer integrated partner, provides the world’s leading mobile engagement platform, helping thousands of businesses of all sizes form a direct and lasting connection with their customers. With Airship, companies gain total control of their mobile footprint — apps, wallets, and user-level data — to deliver experiences that get noticed and drive action across mobile or any other customer touch-point.

> ❗️ Important!
>
> [Some media sources](https://support.appsflyer.com/hc/articles/360006868017-Raw-data-content-restriction-media-source-or-user-identifiers#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Airship

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

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

## Integration tab

The Integration tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to turn on **Activate partner** to enable the setup of the integration tab's parameters. **The toggle must be on for as long as you work with the partner**.

Learn more about [partner activation](https://support.appsflyer.com/hc/articles/360000844778).

### General settings

Airship connects with AppsFlyer via a unique App Key and Token. If you don't already have them, you can obtain it from Airship to continue with the integration, or see below for instructions how to obtain it.

![airship-integration-tab.png](https://files.readme.io/dc33feec09fe551700586b9778a037fa0f5d610224944aea5a0fe56a6d288043-360017400878.png)

**To configure the integration with Airship:**

Minimum requirements - AppsFlyer SDK:

- Android – version 2.3.1.18 and above
- iOS – version 3.3.3 and above

Minimum requirements - Airship SDK - Version 13.1.0 and above.

1. Integrating with Airship requires that the channelid (Airship's unique user identifier) is populated in AppsFlyer's SDK.

   - [More on Channel ID for iOS](https://docs.airship.com/platform/ios/segmentation/#airship-channel-ids).
   - [More on Channel ID for Android](https://docs.airship.com/platform/android/segmentation/#airship-channel-ids).

This parameter is sent with every postback and enables the identification of each user. To perform this you must insert the following strings to your app code:

> ❗️ Important Note
>
> Make sure the lines of code are inserted in the correct place – after Airship SDK is launched and before the start method is called on iOS or Android.

<Tabs>
<Tab title="Android">

For more details about the `setAdditionalData` method, click [here](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata).

```java
JavaHashMap<String, Object> customData = new HashMap<String,Object>();
String channelId = UAirship.shared().getChannel().getId();
customData.put(