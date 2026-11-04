---
title: Criteo campaign configuration
metadata:
  keywords:
    - Criteo
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
  created_at: '2018-03-27T06:56:54Z'
  edited_at: '2026-09-09T13:00:13Z'
  id: 360000601785
  locale: en-us
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360000601785-Criteo-campaign-configuration
---
> **At a glance:** Criteo, an AppsFlyer ad network integrated partner, drives growth through machine-learning technology, data and performance at scale, and measurable ROI for its clients. In addition to click-based mobile attribution, Criteo also offers retargeting attribution, which you can record with AppsFlyer.

<div id="setting-up-criteo" />

## Setting up Criteo

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

<div id="activate-partner" />

### Activate Partner

On the **first visit**, you will need to toggle ON the ***Activate Partner*** button to enable the setup of integration tab parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">here</Anchor>.

<div id="note" />

> 📘 **Note**
>
> As an ALL-Installs network, Criteo prefers to receive postbacks for all new installs of your app from ANY source, including organic. It is recommended to select **Events attributed to any partner** to send all install postbacks to Criteo.

<div id="default-postbacks" />

### Default postbacks

Send automatic postbacks to Criteo following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Criteo.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Criteo.

<div id="in-app-events-settings" />

### In-app events settings

In this section, map your AppsFlyer events with Criteo via postbacks.

1. Toggle In-App Event Postbacks to ON.
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner.  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner.
3. Click **Add Event** to add an SDK Event to the list.
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Criteo's side.  <br />Obtain the corresponding Event ID from Criteo and set in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

<div id="warning" />

> ❗️ **Warning**
>
> <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#what-are-complex-inapp-events-and-how-do-i-set-them-up">Complex in-app events</Anchor> cause postback issues with Criteo. If you need the event to be fully mapped with Criteo, send separate events per user action (for example, send an Add to cart event per each added item). Use the in-app events raw data to group these events together.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. 

**Note**:

* Cost data requires an ROI360 subscription.
* Cost data from Criteo can be received only for downloads coming from Google Play or Apple App Store. For Android, cost data for third-party Android app stores isn't supported.
* Agency cost is only available via <Anchor target="_blank" href="/marketers/docs/view-aggregated-cost-data-for-attribution-links">click</Anchor>; not via API integration.

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">these integration instructions</Anchor>.

<Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue integration is not available for Criteo.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Criteo, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Criteo, the permissions tab is active and you can grant control to Criteo.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

Ad Network Permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKWB41KJ4XG0SGX69NHGYBYD=setting-up-criteo h_01HKWB41KJR5H4TDH80AG7JEYQ=integration-tab h_01HKWB41KJ2Z3RHNQ2XYJXJBKC=activate-partner h_01HKWB41KJRHZCFJ0CF7K3SMAS=note h_01HKWB41KJHZM1P6ZKJ1Q10C7D=default-postbacks inapp-events-settings=in-app-events-settings h_01HKWB41KJSDADQZYVAD13QYEH=in-app-events-settings h_01HDBZW9XF33FHR418MNVH6BS2=warning h_01HKWB41KKPPSGDVB1EKDXD6A5=attribution-link-tab h_01HKWB41KKW3EEF3VVMS9BSZ53=cost-tab h_01HKWB41KKFT61V0TWGM5P5X8H=ad-revenue-tab h_01HKWB41KKPFBWKE748V5FD5Y3=permissions-tab" />
