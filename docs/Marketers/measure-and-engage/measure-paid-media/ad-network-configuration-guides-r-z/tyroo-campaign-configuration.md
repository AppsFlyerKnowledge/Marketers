---
title: Tyroo campaign configuration
metadata:
  keywords:
    - Advertisers
    - Tyroo
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-03T11:32:42Z'
  edited_at: '2026-09-09T13:07:33Z'
  id: 208270836
  locale: en-us
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/208270836-Tyroo-campaign-configuration
---
> **At a glance:** Tyroo, an AppsFlyer ad network integrated partner, is a leading global mobile user acquisition and monetization platform. In addition to click-based mobile attribution, Tyroo offers cost and view-through attribution, which can be recorded with AppsFlyer.

To configure your campaigns with Tyroo, follow the steps below.

## Setting up Tyroo

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to turn on the ***Activate Partner*** toggle to enable setup of the Integration tab parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">here</Anchor>.

> 📘 **Note**
>
> As an ALL-Installs network, Tyroo prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to Tyroo.

### General settings

**Partner ID**

Tyroo connects with AppsFlyer via a unique action key. If you don't already have the action key, you must obtain it from Tyroo to continue with the integration.

**Enable View-Through attribution**

Turn this to on if you want to attribute view-through installs from Tyroo. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to Tyroo following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Tyroo.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Tyroo.

### In-app events settings

In this section, you can map your AppsFlyer events with Tyroo via postbacks.

1. Turn on In-App Event Postbacks
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server-to-server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Tyroo's side.  <br />Obtain the corresponding Event ID from Tyroo and set it in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Tyroo for attributing Tyroo's campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Tyroo.  
  **Attribution link parameter:** c
* **Adset** - set adset names to compare different ad sets within specific Tyroo campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set adset names to compare different creatives within specific ad sets within specific campaigns Tyroo.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set the Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise limiting the number of used site IDs and using the subsite ID parameter, to avoid <Anchor target="_blank" href="/marketers/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Tyroo.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/docs/set-up-lookback-windows">click lookback window here</Anchor>.

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Tyroo to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to Tyroo, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the <Anchor target="_blank" href="/marketers/docs/set-up-lookback-windows">view-through attribution here</Anchor>.

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to Tyroo to be activated when a corresponding ad is watched, usually for 1 second or more.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Tyroo automatically sends CPI cost data on the attribution link for all installs.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Tyroo, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Tyroo, the permissions tab is active and you can grant control to Tyroo.

Use these toggles to give the ad network permissions to handle its own configuration for your app: Ad Network Permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to set up in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HJZTZ361TE694SVPQTN8Q4C1=setting-up-tyroo h_01HJZTZ361V5G81NBA1G0ZBXJG=integration-tab h_01HJZTZ361FKYED35K4E57DEJ4=activate-partner h_01HJZTZ361QM6Z3N693N3PJ1Z9=note h_01HJZTZ362XG66Q54JRATHJW9X=general-settings h_01HJZTZ3621ZWG5TZD76Z80DHE=default-postbacks inapp-events-settings=in-app-events-settings h_01HJZTZ362WMPD0C1HMG8HC2HD=in-app-events-settings h_01HJZTZ3627FHZS6J5FABPJJ1Q=attribution-link-tab h_01HJZTZ362TG648JZEXWX3MK5P=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HJZTZ362TCHGN0MGRA0B9Z7P=click-through-attribution h_01HJZTZ36282E6VNNH740AF9EW=click-attribution-link viewthrough-attribution-lookback-window=view-through-attribution-lookback-window h_01HJZTZ362V11V157Q2NFN550W=view-through-attribution-lookback-window h_01HJZTZ362ZF2FY83NMD5ZJ89J=impressions-attribution-link h_01HJZTZ362JBBAZ5RDWJ03EE2X=cost-tab h_01HJZTZ36323B1PET2X3FPD1H1=ad-revenue-tab h_01HJZTZ3637M1AMNTWXV9NPNGV=permissions-tab" />
