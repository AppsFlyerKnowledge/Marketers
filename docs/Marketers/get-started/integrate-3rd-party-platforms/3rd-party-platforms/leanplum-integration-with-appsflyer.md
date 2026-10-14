---
title: Leanplum integration with AppsFlyer
excerpt: >-
  Leanplum, an AppsFlyer integrated partner, is a mobile marketing platform,
  designed for intelligent action. Its integrated solution delivers engagement
  across messaging and the in-app experience. Leanplum offers Messaging,
  Automation, App Editing, Personalization, A/B Testing, and Analytics.
metadata:
  keywords:
    - Leanplum
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2016-08-08T13:41:18Z'
  edited_at: '2026-06-16T09:59:12Z'
  id: 211487846
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/211487846-Leanplum-integration-with-AppsFlyer
---
> 📘 **Important!**
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Leanplum

Leanplum customers can integrate with AppsFlyer by sending Leanplum a postback containing publisher information. This allows you to view this data in Leanplum analytics as well as use it for targeting in A/B tests or marketing campaigns, using Leanplum’s targeting and segmentation menu.

Before you activate the integration with AppsFlyer, you first must confirm that your Leanplum integration is using the same device ID as Appsflyer. This is important as Leanplum matches the user install with the postback using the device ID, so if they do not match Leanplum cannot report the data.

By default, Leanplum collects the IDFV for iOS and the MD5 hash of the MAC address for Android, but this can be easily changed to IDFA for iOS and GAID for Android with one line of code. For information about how to change the device ID format for Android and iOS, click [here](https://docs.leanplum.com/docs/which-device-id-format-should-i-use).

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

The Leanplum configuration window uses only the **Integration** tab.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable the set up of the Integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

### General settings

**App ID and Client Key**

Leanplum connects with AppsFlyer via a unique App ID and Client Key. If you don't already have them, you must obtain them from Leanplum to continue with the integration or follow the steps below.

![Leanplum_msc_new_3.png](https://files.readme.io/0ef9adb16568192e922b33688a0525a3e61bc0f18dfc63e3717390adc34a66c4-360001904209.png)

**Sending IDFA or IDFV**

If the option is active, IDFV is sent in a postback. If no IDFV is found, IDFA is sent as a fallback.

If the option is inactive, IDFA is sent in a postback. If no IDFA found, IDFV is sent as a fallback.

If neither is available, no postback is sent.

### Obtaining the app ID and client key

Click on your name at the top right of the screen and select **App Settings**

![](https://files.readme.io/fcb9bb4fab1eec1db130904c2c4856529f58582bd8c9c04f08200ed82c0fcb80-206117303.png)

Select an app and click **Keys & Settings**

[![](https://files.readme.io/5608bddb2c31b1569e3d2e262946e239f3e637e5ac5d95bc24a03c3ff0d8d763-206117323.png)](https://files.readme.io/5608bddb2c31b1569e3d2e262946e239f3e637e5ac5d95bc24a03c3ff0d8d763-206117323.png)

![](https://files.readme.io/cd638732b197f03c6194b8bae7b8f726a6e4c16661702fdad48054a35ce333e5-206117343.png)

### Default postbacks

AppsFlyer can send automatic postbacks to Leanplum user installs. Use this section to define sending these postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/bb7f10cea006b95701be3fd4beb33fd237e1aa59a148bf2dd88935bf61aed2e1-18274529202193.png)

Select **Events attributed to any partner or organic** to send postbacks for any user that downloads the app to Leanplum.

Click **Save.**

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution links are not available for Leanplum.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Permissions are not available for Leanplum.

</Accordion>

## Viewing user attribution data in Leanplum

Once you have set up the integration between Leanplum and Appsflyer, you can access the information by utilizing Leanplum’s targeting and segmentation menu:

[![](https://files.readme.io/5685cfe357930bd57611365d7f47fff1608a8e7c345110070763af26374e01bc-206117523.png)](https://files.readme.io/5685cfe357930bd57611365d7f47fff1608a8e7c345110070763af26374e01bc-206117523.png)

This menu is available in the Analytics, Messages, A/B Tests, and Users sections of the Leanplum platform. You can filter by, group by, and cohort by this data in Analytics, filter by this data in the Users section, and target by this data in Analytics and A/B Tests.

<div data-zendesk-anchors="h_01H9FKB51R253NAXWEKSYVRZ3P=important h_01H9FKB51RA35X0G19ZPN2KAQ7=setting-up-leanplum h_01H9FKB51VVVS5C4WEQ4FKHH4H=integration-tab h_01H9FKB51VY7QASRV8XW8KRZK1=activate-partner h_01H9FKB51VA8A6XZYM3W6AVNMH=general-settings h_01H9FKB51VFGCW21AG0BYWGFXZ=obtaining-the-app-id-and-client-key h_01H9FKB51V63GPAS3R1GBWNTWR=default-postbacks h_01H9FKB51VR8160P1RQK994DGZ=attribution-link-tab h_01H9FKB51VEJWHZXKENFASR9NG=cost-tab h_01H9FKB51V7C44MGTWR3RNX4D8=ad-revenue-tab h_01H9FKB51VY9V478W297NB58EM=permissions-tab h_01H9FKB51VHAYS1STK6GQE4515=viewing-user-attribution-data-in-leanplum" />
