---
title: 연동된 파트너 설정
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-11-08T08:02:46Z'
  edited_at: '2026-10-14T10:30:29Z'
  id: 4410395957521
  locale: ko
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/ko/articles/4410395957521
---
> **한눈에 보기:** 앱스플라이어와 연동을 설정하여 어트리뷰션 측정을 활성화하고, 파트너에게 포스트백을 발송하며 기타 연동 기능을 활성화하세요.

<div id="overview" />

## 개요

파트너, 미디어 소스 및 써드 파티 플랫폼은 API를 통해 앱스플라이어와 연동됩니다. 이 문서에는 비 SRN 애드 네트워크에 대한 어트리뷰션 링크 생성을 포함하여 연동을 활성화하고 설정하기 위한 일반적인 지침이 포함되어 있습니다.

* 이 가이드는 SRN에는 적용되지 않습니다. SRN에 대한 <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns">명시적인</Anchor> 문서를 사용하세요.
* 일부 광고 네트워크에는 전용 문서가 있습니다.
* 구성을 설정하기 전에 파트너에게 연락하여 계정을 개설하세요.

<div id="partner-types-in-the-ecosystem" />

<Accordion title="생태계의 파트너 유형">

아래 이미지는 어트리뷰션 생태계를 구성하는 다양한 파트너 유형을 보여줍니다.

