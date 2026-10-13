---
title: "Basic fraud detection and insights​ with ProtectLITE dashboard and reporting"
excerpt: "ProtectLITE provides insights about fraudulent installs blocked by AppsFlyer's basic, free protection engine and validation rules."
x-zendesk:
  id: 360017223058
  url: https://support.appsflyer.com/hc/en-us/articles/360017223058-Basic-fraud-detection-and-insights-with-ProtectLITE-dashboard-and-reporting
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Protect your traffic
  section_id: 6551015912465
  position: 7
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-yanai, Marketers, Protect360 / Fraud protection]
  labels: [Advertisers, Protect360, Marketers, Loc In Prog]
  promoted: false
  comments_disabled: true
  created_at: '2021-01-25T09:47:02Z'
  edited_at: '2025-06-03T07:54:47Z'
---
**At a glance:** ProtectLITE provides insights about fraudulent installs blocked by our basic, free protection engine, and installs blocked due to the application of validation rules.

## ProtectLITE

ProtectLITE provides free, basic protection against install attribution fraud. Advanced fraud protection and detection are available with [Protect360](/docs/protect360-anti-fraud-guide).

When AppsFlyer identifies fraud, it is blocked in the traffic data (available via AppsFlyer dashboards and raw data reports), but it does not impact the end-user app experience. This means the app user can still use the app and generate revenue for the advertiser.

The ProtectLITE dashboard:

* Displays aggregate data for all your apps for installs blocked in real-time, either due to fraudulent installs, hijacked installs, or your [Validation Rules](/docs/implement-validation-rules-to-prevent-fraud).
* Allows you to drill down to further examine identified installs by using the filtering and grouping options.
* Shows you additional anti-fraud capabilities that can be accessed only with a Protect360 subscription, including: Advanced real-time fraud, post-attribution fraud, in-app events fraud, in-app events Validation Rules, and anomalies analysis tools.

ProtectLITE [raw data](/docs/protect360-raw-data-reports):

* Is available in the Protect360 Installs report via the Export Data page and Pull API.

## Dashboard

To view the ProtectLITE dashboard, in AppsFlyer, go to **Protect360**.

Dashboard features are described in the sections that follow.

### Filters and groupings

**Filter and groupings window**

The following filtering and grouping options are available:

* Basic filters:
  * App name
  * Source type: Non-organic and/or organic
  * Media source
  * Geo
  * Date range ([see time zone support](/docs/about-data-freshness-and-timezone-support#protect360-dashboard))
* Expanded filters - click on the blue arrow, to the right of the date picker:
  * Agencies
  * Channels
  * Minimum cohort size
* Grouping options - choose different dimensions to group the fraud data by to get the specific insights you need:
  * **Application:** compare the total amount of fraud per each of your apps.
  * **Media Source**(default): compare the handled fraud from each of the media sources used by your apps.
  * **Media Source + Campaign**: compare the handled fraud from all your campaigns across all media sources used by your apps.
  * **Media Source + Site ID**: compare the handled fraud from all publishers (site IDs) across all media sources used by your apps.
  * **Media Source + Site ID + Campaign**: compare the handled fraud from all publishers (site IDs) across all media sources used by your apps, associated with the relevant campaign names.
  * **Geo**: compare the handled fraud from all countries.
  * **Media source + Geo** (available in the In-app events dashboard): compare the handled fraud from each of the media sources used by your apps associated with the relevant countries.

### Installs—headline metrics

The headline metrics enable you to see:

* Estimated savings
* Identified installs
* Suspected overall fraud threat

Metrics are relevant for the time period selected in the date filter.

For the Estimated savings and Identified installs KPIs, there is a percentage value. This value shows how the presented KPI is in relation to the parallel date range before it. For example, this week compared to last week, or any days selected in the date range compared to the same number of days that came before: if it shows an X% increase in estimated savings, it means the previous parallel date range had X% fewer fraudulent installs.

#### Estimated savings

[![](https://files.readme.io/f53d6245eb8bb81fb652a05869fe71102ed50ab304d2fc8faf1cc17198794470-360019038197.jpg)](https://files.readme.io/f53d6245eb8bb81fb652a05869fe71102ed50ab304d2fc8faf1cc17198794470-360019038197.jpg)

Estimated savings metrics:

* Displays the value of fraud identified and blocked in real-time by ProtectLITE and Validation Rules, to be settled by you with the ad networks.
* Uses the formula: Estimated Savings = number of blocked installs X app average eCPI.
* Are not relevant for organic traffic.

For more details on how this amount is calculated read this [FAQ](/docs/protect360-anti-fraud-guide#faq).

#### Identified installs

[![](https://files.readme.io/2bc38a1ee19b4a13c18ed7571d97efd0f855d27142e8a6cd9a761cac276d3bd0-360019090998.jpg)](https://files.readme.io/2bc38a1ee19b4a13c18ed7571d97efd0f855d27142e8a6cd9a761cac276d3bd0-360019090998.jpg)

Identified installs metrics display the number of installs identified and blocked in real-time by ProtectLITE and Validation Rules.

#### Suspected overall fraud threat

[![](https://files.readme.io/bb6a33cfea1dbff695d46a4b2f6547b756740cf35b750db25097d7ec772cc3d8-360019091058.jpg)](https://files.readme.io/bb6a33cfea1dbff695d46a4b2f6547b756740cf35b750db25097d7ec772cc3d8-360019091058.jpg)

The suspected overall threat level:

* Is an estimate of the fraud that would be blocked by Protect360, if you had a subscription.
* Gives you a good idea of whether you should upgrade to Protect360 to receive more advanced anti-fraud protection.

### Installs—chart

#### Fraud trend over time chart

The chart displays the number of installs per day blocked by ProtectLITE and Validation Rules, for the time period selected in the date filter.

### Installs—table

#### Identified fraud breakdown

The table displays the number of installs blocked by ProtectLITE and Validation Rules for the time period selected in the date filter.

Click **Export CSV** to download the table to your desktop in CSV format.

The table is presented in a general overview format, as shown in the image that follows.

[![plite_fraud_table.jpg](https://files.readme.io/81246675ce8f0e1243e0c0d64e1cf347246bb403894718ad9e23c56fc594eb84-360019038257.jpg)](https://files.readme.io/81246675ce8f0e1243e0c0d64e1cf347246bb403894718ad9e23c56fc594eb84-360019038257.jpg)

The dynamic table structure lets you:

* Click the table settings button to add or remove columns to the table.  
  If you make any changes, make sure to click the Save button afterward so your customizations are saved for your future visits.
* Change the order of the columns by dragging the columns sections in the columns settings.

[![plite_edit_columns.jpg](https://files.readme.io/52fc1378d4c758d80ed2a89b24f5b7fa949c9ccccae7ff5edf4af307538e805a-360019038297.jpg)](https://files.readme.io/52fc1378d4c758d80ed2a89b24f5b7fa949c9ccccae7ff5edf4af307538e805a-360019038297.jpg)

#### Content of the identified fraud breakdown table



| Table column | Description |
| --- | --- |
| Groupings | * [Default] The table and dashboard are grouped by Media source.<br />* When selecting a specific media source, the grouping is automatically by both Media source and Site ID.<br />* Optional groupings include Campaign, GEO, Channel, agency, and combinations thereof.<br />* If you select a grouping with dimensions that only apply to non-organic traffic, the table displays N/A for the organic media source. |
| **Installs** | **Headline breakdown of installs blocked due to fraud and Validation Rules** |
| Total (A) | * Total installs = All app installs including fraudulent installs and installs identified via Validation Rules.<br />* Regular installs are available per media source (non-organic) in the Overview dashboard. |
| Identified installs (B) | * Total number of installs identified and blocked in real-time<br />* Organic blocked installs are not shown in the dashboard. To see organic blocked installs, use raw data reports.<br />* [Default] The table is sorted in descending order using this KPI. |
| **Identified installs %**(B/A) | Identified installs / Total installs |
| **Identified post-attribution (C)** | Requires Protect360 |
| **Identified post-attribution % (C/A)** | Requires Protect360 |
| **Fake installs** | **Fraudulent installs simulating real user activity.** |
| Real-time block | Fake installs blocked in real-time. |
| Identified post-attribution | Requires Protect360 |
| **Hijacked installs** | **Fraudulent last clicks stealing attribution of real user installs.** |
| Real-time block | Hijacked installs blocked in real-time. |
| Identified post-attribution | Requires Protect360 |
| **Validation rules** | **Installs found invalid due to validation rules conditions.** |
| Blocked installs | Installs blocked by validation rules. |
| Blocked attribution | Installs with attribution corrected due to validation rules. |
| **Clicks** | **Legit clicks from the source.**<br /><br />**Note:** All attribution types must be selected in the filter bar in order for click data to display in the table (otherwise it will display as N/A). Be sure to adjust your filter selections accordingly. |
| Total (E) | Total number of legit clicks received from the source. |
| Blocked | Clicks blocked due to fraud |
| **Impressions** | **Impressions from the source.**<br /><br />**Note:** All attribution types must be selected in the filter bar in order for impressions data to display in the table (otherwise it will display as N/A). Be sure to adjust your filter selections accordingly. |
| Total | Total number of legitimate and fraudulent impressions received from the source |
| Blocked | Impressions blocked due to fraud |



## Traits and limitations



| Trait | Remarks |
| --- | --- |
| Advertiser access | All account users. |
| Ad network access | * ProtectLITE dashboard and raw data access require [advertiser permission.](/docs/set-up-an-integrated-partner#ad-network-permissions)<br />* Advertiser must have the ad network as an integrated partner. |
| Agency access | ProtectLITE dashboard and raw data access require [advertiser permission.](/docs/set-up-an-integrated-partner#ad-network-permissions) |
| Agency transparency | Transparent agency: Can see specific media sources<br /><br />Non-transparent agency: Cannot see specific media sources |