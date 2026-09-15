---
title: "Spoteffects integration with AppsFlyer"
excerpt: "Learn how to set up the Spoteffects integration with AppsFlyer to optimize your TV campaigns based on immediately generated visits and conversions."
---
**At a glance:** Spoteffects, an AppsFlyer integrated partner, develops and markets the software as a service solution. The solution allows media planners to optimize their TV campaigns for online shops and websites based on immediately generated visits and conversions per ad.

> 📘 **Important!**
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.


## Setting up Spoteffects

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

The Spoteffects configuration window uses only the ***Integration*** tab.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

## Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

### Default postbacks

AppsFlyer can send automatic postbacks to Spoteffects user installs. Use this section to define sending these postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/a8cf728ceaa6ed9804dece249820496563f2a89aaf6a90275940e1be643646ab-18301290568465.png)

Select **Events attributed to any partner or organic** to send postbacks for any user that downloads the app to Spoteffects or select **Off**.

Click **Save.**

### In-app event settings

[![](https://support.appsflyer.com/hc/article_attachments/360002201165)](https://support.appsflyer.com/hc/article_attachments/360002201165)

In this section, you can map your AppsFlyer events with Spoteffects via postbacks.

1. Toggle In-App Event Postbacks to ON
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Complete the following parameters:



| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Spoteffect's side.  <br />Obtain the corresponding Event ID from Spoteffect and set it in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |



Click **Save**.

Once you have saved the configuration, AppsFlyer sends the following data to Spoteffects for every organic and non-organic install:

* Device ID (IDFA / Goggle Advertising ID)
* Media Source
* Campaign name

## Attribution link tab

Attribution Links are not available for Spoteffects.

## Cost tab

Cost data is not supported in the integration with this partner.

## Ad revenue tab

Ad Revenue is not supported in the integration with this partner.

## Permissions tab

Permissions are not available for Spoteffects.