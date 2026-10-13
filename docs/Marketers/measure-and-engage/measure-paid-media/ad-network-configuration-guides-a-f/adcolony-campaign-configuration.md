---
title: "AdColony campaign configuration"
excerpt: "Configure your AdColony integration in AppsFlyer to record mobile attribution, cost, ad revenue, and view-through attribution."
x-zendesk:
  id: 208005106
  url: https://support.appsflyer.com/hc/en-us/articles/208005106-AdColony-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  position: 2
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Adcolony, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2016-03-06T10:58:12Z'
  edited_at: '2026-09-09T12:34:54Z'
---
AdColony, an AppsFlyer ad network integrated partner, is a premium video advertising network, providing advertisers and brands with an engaged and responsive audience and offers monetization solutions to publishers and developers. In addition to click-based mobile attribution, AdColony also offers cost, ad revenue, and view-through attribution, which you can record with AppsFlyer.

## Setting up AdColony

> 📘 Prerequisite
>
> An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

> 📘 Note
>
> The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)

5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

## Integration tab

The **Integration** tag is divided into different sections as described below.

### Activate partners

The [partner must be activated](/docs/partner-activation-deactivation#activating-a-partner) by switching on the _**Activate partner**_ toggle on the first visit, to enable its setup.

### General settings

#### Enable View-Through attribution

Toggle this ON if you want to attribute view-through installs from AdColony. The view-through lookback slider is available on the _**Attribution link**_ tab.

### Default postbacks

Send automatic postbacks to AdColony following installs and rejected installs. Use this section to define the **source of the users** for the postbacks.

Select _**This partner only**_ for installs coming only from users attributed to AdColony.

Select _**All sources, including organic**_ to have your entire user base available to be reported to AdColony.

Rejected installs can be sent for **This partner only**.

#### Launch postbacks

As of July 1, 2020, we no longer send launch postbacks to AdColony. If your integration was set up prior to this date, there may be changes to your configurations. The following table explains possible changes and your actions, where applicable:

| Your configuration | Will be updated to | Your next actions |
| --- | --- | --- |
| Send to AdColony **all launches** (from all media sources, including organic) | Send to AdColony:<br />- **all installs** (from all media sources, including organic)<br />- **all**`af_app_opened` **events** (from all media sources, including organic) | No further actions required. This update has no actual impact on the configuration. |
| Send to AdColony **attributed first launches only** | Send to AdColony **installs** attributed to AdColony only | If you wish to send `af_app_open` events as well:<br />- In AppsFlyer, on AdColony integration page, configure sending the event under the _**In-app event postbacks**_ section |
| Send to AdColony **all launches** (from all media sources, including organic)<br />**BUT**<br />No conversions have been attributed to AdColony in the 3 months prior to July 1, 2020 | Send **all installs**<br />**AND**<br />For 30 days after July 1, 2020, **all launches** | If you wish to send `af_app_open` events as well:<br />- In AppsFlyer, on AdColony integration page, configure sending the event under the _**In-app event postbacks**_ section.<br />If done during the 30 days period, we will discontinue sending all launches and start sending all `af_app_open` events instead.<br />If done after the 30 days period, we will stop sending launches and won't send `af_app_open` events until configured otherwise. |

### In-app events settings

In this section, you can configure in-app event postbacks that are sent to AdColony.

**To configure in-app event postbacks:**

1. Activate _**In-app event postbacks**_
2. Click _**Add event**_ to add an SDK Event to the list
3. 
| Parameter name | Description |
| --- | --- |
| **SDK event name** | The name of the event, as received by AppsFlyer either from the SDK, or from server-to-server events.<br />**Tip**: If you don't see the event you want in the list, activate this event on a device with a non-organic installation and recheck. |
| **Partner event identifier** | The unique name or ID of each event as defined on the partner's side. Select the most suitable pre-defined event for your SDK event. |
| **Sending option** | Select the sending option for the event:<br />**This partner only** for events coming **only** from users attributed to AdColony.<br />**All sources, including organic** to have your entire user base available to be reported to the partner |
| **Send event data** | - **No values & no revenue:** sends only the event itself without the event value.<br />   - **Values & no revenue:** sends all the parameters excluding the revenue value.<br />   - **Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event). |

4. Click _**Save**_.

## Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).

[Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters).

**To generate an attribution link,** follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

## Cost tab

Cost integration via API isn't available for this partner.

## Ad revenue tab

Ad revenue isn't currently supported for this partner integration.

## Permissions tab

In this tab, you can select the permissions to grant AdColony. Note that even if attribution is disabled for AdColony, the permissions tab is active and you can grant control to AdColony.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

- _**Allow to configure integration**_ - permit the partner to set up the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks**_ - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report**_ - only to the partner's own retention data
- _**Allow access to your aggregate loyal user data**_ - only to the partner's own loyal user dataost data sync
- _**Allow access to your aggregate in-app events data**_ - only to the partner's own in-app events data
- _**Allow access to your aggregate revenue data**_ - only to the revenue data attributed to the partner
- _**Allow access to your Protect360 dashboard**_ - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).