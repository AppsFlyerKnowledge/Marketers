---
title: "Ströer Mobile Performance campaign configuration"
excerpt: "Learn how to configure your mobile campaigns and record cost data with Ströer Mobile Performance in AppsFlyer."
x-zendesk:
  id: 115000068903
  url: https://support.appsflyer.com/hc/en-us/articles/115000068903-Str%C3%B6er-Mobile-Performance-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  position: 9
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Stroer, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2016-12-19T09:26:27Z'
  edited_at: '2026-07-27T09:42:39Z'
---
Ströer Mobile Performance, an AppsFlyer ad network integrated partner, provides international exposure suited to mobile applications through its unique global network. In addition to click-based mobile attribution, Ströer Mobile Performance provides cost data, which can be recorded with AppsFlyer.

To configure your campaigns with Ströer Mobile Performance, follow the steps below.

## Setting up Ströer mobile performance

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

Ströer Mobile Performance's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

> 👍 Tip
>
> - The [General Settings](/docs/set-up-an-integrated-partner#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> - All the rest of the steps are either descriptive or **optional**

## Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partners

On the **first visit** here, you will need to turn on the **Activate Partner** toggle to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](/docs/partner-activation-deactivation).

General Settings

**Security Token**

Ströer Mobile Performance connects with AppsFlyer via a unique Security Token. If you don't already have it, you must obtain it from Ströer Mobile Performance to continue with the integration.

### Default postbacks

Send automatic postbacks to Ströer Mobile Performance following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Ströer Mobile Performance.

### In-app events settings

In this section, you can map your AppsFlyer events with Ströer Mobile Performance via postbacks.

1. Toggle In-App Event Postbacks to ON
2. Select the Sending Option for all SDK-defined events.

**- Only events attributed to this partner** for events coming **only** from users attributed to this partner

**- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.<br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Ströer Mobile Performance's side.<br />Obtain the corresponding Event ID from Ströer Mobile Performance and set in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af_revenue** parameter.<br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

## Attribution link tab

In this tab, you can create the attribution links you want to send to Ströer Mobile Performance for attributing Ströer Mobile Performance's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with Ströer Mobile Performance.

  **Attribution link parameter:** c
- **Adset** - set ad set names to compare different ad sets within specific Ströer Mobile Performance campaigns.

  **Attribution link parameter:** af_adset
- **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Ströer Mobile Performance.

  **Attribution link parameter:** af_ad
- **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the subsite ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.

  **Attribution link parameters:** af_siteid and af_sub_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

  **Attribution link parameters:** af_sub1, af_sub2, af_sub3, af_sub4, af_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about [**AppsFlyer's Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters).

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Ströer Mobile Performance.

**Attribution link parameter:** af_click_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Ströer Mobile Performance to be activated when leads click on a corresponding ad.

## Cost tab

Ströer Mobile Performance automatically sends CPI cost data on the attribution link for all installs.

For the full list of partners supporting cost data, click [here](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api).

## Ad revenue tab

Ad Revenue data is not supported by this partner.

## Permissions tab

In this tab, you can select the permissions to grant Ströer Mobile Performance, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Ströer Mobile Performance, the permissions tab is active and you can grant control to Ströer Mobile Performance.

Use these toggles to give the ad network permissions to handle its own configuration for your app.

### Ad Network Permissions

- _**Allow to configure integration**_ - permit the partner to set up the Integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your aggregate loyal user data**_ - only to the partner's own loyal user data
- _**Allow access to your aggregate in-app events data**_ - only to the partner's own in-app events data
- _**Allow access to your aggregate revenue data**_ - only to the revenue data attributed to the partner
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).