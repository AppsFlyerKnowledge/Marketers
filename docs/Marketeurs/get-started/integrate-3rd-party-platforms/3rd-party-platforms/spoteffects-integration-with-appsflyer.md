---
title: Spoteffects integration with AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Webeffects
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
  created_at: '2017-09-06T14:38:15Z'
  edited_at: '2026-06-16T09:52:43Z'
  id: 115004574426
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115004574426-Spoteffects-integration-with-AppsFlyer
---
> **At a glance:** Spoteffects, an AppsFlyer integrated partner, develops and markets the software as a service solution. The solution allows media planners to optimize their TV campaigns for online shops and websites based on immediately generated visits and conversions per ad.

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions#restrictions-des-sources-média">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Spoteffects

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

The Spoteffects configuration window uses only the ***Integration*** tab.

For a detailed description of the Partner Configuration Window Header, click <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">here</Anchor>.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">here</Anchor>.

### Default postbacks

AppsFlyer can send automatic postbacks to Spoteffects user installs. Use this section to define sending these postbacks.

<Image align="center" alt="Swrve_msc_new_4.png" src="https://files.readme.io/a8cf728ceaa6ed9804dece249820496563f2a89aaf6a90275940e1be643646ab-18301290568465.png" />

Select **Events attributed to any partner or organic** to send postbacks for any user that downloads the app to Spoteffects or select **Off**.

Click **Save.**

### In-app event settings

<Image align="center" alt="" src="https://files.readme.io/97da1d47ab9bfa3855d18dcd60f3a263b8a631c477b354dc32486170b7708e96-360002201165.png" />

In this section, you can map your AppsFlyer events with Spoteffects via postbacks.

1. Toggle In-App Event Postbacks to ON
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Spoteffect's side.  <br />Obtain the corresponding Event ID from Spoteffect and set it in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

Click **Save**.

Once you have saved the configuration, AppsFlyer sends the following data to Spoteffects for every organic and non-organic install:

* Device ID (IDFA / Goggle Advertising ID)
* Media Source
* Campaign name

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for Spoteffects.

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

Permissions are not available for Spoteffects.

</Accordion>

<div data-zendesk-anchors="h_01H9HWJYD7AZTFXKESY1KHW52S=important h_01H9HWJYD75MTKJBMSZRFAG66Q=setting-up-spoteffects h_01H9HWJYD7MAWK9S226YWPZJ8G=integration-tab h_01H9HWJYD7X6KEFF3VEZEP4PGM=activate-partner h_01H9HWJYD7PW2TCYJRA815YNQE=default-postbacks inapp-event-settings=in-app-event-settings h_01H9HWJYD7SK47G91GF9J9Q2ZB=in-app-event-settings h_01H9HWJYD8RJM9BDX9RKSCC4RY=attribution-link-tab h_01H9HWJYD81VXJPT5D2TKQQN9C=cost-tab h_01H9HWJYD8XBV0V0KDNY955JCT=ad-revenue-tab h_01H9HWJYD8B9AQMVVMT16EH602=permissions-tab" />
