---
title: Ligatus campaign configuration
excerpt: >-
  Ligatus, an AppsFlyer ad network integrated partner, leads Native Advertising
  Solutions for Publishers, Advertisers, and Programmatic buyers offering
  high-quality and high-performance results. In addition to click-based mobile
  attribution, Ligatus also offers cost, ad revenue, retargeting, and
  view-through attribution, which you can record with AppsFlyer.
metadata:
  keywords:
    - Ligatus
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-06-20T12:47:01Z'
  edited_at: '2026-06-16T11:41:41Z'
  id: 211189743
  locale: en-us
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/211189743-Ligatus-campaign-configuration
---
![](https://cdn.appsflyer.com/marketplace/static/logo/ligatus.png)

## Setting up Ligatus

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

Ligatus's configuration window includes 2 active tabs: Integration and Attribution link. Click on the items below to read about the tab setup.

> 📘 **Tip**
>
> * The [General Settings](/docs/set-up-an-integrated-partner#d-general-settings) step in the Integration tab is **mandatory** for all partners.
> * All the rest of the steps are either descriptive or **optional**

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable setup of the Integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation, please click [here](/docs/partner-activation-deactivation).

### Default postbacks

send automatic postbacks to Ligatus following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Ligatus.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Ligatus for attributing Ligatus's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to perform thorough drill-down analyses later. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Ligatus.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Ligatus campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Ligatus.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise limiting the number of used site IDs and using the subsite ID parameter to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about[**AppsFlyer Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters).

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Ligatus.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Ligatus to be activated when leads click on a corresponding ad.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Permission configuration is not available for Ligatus.

</Accordion>

<div data-zendesk-anchors="h_01HKW2DXQHTK9HVAWK0ECR46AZ=setting-up-ligatus h_01HKW2DXQJ4DBPP38P4RRZGX10=tip h_01HKW2DXQJYQ7PJVN6HAM0AHXB=integration-tab h_01HKW2DXQJEF1KX2C489M18EB7=activate-partner h_01HKW2DXQJPJKBMA7ZN75JSSNR=default-postbacks h_01HKW2DXQJNFZJT6NVC2R3GDSB=attribution-link-tab h_01HKW2DXQJC123Y5DPX0V86M4K=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW2DXQK53YBMRBF2RC26SG8=click-through-attribution h_01HKW2DXQKFGXMBB31N3EJAA55=click-attribution-link h_01HKW2DXQKPZBFVKQ71G6076VN=cost-tab h_01HKW2DXQKQ0YDVHMGJ0WMP1CB=ad-revenue-tab h_01HKW2DXQKBC42EMXQRVZSK7N4=permissions-tab" />
