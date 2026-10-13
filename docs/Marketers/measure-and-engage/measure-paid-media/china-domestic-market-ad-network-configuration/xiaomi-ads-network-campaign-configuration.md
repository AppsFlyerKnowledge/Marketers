---
title: "Xiaomi Ads Network campaign configuration"
excerpt: "Learn how to configure and activate the Xiaomi Ads Network integration in AppsFlyer, including setting up attribution links and granting partner permissions."
---
**At a glance:** Xiaomi, an AppsFlyer ad network integrated partner, operates the Xiaomi Android App Store which ranks in the Top 5 Android App Distribution Platforms in China, with 5 billion app downloads per month. In addition to click-based mobile attribution, Xiaomi also offers view-through attribution, which you can record with AppsFlyer.

## Setting up Xiaomi

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

Xiaomi's configuration window includes 3 active tabs: Integration, Attribution link and Permissions. Click on the items below to read about the tabs setup.

## Integration tab

### Activate partner

On the **first visit**, you will need to toggle ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

General Settings

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from Xiaomi. The view-through lookback slider is available on the attribution link tab (described below).

![](https://files.readme.io/c01732abe8d1bb3c68acdf84bab50cc46d4f4923b7220e3ca51c399074113c1e-50899866307217.png)

### Default postbacks

AppsFlyer can send automatic postbacks to Xiaomi following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

![xiaomi-default-postbacks.png](https://files.readme.io/ae215140550604649e4345729a7106fa08c15713e003cec534199e3889122b5e-50899866309265.png)

## Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).  
[Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters).

**To generate an attribution link,**follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

## Cost tab

Cost data integration is currently not supported with Xiaomi.

## Ad revenue tab

Ad revenue integration is currently not supported with Xiaomi.

## Permissions tab

In this tab, you can select the permissions to grant Xiaomi, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for Xiaomi, the permissions tab is active and you can grant control to Xiaomi.

![ad_network_permissions.png](https://files.readme.io/2532b798bacccf9028a157e44a9785a285cd81dd521c0c5ec5303ae420827620-50899913924113.png)

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to setup the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -*only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*****a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).