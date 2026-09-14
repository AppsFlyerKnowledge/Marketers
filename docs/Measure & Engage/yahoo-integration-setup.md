---
title: "Yahoo integration setup"
excerpt: "Learn how to set up mobile attribution, cost, and view-through tracking with Yahoo in AppsFlyer."
---
Yahoo, an AppsFlyer ad network integrated partner, offers search and native advertising in one advertising platform. In addition to click-based mobile attribution, Yahoo offers cost and view-through attribution, which can be recorded with AppsFlyer.

## Setting up Yahoo

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

> 👍 Tip
>
> The [General Settings](/docs/set-up-an-integrated-partner#d-general%20settings) step in the Integration tab is **mandatory**. All other steps are descriptive or **optional**.

## Integration tab

### Advertiser configuration

The Integration tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to switch on the _**Activate Partner**_ toggle to enable the setup of the Integration tab parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

### General settings

Follow these steps for the general settings of Yahoo.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Yahoo.

You can customize this value to 1-23 hours or 1-30 days. We recommend setting the Click-through lookback window to 7 days, to align with Yahoo.

More details about the [click lookback window here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

**Enable View-Through attribution**

Turn this to on if you want to attribute view-through installs from Yahoo. The view-through lookback slider is available on the attribution link tab (described below).

You can customize this value to 1-23 hours or 1-7 days. We recommend setting the View-through lookback window to 1 day, to align with Yahoo.

### Agency configuration

Before you start working with Yahoo, the advertiser should activate the integration on their side, otherwise conversions cannot be attributed to you.

For your Yahoo account, enter your Yahoo account ID. For Yahoo DSP, enter the Advertiser ID.

> 📘 Note
>
> - In case the Advertiser and Agency both promote the app on Yahoo, they need to work with separate Yahoo accounts.
> - Agency can use only one account at Yahoo.

To find your account ID, log into the Yahoo dashboard, click the cog icon to open the _**Settings**_ menu, and select _**Billing**_:

![gemini-account-number.png](https://files.readme.io/77f464c6dadefc54acb3a84d97ab0d0751610b253d2da90523bc117f1f26683c-50705625726865.png)

Click-through and view-through lookback windows are in read-only mode and should be configured by the advertiser.

### In-app events settings

In this section, you can map your AppsFlyer events with Yahoo via postbacks.

1. Enter the Dot Tag ID provided by Yahoo.

To find it on the Yahoo dashboard, click the cog icon to open the **Settings** menu and select **View Dot tag code**. Copy the code from the dashboard:

![yahoo-dot-tag.png](https://files.readme.io/6ceaea7447d1c3a81451dac3aa7c3c3063a5cf2c0051b4dfad6cf7aeba40ab24-small-50705593680401.png)

2. Turn on In-App Event Postbacks
3. Select the Sending Option for all SDK-defined events.

**- Only events attributed to this partner** for events coming **only** from users attributed to this partner

**- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list
5. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app or from server-to-server events.<br>**Tip** \- If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on the Yahoo side.<br>Obtain the corresponding Event ID from Yahoo and set in the text field. |
| **Send Revenue** | **When unchecked** \- sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.<br>**When checked** \- sends all the parameters including the revenue value (if it exists in the event). |

> 📘 Note
>
> For agencies, the _**Sending option**_ and the list of events available for mapping depend on the permissions given to the agency by the advertiser.

## Attribution link tab

This tab is not applicable for Yahoo.

> 📘 Note
>
> For all SRNs, such as Meta ads, Apple Search Ads, Adwords, Snapchat, etc. this tab is not functional, as they do not use external attribution links.

## Cost tab

### Enabling and testing Yahoo cost integration

The cost integration provides the following aggregated data:

- Cost data for your campaigns, adsets, ads, and geos/countries. See the [ad network cost integration table](https://support.appsflyer.com/hc/articles/207040526-Ad-cost-measurement-guide#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features.

> 📘 Note
>
> Cost data requires an [ROI360](/docs/roi360-cost-aggregation-overview) subscription.

- Data on clicks, impressions, and enriched data (keywords, campaign names, and adset).

**To enable the cost API**:

- Follow [these integration instructions](https://support.appsflyer.com/hc/articles/360008850257#enable-cost-api).

[View your cost API status](https://support.appsflyer.com/hc/articles/360008850257#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

> 🚧 Warning
>
> Once you set Yahoo's cost do not change the name of any running campaign, ad set, or single ad, as it may cause serious discrepancies or missing cost data.

## Ad revenue tab

Ad Revenue is not supported by this partner.

## Permissions tab

In this tab, you can select the permissions to grant Yahoo. Note that even if attribution is disabled for Yahoo, the permissions tab is active and you can grant control to Yahoo.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

- _**Allow to configure integration**_ \- permit the partner to set up the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ \- permit the partner to set up in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ \- only to the partner's own retention data
- _**Allow access to your aggregate loyal user data**_ \- only to the partner's own loyal user data
- _**Allow access to your aggregate in-app events data**_ \- only to the partner's own in-app events data
- _**Allow access to your aggregate revenue data**_ \- only to the revenue data attributed to the partner
- _**Allow access to your Protect360 dashboard**_ \- only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).

## Marking events as conversions in Yahoo

You can mark as conversions the events that AppsFlyer sends to Yahoo through in-app event postbacks:

![yahoo-conversion-rules.png](https://files.readme.io/17a3fdd1619d4e4d0bfcca35e4fd51e7f270ce7446f9e70fb6f7787291e2e022-50705625729297.png)

## Yahoo raw report

AppsFlyer receives the following parameters from Yahoo and maps them to the following fields in the raw reports.

| Yahoo Parameters | AppsFlyer Raw Report Parameters |
| --- | --- |
| Creative ID | Ad ID |
| Creative Name | Ad |
| Adgroup ID | Adset ID |
| Adgroup Name | Adset |
| Campaign ID | Campaign ID |
| Campaign Name | Campaign |
| Site ID | Site ID |

## Limitations

- When you enable attribution for the first time, it takes up to 4 hours to be reflected in the Yahoo UI.

## SKAdNetwork support

SKAdNetwork interoperation with Yahoo is available.