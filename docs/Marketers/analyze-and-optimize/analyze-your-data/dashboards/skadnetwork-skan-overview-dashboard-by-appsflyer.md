---
title: SKAdNetwork (SKAN) overview dashboard by AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-07-25T21:27:38Z'
  edited_at: '2026-10-18T07:56:11Z'
  id: 360011307357
  locale: en-us
  section: Dashboards
  section_id: 6550925337873
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360011307357-SKAdNetwork-SKAN-overview-dashboard-by-AppsFlyer
---
**At a glance:** The SKAdNetwork (SKAN) dashboard displays campaign metrics reported via iOS SKAN postbacks and additional data points during initial user measurement windows. Modeled metrics which consider null conversions are also available. Data displays using the install or postback arrival date.

![SKAdHeadling8_us-en.png](https://files.readme.io/72c2eb452741cbd77c5828197f827f238c71c5097b8703528fa180dcafe2364c-360011831017.png)

## Dashboard principles

The dashboard contains SKAN campaign performance data and adheres to the following principles:

* Consider that Apple, due to a <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork">privacy threshold mechanism</Anchor>, doesn't always populate the conversion value (CV). These are referred to as null CVs. In the case of null CVs, only an install is recorded.
* Metrics are calculated as follows:
  * Non-organic metrics in the dashboard are calculated using SKAN postback data received by AppsFlyer. Some metrics like redownloads, source app ID, and fidelity type metrics require that you configure your app to <Anchor target="_blank" href="/marketers/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">send postback copies directly to AppsFlyer</Anchor>.
  * Organic metrics are calculated as AppsFlyer attribution data minus SKAN non-organic attribution data. **Note**: Organic metrics aren't always available. [Learn more](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations).
    * Make sure you filter by **New installs** in the install type field.
  * Some metrics, like revenue and ROAS, have both the original value derived from postbacks and a [modeled value](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) that considers the null CV rate.
* Agency-driven traffic is treated as coming from a transparent agency.
* Data freshness:
  * Daily.
  * Postbacks received on a given day are processed at the end of the day UTC. Data is available by 08:00 UTC of the following day. Meaning postbacks received on Monday are available in the dashboard on Tuesday morning.
  * See <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">expected dashboard update time.</Anchor>

## SKAN dashboard view options

Display data using either the [install date or postback arrival date](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#filter-options).

**To select a date display option**, in AppsFlyer, from the side menu, select **Analyze** > **SKAN Overview.** In the filter bar, select a **Display by** date option.

Additional filters and display options are described in the sections that follow.

## Dashboard use

<div id="dashboard-settings" />

<Accordion title="Dashboard settings">

Dashboard settings are available when your app uses legacy <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio#fixed-modes">fixed-mode conversion measurement</Anchor> to select the conversion event.

**To select the conversion event**:

1. In the upper-right side of the dashboard, click **Dashboard settings**.
2. Select a conversion event.
3. Click apply.  
   Conversion metrics are calculated using this event.  
   Note! This setting relates to the display in the dashboard and doesn't affect the CV setting in the app.

</Accordion>

<div id="filter-options" />

<Accordion title="Filter options">

Use filters to refine the information displayed.

| **Filter** | **Remarks** |
| --- | --- |
| Display by | <ul><li>**Install date**: Is derived from the postback arrival time as follows:<ul><li>If the SKAN postbacks are SKAN V4, the install date formula is: Install date = postback arrival time - [accumulated window length] - [average postback delay].<ul><li>Postback 1: install date = postback arrival time - 48h - 36h</li><li>Postback 2: install date = postback arrival time - 168h - 84h</li><li>Postback 3: install date = postback arrival time - 840h - 84h</li></ul></li><li>If the SKAN postbacks are SKAN V3 or earlier, the install date formula is: Install date = postback arrival time - 36 hours - [average last-active range].<ul><li>The default [average last-active range] is 12 hours.</li><li>For a conversion value of 0, the average last-active range is set to 0.</li></ul></li></ul></li><li>**Postback arrival date**:<ul><li>The date in the ad\_network\_timestamp field of the SKAN raw data reports. The timestamp depends on the ad network:<ul><li>Google Ads: The estimated click timestamp.</li><li>Meta Ads: The timestamp returned via the Meta API.</li><li>All other ad networks: The timestamp when the ad network received the SKAN postback from Apple.</li></ul></li><li>When you compare metrics in the AppsFlyer SKAN dashboard to those provided by ad networks, consider that ad networks typically make data available using the postback arrival date.</li><li>Organic metrics aren't available when selecting this option.</li><li>In the case of Google Ads, the arrival and install dates don't differ.</li></ul></li></ul> |
| Date range | <ul><li>The attributed install date. This date is derived using the postback arrival time.</li><li>If there are large numbers of installs, the inaccuracy due to timing issues is insignificant.</li><li>Installs include redownloads.</li><li>The date range is limited to 90 days.</li></ul> |
| Media source | <ul><li>The ad network attributed with the install</li><li>Agency-driven traffic: The actual media source displays irrespective of the agency transparency status. Consequently, you may see media sources that you aren't familiar with.</li></ul> |
| Campaign | <ul><li>Campaign name and ID as set by the ad network.</li><li>AppsFlyer translates the postback campaign ID to that of the ad network.</li><li>If a given campaign ID has multiple campaign names associated with it, then all names display in the dashboard. Note! The ad network provides the campaign ID and name per postback. Both campaign ID and campaign name are available in raw data and aggregated SKAN reports.</li></ul> |
| Site ID | <ul><li>Source app displaying your ad.</li><li>Use to analyze the apps most beneficial to you.</li></ul> |
| Geo | <ul><li>Territory or country</li><li>The Geo is derived using data supplied by the ad network or using the device IP address.</li><li>Starting iOS 14.6 the device IP address is masked by an Apple proxy server. Meaning that the geolocation of the Apple server is reflected and not the device itself.</li></ul> |
| Install type | <ul><li>Installs</li><li>Redownloads reported by the app store</li></ul> |
| Adset | Available if the ad network provides this data point |
| Ad | Available if the ad network provides this data point |
| Version | The SKAN version |

</Accordion>

<div id="headline-metrics" />

<Accordion title="Headline metrics">

| Metric | Remarks |
| --- | --- |
| Installs | SKAN does not report installs if the user did not engage with an ad prior to the install. AppsFlyer calculates the organic metrics using AppsFlyer attributed installs (LTV dashboard.)<ul><li>Non-organic: Installs attributed to a media source in the context of a paid app-to-app campaign and reported by SKAN.</li><li>Organic calculated by AppsFlyer includes the following:<ul><li>Installs not attributed by SKAN or for which no postback was received from an ad network.</li><li>App Clips</li></ul></li></ul>Apple Ads (media-source iossearchads\_int) now appears under non-organic SKAN traffic. |
| Touchpoints | Ad networks report impressions and clicks by click or API. |
| Total Revenue | <ul><li>Available when revenue mode is active.</li><li>Displays in USD or in the app-specific local currency as set on the <Anchor target="_blank" href="/marketers/docs/app-settings">app settings page</Anchor>.</li><li>Divided between organic and non-organic revenue.</li><li>Organic revenue is calculated as the revenue of all sources minus non-organic revenue.</li><li>To enable a like-to-like comparison, the duration of the post-install window of organic and non-organic installs is the same.</li><li>Includes <Anchor target="_blank" href="/marketers/docs/skan-modeled-data#null-conversion-values">modeled data</Anchor></li></ul>**Note**: Organic metrics aren't always available. [Learn more](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations). |
| Cost | <ul><li>Cost reported by the ad network. Cost data is reported to AppsFlyer using ROI360/Cost API. Cost displays in USD or in the app-specific local currency as set on the <Anchor target="_blank" href="/marketers/docs/app-settings">app settings page</Anchor>.</li><li>If the campaign name changes cost displays under the most recent campaign name used. (If there are multiple campaign names)</li><li>Cost metrics are only available for the filter Install type=All that includes both installs and redownloads.</li></ul> |
| Click-to-install rate | Click-to-install rate. |
| Adjacent period trend | Trend values in % indicate the change of the current metric relative to the metric of the previous equivalent period. For example, if the current period is May 1-10, the previous period is April 21-30. |

</Accordion>

<div id="charts" />

<Accordion title="Charts">

The charts available depend on the selected measurement type.

| Chart metric | Remarks |
| --- | --- |
| User acquisition trend | Dimensions available:<ul><li>Organic</li><li>Non-organic</li></ul>[![SKAdNetwork_Dashboard_AppsFlyer2_us-en.png](https://files.readme.io/5c46dc05b4df07f3f60ff6015f115b4bc89106a6eb594f43d777af2100fdf460-360010368477.png)](https://files.readme.io/e30781379f0acb50d73e18e6c59ff76f8c91fa4cda6b92064310050555f826a3-360010359738.png) |
| Touch to conversion | Views available:<ul><li>Touchpoint dimensions:<ul><li>Impressions</li><li>Clicks</li></ul></li><li>Click-to-install rate</li></ul>[![SKAdNetwork_Dashboard_AppsFlyer3_us-en.png](https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png)](https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png) |
| Installs per day grouped by advertising hierarchy element | Elements available: Media source, Campaign, Site ID, Adset, Ad,Version [![SKAdNetwork_Dashboard_AppsFlyer4_us-en.png](https://files.readme.io/a9b80aaeb0f34a3054bfb97bb72ff2ab549ff88ae4f6af43bf1c5e1ab604d3d3-360010368537.png)](https://files.readme.io/a9b80aaeb0f34a3054bfb97bb72ff2ab549ff88ae4f6af43bf1c5e1ab604d3d3-360010368537.png) |
| Metric breakdown by advertising hierarchy elements | Elements available: Media source, Campaign, Site ID, Adset, Ad, Version<br /><br />[![SKAdNetwork_Dashboard_AppsFlyer5_us-en.png](https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png)](https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png) |
| Top events | Top events contain both organic and non-organic users. Use the media source filter, at the top of the page, to distinguish between organic and non-organic users or per selected media sources.<br /><br />[![SKAdNetwork_Dashboard_AppsFlyer6_us-en.png](https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png)](https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png) |
| Top countries | [![mceclip1.png](https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png)](https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png)<br /><br />Note: This chart is available to agencies and not to advertisers |
| Postback copy | This chart is available after you configure the app to send iOS 15+ <Anchor target="_blank" href="/marketers/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">postback copies</Anchor> to AppsFlyer. If no chart displays, consider that:<ul><li>We aren't receiving the postbacks from the app or aren't yet receiving them. Verify with your app developer, that the AppsFlyer endpoint has been set in the app and the updated app version is in the App Store.</li><li>No postbacks were received (meaning there are no SKAN installs) for the selected date or you selected a date earlier than January 1, 2022.</li></ul>Notes:<ul><li>All other metrics in the dashboard are calculated using iOS postbacks forwarded by ad networks to AppsFlyer or from data provided directly by SRNs. Expect discrepancies between postback copy metrics and the other metrics.</li><li>The postback copy chart isn't available to agencies.</li></ul>[![PostbackCopy.png](https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png)](https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png)<table><thead><tr><th>Dimension</th><th>Remarks</th></tr></thead><tbody><tr><td>Media source</td><td>The media source attributed to the install.    \* Metrics:   \* **Redownload rate:** Metrics relate to postbacks using SKAdNetwork V2.0+.   \* **Attributed touch-type rate:** The engagement, view, or click, leading to the install. Metrics relate to postbacks using SKAdNetwork V2.2+ \* Note: If the media source ID displays, we currently don't have a name associated with that ID. Ask the media source to update their SKAdNetwork ID in AppsFlyer.</td></tr><tr><td>Source app</td><td>The ad publisher name, in other words, the app name in which the user engaged with your ad.   \* Metric:   \* **Install count**: The number of installs brought by the publisher app. \* Notes:   \* If Apple withholds the source app ID, due to privacy thresholds, the source app displays as \*unknown\*.   \* If the app name can't be found, the app ID displays</td></tr><tr><td>Source app ID</td><td>The ad publisher id, in other words, the app ID in which the user engaged with your ad.   \* Metric:   \* **Install count**: The number of installs brought by the publisher app ID.</td></tr></tbody></table> |
| Dimension | Remarks |
| Media source | The media source attributed to the install.<ul><li>Metrics:<ul><li>**Redownload rate:** Metrics relate to postbacks using SKAdNetwork V2.0+.</li><li>**Attributed touch-type rate:** The engagement, view, or click, leading to the install. Metrics relate to postbacks using SKAdNetwork V2.2+</li></ul></li><li>Note: If the media source ID displays, we currently don't have a name associated with that ID. Ask the media source to update their SKAdNetwork ID in AppsFlyer.</li></ul> |
| Source app | The ad publisher name, in other words, the app name in which the user engaged with your ad.<ul><li>Metric:<ul><li>**Install count**: The number of installs brought by the publisher app.</li></ul></li><li>Notes:<ul><li>If Apple withholds the source app ID, due to privacy thresholds, the source app displays as *unknown*.</li><li>If the app name can't be found, the app ID displays</li></ul></li></ul> |
| Source app ID | The ad publisher id, in other words, the app ID in which the user engaged with your ad.<ul><li>Metric:<ul><li>**Install count**: The number of installs brought by the publisher app ID.</li></ul></li></ul> |

</Accordion>

<div id="metrics" />

<Accordion title="Metrics">

* Select metrics from those available. [Modeled metrics](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) consider the null CV rate.
* Set the primary and secondary groups by dimensions to drill down into performance metrics.

[![SKAdNetwork_Dashboard_AppsFlyer7_us-en.png](https://files.readme.io/434a848c7a33c052c80101788b066f4bdb90ef36423ea140f85c1cc59ace2ebf-360010368617.png)](https://files.readme.io/434a848c7a33c052c80101788b066f4bdb90ef36423ea140f85c1cc59ace2ebf-360010368617.png)

About the metrics table:

* Use the table to compare the performance of campaigns and media sources.
* Initially, the top 20 media sources display, sorted by the number of installs in descending order.
* To sort the table, click on a column header. Click again to reverse the sort order.
* Cost-related metrics (cost, impressions, and clicks) are available if at least 1 install is associated with a given campaign. Note:
  * Campaigns with 0 installs don't display at all.
  * Some ad networks, report cost-related metrics at the adset and ad level, but report the install at the campaign level. In this case, the adset and ad cost-related metrics display with an install metric of 0.
* Attributed touch-type dimension limitation: Cost-related metrics can't be broken down and display as **Unknown**.

Table metrics:

<table><thead><tr><th>Metric</th><th>Formula/remarks</th></tr></thead><tbody><tr><td>Installs</td><td><ul><li>Total installs</li><li>Click-throughs<ul><li>Users brought via click-through attribution</li><li>Available for installs recorded starting December 22, 2021</li></ul></li><li>View-throughs<ul><li>Available for installs recorded starting December 22, 2021</li><li>Applies to ad networks implementing SKAdNetwork V2.2+</li></ul></li></ul><p>This data is derived from the fidelity_type field in the postback</p></td></tr><tr><td>Null conversion value rate</td><td>Postbacks having a null conversion value/Installs \* 100 </td></tr><tr><td>Impressions</td><td> </td></tr><tr><td>Clicks</td><td> </td></tr><tr><td>Click-to-install rate</td><td>Installs/Clicks \* 100</td></tr><tr><td>Converted users</td><td><p>Count of unique users performing a designated measurement event.</p><ul><li>Custom mode: Always af_skad_revenue (if anything else is selected, converted users remains empty)</li><li>SKAN 4 mode: Always af_skad_revenue (if anything else is selected, converted users remains empty)</li><li>Revenue mode: Always af_skad_revenue</li><li>Conversion mode: In-app event selected in the dashboard settings</li><li>Engagement mode: In-app event as set in Conversion Studio<br/><br/> </li></ul><p><strong>Organic</strong> converted users traffic are not shown in the SKAN dashboard</p></td></tr><tr><td>Converted users/Installs</td><td> </td></tr><tr><td>Total revenue</td><td>Revenue, including modeled data of null values. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Learn more</a></td></tr><tr><td>Total revenue (unmodeled)</td><td>Revenue reported via the conversion values. Modeled data not included</td></tr><tr><td>Revenue D1-D2</td><td>Revenue for SKAN window 1 (days 1-2 unless modified), including modeled data of null values. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Learn more</a></td></tr><tr><td>Revenue D1-D2 (unmodeled)</td><td>Revenue received in SKAN window 1 (days 1-2 unless modified). Modeled data not included</td></tr><tr><td>Revenue D3-D7</td><td>Revenue for SKAN window 2 (days 3-7 unless modified)</td></tr><tr><td>Revenue D8-D35</td><td>Revenue for SKAN window 3 (days 8-35 unless modified)</td></tr><tr><td>Cost</td><td><ul><li>Cost reported by the ad network</li><li>If the campaign name changes cost displays under the most recent campaign name used. (If there are multiple campaign names)</li></ul></td></tr><tr><td>ARPU</td><td><ul><li>Average revenue per user, including modeled data of null values. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Learn more</a></li><li>Formula: Revenue ($) (modeled) / Installs</li></ul></td></tr><tr><td>ARPU (unmodeled)</td><td>Average revenue per user, modeled data not included</td></tr><tr><td>ROI</td><td><ul><li>Return on investment, including modeled data of null values. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Learn more</a></li><li>Formula: (Revenue ($) (modeled) - Cost) / Cost \* 100</li></ul></td></tr><tr><td>ROI (unmodeled)</td><td>Return on investment, modeled data not included</td></tr><tr><td>ROAS</td><td><ul><li>Return on ad spend, including modeled data of null values. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Learn more</a></li><li>Formula: (Revenue ($) (modeled) / Cost \* 100</li></ul></td></tr><tr><td>ROAS (unmodeled)</td><td>Return on ad spend, modeled data not included</td></tr><tr><td>eCPI</td><td> </td></tr><tr><td colspan="2"><strong>In-app event metrics</strong></td></tr><tr><td>In-app event name</td><td> </td></tr><tr><td>eCPA</td><td><ul><li>Effective cost per action, including modeled data of null values. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Learn more</a></li><li>Formula: Cost / Unique users performing the events (modeled)</li></ul></td></tr><tr><td>eCPA (unmodeled)</td><td>Effective cost per action, modeled data not included</td></tr><tr><td>Total event count</td><td>Total event occurrences across all windows, including modeled data of null values. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Learn more</a></td></tr><tr><td>Total event count (unmodeled)</td><td>Total event occurrences across all windows, modeled data not included</td></tr><tr><td>Event count D1-D2</td><td>Event occurrences for window 1 (days 1-2 unless modified), including modeled data of null values. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Learn more</a></td></tr><tr><td>Event count D1-D2 (unmodeled)</td><td>Event occurrences for window 1 (days 1-2 unless modified), modeled data not included</td></tr><tr><td>Event count D3-D7</td><td>Event occurrences for window 2 (days 3-7 unless modified).</td></tr><tr><td>Event count D8-D35</td><td>Event occurrences for window 3 (days 8-35 unless modified).</td></tr><tr><td>Event unique users D1-D2</td><td>Number of unique users who performed the event for window 1 (days 1-2)</td></tr><tr><td>Event unique users D1-D2 (unmodeled)</td><td>Number of unique users who performed the event for window 1 (days 1-2 unless modified). Modeled data not included.</td></tr><tr><td>Event unique users D3-D7 (unmodeled)</td><td>Number of unique users who performed the event for window 2 (days 3-7 unless modified). Modeled data not included.</td></tr><tr><td>Event unique users D8-D35 (unmodeled)</td><td>Number of unique users who performed the event for window 3 (days 8-35 unless modified). Modeled data not included.</td></tr></tbody></table>

</Accordion>

<div id="modeled-metrics-and-null-cv" />

<Accordion title="Modeled metrics and null CV">

SKAdNetwork (SKAN) reporting can be limited because:

* SKAN relies on conversion values (CVs) that are limited to 6 bits, resulting in 64 possible values (0-63).
* Apple sometimes withholds the actual CV (and returns data as "null") to preserve user privacy.
* Data is only available from within a measurement window and full lifetime value (LTV) isn't known.

SKAN modeled data solves these issues, providing:

* Modeled conversion values instead of null values.
* Modeled revenue and event occurrences.
* A more complete picture regarding app and campaign LTV performance.

Modeled metrics available include:

* Revenue
* Event count
* eCPA
* ARPU
* ROI
* ROAS

<Anchor target="_blank" href="/marketers/docs/skan-modeled-data">Learn more about modeled SKAN data</Anchor>

</Accordion>

<div id="appsflyer-attribution-vs-skan-attribution" />

<Accordion title="AppsFlyer attribution vs. SKAN attribution">

SKAN metrics differ from those available using the AppsFlyer attribution model. The table that follows enumerates the main causes.

Definitions:

* **Times:** Assume the default activity window of 24 hours (48 hours once you upgrade to SKAN 4).
* **SDK:** AppsFlyer SDK embedded in the app.
* **Rules**: <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model">AppsFlyer attribution model</Anchor>

#### Attribution framework differences

| Concept | SKAN | AppsFlyer |
| --- | --- | --- |
| Attribution methodology supported | Apple SKAN for click- and view-through attribution. Contains traffic of app-to-app campaigns of ad networks and SRNs supporting SKAN. | <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model">**AppsFlyer attribution model**</Anchor> **supports multiple attribution methods and scenarios:**<ul><li>Mobile web</li><li>View-through</li><li>Click-through</li><li>App Clips</li><li>Web attribution</li><li>Apple Search Ads</li><li>Owned media</li><li>SRN traffic (consenting users)</li><li>And more</li></ul> |
| Primary data source | <ul><li>SKAN postbacks</li><li>SDK</li></ul> | SDK and associated solutions.  Example: Server-to-Server events. |
| Data freshness | <Anchor target="_blank" href="/marketers/docs/about-data-freshness-and-timezone-support#skan">SKAN data freshness.</Anchor> | Real-time when the user launches and uses the app. |
| Time zone | UTC | App-specific time zone. |
| Install time | Derived from the iOS postback arrival time. | Reported by SDK. |
| Activity window | User activity during a fixed measurement window, starting with the app open. | Contains LTV data from the install date until the present.<br /><br />Use Cohort to view data limited to cohort day 0 or cohort day 1, or both together to view a comparable measurement period.<br /><br />Consider, cohort day 0 consists of less than 24 hours of activity. For example, a user installing at 18:00 on a given day has 6 hours of activity on cohort day 0. |
| Installs reported by | <ul><li>**SKAN**: Limited to non-organic installs and non-organic redownloads.</li><li>**SDK**: All installs are reported. Only first-time installs are counted for metric purposes. Meaning reattributions are disregarded.</li></ul> | SDK reports all installs categorized using Rules into first-time installs and retargeting reinstalls (re-attributions). |
| Advertising granularity level | Campaign, adset, adset ID, ad, and ad ID. | Full hierarchy: Campaign, campaign ID, adset, additional parameters like channel and partner. |
| Redownloads vs. reinstalls | Redownloads relate to the actions of a given Apple ID user. They are not parallel to re-attributions. | Retargeting (re-engagements re-attributions) reflect in the Retargeting dashboard. They are not parallel to redownloads. |

#### Metric differences

| Metric | SKAN | Traditional attribution |
| --- | --- | --- |
| Non-organic installs | Count of valid iOS postbacks received by AppsFlyer.<br /><br />Consider, AppsFlyer doesn't get the postbacks of ad networks that haven't completed SKAN integration with AppsFlyer.<br /><br />This can lead to undercounting of non-organic installs and increased organic installs. | <ul><li>Reported by SDK.</li><li>Attributed to a media source.</li><li>Counted using Rules.</li></ul> |
| Organic installs | SDK installs minus SKAN installs. | <ul><li>Reported by SDK.</li><li>Not attributed to any media source.</li><li>Counted using Rules.</li></ul> |
| Revenue | **Non-organic**: Revenue reported by SKAN postbacks.<br /><br />**Organic:** Revenue reported by SDK in-app events minus non-organic revenue. **Note**: Organic metrics aren't always available. [Learn more](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations). | <ul><li>Reported by SDK and server-to-server API.</li></ul> |
| Ad revenue | <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">Available</Anchor> | User-level ad revenue is attributed based on IDFV |
| ROI/ROAS | Revenue during the measurement window. | <ul><li>LTV</li><li>Metrics of UA and retargeting campaigns.</li></ul> |

</Accordion>

<div id="faq-skan-discrepancies" />

<Accordion title="FAQ—SKAN discrepancies">

| Reason | Discrepancies—QA |
| --- | --- |
| A | **Q: Why do the conversion numbers in the AppsFlyer dashboard differ to that of the ad network dashboard?**<br /><br />**A**: Reasons for discrepancies<ul><li>**Install date vs. postback arrival date:**<ul><li>AppsFlyer: The install date is derived using a formula that takes into account the iOS postback arrival time, window length, and postback delay time.</li><li>Ad network: Typically use only the iOS postback arrival time as the install date, without adjustment.</li><li>Use the **display by postback arrival date** option in the dashboard to eliminate this difference.</li></ul></li><li>**Postback validation:** AppsFlyer validates the iOS postbacks received and ensures that the Apple signature is valid. The ad network may send invalid postbacks disregarded by AppsFlyer.</li><li>**Missing postbacks**: iOS Postbacks must be sent by the ad network to AppsFlyer. AppsFlyer doesn't get the postback directly from the device. If postbacks are missing, AppsFlyer has no way of knowing this.</li></ul> |
| B | **Q**: **Differences between the** <Anchor target="_blank" href="/marketers/docs/skan-aggregated-performance-report-api">**SKAN performance API**</Anchor> **and dashboard versus the** <Anchor target="_blank" href="/marketers/docs/skan-aggregated-postback-arrival-date-api">**SKAN aggregate postback API?**</Anchor><br /><br />**A**: The postback API date range relates to the date on which AppsFlyer received the postback. The performance API date range relates to the install date derived as described in reason A. |
| C | **Q: Do all ad networks report the Geo?**<br /><br />**A:** No. |
| D | **Q: Why are there differences between the Overview dashboard and the SKAN dashboard.**<br /><br />**A:** See the preceding section for an overview as to reasons for discrepancies. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Modeled event occurrences | <ul><li>Modeled events are based on the formula described in [modeled metrics and null CV](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv).</li><li>The formula is applied per row of data. This may cause discrepancies between the modeled event count for a given media source and the sum of the modeled event count of its campaigns.</li></ul> |
| Postback arrival date | The final date in a date range is limited to the day when the last install was recorded. |
| Organic data | <ul><li>**Organic revenue** is only available for Revenue in either <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio#fixed-modes">fixed</Anchor> or legacy mode.</li><li>**Organic in-app** events are only available for "Conversion" in <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio#fixed-modes">fixed</Anchor> or legacy modes.</li><li>For the **non-legacy modes** (<Anchor target="_blank" href="/marketers/docs/skan-conversion-studio#skan-4">SKAN4</Anchor>, custom encode, and decode modes) organic data is available only for installs.</li><li>Consider using SSOT to view organic data, as SSOT deduplicates SKAN-attributed and AppsFlyer model-attributed events.</li><li>If AppsFlyer attribution data (new installs for both organic and non-organic) minus SKAN attribution data (non-organic installs) equals a negative number, the SKAN dashboard displays 0 under organic installs.</li></ul> |
| Historical data | Earliest conversion data supported: November 1, 2020 |
| Currency | Displays in USD or in the app-specific local currency as set on the <Anchor target="_blank" href="/marketers/docs/app-settings">app settings page</Anchor>. |
| Timezone | For SKAN-reported data, installs and events display using UTC, with the exception of Meta and Google SKAN data, for which the timezone is based on the timezone configured in your Meta and Google accounts, respectively. |
| Filter by SKAN version | For some media partners, **unknown** is displayed. This is because they do not currently provide that field.<ul><li>Google</li><li>Meta<br />Others - you'll see this field as the SKAN dashboard supports the pre-attribution metrics such as cost, clicks, and impressions - and we can not break those metrics down by version, so a new row will have those metrics.</li></ul> |
| Apple Search Ads | Apple Search Ads does not share campaign-level data. Any agency campaigns that require a prefix will not appear in the agency view. |

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide">AppsFlyer SKAN Solution guide</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/about-att-and-skan">What's different—AppsFlyer iOS 14 related updates</Anchor>

<div data-zendesk-anchors="01H81P8JPZM24J0536GKBPNFMJ=dashboard-principles 01H81P8JPZC5K0KZR64P084N4W=skan-dashboard-view-options 01H81P8JPZGSHQVMG27YEJPARH=dashboard-use 01H81P8JPZ93G4EQY343SV2B1Q=dashboard-settings 01H81P8JPZV5F4VCZHR537HREH=filter-options 01H81P8JQ0KRGXWCVT82YW30CS=headline-metrics 01H81P8JQ0ETB0W3SGS56CBCX8=charts 01H81P8JQ0KK1NMRGFR0GBX4EK=metrics 01H81P8JQ0ZKGTRWNW95D015Z7=modeled-metrics-and-null-cv 01H81P8JQ18NGP8Z74D02DMQ7P=appsflyer-attribution-vs-skan-attribution 01H81P8JQ1VTYX3382WDXDMVT3=attribution-framework-differences 01H81P8JQ1M8M9TSHF0C12Z2QE=metric-differences faq%E2%80%94skan-discrepancies=faq-skan-discrepancies 01H81P8JQ157YYNX9C527ES4C8=faq-skan-discrepancies 01H81P8JQ1T3DE29Y14VARKASK=traits-and-limitations h_01HE7SWGPWNWG26CEN40VSTA9J=see-also" />
