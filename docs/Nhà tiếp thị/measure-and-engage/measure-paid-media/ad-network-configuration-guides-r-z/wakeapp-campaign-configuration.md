---
title: WakeApp campaign configuration
metadata:
  keywords:
    - Advertisers
    - WakeApp
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-06-30T12:39:52Z'
  edited_at: '2026-09-07T07:24:59Z'
  id: 211506443
  locale: en-us
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/211506443-WakeApp-campaign-configuration
---
> **At a glance:** WakeApp, an AppsFlyer ad network integrated partner, is a global company specializing in mobile marketing.

To configure your campaigns with Wakeapp, follow the steps below.

## Setting up WakeApp

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

The Wakeapp configuration includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">here</Anchor>.

> 👍 **Tip**
>
> * The <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#d-general-settings">General Settings</Anchor> step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to turn on the ***Activate Partner*** toggle to enable setup of the Integration tab's parameters. The toggle MUST be on for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">here</Anchor>.

### Default postbacks

Send automatic postbacks to Wakeapp following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Wakeapp.

### In-app events settings

In this section, you can map your AppsFlyer events with Wakeapp via postbacks.

1. Toggle In-App Event Postbacks to ON
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated with your app or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event, as defined on Wakeapp's side.  <br />Obtain the corresponding Event ID from Wakeapp and set the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Wakeapp for attributing Wakeapp's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Wakeapp.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Wakeapp campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Wakeapp.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub-site ID parameter, to avoid <Anchor target="_blank" href="/marketers/vi/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Wakeapp.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">click lookback window here</Anchor>.

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Wakeapp to be activated when leads click on a corresponding ad.

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

In this tab, you can select the permissions to grant Wakeapp, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Wakeapp, the permissions tab is active and you can grant control to Wakeapp.

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

* ***Main toggle*** - Set to On to reveal the agency permissions options
* ***Allow access to your retention report*** - only to the agency's own retention data
* ***Allow access to aggregate organic data***
* ***Allow to configure in-app event postbacks*** - permit the agency to setup in-app event postbacks mapping to itself on the integration tab

Learn more about granting <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#cấp-quyền-cho-đại-lý">agency permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HJZVGH83HTK5PZBCSTKC1ZYV=setting-up-wakeapp h_01HJZVGH83T3H15CNPDEC0G580=tip h_01HJZVGH836Y6104G1HJVG22NE=integration-tab h_01HJZVGH83DXZ1JZ5B14DSAY47=activate-partner h_01HJZVGH84EHZJEY0EERDK4WP1=default-postbacks inapp-events-settings=in-app-events-settings h_01HJZVGH840N0W4JXRM82K6936=in-app-events-settings h_01HJZVGH844DSMXM6M07MG5GNC=attribution-link-tab h_01HJZVGH84FZMXM843ZXQ1WKEX=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HJZVGH849REDVA5HGEWJTZQH=click-through-attribution h_01HJZVGH84QASMHXVGCF0DGXN8=click-attribution-link h_01HJZVGH84AGW72MCGDMR4YXM2=cost-tab h_01HJZVGH84P75Z4N4EPD4121DY=ad-revenue-tab h_01HJZVGH84MAQKSTCFPEG70YF3=permissions-tab h_01HJZVGH84YD3AH66K633T6S00=agency-permissions" />
