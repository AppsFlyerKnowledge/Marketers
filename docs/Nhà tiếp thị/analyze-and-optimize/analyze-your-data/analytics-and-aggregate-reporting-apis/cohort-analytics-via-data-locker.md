---
title: Cohort analytics via Data Locker
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2021-10-14T08:46:00Z'
  edited_at: '2025-03-10T14:46:25Z'
  id: 4408945472529
  locale: en-us
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4408945472529-Cohort-analytics-via-Data-Locker
---
> **At a glance**: Cohort analytics in Data Locker contains aggregated data of all elements in the advertising hierarchy. Reports contain data of users attributing in the previous 365 days. This report is available to advertisers who have raw data or Cohort API, or both as part of their subscription. It means that a Data Locker subscription isn't required for this report.

## Cohort analytics in Data Locker

In some cases, attribution raw data in AppsFlyer is <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">restricted</Anchor> due to media source data-sharing policies or your <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">privacy-preserving policies.</Anchor> The restriction includes all attribution-related fields like campaign and adset. Cohort reports provide you with aggregated data that can be used as an alternative to raw data.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ8q_4xv83wHkl4fs6jndEffRu-RHsPobBRfxDG-bUNXb0pOnvJH4QT0nXKdWvi3JPtVUBegTFbxIEe/pub?output=xlsx">Download example report</Anchor>

<div id="enable-data-locker" />

<Accordion title="Enable Data Locker">

The report is available to Data Locker, Cohort API, and raw data subscribers. To enable the report in <Anchor target="_blank" href="/marketers/vi/docs/data-locker-for-marketers">Data Locker,</Anchor> complete one of the following procedures.

| Do you currently get data via Data Locker? | Procedure |
| --- | --- |
| Yes | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/13d984aa18df9aacf5a8977c7dd3f8ca950df5a34e371014a72836981718399c-33338207213329.png)To add the Cohort reports to Data Locker:<ol><li>In AppsFlyer, from the side menu, select **Report > Data Locker**.</li><li>Select all the reports in the **Cohort analytics** section.</li><li>Click **Save configuration**.<br />The reports will be available on the next day by 10:00 UTC.</li></ol> |
| No | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/13d984aa18df9aacf5a8977c7dd3f8ca950df5a34e371014a72836981718399c-33338207213329.png)**To set up Data Locker**:<ol><li>Complete the first-time Data Locker ( <Anchor target="_blank" href="/marketers/vi/docs/data-locker-for-marketers#set-up-data-locker">advertiser</Anchor> \| <Anchor target="_blank" href="/partners/vi/docs/data-locker-for-partners">partner</Anchor> ) setup.</li><li>Add the Cohort reports to Data Locker:<ol><li>In AppsFlyer, from the side menu, select **Report > Data Locker**.</li><li>Select all the reports in the **Cohort analytics** section.</li><li>Click **Save configuration**.<br />The reports will be available on the next day by 10:00 UTC.</li></ol></li></ol> |

</Accordion>

You can load the data into your BI systems and use them as part of your campaign performance and optimization processes.

**Metrics available**

The metrics available are revenue, unique users performing an event and the number of event occurrences. To calculate cost-related metrics like ROI, and ROAS you need both revenue and cost metrics. Revenue metrics are in Cohort, and cost metrics are provided by <Anchor target="_blank" href="/marketers/vi/docs/set-up-and-use-roi360-cost-etl-reports">ROI360 Cost ETL</Anchor>.

<div id="facts" />

<Accordion title="Cohort analytics facts">

