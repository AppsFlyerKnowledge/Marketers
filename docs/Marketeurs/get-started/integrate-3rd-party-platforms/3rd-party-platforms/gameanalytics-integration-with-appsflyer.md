---
title: GameAnalytics integration with AppsFlyer
metadata:
  keywords:
    - GameAnalytics
    - integrated partner
    - Advertisers
    - Ad Networks
    - game
    - game analytics
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
  created_at: '2015-12-24T11:42:56Z'
  edited_at: '2026-06-16T11:24:01Z'
  id: 207447143
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207447143-GameAnalytics-integration-with-AppsFlyer
---
> **At a glance:** Game Analytics, an AppsFlyer integrated partner, is a powerful free tool that helps developers understand player behavior so they can improve engagement, reduce churn, and perfect monetization. It helps to visualize core gaming KPIs in one convenient view and offers in-game benchmarking to see how your metrics stack up against more than 14,000 similar titles.

It takes just a few minutes to set up and it’s totally free of charge – no usage caps or hidden premium features! If you’d rather see the platform in action before integrating it with your title, just sign up to see a demo game with pre-populated data.

The platform is trusted by more than 40,000 game developers worldwide, from indies to world-renowned studios, and handles over five billion unique events every day across 2+ billion devices. GameAnalytics is widely integrated, with SDKs for every major game engine and platform. You can sign up for free today at https://gameanalytics.com/

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions#restrictions-des-sources-média">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up GameAnalytics

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below:

The Game Analytics configuration window uses only the ***Integration*** tab.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable the setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">here</Anchor>.

### General settings

**Game Key**

Game Analytics connects with AppsFlyer via a unique Game Key. If you don't already have it, you must obtain it from Game Analytics to continue with the integration.

<Image align="center" alt="Game_Analytics_msc_new_2.png" src="https://files.readme.io/0c629a74c16d6d8a861ee3ec344de68516a6224e9d6f5afb4b7d89fe78baa49f-360002199865.png" />

### Default postbacks

AppsFlyer can send automatic postbacks to Game Analytics user installs. Use this section to define sending these postbacks.

<Image align="center" alt="Swrve_msc_new_4.png" src="https://files.readme.io/6dc59212bec2f68ca6b4c26d77324f204c67fedb1329fea8dda41fcefc832a92-18274501554449.png" />

Select **Events attributed to any partner or organic** to send postbacks for any user that downloads the app to Game Analytics or select **Off**.

### In-app event settings

<Image align="center" alt="" src="https://files.readme.io/64dd102e95aacda70cb8c0cde471c5c31d6b744543089a2d00a1ab1640fbb1c3-360002219789.png" />

In this section you can map your AppsFlyer events with Game Analytics via postbacks.

1. Enter the Game Key again.
2. Toggle In-App Event Postbacks to ON
3. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list
5. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated with your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Game Analytics's side.  <br />Obtain the corresponding Event ID from Game Analytics and set it in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

Click **Save**.

Once this configuration is saved, AppsFlyer begins sending the following data to Game Analytics for every non-organic install:

* game\_key
* Media Source
* Campaign name

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for Game Analytics.

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

Permissions are not available for Game Analytics.

</Accordion>

<div data-zendesk-anchors="h_01H9FK7ZH27GNEHRZ5KKVH5CHY=important h_01H9FK7ZH24E9AD7Z0J94NS0JJ=setting-up-gameanalytics h_01H9FK7ZH3VPBE965Z8MCVXSMQ=integration-tab h_01H9FK7ZH3D2H5AWW0DMBQP9R3=activate-partner h_01H9FK7ZH3E32TT8EGAYWPRWBE=general-settings h_01H9FK7ZH3P0HSQGR2409BFA2F=default-postbacks inapp-event-settings=in-app-event-settings h_01H9FK7ZH366RDSY36QVVWJMJN=in-app-event-settings h_01H9FK7ZH39J4Q7W5XSFZAEZWH=attribution-link-tab h_01H9FK7ZH37FQ6RN80E90TH4K9=cost-tab h_01H9FK7ZH3GE3G69AA03KJK499=ad-revenue-tab h_01H9FK7ZH3RQJQPAYSZBR208H7=permissions-tab" />
