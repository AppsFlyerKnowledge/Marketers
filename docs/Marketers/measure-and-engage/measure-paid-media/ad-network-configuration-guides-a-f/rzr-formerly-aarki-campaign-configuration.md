---
title: "RZR (formerly Aarki) campaign configuration"
excerpt: "Configure mobile attribution, retargeting, and cost API integrations with RZR (formerly Aarki) in AppsFlyer."
---
RZR, an AppsFlyer ad network integrated partner, is a well-known mobile DSP. RZR offers both click-based and view-through mobile attribution. In addition, RZR also offers click-based retargeting which you can record with AppsFlyer.

![RZR Logo Horizontal gradient black wordmark (3).png](https://files.readme.io/b1064bdec0e836399c583c3f55e5e79a81380a9a8d86eeaee19391b6d09f2bbd-small-46161100230545.png)

## Setting up RZR

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

### Integration tab

### Activate partner

On the **first visit**, you will need to toggle ON the _**Activate Partner**_ button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner. For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360006091197).

> 📘 Note
>
> As an ALL-Installs network, RZR prefers to receive postbacks for all new installs of your app from ANY source, including organic. It is recommended to select **Events attributed to any partner** to send all install postbacks to RZR.

### General settings

**Partner ID**

RZR connects with AppsFlyer via a unique network ID. If you don't already have the Network ID, you must obtain it from RZR to continue with the integration.

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from RZR. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to RZR following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to RZR. Select **Events attributed to any partner or organic** to have your entire user base available to be reported to RZR.

### In-app events settings

In this section you can map your AppsFlyer events with RZR via postbacks.

**To configure in-app event postbacks:**

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br>**Tip**: Don't see the event you are looking for?<br>   - Make sure to activate the event on a device with a non-organic installation, and recheck.<br>   - Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](https://support.appsflyer.com/hc/articles/208439256#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<br>   - **Text field:** Get the corresponding event ID from the partner.<br>   - **Drop-down box:** Select the most suitable pre-defined AppsFlyer event.<br>   - **As is**: Send the events as they are, without name mapping. |
| **for users from** | Select the sending option for the event:<br>   - **This partner only**: Send postbacks only when this event is attributed to this partner.<br>   - **All media sources including organic**: Send postbacks for events attributed to any partner, as well as organic events. |
| **including** | - **No data (default)**: Send only the event itself without any event values.<br>   - **Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).<br>   - **Values without revenue**: Send all the parameters **excluding** the revenue value. |

3. [Optional] Click the **Add condition** ![conditional-iae-postbacks-icon.png](https://files.readme.io/b7d9d43fd559bb7fe6b77531ea87229dbcbfdd20f2683815f9f1eaccc1720e01-27310995360273.png) icon to [set conditions](https://support.appsflyer.com/hc/articles/208439256#conditional-inapp-event-postbacks) for an event.
4. Click **Save integration**.
5. [Optional]After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
1. From the top-left corner, under the partner name, click the app name to open the list of apps.
2. Select a different app from the drop-down list.
3. Repeat the [integration steps](https://support.appsflyer.com/hc/articles/11904659502737#integration-tab) for the selected app.

### Attribution link tab

In this tab, you can create the attribution links you want to send to RZR for attributing RZR's campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** \- add it to compare different campaigns running with Aarki. **Attribution link parameter:** c
- **Adset** \- set ad set names to compare different ad sets within specific Aarki campaigns. **Attribution link parameter:** af\_adset
- **Ad Name** \- set ad set names to compare different creatives within specific ad sets within specific campaigns Aarki. **Attribution link parameter:** af\_ad
- **Site ID** and **Sub Site ID** \- set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](https://support.appsflyer.com/hc/articles/115005099063-What-are-the-Exceeded-Media-Sources-#exceeded_siteid_limit) limitations. **Attribution link parameters:** af\_siteid and af\_sub\_siteid
- **Subscriber Parameters** \- use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering. **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information [**about AppsFlyer's Attribution Link Structure and Parameters**](https://support.appsflyer.com/hc/articles/207447163) **.**

### Retargeting settings

When enabled, AppsFlyer recognizes a link as a [retargeting](https://support.appsflyer.com/hc/articles/207033786-AppsFlyer-s-Retargeting-Attribution) attribution link, rather than a user acquisition link, by adding the &is\_retargeting=true to the click recording link. Note that retargeting is currently only supported for click-through and not view-through attribution. **Attribution link parameter:** is\_retargeting.

The following setup below is displayed when retargeting is enabled.

1\. Standard Link vs. OneLink

Select _**standard attribution link**_ option if:

- You don't need to deep link with the URL or
- Plan to use only [URI schemes](https://support.appsflyer.com/hc/articles/208874366#social-app-landing-page) for deep linking

Select _**Use OneLink**_ for:

- Using a single link for both Android and iOS apps or
- Deep linking using Universal or app links

Note that selecting OneLink changes the click recording link from app specific to a [OneLink URL](https://support.appsflyer.com/hc/articles/115005248543-OneLink-Overview).

2\. Deep Link URL

Use this field if the link is meant to deep link users to any specific activity within your app. **Attribution link parameter:** af\_dp You can find more information about AppsFlyer's [deep linking solution in this guide.](https://support.appsflyer.com/hc/articles/208874366-Deep-Linking-Step-by-Step)

3\. Re-engagement Window

Set the time period following the re-engagement, where the user's in-app events are attributed to the retargeting media source. You can set the value in days (1-90), hours (up to 23), or even lifetime.

**Attribution link parameter:** af\_reengagement\_window

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to RZR.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to RZR to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that occur within this lookback window following an ad impression are attributed to RZR, provided there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the [view-through attribution here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to RZR to be activated when a corresponding ad is watched, usually for 1 second or more.

### Cost tab

AppsFlyer gets cost details by API. See the [ad network cost integration table](https://support.appsflyer.com/hc/articles/207040526-Ad-cost-measurement-guide#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

- Follow [these integration instructions](https://support.appsflyer.com/hc/articles/360008850257#enable-cost-api).

[View your cost API status](https://support.appsflyer.com/hc/articles/360008850257#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

> 🚧 Warning
>
> Once you set RZR cost do not change the name of any running campaign, ad set or single ad as it may cause serious discrepancies or missing cost data.

### Ad revenue tab

Ad Revenue data is not supported by RZR.

### Permissions tab

In this tab, you can select the permissions to grant RZR, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for RZR, the permissions tab is active and you can grant control to RZR.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

- _**Allow to configure integration**_ \- permit the partner to setup the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ \- permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ \- only to the partner's own retention data
- _**Allow access to your aggregate loyal user data**_ \- only to the partner's own loyal user data
- _**Allow access to your aggregate in-app events data**_ \- only to the partner's own in-app events data
- _**Allow access to your aggregate revenue data**_ \- only to the revenue data attributed to the partner
- _**Allow access to your Protect360 dashboard**_ \- only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

- _**Main toggle**_ \- Set to On to reveal the agency permissions options
- _**Allow to configure in-app event postbacks**_ \- permit the agency to setup in-app event postbacks mapping to itself on the integration tab
- _**Allow access to aggregate organic data**_
- _**Allow access to your retention report**_ \- only to the agency's own retention data

Learn more about granting [agency permissions](https://support.appsflyer.com/hc/articles/4410395957521#agency-permissions).