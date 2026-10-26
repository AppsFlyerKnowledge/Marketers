---
title: Single Source of Truth (SSOT) guide for iOS attribution
metadata:
  keywords:
    - iOS
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
  created_at: '2021-11-11T09:28:42Z'
  edited_at: '2026-06-11T08:37:47Z'
  id: 4410634145425
  locale: en-us
  section: SKAN solution
  section_id: 6552135379985
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4410634145425-Single-Source-of-Truth-SSOT-guide-for-iOS-attribution
---
> **At a glance**: In the context of the iOS 14+ environment, AppsFlyer brings together data from multiple attribution match methods like IDFA, IDFV, SKAN, Apple Ads, and so on, and gives a complete picture of app campaign performance. No attribution method provides the full app performance picture. The challenge is to count a given user once because that same user can be attributed by two methods. The AppsFlyer Single Source of Truth (SSOT) mechanism does just that. SSOT reports and metrics are true and accurate and count the same user only once.

<Embed title="Single Source of Truth (SSOT) guide for iOS attribution" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/545isomgo1" providerUrl="https://fast.wistia.com" />

## About Single Source of Truth—True iOS performance data

Starting iOS 14, AppsFlyer attributes iOS users using data from multiple data streams, including SKAdNetwork, ATT consenting users, probabilistic modeling, incrementality-based insights, and dedicated APIs for Apple Ads. The absence of IDFA makes it nearly impossible to tie the attribution methods together without including duplicate data.

The SSOT mechanism eliminates duplicate install data and corrects the attribution of misattributed users. In other words, users attributed as organic who should have been attributed to a non-organic media source. As a result, the number of installs attributed to a campaign is corrected and the associated cost- and revenue-related metrics, like eCPI, ROI, and ROAS, are also calculated correctly.

Simply put, the SSOT mechanism flags SKAN installs which are also attributed using another match type. The flag is considered in calculating aggregated metrics to avoid counting the same user twice. Similarly, you use the flag when processing SKAN raw data.

To include the SSOT flag in your data, you must turn on SSOT in the Conversion Studio.

<div id="turn-on-single-source-of-truth" />

<Accordion title="Turn on Single Source of Truth">

