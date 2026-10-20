---
title: Eulerian integration with AppsFlyer
excerpt: >-
  Eulerian, an AppsFlyer integrated partner, is focusing on the analysis and
  real-time optimization of e-marketing operations. Based on an exhaustive data
  collection system, Eulerian marketing suite provides a combination of
  marketing web attribution and data management solutions. This technology
  enables users to centralize, analyze, manage and activate data in real-time.
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Eulerian
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
  created_at: '2018-10-02T08:41:24Z'
  edited_at: '2026-06-16T09:54:27Z'
  id: 360001521405
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360001521405-Eulerian-integration-with-AppsFlyer
---
> 📘 **Important!**
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Eulerian

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

Eulerian's configuration window includes 4 tabs: **Integration, Attribution link, Data Enrichment**, and **Permissions**. Click on the items below to read about the tab setup.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/user-level-data-retention).

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation, click [here](/docs/partner-activation-deactivation).

### General settings

**HostID**

Eulerian connects with AppsFlyer via a unique Host ID. If you don't already have it, you must obtain it from Eulerian to continue with the integration.

![Eulerian_msc_new_2.png](https://files.readme.io/345b05c3960015bfe1b44dd2a298c4216185c2315fb859378e9e337ba2bf913a-360002665949.png)

Perform the following steps, as required:

* Enter the **HostID**
* Toggle **Enable** to send all installs to Eurlerian

### Default postbacks

AppsFlyer can send automatic postbacks to Eulerian following user installs. Use this section to define sending these postbacks.

![Eulerian_new_2.png](https://files.readme.io/59cb41cdbec6c06dd4fc2086d238fe2015e5414a474591b23f9a18f8421fb030-360002795789.png)

Select **Events attributed to any partner** to send postbacks to Eulerian.

### In-app event settings

In this section you can map your AppsFlyer events with Eulerian via postbacks.

![Eulerian_new_3.png](https://files.readme.io/c190a6b05c977c8d5fa2a0e5301cdb5be239e56455b066cba93b8c1ffa6fcd9a-360002795829.png)

1. Enter the HostID again.
2. Toggle In-App Event Postbacks to ON
3. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list
5. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Eulerian's side.  <br />Obtain the corresponding Event ID from Eulerian and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

6. Click **Save**.

Once saved, AppsFlyer begins sending data to Eulerian for every organic and non-organic install.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for Eulerian.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost is not supported in the integration with Eulerian.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with Eulerian.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Permissions are not available for Eulerian.

</Accordion>

<div data-zendesk-anchors="h_01H9FK7FC3ME19HXCRQ0XKVQQC=important h_01H9FK7FC309KKTAKZ1K9AHAN5=setting-up-eulerian h_01H9FK7FC3K3Y8220AG9YK3BP8=integration-tab h_01H9FK7FC316DZHE9YKSWQ5A5N=activate-partner h_01H9FK7FC4ZBQ2XPTFYQ4C7XH6=general-settings h_01H9FK7FC4VBY3TEE6HEJZCWWT=default-postbacks inapp-event-settings=in-app-event-settings h_01H9FK7FC4KF5QGXA9KQ4YQEA3=in-app-event-settings h_01H9FK7FC4H7QSFGWDV1AP0YK6=attribution-link-tab h_01H9FK7FC48YAYF3TGXC2C9EB8=cost-tab h_01H9FK7FC4YAPTGA15172P5TXB=ad-revenue-tab h_01H9FK7FC46W5A1BRSVPBEGJTK=permissions-tab" />
