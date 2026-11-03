---
title: SKAN 데이터 집약형 포스트백 도착 날짜 API
metadata:
  keywords:
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
  created_at: '2020-12-21T09:03:09Z'
  edited_at: '2026-10-14T10:39:20Z'
  id: 360016646557
  locale: ko
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ko/articles/360016646557
---
> **한눈에 보기:** API를 통해 데이터 집약형 SKAdNetwork 포스트백 데이터는 포스트백 도착 날짜를 사용하여 집합합니다.

## SKAN 데이터 집약형 포스트백 도착 날짜 API

API는 포스트백 도착 날짜 범위를 사용하여 데이터 집약형 SKAdNetwork 포스트백을 반환합니다.

**참고**! 포스트백 도착 날짜는 SKAdNetwork 대시보드와 리포트에서 사용된 인스톨 날짜와 다릅니다.

<div id="using-skan-aggregated-performance-report-api" />

<Accordion title="SKAN 데이터 집약형 포스트백 도착 날짜 API">

SKAN 데이터 집약형 포스트백 도착 날짜 API

1. API 토큰을 받아야 합니다. 관리자가 토큰을 검색해야 합니다.
2. 인증 헤더에 사용할 API 토큰을 개발자에게 제공합니다.
3. API 호출 시 입력해야 할 파라미터를 개발자에게 제공하세요. 다음 섹션에서 설명합니다. 파라미터는 리포트의 중점 사항, 구성 방법을 결정하고 리포팅 기간을 제공합니다.

#### 파라미터

