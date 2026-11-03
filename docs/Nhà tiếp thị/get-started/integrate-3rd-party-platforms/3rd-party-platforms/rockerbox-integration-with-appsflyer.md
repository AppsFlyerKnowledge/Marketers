---
title: Rockerbox integration with AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2020-11-23T14:55:00Z'
  edited_at: '2026-06-16T09:41:31Z'
  id: 360015760757
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360015760757-Rockerbox-integration-with-AppsFlyer
---
> **At a glance:** Learn how to automatically share data from AppsFlyer to Rockerbox, a marketing and analytics platform for mobile and web apps.

![rockerbox-logo_en-us.png](https://cdn.appsflyer.com/marketplace/static/logo/rockerbox.png)

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions#hạn-chế-nguồn-truyền-thông">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Rockerbox

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

This toggle must be enabled for as long as you work with the partner.  
Learn more about <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation#activate-a-partner-integration">partner activation</Anchor>.

### General settings

**Rockerbox Account ID**

**To connect your Rockerbox account with AppsFlyer,** enter your account ID in **Rockerbox account ID**.   
Your Rockerbox account ID is available in the Rockerbox platform under **Settings** > **Account** > **General**.

### Default postbacks

AppsFlyer can send automatic postbacks to Rockerbox following user installs. Use this section to define the source of the users the postbacks are sent to for each event. Learn more about <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#default-postbacks">default postbacks</Anchor>.

To send postbacks for any user that downloads the app to Rockerbox, select **All media sources, including organic**.

### In-app events settings

![rockerbox-in-app-events_en-us.png](https://files.readme.io/3fc74bb16d6a1222d1d244bbb1083ff247e3315d0fc7060e0ec3e8ad30a07233-360013891517.png)

In this section, you map AppsFlyer events with the partner via postbacks. Learn more about <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">in-app event postbacks.</Anchor>

**To configure in-app events postbacks:**

1. Enter the **Rockerbox Account ID**.
2. Enable **In-app event postback.**
3. Click **Add Event** to add an SDK Event to the list.
4. Select the **SDK event name** from the dropdown menu.
5. Select the required option from the Send revenue dropdown menu:
   * **No values & no revenue:** sends only the event itself without the event value.
   * **Values & no revenue:** sends all the parameters excluding the revenue value.
   * **Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event).
6. To complete the integration configuration, click **Save Integration**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for this partner.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is not applicable in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not applicable in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Permissions are not available for this partner.

</Accordion>

<div data-zendesk-anchors="h_01H9HWJW82HZ9FR31VHHRBZ3EM=important h_01H9HWJW83BKP8DSYTV6YGPHK7=setting-up-rockerbox h_01H9HWJW83WDGQKKMM942NPA1S=integration-tab h_01H9HWJW83Z4NGT000091AHX0Z=activate-partner h_01H9HWJW832NQBPK2VS6TS1QK7=general-settings h_01H9HWJW83CGMBADDBP7EJTR9N=default-postbacks inapp-events-settings=in-app-events-settings h_01H9HWJW84H4SDVRNZAG1D6N0D=in-app-events-settings h_01H9HWJW84G6GXMBTGMHTDPM6R=attribution-link-tab h_01H9HWJW84BZNHN4DRKA33WCVK=cost-tab h_01H9HWJW848DRTKBF3AKR5KYC5=ad-revenue-tab h_01H9HWJW84NTZWKP2FP2WK4FZD=permissions-tab" />
