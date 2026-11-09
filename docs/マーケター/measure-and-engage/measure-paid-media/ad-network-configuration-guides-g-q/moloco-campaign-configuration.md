---
title: MOLOCO campaign configuration
metadata:
  keywords:
    - Advertisers
    - Moloco
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-12-16T07:37:12Z'
  edited_at: '2026-10-01T00:26:36Z'
  id: 360000691978
  locale: ja
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ja/articles/360000691978
---
> **At a glance:** MOLOCO, an AppsFlyer integrated partner, turns user data into ad performance, enabling mobile businesses to execute marketing and advertising monetization programs.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/moloco.png?v=1" width="149px" />

## Setting up MOLOCO

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

MOLOCO's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">here</Anchor>.

> 👍 **Tip**
>
> * The <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#d-general-settings">General Settings</Anchor> step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable setup of the Integration tab parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation, please click <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">here</Anchor>.

> 📘 **Note**
>
> As an all-install network, MOLOCO prefers to receive postbacks for all new installs of your app from any source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to MOLOCO.

### General settings

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from MOLOCO. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to MOLOCO following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to MOLOCO.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to MOLOCO.

### In-app events settings

In this section you can map your AppsFlyer events with MOLOCO via postbacks.

1. Toggle In-App Event Postbacks to ON.
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list.
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">custom event mapping.</Anchor></li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<ul><li>**Text field:** Get the corresponding event ID from the partner.</li><li>**Drop-down box:** Select the most suitable pre-defined AppsFlyer event.</li><li>**As is**: Send the events as they are, without name mapping.</li></ul> |
| **for users from** | Select the sending option for the event:<ul><li>**This partner only**: send postbacks only when this event is attributed to this partner.</li><li>**All media sources, including organic**: send postbacks for events attributed to any partner, as well as organic events. According to Unity Ads, this option is recommended.</li></ul> |
| **including** | <ul><li>**No data (default)**: send only the event itself without the event value.</li><li>**Values and revenue**: send all the event parameters, **including** the revenue value (if exists in the event). According to Unity Ads, this option is recommended.</li><li>**Values without revenue**: send all the parameters **excluding** the revenue value.</li></ul> |

> 📘 **Note**
>
> You can send <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">ad revenue postbacks</Anchor> to MOLOCO using the`af_ad_revenue` event so they can optimize campaigns.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">these integration instructions</Anchor>.

Yesterday's data is available from Moloco at approximately 4 AM (depending on the time zone settings in your MOLOCO account). For example, If the event occurred on Monday, cost data can be pulled by AppsFlyer on Tuesday at approximately 4 AM. After pulling the MOLOCO cost data, AppsFlyer analyzes and prepares the data and once this process is complete, the data can be consumed.

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue integration is not available for this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant MOLOCO, whether the partner acts as an ad network, agency, or both. Note that even if attribution is disabled for MOLOCO, the permissions tab is active and you can grant control to MOLOCO.

#### ![MOLOCO_permissions.png](https://files.readme.io/f443306f1b56197709308c0a33e436dc26adc7a0e80e6c2887edc63a5697b6d4-360002616197.png) Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* **Allow to configure integration** - permit the partner to set up the integration tab (except in-app event postbacks)
* **Allow to configure in-app event postbacks** - permit the partner to setup in-app event postbacks mapping to itself on the Integration tab
* **Allow access to your retention report** - only to the partner's own retention data
* **Allow access to your Protect360 dashboard** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HBB9EEMJRHWC21713D60725N=setting-up-moloco h_01HBB9EEMJQ9VAMJMYG2T5FX0S=tip h_01HBB9EEMJ7X92Y5TK4YXXGSZX=integration-tab h_01HBB9EEMJ0EW14NZE9WCKJR1M=activate-partner h_01HBB9EEMJ55BQDJ1ZEJT136ZF=note h_01HBB9EEMJ2XSWFQZZFJ7J54VY=general-settings h_01HBB9EEMJV2SS4VJW0HW8D12R=default-postbacks inapp-events-settings=in-app-events-settings h_01HBB9EEMJE2X04XZGMSJSSXAT=in-app-events-settings h_01HBB9EEMJ6WA79D7R4BG8S9HS=note-1 h_01HBB9EEMJXGFHY28K2DDHKBF8=attribution-link-tab h_01HBB9EEMJT7VSNFQJC86TS1YX=cost-tab h_01HBB9EEMJ61WDHNPKMW5A1YKM=ad-revenue-tab h_01HBB9EEMJ3Z40S2A6FZG7RJ6K=permissions-tab ad-network-permissions=-ad-network-permissions h_01HBB9EEMJ54Y8KJBK4395ENPJ=-ad-network-permissions" />
