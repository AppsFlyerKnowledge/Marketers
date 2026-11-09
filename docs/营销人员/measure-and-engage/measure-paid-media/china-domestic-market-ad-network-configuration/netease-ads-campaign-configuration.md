---
title: Netease Ads campaign configuration
metadata:
  keywords:
    - netease ads
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-06-18T06:59:42Z'
  edited_at: '2026-10-13T01:18:06Z'
  id: 115003044126
  locale: zh-cn
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/zh-cn/articles/115003044126
---
> **At a glance:** Netease, an AppsFlyer integrated partner, is a leading advertisement service provider in the Chinese market.

## Setting up Netease

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

Netease's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration tab">

The integration with Netease Ads only supports the install event in the default postback.

### Activate partner

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">here</Anchor>.

### Default postbacks

<Image align="center" alt="netease-default-postback.png" src="https://files.readme.io/0b1db2d0f9e772ad7459c8d28d46cf92bb26501da47b9e5f2f3dd4951a469470-50900350199825.png" width="513px" />

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Netease for attributing Netease's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Netease.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Netease campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Netease.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid <Anchor target="_blank" href="/marketers/zh/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image align="center" alt="attribution-link-parameters.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" />

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">**AppsFlyer Attribution Link Structure and Parameters**</Anchor>.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Netease.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">click lookback window here</Anchor>.

<Image align="center" alt="netease-click-through.png" src="https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png" />

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Netease to be activated when leads click on a corresponding ad.

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

In this tab, you can select the permissions to grant RTB House, whether the partner acts as an ad network, agency, or both. Note that even if attribution is disabled for RTB House, the permissions tab is active and you can grant control to RTB House.

<Image align="center" alt="rtb_house-permissions-new.png" src="https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png" />

### Ad network permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKW6VWQKD2K6REG5MN6274MD=setting-up-netease h_01HKW6VWQKNZ067ASNH3W5MK2H=integration-tab h_01HKW6VWQKVN9NKJ67HEJXRBZJ=activate-partner h_01HKW6VWQKJGFGER02BFXNV88C=default-postbacks h_01HKW6VWQKK3P5TE72MQRV0TPA=attribution-link-tab h_01HKW6VWQKEB8DK5YN4E976SQV=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW6VWQKNNE4Y46QWR8VZHP0=click-through-attribution h_01HKW6VWQKSW8NYCK7VCQ2PRHW=click-attribution-link h_01HKW6VWQKBRWE8RHFTPF9JADE=cost-tab h_01HKW6VWQMJFES084XN3Z52GC2=ad-revenue-tab h_01HKW6VWQMJ419903HKE1C0GRD=permissions-tab h_01HKW6VWQMDR1K426AVZ25Z7VH=ad-network-permissions" />
