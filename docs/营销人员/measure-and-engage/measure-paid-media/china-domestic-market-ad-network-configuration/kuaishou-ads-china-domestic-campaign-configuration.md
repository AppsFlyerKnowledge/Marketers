---
title: Kuaishou Ads (China Domestic) campaign configuration
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-06-05T06:07:11Z'
  edited_at: '2026-10-13T01:17:51Z'
  id: 360001748437
  locale: zh-cn
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/zh-cn/articles/360001748437
---
> **At a glance:** Kuaishou is an AppsFlyer ad network integrated partner.

## Setting Up Kuaishou

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

Kuaishou's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">here</Anchor>.

### Default postbacks

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" />

### In-app events settings

In this section, you can map your AppsFlyer events with Kuaishou via postbacks.

<Image align="center" alt="mceclip0.png" src="https://files.readme.io/74a4c9e81ac69f65079f5e214de90dc8725f8aedaf59c7ee4d9a3d947a853a0b-50899821661713.png" />

1. Toggle In-App Event Postbacks to ON
2. Click **Add Event** to add an SDK Event to the list
3. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on iQIYI Ads side.  <br />Obtain the corresponding Event ID from iQIYI Ads and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

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

In this tab, you can select the permissions to grant Kuaishou, whether the partner acts as an ad network, an agency, or even both. Note that even if attribution is disabled for Kuaishou, the permissions tab is active and you can grant control to Kuaishou.

<Image align="center" alt="rtb_house-permissions-new.png" src="https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png" />

### Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to setup the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKW6VK4HFZYAY2XC7Y6QGXD4=setting-up-kuaishou h_01HKW6VK4HMKVSRH9PXH6ASDGJ=integration-tab h_01HKW6VK4HWBBP9W3BMTC8KQBJ=activate-partner h_01HKW6VK4H4SQP4Q5QXC683R38=default-postbacks inapp-events-settings=in-app-events-settings h_01HKW6VK4HW50X9Z2WJ5X9RP90=in-app-events-settings h_01HKW6VK4HKFCXKQNN0RY16B10=attribution-link-tab h_01HKW6VK4JSK4JFC0XD2JM7JJ6=cost-tab h_01HKW6VK4JSCS6M01R6SF1V9YB=ad-revenue-tab h_01HKW6VK4JEEBKB2G0H3WFRB8W=permissions-tab h_01HKW6VK4JY5YG805PZQ7EG1VM=ad-network-permissions" />
