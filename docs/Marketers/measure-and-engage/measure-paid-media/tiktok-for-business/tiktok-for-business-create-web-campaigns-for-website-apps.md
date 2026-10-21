---
title: TikTok for Business—Create web campaigns for website apps
metadata:
  keywords:
    - Web Attribution
    - Web Attribution SDK
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-04-29T07:09:07Z'
  edited_at: '2026-08-30T15:27:34Z'
  id: 46191822292113
  locale: en-us
  section: TikTok for Business
  section_id: 12192554266385
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/46191822292113-TikTok-for-Business-Create-web-campaigns-for-website-apps
---
**At a glance:** Set up a TikTok Web Ads integration for your website app to send web conversion signals to TikTok via the Events API.

## Overview

AppsFlyer supports integration with TikTok Web Ads (`tiktokweb_int`) for website app campaigns, letting you report attribution and conversion data directly through TikTok's Events API. TikTok can then use this data to optimize ad targeting, measure performance, and build custom audiences.

Here's how it works: when a user clicks a TikTok ad and lands on your website, and then completes a website event (for example, a purchase or sign-up), AppsFlyer sends the conversion signal to TikTok via the Events API. TikTok uses this data to optimize ad targeting and measure campaign performance.

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/web-performance-measurement-overview">Web Performance Measurement - Overview</Anchor>

> 🚧 **Important!**
>
> At present, the integration does not support sending re-engagement postbacks via the Events API.

### Prerequisites

Before activating the TikTok Web Ads integration for your website app, make sure you have:

* A website app set up in AppsFlyer
* A business account in <Anchor target="_blank" href="https://getstarted.tiktok.com/grow-your-business-gb">TikTok Ads Manager</Anchor>

### How to set up TikTok Web Ads for your website app

The setup involves defining the integration between TikTok Web Ads and AppsFlyer, and configuring the campaign in TikTok Ads Manager. It includes the following parts:

