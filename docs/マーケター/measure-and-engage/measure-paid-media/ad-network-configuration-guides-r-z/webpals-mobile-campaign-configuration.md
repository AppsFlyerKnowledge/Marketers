---
title: Webpals Mobile campaign configuration
metadata:
  keywords:
    - ClicksMob
    - Advertisers
    - Webpals mobile
    - Webpals
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-06-27T13:49:23Z'
  edited_at: '2026-10-01T00:27:48Z'
  id: 211395903
  locale: ja
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ja/articles/211395903
---
> **At a glance:** Webpals Mobile, an AppsFlyer ad network integrated partner with global coverage, is a leader in mobile user acquisition and revenue maximization.

To configure your campaigns with Webpals Mobile, follow the steps below.

## Setting up Webpals Mobile

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

Webpals Mobile configuration includes 3 active tabs: **Integration**, **Attribution link**, and **Permissions**. Click on the tabs below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to turn on the **Activate Partner** toggle to enable setup of the Integration tab parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">here</Anchor>.

### Default postbacks

Send automatic postbacks to Webpals Mobile following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Webpals Mobile.

### In-app events settings

In this section, you can map your AppsFlyer events with Webpals Mobile via postbacks.

1. Turn on In-App Event Postbacks
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated with your app or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on the Webpals Mobile side.  <br />Obtain the corresponding Event ID from Webpals Mobile and set it in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Webpals Mobile for attributing Webpals Mobile campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Webpals Mobile.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Webpals Mobile campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Webpals Mobile.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub-site ID parameter, to avoid <Anchor target="_blank" href="/marketers/ja/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Webpals Mobile.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">click lookback window here</Anchor>.

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Webpals Mobile to be activated when leads click on a corresponding ad.

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

In this tab, you can select the permissions to grant Webpals Mobile, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Webpals Mobile, the permissions tab is active and you can grant control to Webpals Mobile.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

* ***Main toggle*** - Set to On to reveal the agency permissions options
* ***Allow to configure in-app event postbacks*** - permit the agency to set up in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the agency's own retention data

Learn more about granting <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#代理店の許可">agency permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HJZW1R6FFQZ5WETP6FCMW7VN=setting-up-webpals-mobile h_01HJZW1R6F51BEYH46VPZ23X1B=integration-tab h_01HJZW1R6GKV9ZD222NSWDXVNE=activate-partner h_01HJZW1R6G1S7M82QVKQPKKDSE=default-postbacks inapp-events-settings=in-app-events-settings h_01HJZW1R6GWT322E28533S7F8N=in-app-events-settings h_01HJZW1R6G3Z21RK8ANKRP5BRY=attribution-link-tab h_01HJZW1R6GVEGEWJHWAW8N368X=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HJZW1R6G6F4Z010A7FYG6HF9=click-through-attribution h_01HJZW1R6GC6G4T3NV3FZYZ0RN=click-attribution-link h_01HJZW1R6GHK1TKD0BC72QFB0S=cost-tab h_01HJZW1R6GHP4S7BFTZZS6NDPA=ad-revenue-tab h_01HJZW1R6GV3AB25V5SA0Y3YR2=permissions-tab h_01HJZW1R6G1486DSCDP92P4MGJ=ad-network-permissions h_01HJZW1R6HXXRVWM3773VSM8WC=agency-permissions" />
