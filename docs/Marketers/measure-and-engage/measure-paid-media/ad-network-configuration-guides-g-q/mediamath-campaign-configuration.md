---
title: MediaMath campaign configuration
metadata:
  keywords:
    - Advertisers
    - MediaMath
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-10-06T14:55:35Z'
  edited_at: '2026-07-23T13:08:45Z'
  id: 214956583
  locale: en-us
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/214956583-MediaMath-campaign-configuration
---
> **At a glance:** MediaMath, an AppsFlyer integrated partner, specializes in programmatic marketing technology, with data management platforms and omnichannel DSPs. In addition to click-based mobile attribution, MediaMath also offers retargeting and view-through attribution, which you can record with AppsFlyer.

![](https://cdn.appsflyer.com/marketplace/static/logo/mediamath.png)

<div id="setting-up-mediamath" />

## Setting up Mediamath

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

Enabling **Advanced Data Sharing** will allow AppsFlyer to send MediaMath the attributed source and referrer data for install postbacks. The ‘CB\_AD’ toggle does the same thing for in-app events.

MediaMath's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">here</Anchor>.

<div id="tip" />

> 👍 **Tip**
>
> * The <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#d-general-settings">General Settings</Anchor> step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**

<div id="integration-tab" />

<Accordion title="Integration tab">

<div id="activate-partner" />

### Activate partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">here</Anchor>.

<div id="note" />

> 📘 **Note**
>
> As an ALL-Installs network, MediaMath prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to MediaMath.

<div id="general-settings" />

### General settings

**Partner ID**

MediaMath connects with AppsFlyer via unique Advertiser ID and Pixel ID. If you don't already have the Advertiser ID and Pixel ID, you must obtain it from MediaMath to continue with the integration.

**Advanced Data Sharing**

Toggle this to ON if you want AppsFlyer to send additional information to MediaMath.

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from MediaMath. The view-through lookback slider is available on the attribution link tab (described below).

<div id="default-postbacks" />

### Default postbacks

Send automatic postbacks to MediaMath following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to MediaMath.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to MediaMath.

<div id="in-app-events-settings" />

### In-app events settings

In this section you can map your AppsFlyer events with MediaMath via postbacks.

1. Enter the Advertiser ID again.
2. Toggle In-App Event Postbacks to ON
3. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list
5. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated with your app or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on MediaMath's side.  <br />Obtain the corresponding Event ID from MediaMath and set it in the text field. |
| **Send Revenue** | **When unchecked** - Send all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - Send all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is not supported by MediaMath.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported by MediaMath.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant MediaMath, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for MediaMath, the permissions tab is active and you can grant control to MediaMath.

<div id="ad-network-permissions" />

### Ad network permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKW2X0DS3WRS3N268E2SH2HT=setting-up-mediamath h_01HKW2X0DSW1P1RZGK26RS20QM=tip h_01HKW2X0DSSQVB3MSSEK1HB7V7=integration-tab h_01HKW2X0DS26H7GFZKBY3VJV59=activate-partner h_01HKW2X0DSBYTBEDCM4YCPHEPA=note h_01HKW2X0DSQWZY0KPS42RQKCFB=general-settings h_01HKW2X0DSAM76C6S22VMVTPGZ=default-postbacks inapp-events-settings=in-app-events-settings h_01HKW2X0DSS1TN1B4GWP8SHY6X=in-app-events-settings h_01HKW2X0DSWT4VW9J5DMYZ2DPJ=attribution-link-tab h_01HKW2X0DS69CD1QKF8CZM3MN4=cost-tab h_01HKW2X0DS4B391FNY0W6W9YAK=ad-revenue-tab h_01HKW2X0DTC7BR20T5FPP8PW0X=permissions-tab h_01HKW2X0DTFX6A7X3F67WW0XNW=ad-network-permissions" />
