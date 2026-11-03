---
title: 리타게팅 이벤트의 이중 어트리뷰션
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2020-12-13T07:35:18Z'
  edited_at: '2026-10-14T10:33:08Z'
  id: 360016371077
  locale: ko
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/ko/articles/360016371077
---
> **한눈에 보기:** 한눈에 보기: 리타게팅 캠페인의 리인게이지먼트 기간 동안의 성과를 평가하기 위해 인앱이벤트와 세션은 사용자 확보(UA) 및 리타게팅 미디어소스에 이중으로 어트리뷰트됩니다.

![](https://files.readme.io/fce514999471aa7bfced06fa0e1c7d6fa7363a8d30119bd20d0b5d7e56eb1f7d-9479192551825.png)

## 개요

* 재참여
* **리어트리뷰션:**

앞의 그림에서 UA 이벤트는 green\_network에 어트리뷰트됩니다. 하나의 이벤트가 생성됩니다. 반대로, 사용자가 blue\_network 리타게팅 광고에 참여한 후에는 두 개의 이벤트가 생성됩니다. 이벤트 크레딧:

* blue\_network 리인게이지먼트를 유도하는 주요 원천입니다.
* green\_network 원래 설치에 동기를 부여한 보조 소스입니다.

더 명확히 하기 위해 다음 표에는 리인게이지먼트 기간 이전, 도중, 이후에 인앱이벤트가 어트리뷰션되는 방식에 대한 시나리오가 포함되어 있습니다. 표의 표기법은 이중 어트리뷰트된 이벤트를 식별하는 데 사용되는 원시 데이터 필드를 나타냅니다.

* is\_primary\_attribution:
* context: 다음 필드 중 하나를 사용합니다.
  * [모범 사례] **conversion\_type**: 인스톨 또는 리인게이지먼트.
  * is\_retargeting: true인 경우 데이터는 리타게팅 캠페인과 관련이 있습니다.

#### 리인게이지먼트 윈도우에 대한 어트리뷰션

| 미디어 소스 | 재계약 전 | 리인게이지먼트 중 | 인게이지먼트 후 |
| --- | --- | --- | --- |
| 유저 유입 | is\_primary\_attribution: True<br /><br />conversion\_type=인스톨<br /><br />(is\_retargeting: False | 보조<br /><br />is\_primary\_attribution: 거짓됨<br /><br />conversion\_type: re-engagement<br /><br />(is\_retargeting: False | is\_primary\_attribution: True<br /><br />conversion\_type=인스톨<br /><br />(is\_retargeting: False |
| 리타겟팅 | 해당 없음 | is\_primary\_attribution: True<br /><br />conversion\_type: re-engagement<br /><br />(is\_retargeting: True | 해당 없음 |

## 대시보드 보기 유형 지원

일부 대시보드 및 동질 집단 보고서에는 통합되는 여러 보기 옵션, 사용자 확보 및 리타게팅이 포함되어 있습니다. 이러한 뷰 유형은 원시 데이터에 사용되는 것과 유사한 논리를 사용합니다.

![](https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png)


<table><thead><tr><th><span id="data-filtering-by-view-type-using-the-conversion_type-field"></span>보기 유형</th><th>conversion_type</th><th>1차 어트리뷰션</th><th>어트리뷰션</th></tr></thead><tbody><tr><td rowspan="2">유저 유입</td><td>인스톨</td><td>True 또는 False</td><td>UA 미디어소스에 어트리뷰트되는 UA 이벤트</td></tr><tr><td>리인게이지먼트</td><td>거짓됨</td><td>UA 미디어소스에 어트리뷰션된 리타게팅 이벤트입니다.</td></tr><tr><td>리타겟팅</td><td>리인게이지먼트 또는 리어트리뷰션</td><td>True</td><td>리타게팅 미디어소스에 어트리뷰트된 리타게팅 이벤트</td></tr><tr><td>통합</td><td>인스톨 또는 리인게이지먼트</td><td>True</td><td>마지막 터치 미디어소스에 어트리뷰트되는 모든 이벤트</td></tr></tbody></table>

## 유저 인입 인앱 보고서에서 이중 어트리뷰션 리타게팅 이벤트를 식별하려면 어떻게 해야 합니까?

**UA 인앱이벤트 리포트** 에서 이중 어트리뷰션의 결과로 기록된 이벤트는 다음과 같이 식별됩니다.

* is\_primary\_attribution 필드는 기본 및 보조 미디어소스를 식별합니다. false인 경우 어트리뷰션은 리타게팅 캠페인의 결과이고 UA 미디어소스는 부차적임을 의미합니다.
* is\_retargeting 필드는 항상 false입니다.

리인게이지먼트 기간 동안 리타게팅 인앱이벤트 보고서의 해당 레코드는 다음과 같이 채워집니다.

* is\_primary\_attribution 필드는 항상 true입니다.
* is\_retargeting 필드는 항상 true입니다.

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01J8FJW0TE4DV5BFHGARS4ERT6=%EA%B0%9C%EC%9A%94 attribution-relative-to-the-reengagement-window=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%9C%88%EB%8F%84%EC%9A%B0%EC%97%90-%EB%8C%80%ED%95%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01J8FJW0TEJH716NXMM2RDN4J1=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%9C%88%EB%8F%84%EC%9A%B0%EC%97%90-%EB%8C%80%ED%95%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 support-for-dashboard-view-types=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EB%B3%B4%EA%B8%B0-%EC%9C%A0%ED%98%95-%EC%A7%80%EC%9B%90 h_01J8FJW0TEDFGFPPYZEAREKY4Q=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EB%B3%B4%EA%B8%B0-%EC%9C%A0%ED%98%95-%EC%A7%80%EC%9B%90 h_01J8FJW0TETSV5X6D7NJ4EQHGC=data-filtering-by-view-type-using-the-conversion_type-field how-do-i-identify-doubleattributed-retargeting-events-in-user-acquisition-inapp-reports=%EC%9C%A0%EC%A0%80-%EC%9D%B8%EC%9E%85-%EC%9D%B8%EC%95%B1-%EB%B3%B4%EA%B3%A0%EC%84%9C%EC%97%90%EC%84%9C-%EC%9D%B4%EC%A4%91-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A6%AC%ED%83%80%EA%B2%8C%ED%8C%85-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EB%A5%BC-%EC%8B%9D%EB%B3%84%ED%95%98%EB%A0%A4%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%95%B4%EC%95%BC-%ED%95%A9%EB%8B%88%EA%B9%8C h_01J8FJW0TED4T9JN89PCRA3M9R=%EC%9C%A0%EC%A0%80-%EC%9D%B8%EC%9E%85-%EC%9D%B8%EC%95%B1-%EB%B3%B4%EA%B3%A0%EC%84%9C%EC%97%90%EC%84%9C-%EC%9D%B4%EC%A4%91-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A6%AC%ED%83%80%EA%B2%8C%ED%8C%85-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EB%A5%BC-%EC%8B%9D%EB%B3%84%ED%95%98%EB%A0%A4%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%95%B4%EC%95%BC-%ED%95%A9%EB%8B%88%EA%B9%8C" />
