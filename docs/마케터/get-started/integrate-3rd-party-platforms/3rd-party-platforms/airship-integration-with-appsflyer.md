---
title: Airship integration with AppsFlyer
metadata:
  keywords:
    - Attribution
    - SDK
    - Configure
    - urban airship
    - Advertisers
    - Ad Networks
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
  created_at: '2015-12-16T11:31:38Z'
  edited_at: '2026-10-13T00:27:58Z'
  id: 207033976
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/207033976
---
> **At a glance:** Airship, an AppsFlyer integrated partner, provides the world’s leading mobile engagement platform, helping thousands of businesses of all sizes form a direct and lasting connection with their customers. With Airship, companies gain total control of their mobile footprint — apps, wallets, and user-level data — to deliver experiences that get noticed and drive action across mobile or any other customer touch-point.

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Airship

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below:

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to turn on **Activate partner** to enable the setup of the integration tab's parameters. **The toggle must be on for as long as you work with the partner**.  
Learn more about <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">partner activation</Anchor>.

### General settings

Airship connects with AppsFlyer via a unique App Key and Token. If you don't already have them, you can obtain it from Airship to continue with the integration, or see below for instructions how to obtain it.

<Image align="center" alt="airship-integration-tab.png" src="https://files.readme.io/dc33feec09fe551700586b9778a037fa0f5d610224944aea5a0fe56a6d288043-360017400878.png" />

**To configure the integration with Airship:**

Minimum requirements - AppsFlyer SDK:

* Android – version 2.3.1.18 and above
* iOS – version 3.3.3 and above

Minimum requirements - Airship SDK - Version 13.1.0 and above.

1. Integrating with Airship requires that the channelid (Airship's unique user identifier) is populated in AppsFlyer's SDK.

   * [More on Channel ID for iOS](https://docs.airship.com/platform/ios/segmentation/#airship-channel-ids).
   * [More on Channel ID for Android](https://docs.airship.com/platform/android/segmentation/#airship-channel-ids).

   This parameter is sent with every postback and enables the identification of each user. To perform this you must insert the following strings to your app code:

   > 📘 **Important Note**
   >
   > Make sure the lines of code are inserted in the correct place – after Airship SDK is launched and before the start method is called on iOS or Android.


   <Tabs>
   <Tab title="Android">

   For more details about the  `setAdditionalData` method, click <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">here</Anchor>.

   ```java
   HashMap<String, Object> customData = new HashMap<String,Object>();
   String channelId = UAirship.shared().getChannel().getId();
   customData.put("channelid", channelId);
   AppsFlyerLib.getInstance().setAdditionalData(customData);
   ```

   </Tab>

   <Tab title="iOS">

   For more details about the  `setAdditionalData` method, click <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">here</Anchor>.

   ```objectivec
   let channelID = UAirship.channel().identifier
   print("My Application Channel ID: \(channelID)")
   ```

   </Tab>
   </Tabs>

2. Get the App Key from Airship:
   1. Login to your Airship account at: [go.airship.com](http://go.urbanairship.com/)
   2. On the left menu, go to **Settings >** **APIs &** **Integrations** and click **Airship API**.

      <Image align="center" alt="airship-appkey-en_us.png" src="https://files.readme.io/c33611035d8dcadb73e41a3787690726608bddde55edbc38f34990c03948985d-360017666917.png" />
   3. Copy the App Key.
   4. In AppsFlyer, paste the App Key in the App Key field.
3. Get the Token from Airship:
   1. Login to your Airship account at: [go.airship.com](http://go.urbanairship.com/)
   2. On the left menu, go to **Settings >** **APIs &** **Integrations** and click **Tokens**.

      <Image align="center" alt="airship-token-creation-1.png" src="https://files.readme.io/b0c22d9844dbc93f7dd158a75916eca98404474a65be0c1528f83e6e4ac7b210-360017480697.png" />
   3. Click **Create Token**.

      <Image align="center" alt="airship-token-creation-2.png" src="https://files.readme.io/656f6f5a6eebe3ccd1a786f6abec62739633e4150722fec41bc1fbdea78f8275-360017549138.png" />
   4. Enter token name and select the role.
   5. Click **Create token**.
   6. In AppsFlyer, paste the Token in the **Token Authentication** field.

### Default postbacks

AppsFlyer can send automatic postbacks to Airship following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

<Image align="center" alt="urban_airship_msc_new_3.png" src="https://files.readme.io/394dd47ff26742092f3012e333f137d706f41bc85cd6875013d792ce7f36b01d-360001900305.png" />

Select **Events attributed to any partner or organic** to send postbacks for any user that downloads the app to Airship.

Once you have saved the configuration, AppsFlyer sends the following data to Airship for every organic and non-organic install:

* Device ID (IDFA / Google Advertising ID)
* Media Source
* Campaign name

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for Airship.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Permissions are not available for Airship.

</Accordion>

## Set up and manage the attribution data in Airship console

In Airship, attributes are key-value pairs that you associate with your audience to help better target them with messages. Use attributes to target audiences with greater specificity than you would with tags.

Configure your AppsFlyer attribution data in Airship by [adding individual attributes to your project](https://docs.airship.com/partners/appsflyer/#setting-attributes-for-integration).

<div data-zendesk-anchors="h_01H9FJYKH3V1TZ4GYEKKG46F2S=important h_01H9FJYKH3SWMNC8CRPPDQMCGQ=setting-up-airship h_01H9FJYKH4KQMK2N5BTTFTY076=integration-tab h_01H9FJYKH4NTCNVKBW9XSENFTP=activate-partner h_01H9FJYKH4MMRE57BNEBD0P5NT=general-settings h_01H9FJYKH4H93Q5S41HK7S4RD6=important-note h_01H9FJYKH44F4YQSEPKTGN7EYK=default-postbacks h_01H9FJYKH44S8F34YJ97TE32PM=attribution-link-tab h_01H9FJYKH47DYTR8T197CEXH0Z=cost-tab h_01H9FJYKH46AC5X7F6GAD9MQJG=ad-revenue-tab h_01H9FJYKH4N4T5JTGWHQC0A18Z=permissions-tab h_01H9FJYKH4Q09JSBJ25RRE02Y3=set-up-and-manage-the-attribution-data-in-airship-console" />
