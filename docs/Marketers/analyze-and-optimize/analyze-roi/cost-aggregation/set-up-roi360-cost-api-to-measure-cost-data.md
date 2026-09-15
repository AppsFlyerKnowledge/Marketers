---
title: "Set up ROI360 cost API to measure cost data"
excerpt: "Learn how to set up and manage ROI360 Cost API integrations at both the app and account levels to measure aggregate marketing cost data."
---
Get aggregate marketing cost data (including cost-related LTV (Lifetime Value) performance metrics) using Cost API at the app or media source account level.

## Overview

ROI360 provides cost measurement at both the app and account levels, allowing stakeholders to analyze spend granularity per individual application or across an entire media source account.

Cost integrations are managed in two different locations, depending on the media source:

- **Account-level integrations** are managed in **Cost settings**. These integrations are configured at the ad account level. see the [list of supported ad networks](/docs/set-up-roi360-cost-api-to-measure-cost-data#h_01KQ7V7Q6MAEMXKKJ7TV8GC1YR).
- **App-level integrations** are managed in the **Cost** tab. These integrations are configured separately for each app. If a media source isn't available in **Cost settings**, configure its cost integration in the **Cost** tab at the app level.

Role permissions control access to Cost settings. If you can't open **Cost settings**, ask your administrator to update your role permissions on the **User Management** page. The relevant capability is **Cost Connections**.

## Enable Cost API

There are two ways to enable cost integration: at the app or account levels.

<Tabs>
<Tab title="Enable on the app level (Cost tab)">

To set up a dedicated cost connection with a media source for an individual app, follow these steps:

1. In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations**, and select the partner.
2. Click **Manage integration**.
3. Open the integrated partner **Cost** tab.
4. Turn on **Get Cost Data**. The requirements for connecting to the partner are displayed.
5. Configure and authenticate the cost integration to the partner. The authentication method depends on the media source. [See Cost integration methods](#cost-integration-methods) below.
6. If the partner's cost configuration has **Site ID mapping**, select the required site ID configuration from the dropdown. See [Site ID mapping](#site-id-mapping) below.
7. Click **Save Cost**.
   - Cost data will start showing on your dashboards within 5-6 hours.
   - AppsFlyer collects data from the partner 6 times a day, on average, once every four hours.
   - The media source account in the **Cost settings** section is updated according to what you did at the app level via the **Cost** tab.

</Tab>
<Tab title="Enable on the account level (Cost settings page)">

You need to connect each media source account once to enable cost for multiple or all apps in your AppsFlyer account.

To enable the cost integration on the account level, follow these steps:

1. In AppsFlyer, from the side menu, open **Settings** > **ROI360** > **Cost settings.**
2. Select the media source to retrieve cost data, then click **Next**.
3. Configure and authenticate the cost integration to the media source. The authentication method depends on the media source. See [Cost integration methods](#cost-integration-methods) below.
4. Enter (or customize) the cost integration name.
5. Select the apps to include in this cost integration.
6. Click **Save integration**.
   - Cost data will start showing on your dashboards within 5-6 hours.
   - AppsFlyer collects data from the media source 6 times a day, on average, once every four hours.
   - Updates made at the account level in **Cost settings** are automatically applied to the **Active Integration**'s **Cost** tab for relevant apps and media sources.

</Tab>
</Tabs>

> 📘 Note
>
> If an advertiser uses an agency to run their campaigns, we recommend that the agency, and not the advertiser, integrate with the relevant partners. Otherwise, cost data is duplicated if both the advertiser and agency integrate with a media source using the same credentials for the same app.

## Cost integration methods

The method for enabling cost integration depends on the media source's integration mode with AppsFlyer. It can be one of the following:

- **Login**: Click **Log in to \<media source\>** to open the media source login window. Then follow the media source's login prompts.
- **Credentials**: Enter media source-specific parameter values, for example, **API Key**.
- **None:** No connection configuration is required other than turning on **Get Cost Data** like was instructed above.

To learn what method a particular media source uses, you can see the **Integration method** column in the [media source cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api).

## Site ID mapping

[Some media source integrations](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) allow you to select how the [site ID](/docs/raw-data-field-dictionary#attribution::e9b53459) field populates when reporting cost data. This makes sure that the AppsFlyer attribution link `site-id` macros match the value the media source expects.

- By default, site ID mapping is aligned with the AppsFlyer macros in the attribution link.
- If your attribution link uses macros that differ from the site ID mapping options, site ID data will not populate correctly.

To set Site ID mapping on the app level, follow these steps:

1. In the integrated partner **Cost** tab, go to **Site ID mapping**, and select a configuration from the dropdown menu.
2. Click **Save Cost**. The change takes effect from the next day UTC.

## Delete cost integrations

You can delete cost integrations at either the app or the account level. Once deleted, AppsFlyer can no longer pull cost data from the account. Deleting an integration does not impact historical data.

<Tabs>
<Tab title="Delete on the app level (Cost tab)">

You can delete the integration at any time.

To delete the cost integration on the app level, follow these steps:

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Active integrations**.
2. Select the integrated partner (for example, Meta Ads).
3. Click **Manage integration**.
4. Open the **Cost** tab. The list of connected accounts is displayed.
5. In the **Actions** column, hover over the account and click **Delete connection**.
6. In response to the confirmation prompt, click **Yes, Delete**.

The cost integration previously configured at the app level has been removed from both the app and account levels. As a result, cost data collection will be stopped immediately. This change does not affect any historical cost data already collected.

</Tab>
<Tab title="Delete on the account level (Cost settings page)">

To delete the cost integration on the account level, follow these steps:

1. In AppsFlyer, from the side menu, select **Settings** > **ROI360 > Cost settings** and select the media source from which you want to delete the integration.
2. In the integrations list for the media source, click the integration record.
3. In response to the confirmation prompt, click **Yes, Delete**.

The cost integration previously configured on the account level has been removed from both the app and account levels. As a result, cost data collection will be stopped immediately. This change does not affect any historical cost data already collected.

</Tab>
</Tabs>

## Disable Cost API

Disabling the Cost API is available only at the app level.

To turn off Cost API, follow these steps:

1. Go to **Active integrations** and select the media source.
2. Go to the **Cost** tab.
3. Turn off **Get Cost Data**.
4. Click **Save Cost**.

> 📘 Note
>
> If an advertiser stops working with an agency and turns off the agency permissions at the app level, cost data is still pulled if the agency has cost configured for the app. The advertiser must ask the agency to turn off their cost integration to stop this data from being pulled.

## Cost API status

The operational status of cost integrations is available as follows:

- Cost (and ad revenue) integration status dashboard: Centralized list of media sources for which cost integration is enabled for one or more apps housed in your account.
- Integrated partners: Status available in the context of an individual app.
- Cost settings: The **Cost settings** page allows you to view the cost API status at both the account and app levels. For more information, see the "View the media source aggregate cost integration status" below.

### View the media source cost integration status (Cost tab)

The **Cost** tab in the media source **Active integration** page (relevant for media sources that support getting cost data via API) displays:

- The status of your cost integration of the selected app.
- Last time, AppsFlyer successfully pulled matching cost data for the app.

To view the individual media source cost integration status for a selected app, follow these steps:

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Active integrations.**
2. Select the media source.
3. In the media source **Active integration** page, select the app whose cost status you want to view from the App list above the tab bar.
4. Click the **Cost** tab. The status and last sync time are displayed.

### View the media source aggregate cost integration status (Cost settings page)

To view the media source aggregate cost integration status, follow these steps:

1. In AppsFlyer, from the side menu, select **Settings** > **ROI360 > Cost settings**.
2. Select the relevant media source.
3. On the media source page, you can see the media source account status in the **Status** column. If all apps associated with the account have the same status, that status is displayed. If app statuses differ, the status shows as **Mixed status**.
4. To see a specific app's status associated with a media source account, click the media source account row to display the **Cost integration** page.
5. View the app status in the list of the media source-associated apps.

### Status table

| Status | Remarks/action required |
| --- | --- |
| Active | Integration is enabled and successfully connected to the media source. |
| API is not returning matching cost data | This may happen because:<br />• The campaign ID has not been provided, so the cost can't be matched to campaigns.<br />• You integrated a different partner ad account when logging into the partner via AppsFlyer (for example, a different Meta ads account). Check that you connected the right partner ad account.<br />• One of the credential fields in the partner cost integration is incorrect. For example, the bundle ID. Review and correct the integration credentials.<br />• Your campaigns are paused, and there is no data. |
| Partner API is not responding | • The integrated partner's server is not responding to AppsFlyer.<br />• Wait 6 hours. If the status message persists, contact AppsFlyer support. |
| Invalid credentials | • AppsFlyer can't get data via the API because the credentials are not valid.<br />• Reconnect using the correct credentials. |
| Reach out to your ad network account manager to get access to their reporting API | Work with the partner account manager to enable the cost integration in the partner's system. |
| Partner API is not returning data. Review integration. | This happens because:<br />• Your campaigns are paused, and there is no data. |
| Your account is not enabled on the partner system to get cost data | Contact the partner. |
| Mixed status | Status is shown on the Cost settings > **Media source** page only if the associated apps have different statuses. From the **Media source** page, open the **Integration** page to view the status of the individual app. This status isn't displayed on the status dashboard |

## Account-level cost configuration supporting media sources

ROI360 customers can create and edit cost integrations at the account level in **Cost settings** and in the **Cost** tab. The following media sources support account-level cost configuration:

| Display name | Integration ID |
| --- | --- |
| AdAction3 | `adaction5_int` |
| Adbloom | `adbloom_int` |
| AdColony | `adcolony_int` |
| AdGate Media | `adgatemedia_int` |
| adjoe GmbH | `adjoe_int` |
| Adikteev Retargeting | `trademob_int` |
| Apple Search Ads | `iossearchads_int` |
| AppLift | `applift_int` |
| AppLovin | `applovin_int` |
| Aura | `aura_int` |
| Blind Ferret Agency | `blindferret_int` |
| Bluestacks | `bluestacks_int` |
| ByteDance | `bytedance_int` |
| Chartboost | `chartboost_int` |
| Dataseat | `dataseat_int` |
| Digital Turbine Legacy | `appia_int` |
| Digital Turbine On Device | `digitalturbine_int` |
| Domob | `domobc_int` |
| DV360 | `dv360_int` |
| GlobalWide Media | `globalwide_int` |
| Google Ads | `googleadwords_int` |
| InMobi | `inmobi_int` |
| InMobi DSP | `inmobidsp_int` |
| Liftoff Influence | `jetfuelit_int` |
| Mediaforce | `mediaforce_int` |
| Meta Ads | `facebook` |
| Mintegral | `mintegral_int` |
| Mobupps | `mobupps_int` |
| Moloco | `moloco_int` |
| MoPub Acquire | `crossinstall_int` |
| Opera Mobile | `operaevent_int` |
| Persona.ly RTB | `personalyrtb_int` |
| Pinterest | `pinterest_int` |
| Pinsight | `pinsight_int` |
| Point2Web | `point2web_int` |
| Reddit | `reddit_int` |
| Smadex | `smadex_int` |
| Snapchat | `snapchat_int` |
| Tapjoy | `tapjoy_int` |
| Taptica | `taptica_int` |
| TikTok | `tiktokglobal_int` |
| TUNE | `hasoffers_int` |
| Unity Ads | `unityads_int` |
| X (Twitter) | `twitter` |

Additional media sources are available through InCost ad networks. To get the full list of supported InCost ad networks, contact your Customer Success Manager (CSM).

## Traits and limitations

| Trait | Description |
| --- | --- |
| Agencies | Agencies can't use Cost settings to perform cost integrations across multiple apps simultaneously. |
| Future apps automatically inherit the cost settings feature in Account-level Cost settings | Currently not supported |
| Cost data behavior when the advertiser and agency connect to the same ad network | If both an **advertiser and an agency connect to cost integration** for the same ad network account (for example, Google Ads), cost data is pulled from the **account that receives attribution**.<br />**Example scenario:**<br />- The advertiser connects to cost integration using the advertiser credentials<br />- The agency connects cost integration using agency credentials<br />- Attribution assigned to the agency account.<br />**Result:**<br />- ROI360 pulls **cost data from the agency connection**.<br />- The **advertiser connection** shows as No Data. |
| Google cost integration automatic disconnection | Cost integrations that show a **No Data** or **Invalid credentials** status for more than 365 consecutive days are automatically disconnected. This applies to Google integrations only. |
| TikTok advertiser ID list configuration | Configure the advertiser ID list at the account level using only advertiser IDs connected to the TikTok user in the ad network.<br />Advertiser IDs added to the list that are not aligned with the user in the ad network do not return cost data. |