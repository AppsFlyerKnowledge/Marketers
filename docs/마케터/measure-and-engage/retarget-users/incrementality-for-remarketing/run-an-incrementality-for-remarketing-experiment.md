---
title: 성과 증분 측정 솔루션 시험 실행
metadata:
  keywords:
    - Advertisers
    - Premium
    - Marketers
    - Incrementality
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-niv-klein
    - Marketers
    - Incrementality
  created_at: '2020-10-12T19:26:09Z'
  edited_at: '2026-10-14T10:38:24Z'
  id: 360014225577
  locale: ko
  section: Incrementality for remarketing
  section_id: 6551378485649
  url: https://support.appsflyer.com/hc/ko/articles/360014225577
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 귀사의 리마케팅 캠페인의 실제 영향을 파악하기 위해 성과 증분 측정 솔루션 시험을 실행해 보세요.

<Image align="center" alt="KB_토글_최종.jpg" src="https://files.readme.io/4de8c3ff1edaaae77fc0571de6125b25c884bcc4e4ac67471fc90610298866e1-30780522054801.jpg" />

<div id="about-the-experiment" />

## 실험에 대하여

<Anchor target="_blank" href="/marketers/ko/docs/incrementality-for-remarketing-overview">성과 증분 측정</Anchor> 테스트는 귀사의 캠페인이 가져온 실제 영향을 A\/B 테스트로 정확히 측정하여 "성과 증가분"—리마케팅 캠페인 결과로 발생한 전환과 그 외에 발생했을 전환 간의 차이를 확인합니다.

결과는 귀사의 마케팅 투자로 발생한 실제 가치를 이해하는 데 매우 중요합니다. 성과 증분 측정 테스트를 통해 특정 채널과 캠페인의 영향을 객관적으로 파악하여 예산 배분 및 캠페인 최적화에 대한 보다 나은 결정을 내릴 수 있습니다.

앱스플라이어는 잠재 오디언스 생성 시점부터 시작하는 자동화된 프로세스로 성과 증분 측정 테스트를 쉽게 수행할 수 있게 지원합니다. 새 오디언스는 활성화된 "증분적 영향 측정" 토글을 통해 연결된 매체 파트너와 통제군 간에 자동으로 분할됩니다. 통제군은 파트너로부터 배제된 오디언스의 일부로, 시험에 필수적인 요소입니다. 오디언스가 저장되면 성과 증분 측정 솔루션 실험이 자동으로 생성됩니다. 파트너 측에서 귀사의 캠페인을 시작하고 올바른 캠페인이 연결되었는지 확인한 후, 성과 증분 측정 대시보드에서 실험 결과를 볼 수 있습니다.

<div id="get-started" />

## 시작하기

