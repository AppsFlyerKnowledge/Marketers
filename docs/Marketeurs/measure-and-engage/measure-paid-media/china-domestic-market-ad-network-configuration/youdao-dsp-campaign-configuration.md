---
title: Youdao DSP campaign configuration
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - youdao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-07-30T09:13:02Z'
  edited_at: '2026-09-15T10:32:12Z'
  id: 360002133558
  locale: en-us
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360002133558-Youdao-DSP-campaign-configuration
---
> **At a glance:** Youdao DSP is an AppsFlyer ad network integrated partner.

## Setting Up Youdao DSP

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

Youdao DSP's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration Tab">

The integration with Youdao DSP only supports the install event in the default postback.

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">here</Anchor>.

### Default Postbacks

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/8e104f89182a421579a067a4904a0d6ddc7ae4fbae7da6a9a8e0c800ccc42e99-50900269840529.png" width="583px" />

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution Link Tab">

In this tab, you can create the attribution links you want to send to Youdao DSP for attributing Youdao DSP's campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Youdao DSP.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Youdao DSP campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Youdao DSP.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid <Anchor target="_blank" href="/marketers/fr/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image align="center" alt="attribution-link-parameters.png" src="https://files.readme.io/132e20e29758b2865ee315e2b185c0689622f2b9e0a01c223253a83bf9ad6ceb-50900241322385.png" width="511px" />

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Youdao DSP.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">click lookback window here</Anchor>.

<Image align="center" alt="netease-click-through.png" src="https://files.readme.io/6b45720763d086c8e2bfc18b7551eabf66b9ec06a7d93d051fa7b3bd67acad07-50900241323025.png" />

### Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to Youdao DSP to be activated when leads click on a corresponding ad.

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

In this tab, you can select the permissions to grant Youdao DSP, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for Youdao DSP, the permissions tab is active and you can grant control to Youdao DSP.

<Image align="center" alt="rtb_house-permissions-new.png" src="https://files.readme.io/0bad858445c3ecf36204fa24c35f532fb47949cda104ed4535444736962cb1ab-50900269845649.png" />

### Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to setup the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKW6ZN60XK9DSCEVQ216P1G9=setting-up-youdao-dsp h_01HKW6ZN60TAMV09SSD8JM29GS=integration-tab h_01HKW6ZN60PGGR7RDWKP5S2HJ9=activate-partner h_01HKW6ZN61B4KY1BEA76MYX4BC=default-postbacks h_01HKW6ZN61WPTBRKNTG3BXHYRP=attribution-link-tab h_01HKW6ZN6172ASA82J51CM13NW=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW6ZN614J1A71A9B38QRN7E=click-through-attribution h_01HKW6ZN61EZP9ES6GK09C68DH=attribution-link h_01HKW6ZN61AWQFR8VD489ZEC6J=cost-tab h_01HKW6ZN68J89ZY3QCJZARYSTP=ad-revenue-tab h_01HKW6ZN68EQS2MB9MK7TV7TB1=permissions-tab h_01HKW6ZN68HZECRSMR3GPTAG4R=ad-network-permissions" />
