---
title: ROI360—비용 집계 개요
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Premium
    - Premium Feature
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2015-12-24T10:45:16Z'
  edited_at: '2026-10-14T10:27:32Z'
  id: 207040526
  locale: ko
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/ko/articles/207040526
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 광고주가 마케팅 비용 데이터를 집계하고 확인할 수 있는 방법에 대해 알아보세요.

<div id="cost-aggregation" />

## 비용 집약

**ROI360**:

* 종합 광고 비용 데이터 및 비용 관련 LTV (평생 가치) 성과 지표를 제공합니다. 이러한 정보는 대시보드와 성과 보고서를 통해 확인할 수 있습니다. 사용 가능한 비용 관련 지표에는 ROI, ROAS, 클릭, 노출, 캠페인 ROI 및 평균 인스톨당 유효 비용(eCPI)이 포함됩니다.
* 모바일 앱, 웹 브라우저, CTV, PC 및 콘솔을 포함한 모든 플랫폼의 광고 비용을 지원합니다.
* 파트너가 사용하는 다양한 비용 모델(CPI, CPA, CPC, CPM 등)을 지원합니다.
* API, 비용 가져오기(CSV 파일 업로드), <Anchor target="_blank" href="/marketers/ko/docs/view-aggregated-cost-data-for-attribution-links">어트리뷰션 링크의 비용</Anchor>을 통해 광고 비용을 기록합니다.
* 에이전시는 ROI360을 구독하는 광고주의 ROI360 비용 데이터에 대한 권한을 가질 수 있습니다.

ROI360을 사용하지 않는 광고주는 다음 지표를 사용할 수 있습니다.

* <Anchor target="_blank" href="/marketers/ko/docs/view-aggregated-cost-data-for-attribution-links">어트리뷰션 링크에 보고된 비용 데이터</Anchor>.
* **SRN 통합 파트너 비용 탭을 통해 구성된 SRN (자체 보고 네트워크) 클릭 및 노출 데이터.**

<div id="principles-of-cost-data-aggregation" />

## 비용 데이터 집계 원리

이 섹션에서는 캠페인 비용 데이터 집계의 기본 원리에 대해 설명합니다.

<div id="cost-aggregation-methods" />

<Accordion title="비용 집계 방법">

