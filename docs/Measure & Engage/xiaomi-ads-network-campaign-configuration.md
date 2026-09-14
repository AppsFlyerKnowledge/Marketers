---
title: "Xiaomi Ads Network campaign configuration"
excerpt: "Learn how to configure and activate the Xiaomi Ads Network integration in AppsFlyer, including setting up attribution links and granting partner permissions."
---
At a glance: Xiaomi, an AppsFlyer ad network integrated partner, operates the Xiaomi Android App Store which ranks in the Top 5 Android App Distribution Platforms in China, with 5 billion app downloads per month. In addition to click-based mobile attribution, Xiaomi also offers view-through attribution, which you can record with AppsFlyer.

## Setting up Xiaomi

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

Xiaomi's configuration window includes 3 active tabs: Integration, Attribution link and Permissions. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](https://support.appsflyer.com/hc/articles/4410395957521#about-the-integrated-partner-page).

> 👍 Tip
>
> - The [General Settings](https://support.appsflyer.com/hc/articles/4410395957521#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> - All the rest of the steps are either descriptive or **optional**

## Integration tab

### Activate partner

On the **first visit**, you will need to toggle ON the _**Activate Partner**_ button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360000844778).

General Settings

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from Xiaomi. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

AppsFlyer can send automatic postbacks to Xiaomi following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

![xiaomi-default-postbacks.png](https://files.readme.io/cbd98386c07edc96a13b9e98190bf20b084700d12e8af09209ab8f951744a506-360002077549.png)

## Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](https://support.appsflyer.com/hc/articles/115005248543-OneLink-overview).

[Learn more about attribution link structure and parameters](https://support.appsflyer.com/hc/articles/207447163).

**To generate an attribution link,** follow [these instructions](https://support.appsflyer.com/hc/articles/4410395957521#attribution-link-tab).

## Cost tab

Cost data integration is currently not supported with Xiaomi.

## Ad revenue tab

Ad revenue integration is currently not supported with Xiaomi.

## Permissions tab

In this tab, you can select the permissions to grant Xiaomi, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for Xiaomi, the permissions tab is active and you can grant control to Xiaomi.

![ad_network_permissions.png](https://files.readme.io/9c78dd4c5fdf476816c20026e21de49da12688e2f8a05b8f5a00a341c303e48a-360002229218.png)

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

- _**Allow to configure integration**_ - permit the partner to setup the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your aggregate loyal user data**_ - only to the partner's own loyal user data
- _**Allow access to your aggregate in-app events data**_ - only to the partner's own in-app events data
- _**Allow access to your aggregate revenue data**_ - only to the revenue data attributed to the partner
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).