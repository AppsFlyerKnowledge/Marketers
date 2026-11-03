---
title: RTB House campaign configuration
metadata:
  keywords:
    - Advertisers
    - RTB
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-07-05T08:30:48Z'
  edited_at: '2026-10-13T01:12:39Z'
  id: 360001274325
  locale: zh-cn
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/zh-cn/articles/360001274325
---
> **At a glance:** RTB House, an AppsFlyer ad network integrated partner, provides retargeting technology for e-commerce and gaming companies. RTB House has developed its own retargeting solution, based on deep learning algorithms, for purchasing online ads in the Real-Time Bidding model. In addition to click-based mobile attribution, RTB House offers retargeting attribution, which can be recorded with AppsFlyer.

## Setting up RTB House

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

RTB House's configuration window includes 3 active tabs: **Integration, Attribution link**, and **Permissions**. Click on the items below to read about the tabs setup.

> 👍 **Tip**
>
> * The <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#d-general-settings">General Settings</Anchor> step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle on **Activate Partner** to enable setting up the integration parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">here</Anchor>.

### Default postbacks

Send automatic postbacks to RTB House following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

> 📘 **Note**
>
> As an ALL-Installs network, RTB House prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to RTB House.

### In-app events settings

In this section, you can map your AppsFlyer events with RTB House via postbacks.

#### Region

Enter the region of your RTB House data center. Possible options: **emea**, **us**, **asia**.

#### In-app event postback settings

1. Toggle on In-App Event Postbacks
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on RTB House's side.  <br />Obtain the corresponding Event ID from RTB House and set in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Create and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To create an attribution link,** follow <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is supported in the integration with this partner via <Anchor target="_blank" href="/partners/zh/docs/incost-api-for-ad-networks">InCost API</Anchor>.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant RTB House, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for RTB House, the permissions tab is active and you can grant control to RTB House.

### Ad network permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to set up in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HJRZXXH277REM62TJA907WX0=setting-up-rtb-house h_01HJRZXXH2P8Q15V7DKQT7AVTT=tip h_01HJRZXXH2DJ8WMYPQ0NV08R05=integration-tab h_01HJRZXXH309BVZZ2VRRJQ02N8=activate-partner h_01HJRZXXH3X46N8KQ8GTP4BYYP=default-postbacks h_01HJRZXXH3SDCH4K86YV4VC5VH=note inapp-events-settings=in-app-events-settings h_01HJRZXXH3HJP28D34NW8A8EZN=in-app-events-settings h_01HJRZXXH3E7STC8XVRDP39282=region inapp-event-postback-settings=in-app-event-postback-settings h_01HJRZXXH3336ZJZZD1P8408GP=in-app-event-postback-settings h_01HJRZXXH3R7F4QA9PYWY7EYZZ=attribution-link-tab h_01HJRZXXH30PDV0S32THB0C4FM=cost-tab h_01HJRZXXH37CHDD10ASEXPN7VH=ad-revenue-tab h_01HJRZXXH3CASE2ZTRJDSW9545=permissions-tab h_01HJRZXXH3TJSTVG4Z8ZDQBATG=ad-network-permissions" />
