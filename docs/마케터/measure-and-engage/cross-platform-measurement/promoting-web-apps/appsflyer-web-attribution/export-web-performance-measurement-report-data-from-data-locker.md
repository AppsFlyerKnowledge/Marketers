---
title: 데이터 락커에서 웹 성과 측정 리포트 데이터 내보내기
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T10:49:59Z'
  edited_at: '2026-10-14T10:27:28Z'
  id: 43510758321809
  locale: ko
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ko/articles/43510758321809
---
> **한눈에 보기:** 데이터 락커에서 웹 성능 측정 데이터를 두 가지 보고서 유형으로 내보내 웹 사이트 성능을 적절한 수준에서 분석할 수 있습니다. 최종 사용자 이벤트를 사용하여 모든 방문 및 이벤트를 분석하고, 전환을 사용하여 고유한 전환 앵커 (첫 방문, 재방문, 사용자 획득 이벤트) 를 집계하고 속성을 지정할 수 있습니다.

> 🚧 **중요!**
>
> 데이터 락커에서 웹 성능 측정 보고서에 액세스하려면 데이터 락커 구독이 있어야 합니다.

<div id="about-the-web-performance-measurement-reports" />

## 웹 성과 측정 보고서 정보

데이터 락커는 웹 성과 측정, **최종 사용자 이벤트** 및 **전환에 대한 두 가지 보고서를 제공하며,** 각 보고서는 서로 다른 분석 요구에 맞게 설계되었습니다.

* **웹 최종 사용자 이벤트** 보고서는 웹 사이트 활동을 분석하기 위한 기본 소스입니다.
  * **모든 웹 이벤트 및 방문** 포함
  * 각 방문을 어트리뷰트로 기록합니다. `SESSION`
  * **방문 수준 및 이벤트 수준 리포팅에** **적합**
* **전환 보고서는 전환** 수준 분석에 가장 적합합니다. 전환은 마케팅 크레딧을 할당하는 시기와 방법을 결정하는 터치포인트인 귀속 앵커입니다. 여기에는 다음이 포함됩니다.
  * *첫 방문* (사용자가 웹사이트에 처음 도착했을 때),
  * *재방문* (사용자가 논오가닉 광고 인게이지먼트 후 재방문 시),
  * 사용자가 확보되었음을 표시한다는 *사용자 획득 이벤트* (가입 또는 첫 입금과 같은 커스텀 이벤트)
* 모든 사용자 이벤트는 나중에 이러한 전환과 연결되며 캠페인 세부 정보를 상속합니다.

<div id="report-fields" />

## 리포트 필드

보고서에 어떤 필드가 포함되는지 알아보려면 각 보고서의 샘플을 다운로드하십시오.

