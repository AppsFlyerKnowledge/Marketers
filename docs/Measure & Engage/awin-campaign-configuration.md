---
title: "Awin campaign configuration"
excerpt: "Configure the Awin integration in AppsFlyer to run user acquisition and retargeting campaigns, including setting up attribution links, postbacks, and deep linking."
---
At a glance: Awin (affiliatewindow_int) is an integrated partner that allows advertisers to run UA and retargeting campaigns. Awin's marketing platform helps connect merchants (advertisers) with affiliates (publishers).

![awin icon.png](https://files.readme.io/2a7f22084586fec820c0bfab7f3a256259c43d37f14d6fed8e8db3d2e9905947-18533392495377.png)

## Activate partner

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

## Setting up Awin

The integration with Awin supports click-through attribution.

The general configuration window includes the following tabs: Integration, Attribution link, Cost, Ad revenue, and Permissions. For Awin, the available tabs are Integration, Attribution link, and Permissions.

> 📘 Note
>
> - Some settings differ for iOS and Android devices
> - Learn more about [setting up partner integrations](/docs/set-up-an-integrated-partner)

### Prerequisite

Before setting up the integration, make sure to implement the required "commission group" parameters in the SDK, as specified in [Awin documentation](https://help.awin.com/docs/appsflyer).

### Integration tab

The **Integration** tab includes a number of sections, as described below.

#### Activate partner

To configure the integration, you must first [turn on](https://support.appsflyer.com/hc/articles/11904659502737#activate-partner) the **Activate partner** toggle. Learn more about [activating and deactivating partner integrations](https://support.appsflyer.com/hc/articles/360000844778#activating-a-partner). For additional information, you can reference the [Awin integration page](https://developer.awin.com/docs/appsflyer).

#### Advanced Privacy

For iOS apps only: Your control over data shared with the partner via postbacks and [reports](https://support.appsflyer.com/hc/articles/360006868017) depends on the **Advanced Privacy (for iOS 14.5+ and later)** toggle state:

| Advanced Privacy: On | Advanced Privacy: Off |
| --- | --- |
| Postbacks are sent only for events attributed to the partner | Postbacks are sent according to your configuration:<br>- **All media sources, including organic**<br>- **This partner only** |
| Postbacks are sent according to the [Advanced Privacy template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks) |  |
| [Aggregated and anonymous data](https://support.appsflyer.com/hc/articles/360018515798-Aggregated-Advanced-Privacy-framework) is shared with the partner, meaning no user-level data (device ID) is shared. |  |

#### General settings

**Awin advertiser ID**

Add your Awin advertiser (or merchant) ID.

> 📘 Note
>
> An advertiser ID identifies your advertiser account on the partner’s side and is necessary for AppsFlyer attribution and postbacks. The ID must appear in the attribution link.

#### Default postbacks

Install postbacks are sent to this partner only.

#### In-app event settings

**Awin advertiser ID**

Add your Awin merchant ID.

#### In-app event postbacks

Configure mapping of in-app events with Awin events, sent via postbacks:

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br>**Tip**: Don't see the event you are looking for?<br>   - Make sure to activate the event on a device with a non-organic installation, and recheck.<br>   - Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](https://support.appsflyer.com/hc/articles/208439256#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<br>   - **Text field:** Get the corresponding event ID from the partner.<br>   - **Drop-down box:** Select the most suitable pre-defined AppsFlyer event.<br>   - **As is**: Send the events as they are, without name mapping. |
| **for users from** | **This partner only:** You can send in-app event postbacks only when the event is attributed to this partner—meaning, the user who performed it came from this partner. |
| **including** | - **No data (default)**: Send only the event itself without any event values.<br>   - **Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).<br>   - **Values without revenue**: Send all the parameters **excluding** the revenue value. |

3. [Optional] Click the **Add condition**  ![conditional-iae-postbacks-icon.png](https://files.readme.io/c95f88d3e2fce153d0a04390fcbca5dabdb97f93ee700f0d69feb568169fddf0-18532570767761.png) icon to [set conditions](https://support.appsflyer.com/hc/articles/208439256#conditional-inapp-event-postbacks) for an event.
4. Set the **In-app event postback window**, if required (read more about [in-app event postback window configuration](https://support.appsflyer.com/hc/articles/208439256-In-App-Events-Postback-Configuration#inapp-event-postback-window)).
5. Click **Save integration**.
6. [Optional]After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
1. From the top-left corner, under the partner name, click the app name to open the list of apps.
2. Select a different app from the drop-down list.
3. Repeat the [integration steps](https://support.appsflyer.com/hc/articles/11904659502737#integration-tab) for the selected app.

> 📘 Note
>
> For iOS apps only: Your control over data shared with the partner via postbacks and [reports](https://support.appsflyer.com/hc/articles/360006868017) depends on the **Advanced Privacy (for iOS 14.5+ and later)** [toggle state](https://support.appsflyer.com/hc/articles/6722785184913#advanced-privacy).

### Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](https://support.appsflyer.com/hc/articles/115005248543-OneLink-overview). [Learn more about attribution link structure and parameters](https://support.appsflyer.com/hc/articles/207447163). **To generate an attribution link,** follow [these instructions](https://support.appsflyer.com/hc/articles/4410395957521#attribution-link-tab).

### Cost tab

Cost data isn't available for Awin.

### Ad revenue tab

Ad revenue isn't available for Awin.

### Permissions tab

Select which permissions to grant Awin to access your data and perform various actions.

> 📘 Note
>
> - When the integration is [deactivated](https://support.appsflyer.com/hc/articles/360000844778) while the Permissions toggle is still turned on, permissions remain granted.
> - Learn more about [granting permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).

## Deep linking and deferred deep linking using OneLink

AWIN wraps any link used in their platform so that they can provide analytics data to their customers. This means the link will be redirected to AWIN’s site before sending users to their final destination. [Learn more about link wrapping](https://www.appsflyer.com/blog/mobile-marketing/universal-links-app-links/#:~:text=%231%3A%20Link%20wrapping%20and%20Universal%20Links).

AWIN as a platform supports a URI scheme but **doesn’t support** handling the iOS Universal links and Android app link methods of deep linking. This applies to any link used within AWIN.

To deep link with OneLink via AWIN:

- [Setup your OneLink URL with a URI scheme](https://support.appsflyer.com/hc/articles/207032246-OneLink-templates#add-redirection-logic-for-existing-app-users)

> 📘 Note
>
> For iOS apps, use the `af_force_deeplink=true` parameter on the OneLink URL to activate the deep link [URI scheme](https://support.appsflyer.com/hc/articles/207032246-OneLink-templates#add-redirection-logic-for-existing-app-users).