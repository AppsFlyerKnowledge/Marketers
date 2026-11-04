---
title: Meta Ads— Create web-based campaigns
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
  created_at: '2024-06-04T16:08:28Z'
  edited_at: '2026-09-15T10:56:07Z'
  id: 25646834966033
  locale: en-us
  section: Meta ads
  section_id: 6551109855761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/25646834966033-Meta-Ads-Create-web-based-campaigns
---
> **At a glance:** Use Meta Ads Web campaigns to attribute web-to-app conversions from Meta Ads

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

* [Set up Meta Web Ads integration in AppsFlyer](#set-up-meta-web-ads-integration-in-appsflyer) (Required)
* [Set up AppsFlyer integration in Meta Ads](#set-up-appsflyer-integration-in-meta-ads) (Required)

And the following optional steps:

* [Create a landing page with OneLink Smart Script](#create-a-landing-page-with-onelink-smart-script) (Optional)
* [Create a landing page with OneLink Smart Banners](#create-a-landing-page-with-onelink-smart-banners) (Optional)

## Set up Meta Web Ads integration in AppsFlyer

Start with activating the Meta Ads integration and setting the postbacks AppsFlyer sends to CAPI.

<div id="a-activate-the-meta-ads-integration" />

<Accordion title="1. Activate the Meta Web Ads integration">

To activate the Meta Web Ads integration:

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Partner Integrations** > **Partner Marketplace**.
2. Search for **Meta Web** and select it. You're directed to the setup page.
3. In the **Integration** tab, turn on **Activate Partner**. **Note:** The toggle must stay on (<Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">activated</Anchor>) for as long as you work with the partner.
4. Turn off **Advanced Privacy** (if you are setting an iOS app integration).
5. **Advanced Matching data sharing:** Turn on to share Advanced Matching fields, such as hashed email, hashed phone number, hashed first name, hashed last name, and Facebook login ID, with Meta, if these fields are included in the event information sent to AppsFlyer. For more information, see: <Anchor target="_blank" href="/marketers/id/docs/advanced-matching-data-sharing">Advanced Matching Data Sharing</Anchor>.
6. Fill in the **Pixel ID** field. You can retrieve the pixel ID from your Meta ads Manager:
   1. <span class="af-ol-a"></span>From the [Ads manager](https://www.facebook.com/ads/manager) side menu, go down to **All tools** > **Events Manager**. **Note:** Make sure you have the correct business selected from the drop-down on the top right.
   2. From the **Events Manager** side menu, select **Data sources**. You'll see a list of your pixels. If you don't have a pixel for the selected business, you can create one through the same view.
   3. Copy the pixel ID showing under the pixel name.  
      and paste it into the  
      **Pixel ID** field in AppsFlyer.
7. Fill the **Access Token** field. To retrieve the access token, follow [these instructions](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)
8. Turn on **Limit Meta Ads' use of users' personal information (CCPA)** to enable compliance with <Anchor target="_blank" href="/marketers/id/docs/send-opendsr-api-requests">data protection laws</Anchor>. **Note:** Complying with CCPA privacy regulations limits the data coming from Meta Ads users based in California.

</Accordion>

<div id="d-enable-view-through-attribution-for-meta-web" />

<Accordion title="2. Enable view-through attribution">

AppsFlyer supports view-through attribution for Meta Web campaigns using a [Smart Script](#set-up-smart-script-crossplatform-landing-page) or [Smart Banner](#set-up-smart-banners-landing-page)-enabled landing page. This allows probabilistic modeling (PMOD) attribution of app installs triggered by ad impressions, even when users don't click the ad directly.

When a user clicks a Meta Web ad and lands on a [Smart Script](#set-up-smart-script-crossplatform-landing-page) or [Smart Banner](#set-up-smart-banners-landing-page)-enabled landing page, AppsFlyer can attribute the downstream app install. If available, the `fbclid` will be included in the postback to Meta to enhance attribution fidelity.

**To enable Meta Web view-through attribution:**

1. In AppsFlyer, from the sidebar, open **Collaborate** > **Partner Integrations > Active Integrations** > **Meta web ads**.
2. In the **Integration** tab, scroll to the **Install attribution** section.
3. Turn on **Install view-through attribution**.
4. **[optional]** Turn on **Cross-platform equal attribution priority** and set its lookback window. For more information, see <Anchor target="_blank" href="/marketers/id/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Enable equal priority for cross-platform impressions</Anchor>.
5. Open the **Attribution link** tab.
6. Scroll to the **View-through attribution** section and set the **view-through lookback window** (up to 24 hours).
7. Click **Save integration** to apply your settings.

</Accordion>

<div id="b-set-inapp-event-postbacks" />

<Accordion title="3. Set in-app event postbacks">

Installs are currently the only events that trigger automatic default postbacks to Meta Ads. For other event types, you can create custom postbacks by mapping AppsFlyer events to Meta Ads events, which can be viewed in the [Meta Events Manager](https://www.facebook.com/business/help/1541268312717919?id=818859032317965).  
To set in-app events postbacks perform the following:

1. Turn on **In-app event postbacks**.
2. If required, set the In-app event postback window (read more about in-app event postback window configuration in general in <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#in-app-event-postback-window">this article</Anchor>).
3. Click **Add event** to add an event to the list.
4. In the **AppsFlyer event** column, select the event name from the drop-down box. AppsFlyer receives the event's name either from the SDK integrated into your app or from server-to-server events.
5. In the **mapped to partner event** column, select from the dropdown box the most suitable pre-defined partner event or select CUSTOM.
6. In the **For Users From** column, select the sending option for the event:
   * **This partner only**: send postbacks only when this event is attributed to Meta ads.
   * **All media sources, including organic,** send postbacks for events attributed to any partner and organic events.
7. In the **including** column, select whether events will be sent with their revenue values. See <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#data-untuk-disertakan-dalam-postback">Data to include in the postbacks</Anchor>.

   > 📘 **Note**
   >
   > If you are setting a purchase event, set the **including** column to **Values and revenue**. Selecting any other option will cause the postback to fail.

8. [Optional] Click the **Add condition** icon to <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">set conditions</Anchor> for an event.
9. Click **Save integration**.
10. [Optional] After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
    1. <span class="af-ol-a"></span>From the top-left corner, click the app name under the partner name to open the list of apps.
    2. Select a different app from the drop-down list.
    3. Repeat the integration steps for the selected app.

> 📘 **Note**
>
> If you are sending S2S events to `metaweb_int`, the S2S payload must include the `ua` (User Agent) and `ip` (IP address) parameters. These values are required for Meta CAPI campaign optimization. AppsFlyer includes them automatically for SDK events. For S2S events, advertisers must send them explicitly. See <Anchor target="_blank" href="/marketers/id/docs/server-to-server-events-api-for-mobile-s2s-mobile">Server-to-server events API for mobile</Anchor>.

</Accordion>

## Set up AppsFlyer integration in Meta Ads

Perform the next steps in Meta Ads Manager.

<div id="a-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Set the campaign type, objective, and goals">

1. Log in to Meta Ads and create a campaign.
2. In **Campaign objective** select one of the following: [![](https://files.readme.io/a0cdd42ddf3bc69106de5137e5c842468178bd1dcd76805ea77ead750ba1e9bb-25646834955921.png)](https://files.readme.io/a0cdd42ddf3bc69106de5137e5c842468178bd1dcd76805ea77ead750ba1e9bb-25646834955921.png)
   * **Sales**: This lets Meta optimize towards a specific event (your main KPI).
   * **Traffic**: This lets Meta optimize towards ad clicks. This should only be used if you don't have other KPIs or if the volume of other KPI events is too low.
3. [Optional] If you want to add a custom objective to the above options perform the following:
   1. <span class="af-ol-a"></span>In Meta Ads, select the custom event that you want to set as a campaign objective and mark it as a conversion action in Meta Ads.
   2. In AppsFlyer, in the **Meta Web integration** page, under **In-app event postbacks** map an AppsFlyer event to a custom partner event (under the **mapped to partner event** column) and name it with the same name as the conversion action in Meta Ads.

      > 📘 **Note**
      >
      > To learn more about the Meta Campaign objectives, see the [Meta documentation](https://www.facebook.com/business/help/175683976191028).

4. In **Conversion location** select **Website**. [![](https://files.readme.io/32e4dcb4ced7e2011728ed709069b78cffffc4090f09a33c729a2b2e7e882e8b-25646834954257.png)](https://files.readme.io/32e4dcb4ced7e2011728ed709069b78cffffc4090f09a33c729a2b2e7e882e8b-25646834954257.png)
5. In **Pixel** enter the same pixel ID you entered for `metaweb_int` in the AppsFlyer Partner Marketplace. To learn more about the Meta Pixel, see the [Meta documentation](https://www.facebook.com/business/help/742478679120153) (a login is required).
6. Click **Next**.

</Accordion>

<div id="b-set-destination-url" />

<Accordion title="2. Set destination URL">

1. Under **Destination,** in the **Website URL** field, enter the URL that serves as the destination for your ad. The URL should be for one of the following:

   [![](https://files.readme.io/aec9109f2f3000f669799093460e70198de1934e483314b6cd7f95d8209f361d-25646834955537.png)](https://files.readme.io/aec9109f2f3000f669799093460e70198de1934e483314b6cd7f95d8209f361d-25646834955537.png)

   * **Web landing page:** Using a landing page is recommended when:

     * You have an app on multiple platforms.
     * You want to use the landing page to give more information about your advertised product.
     * You want to use the landing page to collect more data.

     For all these use cases create a [landing page with a Smart Script](#create-a-landing-page-with-onelink-smart-script) or [a Smart Banner](#create-a-landing-page-with-onelink-smart-banners).
   * **AF attribution links:** Using AF attribution links (OneLink, single platform or cross-platform) is recommended when you want the user to be redirected directly to the store to download the app without first visiting a landing page.

     > 🚧 **Important!**
     >
     > Sometimes, the use of AF attribution links may lead to errors. If this occurs, ask your Meta representatives for a solution, or simply use a Web landing page as the destination URL.

2. Click **Build a URL parameter** to add the URL parameters to the URL (whether it is a landing page URL or an AF attribution link).
3. Under **Custom parameters**, click **Add parameter**

   [![4.png](https://files.readme.io/bbce415e16d3442f8959bf7a0c23825035d7d4740d5bf3570306c3684c8764d4-25722672143633.png)](https://files.readme.io/bbce415e16d3442f8959bf7a0c23825035d7d4740d5bf3570306c3684c8764d4-25722672143633.png)
4. Map the AppsFlyer parameters to their Meta values.

   * If your destination URL is **a landing page, a OneLink attribution link, or a single platform attribution link**, map the following AF parameters to their Meta counterparts: 

| AF Parameter | Mapped Meta value |
| --- | --- |
| <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `metaweb_int` |
| <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#c">`c`</Anchor> | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

     An example of the resulting URL should be:

     ```http
     https://app.appsflyer.com/{app_id}?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={https://Add-your-store-url.com}
     ```

     * If your app's APK is NOT hosted in Google Play Store, add the <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor> parameter and map to it the store URL, e.g, `https://Add-your-store-url.com`
   * If your destination URL is a **PC or a console store**, create the link by following the instructions in the table below. For additional information see: <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-direct-attribution-links">CTV, PC, and console platform direct attribution links</Anchor>

<table><thead><tr><th colspan="2">Attribution link structure</th></tr></thead><tbody><tr><td>Base URL</td><td>engagements.appsflyer.com/v1.0/c2s/click/app/</td></tr><tr><td>Mandatory path parameters</td><td><ul><li>platform<br/>Example: steam</li><li>app_id<br/>Example: 123456</li></ul></td></tr><tr><td>Mandatory query parameters</td><td><ul><li>af_media_source</li><li>af_campaign_id</li><li>af_r</li></ul></td></tr><tr><td>Other parameters</td><td><a href="./ctv-pc-and-console-platform-direct-attribution-links#parameters" target="_blank">See all parameters</a></td></tr><tr><td>URL structure</td><td><code>https://engagements.appsflyer.com/v1.0/c2s/click/app/`{platform}/{app_id}?af_media_source={media_source}&amp;af_campaign_id={campaign_id}&amp;af_r={app_store_url}`</code></td></tr></tbody></table>

     Map the following AppsFlyer parameters to their Meta counterparts:

| AF Parameter | Mapped Meta value |
| --- | --- |
| `af_media_source` | `metaweb_int` |
| `af_campaign` | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

     An example of cross-platform URL:

     ```http
     https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
     ```

   > 📘 **Note**
   >
   > Meta adds the `fbclid={{fbclid}}` to the destination URL automatically when the ad is clicked


   > 👍 **Tip**
   >
   > To simplify campaign analysis, include the campaign type, web or mobile, as a prefix or suffix in the campaign name (e.g., campaign-name\_web)


> 📘 **Note**
>
> For a comprehensive guide on the AF link parameters, see <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#parameter-link-atribusi">Attribution link parameters</Anchor>.

</Accordion>

<div id="c-select-tracked-events" />

<Accordion title="3. Select tracked events">

Use the Tracking section to select the conversion events promoted by your ad (setting up of the events is done via the [Event Manager](https://www.facebook.com/business/help/898185560232180?id=1205376682832142)).

[![](https://files.readme.io/75b6136fdf3fd9790e39aeec735ccd2e1ff0b8a5f302c85f0ed3b05926fcc435-25646834958481.png)](https://files.readme.io/75b6136fdf3fd9790e39aeec735ccd2e1ff0b8a5f302c85f0ed3b05926fcc435-25646834958481.png)

> 🚧 **Important!**
>
> Make sure not to choose **App Events,** otherwise Meta will claim those conversions using the SRN API, which can cause reporting and optimization misalignments.

</Accordion>

## Create a landing page with OneLink Smart Script

**User journey:** The user clicks on a Meta ad and is directed to your mobile website. They land on a page with CTA buttons urging them to download your app from one or more platforms. Clicking the button redirects the user to the store.

<div id="end-to-end-data-flow" />

<Accordion title="End-to-end data flow">

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. The Meta ad URL includes the the `pid=metaweb_int` parameter. When the user clicks on the ad an `fbclid` parameter is automatically appended to the clicked URL.
2. The User is redirected to the URL destination - a landing page containing a Smart Script.
3. When the landing page loads, Smart Script fires an impression to AppsFlyer containing the incoming URL parameters. The impression will allow view-through attribution from the web landing page. To learn about impressions and view-through attribution, see <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">here</Anchor>.
4. Smart Script generates the outgoing URLs for the CTA buttons on the page based on the incoming URL parameters, including the `fbclid` parameter. The buttons can lead to:
   * Google Play and App Store via a OneLink attribution link.
   * Multiple platform stores (e.g., CTV, Epic and Steam). In this use case, Smart Script generates a single platform attribution link for each platform, leading to the specified platform's store.
   * Downloading an APK file to the user's device.
5. When the user clicks the CTA button, the click is fired and registered in AppsFlyer.
6. The user is redirected to the store and downloads the app.
7. When the user opens the app, the install event is registered in AppsFlyer.
8. AppsFlyer attributes the install based on probabilistic modeling or deterministically if an [install referrer](https://www.appsflyer.com/glossary/install-referrer/) is available.
9. A postback containing the `fbclid` parameters and other event parameters is generated and sent to Meta via the CAPI API. Meta uses the `fbclid` parameter to identify the specific click while the other parameters help optimize the campaign.

</Accordion>

<div id="set-up-smart-script-landing-page" />

<Accordion title="Set up a Smart Script landing page">

To set up your smart script Meta Ads campaigns perform the following:

1. Set up the template for the campaign's OneLink attribution links. For more information, see <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template#create-a-onelink-template">How to create OneLink templates</Anchor>.
2. Create a smart script. For more information, see <Anchor target="_blank" href="/marketers/id/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">How to create a OneLink Smart Script</Anchor>.

   > 📘 **Note**
   >
   > The instructions below focus on the specific steps required to set up a Meta Ads campaign with Smart Script. For a comprehensive guide on how to set up Smart Script campaigns see the <Anchor target="_blank" href="/marketers/id/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">How to create a OneLink Smart Script</Anchor> section of the <Anchor target="_blank" href="/marketers/id/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink Smart Script V2 setup</Anchor> article.

3. Make sure all relevant URL parameters are appended to the incoming URL. To review the parameters appended to the incoming URL, open Meta Ads Manager and check the URL parameters set during the creation of the destination URL. For more information see: [Set destination URL](#b-set-destination-url).
4. Map the incoming URL parameters required for the Meta Ads campaign to the outgoing URL parameters that will be sent to AppsFlyer when the user clicks the CTA button:
   * **PID**: Make sure that Smart Script takes the `pid=metaweb_int` parameter value from the incoming URL and maps it to the corresponding parameters in the outgoing URL.
   * **FBCLID**: The `fbclid` parameter is essential for successfully sending in-app events postbacks to Meta. The outgoing  URL FBCLID  parameter mapping depends on your Smart Script version:

     * Version 2.8.1 and above: The `fbclid` parameter is forwarded automatically to the outgoing URL parameter when present in the incoming URL, eliminating the need for manual mapping.
     * Version 2.8.0 and below: The `fbclid` parameter should be mapped manually in the **URL parameter mapping** section of the **Smart Script** page:
       1. In **Mapping for**, select **Custom parameter**.
       2. In **Outgoing URL parameter** and **Incoming URL parameters** enter **fbclid**.

     > 📘 **Note**
     >
     > To display in AppsFlyer raw data reports, the incoming `fbclid` parameter must also be mapped (in addition to the outgoing `fbclid` parameter) to one of the outgoing `af_sub[1-5]` parameters. For more information, see <Anchor target="_blank" href="/marketers/id/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id">Facebook FBCLID</Anchor>.


</Accordion>

<div id="set-up-smart-script-crossplatform-landing-page" />

<Accordion title="Set up a Smart Script cross-platform landing page">

To set up your smart script Meta Ads campaigns for cross-platform landing pages perform the following:

1. Set up the template for the campaign's OneLink attribution links. For more information, see <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template#create-a-onelink-template">How to create OneLink templates</Anchor>.
   * Enable your OneLink template for cross-platform attribution, see <Anchor target="_blank" href="/marketers/id/docs/set-up-cross-platform-links-for-multi-device-campaigns#create-a-onelink-templatefor-cross-platform-attribution">here</Anchor>.
2. Make sure all relevant URL parameters are appended to the incoming URL. To review the parameters appended to the incoming URL, open Meta Ads Manager and examine the URL parameters you set when you built the destination URL. For more information, see [Set destination URL](#b-set-destination-url).
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

     > 📘 **Note**
     >
     > To display in AppsFlyer raw data reports, the incoming `fbclid` parameter must also be mapped (in addition to the outgoing `fbclid` parameter) to one of the outgoing `af_sub[1-5]` parameters.


</Accordion>

## Create a landing page with OneLink Smart Banners

**User journey:** The user clicks on a Meta ad and is directed to your mobile website. They land on a page and a Smart Banner is displayed with a CTA to download the app from the app store.

<div id="end-to-end-data-flow::4f887e1c" />

<Accordion title="End-to-end data flow">

1. The Meta ad URL includes the the `pid=metaweb_int` parameter. When the user clicks on the ad an `fbclid` parameter is automatically appended to the clicked URL.
2. The User is redirected to the URL destination - a landing page containing a Smart Banner.
3. When the landing page loads, the Smart Banner fires an <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">impression</Anchor> event to AppsFlyer, which includes the incoming URL parameters. This impression enables view-through attribution for the landing page. To learn about impressions and view-through attribution, see <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">here</Anchor>.
4. The Smart Banner generates the outgoing URL for the CTA button on the banner. The outgoing URL is based on the incoming URL parameters including the `fbclid` parameter. The Smart banner can generate only OneLink-based links.
5. When the user clicks the Smart Banner CTA button the click is fired and registered in AppsFlyer.
6. The user is redirected to the store and downloads the app.
7. When the user opens the app, the install event is registered in AppsFlyer.
8. AppsFlyer attributes the install based on probabilistic modeling or deterministically if the install referrer is available.
9. A postback containing the `fbclid` parameters and other event parameters is generated and sent to Meta via the CAPI API. Meta uses the `fbclid` parameter to identify the specific click while the other parameters help optimize the campaign.

</Accordion>

<div id="set-up-smart-banners-landing-page" />

<Accordion title="Set up a Smart Banners landing page">

To set up your Smart Banners Meta Ads campaigns perform the following:

1. Set up the template for the campaign's OneLink attribution links. For more information, see <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template#create-a-onelink-template">How to create OneLink templates</Anchor>.
2. Create a Smart Banner.

   > 📘 **Note**
   >
   > The instructions below focus on the specific steps required to set up a Meta Ads campaign with Smart Banners. For a comprehensive guide on how to set up Smart Banners campaigns, see the <Anchor target="_blank" href="/marketers/id/docs/smart-banners-mobile-web-to-app-for-marketers#setup">setup section</Anchor> of the <Anchor target="_blank" href="/marketers/id/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners—mobile web-to-app (for marketers)</Anchor> article.

3. Set the Smart Banner parameters for Meta Ads campaigns:
   * Make sure all relevant URL parameters are appended to the incoming URL. Most importantly the `pid=metaweb_int` and `fbclid` are available in the incoming URL to allow the Smart Banner to collect them. These two parameters are necessary for attribution and for sending postbacks to Meta Ads. To review the parameters that are appended to the incoming URL, open Meta Ads Manager and review the URL parameters that you set when you built the destination URL, see: [Set destination URL](#b-set-destination-url).

</Accordion>

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
| Cost, clicks, and impressions data | Cost, clicks, and impressions data for Meta Ads Web (`metaweb_int`) is supported through the Meta Ads integration (`Facebook Ads`).<ul><li>To get the data, make sure to connect the ad network account to the main PID (`Facebook Ads`):<ul><li>ROI360 subscribers: in the **Cost Settings** page,</li><li>ROI360 non-subscribers: in the **Active Integration** page (**Cost** tab).</li></ul></li><li>To view cost, clicks, and impressions data for Meta Ads Web campaigns, make sure the campaign ID (<Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_c_id">af\_c\_id</Anchor>) is included in the attribution link.</li><li>The attribution link must include the full campaign hierarchy to view cost, clicks, and impressions data tied to attribution at the most granular level.</li></ul> |

<div data-zendesk-anchors="h_01HZKNS17JYFQ3F5TKNE5Q5TJ4=overview h_01J8CYG29BETYPZ03A1X54M3ZF=note prerequisite=prerequisites h_01HZKNS17JTCXE4JMZ64NEVPS6=prerequisites how-to-create-a-meta-ads-campaign=how-to-create-a-meta-web-ads-campaign h_01HZKNS17JERCAKZHK43ZQWARJ=how-to-create-a-meta-web-ads-campaign set-up-meta-ads-integration-in-appsflyer=set-up-meta-web-ads-integration-in-appsflyer h_01HZKNS17J284R2MAN42WV7F0S=set-up-meta-web-ads-integration-in-appsflyer h_01HZKNS17JGQBENY2X8S5PHFVH=a-activate-the-meta-ads-integration h_01ZXVWB1ZYKK4DP38QY1RMEY6M=d-enable-view-through-attribution-for-meta-web h_01HZKNS17JH2ZJKATV1AP6JDWP=b-set-inapp-event-postbacks 01JJ4MGS84WXEVG4FWQ0YQ7GN6=note-1 h_01_s2s_metaweb_ua_ip=note-2 h_01HZKNS17JJWX7N9W6BN05B57C=set-up-appsflyer-integration-in-meta-ads h_01HZKNS17JTVX8N5CKTKVGH0QB=a-set-the-campaign-type-objective-and-goals h_01HZKNS17JHHS7GYPBT441ND7A=note-3 h_01HZKNS17KT8TRD2TGDBRGKBZ3=b-set-destination-url h_01HZKNS17KCNKS4YY4JHMQRM1Z=important h_01J2V9WF300WDY0PWV68TDR9TT=note-4 h_01K88MSNRX9QFQ49FN2MXPMADX=tip 01J2V903C36X5K6VRPGQQGWFMW=note-5 h_01HZKNS17K07CENP8GG7MQRKHK=c-select-tracked-events h_01HZKNS17KARAENYPMVJSM1ARQ=important-1 create-landing-page-with-onelink-smart-script=create-a-landing-page-with-onelink-smart-script h_01HZKNS17KPJMP74HQKWY022T2=create-a-landing-page-with-onelink-smart-script h_01HZKNS17K5PRRXSD2JMJ54NTN=end-to-end-data-flow h_01HZKNS17KA8VAK5TDFG1NV9YN=set-up-smart-script-landing-page h_01HZKNS17K6DPA6E9CTM5F3X1A=note-9 h_01HZKNS17K2W4XJB0BH87RZYTJ=note-8 h_01HZKNS17K5RRAFFTNA6QT7AKJ=set-up-smart-script-crossplatform-landing-page h_01HZKNS17K03S4B3ZRQ62TRFRE=note-8 create-landing-page-with-onelink-smart-banners=create-a-landing-page-with-onelink-smart-banners h_01HZKNS17KH8NQ68RPZGMEAQTV=create-a-landing-page-with-onelink-smart-banners h_01HZKNS17K4Y7WSM14EEJ2G5NC=end-to-end-data-flow::4f887e1c h_01HZKNS17KZ3YKS5R52SRKR9P2=set-up-smart-banners-landing-page h_01HZKNS17K3W3GPV6TM5RQS1WP=note-9 meta%20view=view-web-to-app-attribution-data view-webtoapp-attribution-data-from-november-2-2025=view-web-to-app-attribution-data h_01K88J8JFNEYBZNR18133NMRP9=view-web-to-app-attribution-data h_01K88J8JFNMHCVZ0C34E3D7AST=view-in-the-dashboard h_01K88J8JFN8W2572N92466YFZQ=view-in-raw-data-and-api-reports 01JEZXJNF1C932KGAEFS4P5D51=traits-and-limitations" />
