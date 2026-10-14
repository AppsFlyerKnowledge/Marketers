---
title: "Convertro integration with AppsFlyer"
excerpt: "Convertro, an AppsFlyer integrated partner, strives to be the leading automated tool for marketers to truly understand the performance of their advertising choices and activate upon these insights as quickly as possible. They've built a technology that not only gathers granular information about the customer path to conversion, but is also able to scientifically optimize marketing mix and automatically understand how to shift spend to maximize ROI."
x-zendesk:
  id: 207040636
  url: https://support.appsflyer.com/hc/en-us/articles/207040636-Convertro-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: 3rd-party platforms
  section_id: 6551199962257
  position: 7
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Ad Networks]
  labels: [Attribution, Convertro, integrated partner, Advertisers, Ad Networks, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2015-12-24T11:37:56Z'
  edited_at: '2026-06-16T10:00:29Z'
---
> 📘 **Important!**
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Convertro

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

The Convertro configuration window uses only the **Integration** tab.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation, click [here](/docs/partner-activation-deactivation).

### General settings

**Page URL, Site ID, and Client Name**

Convertro connects with AppsFlyer via a unique Page URL, Site ID, and Client Name. If you don't already have them, you must obtain them from Convertro to continue with the integration or follow the instructions below.

[![](https://files.readme.io/74a1ea32d0667da1a4fe4797cb83f75639111b24c98f72d2caa721e6911e3015-360002220189.png)](https://files.readme.io/74a1ea32d0667da1a4fe4797cb83f75639111b24c98f72d2caa721e6911e3015-360002220189.png)

### Obtaining the "Client Name, Page URL & Site ID" From the Convertro Platform

To obtain the Client Name, Page URL, and Site ID, login to the Convertro dashboard:

**Page URL:**

[![](https://files.readme.io/f20c2e45146f0874d94dc84c4f61658e15274970f348896a40b2806d3fe540c9-204790263.png)](https://files.readme.io/f20c2e45146f0874d94dc84c4f61658e15274970f348896a40b2806d3fe540c9-204790263.png)

**Site ID:**

[![](https://files.readme.io/b60897bea0b640cb393bceecb57c14370b2ba074818160af0a25a53c7a8ce26b-204790283.png)](https://files.readme.io/b60897bea0b640cb393bceecb57c14370b2ba074818160af0a25a53c7a8ce26b-204790283.png)

**Client Name:**

![](https://files.readme.io/2e5342006bdfff9e3b3c1dffdaed3e9d83ec2fe4c465b7918023a359776cee91-204595606.png)

### Default postbacks

AppsFlyer can send automatic postbacks to Convertro user installs. Use this section to define sending these postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/e0cf7b9ce9a13f572017dfc7bb4581430ddbfdd2e198fe20ef0b953c6c3188a6-18274456382865.png)

Select **Events attributed to any partner or organic** to send postbacks for any user that downloads the app to Convertro or select **Off**.

Click **Save.**

### In-app event settings

[![](https://files.readme.io/5c1d6841c7f8397d797964790c1f200d60a6ab81fe67eb2162b2a5e7c73462d3-360002200405.png)](https://files.readme.io/5c1d6841c7f8397d797964790c1f200d60a6ab81fe67eb2162b2a5e7c73462d3-360002200405.png)

In this section, you can map your AppsFlyer events with Convertro via postbacks.

1. Enter the Client Name, Site ID, and Page URL again.
2. Toggle In-App Event Postbacks to ON.
3. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list.
5. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Convertro's side.  <br />Obtain the corresponding Event ID from Convertro and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

Click **Save**.

Once this configuration is saved, AppsFlyer begins sending the following data to Convertro for every organic and non-organic install:

* Converto Parameters
* Device ID for Android and iOS
* Media Source
* Campaign name
* Click Time
* User IP
* User Agent
* Customer User ID (optional, if configured)

</Accordion>

<Accordion title="Attribution link tab">

Attribution Links are not available for Convertro.

</Accordion>

<Accordion title="Cost tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<Accordion title="Permissions tab">

Permissions are not available for Convertro.

</Accordion>
