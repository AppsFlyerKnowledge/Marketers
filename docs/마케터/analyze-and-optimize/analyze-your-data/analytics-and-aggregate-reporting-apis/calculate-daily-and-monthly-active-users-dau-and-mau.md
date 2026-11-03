---
title: 일일 및 월간 활성 사용자(Daily Active Users 및 Monthly Active Users) 계산
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
  edited_at: '2026-10-14T10:28:36Z'
  id: 39071744864657
  locale: ko
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ko/articles/39071744864657
---
> **한눈에 보기:** 캠페인에 대한 중요한 인사이트를 얻기 위해 일일 및 월간 활성 사용자를 계산하는 방법을 알아보세요.

## 개요

일일 활성 사용자(DAU) 및 월간 활성 사용자(MAU)는 앱 참여도와 전반적인 사용자 행동을 이해하는 데 있어 핵심 지표입니다. 이 데이터는 사용자의 충성도, 캠페인 성과 및 시간 경과에 따른 성장 추세를 포함하여 활성 사용자 기반을 이해하는 데 유용한 인사이트를 제공합니다.

이 문서에서는 사용자 유입 및 리타겟팅 트래픽을 나타내는 두 개의 Data Locker 로데이터 테이블인 `sessions` 및 `sessions_retargeting`에 쿼리를 실행하여 DAU 및 MAU를 계산하는 방법을 설명합니다.

> 📘 **참고**
>
> 2025년 2월부터 앱스플라이어의 활동 대시보드는 통합(UA 및 리타겟팅) 데이터를 표시합니다. <Anchor target="_blank" href="/marketers/ko/docs/activity-metrics-in-my-dashboards#사양-및-제한-사항">승인된 알고리즘 조정</Anchor>으로 인해 로데이터와 대시보드 숫자 사이에 약간의 차이가 있을 수 있습니다.

### 활성 고유 사용자 쿼리 실행

고유 사용자 수를 계산하려면 `advertising_id`을 쿼리의 기본 식별자로 사용하세요. `advertising_id`를 사용할 수 없는 경우, `appsflyer_id`으로 대체하세요. 이 방법은 <Anchor target="_blank" href="/marketers/ko/docs/measure-reinstalls#attributed-to-the-first-install">첫 인스톨 모드</Anchor>로 구성된 앱에만 적용됩니다.

이 모드를 사용하지 않는 앱의 경우 `count(distinct appsflyer_id)`을 적용하는 것이 좋습니다.

## 일일 활성 사용자(DAU) 계산

아래 쿼리를 사용하여 하루 동안의 고유 사용자 수를 계산합니다.

<div id="query-for-dau---user-acquisition-ua" />

<Accordion title="DAU용 쿼리 – 사용자 유입(UA)">

지정된 날짜의 활성 UA 사용자를 선택합니다.

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

<Accordion title="DAU용 쿼리 – 리타겟팅">

지정된 날짜의 활성 리타겟팅 사용자를 선택합니다.

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

<Accordion title="DAU용 쿼리 – 통합(UA 및 리타겟팅)">

지정된 날짜에 활성 UA 및 리타겟팅 사용자를 선택합니다.

활성 사용자를 완벽하게 포함하려면 테이블 `sessions` 와`sessions_retargeting`를 **통합**해야 합니다. 필드가 다음과 같이 정렬되어 있는지 확인하세요. `app_id`, `event_time`, `advertising_id`, 그리고 `appsflyer_id`. 필요에 따라 스키마를 정상화하여 두 테이블이 일관된 열 이름을 갖도록 하십시오.

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

## **월간 활성 유저 (MAU) 계산 방법**

AppsFlyer 대시보드는 MAU를 두 가지 방식으로 표시합니다.

1. **지난 31일 동안 활성 사용자** – 지난 31일 동안 고유 활성 사용자 수.
2. **캘린더 월 MAU** – 특정 달력월 내에서의 고유 활성 사용자 수.

