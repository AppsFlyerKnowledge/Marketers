---
title: Liftoff campaign configuration in AppsFlyer
metadata:
  keywords:
    - liftoff
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
  created_at: '2016-03-28T09:38:23Z'
  edited_at: '2026-09-09T13:05:34Z'
  id: 209731633
  locale: en-us
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/209731633-Liftoff-campaign-configuration-in-AppsFlyer
---
> **At a glance:** Liftoff, an AppsFlyer ad network integrated partner, is one of the top demand partners for brands and app developers. Liftoff offers click-based and view-through mobile attribution, as well as click-based and view-through retargeting which you can record with AppsFlyer.

![](https://cdn.appsflyer.com/marketplace/static/logo/liftoff.png)

> 🚧 **Important!**
>
> Some media sources restrict sharing data with 3rd parties. AppsFlyer can't share user-level data of users acquired through these media sources with 3rd party platforms or services. All installs from such media sources are therefore sent as organic.
>
> For more details and a list of media sources that restrict sharing data with 3rd parties, click <Anchor target="_blank" href="/marketers/docs/user-level-data-retention">here</Anchor>.

## Setting up Liftoff

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

The **Integration tab** is divided into different sections as described below.

### Activate partners

The <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation#activate-a-partner-integration">partner must be activated</Anchor> by switching on the **Activate partner** toggle on the first visit to enable its setup.

### General settings

**Enable view-through attribution**

Activate, if you want to attribute view-through installs from Liftoff. The view-through lookback slider is available in the [**Attribution link**](/docs/liftoff-campaign-configuration-in-appsflyer#attribution-link-tab) tab.

### Default postbacks

Send automatic postbacks to Liftoff following user installs, rejected installs, and reengagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **This partner only** for events coming only from users attributed to Liftoff.  
Select **All sources, including organic** to have your entire user base available to be reported to Liftoff.

> 📘 **Note**
>
> As an ALL-Installs network, Liftoff prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **All sources, including organic** to send all install postbacks to Liftoff.

**To configure in-app event postbacks:**

1. Activate **In-app event postbacks**
2. Choose whether to report **selected events** to the partner or **all** of them.
   * Note: If you choose to report all events, the af\_app\_opened event is not reported.
3. If you choose to manually select events, click **Add event** to add an SDK Event to the list.
4. Fill in the following data:

| Parameter name | Description |
| --- | --- |
| **SDK event name** (required for manual selection only) | The name of the event, as received by AppsFlyer either from the SDK or from server-to-server events.  <br />**Tip**: If you don't see the event you want in the list, activate this event on a device with a non-organic installation and recheck. |
| **Sending option** | Select the sending option for the event:  <br />**This partner only** for events coming **only** from users attributed to Liftoff.  <br />**All sources, including organic** to have your entire user base available to be reported to the partner |
| **Send event data** | <ul><li>**No values & no revenue:** sends only the event itself without the event value.</li><li>**Values & no revenue:** sends all the parameters excluding the revenue value.</li><li>**Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event).</li></ul> |

5. Click **Save**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">these integration instructions</Anchor>.

<Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue data is not supported by this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Liftoff. Note that even if attribution is disabled for Liftoff, the permissions tab is active and you can grant control to Liftoff.

### Ad network permissions

In this tab, you can select the permissions to grant Liftoff. Note that even if attribution is disabled for Liftoff, the permissions tab is active and you can grant control to liftoff.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* **Allow to configure integration** - permit the partner to set up the integration tab (except in-app event postbacks)
* **Allow to configure in-app event postbacks** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* **Allow access to your retention report** - only to the partner's own retention data
* **Allow access to your aggregate loyal user data** - only to the partner's own loyal user data
* **Allow access to your aggregate in-app events data** - only to the partner's own in-app events data
* **Allow access to your aggregate revenue data** - only to the revenue data attributed to the partner
* **Allow access to your Protect360 dashboard** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

### Agency permissions

If you work with Liftoff as an agency partner, in this section you can give them permissions to handle their own configuration for your app:

* **Main toggle** - Setting this to **ON**:

  * Reveals the agency permissions options
  * Enables the agency to get attributed with installs for the app
  * Enables the agency to see Meta ads and X Ads promoted data

  **Warning: Agency installs occurring while the toggle is OFF are not attributed to the agency** and don't show up on the agency's dashboard and data (<Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation#agency-permissions">more details</Anchor>).

* **Allow access to your Protect360 dashboard**
* **Allow access to your retention and cohort reports** - retention/cohort data created by the users brought by the agency only.
* **Allow access to aggregate organic data**
* **Allow to configure in-app event postbacks** - permit the agency to setup in-app event postbacks mapping to itself on the integration tab
  * **Event sharing permissions** - select your preferred option here:  
    a) **This partner only** - send only events from agency's own brought traffic to the app  
    b) **All sources, including organic** - send events from all sources of your traffic, including other media sources, agencies, and organic users
  * **Allow to send event revenue** - permit the agency to send events including their monetary value
  * Make sure to select specific events you want to grant the agency permission to. Click **Add event** and pick the event from the drop-down list. Do this for each event you want to add.

