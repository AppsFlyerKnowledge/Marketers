---
title: "Remerge campaign configuration"
excerpt: "Remerge, an AppsFlyer ad network integrated partner, enables app-marketers to deliver better-placed, customized advertisements. In addition to click-based mobile attribution, Remerge offers view-through mobile attribution and click-based retargeting, which can be recorded with AppsFlyer."
x-zendesk:
  id: 115000172003
  url: https://support.appsflyer.com/hc/en-us/articles/115000172003-Remerge-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  position: 3
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Re-Targeting, Retargeting, retargeting, Remerge, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2017-01-02T16:20:43Z'
  edited_at: '2026-09-09T13:13:23Z'
---
## Setting up Remerge

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

> 📘 **Note**
>
> As an ALL-Installs network, Remerge prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to Remerge.

### Install and Re-engagement attribution

These two toggles enable you to attribute users, who only viewed your ad, but didn’t click on it, to Remerge.

* Switch on ***Install view-through attribution*** to attribute new installs following impressions only, to Remerge.
* Switch on ***Re-engagement view-through attribution*** to attribute new re-engagements of your existing users following impressions only, to Remerge.

### Default postbacks

Send automatic postbacks to Remerge following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Remerge.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Remerge.

### In-app events settings

In this section, you can map your AppsFlyer events with Remerge via postbacks.  
If you choose to map all events (both including and excluding their revenue values) the af\_app\_opened event will NOT be sent to Remerge.  
If you wish to send af\_app\_opened events to Remerge you must add each event manually.

1. Toggle on In-App Event Postbacks
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server-to-server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Remerge for attributing Remerge's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Remerge.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Remerge campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Remerge.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise limiting the number of used site IDs and using the subsite ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about[**AppsFlyer's Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters).

### Retargeting settings

When enabled, AppsFlyer recognizes a link as a [retargeting](/docs/retargeting-attribution-guide) attribution link, rather than a user acquisition link, by adding the `&is_retargeting=true` to the click recording link. Note that retargeting is currently only supported for click-through and not view-through attribution.  
**Attribution link parameter:** is\_retargeting.

The following setup below is displayed when retargeting is enabled.

1. Standard Link vs. OneLink

Select ***standard attribution link*** option if:

* You don't need to deep link with the URL or
* Plan to use only [URI schemes](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings) for deep linking

select ***Use OneLink*** for:

* Using a single link for both Android and iOS apps or
* Deep linking using Universal or app links

Note that selecting OneLink changes the click recording link from app specific to a [OneLink URL](/docs/onelink-guide).

2. Deep Link URL

Use this field if the link is meant to deep link users to any specific activity within your app.  
**Attribution link parameter:** af\_dp  
You can find more information about AppsFlyer [deep linking solution in this guide.](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink)

3. Re-engagement Window

Set the time period following the re-engagement, where the user's in-app events are attributed to the retargeting media source. You can set the value in days (1-90), hours (up to 23), or even lifetime.

**Attribution link parameter:** af\_reengagement\_window

### Click-through attribution

This slider allows you to set the **maximum time from click-to-install**. Only installs (first launches) that take place within the lookback window may be attributed to Remerge.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Remerge to be activated when leads click on a corresponding ad.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow [these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api).

[View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported by Remerge.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Remerge, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Remerge, the permissions tab is active and you can grant control to Remerge.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -*only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).

</Accordion>

<div data-zendesk-anchors="h_01HJRZQ2X3A955H1T76X8GF35A=setting-up-remerge h_01HJRZQ2X45PTBDQARWHDSJS1V=integration-tab h_01HJRZQ2X4PG81M9GYBGPNANGY=activate-partner h_01HJRZQ2X4THDK9AV0MFGKD5GG=note install-and-reengagement-attribution=install-and-re-engagement-attribution h_01HJRZQ2X4KQHXXJH3F4TNABC4=install-and-re-engagement-attribution h_01HJRZQ2X4TY2DT0DTTEMJYWPG=default-postbacks inapp-events-settings=in-app-events-settings h_01HJRZQ2X549ZMW6SZGHPG6853=in-app-events-settings h_01HJRZQ2X56BEBQ0FHJYCMGE4J=attribution-link-tab h_01HJRZQ2X5EE1XDFN56VEEPWKM=attribution-link-parameters h_01HJRZQ2X60JEVJYVK5X934DP4=retargeting-settings clickthrough-attribution=click-through-attribution h_01HJRZQ2X6DGP82VBKNF86S0E0=click-through-attribution h_01HJRZQ2X61NZQB1JSMSRMNTH7=click-attribution-link h_01HJRZQ2X6M83KFXR58BS4B024=cost-tab h_01HJRZQ2X6GZ51M21S5PTD3NC4=ad-revenue-tab h_01HJRZQ2X67S37CAH31KNVRQPG=permissions-tab h_01HJRZQ2X6CEX8T2A57JHBHERR=ad-network-permissions" />
