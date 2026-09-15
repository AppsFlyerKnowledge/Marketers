---
title: "MoEngage campaign configuration"
excerpt: "Learn how to configure the MoEngage integration in AppsFlyer to send install and event postbacks to your customer engagement platform."
---
At a glance: MoEngage, a third-party customer engagement platform integrated with AppsFlyer, is an agentic customer engagement platform built for the mobile-first world.

> ❗️ Important!
>
> [Some media sources](https://support.appsflyer.com/hc/articles/360006868017-Raw-data-content-restriction-media-source-or-user-identifiers#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up MoEngage

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

5. Complete the configuration using the relevant tabs, as described below.

Learn more about [setting the partner page header.](https://support.appsflyer.com/hc/articles/4410395957521#about-the-integrated-partner-page)

## Integration tab

The **Integration** tab is divided into different sections, as described below.

### Activate partner

On your first visit, turn **Activate Partner** on to set up the integration. The toggle must be on for as long as you work with the partner. Learn more about [partner activation](https://support.appsflyer.com/hc/articles/360000844778).

### General settings

MoEngage connects with AppsFlyer via a unique App ID, App Key, and the Data Center of MoEngage. If you don't already have the App ID and App Key, you must obtain the first to continue with the integration:

* **APP\_ID:** Enter the app ID. To obtain it, log in to your MoEngage account from the left menu, and go to **Settings** > **App Settings**.
* **MoEngage Data Center:** Specify the MoEngage data center that you have signed up with. Learn more about [Data Centers in MoEngage](https://help.moengage.com/hc/en-us/articles/360057030512-Data-Centers-in-MoEngage).
* **APP\_KEY:** Enter the app API key. To obtain it, log in to your MoEngage account, and go to **Settings** > **Analytics**.

<Image src="https://files.readme.io/0180fb4ad22857320200b1f53a01c72c87fc6cc4a3f4aabcd585b2cfb0f7596a-8179576817809.png" alt="moengage_general_settings_en-us.png" />

### Default postbacks

AppsFlyer can send automatic postbacks to MoEngage following user installs. Select one of the following options:

* **Off**: Don't send any install postbacks.
* **All media sources, including organic**: Send postbacks for events attributed to any partner and for organic events.

<Image src="https://files.readme.io/9be309d681904a015fc0295b2ee463411f5c8fbaf450145b132e8ab37bda7665-17028057319697.png" alt="web_mo_engage_default_postbacks_en-us.png" />

> 📘 Note
>
> As an all-installs network, MoEngage prefers to receive postbacks for all new installs of your app from any source, including organic. MoEngage recommends selecting **All media sources, including organic**.

## Attribution link tab

**Attribution link** isn't supported in the integration with this partner.

## Cost tab

**Cost data** isn't supported in the integration with this partner.

## Ad revenue tab

**Ad revenue** isn't supported in the integration with this partner.

## Permissions tab

**Permissions** isn't supported in the integration with this partner.