---
title: NativeX campaign configuration
metadata:
  keywords:
    - Advertisers
    - NativeX
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-28T12:46:22Z'
  edited_at: '2026-08-13T08:46:59Z'
  id: 208209876
  locale: en-us
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/208209876-NativeX-campaign-configuration
---
> **At a glance:** NativeX, an AppsFlyer integrated partner, is a mobile advertising network specializing in native ad formats that seamlessly blend in with the user’s game or app, delivering higher revenues for developers. In addition to click-based mobile attribution, NativeX also offers cost and view-through attribution, which you can record with AppsFlyer.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobvista.png?v=1" width="150px" />

## Setting up NativeX

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

NativeX's configuration window includes 4 active tabs: Integration, Attribution link, Cost, and Permissions. Click on the items below to read about the tabs setup.

> 📘 **Note**
>
> * The General Settings step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partners

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable set up of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">here</Anchor>.

General Settings

**App ID**

NativeX connects with AppsFlyer via a unique w3i App ID. If you don't already have an App ID, you must obtain it from NativeX to continue with the integration.

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from NativeX. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to NativeX following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to NativeX.

### In-app events settings

In this section, you can map your AppsFlyer events with NativeX via postbacks.

1. Enter the w3i App ID again.
2. Toggle In-App Event Postbacks to ON
3. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list
5. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on NativeX's side.  <br />Obtain the corresponding Event ID from NativeX and set in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to NativeX for attributing NativeX's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with NativeX.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific NativeX campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns NativeX.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the subsite ID parameter, to avoid <Anchor target="_blank" href="/marketers/fr/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">**AppsFlyer Attribution Link Structure and Parameters**</Anchor>.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to NativeX.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">click lookback window here</Anchor>.

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to NativeX to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to NativeX, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">view-through attribution here</Anchor>.

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to NativeX to be activated when a corresponding ad is watched, usually for 1 second or more.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

NativeX automatically sends encrypted CPI cost data on the attribution link for all installs.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue data is not supported by NativeX.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant NativeX, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for NativeX, the permissions tab is active and you can grant control to NativeX.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKW7WZR589NZ45YYQB48W2M5=setting-up-nativex h_01HKW7WZR52157AQERBZY0VV75=integration-tab h_01HKW7WZR5QY0Y3NAKAGMJ8W6C=activate-partners h_01HKW7WZR51EWEB7Q0JDA69T2Z=default-postbacks inapp-events-settings=in-app-events-settings h_01HKW7WZR5P648PG9P2E7E7XRM=in-app-events-settings h_01HKW7WZR6W3ANFNEKZQ90RBTJ=attribution-link-tab h_01HKW7WZR617PKZ0GT3BME4NQH=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW7WZR68SBAC1XFH5143FXP=click-through-attribution h_01HKW7WZR6GQ15Y45TC5FKDX54=click-attribution-link viewthrough-attribution-lookback-window=view-through-attribution-lookback-window h_01HKW7WZR6QJ9P1KB54TWFD0YC=view-through-attribution-lookback-window h_01HKW7WZR6Q7Q77EF1J9V3BHMR=impressions-attribution-link h_01HKW7WZR6RGPNHCVPX80FW1Q6=cost-tab h_01HKW7WZR6955K4V6NA6MJ519J=ad-revenue-tab h_01HKW7WZR61N5CH1PZBE9YCNVA=permissions-tab h_01HKW7WZR6KMJS50DNJX5E7KQ1=ad-network-permissions" />
