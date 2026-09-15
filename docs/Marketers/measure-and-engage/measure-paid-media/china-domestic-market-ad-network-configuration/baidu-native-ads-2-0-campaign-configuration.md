---
title: "Baidu Native Ads 2.0 campaign configuration"
excerpt: "Learn how to set up and configure the Baidu Native Ads 2.0 integration in AppsFlyer, including integration settings, attribution links, and in-app event mapping."
---
Baidu Native Ads 2.0 is an AppsFlyer ad network integrated partner.

## Setting Up Baidu Native Ads 2.0

The setup is done from the **Active Integrations** page, but to find new partners you must first go to the [marketplace](/docs/partner-integrations).

> 📘 Note
>
> Before setting up an integration, make sure you [contact the partner](/docs/partner-integrations#contact-details) and open an account with them.

**To activate the integration:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Marketplace**.
2. Search for the partner and select it.
3. Click **Set up integration**.
4. Select the app for the integration. You’re directed to the integration setup page.
5. In the **Integration** tab, turn **Activate partner** on.

Baidu Native Ads 2.0's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

> 👍 Tip
>
> - The [General Settings](/docs/set-up-an-integrated-partner#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> - All the rest of the steps are either descriptive or **optional**

## Integration Tab

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the _**Activate Partner**_ button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](/docs/partner-activation-deactivation).

### General settings

Baidu Native Ads 2.0 connects with AppsFlyer via a unique **akey**. If you don't already have the key, you must obtain it from Baidu Native Ads 2.0 to continue with the integration.

![mceclip2.png](https://files.readme.io/41b5fffa62de604dc3d6c28e109d61e15deefe156926ae08c52cd0bdedb56cbf-360003450038.png)

### Default Postbacks

![mceclip2.png](https://files.readme.io/312310fdaf763d570a0063ed4acad677463df0da28a397401e1160fbed49ce03-21594047315857.png)

### In-app events settings

In this section you can map your AppsFlyer events with Baidu Native Ads 2.0 via postbacks.

![mceclip1.png](https://files.readme.io/a19f91e96b1d361c3789dbacd889631dd0987f7bf1defcc32306aae7bf9b9625-360015744517.png)

1. Toggle In-App Event Postbacks to ON
2. Click **Add Event** to add an SDK Event to the list
3. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.<br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Baidu Native Ads 2.0's side.<br />Obtain the corresponding Event ID from Baidu Native Ads 2.0 and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.<br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

## Attribution Link Tab

In this tab, you can create the attribution links you want to send to Baidu Native Ads 2.0 for attributing Baidu Native Ads 2.0's campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with Baidu Native Ads 2.0.

**Attribution link parameter:** c
- **Adset** - set ad set names to compare different ad sets within specific Baidu Native Ads 2.0 campaigns.

**Attribution link parameter:** af\_adset
- **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific Baidu Native Ads 2.0 campaigns.

**Attribution link parameter:** af\_ad
- **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.

**Attribution link parameters:** af\_siteid and af\_sub\_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

**Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/55bd1ca3837b77ae55f88793ed5d7d964f661f95db760d17367f12e99630159b-21594030893073.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. Learn more about **[AppsFlyer's Attribution Link Structure and Parameters](/docs/about-link-structure-and-parameters).**

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Baidu Native Ads 2.0.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

![netease-click-through.png](https://files.readme.io/bd354d94c2800c2ef19d5ba611e4b422f7b627395463488f1a0edeafd9e2411b-21594047341329.png)

### Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to Baidu Native Ads 2.0 to be activated when leads click on a corresponding ad.

## Cost Tab

Cost data is not supported in the integration with this partner.

## Ad Revenue Tab

Ad Revenue is not supported in the integration with this partner.

## Permissions Tab

Permissions are not supported in the integration with this partner.