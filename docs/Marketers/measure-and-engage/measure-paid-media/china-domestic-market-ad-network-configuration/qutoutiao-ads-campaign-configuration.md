---
title: "Qutoutiao ads campaign configuration"
excerpt: "Learn how to configure and activate the Qutoutiao Ads integration in AppsFlyer, including setting up postbacks, attribution links, and partner permissions."
---
Qutoutiao Ads is an AppsFlyer ad network integrated partner. This guide covers how to set up the integration, configure attribution links, and manage permissions. 

## Setting Up Qutoutiao Ads

The setup is done from the **Active Integrations** page, but to find new partners you must first go to the [marketplace](https://support.appsflyer.com/hc/articles/9960361873809).

> 📘 Note
>
> Before setting up an integration, make sure you [contact the partner](https://support.appsflyer.com/hc/articles/9960361873809#contact-details) and open an account with them.

**To activate the integration:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Marketplace**.
2. Search for the partner and select it.
3. Click **Set up integration**. You’re directed to the integration setup page.
4. In the **Integration** tab, turn on **Activate partner**.

> 📘 Note
>
> The toggle must stay on ([activated](https://support.appsflyer.com/hc/articles/360000844778)) for as long as you work with the partner.

5. Complete the configuration using the relevant tabs, as described below.

Qutoutiao Ads configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](https://support.appsflyer.com/hc/articles/4410395957521#about-the-integrated-partner-page).

> 👍 Tip
>
> - The [General Settings](https://support.appsflyer.com/hc/articles/4410395957521#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> - All the rest of the steps are either descriptive or **optional**

## Integration Tab

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the _**Activate Partner**_ button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

### Default Postbacks

![mceclip2.png](https://files.readme.io/3ddb2eedbfe9001e6e1a2a1bc75a0242dd2e020c1e2455554407c107c90bfb4f-21594025732625.png)

### In-app events settings

In this section you can map your AppsFlyer events with Qutoutiao Ads via postbacks.

![mceclip0.png](https://files.readme.io/37f9ac07d4a82f8dd1ff9ddb601cad03b06e0d33eb29af0ca30445f9da0d615e-360015747917.png)

1. Toggle In-App Event Postbacks to ON
2. Click **Add Event** to add an SDK Event to the list
3. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.<br>**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Qutoutiao Ads side.<br>Obtain the corresponding Event ID from Qutoutiao Ads and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.<br>**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

## Attribution Link Tab

In this tab, you can create the attribution links you want to send to Qutoutiao Ads for attributing Qutoutiao Ads campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with Qutoutiao Ads.

**Attribution link parameter:** c
- **Adset** - set ad set names to compare different ad sets within specific Qutoutiao Ads campaigns.

**Attribution link parameter:** af\_adset
- **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific Qutoutiao Ads campaigns.

**Attribution link parameter:** af\_ad
- **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](https://support.appsflyer.com/hc/articles/115005099063-What-are-the-Exceeded-Media-Sources-#exceeded_siteid_limit) limitations.

**Attribution link parameters:** af\_siteid and af\_sub\_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

**Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/7fe37994972f1bf44bf98d6a39fc4f48480ce9f8f555a353be5489a675a432ec-21594020897425.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about **[AppsFlyer's Attribution Link Structure and Parameters](https://support.appsflyer.com/hc/articles/207447163).**

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Qutoutiao Ads.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

![netease-click-through.png](https://files.readme.io/9fc501e8e57ca2e8d8d4a10beff06a6c6b746893a04efc8577ebce6228b5d54e-21594025759505.png)

### Click Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to Qutoutiao Ads to be activated when leads click on a corresponding ad.

## Cost Tab

Cost data is not supported in the integration with this partner.

## Ad Revenue Tab

Ad Revenue is not supported in the integration with this partner.

## Permissions Tab

In this tab, you can select the permissions to grant Qutoutiao Ads, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for Qutoutiao Ads, the permissions tab is active and you can grant control to Qutoutiao Ads.

![rtb_house-permissions-new.png](https://files.readme.io/e3558a40446b8afb960ee8e0eb3ea721a0f9551bbb65c661e11970c0b27c9e9f-21594020921873.png)

### Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

- _**Allow to configure integration**_ - permit the partner to setup the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).