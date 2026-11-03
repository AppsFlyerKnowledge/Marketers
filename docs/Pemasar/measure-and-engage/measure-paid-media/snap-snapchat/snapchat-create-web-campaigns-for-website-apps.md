---
title: Snapchat—Create web campaigns for website apps
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
  created_at: '2026-04-29T09:02:24Z'
  edited_at: '2026-10-16T09:31:21Z'
  id: 46196482479249
  locale: en-us
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/46196482479249-Snapchat-Create-web-campaigns-for-website-apps
---
> **At a glance:** Set up a Snapchat Ads integration for your website app to send web conversion signals to Snapchat via the Conversions API.

## Overview

AppsFlyer supports integration with Snapchat Ads (`snapweb_int`) for website app campaigns, letting you report attribution and conversion data directly through Snapchat's Conversions API. Snapchat can then use this data to optimize ad targeting, measure performance, and build custom audiences.

Here is how it works: a user clicks a Snapchat ad and lands on your website. When the user completes a website event (for example, a purchase or sign-up), AppsFlyer sends the conversion signal to Snapchat via the Conversions API. Snapchat uses this data to optimize ad targeting and measure campaign performance.

> 🚧 **Important!**
>
> At present, the integration does not support sending re-engagement postbacks via the Conversions API.

### Prerequisites

Before activating the Snapchat Ads integration for your website app, make sure you have:

* A website app set up in AppsFlyer
* A business account in <Anchor target="_blank" href="https://ads.snapchat.com/">Snapchat Ads Manager</Anchor>

### How to set up Snapchat Ads for your website app

The setup involves defining the integration between Snapchat Ads and AppsFlyer, and configuring the campaign in Snapchat Ads Manager. It includes the following steps:

