---
title: UC Toutiao Ads campaign configuration
metadata:
  keywords:
    - Advertisers
    - UC Toutiao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-09-25T05:41:49Z'
  edited_at: '2026-09-15T10:39:33Z'
  id: 115004843026
  locale: en-us
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115004843026-UC-Toutiao-Ads-campaign-configuration
---
> **At a glance:** UC Toutiao Ads, an AppsFlyer ad network integrated partner, is one of China's leading news aggregator apps.

## Setting up UC Toutiao

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

UC Toutiao's configuration window includes 2 active tabs: Integration and Attribution link.

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partners

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">here</Anchor>.

### Default Postbacks

By default, UC Toutiao receives postbacks only for new install events attributed to it.

![uc-toutiao-integration.png](https://files.readme.io/1ed78bd49d9a49d134f5c48655765ad205515752d88528a0a453bd3a091492c0-360002074869.png)

### In-app events settings

In this section, you can map your AppsFlyer events with UC Toutiao via postbacks.

[![](https://files.readme.io/ae230875cb4d08e7b58249a9bf61a1fcabe2893b1a338c01bdc57b2043deda55-21594057898769.png)](https://files.readme.io/ae230875cb4d08e7b58249a9bf61a1fcabe2893b1a338c01bdc57b2043deda55-21594057898769.png)

1. Set the UC Toutiao network ID again here
2. Toggle In-App Event Postbacks to ON
3. Select the Sending Option for all SDK defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list
5. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on UC Toutiao's side.  <br />Obtain the corresponding Event ID from UC Toutiao and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to UC Toutiao for attributing UC Toutiao's campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

[![UC_Toutiao_attribution_link_tab.png](https://files.readme.io/d8e96914bb9bc703fc7540cd8abc82b745a96066493240952720c2c82d7d21d0-360002880397.png)](https://files.readme.io/d8e96914bb9bc703fc7540cd8abc82b745a96066493240952720c2c82d7d21d0-360002880397.png)

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with UC Toutiao.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific UC Toutiao campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns UC Toutiao.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid <Anchor target="_blank" href="/marketers/vi/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-params.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to UC Toutiao.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">click lookback window here</Anchor>.

![uc-toutiao-click-through.png](https://files.readme.io/8128e80c365aa223105260a25aa99a61bd9eeccdf19d311804ed3e66b744ef39-360002074929.png)

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to UC Toutiao to be activated when leads click on a corresponding ad.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost integration is not available for this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue integration is not available for this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

No permission configuration is available for this partner.

</Accordion>

## Create conversion at uc toutiao ads

Login to UC Toutiao Ads (<Anchor target="_blank" href="https://e.uc.cn/">https://e.uc.cn/</Anchor>) and go to **Click Promotion Tools** >> **Click Conversion Tools** >> **Create Conversion**

![Toutiao_4.png](https://files.readme.io/40e4c3f26faf2cf928fe874398a7e505d100e717669867fc8a55b8b9fec1f021-115016024743.png)

Enter App related information >> **Click Confirm** >> **Generate 2-dimension code**

Android App:

![Toutiao_5.png](https://files.readme.io/8db1f985882f847aad08e4e46710bd9af8a95b62e0a0b488d5242879cd11b7bd-115015832006.png)

iOS App:

![Toutiao_6.png](https://files.readme.io/18b8ba97b8792db66ec4874269bf1b6ccb21ad68016a57e52534f4e97835cc92-115016025123.png)

Use Alipay App or Dingding App to scan the 2-dimension code to install your App. Finish the conversion test and then this conversion status becomes active.

6. Create Your Ads

Create you ad by going to: **Ad Unit Level** >> **Bid Setting Section** >> **Enable the Conversion**

![Toutiao_7.png](https://files.readme.io/f2c49499432c3c358d737544ea02cb5b1e634244313606a62102707dd8a3c31e-115015832146.png)

<div data-zendesk-anchors="h_01HKW6Y1PVGS22BXK54VW8C488=setting-up-uc-toutiao h_01HKW6Y1PWJEJHCCY5WM8AYNGE=integration-tab h_01HKW6Y1PWX3TMM41S78MJ21C1=activate-partners h_01HKW6Y1PWRZNRX6061KFECTDN=default-postbacks inapp-events-settings=in-app-events-settings h_01HKW6Y1PWRMK1H7QCW1GQWAA7=in-app-events-settings h_01HKW6Y1PW95EWPGP09CCJF97M=attribution-link-tab h_01HKW6Y1PWVTGGNX96AWVZJ9PP=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW6Y1PWEW2FWN8K5S8DKQJJ=click-through-attribution h_01HKW6Y1PWKPJ09G70XMQG8H1S=click-attribution-link h_01HKW6Y1PWFS5X835MYJG0CVJ0=cost-tab h_01HKW6Y1PWJW4EW33MYRDN2FJB=ad-revenue-tab h_01HKW6Y1PWDWN4KWMA1KX5FYDT=permissions-tab h_01HKW6Y1PWVMM70F6MJVCJYKT3=create-conversion-at-uc-toutiao-ads" />