[![Ecosystem.jpg](https://files.readme.io/9377db3a6a6effd7ff8139994e2e8ed8dea04331588b5df2a31f1acd643afd9f-4411031173265.jpg)](https://files.readme.io/9377db3a6a6effd7ff8139994e2e8ed8dea04331588b5df2a31f1acd643afd9f-4411031173265.jpg)

**관련 자료**: <Anchor target="_blank" href="https://www.appsflyer.com/performance-index/">앱스플라이어 퍼포먼스 인덱스</Anchor>는 모바일 매체 소스를 카테고리와 지역별로 순위 매깁니다.

| 파트너 유형 | 설명 |
| --- | --- |
| 애드 네트워크 | 귀사를 대신하여 캠페인을 운영합니다. |
| 대행사 | 대행사의 전문 지식을 활용하여 귀사를 대신해 캠페인을 운영하여 고품질 사용자를 확보하세요. <Anchor target="_blank" href="/marketers/ko/docs/view-agency-data">기관 데이터</Anchor>에 대해 자세히 알아보세요. |
| 마케팅 파트너 | 마케팅 파트너는 특정 광고 네트워크와 협력하는 데 특화되어 있습니다. 예시: Meta 캠페인 관리 파트너, Apple Ads 마케팅 파트너, X 마케팅 파트너. |
| 리타겟팅 네트워크 | 리타겟팅 캠페인에 특화된 광고 네트워크. |
| 써드 파티 플랫폼 | 분석 및 마케팅 자동화 플랫폼과 같은 BI 관련 서비스를 제공합니다. |
| 프로드 감지 | 앱스플라이어 Protect360 프로드 방지 솔루션에 포함되지 않은 외부 써드 파티 프로드 방지 시스템을 가리킵니다. |

</Accordion>

<div id="partners-in-the-marketplace" />

<Accordion title="파트너 통합 분야의 파트너">

앱스플라이어 와 통합된 모든 파트너, 미디어 소스 및 기타 플랫폼은 파트너 통합 페이지에서 확인할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">활성 및 비활성</Anchor> 파트너를 모두 찾고 연결할 새로운 파트너를 검색할 수 있습니다.

**파트너 통합에서 모든 파트너, 미디어 소스 또는 기타 플랫폼을 검색하고 필터링하려면 다음을 수행하세요.**

* 앱스플라이어의 사이드 메뉴에서 **협업** > **파트너 마켓플레이스**를 선택합니다. 다양한 검색 **필터**를 사용할 수 있습니다.

<div id="invite-new-partners-to-appsflyer" />

#### 앱스플라이어에 새로운 파트너 초대

협력하고 있는 파트너가 아직 앱스플라이어와 연동되지 않은 경우, <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#앱스플라이어에-새로운-파트너-초대하기">초대 링크를 발송</Anchor>할 수 있습니다.

</Accordion>

<div id="your-integrated-partners" />

<Accordion title="활성화된 귀사의 연동된 파트너">

파트너 통합의 1. (기능이) 활성화된 2. (사용자가 앱을) 사용중인 통합 탭에는 현재 통합된 모든 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">활성</Anchor> 파트너가 표시됩니다. 이 페이지에서 파트너에 대해 알아보고 연동을 관리할 수 있습니다.

<div id="note" />

> 📘 **참고**
>
> 탭에 표시되는 파트너 목록은 선택한 앱에 따라 다릅니다. 왼쪽 상단에서 앱을 클릭하고 다른 앱을 선택하면 어떤 파트너가 다른 앱에 연결되어 있는지 확인할 수 있습니다.

**활성화된 모든 파트너를 보려면:**

* 앱스플라이어 의 사이드 메뉴에서 **협업** > **파트너 연동** > **활성 연동** 탭을 선택하세요.

</Accordion>

<div id="about-the-integrated-partner-page" />

<Accordion title="파트너 구성 페이지에 대하여">

이 페이지는 다음과 같이 구성되어 있습니다:

* **헤더**: 포함 사항
  * 파트너 이름
  * 전담 파트너 문서로의 링크입니다. 전담 문서가 없을 경우 이 문서가 표시됩니다.
  * 연동 상태
  * 선택된 앱
* **설정 탭**: 사용 가능한 탭은 파트너 유형과 지원되는 기능에 따라 다릅니다.
* **하단**:
  * **목록으로 돌아가기**: 이전에 선택한 필터링 옵션을 사용하여 활성화된 연동 목록으로 돌아갑니다.
  * **상태 메시지:** 탭 데이터의 현재 상태 (예: 저장 중, 저장됨, 오류, 저장되지 않은 변경 사항 있음).
  * **변경 사항 취소:** 저장하지 않고 마지막 변경 사항을 취소합니다.
  * **저장:** 현재 탭의 설정만 저장합니다.

<div id="applicable-settings-tabs-per-partner-type" />

#### 파트너 유형별 적용 가능한 설정 탭

<table><thead><tr><th> </th><th colspan="2">설정 탭</th><th> </th></tr><tr><th>파트너 유형</th><th>연동 </th><th>권한</th><th>비고</th></tr></thead><tbody><tr><td>미디어 소스</td><td>Y</td><td>Y</td><td><p><strong>추가 탭 사용 가능</strong>: 비용, 광고 수익, 어트리뷰션 링크</p><p>광고 네트워크, 제휴 네트워크, 직접 게시자, 프로그래매틱 광고, 중국 국내 광고 네트워크, 리타겟팅 매체가 포함됩니다.<br/>SRN의 경우 어트리뷰션 링크 탭은 적용되지 않습니다.</p></td></tr><tr><td>대행사 </td><td>N</td><td>Y</td><td>광고 네트워크로 동작하지 않는 독립형 대행사</td></tr><tr><td>써드 파티 플랫폼</td><td>Y</td><td>N</td><td>마케팅 자동화 플랫폼 또는 분석 플랫폼</td></tr><tr><td>마케팅 파트너 </td><td>Y</td><td>N</td><td> </td></tr></tbody></table>

</Accordion>

<div id="set-up-a-partner-non-srn" />

## 파트너 설정(비 SRN)

<div id="important" />

> 🚧 **중요!**
>
> 파트너 연동을 활성화하면, 개인 정보를 포함한 일부 데이터(광고 ID, IP 주소 등)가 설정상 자동으로 파트너와 공유됩니다. 이 데이터를 공유할 적절한 법적 근거와 권리가 있는지 사전에 확인하십시오. <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">집약형 프라이버시 강화(AAP) 프레임워크</Anchor>와 <Anchor target="_blank" href="/marketers/ko/docs/apply-privacy-preserving-sdk-methods">SDK의 개인정보 보호 방법</Anchor> 문서를 참조하면, 파트너와의 데이터 공유 범위를 조정할 수 있습니다.

**설정에 접근하고 파트너와의 캠페인을 구성하려면 다음 단계를 따르세요.**

[파트너 연동](/docs/set-up-an-integrated-partner#partners-in-the-marketplace)에서 파트너를 검색하고 선택하세요.

<div id="note-1" />

> 📘 **참고**
>
> 탭의 [일반 설정](#d-general-settings) 단계는 모든 파트너에게 필수입니다. 비SRN 애드 네트워크의 경우 **어트리뷰션 링크** 탭도 완료해야 합니다. 나머지 탭은 선택 사항입니다.

<div id="integration-tab" />

<Accordion title="연동 탭">

파트너 연동은 요구 사항에 따라 다르며, 이 섹션에서 설명된 모든 가능한 옵션의 하위 집합을 포함할 수 있습니다. iOS와 안드로이드 설정에는 몇 가지 차이가 있습니다.

![set_up_an_integrated_partner.png](https://files.readme.io/441ddfcd784a000099ae75acdb234d32bfe75ab598a34a88c7f9ed651fe8f7ec-15520850610449.png)

요구 사항에 따라 섹션을 작성하세요.

<div id="integration-sections" />

#### 연동 섹션

다음 표에서는 연동 페이지의 다양한 섹션을 포함합니다. 일부 섹션은 모두에게 열려 있으며, 다른 섹션은 특정 연동에 한합니다.

<Table>
  <thead>
    <tr>
      <th>
        섹션
      </th>
      <th>
        설명
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="a-activate-partner"></span>
        파트너 활성화
      </td>
      <td>
        파트너와 어트리뷰션 링크를 공유하기 전에 **파트너 활성화**를 켜고 연동 탭의 나머지 섹션을 완료해야 합니다.

        * 캠페인 어트리뷰션을 일시 중지하거나 끄기 위해 **파트너 활성화**를 사용하지 마세요.
        * 파트너 연동을 비활성화하면 **활성 캠페인에 돌이킬 수 없는 손상을 초래할 수 있습니다**.
        * <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">파트너 활성화</Anchor>와 파트너 비활성화의 영향에 대해 더 보기.

        **연동 파트너를 활성화하려면**:

        1. 앱스플라이어 사이드 메뉴에서 **협업**> **파트너 마켓플레이스**를 선택하세요.
        2. 파트너를 검색하여 선택하세요. 파트너 구성 페이지로 이동됩니다.
        3. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">**파트너 활성화**</Anchor>를 켜세요.
        4. **연동 저장**을 클릭합니다.
        5. [선택 사항] 파트너가 <Anchor target="_blank" href="/marketers/ko/docs/manage-data-access-permissions">자신에게 귀속된 데이터를 볼 수 있도록</Anchor> [권한](/docs/set-up-an-integrated-partner#permissions-tab) 탭에서 [애드 네트워크 권한](/docs/set-up-an-integrated-partner#애드-네트워크-권한)을 켜야 합니다.
      </td>
    </tr>
    <tr>
      <td><span id="b-advanced-privacy"></span>
        프라이버시 강화 모드
      </td>
      <td>
        iOS 앱의 경우에만:  
        **iOS 14.5 이상에서 프라이버시 강화 모드** 기능이 활성화되면, 파트너에게 포스트백 및 리포트 통해 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">어떤 데이터를 공유할지 제어</Anchor>할 수 있습니다. 이렇게 하면 파트너에게 유저 식별자의 공유가 제한됩니다. 앱 설정에서 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">집약형 프라이버시 강화</Anchor> 토글을 활성화하면, **프라이버시 강화 모드(iOS 14.5 이상용)** 기능이 자동으로 활성화되며 수정할 수 없도록 잠깁니다.
      </td>
    </tr>
    <tr>
      <td><span id="c-transaction-id"></span>
        트랜잭션 ID
      </td>
      <td>
        iOS 앱의 경우에만:  
        **SKAN 거래 ID 공유**가 켜져 있으면, 파트너에게 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">SKAdNetwork 포스트백의 거래 ID</Anchor>를 공유합니다. 이를 통해 파트너는 귀사의 SKAdNetwork 전환 값을 해독할 수 있습니다.
      </td>
    </tr>
    <tr>
      <td><span id="d-general-settings"></span>
        일반 설정
      </td>
      <td>
        **파트너 ID-자격 인증**  
        일부 파트너와의 연동을 위해서는 앱스플라이어에 자격 증명 정보를 제공해야 합니다. 해당 ID는 파트너에 따라 앱 ID, 계정 ID, 유저 ID 또는 네트워크 ID 등으로 명칭이 다를 수 있습니다. 이 필드가 표시되면 파트너 대시보드에서 ID를 가져와 필드에 입력하세요.
      </td>
    </tr>
    <tr>
      <td><span id="non-eu-users"></span>
        비 EU 사용자
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/ko/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**비 EU 사용자**</Anchor>를 활성화할지 결정하세요.
      </td>
    </tr>
    <tr>
      <td><span id="e-install-attribution"></span>
        설치 어트리뷰션
      </td>
      <td>
        광고를 보거나 클릭한 사용자의 신규 설치(첫 실행 포함)을 어트리뷰션하기 위한 어트리뷰션 기간을 설정하세요. 어트리뷰션 룩백 윈도우는 광고를 클릭하거나 조회한 순간부터 설치가 파트너에게 측정될 수 있는 최대 시간입니다.

        * **설치 클릭-쓰루 룩백 윈도우:** 앱 클릭 후 설치가 클릭에 어트리뷰션될 수 있는 최대 시간을 설정하세요.

        **인스톨 뷰-쓰루 어트리뷰션: 광고를 봤지만 클릭하지 않은 사용자의 신규 인스톨을 어트리뷰션할 수 있도록 설정하세요.**

        * **인스톨 뷰-쓰루 룩백 윈도우:** 뷰로부터 앱 실행이 설치에 어트리뷰션될 수 있는 최대 시간을 설정하세요.

        <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">룩백 윈도우에 대해 더 알아보기</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="e-re-engagement-attribution"></span>
        리인게이지먼트 어트리뷰션
      </td>
      <td>
        기존 사용자의 리인게이지먼트를 어트리뷰션하기 위해 룩백 윈도우를 켜고 설정하세요. 비 SRN일 경우, 이 설정은 연동 탭 또는 [어트리뷰션 링크](/docs/set-up-an-integrated-partner#리타겟팅-설정) 탭에서 이용할 수 있습니다.

        * **리인게이지먼트 클릭-쓰루 룩백 윈도우:** 클릭 후 앱 실행이 리인게이지먼트로 측정될 수 있는 최대 시간을 설정하세요.

        **리인게이지먼트 뷰-쓰루 어트리뷰션:** 광고를 봤지만 클릭하지 않은 기존 사용자의 리인게이지먼트를 어트리뷰션할 수 있도록 설정하세요.

        * **리인게이지먼트 뷰-쓰루 룩백 윈도우:** 뷰로부터 앱 실행이 리인게이지먼트로 어트리뷰션될 수 있는 최대 시간을 설정하세요.

        <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">룩백 윈도우에 대해 더 알아보기</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="reengagement-window"></span>
        리인게이지먼트 기간
      </td>
      <td>
        리인게이지먼트 전환에 주요하게 기여하는 인앱 이벤트의 시간 범위를 설정합니다. <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide#setup-reengagement-window">더 알아보기</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="ignore-active-users"></span>
        리타게팅 시 활성 사용자 제외
      </td>
      <td>
        지정된 기간 내 활성 사용자에 대한 리타겟팅 전환이 기록되지 않도록 비활성 기간을 설정합니다. <Anchor target="_blank" href="/marketers/ko/docs/set-retargeting-inactivity-window">리타겟팅 비활성 기간</Anchor>에 대해 자세히 알아보세요.

        <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns">**SRN**</Anchor>**의 경우:**

        1. 연동 탭에서 **리인게이지먼트 어트리뷰션**을 켭니다.
        2. **리타겟팅을 위해 활성 사용자 무시**를 켭니다.
        3. **비활성 기간**을 설정합니다.

        **SRN이 아닌 경우:**

        1. 어트리뷰션 링크 탭에서 **리타겟팅 설정**을 켭니다.
        2. **리타겟팅을 위해 활성 사용자 무시**를 켭니다.
        3. **비활성 기간**을 설정합니다.
      </td>
    </tr>
    <tr>
      <td><span id="e-cross-platform-attribution"></span>
        크로스 플랫폼 어트리뷰션
      </td>
      <td>
        **크로스 플랫폼의 동일 어트리뷰션 우선순위**가 활성화되면, 선택한 기간 동안 크로스 플랫폼 노출이 동일한 어트리뷰션 우선순위를 갖습니다.
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-attribution"></span>
        프리로드 어트리뷰션
      </td>
      <td>
        **프리로드 어트리뷰션**이 켜져 있으면, 인스톨이 <Anchor target="_blank" href="/marketers/ko/docs/measure-preload-campaigns-with-google-play-install">프리로드 캠페인</Anchor>에 할당됩니다. 디바이스 활성화 후, 프리로드 인스톨이 파트너에게 귀속되는 기간을 결정하려면 **프리로드 룩백 윈도우**를 설정하세요.
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-equal-attribution-priority"></span>
        프리로드와 동일한 어트리뷰션 우선순위
      </td>
      <td>
        **프리로드 동일 어트리뷰션 우선순위**가 활성화되면, 선택된 룩백 기간 동안의 프리로드 인게이지먼트가 결정적 클릭과 동일한 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#어트리뷰션-메서드">어트리뷰션 우선순위</Anchor>를 갖습니다.
      </td>
    </tr>
    <tr>
      <td><span id="advanced-data-sharing"></span>
        고급 데이터 공유
      </td>
      <td>
        **고급 데이터 공유**가 활성화되면, 추가 데이터가 어트리뷰션 링크를 통해 파트너와 공유됩니다.  
        **참고:** 이 공유 옵션은 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-aggregate-event-measurement-aem-for-ios#aem-데이터-공유">Meta Ads AEM 고급 데이터 공유</Anchor>와는 다릅니다.
      </td>
    </tr>
    <tr>
      <td><span id="default-postbacks"></span>
        기본 포스트백
      </td>
      <td>
        파트너 연동이 켜져 있으면, 앱 실행 전에 발생하는 유저 행동(예: 인스톨, 인스톨 거부, 리인게이지먼트)과 관련된 기본 포스트백이 파트너에게 전송됩니다.

        <div id="01H80XGTBQ4MPGGKSZW0D9GG9H" />

        > 📘 **참고**
        >
        > * 거부된 이벤트는 <Anchor target="_blank" href="/marketers/ko/docs/protect360-anti-fraud-guide">Protect360</Anchor>에 의해 차단되었거나, 타겟 검증 과정에서 기준을 충족하지 못한 인앱 이벤트를 의미합니다. 거부된 이벤트의 경우, 파트너가 앱스플라이어와의 거부 이벤트 연동을 활성화했는지 확인하세요.
        > * 기술 파트너는 인스톨 및 리인게이지먼트에 대한 기본 포스트백을 받을 수 있습니다. 어떤 경우에는 인앱 이벤트 포스트백도 받을 수 있습니다.

        **파트너에 대한 기본 포스트백을 구성하려면**, 포스트백을 보낼 사용자 소스를 정의하세요.

        * **이 파트너만**: 이 이벤트가 해당 파트너에게 할당된 경우에만 포스트백을 전송합니다. 즉, 해당 이벤트를 수행한 사용자가 이 파트너를 통해 유입된 경우를 의미합니다.  
          **참고:** 다음의 경우 기본 포스트백은 항상 **이 파트너만**으로 정의됩니다.
          * 거부된 설치
          * 에이전시([권한](/docs/set-up-an-integrated-partner#에이전시-권한) 포함)
        * **오가닉을 포함한 모든 미디어 소스:** 모든 파트너에게 할당된 이벤트와 오가닉 이벤트에 대해 포스트백을 전송합니다. 즉, 해당 이벤트를 수행한 사용자가 모든 미디어 소스에서 유입된 경우를 뜻합니다.
        * **꺼짐**: 해당 파트너에게 기본 포스트백을 발송하지 않습니다.
      </td>
    </tr>
    <tr>
      <td><span id="g-in-app-event-postback-configuration"></span>
        <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration">인앱 이벤트 포스트백</Anchor>
      </td>
      <td>
        포스트백을 통해 앱스플라이어 이벤트를 파트너 이벤트와 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#이벤트-매핑">매핑</Anchor>합니다. 포스트백 발송이 활성화된 경우, 이는 거부된 인앱 이벤트(Protect360에 의해 차단된 이벤트나 유효성 검증 규칙을 준수하지 않는 것으로 판단된 이벤트)를 포함합니다.

        **인앱 이벤트 포스트백을 구성하려면:**

        1. **파트너 ID**를 설정합니다(필요한 경우).
        2. **인앱 이벤트 포스트백**을 활성화합니다.
        3. 필요한 경우 **인앱 이벤트 포스트백 기간**을 설정합니다(<Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">인앱 이벤트 포스트백 기간 구성</Anchor>에 대해 자세히 알아보세요).
        4. **이벤트 추가**를 클릭하여 SDK 또는 서버-투-서버 이벤트를 목록에 추가합니다.
        5. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#매핑-방법">매핑 방법</Anchor>에 따라 필수 파라미터를 완성하세요.
        6. [선택 사항] <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />를 클릭하여 파트너에게 특정 인앱 이벤트를 전송하기 위한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>합니다.

        | 파라미터 이름 | 설명 |
        | --- | --- |
        | <span id="appsflyer-event"></span>**앱스플라이어 이벤트** | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.  <br />**팁**: 찾고 있는 이벤트가 없나요?<br /><br />* 논오가닉 설치된 디바이스에서 이벤트를 활성화하고 다시 확인하세요.<br />* **앱스플라이어 이벤트**에 입력한 다음 **사용자 지정 생성**을 클릭합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">커스텀 이벤트 매핑</Anchor>에 대해 더 알아보세요. |
        | <span id="mapped-to-partner-event"></span>**파트너 이벤트에 매핑** | 파트너 측에서 정의한 각 이벤트의 고유한 이름 또는 ID입니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#매핑-방법">가능한 매핑 구성</Anchor>은 다음과 같습니다.<br /><br />* **텍스트 필드:** 파트너로부터 해당 이벤트 ID를 받으세요.<br />* **드롭다운 상자:** 가장 적합한 사전 정의된 파트너 이벤트를 선택하세요.<br />* **있는 그대로**: 이벤트 이름을 매핑하지 않고 이벤트를 그대로 보냅니다. |
        | <span id="for-users-from"></span>**사용자에 대한** | 이벤트 전송 옵션을 선택하세요:<br /><br />* **이 파트너만**: 이 파트너에 어트리뷰션된 경우에만 포스트백을 발송합니다. 즉, 이벤트를 실행한 사용자가 이 파트너에서 온 경우입니다.<br />* **오가닉을 포함한 모든 미디어 소스:** 모든 파트너에게 할된 이벤트와 오가닉 이벤트에 대해 포스트백을 전송합니다. 즉, 해당 이벤트를 수행한 사용자가 어느 미디어 소스에서 유입되었는지에 관계없이 포함됩니다. |
        | <span id="including"></span>**포함** | 파트너와 포스트백에서 공유할 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#포스트백에-포함할-데이터">이벤트 데이터를</Anchor> 선택하세요.<br /><br />* **값 없음 및 수익 없음**: 파라미터 없이 이벤트 자체만 발송합니다 (값이나 수익).<br />* **값 있음 및 수익 없음**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.<br />* **값 있음 & 수익 있음**: 수익 값(이벤트에 존재하는 경우)을 **포함하여** 모든 이벤트 파라미터를 발송합니다. |

         비고:

        * 특정 파트너에 대한 연동 탭에서 매핑된 이벤트는 기본 및 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">SKAN 포스트백</Anchor> 모두에 적용됩니다.
        * 포스트백은 파트너에게 실시간으로 발송됩니다.
        * 앱스플라이어 이벤트 이름은 선택할 수도 있고 입력할 수도 있습니다.  
          입력된 값에는 이벤트 이름 앞 또는 뒤에 밑줄이 있는 공백(낯은 대시)을 사용할 수 있습니다. 앱스플라이어에서 전송된 이벤트 이름에 밑줄이 있는 공백이 포함되었다면 그 밑줄을 사용하세요.
        * **중요:** 이벤트 이름은 대소문자를 구분합니다. 차이를 막기 위해 모든 미디어 소스와 앱 버전에 대해 올바른 이벤트 이름을 사용하세요.
        * 연동 탭에 **인앱 이벤트 포스트백** 섹션이 없다면, 파트너가 아직 **앱스플라이어**와의 초기 설정에서 인앱 이벤트 기록을 설정하지 않은 것입니다. 파트너는 <Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">파트너 지원 위젯</Anchor>을 사용하여 앱스플라이어에 연락해 연동을 완료할 수 있습니다.
        * 광고주가 의도치 않게 써드 파티 플랫폼과 너무 많은 정보를 공유하지 않도록, 2019년 3월부터 써드 파티 플랫폼에 대한 **모든 이벤트 발송(제거, 세션, {"af_ad_"}수익 제외)** 옵션을 제거했습니다. 이전에 구성된 써드 파티 플랫폼은 여전히 이 설정 옵션을 유지합니다.

        관련 자료:

        * <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration">인앱 이벤트 포스트백</Anchor> 구성
        * <Anchor target="_blank" href="/marketers/ko/docs/share-ad-revenue-data-with-partners#ad-revenue-event-postbacks-for-ad-networks">광고 수익 이벤트 포스트백</Anchor> 구성
      </td>
    </tr>
    <tr>
      <td><span id="h"></span>
        연동 저장
      </td>
      <td>
        변경 사항을 적용한 후 **연동 저장**을 클릭합니다.
      </td>
    </tr>
    <tr>
      <td><span id="i-connect-more-apps-optional"></span>
        더 많은 앱 연결(선택 사항)
      </td>
      <td>
        연동을 저장한 후 구성 페이지에 남아 있으면 파트너와 더 많은 귀사의 앱을 연동할 수 있습니다.

        1. 왼쪽 상단 모서리에서 파트너 이름 아래에 있는 앱 이름을 클릭하여 앱 목록을 엽니다.
        2. 드롭다운 목록에서 다른 앱을 선택합니다.
        3. 선택한 앱에 대해 연동 단계를 반복합니다.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

클릭(비(非) SRN) 광고 네트워크 사용을 위한 어트리뷰션 링크를 생성하고 저장한 후, 해당 어트리뷰션 링크를 파트너에게 보내 특정 캠페인, 광고 세트 또는 단일 광고를 어트리뷰션합니다.

**참고:** SRN은 광고주가 생성한 어트리뷰션 링크를 구현하지 않으므로 이 탭은 SRN 캠페인에 해당되지 않습니다.

**어트리뷰션 링크를 생성하려면**:

1. **단일 플랫폼 링크 사용** 또는 **원링크 사용**을 선택하세요.

   다음 중 하나라도 해당되는 경우 **단일 플랫폼 링크 사용**을 선택하세요.

   * 앱을 열기 위해 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">URI 스키마</Anchor>만을 사용하려는 경우.
   * URL로 딥링크가 필요하지 않은 경우.

   다음 중 하나라도 해당되는 경우 **원링크 사용**을 선택하세요.

   * 안드로이드와 iOS 앱 모두에 단일 링크가 필요한 경우.
   * 안드로이드 앱 링크나 iOS 유니버설 링크를 사용하여 앱을 열려는 경우.
   * 딥링크 기능이 필요한 경우.

   **참고**: 원링크를 선택하면 앱별 클릭 기록 링크가 <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">원링크 URL</Anchor>로 변경됩니다.
2. **원링크 사용**을 선택한 경우:
   1. 앱을 여는 데 사용할 원링크 템플릿을 선택합니다(그리고 잠재적으로 딥링크 값도 선택합니다).
   2. [선택 사항] **딥링크 값**을 입력하세요.
   3. [선택 사항] **추가 딥링크 값**을 입력하세요.
3. 필요 시 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#android-특정-파라미터">안드로이드</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#ios-전용-파라미터">iOS</Anchor>에 대한 파라미터를 추가하세요.
4. [선택 사항] 추가 어트리뷰션 파라미터를 선택하세요.

<div id="attribution-link-parameters" />

#### 어트리뷰션 링크 파라미터

[![attribution-link-parameters-en_us.png](https://files.readme.io/5f010d760295d53b8ff1891b58aaa57ac8171af7d08d7bc0df07b0998f81f666-4414306787601.png)](https://files.readme.io/5f010d760295d53b8ff1891b58aaa57ac8171af7d08d7bc0df07b0998f81f666-4414306787601.png)

어트리뷰션 링크에 파라미터를 추가하면 철저한 드릴다운 분석이 가능합니다. 이미 정의된 어트리뷰션 링크 파라미터를 여기에서 새 값을 추가하여 편집할 수 있습니다. 어트리뷰션 링크를 저장할 때 이 탭에서 구성된 모든 파라미터가 저장됩니다.

어트리뷰션 링크에 추가할 파라미터를 선택하세요.

<div id="attribution-link-parameters-1" />

#### 어트리뷰션 링크 파라미터

| 이름 | 설명 | 어트리뷰션 링크 파라미터 |
| --- | --- | --- |
| 캠페인 | **필수 파라미터입니다.**  <br />미디어 소스의 운영되는 다양한 캠페인을 비교하세요. | c |
| 광고세트 | 미디어 소스의 특정 캠페인 내 다양한 광고세트를 비교하세요. | af\_adset |
| 광고 이름 | 미디어 소스의 특정 광고세트 내 다양한 크리에이티브를 비교하세요. | af\_ad |
| 사이트 ID 및 하위 사이트 ID | **필수 파라미터입니다.**<br /><br />사이트 ID를 설정하여 특정 퍼블리셔에게 설치를 귀속합니다.<br /><br />사이트 ID는 다음과 같은 이유로 어트리뷰션 링크에서 앱스플라이어로 전달되어야 합니다:<ul><li>퍼블리셔에 대한 명확성과 투명성을 제공합니다</li><li>앱스플라이어는 사기성 퍼블리셔와 기타 트래픽 클러스터를 식별하고 제거하는 데 사용합니다.</li></ul>사이트 ID가 없어도 어트리뷰션에는 영향이 없습니다. <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#site-id-parameter">사이트 ID 파라미터</Anchor>에 대해 더 보기.<br /><br />퍼블리셔가 많은 경우 사용되는 사이트 ID 수를 제한하고 하위 사이트 ID 파라미터를 사용하여 <Anchor target="_blank" href="/marketers/ko/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">사이트 ID</Anchor> 제한을 초과하지 않도록 하는 것이 좋습니다. | af\_siteid 및 af\_sub\_siteid |
| 구독자 파라미터 | 사용 가능한 5개의 구독자 파라미터로 유용한 값을 삽입하세요. 이러한 파라미터는 분석되어 로우 데이터 리포트에 표시됩니다. 그래서 데이터 집계나 필터링에 매우 편리합니다. | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |

새 파라미터 상자에 입력하여 어트리뷰션 링크에 다른 파라미터를 추가할 수 있습니다. 모든 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">앱스플라이어 사용 가능한 URL 파라미터를 사용할 수 있습니다.</Anchor> URI 스킴과 원링크 파라미터만 어트리뷰션 링크에 인코딩된다는 점에 유의하세요.

<div id="retargeting-settings" />

#### 리타겟팅 설정

**리타겟팅이 활성화된 경우**: 앱스플라이어는 을 어트리뷰션 링크에 추가하여 사용자 유입 링크가 아닌 <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">리타겟팅</Anchor> 어트리뷰션 링크로 인식합니다.  
**어트리뷰션 링크 파라미터:** is\_retargeting

리타겟팅에 귀사의 링크를 사용하려면:

1. **리타겟팅 설정**을 켜세요.
2. [선택사항] 앱을 열기 위한 URI 스킴을 원하는 경우 URI 스킴을 입력하십시오.   
   **참고**:
   * URI 스킴은 유니버설 링크나 앱 링크가 실패할 경우 앱을 여는 대체 방법으로 권장됩니다.
   * 여기에 URI 스킴을 추가하면 귀사의 원링크 템플릿 설정에 이미 있는 다른 URI 스킴이 무시됩니다.
   * URI 스킴이 af\_dp 파라미터의 링크에 추가됩니다.
3. [선택 사항] **리타겟팅에 활성 사용자 무시** 기능을 켜세요.
4. 비활성 기간을 설정하여 어떤 사용자가 활성 사용자이고, 어떤 사용자가 비활성 사용자인지 판단합니다.
5. 리인게이지먼트 이후 사용자의 인앱 이벤트가 리타겟팅 미디어 소스로 어트리뷰션되는 기간을 설정하여 판단합니다.
   * 값은 일(1&#126;90), 시간(최대 23시간) 또는 수명 단위로 설정할 수 있습니다.
   * 리인게이지먼트 기간이 af\_reengagement\_window 파라미터의 링크에 추가됩니다.

<div id="click-through-attribution" />

#### 클릭-쓰루 어트리뷰션

설정을 사용하여 **클릭부터 설치까지의 최대 시간**을 설정하세요. 룩백 윈도우 내에 발생한 설치(첫 실행)만 어트리뷰션 됩니다.

허용 범위: 1&#126;23시간 또는 1&#126;30일.

**어트리뷰션 링크 파라미터:** af\_click\_lookback

<Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">클릭 룩백 윈도우</Anchor>에 대해 더 알아보기.

**클릭 어트리뷰션 링크**

[![click-through-attribution-link_en-us.png](https://files.readme.io/aba15af3164c4f233625cd56f90aa4d1a18b834cfb151c4e7042fa099c8f9125-4411038599953.png)](https://files.readme.io/aba15af3164c4f233625cd56f90aa4d1a18b834cfb151c4e7042fa099c8f9125-4411038599953.png)

이 링크는 설정한 모든 구성 정보를 포함하는 어트리뷰션 링크입니다. 나중에 참조할 수 있도록 **어트리뷰션 링크 저장**을 클릭하십시오.

**클릭 어트리뷰션 링크를 복사하려면:**

1. **어트리뷰션 링크 저장**을 클릭하세요.
2. 생성된 링크를 복사합니다.

귀사의 잠재 고객이 해당 광고를 클릭하면 활성화되도록 파트너에게 링크를 발송합니다.

<div id="view-through-attribution-lookback-window" />

#### 뷰-쓰루 어트리뷰션 룩백 윈도우

**노출부터 설치까지의 최대 시간**을 설정합니다. 광고 노출 후 다른 관련 광고 클릭이 없는 경우에 한해 이 룩백 윈도우 내에 발생하는 설치(첫 실행)만 파트너에게 어트리뷰션됩니다.

이 값을 1&#126;24시간으로 사용자 정의할 수 있습니다.

**어트리뷰션 링크 변수:** af\_viewthrough\_lookback

<Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">뷰-쓰루 어트리뷰션</Anchor>에 대해 더 알아보세요.

**노출수 어트리뷰션 링크**

[![impressions-attribution-link_en-us.png](https://files.readme.io/76a2d084f66f3a279b281f60a465af5098e05de8de128cfd6f04a97fe52c4dc6-4411047429265.png)](https://files.readme.io/76a2d084f66f3a279b281f60a465af5098e05de8de128cfd6f04a97fe52c4dc6-4411047429265.png)

노출 어트리뷰션 링크는 다른 룩백 윈도우를 제외하고 클릭 기록 링크와 유사한 어트리뷰션 데이터를 포함합니다. 나중에 참조할 수 있도록 **어트리뷰션 링크 저장**을 클릭하십시오.

어트리뷰션 링크 저장을 클릭하고 생성된 링크를 복사합니다.

**노출 어트리뷰션 링크를 복사하려면:**

1. **어트리뷰션 링크 저장**을 클릭하세요.
2. 생성된 링크를 복사합니다.

일반적으로 1초 이상 광고가 노출되면 활성화되도록 파트너에게 발송합니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

* 비용 데이터는 연동된 파트너에 의해 클릭 시점에 또는 비용 API를 통해 보고됩니다.
* 가장 좋은 방법은 비용 API를 구현하는 것입니다.(ROI360 구독 필요)
* 비용 API에는 클릭수 및 노출수 리포트가 포함되어 있습니다. 지원되는 디멘션, 지표 및 기능에 대한 세부 정보는 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">애드 네트워크 비용 연동 표</Anchor>를 참조하세요.

<div id="note-2" />

> 📘 **참고**
>
> 광고주가 대행사를 통해 캠페인을 실행하는 경우, 광고주가 아닌 대행사가 관련 파트너와 연동해야 합니다. 그렇지 않으면 광고주와 대행사가 동일한 앱에 대해 동일한 자격 증명을 사용하여 파트너와 연동하면 비용 데이터가 중복됩니다.

<div id="enabling-cost-data-by-api" />

#### API를 통한 비용 데이터 활성화

**비용 API**를 활성화하려면:

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">이 연동 지침</Anchor>을 따르세요.

<div id="cost-data-sync-status" />

#### 비용 데이터 동기화 상태

비용(및 광고 수익) 연동 상태 대시보드 또는 각 애드 네트워크별 대시보드에서 <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">비용 API 상태</Anchor>와 앱스플라이어가 마지막으로 일치하는 비용 데이터를 불러온 시점을 확인할 수 있습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

귀사가 앱에 광고를 게재하는 퍼블리셔로 활동 중인 경우, 광고 수익 기능을 이용하여 사용자를 데려온 미디어 소스에 광고 수익을 귀속할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution">광고 수익 어트리뷰션에 대해서</Anchor>

<div id="enable-ad-revenue-attribution" />

#### 광고 수익 어트리뷰션 활성화

1. 파트너가 지원하는 메서드를 확인하세요. (<Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#list-of-ad-revenue-integrated-partners">집계 또는 사용자 수준 어트리뷰션</Anchor>)
2. <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#구현하기">광고 수익 연동 가이드</Anchor>에 따라 적절한 방법을 따르세요.

<div id="ad-revenue-api-status-messages" />

#### 광고 수익 API 상태 메시지

| 상태 | 비고/필요한 조치 |
| --- | --- |
| 활성화됨 | 연결이 활성화되어 데이터를 가져오고 있습니다. |
| 가져올 데이터를 찾을 수 없습니다. | 연결이 성공적이었습니다. 파트너는 이 앱과 관련된 데이터를 보유하고 있지 않습니다. |
| 파트너 API가 응답하지 않습니다. 앱스플라이어 지원팀에 문의하세요. | 파트너의 서버가 앱스플라이어에 응답하지 않습니다. |
| 잘못된 자격 증명입니다. 업데이트된 자격 증명을 입력하세요. |  |
| 문제가 발생했습니다. 앱스플라이어 지원팀에 문의하세요. | 기술적 문제가 발생했습니다. |
| 파트너 데이터가 아직 준비되지 않았습니다. 문제가 지속되면 앱스플라이어 지원팀에 문의하세요. |  |
| 데이터가 처리 중이며 곧 제공될 예정입니다. | 현재 파트너로부터 받은 데이터를 처리 중입니다. 해당 데이터는 대시보드와 보고서에서 확인할 수 있습니다. |
| 데이터를 성공적으로 가져오지 못했습니다. | 이 상태가 한 시간 이상 지속되면 앱스플라이어 지원팀에 문의하세요. |

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

애드 네트워크와 대행사에 귀사의 데이터에 액세스하고 다양한 작업을 수행할 수 있는 특정 권한을 부여하세요.

* 파트너와의 연동이 켜져 있지 않아도 해당 파트너에게 권한을 부여할 수 있습니다.
* **대행사가 설정한 애드 네트워크:** 대행사가 파트너 설정을 수행하는 경우, 광고주는 애드 네트워크 활성화 상태나 부여된 권한을 볼 수 없습니다.
* 파트너와의 관계가 귀사의 대행사로서의 역할만 있는 경우 **대행사 권한**을 사용하고, **애드 네트워크 권한**은 사용하지 마세요. 대행사 권한 토글을 활성화하면 대행사가 광고 네트워크 권한을 제어할 수 있도록 허용하게 됩니다. 자세한 내용은 <Anchor target="_blank" href="/partners/ko/docs/getting-started-agency-onboarding#이것은-마케터로부터-권한을-부여받는다는-것을-의미합니다">마케터 권한 승인의 의미</Anchor> 노트를 참고하세요.
* 현재 선택된 앱에 대한 권한이 부여됩니다.

<div id="ad-network-permissions" />

#### 애드 네트워크 권한

**애드 네트워크 권한**을 켜면 애드 네트워크가 귀사의 대시보드에 접근할 수 있으며, 아래 표에 자세히 설명된 추가 권한을 부여할 수 있습니다.

<div id="note-3" />

> 📘 **참고**
>
> 모든 액세스 권한은 애드 네트워크가 소유한 데이터로 제한됩니다.

**애드 네트워크와 팀원에게 권한을 부여하려면:**

1. **애드 네트워크 권한**을 켜세요.

   * 귀사의 앱이 애드 네트워크의 대시보드에 나타납니다.
   * 애드 네트워크 관리자는 <Anchor target="_blank" href="/marketers/ko/docs/manage-data-access-permissions">앱에 대한 기본 데이터를 볼 수 있는 권한이 있습니다.</Anchor>

   **참고:** 광고 네트워크 팀원 계정은 해당 광고 네트워크에서 직접 관리합니다. 특정 팀원에게 액세스 권한을 부여하려면 해당 광고 네트워크에 문의하세요. <Anchor target="_blank" href="/partners/ko/docs/user-management-for-ad-networks#사용자-생성">더 알아보기</Anchor>
2. 애드 네트워크에 부여할 추가 권한을 선택하세요.

| **권한** | **기능 부여됨** |
| --- | --- |
| <span id="configure-integration"></span>연동 설정 | 인앱 이벤트 포스트백 구성을 제외하고, 애드 네트워크는 연동 탭에서 파라미터를 변경할 수 있습니다. |
| <span id="configure-inapp-event-postbacks"></span>인앱 이벤트 포스트백 구성 | 애드 네트워크는 인앱 이벤트 포스트백을 구성할 수 있습니다. 즉, 애드 네트워크는 포스트백 설정을 생성, 정의(맵핑), 변경할 수 있습니다.<br /><br />**주의**! 이 권한과 연동 구성 권한이 동시에 활성화되면, 애드 네트워크는 모든 이벤트에 접근할 수 있습니다. 여기에는 모든 미디어소스의 오가닉 트래픽과 논오가닉 트래픽이 포함됩니다. |
| <span id="access-retention-report"></span>리텐션 및 코호트 리포트 접근 | 에이전시는 자사 유입 사용자로부터 생성된 리텐션/코호트 데이터에만 접근할 수 있습니다. |
| <span id="access-aggregate-loyal-users-data"></span>집약형 충성도 사용자 데이터 접근 | 애드 네트워크는 자체 <Anchor target="_blank" href="/marketers/ko/docs/about-a-loyal-user">충성 사용자</Anchor> 지표에 접근할 수 있습니다. |
| <span id="access-aggregate-conversions-data"></span>집약형 전환 데이터 접근 | 애드 네트워크는 집약형 전환 이벤트 지표 리포트에 접근할 수 있습니다. 여기에는 인스톨, 리인게이지먼트, 재설치, 리어트리뷰션이 포함됩니다. 예시: <Anchor target="_blank" href="/partners/ko/docs/aggregated-campaign-performance-report-for-ad-networks">애드 네트워크 리포트를 위한 집약형 캠페인 성과</Anchor>. |
| <span id="access-aggregate-inapp-events-data"></span>집약형 인앱 이벤트 데이터 접근 | 애드 네트워크는 다음을 수행할 수 있습니다.<ul><li>인앱 이벤트 데이터 집약형 리포트에 접근. Protect360 인앱 이벤트 데이터를 포함하여 선택한 앱의 모든 인앱 이벤트 데이터에 접근할 수 있습니다. 즉, 포스트백 구성에 매핑된 이벤트뿐만 아니라 다른 이벤트에도 액세스할 수 있습니다.</li><li>다른 매체 소스의 광고 수익화 이벤트를 포함할 수 있는 광고 수익화 데이터 집계 보고서에 액세스합니다.</li></ul> |
| <span id="view-validation-rules"></span>유효성 검증 규칙 보기 | 애드 네트워크는 <Anchor target="_blank" href="/marketers/ko/docs/implement-validation-rules-to-prevent-fraud">유효성 검증 규칙</Anchor>의 세부 정보를 조회할 수 있습니다. |
| <span id="access-aggregate-revenue-data"></span>집약형 수익 데이터 접근 | 애드 네트워크는 해당 네트워크의 유입 사용자에게 기여도가 할당된 인앱 및 광고 수익 데이터의 집약 리포트에 접근할 수 있습니다. **참고:** 이 권한은 광고 수익 파트너를 직접적으로 식별하지 않습니다. 그러나 수익화 이벤트 이름에 파트너 이름을 포함하도록 설정한 경우, 실수로 수익화 네트워크의 신원을 공개할 수 있습니다. |
| <span id="use-ad-spend-ingestion"></span>광고 지출 데이터 수집 사용 | 애드 네트워크는 다음을 수행할 수 있습니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/import-cost-data">광고 지출 데이터 수집</Anchor>  창에 접근. 해당 창에서는 권한이 있는 앱만 표시됩니다.</li><li>데이터 수집을 위해 광고 지출 파일 전송.</li></ul> |
| <span id="access-protect360-dashboard-raw-data"></span>Protect360 대시보드 및 로데이터에 접근 | 애드 네트워크는 다음을 수행할 수 있습니다:<ul><li>Protect360 대시보드에 액세스합니다 (<Anchor target="_blank" href="/marketers/ko/docs/basic-fraud-detection-and-insights-with-protectlite-dashboard-and-reporting">ProtectLITE</Anchor> 포함).</li><li>구독 플랜에 포함되어 있는 경우 Protect360, 유효성 검증 규칙, 로데이터에 접근 가능합니다. ProtectLITE에는 로데이터에 대한 접근 권한이 포함되지 않습니다.</li></ul>**참고:** <Anchor target="_blank" href="/marketers/ko/docs/protect360-anti-fraud-guide"> Protect360</Anchor>에 구독되어 있으면, 애드 네트워크가 전체 대시보드를 조회할 수 있습니다. Protect360 구독이 없으면 LITE 대시보드를 볼 수 있습니다. |
| <span id="access-ad-revenue-raw-data"></span>광고 수익 로데이터 접근 | 애드 네트워크는 <Anchor target="_blank" href="/partners/ko/docs/ad-revenue-signals-for-ua-ad-networks"> UA 최적화에 사용할 광고 수익 데이터</Anchor>에 접근할 수 있습니다.  <br />**참고:** 이 권한은 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor> 구독이 있는 앱에서만 사용할 수 있습니다. |

<div id="agency-permissions" />

#### 에이전시 권한

대행사가 권한을 받았을 때 <Anchor target="_blank" href="/partners/ko/docs/getting-started-agency-onboarding#이것은-마케터로부터-권한을-부여받는다는-것을-의미합니다">무엇을 할 수 있는지</Anchor> 자세히 알아보세요.

<div id="important-1" />

> 🚧 **중요!**
>
> 대행사와 협업할 때 통합 파트너를 비활성화해도 해당 파트너에 연결된 대행사에 대한 특정 기여도 분석 기능이 자동으로 비활성화되지는 않습니다.
>
> 대행사에 대한 이러한 기능을 완전히 비활성화하려면 광고주는 파트너를 비활성화하기 전에 다음 설정을 수동으로 해제해야 합니다.
>
> 1. 설치 뷰-쓰루 어트리뷰션
> 2. 플랫폼 간 동등한 어트리뷰션 우선순위
>
> 광고주는 이러한 토글 기능을 비활성화한 후에만 파트너를 비활성화해야 합니다.
>
> **참고:** 광고주가 이러한 설정을 먼저 해제하지 않고 파트너를 비활성화하면 대행사는 이러한 기여도 분석 기능을 계속 사용할 수 있습니다.

**주의:** 제어가 비활성화된 동안 발생한 대행사 설치는 대행사에 귀속되지 않으며, 대행사의 대시보드와 데이터에 나타나지 않습니다. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation#에이전시-권한">대행사 활성화</Anchor>에 대해 더 보기.

**대행사에 권한을 부여하려면:**

1. **대행사 권한**을 켜세요.
2. 대행사에 부여할 권한을 선택하세요:

| **권한** | **기능 부여됨** |
| --- | --- |
| <span id="change-advanced-privacy-configuration"></span>프라이버시 강화 모드 설정 변경 | 에이전시는 애드 네트워크의 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">프라이버시 강화 모드 데이터 공유</Anchor> 설정을 변경할 수 있습니다.   <br />**참고:** 이 권한은 TikTok for Business와 Snapchat에는 적용되지 않습니다. 이와 같은 연동의 경우, 프라이버시 강화 모드 설정은 회색으로 비활성화되어 있으며, 이는 광고주의 설정을 반영한 것입니다. |
| <span id="access-retention-and-cohort-reports"></span>리텐션 및 코호트 리포트 접근 | 에이전시는 자사 유입 사용자로부터 생성된 리텐션/코호트 데이터에만 접근할 수 있습니다. |
| <span id="access-aggregate-organic-data"></span>집약형 오가닉 데이터 접근 | 에이전시는 집약형 오가닉 데이터에 접근할 수 있습니다. |
| <span id="view-validation-rules::6872643b"></span>유효성 검증 규칙 보기 | 에이전시는 유효성 검증 규칙의 세부 정보를 확인할 수 있습니다. |
| <span id="add-validation-rules"></span>유효성 검증 규칙 추가 | 에이전시는 유효성 검증 규칙을 추가하고 편집할 수 있습니다. **유효성 검증 규칙 보기**가 켜져 있으면 사용할 수 있습니다.   <br />**참고**: 대행사는 광고주가 만든 규칙을 편집할 수 없습니다. |
| <span id="access-rawdata-reports"></span>로데이터 리포트 접근 | 에이전시는 에이전시에 기여도가 할당된 트래픽에 대한 로데이터 보고서에 접근할 수 있습니다. 광고주는 에이전시가 리포트에서 볼 수 있는 이벤트를 제한할 수 없습니다. |
| <span id="access-protect360-dashboard-raw-data::dd9829fd"></span>Protect360 대시보드 및 로데이터에 접근 | 에이전시는 다음을 수행할 수 있습니다.<ul><li>귀사의 Protect360 집약형 대시보드에 접근</li><li>Protect360, 검증 규칙 및 로데이터(구독 플랜의 일부인 경우)에 접근</li></ul>**참고:** 광고주가 에이전시를 통해 애드 네트워크와 협업하는 경우, 애드 네트워크와 에이전시 모두가 데이터에 접근할 수 있도록 하려면, 광고주는 앱스플라이어에서 에이전시와 애드 네트워크를 모두 연동하고, 각각에 데이터 접근 권한을 부여해야 합니다. 에이전시만 연동하고 권한을 부여하면 애드 네트워크가 데이터에 접근할 수 없습니다. |
| <span id="configure-inapp-event-postbacks::8743ba60"></span>인앱 이벤트 포스트백 구성 | 대행사는 귀사가 선택한 특정 이벤트의 인앱 이벤트 포스트백을 구성할 수 있습니다.<ul><li>**이벤트 추가:** 드롭다운 메뉴에서 대행사에게 권한을 부여할 이벤트를 선택하세요.</li></ul>선택한 이벤트에 다음 옵션이 적용됩니다.<ul><li>**이벤트 수익 발송:** 이 기능을 활성화하면 대행사는 통화 가치를 포함하여 이벤트 발송을 구성할 수 있습니다.</li><li>**보내기 옵션:**<ul><li>**이 파트너만 해당:** 선택 시, 대행사는 자사에서 발생한 트래픽에 어트리뷰션된 이벤트에 대해서만 포스트백을 발송하도록 구성할 수 있습니다.</li><li>**오가닉을 포함한 모든 매체 소스:** 선택 시, 대행사는 모든 다른 매체 소스, 대행사 및 오가닉 사용자에게 어트리뷰션된 이벤트에 대한 포스트백 발송을 구성할 수 있습니다.</li></ul></li></ul> |

대행업체와의 협력에 대해 <Anchor target="_blank" href="/partners/ko/docs/about-agency-accounts#마케터-데이터에-대한-에이전시-액세스">더 보기</Anchor>.

</Accordion>

<div id="test-the-integration" />

## 연동을 시험합니다.

파트너 연동을 완료한 후 새로 추가된 파트너와  캠페인을 운영하기 전에 연동을 시험하는 것이 중요합니다. 설정 중에 실수가 발생하기 쉽습니다. 사전에 테스트를 진행하면, 어트리뷰션 데이터의 누락이나 오류로 인해 리소스가 낭비되는 상황을 방지할 수 있습니다.

<div id="note-4" />

> 📘 **참고**
>
> 연동을 테스트하기 전에, 오가닉 인스톨과 논오가닉 인스톨을 포함한 <Anchor target="_blank" href="/marketers/ko/docs/testing-the-sdk-integration-for-marketers">기본 SDK 연동이 정상적으로 이루어졌는지 먼저 앱을 테스트</Anchor>하세요.

<div id="test-the-attribution-link-for-nonsrns" />

<Accordion title="비 SRN 어트리뷰션 링크 테스트">

통합 애드 네트워크의 99.5%를 차지하는 비 SRN 애드 네트워크는 앱스플라이어 어트리뷰션 링크를 사용합니다. 마찬가지로, 온드 미디어 어트리뷰션은 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">원링크</Anchor> 링크를 사용하여 수행됩니다.

올바른 어트리뷰션은 어트리뷰션 링크의 파라미터에 달려 있으므로, 비 SRN 애드 네트워크나 커스텀 어트리뷰션 링크와 함께 캠페인을 실행하기 전에 이러한 링크를 시험하세요.

**어트리뷰션 링크 시험 방법:**

1. [어트리뷰션 링크](/docs/set-up-an-integrated-partner#attribution-link-tab)를 만듭니다.
2. 새로운 어트리뷰션 링크를 귀사의 <Anchor target="_blank" href="/marketers/ko/docs/registering-test-devices">등록된</Anchor> 시험 디바이스로 발송합니다(이메일이나 QR 코드를 통해).
3. 링크를 클릭하여 앱 스토어로 리디렉션되는지 확인하세요.
4. 앱을 설치하세요.
5. 앱을 실행하세요.
6. 해당 인스톨이 파트너의 미디어 소스 이름으로 앱스플라이어 대시보드에 표시되는지 확인하세요. 대시보드에 설치가 나타날 때까지 최대 30분이 소요됩니다.
7. 개요 페이지 상단에 있는 **미디어 소스 필터**에서 파트너를 선택해 캠페인 수준으로 드릴다운한 후, 인스톨이 올바른 캠페인 이름 아래에 표시되는지 확인하세요.
8. 필요하다면 계속해서 애드셋과 개별 광고 수준도 확인하세요.

</Accordion>

<div id="test-the-srn-integration" />

<Accordion title="SRN 연동 시험">

Meta ads, Apple Ads, Google Ads와 같은 SRN은 어트리뷰션을 진행할 때 외부 어트리뷰션 링크에 의존하지 않습니다. 대신, SRN은 앱스플라이어로부터 쿼리를 받고, 자체적으로 어트리뷰션을 한 후 결과를 반환합니다. 따라서 일반 광고 네트워크와 달리 네트워크 시스템과 별도로 연동 시험하는 것은 불가능합니다. 사용하는 각 SRN에 대해 연동을 별도로 시험해야 합니다.

**SRN 연동을 시험하려면**[:](/docs/set-up-an-integrated-partner)

1. 앱스플라이어에서 <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#앱스플라이어와-통합된-srn">특정 SRN 설정 가이드</Anchor>에 따라 전체 SRN 설정을 수행합니다.
2. SRN 파트너와 함께 새로운 저예산 캠페인을 운영하세요.
3. 파트너 대시보드에 새로운 설치가 표시되면, 앱스플라이어 대시보드의 파트너 미디어 소스 이름 아래에 나타나는지 확인하세요.
4. 개요 대시보드에서 **미디어 소스 필터**에서 파트너를 선택하여 캠페인 수준까지 드릴다운하여 인스톨이 올바른 캠페인 이름 아래에 표시되는지 확인합니다. 대시보드에 설치가 나타날 때까지 최대 30분이 소요됩니다.
5. 필요한 경우 계속해서 애드셋과 개별 광고 수준까지 드릴다운하여 확인하세요.

모든 것이 잘되면 파트너와 함께 새로운 고예산 캠페인을 운영할 수 있습니다. SRN 파트너당 연동 시험은 한 번만 하면 됩니다. 즉, 캠페인 별로 시험할 필요는 없습니다.

</Accordion>

<div id="test-the-raw-data" />

<Accordion title="로우 데이터 시험">

앱스플라이어와의 플랜에 로우 데이터 액세스가 포함되어 있는 경우, 로우 데이터를 시험해야 합니다.

**로우 데이터를 시험하려면**:

1. 이전에 언급한 시험을 수행한 후 **보고서** > <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">**데이터 내보내기**</Anchor>로 이동합니다.
2. 시험한 미디어 소스를 선택하세요.
3. 설치 후 최대 15분이 소요될 수 있으며, 그런 다음 설치 리포트를 다운로드하세요.
4. 파트너 설치 기록이 있는지 확인하고 미디어 소스, 캠페인 이름, 터치 시간 및 유형, 디바이스 ID(해당되는 경우), 대행사 이름(리포트에서는 "파트너"라고 함) 등의 파라미터가 포함되어 있는지 확인하세요.

<div id="important-2" />

> 🚧 **중요!**
>
> 일부 애드 네트워크는 원시 사용자 수준 데이터를 수집하기 위해 특별한 작업이 필요합니다.
>
> 대시보드에는 새로운 설치가 표시되지만 원시 데이터에서는 확인되지 않는 경우, 해당 광고 네트워크의 전용 헬프센터 가이드(예: <Anchor target="_blank" href="/marketers/ko/docs/x-ads-formerly-twitter-ads-faq-and-discrepancies#do-you-make-twitters-raw-data-available-to-agencies">X Ads</Anchor>)를 참조하세요.

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 01H80XGTBQ6MAK3VG0X6QMAYMP=%EA%B0%9C%EC%9A%94 01H80XGTBQPPZV7WR5JBHQFB0B=partner-types-in-the-ecosystem 01H80XGTBQ4CPMBRVSMM7TD4VD=partners-in-the-marketplace invite-new-partners-to-appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90-%EC%83%88%EB%A1%9C%EC%9A%B4-%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%B4%88%EB%8C%80 01H80XGTBQRJ78XCGNZBTJVYEQ=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90-%EC%83%88%EB%A1%9C%EC%9A%B4-%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%B4%88%EB%8C%80 01H80XGTBQ8VF6V9WARZRECWVR=your-integrated-partners 01H80XGTBQJQYD3R46H95WVVM0=%EC%B0%B8%EA%B3%A0 01H80XGTBQ5BE24X219BVZBMDG=about-the-integrated-partner-page applicable-settings-tabs-per-partner-type=%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%9C%A0%ED%98%95%EB%B3%84-%EC%A0%81%EC%9A%A9-%EA%B0%80%EB%8A%A5%ED%95%9C-%EC%84%A4%EC%A0%95-%ED%83%AD 01H80XGTBQPP74G38YNNYVXWP2=%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%9C%A0%ED%98%95%EB%B3%84-%EC%A0%81%EC%9A%A9-%EA%B0%80%EB%8A%A5%ED%95%9C-%EC%84%A4%EC%A0%95-%ED%83%AD set-up-a-partner-nonsrn=%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%84%A4%EC%A0%95%EB%B9%84-srn 01H80XGTBQXNQ7SFXZ5PBQGS1V=%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%84%A4%EC%A0%95%EB%B9%84-srn 01JDM949M75Q3BAG6M65DYMHZT=%EC%A4%91%EC%9A%94 01H80XGTBQZXZARZCM61CMG0K3=%EC%B0%B8%EA%B3%A0-1 01H80XGTBQB9T22GQ7CSHS2S1X=integration-tab integration-tab-sections=%EC%97%B0%EB%8F%99-%EC%84%B9%EC%85%98 01H80XGTBQ0531M2RS3DH7E4Z0=%EC%97%B0%EB%8F%99-%EC%84%B9%EC%85%98 d-general%20settings=d-general-settings default%20postbacks=default-postbacks 01H80XGTBQ4MPGGKSZW0D9GG9H=%EC%B0%B8%EA%B3%A0-2 01H80XGTBRT41FGP5107G96TWC=attribution-link-tab attribution-link-parameters=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 01H80XGTBRPENCTCRK8PPYSCGX=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 attribution-link-parameters::3874dfb8=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-1 01H80XGTBR8630SEV80K9RD6V9=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-1 retargeting-settings=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%84%A4%EC%A0%95 01H80XGTBRT57QMPRENYSS81Z3=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%84%A4%EC%A0%95 clickthrough-attribution=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H80XGTBREZTJ6B0Y08JCKN1E=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 viewthrough-attribution-lookback-window=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 01H80XGTBRXC1YYX4FW94NDR2Z=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 01H80XGTBRERTJ9XHGDV416T7V=cost-tab 01H80XGTBR54TQ0DNY1JR36GXN=%EC%B0%B8%EA%B3%A0-3 enabling-cost-data-by-api=api%EB%A5%BC-%ED%86%B5%ED%95%9C-%EB%B9%84%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%99%9C%EC%84%B1%ED%99%94 01H80XGTBRV6BHWS76HWHK933M=api%EB%A5%BC-%ED%86%B5%ED%95%9C-%EB%B9%84%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%99%9C%EC%84%B1%ED%99%94 cost-data-sync-status=%EB%B9%84%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%8F%99%EA%B8%B0%ED%99%94-%EC%83%81%ED%83%9C 01H80XGTBRPWREFYFXA0A6VD47=%EB%B9%84%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%8F%99%EA%B8%B0%ED%99%94-%EC%83%81%ED%83%9C 01H80XGTBRJ1AKX2Q7WPXFVA49=ad-revenue-tab enable-ad-revenue-attribution=%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%99%9C%EC%84%B1%ED%99%94 01H80XGTBRHE9PPRA9X46M4TGZ=%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%99%9C%EC%84%B1%ED%99%94 ad-revenue-api-status-messages=%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-api-%EC%83%81%ED%83%9C-%EB%A9%94%EC%8B%9C%EC%A7%80 01H80XGTBRNT4K4ZNPKVV25ESJ=%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-api-%EC%83%81%ED%83%9C-%EB%A9%94%EC%8B%9C%EC%A7%80 01H80XGTBRGXS97JMG45QR4BEQ=permissions-tab ad-network-permissions=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C 01H80XGTBRS9BTT2F8F95BCE9Z=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C h_01HGFD78GRX9P2G58W21QZN4X7=%EC%B0%B8%EA%B3%A0-4 agency-permissions=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EA%B6%8C%ED%95%9C 01H80XGTBRTVP407AAA77N090E=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EA%B6%8C%ED%95%9C h_01KC9MDDRPTB05PV6NCGZVFRMJ=%EC%A4%91%EC%9A%94-1 test-the-integration=%EC%97%B0%EB%8F%99%EC%9D%84-%EC%8B%9C%ED%97%98%ED%95%A9%EB%8B%88%EB%8B%A4 01H80XGTBSEWPHCPQF29XD6Y4W=%EC%97%B0%EB%8F%99%EC%9D%84-%EC%8B%9C%ED%97%98%ED%95%A9%EB%8B%88%EB%8B%A4 01H80XGTBSTHG2FC2M31F83RGK=%EC%B0%B8%EA%B3%A0-5 01H80XGTBS4P06757QXHDKYAHT=test-the-attribution-link-for-nonsrns 01H80XGTBS2K9SPQ1MTAV7GP2H=test-the-srn-integration 01H80XGTBSTBV4RC3V279WNNB1=test-the-raw-data 01H80XGTBSN0VAX76XW9Y77T04=%EC%A4%91%EC%9A%94-2" />
