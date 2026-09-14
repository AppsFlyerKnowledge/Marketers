---
title: "Chartboost campaign configuration"
excerpt: "Learn how to configure Chartboost integration in AppsFlyer, including setting up attribution links, cost API, ad revenue tracking, and permissions."
---
At a glance: Chartboost, an AppsFlyer ad network integrated partner, is one of the largest mobile games-only ad platforms to increase revenue. In addition to click-based mobile attribution, Chartboost also offers cost, ad revenue, and view-through attribution, which you can record with AppsFlyer.

> 📘 Note
>
> Integrating the Chartboost SDK is only necessary if you act as a Chartboost publisher and wish to attribute ad revenue. Otherwise, the AppsFlyer SDK is all that is required. For more information, see this article's [ad revenue section](https://support.appsflyer.com/hc/articles/209731553#ad-revenue-tab).

## Setting up Chartboost

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

## Integration tab

The _**Integration Tab**_ is divided into different sections as described below.

### Activate partners

The [partner must be activated](https://support.appsflyer.com/hc/articles/360000844778#activating-a-partner) by switching on the _**Activate partner**_ toggle on the first visit, to enable its setup.

### General settings

**Chartboost App ID and Signature**

Chartboost requires connecting with AppsFlyer via a unique app ID and a signature. If you do not know yours, you can obtain it directly from Chartboost.

**Enable View-Through attribution**

Toggle ON if you want to attribute view-through installs from Chartboost. The view-through lookback slider is available in the _**Attribution link**_ tab.

### Default postbacks

Send automatic postbacks to Chartboost following installs and rejected installs. Use this section to define the **source of the users** for the postbacks.

Select _**This partner only**_ for installs coming only from users attributed to Chartboost.

Select _**All sources, including organic**_ to have your entire user base available to be reported to Chartboost.

Rejected installs can be sent for **This partner only**.

#### Launch postbacks

As of July 1, 2020, we no longer send launch postbacks to Chartboost. If your integration was set up before this date, there may be changes to your configurations. The following table explains possible changes and your actions, where applicable:

| Your configuration | Will be updated to | Your next actions |
| --- | --- | --- |
| Send to Chartboost **all launches** (from all media sources, including organic) | Send to Chartboost:<br>- **all installs** (from all media sources, including organic)<br>- **all**`af_app_opened` **events** (from all media sources, including organic) | No further actions required. This update has no actual impact on the configuration. |

### In-app events settings

In this section, you can configure in-app event postbacks that are sent to Chartboost.

**To configure in-app event postbacks:**

1. Activate _**In-app event postback**_.
2. Choose whether to report selected events to the partner, or all of them.
   - Note: If you choose to report all events, the _af_app_opened_ event is not reported.
3. If you choose to manually select events, click _**Add event**_ to add an SDK Event to the list.

| Parameter name | Description |
| --- | --- |
| **SDK event name** _(required for manual selection only)_ | The name of the event, as received by AppsFlyer either from the SDK, or from server-to-server events.<br>**Tip**: If you don't see the event you want in the list, activate this event on a device with a non-organic installation and recheck. |
| **Sending option** | Select the sending option for the event:<br>**This partner only** for events coming **only** from users attributed to Chartboost.<br>**All sources, including organic** to have your entire user base available to be reported to the partner |
| **Send event data** | - **No values & no revenue:** sends only the event itself without the event value.<br> - **Values & no revenue:** sends all the parameters excluding the revenue value.<br> - **Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event). |

4. Click _**Save**_.

## Attribution link tab

In this tab, you can create the attribution links you want to send to Chartboost for attributing Chartboost campaigns, ad sets, or single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with Chartboost.

**Attribution link parameter:** c
- **Adset** - set ad set names to compare different ad sets within specific Chartboost campaigns.

**Attribution link parameter:** af_adset
- **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Chartboost.

