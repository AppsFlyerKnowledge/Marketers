---
title: iOS 어트리뷰션을 위한 Single Source of Truth (SSOT) 가이드
metadata:
  keywords:
    - iOS
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
  created_at: '2021-11-11T09:28:42Z'
  edited_at: '2026-10-14T10:26:28Z'
  id: 4410634145425
  locale: ko
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ko/articles/4410634145425
---
> **한눈에 보기**: iOS 14+ 환경에서 앱스플라이어는 IDFA, IDFV, SKAN, Apple Search Ads 등 다양한 어트리뷰션 매칭 메서드를 통해 데이터를 통합하여 앱 캠페인 성과에 대한 전체적인 그림을 제공합니다. 어떠한 어트리뷰션 메서드도 앱 성과의 전체적인 그림을 완전히 제공하지는 못합니다. 도전 과제는 동일한 사용자가 두 가지 방법으로 측정될 수 있기 때문에 주어진 사용자를 한 번만 계산하는 것입니다. 앱스플라이어의 SSOT 메커니즘이 바로 이를 해결합니다. SSOT 보고서와 지표는 사실이며 정확하여 동일한 사용자를 한 번만 계산합니다.

<Embed title="iOS 어트리뷰션을 위한 Single Source of Truth (SSOT) 가이드" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/545isomgo1" providerUrl="https://fast.wistia.com" />

<div id="about-single-source-of-truthtrue-ios-performance-data" />

## Single Source of Truth에 관한 사항 - 진정한 iOS 성과 데이터

iOS 14부터 앱스플라이어는 SKAdNetwork, 앱 추적 투명성 동의 사용자, 확률적 모델링, 증분 기반 데이터 인사이트, Apple Search Ads 전용 API를 포함한 여러 데이터 스트림을 활용하여 iOS 사용자 어트리뷰션을 수행합니다. IDFA가 없으면, 중복된 데이터를 포함하지 않고 여러 어트리뷰션 방법을 연결하는 것이 사실상 불가능합니다.

SSOT 메커니즘은 중복된 인스톨 데이터를 제거하고 잘못 어트리뷰션된 사용자를 수정합니다. 즉, 논오가닉 미디어 소스에 어트리뷰션되어야 할 사용자가 오가닉으로 측정된 것을 수정합니다. 결과적으로 캠페인에 어트리뷰션된 인스톨 수가 수정되고 eCPI, ROI (투자수익률), ROAS와 같은 관련 비용 및 수익 관련 지표도 올바르게 계산됩니다.

간단히 말해, SSOT 메커니즘은 다른 측정 유형을 사용하여 어트리뷰션이 지정된 SKAN 인스톨을 플래그로 표시합니다. 플래그는 동일한 사용자를 두 번 계산하는 것을 방지하기 위해 데이터 집약형 지표를 계산할 때 고려됩니다. 마찬가지로, SKAN 로데이터를 처리할 때도 플래그를 사용합니다.

귀사의 데이터에 SSOT 플래그를 포함하려면 컨버전 스튜디오에서 SSOT를 활성화해야 합니다.

<div id="turn-on-single-source-of-truth" />

<Accordion title="Single Source of Truth 활성화">

<Image align="center" alt="SSOT컨트롤.png" src="https://files.readme.io/fd99117e9278ebda3b1f0cc137afb266643e5e45325345ec51aeb58c16d4f13c-31247514683153.png" />

**SSOT를 활성화하려면:**

1. 시작 전, 앱스플라이어의 <Anchor target="_blank" href="https://content.appsflyer.com/ios-hub/billing/">Single Source of Truth 청구 정책</Anchor>을 고려하세요.
2. 앱스플라이어에서 **설정** > **SKAN 컨버전 스튜디오**로 이동합니다.
3. 커스텀 **모드**를 선택하세요.
4. **Single Source of Truth**를 켜세요.
5. 필요한 설정을 완료하세요.

<Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio">SKAN 컨버전 스튜디오</Anchor>를 참조하세요.

</Accordion>

<div id="overview-dashboard-single-source-of-truth-view" />

## 개요 대시보드의 Single Source of Truth 보기

<Image align="center" alt="SSOTisNowOn.png" src="https://files.readme.io/8e21fd0c64bb85fb94af752eb037472726d68cd55bf028dc5306b0acb398d199-31247490958225.png" />

개요 대시보드를 통해 제공되는 SSOT 보기는 논오가닉 성과 지표의 전체적인 모습을 제공합니다. 보기에서:

* 인스톨 지표는 신뢰할 만합니다.
* eCPI, ARPU, ROAS를 포함하여 인스톨 지표에 의존하는 비용 및 수익 관련 지표가 정확히 계산됩니다.
* 잘못 귀속된 인스톨을 고려하여 조정된 오가닉 지표입니다.

이 섹션에서는 SSOT 보기의 차이점과 고유한 기능을 강조합니다. 이 섹션에서는 개요 대시보드에 익숙하신 분을 대상으로 합니다.

<div id="turn-on-single-source-of-truth-view" />

<Accordion title="Single Source of Truth 보기 활성화">

SSOT 보기의 데이터는 컨버전 스튜디오에서 Single Source of Truth를 활성화한 후 3&#126;5일 후에 이용할 수 있습니다.

