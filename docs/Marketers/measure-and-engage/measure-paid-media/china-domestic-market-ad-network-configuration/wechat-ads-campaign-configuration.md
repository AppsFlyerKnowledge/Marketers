---
title: "WeChat Ads campaign configuration"
excerpt: "Learn how to configure and measure your WeChat advertising campaigns using AppsFlyer."
---
**At a glance:** Learn how to measure your campaigns with WeChat on AppsFlyer.

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

![wechat-configuration.png](https://files.readme.io/2324f9735242ac12930db514627cc1b5ec8f48ae3e66ae3fcd467e2d5b22432f-360003067997.png)

Once you have entered this info, confirm it by clicking the highlighted button. In the next step, you receive the *encrypt \_key* and the *sign\_key*:

![wechat-keys.png](https://files.readme.io/2c4602b8dba26bc399228133dfa2bdaa70fec0af5b4d38b4e4b6881f11b52f3e-360003156558.png)

Copy the keys and use them when you configure the campaign on AppsFlyer.

### Setting up wechat campaign as an agency

Agencies have different account types on WeChat. Depending on the account type, some agencies can and some cannot create conversion targets.

If your account allows you to create a conversion target, you can proceed following the instructions above.

If you’re not allowed to create a conversion target, you can see on WeChat a target created by another account that manages the same app. In this case, ask the advertiser to provide you with the *encrypt \_key* and the *sign\_key* and use them to configure the campaign on AppsFlyer.

## Setting up wechat on AppsFlyer

The setup is done from the **Active Integrations** page, but to find new partners you must first go to the [marketplace](/docs/partner-integrations).

> 📘 **Note**
>
> Before setting up an integration, make sure you [contact the partner](/docs/partner-integrations#contact-details) and open an account with them.


**To activate the integration:**

1. In AppsFlyer, from the side menu, select**Collaborate**> **Partner Marketplace**.
2. Search for the partner and select it.
3. Click **Set up integration**. You’re directed to the integration setup page.
4. In the **Integration** tab, turn on **Activate partner**.  
   **Note:** The toggle must stay on ([activated](/docs/partner-activation-deactivation)) for as long as you work with the partner.
5. Complete the configuration using the relevant tabs, as described below.

WeChat's configuration window includes 4 tabs: Integration, Attribution link, Data enrichment and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

> 📘 **Tip**
>
> * The [General Settings](/docs/set-up-an-integrated-partner#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**


## Integration tab

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

![wechat-integration-general-settings.png](https://files.readme.io/dd42aa487d65300a222f7d3ae3258a6a08a9de7849e3122dd14562f54d444523-360002069485.png)

### Default postbacks

AppsFlyer can send automatic postbacks to WeChat following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

![wechat-default-postbacks.png](https://files.readme.io/6828f26f84b6a83a9e8ca89637f0b2e2495980553664889b2fa39d994b04a5e9-360002069505.png)

Select **Only events** **attributed to this partner** for events coming only from users attributed to Wechat.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to WeChat.

### In-app events settings

In this section you can map your AppsFlyer events with WeChat via postbacks.

![wechat_in_app_event_postbacks.png](https://files.readme.io/6507e3ab34a6ae7953c876315847c8e60a14b7dde530e02f8e35577e4f4b2f93-360002683537.png)

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



## Attribution link tab

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

![attribution-link-parameters.png](https://files.readme.io/bfbd4543d46c65999b8930497775c89e26e1c36d82a74cf822003d1d4d4ed90b-360002968938.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about **[AppsFlyer's Attribution Link Structure and Parameters](/docs/about-link-structure-and-parameters).**

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to WeChat.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

[![](https://support.appsflyer.com/hc/article_attachments/360002069525)](https://support.appsflyer.com/hc/article_attachments/360002069525)

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to WeChat to be activated when leads click on a corresponding ad.

## Cost tab

Enable Tencent cost integration to receive cost data for WeChat.

## Ad revenue tab

Ad revenue integration is not available for this partner.

## Permissions tab

No permission configuration available for this partner.