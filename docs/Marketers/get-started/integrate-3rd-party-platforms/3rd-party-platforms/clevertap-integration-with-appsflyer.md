---
title: CleverTap integration with AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Clevertap
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2018-07-12T06:26:58Z'
  edited_at: '2026-06-16T11:23:22Z'
  id: 360001299165
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360001299165-CleverTap-integration-with-AppsFlyer
---
> **At a glance:** CleverTap is a modern, integrated retention cloud that empowers digital consumer brands to increase customer retention and lifetime value.

<Image align="center" alt="clevertap-logo.png" src="https://files.readme.io/ee01a7da1ae0c77758e279c47f2f588d90fdb7f52dce51161fce3891cc5fd498-4405112002833.png" width="193px" />

<div id="important" />

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions#media-source-restrictions">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

<div id="setting-up-clevertap" />

## Setting up CleverTap

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below:

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

<div id="activate-partner" />

### Activate partner

This toggle must be enabled for as long as you work with the partner.  
Learn more about <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation#activate-a-partner-integration">partner activation</Anchor>.

<div id="general-settings" />

### General settings

**Account Token**

CleverTap connects with AppsFlyer via a unique Account Token, Region, Account Passcode, and Account ID. If you don't already have them, you must obtain them from CleverTap to continue with the integration or follow the steps below.

<div id="important-1" />

> 🚧 **Important!**
>
> To allow sending postbacks to CleverTap, make sure to complete **both** of the following steps:
>
> * Complete at least **one** of the following fields: account\_token, account\_passcode, or account\_id
> * In the AppsFlyer SDK, set the value of Customer User ID (<Anchor target="_blank" href="/marketers/docs/customer-user-id-field-cuid#setting-the-cuid">iOS, Android</Anchor>). See [CleverTap documentation](https://developer.clevertap.com/docs/appsflyer#section-step-2-integration) for guidelines on which parameter is recommended to use as your Customer User ID. Note that in case Customer User ID is empty, postbacks won't be sent to CleverTap.

<Image align="center" alt="CleverTap_msc_new_2.png" src="https://files.readme.io/dd3f79fdce7dc4d48605f18021e328754d3e78aae98cb5214466c7489fd29fdf-360002305685.png" />

<div id="obtain-clevertap-account-token" />

### Obtain CleverTap account token

**To obtain account tokens from CleverTap:**

1. In the CleverTap dashboard, go to **Settings** in the top-right corner.

   <Image align="center" alt="CleverTap_msc_new_4.png" src="https://files.readme.io/2fd248582c3e267b2eaacfc6bf49068bdd4c6811b066c8286f0059e18d8535ae-360002541969.png" />
   At the very top of the “Settings” view, you’ll see your CleverTap Account ID, Account token, and Passcode next to "Account ID", “Account token”, and “Passcode”, respectively:

   <Image align="center" alt="CleverTap_msc_new_5.png" src="https://files.readme.io/795086dfc16cdee369b470e0b598b5089fff6469c77d0ccbf929e230d94191c8-360002537945.png" />
2. To reveal the values, click the ‘eye’ icons next to each field.
3. Copy the values and paste them into the AppsFlyer CleverTap page.

   <div id="note" />

   > 📘 **Note**
   >
   > * The region depends on the CleverTap dashboard URL for your account:
   > * If your account URL is <Anchor target="_blank" href="https://eu1.dashboard.clevertap.com/">https://eu1.dashboard.clevertap.com</Anchor>, the region is EU1, meaning that the account data is hosted in an EU-based data center.
   > * If your account URL is <Anchor target="_blank" href="https://in1.dashboard.clevertap.com">https://in1.dashboard.clevertap.com</Anchor>, the region is IN1, meaning that the account data is hosted in an IN-based data center.
   > * If your account URL is [https://aps3.dashboard.clevertap.com](https://aps3.dashboard.clevertap.com), the region is ID, meaning that the account data is hosted in an Indonesia-based data center.* The region setting is case-sensitive and must be used with capital letters only. When lowercase letters are used, the postback will be sent to the default server (EU1).

4. Finalize the integration according to <Anchor target="_blank" href="https://developer.clevertap.com/docs/appsflyer#section-step-2-integration">CleverTap's documentation</Anchor>.

<div id="default-postbacks" />

### Default postbacks

AppsFlyer can send automatic postbacks to CleverTap following user installs. Use this section to define the source of the users that the postbacks are sent to for each event. Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#default-postbacks">default postbacks</Anchor>.

<Image align="center" alt="clevertap-default-postbacks_en-us.png" src="https://files.readme.io/58424df9f5e8ba0e30e2390e26e0ecec7fc827baa43f3b812181caa2283dca0a-360014085238.png" />

**To send postbacks for any user that downloads the app to CleverTap:** select **All media sources, including organic**.

<div id="in-app-events-settings" />

### In-app events settings

<Image align="center" alt="clevertap-in-app-events_en-us.png" src="https://files.readme.io/2ccc8a5a62cd601c45647d72caff0d94af814f78d9e1a8ae1548f973ed4c554f-360014005017.png" />

In this section, you map AppsFlyer events with the partner via postbacks.  
Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">in-app event postbacks.</Anchor>

**To configure in-app events postbacks:**

1. Enter all the required tokens.
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

Cost data is not applicable for this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue data is not applicable for this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Permissions are not available for CleverTap.

</Accordion>

<div id="measure-clevertap-owned-media" />

## Measure CleverTap owned media

Since CleverTap is a platform that uses emails, SMS, push notifications, etc., for marketing automation purposes, you can use <Anchor target="_blank" href="/marketers/docs/onelink-guide">AppsFlyer OneLink</Anchor> as a solution for measuring owned media that originates from CleverTap.

<div data-zendesk-anchors="h_01H9FK5JT1TM77CAH0JTDCV376=important h_01H9FK5JT1ATCHY6WAVB6E2YEW=setting-up-clevertap h_01HKW9C39FKN3QN21NKDS6N3BQ=integration-tab h_01H9FK5JT12Z1M6WW3GQQF5QVN=activate-partner h_01H9FK5JT1FMC6JANBP9KBB0V2=general-settings h_01H9FK5JT1MQKT7KWJ3EVNEA1E=important-1 h_01H9FK5JT1RVJ1V0CGXSH1XZPM=obtain-clevertap-account-token h_01H9FK5JT2QV9CKSZ1N3S4WTGE=note h_01H9FK5JT2CE0WQ9HAGVGAQA5B=default-postbacks inapp-events-settings=in-app-events-settings h_01H9FK5JT2YS7G5WDD4F5MPYVZ=in-app-events-settings h_01H9FK5JT2939VDXQCDDG7MZ0R=attribution-link-tab h_01H9FK5JT2AEDDCD11K77WJHBX=cost-tab h_01H9FK5JT2WYWRGZAS1HBYYBSJ=ad-revenue-tab h_01H9FK5JT2FD6WN3Z1RET108JZ=permissions-tab h_01H9FK5JT2AZTT5936DD88ZZV3=measure-clevertap-owned-media" />
