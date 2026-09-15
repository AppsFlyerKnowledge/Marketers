---
title: "Mobusi campaign configuration"
excerpt: "Learn how to configure Mobusi, an AppsFlyer integrated partner, to set up mobile user acquisition campaigns, postbacks, attribution links, and permissions."
---
**At a glance:** Mobusi, an AppsFlyer integrated partner, is a mobile user acquisition and marketing services company with expertise in performance advertising.

![](https://cdn.appsflyer.com/marketplace/static/logo/mobusi.png?v=1)

## Setting up Mobusi

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

## Integration tab

### Activate partner

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable the set up of the Integration tab parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation, click [here](/docs/partner-activation-deactivation).

### Default postbacks

Send automatic postbacks to Mobusi following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

### In-app event postbacks settings

In this section you can map your AppsFlyer events with Mobusi via postbacks.

1. Toggle In-App Event Postbacks to ON
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Complete the following parameters:



| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Mobusi's side.  <br />Obtain the corresponding Event ID from Mobusi and set in the text field. |
| **Send Revenue** | **When unchecked** - Sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - Sends all the parameters, including the revenue value (if it exists in the event). |



## Attribution link tab

In this tab, you can create the attribution links you want to send to Mobusi for attributing Mobusi's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to perform thorough drill-down analyses later. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Mobusi.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Mobusi campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Mobusi.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise limiting the number of used site IDs and using the subsite ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about[**AppsFlyer Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters)**.**

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Mobusi.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Mobusi to be activated when leads click on a corresponding ad.

## Cost tab

Cost integration is not available for Mobusi.

## Ad revenue tab

Ad Revenue is not supported by Mobusi.

## Permissions tab

In this tab, you can select the permissions to grant Mobusi, whether the partner acts as an ad network, agency, or both. Note that even if attribution is disabled for Mobusi, the permissions tab is active and you can grant control to Mobusi.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -*only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*****a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).