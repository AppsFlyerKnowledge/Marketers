---
title: Qutoutiao ads campaign configuration
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-04-11T09:26:22Z'
  edited_at: '2026-09-15T10:27:37Z'
  id: 360001390337
  locale: en-us
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360001390337-Qutoutiao-ads-campaign-configuration
---
> **At a glance:** Qutoutiao Ads is an AppsFlyer ad network integrated partner.

## Setting Up Qutoutiao Ads

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

Qutoutiao Ads configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration Tab">

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">here</Anchor>.

### Default Postbacks

<Image alt="mceclip2.png" src="https://files.readme.io/445b39b0d2635e1715f92dc5b55223a67bfe0f46a65276db630fab4f7bbb556a-50900041349777.png" width="601px" />

### In-app events settings

In this section you can map your AppsFlyer events with Qutoutiao Ads via postbacks. 

![mceclip0.png](https://files.readme.io/a4e06079141b7df1495eef96144c72d9cbeef6bc20959bb27dc16535f57ce74a-50900041353233.png)

1. Toggle In-App Event Postbacks to ON
2. Click **Add Event** to add an SDK Event to the list
3. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Qutoutiao Ads side.  <br />Obtain the corresponding Event ID from Qutoutiao Ads and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution Link Tab">

In this tab, you can create the attribution links you want to send to Qutoutiao Ads for attributing Qutoutiao Ads campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Qutoutiao Ads.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Qutoutiao Ads campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific Qutoutiao Ads campaigns.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid <Anchor target="_blank" href="/marketers/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/e4ea7011f1349ebe716bebaf441fc363cb9e8c9d8c59b11c7f785bcbe0503e84-50900041358865.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Qutoutiao Ads.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/docs/set-up-lookback-windows">click lookback window here</Anchor>.

![netease-click-through.png](https://files.readme.io/af41e5f6eeefd2ac94050659c919e86b312e205473a7ca539c8cd6f400930c6e-50900041360145.png)

### Click Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to Qutoutiao Ads to be activated when leads click on a corresponding ad.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost Tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad Revenue Tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions Tab">

In this tab, you can select the permissions to grant Qutoutiao Ads, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for Qutoutiao Ads, the permissions tab is active and you can grant control to Qutoutiao Ads.

![rtb_house-permissions-new.png](https://files.readme.io/5aff8873b61b3685001598c30a1103dbfa5828b42afdcb3a0131d3ee75bf34cb-50900041361937.png)

### Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to setup the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKW6WY2H57T49HJPMF29J8XH=setting-up-qutoutiao-ads h_01HKW6WY2JY25ZMQXA963Z0Q71=integration-tab h_01HKW6WY2J4WMBMSAJEP8GGWYA=activate-partner h_01HKW6WY2JJ52DGPRH5KE6K094=default-postbacks inapp-events-settings=in-app-events-settings h_01HKW6WY2JH1QC5QDMQ4RN67JG=in-app-events-settings h_01HKW6WY2JZ7X4EPZ0C3D4QV7J=attribution-link-tab h_01HKW6WY2J5GF13RV6JBW5QPXP=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW6WY2J5CBA3VCKKK61N7N7=click-through-attribution h_01HKW6WY2JNAZ769AQ64539P8J=click-attribution-link h_01HKW6WY2J30M3DSQZBY327364=cost-tab h_01HKW6WY2J8MAM70BH33PDKRHB=ad-revenue-tab h_01HKW6WY2J6NHVSVZXC60KATFP=permissions-tab h_01HKW6WY2JJF66DWZS5W4Z95E3=ad-network-permissions" />
