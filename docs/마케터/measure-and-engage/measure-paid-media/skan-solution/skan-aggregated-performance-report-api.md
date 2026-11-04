---
title: SKAN 통합 성과 리포트 API
metadata:
  keywords:
    - Advertisers
    - SKAD
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-08T09:45:03Z'
  edited_at: '2026-10-14T10:32:56Z'
  id: 360014104157
  locale: ko
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ko/articles/360014104157
---
> **한눈에 보기:** 추가적인 데이터 포인트들로 성과가 더 풍부해진 SKAN. SKAdNetwork 대시보드의 데이터와 비슷합니다. 설치 날짜 또는 포스트백 도착 날짜를 기준으로 집계할 수 있습니다.

<div id="skan-aggregated-performance-report-api" />

## SKAN 통합 성과 리포트 API

API는 Apple SKAdNetwork에서 보고한 어트리뷰션 지표(실제 데이터)와 설치나 포스트백 도착 날짜를 통해 얻은 기타 데이터 포인트들을 반환합니다. <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN 대시보드</Anchor><Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">에 나타낸 데이터 구조와 비슷한 리포트입니다.</Anchor>

<div id="using-skan-aggregated-performance-report-api" />

<Accordion title="SKAN 집계 성과 리포트 API를 활용하기">

**SKAN 데이터 집약형 성과 리포트 API를 사용하려면**:

1. API 토큰을 받아야 합니다. 관리자가 토큰을 검색해야 합니다.
2. 인증 헤더에 사용할 API 토큰을 개발자에게 제공합니다.
3. API 호출 시 입력해야 할 파라미터를 개발자에게 제공하세요. 다음 섹션에서 설명합니다. 파라미터는 리포트의 초점이 무엇인지, 구성 방법을 결정하며, 리포팅 기간을 제공합니다.
4. 개발자에게 개발자 허브에서 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-agg-performance-report-api-get">SKAN 데이터 집약형 성과 리포트 API</Anchor>를 따르라고 하세요.

<div id="parameters" />

#### 파라미터

