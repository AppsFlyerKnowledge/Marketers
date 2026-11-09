---
title: IBM UBX integration guide with AppsFlyer
metadata:
  keywords:
    - Analytics
    - IBM
    - UBX
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
  created_at: '2016-07-03T09:06:26Z'
  edited_at: '2026-06-16T10:01:11Z'
  id: 210093266
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/210093266-IBM-UBX-integration-guide-with-AppsFlyer
---
> **At a glance:** IBM UBX (Universal Behavior Exchange), an AppsFlyer integrated partner, is a feature of the IBM Marketing Cloud and other IBM Commerce offerings which allows marketers to take control of all their customer data integration with an easy-to-use console. This open data exchange capability provides a contextual view of customer buying behaviors across all channels, devices, and interactions, so marketers can quickly design and deploy effective campaigns, delivering meaningful experiences in an instant, while driving ROI.

<div id="important" />

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions#media-source-restrictions">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

<div id="setting-up-ibm" />

## Setting up IBM

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

The IBM configuration window uses only the **Integration** tab.

For a detailed description of the Partner Configuration Window Header, click <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">here</Anchor>.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

<div id="activate-partner" />

### Activate partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">here</Anchor>.

<div id="general-settings" />

### General settings

**Authorization Key**

IBM connects with AppsFlyer via a unique Authorization Key. If you don't already have it, you must obtain it from IBM to continue with the integration or follow the steps below.

<Image align="center" alt="IBM_msc_new_2.png" src="https://files.readme.io/d6dddd7232ba7ecba2ed5bd944f98669902689fc0953afc558fbc6586be8b5cf-360002219269.png" />

<div id="obtaining-the-authorization-key" />

### Obtaining the authorization key

The first step in setting up a generic AppsFlyer event publisher endpoint is to create a blank endpoint in the UBX interface.

To do this, log into your UBX account and navigate to the **Endpoints** tab

<Image align="center" alt="" src="https://files.readme.io/8c0833f890c5e2ed2df1c0a8904e1764b341a82f3381c0a1a3fb6effe4f76673-205128323.png" />

Next, click **Register new endpoint**

<Image align="center" alt="" src="https://files.readme.io/23c8d4a88eda765fce1b42f9eb2e74b1325160e6d0602dc65a8ab05488598b9e-205053206.png" />

Next, select **AppsFlyer** and click **Next**.

<Image align="center" alt="IBM_1.png" src="https://files.readme.io/f30b7b27d2ffecf3e562cbe651367306a581d1881325dd141c950b39efac016c-115002600286.png" />

Click **Next**

<Image align="center" alt="Pasted_image_at_2017_02_23_02_48_PM.png" src="https://files.readme.io/11a94c4d9f4c9282c230e4cf69f31e0d39f4eb88196313b3cfc103a5bbaba9a4-115002600326.png" />

Click on the 3 dots on the right side in the newly generated AppsFlyer endpoint and click **endpoint details**.

<Image align="center" alt="IBM_3.png" src="https://files.readme.io/70edd2e14c6c344188dcc65b65b3a8d92081401dd34909f5a4e0dd6bd137b8df-115002599203.png" />

Copy the Authentication key:

<Image align="center" alt="IBM_Endpoint_details.png" src="https://files.readme.io/3706f4dd665d8d2a26de9013b03c0e6575d051f2fa5500033e172312a63f09ea-115002601006.png" />

<div id="default-postbacks" />

### Default postbacks

AppsFlyer can send automatic postbacks to IBM user installs. Use this section to define sending these postbacks.

<Image align="center" alt="Swrve_msc_new_4.png" src="https://files.readme.io/4177c541ab0fca228cfa24827a7828260566fa4ff9110e65688abd4c1892ccb5-18274502749329.png" />

Select **Events attributed to any partner or organic** to send postbacks for any user that downloads the app to IBM or select **Off**.

Click **Save.**

<div id="in-app-event-settings" />

### In-app event settings

<Image align="center" alt="" src="https://files.readme.io/c945ee3c04f49076e54c9966389506aea441406e01daa49d737a86da9f5bd2bc-360002219429.png" />

In this section you can map your AppsFlyer events with IBM via postbacks.

1. Enter the Authorization Key again.
2. Toggle In-App Event Postbacks to ON
3. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list
5. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated with your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on IBM's side.  <br />Obtain the corresponding Event ID from IBM and set it in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for IBM.

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

Permissions are not available for IBM.

</Accordion>

<div data-zendesk-anchors="h_01H9FK8FS5T9KZ30N87B76QVT5=important h_01H9FK8FS5QPJYSA7JVY4QNB3S=setting-up-ibm h_01H9FK8FS5J30GZS634NMG62BQ=integration-tab h_01H9FK8FS5SYTBF8A3QX4QGESM=activate-partner h_01H9FK8FS5YXRCN83RHG6QBAKS=general-settings h_01H9FK8FS5ZVGX5RK7K72SH6K6=obtaining-the-authorization-key h_01H9FK8FS5SVF4YQC8AG2V6N8D=default-postbacks inapp-event-settings=in-app-event-settings h_01H9FK8FS54N196VQ0XCXJ763Q=in-app-event-settings h_01H9FK8FS50TB7TZH9JKEH3Y7H=attribution-link-tab h_01H9FK8FS54P1MYVXGR46TXN7D=cost-tab h_01H9FK8FS600SP0MS1T6PTBMH4=ad-revenue-tab h_01H9FK8FS65VMZK13D2BE5DT09=permissions-tab" />
