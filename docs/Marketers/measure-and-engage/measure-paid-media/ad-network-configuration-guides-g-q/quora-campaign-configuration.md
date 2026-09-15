---
title: "Quora campaign configuration"
excerpt: "Learn how to set up and configure your mobile attribution campaigns with Quora in AppsFlyer."
---
**At a glance:** Quora, AppsFlyer integrated partners, is one of the most popular online Q&A communities. Over 300 million unique visitors come to Quora every month to ask questions and read insightful answers. Quora's large, engaged audience is one of the key reasons why marketers have found success advertising on Quora.

![](https://cdn.appsflyer.com/marketplace/static/logo/quora.png?v=1%0A)

## Setting up Quora

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

Quora's configuration window includes 3 active tabs: **Integration, Attribution link**, and **Permissions**. Click the items below to read about the tab setup.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

> 📘 **Note**
>
> #### Tip
>
> * The [General Settings](/docs/set-up-an-integrated-partner#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**


## Integration tab

### Activate partner

On the **first visit**, you will need to toggle ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

Default Postbacks

Send automatic postbacks to Quora following user installs.

> 📘 **Note**
>
> #### Note
>
> The option **Only events attributed to this partner** is the only option with Quora and is selected by default.


## Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).  
[Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters).

**To generate an attribution link,**follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

## Cost tab

Cost integration is not available for this partner.

## Ad revenue tab

Ad Revenue integration is not available for this partner.

## Permissions tab

In this tab, you can select the permissions to grant Quora, whether the partner acts as an ad network, agency, or both. Note that even if attribution is disabled for Quora, the permissions tab is active and you can grant control to Quora.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -*only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*****a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).