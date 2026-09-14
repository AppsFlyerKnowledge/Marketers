---
title: "Youdao DSP campaign configuration"
excerpt: "Learn how to set up and configure your mobile attribution campaigns with Youdao DSP in AppsFlyer."
---
**At a glance:** Youdao DSP is an AppsFlyer ad network integrated partner.

## Setting Up Youdao DSP

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

Youdao DSP's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](https://support.appsflyer.com/hc/articles/4410395957521#about-the-integrated-partner-page).

> 👍 Tip
>
> - The [General Settings](https://support.appsflyer.com/hc/articles/4410395957521#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> - All the rest of the steps are either descriptive or **optional**

## Integration Tab

The integration with Youdao DSP only supports the install event in the default postback.

### Activate Partner

On the **first visit** here, you will need to toggle below. ON the _**Activate Partner**_ button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

### Default Postbacks

<Image src="https://files.readme.io/25195e81f0cda6b626f31719eb11a1859d71d9ae5ebed5ecced2bf76d68364db-21594095727633.png" alt="mceclip2.png" />

## Attribution Link Tab

In this tab, you can create the attribution links you want to send to Youdao DSP for attributing Youdao DSP's campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution Link Parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with Youdao DSP.

  **Attribution link parameter:** c
- **Adset** - set ad set names to compare different ad sets within specific Youdao DSP campaigns.

  **Attribution link parameter:** af\_adset
- **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Youdao DSP.

  **Attribution link parameter:** af\_ad
- **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](https://support.appsflyer.com/hc/articles/115005099063-What-are-the-Exceeded-Media-Sources-#exceeded_siteid_limit) limitations.

  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image src="https://files.readme.io/42feb31c65728c4a032f3642efa13d9b1777a2474c3cda253ef2bcea981269ab-21594079368081.png" alt="attribution-link-parameters.png" />

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about **[AppsFlyer's Attribution Link Structure and Parameters](https://support.appsflyer.com/hc/articles/207447163).**

### Click-Through Attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Youdao DSP.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-).

<Image src="https://files.readme.io/acf6c03da27561a76a0e16295248641120bbe790bab8b9866cc869f8534b99f4-21594079376529.png" alt="netease-click-through.png" />

### Attribution Link

This is the attribution link that contains all the setup information you have set for it. Send it to Youdao DSP to be activated when leads click on a corresponding ad.

## Cost Tab

Cost data is not supported in the integration with this partner.

## Ad Revenue Tab

Ad Revenue is not supported in the integration with this partner.

## Permissions Tab

In this tab, you can select the permissions to grant Youdao DSP, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for Youdao DSP, the permissions tab is active and you can grant control to Youdao DSP.

<Image src="https://files.readme.io/f6bf67f1a99cd8dfcd3ae3e6f0c70b6aba72df8ce64d7b5c8733d85dbc0cfcce-21594079386257.png" alt="rtb_house-permissions-new.png" />

### Ad Network Permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

- _**Allow to configure integration**_ - permit the partner to setup the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).