---
title: Calculate daily and monthly active users (DAU and MAU)
metadata:
  keywords:
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2025-09-15T15:49:21Z'
  edited_at: '2025-10-23T07:50:52Z'
  id: 39071744864657
  locale: en-us
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/39071744864657-Calculate-daily-and-monthly-active-users-DAU-and-MAU
---
> **At a glance:** Learn how to calculate Daily and Monthly active users to get valuable insights about your campaigns

## Overview

Daily Active Users (DAU) and Monthly Active Users (MAU) are key metrics for understanding app engagement and overall user behavior. They provide valuable insights into your active user base, including user stickiness, campaign performance, and growth trends over time.

This article explains how to calculate DAU and MAU using queries on two **Premium** Data Locker raw data tables that represent user acquisition and retargeting traffic: the `sessions` and `sessions_retargeting` tables.

> 📘 **Note**
>
> Starting February 2025, the Activity dashboard in AppsFlyer shows Unified (UA & Retargeting) data by default. You may notice a minor delta between raw data and dashboard numbers due to <Anchor target="_blank" href="/marketers/id/docs/activity-metrics-in-my-dashboards#specifications-and-limitations">approved algorithmic adjustments</Anchor>.

### Querying for active unique users

To calculate unique users, use the `advertising_id` as the primary identifier in your query. If the `advertising_id` is unavailable, substitute it with the `appsflyer_id`. This method applies only to apps configured in <Anchor target="_blank" href="/marketers/id/docs/measure-reinstalls#attributed-to-the-first-install">first-install mode</Anchor>.

For apps not using this mode, we recommend applying `count(distinct appsflyer_id)` instead.

## Calculate Daily Active Users (DAU)

Calculate the total number of unique users per day using the queries below.

<div id="query-for-dau---user-acquisition-ua" />

<Accordion title="Query for DAU – User Acquisition (UA)">

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

</Accordion>

<div id="query-for-dau---retargeting" />

<Accordion title="Query for DAU – Retargeting">

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

</Accordion>

<div id="query-for-dau---unified-ua-retargeting" />

<Accordion title="Query for DAU – Unified (UA & Retargeting)">

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

</Accordion>

## **Calculate Monthly Active Users (MAU)**

AppsFlyer dashboards present MAU in two ways:

1. **Active users in the last 31 days** – the number of unique active users in the last 31 days.
2. **Calendar month MAU** – the number of unique active users within a specific calendar month.

The queries below demonstrate how to calculate the first type of MAU. To calculate calendar month MAU instead, simply adjust the date range to match the desired month.

<div id="query-for-mau---user-acquisition-ua" />

<Accordion title="Query for MAU – User Acquisition (UA)">

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

</Accordion>

<div id="query-for-mau---retargeting" />

<Accordion title="Query for MAU – Retargeting">

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

</Accordion>

<div id="query-for-mau---unified-ua-retargeting" />

<Accordion title="Query for MAU – Unified (UA & Retargeting)">

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

</Accordion>

<div data-zendesk-anchors="h_01K58WFCYQJE3JVR6Q4G5P1T3V=overview h_01K58WFCYQSX0YTSGWBC02TCG1=note h_01K58WFCYQ942VY9P70GHVG6SH=querying-for-active-unique-users h_01K58WFCYQ406CW66EEYPP5GFJ=calculate-daily-active-users-dau query-for-dau-%E2%80%93-user-acquisition-ua=query-for-dau---user-acquisition-ua h_01K58WFCYQVXBZN97BWHA8FC3C=query-for-dau---user-acquisition-ua query-for-dau-%E2%80%93-retargeting=query-for-dau---retargeting h_01K58WFCYQ4XNKQ9CW4D3KV2E2=query-for-dau---retargeting query-for-dau-%E2%80%93-unified-ua-retargeting=query-for-dau---unified-ua-retargeting h_01K58WFCYQ0NM0E44531YDJBCH=query-for-dau---unified-ua-retargeting h_01K58WFCYQ251WMSNSD0EYXV69=calculate-monthly-active-users-mau query-for-mau-%E2%80%93-user-acquisition-ua=query-for-mau---user-acquisition-ua h_01K58WFCYQAV6T3S7SABSTMYKS=query-for-mau---user-acquisition-ua query-for-mau-%E2%80%93-retargeting=query-for-mau---retargeting h_01K58WFCYQ4H5CFQPPC5JQKHTJ=query-for-mau---retargeting query-for-mau-%E2%80%93-unified-ua-retargeting=query-for-mau---unified-ua-retargeting h_01K58WFCYQA1W91CHM1PN31MFG=query-for-mau---unified-ua-retargeting" />