비용 데이터는 하나 이상의 방법을 사용하여 파트너로부터 얻습니다. 비용이 여러 방법으로 보고되는 경우, [비용 우선순위 메커니즘](/docs/roi360-cost-aggregation-overview#cost-prioritization-mechanism)에 따라 사용할 데이터가 결정됩니다. 이렇게 하면 비용 데이터가 부풀려지지 않습니다.

<Anchor target="_blank" href="/marketers/ko/docs/changing-app-time-zone-settings">앱스플라이어가 데이터를 처리한 후 UTC 시간대 (기본값) 또는 앱별 시간대 설정에 따라 데이터를 표시합니다.</Anchor>

<table><thead><tr><th>비용 집계 방법</th><th>지원되는 비용 모델</th><th>데이터 세분화 수준</th><th>데이터 최신성</th><th>비고</th></tr></thead><tbody><tr><td> <a href="./set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화" target="_blank">API</a>\*</td><td>모두</td><td>레벨은 연동에 따라 달라집니다.</td><td><a href="./about-data-freshness-and-timezone-support#intraday-during-the-day" target="_blank">당일 내</a></td><td>비용 이벤트 발생 이후 데이터가 변동될 수 있습니다. 이는 (미디어 소스에 따라) 최대 7일 전의 데이터까지 수신하기 위해 시도하기 때문입니다. 이를 통해 미디어 소스의 변경 사항을 소급 적용할 수 있습니다.</td></tr><tr><td><a href="./import-cost-data" target="_blank">비용 가져오기(파일 업로드)</a></td><td>모두</td><td>업로드된 파일에 따라 레벨이 다름</td><td>가져오기 후 최대 4시간</td><td>보고된 비용은 되돌릴 수 있으며 최대 90일 동안 수정된 데이터를 제출할 수 있습니다.</td></tr><tr><td><a href="./view-aggregated-cost-data-for-attribution-links" target="_blank">어트리뷰션 링크의 비용</a></td><td>CPI</td><td>사용자 수준</td><td><p>최소: 실시간</p><p>최대: 링크를 클릭된 후 최대 4시간</p></td><td>변경 불가</td></tr><tr><td colspan="5">\* 앱스플라이어와 파트너사 사이의 API 연동은 Cost API나 InCost API를 통해 이루어집니다(두 API를 동시에 사용할 수는 없습니다). 사용되는 API와 제공되는 데이터 세분성은 파트너에 따라 다릅니다.</td></tr></tbody></table>

</Accordion>

<div id="cost-data-availability-and-reports" />

<Accordion title="비용 데이터를 조회할 수 있는 대시보드 및 리포트">

다음 표는 비용 데이터를 확인할 수 있는 위치를 보여줍니다.

표를 이해하기 위해 표 주석에서 달리 명시되지 않은 한 다음 설명이 적용됩니다.

<div id="note" />

<div id="cost-in-the-ua-view" />

#### UA 뷰에서 비용

캠페인 비용 데이터는 비용이 보고된 날짜(설치 날짜) 및 해당 날짜의 ±10일 이내에 최소 1개의 설치, 클릭 또는 노출이 기록되었는지 여부에 따라 사용자 유입으로 분류됩니다. 매칭은 미디어 소스, 캠페인 ID 및 대행사를 기반으로 이루어집니다.

<div id="cost-in-the-unified-view" />

#### 통합 보기의 비용

통합 뷰에는 비용이 보고된 날짜(설치 날짜)의 ±10일 이내에 설치, 클릭 또는 노출이 존재하는지 여부와 관계없이, 선택한 앱의 모든 캠페인에 대한 비용 데이터가 포함됩니다.

<div id="example" />

#### 예시

* 예를 들어 캠페인 X의 비용이 3월 10일에 보고되고, 캠페인 X에 3월 1일에서 3월 20일 사이에 최소 1개의 클릭 또는 설치가 발생했다면, 3월 10일의 비용은 UA 뷰와 통합 뷰에 모두 표시됩니다.

  * 해당 기간에 활동이 없는 경우, 3월 10일의 비용은 **통합에만** 표시됩니다.
* 캠페인 이름 변경이 지원되지 않는 경우 두 캠페인 이름이 모두 표시됩니다. 하나에는 어트리뷰션 데이터가, 다른 하나에는 비용 데이터가 표시됩니다. 표시된 캠페인 이름에는 전체 데이터 내용이 포함되지 않습니다.

<div id="note-1" />

<div id="cost-data-availability-and-reports-table" />

#### 비용 데이터를 조회할 수 있는 대시보드 및 리포트

| 리포트 메서드 | 뷰/데이터 유형 | 캠페인 이름 변경 지원 | 비고 |
| --- | --- | --- | --- |
| 개요 대시보드 | <ul><li>UA</li><li>통합</li></ul> | 예 | 리타겟팅 뷰에서는 비용이 표시되지 않습니다. 리타케팅 비용은 통합 뷰에 표시됩니다. |
| 액티비티 대시보드 | UA | 예 |  |
| 코호트 대시보드 | <ul><li>UA</li><li>통합</li></ul> | 예 | <ul><li>리타게팅 뷰는 비용을 표시하지 않습니다.</li><li>이 통합 데이터는 비용이 보고된 날짜(설치 날짜)의 ±10일 이내에 최소 1개의 설치, 클릭 또는 노출이 기록된 캠페인에 한해서만 제공됩니다.</li></ul> |
| 코호트 API | <ul><li>UA</li><li>통합</li></ul> | 예 | 이 통합 데이터는 비용이 보고된 날짜(설치 날짜)의 ±10일 이내에 최소 1개의 설치, 클릭 또는 노출이 기록된 캠페인에 한해서만 제공됩니다. |
| SKAN 대시보드 | SKAN | 아니요 | **SKAN 설치는 모든 설치(SKAN이 아닌 설치 포함)에 대한 비용 데이터와 함께 표시됩니다.** |
| SKAN 집약형 성과 API | SKAN | 아니요 | **SKAN 설치는 모든 설치(SKAN이 아닌 설치 포함)에 대한 비용 데이터와 함께 표시됩니다.** |
| 피봇 대시보드 | UA | 아니요 |  |
| 마스터 API | UA | 아니요 |  |
| 커스텀 대시보드 | UA | 아니요 |  |
| 비용 ETL | 통합 | 예 | 모든 사용 가능한 비용 데이터가 표시됩니다. |
| 집약형 Pull API | UA | 아니요 |  |
| Push API | 원시 클릭 데이터(집계되지 않음) | 관련 없음 |  |
| 로데이터 Pull API | 원시 클릭 데이터(집계되지 않음) | 관련 없음 |  |
| 데이터 락커 | 원시 클릭 데이터(집계되지 않음) | 관련 없음 | 데이터 락커 코호트는 비용을 지원하지 않습니다. |

**참고**:

* 데이터 세분성은 대시보드/보고서 유형에 따라 다를 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-and-use-roi360-cost-etl-reports">비용 ETL</Anchor> 리포팅 도구는 전체 데이터 세트를 포함합니다. 여기에는 캠페인 계층 구조 세부 정보(미디어 소스, 캠페인 이름, 광고 세트 및 지역, 채널, 사이트 ID, 키워드를 포함하여 미디어 소스에서 제공하는 가용 디멘션)가 포함됩니다.
* 어트리뷰션 링크에 보고된 비용 데이터는 원시 데이터 보고서에서 확인할 수 있습니다.

</Accordion>

<div id="cost-prioritization-mechanism" />

<Accordion title="비용 산정 방식 우선 순위 메커니즘">

![](https://files.readme.io/8dbea1b8561d67f77d27cad85ab109e5203930273f32d2a9b04900b810c46ec2-25433450962577.png)

특정 미디어 소스의 경우, 비용 데이터가 둘 이상의 집계 방식으로 수집될 수 있습니다. 비용 과다 집계를 막기 위해, 캠페인 비용 우선 순위 메커니즘은 플랫폼에서 어떤 비용 데이터가 사용되는지를 결정합니다. 집계 방법에 따라 우선 순위가 결정됩니다. 우선순위는 가장 낮은 것부터 오름차순으로 어트리뷰션 링크의 비용 > 비용 API > 비용 가져오기.

비용 우선순위 지정 메커니즘은 집계 데이터 보고서 및 대시보드에 영향을 미칩니다. 원시 데이터 보고서에 제공되는 어트리뷰션 링크의 비용 데이터는 우선순위 메커니즘의 영향을 받지 않습니다.

**고려사항:**

* 우선순위 메커니즘은 캠페인 수준에서 작동합니다. 즉, 하나의 캠페인에 대해 서로 다른 메커니즘을 통해 두 개의 비용 입력을 받으면 경쟁을 통해 우선순위가 높은 캠페인이 전체 캠페인에서 승리하게 됩니다.
  * 어떤 날에는 특정 앱과 미디어 소스(또는 에이전시)에 대해 비용 API를 통해 비용 데이터가 있을 경우, 어트리뷰션 링크의 비용 데이터는 무시됩니다.
* 비용 집계 방법을 변경하면, 변경 사항이 소급 적용됩니다. 과거 집계 비용 데이터는 변경될 수 있습니다.
* 비용 집계 방법 변경은 에이전시 생성 트래픽에도 동일한 방식으로 영향을 미칩니다. 여기에는 투명 대행사와 비투명 대행사가 모두 포함됩니다.

<div id="example-1" />

> 📄 **예시**
>
> 미디어 소스가 어트리뷰션 링크를 통해 비용을 보고하고 있지만, 사용자가 해당 미디어 소스의 비용 API(Cost API)를 활성화하기로 결정한 경우입니다.
>
> **결과:** 비용은 어트리뷰션 링크와 Cost API 모두에서 집계됩니다. 비용 API가 우선하므로 어트리뷰션 링크의 비용은 무시됩니다.

</Accordion>

<div id="closed-beta--cost-split" />

<Accordion title="비용 분담">

관련 앱 ID 없이 캠페인 비용 데이터만 보고하는 광고 네트워크들이 존재합니다. 이 같은 케이스가 발생할 경우, 앱스플라이어는 자체 트래킹된 인게이지먼트 데이터와 어트리뷰션 데이터를 기반으로 해당 앱 ID 정보를 역추적하여 매핑합니다.

앱스플라이어는 보고된 비용 날짜를 기준으로 **±10일 기간 내**에 발생한 캠페인의 클릭, 노출, 전환과 연관된 앱을 기반으로 앱을 매칭합니다.

앱 정보 보완 프로세스를 통해 여러 개의 앱이 매칭되는 경우, 앱스플라이어는 다음과 같은 방식으로 해당 앱들에 캠페인 비용을 배분합니다.

<div id="proportional-split-by-conversions" />

#### 비례 분할 (전환 수 기준)

보고된 비용 날짜에 전환(설치, 재어트리뷰션 및 재인게이지먼트)이 존재하는 경우, 비용은 각 앱의 전환 수에 따라 비례하여 분할됩니다.

**예:** 예를 들어 1일 차의 총비용이 **$100** 이고, 해당 캠페인을 통해 **iOS에서 60건의 설치**, **Android에서 40건의 설치**가 발생했다면 다음과 같이 적용됩니다.

* iOS: **$60**
* Android: **$40**

<div id="equal-split-no-conversions" />

#### 동등 분할 (전환 없음)

보고된 비용 날짜에 전환 데이터가 존재하지 않는 경우, 비용은 매칭된 앱들에 동일하게 균등 분할됩니다.

**예시:** 1일 차의 총비용이 **$100** 이고, 해당 날짜에 캠페인의 노출은 발생했으나 전환은 없는 경우 다음과 같이 적용됩니다.

* iOS: **$50**
* Android: **$50**

<div id="note-2" />

> 📘 **참고**
>
> 비례 (전환 기반) 분할은 어트리뷰션에서 사용할 수 있는 전환 세분성이 애드 네트워크가 비용 데이터에 대해 보고하는 세분성과 정확히 일치하는 경우에만 적용됩니다. 이 둘이 부분적으로만 일치하면 앱스플라이어는 비용을 각 앱의 전환에 매핑할 수 없으므로 일치하는 앱 전체에 균등 분할을 적용합니다.

<div id="limitations" />

#### 제한 사항

* 이 기능은 구글, 틱톡, DV360 크로스 플랫폼 및 웹투앱 (W2A) 캠페인 (모바일/앱과 캠페인 목표가 다른 캠페인) 에서 지원됩니다.
* **구글 퍼포먼스 맥스 (PMAX) 캠페인**: 비례 (전환 기반) 분할은 적용되지 않습니다. Google API는 PMAX 캠페인의 광고 ID 또는 지역 세분성을 보고하지 않으므로 전환 세분성이 부분적으로만 일치하며 비용을 각 앱의 설치, 리어트리뷰션, 리인게이지먼트에 매핑할 수 없습니다. 결과적으로 비용은 앱당 전환 수에 관계없이 일치하는 앱 간에 균등하게 분배됩니다. 캠페인 수준에서 대시보드에서 모든 플랫폼 (iOS, 안드로이드 등) 을 선택해도 총 비용은 여전히 구글이 보고한 비용과 일치합니다.

</Accordion>

<div id="additional-information" />

## 추가 정보

<div id="ad-networks-supporting-cost-api" />

<Accordion title="비용 API를 지원하는 미디어소스 목록">

다운로드 가능한 아래 표는 비용 API(Cost API)를 지원하는 모든 미디어 소스와 각 소스별로 제공되는 데이터 세분성을 나타냅니다.

* 디멘션
* 지원되는 기능 및 특징
* 지표 (미디어 소스에 의해 보고된 기준)

파일 다운로드: [CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=csv), <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=xlsx">XLS</Anchor>

</Accordion>

<div id="changing-campaign-names" />

<Accordion title="캠페인 이름을 변경하는 경우">

앱스플라이어는 캠페인 ID를 키로 사용하여 캠페인을 표시합니다.

디스플레이 이상을 방지하려면 다음을 확인하십시오.

* 각 캠페인에는 고유한 캠페인 ID가 할당되어 있습니다.
* 다른 캠페인 ID에 동일한 캠페인 이름을 사용하지 않습니다.

<Anchor target="_blank" href="/marketers/ko/docs/campaign-name-changes">캠페인 이름 변경에 대해 자세히 알아보기</Anchor>

</Accordion>

<div id="costs-without-installs" />

<Accordion title="설치 없이 비용만 있는 경우">

**설치가 없는데도 비용 데이터가 표시되는 이유는 무엇인가요?** 이는 비용이 계층 구조의 상위 수준 (예: 캠페인 수준) 에 제공되지만 성과 정보 (클릭 및 설치) 는 광고 계층 구조의 하위 수준 (예: 광고 광고) 에 제공되는 경우에 발생합니다.

앱스플라이어는 상위 계층 구조에서 누락된 차원에 대한 비용 데이터를 완성합니다. 이를 통해 모든 수준에서 비용 데이터를 전체적으로 볼 수 있으며, 내부 불일치가 최소화됩니다.

<div id="example-2" />

> 📄 **예시**
>
> 광고주가 캠페인을 운영합니다. 캠페인 체계는 아래와 같습니다.
>
> * **미디어 소스**: media\_eg
> * **캠페인**: campaign\_eg
> * **광고 세트**: **adset1**, adset2.
>
> 미디어소스와 관련된 다음 정보가 표시됩니다.
>
> 계층 구조: 모든 미디어 소스 > media\_eg
>
>
>
> | 캠페인 | 비용 | 설치 |
> | --- | --- | --- |
> | campaign\_eg | $100 | 100 |
> | campaign\_yy | $200 | 1000 |
> | campaign\_zz | $300 | 2000 |
>
>
>
> campaign\_eg 하위로 드릴다운하면, 광고 세트 단위가 표시됩니다.
>
> 계층 구조: 모든 미디어 소스 > 미디어\_eg > 캠페인\_eg
>
>
>
> | 광고세트 | 비용 | 설치 |
> | --- | --- | --- |
> | 없음 | $100 |  |
> | adset\_1 | 해당 없음 | 30 |
> | adset\_2 | 해당 없음 | 70 |
>
>
>
> 이러한 경우, campaign\_eg 캠페인의 비용은 $100이며 캠페인 수준에서 제공됩니다. 캠페인 구성 요소인 광고 세트 단위로 드릴다운 했을 때, 비용은 광고 세트 단위로 나뉘어 구분될 수 없습니다.
>
> 이를 극복하기 위해, 앱스플라이어는 캠페인 단위의 비용을 그대로 가져 내려가서 별도의 행에 표시합니다. 위의 예시의 경우, 해당 광고 세트가 없음으로 표시되고 인스톨 필드가 비어 있습니다.

</Accordion>

<div id="cost-currency-conversion" />

<Accordion title="비용 통화 변환">

미디어 소스에서 제공하는 캠페인 비용 통화가 플랫폼에 설정된 앱 정의 통화와 다른 경우, 다음과 같이 앱 정의 통화로 환전되어 반영됩니다.

* 앱스플라이어는 <Anchor target="_blank" href="https://openexchangerates.org/">openexchangerates.org</Anchor>에서 환율 정보를 얻습니다.
* 환율은 최대 7일 전까지의 데이터에 대해 매시간 업데이트됩니다.
* 통화 변환은 마지막으로 알려진 환율을 사용하여 이루어집니다.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특성 및 한계">

| 특징 | 설명 |
| --- | --- |
| 에이전시 | <ul><li>에이전시는 ROI360을 사용하는 광고주의 ROI360 비용 데이터에 대한 권한을 가질 수 있습니다.</li><li>투명한 대행사가 캠페인을 실행한다면 광고주는 대시보드와 보고서에 표시된 비용을 확인할 수 있어 통합된 시각을 제공합니다. [더 알아보기](/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports)</li><li>광고주가 대행사와의 관계를 종료하고 대행사가 앱에 대해 비용 설정을 해둔 경우, 광고주가 앱 수준에서 대행사 권한을 비활성화하더라도 비용 데이터는 계속해서 가져옵니다. 이러한 상황을 방지하기 위해, 광고주는 대행사 권한을 비활성화하기 전에 먼저 대행사 측에 앱스플라이어 내 비용 연동 설정을 비활성화해 달라고 요청해야 합니다.</li><li>일부 미디어 소스의 경우, 대행사는 연동을 활성화하기 위해 광고주에게 연락해야 하며, 앱스플라이어 UI에서 이를 수행하라는 안내가 표시됩니다. 이러한 네트워크의 경우, 대행사와 광고주는 미디어 소스가 데이터를 보낼 때 대행사 비용 어트리뷰션(기여)에 필요한 `af_prt`파라미터가 포함되어 있는지 확인해야 합니다.</li><li>X 광고의 경우 SKAN 전용 캠페인(SKAN 설치만 있고 '일반' 설치가 없는 캠페인)에 대한 비용 데이터는 대행사에서 사용할 수 없습니다. 비용 설정은 광고주가 해야 합니다. 그리고 데이터는 광고주만 볼 수 있습니다.</li></ul> |
| API 데이터 최신성 | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">당일 내</Anchor> (Moloco 제외)</li><li>Mintegral 데이터는 전날이 종료된 후 약 4시간 뒤인 익일까지 API를 통해 제공됩니다. 즉, 이벤트가 1일째에 발생한 경우 비용 데이터는 2일째 약 4시에 사용할 수 있습니다.</li></ul> |
| 캠페인 이름 변경 | 광고 지출 데이터는 가장 최근에 보고된 캠페인 이름으로 표시됩니다. **참고**: 이는 로데이터 자체가 아닌 집계 데이터를 표시하기 위한 것입니다. |
| 시간대 | 미디어 소스가 단 하나의 표준시(타임존)만 지원하고, 해당 미디어 소스가 지원하는 표준시와 앱 설정에 지정된 표준시 간에 차이가 있는 경우, 미디어 소스가 지원하는 표준시를 기준으로 데이터가 처리됩니다. |
| CTV, PC 및 콘솔 플랫폼 | 이러한 플랫폼에 있는 앱의 경우 비용 데이터는 이메일로 파일 업로드 방법을 사용하여 <Anchor target="_blank" href="/marketers/ko/docs/import-cost-data">광고 지출 처리를</Anchor> 통해 전송해야 합니다. |
| 크로스 플랫폼 | 크로스 플랫폼 클릭과 노출에 대한 비용 데이터는 제공되지 않습니다. 즉, 노출/클릭은 한 플랫폼에서 발생하고 앱 설치는 다른 플랫폼에서 발생할 수 있습니다. |
| 스토어 외 앱 | Mintegral의 비용 데이터는 스토어 외부 앱(구글 플레이 및 앱스토어가 아닌 플랫폼의 앱)에는 사용할 수 없습니다. |
| 지역 | Mistplay 번들 캠페인(여러 국가를 대상으로 하는 캠페인)에는 지역\/국가별 분류가 제공되지 않습니다. 이러한 캠페인의 경우, 지역이 N\/A로 표시됩니다. |
| Smadex | 대시보드와 비용 ETL 보고서는 비용 및 어트리뷰션 데이터를 별도로 표시할 수 있습니다. 이는 Smadex가 사이트 ID 값에 추가 요소 (예: 인벤토리 ID) 를 포함할 때 발생합니다. |
| apple\_search\_ads.png | SKAN 전용 리포팅의 경우, Apple이 SKAN 포스트백에 캠페인 수준 데이터를 포함하지 않기 때문에 ASA(애플 서치 애즈) 비용 데이터는 SKAN 대시보드나 Pull API에서 제공되지 않습니다. 그러나 비용 데이터는 기존 연동(Classic integration)을 통해 SSOT 리포트에서 확인할 수 있습니다. |
| 비용 데이터 디멘션 문자 제한 | 아래 나열된 네트워크의 경우 다음 차원이 지정된 문자 길이를 초과해서는 안 됩니다. 이 글자 수 제한을 준수하지 않을 경우, 해당 디멘션 값은 리포트에서 제외됩니다.<ul><li>`app_id` &lt;=100</li><li>`publisher` &lt;=250</li><li>`partner` &lt;=250</li><li>`campaign` &lt;=250</li><li>`campaign_id` &lt;=250</li><li>`adset` &lt;=250</li><li>`adset_id` &lt;=250</li><li>`ad` &lt;=250</li><li>`ad_id` &lt;=250</li><li>`site_id` &lt;=250</li><li>`site_name` &lt;=250</li><li>`channel` &lt;=250</li><li>`ad_account` &lt;=250</li><li>`ad_account_name` &lt;=250</li></ul>제한 사항은 다음 네트워크에만 적용됩니다.<ul><li>mintegral\_int,</li><li>moloco\_int,</li><li>applovin\_int</li><li>liftoff\_int,</li><li>aura\_int,</li><li>tiktokglobal\_int,</li><li>pinterest\_int,</li><li>vungle\_int,</li><li>iossearchads\_int</li></ul> |
| API 비용 데이터 가용성 | API 비용 데이터는 활성 ROI360 자산을 보유한 고객에게만 표시됩니다. ROI360이 비활성화된 경우 API 소스의 비용 데이터는 더 이상 사용할 수 없으며, CPI 기반의 비용 데이터만 대시보드에 표시됩니다. |
| Mintegral: 광고 단위 세분화 | Mintegral에서 광고 단위 수준의 세밀한 비용 리포팅을 확인하려면, 광고 계정당 다음 애드 네트워크 권한이 필요합니다. **서브/패키지 × 크리에이티브 차원**. |

</Accordion>

> 📄 **참고 항목**
>
> * Xpend—비용 데이터 집약 솔루션
> * <Anchor target="_blank" href="/marketers/ko/docs/view-aggregated-cost-data-for-attribution-links">어트리뷰션 링크의 비용</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support">데이터 최신성 및 시간대 지원</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/campaign-name-changes">캠페인 이름 변경</Anchor>

<div data-zendesk-anchors="cost-aggregation=%EB%B9%84%EC%9A%A9-%EC%A7%91%EC%95%BD h_01HC7K2Y627P56F5JH9QT47GB2=%EB%B9%84%EC%9A%A9-%EC%A7%91%EC%95%BD principles-of-cost-data-aggregation=%EB%B9%84%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A7%91%EA%B3%84-%EC%9B%90%EB%A6%AC h_01HC7K2Y62ZC932EDX00YP7DAW=%EB%B9%84%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A7%91%EA%B3%84-%EC%9B%90%EB%A6%AC h_01HC7K2Y62K78M02ZN034N99T0=cost-aggregation-methods h_01HC7K2Y62YPM3A6Z0HBY58J00=cost-data-availability-and-reports cost-in-the-ua-view=ua-%EB%B7%B0%EC%97%90%EC%84%9C-%EB%B9%84%EC%9A%A9 h_01KGS7NM964HW175AW2CF59P5K=ua-%EB%B7%B0%EC%97%90%EC%84%9C-%EB%B9%84%EC%9A%A9 cost-in-unified-view=%ED%86%B5%ED%95%A9-%EB%B3%B4%EA%B8%B0%EC%9D%98-%EB%B9%84%EC%9A%A9 h_01KGS7QG5GNKG1YVACWQKCQFZ4=%ED%86%B5%ED%95%A9-%EB%B3%B4%EA%B8%B0%EC%9D%98-%EB%B9%84%EC%9A%A9 example=%EC%98%88%EC%8B%9C h_01KGS7R5SJ3NSVJAHG3BM922VS=%EC%98%88%EC%8B%9C cost-data-availability-and-reports::865c5bcd=%EB%B9%84%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EC%A1%B0%ED%9A%8C%ED%95%A0-%EC%88%98-%EC%9E%88%EB%8A%94-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EB%B0%8F-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HC7K2Y62ZY6HWG5TJDEPHZKH=%EB%B9%84%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EC%A1%B0%ED%9A%8C%ED%95%A0-%EC%88%98-%EC%9E%88%EB%8A%94-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EB%B0%8F-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HC7K2Y62112X308A0Y7DDDRM=cost-prioritization-mechanism h_01HC7K2Y62SZKXD4W0EJGYF6RS=%EC%98%88%EC%8B%9C-1 %5Bclosed-beta%5D-cost-split=closed-beta--cost-split h_01KHR3PQTNF5XP7J4HZEYVRK95=closed-beta--cost-split proportional-split-by-conversions=%EB%B9%84%EB%A1%80-%EB%B6%84%ED%95%A0-%EC%A0%84%ED%99%98-%EC%88%98-%EA%B8%B0%EC%A4%80 h_01KHR3PQTNMDX8AGM1C73N7SMK=%EB%B9%84%EB%A1%80-%EB%B6%84%ED%95%A0-%EC%A0%84%ED%99%98-%EC%88%98-%EA%B8%B0%EC%A4%80 equal-split-no-conversions=%EB%8F%99%EB%93%B1-%EB%B6%84%ED%95%A0-%EC%A0%84%ED%99%98-%EC%97%86%EC%9D%8C h_01KHR3PQTPG8GTHV64MFCM628H=%EB%8F%99%EB%93%B1-%EB%B6%84%ED%95%A0-%EC%A0%84%ED%99%98-%EC%97%86%EC%9D%8C h_01KZ8TMT06KNYFZ7VBX1GY07JB=%EC%B0%B8%EA%B3%A0 limitations=%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01KHR3PQTPPJYKXRYKNHM4W95A=%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD list-of-ad-networks=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HC7K2Y63T9GK0WW95YM39B5C=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HC7K2Y63MG10M4Z66VHY5WYW=ad-networks-supporting-cost-api h_01HE0T3TGPZFB2ZBHFGGWXY6AP=changing-campaign-names h_01HE0T3TGQGK6135KM7AYJ7S1G=costs-without-installs h_01HE0T3TGQMK285N8RV48KG8N9=%EC%98%88%EC%8B%9C-2 h_01HE0T3TGQ7MSSB09GFNPYFKR1=cost-currency-conversion h_01HJ10FMTJKH48CEXM0G40Y9J1=traits-and-limitations h_01KZB8X752XR3PB8ZACZE4QWTC=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