**Attribution link parameter:** af_ad
- **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the subsite ID parameter, to avoid [exceeding the site ID](https://support.appsflyer.com/hc/articles/115005099063-What-are-the-Exceeded-Media-Sources-#exceeded_siteid_limit) limitations.

**Attribution link parameters:** af_siteid and af_sub_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

**Attribution link parameters:** af_sub1, af_sub2, af_sub3, af_sub4, af_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about [**AppsFlyer Attribution Link Structure and Parameters**](https://support.appsflyer.com/hc/articles/207447163).

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Chartboost.

**Attribution link parameter:** af_click_lookback

More details about the [click lookback window here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Chartboost to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to Chartboost, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af_viewthrough_lookback

More details about the [view-through attribution here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to Chartboost to be activated when a corresponding ad is watched.

## Cost tab

AppsFlyer gets cost details by API. See the [ad network cost integration table](https://support.appsflyer.com/hc/articles/207040526-Ad-cost-measurement-guide#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

- Follow [these integration instructions](https://support.appsflyer.com/hc/articles/360008850257#enable-cost-api).

[View your cost API status](https://support.appsflyer.com/hc/articles/360008850257#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

## Ad revenue tab

This section is relevant if you are acting as a publisher, displaying ads of the partner to your users. As such, you would certainly like to measure the engagement of your users acquired from different sources, to find the most profitable sources for you.

**To enable the ad revenue API**:

- Follow [these integration instructions](https://support.appsflyer.com/hc/articles/217490046-Ad-revenue-attribution-guide#connect-to-ad-revenue-integrated-partners).

> ❗️ Important!
>
> As a Chartboost publisher, there are two additional requirements besides AppsFlyer configuration:
>
> 1. [Integrate Chartboost SDK](https://answers.chartboost.com/en-us/child_article/ios) - this is only required if you act as a publisher. **If you only use Chartboost to advertise your app, AppsFlyer SDK is all you need to integrate**.
> 2. [Enable Chartboost S2S](https://answers.chartboost.com/en-us/child_article/s2s-setup) - this step is required to allow AppsFlyer to query Chartboost for ad revenue data. **This should not be confused with** [**AppsFlyer S2S**](https://support.appsflyer.com/hc/articles/207034486) **which is your way of sending in-app events to AppsFlyer using a dedicated API.**

## Permissions tab

In this tab, you can select the permissions to grant Chartboost, whether the partner acts as an ad network, agency, or both. Note that even if attribution is disabled for Chartboost, the permissions tab is active and you can grant control to Chartboost.

Use these toggles to give the ad network permissions to handle its own configuration for your app: Ad Network Permissions

- _**Allow to configure integration**_ - permit the partner to set up the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your aggregate loyal user data**_ - only to the partner's own loyal user data
- _**Allow access to your aggregate in-app events data**_ - only to the partner's own in-app events data
- _**Allow access to your aggregate revenue data**_ - only to the revenue data attributed to the partner
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).

## Discrepancies between Chartboost and AppsFlyer

Sometimes there are discrepancies between the Chartboost dashboard and AppsFlyer dashboard.

Advertisers should be aware of the following reasons:

| Cause | Chartboost | AppsFlyer |
| --- | --- | --- |
| **Attribution Window** | Chartboost attribution window is 21 days | AppsFlyer lookback window is 7 days<br>**\*\* This is the main cause of discrepancies between AppsFlyer and Chartboost** |
| **Multi-Channel Source Attribution** | Chartboost attribution works as specified above regardless of other sources. | AppsFlyer uses the last click attribution (For more information about AppsFlyer attribution, click [here](https://support.appsflyer.com/hc/articles/207447053 "AppsFlyer Attribution Model")) |

> 📘 Note
>
> While Chartboost shows all installs of a retargeting campaign in the same place, on the AppsFlyer dashboard, installs are divided between the Overview page (new installs) and the Retargeting page (re-attribution and re-engagements).