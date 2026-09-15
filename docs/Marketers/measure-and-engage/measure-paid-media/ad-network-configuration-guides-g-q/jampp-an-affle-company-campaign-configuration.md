---
title: "Jampp, an Affle company campaign configuration"
excerpt: "Configure Jampp, an Affle company, in AppsFlyer to enable mobile attribution, cost tracking, retargeting, and view-through attribution."
---
Jampp, an Affle company and AppsFlyer integrated partner, provides a performance marketing platform for acquiring and retargeting app customers. In addition to click-based mobile attribution, Jampp also offers cost, retargeting and view-through attribution, which you can record with AppsFlyer.

## Setting up Jampp integration

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

## Integration tab

### Activate partner

On the **first visit** here, you will need to toggle below. ON the _**Activate Partner**_ button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

> 📘 Note
>
> As an ALL-Installs network, Jampp prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to Jampp.

### General settings

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from Jampp. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to Jampp following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Jampp.

Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Jampp.

### In-app events settings

In this section you can map your AppsFlyer events with Jampp via postbacks.

1. Toggle In-App Event Postbacks to ON
2. Select the Sending Option for all SDK-defined events.

**- Only events attributed to this partner** for events coming **only** from users attributed to this partner

**- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated with your app, or from server to server events.<br>**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Jampp's side.<br>Obtain the corresponding Event ID from Jampp and set it in the text field. |
| **Send Revenue** | **When unchecked** - Send all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af_revenue** parameter.<br>**When checked** - Send all the parameters including the revenue value (if it exists in the event). |

## Attribution link tab

In this tab, you can create the attribution links you want to send to Jampp for attributing Jampp's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with Jampp.

**Attribution link parameter:** c
- **Adset** - set ad set names to compare different ad sets within specific Jampp campaigns.

**Attribution link parameter:** af_adset
- **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Jampp.

**Attribution link parameter:** af_ad
- **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the subsite ID parameter, to avoid [exceeding the site ID](https://support.appsflyer.com/hc/articles/115005099063-What-are-the-Exceeded-Media-Sources-#exceeded_siteid_limit) limitations.

**Attribution link parameters:** af_siteid and af_sub_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

**Attribution link parameters:** af_sub1, af_sub2, af_sub3, af_sub4, af_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about [**AppsFlyer Attribution Link Structure and Parameters**](https://support.appsflyer.com/hc/articles/207447163) .

### Retargeting settings

When enabled, AppsFlyer recognizes a link as a [retargeting](https://support.appsflyer.com/hc/articles/207033786-AppsFlyer-s-Retargeting-Attribution) attribution link, rather than a user acquisition link, by adding the `&is_retargeting=true` to the click recording link. Note that retargeting is currently only supported for click-through and not view-through attribution.

**Attribution link parameter:** is_retargeting.

The following setup below is displayed when retargeting is enabled.

1. Standard Link vs. OneLink

Select _**standard attribution link**_ option if:

- You don't need to deep link with the URL or
- Plan to use only [URI schemes](https://support.appsflyer.com/hc/articles/208874366#general-settings) for deep linking

select _**Use OneLink**_ for:

- Using a single link for both Android and iOS apps or
- Deep linking using Universal or app links

Note that selecting OneLink changes the click recording link from app specific to a [OneLink URL](https://support.appsflyer.com/hc/articles/115005248543-OneLink-Overview).

2. Deep Link URL

Use this field if the link is meant to deep link users to any specific activity within your app.

**Attribution link parameter:** af_dp

You can find more information about AppsFlyer's [deep linking solution in this guide.](https://support.appsflyer.com/hc/articles/208874366-Deep-Linking-Step-by-Step)

3. Re-engagement Window

Set the time period following the re-engagement, where the user's in-app events are attributed to the retargeting media source. You can set the value in days (1-90), hours (up to 23), or even lifetime.

**Attribution link parameter:** af_reengagement_window

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Jampp.

**Attribution link parameter:** af_click_lookback

More details about the [click lookback window here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Jampp to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to Jampp, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af_viewthrough_lookback

More details about the [view-through attribution here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to Jampp to be activated when a corresponding ad is watched, usually for 1 second or more.

## Cost tab

AppsFlyer gets cost details by API. See the [ad network cost integration table](https://support.appsflyer.com/hc/articles/207040526-Ad-cost-measurement-guide#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

- Follow [these integration instructions](https://support.appsflyer.com/hc/articles/360008850257#enable-cost-api).

[View your cost API status](https://support.appsflyer.com/hc/articles/360008850257#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

## Ad revenue tab

Ad Revenue integration is not available for this partner.

## Permissions tab

In this tab, you can select the permissions to grant Jampp, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Jampp, the permissions tab is active and you can grant control to Jampp.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

- _**Allow to configure integration**_ - permit the partner to set up the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your aggregate loyal user data**_ - only to the partner's own loyal user data
- _**Allow access to your aggregate in-app events data**_ - only to the partner's own in-app events data
- _**Allow access to your aggregate revenue data**_ - only to the revenue data attributed to the partner
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

- _**Main toggle**_ - Set to On to reveal the agency permissions options
- _**Allow access to your retention report**_ - only to the agency's own retention data
- _**Allow access to aggregate organic data**_
- _**Allow to configure in-app event postbacks**_ - permit the agency to setup in-app event postbacks mapping to itself on the integration tab

Learn more about granting [agency permissions](https://support.appsflyer.com/hc/articles/4410395957521#agency-permissions).