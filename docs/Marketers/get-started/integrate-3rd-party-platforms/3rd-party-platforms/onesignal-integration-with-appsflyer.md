---
title: OneSignal integration with AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2020-11-29T08:11:41Z'
  edited_at: '2026-08-14T16:22:59Z'
  id: 360015926437
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360015926437-OneSignal-integration-with-AppsFlyer
---
> **At a glance:** OneSignal is the market-leading push notification and in-app messaging provider, supporting over 1 million developers and marketers with a best-of-breed engagement platform.

![onesignal-logo-stack__3_.png](https://files.readme.io/49c50c481c00391f25cf8cc7eb2c35cc166f6a88a10db9120769a7d11affa26a-13013733757841.png)

OneSignal delivers 8 billion messages every day across the globe. Powered by superior architecture and an easy-to-use platform, the OneSignal delivers messages faster, more efficiently, and at a greater scale than any other solution in the world. Learn more at [onesignal.com](https://onesignal.com/?utm_medium=partner&utm_source=appsflyer)

> 🚧 **Important**
>
> **Important!**
>
> <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions#media-source-restrictions">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up OneSignal

The integration with OneSignal includes inserting a few lines of code to the AppsFlyer SDK in your app and then activating the integration in AppsFlyer.

### Set up the AppsFlyer SDK

When using Android, integrating with OneSignal requires that the OneSignal Player ID (OneSignal unique user identifier) is populated in AppsFlyer Android SDK. This parameter is sent with every postback and enables the identification of each user.

**To set up the AppsFlyer Android SDK:**

1. Make sure that the SDK version you use is 2.3.1.18 and above.
2. Insert the following lines of code in your app's code - [after OneSignal SDK was launched](https://documentation.onesignal.com/docs/android-sdk-setup) and before the initialization code for AppsFlyer SDK.
   * For Android devices using OneSignal SDK version 3.x.x:

     ```
     OSPermissionSubscriptionState status = OneSignal.getPermissionSubscriptionState();

               String deviceId = status.getSubscriptionStatus().getUserId();

                 customData.put("onesignalCustomerId", deviceId);
     ```
   * For Unity SDK:

     ```
     var status = OneSignal.GetPermissionSubscriptionState();

               String deviceId = status.subscriptionStatus.userId;

                 customData.put("onesignalCustomerId", deviceId);
     ```
   * For Android devices using OneSignal Native SDK version 4+:

     ```
     OSDeviceState device = OneSignal.getDeviceState();

               String deviceId = device.getUserId();

                 customData.put("onesignalCustomerId", deviceId);
     ```

**To set up the AppsFlyer iOS SDK:**

1. Make sure that the SDK version you use is 2.3.1.18 and above.
2. Insert the following lines of code in your app's code - [after OneSignal SDK was launched](https://documentation.onesignal.com/docs/android-sdk-setup) and before the initialization code for AppsFlyer SDK.
   * For iOS devices using OneSignal SDK version 2.x.x:

     <Tabs>
     <Tab title="Swift">

     ```
     let status: OSPermissionSubscriptionState = OneSignal.getPermissionSubscriptionState()
     if let deviceId = status.subscriptionStatus.userId{
         customData.put("onesignalCustomerId", deviceId);
     ```

     </Tab>

     <Tab title="Objective-C">

     ```
     OSPermissionSubscriptionState* status = [OneSignal getPermissionSubscriptionState];
     NSDictionary* CustomDataMap = [[NSDictionary alloc] initWithObjectsAndKeys:status.subscriptionStatus.userId, @"onesignalCustomerId", nil];
     [[AppsFlyerLib shared] setAdditionalData:CustomDataMap];
     ```

     </Tab>
     </Tabs>

   * For iOS devices using OneSignal Native SDK version 3+:

     <Tabs>
     <Tab title="Swift">

     ```
     if let deviceState = OneSignal.getDeviceState() {
         let deviceId = deviceState.userId
         customData.put("onesignalCustomerId", deviceId);
     ```

     </Tab>

     <Tab title="Objective-C">

     ```
     OSDeviceState *deviceState = [OneSignal getDeviceState];
     NSString *deviceId = deviceState.userId;
     NSDictionary* CustomDataMap = [[NSDictionary alloc] initWithObjectsAndKeys:deviceId, @"onesignalCustomerId", nil];
     [[AppsFlyerLib shared] setAdditionalData:CustomDataMap];
     ```

     </Tab>
     </Tabs>

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below:

<div id="integration-tab" />

<Accordion title="Integration tab">

![onesignal-integration-tab.png](https://files.readme.io/95ec88041360d492367ed383aa3242bebe1cd5c5abcff8fba64e7888f0a9c052-360017329277.png)

The Integration Tab is divided into different sections as described below.

### Activate partner

Must be enabled for as long as you work with the partner.  
Learn more about <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation#activate-a-partner-integration">partner activation</Anchor>.

### General settings

#### OneSignal AppID

To connect your OneSignal account with AppsFlyer, enter your app ID in **OneSignal AppID** field.  
Your OneSignal app ID is available in the OneSignal platform under **Settings** > **Keys & IDs**.

![onesignal-app-id-en_us.png](https://files.readme.io/2801bce8ea7ef4be731d8429bd0408f432d4b5600fbd359e989b0013da56b93e-360015238678.png)

### Default postbacks

![onesignal-default-postbacks_en-us.png](https://files.readme.io/07e40365685543a318be8a16c9ea83638634d4a60333338eca0f76d140f84bef-360014377697.png)

AppsFlyer can send automatic postbacks to OneSignal following user installs. Use this section to define the source of the users that the postbacks are sent to for each event.  
Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#default-postbacks">default postbacks</Anchor>.

**To send postbacks for any user that downloads the app to OneSignal**, select **All media sources, including organic**.

**To complete the integration configuration,** click **Save Integration**.

Although all events are sent by AppsFlyer, organic installs are not counted by OneSignal and therefore are ignored by OneSignal API.

Once you have saved the configuration, AppsFlyer sends the following data to OneSignal for every organic and non-organic install:

* Media source
* Campaign name
* Device ID
* Ad ID

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for this partner.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is not applicable in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not applicable in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Permissions are not available for this partner.

</Accordion>

## View user attribution data in OneSignal

You can view attribution in the Segment Editor under the OneSignal tags either as the individual device level or when creating a segment to use in a campaign.

![onesignal-view-attribution_en-us.png](https://files.readme.io/ac23c9310cad560f692598127f3e9efb7c2b905efb6fd5de21efabe90bf58eea-360014377737.png)

<div data-zendesk-anchors="h_01H9HWJTEYDEZ8AGVQBHZZTP7K=setting-up-onesignal h_01H9HWJTEY71PTXR1YSAK709QT=set-up-the-appsflyer-sdk h_01H9HWJTEZC62F9JW1KD4Y1CYS=integration-tab h_01H9HWJTEZH60AEPE7AB43X4YG=activate-partner h_01H9HWJTEZJAK2PTF4HQP3DQ1X=general-settings h_01H9HWJTEZCNZX17K86H9KCRFN=onesignal-appid h_01H9HWJTEZ91KR3ZA8NX5BVZCF=default-postbacks h_01H9HWJTEZZYRBS6PPRBBQAXZ5=attribution-link-tab h_01H9HWJTEZNT0EHJ7G4SFRD8K5=cost-tab h_01H9HWJTEZS7TN4FCAN40QB1NT=ad-revenue-tab h_01H9HWJTEZEY5VKCKDZ1Q7APRG=permissions-tab h_01H9HWJTEZZTJFTZC1Z2A6F5QM=view-user-attribution-data-in-onesignal" />
