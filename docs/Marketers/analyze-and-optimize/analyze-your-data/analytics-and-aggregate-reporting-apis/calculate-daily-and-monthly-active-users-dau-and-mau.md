---
title: "Calculate daily and monthly active users (DAU and MAU)"
excerpt: "Learn how to calculate Daily and Monthly active users to get valuable insights about your campaigns"
x-zendesk:
  id: 39071744864657
  url: https://support.appsflyer.com/hc/en-us/articles/39071744864657-Calculate-daily-and-monthly-active-users-DAU-and-MAU
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  position: 0
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-nohar-avigal, Marketers, Marketing Analytics]
  labels: []
  promoted: false
  comments_disabled: false
  created_at: '2025-09-15T15:49:21Z'
  edited_at: '2025-10-23T07:50:52Z'
---
Daily Active Users (DAU) and Monthly Active Users (MAU) are key metrics for understanding app engagement and overall user behavior. They provide valuable insights into your active user base, including user stickiness, campaign performance, and growth trends over time.

This article explains how to calculate DAU and MAU using queries on two **Premium** Data Locker raw data tables that represent user acquisition and retargeting traffic: the `sessions` and `sessions_retargeting` tables.

> 📘 Note
>
> Starting February 2025, the Activity dashboard in AppsFlyer shows Unified (UA & Retargeting) data by default. You may notice a minor delta between raw data and dashboard numbers due to [approved algorithmic adjustments](/docs/activity-metrics-in-my-dashboards#specifications-and-limitations).

### Querying for active unique users

To calculate unique users, use the `advertising_id` as the primary identifier in your query. If the `advertising_id` is unavailable, substitute it with the `appsflyer_id`. This method applies only to apps configured in [first-install mode](/docs/measure-reinstalls#attributed-to-the-first-install).

For apps not using this mode, we recommend applying `count(distinct appsflyer_id)` instead.

## Calculate Daily Active Users (DAU)

Calculate the total number of unique users per day using the queries below.

<Tabs>
<Tab title="User Acquisition (UA)">

Select active UA users for a specified day.

```sql
WITH sessions_cleaned AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions
    WHERE app_id = 'your.app.id.here'                      -- Replace with your app ID
		    AND SUBSTR(event_time, 1, 10) = 'YYYY-MM-DD'       -- Target date
)

SELECT COUNT(DISTINCT user_id) AS dau_ua
FROM sessions_cleaned;
```

</Tab>
<Tab title="Retargeting">

Select active retargeting users for a specified day.

```sql
WITH sessions_retargeting_cleaned AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions_retargeting
    WHERE app_id = 'your.app.id.here'                      -- Replace with your app ID
		    AND SUBSTR(event_time, 1, 10) = 'YYYY-MM-DD'   -- Target date
)
SELECT COUNT(DISTINCT user_id) AS dau_retargeting
FROM sessions_retargeting_cleaned;
```

</Tab>
<Tab title="Unified (UA & Retargeting)">

Select active UA and retargeting users for a specified day.

To get complete active user coverage, you must **union** the `sessions` and `sessions_retargeting` tables. Make sure the fields are aligned — typically by `app_id`, `event_time`, `advertising_id` and `appsflyer_id`. If needed, normalize the schema so that both tables have consistent column names.

```sql
WITH ua_sessions AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions
    WHERE app_id = 'your.app.id.here'                 -- Replace with your app ID
      AND SUBSTR(event_time, 1, 10) = 'YYYY-MM-DD'    -- Target date
      AND is_primary_attribution = TRUE
),

retargeting_sessions AS ( 
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions_retargeting
    WHERE app_id = 'your.app.id.here'                  -- Same app
      AND SUBSTR(event_time, 1, 10) = 'YYYY-MM-DD'     -- Same date
),

all_sessions AS (
    SELECT * FROM ua_sessions
    UNION ALL
    SELECT * FROM retargeting_sessions
)

SELECT COUNT(DISTINCT user_id) AS dau_unified
FROM all_sessions;
```

</Tab>
</Tabs>

## Calculate Monthly Active Users (MAU)

AppsFlyer dashboards present MAU in two ways:

1. **Active users in the last 31 days** – the number of unique active users in the last 31 days.
2. **Calendar month MAU** – the number of unique active users within a specific calendar month.

The queries below demonstrate how to calculate the first type of MAU. To calculate calendar month MAU instead, simply adjust the date range to match the desired month.

<Tabs>
<Tab title="User Acquisition (UA)">

Select active UA users for a specified month.

```sql
WITH sessions_cleaned AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions
    WHERE app_id = 'your.app.id.here'  -- Replace with your app ID
			AND DATE_DIFF('day', TRY_CAST(SUBSTR(event_time, 1, 10) AS DATE), DATE('YYYY-MM-DD')) <= 31  -- Replace with target end date
)
SELECT COUNT(DISTINCT user_id) AS mau_ua
FROM sessions_cleaned;
```

</Tab>
<Tab title="Retargeting">

Select active retargeting users for a specified month.

```sql
WITH sessions_cleaned AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions_retargeting
    WHERE app_id = 'your.app.id.here'  -- Replace with your app ID
			AND DATE_DIFF('day', TRY_CAST(SUBSTR(event_time, 1, 10) AS DATE), DATE('YYYY-MM-DD')) <= 31  -- Replace with target end date
)

SELECT COUNT(DISTINCT user_id) AS mau_retargeting
FROM sessions_cleaned;
```

</Tab>
<Tab title="Unified (UA & Retargeting)">

Select active UA and retargeting users for a specified month.

To get complete active user coverage, you must **union** the `sessions` and `sessions_retargeting` tables. Make sure the fields are aligned — typically by `app_id`, `event_time`, `advertising_id` and `appsflyer_id`. If needed, normalize the schema so that both tables have consistent column names.

```sql
WITH ua_sessions AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions
    WHERE app_id = 'your.app.id.here'                        -- Replace with your app ID
      AND DATE_DIFF('day', TRY_CAST(SUBSTR(event_time, 1, 10) AS DATE), DATE('YYYY-MM-DD')) <= 31  -- Replace with target end date
      AND is_primary_attribution = TRUE
),

retargeting_sessions AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions_retargeting
    WHERE app_id = 'your.app.id.here'                        -- Same app
      AND DATE_DIFF('day', TRY_CAST(SUBSTR(event_time, 1, 10) AS DATE), DATE('YYYY-MM-DD')) <= 31  -- Replace with target end date
),

all_sessions AS (
    SELECT * FROM ua_sessions
    UNION ALL
    SELECT * FROM retargeting_sessions
)

SELECT COUNT(DISTINCT user_id) AS mau_unified
FROM all_sessions;
```

</Tab>
</Tabs>