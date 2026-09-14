---
title: "Avow GmbH campaign configuration"
excerpt: "Configure the Avow GmbH integration in AppsFlyer to run User Acquisition campaigns with click-through and view-through attribution."
---
AVOW GmbH (avow1_int) is an integrated partner with both ad network and agency accounts, that allows advertisers to run User Acquisition campaigns on mobile devices. In addition to click-based mobile attribution, Avow GmbH also offers view-through attribution, which advertisers can record with AppsFlyer.

![avow_icon.png](https://files.readme.io/f6dc549357d6c7a6ddaec67752570484289529f85defaf0316ccd925868deab7-18523559800465.png)

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

## Setting up Avow GmbH

The integration with Avow GmbH supports click-through and view-through attribution. The general configuration window includes the following tabs: Integration, Attribution link, Cost, Ad revenue, and Permissions. For Avow GmbH, the available tabs are Integration, Attribution link, and Permissions.

> 📘 Note
>
> * Some settings differ for iOS and Android devices
> * Learn more about [setting up partner integrations](/docs/set-up-an-integrated-partner)

### Integration tab

The **Integration** tab includes a number of sections, as described below.

#### Activate partner

To configure the integration, you must first [turn on](https://support.appsflyer.com/hc/articles/11904659502737#activate-partner) the **Activate partner** toggle. Learn more about [activating and deactivating partner integrations](https://support.appsflyer.com/hc/articles/360000844778#activating-a-partner).

#### Advanced Privacy

For iOS apps only: Your control over data shared with the partner via postbacks and [reports](https://support.appsflyer.com/hc/articles/360006868017) depends on the **Advanced Privacy (for iOS 14.5+ and later)** toggle state:

| Advanced Privacy: On | Advanced Privacy: Off |
| --- | --- |
| Postbacks are sent only for events attributed to the partner | Postbacks are sent according to your configuration:<br>- **All media sources, including organic**<br>- **This partner only** |
| Postbacks are sent according to the [Advanced Privacy template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks) |  |
| [Aggregated and anonymous data](https://support.appsflyer.com/hc/articles/360018515798-Aggregated-Advanced-Privacy-framework) is shared with the partner, meaning no user-level data (device ID) is shared. |  |

#### General settings

**token**

Add the verification token provided by the AVOW Specialist (AM/BDM).

#### Install attribution

To attribute view-through installs from Avow GmbH, turn on **Install view-through attribution** . The view-through lookback slider is available on the Attribution link tab (described below).

#### Default postbacks

Postbacks for installs and rejected installs are sent to this partner only.

#### In-app event settings

**token**

Add the verification token provided by the AVOW Specialist (AM/BDM).

#### In-app event postbacks

Configure mapping of in-app events with Avow GmbH events, sent via postbacks:

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br>**Tip**: Don't see the event you are looking for?<br>   - Make sure to activate the event on a device with a non-organic installation, and recheck.<br>   - Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](https://support.appsflyer.com/hc/articles/208439256#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<br>   - **Text field:** Get the corresponding event ID from the partner.<br>   - **Drop-down box:** Select the most suitable pre-defined AppsFlyer event.<br>   - **As is**: Send the events as they are, without name mapping. |
| **for users from** | **This partner only:** In-app event postbacks are sent only for events attributed to this partner—meaning, the user who performed it came from this partner. |
| **including** | - **No data (default)**: Send only the event itself without any event values.<br>   - **Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).<br>   - **Values without revenue**: Send all the parameters **excluding** the revenue value. |

3. [Optional] Click the **Add condition**  ![conditional-iae-postbacks-icon.png](https://files.readme.io/ccd3619229eddf2c91979ab4b0531b95dc2fe1d8fffee5ba61ae965d68e9be99-18523570168081.png) icon to [set conditions](https://support.appsflyer.com/hc/articles/208439256#conditional-inapp-event-postbacks) for an event.
4. Set the **In-app event postback window**, if required (read more about [in-app event postback window configuration](https://support.appsflyer.com/hc/articles/208439256-In-App-Events-Postback-Configuration#inapp-event-postback-window)).
5. Click **Save integration**.
6. [Optional]After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
1. From the top-left corner, under the partner name, click the app name to open the list of apps.
2. Select a different app from the drop-down list.
3. Repeat the [integration steps](https://support.appsflyer.com/hc/articles/11904659502737#integration-tab) for the selected app.

> 📘 Note
>
> For iOS apps only: Your control over data shared with the partner via postbacks and [reports](https://support.appsflyer.com/hc/articles/360006868017) depends on the **Advanced Privacy (for iOS 14.5+ and later)** [toggle state](https://support.appsflyer.com/hc/articles/6722785184913#advanced-privacy).

### Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](https://support.appsflyer.com/hc/articles/115005248543-OneLink-overview). [Learn more about attribution link structure and parameters](https://support.appsflyer.com/hc/articles/207447163). **To generate an attribution link,** follow [these instructions](https://support.appsflyer.com/hc/articles/4410395957521#attribution-link-tab).

### Cost tab

Cost data isn't available for Avow GmbH.

### Ad revenue tab

Ad revenue isn't available for Avow GmbH.

### Permissions tab

Select which permissions to grant Avow GmbH to access your data and perform various actions.

> 📘 Note
>
> * When the integration is [deactivated](https://support.appsflyer.com/hc/articles/360000844778) while the Permissions toggle is still turned on, permissions remain granted.
> * Learn more about [granting permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).