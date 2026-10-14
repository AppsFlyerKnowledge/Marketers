---
title: "Zhihu Ads campaign configuration"
excerpt: "Zhihu Ads is an AppsFlyer ad network integrated partner."
x-zendesk:
  id: 360001758338
  url: https://support.appsflyer.com/hc/en-us/articles/360001758338-Zhihu-Ads-campaign-configuration
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
  created_at: '2019-06-05T06:05:50Z'
  edited_at: '2026-09-15T10:38:21Z'
---
## Setting Up Zhihu Ads

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

Zhihu Ads's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

<Accordion title="Integration Tab">

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

### General settings

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from Zhihu Ads. The view-through lookback slider is available on the attribution link tab (described below).

### Default Postbacks

![mceclip2.png](https://files.readme.io/4f11e674b3e876d5d612a4700163520fa542bd255c3427640d1abe5be7cfaf7a-50900523403153.png)

### In-app events settings

In this section you can map your AppsFlyer events with Zhihu Ads via postbacks.

![mceclip2.png](https://files.readme.io/39f3b95126da7107b2972b5811d0367d51191eed76cc6ddbef52ffb3a0c1e137-50900503184017.png)

1. Toggle In-App Event Postbacks to ON
2. Click **Add Event** to add an SDK Event to the list
3. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Zhihu Ads's side.  <br />Obtain the corresponding Event ID from Zhihu Ads and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<Accordion title="Attribution Link Tab">

In this tab, you can create the attribution links you want to send to Zhihu Ads for attributing Zhihu Ads's campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

![mceclip1.png](https://files.readme.io/3f946bccf687826dd2e9ebc318e2510ee5bef5641e9cbfaa1f4b231089ebfee5-50900523405713.png)

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Zhihu Ads.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Zhihu Ads campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific Zhihu Ads campaigns.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/3518a235855b8d8a1a673dc6e7266615e16e32b63b3cf5533d02582db16169fe-50900523407633.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about[**AppsFlyer's Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters).

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Zhihu Ads.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

![netease-click-through.png](https://files.readme.io/02473962e9224f0df4339d9848ccae59b2ef2370f15144bb0b36a6de15756558-50900503191185.png)

### Click Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to Zhihu Ads to be activated when leads click on a corresponding ad.

<Accordion title="">

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to Zhihu Ads, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the [view-through attribution here](/docs/set-up-lookback-windows).

[![](https://files.readme.io/7010eb3bfd9dda24550753ee8ef89b72462c2b762cfd1315a741a7e109b69128-50900503192209.png)](https://files.readme.io/7010eb3bfd9dda24550753ee8ef89b72462c2b762cfd1315a741a7e109b69128-50900503192209.png)

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to Zhihu Ads to be activated when a corresponding ad is watched, usually for 1 second or more.

</Accordion>

</Accordion>

<Accordion title="Cost Tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<Accordion title="Ad Revenue Tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<Accordion title="Permissions Tab">

In this tab, you can select the permissions to grant Zhihu Ads, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for Zhihu Ads, the permissions tab is active and you can grant control to Zhihu Ads.

![rtb_house-permissions-new.png](https://files.readme.io/0192ccb7682af8b56c1bb5f8d7d75c87941f94441b644cf6fa7973159bc961a0-50900503192977.png)

### Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to setup the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).

</Accordion>
