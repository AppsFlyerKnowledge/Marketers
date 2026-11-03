---
title: Liquid integration with AppsFlyer
metadata:
  keywords:
    - Liquid
    - attribution data
    - integrated partner
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
  created_at: '2015-12-24T11:36:06Z'
  edited_at: '2026-06-16T09:40:28Z'
  id: 207040626
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207040626-Liquid-integration-with-AppsFlyer
---
> **At a glance:** Liquid, an AppsFlyer integrated partner, automates your campaigns and processes with no need to call your IT. Their intelligent rules engine acts based on user behavior and advanced analytics.

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions#pembatasan-sumber-media">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Liquid

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">here</Anchor>.

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

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for Liquid.

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

Permissions are not available for Liquid.

</Accordion>

<div data-zendesk-anchors="h_01H9FKBW5QYQGZ7PNEJMHZ6H2R=important h_01H9FKBW5QMJTARZ6KZ41QT1BN=setting-up-liquid h_01H9FKBW5QM601CMQ6Y2PNJ1HQ=integration-tab h_01H9FKBW5RRYW1JTK2S9V4V6SA=activate-partner h_01H9FKBW5RB52QQKVF5TMFVKKT=general-settings h_01H9FKBW5RCGHVJRJEBQW4KNGD=obtaining-the-api-token h_01H9FKBW5RVYXPEEFDG948P1XV=default-postbacks h_01H9FKBW5RNH2BRV8S31DT8SWA=attribution-link-tab h_01H9FKBW5RRQZZC4YQNWGHQTW6=cost-tab h_01H9FKBW5R7TNN5YA5YP36EJ63=ad-revenue-tab h_01H9FKBW5RC55F56K3EMQBJGEK=permissions-tab" />
