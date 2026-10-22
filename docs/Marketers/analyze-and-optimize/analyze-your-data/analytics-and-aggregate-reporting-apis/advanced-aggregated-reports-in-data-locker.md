---
title: Advanced aggregated reports in Data Locker
metadata:
  keywords:
    - Premium
    - Premium Feature
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2024-03-06T10:46:12Z'
  edited_at: '2025-03-10T14:45:58Z'
  id: 23127074968721
  locale: en-us
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/23127074968721-Advanced-aggregated-reports-in-Data-Locker
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance**: Advanced aggregated reports in Data Locker contain aggregated data with optimal data freshness, accuracy, granularity, and unlimited volume.

## Advanced aggregated reports in Data Locker

Advanced aggregated reports in Data Locker:

* Provide an efficient and privacy-preserving way to build your internal BI systems based on aggregated data: Attribution, events, and revenue data, with all possible dimensions and metrics.
* You can load the data into your BI systems and use them as part of your campaign performance and optimization processes.
* Have the best freshness to accuracy: Data arrives <Anchor target="_blank" href="/marketers/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">multiple times per day</Anchor> and gets updated with each subsequent version of a report with all available data for that day.
* Helps you augment raw data that may be limited and <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions">restricted</Anchor> due to media source data-sharing policies or your <Anchor target="_blank" href="/marketers/docs/apply-aggregated-advanced-privacy-framework">privacy-preserving policies</Anchor>. The restrictions impact attribution-related fields like campaign and adset.

## Setup

To get advanced aggregated reports, complete one of the following procedures.

| Do you currently get data via Data Locker? | Procedure |
| --- | --- |
| Yes | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/fd2f20f4365b0ccf2b4f39700587a960563f4087b6f576063c0e49b95e0907c1-23127074967441.png)To add the reports to Data Locker:<ol><li>In AppsFlyer, from the side menu, select **Export > Data Locker**.</li><li>Select all the reports you want to get.</li><li>Click **Save configuration**.<br />The reports will be available the next day.</li></ol> |
| No | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/fd2f20f4365b0ccf2b4f39700587a960563f4087b6f576063c0e49b95e0907c1-23127074967441.png)**To set up Data Locker**:<ol><li>Complete the first-time Data Locker (<Anchor target="_blank" href="/marketers/docs/data-locker-for-marketers#set-up-data-locker">advertiser</Anchor> \| <Anchor target="_blank" href="/partners/docs/data-locker-for-partners">partner</Anchor>) setup.</li><li>Add the reports to Data Locker:<ol><li>In AppsFlyer, from the side menu, select **Export > Data Locker**.</li><li>Select all the reports you want to get.</li><li>Click **Save configuration**.<br />The reports will be available the next day.</li></ol></li></ol> |

## Reports available

<div id="cohort-versioned-report" />

<Accordion title="Advanced aggregated (cohort versioned) reports">

### Report facts

