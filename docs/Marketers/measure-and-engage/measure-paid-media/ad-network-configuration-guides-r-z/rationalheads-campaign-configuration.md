---
title: RationalHeads campaign configuration
metadata:
  keywords:
    - rationalheads
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-04T15:30:57Z'
  edited_at: '2026-07-27T09:43:16Z'
  id: 208277926
  locale: en-us
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/208277926-RationalHeads-campaign-configuration
---
> **At a glance:** Remerge, an AppsFlyer ad network integrated partner, enables app-marketers to deliver better-placed, customized advertisements. In addition to click-based mobile attribution, Remerge offers view-through mobile attribution and click-based retargeting, which can be recorded with AppsFlyer.

<div id="setting-up-rationalheads" />

## Setting up RationalHeads

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

RationalHead's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">here</Anchor>.

<div id="tip" />

> 👍 **Tip**
>
> * The <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#d-general-settings">General Settings</Anchor> step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

<div id="general-settings" />

### General settings

**Part ID**

RationalHeads connects with AppsFlyer via a unique Part ID. If you don't already have the Part ID and password, you must obtain it from RationalHeads to continue with the integration.

<Image align="center" alt="Rationalheads_msc_new_2.png" src="https://files.readme.io/7e93003c13d4fa1e60bee4120307691b618757a7c55a271561827823005b86c3-360002076529.png" width="317px" />

<div id="default-postbacks" />

### Default postbacks

<div id="activate-partner" />

### Activate partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">here</Anchor>.

Send automatic postbacks to RationalHeads following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to RationalHeads.

<div id="in-app-events-settings" />

### In-app events settings

In this section, you can map your AppsFlyer events with RationalHeads via postbacks.

1. Toggle In-App Event Postbacks to ON.
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list.
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on RationalHead's side.  <br />Obtain the corresponding Event ID from RationalHeads and set in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to RationalHeads for attributing RationalHead's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

<div id="attribution-link-parameters" />

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with RationalHeads.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific RationalHeads campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns RationalHeads.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid <Anchor target="_blank" href="/marketers/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

<div id="click-through-attribution" />

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to RationalHeads.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/docs/set-up-lookback-windows">click lookback window here</Anchor>.

<div id="click-attribution-link" />

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to RationalHeads to be activated when leads click on a corresponding ad.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant RationalHeads, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for RationalHeads, the permissions tab is active and you can grant control to RationalHeads.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

<div id="ad-network-permissions" />

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HJRZB6JCPYZZJ3QWS9BRJPSX=setting-up-rationalheads h_01HJRZB6JC4GDCV3RVGJBFTPAT=tip h_01HJRZB6JCE5G700RRHGJY3M4A=integration-tab h_01HJRZB6JCXARZ29M8RCP30VBD=general-settings h_01HJRZB6JCXR6ZHH3YV05W6JY1=default-postbacks h_01HJRZB6JCW3C1AWRS4041SKJP=activate-partner inapp-events-settings=in-app-events-settings h_01HJRZB6JDH6A108JYXEST4AQY=in-app-events-settings h_01HJRZB6JDG7YQD0ANE4W8C55C=attribution-link-tab h_01HJRZB6JDM91MC9B4VXCHEW6Z=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HJRZB6JDQ148X9J0XCFPVZD1=click-through-attribution h_01HJRZB6JDZ27KM6N7GVZX54CW=click-attribution-link h_01HJRZB6JDJG6HVCEXMC5S30NM=cost-tab h_01HJRZB6JDTJE0K27Y4XTJG7QX=ad-revenue-tab h_01HJRZB6JDD32KPQ13CTEEMEBB=permissions-tab h_01HJRZB6JD6412B28R5N8MRVH3=ad-network-permissions" />
