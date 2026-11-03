---
title: ByteDance Ads China—campaign configuration
metadata:
  keywords:
    - bytedance
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
  created_at: '2017-06-18T07:05:42Z'
  edited_at: '2026-10-01T00:28:50Z'
  id: 115003019403
  locale: ja
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ja/articles/115003019403
---
> **At a glance:** ByteDance Ads China (Ocean Engine), an AppsFlyer integrated partner, is an Internet technology company operating several machine learning-enabled content platforms.

> 📘 **Note**
>
> If you want to promote your Android Apps with ByteDance Ads China, you are required to send your OAID to AppsFlyer SDK according to the instructions in the <Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">AppsFlyer SDK Integration - Android</Anchor>. Google Play service is blocked in China, OAID is the most popular Android Device ID for ad attribution.

In addition to click-based mobile attribution, ByteDance Ads China also offers view-through attribution, which you can record with AppsFlyer.

To configure your campaigns with ByteDance Ads China, follow the steps below.

## Setting up ByteDance Ads China

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

Tip

> 👍 **Tip**
>
> * The <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#d-general-settings">General Settings</Anchor> step in the Integration tab is **mandatory** for all partners.
> * All the rest of the steps are either descriptive or **optional**.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partners

On the **first visit** here, you must toggle ON the ***Activate Partner*** button to enable the setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation, click <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">here</Anchor>.

General Settings

**Enable View-Through attribution**

[![](https://files.readme.io/3340b894428079e37c238cd78883669abd53cd6895165c5f9b5ea90d27d570c9-50612201111697.png)](https://files.readme.io/3340b894428079e37c238cd78883669abd53cd6895165c5f9b5ea90d27d570c9-50612201111697.png)

Toggle this to **ON** if you want to attribute view-through installs from ByteDance Ads China. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

AppsFlyer can send automatic postbacks to ByteDance Ads China following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

![bytedance-default-postbacks.png](https://files.readme.io/5f3cb637fb9ff652533fcfd9c02ea8dc1768e0e1c1686a180ea18c0d2e09309f-50612201121425.png)

### In-app events settings

In this section, you can map your AppsFlyer events with ByteDance Ads China via postbacks.

1. Turn In-App Event Postbacks on.
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner.
3. Click **Add Event** to add an SDK Event to the list.
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">custom event mapping.</Anchor></li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<ul><li>**Text field:** Get the corresponding event ID from the partner.</li><li>**Drop-down box:** Select the most suitable pre-defined AppsFlyer event.</li><li>**As is**: Send the events as they are, without mapping the event name.</li></ul> |
| **for users from** | Select the sending option for the event:<ul><li>**This partner only**: Send postbacks only when the event is attributed to this partner—meaning, the user who performed it came from this partner.</li><li>**All media sources including organic**: Send postbacks for events attributed to any partner and for organic events—meaning, the user who performed it came from any media source.</li></ul> |
| **including** | Select which event data to share with the partner in the postback:<ul><li>**No values & no revenue**: Send just the event itself without any parameters (values or revenue).</li><li>**Values & no revenue**: Send all the parameters **excluding** the revenue value.</li><li>**Values & revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

### Click attribution link

Once you have generated the attribution link, complete the campaign setup process on the ByteDance Ads China site.

**1. Create Conversion Tracking in Ocean Engine.**

Log in to Ocean Engine ([https://ad.oceanengine.com/](https://ad.oceanengine.com/)) > **Library** > **Conversion Tracking**.

![OE_dashboard_1.png](https://files.readme.io/fda140ac7e3023033880b04ed500a675ae78187e4eb694ee200922b729ab119f-50612185108497.png)

Click on **Tracking application** and create a **New Application Transformation**.

![OE_dashboard_2.png](https://files.readme.io/dbf0c13c23d21d08c195a4ab747e5de0986cb01f5ebde98f6c701ce731480958-50612185109009.png)

Click the **API** method.

![OE_dashboard3.png](https://files.readme.io/70e7f6ca01c532fafb8f2ab7d31d6de51494f11749329c1c1333d1da6f28f284-50612185110417.png)

In the Monitoring link part, enter AppsFlyer click attribution link and/or impression attribution link.

![dashboard4.png](https://files.readme.io/d36ec92a03062fc7ee169bb1ff3863722343577f3ee2b12779065b3e52731348-50612201124369.png)

**2. Finish the Attribution Test Following the Instructions on the Website**.

**3. Create an Ad Campaign with the Newly Created Conversion**.

Go to **New Ad** >> **Set Budget and Bid** select the conversion you created for this app.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. Note that AppsFlyer doesn't support the ad-level cost data for ByteDance, except for campaigns running on the v1.0 ByteDance system.

### API dimensions supported

| Geo | Media source | Campaign | Adset | Ad | Other |
| --- | --- | --- | --- | --- | --- |
| Yes | - | Yes | Yes | No<br /><br />(Ads are only supported for v1.0 ByteDance campaigns) | - |

**To enable ByteDance Ads China cost API**:

1. In the integrated partner Cost tab, enable ***Get Cost Data***.
2. Log in to ByteDance Ads China.
3. Click ***Save Cost***.
   * You have successfully completed the procedure. API is active. AppsFlyer collects data from the partner 6 times a day, on average once every four hours.
   * The cost tab shows the status of your cost integration and the last time AppsFlyer managed to pull matching cost data.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

This section is relevant if you are acting as a publisher, displaying ads of the partner to your users. As such, you would certainly like to measure the engagement of your users acquired from different sources, to find the most profitable sources for you.

**To enable the ad revenue API**:

* Follow <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">these integration instructions</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant ByteDance Ads China, whether the partner acts as an ad network, agency, or both. Note that even if attribution is disabled for ByteDance Ads China, the permissions tab is active and you can grant control to ByteDance Ads China.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HJR1HREQDCQDN6JZRPD356VS=note h_01HJR1HREQ6YAW1WPX2BTZS2R7=setting-up-bytedance-ads-china h_01HJR1HRERBBZFKBHH78BK6QW2=integration-tab h_01HJR1HRER22XX94R1WEQK60GJ=activate-partners h_01HJR1HRERMXHAAGXEFJS4ZS8C=default-postbacks inapp-events-settings=in-app-events-settings h_01HJR1HRERF2Y205KP0J8HZFR3=in-app-events-settings h_01HJR1HRER391J6PD9Q0M1MW3F=attribution-link-tab h_01HJR1HRERCHNHQGX3X1E1ARDK=click-attribution-link h_01HJR1HRER1G4K3PQG1Z7M6CCX=cost-tab h_01HJR1HRES86BJM4ABQ0B414F1=api-dimensions-supported h_01HJR1HRES470MKXS1S08X202D=ad-revenue-tab h_01HJR1HRESJ7KNFZ9TDHZKESJ7=permissions-tab h_01HJR1HRESZCC6YV9D40YYSYX0=ad-network-permissions" />
