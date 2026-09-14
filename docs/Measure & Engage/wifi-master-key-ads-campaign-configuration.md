---
title: "WiFi Master Key Ads campaign configuration"
excerpt: "Learn how to configure and activate the WiFi Master Key Ads integration in AppsFlyer, including setting up postbacks, attribution links, and permissions."
---
At a glance: WiFi Master Key Ads is an AppsFlyer ad network integrated partner.

## Setting Up WiFi Master Key Ads

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

WiFi Master Key Ads configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](https://support.appsflyer.com/hc/articles/4410395957521#about-the-integrated-partner-page).

> 👍 Tip
>
> - The [General Settings](https://support.appsflyer.com/hc/articles/4410395957521#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> - All the rest of the steps are either descriptive or **optional**

## **Integration Tab**

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the _**Activate Partner**_ button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

### General settings

**clientid and secretkey**

WiFi Master Key Ads connects with AppsFlyer via a unique clientid and secretkey. If you don't already have the clientid and secretkey, you must obtain it from WiFi Master Key Ads to continue with the integration.

<Image src="https://files.readme.io/0cf16d517e6df0089e9ce6d742ed68b66b2c0dceff656d21c2719355d5e22033-360003355597.png" alt="mceclip2.png" />

### Default Postbacks

<Image src="https://files.readme.io/8f4e31507914f121b0622476c05edbab69948e5174d9fa87c8e890afea96a482-21594071343889.png" alt="mceclip2.png" />

### In-app events settings

In this section you can map your AppsFlyer events with WiFi Master Key Ads via postbacks.

**clientid and secretkey**

WiFi Master Key Ads connects with AppsFlyer via a unique clientid and secretkey. If you don't already have the clientid and secretkey, you must obtain it from WiFi Master Key Ads to continue with the integration.

<Image src="https://files.readme.io/749be186e563f6138ad21e674f4e0cfa74944f49d959621a8cd4a23b437cf196-360003355617.png" alt="mceclip3.png" />

1. Set the WiFi Master Key Ads clientid and secretkey here
2. Toggle In-App Event Postbacks to ON
3. Click **Add Event** to add an SDK Event to the list
4. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.<br>**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on WiFi Master Key Ads side.<br>Obtain the corresponding Event ID from WiFi Master Key Ads and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af_revenue** parameter.<br>**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

## Attribution Link Tab

In this tab, you can create the attribution links you want to send to WiFi Master Key Ads for attributing WiFi Master Key Ads campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with WiFi Master Key Ads.

**Attribution link parameter:** c
- **Adset** - set ad set names to compare different ad sets within specific WiFi Master Key Ads campaigns.

**Attribution link parameter:** af_adset
- **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific WiFi Master Key Ads campaigns.

**Attribution link parameter:** af_ad
- **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](https://support.appsflyer.com/hc/articles/115005099063-What-are-the-Exceeded-Media-Sources-#exceeded_siteid_limit) limitations.

**Attribution link parameters:** af_siteid and af_sub_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

**Attribution link parameters:** af_sub1, af_sub2, af_sub3, af_sub4, af_sub5

<Image src="https://files.readme.io/5064601618d15b208ba22a63c8825863c48067e221a5ba42bc92bc57dc043885-21594046837393.png" alt="attribution-link-parameters.png" />

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about **[AppsFlyer's Attribution Link Structure and Parameters](https://support.appsflyer.com/hc/articles/207447163).**

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to WiFi Master Key Ads.

**Attribution link parameter:** af_click_lookback

More details about the [click lookback window here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

<Image src="https://files.readme.io/35a8d0c32d7bcad3bb191114a9fee096838e38ceb89fc24a5dedede23480b18a-21594046847505.png" alt="netease-click-through.png" />

### Click Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to WiFi Master Key Ads to be activated when leads click on a corresponding ad.

## Cost Tab

Cost data is not supported in the integration with this partner.

## Ad Revenue Tab

Ad Revenue is not supported in the integration with this partner.

## Permissions Tab

In this tab, you can select the permissions to grant WiFi Master Key Ads, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for WiFi Master Key Ads, the permissions tab is active and you can grant control to WiFi Master Key Ads.

<Image src="https://files.readme.io/64ce1f8648952fce055f7eba21b4d43d471681b9ed3ab20d1fd03ac7d592a020-21594071383441.png" alt="rtb_house-permissions-new.png" />

### Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

- _**Allow to configure integration**_ - permit the partner to setup the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).