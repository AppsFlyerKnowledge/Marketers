---
title: "AdColony campaign configuration"
excerpt: "AdColony, an AppsFlyer ad network integrated partner, is a premium video advertising network, providing advertisers and brands with an engaged and responsive audience and offers monetization solutions to publishers and developers. In addition to click-based mobile attribution, AdColony also offers cost, ad revenue, and view-through attribution, which you can record with AppsFlyer."
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
## Setting up AdColony

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

<Accordion title="Integration tab">

The **Integration** tag is divided into different sections as described below.

### Activate partners

The [partner must be activated](/docs/partner-activation-deactivation#activate-a-partner-integration) by switching on the ***Activate partner*** toggle on the first visit, to enable its setup.

### General settings

#### Enable View-Through attribution

Toggle this ON if you want to attribute view-through installs from AdColony. The view-through lookback slider is available on the ***Attribution link*** tab.

### Default postbacks

Send automatic postbacks to AdColony following installs and rejected installs. Use this section to define the **source of the users** for the postbacks.

Select ***This partner only*** for installs coming only from users attributed to AdColony.  
Select ***All sources, including organi*c** to have your entire user base available to be reported to AdColony.

Rejected installs can be sent for **This partner only**.

#### Launch postbacks

As of July 1, 2020, we no longer send launch postbacks to AdColony. If your integration was set up prior to this date, there may be changes to your configurations. The following table explains possible changes and your actions, where applicable:

| Your configuration | Will be updated to | Your next actions |
| --- | --- | --- |
| Send to AdColony **all launches** (from all media sources, including organic) | Send to AdColony:<br /><br />* **all installs** (from all media sources, including organic)<br />* **all** `af_app_opened` **events** (from all media sources, including organic) | No further actions required. This update has no actual impact on the configuration. |
| Send to AdColony **attributed first launches only** | Send to AdColony **installs** attributed to AdColony only | If you wish to send `af_app_open` events as well:<br /><br />* In AppsFlyer, on AdColony integration page, configure sending the event under the ***In-app event postbacks*** section |
| Send to AdColony **all launches** (from all media sources, including organic)<br /><br />**BUT**<br /><br />No conversions have been attributed to AdColony in the 3 months prior to July 1, 2020 | Send **all installs**<br /><br />**AND**<br /><br />For 30 days after July 1, 2020, **all launches** | If you wish to send `af_app_open` events as well:<br /><br />* In AppsFlyer, on AdColony integration page, configure sending the event under the ***In-app event postbacks*** section.<br /><br />If done during the 30 days period, we will discontinue sending all launches and start sending all `af_app_open` events instead.<br /><br />If done after the 30 days period, we will stop sending launches and won't send `af_app_open` events until configured otherwise. |

### In-app events settings

In this section, you can configure in-app event postbacks that are sent to AdColony.

**To configure in-app event postbacks:**

1. Activate ***In-app event postbacks***
2. Click ***Add event*** to add an SDK Event to the list
3. 

| Parameter name | Description |
| --- | --- |
| **SDK event name** | The name of the event, as received by AppsFlyer either from the SDK, or from server-to-server events.  <br />**Tip**: If you don't see the event you want in the list, activate this event on a device with a non-organic installation and recheck. |
| **Partner event identifier** | The unique name or ID of each event as defined on the partner's side. Select the most suitable pre-defined event for your SDK event. |
| **Sending option** | Select the sending option for the event:  <br />**This partner only** for events coming **only** from users attributed to AdColony.  <br />**All sources, including organic** to have your entire user base available to be reported to the partner |
| **Send event data** | <ul><li>**No values & no revenue:** sends only the event itself without the event value.</li><li>**Values & no revenue:** sends all the parameters excluding the revenue value.</li><li>**Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event).</li></ul> |

4. Click ***Save***.

</Accordion>

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).

[Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters).

**To generate an attribution link,** follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

</Accordion>

<Accordion title="Cost tab">

Cost integration via API isn't available for this partner.

</Accordion>

<Accordion title="Ad revenue tab">

Ad revenue isn't currently supported for this partner integration.

</Accordion>

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant AdColony. Note that even if attribution is disabled for AdColony, the permissions tab is active and you can grant control to AdColony.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user dataost data sync
* ***Allow access to your aggregate in-app events data** -*only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).

</Accordion>
