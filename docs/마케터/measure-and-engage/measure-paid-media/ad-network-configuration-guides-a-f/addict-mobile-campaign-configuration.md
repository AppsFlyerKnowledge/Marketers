---
title: Addict Mobile campaign configuration
metadata:
  keywords:
    - Advertisers
    - Addict Mobile
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-01-03T09:11:00Z'
  edited_at: '2026-10-13T01:05:30Z'
  id: 115000174783
  locale: ko
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ko/articles/115000174783
---
> **At a glance:** Addict Mobile, an AppsFlyer ad network integrated partner, is a mobile performance marketing expert for user acquisition and retargeting on mobile. In addition to click-based mobile attribution, Addict Mobile also offers view-through attribution, which you can record with AppsFlyer.

## Setting up Addict Mobile

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partner

On the **first visit** here, you need to toggle ON the ***Activate Partner*** button to enable the setup of the integration tab parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">here</Anchor>.

### General settings

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from Addict Mobile. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to Addict Mobile following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Addict Mobile.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Addict Mobile.

### In-app events settings

In this section, you can map your AppsFlyer events with Addict Mobile via postbacks.

1. Toggle In-App Event Postbacks to ON.
2. Select the Sending Option for all SDK-defined events.
   * **Only events attributed to this partner** for events coming **only** from users attributed to this partner.
   * **Events attributed to any partner or organic** to have your entire user base available to be reported to the partner.
3. Click **Add Event** to add an SDK Event to the list.
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Addict Mobile side.  <br />Obtain the corresponding Event ID from Addict Mobile and set it in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Addict Mobile for attributing Addict Mobile's campaigns, ad sets, or single ads. Note that AppsFlyer DOES NOT save your generated attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Addict Mobile.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Addict Mobile campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad names to compare different creatives within specific ad sets within specific campaigns Addict Mobile.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid <Anchor target="_blank" href="/marketers/ko/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">**AppsFlyer Attribution Link Structure and Parameters**</Anchor>.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Addict Mobile.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">click lookback window here</Anchor>.

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Addict Mobile to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to Addict Mobile, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">view-through attribution here</Anchor>.

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to Addict Mobile to be activated when a corresponding ad is watched, usually for 1 second or more.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost integration is not available for Addict Mobile.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue data is not supported by Addict Mobile.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Addict Mobile, whether the partner acts as an ad network, agency, or both. Note that even if attribution is disabled for Addict Mobile, the permissions tab is active and you can grant control to Addict Mobile.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

* ***Main toggle*** - Set to On to reveal the agency permissions options
* ***Allow access to your retention report*** - only to the agency's own retention data
* ***Allow access to aggregate organic data***
* ***Allow to configure in-app event postbacks*** - permit the agency to setup in-app event postbacks mapping to itself on the integration tab

Learn more about granting <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#에이전시-권한">agency permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HJR633087HDAET7KHT8E9XEB=setting-up-addict-mobile h_01HJR63308JRT30ATJGHK8ENGD=integration-tab h_01HJR6330800PFWSAB8A3GXMW4=activate-partner h_01HJR63308AZ4815GFH2JMV1G5=general-settings h_01HJR63308QQN56PHAZJJEEN46=default-postbacks inapp-events-settings=in-app-events-settings h_01HJR63309W68NWQ8JBH44HJRT=in-app-events-settings h_01HJR63309HPDZGQTG2P5429GX=attribution-link-tab h_01HJR63309YXMMFWC3BJ5P4QZ6=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HJR63309B694DZTGKBCEJ9Q5=click-through-attribution h_01HJR633091B528NHJC60RQ9QT=click-attribution-link viewthrough-attribution-lookback-window=view-through-attribution-lookback-window h_01HJR63309G1W0P1Y5CZQ9MWYF=view-through-attribution-lookback-window h_01HJR633092XASXD3STXJW5RN7=impressions-attribution-link h_01HJR63309MSKSWQNCSCYC33BR=cost-tab h_01HJR633092FJD6G3P97ZBG4WA=ad-revenue-tab h_01HJR63309BHWNSKQ7Y63P2B9M=permissions-tab h_01HJR63309BKERBX97ZRPHC4EC=ad-network-permissions h_01HJR6330A35DEFCHZA2DC95WR=agency-permissions" />