**SSOT 보기를 활성화하려면**:

1. 시작 전, 컨버전 스튜디오에서 <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio#single-source-of-truth">Single Source of Truth</Anchor>가 켜져 있는지 확인하세요.
2. 앱스플라이어에서 **대시보드** > **개요**로 이동합니다.   
   <Image align="center" alt="저장된 보고서 선택.png" src="https://files.readme.io/863a9c66c37e031a1f1b2a7fb3e0c68eb9c29405283214e68a432357c35524dd-31247514684177.png" width="243px" />
3. ▼를 클릭하세요.
4. Lite 개요를 선택하세요.  
   Single Source of Truth 스위치가 표시됩니다.  
   <Image align="center" alt="SSOTviewon.png" src="https://files.readme.io/7b0a664f0882dad46e7239b5363592717358a79d920377dde13aa9c5dfbe84c3-31247514684433.png" width="246px" />
5. Single Source of Truth를 켜세요.
6. 다음 중 하나가 나타납니다.
   * 대시보드 지표와 차트가 표시됩니다.  
     다음 섹션에서는 사용 가능한 데이터를 설명합니다. 표시되는 데이터에 대한 자세한 내용은 다음 섹션을 참조하세요.  
     SSOT 보기를 새로운 리포트로 저장합니다. 이렇게 하려면:  
     1. ▼를 클릭하세요.
     2. **+ 새 리포트 저장**을 클릭하세요.
     3. 리포트 이름을 입력하세요.
     4. **저장**을 클릭하세요.
   * 데이터가 표시되지 않습니다. SSOT를 켠 후 데이터가 표시되기까지 3&#126;5일이 걸릴 수 있습니다. 이 기간이 지나기를 기다렸다가 대시보드를 다시 방문하세요.

일반 데이터를 보려면 SSOT 스위치를 언제든지 끌 수 있습니다. SSOT에서 사용할 수 없는 차원도 확인가능합니다.  그렇게 하면 심층 분석이 가능합니다.

</Accordion>

<div id="ssot-view-considerations" />

<Accordion title="SSOT 뷰 고려 사항">

SSOT 보기에서:

* **Null 전환 값 (CV)**: 모델링됨. 고급 머신러닝은 [af\_attribution 플래그](/docs/single-source-of-truth-ssot-guide-for-ios-attribution#어트리뷰션-플래그-필드)를 사용하여 앱스플라이어 또는 SKAN이 부여한 null 값을 모델링합니다. SKAN에 어트리뷰트한 경우 모든 설치 후 SKAN 측정이 SSOT 대시보드에 포함됩니다. <Anchor target="_blank" href="/marketers/ko/docs/skan-modeled-data">더 알아보기</Anchor>
* **다시 다운로드**: 인스톨 지표에 포함됩니다. 인스톨과 재다운로드가 분리되지 않습니다.
* **시간대**: 앱스플라이어가 보고한 인스톨 및 이벤트는 UTC 또는 <Anchor target="_blank" href="/marketers/ko/docs/app-settings">앱 설정 페이지</Anchor>에서 설정한 앱별 로컬 시간대로 표시됩니다. SKAN에서 보고한 데이터의 경우 인스톨과 이벤트는 UTC를 사용하여 표시되며, Meta 및 Google SKAN 데이터는 Meta와 Google 계정에서 설정한 시간대에 기반하여 표시됩니다.
* **통화**: <Anchor target="_blank" href="/marketers/ko/docs/app-settings">앱 설정 페이지</Anchor>에 설정된 USD 또는 앱별 현지 통화로 표시됩니다.
* **수익 지표 (D2, D7):** 불완전하거나 누락된 SKAN 포스트백(Null 변환 값)을 고려한 모델링된 데이터 포함

<div id="filter-considerations" />

#### 필터 고려 사항

다음 표에 설명된 대로 필터가 데이터 표시 및 지표에 미치는 영향을 고려해 보세요.

| 필터 | 고려 사항 |
| --- | --- |
| Single Source of Truth | Single Source of Truth 지표를 보려면 제어가 켜져 있는지 확인하세요. |
| 보기 유형 | <ul><li>**유저 유입:** SSOT 데이터에 가장 적합한 뷰.</li><li>**리타겟팅**: SKAN은 리타겟팅을 지원하지 않습니다.</li><li>**통합**: 인스톨 캠페인에는 SSOT 데이터가 포함됩니다. 리타겟팅 캠페인은 SSOT에 영향을 받지 않습니다.</li></ul> |
| 날짜 | <ul><li>[모범 사례] 정확한 결과를 얻으려면 최근 3일을 포함하지 않는 7일 이상의 날짜 범위를 선택하세요.</li><li>일반적으로 SSOT를 켜고 나서 3일 후가 가장 빠른 시작 날짜입니다. 앱스플라이어가 이 날짜를 결정합니다.</li><li>최적의 날짜 선택 예시:<ul><li>현재 날짜가 2월 10일이고 1월 29일에 SSOT를 시작했다면, 2월 1일부터 7일까지를 선택할 수 있습니다.</li></ul></li><li>일부 데이터(예: 수익)는 SSOT를 켜고 나서 8일 후에만 사용할 수 있을 수 있습니다.</li><li>Google SKAN 인스톨은 최대 45일의 지연이 있을 수 있습니다.</li></ul> |
| 캠페인 필터 | 사용 가능한 캠페인 데이터 계층 구조 필터:<ul><li>미디어 소스</li><li>캠페인</li></ul> |
| 주요 KPI | SSOT 대시보드에서 이용 가능한 주요 KPI를 통해 다음을 확인할 수 있습니다.<ul><li>유저 유입: 논오가닉 및 오가닉 모두</li><li>SKAN 중복</li><li>리타겟팅: 리인게이지먼트 및 재어트리뷰션</li><li>비용</li><li>eCPI</li></ul>각 KPI에는 퍼센트 값이 있습니다. 이 값은 제시된 KPI가 이전 기간의 병렬 날짜 범위와 어떻게 비교되는지를 나타냅니다. 예를 들어, 이번 주와 지난 주를 비교하거나 선택된 날짜 범위를 그 전의 동일한 날 수와 비교할 수 있습니다: 예를 들어, 인스톨의 X% 증가가 표시되면 이는 이전 병행 날짜 범위에 X% 적은 인스톨이 있었음을 의미합니다. |
| 차트 | **사용 가능한 디멘션:**<ul><li>어트리뷰션 메서드:<ul><li>AF 모델: SKAN을 포함한 두 가지 이상의 메서드로 일치하는 인스톨. 대시보드에서는 동일한 인스톨을 중복 계산하지 않기 위해 SKAN 기록이 무시됩니다. SKAN 로데이터에서 인스톨의 af\_attribution\_flag가 true로 설정됩니다.</li><li>SKAN 고유 특징: SKAN에 의해서만 일치하고 다른 메서드는 일치하지 않는 인스톨. SKAN 로데이터에서 인스톨의 af\_attribution\_flag가 false로 설정됩니다.</li></ul></li><li>어트리뷰션 유형</li><li>어트리뷰션 터치 유형</li><li>캠페인</li><li>캠페인 ID</li><li>미디어 소스</li><li>소스</li><li>앱 ID(일부 차트의 경우)</li><li>지역(SKAN 지역은 <Anchor target="_blank" href="/marketers/ko/docs/skan-modeled-data#geo">모델링</Anchor>됨)</li><li>인앱 이벤트 이름(특정 인앱 이벤트의 이름을 SKAN 전환 스튜디오에서 구성함을 의미합니다).</li></ul>**지표:**<br /><br />지표 섹션에 설명된 대로입니다. |
| 표 | **그룹화:**<ul><li>[기본값] 표는 미디어 소스 및 캠페인 별로 그룹화됩니다.</li><li>그룹화 옵션은 다음과 같습니다. 미디어 소스, 어트리뷰션 유형, 어트리뷰션 방법, 캠페인, 캠페인 ID, 귀속된 터치 유형, 날짜, 소스, 지역 및 이들의 조합입니다. **참고**: SKAN 지역은 <Anchor target="_blank" href="/marketers/ko/docs/skan-modeled-data#geo">모델링</Anchor>됩니다.</li><li>논오가닉 트래픽에만 적용되는 차원을 그룹화할 경우, 표에는 오가닉 미디어 소스에 대해 N\/A가 표시됩니다.</li></ul>**지표:**<br /><br />지표 섹션에 설명된 대로입니다. |

</Accordion>

<div id="metrics" />

<Accordion title="지표">

SSOT 대시보드에서 사용 가능한 지표:

| 지표 | 설명 및 고려 사항 |
| --- | --- |
| 그룹화 | <ul><li>[기본값] 표는 미디어 소스 및 캠페인 별로 그룹화됩니다.</li><li>그룹화 옵션은 다음과 같습니다. 미디어 소스, 어트리뷰션 유형, 어트리뷰션 방법, 캠페인, 캠페인 ID, 귀속된 터치 유형, 날짜, 소스 및 이들의 조합.</li><li>논오가닉 트래픽에만 적용되는 차원을 그룹화할 경우, 표에는 오가닉 미디어 소스에 대해 N\/A가 표시됩니다.</li></ul> |
| **SSOT 어트리뷰션** | **선택한 날짜 동안 SSOT 인스톨, 리어트리뷰션 및 재참여에 대한 주요 분석**<ul><li>**논오가닉: 유저를 유입시키는 캠페인입니다. SSOT 메커니즘은 동일한 인스톨이 한 번만 계산되도록 보장합니다.**</li><li>**오가닉 지표.**</li></ul> |
| 총합 | 인스톨 수, 리어트리뷰션 및 재참여 수. |
| 인스톨 | 앱을 인스톨한 고유 사용자 수입니다. UA 캠페인에서 앱스플라이어가 보고한 인스톨에 SKAN이 중복을 제거한 새로운 인스톨 및 재다운로드수를 더해 계산합니다. |
| 리어트리뷰션 | 리타게팅 지표는 통합 및 리타게팅 보기 유형에서 조회할 수 있습니다. SKAN이 리타게팅을 지원하지 않는다는 점을 고려하세요. |
| 재참여 | 리타게팅 지표는 통합 및 리타게팅 보기 유형에서 조회할 수 있습니다. SKAN이 리타게팅을 지원하지 않는다는 점을 고려하세요. |
| **기타 지표** | **SSOT 및 광고 성과와 관련된 다양한 기타 지표** |
| SKAN 중복 | af\_attribution\_flag=true인 SKAN 인스톨 수 |
| 클릭 수 | API를 통해 광고 네트워크가 보고한 클릭 및 노출 데이터입니다. SSOT 메커니즘은 터치포인트 지표에 영향을 주지 않습니다. |
| 노출 수 | API를 통해 광고 네트워크가 보고한 클릭 및 노출 데이터입니다. SSOT 메커니즘은 터치포인트 지표에 영향을 주지 않습니다. |
| 전환율 | 클릭 후 인스톨 |
| 비용 ($) | API를 통해 광고 네트워크에서 보고한 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview">캠페인 비용</Anchor> 데이터입니다. 최소 1회의 인스톨이 포함된 캠페인의 데이터가 표시됩니다. SSOT 메커니즘은 보고된 총 비용에 영향을 미치지 않습니다. 오직 인스톨 수를 사용하여 계산된 지표에만 영향을 줍니다. |
| 평균 eCPI ($) | 인스톨 지표당 유효 비용은 SSOT 뷰 인스톨 지표를 사용하여 계산됩니다. 오가닉 인스톨은 제외됩니다. |
| CPM | 1,000 노출 당 비용 (Cost per Mille) 공식: (비용 \/ 노출) * 1000 |
| CPC | 클릭당 비용 공식: 비용 \/ 클릭 |
| 클릭-쓰루 | 사용자가 광고(CTA)를 클릭한 후 발생하는 어트리뷰션 수 |
| CTR | 클릭률 공식: 클릭 \/ 노출 |
| 뷰-쓰루 | <span id="simple-tabpanel-2"></span>사용자가 광고를 본 후 발생하는 어트리뷰션 수 (VTA) |
| 수익 (D2) | <ul><li>불완전하거나 누락된 SKAN 포스트백(널 변환 값)을 고려하기 위해 모델링된 데이터가 포함되어 있습니다.</li></ul>첫 번째 SKAN 측정 기간 (D2)에 대한 SKAN 및 클래식 수익 (광고 수익 포함):<ul><li>**SKAN 수익:** SKAN 인스톨 수익 (af\_attribution\_flag=false\/null). 컨버전 스튜디오 의 <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio#revenue-component">수익에 대한 전환 값 설정과 측정 기간을 기준으로 합니다.</Anchor></li><li>**클래식 수익: 클래식 어트리뷰션 메서드로 귀속된 인스톨 후 앱 사용자가 발생한 수익과 SKAN 측정 기간 내 수익입니다.**</li><li>컨버전 스튜디오에서 SKAN 4를 사용하는 경우, 이는 인스톨 후 2일간의 데이터입니다. 컨버전 스튜디오에서 SKAN 3을 사용하는 경우, 데이터는 정의된 SKAN 유저 활동 측정 기간을 기준으로 하며, 이는 2일 이상 또는 미만인지 여부입니다.</li><li>예시<ul><li>활동 기간은 24시간입니다.</li><li>수익 이벤트는 인스톨 다음날 (Day X+1)에 발생하지만 24시간 유저 활동 측정 기간 내에 발생합니다.<ul><li>SKAN과 AF에서 보고된 수익은 모두 24시간 기간 내에 발생한 것으로 계산됩니다. 이는 인스톨과 다른 날이라도 마찬가지입니다.</li></ul></li></ul></li></ul>**팁**: SKAN 수익 정확도를 높이려면:<ul><li><Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">SKAN 광고 수익 지침</Anchor>을 따르십시오.</li><li>수익 권장 사항을 활용하세요.</li></ul> |
| 수익 D7 | <ul><li>불완전하거나 누락된 SKAN 포스트백(Null 변환 값)을 고려한 모델링된 데이터 포함</li><li>SKAN 측정 기간을 넘어서, 앱 설치 후 최대 7일까지의 모델링 데이터를 포함합니다. <Anchor target="_blank" href="/marketers/ko/docs/skan-modeled-data#revenue-ltv">더 알아보기</Anchor></li><li>모델링을 위해 수익 D2 데이터가 필요합니다.</li></ul> |
| ARPU D2 | 유저 당 평균 수익.<br /><br />공식: 수익\자 고유 사용자<br /><br />컨버전 스튜디오에서 SKAN 4를 사용하는 경우, 이는 인스톨 후 2일간의 데이터입니다. 컨버전 스튜디오에서 SKAN 3을 사용하는 경우, 데이터는 정의된 SKAN 유저 활동 측정 기간을 기준으로 하며, 이는 2일 이상 또는 미만인지 여부입니다. |
| ARPU D7 | SKAN 측정 기간을 넘어서, 앱 설치 후 최대 7일까지의 모델링 데이터를 포함합니다. <Anchor target="_blank" href="/marketers/ko/docs/skan-modeled-data#revenue-ltv">더 알아보기</Anchor> |
| ROAS D2 | 광고 지출 수익률(%).<br /><br />공식: 수익\/비용 * 100<br /><br />컨버전 스튜디오에서 SKAN 4를 사용하는 경우, 이는 인스톨 후 2일간의 데이터입니다. 컨버전 스튜디오에서 SKAN 3을 사용하는 경우, 데이터는 정의된 SKAN 유저 활동 측정 기간을 기준으로 하며, 이는 2일 이상 또는 미만인지 여부입니다. |
| ROAS D7 | SKAN 측정 기간을 넘어서, 앱 설치 후 최대 7일까지의 모델링 데이터를 포함합니다. <Anchor target="_blank" href="/marketers/ko/docs/skan-modeled-data#revenue-ltv">더 알아보기</Anchor> |
| ROI (투자수익률) D2 | ROI (투자수익률)(%).<br /><br />공식: (수익 - 비용)\/비용 * 100<br /><br />컨버전 스튜디오에서 SKAN 4를 사용하는 경우, 이는 인스톨 후 2일간의 데이터입니다. 컨버전 스튜디오에서 SKAN 3을 사용하는 경우, 데이터는 정의된 SKAN 유저 활동 측정 기간을 기준으로 하며, 이는 2일 이상 또는 미만인지 여부입니다. |
| ROI (투자수익률) D7 | SKAN 측정 기간을 넘어서, 앱 설치 후 최대 7일까지의 모델링 데이터를 포함합니다. <Anchor target="_blank" href="/marketers/ko/docs/skan-modeled-data#revenue-ltv">더 알아보기</Anchor> |
| 총이익 D2 | 캠페인 비용을 공제한 후의 이익입니다.<br /><br />공식: 수익 - 비용<br /><br />컨버전 스튜디오에서 SKAN 4를 사용하는 경우, 이는 인스톨 후 2일간의 데이터입니다. 컨버전 스튜디오에서 SKAN 3을 사용하는 경우, 데이터는 정의된 SKAN 유저 활동 측정 기간을 기준으로 하며, 이는 2일 이상 또는 미만인지 여부입니다. |
| 총이익 D7 | SKAN 측정 기간을 넘어서, 앱 설치 후 최대 7일까지의 모델링 데이터를 포함합니다. <Anchor target="_blank" href="/marketers/ko/docs/skan-modeled-data#revenue-ltv">더 알아보기</Anchor> |
| **인앱 이벤트 메트릭** | **특정 인앱 이벤트에 관련된 메트릭** |
| 이벤트 고유 사용자 (D2) | 이벤트를 수행하는 고유 사용자. 앱스플라이어와 SKAN을 조합하여 측정하며, null 값의 모델링된 데이터를 포함합니다. SKAN 4를 사용하는 경우, 이 데이터는 설치 후 첫 2일간 누적됩니다. SKAN 3을 사용하는 경우 데이터는 정의된 유저 활동 측정 기간에 근거해 설치 후의 날수로 누적된 것입니다. |
| 이벤트 고유 사용자 (D7) | 앱스플라이어와 SKAN의 조합을 기반으로 모델링된 이벤트 수행하는 고유 사용자. SKAN 측정 기간을 넘어 앱 설치 후 최대 7일까지 모델링된 데이터가 포함됩니다. <Anchor target="_blank" href="/marketers/ko/docs/skan-modeled-data#inapp-event-ltv">더 알아보기</Anchor><br /><br />참고: D7의 고유 사용자에는 D2의 고유 사용자도 포함됩니다. |
| 이벤트 eCPA (D2) | 효율적인 행동당 비용: 비용\/고유 사용자 수행 이벤트. |
| 이벤트 eCPA (D7) | 효율적인 행동당 비용: 비용\/고유 사용자 수행 이벤트. SKAN 측정 기간을 넘어 앱 설치 후 최대 7일까지 모델링된 데이터가 포함됩니다. <Anchor target="_blank" href="/marketers/ko/docs/skan-modeled-data#inapp-event-ltv">더 알아보기</Anchor> |
| 이벤트 전환 (D2) | 이벤트를 수행하는 고유 사용자의 비율(%)은 사용자 설치, 재참여 또는 재귀속되는 사용자에 대한 비율입니다. 공식: 고유 사용자 / 어트리뷰션 * 100. |
| 이벤트 전환 (D7) | 이벤트를 수행하는 고유 사용자의 비율(%)은 사용자 설치, 재참여 또는 재귀속되는 사용자에 대한 비율입니다. 공식: 고유 사용자 / 어트리뷰션 * 100. SKAN 측정 기간을 넘어 앱 설치 후 최대 7일까지 모델링된 데이터가 포함됩니다. <Anchor target="_blank" href="/marketers/ko/docs/skan-modeled-data#inapp-event-ltv">더 알아보기</Anchor> |
| 이벤트 수익 (D2) | 이 이벤트로 생성된 수익, 설치 후 정의된 일 수 |
| 이벤트 수익 (D7) | 이 이벤트로 인해 발생한 수익은 앱 설치 후 정의된 일수 내에 발생한 수익입니다. SKAN 측정 기간을 넘어 앱 설치 후 최대 7일까지 모델링된 데이터가 포함됩니다. <Anchor target="_blank" href="/marketers/ko/docs/skan-modeled-data#inapp-event-ltv">더 알아보기</Anchor> |

</Accordion>

<div id="how-does-ssot-work" />

## SSOT 작동 방식

<div id="understanding-skanaf-modeled-attribution-duplication" />

<Accordion title="SKAN-AF 모델 어트리뷰션 중복 이해">

SKAN 어트리뷰션과 AF 모델 어트리뷰션은 다르게 작동하며 다양한 특성과 한계를 가집니다. 그래서 각 인스톨은 다음과 같은 논오가닉 미디어 소스에 측정될 수 있습니다:

* SKAN 또는 AF 모델을 통해서만 (고유 어트리뷰션).
* SKAN과 AF 모델을 동시에 사용 (중복). 이 경우 SSOT 메커니즘은 af\_attribution\_flag=TRUE를 플래그하여 SKAN 중복 인스톨을 신호로 보냅니다. SSOT 대시보드에는 두 개 대신 하나의 인스톨만 표시됩니다.
* SKAN이나 AF 모델 모두에 해당하지 않는, 즉 이 인스톨은 오가닉입니다.

가능한 SKAN-AF 모델 어트리뷰션 시나리오는 다음의 벤 다이어그램에 설명되어 있습니다.

altskan\_af\_model\_diagram.pngalt

다음 표는 각 어트리뷰션 시나리오의 이유를 설명합니다.

| SKAN만 | AF 모델만 | SKAN과 AF 모델 모두 | SKAN도 AF 모델도 아님 |
| --- | --- | --- | --- |
| <ul><li>미디어 소스가 SRN이고, 사용자의 디바이스가 iOS 14.5+이며, 사용자가 이중 앱 추적 투명성(ATT) 동의를 제공하지 않는 경우.</li><li>미디어 소스가 비(非) SRN이며, 사용자의 디바이스가 iOS 14.5+ 환경에서 확률적 모델링을 사용할 수 없고, 사용자가 이중 앱 추적 투명성(ATT) 동의를 제공하지 않는 경우.</li></ul> | <ul><li>사용자의 디바이스가 iOS 14.4 이하입니다.</li><li>미디어 소스가 SKAN을 지원하지 않습니다.</li><li>인스톨이 웹에서 앱으로의 흐름에서 발생했습니다 (SKAN은 앱 간만 지원함).</li><li>리타겟팅을 통해 인스톨이 이루어졌습니다 (SKAN에서는 지원되지 않음).</li></ul> | 제한 사항이 존재하지 않으며, SKAN과 AF 모델 모두 인스톨을 어트리뷰트합니다.<br /><br />이 경우 중복 인스톨이 생성되며, SSOT가 중복을 제거하는 데 필요합니다. | 사용자는 오가닉입니다. |

</Accordion>

<div id="ssot-mechanism-workings" />

<Accordion title="SSOT 메커니즘 작동 방식">

SSOT는 다음의 시각 자료에 해당하는 방식으로 작동합니다.

<Image align="center" alt="SingleSourceOfTruth.png" src="https://files.readme.io/882527d4828cf3c7156caf183652368de33463a440715c69f7ec39bfd0f655fa-31247514685329.png" />

**SSOT 메커니즘은 어떻게 작동하나요?**

SSOT 메커니즘은 유저 디바이스에 있는 귀사의 앱에서 사용되는 앱스플라이어 SDK와 앱스플라이어 플랫폼에 존재합니다. 자세한 내용은 다음과 같습니다:

**유저 디바이스:**

* 유저가 처음으로 앱을 엽니다. 앱스플라이어 플랫폼은 유저를 어트리뷰션하려고 시도합니다. 어트리뷰션 가능 여부는 캠페인 유형과 유저 동의(앱 추적 투명성(ATT)) 상태에 따라 결정됩니다.
* 어트리뷰션에 성공하면, SDK가 전환 값(CV)에 어트리뷰션 비트를 설정합니다.
* 일반 SKAdNetwork의 흐름은 변함없이 계속됩니다. 즉, 측정 기간이 종료될 때까지 유저 액티비티는 계속 측정되고 전환 값이 설정됩니다.
* 그리고 나서, iOS가 포스트백을 전송합니다.

**앱스플라이어 플랫폼**

* 앱스플라이어는 iOS 포스트백을 수신하여 전환 값을 디코딩하고, af\_attribution\_flag를 통해 어트리뷰션 비트의 값을 노출합니다. 자세한 내용은 다음 표에 설명되어 있습니다.

**고려 사항**

* 일반적으로, 앱스플라이어는 재설치를 포함하지 않습니다. SSOT에서는 재설치 상태를 고려하지 않습니다. 즉, SSOT 분석 컨텍스트에서 재설치로 인한 중복된 SKAN 인스톨은 제거되지 않으며 af\_attribution 플래그 설정에 영향을 미치지 않습니다.

<div id="attribution-flag-field" />

#### **어트리뷰션 플래그 필드**

| 전환 값 내의 SSOT 지표 | 의미 | af\_attribution\_flag 필드 |
| --- | --- | --- |
| 켜짐 | SSOT가 컨버전 스튜디오에 작동 중이며, 앱스플라이어가 유저 어트리뷰션에 성공했습니다. | 참됨 |
| 꺼짐 | SSOT가 컨버전 스튜디오에 작동 중이지만, 앱스플라이어가 유저 어트리뷰션에 실패했습니다. | 거짓됨 |
| -- | SSOT가 컨버전 스튜디오에서 꺼져 있습니다. | Null |

**af\_attribution\_flag(어트리뷰션 비트)는 리포팅 도구에 어떤 영향을 미칠까요?**

* SKAN 대시보드: SKAN 포스트백에서 보고한 성과만 반영됩니다. 따라서 af\_attribution 플래그는 고려되지 않으며 중복은 제거되지 않습니다.
* SKAN <Anchor target="_blank" href="/marketers/ko/docs/skan-aggregated-performance-report-api">데이터 집약형 성과 리포트</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/skan-raw-data-reports">로데이터 리포트</Anchor>: af\_attribution\_flag는 이 보고서에서 확인할 수 있습니다. 귀사의 리포팅 요구에 맞게 활용하세요. SKAN 데이터와 앱스플라이어 데이터를 함께 사용할 경우, 플래그를 사용하여 중복 데이터를 제거하세요. 이 내용은 원시 데이터와 데이터 집약형 보고서 모두에 적용됩니다.
* 개요 대시보드의 SSOT 보기: 모든 어트리뷰션 방법, SKAN, IDFA, IDFV, Apple Search Ads 등의 데이터는 중복된 SKAN 데이터를 제거한 후 단일 화면에 통합됩니다.

</Accordion>

<div id="metrics-derived-by-combining-data-from-multiple-attribution-methods" />

<Accordion title="다양한 어트리뷰션 방법의 데이터를 결합하여 산출된 지표">

SKAN 데이터를 다른 어트리뷰션 방법의 데이터와 결합할 때는 af\_attribution\_flag를 사용해 중복 데이터를 제거하세요. 이 내용은 원시 데이터와 데이터 집약형 보고서 모두에 적용됩니다.

다음 예시 지표는 af\_attribution\_flag를 사용해 계산할 수 있습니다.

* 논오가닉 인스톨
* 오가닉 설치
* eCPI
* 코호트 수익

예시 지표를 계산하는 공식:

| 지표 설명 | 지정 | 공식 |
| --- | --- | --- |
| 논오가닉 앱스플라이어 인스톨 | A | 앱스플라이어가 보고한 논오가닉 인스톨 |
| SKAN 고유 인스톨 | B | af\_attribution\_flag=false인 경우 SKAN 인스톨 |
| 모든 논오가닉 인스톨 | C | A + B |
| 오가닉 설치 | D | 총 인스톨 - C<br /><br />**참고**: 총 인스톨은 어트리뷰션과 상관없이 앱스플라이어 SDK가 기록한 모든 인스톨을 의미합니다. |
| 캠페인 eCPI | E | 비용 \/ C |
| 코호트 수익 | F | 다음 요소를 더하세요:<ul><li>A로 정의된 사용자들의 수익입니다. 귀사의 SKAN 측정 기간과 동일한 초기 앱 설치 후 기간 동안 발생한 이벤트를 포함하세요.</li><li>af\_attribution\_flag = false인 경우 SKAN 수익</li></ul> |
| 오가닉 수익 D2 | G | 총 D2 수익 - A 및 B 인스톨의 D2 수익 |
| 오가닉 IAE 고유 사용자 D2 | H | 총 D2 IAE 고유 사용자 - A 및 B 인스톨의 D2 이벤트 고유 사용자 |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특성 및 제한 사항">

| 특징 | 비고 |
| --- | --- |
| SSOT 보기 | SSOT 는 `af_attribution_flag=true`을 포함하는 지난 5일 동안 최소 1개의 SKAN 포스트백이 있을 때만 사용할 수 있습니다. |
| 총 인스톨 | 경우에 따라 SSOT를 끌 때보다 SSOT를 켤 때 더 많은 인스톨이 표시될 수 있습니다. 그 이유 중 하나는 누락된 전환 값 추정 모델링이 인스톨 날짜 계산에 영향을 미칠 수 있으며, 유사한 날짜의 인스톨을 비교할 때 차이를 발생시킬 수 있기 때문입니다. 또한 null CV가 모델링되지 않으면 총 인스톨 수가 증가할 수 있습니다. 이 사례, 모든 SKAN 인스톨이 고유한 것으로 계산되기 때문입니다(플래그 사용). |
| 수익 | 수익 및 기타 수익 관련 지표(ARPU, ROAS, ROI (투자수익률), 매출총이익)는 2022년 9월 1일부터 지원됩니다. |
| 대행사 | 에이전시 사용자는 개요 대시보드에서 SSOT 보기를 볼 수 있습니다. |
| 애드 네트워크 | <ul><li>애드 네트워크는 개요 대시보드에서 SSOT 보기에 액세스하여 미디어 소스에 기인된 데이터를 확인할 수 있습니다. SSOT 보기를 확인하려면:<ul><li>광고주는 컨버전 스튜디오에서 SSOT를 켜 놓아야 합니다.</li><li>애드 네트워크는 SKAN 캠페인을 운영되어야 합니다.</li><li>애드 네트워크는 집계 데이터에 액세스하기 위해 광고주로부터 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">필요한 권한</Anchor>을 받아야 합니다.</li></ul></li><li>애드 네트워크는 skad\_af\_attribution\_flag 필드 매크로를 추가하여 SKAN 포스트백을 통해 SSOT 신호를 받을 수 있습니다. <Anchor target="_blank" href="/partners/ko/docs/skan-integration-guide-for-ad-networks#앱스플라이어에서-데이터-수신">더 보기</Anchor></li></ul> |
| D7 메트릭 | 다음과 같은 사례, D7 메트릭이 누락되었거나 D2 메트릭보다 적을 수 있습니다:<ul><li>날짜 범위에 8일이 경과하지 않은 날짜가 포함되어 있습니다.</li><li>모델링된 데이터를 사용할 수 없습니다. 예를 들어, 14일 동안의 수익 데이터가 없는 사례입니다. <Anchor target="_blank" href="/marketers/ko/docs/skan-modeled-data#revenue-ltv">더 알아보기</Anchor></li><li>지난 14일간 SKAN 컨버전 스튜디오 구성이 변경되었습니다.</li><li>특정 날짜에 인스톨 수가 10회 미만입니다.</li></ul> |
| SKAN 컨버전 스튜디오 구성 변경 | 귀사의 SKAN 컨버전 스튜디오 구성을 변경하면 약 96시간 동안 SSOT 데이터에 부정확성이 있을 수 있습니다. 이는 앱스플라이어가 새 스키마로 SKAN 포스트백을 즉시 디코딩하기 시작하지만, 여전히 이전 스키마로 인코딩된 인스톨의 포스트백이 도착하기 때문입니다. |
| AF 보고 데이터 | <ul><li>AF 보고 데이터(AF 모델 데이터라고도 함)는 SKAN과 달리 다른 앱스플라이어 어트리뷰션 방법을 통해 어트리뷰션된 인스톨 또는 기타 이벤트의 데이터를 나타냅니다.</li><li>SSOT 대시보드의 목적은 SKAN과 다른 앱스플라이어 방식을 통해 어트리뷰션된 인스톨 및 이벤트의 중복을 방지하는 것입니다.</li><li>SSOT를 켠 후 SSOT가 켜지기 전의 데이터를 보려는 경우 SSOT 대시보드에는 AF 보고 데이터만 표시됩니다.</li></ul> |
| 인앱 이벤트 | (분류 기준으로서의) 인앱 이벤트와 인앱 이벤트 지표는 다음과 같은 조건으로만 사용할 수 있습니다.<ul><li>Window 1 기간 동안 발생한 이벤트는 확인할 수 있습니다.</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * 개요 대시보드
> * <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">SKAN 솔루션 가이드</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio">SKAN 컨버전 스튜디오</Anchor>
> * 개요 대시보드

<div data-zendesk-anchors="how-to-get-true-ios-14-performance-data=single-source-of-truth%EC%97%90-%EA%B4%80%ED%95%9C-%EC%82%AC%ED%95%AD---%EC%A7%84%EC%A0%95%ED%95%9C-ios-%EC%84%B1%EA%B3%BC-%EB%8D%B0%EC%9D%B4%ED%84%B0 01H8TZV6P41Z3ZEZ8VS86DK1J9=single-source-of-truth%EC%97%90-%EA%B4%80%ED%95%9C-%EC%82%AC%ED%95%AD---%EC%A7%84%EC%A0%95%ED%95%9C-ios-%EC%84%B1%EA%B3%BC-%EB%8D%B0%EC%9D%B4%ED%84%B0 01H8TZV6P4G5AF2MJDQB8J6W2M=turn-on-single-source-of-truth overview-dashboard-single-source-of-truth-view=%EA%B0%9C%EC%9A%94-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%9D%98-single-source-of-truth-%EB%B3%B4%EA%B8%B0 01H8TZV6P4ZBJTDH0FQ6F5D6Q9=%EA%B0%9C%EC%9A%94-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%9D%98-single-source-of-truth-%EB%B3%B4%EA%B8%B0 01H8TZV6P47ZE6PMPF7S9GCJ16=turn-on-single-source-of-truth-view 01H8TZV6P4VCC5NRKBRQNJ4NX3=ssot-view-considerations filter-considerations=%ED%95%84%ED%84%B0-%EA%B3%A0%EB%A0%A4-%EC%82%AC%ED%95%AD 01H8TZV6P4QXEXYWSXKDB7B5SV=%ED%95%84%ED%84%B0-%EA%B3%A0%EB%A0%A4-%EC%82%AC%ED%95%AD 01H8TZV6P4YNTFBX5RXVKK8J0F=metrics how-does-ssot-work=ssot-%EC%9E%91%EB%8F%99-%EB%B0%A9%EC%8B%9D 01H8TZV6P4K8VXNKDR7JHM8PFW=ssot-%EC%9E%91%EB%8F%99-%EB%B0%A9%EC%8B%9D 01H8TZV6P4QYQJ177E2ZG676MH=understanding-skanaf-modeled-attribution-duplication 01H8TZV6P58E502Y1FDFHC3KHM=ssot-mechanism-workings attribution-flag-field=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%94%8C%EB%9E%98%EA%B7%B8-%ED%95%84%EB%93%9C 01H8TZV6P5SSKDTKV4BV3TTA7D=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%94%8C%EB%9E%98%EA%B7%B8-%ED%95%84%EB%93%9C 01H8TZV6P5AHZD8VRWRS4SPBYW=metrics-derived-by-combining-data-from-multiple-attribution-methods 01H8TZV6P5KN4F24ZN33V0TK7K=traits-and-limitations h_01HE182N43SSBX051E4GK7NFQ8=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