* [Part 1: Set up TikTok Web Ads integration in AppsFlyer](#part-1-set-up-tiktok-web-ads-integration-in-appsflyer) (Required)
* [Part 2: Set up AppsFlyer integration in TikTok Web Ads](#part-2-set-up-appsflyer-integration-in-tiktok-web-ads) (Required)

## Part 1: Set up TikTok Web Ads integration in AppsFlyer

Start by activating the TikTok Web Ads integration and setting the postbacks AppsFlyer sends to the Events API.

<div id="1-activate-the-tiktok-ads-integration" />

<Accordion title="1. Activate the TikTok Web Ads integration">

To activate the TikTok Web Ads integration:

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Partner Marketplace**.
2. Search for **TikTok For Business - Advanced SRN** (or `tiktokweb_int`) and select it.
3. Click **Set up integration**. You're directed to the **Active Integrations** setup page.
4. In the **Integration** tab, turn on **Activate Partner**. The toggle must stay on for as long as you work with the partner.
5. **Pixel ID:** Enter the Pixel ID. You can generate it or retrieve it from your TikTok Ads Manager by following the instructions in the <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">TikTok documentation</Anchor>.
6. **Access token:** Enter the access token. To generate or retrieve it, follow the same <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">TikTok documentation</Anchor>.
7. **Limit TikTok Web Ads' use of users' personal information (CCPA):** Turn on this toggle to enable compliance with <Anchor target="_blank" href="/marketers/docs/send-opendsr-api-requests">data protection laws</Anchor>.

> 📘 **Note**
>
> Enabling CCPA compliance limits the data coming from TikTok Web Ads users based in California or other sensitive states in the US.

</Accordion>

<div id="2-set-inapp-event-postbacks" />

<Accordion title="2. Set in-app event postbacks">

You can define which web conversion events AppsFlyer sends to TikTok Ads by mapping AppsFlyer events to TikTok Web Ads events. These postbacks can be viewed in TikTok Ads Manager, and TikTok uses the mapped events for campaign optimization and reporting.

To set in-app event postbacks:

1. Turn on **In-app event postbacks**.
2. If required, set the in-app event postback window. Read more
   about in-app event postback window configuration in
   <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#in-app-event-postback-window">In-app event postback configuration</Anchor>.
3. Click **Add event** to add an event to the list.
4. In the **AppsFlyer event** column, select the
   event
   name from the drop-down list. AppsFlyer receives the event
   name
   either from the Web SDK integrated on your website or from
   server-to-server
   (S2S) events you send to AppsFlyer.
5. In the **mapped to partner event** column, select
   the most suitable pre-defined partner event.
6. In the **For Users From** column, select the
   appropriate
   option:
   * **This partner only**, to send events
     attributed
     to TikTok Web Ads only.
   * **All media sources, including organic**,
     to send all events regardless of attribution source.
7. In the **including** column, select whether
   events
   will be sent with their revenue values. See
   <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks">Data to include in the postbacks</Anchor>.

   > 📘 **Note**
   >
   > * If you are setting a purchase event, set the
   >   **including** column to
   >   **Values and revenue**. Selecting any other
   >   option will cause the postback to fail.
   > * Currently, only the purchase event can be set to include
   >   revenue.

8. [Optional] Click the **Add condition** icon
   to
   <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">set conditions</Anchor>
   for an event.
9. Click **Save integration**.

> 📘 **Note**
>
> If you also run the TikTok Pixel on your website, send
> the same event ID
> to both AppsFlyer and TikTok so AppsFlyer can deduplicate
> the events:
>
> * Include `af_customer_event_id` in the
>   event payload you
>   send to AppsFlyer, inside `eventValue`
>   for the Web SDK
>   or `event_value` for the S2S (server-to-server)
>   API.
> * Send the same value in the corresponding Pixel event.
>
> AppsFlyer forwards this value to TikTok as the event
> ID. TikTok then uses
> it to deduplicate the server-side event it receives from
> AppsFlyer against
> the Pixel event, so AppsFlyer counts the conversion once.
>
> If you don't send `af_customer_event_id`,
> AppsFlyer generates
> an event ID automatically. This ID won't match your Pixel
> events.
>
> For more information, see
> <Anchor target="_blank" href="/marketers/docs/integrate-appsflyer-web-sdk">[Beta] Integrate AppsFlyer Web SDK</Anchor>.

</Accordion>

## Part 2: Set up AppsFlyer integration in TikTok Web Ads

Complete the following steps in TikTok Ads Manager.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Set the campaign type, objective, and goals">

You can choose any pre-defined in-app event sent from AppsFlyer as your campaign goal. Select a campaign objective that aligns with your website conversion goals, for example, driving traffic to your website or optimizing for on-site conversions.

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. Set destination URL">

1. Under **Destination**, in the **Website URL** field, enter the URL of your website, which is the page where users land after clicking your ad.

   **Website URL** is the primary destination option. Users click the ad and land directly on your website to complete conversion events.
2. **[Alternative] AF attribution link (OneLink):** If you want to redirect users to the mobile app with a fallback to the website, you can use an AF attribution link (OneLink) as the destination URL instead.
3. Click **Build a URL parameter** to add the URL parameters to the destination URL.
4. Under **Custom parameters**, click **Add parameter**.
5. Map the AppsFlyer parameters to their TikTok values:

| AF parameter | Mapped TikTok value |
| --- | --- |
| `pid` | `tiktokweb_int` |
| `c` | `__campaign_name__` |
| `af_c_id` | `__campaign_id__` |
| `af_adset` | `__aid_name__` |
| `af_adset_id` | `__aid__` |
| `af_ad` | `__cid_name__` |
| `af_ad_id` | `__cid__` |

   > 📘 **Note**
   >
   > To simplify campaign analysis, include the campaign type (web or mobile) as a prefix or suffix in the campaign name, for example, `campaign-name_web`.


   For best practices on URL parameter configuration and traffic source resolution, see <Anchor target="_blank" href="/marketers/docs/about-traffic-source-resolution">About traffic source resolution</Anchor>.

   An example of the resulting URL:

   ```
   https://www.example.com?pid=tiktokweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__
   ```

   > 📘 **Note**
   >
   > TikTok automatically adds `ttclid={{ttclid}}` to the destination URL when the ad is clicked.


</Accordion>

## View web attribution data

Web conversion events are reported under the `tiktokweb_int` PID in the `media_source` field. To view web attribution data, use raw data reports and filter by `media_source = tiktokweb_int` to isolate TikTok website app conversions.

Dashboard reporting for website app campaigns is not yet available. A unified reporting view that lets you analyze web campaign performance alongside other channels is planned for a future release.

## Measure cost, clicks, and impressions

Measure TikTok cost, clicks, and impressions alongside your web attribution data in the dashboard and in Cost ETL reports (ROI360 customers only).

1. **Connect TikTok as a cost integration on your web app:** Go to the **Cost** tab or **Cost Settings** page and connect via `tiktokglobal_int`. For step-by-step instructions, see <Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data">Set up ROI360 cost API to measure cost data</Anchor>.
2. **Add the campaign ID to your landing page URL:** Include `af_c_id` along with the full campaign hierarchy in the landing page URL. This ensures cost, clicks, and impressions are matched to your web attribution data at the most granular level.

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Re-engagement | Re-engagement postbacks via the Events API are not currently supported. |

<div data-zendesk-anchors="h_01KQC152Q49R7P96BPMMZGVZWS=overview h_01KQC25PY3PPRTQBJ7K8NV3JWQ=see-also h_01KQC152Q42VT7XKTGCEJV7V7S=important h_01KQC152Q4A31VJ1JTXWJG6CN0=prerequisites how-to-set-up-tiktok-ads-for-your-website-app=how-to-set-up-tiktok-web-ads-for-your-website-app h_01KQC152Q4S1VTK7BGWPHHD27W=how-to-set-up-tiktok-web-ads-for-your-website-app part-1-set-up-tiktok-ads-integration-in-appsflyer=part-1-set-up-tiktok-web-ads-integration-in-appsflyer h_01KQC152Q4J5ZCSFVM8EZ8ZBTZ=part-1-set-up-tiktok-web-ads-integration-in-appsflyer h_01KQC152Q4WDH8W6AVV679JPGS=1-activate-the-tiktok-ads-integration h_01KQC152Q492SBJMJ3J10B1R84=note h_01KQC152Q4QWF2996MBS0BYCK7=2-set-inapp-event-postbacks h_01KQC152Q4561EWHVKB7A1AWDX=note-1 part-2-set-up-appsflyer-integration-in-tiktok-ads=part-2-set-up-appsflyer-integration-in-tiktok-web-ads h_01KQC152Q4NKQHF75Y14XCCFNH=part-2-set-up-appsflyer-integration-in-tiktok-web-ads h_01KQC152Q4TMJ0F09Q1PZYV71A=1-set-the-campaign-type-objective-and-goals h_01KQC152Q414XNHHR0Q2B8ZCST=2-set-destination-url h_01KQC152Q4F3WQKETR34WRHACT=note-3 h_01KQC152Q4BYHRW52BYBJHBGJ4=note-4 h_01KQC152Q45QE5M5BGD4RJNFR9=view-web-attribution-data h_01KQD9Z1XY7AB3CDE4FGHTKLM=measure-cost-clicks-and-impressions h_01KQC152Q45WC7HNZ64T98JJ6Y=traits-and-limitations" />
