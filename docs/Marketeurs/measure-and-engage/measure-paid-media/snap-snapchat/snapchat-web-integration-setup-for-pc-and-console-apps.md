---
title: Snapchat—Web integration setup for PC and console apps
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2025-11-28T12:53:35Z'
  edited_at: '2026-09-15T10:17:44Z'
  id: 41396370612497
  locale: en-us
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/41396370612497-Snapchat-Web-integration-setup-for-PC-and-console-apps
---
> **At a glance:** Learn how to integrate Snapchat Ads web for PC and console apps with AppsFlyer and set up campaigns in Snapchat Ads web.

> ❗️ **Warning**
>
> This integration is only available for PC and console apps, such as Steam, Epic, or Native PC. For mobile apps, see the <Anchor target="_blank" href="/marketers/fr/docs/tiktok-for-business-advanced-srn-integration-setup">Snapchat Ads integration setup</Anchor> page.

## Overview

This article contains information and steps on how to set up and use Snapchat Ads web for PC and console apps with AppsFlyer.

### Prerequisite

Before activating the Snapchat Ads web integration, make sure you have a business account in <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/topic/0TO8b000000KfssGAC/ads-manager?language=en_US">Snapchat Ads Manager.</Anchor>

## Activating partner in AppsFlyer

**To activate the partner integration:**

