---
title: Google Ads (AdWords)—Integration setup for advertisers
excerpt: >-
  Integrate your Google Ads account with AppsFlyer to display attribution data
  from all of your campaigns.
metadata:
  keywords:
    - Integration
    - Google AdWords
    - Configuration
    - google
    - migration
    - Advertisers
    - google ads configuration
    - ads
    - google ads
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2017-05-17T19:16:15Z'
  edited_at: '2026-10-13T10:46:28Z'
  id: 115002504686
  locale: en-us
  section: Google Ads
  section_id: 6551205645457
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115002504686-Google-Ads-AdWords-Integration-setup-for-advertisers
---
Set up the Google Ads integration in AppsFlyer to measure and attribute installs and in-app events from your Google Ads campaigns. In AppsFlyer, this integration is named `googleadwords_int`, and attribution results are reported under the media source `googleadwords_int`.

## Google Ads attribution flow with advanced data sharing

![Google ads attribution flow.png](https://files.readme.io/1c49e06e48658a8cb60ae6a9e9a83c0fad751766f3d4ce9c6afdd041fb5e8579-small-38644882427537.png)

1. AppsFlyer sends install events to Google, as usual. If **Advanced Data Sharing** is ON, installs are sent with or without a device ID. If it's OFF, installs are sent **only when a device ID is present**.
2. Google attempts to claim the install either via a deterministic claim (ID match, using the device ID if available) or a non-deterministic claim (when device ID is not available), using probabilistic modeling.
3. In both cases, Google responds to AppsFlyer with a claim—either deterministic or non-deterministic.
4. AppsFlyer validates the non-deterministic claim using its own probabilistic modeling. Only validated claims are accepted.
5. After validation, the Google claim (if accepted) enters the attribution decision step, where AppsFlyer compares it against other potential attribution candidates (for example, other SRNs, click-based networks, organic). The install is attributed to the winning source based on AppsFlyer’s attribution logic and priority rules.
6. If the claim is accepted and selected as the winning candidate, the install is attributed to Google. In raw data reports, deterministic claims will show a [match\_type](/docs/raw-data-field-dictionary#attribution::cecc12c5) of `srn`, while non-deterministic claims will show a match type of “`probabilistic`”.

## Configuring Google Ads attribution for advertisers

To start attributing Google Ads campaigns with AppsFlyer, follow these steps:

<Accordion title="Step 1: Verify ICM prerequisites">

Make sure the requirements below are met to support Google PMOD install claims on iOS via AppsFlyer. This is necessary for enabling Google’s On-Device Measurement (ODM). No SDK update is needed for Android.

1. [Update AppsFlyer’s iOS SDK](https://dev.appsflyer.com/hc/docs/install-ios-sdk) to **v6.17.9 or higher** (no additional SDK configuration is required).
2. For Google SDK update, one of the following:
   * **Google’s Firebase iOS** SDK **v11.14.0 or higher.** For more information, see [the Google documentation](https://github.com/firebase/firebase-ios-sdk/releases). **OR**
   * **Google ODM standalone** SDK. For more information, see [the Firebase documentation.](https://support.google.com/google-ads/answer/16384720)
3. Make sure that [IDFV](/docs/appsflyer-knowledge-base-glossary#idfv) is sent to AppsFlyer with every app open or in-App event.
4. Make sure the IP address is sent to AppsFlyer with every app open event. When IP masking is configured for the app, ICM might not work.

</Accordion>

<Accordion title="Step 2: Create the Google Ads Link ID (mandatory)">

Creating a link ID requires **Google administrative access** to the account. Follow the steps below or[the Google documentation](https://support.google.com/google-ads/answer/7365001?hl=en).

1. Log in to your Google Ads admin account.
2. From the top menu, click **Tools and settings**.
3. Under the **Setup** menu, select **Data manager** and click **+ Connect Product**.
4. In the **Data sources** search bar, type "Third-party app analytics", select it, and click **Continue**.
5. Click **Create link ID**.
6. Select **AppsFlyer** as your app analytics provider.
7. Select the platform, Android or iOS.
8. Find your app and select it.
9. Click **Create link ID**.

</Accordion>

<Accordion title="Step 3: Set up Google Ads on AppsFlyer (mandatory)">

**(Any member in AppsFlyer's account)**

1. In AppsFlyer, from the side menu, select**Collaborate**>**Partner Integrations > Marketplace** tab.
2. Search for **Google Ads**.
3. Click I**ntegrate**. You’re directed to the integration setup page.
4. From the **Integration** tab, turn on **Activate partner**.  
   **Note:** The toggle must stay on ([activated](/docs/partner-activation-deactivation)) for as long as you work with the partner[.](/docs/partner-activation-deactivation)
5. Paste the **Link ID** you copied in the previous step.
6. Decide whether or not to turn on [**Non EU users**](/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users).

   ![non eu usrs.png](https://files.readme.io/f77a449ffaf508b8fe27b4ead44aa511354572dd4ecf82509a2157ca2f08edfa-30759261958673.png)
7. Turn **Advanced data sharing** ONorOFF. When ON Google Ads receives postbacks and events with device-level identifiers for all devices, including devices that have not made their Advertising ID  (IDFA or Google advertising ID)  available.

   Furthermore, when **Advanced Data Sharing** is ON, AppsFlyer attributes these events. When OFF, only postbacks and events from devices with an IDFA are sent and attributed.
8. Configuring **Install attribution**:
   1. Set the **Install click-through lookback window**.  
      Select the lookback window units (hours or days) and set the slider to the desired value. We recommend setting the lookback window to 30 days to match with Google Ads.
   2. [Optional] If you run pre-registration campaigns for Android apps, set the **Pre-registration campaign lookback window** (default is 90 days). This slider determines the lookback window for attributing installs to pre-registration campaigns.
   3. Enable **Install view-through attribution.**
   4. Select the lookback window units (hours or days) and set the slider to the desired value. We recommend setting the view-through lookback window to 1 day to match with Google Ads.  
      **Note:** Google doesn't send claims for iOS app impressions. The install view-through attribution toggle and the lookback window slider are no longer relevant for iOS apps.

      ![](https://files.readme.io/a6f05b9f92abf6dfdbaafc248c0381bfe063086daa10727dc088d484c1b38f0b-30759221879825.png)
9. The **Reinstall attribution** toggle is turned on by default for new integrations. Reinstall attribution lets you measure users who reinstall your app during their re-attribution window.

   No separate lookback window configuration is needed, as reinstall attribution uses the values from your install attribution settings. For more information, see [Measure reinstalls](/docs/measure-reinstalls).

   > 📘 **Important!**
   >
   > A reinstall conversion data is **presented as a session\_start** on Google Ads dashboard. In AppsFlyer, it is attributed and seen as a re-attribution.

10. Configure **Re-engagement attribution**:
    1. [Enable retargeting in App Settings](/docs/app-settings#reengagement-attribution).
    2. Enable re-engagement attribution in Google Ads integration settings
    3. Set the **Re-engagement click-through lookback window**, which is the period of time, starting from an ad click, during which the app must be launched for the click to be recorded as a re-engagement. Select a lookback window in hours or days and set the slider to the desired value.
    4. Enable **Re-engagement view-through attribution**.  
       **Note:** Google doesn't send claims for iOS app impressions. The re-engagement view-through attribution toggle and the lookback window slider are no longer relevant for iOS apps.
    5. Set the **Re-engagement view-through lookback window**, which is the period of time, starting from an ad impression, during which the app must be launched for the impression to be recorded as a re-engagement. Select a lookback window in hours or days and set the slider to the desired value.
    6. Set the **Re-engagement window**. This is the period when the user's in-app events are attributed to the retargeting media source, following either a click or an impression. You can set the value in days (1-90), hours (up to 23), or even lifetime. The default is 30 days.

       ![](https://files.readme.io/221a5489e91a15f1d9e4db9ab8f7cbff9e47dc1b50b0f7b43323096b26008870-30759261966225.png)
11. If you have a [Google Ads iOS app asset](https://support.google.com/google-ads/answer/2402582?hl=en) (formerly known as app extension):  
    To get attributions from the ad link, go to the [**Attribution link**](/docs/set-up-an-integrated-partner#attribution-link-tab) tab, create an AppsFlyer single-platform attribution link, and insert it into the Google Ads app asset.  
    **Note:** Make sure to add a static campaign name (mandatory).

    ![](https://files.readme.io/6b7513829fb3abbaab75942e3612760f39f6ae6502064eac1f31b0783a63e95b-30759221884561.png)
12. Go to the **Cost** tab.
13. Turn on **Get cost, clicks and impressions data**.
14. Click the **Connect Google Ads** button, and log into your Google account to get all your Google Ads campaign costs on AppsFlyer. [More details here](/docs/google-ads-adwords-cost-and-ad-revenue).
15. Click **Save**.

> 📘 **Stop!**
>
> * To view AppsFlyer attributions for installs and re-engagements in Google Ads, make sure to import the following AppsFlyer events:
>   * "First open" (for installs)
>   * "Session start" (for re-engagements)
> * You MUST go through [step 4](#h_01HACTC1H5GV04KFM29NCCK8J2) to see Google Ads installs in AppsFlyer. If you also need to map your in-app events to Google Ads, go through [step 5](#h_01HACTC1H50DDS3WCZ9DCHKN0P) first.

</Accordion>

<Accordion title="Step 4: Import your app conversions (mandatory)">

> 📘 **Important!**
>
> For Google Ads to register your new conversions, you must**launch your app and perform your mapped in-app events** at least once. To test iOS apps, you must collect IDFA to see the event. It may take up to 6 hours until the event conversions are added to the queue. Once they are added you can import them, and the new conversions change status from “No recent conversion” to “recording conversion".

This step requires **Google administrative access** to the account to create a link ID.

Follow the steps described in the [Google Ads Help documentation](https://support.google.com/google-ads/answer/7382633?sjid=11699141105296914680-EU). Take note of the following:

* Set the **first\_open** event as a conversion event for all your apps (required for install measurement).
* Set the **session\_start** event as a conversion event if you plan to measure re-engagements with Google.
* Repeat this process for each in-app event you want to measure with Google.

  > 📘 **Note**
  >
  > If the Partner Event identifier in Google Ads has been changed or is labeled as CUSTOM, while the corresponding event name has been modified in AppsFlyer, you will need to re-import the data.

* After finishing the process, you can see your third-party conversion events on the **Conversions** > **Summary** page. If an event doesn't appear in the list, or it has been removed from the Google Ads conversion list
  1. Click **View all conversion actions**. The **Status** filter appears.
  2. Click **Status** and select **All** to see all events, including disabled and removed events.
* Make sure your "include in conversions" setup is aligned with your campaign goals in Google Ads. For more information, consult with your Google representative or refer to the [Google documentation on conversion settings](https://support.google.com/google-ads/answer/4677036?hl=en&co=ADWORDS.IsAWNCustomer=false).

Congratulations! You're now measuring Google Ads mobile campaigns with AppsFlyer!

</Accordion>

<Accordion title="Step 5: Map your in-app events (recommended)">

**(Any member attached to the AppsFlyer's account)**

![In-app_event_postbacks_en-us.png](https://files.readme.io/fbeef1b9d6f4462750d849878045d31b4a6614a9f36d20cd9c6f69d91a34f65a-30759221886609.png)

1. Go to the **Integration** tab and scroll down to the **In-app event postbacks** section.

   > 📘 **Note**
   >
   > When enabling the Google Ads in-app events mapping for an app **for the first time:**
   >
   > * The **af\_app\_opened** event is automatically defined and mapped to **session\_start** (if not, add it manually).
   > * Under **for users from**, you must select **All media sources, including organic** for each event to enable Google Ads to receive these events. After the integration was set successfully, you are able to change this selection for any event.

2. Turn on **In-app event postbacks**.
3. Click **Add event** to add an SDK or server-to-server event to the list.
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events)</li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined in Google Ads. Select the most suitable pre-defined AppsFlyer event from the drop-down box. |
| **for users from** | Select the sending option for the event:<ul><li>**This partner only**: Send postbacks only when this event is attributed to Google Ads.</li><li>**All media sources, including organic**: Send postbacks for events attributed to any partner and organic events.</li></ul> |
| **including** | <ul><li>**No data (default)**: Send only the event itself without the event value.</li><li>**Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</li><li>**Values without revenue**: Send all the parameters **excluding** the revenue value.</li></ul> |

5. Click **Save integration**.
6. After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner.
   1. From the top-left corner, under the partner name, click the app name to open the list of apps.
   2. Select a different app from the drop-down list.
   3. Repeat the integration steps for the selected app.

</Accordion>

> 📘 **Tip**
>
> The Google Ads API integration automatically includes the Google Ads remarketing feature. By completing this integration and sending events to Google Ads you are able to create remarketing audience lists in Google Ads without any additional integrations.

## Granting permissions to Google Ads team members

You can grant Google Ads [permissions to access certain data in your account.](/docs/set-up-an-integrated-partner#permissions-tab) You can do this in the Google Ads configuration page under the Permission tab for each one of your apps.

To be able to get these permissions and access your app, your Google Ads representative must be a team member of Google Ads’ partner account on AppsFlyer.

Because of Google’s privacy requirements, Google can add new team members to its AppsFlyer partner account only when it’s explicitly requested by an advertiser.

To grant a Google Ads team member access to your app, do the following:

1. Fill out and submit [this form](https://docs.google.com/forms/d/e/1FAIpQLSfJmwEPxy4bXw0mEsKfJ3D5dZmRZgHS3LCiyoEFsZRos0jWIQ/viewform) to request your account manager to be added to Google’s partner account on AppsFlyer.
2. Wait for the confirmation from Google Ads that your GA account manager has been added.
3. Go to **Configuration** > **Active Integrations** > **Google Ads** > **Permissions**, and add your account manager email to the list of team members.
4. Activate the permissions you want to grant your Google Ads account manager.

Read more about [providing permissions to Ad networks](/docs/set-up-an-integrated-partner#permissions-tab).

## Enabling Google Ads attribution for agencies

AppsFlyer supports agency configurations with Google Ads. It is essential that the advertiser and the agency have separate Google Ads accounts to enable AppsFlyer to correctly attribute the data. For details, see [Agency configuration for the Google Ads integration](/docs/google-ads-adwords-integration-setup-for-agencies).

## Running with multiple Google Ads accounts

AppsFlyer supports working with multiple Google Ads accounts for the same app. This is performed through sharing the Link ID in Google Ads and importing the events into each Google Ads account.

For further details, see the [Google documentation on sharing your Google Ads Link ID](https://support.google.com/google-ads/answer/7365001).

## iOS app campaigns

**Note**: This section applies to app campaigns for installs and **not** app campaigns for engagement.

On January 27, 2021, [Google announced policy updates](https://blog.google/products/ads-commerce/preparing-developers-and-advertisers-for-policy-updates/) to accommodate iOS 14 release.

Since ATT enforcement began, Google iOS apps do not prompt for ATT, and therefore Google Ads products [stopped using](https://support.google.com/google-ads/answer/10417364) device identifiers (IDFA) that fall under ATT, except for the YouTube app which supports the ATT prompt.

To preserve reporting and campaign optimization, Google expanded modeled conversions to iOS 14+ traffic.

Since modeled conversions are not reliant on device IDs, starting with the iOS14.5 release, the iOS install app campaign inventory logic employed by Google is as follows:

* iOS ACI Search inventory is not attributed by device ID. This follows Google’s January 24, 2020 policy.
* iOS ACI Display inventory can be attributed when a device ID is present, provided that both the advertiser app and the publisher app have user consent.
* Any iOS ACI campaign can be attributed through ICM. This applies when the device ID is unavailable in the advertiser app, the publisher app, or both.
* Google currently claims only clicks on iOS. It does not claim impressions.

## Using deferred deep linking in App campaigns

**What is a deep link and how does it work?**

When a potential user clicks on a feed, they are redirected to the app page. After the user installs the app and launches it, the SDK supplies the specific product details (for example running shoes) with deferred deep linking. The app developer uses this data to deliver the relevant user experience within the app.

**Deferred deep linking in Google**

[Google feeds in App campaigns](https://support.google.com/google-ads/answer/9959794?hl=en&ref_topic=10011599) or [ad group deferred deep linking](https://support.google.com/google-ads/answer/12373847?) enables you to create a smooth content-specific experience for new mobile users. Google enables deep links to be set either in the feed or the ad group—and AppsFlyer supports both cases for deferred deep linking.

**To enable deferred deep linking with Google Ads:**

1. Make sure to use [GCD](/docs/conversion-data-payloads-and-scenarios#re-attribution-with-deferred-deep-linking) to receive the `af_dp` parameter in the AppsFlyer SDK.
2. In Google, [set up feeds](https://support.google.com/google-ads/answer/9958973?hl=en&ref_topic=10011599) or [set ad group level deferred deep linking](https://support.google.com/google-ads/answer/12373847?).
3. In AppsFlyer, Go to **Configuration** > **Active Integrations**. Select **Google Ads (Adwords)**.
4. In the **Integration** tab, turn on **Deferred deep linking with Google Ads.**
5. Click **Save integration**.

The Google Ads deferred deeplink value is only returned by Google for deterministic matches, based on device ID, and is not supported for probabilistic (ICM) matches.

## Google Ads parameter mapping

The following table describes the parameter mapping between Google Ads and AppsFlyer. Note that advertisers can't add personalized parameters to any Google Ads campaigns.

| **Network type** | **Search** | **Display** | **YouTube** |
| --- | --- | --- | --- |
| Channel (`af_channel`) | See table below, [How to populate the `Channel` parameter](/docs/google-ads-adwords-integration-setup-for-advertisers#populate-the-channel-parameter) |  |  |
| Campaign (`c`) | Yes | Yes | Yes |
| Campaign ID (`af_c_id`) | Yes | Yes | Yes |
| Adset (`af_adset`)  <br />Populated by the `ad_group_name` parameter.  <br />If this parameter is null, AF populates `af_adset` with `ad_group_id`. | Yes | Yes | Yes |
| Adset ID (`af_adset_id`) populated by Google `ad_group_id` parameter | Yes | Yes | Yes |
| Ad (`af_ad`). | N/A | N/A | N/A |
| Ad ID (`af_ad_id`)  <br />Populated by Google's `creative_id` parameter. | Yes | Yes | Yes |
| Ad Type (`af_ad_type`) | Yes* | Yes* | Yes* |
| Site ID (`af_siteid`) | GoogleSearch/  <br />SearchPartners | N/A | YouTubeVideos/  <br />VideoPartners |
| Keywords | N/A | N/A | N/A |

### Populate the `Channel` parameter

Google Ads doesn't send the `Channel(af_channel)` parameter. AppsFlyer determines how to populate this parameter for campaign types received from Google Ads, according to the following rules:

<table><thead><tr><th colspan="2">Campaign type <strong>AND</strong> Network type logic:</th><th rowspan="2"><kbd>Channel</kbd> parameter</th><th rowspan="2">Example</th></tr><tr><th>campaign_type</th><th>network_type</th></tr></thead><tbody><tr><td><kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Shopping</kbd>, or <kbd>Hotel</kbd></td><td>All network types</td><td><kbd>campaign_type_network_type</kbd></td><td>channel = <kbd>ACI_Search</kbd></td></tr><tr><td><p><strong>Not:</strong></p><p><kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Shopping</kbd>, or <kbd>Hotel</kbd></p></td><td><kbd>Display</kbd></td><td><kbd>network_subtype</kbd></td><td>channel = <kbd>mGDN</kbd></td></tr><tr><td><p><strong>Not:</strong></p><p><kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Shopping</kbd>, or <kbd>Hotel</kbd></p></td><td><p><strong>Not:</strong></p><p><kbd>Display</kbd></p></td><td><kbd>network_type</kbd></td><td>channel = <kbd>Search</kbd></td></tr></tbody></table>

For more information on what ad types are available in Google's response, see the [Google request and response specifications](https://developers.google.com/app-conversion-tracking/api/request-response-specs).

> 📘 **Note**
>
> When Google attributes an install through probabilistic attribution (ICM), Google doesn’t share the `network_type` with AppsFlyer. As a result, the network type is missing, and the channel value is `ACI_` (without a suffix).

### Campaign type: app campaigns

#### Changes to campaign names by Google Ads

| Until February 15, 2021 | Starting February 23, 2021 |
| --- | --- |
| UAC | ACI |
| UACE | ACE |
| UACPre | ACPRE |

**Note:** Campaign name type is set according to the click or impression date, not the install date.

### Engaged view parameter in raw data reports

An engaged view is a user impression of a video ad that lasted more than 10 seconds. It has the same attribution priority as a click.  For Android, engaged views are displayed in raw data reports as `engaged_view` under the  `Engagement Type` and `Sub Param 5` parameters.   
Engaged views are counted if they occur within the defined click lookback window in AppsFlyer, with a maximum limit of 3 days.

> 📘 **Important!**
>
> * Google is an SRN (Self Reporting Network). For more information about how the attribution flow works for these networks, see [Self-reporting networks (SRNs)](/docs/self-reporting-networks-srns).
> * AppsFlyer can present any campaign information that is provided by Google. The campaign type (Search, Video, Display) and associated information is determined by Google. For more information, see the [Google request and response specifications](https://developers.google.com/app-conversion-tracking/api/request-response-specs).

## Send complex in-app events to Google Ads

To send complex in-app events – events with multiple items – to Google Ads, we recommend using the new `af_order_info` event object. For more information, see [Item-level order data for ad networks (af\_order\_info)](/docs/item-level-order-data-for-ad-networks-af-order-info).

## Optimize Google Ads campaigns for conversions without device ID

Beginning with iOS14.5+ and Android 12+, Google Ads introduced several identifiers. These identifiers are used for deterministic attribution of conversions without device IDs:

| Identifier | Available from | Source | Operating system | Used for | Data granularity |
| --- | --- | --- | --- | --- | --- |
| gclid | December 2021 | Google Play referrer | Android | Installs/ re-installs | User-level |
| gclid | December 2021 | Deep link URL | Android + iOS | Re-engagements | User-level |
| gbraid | March 2021 | Deep link URL | iOS | Re-engagements | Aggregate |
| odm\_info | November 2025 | AppsFlyer SDK / S2S | iOS | Installs / re-installs | Aggregate |

In Google Ads and AppsFlyer, advertisers can receive campaign-level data for traffic without device IDs for re-engagement, installs, and re-attribution activity. However, ad-set and ad-level data are not shared by Google.  
**No action is needed from the advertiser to enable receiving these parameters.**

### Data visibility by operating system

**Android apps:**

In AppsFlyer and Google Ads, advertisers can receive full campaign data for traffic without device IDs – both for installs and re-engagements.

**iOS apps:**

In Google Ads and AppsFlyer, advertisers can receive full campaign data for traffic without device IDs for their re-engagement activity.

## Advertising without the Firebase SDK

When advertising with Google Ads without the Firebase SDK implemented, the following limitations apply.

| Limitation | Details |
| --- | --- |
| tROAS not supported | tROAS (target return on ad spend) optimization is only available when using Firebase SDK revenue events. AppsFlyer revenue events, and those from all other MMPs, are not eligible for this optimization. |
| Audience exclusion not supported | Advertisers can only exclude users from App campaigns when the campaign is optimized toward Firebase SDK events, not MMP events. |

## Google probabilistic attribution (ICM) traits and limitations

| Limitation | Details |
| --- | --- |
| Attribution scope | Supported for **installs and re-attribution only**; does **not** support re-engagements. |
| Claim data included | Google claims include(in most cases):<ul><li>**Campaign name**</li><li>**Campaign ID**</li><li>**Ad group (Adset) name**</li><li>**Ad group (Adset) ID**</li></ul>Does not include **ad information.** |
| Channel field | No network type or subtype provided; the **Channel** field will contain a partial value: `ACI_`  <br />For more information about “Channel” logic, see [How to populate the `Channel` parameter](/docs/google-ads-adwords-integration-setup-for-advertisers#populate-the-channel-parameter). |
| iOS ODM regional support | **Not supported** in the EU, UK, and Switzerland |
| Aggregated Advance Privacy (AAP) | When the  [AAP](/docs/apply-aggregated-advanced-privacy-framework) (Aggregated Advanced Privacy) toggle is turned **ON** in the iOS app settings, Google-attributed data in the raw data reports is shown as restricted. To view Google non-consented data, make sure the AAP toggle is **OFF**. |
| Attributed touch time | Google probabilistic claims timestamp is rounded to 15-minute intervals (00:00, 00:15, 00:30, etc.) |
| IP masking | Using IP masking may impact ICM performance. Google recommends disabling IP masking, as it can affect Google Ads measurement and performance. See [Apply IP masking to user data](/docs/apply-ip-masking-to-user-data#ip-masking). |
| IDFV | Google requires sending [IDFV](/docs/appsflyer-knowledge-base-glossary#idfv) (when available) with installs, app opens, and in-app events, to maximize ICM performance. |

<span id="h_01HDP0SBEE75MAT4A4S9E7Y7FF"></span>**See also:**

* For iOS 14-related considerations, see [Google Ads SKAdNetwork interoperability with AppsFlyer](/docs/get-skan-postback-data-from-google-ads).

<div data-zendesk-anchors="google-icm-attribution-flow-with-advanced-data-sharing=google-ads-attribution-flow-with-advanced-data-sharing h_01K0VKGRK7XXC4GNF6B9X76M4T=google-ads-attribution-flow-with-advanced-data-sharing h_01HACTC1H5MANBCRWYQPNW5CC2=configuring-google-ads-attribution-for-advertisers h_01HACTC1H5R995RXYRFQBFHRF1=important h_01HACTC1H5EFJKV6AXNSTNFZA4=stop h_01HSX7TJC7PQ0ATM1J86Z4HMYJ=important-1 h_01KA6S8V6CKRATXHZQZ4YN7V9R=note h_01HACTC1H58WHJDBN2DRQAZKGB=note-1 h_01HACTC1H5Z3XXS1MGBS4WYJBV=tip h_01HACTC1H5PAY95M4H1A6WTSEF=granting-permissions-to-google-ads-team-members h_01HACTC1H5QE93EAYYVVDQV2WC=enabling-google-ads-attribution-for-agencies h_01HACTC1H5Z8B15RHQ75HVV2RP=running-with-multiple-google-ads-accounts h_01HACTC1H5X567H6A8M3FWCTAN=ios-app-campaigns h_01HACTC1H57HJZNAGDKSQD6MVC=using-deferred-deep-linking-in-app-campaigns h_01HACTC1H6P1A2E160Z6GAGZZS=google-ads-parameter-mapping how-to-populate-the-channel-parameter=populate-the-channel-parameter h_01HACTC1H6TPTDDFSMPQ9YVMDY=populate-the-channel-parameter h_01KEYE1W4VJYXYHY4FP1KN3SP9=note-2 h_01HACTC1H6CEGD2E3HXHWFWBRB=campaign-type-app-campaigns h_01HACTC1H6A028HKVXJ66MCF6M=changes-to-campaign-names-by-google-ads h_01HACTC1H6Q6WCTK4Z9RGV6PA4=engaged-view-parameter-in-raw-data-reports h_01HACTC1H62HC36C08ZBFZ05XS=important-2 h_01M20SN9DCHRQP8TD5Q2Z00CWQ=send-complex-in-app-events-to-google-ads h_01HACTC1H6EFDVN9N89Y17HDFR=optimize-google-ads-campaigns-for-conversions-without-device-id h_01HACTC1H6WZNMVJK479M5KJYF=data-visibility-by-operating-system h_01_advertising-without-firebase-sdk=advertising-without-the-firebase-sdk google-icm-traits-and-limitations=google-probabilistic-attribution-icm-traits-and-limitations h_01K0XMCXSS5MKY90DZWJTNVBBS=google-probabilistic-attribution-icm-traits-and-limitations" />
