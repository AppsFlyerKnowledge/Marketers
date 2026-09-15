---
title: "Rockerbox integration with AppsFlyer"
excerpt: "Learn how to automatically share data from AppsFlyer to Rockerbox, a marketing and analytics platform for mobile and web apps."
---
<Cards>
  <Card title="Setting up Rockerbox" href="#setting-up-rockerbox" />
  <Card title="Integration tab" href="#integration-tab" />
  <Card title="Attribution link tab" href="#attribution-link-tab" />
  <Card title="Cost tab" href="#cost-tab" />
  <Card title="Ad revenue tab" href="#ad-revenue-tab" />
  <Card title="Permissions tab" href="#permissions-tab" />
</Cards>

**At a glance:** Learn how to automatically share data from AppsFlyer to Rockerbox, a marketing and analytics platform for mobile and web apps.

![rockerbox-logo_en-us.png](https://files.readme.io/d21ed29ebfff58b6ce129b1767a7ce4e5dd0a90aab217b1d41aac5ca90e34003-rockerbox.png)

> ❗️ Important!
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Rockerbox

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

## Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partner

This toggle must be enabled for as long as you work with the partner.

Learn more about [partner activation](/docs/partner-activation-deactivation#activating-a-partner).

### General settings

**Rockerbox Account ID**

**To connect your Rockerbox account with AppsFlyer,** enter your account ID in **Rockerbox account ID**.

Your Rockerbox account ID is available in the Rockerbox platform under **Settings** > **Account** > **General**.

### Default postbacks

AppsFlyer can send automatic postbacks to Rockerbox following user installs. Use this section to define the source of the users the postbacks are sent to for each event. Learn more about [default postbacks](/docs/set-up-an-integrated-partner#default%20postbacks).

To send postbacks for any user that downloads the app to Rockerbox, select **All media sources, including organic**.

### In-app events settings

![rockerbox-in-app-events_en-us.png](https://files.readme.io/3fc74bb16d6a1222d1d244bbb1083ff247e3315d0fc7060e0ec3e8ad30a07233-360013891517.png)

In this section, you map AppsFlyer events with the partner via postbacks. Learn more about [in-app event postbacks.](/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration)

**To configure in-app events postbacks:**

1. Enter the **Rockerbox Account ID**.
2. Enable **In-app event postback.**
3. Click **Add Event** to add an SDK Event to the list.
4. Select the **SDK event name** from the dropdown menu.
5. Select the required option from the Send revenue dropdown menu:
   - **No values & no revenue:** sends only the event itself without the event value.
   - **Values & no revenue:** sends all the parameters excluding the revenue value.
   - **Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event).
6. To complete the integration configuration, click **Save Integration**.

## Attribution link tab

Attribution Links are not available for this partner.

## Cost tab

Cost data is not applicable in the integration with this partner.

## Ad revenue tab

Ad Revenue is not applicable in the integration with this partner.

## Permissions tab

Permissions are not available for this partner.