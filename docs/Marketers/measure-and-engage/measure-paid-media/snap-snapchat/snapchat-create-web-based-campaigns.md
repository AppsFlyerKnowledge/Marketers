---
title: Snapchat—Create web-based campaigns
excerpt: >-
  Use Snapchat Ads Web campaigns to attribute web-to-app conversions from
  Snapchat Ads
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2025-11-27T14:39:44Z'
  edited_at: '2026-09-15T10:59:21Z'
  id: 41365000854161
  locale: en-us
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/41365000854161-Snapchat-Create-web-based-campaigns
---
## Overview

AppsFlyer supports integration with Snapchat Ads (`snapweb_int`) for User Acquisition web-based campaigns, allowing you to report attribution and conversion data directly through Snapchat's Events API. Snapchat can then utilize this data to optimize ad targeting, measure performance, and build custom audiences.

> 📘 **Important!**
>
> At present, the integration with Snapchat Web does not support sending re-engagement postbacks to CAPI.

### Prerequisites

Before activating the Snapchat Web integration, make sure you have a business account in œœœœ.

### How to create a Snapchat Ads web campaign

This article contains information and steps on how to set up a web campaign in Snapchat Ads for Mobile apps with AppsFlyer. The setup involves defining the integration between Snapchat Ads and AppsFlyer, setting the campaign configuration on both platforms, and creating landing pages with OneLink Smart Script or OneLink Smart Banners.

The setup process includes the following mandatory steps:

* [Set up Snapchat Ads web integration in AppsFlyer](#set-up-snapchat-ads-web-integration-in-appsflyer) (Required)
* [Set up AppsFlyer integration in Snapchat Ads](#set-up-appsflyer-integration-in-snapchat-ads) (Required)

And the following optional steps:

* [Create a landing page with OneLink Smart Script](#create-a-landing-page-with-onelink-smart-script) (Optional)
* [Create a landing page with OneLink Smart Banners](#create-a-landing-page-with-onelink-smart-banners) (Optional)

## Set up Snapchat Ads web integration in AppsFlyer

Start by activating the Snapchat Ads web integration. Then configure the postbacks that AppsFlyer sends to the Events API.

<div id="1-activate-the-snapchat-ads-web-integration" />

<Accordion title="1. Activate the Snapchat Ads web integration">

To activate the Snapchat Ads web integration:

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Partner Marketplace**.
2. Search for **Snapchat Web** and select it.
3. Click **Set up integration**. You’re directed to the **Active Integrations** setup page.
4. In the **Integration** tab, turn on **Activate Partner**. The toggle must stay on ([activated](/docs/partner-activation-deactivation)) for as long as you work with the partner.
5. Turn off **Advanced Privacy**(if you are setting an iOS app integration).
6. **Advanced Matching data sharing:** Turn on to share Advanced Matching fields, such as hashed email, hashed phone number, hashed first name, and hashed last name, with Snapchat, if these fields are included in the event information sent to AppsFlyer. For more information, see: [Advanced Matching Data Sharing](/docs/advanced-matching-data-sharing).
7. **Pixel ID:** Enter the Pixel ID. You can generate it or retrieve it from your Snapchat Ads Manager by following the instructions detailed in the [Snapchat Ads official documentation](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US)
8. **Access token:** Enter the access token. To generate it or retrieve it, follow the [instructions in the Snapchat Ads official documentation](https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted)

</Accordion>

<div id="2-enable-viewthrough-attribution" />

<Accordion title="2. Enable view-through attribution">

AppsFlyer supports view-through attribution for Snapchat Web campaigns when you use a [Smart Script](#create-a-landing-page-with-onelink-smart-script) or [Smart Banner](#set-up-smart-banners-landing-page)-enabled landing page. This enables probabilistic modeling (PMOD) attribution for app installs triggered by ad impressions, even when users do not click the ad.

If available, the `ScCid` will be included in the postback to Snapchat to enhance attribution fidelity.

**To enable Snapchat Web view-through attribution:**

1. In AppsFlyer, from the sidebar, open **Active Integrations** > **Snapchat Ads web**.
2. In the **Integration** tab, scroll to the **Install attribution** section.
3. Turn on **Install view-through attribution**.
4. **[optional]** Turn on **Cross-platform equal attribution priority** and set its lookback window. For more information, see [Enable equal priority for cross-platform impressions](/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions).
5. Open the **Attribution link** tab.
6. Scroll to the **View-through attribution** section and set the **view-through lookback window** (up to 24 hours).
7. Click **Save integration** to apply your settings.

</Accordion>

<div id="3-set-inapp-event-postbacks" />

<Accordion title="3. Set in-app event postbacks">

Installs are currently the only events that trigger automatic default postbacks for Snapchat Ads. For all other event types, you can create custom postbacks by mapping AppsFlyer events to Snapchat Ads events. These postbacks can be viewed in the Snapchat Ads manager.

To set in-app events postbacks, perform the following:

1. Turn on **In-app event postbacks**.
2. If required, set the In-app event postback window (read more about in-app event postback window configuration in general in [In-app event postback configuration](/docs/in-app-event-postback-configuration#in-app-event-postback-window)).
3. Click **Add event** to add an event to the list.
4. In the **AppsFlyer event**column, select the event name from the list. AppsFlyer receives the event's name either from the SDK integrated into your app or from server-to-server events.
5. In the **Mapped to Partner Event** column,select the most suitable predefined partner event from the list.
6. In the **For Users From** column, select **This Partner Only** to ensure that in-app event postbacks are sent only for events performed by users who originated from this partner.
7. In the **including** column, select whether to send events with their revenue values. See [Data to include in the postbacks](/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks).

   > 📘 **Note**
   >
   > * If you are setting a purchase event, set the **including** column to **Values and revenue**. Selecting any other option causes the postback to fail.
   > * Currently, you can set only the purchase event to include revenue.

8. [Optional] Click the **Add condition** icon to [set conditions](/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks) for an event.
9. Click **Save integration**.
10. [Optional] After you save the integration, and while you remain on the configuration page, you can integrate additional apps with the partner:
    1. From the top-left corner, select the app name under the partner name to open the list of apps.
    2. Select a different app from the list.
    3. Repeat the above steps for the selected app.

</Accordion>

## Set up AppsFlyer integration in Snapchat Ads

Perform the next steps in Snapchat Ads Manager.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Set the campaign type, objective, and goals">

You can choose any pre-defined INAPP event sent from AppsFlyer as your campaign goal, or choose “PAGE\_VIEW” if you want to optimize for mobile App Installs.

> 📘 **Warning**
>
> Make sure that you do not choose **App Events;** otherwise, Snapchat will claim those conversions using the SRN API, which can lead to misalignments in reporting and optimization.

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. Set destination URL">

1. Under **Destination,** in the **Website URL**field, enter the URL that serves as the destination for your ad. The URL should be for one of the following:
   * **Web landing page:** Using a landing page is recommended when:

     * You have an app on multiple platforms.
     * You want to use the landing page to give more information about your advertised product.
     * You want to use the landing page to collect more data.

     For all these use cases, create a [landing page with a Smart Script](#create-a-landing-page-with-onelink-smart-script) or [a Smart Banner](#create-a-landing-page-with-onelink-smart-banners).
   * **AF attribution links:** Using AF attribution links (OneLink, single platform, or cross-platform) is recommended when you want users to be redirected directly to the store to download the app without first visiting a landing page.
2. Click **Build a URL parameter** to add the URL parameters to the URL (whether it is a landing page URL or an AF attribution link).
3. Under **Custom parameters**, click **Add parameter**

   [![Screenshot 2025-11-26 at 8.56.29.png](https://files.readme.io/cb3ceba75974f7a57d7f26c3587fd0d0c401427d26fcacff40f2514981b9b02f-small-41366139737873.png)](https://files.readme.io/cb3ceba75974f7a57d7f26c3587fd0d0c401427d26fcacff40f2514981b9b02f-small-41366139737873.png)
4. Map the AppsFlyer parameters to their Snapchat values.
   * If your destination URL is **a landing page, a OneLink attribution link, or a single platform attribution link**, map the following AF parameters to their Snapchat counterparts:

| AF Parameter | Mapped Snapchat value |
| --- | --- |
| [`pid`](/docs/about-link-structure-and-parameters#pid) | `snapweb_int` |
| [`c`](/docs/about-link-structure-and-parameters#c) | `{{campaign.name}}`* |
| [`af_c_id`](/docs/about-link-structure-and-parameters#af_c_id) | `{{campaign.id}}`* |
| [`af_adset`](/docs/about-link-structure-and-parameters#af_adset) | `{{adSet.name }}`* |
| [`af_adset_id`](/docs/about-link-structure-and-parameters#af_adset_id) | `{{adSet.id}}`* |
| [`af_ad`](/docs/about-link-structure-and-parameters#af_ad) | `{{creative.name }}` |
| [`af_ad_id`](/docs/about-link-structure-and-parameters#af_ad_id) | `{{ad.id}}`* |
| [`af_channel`](/docs/raw-data-field-dictionary#attribution::1d1e08b5) | `{{site_source_name}}` |

     An example of the resulting URL should be:

     ```
     https://app.appsflyer.com/{app_id}?pid=snapweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r={https://Add-your-store-url.com}
     ```

     * If your app’s APK is NOT hosted in Google Play Store, add the [`af_r`](/docs/about-link-structure-and-parameters#af_r) parameter and map to it the store URL, e.g, `https://Add-your-store-url.com`

* If your destination URL is a **PC or a console store**, create the link by following the instructions in the table below. For additional information, see: [CTV, PC, and console platform direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links)

| Attribution link structure |  |
| --- | --- |
| Base URL | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| Mandatory path parameters | ▪ platformExample: steam  <br />▪ app\_idExample: 123456 |
| Mandatory query parameters | ▪ af\_media\_source  <br />▪ af\_campaign\_id  <br />▪ af\_r |
| Other parameters | [See all parameters](/docs/ctv-pc-and-console-platform-direct-attribution-links#parameters) |
| URL structure | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |

  Map the following AppsFlyer parameters to their Snapchat counterparts:

| AF Parameter | Mapped Snapchat value |
| --- | --- |
| `af_media_source` | `snapweb_int` |
| `af_campaign` ***** | `{{campaign.name}}`* |
| [`af_campaign_id`](/docs/about-link-structure-and-parameters#af_c_id) | `{{campaign.id}}`* |
| [`af_adset`](/docs/about-link-structure-and-parameters#af_adset) | `{{adSet.name }}`* |
| [`af_adset_id`](/docs/about-link-structure-and-parameters#af_adset_id) | `{{adSet.id}}`* |
| [`af_ad`](/docs/about-link-structure-and-parameters#af_ad) | `{{creative.name }}` |
| [`af_ad_id`](/docs/about-link-structure-and-parameters#af_ad_id) | `{{ad.id}}`* |
| [`af_channel`](/docs/raw-data-field-dictionary#attribution::1d1e08b5) | `{{site_source_name}}` |

  ***** To simplify campaign analysis, include the campaign type, web or mobile, as a prefix or suffix in the campaign name (e.g., campaign-name\_web)

  An example of cross-platform URL:

  ```
  https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=snapweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
  ```

  > 📘 **Note**
  >
  > Snapchat adds the `ScCid={{ScCid}}` to the destination URL automatically when the ad is clicked

  > 📘 **Note**
  >
  > For a comprehensive guide on the AF link parameters, see [Attribution link parameters](/docs/about-link-structure-and-parameters#attribution-link-parameters).


</Accordion>

## Create a landing page with OneLink Smart Script

**User journey:** The user clicks on a Snapchat ad and is directed to your mobile website. They land on a page with CTA buttons prompting them to download your app from one or more platforms. Clicking the button redirects the user to the store.

<div id="endtoend-data-flow" />

<Accordion title="End-to-end data flow">

[![](https://files.readme.io/215e3d98b36cacd37fd74480cb007ee1d395a4d5d0653318af7d6c71f35d8f31-41364969285521.png)](https://files.readme.io/215e3d98b36cacd37fd74480cb007ee1d395a4d5d0653318af7d6c71f35d8f31-41364969285521.png)

1. The Snapchat ad URL includes the `pid=snapweb_int` parameter. When the user clicks on the ad, an `ScCid` parameter is automatically appended to the clicked URL.
2. The User is redirected to the URL destination - a landing page containing a Smart Script.
3. When the landing page loads, Smart Script fires an impression to AppsFlyer containing the incoming URL parameters. The impression will allow view-through attribution from the web landing page. To learn about impressions and view-through attribution, see [here](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url).
4. Smart Script generates the outgoing URLs for the CTA buttons on the page based on the incoming URL parameters, including the `ScCid` parameter. The buttons can lead to:
   * Google Play and App Store via a OneLink attribution link.
   * Multiple platform stores (e.g., CTV, Epic, and Steam). In this use case, Smart Script generates a single platform attribution link for each platform, leading to the specified platform's store.
   * Downloading an APK file to the user's device.
5. When the user clicks the CTA button, the click is fired and registered in AppsFlyer.
6. The user is redirected to the store and downloads the app.
7. When the user opens the app, the install event is registered in AppsFlyer.
8. AppsFlyer attributes the install based on probabilistic modeling or deterministically if an [install referrer](https://www.appsflyer.com/glossary/install-referrer/) is available.
9. A postback containing the `ScCid` parameters and other event parameters are generated and sent to Snapchat via the Events API. Snapchat uses the `ScCid` parameter to identify the specific click, while the other parameters help optimize the campaign.

</Accordion>

<div id="set-up-a-smart-script-landing-page" />

<Accordion title="Set up a Smart Script landing page">

To set up your smart script Snapchat Ads campaigns, perform the following:

1. Set up the template for the campaign’s OneLink attribution links. For more information, see [How to create OneLink templates](/docs/create-a-onelink-template#create-a-onelink-template).
2. Create a smart script. For more information, see [How to create a OneLink Smart Script](/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script).

   > 📘 **Note**
   >
   > The instructions below outline the specific steps required to set up a Snapchat Ads campaign with Smart Script. For a comprehensive guide on how to set up Smart Script campaigns, see the [How to create a OneLink Smart Script](/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script) section of the [OneLink Smart Script V2 setup](/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script) article.

3. Make sure all relevant URL parameters are appended to the incoming URL. To review the parameters appended to the incoming URL, open Snapchat Ads Manager and check the URL parameters you set when creating the destination URL. For more information, see  [Set destination URL](#2-set-destination-url).
4. Map the incoming URL parameters required for the Snapchat Ads campaign to the outgoing URL parameters. Those parameters are sent to AppsFlyer when the user clicks the CTA button:
   * **PID**: Make sure that Smart Script takes the `pid=snapweb_int` parameter value from the incoming URL and maps it to the corresponding parameters in the outgoing URL.
   * **ScCid**: The `ScCid` parameter is required for successfully sending in-app events postbacks to Snapchat. The `ScCid` parameter should be mapped manually in the **URL parameter mapping** section of the **Smart Script** page:

     1. In **Mapping for**, select **Custom parameter**.
     2. In the **Outgoing URL parameter** and the **Incoming URL parameters,** enter **ScCid**.

        <br /><br />**Note**<br />


     #### Note

     To display in AppsFlyer raw data reports, you must also map the incoming `ScCid` parameter, separately from the outgoing `ScCid` parameter, to one of the outgoing `af_sub[1–5]` parameters.



</Accordion>

<div id="set-up-a-smart-script-crossplatform-landing-page" />

<Accordion title="Set up a Smart Script cross-platform landing page">

To set up your smart script Snapchat Ads campaigns for cross-platform landing pages, perform the following:

1. Set up the template for the campaign’s OneLink attribution links. For more information, see [How to create OneLink templates](/docs/create-a-onelink-template#create-a-onelink-template).
   * Enable your OneLink template for cross-platform attribution. For more information, see [Create a OneLink template for cross-platform attribution](/docs/set-up-cross-platform-links-for-multi-device-campaigns#create-a-onelink-templatefor-cross-platform-attribution).
2. Make sure all relevant URL parameters are appended to the incoming URL. To review the parameters appended to the incoming URL, open Snapchat Ads Manager and examine the URL parameters you set when building the destination URL. For more information, see [Set destination URL](#2-set-destination-url).
3. Decide for each incoming parameter the outgoing parameter to which it will be mapped. for example, the incoming `af_site_id` parameter in the incoming URL will be mapped to the  `af_site_id` parameter in the outgoing URL.
4. Determine the default value for the mandatory outgoing parameters that cannot be left empty.
5. Send your developer the following information:
   * Your incoming - outgoing parameter mapping. The developer will create a script that generates an outgoing direct URL based on the incoming-outgoing parameter mapping.
   * The parameters’ default values. The script will populate the outgoing URL parameters with the default values whenever there are no corresponding incoming URL parameter values.
   * If you are using a OneLink attribution link, send the domain and template ID to your developer. The developer uses this to create the outgoing OneLink URL. For example: `yourbrand.onelink.me/A1b2` or Branded domain example: `click.yourbrand.com/A1b2`
   * Send your developer the following Dev Hub links:
     * [Instructions and code examples](https://dev.appsflyer.com/hc/docs/create-direct-click-url) on how to create the outgoing direct URLs to the non-mobile platforms.
     * [A demo and instructions](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/) for creating a cross-platform landing page.

* Remind your developer to include the incoming `ScCid` parameter in the outgoing URL.

  > 📘 **Note**
  >
  > To display in AppsFlyer raw data reports, the incoming `ScCid` parameter must also be mapped (in addition to the outgoing `ScCid` parameter) to one of the outgoing `af_sub[1-5]` parameters.


</Accordion>

## Create a landing page with OneLink Smart Banners

**User journey:** The user clicks on a Snapchat ad and is directed to your mobile website. They land on a page, and a Smart Banner is displayed with a CTA to download the app from the App Store.

<div id="endtoend-data-flow::b905b9a5" />

<Accordion title="End-to-end data flow">

1. The Snapchat ad URL includes the `pid=snapweb_int` parameter. When the user clicks on the ad, an `ScCid` parameter is automatically appended to the clicked URL.
2. The User is redirected to the URL destination - a landing page containing a Smart Banner.
3. When the landing page loads, the Smart Banner fires an [impression](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url) event to AppsFlyer, which includes the incoming URL parameters. This impression enables view-through attribution for the landing page. To learn about impressions and view-through attribution, see [Create a custom impression URL](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url).
4. The Smart Banner generates the outgoing URL for the CTA button on the banner. The outgoing URL is based on the incoming URL parameters, including the `ScCid` parameter. The Smart banner can generate only OneLink-based links.
5. When the user clicks the Smart Banner CTA button, the click is fired and registered in AppsFlyer.
6. The user is redirected to the store and downloads the app.
7. When the user opens the app, the install event is registered in AppsFlyer.
8. AppsFlyer attributes the install based on probabilistic modeling or deterministically if the install referrer is available.
9. A postback containing the `ScCid` parameters and other event parameters are generated and sent to Snapchat via the Events API. Snapchat uses the `ScCid` parameter to identify the specific click, while the other parameters help optimize the campaign.

</Accordion>

<div id="set-up-a-smart-banners-landing-page" />

<Accordion title="Set up a Smart Banners landing page">

To set up your Smart Banners Snapchat Ads campaigns, perform the following:

1. Set up the template for the campaign’s OneLink attribution links. For more information, see [How to create OneLink templates](/docs/create-a-onelink-template#create-a-onelink-template).
2. Create a Smart Banner.

   > 📘 **Note**
   >
   > The instructions below outline the specific steps required to set up a Snapchat Ads campaign with Smart Banners. For a comprehensive guide on how to set up Smart Banners campaigns, see the [setup section](/docs/smart-banners-mobile-web-to-app-for-marketers#setup) of the [Smart Banners—mobile web-to-app (for marketers)](/docs/smart-banners-mobile-web-to-app-for-marketers) article.

3. Set the Smart Banner parameters for Snapchat Ads campaigns:

   * Make sure all relevant URL parameters are appended to the incoming URL.
   * To review the parameters appended to the incoming URL, open Snapchat Ads Manager and review the URL parameters you set when [creating the destination URL](#2-set-destination-url).

     <br /><br />**Note**<br />


   #### Note

   Most importantly the `pid=snapweb_int` and `ScCid` are available in the incoming URL to allow the Smart Banner to collect them. These two parameters are necessary for attribution and for sending postbacks to Snapchat Ads.



</Accordion>

## **View web-to-app attribution data**

Although web-based conversion events are sent to Snapchat under the original `snapweb_int` PID, they are reported in the AppsFlyer dashboard and raw data reports under the `snapchat_int` PID. This applies both to primary conversion events and to conversion assist events.

This unified reporting view enables you to analyze both web and app campaign performance in one place, including comprehensive mobile and web cost reporting.

### **View in the dashboard**

All Snapchat web-to-app attributions appear under `snapchat_int` in the Overview and Activity dashboards. This provides a single, consolidated view of campaign results across platforms. Use standard filters and breakdowns to compare app and web traffic within your Snapchat data.

### **View in raw data and API reports**

* **Raw data exports and API responses**include the `snapchat_int` PID in the `media_source` field for Google web activity. To verify web campaign setup details, refer to the `original_url` field that shows `snapchat_int` as the PID used during the creation of web campaigns.
* **Postback reports** show `snapweb_int` as the original media source to which the postback was sent.

## Traits and Limitations

| Trait | Remarks |
| --- | --- |
| Cost data | Cost data for Snapchat Ads (`snapweb_int`) web-based campaigns isn’t retrieved automatically. Instead, it must be imported manually using one of [two supported methods: email-based file upload or manual upload via the AppsFlyer UI](/docs/import-cost-data#procedures). This applies to all users, including ROI360 subscribers. |
| Clicks and impressions (temporary limitation) | Clicks and impressions for web campaigns are temporarily unavailable from Snapchat SRN (`snapchat_int`). |

<div data-zendesk-anchors="h_01KB2W28THC55F0AJ0KZJPQ6S5=overview h_01KB2W28THSST3148Y5Y07PJ7S=important h_01KB2W28THW7E6TRVTTHJZ9BP4=prerequisites h_01KB2W28THTST7HWTJA9TTGPGG=how-to-create-a-snapchat-ads-web-campaign h_01KB2W28THQJF8K4AWTRXNA3RX=set-up-snapchat-ads-web-integration-in-appsflyer h_01KB2W28TH6NZCGCJAN8K3WFGA=1-activate-the-snapchat-ads-web-integration h_01KB2W28TJ6XY7WKR4VC5XS7DS=2-enable-viewthrough-attribution h_01KB2W28TJGRKP3C50ZPQAWAS9=3-set-inapp-event-postbacks h_01KB2W28TJ14KC606KE82Q7BB7=note h_01KB2W28TJVZ1BX94SZYH1K5EM=set-up-appsflyer-integration-in-snapchat-ads h_01KB2W28TJ2R95JK7C1PQE644C=1-set-the-campaign-type-objective-and-goals h_01KB2W28TJ4BK88DVYJG4XYE0S=warning h_01KB2W28TJB1V382HD09M9Y0C3=2-set-destination-url h_01KB2W28TJT7QZ2P7AZ5X61ZXV=note-1 h_01KB2W28TJQA1TBXXQ7MA1F0CB=create-a-landing-page-with-onelink-smart-script h_01KB2W28TJ4J426HD3ZFHXAV4J=endtoend-data-flow h_01KB2W28TJR8S029FJ3Y81MG8Y=set-up-a-smart-script-landing-page h_01KB2W28TJBYHKYNQRMJ4ZGWYD=note-6 h_01KB2W28TJZMQEDSNVWRZCNXYD=note-4 h_01KB2W28TJT0TEFB97RXEGDVRM=set-up-a-smart-script-crossplatform-landing-page h_01KB2W28TJ6XWR7GW4SQQAKZH9=note-5 h_01KB2W28TJM0X7K5Z7M2120MT9=create-a-landing-page-with-onelink-smart-banners h_01KB2W28TKJZBNFR335SXKY6FC=endtoend-data-flow::b905b9a5 h_01KB2W28TKKA9NTQEC7ZA9E6EA=set-up-a-smart-banners-landing-page h_01KB2W28TKW8B6H4W0R9YJM3ZE=note-6 h_01KB2W28TKRH3NC73J2JHNSMWD=note-7 view-webtoapp-attribution-data=view-web-to-app-attribution-data h_01KB2W28TKDAV34JGYJKF2VT43=view-web-to-app-attribution-data h_01KB2W28TKNWYXJX189EP2HPN2=view-in-the-dashboard h_01KB2W28TKJ1MAMM00KY3M3S2W=view-in-raw-data-and-api-reports h_01KB2W28TKFY74YBXHD91QP9V0=traits-and-limitations" />