아래 쿼리는 첫 번째 유형의 MAU를 계산하는 방법을 보여줍니다. 달력월 MAU를 계산하려면 원하는 달과 일치하도록 날짜 범위를 조정합니다.

<div id="query-for-mau---user-acquisition-ua" />

<Accordion title="MAU에 대한 쿼리 – 사용자 유입UA)">

지정된 월 동안 활성 UA 사용자를 선택합니다.

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

<Accordion title="MAU에 대한 쿼리 – 리타겟팅">

지정된 월 동안 활성 리타겟팅 사용자를 선택합니다.

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

<Accordion title="MAU에 대한 쿼리 – 통합(UA & 리타겟팅)">

지정된 월 동안 활성 UA 및 리타겟팅 사용자를 선택합니다.

활성 사용자를 완벽하게 포함하려면 테이블 `sessions` 와`sessions_retargeting`를 **통합**해야 합니다. 필드가 다음과 같이 정렬되어 있는지 확인하세요. `app_id`, `event_time`, `advertising_id`, 그리고 `appsflyer_id`. 필요에 따라 스키마를 정상화하여 두 테이블이 일관된 열 이름을 갖도록 하십시오.

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

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01K58WFCYQJE3JVR6Q4G5P1T3V=%EA%B0%9C%EC%9A%94 h_01K58WFCYQSX0YTSGWBC02TCG1=%EC%B0%B8%EA%B3%A0 querying-for-active-unique-users=%ED%99%9C%EC%84%B1-%EA%B3%A0%EC%9C%A0-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%BF%BC%EB%A6%AC-%EC%8B%A4%ED%96%89 h_01K58WFCYQ942VY9P70GHVG6SH=%ED%99%9C%EC%84%B1-%EA%B3%A0%EC%9C%A0-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%BF%BC%EB%A6%AC-%EC%8B%A4%ED%96%89 calculate-daily-active-users-dau=%EC%9D%BC%EC%9D%BC-%ED%99%9C%EC%84%B1-%EC%82%AC%EC%9A%A9%EC%9E%90dau-%EA%B3%84%EC%82%B0 h_01K58WFCYQ406CW66EEYPP5GFJ=%EC%9D%BC%EC%9D%BC-%ED%99%9C%EC%84%B1-%EC%82%AC%EC%9A%A9%EC%9E%90dau-%EA%B3%84%EC%82%B0 query-for-dau-%E2%80%93-user-acquisition-ua=query-for-dau---user-acquisition-ua h_01K58WFCYQVXBZN97BWHA8FC3C=query-for-dau---user-acquisition-ua query-for-dau-%E2%80%93-retargeting=query-for-dau---retargeting h_01K58WFCYQ4XNKQ9CW4D3KV2E2=query-for-dau---retargeting query-for-dau-%E2%80%93-unified-ua-retargeting=query-for-dau---unified-ua-retargeting h_01K58WFCYQ0NM0E44531YDJBCH=query-for-dau---unified-ua-retargeting calculate-monthly-active-users-mau=%EC%9B%94%EA%B0%84-%ED%99%9C%EC%84%B1-%EC%9C%A0%EC%A0%80-mau-%EA%B3%84%EC%82%B0-%EB%B0%A9%EB%B2%95 h_01K58WFCYQ251WMSNSD0EYXV69=%EC%9B%94%EA%B0%84-%ED%99%9C%EC%84%B1-%EC%9C%A0%EC%A0%80-mau-%EA%B3%84%EC%82%B0-%EB%B0%A9%EB%B2%95 query-for-mau-%E2%80%93-user-acquisition-ua=query-for-mau---user-acquisition-ua h_01K58WFCYQAV6T3S7SABSTMYKS=query-for-mau---user-acquisition-ua query-for-mau-%E2%80%93-retargeting=query-for-mau---retargeting h_01K58WFCYQ4H5CFQPPC5JQKHTJ=query-for-mau---retargeting query-for-mau-%E2%80%93-unified-ua-retargeting=query-for-mau---unified-ua-retargeting h_01K58WFCYQA1W91CHM1PN31MFG=query-for-mau---unified-ua-retargeting" />
