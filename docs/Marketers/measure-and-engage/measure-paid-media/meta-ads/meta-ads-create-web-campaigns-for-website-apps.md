---
title: Meta Ads—Create web campaigns for website apps
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
  created_at: '2026-04-28T14:18:14Z'
  edited_at: '2026-10-16T09:33:29Z'
  id: 46172666260241
  locale: en-us
  section: Meta ads
  section_id: 6551109855761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/46172666260241-Meta-Ads-Create-web-campaigns-for-website-apps
---
> **At a glance:** Set up a Meta Ads integration for your website app to send web conversion signals to Meta via the Conversions API (CAPI). Meta uses these signals to optimize ad targeting and measure campaign performance.

<div id="overview" />

## Overview

AppsFlyer supports integration with Meta Ads (`metaweb_int`) for website app campaigns. The integration lets you report attribution and conversion data directly through Meta's Conversions API (CAPI), which Meta then uses to optimize ad targeting, measure performance, and build custom audiences.

Here's how it works: a user clicks a Meta ad and lands on your website. AppsFlyer captures any conversion events the user completes, such as a purchase or sign-up, and sends that signal to Meta via CAPI. Meta uses this data to refine targeting and evaluate campaign results.

<div id="note" />

> 📘 **Note**
>
> The current Meta Web integration does not support sending re-engagement postbacks to CAPI.

<div id="prerequisites" />

### Prerequisites

Before activating the Meta Ads integration, make sure you have:

* A website app set up in AppsFlyer. For more information, see:
  * <Anchor target="_blank" href="/marketers/docs/adding-an-app-to-appsflyer#web">Adding a web app</Anchor>
  * <Anchor target="_blank" href="/marketers/docs/configure-web-performance-measurement-settings">Configure Web Performance Measurement settings</Anchor>
* A <Anchor target="_blank" href="https://www.facebook.com/business/help/1710077379203657?id=180505742745347">business account in Meta Business Manager</Anchor>.

<div id="set-up-meta-ads-web-campaigns-for-website-apps" />

## Set up Meta Ads web campaigns for website apps

The setup involves defining the integration between Meta Ads and AppsFlyer and configuring the campaign in both platforms. Complete both parts in order.

