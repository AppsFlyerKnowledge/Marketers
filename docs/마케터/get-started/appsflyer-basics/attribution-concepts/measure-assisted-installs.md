---
title: 인스톨 어시스트(Assisted Installs) 설명
metadata:
  keywords:
    - Attribution
    - installs
    - Assisted
    - multi-touch
    - reporting
    - assisted intalls
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-12-24T10:21:25Z'
  edited_at: '2026-10-14T10:30:27Z'
  id: 207040506
  locale: ko
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ko/articles/207040506
---
> **한눈에 보기:** 요약: 마지막 터치 전에 사용자를 참여시키고 도움을 준 매체사의 광범위한 영향을 측정합니다.

## 어시스트된 인스톨

<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/assisted-installs-mobile-advertising-assists/">어시스트 인스톨</Anchor> (일명 멀티터치 어트리뷰션)은 미디어소스/캠페인이 마지막 터치를 하지 않았지만 인스톨 전과 어트리뷰션 윈도우 동안 유저를 터치한 인스톨입니다. 하나의 인스톨에는 최대 3개의 인스톨 어시스트가 있을 수 있습니다.

각 미디어소스와 캠페인의 광범위한 영향을 측정하기 위해 미디어소스 및 캠페인 수준에서 어시스트 인스톨의 분석 데이터를 사용할 수 있습니다.

### 개요 대시보드에서 어시스트 인스톨 지표 확인하기

**개요 대시보드에서 어시스트 인스톨을 확인하는 방법**:

1. 앱스플라이어의 사이드 메뉴에서 Analyze > **Overview**를 선택합니다.
2. 확장 개요 보고서를 선택합니다.
3. 시간 경과에 따른 추세 차트까지 아래로 스크롤합니다.
4. **미디어소스** 또는 **캠페인** 기준을 선택합니다.
5. **어시스트 인스톨** 지표를 선택합니다.  
   어시스트 인스톨 차트가 표시됩니다. 파란색은 논오가닉 인스톨을 나타내고 주황색은 어시스트 인스톨을 나타냅니다.

   ![AssitedInstallWidget.png](https://files.readme.io/a2fb5fb1f7414ede9a96858e325688d0c60b2ff910e24bc86e5597160c7548ca-33302646504977.png)

### 어시스트가 중요한 이유

많은 경우, 어시스트 소스를 통해 잠재적 사용자는 앱에 익숙해지지만, 어떤 이유인지 인스톨까지는 도달하지 못합니다. 따라서 캠페인 최적화 및 측정에 있어 어시스트를 측정하고 인식하는 것이 중요합니다.

### 인스톨 어시스트 리포트

앱스플라이어는 어트리뷰션된 인스톨 소스 외에 최대 3개의 기여 네트워크를 어트리뷰션합니다.

집계 대시보드 및 리포트에서 (최대 3개의) 기여자 네트워크는 "어시스티드 인스톨"라는 하나의 지표로 통합됩니다. 즉, 1개의 인스톨은 최대 3개의 어시스트 인스톨을 계산할 수 있습니다.

로데이터 리포트에서 기여 네트워크의 데이터는 기여자 1-3에 대한 별도의 필드로 나뉩니다.

각각의 기여 네트워크에 대하여 로데이터 리포트는 다음을 포함합니다.

* 네트워크 이름 (Media source)
* 캠페인 이름
* 참여 시간 (touch time)
* 참여 유형 (click 또는 impression)
* 연관된 에이전시 이름 (partner), 에이전시가 있는 경우.

<Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview#유저-여정-리포트">사용자 여정 로데이터</Anchor>를 참조하십시오.

> 📘 **참고**
>
> 에이전시 고려사항
> 몇몇 주요 애드 네트워크는 <Anchor target="_blank" href="/marketers/ko/docs/user-level-data-retention">그들의 데이터를 제3자 플랫폼과 공유하는 것을 제한하며</Anchor>, 여기에는 에이전시도 포함됩니다. 따라서 이런 네트워크의 경우, 인스톨 어시스트는 에이전시 대시보드에 표시되지 않습니다.

<div data-zendesk-anchors="assisted-installs=%EC%96%B4%EC%8B%9C%EC%8A%A4%ED%8A%B8%EB%90%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8 h_01HCBC922K9PCDXGDCCVEARADH=%EC%96%B4%EC%8B%9C%EC%8A%A4%ED%8A%B8%EB%90%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8 view-assisted-installs-metrics-in-the-overview-dashboard=%EA%B0%9C%EC%9A%94-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90%EC%84%9C-%EC%96%B4%EC%8B%9C%EC%8A%A4%ED%8A%B8-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%A7%80%ED%91%9C-%ED%99%95%EC%9D%B8%ED%95%98%EA%B8%B0 h_01HCBC922KRHB043FK1CQRKXDA=%EA%B0%9C%EC%9A%94-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90%EC%84%9C-%EC%96%B4%EC%8B%9C%EC%8A%A4%ED%8A%B8-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%A7%80%ED%91%9C-%ED%99%95%EC%9D%B8%ED%95%98%EA%B8%B0 why-are-assists-important=%EC%96%B4%EC%8B%9C%EC%8A%A4%ED%8A%B8%EA%B0%80-%EC%A4%91%EC%9A%94%ED%95%9C-%EC%9D%B4%EC%9C%A0 h_01HCBC922KDAG8T27KK2JGRE7C=%EC%96%B4%EC%8B%9C%EC%8A%A4%ED%8A%B8%EA%B0%80-%EC%A4%91%EC%9A%94%ED%95%9C-%EC%9D%B4%EC%9C%A0 assisted-installs-reporting=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%EC%8B%9C%EC%8A%A4%ED%8A%B8-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HCBC922KJV54QW6G85SN2JM7=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%EC%8B%9C%EC%8A%A4%ED%8A%B8-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HCBC922K5HKF94JCY7C88R88=%EC%B0%B8%EA%B3%A0" />
