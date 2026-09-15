---
title: "RTB House campaign configuration"
excerpt: "Configure RTB House integration in AppsFlyer to enable deep learning-based retargeting and mobile attribution."
---
RTB House, an AppsFlyer ad network integrated partner, provides retargeting technology for e-commerce and gaming companies. RTB House has developed its own retargeting solution, based on deep learning algorithms, for purchasing online ads in the Real-Time Bidding model. In addition to click-based mobile attribution, RTB House offers retargeting attribution, which can be recorded with AppsFlyer. 

## Setting up RTB House

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

RTB House's configuration window includes 3 active tabs: **Integration, Attribution link**, and **Permissions**. Click on the items below to read about the tabs setup.

> 👍 Tip
>
> * The [General Settings](https://support.appsflyer.com/hc/articles/4410395957521#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**

## Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle on **Activate Partner** to enable setting up the integration parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

### Default postbacks

Send automatic postbacks to RTB House following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

> 📘 Note
>
> As an ALL-Installs network, RTB House prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to RTB House.

### In-app events settings

In this section, you can map your AppsFlyer events with RTB House via postbacks.

#### Region

Enter the region of your RTB House data center. Possible options: **emea**, **us**, **asia**.

#### In-app event postback settings

1. Toggle on In-App Event Postbacks
2. Select the Sending Option for all SDK-defined events.

**- Only events attributed to this partner** for events coming **only** from users attributed to this partner

**- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.<br>**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on RTB House's side.<br>Obtain the corresponding Event ID from RTB House and set in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af_revenue** parameter.<br>**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

## Attribution link tab

Create and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](https://support.appsflyer.com/hc/articles/115005248543-OneLink-overview).

[Learn more about attribution link structure and parameters](https://support.appsflyer.com/hc/articles/207447163) .

**To create an attribution link,** follow [these instructions](https://support.appsflyer.com/hc/articles/4410395957521#attribution-link-tab).

## Cost tab

Cost data is supported in the integration with this partner via [InCost API](/docs/incost-api-for-ad-networks).

## Ad revenue tab

Ad Revenue is not supported in the integration with this partner.

## Permissions tab

In this tab, you can select the permissions to grant RTB House, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for RTB House, the permissions tab is active and you can grant control to RTB House.

### Ad network permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

- _**Allow to configure integration**_ - permit the partner to set up the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to set up in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your aggregate loyal user data**_ - only to the partner's own loyal user data
- _**Allow access to your aggregate in-app events data**_ - only to the partner's own in-app events data
- _**Allow access to your aggregate revenue data**_ - only to the revenue data attributed to the partner
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).