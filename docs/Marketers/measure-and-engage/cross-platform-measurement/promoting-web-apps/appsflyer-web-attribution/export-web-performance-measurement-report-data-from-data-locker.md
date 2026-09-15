---
title: "Export Web Performance Measurement report data from Data Locker"
excerpt: "Export Web Performance Measurement data from Data Locker in two report types that enable you to analyze website performance at the right level."
---
At a glance: Export Web Performance Measurement data from Data Locker in two report types that enable you to analyze website performance at the right level. Use End User Events to analyze all visits and events, and use Conversions to count and attribute unique conversion anchors (first visits, revisits, and user-acquisition events).

> ❗️ Important
>
> You must have a Data Locker subscription to use the Web Performance Measurement reports in Data Locker.

## About the Web Performance Measurement reports

Data Locker provides two reports for Web Performance Measurement, **End User Events**, and **Conversions,** each designed for different analysis needs.

- The **End User Events** report is the primary source for analyzing website activity:
  - Includes **every web event and visit**
  - Records each visit as an attributed `SESSION`
  - Ideal for **visit-level** and **event-level** reporting
- The **Conversions** report is best for conversion-level analysis. A conversion is an attribution anchor, a touchpoint that determines when and how to assign marketing credit. This includes:
  - *first visits* (when a user arrives at your website for the first time),
  - *revisits* (when a user returns after a non-organic ad engagement), and
  - *user-acquisition events* (custom events such as sign-up or first deposit) that indicate a user has been acquired.
- All user events are later linked to these conversions and inherit their campaign details

The Data Locker Advanced Reports interface also lists **Engagements** and **End User Events Cross-Platform** as separate Web Performance Measurement report options. This article covers **End User Events** and **Conversions**, the two reports used for most Web Performance Measurement analysis.

## Select a Web Performance Measurement report

Before you export Web Performance Measurement data, select the relevant report in Data Locker.

1. In AppsFlyer, from the side menu, select **Export > Data Locker**.
2. Click the **Advanced Reports** tab.
3. Select **End User Events** or **Conversions** from the list of Web Performance Measurement reports.
4. Click **Save configuration**.

## Report fields

To learn which fields are contained in the reports, download a sample for each report:

- [End User events report sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vQYFF0r4pMpo_voSK8QObpiRtx-diU_0a-0XVuKIVMEfh6rRPudIDXA5bgDw_lcc0qwBPcPhYtLdWwh/pub?output=csv)
- [Conversion events report sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vTMqcc6PKBATBg1DYVO8MWKrAs_wlqXxyANe3a_gu62xp3hFZV9wWT1X8c9oRekaIEwCfKZ2y9agVeV/pub?output=csv)

The sample report includes all report fields and their values. For the definitions of the fields, see [the field dictionary](/docs/raw-data-field-dictionary).

## Report timing and data freshness

Use these details to understand when new data is added and when recent events become available in the report.

- **Report frequency**: New data is added every hour.
- **Data freshness**: Events typically appear in the report within 2 to 3 hours of occurrence.

### Here’s how each batch works:

- Each batch **processes** events from a 1.5-hour window.
- Within that window, only the first hour of events is **attributed**.
- The remaining 30 minutes are used **solely to enrich** attributed events with Customer User IDs (CUIDs).
- The most recent 30 minutes of events are **not attributed yet**—they’ll be included in the next batch.

### When will these events appear in the report?

Events are written to reports **after processing finishes**. So, for example, events from **08:00–09:00**, attributed in the 10:00 AM batch, will appear in the **11:00 AM report version**.

### Example: What the 10:00 AM batch does

| **Date** | **Report available at** | **Web events attributed (event time)** | **Web events processed to enrich earlier events with CUIDs** |
| --- | --- | --- | --- |
| 2026-01-28 | 11:00 | 08:00 – 09:00 | 09:00–09:30 |
| 2026-01-28 | 12:00 | 09:00 – 10:00 | 10:00–10:30 |
| 2026-01-28 | 13:00 | 10:00 – 11:00 | 10:00-11:30 |

## Download report data from your cloud bucket

