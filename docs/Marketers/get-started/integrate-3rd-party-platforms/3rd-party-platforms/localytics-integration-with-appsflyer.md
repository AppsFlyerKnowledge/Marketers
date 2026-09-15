---
title: "Localytics integration with AppsFlyer"
excerpt: "Learn how to set up the Localytics integration with AppsFlyer to share attribution data, configure postbacks, and view analytics in the Localytics console."
---
**At a glance:** Localytics, an AppsFlyer integrated partner, is a marketing and analytics platform for mobile and web apps. Localytics app analytics provide cohort-based retention analysis, funnels, customer segmentation, and real-time analyses to uncover groups of users with the highest loyalty rates and lifetime value. Localytics app marketing brings marketing automation services to apps by measuring the long-term success of customer acquisition campaigns and delivering rich and actionable in-app and push messages to relevant customers when they can have the greatest impact.

> 📘 **Note**
>
> #### Important!
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.


## Setting up Localytics

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

The Localytics configuration window includes 4 tabs: **Integration, Attribution link, Data enrichment,** and **Permissions**. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

## Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

[![](https://support.appsflyer.com/hc/article_attachments/360001902809)](https://support.appsflyer.com/hc/article_attachments/360001902809)

### General settings

**Attribution ID**

Localytics connects with AppsFlyer via a unique Attribution ID. If you don't already have it, you must obtain it from Localytics to continue with the integration or follow the steps below.

![Localytics_msc_new_3.png](https://files.readme.io/2a51018b2248a855ed5a86207c18d132addf5ab56449f4c9915df2eb754e39ca-360001902869.png)

Obtaining the Localytics App Key from Localytics

* Login to your Localytics Dashboard
* Click **Attribution** in the left panel
* Select **Third Party Attribution**
* Copy the Attribution key

[![](https://support.appsflyer.com/hc/en-us/article_attachments/207223506/Localytics_new.png)](https://support.appsflyer.com/hc/en-us/article_attachments/207223506/Localytics_new.png)

Configure Localytics in AppsFlyer’s Dashboard.

### Default postbacks

AppsFlyer can send automatic postbacks to Localytics following user installs. Use this section to define sending these postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/f4856955f97fa71eaaa247b3d63eb308adf7352b4f907b389a0cb3add21281a8-18274585535761.png)

Select **Events attributed to any partner or organic** to send postbacks for any user that downloads the app to Localytics.

Once you have completed the configuration, AppsFlyer sends the following data to Localytics for every organic and non-organic install:

* Device ID (IDFA / Google Advertising ID)
* Media Source
* Campaign name

Click **Save.**

## Attribution link tab

Attribution Links are not available for Localytics.

## Cost tab

Cost data is not supported in the integration with this partner.

## Ad revenue tab

Ad Revenue is not supported in the integration with this partner.

## Permissions tab

Permissions are not available for Localytics.

## Viewing the attribution data in the Localytics console

Go to the Localytics Attribution Settings screen and enable Third Party Attribution in Localytics to see AppsFlyer data.

[![](https://support.appsflyer.com/hc/en-us/article_attachments/205662666/Localytics_4.png)](https://support.appsflyer.com/hc/en-us/article_attachments/205662666/Localytics_4.png)

[![](https://support.appsflyer.com/hc/en-us/article_attachments/205663286/Localytics_5.png)](https://support.appsflyer.com/hc/en-us/article_attachments/205663286/Localytics_5.png)