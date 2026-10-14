---
title: "TikTok for Business—Web integration setup for PC and console apps"
excerpt: "Learn how to integrate TikTok Web for PC and console apps with AppsFlyer and set up campaigns in TikTok Web."
x-zendesk:
  id: 40500157955601
  url: https://support.appsflyer.com/hc/en-us/articles/40500157955601-TikTok-for-Business-Web-integration-setup-for-PC-and-console-apps
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: TikTok for Business
  section_id: 12192554266385
  position: 3
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roi-tamir, Marketers, PC & Console Attribution]
  labels: []
  promoted: false
  comments_disabled: false
  created_at: '2025-10-31T13:58:16Z'
  edited_at: '2026-09-15T09:26:02Z'
---
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

<div id="integration-tab" />

<Accordion title="Integration tab">

The **Integration** tab comprises several sections, as described below.

#### Activate partner

To configure the integration, you must first turn on the **Activate partner**toggle.

#### General settings

* **Pixel ID:** Enter the Pixel ID. You can generate it or retrieve it from your TikTok Ads Manager by following the instructions detailed [HERE](https://business-api.tiktok.com/portal/docs?id=1771100865818625).
* **Access token:** Enter the access token. To generate it or retrieve it, follow [these instructions](https://business-api.tiktok.com/portal/docs?id=1771100865818625)
* **Limit TikTok Ads’ use of users’ personal information (CCPA):** Turn on this toggle to enable compliance with [data protection laws](/docs/send-opendsr-api-requests).

  > 📘 **Note**
  >
  > Complying with CCPA privacy regulations limits the data coming from TikTok Ads users based in California or other sensitive states in the US.


#### Enable view-through attribution

AppsFlyer supports view-through attribution for TikTok Web campaigns using probabilistic modeling (PMOD) and a [Smart Script](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21) or [Smart Banner](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21)-enabled landing page. This allows AppsFlyer to attribute app installs that result from users viewing an ad and then later installing the app, even across platforms, without requiring a direct click.

When a user clicks a TikTok Web ad and lands on a [Smart Script](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21) or [Smart Banner](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21)-enabled landing page, AppsFlyer can attribute the downstream app install. If available, the `ttclid` will be included in the postback to TikTok to enhance attribution fidelity.

To enable view-through attribution:

1. In AppsFlyer, from the sidebar, open **Collaborate** > **Partner Integrations** > **Active Integrations** > **TikTok web ads**.
2. In the **Integration** tab, scroll to the **Install attribution** section.
3. Turn on **Install view-through attribution**.
4. **[optional]** Turn on **Cross-platform equal attribution priority** and set its lookback window. For more information, see [Enable equal priority for cross-platform impressions](/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions).
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
| AppsFlyer event | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<ul><li>Click Add item, enter the event name, and click.</li></ul> |
| mapped to partner event | The unique name or ID of each event, as defined on the partner's side.<ul><li>Select from the dropdown box the most suitable pre-defined partner event</li></ul> |
| for users from | This partner only: In-app event postbacks are sent only for events attributed to this partner—meaning, the user who performed it came from this partner. |
| including | Values and revenue: All event parameters, including the revenue value (if exists in the event), are sent in the postback. |

3. [Optional] Click the **Add condition** icon to [set conditions](/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks) for an event.
4. Set the **In-app event postback window**, if required (read more about[in-app event postback window configuration](/docs/in-app-event-postback-configuration#in-app-event-postback-window)).
5. Click **Save integration**.
6. [Optional] After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
   1. From the top-left corner, under the partner name, click the app name to open the list of apps.
   2. Select a different app from the drop-down list.
   3. Repeat the integration steps for the selected app.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generating an attribution link in the AppsFlyer UI isn't currently available. However, you can either use a cross-platform landing page with SmartScript or create a direct attribution link for your app (see table below).

| Option | Actions | Who's involved |
| --- | --- | --- |
| Cross-platform landing page | **Recommended**: For when your campaign promotes an app that's also available on multiple platforms, like Epic and Steam.<br />[Learn about cross-platform landing pages](/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page)<br />[Learn how to set up a cross-platform landing page](/docs/cross-platform-landing-pages-with-smart-script)<ul><li>Make sure all relevant URL parameters (that are later captured by the Smart Script) are appended to the ad URL</li><li>Make sure the script takes TTCLID from the incoming URL and adds it to the generated link. Meaning, map the outgoing TTCLID URL param ttclid to the incoming URL param ttclid. **Note**! To display in AppsFlyer raw data reports, the incoming ttclid param must also mapped to one of the outgoing params  `af_sub[1-5]`.</li><li>Optional: Use TikTok’s dynamic URL macros instead of hard-coding the values manually. [Learn more](https://ads.tiktok.com/help/article/track-offsite-web-events-with-utm-parameters)</li></ul> | Marketer (may require developer assistance) |
| Direct attribution link | If you don't use a cross-platform landing page, because you only have 1 app on 1 platform, you can create direct attribution links to place behind ads.<br />[Learn how to create direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links)<ul><li>Make sure the mandatory parameters are included in your link:<ul><li>`af_media_source`</li><li>`af_campaign_id`</li><li>`af_r`</li></ul></li><li>Use the following recommended macros for the `af_os_version` parameter:<ul><li>Click: `__OS_VERSION__`</li><li>Impression: `__TPL_OS_VERSION__`</li></ul></li></ul>Template to use for TikTok Web ad link:<br /><br />```<br />https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source=tiktokweb_int&af_campaign_id=__CAMPAIGN_ID__&af_campaign=__CAMPAIGN_NAME__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_r={encoded landing page and URL params}&af_os_version=__TPL_OS_VERSION__<br />```<br /><br />Sample link of a TikTok Web ad link leading to Steam:<br /><br />```<br />https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=tiktokweb_int&af_campaign_id=__CAMPAIGN_ID__&af_campaign=__CAMPAIGN_NAME__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello&af_os_version=__OS_VERSION__<br />```<br /><br />**Note**: The template includes some dynamic URL parameters supported by TikTok. If you prefer, you can replace them with real values manually. | Marketer |

> 📘 **Tip**
>
> To simplify campaign analysis, include the campaign type, web or mobile, as a prefix or suffix in the campaign name (e.g., campaign-name\_web)

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost isn't available for TikTok Web.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue isn't available for TikTok Web.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Currently, permissions aren't granted to TikTok Web.

</Accordion>

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

<div data-zendesk-anchors="h_01K8X90869H29Q9N873FAT8BM4=warning h_01K8X90869QTX2RG0KHHM8EHAT=overview h_01K8X9086AJ6B9BKNF0EZQASCJ=prerequisite h_01K8X9086ADTE56DR3MK8MXAFR=activating-partner-in-appsflyer h_01K8X9086AMHZR7GADTH8N07DZ=setting-up-tiktok-web-in-appsflyer h_01K8X9086AHN8761VPM4QA7E6S=integration-tab h_01K8XAAM5SH1XXNX0DNGGS5NHT=activate-partner h_01K8XAATC3M5NW722QD93DRN94=general-settings h_01K8X9086A2FFDCRE2JHXQHGET=note enable-viewthrough-attribution=enable-view-through-attribution h_01K8XAB2SK68WTGYZY7EGHR4SZ=enable-view-through-attribution h_01K8XABK08NCFQSRN41ASKQ7SY=default-postbacks inapp-event-postbacks=in-app-event-postbacks h_01K8XAC3NAYY8S012K2W60TKBJ=in-app-event-postbacks h_01K8X9086A001XKD94G50XY708=attribution-link-tab h_01K88N0TDSFDX5J22YWZPF2J1N=tip h_01K8X9086AFH7J75J9K1QRV1DR=cost-tab h_01K8X9086ACM5WBH6GW243A0PZ=ad-revenue-tab h_01K8X9086AEHV42XZZKA0ATBH2=permissions-tab h_01K8X9086AARVTEDRMQW32BABF=setting-up-campaigns-in-tiktok-web-for-pc-and-console-apps TikTok-view=view-web-to-app-attribution-data view-webtoapp-attribution-data-from-november-2-2025=view-web-to-app-attribution-data h_01K88J8JFNEYBZNR18133NMRP9=view-web-to-app-attribution-data h_01K88J8JFNMHCVZ0C34E3D7AST=view-in-the-dashboard h_01K88J8JFN8W2572N92466YFZQ=view-in-raw-data-and-api-reports h_01KB58BEK7MDZGT7G7RQ9VK9MZ=traits-and-limitations" />
