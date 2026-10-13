---
title: "SKAdNetwork (SKAN) overview dashboard by AppsFlyer"
excerpt: "The SKAdNetwork (SKAN) dashboard displays campaign metrics reported via iOS SKAN postbacks and additional data points during initial user measurement windows. Modeled metrics which consider null conversions are also available. Data displays using the install or postback arrival date."
x-zendesk:
  id: 360011307357
  url: https://support.appsflyer.com/hc/en-us/articles/360011307357-SKAdNetwork-SKAN-overview-dashboard-by-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Dashboards
  section_id: 6550925337873
  position: 7
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, SKAdNetwork (SKAN)]
  labels: [Advertisers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2020-07-25T21:27:38Z'
  edited_at: '2025-07-07T07:03:34Z'
---
![SKAdHeadling8_us-en.png](https://files.readme.io/72c2eb452741cbd77c5828197f827f238c71c5097b8703528fa180dcafe2364c-360011831017.png)

## Dashboard principles

The dashboard contains SKAN campaign performance data and adheres to the following principles:

- Consider that Apple, due to a [privacy threshold mechanism](https://developer.apple.com/documentation/storekit/skadnetwork), doesn't always populate the conversion value (CV). These are referred to as null CVs. In the case of null CVs, only an install is recorded.
- Metrics are calculated as follows:
  - Non-organic metrics in the dashboard are calculated using SKAN postback data received by AppsFlyer. Some metrics like redownloads, source app ID, and fidelity type metrics require that you configure your app to [send postback copies directly to AppsFlyer](/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15).
  - Organic metrics are calculated as AppsFlyer attribution data minus SKAN non-organic attribution data. 
    > 📘 Note
    >
    > Organic metrics aren't always available. [Learn more](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations).
    - Make sure you filter by **New installs** in the install type field.
  - Some metrics, like revenue and ROAS, have both the original value derived from postbacks and a [modeled value](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) that considers the null CV rate.
- Agency-driven traffic is treated as coming from a transparent agency.
- Data freshness:
  - Daily.
  - Postbacks received on a given day are processed at the end of the day UTC. Data is available by 08:00 UTC of the following day. Meaning postbacks received on Monday are available in the dashboard on Tuesday morning.
  - See [expected dashboard update time.](/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update)

## SKAN dashboard view options

Display data using either the [install date or postback arrival date](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#filter-options).

**To select a date display option**, in AppsFlyer, from the side menu, select **Analyze** > **SKAN Overview.** In the filter bar, select a **Display by** date option.

Additional filters and display options are described in the sections that follow.

## Dashboard use

### Dashboard settings

Dashboard settings are available when your app uses legacy [fixed-mode conversion measurement](/docs/skan-conversion-studio#fixed-modes) to select the conversion event.

**To select the conversion event**:

1. In the upper-right side of the dashboard, click **Dashboard settings**.
2. Select a conversion event.
3. Click apply.

Conversion metrics are calculated using this event.

> 📘 Note!
>
1. This setting relates to the display in the dashboard and doesn't affect the CV setting in the app.

### Filter options

Use filters to refine the information displayed.

| **Filter** | **Remarks** |
| --- | --- |
| Display by | - **Install date**: Is derived from the postback arrival time as follows:  - If the SKAN postbacks are SKAN V4, the install date formula is: Install date = postback arrival time - [accumulated window length] - [average postback delay].<br />    - Postback 1: install date = postback arrival time - 48h - 36h<br />    - Postback 2: install date = postback arrival time - 168h - 84h<br />    - Postback 3: install date = postback arrival time - 840h - 84h<br />  - If the SKAN postbacks are SKAN V3 or earlier, the install date formula is: Install date = postback arrival time - 36 hours - [average last-active range].<br />    - The default [average last-active range] is 12 hours.<br />    - For a conversion value of 0, the average last-active range is set to 0.<br />- **Postback arrival date**:  - The date the postback was received by AppsFlyer.<br />  - When you compare metrics in the AppsFlyer SKAN dashboard to those provided by ad networks, consider that ad networks typically make data available using the postback arrival date.<br />  - Organic metrics aren't available when selecting this option.<br />  - In the case of Google Ads, the arrival and install dates don't differ. |
| Date range | - The attributed install date. This date is derived using the postback arrival time.<br />- If there are large numbers of installs, the inaccuracy due to timing issues is insignificant.<br />- Installs include redownloads.<br />- The date range is limited to 90 days. |
| Media source | - The ad network attributed with the install<br />- Agency-driven traffic: The actual media source displays irrespective of the agency transparency status. Consequently, you may see media sources that you aren't familiar with. |
| Campaign | - Campaign name and ID as set by the ad network.<br />- AppsFlyer translates the postback campaign ID to that of the ad network.<br />- If a given campaign ID has multiple campaign names associated with it, then all names display in the dashboard. Note! The ad network provides the campaign ID and name per postback. Both campaign ID and campaign name are available in raw data and aggregated SKAN reports. |
| Site ID | - Source app displaying your ad.<br />- Use to analyze the apps most beneficial to you. |
| Geo | - Territory or country<br />- The Geo is derived using data supplied by the ad network or using the device IP address.<br />- Starting iOS 14.6 the device IP address is masked by an Apple proxy server. Meaning that the geolocation of the Apple server is reflected and not the device itself. |
| Install type | - Installs<br />- Redownloads reported by the app store |
| Adset | Available if the ad network provides this data point |
| Ad | Available if the ad network provides this data point |
| Version | The SKAN version |

### Headline metrics

| Metric | Remarks |
| --- | --- |
| Installs | SKAN does not report installs if the user did not engage with an ad prior to the install. AppsFlyer calculates the organic metrics using AppsFlyer attributed installs (LTV dashboard.) <br />- Non-organic: Installs attributed to a media source in the context of a paid app-to-app campaign and reported by SKAN.<br />- Organic calculated by AppsFlyer includes the following:<br />  - Installs not attributed by SKAN or for which no postback was received from an ad network.<br />  - App Clips<br /><br />Apple Ads (media-source iossearchads\_int) now appears under non-organic SKAN traffic. |
| Touchpoints | Ad networks report impressions and clicks by click or API. |
| Total Revenue | - Available when revenue mode is active.<br />- Displays in USD or in the app-specific local currency as set on the [app settings page](/docs/app-settings).<br />- Divided between organic and non-organic revenue.<br />- Organic revenue is calculated as the revenue of all sources minus non-organic revenue.<br />- To enable a like-to-like comparison, the duration of the post-install window of organic and non-organic installs is the same.<br />- Includes [modeled data](/docs/skan-modeled-data#null-conversion-values)<br />**Note**: Organic metrics aren't always available. [Learn more](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations). |
| Cost | - Cost reported by the ad network. Cost data is reported to AppsFlyer using ROI360/Cost API. Cost displays in USD or in the app-specific local currency as set on the [app settings page](/docs/app-settings).<br />- If the campaign name changes cost displays under the most recent campaign name used. (If there are multiple campaign names)<br />- Cost metrics are only available for the filter Install type=All that includes both installs and redownloads. |
| Click-to-install rate | Click-to-install rate. |
| Adjacent period trend | Trend values in % indicate the change of the current metric relative to the metric of the previous equivalent period. For example, if the current period is May 1-10, the previous period is April 21-30. |

### Charts

The charts available depend on the selected measurement type.

| Chart metric | Remarks |
| --- | --- |
| User acquisition trend | Dimensions available:<br />- Organic<br />- Non-organic<br />[![SKAdNetwork_Dashboard_AppsFlyer2_us-en.png](https://files.readme.io/462439e87f6cd29d4ddc20698cc5ff37901d3619eefecce1fb03d6f58e17ee39-SKAdNetwork_Dashboard_AppsFlyer2_us-en.png)](https://files.readme.io/e30781379f0acb50d73e18e6c59ff76f8c91fa4cda6b92064310050555f826a3-360010359738.png) |
| Touch to conversion | Views available:<br />- Touchpoint dimensions:<br />  - Impressions<br />  - Clicks<br />- Click-to-install rate<br />![SKAdNetwork_Dashboard_AppsFlyer3_us-en.png](https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png) |
| Installs per day grouped by advertising hierarchy element | Elements available: Media source, Campaign, Site ID, Adset, Ad,Version ![SKAdNetwork_Dashboard_AppsFlyer4_us-en.png](https://files.readme.io/a9b80aaeb0f34a3054bfb97bb72ff2ab549ff88ae4f6af43bf1c5e1ab604d3d3-360010368537.png) |
| Metric breakdown by advertising hierarchy elements | Elements available: Media source, Campaign, Site ID, Adset, Ad, Version<br />![SKAdNetwork_Dashboard_AppsFlyer5_us-en.png](https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png) |
| Top events | Top events contain both organic and non-organic users. Use the media source filter, at the top of the page, to distinguish between organic and non-organic users or per selected media sources. <br />![SKAdNetwork_Dashboard_AppsFlyer6_us-en.png](https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png) |
| Top countries | ![mceclip1.png](https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png)<br />Note: This chart is available to agencies and not to advertisers |
| Postback copy | This chart is available after you configure the app to send iOS 15+ [postback copies](/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15) to AppsFlyer. If no chart displays, consider that:<br /><br />- We aren't receiving the postbacks from the app or aren't yet receiving them. Verify with your app developer, that the AppsFlyer endpoint has been set in the app and the updated app version is in the App Store.<br />- No postbacks were received (meaning there are no SKAN installs) for the selected date or you selected a date earlier than January 1, 2022.<br /><br />Notes:<br /><br />- All other metrics in the dashboard are calculated using iOS postbacks forwarded by ad networks to AppsFlyer or from data provided directly by SRNs. Expect discrepancies between postback copy metrics and the other metrics.<br />- The postback copy chart isn't available to agencies.<br /><br />![PostbackCopy.png](https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png) |

| Dimension | Remarks |
| --- | --- |
| Media source | The media source attributed to the install. <br />- Metrics:  - **Redownload rate:** Metrics relate to postbacks using SKAdNetwork V2.0+.<br />  - **Attributed touch-type rate:** The engagement, view, or click, leading to the install. Metrics relate to postbacks using SKAdNetwork V2.2+<br />- Note: If the media source ID displays, we currently don't have a name associated with that ID. Ask the media source to update their SKAdNetwork ID in AppsFlyer. |
| Source app | The ad publisher name, in other words, the app name in which the user engaged with your ad.<br />- Metric:  - **Install count**: The number of installs brought by the publisher app.<br />- Notes:<br />  - If Apple withholds the source app ID, due to privacy thresholds, the source app displays as _unknown_.<br />  - If the app name can't be found, the app ID displays |
| Source app ID | The ad publisher id, in other words, the app ID in which the user engaged with your ad.<br />- Metric:  - **Install count**: The number of installs brought by the publisher app ID. |

### Metrics

- Select metrics from those available. [Modeled metrics](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) consider the null CV rate.
- Set the primary and secondary groups by dimensions to drill down into performance metrics.

![SKAdNetwork_Dashboard_AppsFlyer7_us-en.png](https://files.readme.io/434a848c7a33c052c80101788b066f4bdb90ef36423ea140f85c1cc59ace2ebf-360010368617.png)

About the metrics table:

- Use the table to compare the performance of campaigns and media sources.
- Initially, the top 20 media sources display, sorted by the number of installs in descending order.
- To sort the table, click on a column header. Click again to reverse the sort order.
- Cost-related metrics (cost, impressions, and clicks) are available if at least 1 install is associated with a given campaign. Note:
  - Campaigns with 0 installs don't display at all.
  - Some ad networks, report cost-related metrics at the adset and ad level, but report the install at the campaign level. In this case, the adset and ad cost-related metrics display with an install metric of 0.
- Attributed touch-type dimension limitation: Cost-related metrics can't be broken down and display as **Unknown**.

Table metrics:

| Metric | Formula/remarks |
| --- | --- |
| Installs | - Total installs<br />- Click-throughs<br />  - Users brought via click-through attribution<br />  - Available for installs recorded starting December 22, 2021<br />- View-throughs<br />  - Available for installs recorded starting December 22, 2021<br />  - Applies to ad networks implementing SKAdNetwork V2.2+<br />This data is derived from the fidelity\_type field in the postback |
| Null conversion value rate | Postbacks having a null conversion value/Installs \* 100 |
| Impressions |  |
| Clicks |  |
| Click-to-install rate | Installs/Clicks \* 100 |
| Converted users | Count of unique users performing a designated measurement event.<br />- Custom mode: Always af\_skad\_revenue (if anything else is selected, converted users remains empty)<br />- SKAN 4 mode: Always af\_skad\_revenue (if anything else is selected, converted users remains empty)<br />- Revenue mode: Always af\_skad\_revenue<br />- Conversion mode: In-app event selected in the dashboard settings<br />- Engagement mode: In-app event as set in Conversion Studio<br /><br />**Organic** converted users traffic are not shown in the SKAN dashboard |
| Converted users/Installs |  |
| Total revenue | Revenue, including modeled data of null values. [Learn more](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) |
| Total revenue (unmodeled) | Revenue reported via the conversion values. Modeled data not included |
| Revenue D1-D2 | Revenue for SKAN window 1 (days 1-2 unless modified), including modeled data of null values. [Learn more](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) |
| Revenue D1-D2 (unmodeled) | Revenue received in SKAN window 1 (days 1-2 unless modified). Modeled data not included |
| Revenue D3-D7 | Revenue for SKAN window 2 (days 3-7 unless modified) |
| Revenue D8-D35 | Revenue for SKAN window 3 (days 8-35 unless modified) |
| Cost | - Cost reported by the ad network<br />- If the campaign name changes cost displays under the most recent campaign name used. (If there are multiple campaign names) |
| ARPU | - Average revenue per user, including modeled data of null values. [Learn more](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv)<br />- Formula: Revenue ($) (modeled) / Installs |
| ARPU (unmodeled) | Average revenue per user, modeled data not included |
| ROI | - Return on investment, including modeled data of null values. [Learn more](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv)<br />- Formula: (Revenue ($) (modeled) - Cost) / Cost \* 100 |
| ROI (unmodeled) | Return on investment, modeled data not included |
| ROAS | - Return on ad spend, including modeled data of null values. [Learn more](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv)<br />- Formula: (Revenue ($) (modeled) / Cost \* 100 |
| ROAS (unmodeled) | Return on ad spend, modeled data not included |
| eCPI |  |
| **In-app event metrics** | |
| In-app event name |  |
| eCPA | - Effective cost per action, including modeled data of null values. [Learn more](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv)<br />- Formula: Cost / Unique users performing the events (modeled) |
| eCPA (unmodeled) | Effective cost per action, modeled data not included |
| Total event count | Total event occurrences across all windows, including modeled data of null values. [Learn more](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) |
| Total event count (unmodeled) | Total event occurrences across all windows, modeled data not included |
| Event count D1-D2 | Event occurrences for window 1 (days 1-2 unless modified), including modeled data of null values. [Learn more](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) |
| Event count D1-D2 (unmodeled) | Event occurrences for window 1 (days 1-2 unless modified), modeled data not included |
| Event count D3-D7 | Event occurrences for window 2 (days 3-7 unless modified). |
| Event count D8-D35 | Event occurrences for window 3 (days 8-35 unless modified). |
| Event unique users D1-D2 | Number of unique users who performed the event for window 1 (days 1-2) |
| Event unique users D1-D2 (unmodeled) | Number of unique users who performed the event for window 1 (days 1-2 unless modified). Modeled data not included. |
| Event unique users D3-D7 (unmodeled) | Number of unique users who performed the event for window 2 (days 3-7 unless modified). Modeled data not included. |
| Event unique users D8-D35 (unmodeled) | Number of unique users who performed the event for window 3 (days 8-35 unless modified). Modeled data not included. |

### Modeled metrics and null CV

SKAdNetwork (SKAN) reporting can be limited because:

- SKAN relies on conversion values (CVs) that are limited to 6 bits, resulting in 64 possible values (0-63).
- Apple sometimes withholds the actual CV (and returns data as "null") to preserve user privacy.
- Data is only available from within a measurement window and full lifetime value (LTV) isn't known.

SKAN modeled data solves these issues, providing:

- Modeled conversion values instead of null values.
- Modeled revenue and event occurrences.
- A more complete picture regarding app and campaign LTV performance.

Modeled metrics available include:

- Revenue
- Event count
- eCPA
- ARPU
- ROI
- ROAS

[Learn more about modeled SKAN data](/docs/skan-modeled-data)

### AppsFlyer attribution vs. SKAN attribution

SKAN metrics differ from those available using the AppsFlyer attribution model. The table that follows enumerates the main causes.

Definitions:

- **Times:** Assume the default activity window of 24 hours (48 hours once you upgrade to SKAN 4).
- **SDK:** AppsFlyer SDK embedded in the app.
- **Rules**: [AppsFlyer attribution model](/docs/appsflyer-attribution-model)

#### Attribution framework differences

| Concept | SKAN | AppsFlyer |
| --- | --- | --- |
| Attribution methodology supported | Apple SKAN for click- and view-through attribution. Contains traffic of app-to-app campaigns of ad networks and SRNs supporting SKAN. | [**AppsFlyer attribution model**](/docs/appsflyer-attribution-model) **supports multiple attribution methods and scenarios:**<br />- Mobile web<br />- View-through<br />- Click-through<br />- App Clips<br />- Web attribution<br />- Apple Search Ads<br />- Owned media<br />- SRN traffic (consenting users)<br />- And more |
| Primary data source | - SKAN postbacks<br />- SDK | SDK and associated solutions.  Example: Server-to-Server events. |
| Data freshness | [SKAN data freshness.](/docs/about-data-freshness-and-timezone-support#skan) | Real-time when the user launches and uses the app. |
| Time zone | UTC | App-specific time zone. |
| Install time | Derived from the iOS postback arrival time. | Reported by SDK. |
| Activity window | User activity during a fixed measurement window, starting with the app open. | Contains LTV data from the install date until the present.<br />Use Cohort to view data limited to cohort day 0 or cohort day 1, or both together to view a comparable measurement period.<br />Consider, cohort day 0 consists of less than 24 hours of activity. For example, a user installing at 18:00 on a given day has 6 hours of activity on cohort day 0. |
| Installs reported by | - **SKAN**: Limited to non-organic installs and non-organic redownloads.<br />- **SDK**: All installs are reported. Only first-time installs are counted for metric purposes. Meaning reattributions are disregarded. | SDK reports all installs categorized using Rules into first-time installs and retargeting reinstalls (re-attributions). |
| Advertising granularity level | Campaign, adset, adset ID, ad, and ad ID. | Full hierarchy: Campaign, campaign ID, adset, additional parameters like channel and partner. |
| Redownloads vs. reinstalls | Redownloads relate to the actions of a given Apple ID user. They are not parallel to re-attributions. | Retargeting (re-engagements re-attributions) reflect in the Retargeting dashboard. They are not parallel to redownloads. |

#### Metric differences

| Metric | SKAN | Traditional attribution |
| --- | --- | --- |
| Non-organic installs | Count of valid iOS postbacks received by AppsFlyer.<br />Consider, AppsFlyer doesn't get the postbacks of ad networks that haven't completed SKAN integration with AppsFlyer.<br />This can lead to undercounting of non-organic installs and increased organic installs. | - Reported by SDK.<br />- Attributed to a media source.<br />- Counted using Rules. |
| Organic installs | SDK installs minus SKAN installs. | - Reported by SDK.<br />- Not attributed to any media source.<br />- Counted using Rules. |
| Revenue | **Non-organic**: Revenue reported by SKAN postbacks.<br />**Organic:** Revenue reported by SDK in-app events minus non-organic revenue. **Note**: Organic metrics aren't always available. [Learn more](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations). | - Reported by SDK and server-to-server API. |
| Ad revenue | [Available](/docs/skadnetwork-skan-solution-guide#recording-ad-revenue) | User-level ad revenue is attributed based on IDFV |
| ROI/ROAS | Revenue during the measurement window. | - LTV<br />- Metrics of UA and retargeting campaigns. |

### FAQ—SKAN discrepancies

| Reason | Discrepancies—Q&A |
| --- | --- |
| A | **Q: Why do the conversion numbers in the AppsFlyer dashboard differ to that of the ad network dashboard?**<br />**A**: Reasons for discrepancies<br />- **Install date vs. postback arrival date:**  - AppsFlyer **:** The install date is derived using a formula that takes into account the iOS postback arrival time, window length, and postback delay time.<br />  - Ad network **:** Typically use only the iOS postback arrival time as the install date, without adjustment.<br />  - Use the **display by postback arrival date** option in the dashboard to eliminate this difference.<br />- **Postback validation:** AppsFlyer validates the iOS postbacks received and ensures that the Apple signature is valid. The ad network may send invalid postbacks disregarded by AppsFlyer.<br />- **Missing postbacks**: iOS Postbacks must be sent by the ad network to AppsFlyer. AppsFlyer doesn't get the postback directly from the device. If postbacks are missing, AppsFlyer has no way of knowing this. |
| B | **Q**: **Differences between the** [**SKAN performance API**](/docs/skan-aggregated-performance-report-api) **and dashboard versus the** [**SKAN aggregate postback API?**](/docs/skan-aggregated-postback-arrival-date-api)<br />**A**: The postback API date range relates to the date on which AppsFlyer received the postback. The performance API date range relates to the install date derived as described in reason A. |
| C | **Q: Do all ad networks report the Geo?**<br />**A:** No. |
| D | **Q: Why are there differences between the Overview dashboard and the SKAN dashboard.**<br />**A:** See the preceding section for an overview as to reasons for discrepancies. |

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Modeled event occurrences | - Modeled events are based on the formula described in [modeled metrics and null CV](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv).<br />- The formula is applied per row of data. This may cause discrepancies between the modeled event count for a given media source and the sum of the modeled event count of its campaigns. |
| Postback arrival date | The final date in a date range is limited to the day when the last install was recorded. |
| Organic data | - **Organic revenue** is only available for Revenue in either [fixed](/docs/skan-conversion-studio#fixed-modes) or legacy mode.<br />- **Organic in-app** events are only available for "Conversion" in [fixed](/docs/skan-conversion-studio#fixed-modes) or legacy modes.<br />- For the **non-legacy modes** ( [SKAN4](/docs/skan-conversion-studio#skan-4), custom encode, and decode modes) organic data is available only for installs.<br />- Consider using SSOT to view organic data, as SSOT deduplicates SKAN-attributed and AppsFlyer model-attributed events.<br />- If AppsFlyer attribution data (new installs for both organic and non-organic) minus SKAN attribution data (non-organic installs) equals a negative number, the SKAN dashboard displays 0 under organic installs. |
| Historical data | Earliest conversion data supported: November 1, 2020 |
| Currency | Displays in USD or in the app-specific local currency as set on the [app settings page](/docs/app-settings). |
| Timezone | For SKAN-reported data, installs and events display using UTC, with the exception of Meta and Google SKAN data, for which the timezone is based on the timezone configured in your Meta and Google accounts, respectively. |
| Filter by SKAN version | For some media partners, **unknown** is displayed. This is because they do not currently provide that field.<br />- Google<br />- Meta<br /><br />Others - you'll see this field as the SKAN dashboard supports the pre-attribution metrics such as cost, clicks, and impressions - and we can not break those metrics down by version, so a new row will have those metrics. |
| Apple Search Ads | Apple Search Ads does not share campaign-level data. Any agency campaigns that require a prefix will not appear in the agency view. |

### See also

<Cards>
  <Card title="AppsFlyer SKAN Solution guide" href="/docs/skadnetwork-skan-solution-guide" icon="fa-solid fa-lock">
    Learn how to configure and use AppsFlyer's SKAdNetwork solution.
  </Card>
  <Card title="What's different—AppsFlyer iOS 14 related updates" href="/docs/about-att-and-skan" icon="fa-solid fa-lock">
    Understand the changes introduced with iOS 14 and how they affect attribution.
  </Card>
</Cards>