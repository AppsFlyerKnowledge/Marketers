---
title: 360 Ads campaign configuration
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
  created_at: '2019-08-02T05:47:59Z'
  edited_at: '2026-09-15T10:35:24Z'
  id: 360002152957
  locale: en-us
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360002152957-360-Ads-campaign-configuration
---
> **At a glance:** 360 Ads is an AppsFlyer ad network integrated partner.

## Setting Up 360 Ads

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

360 Ads configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration Tab">

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">here</Anchor>.

### General settings

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from 360 Ads. The view-through lookback slider is available on the attribution link tab (described below).

### Default Postbacks

<Image alt="mceclip2.png" src="https://files.readme.io/76d061e04c962477f32b23236b52b56c2b1533375073b0fc57894fad39f0c924-50900375406993.png" width="506px" />

### In-app events settings

In this section you can map your AppsFlyer events with 360 Ads via postbacks.

**Key and Secret**

360 Ads connects with AppsFlyer via a unique Key and Secret. If you don't already have the Key and Secret, you must obtain it from 360 Ads to continue with the integration.

<Image alt="mceclip2.png" src="https://files.readme.io/0d52eb93f8cba6ec283cdf844cc6fa891499884de0c93689653f4d356078dd85-50900375408017.png" width="412px" />

1. Set the 360 Ads Key and Secret here
2. Toggle In-App Event Postbacks to ON
3. Click **Add Event** to add an SDK Event to the list
4. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on 360 Ads side.  <br />Obtain the corresponding Event ID from 360 Ads and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution Link Tab">

In this tab, you can create the attribution links you want to send to 360 Ads for attributing 360 Ads campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with 360 Ads.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific 360 Ads campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific 360 Ads campaigns.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid <Anchor target="_blank" href="/marketers/id/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image alt="attribution-link-parameters.png" src="https://files.readme.io/823a4ad48f073aa1b45e7a3fc966073711b9a3dd8c8e8196c705e2236d7f93a5-50900375410065.png" width="588px" />

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to 360 Ads.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows">click lookback window here</Anchor>.

![netease-click-through.png](https://files.readme.io/3ad5a42060b78fcd3d5d7f94766ad1a5180696f67425e92abafbfd83bf331965-50900375410321.png)

### Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to 360 Ads to be activated when leads click on a corresponding ad. 

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to 360 Ads, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows">view-through attribution here</Anchor>.

[![](https://files.readme.io/fd01a3f2373e2946f2926ea732431bfb4f10e3d861e2ad4a8a5ae6dcb288cbc1-50900397422097.png)](https://files.readme.io/fd01a3f2373e2946f2926ea732431bfb4f10e3d861e2ad4a8a5ae6dcb288cbc1-50900397422097.png)

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to 360 Ads to be activated when a corresponding ad is watched, usually for 1 second or more.

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

In this tab, you can select the permissions to grant 360 Ads, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for 360 Ads, the permissions tab is active and you can grant control to 360 Ads.

![rtb_house-permissions-new.png](https://files.readme.io/ad21dc33e731bb96aa04093868e7b89c146d2351baebb09b7bba172b9886b04b-50900375415825.png)

### Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to setup the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKW6S90SZY55XRP6YN8B3QTJ=setting-up-360-ads h_01HKW6S90TSD0WKZ4ZT7701DX7=integration-tab h_01HKW6S90TVP4K2XFP5EEFWDC4=activate-partner h_01HKW6S90T9ABAX8E7DK02N538=general-settings h_01HKW6S90TEJ68RG9B3S5KD63Y=default-postbacks inapp-events-settings=in-app-events-settings h_01HKW6S90TN3J07GXS8C7NTETR=in-app-events-settings h_01HKW6S90T7P66TMWFA4T4C350=attribution-link-tab h_01HKW6S90TCMRFHFXBEJBCP9C6=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW6S90TQW75T0HCCC38ETWB=click-through-attribution h_01HKW6S90T0SVWCEV905DC2VTW=attribution-link viewthrough-attribution-lookback-window=view-through-attribution-lookback-window h_01HKW6S90T813FYKMGDAF935YJ=view-through-attribution-lookback-window h_01HKW6S90T4TS5EHK8M7E4QV8G=impressions-attribution-link h_01HKW6S90TXR07SQJW3DTD9VS4=cost-tab h_01HKW6S90T489CVTQXQPRM0M8B=ad-revenue-tab h_01HKW6S90VWKHEWNY7AYKRWGBH=permissions-tab h_01HKW6S90V1ZV766FZ20EKJR0N=ad-network-permissions" />
