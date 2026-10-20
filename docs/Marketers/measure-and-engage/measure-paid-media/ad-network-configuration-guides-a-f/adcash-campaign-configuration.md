---
title: Adcash campaign configuration
excerpt: >-
  Adcash, an AppsFlyer ad network integrated partner, is a worldwide advertising
  platform providing a fully programmable self-service demand-side platform.
metadata:
  keywords:
    - Advertisers
    - Adcash
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-11-06T08:15:21Z'
  edited_at: '2026-07-23T13:13:54Z'
  id: 216519003
  locale: en-us
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/216519003-Adcash-campaign-configuration
---
## Setting up Adcash

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

Adcash's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

> 📘 **Tip**
>
> * The [General Settings](/docs/set-up-an-integrated-partner#d-general-settings) step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partner

On the **first visit** here, you will need to turn on **Activate Partner** to enable setup of the integration tab parameters. The toggle must be on for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

### General settings

To enable the integration with Adcash, enter your **Goal ID (Adcash)** credentials. Note that the ID cannot include any symbols or spaces.

### Default postbacks

Default postbacks for installs are sent to Adcash if they were attributed to Adcash—meaning, the user who performed it came from Adcash.

### In-app events settings

In this section, you can map your AppsFlyer events with Adcash via postbacks.

1. Toggle In-App Event Postbacks to ON
2. Click **Add Event** to add an SDK Event to the list
3. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server-to-server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Adcash's side.  <br />Obtain the corresponding Event ID from Adcash and set it in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Adcash for attributing Adcash's campaigns, ad sets, or single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Adcash.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Adcash campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad names to compare different creatives within specific ad sets within specific campaigns Adcash.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about[**AppsFlyer Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters).

**Attribution link parameter:** af\_reengagement\_window

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Adcash.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Adcash to be activated when leads click on a corresponding ad.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is not supported by Adcash.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported by Adcash.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Adcash. Note that even if attribution is disabled for Adcash, the permissions tab is active and you can grant control to Adcash.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to set up in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -*only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).

</Accordion>

<div data-zendesk-anchors="h_01HJR5XJE7Q9RNPPF86QX7RBZM=setting-up-adcash h_01HJR5XJE7T4ECXFCG58T9Q856=tip h_01HJR5XJE7AR07Y75GBM6JRXBT=integration-tab h_01HJR5XJE7AHST79EBMKXQ2B62=activate-partner h_01HJR5XJE7ZCWWKD8PE6192JXF=general-settings h_01HJR5XJE76R9VRV34QFMAEVCB=default-postbacks inapp-events-settings=in-app-events-settings h_01HJR5XJE7VZ1KC0MJJMWC87S2=in-app-events-settings h_01HJR5XJE7HGJ190GEEYCF61YQ=attribution-link-tab h_01HJR5XJE74T0HF0KVQNF6D3NR=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HJR5XJE72JNRGC4SHV32CYM1=click-through-attribution h_01HJR5XJE8J29TB6GQMEKYHCPF=click-attribution-link h_01HJR5XJE88YGHBF3FC73EMTEB=cost-tab h_01HJR5XJE8R0BP3EVJ50W9MV1Y=ad-revenue-tab h_01HJR5XJE8ZQ6X5KYYWGGM8VKH=permissions-tab h_01HJR5XJE8B4W3E3SAT89YQVR3=ad-network-permissions" />
