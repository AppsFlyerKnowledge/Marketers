---
title: "Criteo campaign configuration"
excerpt: "Configure Criteo integration in AppsFlyer to measure mobile attribution, retargeting, cost data, and manage partner permissions."
---
At a glance: Criteo, an AppsFlyer ad network integrated partner, drives growth through machine-learning technology, data and performance at scale, and measurable ROI for its clients. In addition to click-based mobile attribution, Criteo also offers retargeting attribution, which you can record with AppsFlyer.

## Setting up Criteo

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

## Integration tab

### Activate Partner

On the **first visit**, you will need to toggle ON the _**Activate Partner**_ button to enable the setup of integration tab parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

> 📘 Note
>
> As an ALL-Installs network, Criteo prefers to receive postbacks for all new installs of your app from ANY source, including organic. It is recommended to select **Events attributed to any partner** to send all install postbacks to Criteo.

### Default postbacks

Send automatic postbacks to Criteo following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Criteo.

Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Criteo.

### In-app events settings

In this section, map your AppsFlyer events with Criteo via postbacks.

1. Toggle In-App Event Postbacks to ON.
2. Select the Sending Option for all SDK-defined events.

**- Only events attributed to this partner** for events coming **only** from users attributed to this partner.

**- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner.
3. Click **Add Event** to add an SDK Event to the list.
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.<br>**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Criteo's side.<br>Obtain the corresponding Event ID from Criteo and set in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af_revenue** parameter.<br>**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

> 🚧 Warning
>
> [Complex in-app events](/docs/in-app-events-overview#what-are-complex-inapp-events-and-how-do-i-set-them-up) cause postback issues with Criteo. If you need the event to be fully mapped with Criteo, send separate events per user action (for example, send an Add to cart event per each added item). Use the in-app events raw data to group these events together.

## Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](https://support.appsflyer.com/hc/articles/115005248543-OneLink-overview).

[Learn more about attribution link structure and parameters](https://support.appsflyer.com/hc/articles/207447163).

**To generate an attribution link,** follow [these instructions](https://support.appsflyer.com/hc/articles/4410395957521#attribution-link-tab).

## Cost tab

AppsFlyer gets cost details by API. See the [ad network cost integration table](https://support.appsflyer.com/hc/articles/207040526-Ad-cost-measurement-guide#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features.

> 📘 Note
>
> * Cost data requires an ROI360 subscription.
> * Cost data from Criteo can be received only for downloads coming from Google Play or Apple App Store. For Android, cost data for third-party Android app stores isn't supported.
> * Agency cost is only available via [click](https://support.appsflyer.com/hc/articles/360008981698); not via API integration.

**To enable the cost API**:

* Follow [these integration instructions](https://support.appsflyer.com/hc/articles/360008850257#enable-cost-api).

[View your cost API status](https://support.appsflyer.com/hc/articles/360008850257#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

## Ad revenue tab

Ad revenue integration is not available for Criteo.

## Permissions tab

In this tab, you can select the permissions to grant Criteo, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Criteo, the permissions tab is active and you can grant control to Criteo.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

Ad Network Permissions

* _**Allow to configure integration**_ - permit the partner to set up the integration tab (except in-app event postbacks)
* _**Allow to configure in-app event postbacks**_ - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* _**Allow access to your retention report**_ - only to the partner's own retention data
* _**Allow access to your aggregate loyal user data**_ - only to the partner's own loyal user data
* _**Allow access to your aggregate in-app events data**_ - only to the partner's own in-app events data
* _**Allow access to your aggregate revenue data**_ - only to the revenue data attributed to the partner
* _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).