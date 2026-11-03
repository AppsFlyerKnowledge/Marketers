---
title: Xiaomi Ads Network campaign configuration
metadata:
  keywords:
    - XiaoMi
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
  created_at: '2017-03-28T11:08:46Z'
  edited_at: '2026-10-13T01:19:26Z'
  id: 115001605286
  locale: ko
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ko/articles/115001605286
---
> **At a glance:** Xiaomi, an AppsFlyer ad network integrated partner, operates the Xiaomi Android App Store which ranks in the Top 5 Android App Distribution Platforms in China, with 5 billion app downloads per month. In addition to click-based mobile attribution, Xiaomi also offers view-through attribution, which you can record with AppsFlyer.

## Setting up Xiaomi

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

Xiaomi's configuration window includes 3 active tabs: Integration, Attribution link and Permissions. Click on the items below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partner

On the **first visit**, you will need to toggle ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">here</Anchor>.

General Settings

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from Xiaomi. The view-through lookback slider is available on the attribution link tab (described below).

![](https://files.readme.io/c01732abe8d1bb3c68acdf84bab50cc46d4f4923b7220e3ca51c399074113c1e-50899866307217.png)

### Default postbacks

AppsFlyer can send automatic postbacks to Xiaomi following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

![xiaomi-default-postbacks.png](https://files.readme.io/ae215140550604649e4345729a7106fa08c15713e003cec534199e3889122b5e-50899866309265.png)

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data integration is currently not supported with Xiaomi.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue integration is currently not supported with Xiaomi.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Xiaomi, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for Xiaomi, the permissions tab is active and you can grant control to Xiaomi.

![ad_network_permissions.png](https://files.readme.io/8d8c3d5eb38384d92e52afdc01b0631d8fe5c9590dd618386cbf6ce90fc978f3-50612307452817.png)

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to setup the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKW6ZDW8D6CD60S25FVQ80FC=setting-up-xiaomi h_01HKW6ZDW8JK323YYPCSYZ1PKB=integration-tab h_01HKW6ZDW8B60R3QAZRMPHVC31=activate-partner h_01HKW6ZDW8GW51XT1XXPE7DZ02=default-postbacks h_01HKW6ZDW8ERH0MQ2W2YGC5SXB=attribution-link-tab h_01HKW6ZDW8SHGTTVC4V7R1R90K=cost-tab h_01HKW6ZDW8ENFJN342XN66TM19=ad-revenue-tab h_01HKW6ZDW89CE47NF67TJM4AX9=permissions-tab h_01HKW6ZDW8Y85VBJPQ40MZ5CV5=ad-network-permissions" />