| 파라미터 이름 | 상세 정보 | 필수 |
| --- | --- | --- |
| `start_date` | 포스트백 도착 날짜 범위는 시작 날짜와 종료 날짜로 제한됩니다. 참고 도착 날짜는 SKAdNetwork 대시보드 및 리포트에서 사용된 인스톨 날짜와 다릅니다.<ul><li>YYYY-MM-DD</li><li>허용되는 가장 빠른 날짜: 2020-11-01<br />예: `2020-11-05`</li></ul> | 예 |
| `end_date` | <ul><li>YYYY-MM-DD</li><li>리포트 호출 당 최대 일수: 60일</li><li>예: `2020-11-12`</li></ul> | 예 |
| `ad_network_name` | 미디어 소스로 필터링 | 아니요 |
| `geo` | ISO 3166 (alpha-2)을 사용하여 국가 코드로 필터링합니다. 예: `US`, `CN` | 아니요 |
| `skad_redownload` | `true` 또는 `false`로 필터링 | 아니요 |
| `skad_source_app_id` | 소스 앱 ID로 필터링 | 아니요 |
| `ad_network_campaign_id` | 애드 네트워크 캠페인 ID로 필터링합니다.<br /><br />**참고**: 이는 SKAdNetwork에서 보고된 캠페인 ID가 아닙니다. | 아니요 |
| `modeled_conversion_values` | <ul><li>V2에서만 지원됩니다</li><li>값은  또는 일 수 있습니다</li><li>`true`인 경우 포스트백은 예측 전환 값 데이터로 "count" 열을 채웁니다.  [예측 데이터에 사용 가능한 필드 참조](/docs/skan-aggregated-postback-arrival-date-api#report-structure-and-example)</li><li>인 경우 포스트백은 예측 데이터 없이 리포트 구조에 나열된 모든 사용 가능한 필드와 함께 전환 값 수를 표시합니다.</li><li>기본 설정 값은 입니다.</li></ul> | 아니요 |

</Accordion>

<div id="report-structure-and-example" />

<Accordion title="리포트 구조 및 예제">

API는 CSV 파일을 반환합니다.

사용 가능한 열과 메트릭은 다음 표에 나와 있습니다.

예시: <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRXgsWlkyvMS20HgZuOQnH1YC8QQcRhOMYIOxyj_fcgikfDfmW6wNAMHO6alPWVA1j_KZwtqowohqrK/pub?gid=0&single=true&output=csv">V1</Anchor> | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRMFEELm8JCAQBBAIJqAc1eE5YdN0kOcSVkOPd_Ki2ngnX61wHL4sXypVouOhto8u-JCQmdIYY_5UG6/pub?gid=219191499&single=true&output=csv">V2</Anchor>

| 열 이름 | 데이터 기준 또는 측정값 | API V1 토큰과 함께 사용 가능 | API V2 토큰과 함께 사용 가능 | API V2 토큰과 함께 사용 가능 (SKAN 4용) | 모델링된 데이터만 필터로 사용 가능 |
| --- | --- | --- | --- | --- | --- |
| skad\_포스트백\_서열\_인덱스 | 그룹별로 | N | N | Y | Y |
| skad\_전환\_가치 | 그룹별로 | Y | Y | Y | Y |
| skad\_coarse\_conversion\_value | 그룹별로 | N | N | Y | Y |
| skad\_ad\_network\_id<br /><br />일부 SRN은 자신의 ID를 우리와 공유하지 않습니다. 이 경우, 필드는 비어 있고 ad\_network\_name이 채워집니다. | 그룹별로 | Y | Y | Y | Y |
| 애드 네트워크 이름<br /><br />현재 대부분의 경우 이 필드는 비어 있습니다. skad\_ad\_network\_id를 공유하지 않는 SRN의 경우에는 이를 채웁니다. | 그룹별로 | Y | Y | Y | Y |
| skad\_source\_identifier | 그룹별로 | N | N | Y | Y |
| skad\_campaign\_id | 그룹별로 | Y | Y | Y | Y |
| 애드 네트워크 캠페인 ID | 그룹별로 | Y | Y | Y | Y |
| 애드 네트워크 캠페인 이름 | 그룹별로 | Y | Y | Y | Y |
| 애드 네트워크 광고 세트 ID | 그룹별로 | N | Y | Y | Y |
| 애드 네트워크 광고 세트 이름 | 그룹별로 | N | Y | Y | Y |
| 애드 네트워크 광고 ID | 그룹별로 | N | Y | Y | N |
| 애드 네트워크 광고 이름 | 그룹별로 | N | Y | Y | N |
| 애드 네트워크 크리에이티브 | 그룹별로 | N | N | Y | N |
| 애드 네트워크 채널 | 그룹별로 | N | N | Y | N |
| skad 버전 | 그룹별로 | Y | Y | Y | N |
| skad\_redownload | 그룹별로 | Y | Y | Y | N |
| skad\_source\_app\_id | 그룹별로 | Y | Y | Y | N |
| skad\_source\_domain | 그룹별로 | N | N | Y | Y |
| skad 신뢰도 유형 | 그룹별로 | N | Y | Y | N |
| 지역 | 그룹별로 | Y | Y | Y | N |
| 도착일 | 그룹별로 | Y | Y | Y | Y |
| 개수 | 측정값 | Y | Y | Y | Y |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="사양 및 제한 사항">

| 사양 | 비고 |
| --- | --- |
| 데이터 최신성 | 리포트는 <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#eod">매일</Anchor> 업데이트됩니다.<br /><br />데이터 가용성은 <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#skan">SKAdNetwork</Anchor> 데이터 최신성 비율에 따라 결정됩니다. |
| 날짜 범위 | <ul><li>지원되는 가장 빠른 날짜: 2020년 11월 1일</li><li>최대 조회 범위: 60일</li></ul> |
| 요금 한도 | <ul><li>쿼리는 최대 200K 행을 반환합니다.</li><li>분당 최대 60회 호출 가능</li></ul> |
| SRNs | Google Ads: 포스트백 도착 날짜는 Google의 라스트 클릭 시간을 사용하여 도출됩니다. |
| 애드 네트워크 액세스 | 광고주가 허가하는 경우 분석 파트너에게 제공됩니다. |
| 에이전시 액세스 | 사용 불가 |
| 앱별 시간대 | UTC만 적용 |
| 앱별 통화 | 항상 USD 사용 |
| 오가닉 데이터 | 이 API에서는 사용할 수 없음 |
| 논오가닉 데이터 | 앱스플라이어가 받은 SKAdNetwork 포스트백을 사용하여 계산됨 |
| 과거 데이터 | 지원되는 가장 초기 전환 데이터(인스톨 또는 리타겟): 2020년 11월 1일 |
| 계정 유저 액세스 | 인증 토큰은 대시보드에서 어드민 유저에게 제공됩니다. |

</Accordion>

> 📄 **참조 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/skan-aggregated-performance-report-api">SKAN 데이터 집약형 성과 리포트 API</Anchor>

<div data-zendesk-anchors="skadnetwork-postback-arrival-date-aggregation-reporting-api=skan-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A7%91%EC%95%BD%ED%98%95-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%8F%84%EC%B0%A9-%EB%82%A0%EC%A7%9C-api h_01HDNZKFEHWET0FPX9WN136MB2=skan-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A7%91%EC%95%BD%ED%98%95-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%8F%84%EC%B0%A9-%EB%82%A0%EC%A7%9C-api h_01HDNZKFEH76Y06091QS6Y5K1Z=using-skan-aggregated-performance-report-api parameters=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HDNZKFEHA6N6EE4RMG0HGABA=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HDNZKFEHM2D7GS3RMSRCKZY7=report-structure-and-example h_01HDNZKFEJ5P3245V1R99DGAQW=specifications-and-limitations h_01HDNZP87CWGVJ3G1BDXAR1WN0=%EC%B0%B8%EC%A1%B0-%ED%95%AD%EB%AA%A9" />
