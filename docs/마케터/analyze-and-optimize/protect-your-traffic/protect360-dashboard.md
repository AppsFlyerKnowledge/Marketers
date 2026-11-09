---
title: Protect360 대시보드
metadata:
  keywords:
    - dashboard
    - Advertisers
    - Protect360
    - protect 360
    - '360'
    - P360
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-08-11T09:58:07Z'
  edited_at: '2026-10-14T10:38:50Z'
  id: 360011793077
  locale: ko
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ko/articles/360011793077
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** Protect360 대시보드는 유효성 검증 규칙 적용으로 인해 차단된 사기 트래픽과 인스톨에 대한 통찰력을 제공합니다.

<div id="about-protect360-dashboard" />

## Protect360 대시보드 소개

Protect360 대시보드:

* 계정 수준에서 집약된 사기 데이터를 표시합니다.
* 다음 두 대시보드 뷰가 있습니다.
  * 인스톨(CPI)
  * 인앱 이벤트(CPA)
* 다음을 포함하여 카테고리를 기반으로 사기를 구성합니다.
  * 사기 인스톨 대 하이재킹 인스톨
  * 실시간으로 차단된 사기 대 포스트-어트리뷰션으로 식별된 사기
  * UA의 사기 대 리타게팅 캠페인
* 필터와 그룹화 옵션을 사용하여 드릴다운하면서, 사기 이벤트를 더 깊게 검사할 수 있도록 합니다.

Protect360 대시보드를 보려면 앱스플라이어에서 **최적화 > Protect360으로 이동합니다.**

<div id="filters-and-groupings" />

<Accordion title="필터 및 조회 기준">

**필터 와 조회 기준 창**

<Image align="center" alt="p360_filters_2.png" src="https://files.readme.io/9fd2afbbfc1bdf671ae0427d75c1020085b36da724e40dcfe57da27943e15b0c-4408431325969.png" />

다음 필터와 조회 기준(grouping) 옵션이 가능합니다:

