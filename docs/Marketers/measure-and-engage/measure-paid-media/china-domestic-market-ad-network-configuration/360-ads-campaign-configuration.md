---
title: "360 Ads campaign configuration"
excerpt: "Learn how to configure the 360 Ads integrated partner settings in AppsFlyer, including integration, attribution links, and permissions."
---
**At a glance:** 360 Ads is an AppsFlyer ad network integrated partner.

## Setting Up 360 Ads

The setup is done from the **Active Integrations** page, but to find new partners you must first go to the [marketplace](https://support.appsflyer.com/hc/articles/9960361873809).

> 📘 Note
>
> Before setting up an integration, make sure you [contact the partner](https://support.appsflyer.com/hc/articles/9960361873809#contact-details) and open an account with them.

**To activate the integration:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Marketplace**.
2. Search for the partner and select it.
3. Click **Set up integration**.
4. Select the app for the integration. You’re directed to the integration setup page.
5. In the **Integration** tab, turn **Activate partner** on.

360 Ads configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](https://support.appsflyer.com/hc/articles/4410395957521#about-the-integrated-partner-page).

> 👍 Tip
>
> - The [General Settings](https://support.appsflyer.com/hc/articles/4410395957521#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> - All the rest of the steps are either descriptive or **optional**

## Integration Tab

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the _**Activate Partner**_ button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

### General settings

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from 360 Ads. The view-through lookback slider is available on the attribution link tab (described below).

### Default Postbacks

![mceclip2.png](https://files.readme.io/d779fc38f15be9d764e7ab7883ec27d1fb048c6f3cc9ccdd9b3ae8da285dd59b-21593980554257.png)

### In-app events settings

In this section you can map your AppsFlyer events with 360 Ads via postbacks.

**Key and Secret**

360 Ads connects with AppsFlyer via a unique Key and Secret. If you don't already have the Key and Secret, you must obtain it from 360 Ads to continue with the integration.

![mceclip2.png](https://files.readme.io/b1b665c7864d2a972ea975add2d3735ce42e5376c7d4cffb39429b9e9c52dcf0-360003450098.png)

1. Set the 360 Ads Key and Secret here
2. Toggle In-App Event Postbacks to ON
3. Click **Add Event** to add an SDK Event to the list
4. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.<br>**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on 360 Ads side.<br>Obtain the corresponding Event ID from 360 Ads and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.<br>**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

## Attribution Link Tab

In this tab, you can create the attribution links you want to send to 360 Ads for attributing 360 Ads campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with 360 Ads.

**Attribution link parameter:** c
- **Adset** - set ad set names to compare different ad sets within specific 360 Ads campaigns.

**Attribution link parameter:** af\_adset
- **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific 360 Ads campaigns.

**Attribution link parameter:** af\_ad
- **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](https://support.appsflyer.com/hc/articles/115005099063-What-are-the-Exceeded-Media-Sources-#exceeded_siteid_limit) limitations.

**Attribution link parameters:** af\_siteid and af\_sub\_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

**Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/03dc3e610125c0e4490108dcb218069edb6621e3092d29ff74915ab3a6ce27b0-21593958770833.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about **[AppsFlyer's Attribution Link Structure and Parameters](https://support.appsflyer.com/hc/articles/207447163).**

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to 360 Ads.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

![netease-click-through.png](https://files.readme.io/2bb30de564b5faffef594b1e0ac5ab4c82ffa1e270a17a99abe6e15ec333fb41-21593958786449.png)

### Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to 360 Ads to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to 360 Ads, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the [view-through attribution here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to 360 Ads to be activated when a corresponding ad is watched, usually for 1 second or more.

## Cost Tab

Cost data is not supported in the integration with this partner.

## Ad Revenue Tab

Ad Revenue is not supported in the integration with this partner.

## Permissions Tab

In this tab, you can select the permissions to grant 360 Ads, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for 360 Ads, the permissions tab is active and you can grant control to 360 Ads.

![rtb_house-permissions-new.png](https://files.readme.io/0241afe621784cb6614fd649e956e1d7e518e386769c1df6a53fb31be8dcc96d-21593958818065.png)

### Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

- _**Allow to configure integration**_ - permit the partner to setup the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).