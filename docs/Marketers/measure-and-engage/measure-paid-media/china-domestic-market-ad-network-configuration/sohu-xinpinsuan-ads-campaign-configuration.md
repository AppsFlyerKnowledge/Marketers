---
title: "Sohu XinPinSuan Ads campaign configuration"
excerpt: "Learn how to configure the integration, attribution links, and permissions for Sohu XinPinSuan Ads in AppsFlyer."
---
Sohu XinPinSuan Ads is an AppsFlyer ad network integrated partner.

The setup is done from the **Active Integrations** page, but to find new partners you must first go to the [marketplace](/docs/partner-integrations).

> 📘 Note
>
> Before setting up an integration, make sure you [contact the partner](/docs/partner-integrations#contact-details) and open an account with them.

**To activate the integration:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Marketplace**.
2. Search for the partner and select it.
3. Click **Set up integration**. You’re directed to the integration setup page.
4. In the **Integration** tab, turn on **Activate partner**.

> 📘 Note
>
> The toggle must stay on ([activated](/docs/partner-activation-deactivation)) for as long as you work with the partner.

5. Complete the configuration using the relevant tabs, as described below.

Sohu XinPinSuan Ads configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

> 👍 Tip
>
> - The [General Settings](/docs/set-up-an-integrated-partner) step in the Integration tab is **mandatory** for all partners
> - All the rest of the steps are either descriptive or **optional**

## Integration Tab

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the _**Activate Partner**_ button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](/docs/partner-activation-deactivation#activating-a-partner).

### Default Postbacks

![mceclip2.png](https://files.readme.io/982f93d803cbda05e35eaf4597b9757911d3b189685f3bbcad9208c89bcce5ef-21594027390609.png)

### In-app events settings

In this section, you can map your AppsFlyer events with AD_NETWORK via postbacks.

![mceclip0.png](https://files.readme.io/3047cbd4520882036dc9615aa48176fa2c7229d47f0a7ad06c56dca9fcac4e2c-360015822338.png)

1. Toggle In-App Event Postbacks to ON
2. Click **Add Event** to add an SDK Event to the list
3. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.<br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on AD_NETWORK's side.<br />Obtain the corresponding Event ID from AD_NETWORK and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af_revenue** parameter.<br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

## Attribution Link Tab

In this tab, you can create the attribution links you want to send to Sohu XinPinSuan Ads for attributing Sohu XinPinSuan Ads campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with Sohu XinPinSuan Ads.

**Attribution link parameter:** c
- **Adset** - set ad set names to compare different ad sets within specific Sohu XinPinSuan Ads campaigns.

**Attribution link parameter:** af_adset
- **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific Sohu XinPinSuan Ads campaigns.

**Attribution link parameter:** af_ad
- **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub-site ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.

**Attribution link parameters:** af_siteid and af_sub_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

**Attribution link parameters:** af_sub1, af_sub2, af_sub3, af_sub4, af_sub5

![attribution-link-parameters.png](https://files.readme.io/6d7acd0799c9d54caa8d9fa0a18424dad47d7ea937cbfae38b24c0523edb76a3-21594056147729.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about **[AppsFlyer's Attribution Link Structure and Parameters](/docs/about-link-structure-and-parameters).**

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Sohu XinPinSuan Ads.

**Attribution link parameter:** af_click_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows#lookback-windows).

![netease-click-through.png](https://files.readme.io/748d7f68308d51900688de92f85902369bd096868cc148243723a85647708f9c-21594027410705.png)

### Click Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to Sohu XinPinSuan Ads to be activated when leads click on a corresponding ad.

## Cost Tab

Cost data is not supported in the integration with this partner.

## Ad Revenue Tab

Ad Revenue is not supported in the integration with this partner.

## Permissions Tab

In this tab, you can select the permissions to grant Sohu XinPinSuan Ads, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for Sohu XinPinSuan Ads, the permissions tab is active and you can grant control to Sohu XinPinSuan Ads.

![rtb_house-permissions-new.png](https://files.readme.io/43a96177748ee50399c38b0ec63733646e23fb72b962a058acba3b6e7d62bef5-21594056171281.png)

### Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

- _**Allow to configure integration**_ - permit the partner to setup the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).