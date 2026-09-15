---
title: "Convertro integration with AppsFlyer"
excerpt: "Learn how to set up the Convertro integration with AppsFlyer to measure and optimize your marketing performance."
---
**At a glance:** Convertro, an AppsFlyer integrated partner, strives to be the leading automated tool for marketers to truly understand the performance of their advertising choices and activate upon these insights as quickly as possible. They've built a technology that not only gathers granular information about the customer path to conversion, but is also able to scientifically optimize marketing mix and automatically understand how to shift spend to maximize ROI.

> 📘 **Important!**
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.


## Setting up Convertro

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

The Convertro configuration window uses only the **Integration** tab.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

## Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation, click [here](/docs/partner-activation-deactivation).

### General settings

**Page URL, Site ID, and Client Name**

Convertro connects with AppsFlyer via a unique Page URL, Site ID, and Client Name. If you don't already have them, you must obtain them from Convertro to continue with the integration or follow the instructions below.

[![](https://support.appsflyer.com/hc/article_attachments/360002220189)](https://support.appsflyer.com/hc/article_attachments/360002220189)

### Obtaining the "Client Name, Page URL & Site ID" From the Convertro Platform

To obtain the Client Name, Page URL, and Site ID, login to the Convertro dashboard:

**Page URL:**

[![](https://support.appsflyer.com/hc/en-us/article_attachments/204790263/Convertro4.png)](https://support.appsflyer.com/hc/en-us/article_attachments/204790263/Convertro4.png)

**Site ID:**

[![](https://support.appsflyer.com/hc/en-us/article_attachments/204790283/Convertro5.png)](https://support.appsflyer.com/hc/en-us/article_attachments/204790283/Convertro5.png)

**Client Name:**

![](https://support.appsflyer.com/hc/en-us/article_attachments/204595606/Convertro3.png)

### Default postbacks

AppsFlyer can send automatic postbacks to Convertro user installs. Use this section to define sending these postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/e0cf7b9ce9a13f572017dfc7bb4581430ddbfdd2e198fe20ef0b953c6c3188a6-18274456382865.png)

Select **Events attributed to any partner or organic** to send postbacks for any user that downloads the app to Convertro or select **Off**.

Click **Save.**

### In-app event settings

[![](https://support.appsflyer.com/hc/article_attachments/360002200405)](https://support.appsflyer.com/hc/article_attachments/360002200405)

In this section, you can map your AppsFlyer events with Convertro via postbacks.

1. Enter the Client Name, Site ID, and Page URL again.
2. Toggle In-App Event Postbacks to ON.
3. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list.
5. Complete the following parameters:



| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Convertro's side.  <br />Obtain the corresponding Event ID from Convertro and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |



Click **Save**.

Once this configuration is saved, AppsFlyer begins sending the following data to Convertro for every organic and non-organic install:

* Converto Parameters
* Device ID for Android and iOS
* Media Source
* Campaign name
* Click Time
* User IP
* User Agent
* Customer User ID (optional, if configured)

## Attribution link tab

Attribution Links are not available for Convertro.

## Cost tab

Cost data is not supported in the integration with this partner.

## Ad revenue tab

Ad Revenue is not supported in the integration with this partner.

## Permissions tab

Permissions are not available for Convertro.