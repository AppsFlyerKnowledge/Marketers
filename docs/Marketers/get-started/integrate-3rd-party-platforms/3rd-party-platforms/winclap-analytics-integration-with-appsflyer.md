---
title: Winclap Analytics integration with AppsFlyer
excerpt: >-
  Winclap Analytics, an AppsFlyer integrated partner, uses AppsFlyer attribution
  data for BI and post-attribution analytics.
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2019-09-04T11:07:12Z'
  edited_at: '2026-09-15T09:17:18Z'
  id: 360002403537
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360002403537-Winclap-Analytics-integration-with-AppsFlyer
---
> 📘 **Important!**
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Winclap

The setup is done from the **Active Integrations** page, but to find the partner you must first go to the [marketplace](/docs/partner-integrations).

> 📘 **Note**
>
> **Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.
>
> **To set up a new integration:**
>
> 1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.
>    (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
> 2. Select the relevant app.
> 3. Search for the partner and select **Integrate**.
> 4. In the **Integration** tab, turn on the **Activate partner** toggle.
>    **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
> 5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

Winclap Analytics configuration makes use of the ***Integration*** tab only.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you must toggle ON the ***Activate Partner*** toggle to enable the setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/user-level-data-retention).

### Default postbacks

AppsFlyer can send automatic postbacks to Winclap Analytics user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

![winclap analytics integration - default postbacks](https://files.readme.io/a45d8d7ab4687876d8dea4b026580d80f4b34c151b00c3c47a701771d16582aa-50896714399761.png)

For **installs**, select:

* (Default) ***This partner only***for events coming only from users attributed to Winclap.
* ***All media sources, including organic***to send postbacks for any user that downloads the app to Winclap.

For **reengagements**, the postbacks can be sent for ***This partner only***.

Once this configuration is saved, AppsFlyer sends the following data to Winclap Analytics for each install, both organic and non-organic:

* Click ID
* Campaign name
* User-agent
* Click time
* IP
* Country
* City
* Sub publisher
* Device ID for Android & iOS
* Carrier
* Language
* App ID
* App version
* App name
* Install time

### In-app events settings

In this section, you can map which in-app events to send to Winclap Analytics using postbacks:

[![winclap analytics - in-app event postback configuration](https://files.readme.io/f14f801a50b3c699f71141a387a9d75586bae7b91aad88f29f97778408ee12fb-50896714404369.png)](https://files.readme.io/f14f801a50b3c699f71141a387a9d75586bae7b91aad88f29f97778408ee12fb-50896714404369.png)

1. Switch the ***In-App Event Postbacks*** toggle to ON.
2. Set the ***In-app event postback window***, if required (read more about[in-app event postback window configuration](/docs/in-app-event-postback-configuration#in-app-event-postback-window)).
3. Click ***Add Event*** to add an SDK Event to the list.
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK event name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip**: Don't see the event you are looking for? Type in its SDK Event Name, click **Create custom**, and map normally. Read more about [custom event mapping](/docs/in-app-event-postback-configuration#custom-events). |
| **Partner event identifier** | The unique name or ID of each event as defined by Winclap.  <br />Get from Winclap the corresponding ID for each of the events you want to report to them, and enter in this field. |
| **Sending option** | Select the sending option for the event:  <br />**This partner only** for events coming **only** from users attributed to this partner  <br />**All media sources, including organic** to have your entire user base available to be reported to the partner |
| **Send event data** | <ul><li>**No values & no revenue:** sends only the event itself without the event value.</li><li>**Values & no revenue:** sends all the parameters excluding the revenue value.</li><li>**Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event).</li></ul> |

5. Click ***Save*.**

Once this configuration is saved, AppsFlyer sends the following data to Winclap Analytics for each non-organic event:

* Click ID
* Event name
* Event value
* Event revenue
* Event currency
* Event revenue in USD
* Campaign name
* User-agent
* Click time
* IP
* Country
* City
* Sub publisher
* Device ID for Android & iOS
* Carrier
* Language
* App ID
* App version
* App name
* Install time

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for Winclap Analytics.

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

Permissions are not available for Winclap Analytics.

</Accordion>

<div data-zendesk-anchors="h_01H9HWQK6JA2194MPE8PVQJ346=important h_01H9HWQK6JAQ2GCHHGQ57PJ570=setting-up-winclap h_01H9HWQK6JRZ1KVDJK00PZR7T9=note h_01H9HWQK6JX9MAD64MQ1HPK4T0=integration-tab h_01H9HWQK6JKRB5MDE43RKV3SEH=activate-partner h_01H9HWQK6JP4HQHRFC011KW6XQ=default-postbacks inapp-events-settings=in-app-events-settings h_01H9HWQK6J1MEK67XDMAMKAQKW=in-app-events-settings h_01H9HWQK6JBH1M2MZQM12R0SAR=attribution-link-tab h_01H9HWQK6JG46BGNRMR8ZM9W2J=cost-tab h_01H9HWQK6J7HHJWKVB55WE1VW9=ad-revenue-tab h_01H9HWQK6J6BD0ER2M9Z7GYGSM=permissions-tab" />
