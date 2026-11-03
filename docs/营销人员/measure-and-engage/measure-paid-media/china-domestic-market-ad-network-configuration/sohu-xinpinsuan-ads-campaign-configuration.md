---
title: Sohu XinPinSuan Ads campaign configuration
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
  created_at: '2019-07-05T08:57:46Z'
  edited_at: '2026-10-13T01:18:37Z'
  id: 360001953697
  locale: zh-cn
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/zh-cn/articles/360001953697
---
> **At a glance:** Sohu XinPinSuan Ads is an AppsFlyer ad network integrated partner.

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

Sohu XinPinSuan Ads configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration Tab">

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation#渠道对接的启用方式">here</Anchor>.

### Default Postbacks

<Image alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="520px" />

### In-app events settings

In this section, you can map your AppsFlyer events with AD\_NETWORK via postbacks. 

<Image alt="mceclip0.png" src="https://files.readme.io/74a4c9e81ac69f65079f5e214de90dc8725f8aedaf59c7ee4d9a3d947a853a0b-50899821661713.png" width="611px" />

1. Toggle In-App Event Postbacks to ON
2. Click **Add Event** to add an SDK Event to the list
3. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on AD\_NETWORK's side.  <br />Obtain the corresponding Event ID from AD\_NETWORK and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution Link Tab">

In this tab, you can create the attribution links you want to send to Sohu XinPinSuan Ads for attributing Sohu XinPinSuan Ads campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Sohu XinPinSuan Ads.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Sohu XinPinSuan Ads campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific Sohu XinPinSuan Ads campaigns.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub-site ID parameter, to avoid <Anchor target="_blank" href="/marketers/zh/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Sohu XinPinSuan Ads.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows#回溯窗口">click lookback window here</Anchor>.

![netease-click-through.png](https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png)

### Click Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to Sohu XinPinSuan Ads to be activated when leads click on a corresponding ad.

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

In this tab, you can select the permissions to grant Sohu XinPinSuan Ads, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for Sohu XinPinSuan Ads, the permissions tab is active and you can grant control to Sohu XinPinSuan Ads.

![rtb_house-permissions-new.png](https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png)

### Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to setup the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKW6XEHPM944AN2AZY3GQD77=integration-tab h_01HKW6XEHQFNWXN83X5C5N4HR9=activate-partner h_01HKW6XEHQJEDMSAF5N7MBFZTJ=default-postbacks inapp-events-settings=in-app-events-settings h_01HKW6XEHQB43GJ6CSXG930ZYX=in-app-events-settings h_01HKW6XEHQP53XF1H89ZRDKVTK=attribution-link-tab h_01HKW6XEHQN7KDEZE629D50998=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW6XEHQCCCDMXXAYD7GEYS0=click-through-attribution h_01HKW6XEHQQ6333VSWK2D3JVWF=click-attribution-link h_01HKW6XEHQTJBXHEBY52A1MCWP=cost-tab h_01HKW6XEHQ69P4GY9QMZS9WCQJ=ad-revenue-tab h_01HKW6XEHQD3FS5YQ7EDDNC7QA=permissions-tab h_01HKW6XEHQ4W2Z79GJW45RZ5KN=ad-network-permissions" />
