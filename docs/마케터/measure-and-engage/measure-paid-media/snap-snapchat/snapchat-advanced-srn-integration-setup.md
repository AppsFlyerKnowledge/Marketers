---
title: 스냅챗—고급 SRN 연동 설정
metadata:
  keywords:
    - configuration
    - snapchat measurement partner
    - snapchat
    - measurement
    - snapchat measurement analytics
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-06-13T12:28:59Z'
  edited_at: '2026-10-14T10:40:22Z'
  id: 211011983
  locale: ko
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/ko/articles/211011983
---
> **한눈에 보기:** 2023년 9월 중순부터 스냅챗은 고급 SRN이 되었습니다. 앱스플라이어와 스냅챗 간 연동을 설정하여 어트리뷰션 측정을 활성화하는 방법을 알아보세요.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/snapchat.png?v=1" width="52px" />

## 개요

고급 SRN 연동은 모든 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-knowledge-base-glossary?query=glossar#dual-consent">양자 동의된</Anchor> 트래픽이 일반 SRN 트래픽으로 어트리뷰션되고 리포팅된다는 것을 의미합니다. 동의하지 않은 트래픽의 경우 앱스플라이어는 개인정보 보호 제한에 따라 <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#고급-srn의-어트리뷰션은-어떻게-작동합니까">다른 어트리뷰션 방법</Anchor>을 사용하여 스냅챗에서 발생하는 클릭 및 노출을 기반으로 어트리뷰션을 지정하고 측정할 수 있습니다.

## 스냅챗 연동 설정

**전제 조건:** 연동을 설정하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. **활성화 방법:** 앱스플라이어에서, 측면 메뉴에서 **협업** > **파트너 마켓플레이스**를 선택하세요.  
   **편집 방법**: 앱스플라이어의 측면 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. **스냅챗**을 검색하여 선택하세요.
3. **연동 설정**을 클릭합니다. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.  
   **참고:** 파트너와 협력하는 동안 토글은 반드시 켜져<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화)</Anchor> 있어야 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

파트너 구성 창 헤더에 대한 자세한 설명을 보려면 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하세요.

> 📘 **참고**
>
> * 일부 설정은 iOS와 안드로이드 기기마다 다릅니다.
> * <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner">파트너 연동 설정</Anchor>에 대해 더 알아보세요.

<div id="integration-tab" />

<Accordion title="연동 탭">

연동은 클릭 및 노출 어트리뷰션, 비용, 광고 수익 및 잠재고객을 지원합니다.

#### 파트너 활성화

**처음 방문** 시 설정을 활성화하려면 **파트너 활성화**를 켜야 합니다.  
파트너 활성화에 대한 자세한 내용을 보려면 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

**어트리뷰션 활성화**

**파트너 활성화**를 활성화하여 스냅챗에 대한 어트리뷰션을 허용합니다.

