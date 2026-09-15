---
title: "LINE Ads Platform campaign configuration"
excerpt: "Learn how to set up and configure the LINE Ads Platform integration in AppsFlyer, including attribution links, in-app event mapping, and multi-account settings."
---
At a glance: LINE Ads Platform, an AppsFlyer integrated partner combines a bidding and customized targeting system. In addition to click-based mobile attribution, LINE Ads Platform also offers retargeting attribution, which you can record with AppsFlyer.

## Setting up LINE Ads platform

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

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

The Integration Tab is divided into different sections as described below.

> 📘 Note
>
> As an ALL-Installs network, LINE prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to LINE. This can only be performed by the account owner.

### Activate partner

On the **first visit** here, you will need to toggle below. ON the _**Activate Partner**_ button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

### General settings

**Account ID and App ID**

LINE Ads Platform connects with AppsFlyer via a unique account and app ID, LINE\_Ad\_account\_id, and LINE\_Ad\_app\_ID.

**To connect your LINE Ads account to AppsFlyer:**

- Enter your unique **LINE\_Ad\_account\_id** and your **LINE\_Ad\_app\_ID**.

See [Line Line Ads documentation on creating a business ID](https://lineforbusiness.com/th-en/service/line-ads/manual#Tracking:~:text=Tracking%20app%20conversions).

#### Connect multiple accounts and apps

You can connect multiple Line Ads accounts and apps to AppsFlyer by manually adding an account ID or app ID parameter to an attribution link, after its creation.

> 📘 Note
>
> Parameters existing in both the attribution link and under the **General settings** lead to conflicts. To avoid this, see the **Parameter priority logic** described below before adding parameters to the attribution link.

**Parameter priority logic**

- When both parameter types, account ID and app ID (line\_ad\_account\_id, line\_ad\_app\_id), are included in the attribution link, any corresponding ID set in the General settings gets overridden.
- When one of the parameter types is missing from the attribution link but has been set in the General settings, the value set in the general settings will be included for the connection.
- When both parameter types, account ID and app ID, are missing from the General settings and attribution links, the integration may not function as intended.

**To connect multiple account ID and app ID parameters:**

1. Set up one or more [attribution links](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters).
2. Add to each attribution link an account ID and app ID parameter, using lower-case letters. See the highlighted part in the example below.

#### Example

An example attribution link with an account ID and app ID parameters:

```auto
Autohttps://app.appsflyer.com/id123456789?pid=example_int;...line_ad_account_id=A123456789123&line_ad_app_id=1234567891234&...;redirect=false
```

### Default postbacks

Send automatic postbacks to LINE Ads Platform following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to LINE Ads Platform.

Select **Events attributed to any partner or organic** to have your entire user base available to be reported to LINE Ads Platform.

### In-app events settings

In this section you can map your AppsFlyer events with LINE Ads Platform via postbacks.

1. Enter the LINE\_Ad\_app\_ID and LINE\_Ad\_account\_id again.
2. Toggle In-App Event Postbacks to ON.
3. Select the Sending Option for all SDK-defined events.

**- Only events attributed to this partner** for events coming **only** from users attributed to this partner

**- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. From the dropdown list select an _**SDK Event Name**_.
5. From the _**Partner Event Identifier**_ dropdown list, select the corresponding option.
6. Click _**Add Event**_ to add additional Event Names.
7. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated with your app or from server to server events.<br>**Tip** \- If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on LINE Ads Platform's side.<br>Obtain the corresponding Event ID from LINE Ads Platform and set it in the text field. |
| **Send Revenue** | **When unchecked** \- Send all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.<br>**When checked** \- Send all the parameters including the revenue value (if it exists in the event). |

### Custom in-app events mapping

AppsFlyer allows you to map any custom in-app event to send to LINE, by using the CUSTOM Partner Event Identifier option.

The event name and the event value (including the event parameters) configured in the SDK are forwarded to LINE, as is.

## Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](https://support.appsflyer.com/hc/articles/115005248543-OneLink-overview).

[Learn more about attribution link structure and parameters](https://support.appsflyer.com/hc/articles/207447163) **.**

**To generate an attribution link,** follow [these instructions](https://support.appsflyer.com/hc/articles/4410395957521#attribution-link-tab).

[Follow these instructions](https://lineforbusiness.com/th-en/service/line-ads/manual) to activate the attribution link in LINE Ads Platform.

## Cost tab

Cost data is not supported by this partner.

## Ad revenue tab

Ad Revenue is not supported by this partner.

## Permissions tab

No permission configurations are available for LINE Ads Platform.