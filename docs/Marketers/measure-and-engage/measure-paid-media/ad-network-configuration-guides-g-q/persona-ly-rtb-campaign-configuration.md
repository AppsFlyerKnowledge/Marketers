---
title: "Persona.ly RTB campaign configuration"
excerpt: "Learn how to configure the integration with Persona.ly RTB in AppsFlyer, including setting up attribution links, cost APIs, and postbacks."
---
Persona.ly RTB (personalyrtb_int), an AppsFlyer integrated partner, is a mobile-first DSP operating worldwide. Using proprietary bidder and machine-learning algorithms, Persona.ly offers transparent, performance-driven, highly targeted UA and retargeting solutions.

![persona.ly_logo.png](https://files.readme.io/b0dacbdc4c2e884610a040b5049a1410a88214f8275320163764bcf09f90305b-18699636413969.png)

## Setting up Persona.ly RTB

> 📘 Prerequisite
>
> An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

> 📘 Note
>
> The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)

5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

The integration with Persona.ly RTB supports click-through and view-through attribution.

The general configuration window includes the following tabs: Integration, Attribution link, Cost, Ad revenue, and Permissions. For Persona.ly RTB, the available tabs are Integration, Attribution link, Cost, and Permissions.

> 📘 Note
>
> * Some settings differ for iOS and Android devices
> * Learn more about [setting up partner integrations](/docs/set-up-an-integrated-partner)

### Integration tab

The **Integration** tab includes a number of sections, as described below.

#### Activate partner

To configure the integration, you must first [turn on](/docs/amazon-ads-campaign-configuration#activate-partner) the **Activate partner** toggle. Learn more about [activating and deactivating partner integrations](/docs/partner-activation-deactivation#activating-a-partner).

> 📘 Note
>
> As an all-install network, Persona.ly RTB prefers to receive postbacks for all new installs of your app from any source. To do so, select **All media sources, including organic** to send all install postbacks to Persona.ly RTB.

#### Advanced Privacy

For iOS apps only: Your control over data shared with the partner via postbacks and [reports](/docs/about-raw-data-identifier-restrictions) depends on the **Advanced Privacy (for iOS 14.5+ and later)** toggle state:

| Advanced Privacy: On | Advanced Privacy: Off |
| --- | --- |
| Postbacks are sent only for events attributed to the partner | Postbacks are sent according to your configuration:<br />- **All media sources, including organic**<br />- **This partner only** |
| Postbacks are sent according to the [Advanced Privacy template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks) |  |
| [Aggregated and anonymous data](/docs/apply-aggregated-advanced-privacy-framework) is shared with the partner, meaning no user-level data (device ID) is shared. |  |

#### Transaction ID

For iOS apps only, when **Share SKAN transaction ID** is turned on, you're allowing AppsFlyer to [share the transaction ID of SKAdNetwork postbacks](/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners) with Persona.ly RTB. By doing so, Persona.ly RTB could decode your SKAdNetwork Conversion Values.

#### Install attribution

To attribute view-through installs from Persona.ly RTB, turn on **Install view-through attribution**. The view-through lookback slider is available on the [Attribution link tab](/docs/persona-ly-rtb-campaign-configuration#attribution-link-tab).

#### Default postbacks

Define the source of users for sending automatic postbacks to partners relating to user actions occurring before the app launch:

* For **Installs**, select one of the following:
  * **This partner only:** Send postbacks only when the install is attributed to this partner—meaning, the user who installed the app came from Persona.ly RTB.
  * **All media sources, including organic:** Send postbacks for installs attributed to any partner and for organic events—meaning, the user who installed the app came from any media source.
* For **Rejected installs** and **Re-engagements:** Postbacks are sent to Persona.ly RTB only.

#### In-app event postbacks

Configure mapping of in-app events with Persona.ly RTB events, sent via postbacks:

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<br />   - Make sure to activate the event on a device with a non-organic installation, and recheck.<br />   - Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<br />   - **Text field:** Get the corresponding event ID from the partner.<br />   - **Drop-down box:** Select the most suitable pre-defined AppsFlyer event.<br />   - **As is**: Send the events as they are, without name mapping. |
| **for users from** | Select the sending option for the event:<br />   - **This partner only**: Send postbacks only when this event is attributed to this partner.<br />   - **All media sources including organic**: Send postbacks for events attributed to any partner, as well as organic events. |
| **including** | - **No data (default)**: Send only the event itself without any event values.<br />   - **Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).<br />   - **Values without revenue**: Send all the parameters **excluding** the revenue value. |

3. [Optional] Click the **Add condition** ![conditional-iae-postbacks-icon.png](https://files.readme.io/c3a5830693fb1f7b48c4d44964365ec0f1da36884cef914e7ab2be011bc60044-18699057822865.png) icon to [set conditions](/docs/in-app-event-postback-configuration#conditional-inapp-event-postbacks) for an event.
4. Set the **In-app event postback window**, if required (read more about [in-app event postback window configuration](/docs/in-app-event-postback-configuration#inapp-event-postback-window)).
5. Click **Save integration**.
6. [Optional]After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
1. From the top-left corner, under the partner name, click the app name to open the list of apps.
2. Select a different app from the drop-down list.
3. Repeat the [integration steps](/docs/amazon-ads-campaign-configuration#integration-tab) for the selected app.

> 📘 Note
>
> For iOS apps only: Your control over data shared with the partner via postbacks and [reports](/docs/about-raw-data-identifier-restrictions) depends on the **Advanced Privacy (for iOS 14.5+ and later)** [toggle state](/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy).

### Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide). [Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters). **To generate an attribution link,** follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

### Cost tab

AppsFlyer gets cost details by API. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow [these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api).

[View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

### Ad revenue tab

Ad revenue isn't available for Persona.ly RTB.

### Permissions tab

Select which [permissions to grant](/docs/set-up-an-integrated-partner#permissions-tab) Persona.ly RTB to access your data and perform various actions.

> 📘 Note
>
> When the integration is [deactivated](/docs/partner-activation-deactivation) while the Permissions toggle is still turned on, permissions remain granted.