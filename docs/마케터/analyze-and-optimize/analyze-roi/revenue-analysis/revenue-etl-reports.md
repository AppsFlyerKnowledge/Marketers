---
title: ROI360 수익 ETL 데이터 락커 보고서
metadata:
  keywords:
    - Marketers
    - revenue
    - etl
    - revenueetl
    - revenue etl
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2023-06-25T16:57:02Z'
  edited_at: '2026-10-14T10:40:23Z'
  id: 16464765619985
  locale: ko
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ko/articles/16464765619985
---
> **요약:** ROI360 수익 보고서, 해당 소스, 보고서 생성 방법, 사용 가능 시기 및 액세스 방법에 대해 알아보십시오. 보고서의 필드와 구조에 대해 자세히 알아보려면 데이터 샘플을 다운로드하세요.

<div id="revenue-etl" />

## 수익 ETL

ROI360 수익 ETL을 사용하면 수익 데이터가 데이터 락커를 통해 클라우드 스토리지로 전송되어 BI 시스템에 로드됩니다.

다음 표에서는 사용 가능한 수익 보고서를 보여 줍니다. **참고**: 기존 광고 수익[단일 버전] 보고서를 제외한 모든 보고서에는 ROI360 Advanced 패키지 구독이 필요합니다.

| 리포트 | 연동 타입 | 설명 | 데이터 최신성 |
| --- | --- | --- | --- |
| [기존 광고 수익[단일 버전]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level):<ul><li>어트리뷰션 광고 수익 [단일 버전 x+1]</li><li>오가닉 광고 수익 [단일 버전 x+1]</li><li>리타겟팅 광고 수익 [단일 버전 x+1]</li></ul> | <ul><li>노출 수준(SDK를 통해)</li><li>기기 단위(S2S API를 통해)</li><li>노출 수준(SDK를 통해)과 디바이스 수준(S2S API를 통해)</li></ul> | <ul><li>광고 수익 데이터를 포함합니다.</li><li>단일 버전(추가 데이터 업데이트 없음).</li><li>API 및 SDK 통합이 모두 있는 경우 보고서에는 API 데이터만 포함됩니다.</li></ul> | <ul><li>일일(x+1일에 사용 가능) <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#data-freshness">더 알아보세요</Anchor></li></ul> |
| [광고 수익[버전 관리]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level):<ul><li>어트리뷰션된 광고 수익[버전 관리]</li><li>오가닉 광고 수익[버전 지정]</li><li>리타게팅 광고 수익[버전 지정]</li></ul> | <ul><li>노출 수준(SDK를 통해)</li><li>기기 단위(S2S API를 통해)</li><li>노출 수준(SDK를 통해)과 디바이스 수준(S2S API를 통해)</li></ul> | <ul><li>최신 광고 수익 데이터가 포함되어 있습니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers#version-folders">버전 관리</Anchor></li></ul> | <ul><li>당일 내 <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#data-freshness">더 알아보기</Anchor></li><li>광고 노출 후 4시간부터 14일까지 데이터가 업데이트됩니다.</li></ul> |
| [광고 수익[SDK 노출 수준]](/docs/revenue-etl-reports#impression-level-report) | <ul><li>노출 수준(SDK를 통해)</li><li>노출 수준(SDK를 통해)과 디바이스 수준(S2S API를 통해)</li></ul> | <ul><li>광고 수익 SDK 데이터를 포함합니다.</li><li>최대한의 데이터 새로 고침과 세분성을 제공합니다.</li></ul> | 시간별. <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#data-freshness">더 알아보기</Anchor> |
| [거래 수준 매장 수익](/docs/revenue-etl-reports#transactionlevel-stores-revenue-report) | ROI360 IAP 및 서브스크립션 매출 통합 | <ul><li>트랜잭션 수준에서 ROI360 검증 인앱 구매 및 구독 원시 데이터를 포함합니다.</li><li>최대한의 데이터 새로 고침과 데이터 세분성을 제공합니다.</li><li>고유한 ROI360 수익 창출 관련 데이터 및 순 수익이 포함됩니다.</li></ul> | 시간별 |
| [장치 수준 매장 수익[버전 관리]](/docs/revenue-etl-reports#devicelevel-stores-revenue-report) | ROI360 IAP 및 서브스크립션 매출 통합 | <ul><li>장치 수준에서 ROI360 검증 인앱 구매 및 구독 원시 데이터를 포함합니다.</li><li>고유한 ROI360 순수익 데이터를 포함합니다.</li></ul> | 8시간마다 |

<div id="reports" />

## 리포트

다양한 리포트에 대한 세부 정보—작동 방식, 구독 방법 및 액세스 방법—다음 섹션에서 찾을 수 있습니다.

<div id="ad-revenue-single-version-report-device-level" />

<Accordion title="[레거시] 광고 수익(단일 버전)">

이 보고서에는 기기 수준별로 집계된 하루의 광고 수익 데이터의 단일 버전이 표시됩니다. 보고서는 X+1일(X는 매출 이벤트가 발생한 날)에 사용할 수 있습니다.

**참고:** 별도의 보고서는 유기적 및 리타게팅 수익 데이터를 제공합니다. 이러한 보고서는 구조와 가용성 면에서 동일합니다.

<span id="download-the-report-data-sample"></span>[광고 수익 단일 버전 보고서 데이터 샘플 다운로드하기](https://docs.google.com/spreadsheets/d/e/2PACX-1vSuZYSPuAWIG-MappxQDIT3sl8UmN6MLKP2SKsbREekVAvKSHuUAUAtUE6JapanANJbKsTzCOID8z7G/pub?output=xlsx).

<div id="data-sources" />

#### 데이터 소스

광고 수익 파트너 통합 유형에 따라 보고서 데이터는 다음 중 하나에서 생성될 수 있습니다.

* **SDK**: ROI360 Ad Revenue SDK 커넥터에서 보낸 노출 수준 데이터 페이로드입니다.
* **S2S:** 파트너(미디에이션 또는 수익화 네트워크)의 API 요청에 의해 가져온 디바이스 수준 리포트입니다.

통합 유형을 설정하는 방법에 대한 자세한 내용은 다음을 참조하세요. 광고 수익 연동 파트너에게 연결.

<div id="data-flow" />

#### 데이터 흐름

1. **데이터 수집:** 보고서는 광고 수익 SDK 커넥터 또는 S2S API 요청에서 생성될 수 있습니다(위 섹션 참조).
2. **데이터 처리**: 앱스플라이어 ROI360 광고 수익은 다음을 수행합니다.

   1. <span class="af-ol-a"></span>데이터 정규화,
   2. 인스톨 소스와 데이터 인리치먼트에 대한 어트리뷰션,
   3. 광고 매출 이벤트 생성,
   4. 이벤트는 장치 수준으로 집계됩니다.

   **참고:** 보고서에는 동일한 장치에 대한 둘 이상의 장치 수준 집계가 있을 수 있습니다. 이는 기기 수준 집계가 수익 창출 네트워크, 게재위치, 광고 유형과 같은 수익 창출 관련 측정기준을 기반으로 하기 때문에 발생할 수 있습니다. 예를 들어 앱이 두 개의 서로 다른 노출 위치에 광고를 게재하는 경우 각 노출 위치의 수익 이벤트는 기기 수준에서 별도로 집계됩니다.
3. **데이터 전달**: 장치 수준 데이터는 단일 보고서 버전에 기록됩니다.

<div id="when-is-the-report-data-available" />

#### 보고서 데이터는 언제 사용할 수 있습니까?

| 연동 타입 | 버전 일(X = 매출 이벤트 발생일) | 사용 가능한 버전 | 버전에는 다음 사이에 발생하는 매출 이벤트가 포함됩니다. |
| --- | --- | --- | --- |
| SDK | X일차+1 | 20:00 | 00:00 — 24:00 |
| SDK + S2S | X일차+1 | 17:00 | 00:00 — 24:00 |

<div id="how-to-subscribe-to-the-report" />

#### 보고서를 구독하려면 어떻게 해야 하나요?

1. 앱스플라이어의 사이드 메뉴에서 **보고서** > **데이터 락커**를 선택합니다.
2. **데이터 락커 콘텐츠** 창에서 **ROI360 수익ETL** 타일까지 아래로 스크롤합니다.
3. **어트리뷰션 수익[단일 버전]** 을 선택하세요.

**참고:** 리타겟팅 및 오가닉 광고 수익에 대해서도 동일한 리포트를 선택할 수 있습니다. (리타겟팅/오가닉 광고 수익[단일 버전])

<div id="how-to-access-the-report-in-your-bucket" />

#### 버킷의 리포트에 액세스하는 방법은 무엇입니까?

리포트 경로는 다음과 같은 폴더 계층으로 구성됩니다.

다음 형식으로: `<bucket-name>/t=attributed_ad_revenue/dt=<dt=yyyy-mm-dd>/h=23/`

<div id="report-folder-hierarchy" />

#### 리포트 폴더 계층 구조

광고주 버킷 내에서 어트리뷰트된 광고 수익 단일 버전 리포트의 폴더 구조의 예:

```
bucket
|
└── t=attributed_ad_revenue
    |
    ├── dt=2023-06-02
    |   |
    |   └── h=23
    |        |
    |        ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |        |
    |        ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |        │
    |        └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |
    ├── dt=2023-06-01
    |   |
    |   └── h=23
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |
    ├── dt=2023-05-31
    |   |
    .   . 
    .   .
```

**범례:**

* **dt**: 보고서에 포함된 매출 이벤트가 발생한 날짜입니다.
* **t:** 리포트 유형
* **h:** 단일 버전 생성 시간

</Accordion>

<div id="ad-revenue-versioned-report-device-level" />

<Accordion title="광고 수익(버전 관리)">

보고서에는 단일 날짜의 여러 버전의 수익 데이터가 표시됩니다. 예를 들어 6월 21일에 발생한 수익은 6월 21일, 6월 22일, 6월 23일, 6월 24일, 6월 28일, 7월 5일에 보고됩니다.

같은 날의 여러 버전을 수집하는 목적은 시간 종속 조건에서 발생하는 수익 계산 변동을 캡처하는 것입니다. 예를 들어 실시간으로 수익 가치가 있는 노출은 하루 후에 다른 가치를 가질 수 있습니다.

**참고:** 별도의 보고서는 유기적 및 리타게팅 수익 데이터를 제공합니다. 이러한 보고서는 구조와 가용성 면에서 동일합니다.

[광고 수익 버전이 지정된 보고서 데이터 샘플 다운로드하기](https://docs.google.com/spreadsheets/d/e/2PACX-1vQek1x3rYnYQq3jctSz5hnWG_Nk_LQk2ixMTQFVMb8K6w-UmeNKvKOif3-nudAyIqp9tyuoq9R-FhVz/pub?output=csv).

<div id="data-sources-1" />

#### 데이터 소스

파트너 통합 유형에 따라 보고서 데이터는 다음 중 하나에서 생성될 수 있습니다.

* **SDK**: ROI360 Ad Revenue SDK 커넥터에서 보낸 노출 수준 데이터 페이로드입니다.
* **S2S:** 파트너(미디에이션 또는 수익화 네트워크)의 API 요청에 의해 가져온 디바이스 수준 리포트입니다.
* **S2S + SDK:** SDK 및 S2S 모두에서 시작되는 페이로드입니다.

통합 유형을 설정하는 방법에 대한 자세한 내용은 다음을 참조하세요. 광고 수익 연동 파트너에게 연결.

<div id="data-flow-1" />

#### 데이터 흐름

1. **데이터 수집:** 보고서는 SDK 또는 S2S API 요청에서 시작될 수 있습니다(위 섹션 참조).
2. **데이터 처리:** 앱스플라이어 ROI360 광고 수익은 다음을 수행합니다.

   1. <span class="af-ol-a"></span>데이터 정규화,
   2. 인스톨 소스와 데이터 인리치먼트에 대한 어트리뷰션,
   3. 광고 매출 이벤트 생성,
   4. 이벤트는 장치 수준으로 집계됩니다.

   **참고:** 보고서에는 동일한 장치에 대한 둘 이상의 장치 수준 집계가 있을 수 있습니다. 이는 기기 수준 집계가 수익 창출 네트워크, 게재위치, 광고 유형과 같은 수익 창출 관련 측정기준을 기반으로 하기 때문에 발생할 수 있습니다. 예를 들어 앱이 두 개의 서로 다른 노출 위치에 광고를 게재하는 경우 각 노출 위치의 수익 이벤트는 기기 수준에서 별도로 집계됩니다.
3. **데이터 전달**: 장치 수준 데이터는 미리 결정된 일정(아래에 지정됨)에 따라 여러 보고서 버전에 기록됩니다.

<div id="when-are-the-report-versions-available" />

#### 리포트 버전은 언제 사용할 수 있습니까?

아래 표에는 S2S 및 SDK 버전 모두에 대한 생성 일정이 요약되어 있습니다. ROI360 광고 수익 Freshness to Accuracy 기능의 혜택을 받는 고객은 두 가지 버전을 모두 제공받아, 최적의 정확성과 데이터 최신성을 보장받을 수 있습니다.

| 연동 유형 | 버전 일(X = 매출 이벤트 발생일) | 사용 가능한 버전 | 버전에는 다음 사이에 발생하는 매출 이벤트가 포함됩니다. |
| --- | --- | --- | --- |
| SDK | X일차 | 03:00-04:00 | 00:00 — 03:00 |
| SDK | X일차 | 07:00-08:00 | 00:00 — 07:00 |
| SDK | X일차 | 11:00-12:00 | 00:00 — 11:00 |
| SDK | X일차 | 15:00-16:00 | 00:00 — 15:00 |
| SDK | X일차 | 19:00-20:00 | 00:00 — 19:00 |
| SDK | X일차 | 23:00-24:00 | 00:00 — 23:00 |
| SDK | X일차+1 | 04:00-05:00 | 00:00 — 24:00 |
| S2S | X일차+1 | 12:00-13:00 | 00:00 — 24:00 |
| S2S | X일차+1 | 18:00-19:00 | 00:00 — 24:00 |
| S2S | X일차+2 | 00:00-01:00 | 00:00 — 24:00 |
| S2S | X일차+2 | 13:00-14:00 | 00:00 — 24:00 |
| S2S | X일차+3 | 06:00-07:00 | 00:00 — 24:00 |
| S2S | X일차+7 | 08:00-09:00 | 00:00 — 24:00 |
| S2S | X일차+14 | 10:00-11:00 | 00:00 — 24:00 |
| SDK + S2S | 위의 모든 SDK 및 S2S 버전 |  |  |

**참고:** 일부 S2S 원본 버전은 생성되지 않을 수 있습니다. 마지막 끌어오기 이후 파트너의 데이터가 변경되지 않은 경우 새 버전이 생성되지 않습니다.

<div id="how-to-subscribe-to-the-report-1" />

#### 보고서를 구독하려면 어떻게 해야 하나요?

1. 앱스플라이어의 사이드 메뉴에서 **보고서** > **데이터 락커**를 선택합니다.
2. **데이터 락커 콘텐츠** 창에서 **ROI360 수익ETL** 타일까지 아래로 스크롤합니다.
3. **어트리뷰션 광고 수익[버전]** 을 선택하세요.

**참고:** 리타겟팅 및 오가닉 광고 수익에 대해서도 동일한 리포트를 선택할 수 있습니다. (리타겟팅/오가닉 광고 수익[버전 관리])

<div id="how-to-access-the-report-in-your-bucket-2" />

<div id="how-to-access-the-report-in-your-bucket-1" />

#### 버킷의 리포트에 액세스하는 방법은 무엇입니까?

보고서 경로는 다음과 같은 폴더 계층으로 구성됩니다.

`<bucket-name>/t=attributed_ad_revenue_v2/dt=<dt=yyyy-mm-dd>/version=<9999999>/`

<div id="report-folder-hierarchy-2" />

<div id="report-folder-hierarchy-1" />

#### 보고서 폴더 계층 구조

광고주 버킷에 있는 리포트 트리의 예:

```
bucket
|
└── t=attributed_ad_revenue_v2
    |
    └── dt=2023-06-01
        |
        ├── version=1685588879
        |   |
        │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   |
        │   ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   │
        |   └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |
        ├── version=1685603326
        |   |
        │   ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   |
        │   ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   │
        |   └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |
        ├── version=1685617877
        .
                .
                .
```

* **범례:**
  * **t:** 리포트 유형
  * **dt**: 보고서에 포함된 매출 이벤트가 발생한 날짜입니다.
  * **버전:** 버전의 이름은 버전 생성 날짜 및 시간의 epoch 타임스탬프입니다(예: **버전=1685588879**).
* S2S 또는 SDK에 관계없이 버전의 출처는 버전 생성 시간에서 알 수 있습니다. 첫 번째 SDK 버전은 SDK에서 시작됩니다. 나머지는 S2S입니다.

</Accordion>

<div id="impression-level-report" />

<Accordion title="광고 수익(SDK 노출 수준)">

리포트에는 발생 시간별 폴더로 구분된 노출 수준 데이터가 표시됩니다. 각 폴더에는 **해당 시간 동안 발생한 노출만 포함**됩니다.

[광고 수익 노출 수준 리포트 데이터 샘플 다운로드하기](https://docs.google.com/spreadsheets/d/e/2PACX-1vR5zVxFGaCMNZMbCCYPae6f7MmbtelxrqXb-A5DBENuyTFCN4deRfICvbL0_dNeYVipojmAeUdrGbKI/pub?output=csv)

<div id="data-source" />

#### 데이터 소스

보고서 데이터는 ROI360 광고 수익 SDK 커넥터에서 보낸 노출 수준 데이터에서 생성되며 SDK 유형 통합이 필요합니다.

통합 유형을 설정하는 방법에 대한 자세한 내용은 다음을 참조하세요. 광고 수익 연동 파트너에게 연결.

<div id="data-flow-2" />

#### 데이터 흐름

1. **데이터 수집:** 보고서 데이터는 ROI360 광고 수익 SDK 커넥터에서 보낸 노출 수준 데이터에서 생성되며 SDK 유형 통합이 필요합니다.
2. **데이터 처리**: 앱스플라이어 ROI360 광고 수익은 다음을 수행합니다.
   1. <span class="af-ol-a"></span>데이터 정규화,
   2. 인스톨 소스와 데이터 인리치먼트에 대한 어트리뷰션,
   3. 노출 수준 광고 수익 이벤트 생성.
3. **데이터 전달**: 노출 이벤트는 발생 시간에 따라 폴더별로 나뉘어진 파일에 기록됩니다. 각 폴더에는 해당 시간 동안 발생한 노출수만 포함됩니다.

<div id="when-is-the-report-data-available-1" />

#### 보고서 데이터는 언제 사용할 수 있습니까?

| 연동 타입 | 버전 일(X = 매출 이벤트 발생일) | 사용 가능한 버전 |
| --- | --- | --- |
| SDK | X일차 | 보고된 모든 시간이 끝날 때 |

<div id="how-to-subscribe-to-the-report-2" />

#### 보고서를 구독하려면 어떻게 해야 하나요?

1. 앱스플라이어의 사이드 메뉴에서 **보고서** > **데이터 락커**를 선택합니다.
2. **데이터 락커 콘텐츠** 창에서 **ROI360 수익ETL** 타일까지 아래로 스크롤합니다.
3. **광고 수익[SDK 노출 수준]** 을 선택하세요.

<div id="how-to-access-the-report-in-your-bucket-3" />

#### 버킷의 보고서에 액세스하는 방법은 무엇입니까?

보고서 경로는 다음과 같은 폴더 계층으로 구성됩니다.

`<bucket-name>/t=attributed_adrevenue_sdk_impression_level/dt=<dt=yyyy-mm-dd>/h=<hh>`

#### 보고서 폴더 계층 구조

광고주 버킷에 있는 리포트 트리의 예:

```
bucket
|
└── t=attributed_adrevenue_sdk_impression_level/
    |
    ├── dt=2023-06-01
    |   |
    |   ├── h=0
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=1
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=2
    |   .   |
    |   .   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   .   .
    |   ├── h=23
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   └── h=24
    |       |
    |       └── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |    
    ├── dt=2023-06-02
    |   |  
    |   ├── h=0
        .   .
        .   .
```

**범례:**

* **t:** 리포트 유형
* **dt**: 보고서에 포함된 매출 이벤트가 발생한 날짜입니다.
* **h**: 특정 시간 동안 발생한 노출수가 있는 CSV 파일이 포함된 시간별 폴더입니다.

</Accordion>

<div id="transactionlevel-stores-revenue-report" />

<Accordion title="거래 수준 스토어 수익">

이 보고서는 트랜잭션 레벨에서 원시 일별 데이터를 제공하며, 해당 시간과 관련된 트랜잭션만 포함하는 시간별 폴더로 나뉩니다.

[거래 수준 매장 보고서 데이터 샘플 다운로드](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGlRSg_Xrp2EsqK2uaisjhlqeSuZsypqKqSSRGX3AQBwBLlNdG_5LOOKCM9f9gCcLguMQgQwT--Dz7/pub?output=csv)

<div id="data-sources-3" />

<div id="data-sources-2" />

#### 데이터 소스

보고서 데이터는 ROI360 SDK 구매 커넥터 및 서버 간 저장소 알림을 통해 수집된 트랜잭션에서 비롯됩니다.

<div id="data-flow-3" />

#### 데이터 흐름

1. 보고서 데이터는 ROI360 SDK 구매 커넥터 페이로드 또는 S2S 스토어 알림을 통해 수집된 트랜잭션에서 비롯됩니다.
2. 앱스플라이어 ROI360 VIAP/구독은 데이터를 처리하고, 어트리뷰션하며, 트랜잭션 수준의 이벤트와 값을 생성합니다.
3. 트랜잭션 수준 이벤트는 시간별 폴더로 나뉘어 보고서에 기록됩니다.

<div id="when-is-the-report-data-available-2" />

#### 보고서 데이터는 언제 사용할 수 있습니까?

| 버전 일(X = 매출 이벤트 발생일) | 사용 가능한 버전 |
| --- | --- |
| X일차 | 보고된 모든 시간이 끝날 때 |

<div id="how-to-subscribe-to-the-report-3" />

#### 보고서를 구독하려면 어떻게 해야 하나요?

1. 앱스플라이어의 사이드 메뉴에서 **보고서** > **데이터 락커**를 선택합니다.
2. **데이터 락커 콘텐츠** 창에서 **ROI360 수익ETL** 타일까지 아래로 스크롤합니다.
3. **거래 수준 매장 수익 보고서**를 선택하세요.

<div id="how-to-access-the-report-in-your-bucket-4" />

#### 버킷의 보고서에 액세스하는 방법은 무엇입니까?

보고서 경로는 다음과 같은 폴더 계층으로 구성됩니다.

`<bucket-name>/t=stores_rawdata/dt=<dt=yyyy-mm-dd>/h=<hh>`

<div id="report-folder-hierarchy-3" />

#### 보고서 폴더 계층 구조

광고주 버킷에 있는 리포트 트리의 예:

```
bucket
|
└── t=stores_rawdata
    |
    ├── dt=2023-06-01
    |   |
    |   ├── h=0
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=1
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=2
    |   .   |
    |   .   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   .   .
    |   ├── h=23
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   └── h=24
    |       |
    |       └── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |    
    ├── dt=2023-06-02
    |   |  
    |   ├── h=0
        .   .
        .   .
```

**범례:**

* **t:** 리포트 유형
* **dt**: 보고서에 포함된 매출 이벤트가 발생한 날짜입니다.
* **h**: 특정 시간 동안 발생한 트랜잭션이 있는 CSV 파일이 포함된 시간별 폴더입니다.

</Accordion>

<div id="devicelevel-stores-revenue-report" />

<Accordion title="디바이스 수준 스토어 수익(버전 관리)">

기기 수준 스토어 수익 보고서는 ROI360 제품에서 캡처한 인앱 구매 및 자동 갱신 구독 이벤트를 지정합니다. 이러한 이벤트에는 고유한 ROI360 수익 창출 관련 차원이 포함됩니다. 고객이 발행한 인앱 이벤트는 이 보고서에 포함되지 않습니다.

<span id="download-the-report-data-sample::8cbba4e3"></span>[디바이스 수준 매장 수익 보고서 데이터 샘플 다운로드](https://docs.google.com/spreadsheets/d/e/2PACX-1vSpomvcf2axYeSFcCh0kEx3ShYYRGVfF9WYZXG1UYBkeymeVfh8mcypAOpq2drqE3zhdmbcmrMtahsl/pub?output=csv)

#### 데이터 소스

보고서 데이터는 다음을 통해 수집된 트랜잭션에서 비롯됩니다.

1. ROI360 SDK 구매 커넥터.
2. 서버 간 알림을 통한 스토어(예: App Store 및 Google Play Store).

<div id="data-flow-4" />

#### 데이터 흐름

1. 보고서 데이터는 ROI360 SDK 구매 커넥터 페이로드 또는 S2S 스토어 알림을 통해 수집된 트랜잭션에서 비롯됩니다.
2. 앱스플라이어 ROI360 VIAP/구독은 데이터를 처리하고, 어트리뷰션하고, 인앱 이벤트를 생성합니다.
3. 인앱 이벤트는 장치 수준으로 집계되고 4시간마다 보고서 버전에 기록됩니다.

<div id="when-are-the-report-versions-available-1" />

#### 보고서 버전은 언제 사용할 수 있습니까?

| 버전 일(X = 매출 이벤트 발생일) | 사용 가능한 버전 | 버전에는 다음 사이에 발생하는 매출 이벤트가 포함됩니다. |
| --- | --- | --- |
| X일차 | 04:00 - 05:00 | 00:00 — 04:00 |
| X일차 | 12:00 - 13:00 | 00:00 — 12:00 |
| X일차 | 20:00 - 21:00 | 00:00 — 20:00 |
| X일차+1 | 05:00 - 06:00 | 00:00 — 24:00 |

<div id="how-to-subscribe-to-the-report-4" />

#### 보고서를 구독하려면 어떻게 해야 하나요?

1. 앱스플라이어의 사이드 메뉴에서 **보고서** > **데이터 락커**를 선택합니다.
2. **데이터 락커 콘텐츠** 창에서 **ROI360 수익ETL** 타일까지 아래로 스크롤합니다.
3. **장치 수준 매장 수익 보고서[버전 관리]** 를 선택합니다.

#### 버킷의 보고서에 액세스하는 방법은 무엇입니까?

보고서 경로는 다음과 같은 폴더 계층으로 구성됩니다.

`<bucket-name>/t=stores_devicedata/dt=<dt=yyyy-mm-dd>/version=<999999999>`

<div id="report-folder-hierarchy-4" />

#### 보고서 폴더 계층 구조

광고주 버킷에 있는 리포트 트리의 예:

```
bucket
|
└── t=stores_devicedata
    |
    └── dt=2023-06-01
        |
        ├── version=1685588879
        |   |
        │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   |
        │   ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   │
        |   └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |
        ├── version=1685603326
        |   |
        │   ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   |
        │   ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   │
        |   └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |
        ├── version=1685617877
        .
                .
                .
```

**범례:**

* **t:** 리포트 유형
* **dt**: 보고서에 포함된 매출 이벤트가 발생한 날짜입니다.
* **버전**: 버전의 이름은 버전 생성 날짜 및 시간의 epoch 타임스탬프입니다(예: **버전=1685588879**.

</Accordion>

<div data-zendesk-anchors="revenue-etl=%EC%88%98%EC%9D%B5-etl h_01HMBTDD8TASZ2NEBXP7CZ3Q81=%EC%88%98%EC%9D%B5-etl reports=%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HME0BBF2M47M2AV437RYQ070=%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HETBAQVVYW14END06HBPBQSN=ad-revenue-single-version-report-device-level h_01HETBAQVVZB87JNT0JVYSP80D=download-the-report-data-sample the-report-data-sources=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4 h_01HETBAQVVSKVDM4J90A0WGFJW=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4 the-report-data-flow=%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%9D%90%EB%A6%84 h_01HETBAQVV97R7G6F67RM6K62K=%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%9D%90%EB%A6%84 when-is-the-report-data-available=%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%8A%94-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EC%8A%B5%EB%8B%88%EA%B9%8C h_01HETBAQVVKDAWW2S98TG6682S=%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%8A%94-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EC%8A%B5%EB%8B%88%EA%B9%8C how-to-subscribe-to-the-report=%EB%B3%B4%EA%B3%A0%EC%84%9C%EB%A5%BC-%EA%B5%AC%EB%8F%85%ED%95%98%EB%A0%A4%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94 h_01HETBAQVVFSDRW778VQSSE107=%EB%B3%B4%EA%B3%A0%EC%84%9C%EB%A5%BC-%EA%B5%AC%EB%8F%85%ED%95%98%EB%A0%A4%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94 how-to-access-the-report-in-dl=%EB%B2%84%ED%82%B7%EC%9D%98-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C h_01HETBAQVV15T92VXRHG2CP2KJ=%EB%B2%84%ED%82%B7%EC%9D%98-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C the-report-folder-hierarchy-in-aws=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%8F%B4%EB%8D%94-%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0 h_01HETBAQVVA750VTE1ABSM2M47=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%8F%B4%EB%8D%94-%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0 h_01HETBAQVVCB2SYMW9876HPE7N=ad-revenue-versioned-report-device-level data-sources=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4-1 h_01HMTZ9VQ5WE6D7E5NEBYH71SZ=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4-1 data-flow=%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%9D%90%EB%A6%84-1 h_01HMTZ9VQ5PS8G9JTQ2YXF1G7X=%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%9D%90%EB%A6%84-1 when-are-the-report-versions-available=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%B2%84%EC%A0%84%EC%9D%80-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EC%8A%B5%EB%8B%88%EA%B9%8C h_01HETBAQVVP1M40KHB66AW545S=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%B2%84%EC%A0%84%EC%9D%80-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EC%8A%B5%EB%8B%88%EA%B9%8C how-to-subscribe-to-the-report::cae4aa15=%EB%B3%B4%EA%B3%A0%EC%84%9C%EB%A5%BC-%EA%B5%AC%EB%8F%85%ED%95%98%EB%A0%A4%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94-1 h_01HMTZ9VQ5BBFNNE7Z8EP084CF=%EB%B3%B4%EA%B3%A0%EC%84%9C%EB%A5%BC-%EA%B5%AC%EB%8F%85%ED%95%98%EB%A0%A4%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94-1 how-to-access-the-report-in-your-bucket=%EB%B2%84%ED%82%B7%EC%9D%98-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C-1 h_01HMTZ9VQ5FGBC56AP4R49P4BX=%EB%B2%84%ED%82%B7%EC%9D%98-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C-1 report-folder-hierarchy=%EB%B3%B4%EA%B3%A0%EC%84%9C-%ED%8F%B4%EB%8D%94-%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0 h_01HMTZ9VQ5HCKP7T3JQ2RHZV50=%EB%B3%B4%EA%B3%A0%EC%84%9C-%ED%8F%B4%EB%8D%94-%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0 h_01HETBAQVVR90NJC522WNAG190=impression-level-report the-source-of-the-report-data=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4-2 h_01HETBAQVV3KBEW4VV4RY9VRA2=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4-2 data-flow::c7ffb834=%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%9D%90%EB%A6%84-2 h_01HMTZ9VQ5J837PGG99S8ARAGV=%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%9D%90%EB%A6%84-2 when-is-the-report-data-available::272621c9=%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%8A%94-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EC%8A%B5%EB%8B%88%EA%B9%8C-1 h_01HMTZ9VQ5YQKBQ779YWBWESDZ=%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%8A%94-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EC%8A%B5%EB%8B%88%EA%B9%8C-1 how-to-subscribe-to-the-report::67646c99=%EB%B3%B4%EA%B3%A0%EC%84%9C%EB%A5%BC-%EA%B5%AC%EB%8F%85%ED%95%98%EB%A0%A4%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94-2 h_01HMTZ9VQ5ZST1M7JYKFC3DA62=%EB%B3%B4%EA%B3%A0%EC%84%9C%EB%A5%BC-%EA%B5%AC%EB%8F%85%ED%95%98%EB%A0%A4%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94-2 how-to-access-the-report-in-aws-the-bucket=%EB%B2%84%ED%82%B7%EC%9D%98-%EB%B3%B4%EA%B3%A0%EC%84%9C%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C h_01HETBAQVVHE80MH3SM3GX21V1=%EB%B2%84%ED%82%B7%EC%9D%98-%EB%B3%B4%EA%B3%A0%EC%84%9C%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C report-folder-hierarchy::26ec73c6=%EB%B3%B4%EA%B3%A0%EC%84%9C-%ED%8F%B4%EB%8D%94-%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0-1 h_01HMTZ9VQ5FFSA1XF7YSATM6WH=%EB%B3%B4%EA%B3%A0%EC%84%9C-%ED%8F%B4%EB%8D%94-%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0-1 h_01HETBAQVWZKYBAG5E71KVB9PM=transactionlevel-stores-revenue-report data-sources::68e71455=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4-3 h_01HMTZ9VQ5SWTWTSNW5M9KJ1XN=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4-3 data-flow::bde19643=%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%9D%90%EB%A6%84-4 h_01HMTZ9VQ6XVHDHBKV86F3Q9DJ=%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%9D%90%EB%A6%84-4 when-is-the-report-data-available::87d17fc2=%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%8A%94-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EC%8A%B5%EB%8B%88%EA%B9%8C-2 h_01HMTZ9VQ64AJQM861M6ENHVWC=%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%8A%94-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EC%8A%B5%EB%8B%88%EA%B9%8C-2 how-to-subscribe-to-the-report::6569d202=%EB%B3%B4%EA%B3%A0%EC%84%9C%EB%A5%BC-%EA%B5%AC%EB%8F%85%ED%95%98%EB%A0%A4%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94-3 h_01HMTZ9VQ60HMM6TXAPYSZG5CT=%EB%B3%B4%EA%B3%A0%EC%84%9C%EB%A5%BC-%EA%B5%AC%EB%8F%85%ED%95%98%EB%A0%A4%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94-3 how-to-access-the-report-in-your-bucket::b136ba80=%EB%B2%84%ED%82%B7%EC%9D%98-%EB%B3%B4%EA%B3%A0%EC%84%9C%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C-1 h_01HMTZ9VQ67ZEX3KM6CV32SNBD=%EB%B2%84%ED%82%B7%EC%9D%98-%EB%B3%B4%EA%B3%A0%EC%84%9C%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C-1 report-folder-hierarchy::805d4d8=%EB%B3%B4%EA%B3%A0%EC%84%9C-%ED%8F%B4%EB%8D%94-%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0-2 h_01HMTZ9VQ68VRJRHXSNAE38A0E=%EB%B3%B4%EA%B3%A0%EC%84%9C-%ED%8F%B4%EB%8D%94-%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0-2 h_01HETBAQVVWAFEMK8ENWN7DYEY=devicelevel-stores-revenue-report h_01HETBAQVV9PSDJNS76SNX522C=download-the-report-data-sample::8cbba4e3 the-report-data-sources::af31e5d1=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4-4 h_01HETBAQVWE2R75D034VCYMTR1=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4-4 the-report-data-processing-flow=%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%9D%90%EB%A6%84-4 h_01HETBAQVWZRBE84NV403BCZ9F=%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%9D%90%EB%A6%84-4 when-are-the-report-versions-available::2f1bc55f=%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%B2%84%EC%A0%84%EC%9D%80-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EC%8A%B5%EB%8B%88%EA%B9%8C h_01HETBAQVWQFCKHMT6PJNPXX7D=%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%B2%84%EC%A0%84%EC%9D%80-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EC%8A%B5%EB%8B%88%EA%B9%8C how-to-subscribe-to-the-report::a624afde=%EB%B3%B4%EA%B3%A0%EC%84%9C%EB%A5%BC-%EA%B5%AC%EB%8F%85%ED%95%98%EB%A0%A4%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94-4 h_01HETBAQVW54MD9Q09RNC673PE=%EB%B3%B4%EA%B3%A0%EC%84%9C%EB%A5%BC-%EA%B5%AC%EB%8F%85%ED%95%98%EB%A0%A4%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94-4 how-to-access-the-report-in-the-aws-bucket=%EB%B2%84%ED%82%B7%EC%9D%98-%EB%B3%B4%EA%B3%A0%EC%84%9C%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C-2 h_01HETBAQVWYDR81WS9Q9G20ZND=%EB%B2%84%ED%82%B7%EC%9D%98-%EB%B3%B4%EA%B3%A0%EC%84%9C%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C-2 the-report-folder-hierarchy-in-aws::45c0d598=%EB%B3%B4%EA%B3%A0%EC%84%9C-%ED%8F%B4%EB%8D%94-%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0-3 h_01HETBAQVWXHK6DXFA90GJQWPV=%EB%B3%B4%EA%B3%A0%EC%84%9C-%ED%8F%B4%EB%8D%94-%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0-3" />
