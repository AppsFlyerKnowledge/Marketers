---
title: "TikTok for Business—Create web-based campaigns"
excerpt: "Use TikTok Ads Web campaigns to attribute web-to-app conversions from TikTok Ads"
x-zendesk:
  id: 40496161157521
  url: https://support.appsflyer.com/hc/en-us/articles/40496161157521-TikTok-for-Business-Create-web-based-campaigns
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: TikTok for Business
  section_id: 12192554266385
  position: 2
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution]
  labels: []
  promoted: false
  comments_disabled: false
  created_at: '2025-10-31T12:09:51Z'
  edited_at: '2026-09-15T10:58:44Z'
---
## Overview

AppsFlyer supports integration with TikTok Ads (`tiktokweb_int`) for User Acquisition web-based campaigns, allowing you to report attribution and conversion data directly through TikTok's Events API. TikTok can then utilize this data to optimize ad targeting, measure performance, and build custom audiences.

> 📘 **Important!**
>
> At present, the integration with TikTok Web does not support sending re-engagement postbacks to CAPI.

### Prerequisites

Before activating the TikTok Web integration, make sure you have a business account in [TikTok Ads Manager](https://getstarted.tiktok.com/grow-your-business-gb?lang=en&attr_source=google&attr_source=google&attr_medium=search-br-ad&attr_medium=search-br-ad&attr_adgroup_id=155057567247&attr_adgroup_id=155057567247&attr_term=tiktok%20ads%20manager&attr_term=tiktok%20ads%20manager&no_parent_redirect=1&no_parent_redirect=1&creative=%7BGenZCopy%7D&matchtype=e&gad_source=1&gad_campaignid=20368896948&gbraid=0AAAAACeGRgRdqveOjiUJwxN0-j9g7VjPg&gclid=Cj0KCQjwmYzIBhC6ARIsAHA3IkTKsL0d1xAZLIO_9GIkDDIJR-jZs9jDGVa1hTDbsLzcxZl2j6p7ITcaAhf1EALw_wcB).

### How to create a TikTok Web Ads Campaign

This article contains information and steps on how to set up a web campaign in TikTok Ads for Mobile, apps with AppsFlyer. The setup involves defining the integration between TikTok Ads and AppsFlyer, setting the campaign configuration on both platforms and creating landing pages with OneLink Smart Script or OneLink Smart Banners.

The setup process includes the following mandatory steps:

* [Set up TikTok Web Ads integration in AppsFlyer](#set-up-tiktok-web-ads-integration-in-appsflyer) (Required)
* [Set up AppsFlyer integration in TikTok Ads](#set-up-appsflyer-integration-in-tiktok-ads) (Required)

And the following optional steps:

* [#create-a-landing-page-with-onelink-smart-script](/docs/meta-ads-create-web-based-campaigns#create-a-landing-page-with-onelink-smart-script) (Optional)
* [Create a landing page with OneLink Smart Banners](#create-a-landing-page-with-onelink-smart-banners) (Optional)

## Set up TikTok Web Ads integration in AppsFlyer

Start by activating the TikTok Web integration and setting the postbacks AppsFlyer sends to the Events API.

<Accordion title="1. Activate the TikTok Web Ads integration">

To activate the TikTok Web Ads integration:

1. In AppsFlyer, from the side menu, open **Collaborate** > **Partner Integrations** > **Partner Marketplace**.
2. Search for **TikTok Web** (or `tiktokweb_int`) and select it. You’re directed to the setup page.
3. In the **Integration** tab, turn on **Activate Partner**. The toggle must stay on ([activated](/docs/partner-activation-deactivation)) for as long as you work with the partner.
4. Turn off **Advanced Privacy**(if you are setting an iOS app integration).
5. **Advanced Matching data sharing:** Turn on to share Advanced Matching fields, such as hashed email, hashed phone number, hashed first name, and hashed last name, with TikTok, if these fields are included in the event information sent to AppsFlyer. For more information, see: [Advanced Matching Data Sharing](/docs/advanced-matching-data-sharing).
6. **Pixel ID:** Enter the Pixel ID. You can generate it or retrieve it from your TikTok ads Manager, by following the instructions detailed [HERE](https://business-api.tiktok.com/portal/docs?id=1771100865818625).
7. **Access token:** Enter the access token. To generate it or retrieve it, follow [these instructions](https://business-api.tiktok.com/portal/docs?id=1771100865818625)
8. **Limit TikTok ads use of users’ personal information (CCPA):** Turn on this toggle to enable compliance with [data protection laws](/docs/send-opendsr-api-requests).

   > 📘 **Note**
   >
   > Complying with CCPA privacy regulations limits the data coming from TikTok ads users based in California or other sensitive states in the US.


</Accordion>

<Accordion title="2. Enable view-through attribution">

AppsFlyer supports view-through attribution for TikTok Web campaigns using a [Smart Script](#create-a-landing-page-with-onelink-smart-script) or [Smart Banner](#create-a-landing-page-with-onelink-smart-banners)-enabled landing page. This allows probabilistic modeling (PMOD) attribution of app installs triggered by ad impressions, even when users don’t click the ad directly.

When a user clicks a TikTok Web ad and lands on a [Smart Script](#create-a-landing-page-with-onelink-smart-script) or [Smart Banner](#create-a-landing-page-with-onelink-smart-banners)-enabled landing page, AppsFlyer can attribute the downstream app install. If available, the `ttclid` will be included in the postback to TikTok to enhance attribution fidelity.

**To enable TikTok Web view-through attribution:**

1. In AppsFlyer, from the sidebar, open **Active Integrations** > **TikTok web ads**.
2. In the **Integration** tab, scroll to the **Install attribution** section.
3. Turn on **Install view-through attribution**.
4. **[optional]** Turn on **Cross-platform equal attribution priority** and set its lookback window. For more information, see [Enable equal priority for cross-platform impressions](/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions).
5. Open the **Attribution link** tab.
6. Scroll to the **View-through attribution** section and set the **view-through lookback window** (up to 24 hours).
7. Click **Save integration** to apply your settings.

</Accordion>

<Accordion title="3. Set in-app event postbacks">

Installs are currently the only events that trigger automatic default postbacks to TikTok Ads. For other event types, you can create custom postbacks by mapping AppsFlyer events to TikTok Ads events, which can be viewed in the TikTok Ads Manager.

To set in-app events postbacks, perform the following:

1. Turn on **In-app event postbacks**.
2. If required, set the In-app event postback window (read more about in-app event postback window configuration in general in [this article](/docs/in-app-event-postback-configuration#in-app-event-postback-window)).
3. Click **Add event** to add an event to the list.
4. In the **AppsFlyer event**column, select the event name from the drop-down box. AppsFlyer receives the event's name either from the SDK integrated into your app or from server-to-server events.
5. In the **mapped to partner event** column,select from the dropdown box the most suitable pre-defined partner event.
6. In the **For Users From** column, select **This Partner Only** to ensure that in-app event postbacks are sent exclusively for events performed by users who originated from this partner.
7. In the **including** column, select whether events will be sent with their revenue values. See [Data to include in the postbacks](/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks).

   <br /><br />**Note**<br />#### Note

   * If you are setting a purchase event, set the **including** column to **Values and revenue**. Selecting any other option will cause the postback to fail.
   * Currently, only the purchase event can be set to include revenue.
8. [Optional] Click the **Add condition** icon to [set conditions](/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks) for an event.
9. Click **Save integration**.
10. [Optional] After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
    1. From the top-left corner, click the app name under the partner name to open the list of apps.
    2. Select a different app from the drop-down list.
    3. Repeat the integration steps for the selected app.

</Accordion>

## Set up AppsFlyer integration in TikTok Ads

Perform the next steps in TikTok Ads Manager.

<Accordion title="1. Set the campaign type, objective, and goals">

You can choose any pre-defined INAPP event sent from Appsflyer as your campaign goal, or choose “Download” if you want to optimize for mobile App Installs.

> 📘 **Warning**
>
> If you want to ensure that your web-to-app-triggered conversion events are sent via the TikTok Events API, skip [these steps](/docs/tiktok-for-business-advanced-srn-integration-setup#measuring-app-activity-for-nonapp-campaigns) when creating the campaign; otherwise, TikTok will claim those conversions through the SRN API, which can cause reporting and optimization misalignments.

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. Set destination URL">

1. Under **Destination,** in the **Website URL**field, enter the URL that serves as the destination for your ad. The URL should be for one of the following:
   * **Web landing page:** Using a landing page is recommended when:
     * You have an app on multiple platforms.
     * You want to use the landing page to give more information about your advertised product.
     * You want to use the landing page to collect more data.

       For all these use cases, create a [Smart Script](#create-a-landing-page-with-onelink-smart-script) or [Smart Banner](#create-a-landing-page-with-onelink-smart-banners)-enabled landing page.
   * **AF attribution links:** Using AF attribution links (OneLink, single platform, or cross-platform) is recommended when you want the user to be redirected directly to the store to download the app without first visiting a landing page.
2. Click **Build a URL parameter** to add the URL parameters to the URL (whether it is a landing page URL or an AF attribution link).
3. Under **Custom parameters**, click **Add parameter**
4. Map the AppsFlyer parameters to their TikTok values. The parameters you'll be mapping depend on whether the destination URL points to a landing page, attribution link, or PC or console store.

   #### Landing page or attribution link

   If your destination URL is **a landing page, a OneLink attribution link, or a single platform attribution link**, map the following AF parameters to their TikTok counterparts:

| AF Parameter | Mapped TikTok value |
| --- | --- |
| [`pid`](/docs/about-link-structure-and-parameters#pid) | `tiktokweb_int` |
| [`c`](/docs/about-link-structure-and-parameters#c)* | **\_\_campaign\_name\_\_** |
| [`af_c_id`](/docs/about-link-structure-and-parameters#af_c_id) | **\_\_campaign\_id\_\_** |
| [`af_adset`](/docs/about-link-structure-and-parameters#af_adset) | **\_\_aid\_name\_\_** |
| [`af_adset_id`](/docs/about-link-structure-and-parameters#af_adset_id) | **\_\_aid\_\_** |
| [`af_ad`](/docs/about-link-structure-and-parameters#af_ad) | **\_\_cid\_name\_\_** |
| [`af_ad_id`](/docs/about-link-structure-and-parameters#af_ad_id) | **\_\_cid\_\_** |

   ***** To simplify campaign analysis, include the campaign type, web or mobile, as a prefix or suffix in the campaign name (e.g., campaign-name\_web)

   An example of the resulting URL should be:

   ```
   https://app.appsflyer.com/{app_id}?pid=tiktokweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r={https://Add-your-store-url.com}
   ```

   If your app’s APK is NOT hosted in Google Play Store, add the [`af_r`](/docs/about-link-structure-and-parameters#af_r) parameter and map to it the store URL, e.g, `https://Add-your-store-url.com`

   #### PC or console store

   If your destination URL is a **PC or a console store**, create the link by following the instructions in the table below. For additional information, see: [CTV, PC, and console platform direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links)

| Link component | Value |
| --- | --- |
| Base URL | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| Mandatory path parameters | ▪ platformExample: steam  <br />▪ app\_idExample: 123456 |
| Mandatory query parameters | ▪ af\_media\_source  <br />▪ af\_campaign\_id  <br />▪ af\_r |
| Other parameters | [See all parameters](/docs/ctv-pc-and-console-platform-direct-attribution-links#parameters) |
| URL structure | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |

   Map the following AppsFlyer parameters to their TikTok counterparts:

| AF Parameter | Mapped TikTok value |
| --- | --- |
| `af_media_source` | `tiktokweb_int` |
| `af_campaign` ***** | **\_\_campaign\_name\_\_** |
| [`af_campaign_id`](/docs/about-link-structure-and-parameters#af_c_id) | **\_\_campaign\_id\_\_** |
| [`af_adset`](/docs/about-link-structure-and-parameters#af_adset) | **\_\_aid\_name\_\_** |
| [`af_adset_id`](/docs/about-link-structure-and-parameters#af_adset_id) | **\_\_aid\_\_** |
| [`af_ad`](/docs/about-link-structure-and-parameters#af_ad) | **\_\_cid\_name\_\_** |
| [`af_ad_id`](/docs/about-link-structure-and-parameters#af_ad_id) | **\_\_cid\_\_** |

   ***** To simplify campaign analysis, include the campaign type, web or mobile, as a prefix or suffix in the campaign name (e.g., campaign-name\_web)

   An example of cross-platform URL:

   ```
   https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=tiktokweb_int&af_campaign_id=__campaign_id__&af_campaign=__campaign_name__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
   ```

   > 📘 **Note**
   >
   > TikTok adds the `ttclid={{ttclid}}` to the destination URL automatically when the ad is clicked


</Accordion>

## Create a landing page with OneLink Smart Script

**User journey:** The user clicks on a TikTok ad and is directed to your mobile website. They land on a page with CTA buttons urging them to download your app from one or more platforms. Clicking the button redirects the user to the store.

<Accordion title="End-to-end data flow">

[![](https://files.readme.io/67a7404cfef4b6629dc300f68addcbd66cbd4a4a50ffb702be48f7c7df1831e1-40497655655825.png)](https://files.readme.io/67a7404cfef4b6629dc300f68addcbd66cbd4a4a50ffb702be48f7c7df1831e1-40497655655825.png)

1. The TikTok ad URL includes the  `pid=tiktokweb_int` parameter. When the user clicks on the ad, an `ttclid` parameter is automatically appended to the clicked URL.
2. The User is redirected to the URL destination - a landing page containing a Smart Script.
3. When the landing page loads, Smart Script fires an impression to AppsFlyer containing the incoming URL parameters. The impression will allow view-through attribution from the web landing page. To learn about impressions and view-through attribution, see [here](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url).
4. Smart Script generates the outgoing URLs for the CTA buttons on the page based on the incoming URL parameters, including the `ttclid` parameter. The buttons can lead to:
   * Google Play and App Store via a OneLink attribution link.
   * Multiple platform stores (e.g., CTV, Epic, and Steam). In this use case, Smart Script generates a single platform attribution link for each platform, leading to the specified platform's store.
   * Downloading an APK file to the user's device.
5. When the user clicks the CTA button, the click is fired and registered in AppsFlyer.
6. The user is redirected to the store and downloads the app.
7. When the user opens the app, the install event is registered in AppsFlyer.
8. AppsFlyer attributes the install based on probabilistic modeling or, if an [install referrer](https://www.appsflyer.com/glossary/install-referrer/) is available, deterministically.
9. A postback containing the `ttclid` parameters and other event parameters is generated and sent to TikTok via the Events API. TikTok uses the `ttclid` parameter to identify the specific click, while the other parameters help optimize the campaign.

</Accordion>

<Accordion title="Set up a Smart Script landing page">

To set up your smart script TikTok Ads campaigns, perform the following:

1. Set up the template for the campaign’s OneLink attribution links. For more information, see [How to create OneLink templates](/docs/create-a-onelink-template#create-a-onelink-template).
2. Create a smart script. For more information, see [How to create a OneLink Smart Script](/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script).

   > 📘 **Note**
   >
   > The instructions below focus on the specific steps required to set up a TikTok Ads campaign with Smart Script. For a comprehensive guide on how to set up Smart Script campaigns, see the [How to create a OneLink Smart Script](/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script) section of the [OneLink Smart Script V2 setup](/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script) article.

3. Make sure all relevant URL parameters are appended to the incoming URL. To review the parameters appended to the incoming URL, open TikTok Ads Manager and check the URL parameters set during the creation of the destination URL. For more information, see  [Set destination UR](#2-set-destination-url)[L](#set-destination-url).
4. Map the incoming URL parameters required for the TikTok Ads campaign to the outgoing URL parameters that will be sent to AppsFlyer when the user clicks the CTA button:
   * **PID**: Make sure that Smart Script takes the `pid=tiktokweb_int` parameter value from the incoming URL and maps it to the corresponding parameters in the outgoing URL.
   * **TTCLID**: The `ttclid` parameter is essential for successfully sending in-app events postbacks to TikTok. The `ttclid` parameter should be mapped manually in the **URL parameter mapping** section of the **Smart Script** page:

     1. In **Mapping for**, select **Custom parameter**.
     2. In **Outgoing URL parameter** and **Incoming URL parameters** enter **ttclid**.<br /><br />**Note**<br />#### Note

     To display in AppsFlyer raw data reports, the incoming `ttclid` parameter must also be mapped (in addition to the outgoing `ttclid` parameter) to one of the outgoing `af_sub[1-5]` parameters.

</Accordion>

<Accordion title="Set up a Smart Script cross-platform landing page">

To set up your smart script TikTok Ads campaigns for cross-platform landing pages, perform the following:

1. Set up the template for the campaign’s OneLink attribution links. For more information, see [How to create OneLink templates](/docs/create-a-onelink-template#create-a-onelink-template).
   * Enable your OneLink template for cross-platform attribution, see [here](/docs/set-up-cross-platform-links-for-multi-device-campaigns#create-a-onelink-templatefor-cross-platform-attribution).
2. Make sure all relevant URL parameters are appended to the incoming URL. To review the parameters appended to the incoming URL, open TikTok Ads Manager and examine the URL parameters you set when you built the destination URL. For more information, see [Set destination URL](/docs/meta-ads-create-web-based-campaigns#h_01HZKNS17KT8TRD2TGDBRGKBZ3).
3. Decide for each incoming parameter the outgoing parameter to which it will be mapped. for example, the incoming `af_site_id` parameter in the incoming URL will be mapped to the  `af_site_id` parameter in the outgoing URL.
4. Determine the default value for the mandatory outgoing parameters that cannot be left empty.
5. Send your developer the following information:
   * Your incoming - outgoing parameter mapping. The developer will create a script that generates an outgoing direct URL based on the incoming-outgoing parameter mapping.
   * The parameters’ default values. The script will populate the outgoing URL parameters with the default values whenever there are no corresponding incoming URL parameter values.
   * If you are using a OneLink attribution link, send the domain and template ID to your developer. The developer uses this to create the outgoing OneLink URL. For example: `yourbrand.onelink.me/A1b2` or Branded domain example: `click.yourbrand.com/A1b2`
   * Send your developer the following Dev Hub links:
     * [Instructions and code examples](https://dev.appsflyer.com/hc/docs/create-direct-click-url) on how to create the outgoing direct URLs to the non-mobile platforms.
     * [A demo and instructions](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/) for creating a cross-platform landing page.

* Remind your developer to include the incoming `ttclid` parameter in the outgoing URL.

  > 📘 **Note**
  >
  > To display in AppsFlyer raw data reports, the incoming `ttclid` parameter must also be mapped (in addition to the outgoing `ttclid` parameter) to one of the outgoing `af_sub[1-5]` parameters.


</Accordion>

## Create a landing page with OneLink Smart Banners

**User journey:** The user clicks on a TikTok ad and is directed to your mobile website. They land on a page, and a Smart Banner is displayed with a CTA to download the app from the App Store.

<Accordion title="End-to-end data flow">

1. The TikTok ad URL includes the  `pid=tiktokweb_int` parameter. When the user clicks on the ad, an `ttclid` parameter is automatically appended to the clicked URL.
2. The User is redirected to the URL destination - a landing page containing a Smart Banner.
3. When the landing page loads, the Smart Banner fires an [impression](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url) event to AppsFlyer, which includes the incoming URL parameters. This impression enables view-through attribution for the landing page. To learn about impressions and view-through attribution, see [here](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url).
4. The Smart Banner generates the outgoing URL for the CTA button on the banner. The outgoing URL is based on the incoming URL parameters including the `ttclid` parameter. The Smart banner can generate only OneLink-based links.
5. When the user clicks the Smart Banner CTA button the click is fired and registered in AppsFlyer.
6. The user is redirected to the store and downloads the app.
7. When the user opens the app, the install event is registered in AppsFlyer.
8. AppsFlyer attributes the install based on probabilistic modeling or deterministically if the install referrer is available.
9. A postback containing the `ttclid` parameters and other event parameters are generated and sent to TikTok via the Events API. TikTok uses the `ttclid` parameter to identify the specific click, while the other parameters help optimize the campaign.

</Accordion>

<Accordion title="Set up a Smart Banners landing page">

To set up your Smart Banners TikTok Ads campaigns, perform the following:

1. Set up the template for the campaign’s OneLink attribution links. For more information, see [How to create OneLink templates](/docs/create-a-onelink-template#create-a-onelink-template).
2. Create a Smart Banner.

   > 📘 **Note**
   >
   > The instructions below focus on the specific steps required to set up a TikTok Ads campaign with Smart Banners. For a comprehensive guide on how to set up Smart Banners campaigns, see the [setup section](/docs/smart-banners-mobile-web-to-app-for-marketers#setup) of the [Smart Banners—mobile web-to-app (for marketers)](/docs/smart-banners-mobile-web-to-app-for-marketers) article.

3. Set the Smart Banner parameters for TikTok Ads campaigns:
   * Make sure all relevant URL parameters are appended to the incoming URL. Most importantly the `pid=tiktokweb_int` and `ttclid` are available in the incoming URL to allow the Smart Banner to collect them. These two parameters are necessary for attribution and for sending postbacks to TikTok Ads. To review the parameters that are appended to the incoming URL, open TikTok Ads Manager and review the URL parameters that you set when you built the destination URL, see: [Set destination URL](/docs/meta-ads-create-web-based-campaigns#h_01HZKNS17KT8TRD2TGDBRGKBZ3).

</Accordion>

## View web-to-app attribution data

Although web-based conversion events are sent to TikTok under the original `tiktokweb_int` PID, they are reported in the AppsFlyer dashboard and raw data reports under the `tiktokglobal_int` PID. This applies to both primary conversion events and conversion assist events.

This unified reporting view enables you to analyze both web and app campaign performance in one place, including comprehensive web and mobile cost reporting.

### View in the dashboard

All TikTok web-to-app attributions appear under `tiktokglobal_int` in the Overview and Activity dashboards. This provides a single, consolidated view of campaign results across platforms. Use standard filters and breakdowns to compare app and web traffic within your TikTok Ads data.

### View in raw data and API reports

Raw data exports and API responses include the `tiktokglobal_int` PID in the `media_source` field for TikTok web activity. To verify the web campaign setup details, refer to the `original_url` field, which shows the `tiktokweb_int` PID used during the web campaign creation.

## Measure cost, clicks, and impressions

You can measure TikTok cost, clicks, and impressions alongside your web-to-app attribution data in the dashboard and in Cost ETL reports (ROI360 customers only):

1. Connect TikTok as a cost integration on your mobile app:  
   Go to the **Cost** tab or **Cost Settings** page and connect via `tiktokglobal_int`. For step-by-step instructions, see [Set up ROI360 Cost API to measure cost data](/docs/set-up-roi360-cost-api-to-measure-cost-data).
2. Add the campaign ID to your landing page URL:  
   Include `af_c_id` along with the full campaign hierarchy in the landing page URL. This ensures cost, clicks, and impressions are matched to your web attribution data at the most granular level.

> 📘 **Note**
>
> Cost data is available to ROI360 customers only. Clicks and impressions are available to all customers who complete this setup.