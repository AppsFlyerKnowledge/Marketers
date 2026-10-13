---
title: "TikTok for Business—Advanced SRN integration setup"
excerpt: "Learn how to set up the advanced Self-Reporting Network (SRN) integration with TikTok for Business to measure click and view-based mobile attribution."
x-zendesk:
  id: 6722785184913
  url: https://support.appsflyer.com/hc/en-us/articles/6722785184913-TikTok-for-Business-Advanced-SRN-integration-setup
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: TikTok for Business
  section_id: 12192554266385
  position: 0
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution]
  labels: [Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2022-06-09T16:49:57Z'
  edited_at: '2026-09-09T10:24:24Z'
---
TikTok for Business (tiktokglobal_int) is an advanced Self-Reporting Network (SRN) providing app owners the ability to measure click and view-based mobile attribution with AppsFlyer. This includes app installs coming from app and non-mobile TikTok campaigns.

On January 30, 2023, the new TikTok for Business (Advanced SRN) integration `tiktokglobal_int` was added. The [Legacy] TikTok for Business integration `bytedanceglobal_int` was gradually phased out and officially deprecated on March 20, 2024. TikTok handles the transition, and they will notify you when you can delete the old integration. To avoid any data loss, make sure to keep both integrations live during the transition phase. Learn more in the [bulletin](/docs/bulletin-tiktok-for-business-advanced-srn).

AppsFlyer supports measuring app activity for [non-app campaigns](/docs/tiktok-for-business-advanced-srn-integration-setup#measure-app-activity-for-nonapp-campaigns).

![TTFB_logo__4C_stacked_black_1.png](https://files.readme.io/f876dca1810a33266ad93de7822354d3a9aeb41a1e064a1f85f7120f713e699d-23689976309905.png)

## Overview

An Advanced SRN integration means that all traffic that includes an advertising ID is attributed and reported as regular SRN traffic. When an advertising ID is unavailable, AppsFlyer measures attribution based on TikTok clicks and impressions, in accordance with privacy restrictions.

## Set up TikTok for Business

**Prerequisite:** Before setting up the integration, [contact the partner](/docs/partner-integrations#contact-details) and open an account with them.

**To activate or edit the integration:**

1. **To activate:** In AppsFlyer, from the side menu, select **Collaborate** > **Partner Marketplace**.

**To edit:** In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations**.
2. Search for **TikTok for Business** and select it.
3. Click **Set up integration**. You are directed to the integration setup page.
4. In the **Integration** tab, select the app for the integration and turn **Activate partner** on.

> 📘 Note
>
> The turn on/turn off must be on [(activated)](/docs/partner-activation-deactivation) for as long as you work with the partner.

5. Complete the configuration using the relevant tabs, as described below.

The configuration window includes the following tabs: Integration, Attribution link, Cost, Ad revenue, and Permissions. The **Attribution link** tab is not available for TikTok for Business; the remaining tabs are optional.

Some settings differ for iOS and Android devices.

When setting up a campaign, the campaign name must not start with or end with a space, as it may cause discrepancies in dashboards and reports. Learn more about [how to set up a campaign on TikTok](https://ads.tiktok.com/help/article?aid=9535).

Ads coming from the [TikTok Search Ads Toggle](https://www.tiktok.com/business/en/blog/introducing-tiktok-search-ads-toggle) are included within all TikTok attribution. AppsFlyer does not receive data on specific search terms or keywords.

### Integration tab

The **Integration** tab includes several sections, as described below.

#### Activate partner

To configure the integration, you will first need to turn on the **Activate partner** toggle. For more information about [activating and deactivating a partner](/docs/partner-activation-deactivation#activating-a-partner), see integrations.

#### Advanced Data Sharing

For iOS apps only: Use **Advanced Data Sharing** (ADS) to control how AppsFlyer shares install, reinstall, and postback data with TikTok. Your control over data shared with the partner via postbacks and [reports](/docs/about-raw-data-identifier-restrictions) depends on the Advanced Data Sharing (for iOS 14.5 and later) toggle state:

| Advanced Data Sharing: On | Advanced Data Sharing: Off |
| --- | --- |
| AppsFlyer shares all installs and reinstalls with TikTok. | AppsFlyer shares installs and reinstalls only for users who have opted in. |
| Postbacks are sent according to your configuration:<br />- **All media sources, including organic**<br />- **This partner only** | Postbacks are sent according to the following templates:<br />- **Opted-in users:** Postbacks follow the regular template.<br />- **Opted-out users:** Postbacks follow the [Advanced Privacy template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks). |

When activating the integration (`tiktokglobal_int`), the **Advanced Data Sharing** toggle is turned off by default.

#### Advanced Matching data sharing

When **Advanced Matching data sharing** is turned on, Advanced Matching fields, such as hashed email, hashed phone number, hashed first name, and hashed last name, are shared with TikTok if these fields are included in the event information sent to AppsFlyer. For more information, see [Advanced Matching Data Sharing](/docs/advanced-matching-data-sharing).

#### General settings

**TikTok App ID**

A unique code generated in TikTok Ads Manager and used by TikTok to confirm advertiser ownership of their apps. Although not mandatory, it is recommended to enter app IDs for each of your apps. This helps you better control your data at TikTok for Business and unlock additional products.

**To add your app IDs:**

1. [Optional] Enter your [TikTok App ID](https://ads.tiktok.com/help/article?aid=10001060), available at your TikTok Ads dashboard.
2. [Optional] To add more app IDs:
   1. After entering the first app ID, press Enter.
   2. Enter your next TikTok App ID.

Configuring a TikTok App ID does not impact your data in AppsFlyer.

When migrating to the new integration (`tiktokglobal_int`), any values from the legacy integration (`bytedanceglobal_int`) are auto-populated in this field.

[Learn more about TikTok App ID requirements for iOS 14](https://ads.tiktok.com/help/article?aid=10001070).

#### Default postbacks

Configure how to send postbacks for app **Installs**. For **Rejected installs** and **Re-engagements**, postbacks are sent to TikTok for Business only.

- **This partner only** [Default]: Send postbacks only when the event is attributed to this partner, meaning the user who performed it came from this partner.
- **All media sources including organic**: Send postbacks for events attributed to any partner and for organic events, meaning the user who performed it came from any media source. TikTok for Business recommends changing the selection to **All media sources including organic** for better optimization.

For iOS apps only: Your control over data shared with the partner via postbacks and [reports](/docs/about-raw-data-identifier-restrictions) depends on the **Advanced Data Sharing toggle (iOS 14.5+ and later)**.

When migrating from the legacy integration (`bytedanceglobal_int`) and activating the new integration (`tiktokglobal_int`), the default selected state for postback installs is " **This partner only**," regardless of its state before the migration.

#### Install attribution

Set the different attribution windows to attribute new installs (first launches) of users who viewed, clicked, or engaged with your ad. Note that only installs within the lookback window may be attributed to TikTok for Business.

1. Set the **Install click-through lookback window** to either 1-23 hours or 1-30 days. **Note:** TikTok for Business recommends aligning with them by setting the Install click-through lookback window to 7 days.

Setting the click-through lookback window also determines the lookback windows for engaged views and engaged clicks.

2. [Optional] Turn on **Install view-through attribution** and set the lookback windows:
   - **Install view-through lookback window** between 1-24 hours. **Note:** TikTok for Business recommends aligning with them by setting the Install view-through lookback window to 1 day.

TikTok for Business is implementing advanced data privacy measures to protect users of its services. Starting October 23, 2021, TikTok for Business is providing advertisers with limited view-through attribution data at the device level. For user-level sources, such as raw data reports, Push API messages, Pull API reports, Export data page, and Data Locker, only the following fields are populated:

- Media source (bytedanceglobal\_int)
- Channel
- Attributed touch type (impression)
- Attributed touch time (reported as date only, "dd/mm/yyyy")
- The campaign is reported as "restricted." This data is not available in GCD. Aggregate data reports continue to display view-through conversions.

When migrating from the legacy integration (`bytedanceglobal_int`) and activating the new integration (`tiktokglobal_int`), the lookback window settings (click-through and view-through) are set to the **default values**, regardless of their state before the migration. You can update these settings.

#### Reinstall attribution

Reinstall attribution lets you measure users who reinstall your app during their re-attribution window and attribute them to eligible TikTok clicks and impressions.

When turned on, reinstalls are counted as new conversions in TikTok campaigns and are reported consistently with your existing install attribution settings. For more information about reinstalls, see [Measure reinstalls](/docs/measure-reinstalls).

- The **Reinstall attribution** toggle is turned on by default for new integrations.

Separate lookback windows for reinstalls are not needed. Reinstall attribution uses the same click-through and view-through status and lookback windows as your install attribution settings.

When enabled, eligible reinstall postbacks are sent to TikTok.

#### Re-engagement attribution

Set the different attribution windows to attribute re-engagements of your existing users who viewed, clicked, or engaged with your ad. Note that only re-engagements within the lookback window may be attributed to TikTok for Business.

1. Set the **Re-engagement click-through lookback window** to either 1-23 hours or 1-30 days. **Note:** TikTok for Business recommends aligning with them by setting the Re-engagement click-through lookback window to 7 days.

Setting the re-engagement click-through lookback window also determines the re-engagement lookback windows for engaged views and engaged clicks.

2. [Optional] Turn on **Re-engagement view-through attribution** and set the lookback windows:
   - **Re-engagement view-through lookback window** between 1-24 hours. **Note:** TikTok for Business recommends aligning with them by setting the Re-engagement view-through lookback window to 1 day.
3. Set the **Re-engagement window** to either 1-23 hours, 1-90 days, or **Lifetime**.

When migrating from the legacy integration (`bytedanceglobal_int`) and activating the new integration (`tiktokglobal_int`), the **Re-engagement** toggle is turned off by default, regardless of its state before the migration. If your legacy integration has [retargeting campaigns](/docs/retargeting-attribution-guide), make sure to turn them on in the new integration to ensure continuity.

Learn more about re-engagement [rules and windows](/docs/retargeting-attribution-guide#reengagement-rules-and-windows).

#### Ignore active users for retargeting

Set a window timeframe to [ignore re-engagements and re-attributions](/docs/set-retargeting-inactivity-window#inactivity-period) of users who launched your app. This means their activity during the window timeframe is not recorded in AppsFlyer.

Re-engagement and re-attribution conversions of users who were **dormant** in the set timeframe **are recorded**.

1. Turn on **Ignore active users for retargeting**.
2. Set the Inactivity window.

#### In-app event postbacks

Configure mapping of in-app events with TikTok for Business events, sent via postbacks:

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The event name, as received by AppsFlyer, is either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<br />   - Make sure to activate the event on a device with a non-organic installation, and recheck.<br />   - Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping](/docs/in-app-event-postback-configuration#custom-events). |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<br />   - **Drop-down box:** Select the most suitable predefined TikTok event.<br />   - **As is**: If you choose **Custom** from the dropdown, AppsFlyer sends the events as they are, without mapping them to any of TikTok's predefined events. Please note that TikTok does not use custom events for optimization, only for reporting purposes, so this setup is not recommended by TikTok. To learn more about TikTok standard and custom events, see the [TikTok documentation](https://ads.tiktok.com/help/article/standard-events-parameters). |
| **for users from** | Select the sending option for the event:<br />   - **This partner only** (default): Send postbacks only when this event is attributed to this partner.<br />   - **All media sources including organic**: Send postbacks for events attributed to any partner, as well as organic events. TikTok for Business recommends selecting **All media sources including organic** for better optimization. |
| **including** | - **No values & no revenue** (default): Send only the event itself without any event values.<br />   - **Values & no revenue**: Send all the parameters excluding the revenue value.<br />   - **Values & revenue**: Send all the event parameters, including the revenue value (if it exists in the event). TikTok for Business recommends selecting **Values & revenue** for better optimization. |

3. [Optional] Click the **Add condition** ![conditional-iae-postbacks-icon.png](https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png) icon to [set conditions](/docs/in-app-event-postback-configuration#conditional-inapp-event-postbacks) for an event.
4. Click **Save integration**.
5. [Optional] After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
   1. In the top-left corner, under the partner name, click the app name to open the app list.
   2. Select a different app from the drop-down list.
   3. Repeat the integration steps for the selected app.

For iOS apps only: Your control over data shared with the partner via postbacks and [reports](/docs/about-raw-data-identifier-restrictions) depends on the **Advanced Data Sharing (iOS 14.5+ and later)** [toggle](/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-data-sharing).

When migrating to the new integration (`tiktokglobal_int`), all postback events configured at the legacy integration (`bytedanceglobal_int`) are auto-populated with the same configuration.

- If an event is mapped to the [Legacy] TikTok for Business **Pay** event, it is automatically renamed to Purchase when migrating to the new integration.

### Attribution link tab

Attribution links are not relevant for [SRNs](/docs/self-reporting-networks-srns) or Advanced SRNs.

SRNs perform attribution on their own platform. Attribution for Advanced SRNs is performed by combining their engagement data with AppsFlyer data, using the attribution settings you defined in the [Integration tab](/docs/tiktok-for-business-advanced-srn-integration-setup#integration-tab).

### Cost tab (for cost, clicks, and impressions)

This integration provides aggregated data on cost, clicks, and impressions for your campaigns, adsets, ads, and geos/countries. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features.

> 📘 Note
>
> Data on clicks and impressions is included in the integration. However, **cost data requires an** [**ROI360**](/docs/roi360-cost-aggregation-overview) **subscription**.

**To enable the API connection for cost, clicks, and impressions with TikTok for Business:**

1. Go to the **Cost** tab and turn on **Get cost data**.
2. Click **Log in to TikTok Ads**.
3. From the TikTok window that opens, log in to your TikTok account and confirm the needed permissions.
4. After a success message appears in the TikTok window, close it. Your TikTok account details now appear under **Connected accounts**.
5. From **Advertiser account IDs** > **Advertiser ID**: Enter the TikTok advertiser account ID, and click **Add**.

To get your **Advertiser ID** from your TikTok business account: Go to **Users** > **Members**, and under the Advertiser account, you can see the ID.

Make sure the **Advertiser ID** you add is associated with the **TikTok account** you connected in step 2, as this is the account from which data will be collected.

Connect at least one **Advertiser ID**. You can add up to 30.

6. Click **Save Cost**.

#### For ROI360 subscribers

- Advertisers and agencies that have the cost API enabled in both the legacy `bytedanceglobal_int` and the current `tiktokglobal_int` integrations may see duplicated cost data. To avoid this, go to the `bytedanceglobal_int` integration > **Cost** tab, and turn off the toggle. However, when enabling the new cost integration, cost data from 5 days preceding the transition day is automatically collected. This means the new integration is expected to show duplicated cost data for those 5 days. For example, if the old cost integration was disabled on January 15 and the new cost integration was enabled on the same day, duplicate cost data appears in the new cost integration between January 10th and 14th, even though the new cost integration was only enabled on January 15.
- See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features.
- [View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data, in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.
- Learn more about [enabling the Cost API](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api).

### Ad revenue tab

To send your ad revenue data to TikTok for user acquisition (UA) optimization, you can configure [ad revenue postbacks or UA signals](/docs/share-ad-revenue-data-with-partners).

To get ad revenue data from Pangle, use the Pangle (ad revenue) partner integration.

### Permissions tab

In this section, you can select permissions to grant TikTok for Business access to your data and perform various actions.

Note that even after the integration is [deactivated](/docs/partner-activation-deactivation), the **TikTok for Business permissions** toggle still grants permissions.

Learn more about [granting permissions](/docs/set-up-an-integrated-partner#permissions-tab).

## Deep linking with TikTok for Business

[TikTok supports deep linking and deferred deep linking](https://ads.tiktok.com/help/article/understanding-deeplinks-and-deferred-deeplinks?lang=en) for multiple campaign objectives on the ad level when creating a campaign, ad group, and ad. Creating deep links for the user to navigate to specific content enables you to serve customized content based on the user's engagement with your TikTok ad.

### Access TikTok conversion data via AppsFlyer's GCD API for deep linking

AppsFlyer provides a number of solutions for deferred deep linking:

- [**UDL (Unified deep linking)**](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl): TikTok clicks include a [deep\_link\_value](/docs/about-link-structure-and-parameters#deep_link_value) field (when a deep link is set for the ad), and are supported under the UDL solution.
- [**GCD (Get Conversions Data) API**](https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking): This is the recommended option to access TikTok user conversion data in real time, directly at the SDK level. The data returned in the GCD API includes the [`af_dp`](/docs/about-link-structure-and-parameters#af_dp) parameter, which holds the actual deep link destination (user destination within the app).
- **Using conversion data parameters,** you can create custom logic to guide the user to your content using other parameters, such as the Campaign name, Adset name, or any other field returned in the attribution data for TikTok installs.

## Web to App: Measure app activity for non-app campaigns

AppsFlyer's integration with TikTok enables comprehensive measurement of app activity, such as installs, re-engagements, and in-app events, for non-app campaigns attributed to TikTok for Business.

For instance, app installs can be measured even when the ad destination is a web landing page, enabling measurement of the Web-to-App (W2A) user journey.

By following the steps below in TikTok Ads Manager, you can effectively measure app activity from TikTok non-app campaigns and gain valuable insights into user behavior. You can also see [the TikTok documentation](https://ads.tiktok.com/help/article/how-to-measure-app-activity-for-non-app-promotion-campaigns?lang=en).

1. Go to the TikTok ad campaign page and select **Edit ad**.
2. Under **Tracking** > **App events**, select your app.
3. Click **Save**.
4. Repeat these steps for all relevant ads in your campaign.

## Set up TikTok for Business for agencies

Agencies working on behalf of advertisers can turn on the TikTok for Business integration and start getting attribution for their campaigns. However, this integration has some limitations when it comes to agencies.

### Agency limitations

The following limitations apply when an agency works with this integration:

| Trait | Description |
| --- | --- |
| Access depends on the advertiser | An agency can access the TikTok for Business integration only after the advertiser they work with has activated it on their side. |
| View-only attribution parameters | Starting January 1, 2024, attribution parameters showing on the agency's integration page are inherited from the advertiser's integration in **view-only** mode. This means the agency can see how the advertiser configured the attribution lookback windows, but cannot configure them on their own. |
| No control over Advanced Data Sharing | An agency cannot turn on the Advanced Data Sharing setting, even when granted permission. This setting is limited to the advertiser only. |
| In-app event postback configuration | With the advertiser's [permission](/docs/set-up-an-integrated-partner#configure-inapp-event-postbacks::8743ba60), an agency can configure in-app event postbacks. |
| Mapping alignment recommended | When mapping in-app event postbacks, we recommend making sure the mapping configuration is identical for both the agency and the marketer. |

**To set up TikTok for Business for agencies:**

1. In AppsFlyer, under **Configuration**, go to **Partner Marketplace**.
2. Find **TikTok for Business** and select it.
3. Enter the **TikTok App ID**.
4. Enter your agency **TikTok Account ID**. This identifies agency traffic and distinguishes it from the advertiser's.
5. Click **Save Integration**.
![tiktok.png](https://files.readme.io/b13ee9cd005b97c37019154a0caa10e03b846e7405777d9fc0e3db11bfb233b4-33379202036369.png)

> 🚧 Warning
>
> TikTok for Business account IDs must not be shared between the advertiser and the agency. If they are shared, all of the advertiser's installs are automatically attributed on the agency's dashboard.

## Send complex in-app events to TikTok

To send complex in-app events, events with multiple items, to TikTok, we recommend using the new `af_order_info` event object. For more information, see [Item-level order data for ad networks (af\_order\_info)](/docs/item-level-order-data-for-ad-networks-af-order-info).

TikTok supports up to 7 fields within this object, allowing advertisers to share multiple data points about each item included in the event.

## Smart Plus campaigns reporting

Smart Plus is a new TikTok campaign type that allows advertisers to test multiple creatives within the same ad unit, helping optimize performance through automated creative testing.

[Learn more about Smart Plus campaigns](https://ads.tiktok.com/help/article/about-smart-plus-campaign?lang=en).

### How Smart Plus campaigns are structured

Unlike standard TikTok campaigns, which include three levels (campaign, ad group, and ad), Smart Plus campaigns add a fourth layer, creative.

1. Campaign
2. Ad set
3. Ad
4. Creative

### How Smart Plus data is reported in AppsFlyer

AppsFlyer maps TikTok Smart Plus campaign data as follows:

| TikTok level | AppsFlyer equivalent | Notes |
| --- | --- | --- |
| Campaign | Campaign | Mapped directly |
| Ad group | Ad set | Mapped directly |
| Ad | Not applicable | Not mapped in AppsFlyer |
| Creative | Ad | Mapped to the AppsFlyer ad level |

AppsFlyer's mapping structure for Smart Plus campaigns differs from TikTok Ads Manager. In TikTok Ads Manager, reports are shown only up to the ad level without a dedicated creative breakdown. AppsFlyer, however, maps TikTok's creative data directly to the ad level. As a result, you might see discrepancies when comparing performance data between AppsFlyer and TikTok.

## Troubleshooting

### My TikTok app status is "Pending Verification."

If Aggregated Advanced Privacy (AAP) is enabled at either the app level or the TikTok partner level in AppsFlyer, install and in-app event postbacks are only sent for installs attributed to an ad network. As a result, TikTok may not receive required postbacks from organic sources, leading to a "Pending Verification" status.

#### Recommended resolution

Use the steps below to get your app verified:

1. You can temporarily disable the AAP setting in AppsFlyer to allow TikTok to receive organic postbacks for verification purposes only. (Disabling AAP can make user-level data available to advertisers and partners. For more information, see [AAP disabled](/docs/apply-aggregated-advanced-privacy-framework#aap-disabled).)
   1. Go to the [app-level settings](/docs/apply-aggregated-advanced-privacy-framework#aap-central-switch) and disable AAP.
   2. Go to [TikTok's partner integration configuration](/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-data-sharing) and disable AAP there as well.
2. In the [Postbacks section](/docs/tiktok-for-business-advanced-srn-integration-setup#default-postbacks), set the postback method to **All Media Sources, including Organic**.
3. Wait for TikTok to receive at least one install or in-app event postback. Once received, your app should automatically update to "verified" on the TikTok dashboard.
4. After verification, you may [re-enable the AAP setting](/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-data-sharing), based on your privacy preferences.