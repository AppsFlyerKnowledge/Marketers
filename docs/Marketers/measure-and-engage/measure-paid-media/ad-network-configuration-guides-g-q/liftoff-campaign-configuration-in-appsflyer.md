---
title: "Liftoff campaign configuration in AppsFlyer"
excerpt: "Learn how to set up and configure mobile attribution, cost API, SKAdNetwork, and product feed retargeting for Liftoff in AppsFlyer."
---
**At a glance:** Liftoff, an AppsFlyer ad network integrated partner, is one of the top demand partners for brands and app developers. Liftoff offers click-based and view-through mobile attribution, as well as click-based and view-through retargeting which you can record with AppsFlyer.

![](https://cdn.appsflyer.com/marketplace/static/logo/liftoff.png)

> 📘 **Note**
>
> #### Important!
>
> Some media sources restrict sharing data with 3rd parties. AppsFlyer can't share user-level data of users acquired through these media sources with 3rd party platforms or services. All installs from such media sources are therefore sent as organic.
>
> For more details and a list of media sources that restrict sharing data with 3rd parties, click [here](/docs/user-level-data-retention).


## Setting up Liftoff

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

## Integration tab

The **Integration tab** is divided into different sections as described below.

### Activate partners

The [partner must be activated](/docs/partner-activation-deactivation#activating-a-partner) by switching on the **Activate partner** toggle on the first visit to enable its setup.

### General settings

**Enable view-through attribution**

Activate, if you want to attribute view-through installs from Liftoff. The view-through lookback slider is available in the [**Attribution link**](/docs/liftoff-campaign-configuration-in-appsflyer#attribution-link-tab) tab.

### Default postbacks

Send automatic postbacks to Liftoff following user installs, rejected installs, and reengagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **This partner only** for events coming only from users attributed to Liftoff.  
Select **All sources, including organic** to have your entire user base available to be reported to Liftoff.

> 📘 **Note**
>
> #### Note
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
| **Send event data** | * **No values & no revenue:** sends only the event itself without the event value.<br />* **Values & no revenue:** sends all the parameters excluding the revenue value.<br />* **Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event). |


5. Click **Save**.

## Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).  
[Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters).

**To generate an attribution link,**follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

## Cost tab

AppsFlyer gets cost details by API. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow [these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api).

[View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

## Ad revenue tab

Ad revenue data is not supported by this partner.

## Permissions tab

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

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).

### Agency permissions

If you work with Liftoff as an agency partner, in this section you can give them permissions to handle their own configuration for your app:

* **Main toggle** - Setting this to **ON**:

  * Reveals the agency permissions options
  * Enables the agency to get attributed with installs for the app
  * Enables the agency to see Meta ads and X Ads promoted data

  **Warning: Agency installs occurring while the toggle is OFF are not attributed to the agency** and don't show up on the agency's dashboard and data ([more details](/docs/partner-activation-deactivation#agency-permissions)).

* **Allow access to your Protect360 dashboard**
* **Allow access to your retention and cohort reports** - retention/cohort data created by the users brought by the agency only.
* **Allow access to aggregate organic data**
* **Allow to configure in-app event postbacks** - permit the agency to setup in-app event postbacks mapping to itself on the integration tab
  * **Event sharing permissions** - select your preferred option here:  
    a) **This partner only** - send only events from agency's own brought traffic to the app  
    b) **All sources, including organic** - send events from all sources of your traffic, including other media sources, agencies, and organic users
  * **Allow to send event revenue** - permit the agency to send events including their monetary value
  * Make sure to select specific events you want to grant the agency permission to. Click **Add event** and pick the event from the drop-down list. Do this for each event you want to add.

Learn more about [working with agencies](/docs/about-agency-accounts).

## Set up SKAdNetwork integration with Liftoff

**To receive SKAdNetwork data from Liftoff:**

1. [To support SKAdNetwork, update your AppsFlyer SDK to the latest version](/docs/skadnetwork-skan-solution-guide).
2. In AppsFlyer Conversion Studio, [set up conversion values to measure the events you want](/docs/skan-conversion-studio#setting-up-conversion-values-in-skan-conversion-studio).
3. Share with Liftoff your campaign goal and the final event you want to optimize your campaigns with. It's recommended that your final event correlates with your preferred event and occurs close to install time.  
   For example:
   * **CPA campaigns:** Share the required event and CPA goal to be used for SKAdNetwork campaign optimization.
   * **CPI campaigns:** Share the CPI goal to be used for SKAdNetwork campaign optimization.
4. Reach out to your Liftoff Account Team to confirm that SKAdNetwork postbacks are being sent with conversion values.
5. [Optional] To share SKAdNetwork transaction ID with Liftoff, turn **Share Transaction ID in SKAdNetwork mode** on.  
   Learn more about [transaction ID.](/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners)

## Product feed retargeting with Liftoff

For product event attribution to work correctly, Liftoff needs to receive the product IDs associated with each of your events. For example, the IDs of specific products users purchase or add to their cart.

These IDs must be linked back to the unique IDs you pass to Liftoff within your product feed. Liftoff supports the [standard AppsFlyer convention of sharing this data](/docs/in-app-events-event-structure#predefined-event-parameters) via af\_content\_id attributes out of the box.

If you have a non-standard event data implementation, please reach out to your Liftoff CSM to see if the integration is possible.