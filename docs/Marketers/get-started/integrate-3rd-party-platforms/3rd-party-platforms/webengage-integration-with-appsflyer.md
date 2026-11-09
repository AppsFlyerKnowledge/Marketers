---
title: WebEngage integration with AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-07-25T13:44:42Z'
  edited_at: '2026-06-16T09:54:49Z'
  id: 7898288493841
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/7898288493841-WebEngage-integration-with-AppsFlyer
---
> **At a glance:** WebEngage, an AppsFlyer integrated partner, is an Intelligent Marketing Cloud built for the mobile-first world.

<div id="important" />

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions#media-source-restrictions">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

<div id="setting-up-webengage" />

## Setting up WebEngage

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

The WebEngage configuration window uses only the **Integration** tab.

Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">setting the partner page header.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration tab is divided into different sections, as described below.

<div id="activate-partner" />

### Activate partner

On your first visit, turn **Activate Partner** on to set up the integration. The toggle must be on for as long as you work with the partner. Learn more about <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">partner activation</Anchor>.

<div id="general-settings" />

### General settings

WebEngage connects with AppsFlyer via an API key and the data center region of WebEngage.

* **api\_key:** Enter the API key. To obtain it, log in to your WebEngage account, and follow the <Anchor target="_blank" href="https://docs.webengage.com/docs/appsflyer#step-3-add-webengage-api-key--data-center-region">instructions</Anchor>.
* **Region:** Enter the region where your data is to be hosted: **US** (for the USA Data Center) or **IN** (for the India Data Center). By default, all data is stored in the US data center.

![web_mo_engage_general_settings_en-us.png](https://files.readme.io/1297a02a9e280b238a222b14972dc657acffe4566dc49d607178ea43fdc01a77-8089123842705.png) 

<div id="default-postbacks" />

### Default postbacks

AppsFlyer can send automatic postbacks to WebEngage following user installs and re-engagements.

* **Off**: Don't send any install postbacks.
* **All media sources, including organic**: Send postbacks for events attributed to any partner and for organic events.

<Image align="center" alt="web_mo_engage_default_postbacks_en-us.png" src="https://files.readme.io/0dc0c658f349712158c417f27ce816b7735b8901454293e996a4bc3ae94a32fe-8094249223953.png" />

<div id="note" />

> 📘 **Note**
>
> As an all-installs network, WebEngage prefers to receive postbacks for all new installs of your app from any source, including organic. WebEngage recommends selecting **All media sources, including organic**.

<div id="in-app-event-settings" />

### In-app event settings

Map AppsFlyer events with WebEngage via postbacks. If postback sending is enabled, this includes rejected in-app events (events blocked by Protect360 or events found to be non-compliant by target validation rules).

<div id="to-configure-in-app-event-postbacks" />

#### To configure in-app event postbacks

1. Enter the **api\_key** and **Region**.
2. Enable **In-app event postbacks**.
3. Click **Add event** to add an SDK or server-to-server event to the list.
4. Complete the parameters required.
5. [Optional] Click<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/62f8f45f72137c00326b90f046b15bc36214e35626afafd2e76513b91eea31d9-17028066777873.png" width="30px" />to set conditions for sending certain in-app events to the partner.  
   Learn more about <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">conditional in-app event postbacks</Anchor>.

| Parameter Name | Description |
| --- | --- |
| **AppsFlyer event** | The event name, as received by AppsFlyer, either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#custom-events">custom event mapping.</Anchor></li></ul> |
| **for users from** | Select the sending option for the event:<ul><li>**This partner only**: send postbacks only when this event is attributed to this partner.</li><li>**All media sources, including organic**: send postbacks for events attributed to any partner, including organic events.</li></ul> |
| **including** | <ul><li>**No data (default)**: send only the event itself without the event value.</li><li>**Values and revenue**: send all the event parameters, **including** the revenue value (if exists in the event).</li><li>**Values without revenue**: send all the parameters **excluding** the revenue value.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

**Attribution link** isn't supported in the integration with this partner.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

**Cost data** isn't supported in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

**Ad revenue** isn't supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

**Permissions** isn't supported in the integration with this partner.

</Accordion>

<div data-zendesk-anchors="h_01H9HWK7APBFK7RWVFH79VW0ME=important h_01H9HWK7AP6Z398NP3G2BQQBTF=setting-up-webengage h_01H9HWK7AP3ERT0TM39E6S5M79=integration-tab h_01H9HWK7AP3FMR5RMANZCMQ6M0=activate-partner h_01H9HWK7APG1STZ4Q19QVX4KRY=general-settings h_01H9HWK7AP23GK6WWJTB543FEQ=default-postbacks h_01H9HWK7APMBSZ1PG8MK88HZFS=note inapp-event-settings=in-app-event-settings h_01H9HWK7APFNAFE9YM2484DDHD=in-app-event-settings to-configure-inapp-event-postbacks=to-configure-in-app-event-postbacks h_01H9HWK7APZM8328V0EV4B5QDN=to-configure-in-app-event-postbacks h_01H9HWK7AQTZXE7GPX5E9X2ZYN=attribution-link-tab h_01H9HWK7AQ8SXED5KHVD5T4DZZ=cost-tab h_01H9HWK7AQ2JG4BRS784M85Z6E=ad-revenue-tab h_01H9HWK7AQ5YJDY2M96CA05H6P=permissions-tab" />
