---
title: "Fyber campaign configuration"
excerpt: "Learn how to set up and configure your Fyber campaigns in AppsFlyer, including integration settings, attribution links, cost, ad revenue, and permissions."
x-zendesk:
  id: 208209366
  url: https://support.appsflyer.com/hc/en-us/articles/208209366-Fyber-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  position: 23
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [fyber, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2016-03-28T08:29:40Z'
  edited_at: '2026-09-09T13:04:24Z'
---
Fyber, an AppsFlyer ad network integrated partner, develops a next-generation monetization platform for mobile publishers.

## Setting up Fyber

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

### Activate partners

On the **first visit** here, you will need to toggle on the _**Activate Partner**_ button to enable the setup of the integration tab's parameters. The toggle must be on for as long as you work with the partner.

For more details about partner activation, click [here](/docs/partner-activation-deactivation).

### General Settings

**App ID**

Fyber connects with AppsFlyer via a unique network ID. If you don't already have the Network ID, you must obtain it from Fyber to continue with the integration.

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from Fyber. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to Fyber following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Fyber.

Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Fyber.

### In-app events settings

In this section you can map your AppsFlyer events with Fyber via postbacks.

1. Set the Fyber App ID again here
2. Toggle In-App Event Postbacks to ON
3. Select the Sending Option for all SDK-defined events.

**- Only events attributed to this partner** for events coming **only** from users attributed to this partner

**- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list
5. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated with your app, or from server to server events.<br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Fyber's side.<br />Obtain the corresponding Event ID from Fyber and set it in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af_revenue** parameter.<br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

## Attribution link tab

In this tab, you can create the attribution links you want to send to Fyber for attributing Fyber's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with Fyber.

  **Attribution link parameter:** c
- **Adset** - set ad set names to compare different ad sets within specific Fyber campaigns.

  **Attribution link parameter:** af_adset
- **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Fyber.

  **Attribution link parameter:** af_ad
- **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the subsite ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.

  **Attribution link parameters:** af_siteid and af_sub_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

  **Attribution link parameters:** af_sub1, af_sub2, af_sub3, af_sub4, af_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about [**AppsFlyer's Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters).

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Fyber.

**Attribution link parameter:** af_click_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Fyber to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to Fyber, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af_viewthrough_lookback

More details about the [view-through attribution here](/docs/set-up-lookback-windows).

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to Fyber to be activated when a corresponding ad is watched.

## Cost tab

AppsFlyer gets cost details by API. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

- Follow [these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api).

[View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

## Ad revenue tab

Fyber provides ad revenue mediation with [user-level granularity](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data).

**To enable the ad revenue API**:

- Follow [these integration instructions](/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners).

## Permissions tab

In this tab, you can select the permissions to grant Fyber, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Fyber, the permissions tab is active and you can grant control to Fyber.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

- _**Allow to configure integration**_ - permit the partner to set up the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your aggregate loyal user data**_ - only to the partner's own loyal user data
- _**Allow access to your aggregate in-app events data**_ - only to the partner's own in-app events data
- _**Allow access to your aggregate revenue data**_ - only to the revenue data attributed to the partner
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

- _**Main toggle**_ - Set to On to reveal the agency permissions options
- _**Allow access to your retention report**_ - only to the agency's own retention data
- _**Allow access to aggregate organic data**_
- _**Allow to configure in-app event postbacks**_ - permit the agency to setup in-app event postbacks mapping to itself on the integration tab

Learn more about granting [agency permissions](/docs/set-up-an-integrated-partner#agency-permissions).