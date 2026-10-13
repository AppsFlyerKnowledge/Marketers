---
title: "StartApp campaign configuration"
excerpt: "Learn how to configure mobile attribution, cost, and permissions for your StartApp campaigns in AppsFlyer."
x-zendesk:
  id: 210042746
  url: https://support.appsflyer.com/hc/en-us/articles/210042746-StartApp-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  position: 5
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [StartApp, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2016-06-30T10:55:10Z'
  edited_at: '2026-09-07T07:26:10Z'
---
StartApp, an AppsFlyer ad network integrated partner, is an insight-driven mobile tech company that enables its partners to deliver the world's most fulfilling mobile experiences for their users. In addition to click-based mobile attribution, StartApp offers cost, retargeting, and view-through attribution, which can be recorded with AppsFlyer.

To configure your campaigns with StartApp, follow the steps below.

## Setting up StartApp

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

StartApp's configuration window includes 4 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

> 👍 Tip
>
> - The [General Settings](/docs/set-up-an-integrated-partner#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> - All the rest of the steps are either descriptive or **optional**

## Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to turn on the **Activate Partner** toggle to enable setup of the Integration parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](/docs/partner-activation-deactivation).

> 📘 Note
>
> As an ALL-Installs network, StartApp prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to StartApp.

### General settings

**Enable View-Through attribution**

Turn this on if you want to attribute view-through installs from StartApp. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to StartApp following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to StartApp.

Select **Events attributed to any partner or organic** to have your entire user base available to be reported to StartApp.

### In-app events settings

In this section, you can map your AppsFlyer events with StartApp via postbacks.

1. Toggle In-App Event Postbacks to ON
2. Select the Sending Option for all SDK-defined events.

**- Only events attributed to this partner** for events coming **only** from users attributed to this partner

**- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app or from server-to-server events.<br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on StartApp's side.<br />Obtain the corresponding Event ID from StartApp and set it in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af_revenue** parameter.<br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

## Attribution link tab

In this tab, you can create the attribution links you want to send to StartApp for attributing StartApp's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with StartApp.

**Attribution link parameter:** c
- **Adset** - set ad set names to compare different ad sets within specific StartApp campaigns.

**Attribution link parameter:** af_adset
- **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns StartApp.

**Attribution link parameter:** af_ad
- **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise limiting the number of used site IDs and using the subsite ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.

**Attribution link parameters:** af_siteid and af_sub_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

**Attribution link parameters:** af_sub1, af_sub2, af_sub3, af_sub4, af_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about [**AppsFlyer's attribution link structure and parameters**](/docs/about-link-structure-and-parameters) .

### Retargeting settings

When enabled, AppsFlyer recognizes a link as a [retargeting](/docs/retargeting-attribution-guide) attribution link, rather than a user acquisition link, by adding the `&is_retargeting=true` to the click recording link. Note that retargeting is currently only supported for click-through and not view-through attribution.

**Attribution link parameter:** is_retargeting.

The following setup below is displayed when retargeting is enabled.

1. Standard Link vs. OneLink

Select _**standard attribution link**_ option if:

- You don't need to deep link with the URL or
- Plan to use only [URI schemes](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings) for deep linking

select _**Use OneLink**_ for:

- Using a single link for both Android and iOS apps or
- Deep linking using Universal or app links

Note that selecting OneLink changes the click recording link from app specific to a [OneLink URL](/docs/onelink-guide).

2. Deep Link URL

Use this field if the link is meant to deep link users to any specific activity within your app.

**Attribution link parameter:** af_dp

You can find more information about AppsFlyer [deep linking solution in this guide.](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink)

3. Re-engagement Window

Set the time period following the re-engagement, where the user's in-app events are attributed to the retargeting media source. You can set the value in days (1-90), hours (up to 23), or even lifetime.

**Attribution link parameter:** af_reengagement_window

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to StartApp.

**Attribution link parameter:** af_click_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to StartApp to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to StartApp, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af_viewthrough_lookback

More details about the [view-through attribution here](/docs/set-up-lookback-windows).

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to StartApp to be activated when a corresponding ad is watched, usually for 1 second or more.

## Cost tab

StartApp automatically sends encrypted CPI cost data on the attribution link for all installs.

## Ad revenue tab

Ad Revenue integration is not available for this partner.

## Permissions tab

In this tab, you can select the permissions to grant StartApp, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for StartApp, the permissions tab is active and you can grant control to StartApp.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

- _**Allow to configure integration**_ - permit the partner to set up the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to set up in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your aggregate loyal user data**_ - only to the partner's own loyal user data
- _**Allow access to your aggregate in-app events data**_ - only to the partner's own in-app events data
- _**Allow access to your aggregate revenue data**_ - only to the revenue data attributed to the partner
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).