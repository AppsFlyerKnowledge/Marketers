---
title: "vivo Ads Campaign Configuration"
excerpt: "Learn how to configure vivo Ads in AppsFlyer, including setting up the integration, configuring attribution links, and managing lookback windows."
---
**At a glance:** vivo Ads is an AppsFlyer ad network integrated partner.

## Setting Up vivo Ads

The setup is done from the **Active Integrations** page, but to find new partners you must first go to the [marketplace](/docs/partner-integrations).

> 📘 **Note**
>
> #### Note
>
> Before setting up an integration, make sure you [contact the partner](/docs/partner-integrations#contact-details) and open an account with them.


**To activate the integration:**

1. In AppsFlyer, from the side menu, select**Collaborate**> **Partner Marketplace**.
2. Search for the partner and select it.
3. Click **Set up integration**.
4. Select the app for the integration. You’re directed to the integration setup page.
5. In the **Integration** tab, turn **Activate partner** on.

vivo Ads configuration window includes 2 active tabs: Integration and Attribution link. Click the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

> 📘 **Note**
>
> #### Tip
>
> * The [General Settings](/docs/set-up-an-integrated-partner#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**


## Integration Tab

The integration with vivo Ads only supports the install event in the default postback.

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

### Enable View-Through attribution

Toggle this to ON if you want to attribute view-through installs from vivo Ads. The view-through lookback slider is available on the attribution link tab (described below).

### Default Postbacks

![mceclip2.png](https://files.readme.io/b741d91a0e6480f5d93d64f1a4a581749fa379e91c534c7114142f9d162988ed-21594058508817.png)

## Attribution Link Tab

In this tab, you can create the attribution links you want to send to vivo Ads for attributing vivo Ads campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with vivo Ads.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific vivo Ads campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific vivo Ads campaigns.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/ab4f8c3cd32db8bc64319726512af4ae95e1f4d86f1ba3ed6180fede614f478d-21594029729809.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about **[AppsFlyer's Attribution Link Structure and Parameters](/docs/about-link-structure-and-parameters).**

### Click-through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to vivo Ads.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

![viewthrough_en-us.png](https://files.readme.io/11a713ea3763e230f4b901d7faf827cf9288c6e3aac4e45f32c912f85617eacf-360003683158.png)

### Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to vivo Ads to be activated when leads click on a corresponding ad. 

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to vivo Ads, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the [view-through attribution here](/docs/set-up-lookback-windows).

[![](https://support.appsflyer.com/hc/article_attachments/21594029755409)](https://support.appsflyer.com/hc/article_attachments/21594029755409)

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to vivo Ads to be activated when a corresponding ad is watched, usually for 1 second or more.

## Cost Tab

Cost data is not supported in the integration with this partner.

## Ad Revenue Tab

Ad Revenue is not supported in the integration with this partner.

## Permissions Tab

Permissions are not supported in the integration with this partner.