* [Part 1: Set up Snapchat Ads integration in AppsFlyer (Required)](#part-1-set-up-snapchat-ads-integration-in-appsflyer)
* [Part 2: Set up AppsFlyer integration in Snapchat Ads (Required)](#part-2-set-up-appsflyer-integration-in-snapchat-ads)

## Part 1: Set up Snapchat Ads integration in AppsFlyer

Start by activating the Snapchat Ads integration. Then configure the postbacks that AppsFlyer sends to the Conversions API.

<div id="1-activate-the-snapchat-ads-integration" />

<Accordion title="1. Activate the Snapchat Ads integration">

To activate the Snapchat Ads integration:

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Marketplace**.
2. Search for **Snapchat** and select it.
3. Click **Set up integration**. You're directed to the **Active Integrations** setup page.
4. In the **Integration** tab, turn on **Activate Partner**. The toggle must stay on for as long as you work with the partner.
5. **Pixel ID:** Enter the Pixel ID. You can generate it or retrieve it from your Snapchat Ads Manager by following the instructions in the <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US">Snapchat Ads documentation</Anchor>.
6. **Access token:** Enter the access token. To create or retrieve it, follow the <Anchor target="_blank" href="https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted">instructions in the official Snapchat Ads documentation</Anchor>.

</Accordion>

<div id="2-set-inapp-event-postbacks" />

<Accordion title="2. Set in-app event postbacks">

You can define which web conversion events AppsFlyer sends to Snapchat Ads by mapping AppsFlyer events to Snapchat Ads events. These postbacks can be viewed in Snapchat Ads Manager. Snapchat uses the mapped events for campaign optimization and reporting.

To set in-app event postbacks:

1. Turn on **In-app event postbacks**.
2. If required, set the in-app event postback window. Read more in <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#in-app-event-postback-window">In-app event postback configuration</Anchor>.
3. Click **Add event** to add an event to the list.
4. In the **AppsFlyer event** column, select the event name from the list. AppsFlyer receives the event name either from the Web SDK integrated on your website or from server-to-server (S2S) events you send to AppsFlyer.
5. In the **Mapped to Partner Event** column, select the most suitable predefined partner event from the list.
6. In the **For Users From** column, select the appropriate option:
   * **This partner only** sends events attributed to Snapchat Ads.
   * **All media sources, including organic** sends all events regardless of attribution source.
7. In the **including** column, select whether to send events with their revenue values. See <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#data-untuk-disertakan-dalam-postback">Data to include in the postbacks</Anchor>.
8. [Optional] Click the **Add condition** icon to <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">set conditions</Anchor> for an event.

   > 📘 **Note**
   >
   > * If you are setting a purchase event, set the **including** column to **Values and revenue**. Selecting any other option causes the postback to fail.
   > * Currently, you can set only the purchase event to include revenue.

9. Click **Save integration**.

> 📘 **Note**
>
> If you also run the Snap Pixel on your website, send the same event ID to both AppsFlyer and Snapchat so AppsFlyer can deduplicate the events:
>
> * Include `af_customer_event_id` in the event payload you send to AppsFlyer. For the Web SDK, send it inside `eventValue`. For the S2S (server-to-server) API, send it either as a top-level field or inside `event_value`.
> * Send the same value in the corresponding Pixel event.
>
> AppsFlyer forwards this value to Snapchat as the event ID. Snapchat then uses it to deduplicate the server-side event it receives from AppsFlyer against the Pixel event, so AppsFlyer counts the conversion once.
>
> If you don't send `af_customer_event_id`, AppsFlyer generates an event ID automatically. This ID won't match your Pixel events.
>
> For more information, see <Anchor target="_blank" href="/marketers/id/docs/integrate-appsflyer-web-sdk">[Beta] Integrate AppsFlyer Web SDK</Anchor>.

> 📘 **Note**
>
> If you send S2S events and want AppsFlyer to send postbacks for them to Snapchat Ads, make sure each event includes either `ip` or `user_agent`. If both are missing, AppsFlyer doesn't send the postback. For all supported event fields, see <Anchor target="_blank" href="/marketers/id/docs/server-to-server-s2s-api-for-web-performance-measurement#measure-an-event">Server-to-Server (S2S) API for Web Performance Measurement</Anchor>.

</Accordion>

## Part 2: Set up AppsFlyer integration in Snapchat Ads

Perform the following steps in Snapchat Ads Manager.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Set the campaign type, objective, and goals">

You can choose any predefined in-app event sent from AppsFlyer as your campaign goal. Select a campaign objective that aligns with your website conversion goals, for example, driving traffic to your website or optimizing for on-site conversions.

</Accordion>

<div id="2-set-the-destination-url" />

<Accordion title="2. Set the destination URL">

1. Under **Destination**, in the **Website URL** field, enter the URL of your website, the page where users land after clicking your ad. **Website URL** is the main destination option. Users click the ad and land directly on your website to complete conversion events.
2. **[Alternative] AF attribution link (OneLink):** If you want to redirect users to the mobile app with a fallback to the website, you can use an AF attribution link (OneLink) as the destination URL instead.
3. Click **Build a URL parameter** to add the URL parameters to the destination URL.
4. Under **Custom parameters**, click **Add parameter**.
5. Map the AppsFlyer parameters to their Snapchat values:

| AF parameter | Mapped Snapchat value |
| --- | --- |
| `pid` | `snapweb_int` |
| `c` * | `{{campaign.name}}` |
| `af_c_id` | `{{campaign.id}}` |
| `af_adset` | `{{adSet.name}}` |
| `af_adset_id` | `{{adSet.id}}` |
| `af_ad` | `{{creative.name}}` |
| `af_ad_id` | `{{ad.id}}` |
| `af_channel` | `{{site_source_name}}` |

   * To simplify campaign analysis, include the campaign type (web or mobile) as a prefix or suffix in the campaign name, for example, `campaign-name_web`.

   For best practices on URL parameter configuration and traffic source resolution, see <Anchor target="_blank" href="/marketers/id/docs/about-traffic-source-resolution">About traffic source resolution</Anchor>.

   An example of the resulting URL:

   ```http
   https://www.example.com?pid=snapweb_int&c={{campaign.name}}&af_c_id={{campaign.id}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_channel={{site_source_name}}
   ```

> 📘 **Note**
>
> Snapchat adds `ScCid={{ScCid}}` to the destination URL automatically when the ad is clicked.

</Accordion>

## View web attribution data

Here's what to expect when you review your attribution data after setup:

* **Dashboard:** In <Anchor target="_blank" href="/marketers/id/docs/my-dashboards#crossplatform-dashboard">the cross-platform dashboard</Anchor>, web and app data are displayed side by side, giving you a unified view of campaign performance across platforms.
* **Raw data exports and API responses** include Snap Web in the `media_source` field for Snap web activity.

## Measure web attribution data with web cost

You can get a complete performance view of web attribution data and web cost data from Snapchat Ads in the dashboard and in <Anchor target="_blank" href="/marketers/id/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">Cost ETL reports</Anchor>. To do this, make sure you have <Anchor target="_blank" href="/marketers/id/docs/roi360-onboarding-guide#about-roi360">the ROI360 package</Anchor> and complete the following setup:

1. Connect the cost to your website app via  `snapchat_int` (not via `snapweb_int`)  from the **Cost** tab or the **Cost Settings** page. For more information about how to connect to cost, see <Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">Set up ROI360 cost API to measure cost data</Anchor>.
2. Include the campaign ID (`af_c_id`) in the landing page URL. Make sure the URL includes the full campaign hierarchy to view cost, clicks, and impressions matched to web attribution at the most granular level.

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Clicks and impressions | Clicks and impressions for web campaigns require an <Anchor target="_blank" href="/marketers/id/docs/roi360-onboarding-guide">ROI360 subscription</Anchor>. |
| Re-engagement | Re-engagement postbacks via the Conversions API are not currently supported. |

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/id/docs/web-performance-measurement-overview">Web Performance Measurement - Overview</Anchor>

<div data-zendesk-anchors="h_01KQC7RA5R1PS69N3015WY4QRY=overview h_01KQC7RA5RAY6R70GNHCYWAMRC=important h_01KQC7RA5R02QV60T81NX055DM=prerequisites h_01KQC7RA5RPWP0X927ENN6KJ9V=how-to-set-up-snapchat-ads-for-your-website-app h_01KQC7RA5RY1HF9VHC332FVBFR=part-1-set-up-snapchat-ads-integration-in-appsflyer h_01KQC7RA5RJXR5N13SYW3QMMDQ=1-activate-the-snapchat-ads-integration h_01KQC7RA5R3TZZ8PPHHC8EXPG1=2-set-inapp-event-postbacks h_01KQC7RA5RZVTM2X3N6WXRTAT8=note h_01M520TA4E64EARM6R1EV9QPSR=note-2 h_01KQC7RA5REPX0WDDHT7YWDHMC=part-2-set-up-appsflyer-integration-in-snapchat-ads h_01KQC7RA5R8MDFAF9R5YH1TFPX=1-set-the-campaign-type-objective-and-goals h_01KQC7RA5SB11HRSQR493PM121=2-set-the-destination-url h_01KQC7RA5S422C22YQX1VQ4R7A=note-3 h_01KQC7RA5SKRWGGCKV71MV8J56=view-web-attribution-data h_01KQC7XYSWPTHVDY5R3EG8H4K2=measure-web-attribution-data-with-web-cost h_01KQC7RA5SSZB8M8G00NTXG71K=traits-and-limitations h_01KQC80MBB1KCVVNDSFSJHG5ZT=see-also" />
