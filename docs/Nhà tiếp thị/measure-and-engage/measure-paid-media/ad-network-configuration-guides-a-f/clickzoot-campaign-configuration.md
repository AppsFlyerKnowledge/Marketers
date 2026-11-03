---
title: ClickZoot campaign configuration
metadata:
  keywords:
    - clickzoot
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
  created_at: '2016-04-04T15:44:00Z'
  edited_at: '2026-07-23T13:14:22Z'
  id: 208278016
  locale: en-us
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/208278016-ClickZoot-campaign-configuration
---
> **At a glance:** Clickzoot, an AppsFlyer ad network integrated partner, provides solutions for mobile, lead generation, email marketing, and data optimization.

## Setting up ClickZoot

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

The Clickzoot configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">here</Anchor>.

> 👍 **Tip**
>
> * The <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#d-general-settings">General Settings</Anchor> step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**

### Activate partner

On the **first visit** here, you must toggle ON the ***Activate Partner*** button to enable the setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation, click <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">here</Anchor>.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### General settings

**Offer ID**

Clickzoot connects with AppsFlyer via a unique Offer ID. If you don't already have it, you must obtain it from Clickzoot to continue with the integration.

### Default postbacks

Send automatic postbacks to Clickzoot following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Clickzoot.

### In-app events settings

In this section, you can map your AppsFlyer events with Clickzoot via postbacks.

1. Enter the offer\_id again.
2. Toggle In-App Event Postbacks to ON.
3. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list.
5. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on the Clickzoot side.  <br />Obtain the corresponding Event ID from Clickzoot and set in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Clickzoot for attributing Clickzoot campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Clickzoot.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Clickzoot campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Clickzoot.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the subsite ID parameter, to avoid <Anchor target="_blank" href="/marketers/vi/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">**AppsFlyer Attribution Link Structure and Parameters**</Anchor>.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window can be attributed to Clickzoot.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">click lookback window here</Anchor>.

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Clickzoot to be activated when leads click on a corresponding ad.

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

In this tab, you can select the permissions to grant Clickzoot, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Clickzoot, the permissions tab is active and you can grant control to Clickzoot.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKWB2T5BJFHZN82BHC97JWRZ=setting-up-clickzoot h_01HKWB2T5BWSQPVDPAFYV8KD2N=tip h_01HKWB2T5BGXSXZZBT7CF84HZ4=activate-partner h_01HKWB2T5BYB92GV7KGRDDP6C1=integration-tab h_01HKWB2T5B7ZSRVZGQGAC10533=general-settings h_01HKWB2T5BKYVPJDB115FW1F8A=default-postbacks inapp-events-settings=in-app-events-settings h_01HKWB2T5CJ0BCA2AVVEWMEEZH=in-app-events-settings h_01HKWB2T5CF5BS3YS8BJPM4CGQ=attribution-link-tab h_01HKWB2T5C6HFZDZ4DQ3AD2100=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKWB2T5C03VMECXQM6A9EQV8=click-through-attribution h_01HKWB2T5C42HKK8QFHWXAAV8T=click-attribution-link h_01HKWB2T5C9XYC5326RTSRTHV4=cost-tab h_01HKWB2T5CZE8508SQF05159NG=ad-revenue-tab h_01HKWB2T5CYFTGWWWH8GFNWWXK=permissions-tab h_01HKWB2T5CFSJPGNPDAZV7YY84=ad-network-permissions" />
