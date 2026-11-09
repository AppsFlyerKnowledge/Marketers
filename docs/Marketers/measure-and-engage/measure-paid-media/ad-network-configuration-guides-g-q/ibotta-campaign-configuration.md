---
title: Ibotta campaign configuration
metadata:
  keywords:
    - Advertisers
    - Ibotta
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-02-18T07:55:23Z'
  edited_at: '2026-09-08T07:19:36Z'
  id: 360000295445
  locale: en-us
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360000295445-Ibotta-campaign-configuration
---
> **At a glance:** Ibotta, an AppsFlyer integrated ad network partner, makes it easier for consumers to earn cashback on everyday purchases through a single smartphone app.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ibotta.png?v=1" width="119px" />

<div id="setting-up-ibotta" />

## Setting up Ibotta

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab. (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle. **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="tip" />

> 👍 **Tip**
>
> * The <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#d-general-settings">General Settings</Anchor> step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**

<div id="integration-tab" />

<Accordion title="Integration tab">

<div id="activate-partner" />

### Activate partner

On the **first visit**, you will need to toggle ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">here</Anchor>.

Default Postbacks

Send automatic postbacks to Ibotta following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Ibotta.

<div id="in-app-events-settings" />

### In-app events settings

In this section, you can map your AppsFlyer events with Ibotta via postbacks.

<div id="tip-1" />

> 👍 **Tip**
>
> For a simple and quick integration, select **Send all events excluding their revenue value** or **Send all events including their revenue value**

1. Toggle In-App Event Postbacks to ON
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated with your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Ibotta's side.  <br />Obtain the corresponding Event ID from Ibotta and set it in the text field. |
| **Send Revenue** | **When unchecked** - Send all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - Send all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Ibotta for attributing Ibotta's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

<div id="attribution-link-parameters" />

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Ibotta.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Ibotta campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Ibotta.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the subsite ID parameter, to avoid <Anchor target="_blank" href="/marketers/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about **<Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">AppsFlyer's Attribution Link Structure and Parameters</Anchor>.**

<div id="click-through-attribution" />

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Ibotta.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/docs/set-up-lookback-windows">click lookback window here</Anchor>.

<div id="click-attribution-link" />

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Ibotta to be activated when leads click on a corresponding ad.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost integration is not available for this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue integration is not available for this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Ibotta, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for Ibotta, the permissions tab is active and you can grant control to Ibotta.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

<div id="ad-network-permissions" />

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* **Allow access to your aggregate revenue data** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKA2KDA0JDAF8VEXFH57Q9DP=setting-up-ibotta h_01HKA2KDA0TVNGZQ7EN899112F=tip h_01HKA2KDA05VRNN6YYTBS0AAYD=integration-tab h_01HKA2KDA0GA8GHDP2177EYV3Z=activate-partner inapp-events-settings=in-app-events-settings h_01HKA2KDA0J38WY51ZCP77J7A6=in-app-events-settings h_01HKA2KDA0HKAP9ACF2V8ZCPHX=tip-1 h_01HKA2KDA0QG78TCTKQKPZR0JV=attribution-link-tab h_01HKA2KDA0YP8SYP4YJ5NG5QSN=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKA2KDA0VPPYRMPY3S11ASX5=click-through-attribution h_01HKA2KDA0CZSSXW8DTCBTQ022=click-attribution-link h_01HKA2KDA18SHG1YAZNTE3TBZ8=cost-tab h_01HKA2KDA1JS9YF2WEEHR2K5TD=ad-revenue-tab h_01HKA2KDA1EF0F3JG3F81V3FHG=permissions-tab h_01HKA2KDA1Y2XEFHMV3XWQDDKW=ad-network-permissions" />
