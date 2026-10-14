---
title: "Baidu App Ads campaign configuration"
excerpt: "Baidu App Ads (Baitong), an AppsFlyer ad network integrated partners, is one of the biggest App promotion and distribution platforms in the China domestic market, integrating the mobile traffic of App Stores (Baidu Mobile Assistant, Android Market, 91 Mobile Assistant, etc.), Baidu Mobile Search, Super App, and Baidu Affiliates."
x-zendesk:
  id: 115003044146
  url: https://support.appsflyer.com/hc/en-us/articles/115003044146-Baidu-App-Ads-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: China domestic market ad network configuration
  section_id: 6552066355601
  position: 35
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Baidu App Ads, Baidu, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2017-06-18T07:40:30Z'
  edited_at: '2026-09-15T10:37:14Z'
---
## Setting Up Baidu App Ads (Baitong)

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

Baidu App Ads configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you must toggle ON the ***Activate Partner*** button to enable the setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

### Default postbacks

AppsFlyer can send automatic postbacks to Baidu App Ads (Baitong) following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

The Integration with Baidu Baitong Ads supports only the install event for Default Postbacks.

![baidu-baitong-default-postback.png](https://files.readme.io/c464429db3eae2dac9fbc13df1a56090ef587cd386ed8214eabd21dac653a622-50900467293713.png)

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Baidu App Ads (Baitong) for attributing Baidu App Ads (Baitong) campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Baidu App Ads（Baitong).  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Baidu App Ads（Baitong) campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Baidu App Ads（Baitong).  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information, see[**AppsFlyer Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters).

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window can be attributed to Baidu App Ads（Baitong).

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Baidu App Ads（Baitong) to be activated when leads click on a corresponding ad.

Cost tab

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

In this tab, you can select the permissions to grant RTB House, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for RTB House, the permissions tab is active and you can grant control to RTB House.

### Ad network permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -*only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).

</Accordion>

<div data-zendesk-anchors="h_01HKW6SB83X3G0CV5A8SNB6DSJ=setting-up-baidu-app-ads-baitong h_01HKW6SB83NPWAQ0HKVJDMSXKR=integration-tab h_01HKW6SB83QKQW6D8F72ENFDB1=activate-partner h_01HKW6SB83XK3V4FT17PK0X5PZ=default-postbacks h_01HKW6SB83G06N2PWR760310XV=attribution-link-tab h_01HKW6SB83VTAYK08P42698YRR=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW6SB83R8X1PWPTWG528HPY=click-through-attribution h_01HKW6SB84ZA8KXN7A7N9PEZ7X=click-attribution-link h_01HKW6SB840JT24A8QTB6Z7N7T=cost-tab h_01HKW6SB84MV2RYRQQVPYMFFJ8=ad-revenue-tab h_01HKW6SB84XA73Y64M3S8D2V58=permissions-tab h_01HKW6SB84Q2NWK0Z3YF7ZQ5QJ=ad-network-permissions" />
