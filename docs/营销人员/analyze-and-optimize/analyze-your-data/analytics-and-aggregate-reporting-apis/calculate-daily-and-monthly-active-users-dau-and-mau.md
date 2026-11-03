---
title: 计算每日和每月活跃用户（DAU 和 MAU）
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
  edited_at: '2026-10-14T10:01:46Z'
  id: 39071744864657
  locale: zh-cn
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/zh-cn/articles/39071744864657
---
> **概要：** 学习如何计算每日和每月活跃用户，以获取有关您活动的有价值见解

## 概览

每日活跃用户（DAU）和每月活跃用户（MAU）是理解应用参与度和整体用户行为的关键指标。它们提供了有关您的活跃用户基础的有价值见解，包括用户粘性、活动表现和随时间的增长趋势。

本文解释了如何使用两个数据锁定原始数据表中的查询来计算 DAU 和 MAU，这些表代表用户获取和重定向流量：`sessions`和`sessions_retargeting`表。

> 📘 **注意**
>
> 从 2025 年 2 月开始，AppsFlyer 中的活动仪表板默认显示统一（UA 和重定向）数据。您可能会注意到原始数据和仪表板数字之间存在轻微差异，原因是 <Anchor target="_blank" href="/marketers/zh/docs/activity-metrics-in-my-dashboards#特点与局限性">批准的算法调整</Anchor>。

### 查询活跃的独立用户

要计算独立用户，请在查询中使用 `advertising_id` 作为主要标识符。如果 `advertising_id` 不可用，请用 `appsflyer_id` 替代。此方法仅适用于配置为 <Anchor target="_blank" href="/marketers/zh/docs/measure-reinstalls#attributed-to-the-first-install">首次安装模式</Anchor> 的应用。

对于不使用此模式的应用，我们建议改用 `count(distinct appsflyer_id)`。

## 计算每日活跃用户（DAU）

使用以下查询计算每日独立用户的总数。

<div id="query-for-dau---user-acquisition-ua" />

<Accordion title="查询 DAU – 用户获取（UA）">

选择指定日期的活跃 UA 用户。

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

<Accordion title="查询 DAU – 重定向">

选择指定日期的活跃重定向用户。

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

<Accordion title="查询 DAU – 统一（UA 和重定向）">

选择指定日期的活跃 UA 和重定向用户。

要获得完整的活跃用户覆盖，您必须 **联合** `sessions` 和 `sessions_retargeting` 表格确保字段对齐 — 通常通过 及如果 需要时，规范化架构，以便两个表具有一致的 字段名称

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

## **计算月活跃用户 (MAU)**

AppsFlyer 仪表板以两种方式呈现 MAU：

1. **过去 31 天的活跃用户** – 过去 31 天内的独立活跃用户数量。
2. **日历月 MAU** – 在特定日历月内的独立活跃用户数量。

下面的查询演示了如何计算第一种类型的 MAU。要计算日历月 MAU，只需调整日期范围以匹配所需的月份。

<div id="query-for-mau---user-acquisition-ua" />

<Accordion title="MAU 查询 – 用户获取 (UA)">

选择指定月份的活跃 UA 用户。

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

<Accordion title="MAU 查询 – 再营销">

选择指定月份的活跃再营销用户。

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

<Accordion title="MAU 查询 – 统一 (UA & 再营销)">

选择指定月份的活跃 UA 和再营销用户。

要获得完整的活跃用户覆盖，您必须 **联合** `sessions` 和 `sessions_retargeting` 表格确保字段对齐 — 通常通过 及如果 需要时，规范化架构，以便两个表具有一致的 字段名称

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

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 h_01K58WFCYQJE3JVR6Q4G5P1T3V=%E6%A6%82%E8%A7%88 h_01K58WFCYQSX0YTSGWBC02TCG1=%E6%B3%A8%E6%84%8F querying-for-active-unique-users=%E6%9F%A5%E8%AF%A2%E6%B4%BB%E8%B7%83%E7%9A%84%E7%8B%AC%E7%AB%8B%E7%94%A8%E6%88%B7 h_01K58WFCYQ942VY9P70GHVG6SH=%E6%9F%A5%E8%AF%A2%E6%B4%BB%E8%B7%83%E7%9A%84%E7%8B%AC%E7%AB%8B%E7%94%A8%E6%88%B7 calculate-daily-active-users-dau=%E8%AE%A1%E7%AE%97%E6%AF%8F%E6%97%A5%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7dau h_01K58WFCYQ406CW66EEYPP5GFJ=%E8%AE%A1%E7%AE%97%E6%AF%8F%E6%97%A5%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7dau query-for-dau-%E2%80%93-user-acquisition-ua=query-for-dau---user-acquisition-ua h_01K58WFCYQVXBZN97BWHA8FC3C=query-for-dau---user-acquisition-ua query-for-dau-%E2%80%93-retargeting=query-for-dau---retargeting h_01K58WFCYQ4XNKQ9CW4D3KV2E2=query-for-dau---retargeting query-for-dau-%E2%80%93-unified-ua-retargeting=query-for-dau---unified-ua-retargeting h_01K58WFCYQ0NM0E44531YDJBCH=query-for-dau---unified-ua-retargeting calculate-monthly-active-users-mau=%E8%AE%A1%E7%AE%97%E6%9C%88%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7-mau h_01K58WFCYQ251WMSNSD0EYXV69=%E8%AE%A1%E7%AE%97%E6%9C%88%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7-mau query-for-mau-%E2%80%93-user-acquisition-ua=query-for-mau---user-acquisition-ua h_01K58WFCYQAV6T3S7SABSTMYKS=query-for-mau---user-acquisition-ua query-for-mau-%E2%80%93-retargeting=query-for-mau---retargeting h_01K58WFCYQ4H5CFQPPC5JQKHTJ=query-for-mau---retargeting query-for-mau-%E2%80%93-unified-ua-retargeting=query-for-mau---unified-ua-retargeting h_01K58WFCYQA1W91CHM1PN31MFG=query-for-mau---unified-ua-retargeting" />