For more information on how to download report data from your cloud bucket, see [the Data Locker Folder structure](/docs/data-locker-for-marketers#folder-structure).

## BI developer considerations

Key differences: Web vs. Mobile

Web attribution differs from mobile attribution in both the identifiers and the data logic. To improve data accuracy, apply the following filters and best practices in your queries.

| Aspect | Mobile | Web |
| --- | --- | --- |
| Platform filter | `platform = 'IOS'` or `platform = 'ANDROID’` | `platform = 'WEBSITE'` |
| User identifier (value) | `appsflyer_id` (device-based) | `appsflyer_id_value` (cookie-based) |
| Identifier type | Varies according to device | `appsflyer_id_type` is always `web_id` |
| Acquisition event | Install | First Visit is the default, but the user acquisition event may be customized |
| Re-engagement | `RE-ENGAGEMENT` | `REVISIT` |
| Re-attribution | Supported | Not supported - web only has User Acquisition and Re-visits |
| App ID | App ID (for example, `id123456789`) | Domain with prefix (for example, `website-www.example.com`) |

Which table to query?

The **End User Events** report is suitable for most analyses. It includes every website event and visit. Each web visit is also recorded as an attributed `SESSION` in this report, making it the primary source for visit-level and event-level reporting.

The **Conversions** table is suitable mainly for counting first visits, revisits, and user acquisitions when you need unique conversions without duplicate event records.

| Use case | Table | Why |
| --- | --- | --- |
| Count visits/sessions | `end_user_events` | Each row is a session or event |
| Count unique conversions | `conversions` | Avoids duplicates |
| Analyze in-app events | `end_user_events` with `end_user_event_type = 'IN_APP'` | Only in-app events have event names |

Implement query filters

Apply the following filters to make sure your raw data queries are accurate. Failing to implement these will result in duplicate entries and mixed-platform metrics.

- **Filter by Platform (mandatory):** Include `WHERE platform = 'WEBSITE'` to isolate web-originated data and exclude records from mobile, PC, or CTV environments.
- **Filter by Attribution Credit (mandatory):** The same user action can appear twice in `end_user_events` because AppsFlyer can assign two different attribution credits to it, depending on the reporting view.

This can happen when the user has:

  - an original **User Acquisition (UA)** source, and later
  - a **re-engagement** source.

In that case, AppsFlyer may write two records for the same event:
  - **Primary credit:** Attributes the event to the most recent relevant marketing interaction. Used in Unified and Retargeting views.

    To avoid double-counting, query `end_user_events` using only the primary credit record by default:

    ```sql
    WHERE platform = 'WEBSITE'
      AND is_primary_attribution = true
    ```

  - **Secondary credit:** Attributes the event back to the original UA source. Used in the User Acquisition view for lifetime value (LTV) measurement.

    Because the same user action can be stored as two records (one with primary credit and one with secondary credit), counting events without a filter can double-count that action.

    Use these queries as templates to analyze web attribution data in BigQuery or other BI tools.

- **Filter by Conversion Type (optional):** Include `WHERE conversion_type = 'USER_ACQUISITION'` or `WHERE conversion_type = 'RETARGETING'` to isolate attribution data based on campaign type.

#### Filter Summary table

| Filter Requirement | SQL Logic | Implementation Context |
| --- | --- | --- |
| Platform Specification | `WHERE platform = 'WEBSITE'` | Isolates web-originated data from other platform records. |
| Unified view (Avoid Duplicates) | `WHERE is_primary_attribution = true AND platform = 'WEBSITE'` | Prioritize the credit for retargeting campaign over the original UA camapign. Use for general reporting to avoid double-counting. |
| Retargeting View Only | `WHERE conversion_type = 'RETARGETING' AND platform = 'WEBSITE'` | Use specifically when analyzing performance for retargeting campaigns only. |
| User Acquisition View Only | `WHERE conversion_type = 'USER_ACQUISITION' AND platform = 'WEBSITE'` | Use specifically for acquisition-focused views where events must be tied to the initial visit. |

Identifying and counting end users

In Web Performance Measurement raw data, an end user can appear under two different identifiers:

- `customer_user_id`: A stable identifier you set (typically for logged-in users).
- `appsflyer_id_value`: A cookie-based ID that can expire over time.

To correctly identify **unique users** and calculate **user-level metrics**, always use:

```sql
COALESCE(customer_user_id, appsflyer_id_value)
```

Here’s how it works:

- If `customer_user_id` exists, AppsFlyer uses it (preferred, stable).
- If it doesn’t, AppsFlyer falls back to `appsflyer_id_value`.

Use `COALESCE(customer_user_id, appsflyer_id_value)` whenever you need to:

- Count distinct users
- Group by user
- Filter by specific users
- Join tables by user
- Calculate any user-level metrics

#### Example: Count distinct users

```sql
SELECT
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS unique_users
FROM `end_user_events`
WHERE platform = 'WEBSITE'
  AND is_primary_attribution = TRUE
```

Organic vs. Non-organic traffic

Use the `is_organic` field:

| Traffic type | Filter |
| --- | --- |
| Organic | `is_organic = true` |
| Non-organic | `is_organic = false` |

Handling empty values

| Data type | Empty value |
| --- | --- |
| String | `''` (empty string) |
| Numeric | `NULL` |

Query examples

1\. Total visits by media source (7 days)

Counts web sessions attributed to each media source.

```sql
SELECT media_source, COUNT(*) AS total_visits
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND end_user_event_type = 'SESSION'
GROUP BY media_source
ORDER BY total_visits DESC
```

2\. First visits and re-visits by campaign

```sql
SELECT campaign_name, conversion_name, COUNT(*) AS conversion_count
FROM conversions
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND conversion_name IN ('FIRST_VISIT', 'REVISIT')
GROUP BY campaign_name, conversion_name
ORDER BY conversion_count DESC
```

3\. Count distinct event names (in-app events only)

```sql
SELECT
  event_name,
  COUNT(*) AS event_count
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND end_user_event_type = 'IN_APP'
GROUP BY event_name
ORDER BY event_count DESC
```

4\. Count distinct users by media source

```sql
SELECT
  media_source,
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS unique_users
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
GROUP BY media_source
ORDER BY unique_users DESC
```

5\. Conversion rate - First Visit to Purchase (cross-table join)

```sql
WITH first_visits AS (
  SELECT
    COALESCE(customer_user_id, appsflyer_id_value) AS user_id,
    media_source
  FROM conversions
  WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
    AND platform = 'WEBSITE'
    AND unified_app_id = 'website-example.com'
    AND conversion_name = 'FIRST_VISIT'
),
purchases AS (
  SELECT DISTINCT
    COALESCE(customer_user_id, appsflyer_id_value) AS user_id
  FROM end_user_events
  WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
    AND platform = 'WEBSITE'
    AND unified_app_id = 'website-example.com'
    AND is_primary_attribution = true
    AND end_user_event_type = 'IN_APP'
    AND event_name = 'purchase'
)
SELECT
  fv.media_source,
  COUNT(DISTINCT fv.user_id) AS first_visit_users,
  COUNT(DISTINCT p.user_id) AS purchasers,
  SAFE_DIVIDE(COUNT(DISTINCT p.user_id), COUNT(DISTINCT fv.user_id)) AS conversion_rate
FROM first_visits fv
LEFT JOIN purchases p ON fv.user_id = p.user_id
GROUP BY fv.media_source
ORDER BY conversion_rate DESC
```

6\. Revenue by campaign (last 7 days)

```sql
SELECT
  campaign_name,
  media_source,
  SUM(revenue_usd) AS total_revenue_usd,
  COUNT(*) AS revenue_events
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND revenue_usd IS NOT NULL
  AND revenue_usd <> 0.0
GROUP BY campaign_name, media_source
ORDER BY total_revenue_usd DESC
```

7\. Organic vs. non-organic first visits by day

```sql
SELECT
  DATE(event_time) AS visit_date,
  CASE WHEN is_organic = true THEN 'Organic' ELSE 'Non-Organic' END AS traffic_type,
  COUNT(*) AS first_visits
FROM conversions
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND conversion_name = 'FIRST_VISIT'
GROUP BY visit_date, traffic_type
ORDER BY visit_date, traffic_type
```

8\. User Acquisition vs. Retargeting breakdown

```sql
SELECT
  conversion_type,
  conversion_name,
  COUNT(*) AS conversions
FROM conversions
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
GROUP BY conversion_type, conversion_name
ORDER BY conversions DESC
```

9\. Click ID distribution (Google, Meta, TikTok, etc.)

```sql
SELECT
  click_id_type,
  COUNT(*) AS events_with_click_id
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND click_id_type != ''
GROUP BY click_id_type
ORDER BY events_with_click_id DESC
```

10\. Cohort users by conversion date (equivalent to mobile install date)

```sql
SELECT
  DATE(event_time__conversion) AS cohort_date,
  media_source,
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS cohort_users
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
GROUP BY cohort_date, media_source
ORDER BY cohort_date, cohort_users DESC
```

## Traits and limitations

The following fields are **not supported for web data** and will always be empty:

| Trait | Description |
| --- | --- |
| `advertising_id_type`, `hardware_id_type`, etc. | Both |
| `agency`, `site_id`, `ad_type` | Both |
| `platform_group` | conversions |
| `app_version__conversion` | end_user_events |
| All `__assist_*` fields | conversions |

## See also

<Cards>
  <Card title="About Data Locker Advanced Reports" href="/docs/about-data-locker-advanced-reports" icon="fa-solid fa-box-archive">
    Learn more about Advanced Reports in Data Locker.
  </Card>
  <Card title="Data Locker for marketers" href="/docs/data-locker-for-marketers" icon="fa-solid fa-box-archive">
    Overview of Data Locker features and setup for marketers.
  </Card>
</Cards>