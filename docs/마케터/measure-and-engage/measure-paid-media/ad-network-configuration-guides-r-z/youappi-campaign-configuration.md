---
title: YouAppi campaign configuration
metadata:
  keywords:
    - Advertisers
    - YouAppi
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-09-20T07:14:26Z'
  edited_at: '2026-10-13T01:15:39Z'
  id: 212932106
  locale: ko
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ko/articles/212932106
---
> **At a glance:** YouAppi, an AppsFlyer ad network integrated partner, is a leading mobile growth marketing platform for premium mobile brands. In addition to click-based mobile attribution, YouAppi offers cost, ad revenue, retargeting and view-through attribution, which can be recorded with AppsFlyer.

To configure your campaigns with YouAppi, follow the steps below.

## Setting up YouAppi

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

YouAppi's configuration includes 4 active tabs: Integration, Attribution link, Cost, and Permissions. Click on the items below to read about the tabs setup.

> 👍 **Tip**
>
> * The <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#d-general-settings">General Settings</Anchor> step in the Integration tab is **mandatory** for all partners.
> * All the rest of the steps are either descriptive or **optional**.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to turn on the ***Activate Partner*** toggle to enable setup of the Integration parameters. The toggle **must** be on for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">here</Anchor>.

> 📘 **Note**
>
> As an ALL-Installs network, YouSppi prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to YouAppi.

### General settings

**trackerToken**

YouAppi connects with AppsFlyer via a trackerToken. If you don't already have the trackerToken, you must obtain it from YouAppi to continue with the integration.

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from YouAppi. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to YouAppi following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to YouAappi.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to YouAppi.

### In-app events settings

In this section, you can map your AppsFlyer events with YouAppi via postbacks.

1. Enter the trackerToken again.
2. Turn on In-App Event Postbacks.
3. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner.  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner.
4. Click **Add Event** to add an SDK Event to the list.
5. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app or from server-to-server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Youappi's side.  <br />Obtain the corresponding Event ID from Youappi and set it in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Youappi for attributing Youappi's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Youappi.  
  **Attribution link parameter:** c
* **Adset** - set ad set name to compare different ad sets within specific Youappi campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad name to compare different creatives within specific ad sets within specific campaigns Youappi.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub-site ID parameter, to avoid <Anchor target="_blank" href="/marketers/ko/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to YouAppi.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">click lookback window here</Anchor>.

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to YouAppi to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to YouAppi, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">view-through attribution here</Anchor>.

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to YouAppi to be activated when a corresponding ad is watched, usually for 1 second or more.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">these integration instructions</Anchor>.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported by this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant YouAppi, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for YouAppi, the permissions tab is active and you can grant control to YouAppi.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to set up in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

* ***Main toggle*** - Set to On to reveal the agency permissions options
* ***Allow access to your retention report*** - only to the agency's own retention data
* ***Allow access to aggregate organic data***
* ***Allow to configure in-app event postbacks*** - permit the agency to set up in-app event postbacks mapping to itself on the integration tab

Learn more about granting <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#에이전시-권한">agency permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HK29DCA2B0VJM46KYCPWZ0V0=setting-up-youappi h_01HK29DCA3XH6B98018C6G5MQY=tip h_01HK29DCA3J3TVPAEEH00T1RS8=integration-tab h_01HK29DCA3E890TQ7MZ8BEEA5J=activate-partner h_01HK29DCA3KGV3S44XQ52ZV8YM=note h_01HK29DCA3SR6BGN8PD8X4R198=general-settings h_01HK29DCA390TAZGD1A1EM06VY=default-postbacks inapp-events-settings=in-app-events-settings h_01HK29DCA3VQRZT8SYTQ5T0Z8F=in-app-events-settings h_01HK29DCA3ESN9EA4RKE1F6HE9=attribution-link-tab h_01HK29DCA3CJ5J19D7MGN9ZAWB=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HK29DCA3BGEC5VVC2X00M6HQ=click-through-attribution h_01HK29DCA30YW2PTWKF0HSPG9Q=click-attribution-link viewthrough-attribution-lookback-window=view-through-attribution-lookback-window h_01HK29DCA3DSF3D8GETECYCZXE=view-through-attribution-lookback-window h_01HK29DCA33HGQRRNXN096W2HY=impressions-attribution-link h_01HK29DCA3PRMEEYGB15JWD5N7=cost-tab h_01HK29DCA4KNSAG2XYZQNX26S9=ad-revenue-tab h_01HK29DCA4EV987C7GPPXSKS7V=permissions-tab h_01HK29DCA4ZEYMM46NYRH6VWW1=ad-network-permissions h_01HK29DCA4923EKBV6X8DBCWFZ=agency-permissions" />
