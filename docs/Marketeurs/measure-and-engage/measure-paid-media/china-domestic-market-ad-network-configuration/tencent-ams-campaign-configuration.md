---
title: Tencent AMS campaign configuration
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - China
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-02-01T18:20:01Z'
  edited_at: '2026-09-15T10:40:24Z'
  id: 360017577338
  locale: en-us
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360017577338-Tencent-AMS-campaign-configuration
---
> **At a glance:** Tencent AMS, an AppsFlyer ad network integrated partner, operates social media and mobile utility properties in China, and enables marketers to run app install campaigns on: WeChat, the company’s mobile communication platform, QQ, the instant messaging service, QQ Music, QQ Browser, Myapp, and more.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/tencentams.png" width="120px" />

## Setting up Tencent AMS

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### General settings

The Integration tab is divided into different sections as described below. To integrate TencentAMS with AppsFlyer, you’ll need the following credentials: **account\_id, user\_action\_set\_id, and access\_token**. If you don’t already have these values, please get them directly from Tencent AMS before proceeding with the integration.

<Image alt="tencent.png" src="https://files.readme.io/56bfdc43b976f1f29f5ba121986aa66228cd79029025e84278cb3c304989fc3e-38300461521041.png" width="248px" />

> 📘 **Note**
>
> The **access\_token** is issued by Tencent AMS and is valid for 30 days. Per Tencent's requirement, you (or your managing agency) must **manually refresh the token every 30 days and update it in the above field**.
>
> * If the token expires, postbacks to Tencent AMS will fail until a new token is entered.
> * If you're not sure how to obtain or refresh the token, reach out to your Tencent AMS account manager for guidance.
>
> **Agency-managed traffic:** If your traffic is promoted by an agency, **the agency must also fill in and maintain the token on their side**.

#### Enable View-Through attribution

To enable view-through install attribution, turn this on.  
The view-through lookback slider is available on the attribution link tab (described below).

#### Default postbacks

AppsFlyer can send automatic postbacks to Tencent AMS following user installs. This section displays the **source of the users** that allow sending these postbacks.

#### In-app event settings

In this section, you can configure in-app event postbacks that are sent to Tencent AMS.

**To configure in-app event postbacks**,

1. Turn **In-app event postback** on.
2. Set the **In-app event postback window**, if required (read more about <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#in-app-event-postback-window">in-app event postback window configuration</Anchor>).
3. Click **Add event** to add an SDK Event to the list.
4. Fill in the following parameters in the table below

| Parameter name | Description |
| --- | --- |
| **SDK event name** | The name of the event, as received by AppsFlyer either from the SDK, or from server-to-server events.  <br />**Tip**: If you don't see the event you want in the list, activate this event on a device with a non-organic installation and recheck. |
| **Partner event identifier** | The unique name or ID of each event as defined on the partner's side. Select the most suitable pre-defined event for your SDK event. |
| **Sending option** | Select the sending option for the event:  <br />**This partner only** for events coming **only** from users attributed to Tencent AMS.  <br />**All sources, including organic** to have your entire user base available to be reported to the partner. |
| **Send event data** | <ul><li>**No values & no revenue:** sends only the event itself without the event value.</li><li>**Values & no revenue:** sends all the parameters excluding the revenue value.</li><li>**Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event).</li></ul> |

5. Click **Save Integration**.

</Accordion>

<div id="attribution-link" />

<Accordion title="Attribution link">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/fr/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">these integration instructions</Anchor>.

<Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue integration is not available for Tencent AMS.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Tencent AMS. Note that even if attribution is disabled for Tencent AMS, the permissions tab is active and you can grant control to Tencent AMS.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* **Allow to configure integration** - permit the partner to setup the integration tab (except in-app event postbacks)
* **Allow to configure in-app event postbacks** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* **Allow access to your retention report** - only to the partner's own retention data
* **Allow access to your aggregate loyal user data** - only to the partner's own loyal user data
* **Allow access to your aggregate in-app events data** - only to the partner's own in-app events data
* **Allow access to your aggregate revenue data** - only to the revenue data attributed to the partner
* **Allow spend ingestion** - permit the partner to send ad spend data in files; for this app only.
* **Allow access to your Protect360 & Raw data dashboard** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#autorisations-pour-le-réseau-publicitaire">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HJNQZJX2TX4C8ZR2Y9JCANGC=setting-up-tencent-ams h_01HJNQZJX26YHHDX8GBBGBG68M=integration-tab h_01HJNQZJX2QSYR4D6EWB8S1BHQ=general-settings h_01KXZFXJJGZHGQT345V190R5RJ=note enable-viewthrough-attribution=enable-view-through-attribution h_01HJNQZJX2VSCTVPE1B63P24TQ=enable-view-through-attribution h_01HJNQZJX2K7EJZ89TQBKF8SB7=default-postbacks inapp-event-settings=in-app-event-settings h_01HJNQZJX2W7F5HCEGNVQHMTVE=in-app-event-settings h_01HJNQZJX2XFD0Q8J3XSCN6ZVP=attribution-link h_01HJNQZJX2R4R6FQ01BTAR184H=cost-tab h_01HJNQZJX2T985MXFNSHAP58Y9=ad-revenue-tab h_01HJNQZJX29H2ZTR0PSRHMXAM8=permissions-tab" />
