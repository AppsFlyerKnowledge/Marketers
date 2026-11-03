---
title: Reddit campaign configuration
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - Agencies
    - reddit
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
  created_at: '2020-07-09T09:50:46Z'
  edited_at: '2026-10-13T01:12:21Z'
  id: 360011016138
  locale: zh-cn
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/zh-cn/articles/360011016138
---
> **At a glance:** Reddit, an AppsFlyer ad network integrated partner, is home to 430 million highly engaged monthly users who can’t be found anywhere else.

## Setting up Reddit

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

The ***Integration Tab*** is divided into different sections:

#### Activate partners

To enable the configuration, <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation#渠道对接的启用方式">activate the partner</Anchor>.

#### Advanced Privacy

For iOS apps only, when **Advanced Privacy (for iOS 14.5+ and later)** is turned on, you can <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#b-advanced-privacy">control what data is shared</Anchor> with Reddit via postbacks and reports.

#### Transaction ID

For iOS apps only, when **Share SKAN transaction ID** is turned on, you're allowing AppsFlyer to <Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">share the transaction ID of SKAdNetwork postbacks</Anchor> with Reddit. By doing so, Reddit could decode your SKAdNetwork Conversion Values.

#### General settings

**Enable view-through attribution**

Activate, if you want to attribute view-through installs from Reddit. The view-through lookback slider is available in the [***Attribution link***](/docs/reddit-campaign-configuration#attribution-link-tab) tab.

**Advanced Matching data sharing**

Turn this on to share Advanced Matching fields, such as hashed email, hashed phone number, hashed first name, and hashed last name, with Reddit, if these fields are included in the event information sent to AppsFlyer. For more information, see: <Anchor target="_blank" href="/marketers/zh/docs/advanced-matching-data-sharing">Advanced Matching Data Sharing</Anchor>.

#### Default postbacks

Send automatic postbacks to Reddit following user installs. Select whether to send postbacks for installs attributed to:

* Reddit only
* All sources, including organic

#### In-app events settings

In this section, you can configure in-app event postbacks that are sent to Reddit.

**To configure in-app event postbacks:**

1. Activate ***In-app event postbacks***
2. Click ***Add event*** to add an SDK event to the list.
3. Fill in the following data:

| Parameter name | Description |
| --- | --- |
| **SDK event name** | The name of the event, as received by AppsFlyer either from the SDK or from server-to-server events.  <br />**Tip**: If you don't see the event you want in the list, activate this event on a device with a non-organic installation and recheck. |
| **Partner event identifier** | The unique name or ID of each event as defined on Reddit's side. Select the most suitable pre-defined event for your SDK event:<ul><li>rdt\_install</li><li>rdt\_signup</li><li>rdt\_app\_launch</li><li>rdt\_search</li><li>rdt\_view\_content</li><li>rdt\_add\_payment\_info</li><li>rdt\_add\_to\_cart</li><li>rdt\_purchase</li><li>rdt\_completed\_tutorial</li><li>rdt\_level\_achieved</li><li>rdt\_spend\_credits</li><li>rdt\_ad\_click</li><li>rdt\_ad\_view</li><li>rdt\_add\_to\_wishlist</li><li>rdt\_unlock\_achievement</li><li>rdt\_login</li><li>rdt\_rate</li><li>rdt\_checkout</li><li>rdt\_start\_trial</li><li>rdt\_subscribe</li><li>rdt\_onboard\_started</li><li>rdt\_onboard\_completed</li><li>rdt\_first\_time\_purchase</li></ul> |
| **Sending option** | Select whether to send events by:<ul><li>Reddit only</li><li>all sources, including organic</li></ul> |
| **Send event data** | <ul><li>**No values & no revenue:** sends only the event itself without the event value.</li><li>**Values & no revenue:** sends all the parameters excluding the revenue value.</li><li>**Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event).</li></ul> |

4. Click ***Save***.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">these integration instructions</Anchor>.

<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api状态">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue data is not supported by Reddit.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Reddit. Note that even if attribution is disabled for Reddit, the permissions tab is active and you can grant control to Reddit.

#### Ad network permissions

