---
title: Tapjoy campaign configuration
excerpt: >-
  Tapjoy, an AppsFlyer ad network integrated partner, is an advertising and app
  monetization platform. In addition to click-based mobile attribution, Tapjoy
  offers view-through attribution, which can be recorded with AppsFlyer.
metadata:
  keywords:
    - Tapjoy
    - SDK
    - configuration
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2015-06-10T14:19:38Z'
  edited_at: '2026-09-08T13:50:56Z'
  id: 207033956
  locale: en-us
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207033956-Tapjoy-campaign-configuration
---
To configure your campaigns with Tapjoy, follow the steps below.

## Setting up Tapjoy

**Prerequisite:** An account with the partner. If you don't have
an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to
   **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the
   **Activate partner** toggle.   
   **Note:** The toggle
   **must stay on (active) as long as you work with the partner**.
   [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn
   more about
   [partner integrations.](/docs/set-up-an-integrated-partner)

<div id="integration-tab" />

<Accordion title="Integration tab">

The ***Integration Tab*** is divided into different sections as described below.

### Activate partners

The [partner must be activated](/docs/partner-activation-deactivation#activate-a-partner-integration) by switching on the ***Activate partner*** toggle on the first visit, to enable its setup.

### General settings

#### app\_id

Tapjoy connects with AppsFlyer via a unique network ID. If you don't already have the app ID, you must obtain it from Tapjoy to continue with the integration.

#### Enable View-Through attribution

Toggle ON if you want to attribute view-through installs from Tapjoy. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to Tapjoy following installs and rejected installs. Use this section to define the **source of the users** for the postbacks.

Select ***This partner only*** for installs coming only from users attributed to Tapjoy.  
Select ***All sources, including organi*c** to have your entire user base available to be reported to Tapjoy.

Rejected installs can be sent for **This partner only**.

#### Launch postbacks

As of July 1, 2020, we no longer send launch postbacks to Tapjoy. If your integration was set up prior to this date, there may be changes to your configurations. The following table explains possible changes and your actions, where applicable:

| Your configuration | Will be updated to | Your next actions |
| --- | --- | --- |
| Send to Tapjoy **all launches** (from all media sources, including organic) | Send to Tapjoy:<ul><li>**all installs** (from all media sources, including organic)</li><li>**all `af_app_opened` events** (from all media sources, including organic)</li></ul> | No further actions are required. This update has no actual impact on the configuration. |
| Send to Tapjoy **attributed first launches only** | Send to Tapjoy **installs** attributed to Tapjoy only | If you wish to send `af_app_open` events as well:<ul><li>In AppsFlyer, on Tapjoy integration page, configure sending the event under the ***In-app event postbacks*** section</li></ul> |
| Send to Tapjoy **all launches** (from all media sources, including organic)<br /><br />**BUT**<br /><br />No conversions have been attributed to Tapjoy in the 3 months prior to July 1, 2020 | Send **all installs**<br /><br />**AND**<br /><br />For 30 days after July 1, 2020, **all launches** | If you wish to send `af_app_open` events as well:<ul><li>In AppsFlyer, on Tapjoy integration page, configure sending the event under the ***In-app event postbacks*** section.</li></ul>If done during the 30-day period, we will discontinue sending all launches and start sending all `af_app_open` events instead.<br /><br />If done after the 30-day period, we will stop sending launches and won't send `af_app_open` events until configured otherwise. |

### In-app events settings

In this section, you can configure in-app event postbacks that are sent to Tapjoy.

**To configure in-app event postbacks:**

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list.
3. Fill in the following data:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events)</li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<ul><li>**Text field:** Get the corresponding event ID from the partner.</li><li>**Drop-down box:** Select the most suitable pre-defined AppsFlyer event.</li><li>**As is**: Send the events as they are, without name mapping.</li></ul> |
| **for users from** | Select the sending option for the event:<ul><li>**This partner only**: Send postbacks only when the event is attributed to this partner—meaning, the user who performed it came from this partner.</li><li>**All media sources including organic**: Send postbacks for events attributed to any partner and for organic events—meaning, the user who performed it came from any media source.</li></ul> |
| **including** | <ul><li>**No data (default)**: Send just the event itself, without any event values.</li><li>**Values and revenue**: Send all event parameters, including revenue values (if exist in the event).</li><li>**Values without revenue**: Send all event parameters, excluding revenue values.</li></ul> |

4. [Optional] Click the Add condition![image.png](https://files.readme.io/8e650caf6472b316bd49bc25c45cc4c9d63b67770dd1c920fb873118b82ff868-17023682954385.png) icon of an event to [set conditions for the event](/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks) sent to Tapjoy.   

   > 📘 **Note**
   >
   > Tapjoy recommends not adding conditions to events sent to them, as this could cause issues with Tapjoy's propriety reward system and could negatively impact user experience.

5. Click **Save Integration**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).  
[Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters).

**To generate an attribution link,** follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

**Note:** TapJoy doesn't report Offerwall impressions to AppsFlyer. So installs following Offerwall impressions are not counted in AppsFlyer. Learn more about [Offerwall impressions](https://www.tapjoy.com/offerwall/).

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow [these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api).

<div id="cost-data-sync-status" />

<Accordion title="Cost data sync status">

[View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

> 📘 **Notes**
>
> * If cost macros are being passed on the attribution link, the API integration cannot be enabled. Enabling the cost API integration while cost macros exist on the attribution link may cause duplicate cost reporting. Please contact your TapJoy Account Manager and your AppsFlyer CSM to remove all cost macros from the existing attribution links.
> * Once you set TapJoy's cost, do not change the name of any active campaign, ad set, or single ad, nor use dynamic macros with the campaign name parameter, as they may cause serious discrepancies or missing cost data.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

This section is relevant if you are a publisher displaying partner ads to your users. As such, you would certainly like to measure the engagement of your users acquired from different sources to find the most profitable sources for you. Learn more about [Tapjoy ad revenue setup](https://dev.tapjoy.com/en/graphql-api/Appsflyer#iap-and-ad-revenue-configuration-for-roas).

**To enable the ad revenue API**:

* Follow [these integration instructions](/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners).

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Tapjoy, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Tapjoy, the permissions tab is active and you can grant control to Tapjoy.

Use these toggles to give the ad network permissions to handle its own configuration for your app.

### Ad Network Permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to set up in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).

</Accordion>

<div data-zendesk-anchors="h_01HJS1SANCA03NGA11EA2359Z9=setting-up-tapjoy h_01HJS1SANC560TH8VJ2R2ZRKZA=integration-tab h_01HJS1SANC0KMZ3HFM2MNJ6SCV=activate-partners h_01HJS1SANCN7RXVCKCQD4N8B2S=general-settings h_01HJS1SANCSQ8Z3YB41V7KHAZD=app_id enable-viewthrough-attribution=enable-view-through-attribution h_01HJS1SANCR3DEAPQW0F1S0YP9=enable-view-through-attribution h_01HJS1SANCN0KQ7APJBPAVD7G7=default-postbacks h_01HJS1SANCZTZ2NR3XTEPVRKXG=launch-postbacks inapp-events-settings=in-app-events-settings h_01HJS1SANDCNEXH91VMY2E0KYJ=in-app-events-settings h_01HJS1SAND8DY0SNRZKGBFAZKK=note h_01HJS1SANDQK7DT52KF9011YZB=attribution-link-tab h_01HJS1SAND247NKAB9FQBBCSPQ=cost-tab h_01HJS1SANDWEMAHC3SJ64EMR7F=cost-data-sync-status h_01HJS1SANDVWHSW4GPQHS0ZM6G=notes h_01HJS1SANDTWFDTAZYEHB3KKEH=ad-revenue-tab h_01HJS1SAND4S7S8NW05N4R20NB=permissions-tab h_01HJS1SANDAW1MH9EYRZSD5BTG=ad-network-permissions" />
