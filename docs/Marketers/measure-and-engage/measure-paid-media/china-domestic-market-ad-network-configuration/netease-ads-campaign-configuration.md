---
title: "Netease Ads campaign configuration"
excerpt: "Learn how to configure Netease Ads integration in AppsFlyer, including setting up attribution links, default postbacks, and partner permissions."
---
Netease, an AppsFlyer integrated partner, is a leading advertisement service provider in the Chinese market. This guide covers how to set up the integration, configure attribution links, and manage permissions.

## Setting up Netease

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

Netease's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](https://support.appsflyer.com/hc/articles/4410395957521#about-the-integrated-partner-page).

> 👍 Tip
>
> - The [General Settings](https://support.appsflyer.com/hc/articles/4410395957521#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> - All the rest of the steps are either descriptive or **optional**

## Integration tab

The integration with Netease Ads only supports the install event in the default postback.

### Activate partner

On the **first visit** here, you will need to toggle ON the _**Activate Partner**_ button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

### Default postbacks

<Image src="https://files.readme.io/f86454ac6eea8357be8734c73700cfdf0116c0c509621ffc6c57273db5ebdd8c-360002075369.png" alt="netease-default-postback.png" />

## Attribution link tab

In this tab, you can create the attribution links you want to send to Netease for attributing Netease's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with Netease.
  **Attribution link parameter:** c
- **Adset** - set ad set names to compare different ad sets within specific Netease campaigns.
  **Attribution link parameter:** af\_adset
- **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Netease.
  **Attribution link parameter:** af\_ad
- **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](https://support.appsflyer.com/hc/articles/115005099063-What-are-the-Exceeded-Media-Sources-#exceeded_siteid_limit) limitations.
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image src="https://files.readme.io/9d0720adb3d84647aa3570c60ddc84b246c84014af44d383a27f9b2e8a34edcf-360002880177.png" alt="attribution-link-parameters.png" />

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about **[AppsFlyer Attribution Link Structure and Parameters](https://support.appsflyer.com/hc/articles/207447163).**

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Netease.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

<Image src="https://files.readme.io/d01b4b4535b4632f49dd8de60b5e3518f0b207d9927bebbc4a38a8922e4a665b-360002069365.png" alt="netease-click-through.png" />

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Netease to be activated when leads click on a corresponding ad.

## Cost tab

Cost data is not supported in the integration with this partner.

## Ad revenue tab

Ad Revenue is not supported in the integration with this partner.

## Permissions tab

In this tab, you can select the permissions to grant RTB House, whether the partner acts as an ad network, agency, or both. Note that even if attribution is disabled for RTB House, the permissions tab is active and you can grant control to RTB House.

<Image src="https://files.readme.io/d5f811f08313270f74a10fe64c61137d92b00fa0018dfe6b966361dfd6bb1db0-21594010868369.png" alt="rtb_house-permissions-new.png" />

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