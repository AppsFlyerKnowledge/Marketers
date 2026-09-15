---
title: "Meta Ads— Create web-based campaigns"
excerpt: "Learn how to set up Meta Ads Web campaigns to attribute web-to-app conversions from Meta Ads using AppsFlyer's integration."
---
**At a glance:** Use Meta Ads Web campaigns to attribute web-to-app conversions from Meta Ads

## Overview

AppsFlyer supports integration with Meta Ads (`metaweb_int`) for User Acquisition web-based campaigns, allowing you to report attribution and conversion data directly through Meta's Conversion API (CAPI). Meta can then utilize this data to optimize ad targeting, measure performance, and build custom audiences.

> 📘 **Note**
>
> At present, the integration with Meta Web does not support sending re-engagement postbacks to CAPI.


### Prerequisites

Before activating the Meta Ads integration, make sure that you have a [business account in Meta Business Manager](https://www.facebook.com/business/help/1710077379203657?id=180505742745347).

### How to create a Meta Web Ads Campaign

This article contains information and steps on how to set up a web campaign in Meta Ads for Mobile,  PC, and console apps with AppsFlyer. The setup involves defining the integration between Meta Ads and AppsFlyer, setting the campaign configuration on both platforms and creating landing pages with OneLink Smart Script or OneLink Smart Banners.  
The setup process includes the following mandatory steps:

* [Set up Meta Web Ads integration in AppsFlyer](#h_01HZKNS17J284R2MAN42WV7F0S) (Required)
* [Set up AppsFlyer integration in Meta Ads](#h_01HZKNS17JJWX7N9W6BN05B57C) (Required)

And the following optional steps:

* [Create a landing page with OneLink Smart Script](#h_01HZKNS17KPJMP74HQKWY022T2) (Optional)
* [Create a landing page with OneLink Smart Banners](#h_01HZKNS17KH8NQ68RPZGMEAQTV) (Optional)

## Set up Meta Web Ads integration in AppsFlyer

Start with activating the Meta Ads integration and setting the postbacks AppsFlyer sends to CAPI.

### 1. Activate the Meta Web Ads integration

To activate the Meta Web Ads integration:

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Partner Marketplace**.
2. Search for **Meta Web** and select it.
3. Click **Set up integration**. You're directed to the **Active Integrations** setup page.
4. In the **Integration** tab, turn on **Activate Partner**. **Note:**The toggle must stay on ([activated](/docs/partner-activation-deactivation)) for as long as you work with the partner.
5. Turn off **Advanced Privacy**(if you are setting an iOS app integration).
6. **Advanced Matching data sharing:** Turn on to share Advanced Matching fields, such as hashed email, hashed phone number, hashed first name, hashed last name, and Facebook login ID, with Meta, if these fields are included in the event information sent to AppsFlyer. For more information, see: [Advanced Matching Data Sharing](/docs/advanced-matching-data-sharing).
7. Fill in the **Pixel ID** field. You can retrieve the pixel ID from your Meta ads Manager:
   1. From the[Ads manager](https://www.facebook.com/ads/manager) side menu, go down to **All tools** > **Events Manager**. **Note:** Make sure you have the correct business selected from the drop-down on the top right.
   2. From the **Events Manager** side menu, select **Data sources**. You'll see a list of your pixels. If you don't have a pixel for the selected business, you can create one through the same view.
   3. Copy the pixel ID showing under the pixel name.  
      and paste it into the  
      **Pixel ID** field in AppsFlyer.
8. Fill the **Access Token** field. To retrieve the access token, follow [these instructions](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)
9. Turn on **Limit Meta Ads' use of users' personal information (CCPA)** to enable compliance with [data protection laws](/docs/send-opendsr-api-requests). **Note:** Complying with CCPA privacy regulations limits the data coming from Meta Ads users based in California.

### 2. Enable view-through attribution

AppsFlyer supports view-through attribution for Meta Web campaigns using a [Smart Script](#set-up-smart-script-crossplatform-landing-page) or [Smart Banner](#set-up-smart-banners-landing-page)-enabled landing page. This allows probabilistic modeling (PMOD) attribution of app installs triggered by ad impressions, even when users don't click the ad directly.

When a user clicks a Meta Web ad and lands on a [Smart Script](#set-up-smart-script-crossplatform-landing-page) or [Smart Banner](#set-up-smart-banners-landing-page)-enabled landing page, AppsFlyer can attribute the downstream app install. If available, the `fbclid` will be included in the postback to Meta to enhance attribution fidelity.

**To enable Meta Web view-through attribution:**

1. In AppsFlyer, from the sidebar, open **Active Integrations** > **Meta web ads**.
2. In the **Integration** tab, scroll to the **Install attribution** section.
3. Turn on **Install view-through attribution**.
4. **[optional]** Turn on **Cross-platform equal attribution priority** and set its lookback window. For more information, see [Enable equal priority for cross-platform impressions](/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions)**.**
5. Open the **Attribution link** tab.
6. Scroll to the **View-through attribution** section and set the **view-through lookback window** (up to 24 hours).
7. Click **Save integration** to apply your settings.

### 3. Set in-app event postbacks

Installs are currently the only events that trigger automatic default postbacks to Meta Ads. For other event types, you can create custom postbacks by mapping AppsFlyer events to Meta Ads events, which can be viewed in the [Meta Events Manager](https://www.facebook.com/business/help/1541268312717919?id=818859032317965).  
To set in-app events postbacks perform the following:

1. Turn on **In-app event postbacks**.
2. If required, set the In-app event postback window (read more about in-app event postback window configuration in general in [this article](/docs/in-app-event-postback-configuration#inapp-event-postback-window)).
3. Click **Add event** to add an event to the list.
4. In the **AppsFlyer event** column, select the event name from the drop-down box. AppsFlyer receives the event's name either from the SDK integrated into your app or from server-to-server events.
5. In the **mapped to partner event** column**,** select from the dropdown box the most suitable pre-defined partner event or select CUSTOM.
6. In the **For Users From** column, select the sending option for the event:
   * **This partner only**: send postbacks only when this event is attributed to Meta ads.
   * **All media sources, including organic,** send postbacks for events attributed to any partner and organic events.
7. In the **including** column, select whether events will be sent with their revenue values. See [Data to include in the postbacks](/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks).

   CALLSTART::Note::

   #### Note

   If you are setting a purchase event, set the **including** column to **Values and revenue**. Selecting any other option will cause the postback to fail.

   CALLEND::
8. [Optional] Click the **Add condition** icon to [set conditions](/docs/in-app-event-postback-configuration#conditional-inapp-event-postbacks) for an event.
9. Click **Save integration**.
10. [Optional] After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
    1. From the top-left corner, click the app name under the partner name to open the list of apps.
    2. Select a different app from the drop-down list.
    3. Repeat the integration steps for the selected app.

> 📘 **Note**
>
> If you are sending S2S events to `metaweb_int`, the S2S payload must include the `ua` (User Agent) and `ip` (IP address) parameters. These values are required for Meta CAPI campaign optimization. AppsFlyer includes them automatically for SDK events. For S2S events, advertisers must send them explicitly. See [Server-to-server events API for mobile](/docs/server-to-server-events-api-for-mobile-s2s-mobile).


## Set up AppsFlyer integration in Meta Ads

Perform the next steps in Meta Ads Manager.

### 1. Set the campaign type, objective, and goals

1. Log in to Meta Ads and create a campaign.
2. In **Campaign objective** select one of the following: [![](https://support.appsflyer.com/hc/article_attachments/25646834955921)](https://support.appsflyer.com/hc/article_attachments/25646834955921)
   * **Sales**: This lets Meta optimize towards a specific event (your main KPI).
   * **Traffic**: This lets Meta optimize towards ad clicks. This should only be used if you don't have other KPIs or if the volume of other KPI events is too low.
3. [Optional] If you want to add a custom objective to the above options perform the following:
   1. In Meta Ads, select the custom event that you want to set as a campaign objective and mark it as a conversion action in Meta Ads.
   2. In AppsFlyer, in the **Meta Web integration** page, under **In-app event postbacks** map an AppsFlyer event to a custom partner event (under the **mapped to partner event** column) and name it with the same name as the conversion action in Meta Ads.

      CALLSTART::Note::

      #### Note

      To learn more about the Meta Campaign objectives, see the [Meta documentation](https://www.facebook.com/business/help/175683976191028).

      CALLEND::
4. In **Conversion location** select **Website**. [![](https://support.appsflyer.com/hc/article_attachments/25646834954257)](https://support.appsflyer.com/hc/article_attachments/25646834954257)
5. In **Pixel** enter the same pixel ID you entered for `metaweb_int` in the AppsFlyer Partner Marketplace. To learn more about the Meta Pixel, see the [Meta documentation](https://www.facebook.com/business/help/742478679120153) (a login is required).
6. Click **Next**.

### 2. Set destination URL

1. Under **Destination,** in the **Website URL** field**,** enter the URL that serves as the destination for your ad. The URL should be for one of the following:

   [![](https://support.appsflyer.com/hc/article_attachments/25646834955537)](https://support.appsflyer.com/hc/article_attachments/25646834955537)

   * **Web landing page:** Using a landing page is recommended when:

     * You have an app on multiple platforms.
     * You want to use the landing page to give more information about your advertised product.
     * You want to use the landing page to collect more data.

     For all these use cases create a [landing page with a Smart Script](#h_01HZKNS17KPJMP74HQKWY022T2) or [a Smart Banner](#h_01HZKNS17KH8NQ68RPZGMEAQTV).
   * **AF attribution links:** Using AF attribution links (OneLink, single platform or cross-platform) is recommended when you want the user to be redirected directly to the store to download the app without first visiting a landing page.

     CALLSTART::Note::

     #### Important!

     Sometimes, the use of AF attribution links may lead to errors. If this occurs, ask your Meta representatives for a solution, or simply use a Web landing page as the destination URL.

     CALLEND::
2. Click **Build a URL parameter** to add the URL parameters to the URL (whether it is a landing page URL or an AF attribution link).
3. Under **Custom parameters**, click **Add parameter**

   [![4.png](https://files.readme.io/bbce415e16d3442f8959bf7a0c23825035d7d4740d5bf3570306c3684c8764d4-25722672143633.png)](https://support.appsflyer.com/hc/article_attachments/25722672143633)
4. Map the AppsFlyer parameters to their Meta values.

   * If your destination URL is **a landing page, a OneLink attribution link, or a single platform attribution link**, map the following AF parameters to their Meta counterparts: 

     

| AF Parameter | Mapped Meta value |
| --- | --- |
| [`pid`](/docs/about-link-structure-and-parameters#pid) | `metaweb_int` |
| [`c`](/docs/about-link-structure-and-parameters#c) | `{{campaign.name}}` |
| [`af_siteid`](/docs/about-link-structure-and-parameters#af_siteid) | `{{site_source_name}}` |
| [`af_c_id`](/docs/about-link-structure-and-parameters#af_c_id) | `{{campaign.id}}` |
| [`af_adset`](/docs/about-link-structure-and-parameters#af_adset) | `{{adset.name}}` |
| [`af_adset_id`](/docs/about-link-structure-and-parameters#af_adset_id) | `{{adset.id}}` |
| [`af_ad`](/docs/about-link-structure-and-parameters#af_ad) | `{{ad.name}}` |
| [`af_ad_id`](/docs/about-link-structure-and-parameters#af_ad_id) | `{{ad.id}}` |



     An example of the resulting URL should be:

     ```
     https://app.appsflyer.com/{app_id}?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={https://Add-your-store-url.com}
     ```

     * If your app's APK is NOT hosted in Google Play Store, add the [`af_r`](/docs/about-link-structure-and-parameters#af_r) parameter and map to it the store URL, e.g, `https://Add-your-store-url.com`
   * If your destination URL is a **PC or a console store**, create the link by following the instructions in the table below. For additional information see: [CTV, PC, and console platform direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links)

     

<table><thead><tr><th colspan="2">Attribution link structure</th></tr></thead><tbody><tr><td>Base URL</td><td>engagements.appsflyer.com/v1.0/c2s/click/app/</td></tr><tr><td>Mandatory path parameters</td><td><ul><li>platform<br/>Example: steam</li><li>app_id<br/>Example: 123456</li></ul></td></tr><tr><td>Mandatory query parameters</td><td><ul><li>af_media_source</li><li>af_campaign_id</li><li>af_r</li></ul></td></tr><tr><td>Other parameters</td><td><a href="/docs/ctv-pc-and-console-platform-direct-attribution-links#attribution-link-parameters">See all parameters</a></td></tr><tr><td>URL structure</td><td><code>https://engagements.appsflyer.com/v1.0/c2s/click/app/`{platform}/{app_id}?af_media_source={media_source}&amp;af_campaign_id={campaign_id}&amp;af_r={app_store_url}`</code></td></tr></tbody></table>



     Map the following AppsFlyer parameters to their Meta counterparts:

     

| AF Parameter | Mapped Meta value |
| --- | --- |
| `af_media_source` | `metaweb_int` |
| `af_campaign` | `{{campaign.name}}` |
| [`af_siteid`](/docs/about-link-structure-and-parameters#af_siteid) | `{{site_source_name}}` |
| [`af_campaign_id`](/docs/about-link-structure-and-parameters#af_c_id) | `{{campaign.id}}` |
| [`af_adset`](/docs/about-link-structure-and-parameters#af_adset) | `{{adset.name}}` |
| [`af_adset_id`](/docs/about-link-structure-and-parameters#af_adset_id) | `{{adset.id}}` |
| [`af_ad`](/docs/about-link-structure-and-parameters#af_ad) | `{{ad.name}}` |
| [`af_ad_id`](/docs/about-link-structure-and-parameters#af_ad_id) | `{{ad.id}}` |



     An example of cross-platform URL:

     ```
     https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
     ```CALLSTART::Note::

   #### Note

   Meta adds the `fbclid={{fbclid}}` to the destination URL automatically when the ad is clicked

   CALLEND::
   CALLSTART::Note::

   #### Tip

   To simplify campaign analysis, include the campaign type, web or mobile, as a prefix or suffix in the campaign name (e.g., campaign-name\_web)

   CALLEND::

> 📘 **Note**
>
> For a comprehensive guide on the AF link parameters, see [Attribution link parameters](/docs/about-link-structure-and-parameters#attribution-link-parameters).


### 3. Select tracked events

Use the Tracking section to select the conversion events promoted by your ad (setting up of the events is done via the [Event Manager](https://www.facebook.com/business/help/898185560232180?id=1205376682832142)).

[![](https://support.appsflyer.com/hc/article_attachments/25646834958481)](https://support.appsflyer.com/hc/article_attachments/25646834958481)

> 📘 **Important!**
>
> Make sure not to choose **App Events,** otherwise Meta will claim those conversions using the SRN API, which can cause reporting and optimization misalignments.


## Create a landing page with OneLink Smart Script

**User journey:** The user clicks on a Meta ad and is directed to your mobile website. They land on a page with CTA buttons urging them to download your app from one or more platforms. Clicking the button redirects the user to the store.

### End-to-end data flow

[![](https://support.appsflyer.com/hc/article_attachments/25646834953105)](https://support.appsflyer.com/hc/article_attachments/25646834953105)

1. The Meta ad URL includes the the `pid=metaweb_int` parameter. When the user clicks on the ad an `fbclid` parameter is automatically appended to the clicked URL.
2. The User is redirected to the URL destination - a landing page containing a Smart Script.
3. When the landing page loads, Smart Script fires an impression to AppsFlyer containing the incoming URL parameters. The impression will allow view-through attribution from the web landing page. To learn about impressions and view-through attribution, see [here](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url).
4. Smart Script generates the outgoing URLs for the CTA buttons on the page based on the incoming URL parameters, including the `fbclid` parameter. The buttons can lead to:
   * Google Play and App Store via a OneLink attribution link.
   * Multiple platform stores (e.g., CTV, Epic and Steam). In this use case, Smart Script generates a single platform attribution link for each platform, leading to the specified platform's store.
   * Downloading an APK file to the user's device.
5. When the user clicks the CTA button, the click is fired and registered in AppsFlyer.
6. The user is redirected to the store and downloads the app.
7. When the user opens the app, the install event is registered in AppsFlyer.
8. AppsFlyer attributes the install based on probabilistic modeling or deterministically if an [install referrer](https://www.appsflyer.com/glossary/install-referrer/) is available.
9. A postback containing the `fbclid` parameters and other event parameters is generated and sent to Meta via the CAPI API. Meta uses the `fbclid` parameter to identify the specific click while the other parameters help optimize the campaign.

### Set up a Smart Script landing page

To set up your smart script Meta Ads campaigns perform the following:

1. Set up the template for the campaign's OneLink attribution links. For more information, see [How to create OneLink templates](/docs/create-a-onelink-template#procedures).
2. Create a smart script. For more information, see [How to create a OneLink Smart Script](/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script).

   CALLSTART::Note::

   #### Note

   The instructions below focus on the specific steps required to set up a Meta Ads campaign with Smart Script. For a comprehensive guide on how to set up Smart Script campaigns see the [How to create a OneLink Smart Script](/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script) section of the [OneLink Smart Script V2 setup](/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script) article.

   CALLEND::
3. Make sure all relevant URL parameters are appended to the incoming URL. To review the parameters appended to the incoming URL, open Meta Ads Manager and check the URL parameters set during the creation of the destination URL. For more information see: [Set destination URL](#h_01HZKNS17KT8TRD2TGDBRGKBZ3).
4. Map the incoming URL parameters required for the Meta Ads campaign to the outgoing URL parameters that will be sent to AppsFlyer when the user clicks the CTA button:
   * **PID**: Make sure that Smart Script takes the `pid=metaweb_int` parameter value from the incoming URL and maps it to the corresponding parameters in the outgoing URL.
   * **FBCLID**: The `fbclid` parameter is essential for successfully sending in-app events postbacks to Meta. The outgoing  URL FBCLID  parameter mapping depends on your Smart Script version:

     * Version 2.8.1 and above: The `fbclid` parameter is forwarded automatically to the outgoing URL parameter when present in the incoming URL, eliminating the need for manual mapping.
     * Version 2.8.0 and below: The `fbclid` parameter should be mapped manually in the **URL parameter mapping** section of the **Smart Script** page:
       1. In **Mapping for**, select **Custom parameter**.
       2. In **Outgoing URL parameter** and **Incoming URL parameters** enter **fbclid**.CALLSTART::Note::

     #### Note

     To display in AppsFlyer raw data reports, the incoming `fbclid` parameter must also be mapped (in addition to the outgoing `fbclid` parameter) to one of the outgoing `af_sub[1-5]` parameters. For more information, see [Facebook FBCLID](/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id).

     CALLEND::

### Set up a Smart Script cross-platform landing page

To set up your smart script Meta Ads campaigns for cross-platform landing pages perform the following:

1. Set up the template for the campaign's OneLink attribution links. For more information, see [How to create OneLink templates](/docs/create-a-onelink-template#procedures).
   * Enable your OneLink template for cross-platform attribution, see [here](/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-1-create-or-edit-a%C2%A0onelink-template%C2%A0for-crossplatform-attribution).
2. Make sure all relevant URL parameters are appended to the incoming URL. To review the parameters appended to the incoming URL, open Meta Ads Manager and examine the URL parameters you set when you built the destination URL. For more information, see [Set destination URL](#h_01HZKNS17KT8TRD2TGDBRGKBZ3).
3. Decide for each incoming parameter the outgoing parameter to which it will be mapped. For example `af_site_id` in the incoming URL will be mapped to `af_site_id` in the outgoing URL.
4. Decide on the default value for the mandatory outgoing parameters that cannot be empty.
5. Send your developer the following information:
   * Your incoming - outgoing parameter mapping. The developer will create a script that generates an outgoing direct URL based on the incoming - outgoing parameter mapping.
   * The parameters default values. The script will populate the outgoing URL parameters with the default values whenever there are no corresponding incoming URL parameter values.
   * If you are using a OneLink attribution link, send the domain and template ID to your developer. The developer uses this to create the outgoing OneLink URL. For example: `yourbrand.onelink.me/A1b2` or Branded domain example: `click.yourbrand.com/A1b2`
   * Send your developer the following Dev Hub links:
     * [Instruction and code examples](https://dev.appsflyer.com/hc/docs/create-direct-click-url) on how to create the outgoing direct URLs to the non mobile platforms.
     * [A demo and instruction](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/) for creating a cross platform landing page.
   * Remind your developer to include the incoming `fbclid` parameter in the outgoing URL.

     CALLSTART::Note::

     #### Note

     To display in AppsFlyer raw data reports, the incoming `fbclid` parameter must also be mapped (in addition to the outgoing `fbclid` parameter) to one of the outgoing `af_sub[1-5]` parameters.

     CALLEND::

## Create a landing page with OneLink Smart Banners

**User journey:** The user clicks on a Meta ad and is directed to your mobile website. They land on a page and a Smart Banner is displayed with a CTA to download the app from the app store.

### End-to-end data flow

1. The Meta ad URL includes the the `pid=metaweb_int` parameter. When the user clicks on the ad an `fbclid` parameter is automatically appended to the clicked URL.
2. The User is redirected to the URL destination - a landing page containing a Smart Banner.
3. When the landing page loads, the Smart Banner fires an [impression](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url) event to AppsFlyer, which includes the incoming URL parameters. This impression enables view-through attribution for the landing page. To learn about impressions and view-through attribution, see [here](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url).
4. The Smart Banner generates the outgoing URL for the CTA button on the banner. The outgoing URL is based on the incoming URL parameters including the `fbclid` parameter. The Smart banner can generate only OneLink-based links.
5. When the user clicks the Smart Banner CTA button the click is fired and registered in AppsFlyer.
6. The user is redirected to the store and downloads the app.
7. When the user opens the app, the install event is registered in AppsFlyer.
8. AppsFlyer attributes the install based on probabilistic modeling or deterministically if the install referrer is available.
9. A postback containing the `fbclid` parameters and other event parameters is generated and sent to Meta via the CAPI API. Meta uses the `fbclid` parameter to identify the specific click while the other parameters help optimize the campaign.

### Set up a Smart Banners landing page

To set up your Smart Banners Meta Ads campaigns perform the following:

1. Set up the template for the campaign's OneLink attribution links. For more information, see [How to create OneLink templates](/docs/create-a-onelink-template#procedures).
2. Create a Smart Banner.

   CALLSTART::Note::

   #### Note

   The instructions below focus on the specific steps required to set up a Meta Ads campaign with Smart Banners. For a comprehensive guide on how to set up Smart Banners campaigns, see the [setup section](/docs/smart-banners-mobile-web-to-app-for-marketers#setup) of the [Smart Banners—mobile web-to-app (for marketers)](/docs/smart-banners-mobile-web-to-app-for-marketers) article.

   CALLEND::
3. Set the Smart Banner parameters for Meta Ads campaigns:
   * Make sure all relevant URL parameters are appended to the incoming URL. Most importantly the `pid=metaweb_int` and `fbclid` are available in the incoming URL to allow the Smart Banner to collect them. These two parameters are necessary for attribution and for sending postbacks to Meta Ads. To review the parameters that are appended to the incoming URL, open Meta Ads Manager and review the URL parameters that you set when you built the destination URL, see: [Set destination URL](#h_01HZKNS17KT8TRD2TGDBRGKBZ3).

## View web-to-app attribution data

Although web-based conversion events are sent to Meta under the original `metaweb_int` PID, they are reported in the AppsFlyer dashboard and raw data reports under the `Facebook Ads` PID. This applies to both primary conversion events and conversion assist events.

This unified reporting view lets you analyze both web and app campaign performance in one place, including full web and mobile cost reporting.

### View in the dashboard

All Meta web-to-app attributions appear under `Facebook Ads` in the Overview and Activity dashboards. This provides a single, consolidated view of campaign results across platforms. Use standard filters and breakdowns to compare app and web traffic within your Meta Ads data.

### View in raw data and API reports

* **Raw data exports and API responses** include the `Facebook Ads` PID in the `media_source` field for Meta web activity. To verify web campaign setup details, refer to the `original_url` field that shows `metaweb_int` as the PID used during the creation of web campaigns.
* **Postback reports** show `metaweb_int` as the original media source to which the postback was sent.

## Traits and Limitations



| Trait | Remarks |
| --- | --- |
| Cost, clicks, and impressions data | Cost, clicks, and impressions data for Meta Ads Web (`metaweb_int`) is supported through the Meta Ads integration (`Facebook Ads`).<br /><br />* To get the data, make sure to connect the ad network account to the main PID (`Facebook Ads`):<br />  * ROI360 subscribers: in the **Cost Settings** page,<br />  * ROI360 non-subscribers: in the **Active Integration** page (**Cost** tab).<br />* To view cost, clicks, and impressions data for Meta Ads Web campaigns, make sure the campaign ID ([af\_c\_id](/docs/about-link-structure-and-parameters#af_c_id)) is included in the attribution link.<br />* The attribution link must include the full campaign hierarchy to view cost, clicks, and impressions data tied to attribution at the most granular level. |