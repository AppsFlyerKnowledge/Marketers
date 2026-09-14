---
title: "Baidu App Ads campaign configuration"
excerpt: "Learn how to configure and set up Baidu App Ads (Baitong) campaigns in AppsFlyer, including integration, attribution links, and permissions."
---
Baidu App Ads (Baitong), an AppsFlyer ad network integrated partner, is one of the biggest App promotion and distribution platforms in the China domestic market, integrating the mobile traffic of App Stores (Baidu Mobile Assistant, Android Market, 91 Mobile Assistant, etc.), Baidu Mobile Search, Super App, and Baidu Affiliates.

## Setting Up Baidu App Ads (Baitong)

The setup is done from the **Active Integrations** page, but to find new partners you must first go to the [marketplace](https://support.appsflyer.com/hc/articles/9960361873809).

> 📘 Note
>
> Before setting up an integration, make sure you [contact the partner](https://support.appsflyer.com/hc/articles/9960361873809#contact-details) and open an account with them.

**To activate the integration:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Marketplace**.
2. Search for the partner and select it.
3. Click **Set up integration**. You’re directed to the integration setup page.
4. In the **Integration** tab, turn on **Activate partner**.

> 📘 Note
>
> The toggle must stay on ([activated](https://support.appsflyer.com/hc/articles/360000844778)) for as long as you work with the partner.

5. Complete the configuration using the relevant tabs, as described below.

Baidu App Ads configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](https://support.appsflyer.com/hc/articles/4410395957521#about-the-integrated-partner-page).

> 👍 Tip
>
> - The [General Settings](https://support.appsflyer.com/hc/articles/4410395957521#d-general%20settings) step in the Integration tab is **mandatory** for all partners.
> - All the rest of the steps are either descriptive or **optional**.

## Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you must toggle ON the _**Activate Partner**_ button to enable the setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

### Default postbacks

AppsFlyer can send automatic postbacks to Baidu App Ads (Baitong) following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

The Integration with Baidu Baitong Ads supports only the install event for Default Postbacks.

<Image src="https://files.readme.io/43a8b8df4f78381e457f550fef864dd85c52f16e3cfb4a04b07d4b1c4ed8f964-360002075209.png" alt="baidu-baitong-default-postback.png" />

## Attribution link tab

In this tab, you can create the attribution links you want to send to Baidu App Ads (Baitong) for attributing Baidu App Ads (Baitong) campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with Baidu App Ads（Baitong).
  **Attribution link parameter:** c
- **Adset** - set ad set names to compare different ad sets within specific Baidu App Ads（Baitong) campaigns.
  **Attribution link parameter:** af\_adset
- **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Baidu App Ads（Baitong).
  **Attribution link parameter:** af\_ad
- **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](https://support.appsflyer.com/hc/articles/115005099063-What-are-the-Exceeded-Media-Sources-#exceeded_siteid_limit) limitations.
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information, see **[AppsFlyer Attribution Link Structure and Parameters](https://support.appsflyer.com/hc/articles/207447163).**

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window can be attributed to Baidu App Ads（Baitong).

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Baidu App Ads（Baitong) to be activated when leads click on a corresponding ad.

## Cost tab

Cost data is not supported in the integration with this partner.

## Ad revenue tab

Ad Revenue is not supported in the integration with this partner.

## Permissions tab

In this tab, you can select the permissions to grant RTB House, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for RTB House, the permissions tab is active and you can grant control to RTB House.

### Ad network permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

- _**Allow to configure integration**_ - permit the partner to set up the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your aggregate loyal user data**_ - only to the partner's own loyal user data
- _**Allow access to your aggregate in-app events data**_ - only to the partner's own in-app events data
- _**Allow access to your aggregate revenue data**_ - only to the revenue data attributed to the partner
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).