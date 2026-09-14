---
title: "MOLOCO campaign configuration"
excerpt: "Learn how to configure MOLOCO integration in AppsFlyer, including setting up attribution links, postbacks, cost API, and partner permissions."
---
At a glance: MOLOCO, an AppsFlyer integrated partner, turns user data into ad performance, enabling mobile businesses to execute marketing and advertising monetization programs.

## Setting up MOLOCO

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

MOLOCO's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](https://support.appsflyer.com/hc/articles/4410395957521#about-the-integrated-partner-page).

> 👍 Tip
>
> - The [General Settings](https://support.appsflyer.com/hc/articles/4410395957521#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> - All the rest of the steps are either descriptive or **optional**

## Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle ON the _**Activate Partner**_ button to enable setup of the Integration tab parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation, please click [here](https://support.appsflyer.com/hc/articles/360000844778).

> 📘 Note
>
> As an all-install network, MOLOCO prefers to receive postbacks for all new installs of your app from any source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to MOLOCO.

### General settings

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from MOLOCO. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to MOLOCO following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to MOLOCO.

Select **Events attributed to any partner or organic** to have your entire user base available to be reported to MOLOCO.

### In-app events settings

In this section you can map your AppsFlyer events with MOLOCO via postbacks.

1. Toggle In-App Event Postbacks to ON.
2. Select the Sending Option for all SDK-defined events.

**- Only events attributed to this partner** for events coming **only** from users attributed to this partner

**- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list.
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br>**Tip**: Don't see the event you are looking for?<br>- Make sure to activate the event on a device with a non-organic installation and recheck.<br>- Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](https://support.appsflyer.com/hc/articles/208439256#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<br>- **Text field:** Get the corresponding event ID from the partner.<br>- **Drop-down box:** Select the most suitable pre-defined AppsFlyer event.<br>- **As is**: Send the events as they are, without name mapping. |
| **for users from** | Select the sending option for the event:<br>- **This partner only**: send postbacks only when this event is attributed to this partner.<br>- **All media sources, including organic**: send postbacks for events attributed to any partner, as well as organic events. According to Unity Ads, this option is recommended. |
| **including** | - **No data (default)**: send only the event itself without the event value.<br>- **Values and revenue**: send all the event parameters, **including** the revenue value (if exists in the event). According to Unity Ads, this option is recommended.<br>- **Values without revenue**: send all the parameters **excluding** the revenue value. |

> 📘 Note
>
> You can send [ad revenue postbacks](https://support.appsflyer.com/hc/articles/217490046#ad-revenue-event-postbacks-for-ad-networks) to MOLOCO using the `af_ad_revenue` event so they can optimize campaigns.

## Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](https://support.appsflyer.com/hc/articles/115005248543-OneLink-overview).

[Learn more about attribution link structure and parameters](https://support.appsflyer.com/hc/articles/207447163).

**To generate an attribution link,** follow [these instructions](https://support.appsflyer.com/hc/articles/4410395957521#attribution-link-tab).

## Cost tab

AppsFlyer gets cost details by API. See the [ad network cost integration table](https://support.appsflyer.com/hc/articles/207040526-Ad-cost-measurement-guide#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

- Follow [these integration instructions](https://support.appsflyer.com/hc/articles/360008850257#enable-cost-api).

Yesterday's data is available from Moloco at approximately 4 AM (depending on the time zone settings in your MOLOCO account). For example, If the event occurred on Monday, cost data can be pulled by AppsFlyer on Tuesday at approximately 4 AM. After pulling the MOLOCO cost data, AppsFlyer analyzes and prepares the data and once this process is complete, the data can be consumed.

[View your cost API status](https://support.appsflyer.com/hc/articles/360008850257#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

## Ad revenue tab

Ad Revenue integration is not available for this partner.

## Permissions tab

In this tab, you can select the permissions to grant MOLOCO, whether the partner acts as an ad network, agency, or both. Note that even if attribution is disabled for MOLOCO, the permissions tab is active and you can grant control to MOLOCO.

### Ad Network Permissions

<Image src="https://files.readme.io/f443306f1b56197709308c0a33e436dc26adc7a0e80e6c2887edc63a5697b6d4-360002616197.png" alt="MOLOCO permissions configuration" />

Use these toggles to give the ad network permissions to handle its own configuration for your app:

- **Allow to configure integration** - permit the partner to set up the integration tab (except in-app event postbacks)
- **Allow to configure in-app event postbacks** - permit the partner to setup in-app event postbacks mapping to itself on the Integration tab
- **Allow access to your retention report** - only to the partner's own retention data
- **Allow access to your Protect360 dashboard** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).