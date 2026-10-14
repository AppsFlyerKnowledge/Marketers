---
title: Snapchat—Advanced SRN integration setup
excerpt: >-
  Learn how to set up the integration between AppsFlyer and Snapchat to enable
  attribution measurement. Snapchat is an advanced SRN (Self-Reporting Network).
metadata:
  keywords:
    - configuration
    - snapchat measurement partner
    - snapchat
    - measurement
    - snapchat measurement analytics
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2016-06-13T12:28:59Z'
  edited_at: '2026-10-07T11:44:22Z'
  id: 211011983
  locale: en-us
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/211011983-Snapchat-Advanced-SRN-integration-setup
---
![](https://cdn.appsflyer.com/marketplace/static/logo/snapchat.png?v=1)

## Overview

An Advanced SRN integration means that all [dual-consented](/docs/appsflyer-knowledge-base-glossary?query=glossar#dual-consent) traffic is attributed and reported as regular SRN traffic. For non-consented traffic, AppsFlyer is able to attribute and measure attribution based on clicks and impressions coming from Snapchat using [other attribution methods](/docs/self-reporting-networks-srns#how-does-attribution-work-with-advanced-srns), in accordance with privacy restrictions.

## Set up Snapchat integration

**Prerequisite:** An account with Snapchat. If you don't have an account, contact Snapchat to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   ( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for Snapchat and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.  
   **Note:** The toggle **must stay on (active) as long as you work with Snapchat**. Learn more about [partner activation and deactivation](/docs/partner-activation-deactivation).
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations](/docs/set-up-an-integrated-partner).

<Accordion title="Integration tab">

The integration supports click and impression attribution, cost, and audiences.

#### Activate partner

On the **first visit** here, you must turn on **Activate Partner** to enable setup.  
For more details about partner activation, see [Partner activation and deactivation](/docs/partner-activation-deactivation).

**Enable attribution**

Enable **Activate Partner** to allow attribution to Snapchat.

![mceclip0.png](https://files.readme.io/cf4e73fec951e4e9d2c1919ca20adff88fc0d49d7fea9b033ab9c39194ce2702-360003259638.png)

#### General settings

**Snap App ID**

1. In your Snap Business Manager, go to Apps, and copy the Snap App ID (read Snapchat's guide on [how to generate a Snap App ID](https://businesshelp.snapchat.com/en-US/a/snap-app-id)).
2. Paste the ID in the Snap App ID field in AppsFlyer.

![snapchat-app-id.png](https://files.readme.io/2e5f53240893e2a80ba36065f67f4504f69e1167d96ef35bd7a4ab874d5a7bb9-360008280878.png)

**In case the app is promoted by an agency**:

* Snap App ID can be added by the advertiser only.
* If the agency is under the same organization as you on Snapchat ad platform, use only one Snap App ID.
* If the agency is under a different organization on Snapchat ad platform, request from them to provide their Snap App ID for this app, and enter it in this field. Multiple IDs can be entered. Press Enter after each ID.

#### Advanced Privacy

The **Advanced Privacy** (AP) toggle controls which events AppsFlyer sends to Snapchat. This setting is also referred to as **Advanced Conversions** on the Snapchat side.

* **Advanced Privacy OFF**: AppsFlyer sends all installs, re-engagements, and in-app events to Snapchat for attribution, including events for users who have not made their IDFA (identifier for advertisers) available.  
  **Important:** To use Snapchat's [unified attribution solution](https://businesshelp.snapchat.com/s/article/unified-attribution?language=en_US), you must turn off the Advanced Privacy toggle.
* **Advanced Privacy ON**: AppsFlyer sends only installs, re-engagements, and in-app events for users who have made their IDFA available.

Agencies can't turn on Advanced Privacy, even when granted permission by the advertiser. This setting is limited to the advertiser only.

#### Advanced Matching data sharing

When **Advanced Matching data sharing** is turned on, Advanced Matching fields, such as hashed email, hashed phone number, hashed first name, and hashed last name, are shared with Snapchat if these fields are included in the event information sent to AppsFlyer. For more information, see: [Advanced Matching Data Sharing](/docs/advanced-matching-data-sharing).

#### Install attribution

Set the different attribution windows to attribute new installs (first launches) of users who viewed, clicked, or engaged with your ad. Note that only installs within the lookback window may be attributed to Snapchat.

**Note:** Attribution for reinstalls (any install that isn't the initial setup on the device) isn't supported.

1. Set the **Install click-through lookback window** to either 1-23 hours or 1-30 days. **Note:** Snapchat recommends aligning with them by setting the Install click-through lookback window to 7 days.

Setting the click-through lookback window also determines the lookback windows for engaged views and engaged clicks.

2. [Optional] Turn on **Install view-through attribution** and set the lookback windows:
   * **Install view-through lookback window** between 1-24 hours. **Note:** Snapchat recommends aligning with them by setting the Install view-through lookback window to 1 day.

#### Re-engagement attribution

Set the different attribution windows to attribute re-engagements of your existing users who viewed, clicked, or engaged with your ad. Note that only re-engagements within the lookback window may be attributed to Snapchat.

1. Set the **Re-engagement click-through lookback window** to either 1-23 hours or 1-30 days. **Note:** Snapchat recommends aligning with them by setting the Re-engagement click-through lookback window to 7 days.

Setting the re-engagement click-through lookback window also determines the re-engagement lookback windows for engaged views and engaged clicks.

2. [Optional] Turn on **Re-engagement view-through attribution** and set the lookback windows:
   * **Re-engagement view-through lookback window** between 1-24 hours. **Note:** Snapchat recommends aligning with them by setting the Re-engagement view-through lookback window to 1 day.
3. Set the **Re-engagement window** to either 1-23 hours, 1-90 days, or **Lifetime**.

#### Ignore active users for retargeting

Set a window timeframe to [ignore re-engagements and re-attributions](/docs/set-retargeting-inactivity-window#inactivity-period) of users who launched your app. This means their activity during the window timeframe isn't recorded in AppsFlyer.

Re-engagement and re-attribution conversions of users who were **dormant** in the set timeframe **are recorded**.

1. Turn on **Ignore active users for retargeting**.
2. Set the Inactivity window.

#### In-app event postbacks

Map AppsFlyer events with the partner via postbacks. If postback sending is enabled, this includes rejected in-app events (events blocked by Protect360 or events found to be non-compliant by target validation rules).

[![mceclip0.png](https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png)](https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png)

**To configure in-app event postbacks:**

1. Set the **Partner ID** (if required).
2. Enable **In-app event postback.**
3. Set the **In-app event postback window**, if required (read more about [in-app event postback window configuration](/docs/in-app-event-postback-configuration#in-app-event-postback-window)).
4. If available, select whether to send events automatically or manually. Learn more about [sending all events as they are](/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped).
5. Click **Add event** to add an SDK or server-to-server event to the list.
6. Complete the parameters required.
7. [Optional] Click ![conditional-iae-postbacks-icon.png](https://files.readme.io/6524810d15f08b4b85deab9c2cbfb8fd7880126b3c3180e3ecf4ead5f1f0a9ae-17798909160465.png) to set conditions for sending certain in-app events to the partner.  
   Learn more about [conditional in-app events postbacks](/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks).

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation and recheck.</li><li>Type it in **AppsFlyer event** , then click **Create custom**. Read more about [custom event mapping](/docs/in-app-event-postback-configuration#custom-events).</li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<ul><li>**Text field:** Get the corresponding event ID from the partner.</li><li>**Drop-down box:** Select the most suitable pre-defined AppsFlyer event.</li><li>**As is**: Send the events as they are, without name mapping.</li></ul> |
| **for users from** | Select the sending option for the event:<ul><li>**This partner only**: send postbacks only when this event is attributed to this partner.</li><li>**All media sources including organic**: send postbacks for events attributed to any partner and organic events.</li></ul> |
| **including** | <ul><li>**No data (default)**: send only the event itself without the event value.</li><li>**Values and revenue**: send all the event parameters, **including** the revenue value (if exists in the event).</li><li>**Values without revenue**: send all the parameters **excluding** the revenue value.</li></ul> |

</Accordion>

<Accordion title="Attribution link tab">

Attribution links are not available for Snapchat.

For all SRNs, such as Facebook, Apple Ads, Google Ads, and Snapchat, this tab is not functional, as they do not use external attribution links.

</Accordion>

<Accordion title="Cost tab">

The cost integration provides the following aggregated data:

* Cost data for your campaigns, adsets, ads, and channel levels. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features.  
  **Note:** Cost data requires an [ROI360](/docs/roi360-cost-aggregation-overview?query=xpend) subscription.
* Data on clicks and impressions.

**To enable the cost API**:

* Follow [these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api).

<div id="cost-data-sync-status" />

<Accordion title="Cost data sync status">

[View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="stop-snapchat-cost-sync" />

<Accordion title="Stop Snapchat cost sync">

**To stop getting Snapchat cost and to delete a connected Snapchat account:**

* [In the actions column, hover over an account, click **Delete connection**](/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab).  
  Once deleted, AppsFlyer stops getting the cost. Deleting the connection does not impact historical data.

</Accordion>

* Make sure your campaign setup in Snapchat is for either an iOS or Android app, not both. If the campaign is for both apps, AppsFlyer can't break down the cost per app, and the cost does not display in AppsFlyer.
* To avoid discrepancies in cost data, set the same timezone in both app settings and your Snapchat advertising account.
* Once you set Snap's cost, do not change the name of any active campaign, ad set, or single ad, as it may cause serious discrepancies or missing cost data.

</Accordion>

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<Accordion title="Permissions tab">

Select which [permissions to grant](/docs/set-up-an-integrated-partner#permissions-tab) Snapchat to access your data and perform various actions.

When the integration is deactivated while the Permissions toggle is still turned on, permissions remain granted.

</Accordion>

## Web to app: measuring app activity for non-app campaigns

AppsFlyer's integration with Snapchat enables comprehensive measurement of app activity, such as installs, re-engagements, and in-app events, for non-app campaigns attributed to Snapchat.

For instance, app installs can be measured even when the ad destination is a web landing page, enabling measurement of the Web-to-App (W2A) user journey. To enable this type of measurement, please enable the [Snap App ID Tracking Toggle](https://businesshelp.snapchat.com/s/article/app-id-tracking) in Snapchat Ads Manager.

By following these instructions, you can effectively measure app activity from Snapchat non-app campaigns and gain valuable insights into user behavior.

## Deep linking with Snapchat

Deep linking with Snapchat is based on using a native deep link in Snapchat's platform, while adding AppsFlyer parameters to it.

To perform deep linking with Snapchat:

1. Verify that **deep linking** for [retargeting is enabled for Snapchat](/docs/snapchat-advanced-srn-integration-setup#set-up-deep-links-on-the-snap-platform).
2. Verify that [re-engagement attribution is enabled in AppsFlyer](/docs/app-settings#reengagement-attribution).
3. Take the app's deep link scheme URI and add **at least** the following parameters:
   * **PID** - The media source in this case is always **snapchat\_int**. This enables all data to appear in the AppsFlyer dashboard under the **Snapchat\_int** media source.
   * **C -** the relevant campaign name
   * **is\_retargeting=true -** this field defines the campaign as a retargeting campaign. The engagements of existing users with the retargeting campaign are marked as re-engagements due to the existence of this field in the URI. This makes sure the user's data appears in the retargeting dashboard.

**URI Example**

client://home?pid=snapchat\_int&c=TEST&is\_retargeting=true

### Set up deep links on the Snap platform

1. Go to **Drive traffic to app** opportunity type.
2. Add the Deeplink URI:  
     
   [![](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)

### Deferred deep linking with Snapchat

AppsFlyer provides a number of solutions for deferred deep linking:

* [**UDL (Unified deep linking)**](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl): Snapchat clicks include a [deep\_link\_value](/docs/about-link-structure-and-parameters#deep_link_value) field (when deep link is set for the ad), and are supported under the UDL solution.
* [**GCD (Get Conversions Data) API**](https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking): This is the recommended option to access Snapchat user conversion data in real time, directly at the SDK level. The data returned in the GCD API includes the [`af_dp`](/docs/about-link-structure-and-parameters#af_dp) parameter, which holds the actual deep link destination (user destination within the app).
* **Using conversion data parameters:** You can create custom logic to navigate the user to your content using other parameters, such as the Campaign name, Adset name, or any other field that is returned as part of the attribution data for Snapchat installs.

## Set up Snapchat for agencies

Agencies working on behalf of advertisers can turn on the Snapchat integration and start getting attribution for their campaigns. However, this integration has some limitations when it comes to agencies.

### Agency limitations

* An agency can access the Snapchat integration only after the advertiser they work with has activated it on their side.
* Attribution parameters showing on the agency's integration page are inherited from the advertiser's integration in **view-only** mode. This means the agency can see how the advertiser configured the attribution lookback windows but can't configure them on their own.
* For post-attribution events, if granted permission by the advertiser, an agency can configure in-app event postbacks.
* An agency can't turn on Advanced Privacy, even when granted permission (see **Advanced Privacy** above).

**To set up Snapchat for agencies:**

1. In AppsFlyer, under **Configuration** go to **Partner Marketplace**.
2. Find **Snapchat** and select it.
3. Enter your agency's **Snapchat Account ID**. This identifies agency traffic and distinguishes it from the advertiser's. You can enter up to 50 different Snapchat account IDs. All attribution data coming from the accounts you entered is visible under the agency's dashboard.
4. Click **Save Integration**.

![snapchat-agency-integration.png](https://files.readme.io/261a0246bb7da0899e653a776eb25e17ce3ae8bff1efef33acac0ef0bf99abcf-21074932431505.png)

Snapchat account IDs mustn't be shared between the advertiser and the agency. If they are shared, all of the advertiser's installs are automatically attributed on the agency's dashboard.

## Raw data restrictions

* Starting March 1, 2023, Snapchat Uninstalls aren't included in the raw data reports.
* Starting September 12, 2023, Snapchat is providing advertisers with limited view-through attribution data at the device level. For user-level sources, such as raw data reports, Push API messages, Pull API reports, Export data page, and Data Locker, only the following fields are populated:
  * Media source (snapchat\_int)
  * Channel
  * Attributed touch type (impression)
  * Attributed touch time (reported as date only - "dd/mm/yyyy")
  * Campaign name and ID (Starting Dec 15, 2025)
  * Ad set name and ID (Starting Dec 15, 2025)
* Starting October 6, 2026, `snapchat_int` view-through attribution data is limited (restricted) in raw data only in some cases. The logic of the event restrictions is managed by Snapchat.

## Snapchat data retention

Snapchat requires attribution providers to delete its user-level data 12 months after the install. This means that the events performed by these users 12 months after they install the app are counted as organic.

Past aggregate data remains the same.

<div data-zendesk-anchors="01H8F1RWVPTHBDGF3830DY7G7M=overview setting-up-snapchat-integration=set-up-snapchat-integration 01H7WQ47ECTZHPKMG5Z5ZPAND5=set-up-snapchat-integration 01H7WQ47ECZB5GNCQ0XH68N1DK=activate-partner 01H7WQ47ECQSQPP63H398NTQ6M=general-settings h_01_advanced-privacy=advanced-privacy h_01_advanced-matching-data-sharing=advanced-matching-data-sharing 01H8VVCC8GK8VFPBEPAMVHCAWM=install-attribution reengagement-attribution=re-engagement-attribution 01H8VVCC8HHG5290PYF0BT29QA=re-engagement-attribution h_01HNWSTJZPFQVQ5C8M0JA1J0T5=ignore-active-users-for-retargeting inapp-event-postback-settings=in-app-event-postbacks 01H8VVCC8HHZRFQ2T1X478YZMP=in-app-event-postbacks 01H7WQ47ED1HYEBHFJDHTB6HJH=cost-data-sync-status 01H7WQ47ED3P53B269W93Z341E=stop-snapchat-cost-sync web-to-app-measuring-app-activity-for-nonapp-campaigns=web-to-app-measuring-app-activity-for-non-app-campaigns h_01JJMAS0W9WMEPJCQWD9BXAEZ2=web-to-app-measuring-app-activity-for-non-app-campaigns 01H7WQ47EDC973V7CPE38QAQE7=deep-linking-with-snapchat how-to-set-up-deep-links-on-snap-platform=set-up-deep-links-on-the-snap-platform 01H7WQ47EDJAX2DW7A2JJ4XVJN=set-up-deep-links-on-the-snap-platform 01H7WQ47EDS3MYRN9A9ZPHXG9Z=deferred-deep-linking-with-snapchat setting-up-snapchat-for-agencies=set-up-snapchat-for-agencies 01H7WQ47EDARK9SSP47V5MGX18=set-up-snapchat-for-agencies h_01HHVGS94CB9XC0T63VFDZ18JS=agency-limitations h_01HA3XZPWSKVRX7VTRXT1WQ1EZ=raw-data-restrictions keeping-snapchat-data=snapchat-data-retention 01H7WQ47ED9STKS1CVW5EXYX0Z=snapchat-data-retention" />
