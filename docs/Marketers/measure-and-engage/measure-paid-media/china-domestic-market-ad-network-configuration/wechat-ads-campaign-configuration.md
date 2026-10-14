---
title: "WeChat Ads campaign configuration"
excerpt: "Learn how to measure your campaigns with WeChat on AppsFlyer."
x-zendesk:
  id: 115003044106
  url: https://support.appsflyer.com/hc/en-us/articles/115003044106-WeChat-Ads-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: China domestic market ad network configuration
  section_id: 6552066355601
  position: 38
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Wechat Ads, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2017-06-18T06:41:29Z'
  edited_at: '2026-09-15T10:36:12Z'
---
## Introduction

WeChat, one of AppsFlyer's integrated partners, is a Chinese multi-purpose messaging, social media and mobile payment app developed by Tencent.

To configure your campaigns with WeChat, follow the steps below.

## Setting up your campaign on WeChat

Before you proceed with WeChat integration on AppsFlyer, configure the campaign on WeChat.

On WeChat, do the following:

1. Fill in and verify Tencent key
2. Choose the conversion type from the list:

   * Install
   * Register
   * Purchase
   * Add to cart

   Please note that WeChat allows only one conversion target per app.
3. Enter AppsFlyer’s [click attribution URL](#attribution-link-tab)

![wechat-configuration.png](https://files.readme.io/228ee10ef3dc113ae8af8de0f283b144206db1857f6d1f9169355f294155b8f8-50900431174033.png)

Once you have entered this info, confirm it by clicking the highlighted button. In the next step, you receive the *encrypt \_key* and the *sign\_key*:

![wechat-keys.png](https://files.readme.io/cd7a2406ae9981eaabb4089813c9a1b847f0e6f750b9c0c0a0ac5e726dfe44be-50900431177361.png)

Copy the keys and use them when you configure the campaign on AppsFlyer.

### Setting up wechat campaign as an agency

Agencies have different account types on WeChat. Depending on the account type, some agencies can and some cannot create conversion targets.

If your account allows you to create a conversion target, you can proceed following the instructions above.

If you’re not allowed to create a conversion target, you can see on WeChat a target created by another account that manages the same app. In this case, ask the advertiser to provide you with the *encrypt \_key* and the *sign\_key* and use them to configure the campaign on AppsFlyer.

## Setting up wechat on AppsFlyer

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

WeChat's configuration window includes 4 tabs: Integration, Attribution link, Data enrichment and Permissions. Click on the items below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

> 📘 **Note**
>
> As an ALL-Installs network, Wechat prefers to receive postbacks for all new installs of your app from ANY source, including organic. It is recommended to select **Events attributed to any partner** to send all install postbacks to WeChat.

### General settings

**Partner ID**

Wechat connects with AppsFlyer via three unique parameters:

1. Sign ID
2. WeChat App ID
3. Encrypt Key

If you don't already have the Sign ID, WeChat App ID and Encrypt Key you must obtain it from WeChat to continue with the integration.

![wechat-integration-general-settings.png](https://files.readme.io/f1e0675a26116b628629b07616a7b9b86e8413ee36d7504f415207cb1590cb82-50900431178001.png)

### Default postbacks

AppsFlyer can send automatic postbacks to WeChat following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

![wechat-default-postbacks.png](https://files.readme.io/1a2703b97a71bf82bcc77f5393459bc94b5443b83a4c4965d2624eda0e9f166f-50900402778129.png)

Select **Only events** **attributed to this partner** for events coming only from users attributed to Wechat.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to WeChat.

### In-app events settings

In this section you can map your AppsFlyer events with WeChat via postbacks.

![wechat_in_app_event_postbacks.png](https://files.readme.io/cd6234df4809b27044e361ad8835d4ae92100c491e0aa7c8f003336cdf2ad49d-50900431180561.png)

1. Enter the Encrypt Key again.
2. Enter the Sign ID
3. Enter the WeChat App ID
4. Toggle In-App Event Postbacks to ON
5. Select the Sending Option for all SDK defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
6. Click **Add Event** to add an SDK Event to the list
7. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on WeChat's side.  <br />Obtain the corresponding Event ID from Wechat and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to WeChat for attributing WeChat's campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with WeChat.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific WeChat campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns WeChat.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/28112ce5f9706ffc07d69b233f2b6b4756fda36cb4e8438ab6c9cd03e3a39c59-50900431181841.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about[**AppsFlyer's Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters).

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to WeChat.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

[![](https://files.readme.io/86114a765dea30da658a676d1a7506c6ba385bdf8ebcf7241a1ce85f8c413077-50900402782737.png)](https://files.readme.io/86114a765dea30da658a676d1a7506c6ba385bdf8ebcf7241a1ce85f8c413077-50900402782737.png)

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to WeChat to be activated when leads click on a corresponding ad.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Enable Tencent cost integration to receive cost data for WeChat.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue integration is not available for this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

No permission configuration available for this partner.

</Accordion>

<div data-zendesk-anchors="h_01HKW6Z36NGCWC0R6EQX49S34J=introduction h_01HKW6Z36NTSGCDQM553YMHHDH=setting-up-your-campaign-on-wechat h_01HKW6Z36N8S8KSBNMR8A54RRN=setting-up-wechat-campaign-as-an-agency h_01HKW6Z36N3JSYEWJZH74M5WWJ=setting-up-wechat-on-appsflyer h_01HKW6Z36PDGTT3EERY8F4VA79=integration-tab h_01HKW6Z36P0EQF829NW3GDXKEN=activate-partner h_01HKW6Z36P806MHV6N3D1N9HW3=note h_01HKW6Z36P51EG4BW7WA3JGSKN=general-settings h_01HKW6Z36P3D4EPKC6ZZK94YVF=default-postbacks inapp-events-settings=in-app-events-settings h_01HKW6Z36PA90WEJMFH7BZMD72=in-app-events-settings h_01HKW6Z36PRBT2X6F5BHYW06E1=attribution-link-tab h_01HKW6Z36P73H79MVFXQ29K2M6=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW6Z36P95C7CT1J6YS5CQN8=click-through-attribution h_01HKW6Z36PEAPM8RAKB0RM9RES=click-attribution-link h_01HKW6Z36PEG0T9WQQRNY19EVG=cost-tab h_01HKW6Z36WE1SDC7KZHCMTPA0T=ad-revenue-tab h_01HKW6Z36W6QKR583X4Q4BNBZ4=permissions-tab" />
