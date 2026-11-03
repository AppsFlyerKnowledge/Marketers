---
title: Localytics integration with AppsFlyer
metadata:
  keywords:
    - Localytics
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-07-27T11:09:25Z'
  edited_at: '2026-10-13T00:30:07Z'
  id: 210748626
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/210748626
---
> **At a glance:** Localytics, an AppsFlyer integrated partner, is a marketing and analytics platform for mobile and web apps. Localytics app analytics provide cohort-based retention analysis, funnels, customer segmentation, and real-time analyses to uncover groups of users with the highest loyalty rates and lifetime value. Localytics app marketing brings marketing automation services to apps by measuring the long-term success of customer acquisition campaigns and delivering rich and actionable in-app and push messages to relevant customers when they can have the greatest impact.

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Localytics

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

The Localytics configuration window includes 4 tabs: **Integration, Attribution link, Data enrichment,** and **Permissions**. Click on the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">here</Anchor>.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">here</Anchor>.

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

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Select **Events attributed to any partner or organic** to send postbacks for any user that downloads the app to Localytics.

Once you have completed the configuration, AppsFlyer sends the following data to Localytics for every organic and non-organic install:

* Device ID (IDFA / Google Advertising ID)
* Media Source
* Campaign name

Click **Save.**

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for Localytics.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Permissions are not available for Localytics.

</Accordion>

## Viewing the attribution data in the Localytics console

Go to the Localytics Attribution Settings screen and enable Third Party Attribution in Localytics to see AppsFlyer data.

[![](https://files.readme.io/0c171096b9bfd8a559ba8e1a0ad4296559dc050c7b3b52b8987bd9707e44220a-205662666.png)](https://files.readme.io/0c171096b9bfd8a559ba8e1a0ad4296559dc050c7b3b52b8987bd9707e44220a-205662666.png)

[![](https://files.readme.io/53524088099556d72e6e7573f3997bbb55b1a89e38a2f7a74eec1a1632125c72-205663286.png)](https://files.readme.io/53524088099556d72e6e7573f3997bbb55b1a89e38a2f7a74eec1a1632125c72-205663286.png)

<div data-zendesk-anchors="h_01H9FKCBM5W16BYJQ6TH9SSBVC=important h_01H9FKCBM5Z39GPE5772799DB1=setting-up-localytics h_01H9FKCBM5JZ5V4YMB6S24JA6V=integration-tab h_01H9FKCBM5PSZZ5FP1G12M9F63=activate-partner h_01H9FKCBM5N4RB5ZSB61W02368=general-settings h_01H9FKCBM5STZ79NBP3EFYGMB9=default-postbacks h_01H9FKCBM54S067F1Z51E4FXQD=attribution-link-tab h_01H9FKCBM591RG57Q80JZ7FJWY=cost-tab h_01H9FKCBM5Q8P53V34QRQMS0BS=ad-revenue-tab h_01H9FKCBM5GGXX04JEH3DHNV78=permissions-tab h_01H9FKCBM5VBM87C2PHNZVZ4RJ=viewing-the-attribution-data-in-the-localytics-console" />