![SSOTControl.png](https://files.readme.io/fd99117e9278ebda3b1f0cc137afb266643e5e45325345ec51aeb58c16d4f13c-31247514683153.png)

**To turn on SSOT:**

1. Before you begin, consider the AppsFlyer <Anchor target="_blank" href="https://content.appsflyer.com/ios-hub/billing/">Single Source of Truth billing</Anchor> policy.
2. In AppsFlyer, go to **Settings** > **SKAN Conversion Studio**.
3. Select **Custom** mode.
4. Turn on **Single Source of Truth.**
5. Complete the settings as needed.

See <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>

</Accordion>

## Overview dashboard Single Source of Truth view

![SSOTisNowOn.png](https://files.readme.io/8e21fd0c64bb85fb94af752eb037472726d68cd55bf028dc5306b0acb398d199-31247490958225.png)

The Single Source of Truth view available via the Overview dashboard provides a complete picture of non-organic performance metrics. In the view:

* Install metrics are true.
* Cost- and revenue-related metrics, that depend on the install metric, including eCPI, ARPU, and ROAS, are calculated correctly.
* Organic metrics adjusted after accounting for misattributed installs.

This section highlights the differences and unique features of the SSOT view. It assumes that you are familiar with the Overview dashboard.

<div id="turn-on-single-source-of-truth-view" />

<Accordion title="Turn on Single Source of Truth view">

Data in the SSOT view is available 3-5 days after you enable Single Source of Truth in the Conversion Studio.

**To enable Single Source of Truth view**:

1. Before you begin, verify that in the Conversion Studio <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio#single-source-of-truth">Single Source of Truth</Anchor> is turned on.
2. In AppsFlyer, go to **Dashboard** > **Overview.**   
   <Image alt="SelectSavedReport.png" src="https://files.readme.io/863a9c66c37e031a1f1b2a7fb3e0c68eb9c29405283214e68a432357c35524dd-31247514684177.png" width="243px" />
3. Click ▼.
4. Select **Lite overview**.  
   The Single Source of Truth switch displays.  
   <Image alt="SSOTviewon.png" src="https://files.readme.io/7b0a664f0882dad46e7239b5363592717358a79d920377dde13aa9c5dfbe84c3-31247514684433.png" width="246px" />
5. Turn on Single Source of Truth.
6. One of the following occurs:
   * Dashboard metrics and charts display.  
     The sections that follow describe the data available. See the sections that follow about the data that displays.  
     Save the SSOT view as a new report. To do so:  
     1. Click ▼.
     2. Click **+ Save new report.**
     3. Enter a report name.
     4. Click **Save**.
   * Data doesn't display. Consider that it can take 3-5 days after turning SSOT on until the data displays. Wait for this period to elapse and visit the dashboard again.

Turn off the SSOT switch at any time to see regular data with the dimensions not available in SSOT view.  Doing so enables you to take a deep dive.

</Accordion>

<div id="ssot-view-considerations" />

<Accordion title="SSOT view considerations">

In the SSOT view:

* **Null conversion values (CV)**: Modeled. Advanced machine learning is used to model a null value as attributed by either AppsFlyer or SKAN using the [af\_attribution flag](/docs/single-source-of-truth-ssot-guide-for-ios-attribution#attribution-flag-field). If attributed to SKAN, all post-install SKAN measurements are included in the SSOT dashboard. <Anchor target="_blank" href="/marketers/docs/skan-modeled-data">Learn more</Anchor>
* **Redownloads**: Included in the installs metric. There is no segregation of installs vs. redownloads.
* **Timezone**: AppsFlyer-reported installs and events display in UTC or in the app-specific local timezone as set on the <Anchor target="_blank" href="/marketers/docs/app-settings">app settings page</Anchor>. For SKAN-reported data, installs and events display using UTC, with the exception of Meta and Google SKAN data, for which the timezone is based on the timezone configured in your Meta and Google accounts, respectively.
* **Currency**: Displays in USD or in the app-specific local currency as set on the <Anchor target="_blank" href="/marketers/docs/app-settings">app settings page</Anchor>.
* **Revenue metrics (D2, D7):** Includes modeled data to account for incomplete or missing SKAN postbacks (Null conversion values). Longer cohorts (D14, D21, D30) are exported via the SSOT Data Locker report

#### Filter considerations

Consider the impact of the filters on data display and metrics as described in the tables that follow.

| Filter | Consideration |
| --- | --- |
| Single Source of Truth | To view Single Source of Truth metrics, verify that the control is on. |
| View type | <ul><li>**User Acquisition:** The preferred view for SSOT data.</li><li>**Retargeting**: SKAN doesn't support retargeting.</li><li>**Unified**: Install campaigns contain SSOT data. Retargeting campaigns aren't affected by SSOT.</li></ul> |
| Dates | <ul><li>[Best practice] Select a range long enough to include your desired cohort (e.g., 31 days for D30 revenue), that doesn't include the most recent 3 days to obtain accurate results.</li><li>The earliest date available is usually 3 days after you turned SSOT on. AppsFlyer determines this date.</li><li>Example optimum date selection:<ul><li>If the current date is February 10 and you turned SSOT on  January 29. You can select February 1-7.</li></ul></li><li>Some data (such as revenue) may only be available 8 days after turning on SSOT.</li><li>Google SKAN installs can be reported with a delay of up to 45 days.</li></ul> |
| Campaign filters | Campaign hierarchy filters available:<ul><li>Media source</li><li>Campaign</li></ul> |
| Headline KPIs | The headline KPIs available in the SSOT dashboard let you see:<ul><li>User acquisition: Both non-organic and organic</li><li>SKAN duplicates</li><li>Retargeting: Re-engagements and re-attributions</li><li>Cost</li><li>eCPI</li></ul>For each KPI, there is a percentage value. This value shows how the presented KPI is in relation to the parallel date range before it. For example, this week compared to last week, or any days selected in the date range compared to the same number of days that came before: For example, if it shows an X% increase in installs, it means the previous parallel date range had X% fewer install. |
| Charts | **Dimensions available:**<ul><li>Attributing method:<ul><li>Classic attribution: Installs matched by more than one method including SKAN. In the dashboard, the SKAN record is disregarded to avoid double-counting the same install. In SKAN raw data,  af\_attribution\_flag of the install is set to true.</li><li>SKAN attribution: Installs matched only by SKAN and by no other method. In SKAN raw data, af\_attribution\_flag of the install is set to false.</li></ul></li><li>Attribution type</li><li>Attributed touch type</li><li>Campaign</li><li>Campaign ID</li><li>Media source</li><li>Source</li><li>App ID (for some charts)</li><li>Geo (SKAN geos are <Anchor target="_blank" href="/marketers/docs/skan-modeled-data#geo">modeled</Anchor>)</li><li>In-app event name (meaning the name of a specific in-app event as configured in SKAN Conversion Studio).</li></ul>**Metrics:**<br /><br />As described in the metrics sections. |
| Table | **Groupings:**<ul><li>[Default] The table is grouped by Media source and campaign.</li><li>Grouping options include: Media source, attribution type, attribution method, campaign, campaign ID, Attributed touch type, date, source, geo, and combinations thereof. **Note**: SKAN geos are <Anchor target="_blank" href="/marketers/docs/skan-modeled-data#geo">modeled</Anchor>.</li><li>If you select a grouping with dimensions that only apply to non-organic traffic, the table displays N/A for the organic media source.</li></ul>**Metrics:**<br /><br />As described in the metrics sections. |

</Accordion>

<div id="metrics" />

<Accordion title="Metrics">

Metrics available in the SSOT dashboard:

| Metric | Description and considerations |
| --- | --- |
| Groupings | <ul><li>[Default] The table is grouped by Media source and campaign.</li><li>Grouping options include: Media source, attribution type, attribution method, campaign, campaign ID, Attributed touch type, date, source, and combinations thereof.</li><li>If you select a grouping with dimensions that only apply to non-organic traffic, the table displays N/A for the organic media source.</li></ul> |
| **SSOT attributions** | **Headline breakdown of SSOT installs, reattributions, and re-engagements during the selected dates.**<ul><li>**Non-organic: The campaign that brings the user. The SSOT mechanism ensures that the same install is counted only once.**</li><li>**Organic metrics.**</li></ul> |
| Total | Number of installs, re-attributions, and re-engagements. |
| Installs | The number of unique users who install the app. Calculated as installs attributed by AppsFlyer in the context of UA campaigns plus the number of new installs and re-downloads reported by SKAN after removing duplicates. |
| Re-attributions | Retargeting metrics are available in the Unified and Retargeting view types. Consider that SKAN doesn't support retargeting. |
| Re-engagements | Retargeting metrics are available in the Unified and Retargeting view types. Consider that SKAN doesn't support retargeting. |
| **Other metrics** | **Various other metrics relating to SSOT and advertising performance** |
| SKAN duplicates | The number of SKAN installs with af\_attribution\_flag=true |
| Clicks | Clicks and impressions data reported by ad networks via API. The SSOT mechanism doesn't affect touchpoint metrics. |
| Impressions | Clicks and impressions data reported by ad networks via API. The SSOT mechanism doesn't affect touchpoint metrics. |
| Conversion rate | Click-to-install |
| Cost ($) | <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview">Campaign cost</Anchor> data reported by ad networks via API. Data displays for campaigns with at least one install. The SSOT mechanism doesn't affect the total cost reported. It affects only metrics calculated using install numbers. |
| AVG eCPI ($) | Effective cost per install metric is calculated using SSOT view install metrics. It excludes organic installs. |
| CPM | Cost per mille (1000 impressions). Formula: (Cost / Impressions) * 1000 |
| CPC | Cost per click. Formula: Cost / Clicks |
| Click-throughs | Number of attributions occurring after a user clicks on an ad (CTA) |
| CTR | Click-through rate. Formula: Clicks / Impressions |
| View-throughs | <span id="simple-tabpanel-2"></span>Number of attributions occurring after a user views an ad (VTA) |
| Revenue (D2) | <ul><li>Includes modeled data to account for incomplete or missing SKAN postbacks (Null conversion values)</li></ul>SKAN and Classic revenue (including ad revenue) for the first SKAN measurement window (D2):<ul><li>**SKAN revenue:** Revenue for SKAN installs (where af\_attribution\_flag=false/null). Based on conversion value settings for <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio#revenue-component">revenue in Conversion Studio</Anchor>, and the measurement window time frame.</li><li>**Classic revenue:** Revenue generated by app users after an install attributed by Classic attribution method and within the SKAN measurement window.</li><li>For those using SKAN 4 in Conversion Studio, this is data for 2 days post-install. For those using SKAN 3 in Conversion Studio, data is based on the defined SKAN activity window, whether that's more or less than 2 days.</li><li>**Example**:<ul><li>Activity window is 24h.</li><li>Revenue events occur on the day after the install (Day X+1), but within the 24h activity window.<ul><li>For both SKAN and AF-reported revenue, revenue is counted, as it occurred within the 24h window (even though it was on a different day than the install).</li></ul></li></ul></li></ul>**Tip**: To improve SKAN revenue accuracy:<ul><li>Follow the <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">SKAN ad revenue instructions</Anchor>.</li><li>Use Revenue recommendations.</li></ul> |
| Revenue D7 | <ul><li>Includes modeled data to account for incomplete or missing SKAN postbacks (Null conversion values)</li><li>Includes modeled data, beyond the SKAN measurement window, up to 7 days post-install. <Anchor target="_blank" href="/marketers/docs/skan-modeled-data#revenue-ltv">Learn more</Anchor></li><li>Requires revenue D2 data for modeling.</li></ul> |
| ARPU D2 | Average Revenue per User.<br /><br />Formula: Revenue/Unique Users<br /><br />For those using SKAN 4 in Conversion Studio, this is data for 2 days post-install. For those using SKAN 3 in Conversion Studio, data is based on the defined SKAN activity window, whether that's more or less than 2 days. |
| ARPU D7 | Includes modeled data, beyond the SKAN measurement window, up to 7 days post-install. <Anchor target="_blank" href="/marketers/docs/skan-modeled-data#revenue-ltv">Learn more</Anchor> |
| ROAS D2 | Return On Ad Spend (%).<br /><br />Formula: Revenue/Cost * 100<br /><br />For those using SKAN 4 in Conversion Studio, this is data for 2 days post-install. For those using SKAN 3 in Conversion Studio, data is based on the defined SKAN activity window, whether that's more or less than 2 days. |
| ROAS D7 | Includes modeled data, beyond the SKAN measurement window, up to 7 days post-install. <Anchor target="_blank" href="/marketers/docs/skan-modeled-data#revenue-ltv">Learn more</Anchor> |
| ROI D2 | Return On Investment (%).<br /><br />Formula: (Revenue - Cost)/Cost * 100<br /><br />For those using SKAN 4 in Conversion Studio, this is data for 2 days post-install. For those using SKAN 3 in Conversion Studio, data is based on the defined SKAN activity window, whether that's more or less than 2 days. |
| ROI D7 | Includes modeled data, beyond the SKAN measurement window, up to 7 days post-install. <Anchor target="_blank" href="/marketers/docs/skan-modeled-data#revenue-ltv">Learn more</Anchor> |
| Gross profit D2 | Profit after deducting campaign cost.<br /><br />Formula: Revenue - Cost<br /><br />For those using SKAN 4 in Conversion Studio, this is data for 2 days post-install. For those using SKAN 3 in Conversion Studio, data is based on the defined SKAN activity window, whether that's more or less than 2 days. |
| Gross profit D7 | Includes modeled data, beyond the SKAN measurement window, up to 7 days post-install. <Anchor target="_blank" href="/marketers/docs/skan-modeled-data#revenue-ltv">Learn more</Anchor> |
| **In-app event metrics** | **Metrics relating to specific in-app events (IAEs)** |
| Event unique users (D2) | Unique users performing the event, measured by a combination of AppsFlyer and SKAN, including modeled data of null values. For those using SKAN 4, this data is accumulated for the first 2 days post install. For those using SKAN 3, the data is an accumulation of days post-install based on the defined Activity Window. |
| Event unique users (D7) | Unique users performing the event, modeled based on a combination of AppsFlyer and SKAN. Includes modeled data, beyond the SKAN measurement window, up to 7 days post-install. <Anchor target="_blank" href="/marketers/docs/skan-modeled-data#inapp-event-ltv">Learn more</Anchor><br /><br />Note: Unique users in (D7) also includes unique users in D2. |
| Event eCPA (D2) | Effective cost per action: Cost / unique users performing the event |
| Event eCPA (D7) | Effective cost per action: Cost / unique users performing the event. Includes modeled data, beyond the SKAN measurement window, up to 7 days post-install. <Anchor target="_blank" href="/marketers/docs/skan-modeled-data#inapp-event-ltv">Learn more</Anchor> |
| Event conversion (D2) | Rate (%) of unique users performing the event, as a proportion of the users attributing (meaning installing, re-engaging, or re-attributing). Formula: Unique users / attributions * 100 |
| Event conversion (D7) | Rate (%) of unique users performing the event, as a proportion of the users attributing (meaning installing, re-engaging, or re-attributing). Formula: Unique users / attributions * 100. Includes modeled data, beyond the SKAN measurement window, up to 7 days post-install. <Anchor target="_blank" href="/marketers/docs/skan-modeled-data#inapp-event-ltv">Learn more</Anchor> |
| Event revenue (D2) | Revenue generated with this event, within the defined days post-install |
| Event revenue (D7) | Revenue generated with this event, within the defined days post-install. Includes modeled data, beyond the SKAN measurement window, up to 7 days post-install. <Anchor target="_blank" href="/marketers/docs/skan-modeled-data#inapp-event-ltv">Learn more</Anchor> |

</Accordion>

## How does SSOT work

<div id="understanding-skanaf-modeled-attribution-duplication" />

<Accordion title="Understanding SKAN-AF modeled attribution duplication">

SKAN attribution and AF modeled attribution work differently and have different traits and limitations. Therefore, each install can be attributed to a non-organic media source either:

* Via SKAN or an AF model exclusively (unique attribution).
* Via both SKAN and an AF model simultaneously (duplicates). In this case, the [SSOT mechanism](/docs/single-source-of-truth-ssot-guide-for-ios-attribution#ssot-mechanism-workings) signals a SKAN duplicate install with the flag: af\_attribution\_flag=TRUE. And in the SSOT dashboard, only one install displays instead of two.
* Neither SKAN nor AF model, meaning the install is organic.

The possible SKAN-AF model attribution scenarios are illustrated in the following Venn diagram.

![skan_af_model_diagram.png](https://files.readme.io/1b305d053044f79d12b9190d0b6c24dcc7e0bd17e17ef29029ad0b1c3c7d84c0-31247514684689.png)

The following table describes the reasons for each attribution scenario.

| SKAN only | AF model only | Both SKAN and AF model | Neither SKAN nor AF model |
| --- | --- | --- | --- |
| <ul><li>Media source is an SRN, user device has iOS 14.5+, user doesn’t provide dual ATT consent.</li><li>Media source is a non-SRN, user device has iOS 14.5+,  probabilistic modeling not available, user doesn’t provide dual ATT consent.</li></ul> | <ul><li>User device has iOS 14.4 and below.</li><li>Media source doesn't support SKAN.</li><li>Install came via a web-to-app flow (SKAN only supports app-to-app).</li><li>Install is via retargeting (not supported by SKAN)</li></ul> | No limitations exist and both SKAN and an AF model attribute the install.<br /><br />This creates duplicate installs, and is when SSOT is needed to remove the duplicate. | User is organic |

</Accordion>

<div id="ssot-mechanism-workings" />

<Accordion title="SSOT mechanism workings">

SSOT works as detailed in the visual that follows.

![SingleSourceOfTruth.png](https://files.readme.io/882527d4828cf3c7156caf183652368de33463a440715c69f7ec39bfd0f655fa-31247514685329.png)

**How does the SSOT mechanism work?**

The SSOT mechanism exists in the AppsFlyer SDK in your app on the user device and in the AppsFlyer platform as follows:

**User device:**

* A user opens the app for the first time. The AppsFlyer platform endeavors to attribute the user. The ability to attribute depends on the campaign type and user consent (ATT) status.
* If attribution succeeds, the SDK sets the attribution bit in the Conversion Value (CV)
* The regular SKAdNetwork flow continues unchanged. Meaning that user activity continues to be measured and the CV set until the measurement window terminates.
* Subsequently, iOS sends the postback.

**AppsFlyer platform**

* AppsFlyer receives the iOS postback, decodes the conversion value, and exposes the value of the attribution bit via the af\_attribution\_flag as detailed in the table that follows.

**Considerations**

* In general, AppsFlyer doesn't count reinstalls. In the context of SSOT, the reinstall status isn't considered. This means SSOT doesn't remove duplicate SKAN installs coming from reinstalls in the context of SSOT analytics and they don't affect the setting of the af\_attribution flag.

#### **Attribution flag field**

| SSOT indicator in the Conversion Value | Meaning | af\_attribution\_flag field |
| --- | --- | --- |
| On | SSOT is on in the Conversion Studio and AppsFlyer succeeded in attributing the user. | True |
| Off | SSOT is on in the Conversion Studio and AppsFlyer didn't attribute the user. | False |
| -- | SSOT is off in the Conversion Studio. | Null |

**How does the af\_attribution\_flag (attribution bit) impact reporting tools?**

* SKAN dashboard: Reflects only performance reported by SKAN postbacks. As such, the af\_attribution flag isn't considered and duplicates aren't removed.
* SKAN <Anchor target="_blank" href="/marketers/docs/skan-aggregated-performance-report-api">aggregated performance reports</Anchor> and <Anchor target="_blank" href="/marketers/docs/skan-raw-data-reports">raw data reports</Anchor>: The af\_attribution\_flag is available in these reports. Use it according to your reporting requirements. If you combine SKAN data with AppsFlyer data, use the flag to remove duplicate data. This applies to both raw and aggregated data reports.
* SSOT view in the Overview dashboard: Data from all attribution methods, SKAN, IDFA, IDFV, Apple Ads, and so on are merged in a single view after removing duplicate SKAN data.

</Accordion>

<div id="metrics-derived-by-combining-data-from-multiple-attribution-methods" />

<Accordion title="Metrics derived by combining data from multiple attribution methods">

When you combine SKAN data with the data of other attribution methods, use the af\_attribution\_flag to remove duplicate data from the data. This applies to both raw and aggregated data reports.

The following example metrics can be calculated using the af\_attribution\_flag:

* Non-organic installs
* Organic installs
* eCPI
* Cohorted revenue

Formula to calculate example metrics:

| Metric description | Designation | Formula |
| --- | --- | --- |
| Non-organic AppsFlyer installs | A | Non-organic installs reported by AppsFlyer |
| SKAN unique installs | B | SKAN installs where af\_attribution\_flag=false |
| All non-organic installs | C | A + B |
| Organic installs | D | Total installs - C<br /><br />**Note**: Total installs mean all installs recorded by the AppsFlyer SDK, regardless of attribution. |
| Campaign eCPI | E | Cost / C |
| Cohorted revenue | F | Add together the following:<ul><li>Revenue of users defined by A. Include events generated during the initial post-install period equivalent to your SKAN measurement window.</li><li>SKAN revenue where af\_attribution\_flag = false</li></ul> |
| Organic revenue D2 | G | Total D2 revenue - D2 revenue from A and B installs |
| Organic IAE unique users D2 | H | Total D2 IAE unique users - D2 event unique users from A and B installs |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| SSOT view | SSOT is only available if there is at least one SKAN postback for each of the past 5 days that includes `af_attribution_flag=true`. |
| Total installs | In some cases, there may be more installs displayed when SSOT is turned on versus when it's off. One of the reasons for this is that null conversion value modeling can impact the install date calculation, and cause differences when comparing installs on similar dates. Additionally, total installs can be inflated if null CVs aren't modeled, since in that case, every SKAN install is counted as unique (with the flag `af_attribution_flag=false`). |
| Revenue | Revenue and other revenue-related metrics (ARPU, ROAS, ROI, gross profit) are supported as of September 1, 2022. |
| Agencies | Agency users can view the SSOT view in the Overview dashboard. |
| Ad networks | <ul><li>Ad networks can access the SSOT view in the Overview dashboard to see data attributed to their media source. To see the SSOT view, the:<ul><li>Advertiser must have SSOT turned on in Conversion Studio.</li><li>Ad network must be running SKAN campaigns.</li><li>Ad network must have the <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">required permissions</Anchor> from the advertiser to access aggregate data.</li></ul></li><li>Ad networks can receive SSOT signals via SKAN postbacks by adding the skad\_af\_attribution\_flag field macro. <Anchor target="_blank" href="/partners/docs/skan-integration-guide-for-ad-networks#receive-data-from-appsflyer">Learn more</Anchor></li></ul> |
| D7 metrics | D7 metrics for organic traffic are available starting February 16, 2025.<br /><br />D7 metrics may be missing or less than D2 metrics if:<ul><li>The date range contains dates for which 8 days haven't passed.</li><li>Modeled data isn't available. For example, if there aren't 14 days of revenue data. <Anchor target="_blank" href="/marketers/docs/skan-modeled-data#revenue-ltv">Learn more</Anchor></li><li>SKAN Conversion Studio configuration has been changed in the past 14 days.</li><li>There are fewer than 10 installs for a given date.</li></ul> |
| SKAN Conversion Studio configuration changes | When you change your SKAN Conversion Studio configuration, there may be inaccuracies in SSOT data for approximately 96 hours. This is because AppsFlyer immediately begins to decode SKAN postbacks with the new schema, but postbacks still arrive from installs that were encoded with the previous schema. |
| AF-reported data | <ul><li>AF-reported data, sometimes referred to as AF model data, refers to data from installs or other events attributed via another AppsFlyer attribution method, as opposed to SKAN.</li><li>The SSOT dashboard's purpose is to prevent duplication of installs and events attributed via both SKAN and another AppsFlyer method.</li><li>If you turn on SSOT, but want to view data from before SSOT was turned on, the SSOT dashboard only displays AF-reported data.</li></ul> |
| In-app events | In-app events (as dimensions) and their metrics are available only for:<ul><li>Events that occurred during the Window 1 period are available.</li></ul> |
| SKAN postback delay | When SKAN postbacks arrive with significant delay, for example from Google API, which can take up to 15 days, data for later days (like D7) may initially appear lower than earlier days (like D2). This delay can affect the accuracy of the SSOT model. For this reason, we recommend waiting at least 15 days after the install date for the data to fully populate before evaluating model accuracy. |

</Accordion>

> 📄 **See also**
>
> * Overview dashboard
> * <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide">SKAN solution guide</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio">SKAN conversion studio</Anchor>

<div data-zendesk-anchors="how-to-get-true-ios-14-performance-data=about-single-source-of-truthtrue-ios-performance-data 01H8TZV6P41Z3ZEZ8VS86DK1J9=about-single-source-of-truthtrue-ios-performance-data 01H8TZV6P4G5AF2MJDQB8J6W2M=turn-on-single-source-of-truth 01H8TZV6P4ZBJTDH0FQ6F5D6Q9=overview-dashboard-single-source-of-truth-view 01H8TZV6P47ZE6PMPF7S9GCJ16=turn-on-single-source-of-truth-view 01H8TZV6P4VCC5NRKBRQNJ4NX3=ssot-view-considerations 01H8TZV6P4QXEXYWSXKDB7B5SV=filter-considerations 01H8TZV6P4YNTFBX5RXVKK8J0F=metrics 01H8TZV6P4K8VXNKDR7JHM8PFW=how-does-ssot-work 01H8TZV6P4QYQJ177E2ZG676MH=understanding-skanaf-modeled-attribution-duplication 01H8TZV6P58E502Y1FDFHC3KHM=ssot-mechanism-workings 01H8TZV6P5SSKDTKV4BV3TTA7D=attribution-flag-field 01H8TZV6P5AHZD8VRWRS4SPBYW=metrics-derived-by-combining-data-from-multiple-attribution-methods 01H8TZV6P5KN4F24ZN33V0TK7K=traits-and-limitations h_01HE182N43SSBX051E4GK7NFQ8=see-also" />
