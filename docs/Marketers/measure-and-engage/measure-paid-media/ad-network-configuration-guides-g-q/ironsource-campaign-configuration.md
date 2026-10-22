---
title: ironSource campaign configuration
metadata:
  keywords:
    - Supersonic
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
  created_at: '2016-03-06T10:47:23Z'
  edited_at: '2026-08-14T00:01:08Z'
  id: 208005096
  locale: en-us
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/208005096-ironSource-campaign-configuration
---
> **At a glance:** ironSource, an AppsFlyer integrated partner, builds monetization, engagement, analytics, and discovery tools for app developers, device manufacturers, mobile carriers, and advertisers. In addition to click-based mobile attribution, ironSource also offers cost, ad revenue, retargeting and view-through attribution, which you can record with AppsFlyer.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ironsource.png?v=1" width="213px" />

## Setting up ironSource

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

> 📘 **Note**
>
> As an all-installs network, ironSource prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to ironSource.

ironSource's configuration window includes 5 tabs: Integration, Attribution link, Cost, Ad Revenue, and Permissions. Click on the items below to read about the tabs setup.

> 📘 **Note**
>
> * The General Settings step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partners

On the **first visit** here, you will need to turn on the **Activate Partner** toggle to enable setup of the integration tab parameters. The toggle must stay on for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">here</Anchor>.

#### Advanced Privacy

For iOS apps only, when **Advanced Privacy (for iOS 14.5+ and later)** is turned on, you can <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#b-advanced-privacy">control what data is shared</Anchor> with ironSource via postbacks and reports.

### Transaction ID

For iOS apps only, when **Share SKAN transaction ID** is turned on, you're allowing AppsFlyer to <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">share the transaction ID of SKAdNetwork postbacks</Anchor> with ironSource. By doing so, ironSource could decode your SKAdNetwork Conversion Values.

> 📘 **Note**
>
> For SKAN interoperation with AppsFlyer, contact your ironSource account manager to <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/general/universal-skan-reporting/#step-1">enable sending SKAN data to MMPs</Anchor>.

### General settings

**Advertiser ID**

ironSource connects with AppsFlyer via a unique advertiser ID (6-digit number) and a password. If you don't already have the advertiser ID and password, you must obtain them from ironSource to continue with the integration. Otherwise, copy the ID and the password and paste them into the respective fields.

### Install and Re-engagement attribution

These two toggles enable attributing to ironSource new installs and re-attributions of users who **viewed** your ad but **didn’t click** on it. Learn more about <Anchor target="_blank" href="/marketers/docs/measure-view-through-engagements">view-through attribution</Anchor>.

**To attribute new installs:**