| Overview | The cohort versioned report contains all your aggregated data, cohorted, with all campaign dimension granularity. The report is updated every few hours to maximize data freshness and accuracy.<br /><br /><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vT8NQKO287TxXpdTYpIASL55t4muIt9G3lnkEE436FQhNn5_14DfYgf0ztbm1VVZXI4ecPaGktdixS7/pub?output=xlsx">Download sample report</Anchor> |
| --- | --- |
| Reports available | The following reports are available for download. The report types are described in more detail in the Cohort dashboard.<ul><li>**User acquisition:** attributed to a user acquisition media source including LTV occurring during re-engagement windows.</li><li>**Retargeting:** attributed to a retargeting media source for events occurring:<ul><li>During a re-engagement window</li><li>As a result of re-attributions</li></ul></li><li>**Unified:** display data under the last touch media source bringing the user according to AppsFlyer <Anchor target="_blank" href="/marketers/docs/resolve-retargeting-double-attribution">double attribution</Anchor> rules. Meaning that LTV occurring during re-engagements displays under the retargeting media source and not under the UA media source.</li></ul> |
| Reporting period | Users who converted during the previous 1,095 days. In other words, each day, the reports include events of users who converted during the previous 1,095 days. |
| Report structure | The schema of the report (the dimensions and metrics included) is fixed and can't be edited. |
| Data freshness | <ul><li>Intraday. Reports are sent every few hours.</li><li>Reports are for that day's data. Meaning, on April 18, every report version contains all current data for April 18. [Learn more](/docs/advanced-aggregated-reports-in-data-locker#report-versions-and-data-freshness)</li></ul> |
| Timezone | UTC |
| Directory and filename structure | [Learn more](/docs/advanced-aggregated-reports-in-data-locker#report-structure) |
| Impact of partner retention policies | Consider that some partners implement a data retention policy. In this case, events occurring after the end of the retention period are considered organic in the Cohort reports.<br /><br />Example: SRN "A" has a data retention policy of 180 days. User events until day 180 are attributed to SRN "A". Events that occur after 180 days are considered organic. |

### Report structure

The report is comprised of dimensions and metrics.

The format of the fields is as follows:

* **Dimensions**: String. The maximum length of the string is dynamic and in most instances depends on how you populate the elements of the advertising hierarchy
* **Metrics**: Number. **Note:** The selected\_currency field format is a string.  
  The metrics available are revenue, unique users performing an event and the number of event occurrences. To calculate cost-related metrics like ROI, and ROAS you need both revenue and cost metrics. Revenue metrics are in Cohort, and cost metrics are provided by <Anchor target="_blank" href="/marketers/docs/set-up-and-use-roi360-cost-etl-reports">ROI360 Cost ETL</Anchor>.

#### Dimensions

<Table>
  <thead>
    <tr>
      <th>
        Field name
      </th>
      <th>
        Description
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        app\_id
      </td>
      <td />
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td />
    </tr>
    <tr>
      <td>
        conversion\_type
      </td>
      <td>
        Possible values: install, install\_unified (representing installs in the unified report), re-engagement, re-attribution
      </td>
    </tr>
    <tr>
      <td>
        attributed\_touch\_type
      </td>
      <td>
        Possible values: click, impressions, pre-install, unknown, tv, null
      </td>
    </tr>
    <tr>
      <td>
        days\_post\_attribution
      </td>
      <td>
        <ul><li>The number of days elapsed since the conversion date (not the specific conversion timestamp).</li><li>Tip! Use this to calculate retention and KPI days</li></ul>
      </td>
    </tr>
    <tr>
      <td>
        event\_date
      </td>
      <td>
        <ul><li>The date a user performs a given event.</li><li>Format: yyyy-mm-dd</li><li>Example: The date a user performed a given in-app event. In the case of a conversion.</li><li>Note! If the event\_name is af\_conversion, then the event date and conversion date will be the same.</li></ul>
      </td>
    </tr>
    <tr>
      <td>
        conversion\_date
      </td>
      <td>
        <ul><li>The date the conversion occurred</li><li>Format: yyyy-mm-dd</li><li>Example: The install date</li></ul>
      </td>
    </tr>
    <tr>
      <td>
        event\_name
      </td>
      <td>
        Identifies the event. Some event names have a specific meaning while others relate to in-app events set by the advertiser in the app.<table><thead><tr><th>event\_name</th><th>What did the user do</th></tr></thead><tbody><tr><td>af\_conversion</td><td>User converted. Use conversion\_type to identify if it is an install, re-engagement, or re-attribution.</td></tr><tr><td>af\_session</td><td>Opened the app</td></tr><tr><td>cohort\_uninstalls</td><td>Uninstalled the app</td></tr><tr><td>Advertiser defined in-app event</td><td>Performed an in-app event in the app</td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        campaign
      </td>
      <td>
        Campaign hierarchy<br /><br />Consider: Campaign name changes not supported. Consequently, multiple names can be associated with a given campaign ID.
      </td>
    </tr>
    <tr>
      <td>
        campaign\_id
      </td>
      <td>
        Campaign hierarchy
      </td>
    </tr>
    <tr>
      <td>
        adset
      </td>
      <td>
        Campaign hierarchy
      </td>
    </tr>
    <tr>
      <td>
        adset\_id
      </td>
      <td>
        Campaign hierarchy
      </td>
    </tr>
    <tr>
      <td>
        ad
      </td>
      <td>
        Campaign hierarchy
      </td>
    </tr>
    <tr>
      <td>
        ad\_id
      </td>
      <td>
        Campaign hierarchy
      </td>
    </tr>
    <tr>
      <td>
        channel
      </td>
      <td>
        Campaign hierarchy.<br /><br />[Updated October 27, 2021] At present, Meta ads doesn't populate channel in data provided via the Google Install Referrer mechanism.
      </td>
    </tr>
    <tr>
      <td>
        site\_id
      </td>
      <td>
        Campaign hierarchy
      </td>
    </tr>
    <tr>
      <td>
        is\_primary\_attribution
      </td>
      <td>
        Use to identify and deduplicate retargeting data.
      </td>
    </tr>
    <tr>
      <td>
        geo
      </td>
      <td>
        The ISO country code derived from the user IP address.
      </td>
    </tr>
    <tr>
      <td>
        agency
      </td>
      <td>
        <ul><li>Agency transparency supported.</li><li>In the case of non-transparent agencies, there can be multiple rows containing the same campaign name if the advertiser and the agency both run campaigns with the same name. Don't worry. The rows aren't duplicated.</li></ul>
      </td>
    </tr>
    <tr>
      <td>
        install\_app\_store
      </td>
      <td>
        Android apps only: The Android store from where the app was downloaded. Populated by advertisers implementing <Anchor target="_blank" href="/marketers/docs/set-up-multi-store-android-attribution">multi-store Android attribution</Anchor>. If blank, it means Google Play Store.
      </td>
    </tr>
    <tr>
      <td>
        keywords
      </td>
      <td>
        Word(s) used in the user's online search. As reported by the ad network.
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        Keyword ID returned by the ad network.
      </td>
    </tr>
  </tbody>
</Table>

#### Metrics

| Field name | Description | Format |
| --- | --- | --- |
| unique\_users | Number of on-day unique users performing the event. | Number |
| revenue\_usd | <ul><li>Amount of revenue in USD. For example, $100.56 is reflected as 100.56.</li><li>Maximum of 2 places after the decimal point.</li></ul> | Number |
| event\_count | Number of event occurrences. | Number |
| selected\_currency | 3-letter currency code (USD, EUR) set by you in the app settings. Format <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>. This is the same currency used to display revenue in Cohort in the user interface. | String |
| revenue\_selected\_currency | <ul><li>Amount of revenue in the selected currency. For example, if the selected currency is EUR, then €1234.56 is reflected as 1234.56</li><li>Maximum of 2 places after the decimal point</li></ul> | Number |
| first\_inapp | <ul><li>Number of users performing the event for the first time following their conversion.</li><li>Summing the first\_inapp metrics together gives you the cumulative unique user count for the event.</li></ul> | Number |

#### Directory and filename structure

The path to the report consists of the following folder hierarchy:

With the following format: `<bucket-name>/t=cohort_unified_versioned/dt=<yyyy-mm-dd>/version=<unix timestamp>/<parquet file number>`

#### Report folder hierarchy

An example of the cohort versioned report folder hierarchy in the advertiser bucket:

```
bucket
|
└── t=cohort_unified_versioned
    |
    ├── dt=2024-05-05
    |   |
    |   └── version=1714890235
    |   |    |
    |   |    ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    |
    |   |    ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    │
    |   |    └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |
    |   |
    |   └── version=1714890286
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |   |
    .   . 
    .   .
```

**Legend:**

* **dt**: Date when the events included in the report occurred.
* **t:** report type.
* **version**: Unix timestamp when the version was created.

### Report versions and data freshness

* Intraday. Reports are sent every few hours.
* Reports are for all the data currently available for the day. Meaning, on April 18, every report version contains all available data up to that point for April 18.
* **Only ingest the latest available report version.**

| Version | Report includes data that AppsFlyer received by (Time in UTC) | Use case | Time report is available (Time in UTC) |
| --- | --- | --- | --- |
| 1 | Day 0 at 4 AM | Partial data for Day 0 | Day 0 at 8 AM |
| 2 | Day 0 at 8 AM | Partial data for Day 0 | Day 0 at 1 PM |
| 3 | Day 0 at 12 PM | Partial data for Day 0 | Day 0 at 6 PM |
| 4 | Day 0 at 4 PM | Partial data for Day 0 | Day 0 at 9 PM |
| 5 | Day 0 at 8 PM | Partial data for Day 0 | Day 0 at 11:59 PM |
| 6 | Day 0 at 11:59 PM | Complete conversion and in-app event data for Day 0 (excluding S2S events that AppsFlyer receives between Day 0 at 11:59 PM and Day 1 at 2 AM) | Day 1 at 4 AM |
| 7 | Day 1 at 3 AM | Complete conversion and in-app event data for Day 0, and any currently available ad revenue data sent via S2S | Day 1 at 8 AM |
| 8 | Day 1 at 11 AM | Complete conversion and in-app event data for Day 0, and any currently available ad revenue data sent via S2S | Day 1 at 6 PM |
| 9 | Day 1 at 5 PM | Complete conversion and in-app event data for Day 0, and any currently available ad revenue data sent via S2S | Day 1 at 11:59 PM |
| 10 | Day 8 at 7 AM | Complete conversion and in-app event data for Day 0, and complete ad revenue data sent via S2S, accounting for any potential issues that may have occurred on the ad revenue network side | Day 8 at 1 PM |

</Accordion>

<div id="cohort-timezone-versioned-report" />

<Accordion title="Advanced aggregated (cohort timezone versioned) reports">

### Report facts

| Overview | The cohort timezone versioned report contains all your aggregated data, cohorted, with all campaign dimension granularity, according to localized timezones. The report is updated every few hours to maximize data freshness and accuracy.<br /><br /><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQk1cZkeJhlx3trW13SjGbD4aWX3LmXZJRDJRApuAJkjB7XAg4nSFUyN0_YoirX-QMHkhFeMHwEmiVj/pub?output=xlsx">Download sample report</Anchor> |
| --- | --- |
| Reports available | The following reports are available for download. The reports types are described in more detail in <Anchor target="_blank" href="/marketers/docs/cohort-and-retention-dashboard#cohort-principles">Cohort dashboard.</Anchor><ul><li>**User acquisition:** attributed to a user acquisition media source including LTV occurring during re-engagement windows.</li><li>**Retargeting:** attributed to a retargeting media source for events occurring:<ul><li>During a re-engagement window</li><li>As a result of re-attributions</li></ul></li><li>**Unified:** display data under the last touch media source bringing the user according to AppsFlyer <Anchor target="_blank" href="/marketers/docs/resolve-retargeting-double-attribution">double attribution</Anchor> rules. Meaning that LTV occurring during re-engagements displays under the retargeting media source and not under the UA media source.</li></ul> |
| Reporting period | Users who converted during the previous 1,095 days. In other words, each day, the reports include events of users who converted during the previous 1,095 days.<br /><br />**Note**: If a day hasn't started yet in your local timezone, timezone-versioned reports will arrive without data. |
| Report structure | The schema of the report (the dimensions and metrics included) is fixed and can't be edited. |
| Data freshness | <ul><li>Intraday. Reports are sent every few hours.</li><li>Reports are for that day's data. Meaning, on April 18, every report version contains all current data for April 18. [Learn more](/docs/advanced-aggregated-reports-in-data-locker#report-versions-and-data-freshness-1)</li></ul> |
| Timezone | Any timezone except UTC. Meaning, the reports leave out data for any apps with UTC timezone settings in AppsFlyer. |
| Directory and filename structure | [Learn more](/docs/advanced-aggregated-reports-in-data-locker#report-structure-1) |
| Impact of partner retention policies | Consider that some partners implement a data retention policy. In this case, events occurring after the end of the retention period are disregarded in the Cohort reports.<br /><br />Example: SRN "A" has a data retention policy of 180 days. User events until day 180 are attributed to SRN "A". Events that occur after 180 days are disregarded.<br /><br />**Note**: The events display in the Overview dashboard as organic. |

### Report structure

The report is comprised of dimensions and metrics.

The format of the fields is as follows:

* **Dimensions**: String. The maximum length of the string is dynamic and in most instances depends on how you populate the elements of the advertising hierarchy
* **Metrics**: Number. **Note:** The selected\_currency field format is a string.  
  The metrics available are revenue, unique users performing an event and the number of event occurrences. To calculate cost-related metrics like ROI, and ROAS you need both revenue and cost metrics. Revenue metrics are in Cohort, and cost metrics are provided by <Anchor target="_blank" href="/marketers/docs/set-up-and-use-roi360-cost-etl-reports">ROI360 Cost ETL</Anchor>.

#### Dimensions

<Table>
  <thead>
    <tr>
      <th>
        Field name
      </th>
      <th>
        Description
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        app\_id
      </td>
      <td />
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td />
    </tr>
    <tr>
      <td>
        conversion\_type
      </td>
      <td>
        Possible values: install, install\_unified (representing installs in the unified report), re-engagement, re-attribution
      </td>
    </tr>
    <tr>
      <td>
        attributed\_touch\_type
      </td>
      <td>
        Possible values: click, impressions, pre-install, unknown, tv, null
      </td>
    </tr>
    <tr>
      <td>
        days\_post\_attribution
      </td>
      <td>
        <ul><li>The number of days elapsed since the conversion date (not the specific conversion timestamp).</li><li>Tip! Use this to calculate retention and KPI days</li></ul>
      </td>
    </tr>
    <tr>
      <td>
        event\_date
      </td>
      <td>
        <ul><li>The date a user performs a given event.</li><li>Format: yyyy-mm-dd</li><li>Example: The date a user performed a given in-app event. In the case of a conversion.</li><li>Note! If the event\_name is af\_conversion, then the event date and conversion date will be the same.</li></ul>
      </td>
    </tr>
    <tr>
      <td>
        conversion\_date
      </td>
      <td>
        <ul><li>The date the conversion occurred</li><li>Format: yyyy-mm-dd</li><li>Example: The install date</li></ul>
      </td>
    </tr>
    <tr>
      <td>
        event\_name
      </td>
      <td>
        Identifies the event. Some event names have a specific meaning while others relate to in-app events set by the advertiser in the app.<table><thead><tr><th>event\_name</th><th>What did the user do</th></tr></thead><tbody><tr><td>af\_conversion</td><td>User converted. Use conversion\_type to identify if it is an install, re-engagement, or re-attribution.</td></tr><tr><td>af\_session</td><td>Opened the app</td></tr><tr><td>cohort\_uninstalls</td><td>Uninstalled the app</td></tr><tr><td>Advertiser defined in-app event</td><td>Performed an in-app event in the app</td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        event\_timezone
      </td>
      <td>
        The timezone for:<ul><li>days\_post\_atribution</li><li>event\_date</li><li>conversion\_date</li></ul>
      </td>
    </tr>
    <tr>
      <td>
        campaign
      </td>
      <td>
        Campaign hierarchy<br /><br />Consider: Campaign name changes not supported. Consequently, multiple names can be associated with a given campaign ID.
      </td>
    </tr>
    <tr>
      <td>
        campaign\_id
      </td>
      <td>
        Campaign hierarchy
      </td>
    </tr>
    <tr>
      <td>
        adset
      </td>
      <td>
        Campaign hierarchy
      </td>
    </tr>
    <tr>
      <td>
        adset\_id
      </td>
      <td>
        Campaign hierarchy
      </td>
    </tr>
    <tr>
      <td>
        ad
      </td>
      <td>
        Campaign hierarchy
      </td>
    </tr>
    <tr>
      <td>
        ad\_id
      </td>
      <td>
        Campaign hierarchy
      </td>
    </tr>
    <tr>
      <td>
        channel
      </td>
      <td>
        Campaign hierarchy.<br /><br />[Updated October 27, 2021] At present, Meta ads doesn't populate channel in data provided via the Google Install Referrer mechanism.
      </td>
    </tr>
    <tr>
      <td>
        site\_id
      </td>
      <td>
        Campaign hierarchy
      </td>
    </tr>
    <tr>
      <td>
        is\_primary\_attribution
      </td>
      <td>
        Use to identify and deduplicate retargeting data.
      </td>
    </tr>
    <tr>
      <td>
        geo
      </td>
      <td>
        The ISO country code derived from the user IP address.
      </td>
    </tr>
    <tr>
      <td>
        agency
      </td>
      <td>
        <ul><li>Agency transparency supported.</li><li>In the case of non-transparent agencies, there can be multiple rows containing the same campaign name if the advertiser and the agency both run campaigns with the same name. Don't worry. The rows aren't duplicated.</li></ul>
      </td>
    </tr>
    <tr>
      <td>
        install\_app\_store
      </td>
      <td>
        Android apps only: The Android store from where the app was downloaded. Populated by advertisers implementing <Anchor target="_blank" href="/marketers/docs/set-up-multi-store-android-attribution">multi-store Android attribution</Anchor>. If blank, it means Google Play Store.
      </td>
    </tr>
    <tr>
      <td>
        keywords
      </td>
      <td>
        Word(s) used in the user's online search. As reported by the ad network.
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        Keyword ID returned by the ad network.
      </td>
    </tr>
  </tbody>
</Table>

#### Metrics

| Field name | Description | Format |
| --- | --- | --- |
| unique\_users | Number of on-day unique users performing the event. | Number |
| revenue\_usd | <ul><li>Amount of revenue in USD. For example, $100.56 is reflected as 100.56.</li><li>Maximum of 2 places after the decimal point.</li></ul> | Number |
| event\_count | Number of event occurrences. | Number |
| selected\_currency | 3-letter currency code (USD, EUR) set by you in the app settings. Format <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>. This is the same currency used to display revenue in Cohort in the user interface. | String |
| revenue\_selected\_currency | <ul><li>Amount of revenue in the selected currency. For example, if the selected currency is EUR, then €1234.56 is reflected as 1234.56</li><li>Maximum of 2 places after the decimal point</li></ul> | Number |
| first\_inapp | <ul><li>Number of users performing the event for the first time following their conversion.</li><li>Summing the first\_inapp metrics together gives you the cumulative unique user count for the event.</li></ul> | Number |

#### Directory and filename structure

The path to the report consists of the following folder hierarchy:

With the following format: `<bucket-name>/t=cohort_unified_timezone_versioned/dt=<yyyy-mm-dd>/version=<unix timestamp>/<parquet file number>`

#### Report folder hierarchy

An example of the cohort timezone versioned report folder hierarchy in the advertiser bucket:

```
bucket
|
└── t=cohort_unified_timezone_versioned
    |
    ├── dt=2024-05-05
    |   |
    |   └── version=1714890235
    |   |    |
    |   |    ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    |
    |   |    ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    │
    |   |    └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |
    |   |
    |   └── version=1714890286
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |   |
    .   . 
    .   .
```

**Legend:**

* **dt**: Date when the events included in the report occurred.
* **t:** report type.
* **version**: Unix timestamp when the version was created.

### Report versions and data freshness

* Intraday. Reports are sent every few hours.
* Reports are for all the data currently available for the day. Meaning, on April 18, every report version contains all available data up to that point for April 18.
* Report use cases may be different depending on your geo and timezone. [Learn more](/docs/advanced-aggregated-reports-in-data-locker#timezone-geos)
* **Only ingest the latest available report version.**

| Version | Report includes data that AppsFlyer received by (Time in UTC) | Use case | Time report is available (Time in UTC) |
| --- | --- | --- | --- |
| 1 | Day -1 at 4 AM | Eastern geos - partial data for Day 0 | Day -1 at 8 AM |
| 2 | Day -1 at 8 AM | Eastern geos - partial data for Day 0 | Day -1 at 1 PM |
| 3 | Day -1 at 12 PM | Eastern geos - partial data for Day 0 | Day -1 at 6 PM |
| 4 | Day -1 at 4 PM | Eastern geos - partial data for Day 0 | Day -1 at 9 PM |
| 5 | Day -1 at 8 PM | Eastern geos - partial data for Day 0 | Day -1 at 11:59 PM |
| 6 | Day -1 at 11:59 PM | Eastern and Central geos - partial data for Day 0 | Day 0 at 4 AM |
| 7 | Day 0 at 4 AM | All geos - partial data for Day 0 | Day 0 at 8 AM |
| 8 | Day 0 at 8 AM | All geos - partial data for Day 0 | Day 0 at 1 PM |
| 9 | Day 0 at 12 PM | All geos - partial data for Day 0 | Day 0 at 6 PM |
| 10 | Day 0 at 4 PM | All geos - partial data for Day 0 | Day 0 at 9 PM |
| 11 | Day 0 at 8 PM | <ul><li>Eastern geos - Complete conversion and in-app event data for Day 0</li><li>Central and Western geos - partial data for Day 0</li></ul> | Day 0 at 11:59 PM |
| 12 | Day 0 at 11:59 PM | Central and Western geos - partial data for Day 0 | Day 1 at 4 AM |
| 13 | Day 1 at 4 AM | <ul><li>Central geos - Complete conversion and in-app event data for Day 0</li><li>Western geos - partial data for Day 0</li><li>Any currently available ad revenue data sent via S2S</li></ul> | Day 1 at 8 AM |
| 14 | Day 1 at 8 AM | Western geos - partial data for Day 0, and any currently available ad revenue data sent via S2S | Day 1 at 1 PM |
| 15 | Day 1 at 12 PM | Western geos - partial data for Day 0, and any currently available ad revenue data sent via S2S at the time the report is processed | Day 1 at 6 PM |
| 16 | Day 1 at 12 PM | Western geos - partial data for Day 0, and updated ad revenue data sent via S2S (the report is only processed after ad revenue data completes processing) | Day 1 at 6 PM |
| 17 | Day 1 at 4 PM | Western geos - partial data for Day 0, and any currently available ad revenue data sent via S2S | Day 1 at 9 PM |
| 18 | Day 1 at 6 PM | Western geos - partial data for Day 0, and any currently available ad revenue data sent via S2S | Day 1 at 11:59 PM |
| 19 | Day 1 at 8 PM | Western geos - Complete conversion, in-app event data for Day 0, and complete ad revenue data sent via S2S | Day 1 at 11:59 PM |
| 20 | Day 1 at 11:59 PM | Complete conversion and in-app event data for Day 0, and complete ad revenue data sent via S2S, accounting for any potential issues that may have occurred on the ad revenue network side | Day 2 at 4 AM |
| 21 | Day 8 at 00:00 AM | Complete conversion and in-app event data for Day 0, and complete ad revenue data sent via S2S, accounting for any potential issues that may have occurred on the ad revenue network side | Day 8 at 6 AM |

</Accordion>

## Additional information

<div id="timezone-geos" />

<Accordion title="Timezone geos">

Report use cases may be different depending on your geo and timezone. Use the following table to understand which geos match which timezones.

| Geo | Timezone |
| --- | --- |
| Eastern | UTC+12 - UTC+3 |
| Central | UTC+2.5 - UTC-3 |
| Western | UTC-3.5 - UTC-12 |

</Accordion>

<div id="bi-developer-considerations" />

<Accordion title="BI developer considerations">

**Scope of data in the report**

The reports contain user acquisition installs and retargeting re-attributions and re-engagements, and their related in-app events.

You can load unified, user acquisition, and retargeting reports separately or together into your BI. If you load them together and want to filter the views on your own:

* For unified, use the is\_primary\_attribution=true or null field.
* For user acquisition, use conversion\_type=Install.
* For retargeting, use conversion\_type=re-engagement or re-attribution.

If you just use the unified view in your data loading process, you can use logic to split the data between campaign types, which means, user attribution (installs) and retargeting (re-engagements). To do so, use the conversion\_type=install, install\_unified, re-engagement, or re-attribution. See <Anchor target="_blank" href="/marketers/docs/resolve-retargeting-double-attribution">Double attribution of retargeting events.</Anchor>

**Field-level considerations**

* Use post-attribution days to enable easy calculation of retention metrics.
* Calculate unique users using campaign name and campaign ID dimensions: If you can disregard campaign name granularity, you can sum unique count on campaign ID and the metrics are correct.
* You can aggregate the data using the campaign hierarchy fields.
* Revenue in USD is calculated using the exchange rate on the event day.

**General considerations**

The data of all apps is configurable; it can be provided in a single file or separate files per app.

</Accordion>

<div id="use-cases" />

<Accordion title="Use cases">

The following are examples of some popular, practical applications of the data that BI developers can extract via Data Locker. Each example is illustrated by an SQL statement and sample Excel visual.

#### **1. Calculate retention**

In the following example, we:

* Calculate retention Day 1 and Day 7, as well as the total number of installs per campaign and ad.
* Sum the event count per conversion event by filtering `event_name`to be `af_conversion`.
* Specifically, analyze user acquisition campaigns in the Unified report by filtering the data so that `conversion_type IN (install, install_unified)`.

**SQL statement**

```sql
select
    campaign_id, ad_id,
    sum(if(event_name = 'af_conversion', event_count,0)) as installs,
    sum(if(event_name = 'af_session' and days_post_attribution = 1, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day1,
    sum(if(event_name = 'af_session' and days_post_attribution = 7, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08' 
    and app_id = YOUR_APP
group by 1,2
```

**Excel example**

| Campaign ID | Ad ID | Installs | Retention Day 1 | Retention Day 7 |
| --- | --- | --- | --- | --- |
| 12345678 | 987654 | 100 | 30% | 10% |
| 98765432 | 123456 | 200 | 25% | 15% |
| 07315466 | 613770 | 300 | 20% | 12% |

#### **2. Calculate ARPU of multiple in-app events**

In the following example, we:

* Calculate ARPU of multiple in-app events per campaign.
* Specifically analyze retargeting campaigns by filtering the data so that `conversion_type=re-engagement` and `conversion_type=re-attribution`.
* Sum the event count per conversion event by filtering `event_name`to be `af_conversion`.
* Sum the revenue of multiple events, in this case `af_purchase`and `af_coins`.
* Set `days_post_attribution` to the minimum needed (in this case, 7) to minimize the data processing load.

**SQL statement**

```sql
select
    campaign_id,
    sum(if(days_post_attribution <= 1 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day1,
    sum(if(days_post_attribution <= 3 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day3,
    sum(if(days_post_attribution <= 7 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and days_post_attribution <= 7
    and conversion_type in ('re-engagement', 're-attribution')
    and app_id = YOUR_APP
group by 1
```

**Excel example**

| Campaign ID | Conversion type | ARPU<br /><br />Day 1 | ARPU<br /><br />Day 3 | ARPU<br /><br />Day 7 |
| --- | --- | --- | --- | --- |
| 12345678 | re-engagement | 6.23 | 5.11 | 2.34 |
| 98765432 | re-engagement | 3.57 | 1.34 | 4.86 |
| 07315466 | re-attribution | 7.41 | 6.79 | 5.29 |

#### **3. Calculate in-app event conversion rate for a specific cohort day**

In the following example, we:

* Calculate the Day 0 in-app event conversion rate for multiple dimensions (in this case, conversion date, geo, campaign, ad, and site ID).
* Analyze unified data (both UA and retargeting campaigns) by filtering the data so that `is_primary_attribution=true`.
* Sum the event count per conversion event by filtering `event_name`to be `af_conversion`.
* Set `days_post_attribution` to the minimum needed (in this case, 7) to minimize the data processing load.

**SQL statement**

```sql
select
    conversion_date, geo, campaign_id, ad_id, site_id,
    sum(if(days_post_attribution = 0 and event_name = 'af_complete_tutorial', unique_users, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as day0_af_tutorial_conversion
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and is_primary_attribution = true
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Excel example**

| Conversion date | Geo | Campaign ID | Ad ID | Site ID | Day 0 af\_complete\_tutorial |
| --- | --- | --- | --- | --- | --- |
| 2022-11-07 | US | 12345678 | 123456 | site\_123 | 45% |
| 2022-11-05 | UK | 98765432 | null | site\_654 | 70% |
| 2022-10-31 | KR | 07315466 | null | null | 63% |

#### **4. Calculate daily installs**

In the following example, we:

* Calculate the number of installs per app ID, conversion date, media source, event name, and conversion type.
* In the Unified report, filter the data to show UA installs (not retargeting) by setting `conversion_type` to `install` or `install_unified`.
* Sum the installs by setting `event_name`to be `af_conversion`.

**SQL statement**

```sql
select
    app_id,
    conversion_date,
    media_source,
    event_name,
    conversion_type,
    sum(events_count) as total
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')
    and conversion_type = 'install'
    and event_name = 'af_conversion'
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Excel example**

| App ID | Conversion date | Media source | Event name | Total |
| --- | --- | --- | --- | --- |
| id123456789 | 2022-11-07 | adnet1\_int | af\_conversion | 105 |
| id123456789 | 2022-11-05 | adnet2\_int | af\_conversion | 216 |
| id123456789 | 2022-10-31 | adnet3\_int | af\_conversion | 327 |

#### **5. Calculate revenue from Facebook Ads**

In the following example, we:

* Calculate Day 3 revenue from Facebook by conversion date and app ID.
* Analyze Facebook data by filtering the data so that `media_source='Facebook Ads'`.
* Set `days_post_attribution` to the minimum needed (in this case, 3) to minimize the data processing load.

**SQL statement**

```sql
select
    conversion_date,
    app_id,
    media_source,
    sum(if(days_post_attribution <= 3, revenue_usd, 0)) as revenue_day3
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and days_post_attribution <= 3
    and media_source = 'Facebook Ads'
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3
```

**Excel example**

| Conversion date | App ID | Media source | Revenue<br /><br />Day 3 |
| --- | --- | --- | --- |
| 2022-11-07 | id123456789 | adnet1\_int | 400.45 |
| 2022-11-05 | id123456789 | adnet2\_int | 99.23 |
| 2022-10-31 | id123456789 | adnet3\_int | 13.34 |

#### **6. Calculate ARPU per ASA keyword ID for up to 365 cohort days**

In the following example, we:

* Calculate ARPU from Apple Search Ads per keyword ID until cohort day 365.
* Analyze Apple Search Ads data by filtering the data so that `media_source='Apple Search Ads'`.
* Sum the event count per conversion event by filtering `event_name`to be `af_conversion`.

**SQL statement**

```sql
select
    media_source,
    keyword_id,
    sum(if(days_post_attribution <= 365, revenue_usd,0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day365
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and media_source = 'Apple Search Ads'
    and app_id = YOUR_APP
group by 1
```

**Excel example**

| Media source | Keyword ID | ARPU<br /><br />Day 365 |
| --- | --- | --- |
| adnet1\_int | 123456 | 57,019.93 |
| adnet2\_int | 987654 | 64,867.84 |
| adnet3\_int | 666854 | 48,160.02 |

#### **7. Calculate ARPU Days 7 by attribution time per geo**

The following example illustrates how to use <Anchor target="_blank" href="/marketers/docs/cohort-and-retention-dashboard#trend-type%E2%80%94kpi-by-attribution-time">KPIs by attribution time</Anchor>. In the example, we:

* Calculate ARPU Days 7 by attribution date per geo.
* Results are sorted by the number of conversions, with the top 20 geos displaying.
* Data is filtered so that `conversion_type='install'`.
* The first column shows geo. The second column shows the total conversions. The columns thereafter show the revenue days 7 for every day specified to be a row in the query.

**SQL statement**

```sql
select
    geo,
    sum(if(event_name = 'af_conversion', event_count, 0)) total_conversions,
    sum(if(cohort_day = '2023-07-11' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-11' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_11,
    sum(if(cohort_day = '2023-07-12' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-12' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_12,
    sum(if(cohort_day = '2023-07-13' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-13' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_13,
    sum(if(cohort_day = '2023-07-14' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-14' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_14,
    sum(if(cohort_day = '2023-07-15' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-15' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_15,
    sum(if(cohort_day = '2023-07-16' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-16' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_16
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-07-11' and '2023-07-16'
    and days_post_attribution <= 7
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')    
    and conversion_type = 'install'
    and app_id = 'YOUR_APP'
group by 1
order by 2 desc
limit 20
```

**Excel example**

| Geo | Total conversions | ARPU Day 7 for 2023-07-11 | ARPU Day 7 for 2023-07-12 | ARPU Day 7 for 2023-07-13 | ARPU Day 7 for 2023-07-14 | ARPU Day 7 for 2023-07-15 | ARPU Day 7 for 2023-07-16 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| South Korea | 120,660 | $7,798.89 | $6,997.37 | $8,258.95 | $9,050.21 | $10,018.04 | $13,765.73 |
| Canada | 35,099 | $64,867.84 | $7,050.19 | $5,656.33 | $9,553.75 | $8,632.41 | $11,308.06 |
| Chile | 26,750 | $48,160.02 | $21,249.55 | $22,584.57 | $24,033.07 | $31,118.91 | $41,145.22 |

#### **8. Calculate purchases Day 7 after conversion**

In the following example, we:

* Calculate the cumulative unique users who perform af\_purchase events 7 days following their conversion (in unified view).
* Calculate the conversion rate to the event, meaning the share of conversions who make a purchase in the 7 days following their conversion.
* Data is filtered so that `conversion_type='install'`.
* Data is grouped by app, conversion date, media source, campaign, and adset.

**SQL statement**

```sql
select
    app_id, conversion_date, media_source, campaign, adset,
    sum(if(event_name = 'af_conversion', event_count,0)) as unified_conversions,
    sum(if(event_name = 'af_purchase', first_inapp, 0)) as af_purchase_day_7_cumulative_unique_users,
    concat(
        cast(
            round(
                sum(if(event_name = 'af_purchase', first_inapp, 0)) /
                sum(if(event_name = 'af_conversion', event_count, 0)) * 100.0
            ,2)
        as varchar),
    '%') as af_purchase_day_7_cumulative_unique_users_conversion_rate
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-12-01' and '2023-12-31'
    and is_primary_attribution = true
    and days_post_attribution <= 7
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3,4,5
```

**Excel example**

| App ID | Conversion date | Media source | Campaign | Adset | Unified conversions | D7 af\_purchase cumulative | D7 af\_purchase conversion rate |
| --- | --- | --- | --- | --- | --- | --- | --- |
| id123456789 | 2024-03-05 | adnet1\_int | campaign\_1 | adset\_1 | 100 | 20 | 20% |
| id123456789 | 2024-03-07 | adnet2\_int | campaign\_2 | adset\_2 | 200 | 10 | 5% |
| id123456789 | 2024-03-31 | adnet3\_int | campaign\_3 | adset\_3 | 150 | 15 | 10% |

#### **9. Calculate DAU**

In the following example, we:

* Calculate the DAU for each day in a chosen time range grouped by media source, campaign, and ad.
* Data is filtered so that `event_name = 'af_session'`.
* Sum the unique users for 1 day at a time, where each date is its own dimension (column).

**Note**:

* You can't sum multiple days (for example to get WAU or MAU).
* DAU is based on the activity of users who converted in the past 1,095 days. This differs from data that may be seen in the Activity dashboard and reports, that don't have this limit. See "Days post-conversion" in the [traits and limitations section](/docs/advanced-aggregated-reports-in-data-locker#traits-and-limitations).

**SQL statement**

```sql
select
media_source,campaign_id, ad_id,
sum(case when event_date = '2024-08-06' then unique_users end) as dau_2024_08_06,
sum(case when event_date = '2024-08-07' then unique_users end) as dau_2024_08_07,
sum(case when event_date = '2024-08-08' then unique_users end) as dau_2024_08_08
from YOUR_DATA_LOCKER_REPORT
where event_date between '2024-08-06' and '2024-08-08'
and event_name = 'af_session'
and app_id = YOUR_APP
group by 1,2,3
```

**Excel example**

| Media source | Campaign | Ad | DAU August 6 | DAU August 7 | DAU August 8 |
| --- | --- | --- | --- | --- | --- |
| adnet1\_int | campaign\_1 | adset\_1 | 475,250 | 420,485 | 463,912 |
| adnet2\_int | campaign\_2 | adset\_2 | 380,987 | 355,665 | 401,232 |
| adnet3\_int | campaign\_3 | adset\_3 | 290,042 | 570,322 | 489,787 |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait |  |
| --- | --- |
| Cost data | <ul><li>Not available. <Anchor target="_blank" href="/marketers/docs/set-up-and-use-roi360-cost-etl-reports">Use Cost ETL</Anchor>.</li><li>See also <Anchor target="_blank" href="/marketers/docs/combine-cost-etl-and-cohort-reports-via-data-locker">combine Cost ETL with cohort reports</Anchor>.</li></ul> |
| Campaign name changes | Not supported. Use campaign ID for grouping and filtering if campaign names were changed. |
| Data freshness | Intraday |
| Ad revenue | Available |
| Currency | USD and app-specific currency are both available per row |
| Timezone | App-specific timezone is available with the timezone versioned report. |
| Organic data | Available |
| Days post-conversion (install, re-attribution, re-engagement) data is available | 1,095 days is available. |
| Agency transparency | <ul><li>Supported</li><li>X Ads and Meta ads data is always transparent</li></ul> |
| App segregation | Supported |
| SKAN data | Not included. Meaning, the data is provided by iOS postbacks, not by Data Locker reports. |
| Uninstalls data | Uninstalls are processed daily. Thus, they only appear in reports that contain complete data for a day (not partial data). |
| Reinstalls | <ul><li>If post-reinstall events are considered unattributed organic:<ul><li>They're included only as of May 26, 2024. <Anchor target="_blank" href="/marketers/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">Learn more</Anchor></li><li>The install time is based on the <Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor> field.</li><li>They aren't counted toward unique user and retention measurements.</li></ul></li><li>If post-reinstall events are attributed to the first install, they're always included. <Anchor target="_blank" href="/marketers/docs/unique-users">Learn more</Anchor></li></ul> |

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/combine-cost-etl-and-cohort-reports-via-data-locker">Combine Cost ETL and Advanced aggregated cohort reports</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/cohort-and-retention-dashboard">Cohort dashboard</Anchor>

<div data-zendesk-anchors="h_01HWWH83KNSF4BRGTDJ0JD271G=advanced-aggregated-reports-in-data-locker h_01HWWH83KN9CM7ZY43W01AV6TA=setup h_01HWWNY76W6RFKX33MXHE4GSBD=reports-available h_01HWWNR256DRMBNFX3NV8ATNAY=cohort-versioned-report h_01HVRBVXS47K91A6KVV33S1BY6=report-facts h_01HWWH83KNE46SPK1MS99XX64D=report-structure 01H7WG3CA14PQ2PJ58FX8TE6ZH=dimensions 01H7WG3CA24VQKFVP99S82GCXZ=metrics h_01HVRDKKQA17SMJFFAEDG7A2X2=directory-and-filename-structure the-report-folder-hierarchy-in-aws=report-folder-hierarchy h_01HETBAQVVA750VTE1ABSM2M47=report-folder-hierarchy h_01HWWH83KN51RR2VJ2F5N8YQ3J=report-versions-and-data-freshness h_01HWWNVFCWJ7DZCKKKSBMH9NM5=cohort-timezone-versioned-report report-facts::15e071f=report-facts-1 h_01HWWH83KNPZETHR2TQS2E4QNT=report-facts-1 report-structure::43ffff28=report-structure-1 h_01HWWH83KNG0V2ZMZZ7CTV2GE7=report-structure-1 01HWSX3FA0K39D9M5RQ7J36Q23=dimensions-1 01HWSX3FA035Z8W6EPV4Q6E3JP=metrics-1 01HWSX3FA189EMBJZ1P21YHC45=directory-and-filename-structure-1 01HX97NC4F2WCJABSM2NBSBEDN=report-folder-hierarchy-1 report-versions-and-data-freshness::e0755e26=report-versions-and-data-freshness-1 h_01HWWH83KPS2ANCQKS2B3V529Z=report-versions-and-data-freshness-1 h_01HWWH83KPK8535X9EBZVJ9SQK=additional-information h_01HWWN6GAAD75HPC5GTE40QA37=timezone-geos 01H7WG3CA2C3HV8YT5ZMP9E0QY=bi-developer-considerations 01H7WG3CA2YF03SC6RBMCJYYVX=use-cases 1-Calculate-retention=1-calculate-retention h_01HMTZ0DZWN54HBQ0ZTY0VFNFM=1-calculate-retention 2-Calculate-arpu-of-multiple-inapp-events=2-calculate-arpu-of-multiple-in-app-events h_01HMTZ0DZWHZ77RYWYAQEJV7X5=2-calculate-arpu-of-multiple-in-app-events 3-Calculate-inapp-event-conversion-rate-for-a-specific-cohort-day=3-calculate-in-app-event-conversion-rate-for-a-specific-cohort-day h_01HMTZ0DZW7VA6T6MQY7BY1JZT=3-calculate-in-app-event-conversion-rate-for-a-specific-cohort-day 4-Calculate-daily-installs=4-calculate-daily-installs h_01HMTZ0DZWARZFAQ9R4VF56YN3=4-calculate-daily-installs 5-Calculate-revenue-from-facebook-ads=5-calculate-revenue-from-facebook-ads h_01HMTZ0DZW74HWW6Z3VDWDMGRF=5-calculate-revenue-from-facebook-ads 6-Calculate-arpu-per-asa-keyword-id-for-up-to-365-cohort-days=6-calculate-arpu-per-asa-keyword-id-for-up-to-365-cohort-days h_01HMTZ0DZWSN83V0TEHVM2H5XS=6-calculate-arpu-per-asa-keyword-id-for-up-to-365-cohort-days Calculate-arpu-days-0-7-by-attribution-time-per-geo=7-calculate-arpu-days-7-by-attribution-time-per-geo 01H8XYTJVQ1YFBHPWVPP9D7MJ8=7-calculate-arpu-days-7-by-attribution-time-per-geo h_01J7N4VB83T4KZ6G0Q634ASMHV=8-calculate-purchases-day-7-after-conversion h_01J55D2FFW0XSH3G6AXRS06RPV=9-calculate-dau 01H7WG3CA2Y59D2EVMN3YFFY1W=traits-and-limitations h_01HDNZ8A0QH74CGSEG6TKKARJP=see-also" />
