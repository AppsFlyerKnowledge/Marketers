---
title: "Localytics integration with AppsFlyer"
excerpt: "Localytics, an AppsFlyer integrated partner, is a marketing and analytics platform for mobile and web apps. Localytics app analytics provide cohort-based retention analysis, funnels, customer segmentation, and real-time analyses to uncover groups of users with the highest loyalty rates and lifetime value. Localytics app marketing brings marketing automation services to apps by measuring the long-term success of customer acquisition campaigns and delivering rich and actionable in-app and push messages to relevant customers when they can have the greatest impact."
x-zendesk:
  id: 210748626
  url: https://support.appsflyer.com/hc/en-us/articles/210748626-Localytics-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: 3rd-party platforms
  section_id: 6551199962257
  position: 17
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Ad Networks]
  labels: [Localytics, Advertisers, Ad Networks, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2016-07-27T11:09:25Z'
  edited_at: '2026-06-16T09:50:11Z'
---
> 📘 **Important!**
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

[![](https://files.readme.io/5064c48a0851c34c51b4cfd28e2808a11e6d8d271f1cd735616f6de0d827cea8-360001902809.png)](https://files.readme.io/5064c48a0851c34c51b4cfd28e2808a11e6d8d271f1cd735616f6de0d827cea8-360001902809.png)

### General settings

**Attribution ID**

Localytics connects with AppsFlyer via a unique Attribution ID. If you don't already have it, you must obtain it from Localytics to continue with the integration or follow the steps below.

![Localytics_msc_new_3.png](https://files.readme.io/2a51018b2248a855ed5a86207c18d132addf5ab56449f4c9915df2eb754e39ca-360001902869.png)

Obtaining the Localytics App Key from Localytics

* Login to your Localytics Dashboard
* Click **Attribution** in the left panel
* Select **Third Party Attribution**
* Copy the Attribution key

[![](https://files.readme.io/dbac1c9beb6d22f4cf8f2ccfbdc0f6a22fec7e6ccad5a52e77c7c32044cab55c-207223506.png)](https://files.readme.io/dbac1c9beb6d22f4cf8f2ccfbdc0f6a22fec7e6ccad5a52e77c7c32044cab55c-207223506.png)

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

[![](https://files.readme.io/0c171096b9bfd8a559ba8e1a0ad4296559dc050c7b3b52b8987bd9707e44220a-205662666.png)](https://files.readme.io/0c171096b9bfd8a559ba8e1a0ad4296559dc050c7b3b52b8987bd9707e44220a-205662666.png)

[![](https://files.readme.io/53524088099556d72e6e7573f3997bbb55b1a89e38a2f7a74eec1a1632125c72-205663286.png)](https://files.readme.io/53524088099556d72e6e7573f3997bbb55b1a89e38a2f7a74eec1a1632125c72-205663286.png)