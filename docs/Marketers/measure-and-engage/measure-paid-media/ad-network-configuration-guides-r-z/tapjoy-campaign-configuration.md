---
title: "Tapjoy campaign configuration"
excerpt: "Configure your mobile attribution, view-through attribution, cost, and ad revenue campaigns with Tapjoy in AppsFlyer."
x-zendesk:
  id: 207033956
  url: https://support.appsflyer.com/hc/en-us/articles/207033956-Tapjoy-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  position: 11
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Tapjoy, SDK, configuration, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2015-06-10T14:19:38Z'
  edited_at: '2026-09-08T13:50:56Z'
---
At a glance: Tapjoy, an AppsFlyer ad network integrated partner, is an advertising and app monetization platform. In addition to click-based mobile attribution, Tapjoy offers view-through attribution, which can be recorded with AppsFlyer.

To configure your campaigns with Tapjoy, follow the steps below.

## Setting up Tapjoy

> 📘 Prerequisite
>
> An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

   ( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

> 📘 Note
>
> The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)

5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

## Integration tab

The _**Integration Tab**_ is divided into different sections as described below.

### Activate partners

The [partner must be activated](/docs/partner-activation-deactivation#activating-a-partner) by switching on the _**Activate partner**_ toggle on the first visit, to enable its setup.

### General settings

#### app\_id

Tapjoy connects with AppsFlyer via a unique network ID. If you don't already have the app ID, you must obtain it from Tapjoy to continue with the integration.

#### Enable View-Through attribution

Toggle ON if you want to attribute view-through installs from Tapjoy. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to Tapjoy following installs and rejected installs. Use this section to define the **source of the users** for the postbacks.

Select _**This partner only**_ for installs coming only from users attributed to Tapjoy.

Select **_All sources, including organic_** to have your entire user base available to be reported to Tapjoy.

Rejected installs can be sent for **This partner only**.

#### Launch postbacks

As of July 1, 2020, we no longer send launch postbacks to Tapjoy. If your integration was set up prior to this date, there may be changes to your configurations. The following table explains possible changes and your actions, where applicable:

| Your configuration | Will be updated to | Your next actions |
| --- | --- | --- |
| Send to Tapjoy **all launches** (from all media sources, including organic) | Send to Tapjoy:<br />- **all installs** (from all media sources, including organic)<br />- **all `af_app_opened` events** (from all media sources, including organic) | No further actions are required. This update has no actual impact on the configuration. |
| Send to Tapjoy **attributed first launches only** | Send to Tapjoy **installs** attributed to Tapjoy only | If you wish to send `af_app_open` events as well:<br />- In AppsFlyer, on Tapjoy integration page, configure sending the event under the _**In-app event postbacks**_ section |
| Send to Tapjoy **all launches** (from all media sources, including organic)<br />**BUT**<br />No conversions have been attributed to Tapjoy in the 3 months prior to July 1, 2020 | Send **all installs**<br />**AND**<br />For 30 days after July 1, 2020, **all launches** | If you wish to send `af_app_open` events as well:<br />- In AppsFlyer, on Tapjoy integration page, configure sending the event under the _**In-app event postbacks**_ section.<br />If done during the 30-day period, we will discontinue sending all launches and start sending all `af_app_open` events instead.<br />If done after the 30-day period, we will stop sending launches and won't send `af_app_open` events until configured otherwise. |

### In-app events settings

In this section, you can configure in-app event postbacks that are sent to Tapjoy.

**To configure in-app event postbacks:**

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list.
3. Fill in the following data:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<br />   - Make sure to activate the event on a device with a non-organic installation and recheck.<br />   - Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<br />   - **Text field:** Get the corresponding event ID from the partner.<br />   - **Drop-down box:** Select the most suitable pre-defined AppsFlyer event.<br />   - **As is**: Send the events as they are, without name mapping. |
| **for users from** | Select the sending option for the event:<br />   - **This partner only**: Send postbacks only when the event is attributed to this partner—meaning, the user who performed it came from this partner.<br />   - **All media sources including organic**: Send postbacks for events attributed to any partner and for organic events—meaning, the user who performed it came from any media source. |
| **including** | - **No data (default)**: Send just the event itself, without any event values.<br />   - **Values and revenue**: Send all event parameters, including revenue values (if exist in the event).<br />   - **Values without revenue**: Send all event parameters, excluding revenue values. |

4. [Optional] Click the Add condition ![image.png](https://files.readme.io/8e650caf6472b316bd49bc25c45cc4c9d63b67770dd1c920fb873118b82ff868-17023682954385.png) icon of an event to [set conditions for the event](/docs/in-app-event-postback-configuration#conditional-inapp-event-postbacks) sent to Tapjoy.

> 🚧 Note
>
> Tapjoy recommends not adding conditions to events sent to them, as this could cause issues with Tapjoy's propriety reward system and could negatively impact user experience.

5. Click **Save Integration**.

## Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).

[Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters).

**To generate an attribution link,** follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

> 📘 Note
>
> TapJoy doesn't report Offerwall impressions to AppsFlyer. So installs following Offerwall impressions are not counted in AppsFlyer. Learn more about [Offerwall impressions](https://www.tapjoy.com/offerwall/).

## Cost tab

AppsFlyer gets cost details by API. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

- Follow [these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api).

### Cost data sync status

[View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

> 📘 Notes
>
> - If cost macros are being passed on the attribution link, the API integration cannot be enabled. Enabling the cost API integration while cost macros exist on the attribution link may cause duplicate cost reporting. Please contact your TapJoy Account Manager and your AppsFlyer CSM to remove all cost macros from the existing attribution links.
> - Once you set TapJoy's cost, do not change the name of any active campaign, ad set, or single ad, nor use dynamic macros with the campaign name parameter, as they may cause serious discrepancies or missing cost data.

## Ad revenue tab

This section is relevant if you are a publisher displaying partner ads to your users. As such, you would certainly like to measure the engagement of your users acquired from different sources to find the most profitable sources for you. Learn more about [Tapjoy ad revenue setup](https://dev.tapjoy.com/en/graphql-api/Appsflyer#iap-and-ad-revenue-configuration-for-roas).

**To enable the ad revenue API**:

- Follow [these integration instructions](/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners).

## Permissions tab

In this tab, you can select the permissions to grant Tapjoy, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Tapjoy, the permissions tab is active and you can grant control to Tapjoy.

Use these toggles to give the ad network permissions to handle its own configuration for your app.

### Ad Network Permissions

- _**Allow to configure integration**_ - permit the partner to set up the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to set up in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your aggregate loyal user data**_ - only to the partner's own loyal user data
- _**Allow access to your aggregate in-app events data**_ - only to the partner's own in-app events data
- _**Allow access to your aggregate revenue data**_ - only to the revenue data attributed to the partner
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).