* [최종 사용자 이벤트 리포트 샘플](https://docs.google.com/spreadsheets/d/e/2PACX-1vQYFF0r4pMpo_voSK8QObpiRtx-diU_0a-0XVuKIVMEfh6rRPudIDXA5bgDw_lcc0qwBPcPhYtLdWwh/pub?output=csv)
* [전환 이벤트 리포트 샘플](https://docs.google.com/spreadsheets/d/e/2PACX-1vTMqcc6PKBATBg1DYVO8MWKrAs_wlqXxyANe3a_gu62xp3hFZV9wWT1X8c9oRekaIEwCfKZ2y9agVeV/pub?output=csv)

샘플 보고서에는 모든 리포트 필드와 해당 값이 포함됩니다. 필드 정의는 필드 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary">사전을</Anchor> 참조하십시오.

<div id="report-timing-and-data-freshness" />

## 리포트 타이밍 및 데이터 새로고침

이러한 세부 정보를 사용하여 새 데이터가 추가되는 시점과 최근 이벤트가 보고서에 표시되는 시기를 파악할 수 있습니다.

* **리포트 생성 빈도:** 매시간 새 데이터가 추가됩니다.
* 데이터 최신성 이벤트는 일반적으로 발생 후 2&#126;3시간 내에 리포트에 나타납니다.

<div id="heres-how-each-batch-works" />

### 각 배치의 작동 방식은 다음과 같습니다.

* 각 배치는 1.5시간 기간 내에 이벤트를 **처리합니다**.
* 해당 기간 2. 내에서는 **이벤트의 첫 1시간만 어트리뷰션됩니다**.
* 나머지 30분은 고객 사용자 ID (CUID) 로 어트리뷰션 이벤트를 **강화하는 데만** 사용됩니다.
* 가장 최근 30분 동안 발생한 이벤트는 **아직 어트리뷰션되지 않으며**, 다음 배치에 포함될 예정입니다.

[![](https://files.readme.io/1957b8b0c6b29fb44934ef7d10fd04278d541a4f2c12bb90e49fc8cb61ec7db5-44460048223761.png)](https://files.readme.io/1957b8b0c6b29fb44934ef7d10fd04278d541a4f2c12bb90e49fc8cb61ec7db5-44460048223761.png)

<div id="when-will-these-events-appear-in-the-report" />

### 이러한 이벤트는 언제 리포트에 표시되나요?

이벤트는 **처리가 완료된 후** 보고서에 기록됩니다. **예를 들어 오전 10시 배치에서 발생한** 08:00 ~ 09:00 **이벤트는 오전 11시 리포트 버전에 표시됩니다.**

<div id="example-what-the-1000-am-batch-does" />

### 예: 오전 10시 배치의 기능

| **날짜** | **에서 사용할 수 있는 리포트** | **어트리뷰션된 웹 이벤트 (이벤트 시간)** | **CUID를 사용하여 이전 이벤트를 강화하기 위해 처리한 웹 이벤트** |
| --- | --- | --- | --- |
| 2026-01-28 | 11:00 | 08:00 – 09:00 | 09:00–09:30 |
| 2026-01-28 | 12:00 | 09:00 – 10:00 | 10:00–10:30 |
| 2026-01-28 | 13:00 | 10:00 – 11:00 | 10:00-11:30 |

<div id="download-report-data-from-your-cloud-bucket" />

## 클라우드 버킷의 보고서 데이터에 액세스하는 방법

클라우드 버킷의 보고서 데이터에 액세스하는 방법에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers#folder-structure">데이터 락커 폴더 구조를 참조하세요</Anchor>.

<div id="bi-developer-considerations" />

## BI 개발사 고려사항

<div id="key-differences-web-vs-mobile" />

<Accordion title="주요 차이점: 웹 vs. 모바일">

웹 어트리뷰션은 식별자와 데이터 로직 모두에서 모바일 어트리뷰션과 다릅니다. 데이터 정확도를 높이려면 쿼리에 다음 필터와 모범 사례를 적용하세요.

| 양상 | 모바일 | 웹 |
| --- | --- | --- |
| 플랫폼 필터 | 혹은 | `platform = 'WEBSITE'` |
| 사용자 식별자 (값) | `appsflyer_id` (기기 기반) | `appsflyer_id_value` (쿠키 기반) |
| 식별자 유형 | 기기에 따라 다름 | `appsflyer_id_type`은(는) 항상 `web_id` |
| 획득 이벤트 | 설치 | First Visit이 기본값이지만 사용자 획득 이벤트는 사용자 지정할 수 있습니다. |
| 리인게이지먼트 | `RE-ENGAGEMENT` | `REVISIT` |
| 리어트리뷰션 | 지원됨 | 지원되지 않음 - 웹에는 사용자 획득 및 재방문만 있습니다. |
| 앱 ID | 앱 ID (예: `id123456789`) | 접두사가 있는 도메인 (예: `website-www.example.com`) |

</Accordion>

<div id="which-table-to-query" />

<Accordion title="쿼리할 표는 무엇입니까?">

**최종 사용자 이벤트** 리포트는 대부분의 분석에 적합합니다. 여기에는 모든 웹 사이트 이벤트 및 방문이 포함됩니다. 또한 각 웹 방문은 이 보고서에 속성으로 기록되므로 방문 수준 및 이벤트 수준 보고의 기본 소스가 됩니다`SESSION`.

**전환수** 표는 주로 중복된 이벤트 기록 없이 고유한 전환이 필요한 경우 첫 방문, 재방문, 사용자 확보를 계산하는 데 적합합니다.

| 사용 사례 | 표 | 이유 |
| --- | --- | --- |
| 방문수/세션 수 | `end_user_events` | 각 행은 세션 또는 이벤트입니다. |
| 고유 전환수 계산 | `conversions` | 중복 방지 |
| 인앱 이벤트 분석: | 함께 | 인앱 이벤트에만 이벤트 이름이 있습니다. |

</Accordion>

<div id="implement-query-filters" />

<Accordion title="쿼리 필터 구현">

로데이터 쿼리의 데이터 정확성을 보장하려면 다음 필터를 적용하세요. 이를 구현하지 못하면 항목이 중복되고 플랫폼 지표가 혼합됩니다.

* **플랫폼별 필터링 (필수):** `WHERE platform = 'WEBSITE'`포함하면 웹 기반 데이터를 분리하고 모바일, PC 또는 CTV 환경에서 레코드를 제외할 수 있습니다.
* **귀속 크레딧별 필터링 (필수):** 앱스플라이어는 리포팅 뷰에 따라 두 개의 다른 귀속 크레딧을 할당할 수 `end_user_events` 있기 때문에 동일한 사용자 액션이 두 번 나타날 수 있습니다.

  이는 사용자가 다음과 같은 경우에 발생할 수 있습니다.

  * 오리지널 **UA (사용자 획득)** 소스 및 이후
  * **리인게이지먼트** 소스.

  이 경우 앱스플라이어는 동일한 이벤트에 대해 두 개의 레코드를 작성할 수 있습니다.

  * **기본 크레딧:** 이벤트는 가장 최근의 관련 마케팅 상호작용에 기인합니다. 통합 뷰와 리타겟팅 뷰에서 사용됩니다.

    이중 계산을 피하려면 기본적으로 기본 신용 기록만 `end_user_events` 사용하여 쿼리하십시오.

    ```sql
    WHERE platform = 'WEBSITE'
      AND is_primary_attribution = true
    ```
  * **보조 학점:** 이벤트를 원래 UA 소스에 다시 어트리뷰션합니다. 평생 가치 (LTV) 추적을 위한 UA 획득 뷰에 사용됩니다.

    동일한 사용자 작업을 두 개의 레코드 (하나는 주 크레딧과 보조 크레딧) 로 저장할 수 있으므로 필터 없이 이벤트를 카운트하면 해당 작업이 두 배로 계산될 수 있습니다.

    이러한 쿼리를 템플릿으로 사용하여 BigQuery 또는 기타 BI 도구에서 웹 어트리뷰션 데이터를 분석하세요.

* **전환 유형별 필터링 (선택 사항):** 캠페인 유형에 따라 어트리뷰션 데이터를 `WHERE conversion_type = 'USER_ACQUISITION'` 포함하거나 `WHERE conversion_type = 'RETARGETING'` 분리할 수 있습니다.

<div id="filter-summary-table" />

#### 필터 요약 표

| 필터 요구 사항 | SQL 로직 | 구현 컨텍스트 |
| --- | --- | --- |
| 플랫폼 사양 | `WHERE platform = 'WEBSITE'` | 웹 기반 데이터를 다른 플랫폼 레코드와 분리합니다. |
| 통합 보기 (중복 방지) | `WHERE is_primary_attribution = true AND platform = 'WEBSITE'` | 리타겟팅 캠페인 크레딧을 오리지널 UA 캠페인보다 우선시하세요. 이중 계산을 방지하기 위해 일반 리포팅에 사용합니다. |
| 리타겟팅 보기 전용 | `WHERE conversion_type = 'RETARGETING' AND platform = 'WEBSITE'` | 특히 리타겟팅 캠페인의 성과를 분석할 때만 사용하십시오. |
| 유저 인입 보기: | `WHERE conversion_type = 'USER_ACQUISITION' AND platform = 'WEBSITE'` | 이벤트를 최초 방문과 연계해야 하는 고객 유치 중심의 뷰에 특히 사용합니다. |

</Accordion>

<div id="identifying-and-counting-end-users" />

<Accordion title="최종 사용자 식별 및 계산">

웹 성과 측정 로데이터에서 최종 사용자는 두 가지 다른 식별자로 나타날 수 있습니다.

* `customer_user_id`: 사용자가 설정한 안정적인 식별자 (일반적으로 로그인한 사용자용).
* `appsflyer_id_value`: 시간이 지나면 만료될 수 있는 쿠키 기반 신분증입니다.

**고유 사용자를** 정확하게 식별하고 **사용자 수준 지표를** 계산하려면 항상 다음 용도를 사용하십시오.

```sql
COALESCE(customer_user_id, appsflyer_id_value)
```

작동 원리는 다음과 같습니다:

* `customer_user_id`존재하는 경우 앱스플라이어는 이를 사용합니다 (선호, 안정).
* 그렇지 않으면 앱스플라이어는 이를 대체합니다. `appsflyer_id_value`

`COALESCE(customer_user_id, appsflyer_id_value)`필요할 때마다 사용할 수 있습니다.

* 고유 사용자 수 계산
* 사용자별 그룹
* 특정 사용자별 필터링
* 사용자별 테이블 조인
* 모든 사용자 수준 지표 계산

<div id="example-count-distinct-users" />

#### 예: 고유 사용자 수 계산

```sql
SELECT 
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS unique_users
FROM `end_user_events`
WHERE platform = 'WEBSITE'
  AND is_primary_attribution = TRUE
```

</Accordion>

<div id="organic-vs-nonorganic-traffic" />

<Accordion title="오가닉 vs. 논오가닉 트래픽">

`is_organic`필드 용도:

| 트래픽 유형 | 필터 |
| --- | --- |
| 오가닉 | `is_organic = true` |
| 논오가닉 | `is_organic = false` |

</Accordion>

<div id="handling-empty-values" />

<Accordion title="빈 값 처리">

| 데이터 유형 | 빈 값 |
| --- | --- |
| 문자열 | Empty string |
| 숫자 | `NULL` |

</Accordion>

<div id="query-examples" />

<Accordion title="쿼리 예제">

<div id="1-total-visits-by-media-source-7-days" />

<Accordion title="1. 미디어 소스별 총 방문수 (7일)">

각 미디어 소스에 어트리뷰션된 웹 세션을 계산합니다.

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

</Accordion>

<div id="2-first-visits-and-revisits-by-campaign" />

<Accordion title="2. 캠페인별 첫 방문 및 재방문">

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

</Accordion>

<div id="3-count-distinct-event-names-inapp-events-only" />

<Accordion title="3. 고유한 이벤트 이름 계산 (인앱 이벤트만 해당)">

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

</Accordion>

<div id="4-count-distinct-users-by-media-source" />

<Accordion title="4. 미디어 소스별 고유 사용자 수 계산">

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

</Accordion>

<div id="5-conversion-rate-first-visit-to-purchase-crosstable-join" />

<Accordion title="5. 전환율 - 첫 방문부터 구매까지 (크로스 테이블 조인)">

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

</Accordion>

<div id="6-revenue-by-campaign-last-7-days" />

<Accordion title="6. 캠페인별 수익 (지난 7일)">

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

</Accordion>

<div id="7-organic-vs-nonorganic-first-visits-by-day" />

<Accordion title="7. 오가닉 vs. 비오가닉 일일 첫 방문">

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

</Accordion>

<div id="8-user-acquisition-vs-retargeting-breakdown" />

<Accordion title="8. 유저 유입(UA) 리타겟팅 분류">

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

</Accordion>

<div id="9-click-id-distribution-google-meta-tiktok-etc" />

<Accordion title="9. 클릭 신분증 배포 (구글, 메타, 틱톡 등)">

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

</Accordion>

<div id="10-cohort-users-by-conversion-date-equivalent-to-mobile-install-date" />

<Accordion title="10. 전환일별 코호트 사용자 수 (모바일 인스톨 날짜와 동일)">

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

</Accordion>

</Accordion>

<div id="traits-and-limitations" />

## 특징 및 제한 사항

다음 필드는 **웹 데이터에 지원되지 않으며** 항상 비어 있습니다.

| 특징 | 비고 |
| --- | --- |
| `advertising_id_type`, `hardware_id_type` 등 | 둘 다 |
| `agency`, `site_id`, `ad_type` | 둘 다 |
| `platform_group` | 전환 |
| `app_version__conversion` | end\_user\_events |
| 모든 `__assist_*` 필드 | 전환 |

<div data-zendesk-anchors="h_01KJYKY2RFJKMR2M3VB6R5XKYK=%EC%A4%91%EC%9A%94 about-the-data-locker-web-attribution-reports=%EC%9B%B9-%EC%84%B1%EA%B3%BC-%EC%B8%A1%EC%A0%95-%EB%B3%B4%EA%B3%A0%EC%84%9C-%EC%A0%95%EB%B3%B4 h_01KGM4FT90X1K2V8M8GJV6EW5K=%EC%9B%B9-%EC%84%B1%EA%B3%BC-%EC%B8%A1%EC%A0%95-%EB%B3%B4%EA%B3%A0%EC%84%9C-%EC%A0%95%EB%B3%B4 report-fields=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%95%84%EB%93%9C h_01KGM4FT90WP73N1D75WWNT2TE=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%95%84%EB%93%9C report-timing-and-data-freshness=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%83%80%EC%9D%B4%EB%B0%8D-%EB%B0%8F-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%83%88%EB%A1%9C%EA%B3%A0%EC%B9%A8 h_01KGM4FT90B6W7KBS9K1FSSETD=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%83%80%EC%9D%B4%EB%B0%8D-%EB%B0%8F-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%83%88%EB%A1%9C%EA%B3%A0%EC%B9%A8 here%E2%80%99s-how-each-batch-works=%EA%B0%81-%EB%B0%B0%EC%B9%98%EC%9D%98-%EC%9E%91%EB%8F%99-%EB%B0%A9%EC%8B%9D%EC%9D%80-%EB%8B%A4%EC%9D%8C%EA%B3%BC-%EA%B0%99%EC%8A%B5%EB%8B%88%EB%8B%A4 h_01KGM4FT91MCGCBYSHE18JHQ96=%EA%B0%81-%EB%B0%B0%EC%B9%98%EC%9D%98-%EC%9E%91%EB%8F%99-%EB%B0%A9%EC%8B%9D%EC%9D%80-%EB%8B%A4%EC%9D%8C%EA%B3%BC-%EA%B0%99%EC%8A%B5%EB%8B%88%EB%8B%A4 when-will-these-events-appear-in-the-report=%EC%9D%B4%EB%9F%AC%ED%95%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EB%8A%94-%EC%96%B8%EC%A0%9C-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%97%90-%ED%91%9C%EC%8B%9C%EB%90%98%EB%82%98%EC%9A%94 h_01KGM4FT91XF7HCM8E8TQ56D0D=%EC%9D%B4%EB%9F%AC%ED%95%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EB%8A%94-%EC%96%B8%EC%A0%9C-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%97%90-%ED%91%9C%EC%8B%9C%EB%90%98%EB%82%98%EC%9A%94 example-what-the-1000-am-batch-does=%EC%98%88-%EC%98%A4%EC%A0%84-10%EC%8B%9C-%EB%B0%B0%EC%B9%98%EC%9D%98-%EA%B8%B0%EB%8A%A5 h_01KGM4FT91D90DWYGSE3SES2ZY=%EC%98%88-%EC%98%A4%EC%A0%84-10%EC%8B%9C-%EB%B0%B0%EC%B9%98%EC%9D%98-%EA%B8%B0%EB%8A%A5 how-to-access-report-data-in-your-cloud-bucket=%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EB%B2%84%ED%82%B7%EC%9D%98-%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01KGM4FT91NECKXMDW60A4B9X5=%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EB%B2%84%ED%82%B7%EC%9D%98-%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 bi-developer-considerations=bi-%EA%B0%9C%EB%B0%9C%EC%82%AC-%EA%B3%A0%EB%A0%A4%EC%82%AC%ED%95%AD h_01KGM4FT91C2KP050ZAYW6K8FD=bi-%EA%B0%9C%EB%B0%9C%EC%82%AC-%EA%B3%A0%EB%A0%A4%EC%82%AC%ED%95%AD h_01KGM4FT91VNYYB998QBR6SDCC=key-differences-web-vs-mobile h_01KGM4FT91DEJT1GSA24MDMENV=which-table-to-query h_01KGM4FT91CTGZVST46MYYVJXV=implement-query-filters filter-summary-table=%ED%95%84%ED%84%B0-%EC%9A%94%EC%95%BD-%ED%91%9C h_01KGM4FT91MSN2SN7TKNJZ54V4=%ED%95%84%ED%84%B0-%EC%9A%94%EC%95%BD-%ED%91%9C h_01KGM4FT91BXMPKWXWSHH1X1W2=identifying-and-counting-end-users example-count-distinct-users=%EC%98%88-%EA%B3%A0%EC%9C%A0-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%88%98-%EA%B3%84%EC%82%B0 h_01KGM4FT91VDR0FWTMAPW6GM83=%EC%98%88-%EA%B3%A0%EC%9C%A0-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%88%98-%EA%B3%84%EC%82%B0 h_01KGM4FT91M2ZJ58PFZDE2W26J=organic-vs-nonorganic-traffic h_01KGM4FT91KYHDHYMK2FNE15CN=handling-empty-values h_01KGM9GZMRDVQKM3BQWX9E44E2=query-examples h_01KGM9GZMR7E8NQY9QN1Z0EEX8=1-total-visits-by-media-source-7-days h_01KGM9GZMRQ89CSXVJ4T4995FR=2-first-visits-and-revisits-by-campaign h_01KGM9GZMR90V0V4HBNM46RM1X=3-count-distinct-event-names-inapp-events-only h_01KGM9GZMRZBGNJYF7Y4N912HV=4-count-distinct-users-by-media-source h_01KGM9GZMR5SKN6PHD0NSK0JT0=5-conversion-rate-first-visit-to-purchase-crosstable-join h_01KGM9GZMRK2HTDSRHP5RJ059E=6-revenue-by-campaign-last-7-days h_01KGM9GZMRPVQX2WENF6MXPT1D=7-organic-vs-nonorganic-first-visits-by-day h_01KGM9GZMRER33GK5BYS3G66XJ=8-user-acquisition-vs-retargeting-breakdown h_01KGM9GZMRKNSG5JFE26XJZ2A6=9-click-id-distribution-google-meta-tiktok-etc h_01KGM9GZMRMJNSX8WV0WG01FCZ=10-cohort-users-by-conversion-date-equivalent-to-mobile-install-date traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01KGM4FT91QZR30KJAQ87AG691=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD" />
