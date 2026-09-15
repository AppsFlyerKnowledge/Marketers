---
title: "Airship integration with AppsFlyer"
excerpt: "Learn how to integrate Airship with AppsFlyer to share attribution data and target audiences with greater specificity."
---
**At a glance:** Airship, an AppsFlyer integrated partner, provides the world’s leading mobile engagement platform, helping thousands of businesses of all sizes form a direct and lasting connection with their customers. With Airship, companies gain total control of their mobile footprint — apps, wallets, and user-level data — to deliver experiences that get noticed and drive action across mobile or any other customer touch-point.

> 📘 **Note**
>
> #### Important!
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.


## Setting up Airship

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below:

## Integration tab

The Integration tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to turn on **Activate partner** to enable the setup of the integration tab's parameters. **The toggle must be on for as long as you work with the partner**.  
Learn more about [partner activation](/docs/partner-activation-deactivation).

### General settings

Airship connects with AppsFlyer via a unique App Key and Token. If you don't already have them, you can obtain it from Airship to continue with the integration, or see below for instructions how to obtain it.

![airship-integration-tab.png](https://files.readme.io/dc33feec09fe551700586b9778a037fa0f5d610224944aea5a0fe56a6d288043-360017400878.png)

**To configure the integration with Airship:**

Minimum requirements - AppsFlyer SDK:

* Android – version 2.3.1.18 and above
* iOS – version 3.3.3 and above

Minimum requirements - Airship SDK - Version 13.1.0 and above.

1. Integrating with Airship requires that the channelid (Airship's unique user identifier) is populated in AppsFlyer's SDK.

   * [More on Channel ID for iOS](https://docs.airship.com/platform/ios/segmentation/#airship-channel-ids).
   * [More on Channel ID for Android](https://docs.airship.com/platform/android/segmentation/#airship-channel-ids).

   This parameter is sent with every postback and enables the identification of each user. To perform this you must insert the following strings to your app code:

   CALLSTART::Note::

   #### Important Note

   Make sure the lines of code are inserted in the correct place – after Airship SDK is launched and before the start method is called on iOS or Android.

   CALLEND::

   AndroidiOS

   For more details about the  `setAdditionalData` method, click [here](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata).

   ```
   HashMap<String, Object> customData = new HashMap<String,Object>();
   String channelId = UAirship.shared().getChannel().getId();
   customData.put("channelid", channelId);
   AppsFlyerLib.getInstance().setAdditionalData(customData);
   ```

   For more details about the  `setAdditionalData` method, click [here](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata).

   ```
   let channelID = UAirship.channel().identifier
   print("My Application Channel ID: \(channelID)")
   ```
2. Get the App Key from Airship:
   1. Login to your Airship account at: [go.airship.com](http://go.urbanairship.com/)
   2. On the left menu, go to **Settings >** **APIs &****Integrations** and click **Airship API**.

      ![airship-appkey-en_us.png](https://support.appsflyer.com/hc/article_attachments/360017666917)
   3. Copy the App Key.
   4. In AppsFlyer, paste the App Key in the App Key field.
3. Get the Token from Airship:
   1. Login to your Airship account at: [go.airship.com](http://go.urbanairship.com/)
   2. On the left menu, go to **Settings >** **APIs &****Integrations** and click **Tokens**.

      ![airship-token-creation-1.png](https://support.appsflyer.com/hc/article_attachments/360017480697)
   3. Click **Create Token**.

      ![airship-token-creation-2.png](https://support.appsflyer.com/hc/article_attachments/360017549138)
   4. Enter token name and select the role.
   5. Click **Create token**.
   6. In AppsFlyer, paste the Token in the **Token Authentication** field.

### Default postbacks

AppsFlyer can send automatic postbacks to Airship following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

![urban_airship_msc_new_3.png](https://support.appsflyer.com/hc/article_attachments/360001900305)

Select **Events attributed to any partner or organic** to send postbacks for any user that downloads the app to Airship.

Once you have saved the configuration, AppsFlyer sends the following data to Airship for every organic and non-organic install:

* Device ID (IDFA / Google Advertising ID)
* Media Source
* Campaign name

## Attribution link tab

Attribution Links are not available for Airship.

## Cost tab

Cost data is not supported in the integration with this partner.

## Ad revenue tab

Ad Revenue is not supported in the integration with this partner.

## Permissions tab

Permissions are not available for Airship.

## Set up and manage the attribution data in Airship console

In Airship, attributes are key-value pairs that you associate with your audience to help better target them with messages. Use attributes to target audiences with greater specificity than you would with tags.

Configure your AppsFlyer attribution data in Airship by [adding individual attributes to your project](https://docs.airship.com/partners/appsflyer/#setting-attributes-for-integration).