![mceclip0.png](https://files.readme.io/cf4e73fec951e4e9d2c1919ca20adff88fc0d49d7fea9b033ab9c39194ce2702-360003259638.png)

#### 일반 설정

**Snap 앱 ID**

1. Snap 비즈니스 관리자에서 앱으로 이동하여 Snap 앱 ID를 복사합니다( <Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/a/snap-app-id">Snap 앱 ID를 생성하는 방법</Anchor>에 대한 스냅챗 가이드 참조).
2. 앱스플라이어의 Snap 앱 ID 필드에 ID를 붙여넣습니다.

![snapchat-app-id.png](https://files.readme.io/2e5f53240893e2a80ba36065f67f4504f69e1167d96ef35bd7a4ab874d5a7bb9-360008280878.png)

**에이전시에서 앱을 홍보하는 경우**,

* Snap 앱 ID는 광고주만 추가할 수 있습니다.
* 에이전시가 스냅챗 광고 플랫폼에서 귀하와 동일한 조직에 속해 있는 경우 하나의 Snap 앱 ID만 사용하십시오.
* 에이전시가 스냅챗 광고 플랫폼의 다른 조직에 속해 있는 경우 에이전시에 이 앱에 대한 Snap 앱 ID를 제공하도록 요청하고 이 필드에 입력하십시오. 여러 ID를 입력할 수 있습니다. 각 ID를 입력한 다음에 Enter 키를 누릅니다.

#### 인스톨 어트리뷰션

광고를 본, 클릭한 또는 귀사의 광고에 참여한 사용자의 새로운 인스톨(첫 실행)을 어트리뷰션하기 위해 다양한 어트리뷰션 기간을 설정하세요. 룩백 윈도우 내의 인스톨만 스냅챗에 어트리뷰션될 수 있습니다.

**참고:** 재설치(디바이스의 초기 설정이 아닌 모든 인스톨)에 대한 어트리뷰션은 지원되지 않습니다.

1. **설치 클릭-쓰루 룩백 윈도우**를 1&#126;23시간 또는 1&#126;30일 중 하나로 설정합니다. **참고:** 스냅챗에서는 설치 클릭-쓰루 룩백 윈도우를 7일로 설정하여 조정할 것을 권장합니다.

   > 📘 **참고**
   >
   > 클릭 쓰루 룩백 윈도우를 설정하면 참여한 조회수와 참여한 클릭의 룩백 윈도우도 결정됩니다.

2. [선택 사항] **설치 뷰-쓰루(view-through) 어트리뷰션**을 켜고 룩백 기간을 설정합니다:
   * **뷰-쓰루 룩백 윈도우 설치를** 1-24시간 사이로 설정합니다. **참고:** 스냅챗에서는 설치 뷰-쓰루 룩백 윈도우를 1일로 설정하여 조정할 것을 권장합니다.

#### 리인게이지먼트 어트리뷰션

귀사의 기존 사용자의 리인게이지먼트를 어트리뷰션하기 위해 광고를 보거나 클릭 또는 인게이지먼트한 사용자들에 대해 다양한 어트리뷰션 기간을 설정하세요. 룩백 윈도우 내의 리인게이지먼트만 스냅챗에 어트리뷰션될 수 있습니다.

1. **리인게이지먼트 클릭-쓰루 룩백 윈도우**를 1&#126;23시간 또는 1&#126;30일로 설정합니다. **참고:** 스냅챗 추천에 따라 리인게이지먼트 클릭-쓰루 룩백 윈도우를 7일로 설정하세요.

   > 📘 **참고**
   >
   > 리인게이지먼트 클릭 쓰루 룩백 윈도우를 설정하면 참여한 조회수 및 참여한 클릭 수에 대한 리인게이지먼트 룩백 윈도우도 결정됩니다.

2. [선택 사항] **리인게이지먼트 뷰-쓰루 어트리뷰션**을 활성화하고 룩백 윈도우를 설정하세요.
   * **리인게이지먼트 뷰-쓰루 룩백 윈도우**는 1&#126;24시간입니다. **참고:** 스냅챗 추천에 따라 리인게이지먼트 뷰-쓰루 룩백 윈도우를 1일로 설정하세요.
3. **리인게이지먼트 기간**을 1-23시간, 1-90일, 또는 **생애** 중에서 설정하세요.

#### 리타겟팅 대상으로 활성 유저 무시

앱을 실행한 사용자들의 리인게이지먼트 및 리-어트리뷰션을 <Anchor target="_blank" href="/marketers/ko/docs/set-retargeting-inactivity-window#비활성-기간">무시할</Anchor> 시간대를 정하세요. 이는 지정된 시간대 동안의 사용자 활동이 앱스플라이어에 기록되지 않는다는 것을 의미합니다.

> 📘 **참고**
>
> 지정된 시간 동안 **활동하지 않았던** 사용자들의 재인게이지먼트 및 리-어트리뷰션 전환은 **기록됩니다**.

1. 리타겟팅을 위해 **활동 중인 사용자 무시** 기능을 활성화하세요.
2. 비활성 기간을 설정하세요.

#### 인앱 이벤트 포스트백

포스트백을 통해 앱스플라이어 이벤트를 파트너와 매핑할 수 있습니다. 포스트백 전송이 사용 가능한 경우, 거부된 인앱 이벤트(Protect360에 의해 차단된 이벤트 또는 타겟 유효성 검증 규칙을 비준수하는 것으로 발견된 이벤트)를 포함합니다.

[![mceclip0.png](https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png)](https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png)

**인앱 이벤트 포스트백 설정 방법:**

1. **파트너 ID**를 설정합니다(필요한 경우).
2. **인앱 이벤트 포스트백**을 설정합니다.
3. 필요한 경우 **인앱 이벤트 포스트백 기간**을 설정합니다(<Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">인앱 이벤트 포스트백 기간 구성</Anchor>에 대해 자세히 알아보세요).
4. 가능한 경우 자동 또는 수동으로 이벤트를 전송할지 여부를 선택하십시오. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped">모든 이벤트를 있는 그대로 전송하기</Anchor>에 대해 자세히 알아보십시오.
5. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버 간 이벤트를 추가합니다.
6. 필수 파라미터를 입력합니다.
7. [선택 사항] <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />를 클릭하여 특정 인앱 이벤트를 파트너에게 발송하기 위한 조건을 설정하세요.  
   <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건부 인앱 이벤트 포스트백</Anchor>에 대해 자세히 알아보세요.

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 인스톨 및 재확인을 통해 디바이스에서 이벤트가 활성화되었는지 확인합니다.</li><li>**앱스플라이어 이벤트**에 입력한 다음 **사용자 지정 생성**을 클릭합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">커스텀 이벤트 매핑</Anchor>에 대해 더 알아보세요.</li></ul> |
| **파트너 이벤트에 매핑** | 파트너 측에서 정의한 각 이벤트의 고유한 이름 또는 ID입니다. 가능한 매핑 구성은 다음과 같습니다.<ul><li>**텍스트 필드:** 파트너로부터 해당 이벤트 ID를 받으세요.</li><li>**드롭다운 상자:** 가장 적합한 사전 정의된 앱스플라이어 이벤트를 선택합니다.</li><li>**그대로**: 이름 매핑 없이 이벤트를 있는 그대로 전송합니다.</li></ul> |
| **사용자용** | 이벤트의 전송 옵션을 선택합니다.<ul><li>**이 파트너만**: 이 이벤트가 이 파트너에게 귀속된 경우에만 포스트백을 발송합니다.</li><li>**오가닉을 포함한 모든 미디어 소스**: 파트너 및 오가닉 이벤트에 어트리뷰트된 이벤트에 대한 포스트백을 전송합니다.</li></ul> |
| **포함** | <ul><li>**데이터 없음(기본값)**: 이벤트 값 없이 이벤트 자체만 보냅니다.</li><li>**값 및 수익**: 매출 값(이벤트에 존재하는 경우)을 **포함하여** 모든 이벤트 파라미터를 전송합니다.</li><li>**수익이 없는 값**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

스냅챗에 대해 어트리뷰션 링크를 사용할 수 없습니다.

> 📘 **참고**
>
> 페이스북, Apple Search Ads, 애드워즈, 스냅챗 등과 같은 모든 SRN(Self Reporting Network)의 경우, 외부 어트리뷰션 링크를 사용하지 않기 때문에 이 탭이 작동하지 않습니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

비용 연동은 다음의 집약형 데이터를 제공합니다.

* 캠페인, 광고 세트, 광고, 채널 수준에 대한 비용 데이터입니다. 지원되는 기준, 지표 및 기능에 대한 세부 정보를 얻으려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">애드 네트워크 비용 연동 표</Anchor>를 참조하세요.  
  **참고:** 비용 데이터를 사용하려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor> 구독이 필요합니다.
* 클릭 수 및 노출 수에 대한 데이터입니다.

**비용 API를 활성화 하려면**:

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">이 연동 지침</Anchor>을 따르세요.

<div id="cost-data-sync-status" />

<Accordion title="비용 데이터 동기화 상태">

<Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">비용 API 상태와</Anchor> 앱스플라이어가 비용(및 광고 수익) 통합 상태 대시보드 또는 개별 광고 네트워크 대시보드에서 일치하는 비용 데이터를 가져온 마지막 시간을 확인합니다.

</Accordion>

<div id="stop-snapchat-cost-sync" />

<Accordion title="스냅챗 비용 동기화 중지">

**스냅챗 비용 받기를 중지하고 연결된 스냅챗 계정을 삭제하려면 다음 단계를 따르십시오.**

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">작업 열에서 계정 위로 마우스를 올리고 **연결 삭제**를 클릭합니다.</Anchor>  
  삭제되면 앱스플라이어가 비용 수신을 중지합니다. 연결 삭제는 과거 데이터에 영향을 주지 않습니다.

</Accordion>

> 📘 **참고**
>
> * 스냅챗의 캠페인 설정이 iOS 또는 안드로이드 앱용인지 확인하세요. 둘 다는 아닙니다. 캠페인이 두 앱 모두에 대한 것이라면 앱스플라이어는 앱당 비용을 분석할 수 없으며 비용은 앱스플라이어에 표시되지 않습니다.
> * 비용 데이터의 불일치를 방지하려면 앱 설정과 스냅챗 광고 계정에서 동일한 시간대를 <Anchor target="_blank" href="/marketers/ko/docs/changing-app-time-zone-settings#시간대-변경">설정</Anchor> 하십시오.
> * 일단 Snap 비용을 설정했으면, 실행 중인 캠페인, 광고셋, 단일 광고의 이름을 변경하면 안됩니다. 변경 시에는 비용 데이터에 심각한 불일치나 누락이 발생할 수 있습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

이 파트너와 연동 시 광고 수익은 지원되지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

스냅챗에 데이터에 액세스하고 다양한 작업을 수행할 수 있도록 어떤 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">권한을 부여할지</Anchor> 선택하세요.

> 📘 **참고**
>
> 권한 토글이 켜진 상태에서 연동이 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">비활성화</Anchor>되면 권한이 계속 부여됩니다.

</Accordion>

## 웹에서 앱으로: 비앱 캠페인의 앱 액티비티 측정

## 스냅챗을 통한 딥링킹

스냅챗을 통한 딥링킹은 스냅챗 플랫폼에서 네이티브 딥링크를 사용하는 동시에 앱스플라이어 파라미터를 추가하는 것을 기반으로 합니다.

스냅챗으로 딥링킹을 수행하려면:

1. 리타게팅을 위한 **딥링킹**이 [스냅챗에 대해 사용 가능한지](/docs/snapchat-advanced-srn-integration-setup#snap-플랫폼에서-딥링크를-설정하는-방법은-무엇입니까) 확인합니다.
2. <Anchor target="_blank" href="/marketers/ko/docs/app-settings#reengagement-attribution">앱스플라이어에서 리인게이지먼트 어트리뷰션이 활성화되어</Anchor> 있는지 확인합니다.
3. 앱의 딥링크 스키마 URI를 가져와 **최소한** 다음 파라미터를 추가합니다.

* **PID** - 이 경우 미디어 소스는 항상 **snapchat\_int**. 이렇게 하면 모든 데이터가 앱스플라이어 대시보드의 **Snapchat\_int** 미디어 소스 아래에 표시됩니다.
* **C -** 관련 캠페인 이름
* **is\_retargeting=true -** 이 필드는 캠페인을 리타겟팅 캠페인으로 정의합니다. 리타게팅 캠페인에 대한 기존 사용자의 인게이지먼트는 URI에 이 필드가 있기 때문에 리인게이지먼트로 표시됩니다. 이렇게 하면 사용자의 데이터가 리타겟팅 대시보드에 표시됩니다.

> 📄 **URI 예시**
>
> client://home?pid=snapchat\_int&c=TEST&is\_retargeting=true

### Snap 플랫폼에서 딥링크를 설정하는 방법은 무엇입니까?

1. **앱 기회 유형으로 트래픽 유도**로 이동합니다.
2. 딥링크 URI를 추가합니다.  
     
   [![](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)

### 스냅챗을 통한 디퍼드 딥링킹

<Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">디퍼드 딥링킹</Anchor>을 사용하면 SDK 수준에서 실시간으로 스냅챗 유저 전환 데이터에 액세스할 수 있습니다.

<Anchor target="_blank" href="/marketers/ko/docs/conversion-data-payloads-and-scenarios#snapchat-conversion-data">스냅챗 전환 데이터</Anchor>에는 **af\_dp** 파라미터가 포함되어 있어 사용자의 스냅챗 광고 참여도를 기반으로 맞춤형 콘텐츠를 딥링크하고 제공할 수 있습니다.

또한 **af\_adset** 또는 **af\_channel**과 같은 다른 전환 데이터 파라미터를 사용할 수 있습니다.

광고주를 대신하여 일하는 대행사는 Snapchat 통합을 켜고 캠페인에 대한 어트리뷰션을 시작할 수 있습니다. 그러나 이 통합에는 에이전시와 관련하여 몇 가지 제한 사항이 있습니다.

## 에이전시를 위한 스냅챗 설정하기

광고주를 대신하여 일하는 대행사는 Snapchat 통합을 켜고 캠페인에 대한 어트리뷰션을 시작할 수 있습니다. 그러나 이 통합에는 대행사와 관련하여 몇 가지 제한 사항이 있습니다.

### 에이전시 제한 사항

* 대행사는 함께 일하는 광고주가 Snapchat 통합을 활성화한 후에만 Snapchat 통합에 액세스할 수 있습니다.
* 에이전시의 연동 페이지에 표시되는 어트리뷰션 매개변수는 **보기 전용** 모드의 광고주 연동에서 상속됩니다. 즉, 에이전시는 광고주가 어트리뷰션 전환 확인 기간을 어떻게 구성했는지 확인할 수 있지만 자체적으로 구성할 수는 없습니다.
* 어트리뷰션 후 이벤트의 경우, 광고주로부터 허가받은 경우 에이전시는 인앱 이벤트 포스트백을 구성할 수 있습니다.
* 에이전시는 프라이버시 강화 설정을 켤 수 없으며(허가를 받은 경우에도) 광고주에게만 적용됩니다.

**대행사를 위해 Snapchat을 설정하려면:**

1. 앱스플라이어의 **구성**에서 **파트너 마켓플레이스**로 이동합니다.
2. **스냅챗**을 찾아 선택합니다.
3. 대행사의 **Snapchat 계정 ID**를 입력합니다. 이를 통해 대행사 트래픽을 식별하고 광고주 트래픽과 구별할 수 있습니다. 최대 50개의 서로 다른 스냅챗 계정 ID를 입력할 수 있습니다. 입력한 계정에서 생성된 모든 어트리뷰션 데이터는 대행사의 대시보드에서 확인할 수 있습니다.
4. **연동 저장**을 클릭합니다.

![snapchat-agency-integration.png](https://files.readme.io/261a0246bb7da0899e653a776eb25e17ce3ae8bff1efef33acac0ef0bf99abcf-21074932431505.png)

> ❗️ **경고**
>
> 스냅챗 계정 ID는 광고주 또는 에이전시 간에 공유되어서는 안 됩니다. 공유된 경우 모든 광고주의 설치가 에이전시의 대시보드에 자동으로 어트리뷰션됩니다. 공유된 경우 모든 광고주의 설치가 에이전시의 대시보드에 자동으로 어트리뷰션됩니다.

## 로데이터 제한

* 2023년 3월 1일부터 스냅챗 제거는 로데이터 리포트에 포함되지 않습니다.
* 2023년 9월 12일부터 Snapchat은 광고주에게 기기 수준에서 제한된 뷰스루 어트리뷰션 데이터를 제공합니다. 로데이터 리포트, Push API 메시지, Pull API 리포트, 데이터 내보내기 페이지 및 데이터 락커와 같은 사용자 수준 소스의 경우 다음 필드가 작성됩니다.
* * 미디어소스(snapchat\_int)
  * 채널
  * 어트리뷰트 터치 유형(노출)
  * 어트리뷰트 터치 시간(날짜로만 리포트됨 - "dd/mm/yyyy")
  * 캠페인은 "제한됨"으로 보고됩니다.

## 스냅챗 데이터 보관

스냅챗은 어트리뷰션 파트너에게 사용자 앱 설치 이후 12개월이 지나면, 사용자 레벨 데이터를 삭제하도록 요구합니다. 즉, 사용자가 앱을 설치한 후 12개월 이후에 수행한 이벤트는 오가닉으로 집계됩니다.

과거 종합 데이터는 동일하게 유지됩니다.

> 📄 **참조 항목**
>
> <Anchor target="_blank" href="/marketers/ko/docs/skan-interoperation-with-snapchat">스냅챗과 앱스플라이어 SKAdNetwork 상호 운용성</Anchor>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 01H8F1RWVPTHBDGF3830DY7G7M=%EA%B0%9C%EC%9A%94 setting-up-snapchat-integration=%EC%8A%A4%EB%83%85%EC%B1%97-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 01H7WQ47ECTZHPKMG5Z5ZPAND5=%EC%8A%A4%EB%83%85%EC%B1%97-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 01H88VAJH3BYZSXQGGZZJQ9N0C=%EC%B0%B8%EA%B3%A0 01H7WQ47ECD76GFNM7VVV7C9RG=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 01H7WQ47ECZB5GNCQ0XH68N1DK=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 01H7WQ47ECQSQPP63H398NTQ6M=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 install-attribution=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H8VVCC8GK8VFPBEPAMVHCAWM=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01JE5ZMSXK5Q9KWKY8C6ZXEGD9=%EC%B0%B8%EA%B3%A0-1 reengagement-attribution=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H8VVCC8HHG5290PYF0BT29QA=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01JJMAPTYDYVS5RDGQZA4J0DJ6=%EC%B0%B8%EA%B3%A0-2 ignore-active-users-for-retargeting=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%8C%80%EC%83%81%EC%9C%BC%EB%A1%9C-%ED%99%9C%EC%84%B1-%EC%9C%A0%EC%A0%80-%EB%AC%B4%EC%8B%9C h_01HNWSTJZPFQVQ5C8M0JA1J0T5=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%8C%80%EC%83%81%EC%9C%BC%EB%A1%9C-%ED%99%9C%EC%84%B1-%EC%9C%A0%EC%A0%80-%EB%AC%B4%EC%8B%9C h_01HMXNJVHK9C3FT8E04RE0TH99=%EC%B0%B8%EA%B3%A0-3 inapp-event-postback-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H8VVCC8HHZRFQ2T1X478YZMP=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H7WQ47EDWX9TGAD4X0E41RQ8=attribution-link-tab 01H7WQ47ED5N4REX0SFVY5ZG2K=%EC%B0%B8%EA%B3%A0-4 01H7WQ47EDCKQ1T4NVFD3C1KV0=cost-tab 01H7WQ47ED1HYEBHFJDHTB6HJH=cost-data-sync-status 01H7WQ47ED3P53B269W93Z341E=stop-snapchat-cost-sync 01H7WQ47EDQ0253RY37PX67REV=%EC%B0%B8%EA%B3%A0-5 01H7WQ47EDC3YB1BKNG2C7AD6J=ad-revenue-tab h_01HJ1BJTNNVYCVWY61NW07PY5J=permissions-tab h_01HJ1BJTNPG7NN3XZNP5XBE3XQ=%EC%B0%B8%EA%B3%A0-6 web-to-app-measuring-app-activity-for-nonapp-campaigns=%EC%9B%B9%EC%97%90%EC%84%9C-%EC%95%B1%EC%9C%BC%EB%A1%9C-%EB%B9%84%EC%95%B1-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%98-%EC%95%B1-%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%EC%B8%A1%EC%A0%95 h_01JJMAS0W9WMEPJCQWD9BXAEZ2=%EC%9B%B9%EC%97%90%EC%84%9C-%EC%95%B1%EC%9C%BC%EB%A1%9C-%EB%B9%84%EC%95%B1-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%98-%EC%95%B1-%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%EC%B8%A1%EC%A0%95 deep-linking-with-snapchat=%EC%8A%A4%EB%83%85%EC%B1%97%EC%9D%84-%ED%86%B5%ED%95%9C-%EB%94%A5%EB%A7%81%ED%82%B9 01H7WQ47EDC973V7CPE38QAQE7=%EC%8A%A4%EB%83%85%EC%B1%97%EC%9D%84-%ED%86%B5%ED%95%9C-%EB%94%A5%EB%A7%81%ED%82%B9 01H7WQ47EDXS702A9TZ7DJ8MPG=uri-%EC%98%88%EC%8B%9C how-to-set-up-deep-links-on-snap-platform=snap-%ED%94%8C%EB%9E%AB%ED%8F%BC%EC%97%90%EC%84%9C-%EB%94%A5%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%84%A4%EC%A0%95%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C 01H7WQ47EDJAX2DW7A2JJ4XVJN=snap-%ED%94%8C%EB%9E%AB%ED%8F%BC%EC%97%90%EC%84%9C-%EB%94%A5%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%84%A4%EC%A0%95%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C deferred-deep-linking-with-snapchat=%EC%8A%A4%EB%83%85%EC%B1%97%EC%9D%84-%ED%86%B5%ED%95%9C-%EB%94%94%ED%8D%BC%EB%93%9C-%EB%94%A5%EB%A7%81%ED%82%B9 01H7WQ47EDS3MYRN9A9ZPHXG9Z=%EC%8A%A4%EB%83%85%EC%B1%97%EC%9D%84-%ED%86%B5%ED%95%9C-%EB%94%94%ED%8D%BC%EB%93%9C-%EB%94%A5%EB%A7%81%ED%82%B9 setting-up-snapchat-for-agencies=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C%EB%A5%BC-%EC%9C%84%ED%95%9C-%EC%8A%A4%EB%83%85%EC%B1%97-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 01H7WQ47EDARK9SSP47V5MGX18=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C%EB%A5%BC-%EC%9C%84%ED%95%9C-%EC%8A%A4%EB%83%85%EC%B1%97-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 agency-limitations=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01HHVGS94CB9XC0T63VFDZ18JS=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD 01H7WQ47EDPEDQHX9XRDKYKB1W=%EA%B2%BD%EA%B3%A0 raw-data-restrictions=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A0%9C%ED%95%9C h_01HA3XZPWSKVRX7VTRXT1WQ1EZ=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A0%9C%ED%95%9C keeping-snapchat-data=%EC%8A%A4%EB%83%85%EC%B1%97-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B4%80 01H7WQ47ED9STKS1CVW5EXYX0Z=%EC%8A%A4%EB%83%85%EC%B1%97-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B4%80 h_01HE7RP6VPPAY2CCSNTJ0RVSXM=%EC%B0%B8%EC%A1%B0-%ED%95%AD%EB%AA%A9" />
