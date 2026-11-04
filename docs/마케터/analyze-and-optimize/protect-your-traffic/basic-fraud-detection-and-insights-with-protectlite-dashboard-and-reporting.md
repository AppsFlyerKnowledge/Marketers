---
title: ProtectLITE 대시보드 및 리포트
metadata:
  keywords:
    - Advertisers
    - Protect360
    - Marketers
    - Protect360 / Fraud protection
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360 / Fraud protection
  created_at: '2021-01-25T09:47:02Z'
  edited_at: '2026-10-14T10:37:15Z'
  id: 360017223058
  locale: ko
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ko/articles/360017223058
---
> **한눈에 보기:** 요약: ProtectLITE는 기본 무료 보호 엔진에 의해 차단된 사기 인스톨 및 유효성 검증 규칙 적용으로 인해 차단된 인스톨에 대한 통찰력을 제공합니다.

## ProtectLITE

ProtectLITE는 인스톨 어트리뷰션 사기에 대한 기본적인 무료 보호 기능을 제공합니다. <Anchor target="_blank" href="/marketers/ko/docs/protect360-anti-fraud-guide">Protect360</Anchor>에서는 고급 사기 방지 및 탐지 기능을 사용할 수 있습니다.

앱스플라이어에서 사기를 식별하면 트래픽 데이터(앱스플라이어 대시보드 및 로데이터 리포트를 통해 사용 가능)에서 차단되지만 최종 사용자 앱 경험에는 영향을 미치지 않습니다. 이는 앱 유저가 여전히 앱을 사용할 수 있고, 광고주를 위해 매출을 생성할 수 있음을 의미합니다.

ProtectLITE 대시보드:

* 사기 인스톨, 하이재킹 인스톨 또는 <Anchor target="_blank" href="/marketers/ko/docs/implement-validation-rules-to-prevent-fraud">유효성 검증 규칙</Anchor>으로 인해 실시간으로 차단된 인스톨에 대한 모든 앱의 집계 데이터를 표시합니다.
* 필터링 및 그룹화 옵션을 사용하여 드릴다운하여 식별된 인스톨을 자세히 조사할 수 있도록 합니다.

ProtectLITE <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports">로데이터</Anchor>:

* Protect360 인스톨 리포트에서 데이터 내보내기 페이지 및 Pull API를 통해 사용할 수 있습니다.

<div id="dashboard" />

## 대시보드

**ProtectLITE 대시보드를 보려면 앱스플라이어에서** Protect360으로 이동하십시오.

대시보드 기능은 다음 섹션에 설명되어 있습니다.

<div id="filters-and-groupings" />

<Accordion title="필터 및 조회 기준">

**필터 와 조회 기준 창**

다음 필터와 조회 기준(grouping) 옵션이 가능합니다:

