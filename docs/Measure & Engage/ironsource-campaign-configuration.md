---
title: "ironSource campaign configuration"
excerpt: "Configure ironSource integration in AppsFlyer to record click-based mobile attribution, cost, ad revenue, retargeting, and view-through attribution."
---
At a glance: ironSource, an AppsFlyer integrated partner, builds monetization, engagement, analytics, and discovery tools for app developers, device manufacturers, mobile carriers, and advertisers. In addition to click-based mobile attribution, ironSource also offers cost, ad revenue, retargeting and view-through attribution, which you can record with AppsFlyer.

## Setting up ironSource

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

> 📘 Note
>
> As an all-installs network, ironSource prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to ironSource.

ironSource's configuration window includes 5 tabs: Integration, Attribution link, Cost, Ad Revenue, and Permissions. Click on the items below to read about the tabs setup.

- The General Settings step in the Integration tab is **mandatory** for all partners
- All the rest of the steps are either descriptive or **optional**

## Integration tab

### Activate partners

On the **first visit** here, you will need to turn on the **Activate Partner** toggle to enable setup of the integration tab parameters. The toggle must stay on for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

#### Advanced Privacy

For iOS apps only, when **Advanced Privacy (for iOS 14.5+ and later)** is turned on, you can [control what data is shared](https://support.appsflyer.com/hc/articles/4410395957521#b-advanced-privacy) with ironSource via postbacks and reports.

### Transaction ID

For iOS apps only, when **Share SKAN transaction ID** is turned on, you're allowing AppsFlyer to [share the transaction ID of SKAdNetwork postbacks](https://support.appsflyer.com/hc/articles/360011420698#sending-postbacks-to-integrated-partners) with ironSource. By doing so, ironSource could decode your SKAdNetwork Conversion Values.

> 📘 Note
>
> For SKAN interoperation with AppsFlyer, contact your ironSource account manager to [enable sending SKAN data to MMPs](https://developers.is.com/ironsource-mobile/general/universal-skan-reporting/#step-1).

### General settings

**Advertiser ID**

ironSource connects with AppsFlyer via a unique advertiser ID (6-digit number) and a password. If you don't already have the advertiser ID and password, you must obtain them from ironSource to continue with the integration. Otherwise, copy the ID and the password and paste them into the respective fields.

### Install and Re-engagement attribution

These two toggles enable attributing to ironSource new installs and re-attributions of users who **viewed** your ad but **didn’t click** on it. Learn more about [view-through attribution](https://support.appsflyer.com/hc/articles/210084473).

**To attribute new installs:**

1. Turn on **Install view-through attribution**.
2. Configure the length of the **view-through** lookback window in the [Attribution link tab](https://support.appsflyer.com/hc/articles/208005096#attribution-link-tab).

**To attribute new re-engagements of existing users:**

1. Turn on **Re-engagement view-through attribution**.
2. Configure the length of the **view-through** lookback window in the [Attribution link tab](https://support.appsflyer.com/hc/articles/208005096#attribution-link-tab).

### Default postbacks

Send automatic postbacks to ironSource following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to ironSource.

Select **Events attributed to any partner, or organic** to have your entire user base available to be reported to ironSource.

> 📘 Note
>
> As an all-installs network, ironSource prefers to receive postbacks for all new installs of your app from any source, including organic. To do so, select **Events attributed to any partner, or organic** to send all install postbacks to ironSource.

### In-app event postbacks

Configure mapping of in-app events with ironSource events, sent via postbacks:

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br>**Tip**: Don't see the event you are looking for?<br>   - Make sure to activate the event on a device with a non-organic installation, and recheck.<br>   - Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](https://support.appsflyer.com/hc/articles/208439256#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<br>   - **Text field:** Get the corresponding event ID from the partner.<br>   - **Drop-down box:** Select the most suitable pre-defined AppsFlyer event.<br>   - **As is**: Send the events as they are, without name mapping. |
| **for users from** | Select the sending option for the event:<br>   - **This partner only**: Send postbacks only when this event is attributed to this partner.<br>   - **All media sources including organic**: Send postbacks for events attributed to any partner, as well as organic events. |
| **including** | - **No data (default)**: Send only the event itself without any event values.<br>   - **Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).<br>   - **Values without revenue**: Send all the parameters **excluding** the revenue value. |

3. [Optional] Click the **Add condition**  ![conditional-iae-postbacks-icon.png](https://files.readme.io/a97c5e34c264ddfa9f94b894520f849a3e59b42be14839ee37c71a5b6cc5ebd7-17612766801425.png) icon to [set conditions](https://support.appsflyer.com/hc/articles/208439256#conditional-inapp-event-postbacks) for an event.
4. Click **Save integration**.
5. [Optional]After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
1. From the top-left corner, under the partner name, click the app name to open the list of apps.
2. Select a different app from the drop-down list.
3. Repeat the [integration steps](https://support.appsflyer.com/hc/articles/11904659502737#integration-tab) for the selected app.

> 📘 Note
>
> - For iOS apps only: Your control over data shared with the partner via postbacks and [reports](https://support.appsflyer.com/hc/articles/360006868017) depends on the **Advanced Privacy (for iOS 14.5+ and later)** [toggle state](https://support.appsflyer.com/hc/articles/6722785184913#advanced-privacy).
> - You can send [ad revenue postbacks](https://support.appsflyer.com/hc/articles/217490046#ad-revenue-event-postbacks-for-ad-networks) to ironSource so they can optimize campaigns using ad revenue data:
>   - **Event name:** af\_ad\_revenue
>   - **Mapped to:** adRevenue

## Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](https://support.appsflyer.com/hc/articles/115005248543-OneLink-overview).

[More about attribution link structure and parameters](https://support.appsflyer.com/hc/articles/207447163) **.**

**To generate an attribution link,** follow [these instructions](https://support.appsflyer.com/hc/articles/4410395957521#attribution-link-tab).

## Cost tab

## Ad revenue tab

If you display ads in the app sent by Unity LevelPlay mediation (formerly ironSource) or by the ironSource monetization network, this section is relevant.

The following options for ad revenue granularity are available:

- Aggregate level (via S2S API).
- Device level (via S2S API).
- Impression level (via SDK).
- Impression-level (via SDK) with device-level (via S2S API)

Learn more about [ad revenue attribution](https://support.appsflyer.com/hc/articles/217490046-Ad-Revenue-Attribution).

**To enable the ad revenue integration**:

- Follow [these integration instructions](https://support.appsflyer.com/hc/articles/217490046-Ad-revenue-attribution-guide#connect-to-ad-revenue-integrated-partners).

## Permissions tab

In this tab, you can select the permissions to grant ironSource, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for ironSource, the permissions tab is active and you can grant control to ironSource.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

- **Allow to configure integration** - permit the partner to set up the integration tab (except in-app event postbacks)
- **Allow to configure in-app event postbacks** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- **Allow access to your retention report** - only to the partner's own retention data
- **Allow access to your aggregate loyal user data** - only to the partner's own loyal user data
- **Allow access to your aggregate in-app events data** - only to the partner's own in-app events data
- **Allow access to your aggregate revenue data** - only to the revenue data attributed to the partner
- **Allow access to your Protect360 dashboard** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

- **Main toggle** - Set to On to reveal the agency permissions options
- **Allow access to your retention report** - only to the agency's own retention data
- **Allow access to aggregate organic data**
- **Allow to configure in-app event postbacks** - permit the agency to setup in-app event postbacks mapping to itself on the integration tab

Learn more about granting [agency permissions](https://support.appsflyer.com/hc/articles/4410395957521#agency-permissions).