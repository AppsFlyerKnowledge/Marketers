---
title: "YouAppi campaign configuration"
excerpt: "Configure your mobile growth marketing campaigns with YouAppi, including attribution links, cost API integration, and partner permissions."
---
YouAppi, an AppsFlyer ad network integrated partner, is a leading mobile growth marketing platform for premium mobile brands. In addition to click-based mobile attribution, YouAppi offers cost, ad revenue, retargeting and view-through attribution, which can be recorded with AppsFlyer.

To configure your campaigns with YouAppi, follow the steps below.

## Setting up YouAppi

> 📘 Prerequisite
>
> An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

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

YouAppi's configuration includes 4 active tabs: Integration, Attribution link, Cost, and Permissions. Click on the items below to read about the tabs setup.

> 👍 Tip
>
> * The [General Settings](https://support.appsflyer.com/hc/articles/4410395957521#d-general%20settings) step in the Integration tab is **mandatory** for all partners.
> * All the rest of the steps are either descriptive or **optional**.

## Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to turn on the _**Activate Partner**_ toggle to enable setup of the Integration parameters. The toggle **must** be on for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

> 📘 Note
>
> As an ALL-Installs network, YouSppi prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to YouAppi.

### General settings

**trackerToken**

YouAppi connects with AppsFlyer via a trackerToken. If you don't already have the trackerToken, you must obtain it from YouAppi to continue with the integration.

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from YouAppi. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to YouAppi following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to YouAappi.

Select **Events attributed to any partner or organic** to have your entire user base available to be reported to YouAppi.

### In-app events settings

In this section, you can map your AppsFlyer events with YouAppi via postbacks.

1. Enter the trackerToken again.
2. Turn on In-App Event Postbacks.
3. Select the Sending Option for all SDK-defined events.

**- Only events attributed to this partner** for events coming **only** from users attributed to this partner.

**- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner.
4. Click **Add Event** to add an SDK Event to the list.
5. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app or from server-to-server events.<br>**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Youappi's side.<br>Obtain the corresponding Event ID from Youappi and set it in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af_revenue** parameter.<br>**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

## Attribution link tab

In this tab, you can create the attribution links you want to send to Youappi for attributing Youappi's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with Youappi.

**Attribution link parameter:** c
- **Adset** - set ad set name to compare different ad sets within specific Youappi campaigns.

**Attribution link parameter:** af_adset
- **Ad Name** - set ad name to compare different creatives within specific ad sets within specific campaigns Youappi.

**Attribution link parameter:** af_ad
- **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub-site ID parameter, to avoid [exceeding the site ID](https://support.appsflyer.com/hc/articles/115005099063-What-are-the-Exceeded-Media-Sources-#exceeded_siteid_limit) limitations.

**Attribution link parameters:** af_siteid and af_sub_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

**Attribution link parameters:** af_sub1, af_sub2, af_sub3, af_sub4, af_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about [**AppsFlyer's Attribution Link Structure and Parameters**](https://support.appsflyer.com/hc/articles/207447163) .

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to YouAppi.

**Attribution link parameter:** af_click_lookback

More details about the [click lookback window here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to YouAppi to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to YouAppi, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af_viewthrough_lookback

More details about the [view-through attribution here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to YouAppi to be activated when a corresponding ad is watched, usually for 1 second or more.

## Cost tab

AppsFlyer gets cost details by API. See the [ad network cost integration table](https://support.appsflyer.com/hc/articles/207040526-Ad-cost-measurement-guide#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

- Follow [these integration instructions](https://support.appsflyer.com/hc/articles/360008850257#enable-cost-api).

[View your cost API status](https://support.appsflyer.com/hc/articles/360008850257#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

## Ad revenue tab

Ad Revenue is not supported by this partner.

## Permissions tab

In this tab, you can select the permissions to grant YouAppi, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for YouAppi, the permissions tab is active and you can grant control to YouAppi.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

- _**Allow to configure integration**_ - permit the partner to set up the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to set up in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your aggregate loyal user data**_ - only to the partner's own loyal user data
- _**Allow access to your aggregate in-app events data** -_ only to the partner's own in-app events data
- _**Allow access to your aggregate revenue data**_ - only to the revenue data attributed to the partner
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

- _**Main toggle**_ - Set to On to reveal the agency permissions options
- _**Allow access to your retention report**_ - only to the agency's own retention data
- _**Allow access to aggregate organic data**_
- _**Allow to configure in-app event postbacks**_ - permit the agency to set up in-app event postbacks mapping to itself on the integration tab

Learn more about granting [agency permissions](https://support.appsflyer.com/hc/articles/4410395957521#agency-permissions).