1. Turn on **Install view-through attribution**.
2. Configure the length of the **view-through** lookback window in the [Attribution link tab](/docs/ironsource-campaign-configuration#attribution-link-tab).

**To attribute new re-engagements of existing users:**

1. Turn on **Re-engagement view-through attribution**.
2. Configure the length of the **view-through** lookback window in the [Attribution link tab](/docs/ironsource-campaign-configuration#attribution-link-tab).

### Default postbacks

Send automatic postbacks to ironSource following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to ironSource.  
Select **Events attributed to any partner, or organic** to have your entire user base available to be reported to ironSource.

> 📘 **Note**
>
> As an all-installs network, ironSource prefers to receive postbacks for all new installs of your app from any source, including organic. To do so, select **Events attributed to any partner, or organic** to send all install postbacks to ironSource.

### In-app event postbacks

Configure mapping of in-app events with ironSource events, sent via postbacks:

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation, and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#custom-events">custom event mapping.</Anchor></li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<ul><li>**Text field:** Get the corresponding event ID from the partner.</li><li>**Drop-down box:** Select the most suitable pre-defined AppsFlyer event.</li><li>**As is**: Send the events as they are, without name mapping.</li></ul> |
| **for users from** | Select the sending option for the event:<ul><li>**This partner only**: Send postbacks only when this event is attributed to this partner.</li><li>**All media sources including organic**: Send postbacks for events attributed to any partner, as well as organic events.</li></ul> |
| **including** | <ul><li>**No data (default)**: Send only the event itself without any event values.</li><li>**Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</li><li>**Values without revenue**: Send all the parameters **excluding** the revenue value.</li></ul> |

3. [Optional] Click the **Add condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/a97c5e34c264ddfa9f94b894520f849a3e59b42be14839ee37c71a5b6cc5ebd7-17612766801425.png" width="30px" />icon to <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">set conditions</Anchor> for an event.
4. Click **Save integration**.
5. [Optional]After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
   1. From the top-left corner, under the partner name, click the app name to open the list of apps.
   2. Select a different app from the drop-down list.
   3. Repeat the <Anchor target="_blank" href="/marketers/docs/amazon-ads-campaign-configuration#integration-tab">integration steps</Anchor> for the selected app.

> 📘 **Note**
>
> * For iOS apps only: Your control over data shared with the partner via postbacks and <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions">reports</Anchor> depends on the **Advanced Privacy (for iOS 14.5+ and later)** <Anchor target="_blank" href="/marketers/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">toggle state</Anchor>.
> * You can send <Anchor target="_blank" href="/marketers/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">ad revenue postbacks</Anchor> to ironSource so they can optimize campaigns using ad revenue data:
>   * **Event name:** af\_ad\_revenue
>   * **Mapped to:** adRevenue

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">More about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* <Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">Follow these integration instructions</Anchor>

<Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

If you display ads in the app sent by Unity LevelPlay mediation (formerly ironSource) or by the ironSource monetization network, this section is relevant.

The following options for ad revenue granularity are available:

* Aggregate level (via S2S API).
* Device level (via S2S API).
* Impression level (via SDK).
* Impression-level (via SDK) with device-level (via S2S API)

Learn more about <Anchor target="_blank" href="/marketers/docs/roi360-guide-ad-revenue-attribution">ad revenue attribution</Anchor>.

**To enable the ad revenue integration**:

* Follow <Anchor target="_blank" href="/marketers/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">these integration instructions</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant ironSource, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for ironSource, the permissions tab is active and you can grant control to ironSource.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* **Allow to configure integration** - permit the partner to set up the integration tab (except in-app event postbacks)
* **Allow to configure in-app event postbacks** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* **Allow access to your retention report** - only to the partner's own retention data
* **Allow access to your aggregate loyal user data** - only to the partner's own loyal user data
* **Allow access to your aggregate in-app events data** - only to the partner's own in-app events data
* **Allow access to your aggregate revenue data** - only to the revenue data attributed to the partner
* **Allow access to your Protect360 dashboard** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

* **Main toggle** - Set to On to reveal the agency permissions options
* **Allow access to your retention report** - only to the agency's own retention data
* **Allow access to aggregate organic data**
* **Allow to configure in-app event postbacks** - permit the agency to setup in-app event postbacks mapping to itself on the integration tab

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#agency-permissions">agency permissions</Anchor>.

</Accordion>

</Accordion>

<div data-zendesk-anchors="h_01KZX3MPJ9HY5WJB3MS65SZXNY=setting-up-ironsource h_01HKW1E1KBG121H7YJBW2SZS6E=note h_01HCFHXQQ8XYCKWPVTMK8HF165=integration-tab h_01HCFHXQQ8HCXPEWR4CWY55M2H=activate-partners h_01HCFHXQQ8ABQYRSBGC7Z1F1SV=advanced-privacy h_01HCFHXQQ8Q3BX7GSGD5MH4QT8=transaction-id h_01HCFHXQQ8D26KT5E6YEQ50DA4=note-2 h_01HCFHXQQ8J0ZC9FGCNTPMKHK6=general-settings install-and-reengagement-attribution=install-and-re-engagement-attribution h_01HCFHXQQ8V2E8982XRSY4G50F=install-and-re-engagement-attribution h_01HCFHXQQ8Q27JXG2V7G4XZX43=default-postbacks h_01HCFHXQQ8XZ6H3733GPR3ZFYE=note-3 inapp-event-postbacks=in-app-event-postbacks h_01HCFHXQQ891GH196XFRXY8MYS=in-app-event-postbacks h_01HCFHXQQ8VF25W10CWQHTEAYW=note-4 h_01HCFHXQQ8AYNTCH9GHZJG594E=attribution-link-tab h_01HCFHXQQ87EBRW9NBY58XYFGP=cost-tab h_01HCFHXQQ8XZ8XQFH3XRFVHRZV=ad-revenue-tab h_01HCFHXQQ891P7ET9Q4BSQWJXT=permissions-tab h_01HCFHXQQ86VNX9WRFEZECYV7R=ad-network-permissions h_01HCFHXQQ936CQ1FVHCRC58H4C=agency-permissions" />