각 단계에 대한 추가적인 세부 사항은 아래의 [실험 설정](/docs/run-an-incrementality-for-remarketing-experiment#시험-설정)을 참고하세요.

|  | 단계 |
| --- | --- |
| 1 | [**시험 목표 파악하기**](/docs/run-an-incrementality-for-remarketing-experiment#know-your-test-objectives)<br /><br />명확한 시험 목표와 결과에 대한 가설을 정의하여 귀사의 실험 결과의 실행 가능성을 극대화하세요. |
| 2 | [**대상 오디언스 만들고 그룹을 분할하기**](/docs/run-an-incrementality-for-remarketing-experiment#create-the-target-audience-and-split-groups)<br /><br /><Anchor target="_blank" href="/marketers/ko/docs/audiences-guide">오디언스</Anchor>에서:<ul><li>오디언스를 구성합니다.</li><li>광고 네트워크에 연결하세요.</li><li>오디언스는 활성화된 토글을 통해 자동으로 실험군과 통제군으로 나뉩니다. (성과 증분 측정 솔루션 구독자의 경우, 2023년 1월 11일 이후에 생성된 오디언스)<br />앱스플라이어 오디언스는 실험군 구성원을 광고 네트워크에 업로드하고, 통제군 구성원은 보류합니다.</li></ul> |
| 3 | [**캠페인 시작 및 실험**](/docs/run-an-incrementality-for-remarketing-experiment#launch-the-campaign-and-experiment)<ul><li>광고 네트워크에서 오디언스 사용자를 타겟으로 하는 캠페인을 만들고 실행합니다.</li><li>성과 증분 측정 솔루션 시험은 자동으로 생성됩니다(성과 증분 측정 솔루션 구독자의 경우).</li></ul>실험군은 광고에 노출됩니다. 통제군은 그렇지 않습니다. |
| 4 | [**결과 분석**](/docs/run-an-incrementality-for-remarketing-experiment#analyze-the-results)<ul><li>성과 증분 측정 분석 결과는 <Anchor target="_blank" href="/marketers/ko/docs/incrementality-for-remarketing-overview#incrementality-dashboard">성과 증분 측정 대시보드</Anchor>에 표시됩니다.</li><li>행 수준 사용자 데이터는 <Anchor target="_blank" href="/marketers/ko/docs/incrementality-for-remarketing-overview#raw-data-reports">성과 증분 측정 로데이터 리포트</Anchor>에서 볼 수 있습니다(데이터 락커를 통해).</li></ul>성공적으로 실행된 성과 증분 측정 실험으로 얻은 통찰력을 통해 마케팅 캠페인을 최적화하여 긍정적인 효과를 극대화할 수 있습니다. 예를 들어, 타겟 오디언스를 위한 최상의 메시징, 광고 소재나 프로모션, 가장 효과적인 미디어 소스를 선정하는 데 도움이 될 수 있습니다. |

<div id="set-up-the-experiment" />

## 시험 설정

<div id="know-your-test-objectives" />

<Accordion title="귀사의 시험 목표를 명확히 하세요">

모든 시험에서 중요한 것은 시험하는 것(변수)과 예상 결과(가설)를 명확히 정의하는 것입니다. 다음 표에서는 시험 설계를 위한 지침과 모범 사례를 제공합니다.

| Variables\/가설 | 지침 및 모범 사례 |
| --- | --- |
| 오디언스 | 시험할 오디언스를 설명하세요. 앱스플라이어 오디언스에 이미 설정된 오디언스를 선택하거나, 시험 기준에 맞는 새로운 오디언스를 만드세요. |
| 오디언스 규모 | 사용자 기반이 크고 전환율이 높은 이벤트를 가진 오디언스를 선택하세요. 표본 크기가 클수록 <Anchor target="_blank" href="/marketers/ko/docs/incrementality-for-remarketing-overview#statistical-significance">통계적으로 유의미한 결과</Anchor>를 얻을 가능성이 높습니다.<br /><br />**모범 사례:** 최소 5만 명의 오디언스를 1&#126;3개의 광고 네트워크와 통제군으로 나누세요. |
| 캠페인 | 캠페인 (메시징, 인센티브 등)을 설명하세요. |
| 통제군 비율 | 통제군은 자동으로 오디언스 크기의 15%로 설정됩니다(모범 사례는 15%에서 25% 사이입니다). |
| 실험군 | 시험할 광고 네트워크를 판단하세요. 분할 비율은 네트워크 간에 균등하게 나눠집니다(하지만 각자에게 배정할 오디언스의 비율은 조정할 수 있습니다).<br /><br />**모범 사례:** 1&#126;3개의 광고 네트워크 |
| 가설 | 실험의 예상 결과를 정의합니다.<br /><br />실험을 시작하기 전에 결과를 예측하는 것이 다소 직관에 반할 수 있지만, 가설을 세우는 것은 실험 설계의 중요한 요소입니다. 이는 결과를 해석하는 데 도움이 됩니다.<br /><br />**모범 사례:** 모호한 추정치 대신 실제 백분율을 사용하여 쉽게 검증 가능한 가설을 제시합니다. 예를 들어:<ul><li>***15% 더 많은 사용자이 업그레이드를 구매할 것이라는 가설***은 쉽게 검증할 수 있습니다.</li><li>***훨씬 더 많은 사용자이 업그레이드를 구매할 것이라는 가설***은 시험하기가 더 어렵습니다.</li></ul> |

<div id="example" />

> 📄 **예시**
>
> 위에서 설명한 지침을 사용하면 다음과 같은 실험을 정의할 수 있습니다.
>
>
>
> | Variables\/가설 | 예 |
> | --- | --- |
> | 오디언스 | 등록을 완료했지만 구매를 하지 않은 사용자 |
> | 오디언스 규모 | 100,000 |
> | 캠페인 | 특정 기간 동안 구매하는 사용자에게 할인 쿠폰을 제공하는 캠페인 |
> | 통제군 비율 | 오디언스 규모의 15% |
> | 실험군 | 남은 오디언스를 다음과 같이 분배하세요:<br /><br />* 네트워크 A(오디언스의 42%)<br />* 네트워크 B(오디언스의 43%) |
> | 가설 | 리마케팅 캠페인에 (유저를 앱에) 참여시키고 구매를 한 실험군 사용자의 비율이 통제군 사용자보다 10% 더 높을 것입니다. |

</Accordion>

<div id="create-the-target-audience-and-split-groups" />

<Accordion title="타겟 오디언스를 만들고 그룹을 분할하세요.">

귀사의 목표를 정의한 후 다음 단계는 시험할 오디언스를 구성하는 것입니다.

1. 앱스플라이어 오디언스에서 <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide#오디언스-생성-및-관리">오디언스를 생성</Anchor>합니다(또는 실험 요구 사항을 충족하는 기존 오디언스를 분할할 수도 있습니다).
2. 선택한 오디언스의 **연결** 탭에서:
   * 오디언스를 1&#126;3개의 애드 네트워크 파트너와 연결하세요.
   * <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide#audience-split-and-control-groups">잠재 고객을 분할하는</Anchor> 토글이 활성화되었는지 확인합니다(**2023년 1월 11일 이후에 생성된 잠재 고객에서 성과 증분 측정 가입자에 대해 자동으로 활성화됨**). 그렇지 않은 경우, 토글을 클릭해서 활성화하세요.  
     <Image align="center" alt="측정_영향_토글.jpg" src="https://files.readme.io/a04b3be68fcc00d62e6a92391fbbea685ca2bfcbf83bd5678660c6a1b8c58fc2-30780493858065.jpg" />
   * 통제군은 자동으로 15%로 설정됩니다(권장).
   * 나머지 오디언스는 선택한 애드 네트워크 파트너 사이에 자동으로 균등하게 나뉩니다.
     * 전체 분할 비율은 통제군을 포함하여 100%가 되어야 합니다.

분할이 활성화된 상태로 귀사의 오디언스를 저장하면 성과 증분 측정 솔루션이 자동으로 시작됩니다(성과 증분 측정 솔루션 구독자에게만 해당). 이러한 실험은 제목 앞에 접두사 "[자동]"을 붙여 성과 증분 측정 대시보드에서 볼 수 있습니다.

<Image align="center" alt="자동_제목_앞으로_.jpg" src="https://files.readme.io/fdab39eee29240ae0d9b907f7c6504a9e08e470454d5f8e43933512c65db15d4-30780522066833.jpg" />

**중요 참고사항:**

* 실험이 운영되는 동안에는 오디언스 구성을 변경하지 마세요. 파트너, 오디언스 이름 또는 기타 설정을 변경하면 통계 분석에 오류가 발생할 수 있습니다.  
  **모범 사례:** 실험이 종료된 후에도 이전에 시험한 오디언스 정의를 변경하려면 먼저 오디언스를 복제하고 새 복사본에서 변경하세요. 이를 통해 성과 증분 측정 대시보드의 과거 데이터 무결성을 지속적으로 보장할 수 있습니다.
* 기존 오디언스의 분할 및 파트너 구성을 수정하면 현재 성과 증분 측정 실험이 종료되고 새로운 실험이 생성됩니다.
* #### <span id="check-for-audience-expansion-features"></span>오디언스 확장 기능을 확인하세요:

Meta Ads와 Google Ads에는 캠페인이 설정된 오디언스 목록 외부를 타겟팅하여 도달 범위를 확장할 수 있는 선택 기능이 있습니다. 이 기능이 켜져 있으면 성과 증분 측정 실험에 편향이 생겨 부정확한 결과가 나올 수 있습니다. **이 기능이 꺼져 있는지 확인하세요.**

Meta Ads에서는 이 기능을 "Advantage 커스텀 오디언스"라고 합니다. 이 기능은 광고 세트 수준에서 나타나며 기본적으로 활성화되어 있습니다.

<Image align="center" alt="이미지__4_.png" src="https://files.readme.io/a0bee1bbb2c6521007146a5ac70de52ce821f459fd2aece127a97a2e0b75c93d-30780493862033.png" width="458px" />
Google Ads에서는 이를 "잠재고객 확장"이라고 합니다.

<Image align="center" alt="Google_광고_증가_제한_잘림.jpg" src="https://files.readme.io/042aac534d0a527753b643bb63a52f59889219ebda922cc04f8a61c5984afb80-30780493867409.jpg" width="436px" />

</Accordion>

<div id="launch-the-campaign-and-experiment" />

<Accordion title="캠페인을 시작하고 실험해보세요">

**다음 작업을 수행하세요:**

<div id="1-configure-campaigns-on-ad-networks" />

#### 1. 애드 네트워크에서 캠페인 구성

첫 번째 단계는 귀사의 사용자 오디언스를 타겟으로 하는 캠페인을 생성하고, 오디언스를 업로드하는 각 애드 네트워크에서 캠페인을 시작하는 것입니다.

* **중요!** 정확한 시험 결과를 얻으려면, 캠페인을 구성하여 시험 대상 오디언스의 **사용자만** 타겟으로 삼고 다른 소스의 사용자는 포함하지 않도록 하세요.
* 테스트 대상 오디언스가 새로 생성된 오디언스일 경우, 해당 오디언스가 애드 네트워크 플랫폼에 표시되기까지 최대 24시간이 걸릴 수 있습니다.

<div id="2-ensure-the-correct-campaign-is-linked-to-the-experiment" />

#### 2. 올바른 캠페인이 실험에 연결되어 있는지 확인하세요.

"성과 증분 측정" 토글이 활성화된 상태에서 새 오디언스를 생성하면 (또는 기존 오디언스에서 새로 활성화된 경우), 새로운 성과 증분 측정 실험이 자동으로 시작됩니다. 가장 관련 있는 캠페인이 자동으로 실험에 연결되지만, 원하는 경우 캠페인을 변경할 수 있습니다.

**캠페인을 연결/변경하려면:**

1. **성과 증분 측정 솔루션 대시보드** > 특정 실험 > **실험 편집**을 클릭합니다.

<Image align="center" alt="Edit_experiment.jpg" src="https://files.readme.io/f478737e2a8db560a5ea33b287fe8f41587ec1f743c1bc01ba15ab6ce72478e9-30780493873425.jpg" width="642px" />

또는

**오디언스**에서 특정 오디언스를 찾아 성과 증분 측정 열에서 **+ 캠페인 연결**을 클릭합니다.

<Image align="center" alt="Link_campaign__audiences_status_.jpg" src="https://files.readme.io/5da762448fb731843fef0aec66ae826ed6922a5dd213a78ccd93f544b21fcfdc-small-30780522084625.jpg" width="768px" />

캠페인을 연결할 수 있는 기간이 표시됩니다.

<Image align="center" alt="Link_campaign_to_experiment_window.jpg" src="https://files.readme.io/9492444847bfc6a26778624d72d5b468acc62b705530db66d0bd0fdff89f5e89-30780493883409.jpg" width="506px" />

2. 각 애드 네트워크에 맞는 캠페인을 선택하세요.

**참고:** 드롭다운 메뉴에는 매체사에서 가져온 캠페인이 표시됩니다. 데이터가 제공되면 드롭다운의 캠페인은 특정 오디언스를 겨냥한 마케팅에 사용될 가능성에 따라 정렬됩니다. 가장 위의 제안이 미리 선택되어 있을 것입니다.

3. **저장**을 클릭합니다.

이제 캠페인이 실험과 연결되었습니다.

<div id="manually-create-an-experiment" />

#### 수동으로 실험 생성하기

2023년 1월 11일 이후에 귀사의 오디언스를 생성한 성과 증분 측정 구독자라면 실험을 수동으로 만들 필요가 없습니다. 실험은 자동으로 귀사의 오디언스를 위해 생성되며, 성과 증분 측정 대시보드에 "[자동]"이라는 제목과 함께 표시됩니다. 오래된 오디언스에 대해 수동 실험을 생성하거나 다른 이유가 있는 경우, 다음 단계를 따르세요.

**새로운 성과 증분 측정 실험을 수동으로 생성하려면:**

* 앱스플라이어의 사이드 메뉴에서 **최적화** > **성과 증분 측정**을 선택하세요.
* **성과 증분 측정 실험** 페이지에서 **New 실험** 버튼을 클릭합니다.
* 마법사의 지시에 따라 실험을 만드세요. 각 단계마다 상세한 지침이 제공됩니다.

  <div id="notes" />

  > 📘 **참고**
  >
  > <Image align="center" alt="" src="https://files.readme.io/e956b50df1931b190206f42b48a8f2f061937fe1f25c96801a416d287d7eb3f5-30780493888273.png" width="603px" />
  >
  > 마법사의 2단계에서는 실험에 포함할 오디언스의 **시작 날짜**를 선택하라는 안내가 나옵니다.
  >
  > 기본적으로 이는 오디언스가 처음으로 통제군과 나누어진 날짜입니다. 정확한 실험 결과를 위해, 아래 경우에 해당하면 날짜를 변경하세요:
  >
  > * 선택한 오디언스의 정의를 변경한 경우( <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide#규칙-집합에-대한-모든-것">오디언스 세분화 규칙</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide#user-identifier-device-id-vs-customer-id">유저 식별자</Anchor> 등) → 이 날짜를 정의 변경이 이루어진 최신 날짜로 변경하세요.
  > * 기존 오디언스를 대상으로 New 캠페인을 테스트 중인 경우 → 이 날짜를 New 캠페인 시작 날짜로 변경하세요.
  >
  > **마법사 단계 3 - 목표 설정**
  >
  > <Image align="center" alt="3단계_설정_목표.jpg" src="https://files.readme.io/9c58ad61463b1751f5ad8b2c5235d6d61b13baa156db56d5edeb156debbcfeaa-30780522104081.jpg" />
  >
  > 여기에서 타겟 앱과 KPI를 선택하세요.
  >
  > **참고:** 선택하지 않은 다른 KPI도 실험 종료 시 사용할 수 있습니다.
  >
  > **마법사 단계 4 – 검토**
  >
  > <Image align="center" alt="" src="https://files.readme.io/75c90dc66cff6abc772a352d81b6b57498e5915da66efaa83a754d9a5a08be70-30780522113681.png" width="583px" />
  >
  > 마법사의 4단계에서는 **실험 기간**을 설정하라는 안내가 나옵니다.
  >
  > * 기본적으로 실험은 생성 후 30일 동안 실험되도록 설정됩니다. 이는 실험 운영에 권장되는 최소 기간입니다.
  > * 실험을 계속 운영할 경우 **무기한으로 실험 계속** 옵션을 선택하세요.


</Accordion>

<div id="analyze-the-results" />

<Accordion title="결과 분석">

초기 실험 결과는 광고 네트워크에서 캠페인 시작 후 약 48시간 후에 <Anchor target="_blank" href="/marketers/ko/docs/incrementality-for-remarketing-overview#incrementality-dashboard">성과 증분 측정 솔루션, Incrementality 대시보드</Anchor>에서 확인할 수 있습니다(업데이트 <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#eod">매일</Anchor>). <Anchor target="_blank" href="/marketers/ko/docs/understand-incrementality-for-remarketing-experiment-alerts">실험 페이지</Anchor>에서 결과의 정확성을 저해할 수 있는 문제를 식별하고 이를 해결하기 위한 조치를 받을 수 있는 알림을 볼 수 있습니다.

<Anchor target="_blank" href="/marketers/ko/docs/incrementality-for-remarketing-overview#raw-data-reports">성과 증분 측정 로데이터 리포트</Anchor>는 데이터 락커에서 이용 가능합니다.

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide">오디언스 가이드</Anchor>

<div data-zendesk-anchors="overview=%EC%8B%A4%ED%97%98%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01HARVCSMM80QXXXKJC8TX7CKC=%EC%8B%A4%ED%97%98%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC get-started=%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0 h_01HARVCSMMYJVN6GJ3TB46P8AC=%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0 set-up-the-experiment=%EC%8B%9C%ED%97%98-%EC%84%A4%EC%A0%95 h_01HARVCSMMMAJ6VTYHZ2ZJ5HNS=%EC%8B%9C%ED%97%98-%EC%84%A4%EC%A0%95 h_01HARVCSMM9P2HN5WA9C16PA5E=know-your-test-objectives h_01HARVCSMM2THH54JH58GM1K57=%EC%98%88%EC%8B%9C h_01HARVCSMM77RV7NM9K7D5FJM5=create-the-target-audience-and-split-groups check-for-audience-expansion-features=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%ED%99%95%EC%9E%A5-%EA%B8%B0%EB%8A%A5%EC%9D%84-%ED%99%95%EC%9D%B8%ED%95%98%EC%84%B8%EC%9A%94 h_01HARVCSMMXNE4NCWSQZ9SHK1J=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%ED%99%95%EC%9E%A5-%EA%B8%B0%EB%8A%A5%EC%9D%84-%ED%99%95%EC%9D%B8%ED%95%98%EC%84%B8%EC%9A%94 h_01HARVCSMMH11D6RKDZQZ3WVZ6=launch-the-campaign-and-experiment 1-configure-campaigns-on-ad-networks=1-%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EC%97%90%EC%84%9C-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EA%B5%AC%EC%84%B1 h_01HARVCSMMVXJWCT2BX3CVC3VT=1-%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EC%97%90%EC%84%9C-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EA%B5%AC%EC%84%B1 2-link-campaigns-to-experiment=2-%EC%98%AC%EB%B0%94%EB%A5%B8-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%B4-%EC%8B%A4%ED%97%98%EC%97%90-%EC%97%B0%EA%B2%B0%EB%90%98%EC%96%B4-%EC%9E%88%EB%8A%94%EC%A7%80-%ED%99%95%EC%9D%B8%ED%95%98%EC%84%B8%EC%9A%94 h_01HARVCSMNAWNYEY83NC6Y5XV4=2-%EC%98%AC%EB%B0%94%EB%A5%B8-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%B4-%EC%8B%A4%ED%97%98%EC%97%90-%EC%97%B0%EA%B2%B0%EB%90%98%EC%96%B4-%EC%9E%88%EB%8A%94%EC%A7%80-%ED%99%95%EC%9D%B8%ED%95%98%EC%84%B8%EC%9A%94 manually-create-an-experiment=%EC%88%98%EB%8F%99%EC%9C%BC%EB%A1%9C-%EC%8B%A4%ED%97%98-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0 h_01HARVCSMNZVWK8Z36ER1HH10W=%EC%88%98%EB%8F%99%EC%9C%BC%EB%A1%9C-%EC%8B%A4%ED%97%98-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0 h_01HARVCSMN5944HRD9N7YEKT3P=%EC%B0%B8%EA%B3%A0 h_01HARVCSMNS961WKFX280J3R2X=analyze-the-results h_01HE7RBMSE1RHVSJC7B7FZG8SJ=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
