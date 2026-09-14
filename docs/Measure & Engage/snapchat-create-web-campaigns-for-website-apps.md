---
title: "Snapchat—Create web campaigns for website apps"
excerpt: "Set up a Snapchat Web Ads integration for your website app to send web conversion signals to Snapchat via the Conversions API."
---
AppsFlyer supports integration with Snapchat Web Ads (`snapweb_int`) for website app campaigns, letting you report attribution and conversion data directly through Snapchat's Conversions API. Snapchat can then use this data to optimize ad targeting, measure performance, and build custom audiences. 

Here is how it works: when a user clicks a Snapchat ad and lands on your website, and then completes a website event (for example, a purchase or sign-up), AppsFlyer sends the conversion signal to Snapchat via the Conversions API. Snapchat uses this data to optimize ad targeting and measure campaign performance.

#### See also

- [Web Performance Measurement - Overview](https://support.appsflyer.com/hc/articles/43521734577809--Beta-AppsFlyer-Web-Attribution-Overview)

> 🚧 Important!
>
> At present, the integration does not support sending re-engagement postbacks via the Conversions API.

### Prerequisites

Before activating the Snapchat Web Ads integration for your website app, make sure you have:

- A website app set up in AppsFlyer
- A business account in [Snapchat Ads Manager](https://ads.snapchat.com/)

### How to set up Snapchat Web Ads for your website app

The setup involves defining the integration between Snapchat Web Ads and AppsFlyer, and configuring the campaign in Snapchat Ads Manager. It includes the following steps:

- [Part 1: Set up Snapchat Web Ads integration in AppsFlyer (Required)](#part-1-set-up-snapchat-web-ads-integration-in-appsflyer)
- [Part 2: Set up AppsFlyer integration in Snapchat Web Ads (Required)](#part-2-set-up-appsflyer-integration-in-snapchat-web-ads)

## Part 1: Set up Snapchat Web Ads integration in AppsFlyer

Start by activating the Snapchat Web Ads integration. Then configure the postbacks that AppsFlyer sends to the Conversions API.

### 1. Activate the Snapchat Web Ads integration

To activate the Snapchat Web Ads integration:

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Marketplace**.
2. Search for **Snapchat** and select it.
3. Click **Set up integration**. You're directed to the **Active Integrations** setup page.
4. In the **Integration** tab, turn on **Activate Partner**. The toggle must stay on for as long as you work with the partner.
5. **Pixel ID:** Enter the Pixel ID. You can generate it or retrieve it from your Snapchat Ads Manager by following the instructions in the [Snapchat Web Ads documentation](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US).
6. **Access token:** Enter the access token. To create or retrieve it, follow the [instructions in the official Snapchat Web Ads documentation](https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted).

### 2. Set in-app event postbacks

You can define which web conversion events AppsFlyer sends to Snapchat Ads by mapping AppsFlyer events to Snapchat Web Ads events. These postbacks can be viewed in Snapchat Ads Manager. Snapchat uses the mapped events for campaign optimization and reporting.

To set in-app event postbacks:

01. Turn on **In-app event postbacks**.

02. If required, set the in-app event postback window. Read more in [In-app event postback configuration](https://support.appsflyer.com/hc/articles/208439256-In-App-Events-Postback-Configuration#inapp-event-postback-window).

03. Click **Add event** to add an event to the list.

04. In the **AppsFlyer event** column, select the event name from the list. AppsFlyer receives the event name either from the Web SDK integrated on your website or from server-to-server (S2S) events you send to AppsFlyer.

05. In the **Mapped to Partner Event** column, select the most suitable predefined partner event from the list.

06. In the **For Users From** column, select the appropriate option:
    - **This partner only** sends events attributed to Snapchat Web Ads.
    - **All media sources, including organic**, are to send all events regardless of attribution source.

07. In the **including** column, select whether to send events with their revenue values. See [Data to include in the postbacks](/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks).

08. [Optional] Click the **Add condition** icon to [set conditions](https://support.appsflyer.com/hc/articles/208439256#conditional-inapp-event-postbacks) for an event.

    > 📘 Note
    >
    > - If you are setting a purchase event, set the **including** column to **Values and revenue**. Selecting any other option causes the postback to fail.
    > - Currently, you can set only the purchase event to include revenue.

09. Click **Save integration**.

If you also run the Snap Pixel on your website, send the same event ID to both AppsFlyer and Snapchat so AppsFlyer can deduplicate the events:

- Include `af_customer_event_id` in the event payload you send to AppsFlyer, inside `eventValue` for the Web SDK or `event_value` for the S2S (server-to-server) API.
- Send the same value in the corresponding Pixel event.

AppsFlyer forwards this value to Snapchat as the event ID. Snapchat then uses it to deduplicate the server-side event it receives from AppsFlyer against the Pixel event, so AppsFlyer counts the conversion once.

If you don't send `af_customer_event_id`, AppsFlyer generates an event ID automatically. This ID won't match your Pixel events.

For more information, see [[Beta] Integrate AppsFlyer Web SDK](https://support.appsflyer.com/hc/articles/43485611331473).

## Part 2: Set up AppsFlyer integration in Snapchat Web Ads

Perform the following steps in Snapchat Ads Manager.

### 1. Set the campaign type, objective, and goals

You can choose any predefined in-app event sent from AppsFlyer as your campaign goal. Select a campaign objective that aligns with your website conversion goals, for example, driving traffic to your website or optimizing for on-site conversions.

### 2. Set the destination URL

1. Under **Destination**, in the **Website URL** field, enter the URL of your website, the page where users land after clicking your ad. **Website URL** is the primary destination option. Users click the ad and land directly on your website to complete conversion events.
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

\* To simplify campaign analysis, include the campaign type (web or mobile) as a prefix or suffix in the campaign name, for example, `campaign-name_web`.

For best practices on URL parameter configuration and traffic source resolution, see [About traffic source resolution](https://support.appsflyer.com/hc/articles/43518064765201--Beta-About-traffic-source-resolution).

An example of the resulting URL:

```auto
https://www.example.com?pid=snapweb_int&c={{campaign.name}}&af_c_id={{campaign.id}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_channel={{site_source_name}}
```

> 📘 Note
>
> Snapchat adds `ScCid={{ScCid}}` to the destination URL automatically when the ad is clicked.

## View web attribution data

Here's what to expect when you review your attribution data after setup:

- **Raw data exports and API responses** include Snap Web in the `media_source` field for Snap web activity.
- To verify web campaign setup details, check the `original_url` field that shows `snapchat_int` as the PID used during web campaign creation.

> 📘 Note
>
> Dashboard reporting for website app campaigns is not yet available. A unified reporting view that lets you analyze web campaign performance alongside other channels is planned for a future release.

## Measure web attribution data with web cost

To get a complete performance view of web attribution data and web cost data from Snapchat Ads, in the dashboard and in [Cost ETL reports](/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl), make sure you have [the ROI360 package](/docs/roi360-onboarding-guide#overview%22%20target=%22_blank%22), and you complete the following setup:

1. Connect the cost to your website app via `snapchat_int` (not via `snapweb_int`) from the **Cost** tab or the **Cost Settings** page. For more information about how to connect to cost, see [Set up ROI360 cost API to measure cost data](/docs/set-up-roi360-cost-api-to-measure-cost-data#enabling-cost-api).
2. Include the campaign ID (`af_c_id`) in the landing page URL. Make sure the URL includes the full campaign hierarchy to view cost, clicks, and impressions matched to web attribution at the most granular level.

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Clicks and impressions | Clicks and impressions for web campaigns require an [ROI360 subscription](/docs/roi360-onboarding-guide). |
| Re-engagement | Re-engagement postbacks via the Conversions API are not currently supported. |