* 기본 필터:
  * 앱 이름
  * 소스 유형: 논오가닉 및/또는 오가닉
  * 미디어소스
  * 지역
  * 날짜 범위(<Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#protect360-dashboard">시간대 지원 참조</Anchor>)
* 확장된 필터 - 날짜 선택란 오른쪽의 파란색 화살표를 클릭합니다.
  * 대행사
  * 채널
  * 최소 코호트 크기
* 조회 기준 옵션 - 필요한 특정 인사이트를 얻을 수 있도록 프로드 데이터를 다양한 디멘션으로 그룹화하도록 선택합니다.
  * **애플리케이션:** 앱별 총 사기량을 비교합니다.
  * **미디어소스**(기본값): 앱에서 사용하는 각 미디어 소스에서 처리된 프로드를 비교합니다.
  * **미디어소스 + 캠페인**: 앱에서 사용하는 모든 캠페인에서 처리된 프로드를 비교합니다.
  * **미디어소스 + 사이트 ID**: 앱에서 사용하는 모든 미디어소스의 퍼블리셔(사이트 ID) 전체에서 처리된 프로드를 비교합니다.
  * **미디어소스 + 사이트 ID + 캠페인**: 해당하는 캠페인 이름과 연관되고 앱에서 사용하는 모든 미디어소스의 퍼블리셔(사이트 ID) 전체에서 처리된 프로드를 비교합니다.
  * **지역**: 모든 국가에서 처리된 프로드를 비교합니다.
  * **미디어소스 + 지역**(인앱 이벤트 대시보드에서 사용 가능): 관련 국가와 관련된 앱에서 사용하는 각 미디어소스에서 처리된 사기를 비교합니다.

</Accordion>

<div id="installs-headline-metrics" />

<Accordion title="인스톨- 기본 측정 지표">

기본 측정 지표를 사용하여 다음을 볼 수 있습니다.

* 예상 절약액 (Estimated Savings)
* 식별된 인스톨
* 의심스러운 전체 Fraud 위협

지표는 날짜 필터에서 선택한 기간과 관련이 있습니다.

예상 절감액 및 확인된 설치 KPI의 경우 백분율 값이 있습니다. 이 값은 제시된 KPI가 이전 기간의 병렬 날짜 범위와 어떻게 비교되는지를 나타냅니다. 예를 들어, 지난 주에 비해 이번 주 또는 이전과 같은 기간과 비교하여 날짜 범위에서 선택한 요일: 예상 절감액이 X% 증가하면 이전 병렬 날짜 범위에서 사기 인스톨 횟수가 X% 감소했음을 의미합니다.

<div id="estimated-savings" />

#### 예상 절약액 (Estimated Savings)

[![](https://files.readme.io/f53d6245eb8bb81fb652a05869fe71102ed50ab304d2fc8faf1cc17198794470-360019038197.jpg)](https://files.readme.io/f53d6245eb8bb81fb652a05869fe71102ed50ab304d2fc8faf1cc17198794470-360019038197.jpg)

예상 절약 지표:

* ProtectLITE 및 유효성 검증 규칙에 의해 실시간으로 식별 및 차단된 사기의 가치를 표시하여 사용자가 광고 네트워크를 통해 해결하도록 합니다.
* 다음 수식을 사용합니다. 예상 절약 = 차단된 인스톨 수 X 앱 평균 eCPI.
* 오가닉 트래픽과 관련이 없습니다.

이 합계가 계산되는 방식에 대한 더 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/protect360-anti-fraud-guide#faq">FAQ</Anchor>에서 확인하세요.

<div id="identified-installs" />

#### 식별된 인스톨

[![](https://files.readme.io/2bc38a1ee19b4a13c18ed7571d97efd0f855d27142e8a6cd9a761cac276d3bd0-360019090998.jpg)](https://files.readme.io/2bc38a1ee19b4a13c18ed7571d97efd0f855d27142e8a6cd9a761cac276d3bd0-360019090998.jpg)

식별된 인스톨 지표는 ProtectLITE 및 유효성 검증 규칙에 의해 실시간으로 식별 및 차단된 인스톨 수를 표시합니다.

<div id="suspected-overall-fraud-threat" />

#### 의심스러운 전체 Fraud 위협

[![](https://files.readme.io/bb6a33cfea1dbff695d46a4b2f6547b756740cf35b750db25097d7ec772cc3d8-360019091058.jpg)](https://files.readme.io/bb6a33cfea1dbff695d46a4b2f6547b756740cf35b750db25097d7ec772cc3d8-360019091058.jpg)

의심되는 전체 위협 수준:

* 구독이 있는 경우 Protect360에서 차단할 사기 예상 값입니다.
* 고급 사기 방지 보호를 받기 위해 Protect360으로 업그레이드해야 하는지 여부에 대한 좋은 아이디어를 제공합니다.

</Accordion>

<div id="installs-chart" />

<Accordion title="인스톨—차트">

<div id="fraud-trend-over-time-chart" />

#### 시간 경과에 따른 프로드 경향 차트

이 차트는 날짜 필터에서 선택한 기간 동안 ProtectLITE 및 유효성 검증 규칙에 의해 차단된 일별 인스톨 수를 표시합니다.

</Accordion>

<div id="installs-table" />

<Accordion title="인스톨—표">

<div id="identified-fraud-breakdown" />

#### 프로드 상세

이 표는 날짜 필터에서 선택한 기간 동안 ProtectLITE 및 유효성 검증 규칙에 의해 차단된 인스톨 수를 표시합니다.

CSV 형식으로 테이블을 데스크톱에 다운로드하려면 **CSV 내보내기**를 클릭하십시오.

표는 다음 이미지에 보여지듯이 일반 개요 형식으로 표시됩니다.

[![plite_fraud_table.jpg](https://files.readme.io/81246675ce8f0e1243e0c0d64e1cf347246bb403894718ad9e23c56fc594eb84-360019038257.jpg)](https://files.readme.io/81246675ce8f0e1243e0c0d64e1cf347246bb403894718ad9e23c56fc594eb84-360019038257.jpg)

동적 표 구조를 사용하면 다음을 수행할 수 있습니다.

* 표 설정 버튼을 클릭하여 표에 열을 추가하거나 제거할 수 있습니다.  
  변경 사항이 있는 경우 나중에 저장 버튼을 클릭하여 나중에 방문할 때를 위해 사용자 지정 내용이 저장되도록 하십시오.
* 열 설정에서 열 섹션을 끌어 열 순서를 변경합니다.

[![plite_edit_columns.jpg](https://files.readme.io/52fc1378d4c758d80ed2a89b24f5b7fa949c9ccccae7ff5edf4af307538e805a-360019038297.jpg)](https://files.readme.io/52fc1378d4c758d80ed2a89b24f5b7fa949c9ccccae7ff5edf4af307538e805a-360019038297.jpg)

<div id="content-of-the-identified-fraud-breakdown-table" />

#### 식별된 프로드 쪼개보기 표 내용

| 표 열 | 설명 |
| --- | --- |
| 그룹화 | <ul><li>[기본 설정] 표 및 대시보드는 미디어소스별로 그룹화되어 조회됩니다.</li><li>특정 미디어소스를 선택했을 때, 조회 기준(grouping)은 미디어소스와 사이트 ID 모두로 자동 적용됩니다.</li><li>선택적 조회 기준은 캠페인, 지역, 채널, 에이전시 및 이들의 조합입니다.</li><li>논오가닉 트래픽에만 적용되는 차원을 그룹화할 경우, 표에는 오가닉 미디어 소스에 대해 N\/A가 표시됩니다.</li></ul> |
| **인스톨** | **사기 및 유효성 검증 규칙으로 인해 차단된 인스톨의 헤드라인 분석** |
| Total (A) | <ul><li>총 인스톨 수 = 사기 인스톨 및 유효성 검증 규칙을 통해 식별된 인스톨을 포함한 모든 앱 인스톨 수입니다.</li><li>일반 인스톨은 개요 대시보드에서 미디어소스 (논오가닉)별로 가능합니다.</li></ul> |
| 식별된 인스톨 (B) | <ul><li>실시간으로 식별 및 차단된 총 인스톨 수</li><li>오가닉 차단 인스톨은 대시보드에 표시되지 않습니다. 오가닉 차단 인스톨을 참조하려면 로데이터 리포트를 사용하십시오.</li><li>[기본 설정] 이 KPI에 따라 내림차순으로 표를 정렬합니다.</li></ul> |
| **식별된 인스톨 %** (B/A) | 식별된 인스톨 수 / 총 인스톨 수 |
| 식별된 포스트 어트리뷰션 (C) | Protect360 필요 |
| 식별된 포스트 어트리뷰션 % (C/A) | Protect360 필요 |
| **가짜 설치** | **실제 유저 행동을 모방하는 프로드 인스톨** |
| 실시간 차단 | 실시간 차단된 허위 인스톨 수 |
| 식별된 포스트 어트리뷰션 | Protect360 필요 |
| **하이재킹된 인스톨** | **실제 사용자 인스톨의 어트리뷰션을 가로채려는 사기성 마지막 클릭.** |
| 실시간 차단 | 실시간 차단된 인스톨 하이재킹 수 |
| 식별된 포스트 어트리뷰션 | Protect360 필요 |
| **유효성 검증 규칙** | **유효성 검증 규칙 조건으로 인해 잘못된 것으로 발견된 인스톨.** |
| 차단된 인스톨 | 유효성 검증 규칙에 의해 차단된 인스톨. |
| 차단된 어트리뷰션 | 유효성 검증 규칙으로 인해 수정된 어트리뷰선을 가진 인스톨. |
| **클릭** | **소스에서 합법적인 클릭.**<br /><br />**참고:** 클릭 데이터가 표에 표시되려면 필터 표시줄에서 모든 어트리뷰션 유형을 선택해야 합니다(그렇지 않으면 N/A로 표시됨). 그에 따라 필터 선택을 조정해야 합니다. |
| Total (E) | 소스에서 수신된 합법적인 총 클릭 수. |
| 차단 수 |  |
| **노출** | **소스에서 발생한 노출.**<br /><br />**참고:** 노출 데이터가 표에 표시되려면 필터 표시줄에서 모든 기여 분석 유형을 선택해야 합니다(그렇지 않으면 N/A로 표시됨). 그에 따라 필터 선택을 조정해야 합니다. |
| 합계 | 소스에서 발생한 합법적 노출 및 사기 노출 총수 |
| 차단 수 |  |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특징 | 비고 |
| --- | --- |
| 광고주 액세스 | 모든 계정 사용자. |
| 광고 네트워크 액세스 | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#애드-네트워크-권한">ProtectLITE 대시보드 및 로데이터에 액세스하려면</Anchor> 광고주 권한이 필요합니다.</li><li>광고주는 광고 네트워크를 연동 파트너로 가져야 합니다.</li></ul> |
| 에이전시 액세스 | <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#애드-네트워크-권한">ProtectLITE 대시보드 및 로데이터에 액세스하려면</Anchor> 광고주 권한이 필요합니다. |
| 에이전시 투명성 | 비투명 에이전시: |

</Accordion>

<div data-zendesk-anchors="01JDHEKR6W19WD6HXFFMRNXKFF=protectlite dashboard=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C 01JDHEKR6YGEKRB23M19F5ZGQ5=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C 01JDHEKR6YPNDQAK3ATDRDDZTC=filters-and-groupings installs%E2%80%94headline-metrics=installs-headline-metrics 01JDHEKR75TF5RHJTFM91XPYPY=installs-headline-metrics estimated-savings=%EC%98%88%EC%83%81-%EC%A0%88%EC%95%BD%EC%95%A1-estimated-savings 01JDHEKR76MMVSJSWFTZS5PRBK=%EC%98%88%EC%83%81-%EC%A0%88%EC%95%BD%EC%95%A1-estimated-savings identified-installs=%EC%8B%9D%EB%B3%84%EB%90%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8 01JDHEKR77VGHR1BWQFPYSWW2E=%EC%8B%9D%EB%B3%84%EB%90%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8 suspected-overall-fraud-threat=%EC%9D%98%EC%8B%AC%EC%8A%A4%EB%9F%AC%EC%9A%B4-%EC%A0%84%EC%B2%B4-fraud-%EC%9C%84%ED%98%91 01JDHEKR78BBFEZS98VG0VTERN=%EC%9D%98%EC%8B%AC%EC%8A%A4%EB%9F%AC%EC%9A%B4-%EC%A0%84%EC%B2%B4-fraud-%EC%9C%84%ED%98%91 installs%E2%80%94chart=installs-chart 01JDHEKR795RK8KP9BZ0WECQW8=installs-chart fraud-trend-over-time-chart=%EC%8B%9C%EA%B0%84-%EA%B2%BD%EA%B3%BC%EC%97%90-%EB%94%B0%EB%A5%B8-%ED%94%84%EB%A1%9C%EB%93%9C-%EA%B2%BD%ED%96%A5-%EC%B0%A8%ED%8A%B8 01JDHEKR79YM7VWE6NH2FJ70NS=%EC%8B%9C%EA%B0%84-%EA%B2%BD%EA%B3%BC%EC%97%90-%EB%94%B0%EB%A5%B8-%ED%94%84%EB%A1%9C%EB%93%9C-%EA%B2%BD%ED%96%A5-%EC%B0%A8%ED%8A%B8 installs%E2%80%94table=installs-table 01JDHEKR79ZBQVSTT4GA162J94=installs-table identified-fraud-breakdown=%ED%94%84%EB%A1%9C%EB%93%9C-%EC%83%81%EC%84%B8 01JDHEKR79H7PQFEJGWAY4RMJC=%ED%94%84%EB%A1%9C%EB%93%9C-%EC%83%81%EC%84%B8 content-of-the-identified-fraud-breakdown-table=%EC%8B%9D%EB%B3%84%EB%90%9C-%ED%94%84%EB%A1%9C%EB%93%9C-%EC%AA%BC%EA%B0%9C%EB%B3%B4%EA%B8%B0-%ED%91%9C-%EB%82%B4%EC%9A%A9 01JDHEKR7BR6ESS9DX03NMHPT0=%EC%8B%9D%EB%B3%84%EB%90%9C-%ED%94%84%EB%A1%9C%EB%93%9C-%EC%AA%BC%EA%B0%9C%EB%B3%B4%EA%B8%B0-%ED%91%9C-%EB%82%B4%EC%9A%A9 01JDHEKR9JCAR22V33B7TFZSPV=traits-and-limitations" />
