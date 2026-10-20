---
title: Sizmek campaign configuration
excerpt: >-
  Sizmek, an AppsFlyer ad network integrated partner, is an independent buy-side
  advertising platform and ad server. In addition to click-based mobile
  attribution, Sizmek offers view-through attribution, which can be recorded
  with AppsFlyer.
metadata:
  keywords:
    - Advertisers
    - Sizmek
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-03-30T12:40:13Z'
  edited_at: '2026-07-23T13:08:11Z'
  id: 115001605243
  locale: en-us
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115001605243-Sizmek-campaign-configuration
---
## Setting up Sizmek

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

Sizmek's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

> 📘 **Tip**
>
> * The [General Settings](/docs/set-up-an-integrated-partner#d-general-settings) step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partner

On the **first visit**, you will need to toggle ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

> 📘 **Note**
>
> As an ALL-Installs network, Sizmek prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to Sizmek.

### General settings

**Partner ID**

Sizmek connects with AppsFlyer via a unique Postback Tag ID. If you don't already have the Postback Tag ID, you must obtain it from Sizmek to continue with the integration.

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from Sizmek. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to Sizmek following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Sizmek.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Sizmek.

### In-app events settings

In this section you can map your AppsFlyer events with Sizmek via postbacks.

> 📘 **Note**
>
> To enable In-App Events, you must specify your Sizmek's onetagid.

1. Enter the advertiserid and password again.
2. Toggle In-App Event Postbacks to ON
3. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list
5. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Sizmek's side.  <br />Obtain the corresponding Event ID from Sizmek and set in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).  
[Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters).

**To generate an attribution link,** follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data integration is not supported for Sizmek

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue integration is not supported for Sizmek

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Sizmek, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Sizmek, the permissions tab is active and you can grant control to Sizmek.

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -*only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).

</Accordion>

<div data-zendesk-anchors="h_01HJS0B22MZSA0TXJZ48E27N8S=setting-up-sizmek h_01HJS0B22MABYZKHHD7BJ4BYWB=tip h_01HJS0B22MGEW9A5CCXHKGA7PH=integration-tab h_01HJS0B22MXNRKJ37DRZSJZ6YX=activate-partner h_01HJS0B22MT5NK2BKTFM5K34CH=note h_01HJS0B22M1J0A024DKMXY8C9V=general-settings h_01HJS0B22MM8RZN0T912VPPN6H=default-postbacks inapp-events-settings=in-app-events-settings h_01HJS0B22MT7674SP6TNMR7JVG=in-app-events-settings h_01HJS0B22NJYBS7HV6AT5G400Z=note-1 h_01HJS0B22NAZ40BHR338ZA4H7K=attribution-link-tab h_01HJS0B22NACQQ85MFFDGPMZ9N=cost-tab h_01HJS0B22NGAZBEXRQXF7J49R6=ad-revenue-tab h_01HJS0B22NMCXSPHJJX07CEHMK=permissions-tab h_01HJS0B22NBV1RM3GES734RWGB=ad-network-permissions" />