In this tab, you can select the permissions to grant Reddit. Note that even if attribution is disabled for Reddit, the permissions tab is active and you can grant control to Reddit.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* <span id="01EDKYCTJGZCQ05BQ5JXR6457Y"></span>***<span id="01EDKYCTJHNYT3SRD6Q40YJKR1"></span>Allow to configure integration:*** permit the partner to set up the integration tab (except in-app event postbacks)
* <span id="01EDKYCTJHVW0E6TD5ARMFEQQC"></span>***Allow to configure in-app event postbacks:*** permit the partner to set up in-app event postbacks mapping to itself on the integration tab
* <span id="01EDKYCTJH6C06V91M50CXNSZS"></span>***Allow access to your retention report:*** only to the partner's own retention data
* <span id="01EDKYCTJHY2JXJHQRQM6S1T7H"></span>***Allow access to your aggregate loyal user data:*** only to the partner's own loyal user data
* <span id="01EDKYCTJHF1W3FPJCSSEKJ4GZ"></span>***Allow access to your aggregate in-app events data:*** only to the partner's own in-app events data
* <span id="01EDKYCTJHVN8E1QPY3BSMC3WD"></span>***Allow access to your aggregate revenue dat*a:** only to the revenue data attributed to the partner
* <span id="01EDKYCTJHX0T89JNPJKY71WVW"></span>***Allow spend ingestion:*** permit the partner to send ad spend data in files for this app only.
* <span id="01EDKYCTJHWKWYJS7ZFCJ8558V"></span>***Allow access to your Protect360 dashboard:*** only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

## Raw data restrictions

Starting August 30, 2025:

The following restrictions apply to view-through attribution:

* Media source (reddit\_int) — available
* Attributed touch time Reported as date only (dd/mm/yyyy)
* Campaign details: Reported as restricted
* Clicks and impressions: Not included in raw data reports

The following restrictions apply to click-through attribution:

* Media source (reddit\_int) — available
* Attributed touch time Reported as date only (dd/mm/yyyy)
* Campaign details — available
* Clicks and impressions: Not included in raw data reports

**Reminder:** Data received about a Reddit campaign is subject to <Anchor target="_blank" href="https://protect.checkpoint.com/v2/___https:/business.reddithelp.com/s/article/Reddit-Business-Tool-Terms___.YzJ1OnJlZGRpdDpjOmc6OGFlZGI3Y2U5MDg3ZTgxNzYxYzdjMzEzYzgwZjI3ZDI6NjowMDg5Ojg1MmViZDg4YWY2ZTg4NThjMDE2NjhkYTk2ZjZkYmZlYWI1NGY3MGEwNDk0MmE0ODQ0NTI3ZDM0ZWYwOWVlMmI6cDpUOk4#:%7E:text=These%20Reddit%20Business%20Tool%20Terms,advertising%20purposes%20or%20to%20otherwise">Reddit Business Tool Terms</Anchor>, and includes, among other restrictions, a prohibition on using Reddit data to create profiles of any users.

<div data-zendesk-anchors="01EDKYCH117BTY81G0Z2NF181F=setting-up-reddit 01EDKYCH11YM04HDJTAWP4XHWH=integration-tab 01EDKYCH11E2X1VSSG2HKKP6VS=activate-partners h_01HJRZF42CYME3EZ37470339CF=advanced-privacy h_01HJRZF42CN7VT8SKNX5E638R0=transaction-id 01EDKYCH11WFJ09XBND6RQT0XA=general-settings 01EDKYCH11KZT2BN64AGETTMD6=default-postbacks inapp-events-settings=in-app-events-settings 01EDKYCH11QAYSV2GMYD4R6DJJ=in-app-events-settings h_01HJRZF42DHDDHPCE4NYA7QKV2=attribution-link-tab h_01HJRZF42DYG18DTKSV4G8NHV4=cost-tab 01EDKYCH124QTAFK6VQ3ARHCTM=ad-revenue-tab 01EDKYCH12RY4P6DY3QSWG1A18=permissions-tab 01EDKYCH12FXE1WASY5YQF80CV=ad-network-permissions 01JAQ0TCR54Q03RQWPNT5PJGPN=raw-data-restrictions" />