| Reports available | The following reports are available for download. The reports types are described in more detail in <Anchor target="_blank" href="/marketers/vi/docs/cohort-and-retention-dashboard#cohort-principles">Cohort dashboard.</Anchor><ul><li>**User acquisition:** attributed to a user acquisition media source including LTV occurring during re-engagement windows.</li><li>**Retargeting:** attributed to a retargeting media source for events occurring:<ul><li>During a re-engagement window</li><li>As a result of re-attributions</li></ul></li><li>**Unified:** display data under the last touch media source bringing the user according to AppsFlyer <Anchor target="_blank" href="/marketers/vi/docs/resolve-retargeting-double-attribution">double attribution</Anchor> rules. Meaning that LTV occurring during re-engagements displays under the retargeting media source and not under the UA media source.</li></ul> |
| --- | --- |
| Reporting period | Users converting during the previous 365 days. In other words, each day the reports include the user converting during the previous 365 days. |
| Report structure | The schema of each report (the dimensions and metrics included) is fixed and can't be edited. See [report structure](/docs/cohort-analytics-via-data-locker#report-structure). |
| Report delivery | See [Enable Cohort reports in Data Locker](/docs/cohort-analytics-via-data-locker#enable-data-locker). |
| Data freshness | <ul><li>Daily.</li><li>Metrics are calculated using data available at midnight UTC. In other words, at the end of the day.</li><li>Reports are available in Data Locker in the date-time (dt) folder by 10:00 UTC. For example, Monday's data is available on Tuesday at 10:00 UTC in the Monday folder.</li></ul> |
| Impact of partner retention policies | Consider that some partners implement a data retention policy. In this case, events occurring after the end of the retention period are considered organic in the Cohort reports.<br /><br />Example: SRN A has a data retention policy of 180 days. User events until day 180 are attributed to SRN A. Events that occur after 180 days are considered organic. |

</Accordion>

<div id="report-structure" />

<Accordion title="Report structure">

The report is comprised of dimensions and metrics.

The format of the fields is as follows:

* **Dimensions**: String. The maximum length of the string is dynamic and in most instances depends on how you populate the elements of the advertising hierarchy
* **Metrics**: Number. **Note:** The selected\_currency field format is a string.

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
      <td>
        --
      </td>
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td>
        --
      </td>
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
        Identifies the event. Some event names have a specific meaning while others relate to in-app events set by the advertiser in the app.

        | event\_name | What did the user do |
        | --- | --- |
        | af\_conversion | User converted. Use conversion\_type to identify if it is an install, re-engagement, or re-attribution. |
        | af\_session | Opened the app |
        | cohort\_uninstalls | Uninstalled the app |
        | Advertiser defined in-app event | Performed an in-app event in the app |
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
        Android apps only: The Android store from where the app was downloaded. Populated by advertisers implementing <Anchor target="_blank" href="/marketers/vi/docs/set-up-multi-store-android-attribution">multi-store Android attribution</Anchor>. If blank, it means Google Play Store.
      </td>
    </tr>
    <tr>
      <td>
        keywords
      </td>
      <td>
        Word(s) used in the user's online search. As reported by the ad network
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        [Field available starting April 27, 2022] Keyword ID returned by the ad network.
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

</Accordion>

<div id="bi-developer-considerations" />

<Accordion title="BI developer considerations">

**Scope of data in the report**

The reports contain user acquisition installs and retargeting re-attributions and re-engagements, and their related in-app events.

You can load unified, user acquisition, and retargeting reports separately or together into your BI. If you load them together and want to filter the views on your own:

* For unified, use the is\_primary\_attribution=true or null field.
* For user acquisition, use conversion\_type=Install.
* For retargeting, use conversion\_type=re-engagement or re-attribution.

If you just use the unified view in your data loading process, you can use logic to split the data between campaign types, which means, user attribution (installs) and retargeting (re-engagements). To do so, use the conversion\_type=install, install\_unified, re-engagement, or re-attribution. See <Anchor target="_blank" href="/marketers/vi/docs/resolve-retargeting-double-attribution">Double attribution of retargeting events.</Anchor>

**Field-level considerations**

* Use post-attribution days to enable easy calculation of retention metrics.
* Calculating unique users using campaign name and campaign ID dimensions: If you can disregard campaign name granularity, you can sum unique count on campaign ID and the metrics are correct.
* You can aggregate the data using the campaign hierarchy fields.
* Revenue in USD is calculated using the exchange rate on the event day.
* Ad revenue events are included where available but can update with a lag of up to 3 days.

**General considerations**

The data of all apps is provided in a single file. Use the App ID field to segregate data per app or set Data Locker to segregate by app.

</Accordion>

<div id="use-cases" />

<Accordion title="Use cases">

The following are examples of some popular, practical applications of Cohort data that BI developers can extract via Data Locker. Each example is illustrated by an SQL statement and sample Excel visual.

#### **1. Calculating retention**

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

#### **2. Calculating ARPU of multiple in-app events**

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

#### **3. Calculating in-app event conversion rate for a specific cohort day**

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

#### **4. Calculating daily installs**

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

#### **5. Calculating revenue from Facebook Ads**

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

#### **6. Calculating ARPU per ASA keyword ID for up to 365 cohort days**

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

#### **7. Calculating ARPU Days 7 by attribution time per geo**

The following example illustrates how to use <Anchor target="_blank" href="/marketers/vi/docs/cohort-and-retention-dashboard#trend-type-kpi-by-attribution-time">KPIs by attribution time</Anchor>. In the example, we:

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

</Accordion>

## Additional information

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait |  |
| --- | --- |
| Cost data | <ul><li>Not available. <Anchor target="_blank" href="/marketers/vi/docs/set-up-and-use-roi360-cost-etl-reports">Use Cost ETL</Anchor>.</li><li>See also <Anchor target="_blank" href="/marketers/vi/docs/combine-cost-etl-and-cohort-reports-via-data-locker">combine Cost ETL with cohort reports</Anchor>.</li></ul> |
| Campaign name changes | Not supported. |
| Data freshness | Daily UTC. Reports are in the Data Locker date-time (dt) folder of the reporting day by 10:00 UTC of the next day. |
| Ad revenue | <ul><li>Available</li><li>For af\_ad\_revenue events, the unique users metric isn't available for dates between October 5, 2022-February 16, 2023.</li></ul> |
| Currency | USD and app-specific currency are both available per row |
| Timezone | <ul><li>UTC</li><li>App-specific timezone is available with the <Anchor target="_blank" href="/marketers/vi/docs/advanced-aggregated-reports-in-data-locker">Advanced aggregated cohort timezone versioned report</Anchor>.</li></ul> |
| Organic data | Available |
| Days post-conversion (install, re-attribution, re-engagement) | <ul><li>365 days of post-install data is available.</li><li>1,095 days is available with <Anchor target="_blank" href="/marketers/vi/docs/advanced-aggregated-reports-in-data-locker">advanced aggregated reports</Anchor>.</li></ul> |
| Agency transparency | <ul><li>Supported</li><li>X Ads and Meta ads data is always transparent</li></ul> |
| App segregation | Supported |
| SKAN data | Not included. Meaning, the data provided by iOS postbacks. |
| Reinstalls | <ul><li>If post-reinstall events are considered unattributed organic:<ul><li>They're included only as of May 26, 2024. <Anchor target="_blank" href="/marketers/vi/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">Learn more</Anchor></li><li>The install time is based on the <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor> field.</li><li>They aren't counted toward unique user and retention measurements.</li></ul></li><li>If post-reinstall events are attributed to the first install, they're always included. <Anchor target="_blank" href="/marketers/vi/docs/unique-users">Learn more</Anchor></li></ul> |

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/combine-cost-etl-and-cohort-reports-via-data-locker">Combine Cost ETL and cohort reports</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/cohort-and-retention-dashboard">Cohort dashboard</Anchor>

<div data-zendesk-anchors="01H7WG3CA1DDAN79D1PBPE0RJ3=cohort-analytics-in-data-locker 01H7WG3CA1ZMNTGZ5B8FNXNC4A=enable-data-locker 01H7WG3CA179D6VCWYPCJ1G49M=facts 01H7WG3CA1R3PZCKSGWC90E7RC=report-structure 01H7WG3CA14PQ2PJ58FX8TE6ZH=dimensions 01H7WG3CA24VQKFVP99S82GCXZ=metrics 01H7WG3CA2C3HV8YT5ZMP9E0QY=bi-developer-considerations 01H7WG3CA2YF03SC6RBMCJYYVX=use-cases h_01HMTZ0DZWN54HBQ0ZTY0VFNFM=1-calculating-retention 2-calculating-arpu-of-multiple-inapp-events=2-calculating-arpu-of-multiple-in-app-events h_01HMTZ0DZWHZ77RYWYAQEJV7X5=2-calculating-arpu-of-multiple-in-app-events 3-calculating-inapp-event-conversion-rate-for-a-specific-cohort-day=3-calculating-in-app-event-conversion-rate-for-a-specific-cohort-day h_01HMTZ0DZW7VA6T6MQY7BY1JZT=3-calculating-in-app-event-conversion-rate-for-a-specific-cohort-day h_01HMTZ0DZWARZFAQ9R4VF56YN3=4-calculating-daily-installs h_01HMTZ0DZW74HWW6Z3VDWDMGRF=5-calculating-revenue-from-facebook-ads h_01HMTZ0DZWSN83V0TEHVM2H5XS=6-calculating-arpu-per-asa-keyword-id-for-up-to-365-cohort-days calculating-arpu-days-0-7-by-attribution-time-per-geo=7-calculating-arpu-days-7-by-attribution-time-per-geo 01H8XYTJVQ1YFBHPWVPP9D7MJ8=7-calculating-arpu-days-7-by-attribution-time-per-geo 01H7WG3CA255TG9HW150RW1QTX=additional-information 01H7WG3CA2Y59D2EVMN3YFFY1W=traits-and-limitations h_01HDNZ8A0QH74CGSEG6TKKARJP=see-also" />