* 기본 필터:
  * 앱 이름
  * 소스 유형: 논오가닉 및/또는 오가닉
  * 미디어소스
  * 지역
  * 날짜 범위(<Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#protect360-dashboard">시간대 지원 참조</Anchor>)
  * 어트리뷰션 유형: 설치, 리어트리뷰션 및/또는 리인게이지먼트
  * [지불 가능 이벤트](/docs/protect360-dashboard#payable-events) (인앱이벤트 대시보드에서 사용 가능)
* 확장된 필터 - 날짜 선택란 오른쪽의 파란색 화살표를 클릭합니다.
  * 에이전시
  * 캠페인
  * 채널
* 조회 기준 옵션 - 필요한 특정 인사이트를 얻을 수 있도록 프로드 데이터를 다양한 디멘션으로 그룹화하도록 선택합니다.
  * **애플리케이션:** 앱별 총 사기량을 비교합니다.
  * **미디어소스**(기본값): 앱에서 사용하는 각 미디어소스에서 식별된 프로드를 비교합니다.
  * **미디어소스 + 캠페인**: 앱에서 사용하는 모든 캠페인에서 식별된 프로드를 비교합니다.
  * **미디어소스 + 사이트 ID**: 앱에서 사용하는 모든 미디어소스의 모든 퍼블리셔(사이트 ID)에서 식별된 사기를 비교합니다.
  * **미디어소스 + 사이트 ID + 캠페인**: 해당하는 캠페인 이름과 연관되고 앱에서 사용하는 모든 미디어소스의 퍼블리셔(사이트 ID) 전체에서 식별된 사기를 비교합니다.
  * **미디어소스 + 지역**: (인앱 이벤트 대시보드에서 사용 가능): 관련 국가와 관련된 앱에서 사용하는 각 미디어소스에서 식별된 프로드를 비교합니다.
  * **미디어소스 + 어트리뷰션 유형**: 선택한 어트리뷰션 유형(인스톨, 리어트리뷰션 및/또는 리인게이지먼트)과 관련된 각 미디어소스의 식별된 사기를 비교합니다.
  * **지역**: 모든 국가에서 확인된 사기를 비교합니다.

</Accordion>

<div id="installs-dashboard" />

## 대시보드 인스톨

인스톨 대시보드는 LTV 기반 데이터를 표시합니다. 이는 선택한 날짜 범위에 발생한 인스톨, 리어트리뷰션 및 리인게이지먼트와 관련된 데이터를 의미합니다.

대시보드 기능은 다음 섹션에 설명되어 있습니다.

<div id="installs-headline-metrics" />

<Accordion title="인스톨- 기본 측정 지표">

기본 측정 지표를 사용하여 다음을 볼 수 있습니다.

각 KPI에는 퍼센트 값이 있습니다. 이 값은 제시된 KPI가 이전 기간의 병렬 날짜 범위와 어떻게 비교되는지를 나타냅니다. 예를 들어, 지난주와 대비한 이번 주, 또는 이전에 온 동일한 날짜와 비교한 날짜 범위에서 선택한 임의의 날짜: 예상 절감액이 X% 증가한 것으로 나타난다면 이전의 병렬 날짜 범위에서는 사기 인스톨, 리어트리뷰션 및 리인게이지먼트가 X% 감소했음을 의미합니다.

**식별된 사기 어트리뷰션**

<Image align="center" alt="" src="https://files.readme.io/262403803bd074e4742f63d7998d4642e3b17781e178ed3bc24b35dd958ca262-4408437121297.png" width="100%" />

식별된 총 사기 지표는 다음 양을 표시합니다.

* 다양한 사기 차단 이유로 하여 실시간으로 차단된 사기성 인스톨, 리어트리뷰션, 및 리인게이지먼트.
* 사기성 포스트-어트리뷰션으로 식별된 인스톨, 리어트리뷰션 및 리인게이지먼트.

**차단된 인앱 이벤트**

<Image align="center" alt="" src="https://files.readme.io/ed6692be83cae6a6bee556e5c763d6313c0d32cb577a9587caac41c54b51b378-4403139249809.png" width="100%" />

차단된 인앱이벤트 지표는 앱스플라이어가 차단한 인앱이벤트 수를 표시합니다. 이 이벤트는 차단된 인스톨에 포함되거나 의심스러운 포스트 어트리뷰션 이벤트로 간주되어 차단되었을 수 있습니다.

<Image align="center" alt="" src="https://files.readme.io/49e705c39b88c243af92c88e33d1939d1ec54b6a83e94724bdef702c9442a6a6-32184720638097.png" width="100%" />

</Accordion>

<div id="installs-charts" />

<Accordion title="인스톨—차트">

<div id="identified-fraud-trend-chart" />

#### 식별된 사기 경향 차트

식별된 사기 경향 차트는 하루 동안의 사기성 인스톨, 리어트리뷰션 및 리인게이지먼트 횟수를 다음 중 하나로 구분하여 표시합니다.

* **탐지 유형**: 실시간으로 차단된 인스톨 및 사기성 포스트-어트리뷰션으로 식별된 인스톨.
* **어트리뷰션 유형**: 설치, 리어트리뷰션 및 리인게이지먼트
* **소스 유형**: 논오가닉 및 오가닉

화면표시는 선 그래프 또는 막대 차트일 수 있습니다.

<div id="hijacked-installs-attribution-correction-chart" />

#### 하이재킹 인스톨 어트리뷰션 수정 차트

하이재킹 인스톨 어트리뷰션 수정 차트에는 인스톨, 리어트리뷰션 및 리인게이지먼트로 명성을 얻으려는 미디어소스와 마지막으로 유효한 기여자 소스가 표시됩니다.

다음을 수행할 수 있습니다.

* 실시간으로 식별된 하이재킹 어트리뷰션, 포스트-어트리뷰션 또는 유효성 검증 규칙을 통해 식별된 어트리뷰션을 기준으로 필터링합니다.
* 유효한 소스 어트리뷰션이 수정되거나 하이재킹된 소스 어트리뷰션이 수정되는 대상을 설정합니다.
* 차트 보기를 테이블 형식으로 변경하고 데이터를 CSV로 다운로드합니다.

**참고:**

* 이 차트는 광고주만 액세스할 수 있습니다. 에이전시 및 광고 네트워크는 액세스할 수 없습니다.
* 하이재킹이 실시간으로 차단되면 올바른 어트리뷰션이 앱스플라이어 대시보드 및 리포트에 표시됩니다(Protect360뿐만 아니라). 하이재킹이 포스트 어트리뷰션으로 확인되면 Protect360 로데이터에만 올바른 어트리뷰션이 표시됩니다.
* 이 차트는 오가닉에 **대한** 보정은 표시할 수 있지만 오가닉**에서** 얻은 것은 아닙니다.

<div id="affiliate-attribution-model" />

<div id="identified-fraud-chart" />

#### 식별된 사기 차트

식별된 사기 차트는 경험하는 사기 유형을 백분율별로 표시합니다. 사기 구분을 다음과 같이 구분합니다.

* 차단 사유
* <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports#인스톨-수준-가짜-인스톨-차단-하위-이유">Blocked Sub Reason</Anchor>

* 미디어 소스
* 캠페인
* 지역
* 앱

</Accordion>

<div id="installs-table" />

<Accordion title="인스톨—표">

<div id="identified-fraud-breakdown" />

#### 프로드 상세

**식별된 사기 분류** 표는 다음 데이터를 표시합니다.

* 실시간 차단된 프로드
* 포스트 어트리뷰션에 식별되고 표시된 프로드
* 미디어소스 별 프로드의 기타 징후

표는 다음 이미지에 보여지듯이 일반 개요 형식으로 표시됩니다.

<Image align="center" alt="p360_main_table.png" src="https://files.readme.io/15885268068f2b57e9b22b7028a824951690e737a47cb154cd38d1ddf79937b8-4408431449745.png" />

동적 표 구조:

* 사용자는 표 설정 버튼을 클릭하여 표에 열을 추가하거나 제거할 수 있습니다.  
  표를 변경하는 경우, 작업 후 **저장** 버튼을 클릭하십시오.
* 사용자별로 설정되므로 Protect360 액세스를 가진 모든 계정 사용자는 스스로의 표 구조를 개인적으로 맞춤 설정할 수 있습니다. [추가 표 옵션](/docs/protect360-dashboard#추가적인-표-옵션)을 참조하십시오.

<Image align="center" alt="edit_table.jpg" src="https://files.readme.io/fcde2bc6970c29902dd7585ee92c2bc38edf1d5c56e65de4e3f10df784108e5c-360011641617.jpg" />

<div id="content-of-the-identified-fraud-breakdown-table" />

#### 식별된 프로드 쪼개보기 표 내용

| 표 열 | 설명 |
| --- | --- |
| 그룹화 | <ul><li>[기본 설정] 표 및 대시보드는 미디어소스별로 그룹화되어 조회됩니다.</li><li>특정 미디어소스를 선택했을 때, 조회 기준(grouping)은 미디어소스와 사이트 ID 모두로 자동 적용됩니다.</li><li>선택적 그룹에는 캠페인, GEO, 채널, 대행사, 대행사 + 미디어소스 및 이들의 조합이 포함됩니다.</li><li>논오가닉 트래픽에만 적용되는 기준으로 그룹을 선택하면 테이블에 오가닉 미디어소스에 대해 해당 없음이 표시됩니다.</li></ul> |
| **어트리뷰션** | **차단된 인스톨 및 포스트 어트리뷰션 프로드 인스톨에 대한 상위 단계 분류** |
| Total (A) | <ul><li>전체 인스톨 수 = 일반 (비사기) 인스톨 + 차단된 인스톨</li><li>일반 인스톨은 개요 대시보드에서 미디어소스 (논오가닉)별로 가능합니다.</li></ul> |
| Blocked (B) | <ul><li>차단된 인스톨의 전체 수</li><li>[기본 설정] 이 KPI에 따라 내림차순으로 표를 정렬합니다.</li></ul> |
| Blocked % (B/A) | 차단된 인스톨 수 / 전체 인스톨 수 |
| Post-attribution (C) | 사기 포스트 어트리뷰션으로 식별된 인스톨. |
| Post-attribution % (C/A) | 포스트 어트리뷰션 인스톨 수 / 총 인스톨 수 |
| Total fraudulent installs (D) | 실시간으로 차단됐거나 포스트 어트리뷰션 프로드로 식별된 모든 프로드 인스톨 수 |
| Fraudulent installs % (D/A) | 프로드 인스톨 수 / 전체 인스톨 수 |
| **사기 어트리뷰션 유형 분류** | **사기성 인스톨의 어트리뷰션 유형은 인스톨, 리어트리뷰션 및 리인게이지먼트로 구분됩니다.** |
| 인스톨 | UA 캠페인으로부터 유입된 사기. |
| 리어트리뷰션 | 인스톨로 이어진 리타게팅 캠페인으로부터 유입된 사기. |
| 리인게이지먼트 | 리인게이지먼트로 이어진 리타게팅 캠페인으로부터 유입된 사기. |
| **허위** | **실제 사용자 활동을 따라한 사기성 인스톨 또는 리어트리뷰션 - 실시간 차단과 포스트 어트리뷰션으로 구분.** |
| 실시간 차단 | 실시간 차단된 허위 인스톨 수 |
| 포스트 어트리뷰션 프로드 | 포스트 어트리뷰션 프로드로 식별된 허위 인스톨 수 |
| **하이재킹** | **실제 유저 인스톨의 어트리뷰션을 가로채려는 프로드 라스트 클릭 - 실시간 차단과 포스트 어트리뷰션으로 구분** |
| 실시간 차단 | 실시간 차단된 인스톨 하이재킹 수 |
| 포스트 어트리뷰션 프로드 | 포스트 어트리뷰션 프로드로 식별된 인스톨 하이재킹 수 |
| **유효성 검증 규칙** | **유효성 검증 규칙 조건을 충족하는 인스톨.** |
| 차단된 인스톨 | 유효성 검증 규칙에 의해 차단된 인스톨. |
| 차단된 어트리뷰션 | 유효성 검증 규칙에 의한 인스톨의 어트리뷰션 변경. |
| **허위 인스톨 차단 상세** | **주로 프로그램적으로 수행된, 실시간으로 차단됐거나 포스트 어트리뷰션 프로드로 식별된 허위 인스톨 쪼개보기** |
| 차단된 사이트 ID 거부 리스트 | 인스톨은 Protect360이 사이트 ID를 거부 리스트에 올림으로써 차단됩니다. |
| 포스트 어트리뷰션 사이트 ID 거부 리스트 | 인스톨은 Protect360이 사이트 ID를 포스트 어트리뷰션으로 거부 리스트에 올림으로써 사기로 표시됩니다. |
| 차단된 봇 | 자동화된 봇에 의해 시도되어 차단된 인스톨 수 |
| 포스트 어트리뷰션 봇 | 자동화된 봇 활동이 포스트 어트리뷰션으로 식별되어 프로드로 표시된 인스톨 수 |
| 차단된 행동 이상 현상 | 비정상적인 세션 및 사용자 인앱 이벤트 성과와 같은 행동 이상 현상으로 인해 차단된 인스톨 수 |
| 포스트 어트리뷰션 이상 행동(behavioral anomalies) | 포스트 어트리뷰션 행동 이상 현상으로 인해 프로드로 표시된 인스톨 수 |
| 차단된 인스톨 유효성 검증 | 스토어 유효성 검증 실패로 인해 차단된 총 인스톨 수 |
| **하이재킹 인스톨 차단 상세** | **실제 유저 인스톨의 어트리뷰션을 가로채려는 프로드 라스트 클릭 쪼개보기** |
| 차단된 인스톨 하이재킹 | 소스의 차단된 인스톨 하이재킹 수 |
| 포스트 어트리뷰션 인스톨 하이재킹 | 포스트 어트리뷰션으로 프로드 표시된 인스톨 하이재킹 수 |
| 차단된 CTIT 이상 현상 | CTIT 이상 형상으로 인해 차단된 인스톨 수 |
| 포스트 어트리뷰션 CTIT 이상현상 | 포스트 어트리뷰션으로 프로드 표시된 CTIT 이상 현상 수 |
| 차단된 클릭 플러딩 | 클릭 플러딩으로 인해 차단된 인스톨 수 (임의의 인스톨 전에 라스트 클릭을 전달하려는 희망으로, 다량의 클릭을 보내는 프로드 시도) |
| 포스트 어트리뷰션 클릭 플러딩 | 포스트 어트리뷰션으로 프로드 표시된 클릭 플러딩 인스톨 수 |
| **클릭 수** | **소스에서 발생한 클릭**<br /><br />**참고:** 클릭 데이터가 표에 표시되려면 필터 표시줄에서 모든 어트리뷰션 유형을 선택해야 합니다(그렇지 않으면 N/A로 표시됨). 그에 따라 필터 선택을 조정해야 합니다. |
| Total (E) | 소스에서 발생한 합법적 클릭 및 사기 클릭 총수 |
| 차단 수 |  |
| **노출** | **소스에서 발생한 노출**<br /><br />**참고:** 노출 데이터가 표에 표시되려면 필터 표시줄에서 모든 기여 분석 유형을 선택해야 합니다(그렇지 않으면 N/A로 표시됨). 그에 따라 필터 선택을 조정해야 합니다. |
| 합계 | 소스에서 발생한 합법적 노출 및 사기 노출 총수 |
| 차단 수 |  |
| **인앱 이벤트** | **소스에서 발생한 인앱 이벤트**<br /><br />**참고:** 여기에는 리어트리뷰션 또는 리인게이지먼트가 아닌 인스톨로 인한 인앱 이벤트가 포함됩니다. |
| Total (G) | 전체 인앱 이벤트 수 |
| Blocked (H) | 차단된 인앱이벤트 |
| % (H/G) | 차단된 인앱 이벤트 수 / 전체 이벤트 수 |
| **디바이스 팜 표시기** | **기기 ID 재설정 및 LAT(광고 추적 제한) 사기를 사용한 사기성 디바이스 팜 활동의 표시기.**<br /><br />**참고:** 여기에는 리인게이지먼트가 아닌 인스톨 및 리어트리뷰션이 포함됩니다. |
| Installs (I) | 앱스플라이어에 알려지지 않은 뉴 디바이스 ID를 가진 인스톨. |
| Installs % (I/A) | 뉴 디바이스 인스톨 수 / 전체 인스톨 수 |
| 충성 유저 % | 유저가 실제인지 허위인지 표시하는 일반적인 KPI |
| **클릭 플러딩 지표** | **비정상적인 변환 또는 지원 속도 또는 CTIT 시간에 기반한 클릭 플러딩 사기의 표시기.** |
| Conversion rate (%) | 일반적인 앱 전환율에 비해 전환율이 낮은 경우 클릭 도배 사기로 표시됩니다.<br /><br />**참고**: 전환율 데이터가 표에 표시되려면 필터 표시줄에서 모든 어트리뷰션 유형을 선택해야 합니다(그렇지 않으면 N/A로 표시됨). 그에 따라 필터 선택을 조정해야 합니다. |
| 어시스트 % | (개요 페이지의 어시스트 위젯에서) 보여진 타 미디어소스에 비해 어시스트 비율이 높은 경우, 클릭 플러딩 프로드임을 표시. |
| CTIT > 60분 이상 | 설치, 리어트리뷰션, 리인게이지먼트(클릭과 첫 앱 실행 사이의 시간이 60분 이상인 경우). 계산에는 CTIT가 25시간 미만인 설치만 포함됩니다(모든 설치가 아님). 일반적으로 첫 번째 앱 실행의 약 30%는 다운로드 후 60분 이상 발생합니다. |
| CTIT > 5시간 이상 | 설치, 리어트리뷰션, 리인게이지먼트(클릭과 첫 앱 실행 사이의 시간이 5시간 이상인 경우). 계산에는 CTIT가 25시간 미만인 설치만 포함됩니다(모든 설치가 아님). 일반적으로 첫 번째 앱 실행의 약 20%는 다운로드 후 5시간 이상 발생합니다. |

<div id="additional-table-options" />

#### 추가적인 표 옵션

* CSV 형식으로 테이블을 데스크톱에 다운로드하려면 **CSV 내보내기**를 클릭하십시오.
* 다음을 위해 톱니 아이콘을 클릭합니다.
  * 표의 열 순서 변경
  * 위에서 설명한 열의 추가 또는 삭제
  * 앱에서 **최근 차단된 인앱이벤트**를 표에 추가 또는 삭제합니다. 추가된 각 인앱이벤트마다 다음의 열이 표시됩니다.

| 표 열 | 설명 |
| --- | --- |
| 이벤트 카운터 (합계) | 특정 이벤트가 차단된 수 |
| 유니크 유저(Unique Users) | 특정 이벤트가 차단된 유니크 유저 수 |

이들 KPI가 일반적이지 않은 비율이라고 해서 반드시 프로드를 나타내는 것은 아닙니다. 많은 이벤트가 사기성 포스트 어트리뷰션 인스톨로 인해 차단되기 때문입니다.

CPI 대시보드의 인앱 이벤트 데이터는 LTV 기반입니다. 즉 지정된 날짜 범위에 발생한 인스톨과 관련된 모든 인앱 이벤트입니다.

</Accordion>

<div id="in-app-events-dashboard" />

## 인앱 이벤트 대시보드

인앱 이벤트 대시보드는 날짜 범위 이전에 발생한 인스톨 이벤트를 포함하여 선택한 날짜 범위에 발생한 인앱 이벤트와 관련된 데이터인 활동 기반 데이터를 표시합니다.

대시보드 기능은 다음 섹션에 설명되어 있습니다.

<div id="inapp-events-headline-metrics" />

<Accordion title="인앱이벤트—기본 측정 지표">

<Image align="center" alt="" src="https://files.readme.io/ea33b3ddafc4265eb74b2e1070a77a6afbad429a1aeb20cd1579127f7e8ee605-360012501757.jpg" />

기본 측정 지표를 사용하여 다음을 볼 수 있습니다.

* 예상 절약액 (Estimated Savings)
  * [**지불 가능 이벤트**](/docs/protect360-dashboard#payable-events)가 활성화된 경우에만 사용 가능합니다.
  * 사용자가 구성한 지불 가능 이벤트에 기반합니다.
* 식별된 사기성 IAE 총수

</Accordion>

<div id="inapp-events-charts" />

<Accordion title="인앱이벤트—차트">

<div id="fraud-trend-over-time-chart" />

#### **시간 경과에 따른 프로드 경향 차트**

시간에 따른 사기 경향 차트는 일별 이벤트 수를 표시하며 다음과 같이 구분됩니다.

* **실시간**: 사기성 인앱 이벤트를 실시간으로 차단
* **포스트 어트리뷰션**: 포스트 어트리뷰션에서 식별된 사기성 이벤트
* **비사기**

<div id="top-iae-fraud-by-media-source-chart" />

#### **미디어소스에 의한 상위 IAE 사기 차트**

미디어소스에 의한 상위 인앱이벤트 사기 목록은 다음을 포함합니다. 

* 내림차순으로 가장 많은 사기성 인앱이벤트를 가진 5개 미디어소스.
* 다음 인앱이벤트 유형을 총 인앱이벤트 중 백분율로 표시하는 각 미디어 원본 막대의 막대 차트:
  * **실시간**: 사기성 인앱 이벤트를 실시간으로 차단
  * **포스트 어트리뷰션**: 포스트 어트리뷰션에서 식별된 사기성 이벤트
  * **비사기**

</Accordion>

<div id="inapp-events-table" />

<Accordion title="인앱이벤트—표">

**인앱이벤트 사기 내역** 표는 다음 데이터를 표시합니다.

* 실시간 차단된 프로드
* 포스트 어트리뷰션에 식별되고 표시된 프로드
* 미디어소스 별 프로드의 기타 징후

표는 다음 이미지에 보여지듯이 일반 개요 형식으로 표시됩니다.

<Image align="center" alt="IAE_fraud_table.jpg" src="https://files.readme.io/dd57a2508911b3e26268ad8cc4508d5402fa091ac95a77900c7f257486c99aeb-360012839758.jpg" />

동적 표 구조:

* 사용자는 표 설정 버튼을 클릭하여 표에 열을 추가하거나 제거할 수 있습니다.  
  표를 변경하는 경우, 작업 후 **저장** 버튼을 클릭하십시오.
* 사용자별로 설정되므로 Protect360 액세스를 가진 모든 계정 사용자는 스스로의 표 구조를 개인적으로 맞춤 설정할 수 있습니다. [추가 표 옵션](/docs/protect360-dashboard#installs-table)을 참조하십시오.

<Image align="center" alt="iae_table_structure.jpg" src="https://files.readme.io/5b2933e2b254d8fa268e30a72ae53691da391e365d781d55bcdb6cfeb1f40a6a-360012839778.jpg" />

<div id="content-of-the-in-app-event-fraud-breakdown-table" />

#### 인앱이벤트 사기 내역 표 콘텐츠

| 표 열 | 설명 |
| --- | --- |
| 그룹화 | <ul><li>[기본 설정] 표 및 대시보드는 미디어소스별로 그룹화되어 조회됩니다.</li><li>특정 미디어소스를 선택했을 때, 조회 기준(grouping)은 미디어소스와 사이트 ID 모두로 자동 적용됩니다.</li><li>선택적 그룹에는 캠페인, GEO, 채널, 대행사, 대행사 + 미디어소스 및 이들의 조합이 포함됩니다.</li></ul> |
| **인앱 이벤트** | **차단된 인스톨 및 포스트 어트리뷰션 사기성 IAE에 대한 상위 단계 분류.** |
| 총 IAE(A) | <ul><li>총 IAE = 일반(비사기성) IAE + 차단된 IAE + 사기성 포스트 어트리뷰션으로 식별된 IAE.</li><li>일반 IAE는 개요 대시보드에서 미디어소스(논오가닉)별로 가능합니다.</li></ul> |
| 총 사기성 IAE(B) | <ul><li>차단된 총 IAE 수 + 사기성 포스트 어트리뷰션으로 식별된 IAE.</li><li>[기본 설정] 이 KPI에 따라 내림차순으로 표를 정렬합니다.</li></ul> |
| 사기성 이벤트 %(B/A) | 사기성 IAE / 총 IAE |
| **허위 IAE 실시간 차단** | **실시간으로 차단된 사기성 IAE.** |
| 허위 IAE | 사기로 식별되어 실시간으로 차단된 사기 IAE. |
| 가짜 설치 | 기존 인스톨은 사기로 식별되어 실시간으로 차단되었습니다. |
| 포스트 어트리뷰션 허위 인스톨 | 기존 인스톨은 IAE 전에 사기 포스트 어트리뷰션으로 식별되었습니다. |
| **실시간 하이재킹에서 저장** | **사기성 소스에 의해 하이재크된 기존 인스톨의 IAE는 앱스플라이어가 마지막 비사기성 소스에 올바르게 어트리뷰트합니다.** |
| 오가닉으로 정정 | 오가닉으로 되는 비사기성 소스를 가진 하이재크된 인스톨. |
| 논-오가닉 소스로 정정 | 논오가닉 미디어소스로 되는 마지막 사기성 소스를 가진 하이재크된 인스톨. |
| **포스트 어트리뷰션 IAE Fraud** | **사기성 포스트 어트리뷰션으로 식별된 인앱이벤트.** |
| 가짜 설치 | 인스톨 전에 발생한 IAE는 사기 포스트 어트리뷰션으로 식별되었습니다. |
| 하이재킹된 인스톨 | 인스톨 전에 발생한 IAE는 하이재크로 식별되었으며 포스트 어트리뷰션으로 올바르게 어트리뷰트되었습니다. |
| **유효성 검증 규칙** | **IAE는 유효성 검증 규칙 조건을 충족시킴으로써 차단되었습니다.** |
| 차단된 인스톨 | 유효성 검증 규칙에 의해 차단된 인스톨의 IAE. |
| 차단된 IAE | 유형성 검증 규칙에 의해 차단된 IAE. |
| 오가닉으로 정정 | 오가닉으로 되는 비사기성 소스를 가진 하이재크된 인스톨. |
| 논-오가닉 소스로 정정 | 논오가닉 미디어소스로 되는 마지막 사기성 소스를 가진 하이재크된 인스톨. |

<div id="additional-table-options-1" />

#### 추가적인 표 옵션

* CSV 형식으로 테이블을 데스크톱에 다운로드하려면 **CSV 내보내기**를 클릭하십시오.
* 다음을 위해 톱니 아이콘을 클릭합니다.
  * 표의 열 순서 변경
  * 위에서 설명한 열의 추가 또는 삭제

표시되는 이벤트 수는 액티비티 기준이며, LTV 기준이 아닙니다. 이것은, 특정 날짜 범위 동안 차단된 정확한 이벤트 수를 의미합니다.

</Accordion>

<div id="payable-events" />

<Accordion title="유료 이벤트">

지불 가능 이벤트는 비용을 가진 IAE입니다. 사용가능으로 설정되고 구성되면 인앱이벤트 활동 대시보드는 지불 가능 이벤트와 관련된 데이터만 표시합니다.

**인앱 활동 대시보드에서 지불가능 이벤트를 활성화하는 방법**:

* 인앱 활동 대시보드의 필터 항목 섹션에서 지불 가능 이벤트를 활성화합니다.  
  <Image align="center" alt="" src="https://files.readme.io/8162f6f4f6dcef50fbe0fd998b7a95d20deeb658dd53bafc216b75df050c734c-360012576718.jpg" />

**지불가능 이벤트 구성 방법**:

1. 인앱 활동 대시보드에서 **지불 가능 이벤트 구성**을 클릭합니다.

   <Image align="center" alt="" src="https://files.readme.io/00b1f4506f0c7ec8e1e1b90c16cc2232d2862b231b2673d2decc7a90b6c6b6af-360012505217.jpg" />

   지불 가능 이벤트 구성 팝업 창이 표시됩니다.

   <Image align="center" alt="" src="https://files.readme.io/4643b9d0e0042ca5860d21ec3eb3ff7e4178f92f1f4215db56adda10be41c452-360012580938.jpg" />
2. [선택 사항] 새 지불 가능 이벤트를 구성하면 **새로 추가**를 클릭합니다.
3. 대시보드에 표시하려는 지불 가능한 IAE에 따라 드롭다운 메뉴에서 다음을 선택합니다.
   * 앱
   * 인앱 이벤트
   * 미디어소스
   * 캠페인
4. IAE의 CPA를 입력합니다.
5. **저장**을 클릭하세요.
6. **닫기**를 클릭합니다.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특징 | 비고 |
| --- | --- |
| 리타겟팅 | <ul><li>인스톨(CPI) 대시보드는 인스톨, 리어트리뷰션 및 리인게이지먼트간의 어트리뷰트 터치 유형 분석을 표시할 수 있습니다.</li><li>인앱이벤트(CPA) 대시보드에 UA 인스톨로 인한 사기 이벤트가 표시되지만 리타게팅으로 인한 사기성 이벤트는 표시되지 않습니다. **참고**: 실시간으로 식별된 리어트리뷰션의 사기 이벤트는 로데이터 리포트에서 확인할 수 있습니다.</li></ul> |
| 과거 데이터 | 데이터는 Protect360 구독 시작 시부터 사용할 수 있습니다 |
| 데이터 최신성 | 일일 단위 업데이트.<ul><li>인스톨(CPI), 16:00 UTC</li><li>인앱 이벤트(CPA), 21:00 UTC</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **참조 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/protect360-anti-fraud-guide">Protect360 개요</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports">로데이터(Raw data) 보고서</Anchor>

<div data-zendesk-anchors="about-protect360-dashboard=protect360-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EC%86%8C%EA%B0%9C 01H8H9GQ17C4PBHCAMXE879BX7=protect360-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EC%86%8C%EA%B0%9C 01H8H9GQ173SQ8P29C4DETJRTD=filters-and-groupings installs-dashboard=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8 01H8H9GQ173H3QH1Y5KZ26XMCW=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8 installs%E2%80%94headline-metrics=installs-headline-metrics 01H8H9GQ17FJKWE3M2YSZFTQCS=installs-headline-metrics installs%E2%80%94charts=installs-charts 01H8H9GQ18VHMK7FFV3RY409VB=installs-charts identified-fraud-trend-chart=%EC%8B%9D%EB%B3%84%EB%90%9C-%EC%82%AC%EA%B8%B0-%EA%B2%BD%ED%96%A5-%EC%B0%A8%ED%8A%B8 01H8H9GQ18JDSZ2H8BKZVWGBPV=%EC%8B%9D%EB%B3%84%EB%90%9C-%EC%82%AC%EA%B8%B0-%EA%B2%BD%ED%96%A5-%EC%B0%A8%ED%8A%B8 hijacked-installs-attribution-correction-chart=%ED%95%98%EC%9D%B4%EC%9E%AC%ED%82%B9-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%88%98%EC%A0%95-%EC%B0%A8%ED%8A%B8 01H8H9GQ18VXBPQRN55WHM3GG0=%ED%95%98%EC%9D%B4%EC%9E%AC%ED%82%B9-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%88%98%EC%A0%95-%EC%B0%A8%ED%8A%B8 identified-fraud-chart=%EC%8B%9D%EB%B3%84%EB%90%9C-%EC%82%AC%EA%B8%B0-%EC%B0%A8%ED%8A%B8 01H8H9GQ18FW87TXQZCYERHNDE=%EC%8B%9D%EB%B3%84%EB%90%9C-%EC%82%AC%EA%B8%B0-%EC%B0%A8%ED%8A%B8 installs%E2%80%94table=installs-table 01H8H9GQ18FYXJA7TXQ4RNQGX2=installs-table identified-fraud-breakdown=%ED%94%84%EB%A1%9C%EB%93%9C-%EC%83%81%EC%84%B8 01H8H9GQ18540JJ8X833E6WF44=%ED%94%84%EB%A1%9C%EB%93%9C-%EC%83%81%EC%84%B8 content-of-the-identified-fraud-breakdown-table=%EC%8B%9D%EB%B3%84%EB%90%9C-%ED%94%84%EB%A1%9C%EB%93%9C-%EC%AA%BC%EA%B0%9C%EB%B3%B4%EA%B8%B0-%ED%91%9C-%EB%82%B4%EC%9A%A9 01H8H9GQ18DMPD7YTPTN2XJMSH=%EC%8B%9D%EB%B3%84%EB%90%9C-%ED%94%84%EB%A1%9C%EB%93%9C-%EC%AA%BC%EA%B0%9C%EB%B3%B4%EA%B8%B0-%ED%91%9C-%EB%82%B4%EC%9A%A9 additional-table-options=%EC%B6%94%EA%B0%80%EC%A0%81%EC%9D%B8-%ED%91%9C-%EC%98%B5%EC%85%98 01H8H9GQ18PZ8ABG3D51M7J91R=%EC%B6%94%EA%B0%80%EC%A0%81%EC%9D%B8-%ED%91%9C-%EC%98%B5%EC%85%98 inapp-events-dashboard=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C 01H8H9GQ19CQZV00XA62MGVJ86=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C inapp-events%E2%80%94headline-metrics=inapp-events-headline-metrics 01H8H9GQ19B95MDK2WEHVNEFS5=inapp-events-headline-metrics inapp-events%E2%80%94charts=inapp-events-charts 01H8H9GQ19XEJ0HNY2Y8BMX7A5=inapp-events-charts fraud-trend-over-time-chart=%EC%8B%9C%EA%B0%84-%EA%B2%BD%EA%B3%BC%EC%97%90-%EB%94%B0%EB%A5%B8-%ED%94%84%EB%A1%9C%EB%93%9C-%EA%B2%BD%ED%96%A5-%EC%B0%A8%ED%8A%B8 01H8H9GQ1969AB4KK4ENP8AVQJ=%EC%8B%9C%EA%B0%84-%EA%B2%BD%EA%B3%BC%EC%97%90-%EB%94%B0%EB%A5%B8-%ED%94%84%EB%A1%9C%EB%93%9C-%EA%B2%BD%ED%96%A5-%EC%B0%A8%ED%8A%B8 top-iae-fraud-by-media-source-chart=%EB%AF%B8%EB%94%94%EC%96%B4%EC%86%8C%EC%8A%A4%EC%97%90-%EC%9D%98%ED%95%9C-%EC%83%81%EC%9C%84-iae-%EC%82%AC%EA%B8%B0-%EC%B0%A8%ED%8A%B8 01H8H9GQ19Z078PK1HR7VEZHXG=%EB%AF%B8%EB%94%94%EC%96%B4%EC%86%8C%EC%8A%A4%EC%97%90-%EC%9D%98%ED%95%9C-%EC%83%81%EC%9C%84-iae-%EC%82%AC%EA%B8%B0-%EC%B0%A8%ED%8A%B8 inapp-events%E2%80%94table=inapp-events-table 01H8H9GQ19PTNWGJV6YDWR7SH6=inapp-events-table content-of-the-inapp-event-fraud-breakdown-table=%EC%9D%B8%EC%95%B1%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%82%AC%EA%B8%B0-%EB%82%B4%EC%97%AD-%ED%91%9C-%EC%BD%98%ED%85%90%EC%B8%A0 01H8H9GQ19773CS8TGS2QXBRG5=%EC%9D%B8%EC%95%B1%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%82%AC%EA%B8%B0-%EB%82%B4%EC%97%AD-%ED%91%9C-%EC%BD%98%ED%85%90%EC%B8%A0 additional-table-options::44e54bfa=%EC%B6%94%EA%B0%80%EC%A0%81%EC%9D%B8-%ED%91%9C-%EC%98%B5%EC%85%98-1 01H8H9GQ192WA6XFNW7CKGBQ03=%EC%B6%94%EA%B0%80%EC%A0%81%EC%9D%B8-%ED%91%9C-%EC%98%B5%EC%85%98-1 01H8H9GQ1AVAVQ31ZZA1K024RF=payable-events 01H8H9GQ1BJX0K01NX8VCC0690=traits-and-limitations h_01HE7S2JKX3VMRCF6913S4MCAR=%EC%B0%B8%EC%A1%B0-%ED%95%AD%EB%AA%A9" />
