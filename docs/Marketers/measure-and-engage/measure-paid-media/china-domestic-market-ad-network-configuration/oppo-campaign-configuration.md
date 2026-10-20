---
title: OPPO campaign configuration
excerpt: OPPO is an AppsFlyer ad network integrated partner.
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
  created_at: '2019-08-02T06:46:03Z'
  edited_at: '2026-09-15T10:26:17Z'
  id: 360002159158
  locale: en-us
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360002159158-OPPO-campaign-configuration
---
## Setting Up OPPO

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

OPPO's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration Tab">

The integration with OPPO only supports the install event in the default postback.

### Activate Partner

On the **first visit**, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

### Default Postbacks

![mceclip2.png](https://files.readme.io/d9afb0335626638ad4defb6426e20fbb842ba2a19d96c44987b1209e6f56a4c0-50899981124625.png)

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution Link Tab">

In this tab, you can create the attribution links you want to send to OPPO for attributing OPPO's campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with OPPO.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific OPPO campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific OPPO campaigns.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/59135e2d1d4ff29fcf81c1f0b909dad32702435c6bfea48b7662271f4569d48d-50899981126801.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about[**AppsFlyer's Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters).

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to OPPO.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

![netease-click-through.png](https://files.readme.io/4113f5f4f8d4197a8b0ab376d700f421384da959999ee59b187a70b8648b0632-50900028168337.png)

### Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to OPPO to be activated when leads click on a corresponding ad.

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

In this tab, you can select the permissions to grant OPPO, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for OPPO, the permissions tab is active and you can grant control to OPPO.

![rtb_house-permissions-new.png](https://files.readme.io/1538fb9047917631913e5e8cb316cd9f3a9d8c2f862a1a4e8b847b797690180c-50899981130513.png)

### Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to setup the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).

</Accordion>

<div data-zendesk-anchors="h_01HKW6WR3NKYN9M2J8ZDNYF1ZC=setting-up-oppo h_01HKW6WR3N3RH4GG5AHZ1TTG6V=integration-tab h_01HKW6WR3NJM4XPPJDMPS04JKN=activate-partner h_01HKW6WR3NDWFHVGERDNMS0REC=default-postbacks h_01HKW6WR3NAE4MNHMCPS2W36F2=attribution-link-tab h_01HKW6WR3P6TGT1NDR6DE2JV3B=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW6WR3P0NADPBZ51S4EYJV1=click-through-attribution h_01HKW6WR3P320PGSBHPH0SWQA6=attribution-link h_01HKW6WR3PBTZTWAPD5D7VXXNE=cost-tab h_01HKW6WR3P0299WKGCAM4PJHDR=ad-revenue-tab h_01HKW6WR3P55EE3YNGX8S164CS=permissions-tab h_01HKW6WR3PBC2PZ87RP91RQCFG=ad-network-permissions" />
