---
title: Zenna campaign configuration
metadata:
  keywords:
    - Advertisers
    - Zenna
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-10-23T06:52:44Z'
  edited_at: '2026-09-09T13:01:57Z'
  id: 115005277446
  locale: en-us
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115005277446-Zenna-campaign-configuration
---
> **At a glance:** Zenna, an AppsFlyer integrated ad network partner, provides a performance-based user acquisition solution solely for mobile games.

## Setting up Zenna

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partner

On the **first visit**, you will need to turn on the ***Activate Partner*** toggle to enable setup of the integration tab's parameters. The toggle **must** be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">here</Anchor>.

Default Postbacks

Send automatic postbacks to Zenna following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

> 📘 **Note**
>
> The option **Only events attributed to this partner** is the only option with Zenna and is selected by default.

### In-app events settings

In this section, you can map your AppsFlyer events with Zenna via postbacks.

1. Toggle In-App Event Postbacks to ON
2. Click **Add Event** to add an SDK Event to the list
3. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app or from server-to-server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Zenna's side.  <br />Obtain the corresponding Event ID from Zenna and set in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Zenna for attributing Zenna's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Zenna.  
  **Attribution link parameter:** c
* **Adset** - set adset names to compare different ad sets within specific Zenna campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set adset names to compare different creatives within specific ad sets within specific campaigns Zenna.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set the Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub-site ID parameter, to avoid <Anchor target="_blank" href="/marketers/fr/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Zenna.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">click lookback window here</Anchor>.

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Zenna to be activated when leads click on a corresponding ad.

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

In this tab, you can select the permissions to grant Zenna, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Zenna, the permissions tab is active and you can grant control to Zenna.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to set up in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HK29KRYQHED4BDRQTXX3QCQG=setting-up-zenna h_01HK29KRYQV8ZB97MB7N8KQYAC=integration-tab h_01HK29KRYQ8P16VHDBZMR7464W=activate-partner h_01HK29KRYQPVTA71RT3V3KMD0Q=note inapp-events-settings=in-app-events-settings h_01HK29KRYQBZ8A63YRC7B8MC5P=in-app-events-settings h_01HK29KRYQ458XWFHVQK58DQ5Z=attribution-link-tab h_01HK29KRYQM4SEJ3JERHK4XP66=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HK29KRYR6E498ZJM8AYEYMZ2=click-through-attribution h_01HK29KRYRBM7ZN2956V3GY1X7=click-attribution-link h_01HK29KRYR203VFA2SX4HAWQVV=cost-tab h_01HK29KRYR03B6TKGVEZXF7CRK=ad-revenue-tab h_01HK29KRYREKNX908FP46XNJT5=permissions-tab h_01HK29KRYRW98Q8XS91DK5BTAA=ad-network-permissions" />
