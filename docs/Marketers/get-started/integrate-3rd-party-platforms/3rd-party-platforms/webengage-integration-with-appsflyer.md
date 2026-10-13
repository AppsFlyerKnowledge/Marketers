---
title: "WebEngage integration with AppsFlyer"
excerpt: "Learn how to set up and configure the WebEngage integration with AppsFlyer to send install and in-app event postbacks."
x-zendesk:
  id: 7898288493841
  url: https://support.appsflyer.com/hc/en-us/articles/7898288493841-WebEngage-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: 3rd-party platforms
  section_id: 6551199962257
  position: 31
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2022-07-25T13:44:42Z'
  edited_at: '2026-06-16T09:54:49Z'
---
WebEngage, an AppsFlyer integrated partner, is an Intelligent Marketing Cloud built for the mobile-first world.

> ❗️ Important!
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up WebEngage

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

> 📘 Note
>
> The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)

5. Complete the configuration using the relevant tabs, as described below.

The WebEngage configuration window uses only the **Integration** tab.

Learn more about [setting the partner page header.](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page)

## Integration tab

The Integration tab is divided into different sections, as described below.

### Activate partner

On your first visit, turn **Activate Partner** on to set up the integration. The toggle must be on for as long as you work with the partner. Learn more about [partner activation](/docs/partner-activation-deactivation).

### General settings

WebEngage connects with AppsFlyer via an API key and the data center region of WebEngage.

- **api_key:** Enter the API key. To obtain it, log in to your WebEngage account, and follow the [instructions](https://docs.webengage.com/docs/appsflyer#step-3-add-webengage-api-key--data-center-region).
- **Region:** Enter the region where your data is to be hosted: **US** (for the USA Data Center) or **IN** (for the India Data Center). By default, all data is stored in the US data center.

![web_mo_engage_general_settings_en-us.png](https://files.readme.io/1297a02a9e280b238a222b14972dc657acffe4566dc49d607178ea43fdc01a77-8089123842705.png)

### Default postbacks

AppsFlyer can send automatic postbacks to WebEngage following user installs and re-engagements.

- **Off**: Don't send any install postbacks.
- **All media sources, including organic**: Send postbacks for events attributed to any partner and for organic events.

![web_mo_engage_default_postbacks_en-us.png](https://files.readme.io/0dc0c658f349712158c417f27ce816b7735b8901454293e996a4bc3ae94a32fe-8094249223953.png)

> 📘 Note
>
> As an all-installs network, WebEngage prefers to receive postbacks for all new installs of your app from any source, including organic. WebEngage recommends selecting **All media sources, including organic**.

### In-app event settings

Map AppsFlyer events with WebEngage via postbacks. If postback sending is enabled, this includes rejected in-app events (events blocked by Protect360 or events found to be non-compliant by target validation rules).

#### To configure in-app event postbacks

1. Enter the **api_key** and **Region**.
2. Enable **In-app event postbacks**.
3. Click **Add event** to add an SDK or server-to-server event to the list.
4. Complete the parameters required.
5. [Optional] Click ![conditional-iae-postbacks-icon.png](https://files.readme.io/62f8f45f72137c00326b90f046b15bc36214e35626afafd2e76513b91eea31d9-17028066777873.png) to set conditions for sending certain in-app events to the partner.

Learn more about [conditional in-app event postbacks](/docs/in-app-event-postback-configuration#conditional-inapp-event-postbacks).

| Parameter Name | Description |
| --- | --- |
| **AppsFlyer event** | The event name, as received by AppsFlyer, either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<br />- Make sure to activate the event on a device with a non-organic installation and recheck.<br />- Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events) |
| **for users from** | Select the sending option for the event:<br />- **This partner only**: send postbacks only when this event is attributed to this partner.<br />- **All media sources, including organic**: send postbacks for events attributed to any partner, including organic events. |
| **including** | - **No data (default)**: send only the event itself without the event value.<br />- **Values and revenue**: send all the event parameters, **including** the revenue value (if exists in the event).<br />- **Values without revenue**: send all the parameters **excluding** the revenue value. |

## Attribution link tab

**Attribution link** isn't supported in the integration with this partner.

## Cost tab

**Cost data** isn't supported in the integration with this partner.

## Ad revenue tab

**Ad revenue** isn't supported in the integration with this partner.

## Permissions tab

**Permissions** isn't supported in the integration with this partner.