* [Part 1: Set up Meta Ads integration in AppsFlyer](#part-1-set-up-meta-ads-integration-in-appsflyer) (required)
* [Part 2: Set up AppsFlyer integration in Meta Ads](#part-2-set-up-appsflyer-integration-in-meta-ads) (required)

<div id="part-1-set-up-meta-ads-integration-in-appsflyer" />

## Part 1: Set up Meta Ads integration in AppsFlyer

Start by activating the Meta Ads integration and defining the postbacks AppsFlyer sends to CAPI.

<div id="step-1-activate-the-meta-ads-integration" />

<Accordion title="Step 1: Activate the Meta Ads integration">

To activate the Meta Ads integration:

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Partner Marketplace**.
2. Search for **Meta Ads** and select it.
3. Click **Set up integration**. You are directed to the **Active Integrations** setup page.
4. In the **Integration** tab, turn on **Activate Partner**.

   <div id="note-1" />

   > 📘 **Note**
   >
   > The toggle must stay on (<Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">activated</Anchor>) for as long as you work with the partner.

5. Complete the **Pixel ID** field. To retrieve your pixel ID from Meta Ads Manager:
   1. <span class="af-ol-a"></span>From the <Anchor target="_blank" href="https://www.facebook.com/ads/manager">Ads Manager</Anchor> side menu, go to **All tools** > **Events Manager**.

      <div id="note-2" />

      > 📘 **Note**
      >
      > Make sure you have the correct business selected from the dropdown in the top right.

   2. From the **Events Manager** side menu, select **Data sources**. You'll see a list of your pixels. If you don't have a pixel for the selected business, you can create one from the same view.
   3. Copy the pixel ID shown under the pixel name and paste it into the **Pixel ID** field in AppsFlyer.
6. Complete the **Access Token** field. To retrieve your access token, follow <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token">these instructions</Anchor>.
7. Turn on **Limit Meta Ads' use of users' personal information (CCPA)** to enable compliance with <Anchor target="_blank" href="/marketers/docs/send-opendsr-api-requests">data protection laws</Anchor>.

   <div id="note-3" />

   > 📘 **Note**
   >
   > Complying with CCPA privacy regulations limits the data coming from Meta Ads users based in California.


</Accordion>

<div id="step-2-set-inapp-event-postbacks" />

<Accordion title="Step 2: Set in-app event postbacks">

You can define which web conversion events AppsFlyer sends to Meta Ads by mapping AppsFlyer events to Meta Ads events. These postbacks can be viewed in the <Anchor target="_blank" href="https://www.facebook.com/business/help/1541268312717919?id=818859032317965">Meta Events Manager</Anchor>. Meta uses the mapped events for campaign optimization and reporting.

To set in-app event postbacks:

1. Turn on **In-app event postbacks**.
2. If required, set the in-app event postback window. For more information, see <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#in-app-event-postback-window">In-app event postback window configuration</Anchor>.
3. Click **Add event** to add an event to the list.
4. In the **AppsFlyer event** column, select the event name from the dropdown list. AppsFlyer receives the event name from the Web SDK integrated on your website, or from server-to-server (S2S) events you send to AppsFlyer.
5. In the **Mapped to partner event** column, select the most suitable predefined partner event from the dropdown list, or select **CUSTOM**.
6. In the **For users from** column, select the sending option for the event:
   * **This partner only**: Send postbacks only when this event is attributed to Meta Ads.
   * **All media sources, including organic**: Send postbacks for events attributed to any partner and organic events.
7. In the **Including** column, select whether events are sent with their revenue values. See <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks">Data to include in the postbacks</Anchor>.

   <div id="important" />

   > 🚧 **Important!**
   >
   > If you are setting a purchase event, set the **Including** column to **Values and revenue**. Selecting any other option causes the postback to fail.

8. [Optional] Click the **Add condition** icon to <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">set conditions</Anchor> for an event.
9. Click **Save integration**.

<div id="note-4" />

> 📘 **Note**
>
> If you also run the Meta Pixel on your website, send the same event ID to both AppsFlyer and Meta so AppsFlyer can deduplicate the events:
>
> * Include `af_customer_event_id` in the event payload you send to AppsFlyer. For the Web SDK, send it inside `eventValue`. For the S2S (server-to-server) API, send it either as a top-level field or inside `event_value`.
> * Send the same value in the corresponding Pixel event.
>
> AppsFlyer forwards this value to Meta as the event ID. Meta then uses it to deduplicate the server-side event it receives from AppsFlyer against the Pixel event, so AppsFlyer counts the conversion once.
>
> If you don't send `af_customer_event_id`, AppsFlyer generates an event ID automatically. This ID won't match your Pixel events.
>
> For more information, see <Anchor target="_blank" href="/marketers/docs/integrate-appsflyer-web-sdk">[Beta] Integrate AppsFlyer Web SDK</Anchor>.

<div id="note-5" />

> 📘 **Note**
>
> If you send S2S events and want AppsFlyer to send postbacks for them to Meta Ads, make sure each event includes at least one of `ip`, `user_agent`, or `customer_user_id`. If all three are missing, AppsFlyer doesn't send the postback. For all supported event fields, see <Anchor target="_blank" href="/marketers/docs/server-to-server-s2s-api-for-web-performance-measurement#measure-an-event">Server-to-Server (S2S) API for Web Performance Measurement</Anchor>.

</Accordion>

<div id="part-2-set-up-appsflyer-integration-in-meta-ads" />

## Part 2: Set up AppsFlyer integration in Meta Ads

Complete the following steps in Meta Ads Manager.

<div id="step-1-set-the-campaign-type-objective-and-goals" />

<Accordion title="Step 1: Set the campaign type, objective, and goals">

1. Log in to Meta Ads and create a campaign.
2. In **Campaign objective**, select one of the following:
   * **Sales**: Lets Meta optimize toward a specific event (your main KPI).
   * **Traffic**: Lets Meta optimize toward ad clicks. Use this option only if you don't have other KPIs or if the volume of other KPI events is too low.
3. [Optional] To add a custom objective, do the following:

   1. In Meta Ads, select the custom event you want to set as a campaign objective and mark it as a conversion action.
   2. In AppsFlyer, on the **Meta Web integration** page, under **In-app event postbacks**, map an AppsFlyer event to a custom partner event in the **Mapped to partner event** column. Give it the same name as the conversion action in Meta Ads.

   <div id="note-6" />

   > 📘 **Note**
   >
   > To learn more about Meta campaign objectives, see the <Anchor target="_blank" href="https://www.facebook.com/business/help/175683976191028">Meta documentation</Anchor>.

4. In **Conversion location**, select **Website**.
5. In **Pixel**, enter the same pixel ID you entered for `metaweb_int` in the AppsFlyer Partner Marketplace. To learn more about the Meta Pixel, see the <Anchor target="_blank" href="https://www.facebook.com/business/help/742478679120153">Meta documentation</Anchor> (login required).
6. Click **Next**.

</Accordion>

<div id="step-2-set-destination-url" />

<Accordion title="Step 2: Set destination URL">

1. Under **Destination**, in the **Website URL** field, enter the URL that serves as the destination for your ad. Choose one of the following:

   * **Website URL**: Use your website URL when you want users to land directly on your website and complete web conversion events, such as a purchase or sign-up.
   * **AF attribution link (OneLink)**: Use an AF attribution link when you want users to be redirected to your mobile app, with a fallback to your website if the app is not installed. This is useful when your campaign targets both app and web users. For more information, see <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink links and experiences</Anchor>.

   <div id="important-1" />

   > 🚧 **Important!**
   >
   > In some cases, using AF attribution links might cause errors. If this occurs, ask your Meta representative for a solution, or use your website URL as the destination URL instead.

2. Click **Build a URL parameter** to add URL parameters to the destination URL.
3. Under **Custom parameters**, click **Add parameter**.
4. Map the AppsFlyer parameters to their Meta values as shown in the table below:

| AF parameter | Mapped Meta value |
| --- | --- |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `metaweb_int` |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#c">`c`</Anchor> | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

An example of a resulting URL:

```http
https://www.example.com?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}
```

<div id="note-7" />

> 📘 **Note**
>
> Meta automatically appends `fbclid={{fbclid}}` to the destination URL when the ad is clicked.

<div id="tip" />

> 👍 **Tip**
>
> To simplify campaign analysis, include the campaign type (web or mobile) as a prefix or suffix in the campaign name, for example, `campaign-name_web`.

<div id="see-also" />

> 📄 **See also**
>
> * For best practices on building your ad URL with all relevant parameters, see <Anchor target="_blank" href="/marketers/docs/about-traffic-source-resolution">About traffic source resolution</Anchor>.

</Accordion>

<div id="step-3-select-tracked-events" />

<Accordion title="Step 3: Select tracked events">

Use the **Tracking** section to select the conversion events promoted by your ad. You set up events via the <Anchor target="_blank" href="https://www.facebook.com/business/help/898185560232180?id=1205376682832142">Events Manager</Anchor>.

<div id="important-2" />

> 🚧 **Important!**
>
> Do not choose **App Events**. Doing so causes Meta to claim those conversions via the SRN API, potentially leading to misaligned reporting and optimization.

</Accordion>

<div id="view-web-attribution-data" />

## View web attribution data

Here's what to expect when you review your attribution data after setup:

* **Dashboard:** In <Anchor target="_blank" href="/marketers/docs/my-dashboards#crossplatform-dashboard">the cross-platform dashboard</Anchor>, web and app data are displayed side by side, giving you a unified view of campaign performance across platforms.
* **Raw data exports and API responses** include Meta Web in the `media_source` field for Meta web activity.

<div id="measure-web-attribution-data-with-web-cost" />

## Measure web attribution data with web cost

You can get a complete performance view of web attribution data and web cost data from Meta Ads in the dashboard and in <Anchor target="_blank" href="/marketers/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">Cost ETL reports</Anchor>. To do this, make sure you have <Anchor target="_blank" href="/marketers/docs/roi360-onboarding-guide#about-roi360">the ROI360 package</Anchor> and complete the following setup:

1. Connect the cost to your website app via  `facebook_int` (not via `metaweb_int`)  from the **Cost** tab or the **Cost Settings** page. For more information about how to connect to cost, see <Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">Set up ROI360 cost API to measure cost data</Anchor>.
2. Include the campaign ID (`af_c_id`) in the landing page URL. Make sure the URL includes the full campaign hierarchy to view cost, clicks, and impressions matched to web attribution at the most granular level.

<div id="traits-and-limitations" />

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Clicks and impressions | Clicks and impressions for web campaigns require an <Anchor target="_blank" href="/marketers/docs/roi360-onboarding-guide">ROI360 subscription</Anchor>. |
| Re-engagement | Re-engagement postbacks via CAPI are not currently supported. |

<div id="see-also-1" />

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/web-performance-measurement-overview">Web Performance Measurement - Overview</Anchor>

<div data-zendesk-anchors="h_01KQA78RE9FRENQAK31Q641C0N=overview h_01KQA78RE9F82ZBVF4YZHZTEEX=note h_01KQA78RE93B09A9YH2FRB3XRR=prerequisites set-up-meta-ads-web-campaigns=set-up-meta-ads-web-campaigns-for-website-apps h_01KQA78RE9J681CJ8DQNWJC37H=set-up-meta-ads-web-campaigns-for-website-apps h_01KQA78RE93JYCV2P0DDZC0A4B=part-1-set-up-meta-ads-integration-in-appsflyer h_01KQA78RE94B1JSVJFWR1V9QE5=step-1-activate-the-meta-ads-integration h_01KQA78REA5VN1229F2J3QH794=note-1 h_01KQA78REANHAQ88N4MXWM832D=note-2 h_01KQA78REA08SNB0BKCJDJZ2R0=note-3 h_01KQA78REACR7QTMQWJMV6VJSF=step-2-set-inapp-event-postbacks h_01KQA78REA1EB5ZHX4HKJSW7ZD=important h_01M520Y7YQYY70W2S24N2AXRG4=note-5 h_01KQA78REAEZQPDSKZ0GRNKEJJ=part-2-set-up-appsflyer-integration-in-meta-ads h_01KQA78REASX8JX1H37075WT82=step-1-set-the-campaign-type-objective-and-goals h_01KQA78REA5JZ44C4BE77JCHG8=note-6 h_01KQA78REAKBGQRC713FZ3J02P=step-2-set-destination-url h_01KQA78REAXZ1BFGC5BR75ZB5X=important-1 h_01KQA78REARWGQDCJ4KN3FM120=note-7 h_01KQA78REA7MZSG5JZ1XX2C65P=tip h_01KQA78REA3ZW7W9M3VFSQASB6=see-also h_01KQA78REASTZH19CM58M5Z43R=step-3-select-tracked-events h_01KQA78REBHCR1AHA254BTFZC6=important-2 h_01KQA78REBK1PWXNA1PM9118TA=view-web-attribution-data h_01KNM00RR9TF8JRTJXWN23MF1S=measure-web-attribution-data-with-web-cost h_01KQAE3JKMQ6ZEATDAEXBC4PT6=traits-and-limitations h_01KQC27K5KWP3A6HMM2W7N3MVB=see-also-1" />
