---
title: "Tencent AMS campaign configuration"
excerpt: "Tencent AMS, an AppsFlyer ad network integrated partner, operates social media and mobile utility properties in China, and enables marketers to run app install campaigns on: WeChat, the company’s mobile communication platform, QQ, the instant messaging service, QQ Music, QQ Browser, Myapp, and more."
x-zendesk:
  id: 360017577338
  url: https://support.appsflyer.com/hc/en-us/articles/360017577338-Tencent-AMS-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: China domestic market ad network configuration
  section_id: 6552066355601
  position: 0
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Agencies]
  labels: [integrated partner, Advertisers, China, Agencies, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-02-01T18:20:01Z'
  edited_at: '2026-09-15T10:40:24Z'
---
![](https://cdn.appsflyer.com/marketplace/static/logo/tencentams.png)

## Setting up Tencent AMS

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

### Integration tab

The Integration Tab is divided into different sections as described below.

### General settings

The Integration tab is divided into different sections as described below. To integrate TencentAMS with AppsFlyer, you’ll need the following credentials: **account\_id, user\_action\_set\_id, and access\_token**. If you don’t already have these values, please get them directly from Tencent AMS before proceeding with the integration.

![tencent.png](https://files.readme.io/56bfdc43b976f1f29f5ba121986aa66228cd79029025e84278cb3c304989fc3e-38300461521041.png)

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
2. Set the **In-app event postback window**, if required (read more about[in-app event postback window configuration](/docs/in-app-event-postback-configuration#inapp-event-postback-window)).
3. Click **Add event** to add an SDK Event to the list.
4. Fill in the following parameters in the table below

   

| Parameter name | Description |
| --- | --- |
| **SDK event name** | The name of the event, as received by AppsFlyer either from the SDK, or from server-to-server events.  <br />**Tip**: If you don't see the event you want in the list, activate this event on a device with a non-organic installation and recheck. |
| **Partner event identifier** | The unique name or ID of each event as defined on the partner's side. Select the most suitable pre-defined event for your SDK event. |
| **Sending option** | Select the sending option for the event:  <br />**This partner only** for events coming **only** from users attributed to Tencent AMS.  <br />**All sources, including organic** to have your entire user base available to be reported to the partner. |
| **Send event data** | * **No values & no revenue:** sends only the event itself without the event value.<br />* **Values & no revenue:** sends all the parameters excluding the revenue value.<br />* **Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event). |

5. Click **Save Integration**.

### Attribution link

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).  
[Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters).

**To generate an attribution link,**follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

### Cost tab

AppsFlyer gets cost details by API. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow [these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api).

[View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

### Ad revenue tab

Ad revenue integration is not available for Tencent AMS.

### Permissions tab

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

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#ad-network-permissions).