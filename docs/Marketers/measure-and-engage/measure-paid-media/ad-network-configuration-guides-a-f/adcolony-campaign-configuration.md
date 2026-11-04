---
title: AdColony campaign configuration
metadata:
  keywords:
    - Adcolony
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
  created_at: '2016-03-06T10:58:12Z'
  edited_at: '2026-09-09T12:34:54Z'
  id: 208005106
  locale: en-us
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/208005106-AdColony-campaign-configuration
---
> **At a glance:** AdColony, an AppsFlyer ad network integrated partner, is a premium video advertising network, providing advertisers and brands with an engaged and responsive audience and offers monetization solutions to publishers and developers. In addition to click-based mobile attribution, AdColony also offers cost, ad revenue, and view-through attribution, which you can record with AppsFlyer.

<div id="setting-up-adcolony" />

## Setting up AdColony

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

The **Integration** tag is divided into different sections as described below.

<div id="activate-partners" />

### Activate partners

The <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation#activate-a-partner-integration">partner must be activated</Anchor> by switching on the ***Activate partner*** toggle on the first visit, to enable its setup.

<div id="general-settings" />

### General settings

<div id="enable-view-through-attribution" />

#### Enable View-Through attribution

Toggle this ON if you want to attribute view-through installs from AdColony. The view-through lookback slider is available on the ***Attribution link*** tab.

<div id="default-postbacks" />

### Default postbacks

Send automatic postbacks to AdColony following installs and rejected installs. Use this section to define the **source of the users** for the postbacks.

Select ***This partner only*** for installs coming only from users attributed to AdColony.  
Select ***All sources, including organi*c** to have your entire user base available to be reported to AdColony.

Rejected installs can be sent for **This partner only**.

<div id="launch-postbacks" />

#### Launch postbacks

As of July 1, 2020, we no longer send launch postbacks to AdColony. If your integration was set up prior to this date, there may be changes to your configurations. The following table explains possible changes and your actions, where applicable:

| Your configuration | Will be updated to | Your next actions |
| --- | --- | --- |
| Send to AdColony **all launches** (from all media sources, including organic) | Send to AdColony:<ul><li>**all installs** (from all media sources, including organic)</li><li>**all** `af_app_opened` **events** (from all media sources, including organic)</li></ul> | No further actions required. This update has no actual impact on the configuration. |
| Send to AdColony **attributed first launches only** | Send to AdColony **installs** attributed to AdColony only | If you wish to send `af_app_open` events as well:<ul><li>In AppsFlyer, on AdColony integration page, configure sending the event under the ***In-app event postbacks*** section</li></ul> |
| Send to AdColony **all launches** (from all media sources, including organic)<br /><br />**BUT**<br /><br />No conversions have been attributed to AdColony in the 3 months prior to July 1, 2020 | Send **all installs**<br /><br />**AND**<br /><br />For 30 days after July 1, 2020, **all launches** | If you wish to send `af_app_open` events as well:<ul><li>In AppsFlyer, on AdColony integration page, configure sending the event under the ***In-app event postbacks*** section.</li></ul>If done during the 30 days period, we will discontinue sending all launches and start sending all `af_app_open` events instead.<br /><br />If done after the 30 days period, we will stop sending launches and won't send `af_app_open` events until configured otherwise. |

<div id="in-app-events-settings" />

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
   | **Send event data** | * **No values & no revenue:** sends only the event itself without the event value.<br />* **Values & no revenue:** sends all the parameters excluding the revenue value.<br />* **Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event). |

4. Click ***Save***.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink</Anchor>.

<Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost integration via API isn't available for this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue isn't currently supported for this partner integration.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant AdColony. Note that even if attribution is disabled for AdColony, the permissions tab is active and you can grant control to AdColony.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

<div id="ad-network-permissions" />

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user dataost data sync
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HJR62VJZXTFPXYRMYT05EV1X=setting-up-adcolony h_01HJR62VJZZZQRBHAA6FT8D6GY=integration-tab h_01HJR62VJZQRBWFACANBJ6HG14=activate-partners h_01HJR62VJZFDKC4N7BC5P1TSZK=general-settings enable-viewthrough-attribution=enable-view-through-attribution h_01HJR62VJZEC4E5FZVCKWDXNEY=enable-view-through-attribution h_01HJR62VJZR34JMT4TM0YG1DC6=default-postbacks h_01HJR62VJZJX57VMDNEQFKFB9C=launch-postbacks inapp-events-settings=in-app-events-settings h_01HJR62VJZJHHH4Q8P8ZERXVRM=in-app-events-settings h_01HJR62VK0980EE3ZKYT2KFB5H=attribution-link-tab h_01HJR62VK0G62A2S3WTW49150C=cost-tab h_01HJR62VK0869W4K5R1JF7V0C4=ad-revenue-tab h_01HJR62VK0GMA3TTGPPS3ND64F=permissions-tab h_01HJR62VK0AHRTPN92TGGCMC5D=ad-network-permissions" />
