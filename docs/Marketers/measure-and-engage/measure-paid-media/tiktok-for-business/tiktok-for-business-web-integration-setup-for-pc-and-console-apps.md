---
title: "TikTok for Business—Web integration setup for PC and console apps"
excerpt: "Learn how to integrate TikTok Web for PC and console apps with AppsFlyer and set up campaigns in TikTok Web."
---
**At a glance:** Learn how to integrate TikTok Web for PC and console apps with AppsFlyer and set up campaigns in TikTok Web.

> 📘 **Warning**
>
> This integration is only available for PC and console apps, such as Steam, Epic, or Native PC. For mobile apps, see the [TikTok ads integration setup](/docs/tiktok-for-business-advanced-srn-integration-setup) page.

## Overview

This article contains information and steps on how to set up and use TikTok Web for PC and console apps with AppsFlyer.

### Prerequisite

Before activating the TikTok Web integration, make sure you have a business account in TikTok Ads Manager.

## Activating partner in AppsFlyer

**To activate the partner integration:**

1. In AppsFlyer, from the side menu, open **Collaborate** > **Partner Integrations > Marketplace** tab.
2. Search for **TikTok Web** (`tiktokweb_int`).
3. Click **Integrate**. You’re directed to the setup page.
4. In the **Integration** tab, turn on **Activate partner**. The toggle must stay on ([activated](/docs/partner-activation-deactivation)) for as long as you work with the partner.
5. Complete the configuration using the relevant tabs, as described in the next section.

## Setting up TikTok Web in AppsFlyer

In this part of the setup, you can also set up postbacks to TikTok Web via the TikTok events API. The TikTok Web (tiktokweb\_int) integration uses an Events API tool provided by TikTok ads for advertisers to send data from their **PC and console apps** directly to TikTok's servers. Such data may include user actions, such as purchases, registrations, and other types of conversions performed on non-mobile platforms (websites or applications). The data is then used by TikTok ads to optimize ad targeting, measure ad performance, and build custom audiences for retargeting.

The integration with TikTok Web only supports sending postbacks for installs and in-app events.

### Integration tab

The **Integration** tab comprises several sections, as described below.

#### Activate partner

To configure the integration, you must first turn on the **Activate partner**toggle.

#### General settings

