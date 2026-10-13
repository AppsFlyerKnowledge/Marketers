---
title: "Reddit campaign configuration"
excerpt: "Reddit, an AppsFlyer ad network integrated partner, is home to 430 million highly engaged monthly users who can’t be found anywhere else."
x-zendesk:
  id: 360011016138
  url: https://support.appsflyer.com/hc/en-us/articles/360011016138-Reddit-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  position: 2
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Agencies]
  labels: [integrated partner, Advertisers, Agencies, reddit, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2020-07-09T09:50:46Z'
  edited_at: '2026-09-09T13:07:27Z'
---
## Setting up Reddit

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

> 📘 Active status
>
> The toggle must stay on (active) as long as you work with the partner. [Learn more](/docs/partner-activation-deactivation)

5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

### Integration tab

The _**Integration Tab**_ is divided into different sections:

#### Activate partners

To enable the configuration, [activate the partner](/docs/partner-activation-deactivation#activating-a-partner).

#### Advanced Privacy

For iOS apps only, when **Advanced Privacy (for iOS 14.5+ and later)** is turned on, you can [control what data is shared](/docs/set-up-an-integrated-partner#b-advanced-privacy) with Reddit via postbacks and reports.

#### Transaction ID

For iOS apps only, when **Share SKAN transaction ID** is turned on, you're allowing AppsFlyer to [share the transaction ID of SKAdNetwork postbacks](/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners) with Reddit. By doing so, Reddit could decode your SKAdNetwork Conversion Values.

#### General settings

**Enable view-through attribution**

Activate, if you want to attribute view-through installs from Reddit. The view-through lookback slider is available in the [_**Attribution link**_](/docs/reddit-campaign-configuration#attribution-link-tab) tab.

**Advanced Matching data sharing**

Turn this on to share Advanced Matching fields, such as hashed email, hashed phone number, hashed first name, and hashed last name, with Reddit, if these fields are included in the event information sent to AppsFlyer. For more information, see: [Advanced Matching Data Sharing](/docs/advanced-matching-data-sharing).

#### Default postbacks

Send automatic postbacks to Reddit following user installs. Select whether to send postbacks for installs attributed to:

- Reddit only
- All sources, including organic

#### In-app events settings

In this section, you can configure in-app event postbacks that are sent to Reddit.

**To configure in-app event postbacks:**

1. Activate _**In-app event postbacks**_
2. Click _**Add event**_ to add an SDK event to the list.
3. Fill in the following data:

| Parameter name | Description |
| --- | --- |
| **SDK event name** | The name of the event, as received by AppsFlyer either from the SDK or from server-to-server events.<br />**Tip**: If you don't see the event you want in the list, activate this event on a device with a non-organic installation and recheck. |
| **Partner event identifier** | The unique name or ID of each event as defined on Reddit's side. Select the most suitable pre-defined event for your SDK event:<br />   - rdt\_install<br />   - rdt\_signup<br />   - rdt\_app\_launch<br />   - rdt\_search<br />   - rdt\_view\_content<br />   - rdt\_add\_payment\_info<br />   - rdt\_add\_to\_cart<br />   - rdt\_purchase<br />   - rdt\_completed\_tutorial<br />   - rdt\_level\_achieved<br />   - rdt\_spend\_credits<br />   - rdt\_ad\_click<br />   - rdt\_ad\_view<br />   - rdt\_add\_to\_wishlist<br />   - rdt\_unlock\_achievement<br />   - rdt\_login<br />   - rdt\_rate<br />   - rdt\_checkout<br />   - rdt\_start\_trial<br />   - rdt\_subscribe<br />   - rdt\_onboard\_started<br />   - rdt\_onboard\_completed<br />   - rdt\_first\_time\_purchase |
| **Sending option** | Select whether to send events by:<br />   - Reddit only<br />   - all sources, including organic |
| **Send event data** | - **No values & no revenue:** sends only the event itself without the event value.<br />   - **Values & no revenue:** sends all the parameters excluding the revenue value.<br />   - **Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event). |

4. Click _**Save**_.

### Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).

[Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters) **.**

**To generate an attribution link,** follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

### Cost tab

AppsFlyer gets cost details by API. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

- Follow [these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api).

[View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

### Ad revenue tab

Ad revenue data is not supported by Reddit.

### Permissions tab

In this tab, you can select the permissions to grant Reddit. Note that even if attribution is disabled for Reddit, the permissions tab is active and you can grant control to Reddit.

#### Ad network permissions

In this tab, you can select the permissions to grant Reddit. Note that even if attribution is disabled for Reddit, the permissions tab is active and you can grant control to Reddit.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

- _**Allow to configure integration:**_ permit the partner to set up the integration tab (except in-app event postbacks)
- _**Allow to configure in-app event postbacks:**_ permit the partner to set up in-app event postbacks mapping to itself on the integration tab
- _**Allow access to your retention report:**_ only to the partner's own retention data
- _**Allow access to your aggregate loyal user data:**_ only to the partner's own loyal user data
- _**Allow access to your aggregate in-app events data:**_ only to the partner's own in-app events data
- _**Allow access to your aggregate revenue data:**_ only to the revenue data attributed to the partner
- _**Allow spend ingestion:**_ permit the partner to send ad spend data in files for this app only.
- _**Allow access to your Protect360 dashboard:**_ only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).

## Raw data restrictions

Starting August 30, 2025:

The following restrictions apply to view-through attribution:

- Media source (reddit\_int) — available
- Attributed touch time Reported as date only (dd/mm/yyyy)
- Campaign details: Reported as restricted
- Clicks and impressions: Not included in raw data reports

The following restrictions apply to click-through attribution:

- Media source (reddit\_int) — available
- Attributed touch time Reported as date only (dd/mm/yyyy)
- Campaign details — available
- Clicks and impressions: Not included in raw data reports

> 📘 Reminder
>
> Data received about a Reddit campaign is subject to [Reddit Business Tool Terms](https://protect.checkpoint.com/v2/___https:/business.reddithelp.com/s/article/Reddit-Business-Tool-Terms___.YzJ1OnJlZGRpdDpjOmc6OGFlZGI3Y2U5MDg3ZTgxNzYxYzdjMzEzYzgwZjI3ZDI6NjowMDg5Ojg1MmViZDg4YWY2ZTg4NThjMDE2NjhkYTk2ZjZkYmZlYWI1NGY3MGEwNDk0MmE0ODQ0NTI3ZDM0ZWYwOWVlMmI6cDpUOk4#:%7E:text=These%20Reddit%20Business%20Tool%20Terms,advertising%20purposes%20or%20to%20otherwise), and includes, among other restrictions, a prohibition on using Reddit data to create profiles of any users.