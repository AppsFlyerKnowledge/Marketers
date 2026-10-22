---
title: Glispa campaign configuration
metadata:
  keywords:
    - Glispa
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
  created_at: '2016-04-07T12:53:20Z'
  edited_at: '2026-09-09T13:03:44Z'
  id: 209912983
  locale: en-us
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/209912983-Glispa-campaign-configuration
---
> **At a glance:** Glispa, an AppsFlyer integrated ad network partner, creates solutions that make it simple for agencies and brands to connect with target audiences and for publishers to monetize their apps. In addition to click-based mobile attribution, Glispa offers cost and view-through attribution, which you can record with AppsFlyer.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/glispacpa.png?v=1" width="168px" />

## Setting up Glispa

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable the setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">here</Anchor>.

### General settings

**Enable View-Through attribution**

[![appl013.png](https://files.readme.io/513c24cf8bcf72d8efc3324411a1bea1fd45e8c7cb721c7f1144463fa030492c-50706625495953.png)](https://files.readme.io/513c24cf8bcf72d8efc3324411a1bea1fd45e8c7cb721c7f1144463fa030492c-50706625495953.png)

Toggle this to ON if you want to attribute view-through installs from Glispa. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to Glispa following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Glispa.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Glispa.

### In-app events settings

In this section you can map which of your AppsFlyer events to send to Glispa via postbacks.

1. Toggle In-App Event Postbacks to ON.
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated with your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Send Revenue** | **When unchecked** - send all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - send all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Glispa for attributing Glispa's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Glispa.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Glispa campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific Glispa campaigns.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the subsite ID parameter, to avoid <Anchor target="_blank" href="/marketers/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Glispa.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/docs/set-up-lookback-windows">click lookback window here</Anchor>.

[![](https://files.readme.io/72e192640be302ffede694bc264f1ce5746022242bfa441b29f835605a07004d-50706581523217.png)](https://files.readme.io/72e192640be302ffede694bc264f1ce5746022242bfa441b29f835605a07004d-50706581523217.png)

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Glispa to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to Glispa, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the <Anchor target="_blank" href="/marketers/docs/set-up-lookback-windows">view-through attribution here</Anchor>.

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to Glispa to be activated when a corresponding ad is watched, usually for 1 second or more.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Glispa Media CPI automatically sends encrypted CPI cost data on the attribution link for all installs.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Use these toggles to give Glispa permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

* ***Main toggle*** - Set to On to reveal the agency permissions options
* ***Allow access to your retention report*** - only to the agency's own retention data
* ***Allow access to aggregate organic data***
* ***Allow to configure in-app event postbacks*** - permit the agency to setup in-app event postbacks mapping to itself on the integration tab

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#agency-permissions">agency permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKA0TGE08PJDBQHFER5ZZ785=setting-up-glispa h_01HKA0TGE02G8YFSQSKMQVSWK2=integration-tab h_01HKA0TGE02R2V2WP9S47QZRDC=activate-partner h_01HKA0TGE04YGTY2D9758KFJ0P=general-settings h_01HKA0TGE0TPCZWZXX5YQHW59Q=default-postbacks inapp-events-settings=in-app-events-settings h_01HKA0TGE0Y9ZQDZBRHQGCSEHH=in-app-events-settings h_01HKA0TGE0VQY6MB69G02TE1T6=attribution-link-tab h_01HKA0TGE0BYX5YB9XYCWX5YJH=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKA0TGE0TVP7JRW3J9E4QGKC=click-through-attribution h_01HKA0TGE10GVS8G2HYTB9V13X=click-attribution-link viewthrough-attribution-lookback-window=view-through-attribution-lookback-window h_01HKA0TGE1CNX84Y3JSWQPMP1Y=view-through-attribution-lookback-window h_01HKA0TGE1GVH38JF1AYEBM8EC=impressions-attribution-link h_01HKA0TGE1QXYQ1A5MYHGHZ4B4=cost-tab h_01HKA0TGE10TWPQZRF1NMET76A=ad-revenue-tab h_01HKA0TGE12N0Y8Y88C9PTTF6P=permissions-tab h_01HKA0TGE1TANWDZ23PJKRPWKT=ad-network-permissions h_01HKA0TGE16J58NXGA0VDBBHWY=agency-permissions" />