1. In AppsFlyer, from the side menu, open **Collaborate** > **Partner Integrations > Marketplace** tab.
2. Search for **Snapchat Ads web** (`snapweb_int`).
3. Click **Integrate**. You’re directed to the setup page.
4. In the **Integration** tab, turn on **Activate partner**. The toggle must stay on (<Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">activated</Anchor>) for as long as you work with the partner.
5. Complete the configuration using the relevant tabs, as described in the next section.

## Setting up Snapchat Ads web in AppsFlyer

In this part of the setup, you can also set up postbacks to Snapchat Ads web via the Snapchat events API. The Snapchat Ads web (`snapweb_int`) integration uses an Events API tool provided by Snapchat Ads, allowing advertisers to send data from their **PC and console apps** directly to Snapchat's servers. Such data may include user actions, such as purchases, registrations, and other types of conversions performed on non-mobile platforms (websites or applications). The data is then used by Snapchat Ads to optimize ad targeting, measure ad performance, and build custom audiences for retargeting.

The integration with Snapchat Ads web only supports sending postbacks for installs and in-app events.

<div id="integration-tab" />

<Accordion title="Integration tab">

The **Integration** tab comprises several sections, as described below.

**Activate partner**

To configure the integration, you must first turn on the **Activate partner** toggle.

**General settings**

* **Pixel ID:** Enter the Pixel ID. You can create it or retrieve it from your Snapchat Ads Manager by following the instructions detailed in the <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US">Snapchat Ads official documentation</Anchor>[.](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US)
* **Access token:** Enter the access token. To generate it or retrieve it, follow the instructions [in](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US) the <Anchor target="_blank" href="https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted">Snapchat Ads official documentation</Anchor>[.](https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted)

**Enable view-through attribution**

AppsFlyer supports view-through attribution for Snapchat Ads web campaigns using probabilistic modeling (PMOD) and a [Smart Script](#create-a-landing-page-with-onelink-smart-script) or [Smart Banner](#create-a-landing-page-with-onelink-smart-banners)-enabled landing page. This allows AppsFlyer to attribute app installs that result from users viewing an ad and then later installing the app, even across platforms, without requiring a direct click.

When a user clicks a Snapchat ad on the web and lands on a [Smart Script](#create-a-landing-page-with-onelink-smart-script) or [Smart Banner](#create-a-landing-page-with-onelink-smart-banners)-enabled landing page, AppsFlyer can attribute the downstream app install. If available, the `ScCid` will be included in the postback to Snapchat to enhance attribution fidelity.

**To enable view-through attribution:**

1. In AppsFlyer, from the sidebar, open **Active Integrations** > **Snapchat Ads web ads**.
2. In the **Integration** tab, scroll to the **Install attribution** section.
3. Turn on **Install view-through attribution**.
4. **[optional]** Turn on **Cross-platform equal attribution priority** and set its lookback window. For more information, see <Anchor target="_blank" href="/marketers/fr/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Enable equal priority for cross-platform impressions</Anchor>.
5. Open the **Attribution link** tab.
6. Scroll to the **View-through attribution** section and set the **view-through lookback window** (up to 24 hours).
7. Click **Save integration** to apply your settings.

**Default postbacks**

Postbacks for installs are sent automatically only to Snapchat Ads web.

**In-app event postbacks**

Configure the mapping of in-app event postbacks that are sent to Snapchat Ads web. These events can be viewed in the [Snapchat Ads Manager](https://businesshelp.snapchat.com/s/topic/0TO8b000000KfssGAC/ads-manager?language=en_US).

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table lists and describes the fields:

| **Parameter name** | **Description** |
| --- | --- |
| AppsFlyer event | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<ul><li>Click Add item and enter the event name.</li></ul> |
| mapped to partner event | The unique name or ID of each event, as defined on the partner's side.<ul><li>Select from the list the most suitable pre-defined partner event.</li></ul> |
| for users from | This partner only: In-app event postbacks are sent only for events attributed to this partner. |
| including | Values and revenue: All event parameters, including the revenue value (if it exists in the event), are sent in the postback. |

3. [Optional] Click the **Add condition** icon to <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">set conditions</Anchor> for an event. For more information, see <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">Conditional in-app event postbacks</Anchor>.
4. Set the **In-app event postback window**. For more information, see i<Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#in-app-event-postback-window">n-app event postback window</Anchor>.
5. Click **Save integration**.
6. [Optional] After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
   1. From the top-left corner, under the partner name, click the app name to open the list of apps.
   2. Select a different app from the drop-down list.
   3. Repeat the integration steps for the selected app.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generating an attribution link in the AppsFlyer UI isn't currently available. You can use a cross-platform landing page with SmartScript, or you can create a direct attribution link for your app. See the table below.

<Table>
  <thead>
    <tr>
      <th>
        Option
      </th>
      <th>
        Actions
      </th>
      <th>
        Who's involved
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Cross-platform landing page
      </td>
      <td>
        **Recommended.** Use this option when your campaign promotes an app that’s available on multiple platforms, such as Epic and Steam.  
        <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Learn about cross-platform landing pages</Anchor>  

        <Anchor target="_blank" href="/marketers/fr/docs/cross-platform-landing-pages-with-smart-script">Learn how to set up a cross-platform landing page</Anchor>  
        Make sure all relevant URL parameters (that are later captured by the Smart Script) are appended to the ad URL

        * Make sure the script takes the `ScCid` value from the incoming URL and adds it to the generated link. This means you must map the outgoing `ScCid` URL parameter to the incoming `ScCid` parameter.  
          **Note:** To display `ScCid` in AppsFlyer raw data reports, the incoming `ScCid` parameter must also be mapped to one of the outgoing parameters `af_sub[1–5]`.
        * Optional. You can use Snapchat’s dynamic URL macros instead of hard-coding the values manually. For more info, see the [Snapchat official documentation](https://businesshelp.snapchat.com/s/article/add-url-macros?language=en_US).
      </td>
      <td>
        Marketer (may require developer assistance)
      </td>
    </tr>
    <tr>
      <td>
        Direct attribution link
      </td>
      <td>
        If you don't use a cross-platform landing page, because you only have one app on one platform, you can create direct attribution links to place behind ads.   
        <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-direct-attribution-links">Learn how to create direct attribution links</Anchor>

        Make sure the mandatory parameters are included in your link:

        * `af_media_source`
        * `af_campaign_id`
        * `af_r`

        **Template to use for Snapchat Ads web ad link:**

        ```
        https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source=snapweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_channel={{site_source_name}}&af_r={encoded landing page and URL params}
        ```

        **Sample link of a Snapchat ad web link leading to Steam:**

        ```
        https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=snapweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
        ```

        **Note**: The template includes some dynamic URL parameters supported by Snapchat. If you prefer, you can replace them with real values manually.
      </td>
      <td>
        Marketer
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost isn't available for Snapchat Ads web.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue isn't available for Snapchat Ads web.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Currently, permissions aren't granted to Snapchat Ads web.

</Accordion>

## Setting up campaigns in Snapchat Ads web for PC and console apps

Set up your campaign in Snapchat Ads Manager. For more information, see <Anchor target="_blank" href="/marketers/fr/docs/snapchat-create-web-based-campaigns#set-up-appsflyer-integration-in-snapchat-ads">Set up AppsFlyer integration in Snapchat Ads</Anchor>.

When you set up your new campaign:

* Select **Website** as the conversion location.
* When you name your Snapchat conversion pixel, enter the same pixel ID you entered for `snapweb_int` in the *AppsFlyer Partner Marketplace*.
* When you enter the website URL as the destination for your ad, the URL should be for one of the following:
  * Web landing page (recommended when you have an app on multiple platforms)
  * Store URL (recommended when your app is in a single app store, on a single platform)

## View web-to-app attribution data

Although web-based conversion events are sent to Snapchat under the original `snapweb_int` PID, they are reported in the AppsFlyer dashboard and raw data reports under the `snapchat_int` PID. This applies to both primary conversion events and conversion assist events.

This unified reporting view allows you to analyze the performance of both web and app campaigns in one place, including comprehensive web and mobile cost reporting.

### View in the dashboard

All Snapchat web-to-app attributions appear under `snapchat_int` in the Overview and Activity dashboards. This provides a single, consolidated view of campaign results across platforms. Use standard filters and breakdowns to compare app and web traffic within your Snapchat Ads data.

### View in raw data and API reports

* **Raw data exports and API responses** include the `snapchat_int` PID in the `media_source` field for Snapchat web activity. To verify web campaign setup details, refer to the `original_url` field that shows `snapweb_int` as the PID used during the creation of web campaigns.
* **Postback reports** show `snapweb_int` as the original media source to which the postback was sent.

## Traits and limitations

| Trait | Description |
| --- | --- |
| Clicks and impressions (Temporary limitation) | Clicks and impressions for campaigns targeting PC & Console apps are temporarily not available from Snapchat SRN. |

<div data-zendesk-anchors="h_01KB58BEK73PMXZXB8RA59YHM2=warning h_01KB58BEK78P4C35JYZXKJFPHW=overview h_01KB58BEK77YP1T2XCHZJ00V7S=prerequisite h_01KB58BEK7A3MJT4C9ZA9ZFGDA=activating-partner-in-appsflyer h_01KB58BEK7CGYB1DZJCG2WMH0Y=setting-up-snapchat-ads-web-in-appsflyer h_01KB58BEK7SE837F67MKRFY6K2=integration-tab h_01KB58BEK74Q2K3SNCPFQSCJ2B=attribution-link-tab h_01KB58BEK7WAVABV4YBR728FCF=cost-tab h_01KB58BEK7ESEZFARRQ3HB6P8H=ad-revenue-tab h_01KB58BEK7WXEFMSSB0QRE4E6B=permissions-tab h_01KB58BEK7D8760J2ZWJ9B1K3Y=setting-up-campaigns-in-snapchat-ads-web-for-pc-and-console-apps view-webtoapp-attribution-data=view-web-to-app-attribution-data h_01KB58BEK7M96WYN7YMERH7CWW=view-web-to-app-attribution-data h_01KB58BEK70FB5SYQAV938CB5W=view-in-the-dashboard h_01KB58BEK7YWM10A7RCNV7YDEM=view-in-raw-data-and-api-reports h_01KB58BEK7MDZGT7G7RQ9VK9MZ=traits-and-limitations" />
