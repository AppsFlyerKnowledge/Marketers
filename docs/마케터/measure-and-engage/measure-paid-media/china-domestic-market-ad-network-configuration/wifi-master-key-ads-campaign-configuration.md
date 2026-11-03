---
title: WiFi Master Key Ads campaign configuration
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
  created_at: '2019-07-05T09:27:19Z'
  edited_at: '2026-10-13T01:19:19Z'
  id: 360001954137
  locale: ko
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ko/articles/360001954137
---
> **At a glance:** WiFi Master Key Ads is an AppsFlyer ad network integrated partner.

## Setting Up WiFi Master Key Ads

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

WiFi Master Key Ads configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration Tab">

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">here</Anchor>.

### General settings

**clientid and secretkey**

WiFi Master Key Ads connects with AppsFlyer via a unique clientid and secretkey. If you don't already have the clientid and secretkey, you must obtain it from WiFi Master Key Ads to continue with the integration.

<Image alt="mceclip2.png" src="https://files.readme.io/8b486a98e25837a0d64e0a27e9b3aa7b66b426e8bad3fbae07b7436b91351db5-50900288875153.png" width="406px" />

### Default Postbacks

<Image alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="509px" />

### In-app events settings

In this section you can map your AppsFlyer events with WiFi Master Key Ads via postbacks.

**clientid and secretkey**

WiFi Master Key Ads connects with AppsFlyer via a unique clientid and secretkey. If you don't already have the clientid and secretkey, you must obtain it from WiFi Master Key Ads to continue with the integration.

![mceclip3.png](https://files.readme.io/035ce248d6876cf31870abc49e949fc887f6bef08efd6e132e43b8c74e3aaf45-50900269524881.png)

1. Set the WiFi Master Key Ads clientid and secretkey here
2. Toggle In-App Event Postbacks to ON
3. Click **Add Event** to add an SDK Event to the list
4. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on WiFi Master Key Ads side.  <br />Obtain the corresponding Event ID from WiFi Master Key Ads and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution Link Tab">

In this tab, you can create the attribution links you want to send to WiFi Master Key Ads for attributing WiFi Master Key Ads campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with WiFi Master Key Ads.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific WiFi Master Key Ads campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific WiFi Master Key Ads campaigns.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid <Anchor target="_blank" href="/marketers/ko/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to WiFi Master Key Ads.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">click lookback window here</Anchor>.

![netease-click-through.png](https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png)

### Click Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to WiFi Master Key Ads to be activated when leads click on a corresponding ad.

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

In this tab, you can select the permissions to grant WiFi Master Key Ads, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for WiFi Master Key Ads, the permissions tab is active and you can grant control to WiFi Master Key Ads.

![rtb_house-permissions-new.png](https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png)

### Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to setup the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKW6Z9DPAYATXWJR4GZMD0KM=setting-up-wifi-master-key-ads h_01HKW6Z9DPYGREGB9VHJJQP6FS=integration-tab h_01HKW6Z9DP6WQD968EQS8G0SZY=activate-partner h_01HKW6Z9DQ3K3RTCT7CMT67WCX=general-settings h_01HKW6Z9DQ26D258602BC43T9B=default-postbacks inapp-events-settings=in-app-events-settings h_01HKW6Z9DQ1XMVERFP97HQ7HM7=in-app-events-settings h_01HKW6Z9DQ0GEE118QKXRA335C=attribution-link-tab h_01HKW6Z9DQ8YMNT6W2B8NEV520=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW6Z9DQ9D2F75XWZRM0JAQM=click-through-attribution h_01HKW6Z9DQQE4QP37994K8HMCQ=click-attribution-link h_01HKW6Z9DQJ6F8Z074H9JG97EC=cost-tab h_01HKW6Z9DQ6GW0S9KDG0RFK1BX=ad-revenue-tab h_01HKW6Z9DQ3Y12DV461NHST3FT=permissions-tab h_01HKW6Z9DQZ8TBA8DK6NJNQT4F=ad-network-permissions" />