| 파라미터 이름 | 형식 | 필수적 |
| --- | --- | --- |
| `date_type` | `start_date` 과 `end_date` 사이의 날짜 범위에서 쓰인 날짜 유형<br /><br />옵션:<ul><li>[기본값] `install`: 앱스플라이어가 포스트백의 도착 시점을 기준으로 측정 기간을 고려해 유도한 설치 날짜입니다.</li><li>`arrival`: 포스트백 도착 시점. 참고: 오가닉 설치 지표는 값이 'N/A'입니다.</li></ul>Google Ads에 대한 데이터: Google Ads 리포팅 방식 때문에 설치 날짜와 도착 날짜가 같습니다. | 아니오 |
| `start_date` | 설치 날짜 범위는 start\_date와 end\_date로 정해집니다. 주의! 설치 날짜가 포스트백 도착 날짜와 차이가 있습니다.<ul><li>가장 빠른 설치 날짜의 형식은 YYYY-MM-DD 입니다</li><li>가능한 가장 이른 날짜: 2020-11-01<br />예: `2020-11-05`</li></ul> | 예 |
| `end_date` | <ul><li>가장 최근의 설치 날짜 형식은 YYYY-MM-DD 입니다</li><li>리포트 호출 시 최대 일수: 90일</li><li>예: `2020-11-12`</li></ul> | 예 |
| `view_type` | 설치 유형을 아래와 같이 필터링하세요:<ul><li>`acquisition`: 인스톨</li><li>`retargeting`: 앱 재설치</li><li>`unified`: 유입 및 재다운로드가 함께 표시됩니다.</li><li>[기본값] `unified`</li><li>비용, 클릭, 그리고 노출 지표는 `view_type=unified`일 때 반환됩니다.</li></ul> | 아니오 |
| `modeled_conversion_values` | <ul><li>V2 이상에서 사용 가능</li><li>값은 `true` 또는 `false`가 될 수 있습니다</li><li>참일 경우, 포스트백은 디코딩된 지표 열에 모델링 데이터를 포함하여 제공합니다. [사용 가능한 필드 확인하기](/docs/skan-aggregated-performance-report-api#report-structure-and-example)</li><li>`false`일 경우, 포스트백은 모델링된 데이터 없이 자원 SKAN 포스트백에서 수신된 디코딩된 데이터를 보여줍니다.</li><li>기본 설정 값은 `false`입니다.</li></ul> | 아니요 |

</Accordion>

<div id="report-structure-and-example" />

<Accordion title="리포트 구조 및 예제">

API를 통해 CSV 파일이 제공됩니다.

* 리포트에서 확인 가능한 필드와 지표는 다음과 같이 나열됩니다.
* 일부 지표(수익, 인게이지먼트, 전환)는 SKAN <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio">성과 측정 설정</Anchor>에 따라 달라집니다.
* 리포트에는 리포팅 기간 동안 사용자가 수행한 인앱 이벤트만 포함됩니다. 그래서 리포트마다 인앱 이벤트 컬럼의 수와 순서는 변할 수 있습니다. 데이터를 추출하는 프로세스 설계에 열 순서를 기준으로 삼지 마세요.
* 예시: [V1](https://docs.google.com/spreadsheets/d/e/2PACX-1vSmnyUITQjRxNp6-rz8Xzscu-Rr4Kn2DW1du2VppS-QrpyQSZ0GKQ_qZdWNdNoLuwJAmgh2O-bWiuU3/pub?gid=0&single=true&output=csv) | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQogLd4w3xgrjQBmEiHLfcvz1e9dtWez_Rdg1OxV8bSRHRE-wxZJItfT6azLr4iZAgsW2Vxr_WVmEYo/pub?gid=0&single=true&output=csv">V2</Anchor>

<div id="report-fields" />

#### 리포트 필드

| 필드 이름 | 차원 또는 메트릭 | API V1 토큰이 있을 경우 사용 가능 | API V2 토큰과 함께 사용 가능 | API V2 토큰과 함께 사용 가능 (SKAN 4용) | 모델링된 데이터 필터로만 사용 가능 |
| --- | --- | --- | --- | --- | --- |
| Date (날짜)<br /><br />데이터는 선택된 date\_type에 따라 달라집니다. | 디멘션 | N | Y | Y | Y |
| Media Source (pid) | 디멘션 | Y | Y | Y | Y |
| 캠페인(c) | 디멘션 | Y | Y | Y | Y |
| 캠페인 ID | 디멘션 | Y | Y | Y | Y |
| 사이트 ID | 디멘션 | Y | Y | Y | N |
| 광고세트 | 디멘션 | N | Y | Y | Y |
| 광고세트 ID | 디멘션 | N | Y | Y | Y |
| Ad | 디멘션 | N | Y | Y | N |
| 광고 ID | 디멘션 | N | Y | Y | N |
| 국가 | 디멘션 | Y | Y | Y | N |
| AF 어트리뷰션 플래그<br /><br />다음을 참조하세요. <Anchor target="_blank" href="/marketers/ko/docs/single-source-of-truth-ssot-guide-for-ios-attribution">SSOT 가이드</Anchor> | 디멘션 | N | Y | Y | Y |
| 포스트백 시퀀스 인덱스 | 디멘션 | N | N | Y | Y |
| 광고소재 | 디멘션 | N | N | Y | N |
| 채널 | 디멘션 | N | N | Y | N |
| 노출 수 | 지표 | Y | Y | Y | Y |
| 클릭 수 | 지표 | Y | Y | Y | Y |
| CTR | 지표 | Y | Y | Y | Y |
| 인스톨 | 지표 | Y | Y | Y | Y |
| 클릭을 통한 설치(fidelity\_type = 1) | 지표 | Y | Y | Y | Y |
| 시청을 통한 설치<br /><br />(fidelity\_type = 0) | 지표 | Y | Y | Y | Y |
| 무효 전환 값 비율<br /><br />[2022년 1월 23일부터 이용 가능] | 지표 | N | Y | Y | Y |
| 전환율 | 지표 | Y | Y | Y | Y |
| 전환된 사용자 | 지표 | Y | Y | Y | Y |
| 전환된 사용자/설치 | 지표 | Y | Y | Y | Y |
| Total revenue | 수익 관련 메트릭 | Y | Y | Y | Y |
| Total Cost | 지표 | Y | Y | Y | Y |
| ROI | 수익 관련 메트릭 | Y | Y | Y | Y |
| ARPU | 수익 관련 메트릭 | Y | Y | Y | Y |
| 평균 eCPI | 지표 | Y | Y | Y | Y |
| `{af_skad_revenue}` (고유 유저) | 수익 관련 메트릭 | Y | Y | Y | Y |
| `{af_skad_revenue}`(이벤트 카운터) | 수익 관련 메트릭 | Y | Y | Y | Y |
| `{귀사의 인앱 이벤트 명}` (고유 유저) | 지표 | Y | Y | Y | Y |
| `{귀사의 인앱 이벤트 명}` (이벤트 수) | 지표 | Y | Y | Y | Y |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="사양 및 제한 사항">

| 사양 | 비고 |
| --- | --- |
| 데이터 최신성 | 데이터 가용성은 <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#skan">SKAN</Anchor> 데이터의 신선도에 따라 결정됩니다. |
| 날짜 범위 | <ul><li>날짜 범위를 설정할 때 최신 날짜는 현재 UTC 기준 날짜에서 3일을 뺀 날이어야 합니다. 3월 31일을 예로 들면 3월 28일을 사용해야 합니다.</li><li>지원되는 최소 시작 날짜: 2020년 11월 1일</li><li>최대 쿼리 범위: 90일</li></ul> |
| 요청 제한 | <ul><li>쿼리는 최대 250K 행을 반환합니다</li><li>분당 최대 10번 호출 가능</li></ul> |
| SRN (Self Reporting Network) | <ul><li>Meta 광고: 데이터를 이용할 수 있습니다.</li><li>Google 광고: Google 클릭시간 방식에 따라 설치는 앱 설치 후 최대 45일까지 기록될 수 있습니다. 매일 최근 45일 동안의 Google 데이터를 쿼리하면 Google SKAN 데이터에 필요한 범위를 확보할 수 있습니다.</li></ul> |
| 광고 네트워크 액세스 | 분석 파트너라면 광고주에게 사용 권한을 부여받으라고 요청하세요. |
| 에이전시 액세스 | 사용 불가 |
| 앱별 시간대 | UTC만 적용 |
| 앱별 통화 | 항상 USD 사용 |
| 오가닉 데이터 | SDK가 직접 앱스플라이어에 보고한 모든 데이터와 SKAN 포스트백을 통해 보고된 논오가닉 데이터 사이의 차이로 계산됩니다. |
| 논오가닉 데이터 | 앱스플라이어가 받은 SKAN 포스트백을 사용하여 계산됩니다. |
| 기록 데이터 | 지원되는 가장 초기 전환 데이터(인스톨 또는 리타겟): 2020년 11월 1일 |
| 계정 유저 액세스 | 인증 토큰은 대시보드에서 관리자 유저가 받을 수 있습니다. |
| 총비용 | SKAN API는 광고, 국가 혹은 사이트 ID 같은 최소 단위 수준에서 50K 행을 초과하는 데이터를 포함한 SKAN 캠페인이 일반 어트리뷰션(일반 개요)에 있을 경우 총 비용 지표가 누락될 수 있습니다. |

</Accordion>

<div data-zendesk-anchors="skadnetwork-postback-arrival-date-aggregation-reporting-api=skan-%ED%86%B5%ED%95%A9-%EC%84%B1%EA%B3%BC-%EB%A6%AC%ED%8F%AC%ED%8A%B8-api h_01HH9WHP1SDQ3TJPZ931R9KWKH=skan-%ED%86%B5%ED%95%A9-%EC%84%B1%EA%B3%BC-%EB%A6%AC%ED%8F%AC%ED%8A%B8-api h_01HH9WHP1S7PWJHKAKHN434G7Y=using-skan-aggregated-performance-report-api parameters=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HH9WHP1SZQZGSZ4WEPAAFNV7=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HH9WHP1SYEHGJBBWSMS2XQP0=report-structure-and-example skadnetwork-aggregate-report-structure=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%95%84%EB%93%9C h_01HH9WHP1STYNJK3DRESDF23DG=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%95%84%EB%93%9C h_01HH9WHP1T4NEMW56XVYKM3KHM=specifications-and-limitations" />
