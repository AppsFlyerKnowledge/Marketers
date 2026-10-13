---
title: "Liquid integration with AppsFlyer"
excerpt: "Learn how to set up the Liquid integration with AppsFlyer to automate your campaigns and processes using their intelligent rules engine."
---
**At a glance:** Liquid, an AppsFlyer integrated partner, automates your campaigns and processes with no need to call your IT. Their intelligent rules engine acts based on user behavior and advanced analytics.

> 📘 **Important!**
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.


## Setting up Liquid

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

## Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

### General settings

**API Token**

Liquid connects with AppsFlyer via a unique API Token. If you don't already have it, you must obtain it from Liquid to continue with the integration or follow the instructions below.

[![](https://files.readme.io/1479b1569af7d8fb95c9efd7beddf169369d92790721ad9f15f3fd1615973e0d-360002201405.png)](https://files.readme.io/1479b1569af7d8fb95c9efd7beddf169369d92790721ad9f15f3fd1615973e0d-360002201405.png)

### Obtaining the API token

You can find the API token by logging in to the Liquid dashboard.

* Click the **Settings** icon
* Copy the Production API token
* Insert the APP\_TOKEN you received from Liquid

### Default postbacks

AppsFlyer can send automatic postbacks to Liquid user installs. Use this section to define sending these postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/7a06540c1bbca9fc59e45ffdf47c6b40cb548c371654dff9216a7d1c4f87e4c3-18274574358289.png)

Select **Events attributed to any partner or organic** to send postbacks for any user that downloads the app to Liquid or select **Off**.

Click **Save.**

Once this configuration is saved, AppsFlyer begins sending the following data to Liquid for every organic and non-organic install:

* App Token
* customer\_user\_id as set in the SDK
* Media Source
* Campaign name

## Attribution link tab

Attribution Links are not available for Liquid.

## Cost tab

Cost data is not supported in the integration with this partner.

## Ad revenue tab

Ad Revenue is not supported in the integration with this partner.

## Permissions tab

Permissions are not available for Liquid.