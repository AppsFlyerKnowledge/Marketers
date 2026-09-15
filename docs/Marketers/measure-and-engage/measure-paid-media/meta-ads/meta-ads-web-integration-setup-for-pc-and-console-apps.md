---
title: "Meta Ads—Web integration setup for PC and console apps"
excerpt: "Learn how to integrate Meta Web for PC and console apps with AppsFlyer and set up campaigns in Meta Web."
---
> ❗️ Important!
>
> This integration is only available for PC and console apps, such as Steam, Epic, or Native PC. For mobile apps, see the [Meta ads integration setup](/docs/meta-ads-integration-setup) page.

## Overview

This article contains information and steps on how to set up and use Meta Web for PC and console apps with AppsFlyer. This includes:

- [Activating the partner integration in AppsFlyer](/docs/meta-ads-web-integration-setup-for-pc-and-console-apps#activate-partner).
- [Setting up Meta Web in AppsFlyer](/docs/meta-ads-web-integration-setup-for-pc-and-console-apps#setting-up-metaweb-in-appsflyer).
- [Setting up campaigns in Meta for PC and console apps](/docs/meta-ads-web-integration-setup-for-pc-and-console-apps#setting-up-campaigns-in-meta-web-for-pc-and-console-apps).

### Prerequisite

Before activating the Meta Web integration, make sure you have a [business account in Meta Business Manager](https://www.facebook.com/business/help/1710077379203657?id=180505742745347).

## Activating partner in AppsFlyer

**To activate the partner integration:**

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Partner Marketplace**.
2. Search for **Meta Web** and select it.
3. Click **Set up integration**. You’re directed to the **Active Integrations** setup page.
4. In the **Integration** tab, turn on **Activate partner**.

> 📘 Note
>
> The toggle must stay on ([activated](/docs/partner-activation-deactivation)) for as long as you work with the partner.

5. Complete the configuration using the relevant tabs, as described in the next section.

## Setting up Meta Web in AppsFlyer

In this part of the setup, you can also set up postbacks to Meta Web. The Meta Web (metaweb_int) integration uses a Conversions API tool provided by Meta ads for advertisers to send data from their **PC and console apps** directly to Meta's servers. Such data may include user actions, such as purchases, registrations, and other types of conversions performed on non-mobile platforms (websites or applications). The data is then used by Meta ads to optimize ad targeting, measure ad performance, and build custom audiences for retargeting.

The integration with Meta Web only supports sending postbacks for installs and in-app events.

### Integration tab

The **Integration** tab includes a number of sections, as described below.

#### Activate partner

To configure the integration, you must first turn on the **Activate partner** toggle.

#### General settings

- **Pixel ID:** Enter the Pixel ID. You can retrieve it from your Meta ads Manager:
  1. From the [Ads manager](https://www.facebook.com/ads/manager) side menu, go down to **All tools** > **Events Manager**.

     > 📘 Note
     >
     > Make sure you have the correct business selected from the drop-down on the top right.

  2. From the **Events Manager** side menu, select **Data sources**. You'll see a list of your pixels. If you don’t have a pixel for the selected business, you can create one through the same view.
  3. Copy the pixel ID showing under the pixel name and paste it into the Pixel ID field of the AppsFlyer integration.

     <Image src="https://files.readme.io/77969160b04357d056f2eee435a61314b95225f43e03cb31dd21a80dceef0dae-20748699506193.png" alt="pixel id3.png" />

- **Access token:** Enter the access token. To retrieve it, follow [these instructions](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)
- **Limit Meta ads use of users’ personal information (CCPA):** Turn on this toggle to enable compliance with [data protection laws](/docs/send-opendsr-api-requests).

> 📘 Note
>
> Complying with CCPA privacy regulations limits the data coming from Meta ads users based in California.

#### Enable view-through attribution

AppsFlyer supports view-through attribution for Meta Web campaigns using probabilistic modeling (PMOD) and [Smart Script](/docs/meta-ads-create-web-based-campaigns#set-up-smart-script-crossplatform-landing-page) or [Smart Banner](/docs/meta-ads-create-web-based-campaigns#set-up-smart-banners-landing-page)-enabled landing page. This allows AppsFlyer to attribute app installs that result from users viewing an ad and then later installing the app, even across platforms, without requiring a direct click.

When a user clicks a Meta Web ad and lands on a [Smart Script](/docs/meta-ads-create-web-based-campaigns#set-up-smart-script-crossplatform-landing-page) or [Smart Banner](/docs/meta-ads-create-web-based-campaigns#set-up-smart-banners-landing-page)-enabled landing page, AppsFlyer can attribute the downstream app install. If available, the `fbclid` will be included in the postback to Meta to enhance attribution fidelity.

**To enable view-through attribution:**

1. In AppsFlyer, from the sidebar, open **Active Integrations** > **Meta web ads**.
2. In the **Integration** tab, scroll to the **Install attribution** section.
3. Turn on **Install view-through attribution**.
4. **[optional]** Turn on **Cross-platform equal attribution priority** and set its lookback window. For more information, see [Enable equal priority for cross-platform impressions](/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions).
5. Open the **Attribution link** tab.
6. Scroll to the **View-through attribution** section and set the **view-through lookback window** (up to 24 hours).
7. Click **Save integration** to apply your settings.

#### Default postbacks

Postbacks for installs are automatically sent to Meta Web. In the **For Users From** field, select one of the following:

- **This Partner Only** to ensure that in-app event postbacks are sent exclusively for events performed by users who originated from this partner.
- **All media sources, including organic,** are to ensure that in-app event postbacks are sent for events performed by users who originated from this partner, other partners, or from organic sources.

#### In-app event postbacks

Configure mapping of in-app event postbacks sent to Meta Web. These events can be viewed in the [Meta Events Manager](https://www.facebook.com/business/help/1541268312717919?id=818859032317965):

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br /> - Click **Add item**, enter the event name, and click <Image src="https://files.readme.io/66d595d0ac8a01489ce810bbd3865fca2556342086dc6b20f26fa3d7b7e3afc2-19124971382289.png" alt="check.png" />. |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. <br /> - Select from the dropdown box the most suitable pre-defined partner event or select CUSTOM. |
| **for users from** | - **This Partner Only** to ensure that in-app event postbacks are sent exclusively for events performed by users who originated from this partner.<br /> - **All media sources, including organic,** are to ensure that in-app event postbacks are sent for events performed by users who originated from this partner, other partners, or from organic sources. |
| **including** | **Values and revenue:** All event parameters, including the revenue value (if exists in the event), are sent in the postback. |

3. [Optional] Click the **Add condition** <Image src="https://files.readme.io/16d37e5cdb84468be45960c7927ad721fd5ba0ca67f4bdcd0d71c4bb551db85f-18704290233873.png" alt="conditional-iae-postbacks-icon.png" /> icon to [set conditions](/docs/in-app-event-postback-configuration#conditional-inapp-event-postbacks) for an event.
4. Set the **In-app event postback window**, if required (read more about [in-app event postback window configuration](/docs/in-app-event-postback-configuration#inapp-event-postback-window)).
5. Click **Save integration**.
6. [Optional] After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
   1. From the top-left corner, under the partner name, click the app name to open the list of apps.
   2. Select a different app from the drop-down list.
   3. Repeat the integration steps for the selected app.

### Attribution link tab

Generating an attribution link in the AppsFlyer UI isn't currently available. However, you can either use a cross-platform landing page with SmartScript or create a direct attribution link for your app (see table below).

| Option | Actions | Who's involved |
| --- | --- | --- |
| Cross-platform landing page | **Recommended**: For when your campaign promotes an app that's also available on multiple platforms, like Epic and Steam.<br />[Learn about cross-platform landing pages](/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page)<br />[Learn how to set up a cross-platform landing page](/docs/cross-platform-landing-pages-with-smart-script)<br />- Make sure all relevant URL parameters (that are later captured by the Smart Script) are appended to the ad URL<br />- Make sure the script takes FBCLID from the incoming URL and adds it to the generated link. Meaning, map the outgoing FBCLID URL param `fbclid` to the incoming URL param `fbclid`. **Note**! To display in AppsFlyer raw data reports, the incoming `fbclid` param must also mapped to one of the outgoing params `af_sub[1-5]`.<br />- Optional: Use Meta’s dynamic URL macros instead of hard-coding the values manually. [Learn more](https://www.facebook.com/business/help/2360940870872492) | Marketer (may require developer assistance) |
| Direct attribution link | If you don't use a cross-platform landing page, because you only have 1 app on 1 platform, you can create direct attribution links to place behind ads. <br />[Learn how to create direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links)<br />- Make sure the mandatory parameters are included in your link:<br /> - af_media_source<br /> - af_campaign_id<br /> - af_r<br />Template to use for Meta Web ad link:<br />`https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={encoded landing page and URL params}`<br />Sample link of a Meta Web ad link leading to Steam: `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello`<br />**Note**: The template includes some dynamic URL parameters supported by Meta. If you prefer, you can replace them with real values manually. [Learn more about Meta dynamic URL parameters](https://www.facebook.com/business/help/2360940870872492) | Marketer |

### Cost tab

Cost isn't available for Meta Web.

### Ad revenue tab

Ad revenue isn't available for Meta Web.

### Permissions tab

Currently, permissions aren't granted to Meta Web.

## Setting up campaigns in Meta Web for PC and console apps

**When you set up your new campaign**:

- Select a campaign objective. We recommend selecting one of the following:
  - **Sales**: This lets Meta optimize towards a specific event (your main KPI).
  - **Traffic**: This lets Meta optimize towards ad clicks. This should only be used if you don’t have other KPIs or if the volume of other KPI events is too low.
  - **Custom**: If you want to set a custom event (as your campaign objective). **Note:** To enable the custom event to appear as a campaign objective on Meta's dashboard, first set up the custom event in AppsFlyer.
- Select **Website** as the conversion location.
- When you name your Facebook conversion pixel, enter the same pixel ID you entered for metaweb_int in the AppsFlyer Partner Marketplace.
- When you enter the website URL as the destination for your ad, the URL should be for one of the following:
  - Web landing page (recommended when you have an app on multiple platforms)
  - Store URL (recommended when your app is in a single app store, on a single platform)

## View web-to-app attribution data

Although web-based conversion events are sent to Meta under the original `metaweb_int` PID, they are reported in the AppsFlyer dashboard and raw data reports under the `Facebook Ads` PID. This applies to both primary conversion events and conversion assist events.

This unified reporting view lets you analyze both web and app campaigns performance in one place, including full web and mobile cost reporting.

### View in the dashboard

All Meta web-to-app attributions appear under `Facebook Ads` in the Overview and Activity dashboards. This provides a single, consolidated view of campaign results across platforms. Use standard filters and breakdowns to compare app and web traffic within your Meta Ads data.

### View in raw data and API reports

- **Raw data exports and API responses** include the `Facebook Ads` PID in the `media_source` field for Meta web activity. To verify web campaign setup details, refer to the `original_url` field that shows `metaweb_int` as the PID used during the creation of web campaigns.
- **Postback reports** show `metaweb_int` as the original media source to which the postback was sent.

## Traits and limitations

| Trait | Description |
| --- | --- |
| Clicks and impressions (Temporary limitation) | Clicks and impressions for campaigns targeting PC & Console apps are temporarily not available from Meta SRN (`Facebook Ads`). |