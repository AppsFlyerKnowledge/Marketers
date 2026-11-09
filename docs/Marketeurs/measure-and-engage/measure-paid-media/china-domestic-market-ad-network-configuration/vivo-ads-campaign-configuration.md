---
title: vivo Ads Campaign Configuration
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-29T08:24:47Z'
  edited_at: '2026-09-15T10:34:14Z'
  id: 360002358897
  locale: en-us
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360002358897-vivo-Ads-Campaign-Configuration
---
> **At a glance:** vivo Ads is an AppsFlyer ad network integrated partner.

## Setting Up vivo Ads

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

vivo Ads configuration window includes 2 active tabs: Integration and Attribution link. Click the items below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration Tab">

The integration with vivo Ads only supports the install event in the default postback.

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">here</Anchor>.

### Enable View-Through attribution

Toggle this to ON if you want to attribute view-through installs from vivo Ads. The view-through lookback slider is available on the attribution link tab (described below).

### Default Postbacks

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/4d6fca06a4e11a8748064bce6510abe8594ef1fb68d1876ba5cd486073adf469-50900339194129.png" width="456px" />

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution Link Tab">

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
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid <Anchor target="_blank" href="/marketers/fr/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image align="center" alt="attribution-link-parameters.png" src="https://files.readme.io/5f158d1a7edc30276168a271a48373b2444af4207865f8dc874e95f1c9772ce4-50900334031889.png" width="479px" />

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Click-through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to vivo Ads.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">click lookback window here</Anchor>.

<Image align="center" alt="viewthrough_en-us.png" src="https://files.readme.io/47ff5d900d8edfdc30f2d2c0588f5e06fc3b44e71aeab630d1b5df2ea8c2db47-50900334036625.png" />

### Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to vivo Ads to be activated when leads click on a corresponding ad. 

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to vivo Ads, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">view-through attribution here</Anchor>.

<Image align="center" alt="" src="https://files.readme.io/786f2212e98741dfd8965c78897e35042ea016918aaa216ff8f6f99d2a46cf2a-50900339201809.png" />

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to vivo Ads to be activated when a corresponding ad is watched, usually for 1 second or more.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost Tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad Revenue Tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions Tab">

Permissions are not supported in the integration with this partner.

</Accordion>

<div data-zendesk-anchors="h_01HKW6Y9CJED5RV97WWSYQNBDG=setting-up-vivo-ads h_01HKW6Y9CJZ1YPFBQH1W0QV21G=integration-tab h_01HKW6Y9CJC0EWH84B7GW29VJM=activate-partner enable-viewthrough-attribution=enable-view-through-attribution h_01HKW6Y9CJ8PNMN2ANR3E3WK1H=enable-view-through-attribution h_01HKW6Y9CJDY5XHWXN3CK0YGK8=default-postbacks h_01HKW6Y9CKQXSWXNK1VEXQFEPA=attribution-link-tab h_01HKW6Y9CKSHBWNBH0RY3X3RR3=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW6Y9CKE86Z1Z4QZH0M665T=click-through-attribution h_01HKW6Y9CKNB685ZYXB8RM1P41=attribution-link viewthrough-attribution-lookback-window=view-through-attribution-lookback-window h_01HKW6Y9CKV48NRWSXD0ZKY3M0=view-through-attribution-lookback-window h_01HKW6Y9CKV6XY1BCD9XX42XZ7=impressions-attribution-link h_01HKW6Y9CKZ0TMJ1F3H8X2W733=cost-tab h_01HKW6Y9CKB65QFDTKX4AW3P23=ad-revenue-tab h_01HKW6Y9CKV3KJ5X5ECEF2JJ8N=permissions-tab" />
