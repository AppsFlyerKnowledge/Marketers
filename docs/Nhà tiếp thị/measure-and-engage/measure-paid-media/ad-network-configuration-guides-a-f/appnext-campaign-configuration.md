---
title: Appnext campaign configuration
metadata:
  keywords:
    - Advertisers
    - appnext
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-08-20T07:46:36Z'
  edited_at: '2026-09-09T12:42:49Z'
  id: 360001407109
  locale: en-us
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360001407109-Appnext-campaign-configuration
---
> **At a glance:** Appnext, an AppsFlyer ad network integrated partner, uses technology and data solutions for premium mobile monetization, app marketing, and re-engagement. In addition to click-based mobile attribution, Appnext also offers cost, retargeting and view-through attribution, which you can record with AppsFlyer.

## Setting up Appnext

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partner

On the **first visit** here, you will need to toggle. ON the **Activate Partner** button to enable setup of the integration tab's parameters. The toggle must be set to ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">here</Anchor>.

The Integration Tab is divided into different sections as described below.

### General settings

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from Appnext. The view-through lookback slider is available on the attribution link tab (described below).

![appnext_msc_new_2.png](https://files.readme.io/f974ed2ccc5550cebb87e5070d177fb88efb0c82fe15cbc300979d54b1297a6a-50705658863249.png)

### Default postbacks

Send automatic postbacks to Appnext following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Note: for installs, you can select either **Only events attributed to this partner** (for events coming only from users attributed to Appnext), or **Events attributed to any partner or organic** (for events coming from all partners). For rejected installs and re-engagements, **Only events attributed to this partner** can be sent via a postback.

> 📘 **Note**
>
> As an ALL-Installs network, Appnext prefers to receive postbacks for all new installs of your app from ANY source, including organic. It is recommended to select **Events attributed to any partner** to send all install postbacks to Appnext.

### In-app events settings

In this section, you can map your AppsFlyer events with Appnext via postbacks.

1. Toggle In-App Event Postbacks to ON.
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list.
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server-to-server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Appnext's side.  <br />Obtain the corresponding Event ID from Appnext and set in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/vi/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Appnext automatically sends CPI cost data on the attribution link for all installs.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue integration is not available for this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Appnext. Note that even if attribution is disabled for Appnext, the permissions tab is active and you can grant control to Appnext.

### Ad network permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* **Allow to configure integration** - permit the partner to set up the integration tab (except in-app event postbacks)
* **Allow to configure in-app event postbacks** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* **Allow access to your retention report** - only to the partner's own retention data
* **Allow access to your aggregate loyal user data** - only to the partner's own loyal user data
* **Allow access to your aggregate in-app events data** - only to the partner's own in-app events data
* **Allow access to your aggregate revenue data** - only to the revenue data attributed to the partner
* **Allow access to your Protect360 dashboard** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

* **Main toggle** - Set to ON to reveal the agency permissions options
* **Allow access to your retention report** - only to the agency's own retention data
* **Allow access to aggregate organic data**
* **Allow to configure in-app event postbacks** - permit the agency to setup in-app event postbacks mapping to itself on the integration tab

Learn more about granting <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#cấp-quyền-cho-đại-lý">agency permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKW999WPN45PNK2XN3RD9NTX=setting-up-appnext h_01HKW999WPT67XT04P3GG7PTBS=integration-tab h_01HKW999WPB6KKPN9MZ8N1GM70=activate-partner h_01HKW999WQK8P62W20K1AWHBEN=general-settings h_01HKW999WQS7FM0TE95G7R56M8=default-postbacks h_01HKW999WQP04CC7YPTEJ4E6AJ=note inapp-events-settings=in-app-events-settings h_01HKW999WQFR3DMNGEJFS6ZS7N=in-app-events-settings h_01HKW999WQWFDDS13K2V3F2G3A=attribution-link-tab h_01HKW999WQKB9VNRSVV6JM15ES=cost-tab h_01HKW999WQ1C5CDN4JDYE1XMRZ=ad-revenue-tab h_01HKW999WQ9K1376YHF92GYW45=permissions-tab h_01HKW999WQG5KB588ESQ5XS4HM=ad-network-permissions h_01HKW999WQZMAX4MSM3B49H63W=agency-permissions" />
