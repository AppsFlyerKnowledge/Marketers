---
title: "OPPO campaign configuration"
excerpt: "Learn how to configure the OPPO integration in AppsFlyer, including setting up attribution links, default postbacks, and partner permissions."
---
At a glance: OPPO is an AppsFlyer ad network integrated partner.

## Setting Up OPPO

The setup is done from the **Active Integrations** page, but to find new partners you must first go to the [marketplace](https://support.appsflyer.com/hc/articles/9960361873809).

> 📘 Note
>
> Before setting up an integration, make sure you [contact the partner](https://support.appsflyer.com/hc/articles/9960361873809#contact-details) and open an account with them.

**To activate the integration:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Marketplace**.
2. Search for the partner and select it.
3. Click **Set up integration**.
4. Select the app for the integration. You’re directed to the integration setup page.
5. In the **Integration** tab, turn **Activate partner** on.

OPPO's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](https://support.appsflyer.com/hc/articles/4410395957521#about-the-integrated-partner-page).

> 👍 Tip
>
> - The [General Settings](https://support.appsflyer.com/hc/articles/4410395957521#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> - All the rest of the steps are either descriptive or **optional**

## Integration Tab

The integration with OPPO only supports the install event in the default postback.

### Activate Partner

On the **first visit**, you will need to toggle below. ON the _**Activate Partner**_ button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

### Default Postbacks

![mceclip2.png](https://files.readme.io/e68ee3bfc98b5cce3f181417b7b91b79229b69f2588d29209b500a2a54f51412-21594025098129.png)

## Attribution Link Tab

In this tab, you can create the attribution links you want to send to OPPO for attributing OPPO's campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with OPPO.

**Attribution link parameter:** c
- **Adset** - set ad set names to compare different ad sets within specific OPPO campaigns.

**Attribution link parameter:** af\_adset
- **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific OPPO campaigns.

**Attribution link parameter:** af\_ad
- **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](https://support.appsflyer.com/hc/articles/115005099063-What-are-the-Exceeded-Media-Sources-#exceeded_siteid_limit) limitations.

**Attribution link parameters:** af\_siteid and af\_sub\_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

**Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/b8b4eadc83bf84ebcd6082e1bfd2b9e15c31dfe4fe86a130b71742190d6dbc1f-21594025114001.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about **[AppsFlyer's Attribution Link Structure and Parameters](https://support.appsflyer.com/hc/articles/207447163).**

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to OPPO.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

![netease-click-through.png](https://files.readme.io/171eb745e5a4297ea90c3e71bb1911149bbb409a4d15656fdb68185f65e981b2-21594025130513.png)

### Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to OPPO to be activated when leads click on a corresponding ad.

## Cost Tab

Cost data is not supported in the integration with this partner.

## Ad Revenue Tab

Ad Revenue is not supported in the integration with this partner.

## Permissions Tab

In this tab, you can select the permissions to grant OPPO, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for OPPO, the permissions tab is active and you can grant control to OPPO.

![rtb_house-permissions-new.png](https://files.readme.io/91a51148d090b2607191ebd78eb1223619827d6a0fed09ad11d475bd9527cc17-21594025140113.png)

### Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

- _**Allow to configure integration**_ - permit the partner to setup the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).