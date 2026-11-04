---
title: 캠페인 이름 변경
metadata:
  keywords:
    - Aggregated Data
    - Agencies
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
    - Ad Networks
  created_at: '2023-03-26T10:56:19Z'
  edited_at: '2026-10-14T10:26:02Z'
  id: 14038324952465
  locale: ko
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ko/articles/14038324952465
---
> **한눈에 보기:** 중복 데이터 표시를 만들지 않고 캠페인 이름을 변경합니다.

<div id="campaign-name-changes" />

## 캠페인 이름 변경

캠페인 이름을 변경하면 대시보드와 리포트의 **집계 데이터** 표시에 영향을 미칩니다. 앱스플라이어는 캠페인 ID를 키로 사용하여 캠페인을 표시합니다. 동일한 캠페인 ID와 연결된 이름이 두 개 이상 있는 경우 가장 최근에 보고된 이름이 데이터를 표시하는 데 사용됩니다.

* 이 문서에서는 **캠페인** 이름 변경에 대해 언급하지만, 광고 세트 및 광고 이름 변경에도 동일한 규칙이 적용됩니다.
* 이름 변경은 설치, 인앱 이벤트, 비용, 수익을 포함하여 캠페인에 연결된 모든 데이터의 표시에 영향을 미칩니다.
* 대부분의 광고 네트워크는 캠페인 이름 변경을 지원하지만 일부 광고 네트워크는 지원하지 않으며, 이런 이유로 동일한 데이터가 포함된 중복 행이 표시될 수 있습니다.
* 로데이터는 이름 변경의 영향을 받지 않습니다.

다음 표에서는 캠페인 이름 변경을 지원하는 대시보드와 리포트를 보여줍니다.

| 대시보드/리포트 | 캠페인 이름 변경 지원 |
| --- | --- |
| 개요 대시보드 | 예, CTV 뷰 제외 |
| 액티비티 대시보드 | 예 |
| 코호트 대시보드 | 예 |
| 코호트 API | 예 |
| Pull API | Pull API V5 이하에서는 지원되지 않음 |
| 피봇 대시보드 | 아니요 |
| 커스텀 대시보드 | 아니요 |
| 리텐션 대시보드 | 아니요 |
| 이벤트 대시보드 | 아니요 |
| Protect360 대시보드 | 아니요 |
| Cost ETL | 예 |
| SKAN 개요 대시보드 | 아니요 |

<div id="example" />

> 📄 **예시**
>
> * 1월 1일, 캠페인 **example\_a1**이 실행되기 시작했습니다.
> * 1월 2일, 캠페인 이름이 **example\_a1**에서 **example\_a2**로 변경되었습니다.
>
> #### <span id="example-campaign-data"></span>캠페인 데이터 예시
>
>
>
> | 날짜 | 캠페인 이름 | 캠페인 ID | 인스톨 | 광고 비용 |
> | --- | --- | --- | --- | --- |
> | 1월 1일 | example\_a1 | 123 | 100 | $100 |
> | 1월 2일 | example\_a2 | 123 | 200 | $200 |
>
>
>
> #### <span id="overview-dashboard-display"></span>개요 대시보드 표시
>
>
>
> <table><tbody><tr><th><p><span>캠페인</span></p></th><th><p><span>캠페인 ID</span></p></th><th><p><span>인스톨</span></p></th><th><p><span>광고 비용</span></p></th></tr><tr><td><p><span>example_a2</span></p></td><td><p><span>123</span></p></td><td><p><span>300</span></p></td><td><p><span>$300</span></p></td></tr><tr><td colspan="4"><p>결과: 데이터는 가장 최근의 캠페인 이름 아래에 표시됩니다.</p></td></tr></tbody></table>

<div id="best-practice" />

### 모범 사례

* 대부분의 광고 네트워크는 캠페인 이름 변경을 지원하지만 일부 광고 네트워크는 지원하지 않으며, 이런 이유로 동일한 데이터가 포함된 중복 행이 표시될 수 있습니다. 이러한 표시 이상을 방지하려면 캠페인에는 고유한 캠페인 ID가 할당되어 있어야 합니다.
* 서로 다른 캠페인 ID에 동일한 캠페인 이름을 사용하지 마세요.
* 서로 다른 광고 ID에 동일한 광고 이름을 사용하지 마세요.

<div data-zendesk-anchors="rollout-details=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%9D%B4%EB%A6%84-%EB%B3%80%EA%B2%BD h_01HW896QQ2T4J0N5PDY6YFTJ49=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%9D%B4%EB%A6%84-%EB%B3%80%EA%B2%BD h_01HW896QQ34YVGF6P212ZHAQHG=%EC%98%88%EC%8B%9C example-campaign-data=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%98%88%EC%8B%9C h_01HW896QQ3G07XM06HR2CRXA3G=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%98%88%EC%8B%9C overview-dashboard-display-before-the-behavior-change=%EA%B0%9C%EC%9A%94-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%ED%91%9C%EC%8B%9C h_01HW896QQ3J9NE9GZRKKAPX46B=%EA%B0%9C%EC%9A%94-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%ED%91%9C%EC%8B%9C best-practice=%EB%AA%A8%EB%B2%94-%EC%82%AC%EB%A1%80 h_01HW896QQ4RAQ51GPD17YYZBJF=%EB%AA%A8%EB%B2%94-%EC%82%AC%EB%A1%80" />
