---
title: "Baidu Native Ads 2.0 campaign configuration"
excerpt: "Baidu Native Ads 2.0 is an AppsFlyer ad network integrated partner."
x-zendesk:
  id: 360002158958
  url: https://support.appsflyer.com/hc/en-us/articles/360002158958-Baidu-Native-Ads-2-0-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: China domestic market ad network configuration
  section_id: 6552066355601
  position: 0
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2019-08-02T04:18:11Z'
  edited_at: '2026-09-15T10:23:19Z'
---
## Setting Up Baidu Native Ads 2.0

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

Baidu Native Ads 2.0's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

## Integration Tab

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

### General settings

Baidu Native Ads 2.0 connects with AppsFlyer via a unique **akey**. If you don't already have the key, you must obtain it from Baidu Native Ads 2.0 to continue with the integration.

![mceclip2.png](https://files.readme.io/fe8f44ee7d58fda9ee6289872903f96c716ab6d1191dd831745445cbced8b316-50899807435409.png)

### Default Postbacks

![mceclip2.png](https://files.readme.io/da98623fc56a1615c49fe2a955452270dcf01857fab468c82b58d01fab36e36a-50899846623633.png)

### In-app events settings

In this section you can map your AppsFlyer events with Baidu Native Ads 2.0 via postbacks. 

![mceclip1.png](https://files.readme.io/1d929a3ba75da04165e416843f5037b8e299b12ae190aa9068cc3b317348087c-50899846627601.png)

1. Toggle In-App Event Postbacks to ON
2. Click **Add Event** to add an SDK Event to the list
3. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Baidu Native Ads 2.0's side.  <br />Obtain the corresponding Event ID from Baidu Native Ads 2.0 and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

## Attribution Link Tab

In this tab, you can create the attribution links you want to send to Baidu Native Ads 2.0 for attributing Baidu Native Ads 2.0's campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Baidu Native Ads 2.0.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Baidu Native Ads 2.0 campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific Baidu Native Ads 2.0 campaigns.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/54878d2467201f98d9228e3b7f3028ec6d5a054102534443e256bd7c955f8741-50899846628625.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. Learn more about[**AppsFlyer's Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters)**.**

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Baidu Native Ads 2.0.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

![netease-click-through.png](https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png)

### Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to Baidu Native Ads 2.0 to be activated when leads click on a corresponding ad.

## Cost Tab

Cost data is not supported in the integration with this partner.

## Ad Revenue Tab

Ad Revenue is not supported in the integration with this partner.

## Permissions Tab

Permissions are not supported in the integration with this partner.