* **Pixel ID:** Enter the Pixel ID. You can generate it or retrieve it from your TikTok Ads Manager by following the instructions detailed [HERE](https://business-api.tiktok.com/portal/docs?id=1771100865818625).
* **Access token:** Enter the access token. To generate it or retrieve it, follow [these instructions](https://business-api.tiktok.com/portal/docs?id=1771100865818625)
* **Limit TikTok Ads’ use of users’ personal information (CCPA):** Turn on this toggle to enable compliance with [data protection laws](/docs/send-opendsr-api-requests).

  CALLSTART::Note::

  #### Note

  Complying with CCPA privacy regulations limits the data coming from TikTok Ads users based in California or other sensitive states in the US.

  CALLEND::

#### Enable view-through attribution

AppsFlyer supports view-through attribution for TikTok Web campaigns using probabilistic modeling (PMOD) and a [Smart Script](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21) or [Smart Banner](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21)-enabled landing page. This allows AppsFlyer to attribute app installs that result from users viewing an ad and then later installing the app, even across platforms, without requiring a direct click.

When a user clicks a TikTok Web ad and lands on a [Smart Script](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21) or [Smart Banner](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21)-enabled landing page, AppsFlyer can attribute the downstream app install. If available, the `ttclid` will be included in the postback to TikTok to enhance attribution fidelity.

To enable view-through attribution:

1. In AppsFlyer, from the sidebar, open **Collaborate** > **Partner Integrations** > **Active Integrations** > **TikTok web ads**.
2. In the **Integration** tab, scroll to the **Install attribution** section.
3. Turn on **Install view-through attribution**.
4. **[optional]**Turn on **Cross-platform equal attribution priority** and set its lookback window. For more information, see [Enable equal priority for cross-platform impressions](/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions)**.**
5. Open the **Attribution link** tab.
6. Scroll to the **View-through attribution** section and set the **view-through lookback window** (up to 24 hours).
7. Click **Save integration** to apply your settings.

#### Default postbacks

Postbacks for installs are automatically sent only to TikTok Web.

#### In-app event postbacks

Configure mapping of in-app event postbacks sent to TikTok Web. These events can be viewed in the TikTok Ads Manager

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

   

| **Parameter name** | **Description** |
| --- | --- |
| AppsFlyer event | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br /><br />* Click Add item, enter the event name, and click. |
| mapped to partner event | The unique name or ID of each event, as defined on the partner's side.<br /><br />* Select from the dropdown box the most suitable pre-defined partner event |
| for users from | This partner only: In-app event postbacks are sent only for events attributed to this partner—meaning, the user who performed it came from this partner. |
| including | Values and revenue: All event parameters, including the revenue value (if exists in the event), are sent in the postback. |

3. [Optional] Click the **Add condition** icon to [set conditions](/docs/in-app-event-postback-configuration#conditional-inapp-event-postbacks) for an event.
4. Set the **In-app event postback window**, if required (read more about[in-app event postback window configuration](/docs/in-app-event-postback-configuration#inapp-event-postback-window)).
5. Click **Save integration**.
6. [Optional] After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
   1. From the top-left corner, under the partner name, click the app name to open the list of apps.
   2. Select a different app from the drop-down list.
   3. Repeat the integration steps for the selected app.

### Attribution link tab

Generating an attribution link in the AppsFlyer UI isn't currently available. However, you can either use a cross-platform landing page with SmartScript or create a direct attribution link for your app (see table below).

| Option | Actions | Who's involved |
| --- | --- | --- |
| Cross-platform landing page | **Recommended**: For when your campaign promotes an app that's also available on multiple platforms, like Epic and Steam.  <br />[Learn about cross-platform landing pages](/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page)  <br />[Learn how to set up a cross-platform landing page](/docs/cross-platform-landing-pages-with-smart-script)<br /><br />* Make sure all relevant URL parameters (that are later captured by the Smart Script) are appended to the ad URL<br />* Make sure the script takes TTCLID from the incoming URL and adds it to the generated link. Meaning, map the outgoing TTCLID URL param ttclid to the incoming URL param ttclid. **Note**! To display in AppsFlyer raw data reports, the incoming ttclid param must also mapped to one of the outgoing params  `af_sub[1-5]`.<br />* Optional: Use TikTok’s dynamic URL macros instead of hard-coding the values manually. [Learn more](https://ads.tiktok.com/help/article/track-offsite-web-events-with-utm-parameters) | Marketer (may require developer assistance) |
| Direct attribution link | If you don't use a cross-platform landing page, because you only have 1 app on 1 platform, you can create direct attribution links to place behind ads.   <br />[Learn how to create direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links)<br /><br />* Make sure the mandatory parameters are included in your link:<br />  * `af_media_source`<br />  * `af_campaign_id`<br />  * `af_r`<br />* Use the following recommended macros for the `af_os_version` parameter:<br />  * Click: `__OS_VERSION__`<br />  * Impression: `__TPL_OS_VERSION__`<br /><br />Template to use for TikTok Web ad link:<br /><br />```<br />https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source=tiktokweb_int&af_campaign_id=__CAMPAIGN_ID__&af_campaign=__CAMPAIGN_NAME__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_r={encoded landing page and URL params}&af_os_version=__TPL_OS_VERSION__<br />```<br /><br />Sample link of a TikTok Web ad link leading to Steam:<br /><br />```<br />https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=tiktokweb_int&af_campaign_id=__CAMPAIGN_ID__&af_campaign=__CAMPAIGN_NAME__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello&af_os_version=__OS_VERSION__<br />```<br /><br />**Note**: The template includes some dynamic URL parameters supported by TikTok. If you prefer, you can replace them with real values manually. | Marketer |

> 📘 **Tip**
>
> To simplify campaign analysis, include the campaign type, web or mobile, as a prefix or suffix in the campaign name (e.g., campaign-name\_web)

### Cost tab

Cost isn't available for TikTok Web.

### Ad revenue tab

Ad revenue isn't available for TikTok Web.

### Permissions tab

Currently, permissions aren't granted to TikTok Web.

## Setting up campaigns in TikTok Web for PC and console apps

When you set up your new campaign:

* Select **Website** as the conversion location.
* When you name your TikTok conversion pixel, enter the same pixel ID you entered for `tiktokweb_int` in the *AppsFlyer Partner Marketplace*.
* When you enter the website URL as the destination for your ad, the URL should be for one of the following:
  * Web landing page (recommended when you have an app on multiple platforms)
  * Store URL (recommended when your app is in a single app store, on a single platform)

## View web-to-app attribution data

Although web-based conversion events are sent to TikTok under the original `tiktokweb_int` PID, they are reported in the AppsFlyer dashboard and raw data reports under the `tiktokglobal_int` PID. This applies to both primary conversion events and conversion assist events.

This unified reporting view enables you to analyze both web and app campaign performance in one place, including comprehensive web and mobile cost reporting.

### View in the dashboard

All TikTok web-to-app attributions appear under `tiktokglobal_int` in the Overview and Activity dashboards. This provides a single, consolidated view of campaign results across platforms. Use standard filters and breakdowns to compare app and web traffic within your TikTok Ads data.

### View in raw data and API reports

Raw data exports and API responses include the `tiktokglobal_int` PID in the `media_source` field for TikTok web activity. To verify the web campaign setup details, refer to the `original_url` field, which shows the `tiktokweb_int` PID used during the web campaign creation.

## Traits and limitations

| Trait | Description |
| --- | --- |
| Clicks and impressions (Temporary limitation) | Clicks and impressions for campaigns targeting PC & Console apps are temporarily not available from TikTok SRN. |