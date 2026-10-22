---
title: Meiyou Ads campaign configuration
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - China
    - meiyou
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-01T03:26:18Z'
  edited_at: '2026-09-15T10:30:43Z'
  id: 360002141597
  locale: en-us
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360002141597-Meiyou-Ads-campaign-configuration
---
> **At a glance:** Meiyou Ads is an AppsFlyer ad network integrated partner.

## Setting Up Meiyou Ads

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

Meiyou Ads configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration Tab">

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">here</Anchor>.

### General settings

Meiyou Ads connects with AppsFlyer via a unique **Key**. If you don't already have the Key, you must obtain it from Meiyou Ads to continue with the integration.

![mceclip3.png](https://files.readme.io/451f74c0a6b45926f89a3f2a5d04b6ef240184c4862b576bee0d0a2b7a832f30-50900150950417.png)

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from Meiyou Ads. The view-through lookback slider is available on the attribution link tab (described below).

### Default Postbacks

<Image alt="mceclip2.png" src="https://files.readme.io/b416ec9bd2d01f627fd34972234affae668cefd03a31e6df4ace616a1a1137a3-50900150954001.png" width="548px" />

### In-app events settings

In this section you can map your AppsFlyer events with Meiyou Ads via postbacks.

**Key**

Meiyou Ads connects with AppsFlyer via a unique Key. If you don't already have the Key, you must obtain it from Meiyou Ads to continue with the integration.

<Image alt="mceclip1.png" src="https://files.readme.io/32b1c68531c7aa752514f9b1c13c4438cddef2e93d2ca04ab287d46acecda15e-50900150956305.png" width="661px" />

1. Set the Meiyou Ads Key here
2. Toggle In-App Event Postbacks to ON
3. Click **Add Event** to add an SDK Event to the list
4. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Meiyou Ads side.  <br />Obtain the corresponding Event ID from Meiyou Ads and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution Link Tab">

In this tab, you can create the attribution links you want to send to Meiyou Ads for attributing Meiyou Ads campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

![mceclip2.png](https://files.readme.io/3a9b086aa1a76dc64289a512eec56885d108dce5c2778580fc0b2962f00c8a95-50900150957201.png)

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Meiyou Ads.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Meiyou Ads campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific Meiyou Ads campaigns.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid <Anchor target="_blank" href="/marketers/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/35882c82ab722ed52ab93542dc07d79e0e9ff58a14dad692405bc431b082f28c-50900198462481.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Meiyou Ads.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/docs/set-up-lookback-windows">click lookback window here</Anchor>.

![netease-click-through.png](https://files.readme.io/4686c36edcb524d9ca7f8f6c995f3d0447455f150d22308aee6650cee85ecd6e-50900150960017.png)

### Click Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to Meiyou Ads to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to Meiyou Ads, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the <Anchor target="_blank" href="/marketers/docs/set-up-lookback-windows">view-through attribution here</Anchor>.

[![](https://files.readme.io/bb595db7be55acee05af3d25264263c66986ea066a3d5eb40f07dd3735a54532-50900198466577.png)](https://files.readme.io/bb595db7be55acee05af3d25264263c66986ea066a3d5eb40f07dd3735a54532-50900198466577.png)

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to Meiyou Ads to be activated when a corresponding ad is watched, usually for 1 second or more.


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

In this tab, you can select the permissions to grant Meiyou Ads, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for Meiyou Ads, the permissions tab is active and you can grant control to Meiyou Ads.

![rtb_house-permissions-new.png](https://files.readme.io/01af9850fcb765e33303b6d1a3c792aa459e71dea907d418fcbd60d93135b8c5-50900198468113.png)

### Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to setup the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKW6VQGVGFA45SQK1KANQ10Q=setting-up-meiyou-ads h_01HKW6VQGV71MM2T401TGHEMHA=integration-tab h_01HKW6VQGV3HG1ZTR41BD43ZTC=activate-partner h_01HKW6VQGVNG13KARWZBSD59KX=general-settings h_01HKW6VQGV32R49RCEKCYK1G18=default-postbacks inapp-events-settings=in-app-events-settings h_01HKW6VQGVHCVWR4KDHTH24D17=in-app-events-settings h_01HKW6VQGVV9X64XHW48VGW6E6=attribution-link-tab h_01HKW6VQGVZJ36JVCZ3SW7Z3YD=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW6VQGWZQQZWT476QT496YF=click-through-attribution h_01HKW6VQGWG7BH11EK5HQACKVY=click-attribution-link viewthrough-attribution-lookback-window=view-through-attribution-lookback-window h_01HKW6VQGWFJEJYD9KG8BH9EX0=view-through-attribution-lookback-window h_01HKW6VQGWXCB2W13TM4WAGWE1=impressions-attribution-link h_01HKW6VQGWY3AFFTN0DP8BCV7S=cost-tab h_01HKW6VQGWARB4409DWKVDY45W=ad-revenue-tab h_01HKW6VQGW20F6TTCBPGDH57JW=permissions-tab h_01HKW6VQGWXBME473RXA5K1217=ad-network-permissions" />