Learn more about <Anchor target="_blank" href="/partners/docs/about-agency-accounts">working with agencies</Anchor>.

</Accordion>

## Set up SKAdNetwork integration with Liftoff

**To receive SKAdNetwork data from Liftoff:**

1. <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide">To support SKAdNetwork, update your AppsFlyer SDK to the latest version</Anchor>.
2. In AppsFlyer Conversion Studio, <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio#setting-up-conversion-values-in-skan-conversion-studio">set up conversion values to measure the events you want</Anchor>.
3. Share with Liftoff your campaign goal and the final event you want to optimize your campaigns with. It's recommended that your final event correlates with your preferred event and occurs close to install time.  
   For example:
   * **CPA campaigns:** Share the required event and CPA goal to be used for SKAdNetwork campaign optimization.
   * **CPI campaigns:** Share the CPI goal to be used for SKAdNetwork campaign optimization.
4. Reach out to your Liftoff Account Team to confirm that SKAdNetwork postbacks are being sent with conversion values.
5. [Optional] To share SKAdNetwork transaction ID with Liftoff, turn **Share Transaction ID in SKAdNetwork mode** on.  
   Learn more about <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">transaction ID.</Anchor>

## Product feed retargeting with Liftoff

For product event attribution to work correctly, Liftoff needs to receive the product IDs associated with each of your events. For example, the IDs of specific products users purchase or add to their cart.

These IDs must be linked back to the unique IDs you pass to Liftoff within your product feed. Liftoff supports the <Anchor target="_blank" href="/marketers/docs/in-app-events-event-structure#predefined-event-parameters">standard AppsFlyer convention of sharing this data</Anchor> via af\_content\_id attributes out of the box.

If you have a non-standard event data implementation, please reach out to your Liftoff CSM to see if the integration is possible.

<div data-zendesk-anchors="h_01HGFR9QYBQ3BK3TM364SJDKWZ=important h_01HGFR9QYBPY2XR4KMWMJKHHMQ=setting-up-liftoff h_01HGFR9QYBJG0WD6X203X8MYFV=integration-tab h_01HGFR9QYBXAQQKPRW1KKF6989=activate-partners h_01HGFR9QYBPCYCJRY20S1TCF6R=general-settings h_01HGFR9QYB8JHTAAB591QQ1P6J=default-postbacks h_01HGFR9QYBW8DFZK63EZ3V5622=note h_01HGFR9QYB42YK8FJD308YWXC7=attribution-link-tab h_01HGFR9QYBJ20T4F0W5486B4NW=cost-tab h_01HGFR9QYBV9ZCGJ1D6BD1T9JG=ad-revenue-tab h_01HGFR9QYB9DA5XYXPEARZSCHF=permissions-tab h_01HGFR9QYB0VCPG7YCX64BBKY9=ad-network-permissions h_01HGFR9QYBR3W0JXY7MHQ8PZT7=agency-permissions h_01HGFR9QYBG4830DKGMGV716B7=set-up-skadnetwork-integration-with-liftoff h_01HGFR9QYB302DVBYXMK0XY4ED=product-feed-retargeting-with-liftoff" />
