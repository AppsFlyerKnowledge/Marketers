---
title: Yandex Direct campaign configuration
metadata:
  keywords:
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
  created_at: '2021-03-30T10:52:06Z'
  edited_at: '2026-06-16T11:43:21Z'
  id: 360018910138
  locale: en-us
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360018910138-Yandex-Direct-campaign-configuration
---
> **At a glance:** Yandex Direct is an advertising platform that allows you to run user acquisition and retargeting campaigns on Yandex Search, as well as on thousands of apps and websites in the Yandex Advertising Network.

<div id="set-up-yandex-direct" />

## Set up Yandex Direct

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

Yandex Direct's configuration window includes 3 active tabs: **Integration, Attribution link**, and **Permissions**.

<div id="integration-tab" />

<Accordion title="Integration tab">

<div id="activate-partner" />

### Activate partner

On the **first visit** here, you will need to turn on **Activate partner** to enable the setup of the integration tab's parameters. The toggle must be on for as long as you work with the partner.  
Learn more about <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">partner activation/deactivation</Anchor>.

<div id="advanced-privacy" />

### Advanced privacy

For iOS apps only, **Enable advanced privacy (for iOS 14.5 and above)** controls what data is shared with the partner via postbacks and reports. <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#b-advanced-privacy">Learn more about advanced privacy</Anchor>.

<div id="transaction-id" />

### Transaction ID

For iOS apps only. When **Share SKAN transaction ID** is turned on, you're <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">sharing the transaction ID of SKAdNetwork postbacks</Anchor> with the partner. By doing so, the partner could decode your SKAdNetwork Conversion Values.

<div id="general-settings" />

### General settings

The following general settings are available for Yandex Direct.

<div id="yandex-ecom-feed-counter-id" />

#### Yandex Ecom Feed Counter ID

Enter the Metrika tag number in **Yandex Ecom Feed Counter ID** if you're running Smart Banner campaigns with your product feed.

<div id="yandex-app-id" />

#### Yandex app ID

Enter the **Yandex App ID** derived from Yandex Direct.

<div id="default-postbacks" />

### Default postbacks

Send automatic postbacks to Yandex Direct following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **This partner only** for events coming only from users attributed to Yandex Direct.  
Select **All media sources, including organic** to have your entire user base available to be reported to Yandex Direct.

As an all-installs network, Yandex Direct prefers to receive postbacks for all new installs of your app from all sources, and they recommended selecting **All media sources, including organic**.

<div id="in-app-events-postbacks" />

### In-app events postbacks

In this section, you can configure in-app event postbacks that are sent to Yandex Direct.

1. Turn **In-app event postbacks** on.
2. Set the **In-app event postback window**, if required (read more about <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#in-app-event-postback-window">in-app event postback window configuration</Anchor>).
3. Click **Add event** to add an SDK Event to the list.
4. <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">Complete the required parameters</Anchor>.
5. Click **Save integration**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">these integration instructions</Anchor>. **Note**: Add campaign ID (af\_c\_id=`{campaign_id}`) to your links to ensure accurate cost reporting. <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">Learn more</Anchor>

<Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue data is not available for this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Yandex Direct, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Yandex Direct, the Permissions tab is active and you can grant control to Yandex Direct. <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">Configure permissions to Yandex Direct</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HJZW81YDFP6ZV188XP3H4H54=set-up-yandex-direct h_01HJZW81YD3S8BEE6MNT30VYZH=integration-tab h_01HJZW81YD1JA5N01HT248PR8K=activate-partner h_01HJZW81YDNWAEKA2DP0QPPQRC=advanced-privacy h_01HJZW81YD8QEETTP4NSG2QCPQ=transaction-id h_01HJZW81YDT69PGFTJMQ8WTYN2=general-settings h_01HJZW81YD18MW2BNGTZCZM7ZW=yandex-ecom-feed-counter-id h_01HJZW81YDTQ0Q4H39GVJMHYNG=yandex-app-id h_01HJZW81YDZDYDES5ZPRQ5BEC3=default-postbacks inapp-events-postbacks=in-app-events-postbacks h_01HJZW81YDMTRZ2VG8S9B48GTD=in-app-events-postbacks h_01HJZW81YE8XP6Q9RA9XTCKX2T=attribution-link-tab h_01HJZW81YES6M13VVJMTAB6KXQ=cost-tab h_01HJZW81YE7CYXEDFZKWZYVYET=ad-revenue-tab h_01HJZW81YERG3X6RG9Z2CM3YSF=permissions-tab" />
