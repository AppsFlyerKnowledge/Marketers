---
title: "vivo Ads Campaign Configuration"
excerpt: "Learn how to configure vivo Ads in AppsFlyer, including setting up the integration, configuring attribution links, and managing lookback windows."
---
**At a glance:** vivo Ads is an AppsFlyer ad network integrated partner.

## Setting Up vivo Ads

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

vivo Ads configuration window includes 2 active tabs: Integration and Attribution link. Click the items below to read about the tabs setup.

## Integration Tab

The integration with vivo Ads only supports the install event in the default postback.

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

### Enable View-Through attribution

Toggle this to ON if you want to attribute view-through installs from vivo Ads. The view-through lookback slider is available on the attribution link tab (described below).

### Default Postbacks

![mceclip2.png](https://files.readme.io/4d6fca06a4e11a8748064bce6510abe8594ef1fb68d1876ba5cd486073adf469-50900339194129.png)

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

![attribution-link-parameters.png](https://files.readme.io/5f158d1a7edc30276168a271a48373b2444af4207865f8dc874e95f1c9772ce4-50900334031889.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about[**AppsFlyer's Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters)**.**

### Click-through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to vivo Ads.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

![viewthrough_en-us.png](https://files.readme.io/47ff5d900d8edfdc30f2d2c0588f5e06fc3b44e71aeab630d1b5df2ea8c2db47-50900334036625.png)

### Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to vivo Ads to be activated when leads click on a corresponding ad. 

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to vivo Ads, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the [view-through attribution here](/docs/set-up-lookback-windows).

[![](https://files.readme.io/786f2212e98741dfd8965c78897e35042ea016918aaa216ff8f6f99d2a46cf2a-50900339201809.png)](https://files.readme.io/786f2212e98741dfd8965c78897e35042ea016918aaa216ff8f6f99d2a46cf2a-50900339201809.png)

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to vivo Ads to be activated when a corresponding ad is watched, usually for 1 second or more.

## Cost Tab

Cost data is not supported in the integration with this partner.

## Ad Revenue Tab

Ad Revenue is not supported in the integration with this partner.

## Permissions Tab

Permissions are not supported in the integration with this partner.