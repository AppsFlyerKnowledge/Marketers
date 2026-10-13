---
title: "CleverTap integration with AppsFlyer"
excerpt: "Learn how to set up and configure the CleverTap integration with AppsFlyer to measure user retention, lifetime value, and owned media campaigns."
x-zendesk:
  id: 360001299165
  url: https://support.appsflyer.com/hc/en-us/articles/360001299165-CleverTap-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: 3rd-party platforms
  section_id: 6551199962257
  position: 6
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Ad Networks]
  labels: [Advertisers, Ad Networks, Clevertap, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2018-07-12T06:26:58Z'
  edited_at: '2026-06-16T11:23:22Z'
---
At a glance: CleverTap is a modern, integrated retention cloud that empowers digital consumer brands to increase customer retention and lifetime value.

![clevertap-logo.png](https://files.readme.io/ee01a7da1ae0c77758e279c47f2f588d90fdb7f52dce51161fce3891cc5fd498-4405112002833.png)

> ❗️ Important!
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up CleverTap

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below:

### Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partner

This toggle must be enabled for as long as you work with the partner.

Learn more about [partner activation](/docs/partner-activation-deactivation#activating-a-partner).

### General settings

**Account Token**

CleverTap connects with AppsFlyer via a unique Account Token, Region, Account Passcode, and Account ID. If you don't already have them, you must obtain them from CleverTap to continue with the integration or follow the steps below.

> ❗️ Important!
>
> To allow sending postbacks to CleverTap, make sure to complete **both** of the following steps:
>
> - Complete at least **one** of the following fields: account\_token, account\_passcode, or account\_id
> - In the AppsFlyer SDK, set the value of Customer User ID ( [iOS, Android](/docs/customer-user-id-field-cuid#setting-the-cuid)). See [CleverTap documentation](https://developer.clevertap.com/docs/appsflyer#section-step-2-integration) for guidelines on which parameter is recommended to use as your Customer User ID. Note that in case Customer User ID is empty, postbacks won't be sent to CleverTap.

![CleverTap_msc_new_2.png](https://files.readme.io/dd3f79fdce7dc4d48605f18021e328754d3e78aae98cb5214466c7489fd29fdf-360002305685.png)

### Obtain CleverTap account token

**To obtain account tokens from CleverTap:**

1. In the CleverTap dashboard, go to **Settings** in the top-right corner.

![CleverTap_msc_new_4.png](https://files.readme.io/2fd248582c3e267b2eaacfc6bf49068bdd4c6811b066c8286f0059e18d8535ae-360002541969.png)

At the very top of the “Settings” view, you’ll see your CleverTap Account ID, Account token, and Passcode next to "Account ID", “Account token”, and “Passcode”, respectively:

![CleverTap_msc_new_5.png](https://files.readme.io/795086dfc16cdee369b470e0b598b5089fff6469c77d0ccbf929e230d94191c8-360002537945.png)

2. To reveal the values, click the ‘eye’ icons next to each field.
3. Copy the values and paste them into the AppsFlyer CleverTap page.

> 📘 Note
>
> - The region depends on the CleverTap dashboard URL for your account:
>   - If your account URL is [https://eu1.dashboard.clevertap.com](https://eu1.dashboard.clevertap.com/), the region is EU1, meaning that the account data is hosted in an EU-based data center.
>   - If your account URL is [https://in1.dashboard.clevertap.com](https://in1.dashboard.clevertap.com/), the region is IN1, meaning that the account data is hosted in an IN-based data center.
>   - If your account URL is [https://aps3.dashboard.clevertap.com](https://aps3.dashboard.clevertap.com/), the region is ID, meaning that the account data is hosted in an Indonesia-based data center.
> - The region setting is case-sensitive and must be used with capital letters only. When lowercase letters are used, the postback will be sent to the default server (EU1).

4. Finalize the integration according to [CleverTap's documentation](https://developer.clevertap.com/docs/appsflyer#section-step-2-integration).

### Default postbacks

AppsFlyer can send automatic postbacks to CleverTap following user installs. Use this section to define the source of the users that the postbacks are sent to for each event. Learn more about [default postbacks](/docs/set-up-an-integrated-partner#default%20postbacks).

![clevertap-default-postbacks_en-us.png](https://files.readme.io/58424df9f5e8ba0e30e2390e26e0ecec7fc827baa43f3b812181caa2283dca0a-360014085238.png)

**To send postbacks for any user that downloads the app to CleverTap:** select **All media sources, including organic**.

### In-app events settings

![clevertap-in-app-events_en-us.png](https://files.readme.io/2ccc8a5a62cd601c45647d72caff0d94af814f78d9e1a8ae1548f973ed4c554f-360014005017.png)

In this section, you map AppsFlyer events with the partner via postbacks.

Learn more about [in-app event postbacks.](/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration)

**To configure in-app events postbacks:**

1. Enter all the required tokens.
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

Cost data is not applicable for this partner.

## Ad revenue tab

Ad Revenue data is not applicable for this partner.

## Permissions tab

Permissions are not available for CleverTap.

## Measure CleverTap owned media

Since CleverTap is a platform that uses emails, SMS, push notifications, etc., for marketing automation purposes, you can use [AppsFlyer OneLink](/docs/onelink-guide) as a solution for measuring owned media that originates from CleverTap.