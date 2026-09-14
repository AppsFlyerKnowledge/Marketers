---
title: "Leanplum integration with AppsFlyer"
excerpt: "Learn how to integrate Leanplum with AppsFlyer to send attribution data and postbacks for intelligent mobile marketing campaigns."
---
<Cards>
  <Card title="Setting up Leanplum" href="#setting-up-leanplum" />
  <Card title="Integration tab" href="#integration-tab" />
  <Card title="Attribution link tab" href="#attribution-link-tab" />
  <Card title="Cost tab" href="#cost-tab" />
  <Card title="Ad revenue tab" href="#ad-revenue-tab" />
  <Card title="Permissions tab" href="#permissions-tab" />
  <Card title="Viewing user attribution data in Leanplum" href="#viewing-user-attribution-data-in-leanplum" />
</Cards>

**At a glance:** Leanplum, an AppsFlyer integrated partner, is a mobile marketing platform, designed for intelligent action. Its integrated solution delivers engagement across messaging and the in-app experience. Leanplum offers Messaging, Automation, App Editing, Personalization, A/B Testing, and Analytics.

> ❗️ Important!
>
> [Some media sources](https://support.appsflyer.com/hc/articles/360006868017-Raw-data-content-restriction-media-source-or-user-identifiers#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Leanplum

Leanplum customers can integrate with AppsFlyer by sending Leanplum a postback containing publisher information. This allows you to view this data in Leanplum analytics as well as use it for targeting in A/B tests or marketing campaigns, using Leanplum’s targeting and segmentation menu.

Before you activate the integration with AppsFlyer, you first must confirm that your Leanplum integration is using the same device ID as Appsflyer. This is important as Leanplum matches the user install with the postback using the device ID, so if they do not match Leanplum cannot report the data.

By default, Leanplum collects the IDFV for iOS and the MD5 hash of the MAC address for Android, but this can be easily changed to IDFA for iOS and GAID for Android with one line of code. For information about how to change the device ID format for Android and iOS, click [here](https://docs.leanplum.com/docs/which-device-id-format-should-i-use).

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

The Leanplum configuration window uses only the **Integration** tab.

For a detailed description of the Partner Configuration Window Header, click [here](https://support.appsflyer.com/hc/articles/4410395957521#about-the-integrated-partner-page).

## Integration tab

The Integration tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle ON the _**Activate Partner**_ button to enable the set up of the Integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

### General settings

**App ID and Client Key**

Leanplum connects with AppsFlyer via a unique App ID and Client Key. If you don't already have them, you must obtain them from Leanplum to continue with the integration or follow the steps below.

<Image src="https://files.readme.io/0ef9adb16568192e922b33688a0525a3e61bc0f18dfc63e3717390adc34a66c4-360001904209.png" alt="Leanplum_msc_new_3.png" />

**Sending IDFA or IDFV**

If the option is active, IDFV is sent in a postback. If no IDFV is found, IDFA is sent as a fallback.

If the option is inactive, IDFA is sent in a postback. If no IDFA found, IDFV is sent as a fallback.

If neither is available, no postback is sent.

### Obtaining the app ID and client key

Click on your name at the top right of the screen and select **App Settings**

Select an app and click **Keys & Settings**

### Default postbacks

AppsFlyer can send automatic postbacks to Leanplum user installs. Use this section to define sending these postbacks.

<Image src="https://files.readme.io/bb7f10cea006b95701be3fd4beb33fd237e1aa59a148bf2dd88935bf61aed2e1-18274529202193.png" alt="Swrve_msc_new_4.png" />

Select **Events attributed to any partner or organic** to send postbacks for any user that downloads the app to Leanplum.

Click **Save.**

## Attribution link tab

Attribution links are not available for Leanplum.

## Cost tab

Cost data is not supported in the integration with this partner.

## Ad revenue tab

Ad Revenue is not supported in the integration with this partner.

## Permissions tab

Permissions are not available for Leanplum.

## Viewing user attribution data in Leanplum

Once you have set up the integration between Leanplum and Appsflyer, you can access the information by utilizing Leanplum’s targeting and segmentation menu:

This menu is available in the Analytics, Messages, A/B Tests, and Users sections of the Leanplum platform. You can filter by, group by, and cohort by this data in Analytics, filter by this data in the Users section, and target by this data in Analytics and A/B Tests.