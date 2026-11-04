---
title: TikTok for Business - Advanced SRN 연동 설정
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-06-09T16:49:57Z'
  edited_at: '2026-10-14T10:39:27Z'
  id: 6722785184913
  locale: ko
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/ko/articles/6722785184913
---
> **한눈에 보기:** TikTok for Business(tiktokglobal\_int)는 앱스플라이어를 사용하여 클릭 및 조회 기반 모바일 어트리뷰션을 측정할 수 있는 고급 자체 보고 네트워크(<Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns">SRN</Anchor>)로, 앱 소유자에게 다양한 기능을 제공합니다. 여기에는 앱과 비모바일 TikTok 캠페인에서 발생한 앱 설치가 포함됩니다.

> 📘 **참고**
>
> * 2023년 1월 30일에 새 **TikTok for Business—Advanced SRN** 연동 `tiktokglobal_int`이 추가되었습니다. **[기존] TikTok for Business** 연동 `bytedanceglobal_int`는 점차적으로 중단되었으며, 2024년 3월 20일에 공식적으로 중단되었습니다. 전환은 TikTok에서 처리하며, 이전 연동 삭제가 가능할 때 알려드릴 것입니다. **데이터 손실을 방지하려면 전환 단계 동안 두 연동을 모두 활성 상태로 유지하세요**. <Anchor target="_blank" href="/marketers/ko/docs/bulletin-tiktok-for-business-advanced-srn">공지사항</Anchor>에서 자세히 알아보세요.
> * 앱스플라이어는 [비앱 캠페인](#웹-투-앱-비앱-캠페인의-앱-액티비티-측정)에 대한 앱 활동 측정을 지원합니다.

<Image alt="TTFB_logo__4C_stacked_black_1.png" src="https://files.readme.io/f876dca1810a33266ad93de7822354d3a9aeb41a1e064a1f85f7120f713e699d-23689976309905.png" width="218px" />

<div id="overview" />

## 개요

Advanced SRN 연동은 광고 ID를 포함하는 모든 트래픽이 일반적인 SRN 트래픽으로 어트리뷰션되어 리포트에 반영됨을 의미합니다. 광고 ID를 사용할 수 없는 경우, 앱스플라이어는 프라이버시 제한 규정에 따라 TikTok의 클릭 및 노출 수를 기반으로 어트리뷰션을 측정합니다.

<div id="set-up-tiktok-for-business" />

## TikTok for Business 설정

**전제 조건:** 연동을 설정하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. **활성화 방법:** 앱스플라이어의 측면 메뉴에서 **협업**> **파트너 마켓플레이스**를 선택하세요.  
   **편집하기**: 앱스플라이어의 측면 메뉴에서 **협업**> **활성화된 연동**을 선택하세요.
2. TikTok for Business 검색하여 **선택하세요**.
3. **연동 설정**을 클릭합니다. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.  
   **참고:** 파트너와 함께 작업하는 동안에는 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화됨)</Anchor> 상태로 토글을 켜두어야 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 구성을 완료하세요.

구성 창에는 다음과 같은 탭이 포함되어 있습니다: 연동, 어트리뷰션 링크, 비용, 광고 수익, 권한. **어트리뷰션 링크** 탭은 TikTok for Business에서 사용할 수 없으며, 나머지 탭은 선택 사항입니다.

> 📘 **참고**
>
> * 일부 설정은 iOS 및 안드로이드 디바이스에서 다릅니다.
> * 캠페인을 설정할 때 캠페인 이름이 공백으로 시작하거나 끝나지 않도록 해야 합니다. 그렇지 않으면 대시보드와 보고서에서 불일치가 발생할 수 있습니다. <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=9535">TikTok에서 캠페인 설정 방법</Anchor>에 대해 자세히 알아보세요.
> * <Anchor target="_blank" href="https://www.tiktok.com/business/en/blog/introducing-tiktok-search-ads-toggle">TikTok 검색 광고 토글</Anchor>에서의 광고는 모든 TikTok 어트리뷰션에 포함됩니다. 앱스플라이어는 특정한 검색어나 키워드에 대한 데이터를 수신하지 않습니다.

<div id="integration-tab" />

<Accordion title="연동 탭">

**연동** 탭에는 아래 설명된 바와 같이 여러 섹션이 포함되어 있습니다.

<div id="activate-partner" />

#### 파트너 활성화

연동을 구성하려면 먼저 **파트너 활성화**토글을 켜야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation#파트너-연동-활성화">파트너 활성화 및 비활성화</Anchor>에 대한 자세한 내용은 연동 탭을 참조하세요.

<div id="advanced-data-sharing" />

#### Advanced Privacy

iOS 앱만 해당: 포스트백 및 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">리포트</Anchor>를 통해 파트너와 공유된 데이터에 대한 제어 권한은 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">Advanced Privacy</Anchor> (iOS 14.5 이상)의 활성화 상태에 따라 달라집니다.

| Advanced Privacy: 켜기 | Advanced Privacy: 끄기 |
| --- | --- |
| 포스트백은 파트너에 어트리뷰션된 이벤트에 대해서만 전송됩니다. | 포스트백은 귀사의 설정에 따라 전송됩니다.<ul><li>**오가닉을 포함한 모든 미디어 소스**</li><li>**이 파트너사만 해당**</li></ul> |
| 포스트백은 <Anchor target="_blank" href="/partners/ko/docs/advanced-privacy-guide-postback-macros-for-ad-networks">Advanced Privacy 템플릿</Anchor>에 따라 전송됩니다. |  |
| <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">집계된 익명의 데이터</Anchor>가 고객에 의해 파트너에게 제공되며, 이는 사용자 레벨 데이터(디바이스 ID)가 전혀 포함되지 않음을 의미합니다. |  |

> 📘 **참고**
>
> * 연동(`tiktokglobal_int`)을 활성화할 때 **Advanced Privacy** 토글이 기본적으로 켜집니다.
> * 기존 연동(`bytedanceglobal_int`)에서 새 연동(`tiktokglobal_int`)으로 마이그레이션하고 활성화하면 마이그레이션 이전 상태와 관계없이 **Advanced Privacy** 토글이 기본으로 켜집니다.

<div id="general-settings" />

#### 일반 설정

**TikTok 앱 ID**

TikTok Ads Manager에서 생성된 고유 코드로, 앱의 소유자가 광고주임을 확인하는 데 사용됩니다. 필수는 아니지만 각 앱에 앱 ID를 입력하는 것이 좋습니다. 이렇게 하면 TikTok for Business에서 데이터를 더 잘 제어하고 추가 제품을 볼 수 있습니다.

**앱 ID 추가 방법:**

1. [선택 사항] TikTok 광고 대시보드에 사용 가능한 <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10001060">TikTok 앱 ID</Anchor>를 입력합니다.
2. [선택사항] 앱 ID를 더 추가하는 방법:
   1. 첫 번째 앱 ID를 입력한 후 Enter 키를 누릅니다.
   2. 다음 TikTok 앱 ID를 입력하세요.

> 📘 **참고**
>
> * TikTok 앱 ID를 구성해도 앱스플라이어의 데이터에 영향을 주지 않습니다.
> * 새로운 연동(`tiktokglobal_int`)으로 마이그레이션할 때 기존 연동(`bytedanceglobal_int`)의 모든 값이 이 필드에 자동으로 입력됩니다.
> * <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10001070">iOS 14에 대한 TikTok 앱 ID 요구 사항에 대해 더 보기</Anchor>

<div id="default-postbacks" />

#### 기본 포스트백

앱 **인스톨**에 대한 포스트백 발송 방법을 설정합니다. **거부된 인스톨** 및 **리인게이지먼트**의 경우 포스트백은 TikTok for Business에만 전송됩니다.

* **이 파트너만** [기본값]: 이벤트가 이 파트너에 측정될 때만 포스트백을 발송합니다. 즉, 이를 수행한 사용자가 이 파트너에서 온 경우입니다.
* **오가닉을 포함한 모든 미디어 소스:** 모든 파트너에 측정된 이벤트와 오가닉 이벤트(즉 이를 수행한 사용자가 모든 미디어 소스에서 온 경우)에 대해 포스트백을 발송합니다. 더 나은 최적화를 위해 TikTok for Business에서는 선택 항목을 **오가닉을 포함한 모든 미디어 소스**로 변경하는 것을 권장합니다.

> 📘 **참고**
>
> * iOS 앱만 해당: 포스트백 및 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">리포트</Anchor>를 통해 파트너와 공유되는 데이터 제어는 **Advanced Privacy( iOS 14.5 이상)** [토글 상태](#advanced-privacy)에 따라 달라집니다.
> * 기존 연동(`bytedanceglobal_int`)에서 마이그레이션하고 새로운 연동(`tiktokglobal_int`)을 활성화할 때, 마이그레이션 전 상태와 관계없이 포스트백 인스톨의 기본 선택 상태는 **이 파트너만**입니다.

<div id="install-attribution" />

#### 설치 어트리뷰션

광고를 본 사용자, 클릭한 사용자 또는 참여한 사용자의 새로운 인스톨(첫 실행)을 측정하기 위한 다양한 어트리뷰션 기간을 설정하세요. 룩백 윈도우 내에 있는 설치만 TikTok for Business에 어트리뷰션 될 수 있습니다.

1. **설치 클릭-쓰루 룩백 윈도우**를 1&#126;23시간 또는 1&#126;30일 중 하나로 설정합니다. **참고:** TikTok for Business에서는 설치 클릭-쓰루 룩백 윈도우를 7일로 설정하는 것을 권장합니다.

   > 📘 **참고**
   >
   > 클릭 쓰루 룩백 윈도우를 설정하면 참여한 조회수와 참여한 클릭 룩백 윈도우도 결정됩니다.

2. [선택 사항] **설치 뷰-쓰루(view-through) 어트리뷰션**을 켜고 룩백 기간을 설정합니다:
   * **뷰-쓰루 룩백 윈도우 설치를** 1-24시간 사이로 설정합니다. **참고:** TikTok for Business에서는 설치 뷰-쓰루 룩백 윈도우를 1일로 설정하여 조정할 것을 권장합니다.

> 📘 **참고**
>
> * TikTok for Business에서는 서비스를 사용하는 사람들을 보호하기 위해 고급 데이터 보호 조치를 사용하고 있습니다. 2021년 10월 23일부터 TikTok for Business에서는 광고주에게 디바이스 수준의 제한된 뷰-쓰루 어트리뷰션 데이터를 제공합니다. 로데이터 리포트, Push API 메시지, Pull API 리포트, 데이터 내보내기 페이지, 데이터 락커 같은 사용자 수준 소스에서 다음 필드만 채워집니다.
> * * 미디어 소스 (bytedanceglobal\_int)
>   * 채널
>   * 어트리뷰트 터치 유형(노출)
>   * 어트리뷰션 터치 시간(날짜로만 보고됨 - "dd/mm/yyyy")
>   * 캠페인은 "제한됨"으로 보고됩니다.
>     이 데이터는 GCD에서 사용할 수 없습니다. 집계 데이터 보고서에는 뷰-쓰루 전환이 계속 표시됩니다.
> * 기존 연동 (`bytedanceglobal_int`)에서 새로운 연동 (`tiktokglobal_int`)으로 마이그레이션할 때, 이전 상태와 관계없이 룩백 윈도우 설정(클릭-쓰루 및 뷰-쓰루)이 **기본값**으로 재설정됩니다. 이러한 설정은 업데이트가 가능합니다.

<div id="reinstall-attribution" />

#### 리인스톨 어트리뷰션

재설치 어트리뷰션을 통해 리어트리뷰션 윈도우 기간 내에 앱을 재설치한 사용자를 측정하고, 이들을 유효한 TikTok 클릭 및 노출 성과로 어트리뷰션할 수 있습니다.

이 기능을 켜면 재설치가 TikTok 캠페인에서 새로운 전환으로 집계되며, 기존의 설치 어트리뷰션 설정과 일관된 방식으로 리포트에 반영됩니다. 재설치에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/measure-reinstalls">재설치 측정</Anchor>을 참조하세요.

* 재설치 어트리뷰션을 활성화하려면 **연동** 탭에서 **재설치 어트리뷰션을** 활성화하세요.

> 📘 **참고**
>
> * 재설치를 위한 별도의 룩백 윈도우 설정은 필요하지 않습니다. 재설치 어트리뷰션은 기존 설치 어트리뷰션 설정과 동일한 클릭스루 및 뷰스루 활성화 상태와 룩백 윈도우 기준을 적용합니다.
> * 이 기능을 활성화하면, 조건에 부합하는 재설치 포스트백이 TikTok으로 전송됩니다.

<div id="re-engagement-attribution" />

#### 리인게이지먼트 어트리뷰션

광고를 조회, 클릭 또는 광고와 상호작용을 한 기존 사용자의 리인게이지먼트 성과를 인정할 수 있도록 각기 다른 어트리뷰션 윈도우를 설정하세요. 룩백 윈도우 내의 리인게이지먼트만 TikTok for Business에 의해 측정됩니다.

1. **리인게이지먼트 클릭-쓰루 룩백 윈도우**를 1&#126;23시간 또는 1&#126;30일로 설정합니다. **참고:** TikTok for Business에서는 리인게이지먼트 클릭-쓰루 룩백 윈도우를 7일로 설정하여 조정할 것을 권장합니다.

   > 📘 **참고**
   >
   > 리인게이지먼트 클릭 쓰루 룩백 윈도우를 설정하면 참여한 조회수 및 참여한 클릭 수에 대한 리인게이지먼트 룩백 윈도우도 결정됩니다.

2. [선택 사항] **리인게이지먼트 뷰-쓰루 어트리뷰션**을 활성화하고 룩백 윈도우를 설정하세요.
   * **리인게이지먼트 뷰-쓰루 룩백 윈도우**는 1&#126;24시간입니다. **참고:** TikTok for Business에서는 리인게이지먼트 뷰-쓰루 룩백 윈도우를 1일로 설정하여 추천합니다.
3. **리인게이지먼트 기간**을 1&#126;23시간, 1&#126;90일 또는 **평생**으로 설정하세요.

> 🚧 **중요!**
>
> 기존 연동 (`bytedanceglobal_int`)에서 마이그레이션하고 새로운 연동 (`tiktokglobal_int`)을 활성화하면, 마이그레이션 이전 상태와 관계없이 **리인게이지먼트** 토글이 **기본적으로 비활성화 됩니다**. 기존 연동에 <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">리타겟팅 캠페인</Anchor>이 있는 경우, 연속성을 위해 **새로운 연동에서 반드시 켜 주시기 바랍니다**.

<Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide#reengagement-rules-and-windows">리인게이지먼트 규칙 및 기간</Anchor>에 대해 자세히 알아보세요.

<div id="ignore-active-users-for-retargeting" />

#### 리타겟팅을 위해 활성 사용자 무시

앱을 실행한 사용자들의 리인게이지먼트 및 리어트리뷰션을 <Anchor target="_blank" href="/marketers/ko/docs/set-retargeting-inactivity-window#비활성-기간">무시할</Anchor> 시간대를 정하세요. 이는 지정된 시간대 동안의 사용자 활동이 앱스플라이어에 기록되지 않는다는 것을 의미합니다.

> 📘 **참고**
>
> 지정된 시간 동안 **활동하지 않았던** 사용자들의 리인게이지먼트 및 리어트리뷰션 전환은 **기록됩니다**.

1. 리타겟팅을 위해 **활동 중인 사용자 무시** 기능을 활성화하세요.
2. 비활성 기간을 설정하세요.

<div id="in-app-event-postbacks" />

#### 인앱 이벤트 포스트백

TikTok for Business 이벤트와 인앱 이벤트 매핑을 구성하여 포스트백을 통해 전송됩니다:

1. **인앱 이벤트 포스트백**을 활성화하세요.
2. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버-투-서버 이벤트를 추가하세요. 다음 표는 작성해야 할 필드를 설명합니다.

| 파라미터 이름 | 설명 |
| --- | --- |
| **AppsFlyer event** | 이벤트의 이름은 앱스플라이어가 귀하의 앱에 연동된 SDK로부터 수신했거나 서버-투-서버 이벤트로부터 수신하여 나타나는 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 설치된 디바이스에서 이벤트를 활성화하고 다시 확인하세요.</li><li>**앱스플라이어 이벤트**에 입력한 다음 **사용자 지정 생성**을 클릭합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">커스텀 이벤트 매핑</Anchor>에 대해 더 알아보세요.</li></ul> |
| **mapped to partner event** | 파트너 측에서 정의한 각 이벤트의 고유한 이름 또는 ID입니다. 사용할 수 있는 매핑 설정은 다음과 같습니다.<ul><li>**드롭다운 상자:** 사전에 정의된 TikTok 이벤트 목록 중 가장 알맞은 이벤트를 지정하세요.</li><li>**변경 없이**: 드롭다운 메뉴에서 **사용자정의**를 앱스플라이어는 이벤트를 TikTok에 사전에 정의된 이벤트와 매핑하지 않고 있는 그대로 전송합니다. TikTok은 커스텀 이벤트를 최적화용이 아닌 리포트 목적으로만 사용하므로, TikTok 측에서는 이러한 설정을 권장하지 않습니다. TikTok 표준 및 커스텀 이벤트에 대한 자세한 내용은 <Anchor target="_blank" href="https://ads.tiktok.com/help/article/standard-events-parameters">TikTok 문서</Anchor>를 참조하십시오.</li></ul> |
| **for users from** | 이벤트의 전송 옵션을 선택합니다.<ul><li>**이 파트너만**(기본값): 이 이벤트가 이 파트너에 어트리뷰션된 경우에만 포스트백을 발송합니다.</li><li>**오가닉을 포함한 모든 미디어 소스:** 모든 파트너에 어트리뷰션된 이벤트와 오가닉 이벤트에 대해 포스트백을 발송합니다. TikTok for Business에서는 더 나은 최적화를 위해 **오가닉을 포함한 모든 매체 소스**를 선택할 것을 권장합니다.</li></ul> |
| **including** | <ul><li>**값 없음 & 수익 없음** (기본 설정): 이벤트 값 없이 이벤트 자체만 발송합니다.</li><li>**값 있음 & 수익 없음**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li><li>**값 있음 & 수익 있음**: 수익 값이 있는 경우 이를 **포함**한 모든 이벤트 파라미터를 발송합니다. TikTok for Business에서는 더 나은 최적화를 위해 **값 있음 및 수익**을 선택하는 것이 좋습니다.</li></ul> |

3. [선택 사항] 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>하려면 **Add condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />아이콘을 클릭하세요.
4. **연동 저장**을 클릭하세요.
5. [선택 사항] 연동을 저장한 후 구성 페이지에 남아 있는 동안 더 많은 앱을 파트너와 통합할 수 있습니다.
   1. 왼쪽 상단 모서리의 파트너 이름 아래에서 앱 이름을 클릭하여 앱 목록을 엽니다.
   2. 드롭다운 목록에서 다른 앱을 선택합니다.
   3. 선택한 앱에 대해 연동 단계를 반복합니다.

> 📘 **참고**
>
> * iOS 앱만 해당: 포스트백 및 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">리포트</Anchor>를 통해 파트너와 공유되는 데이터 제어는 **Advanced Privacy( iOS 14.5 이상)** [토글 상태](#advanced-privacy)에 따라 달라집니다.
> * 새 연동(`tiktokglobal_int`)으로 마이그레이션할 때 레거시 연동(`bytedanceglobal_int`)에서 구성된 모든 포스트백 이벤트는 동일한 구성으로 자동으로 채워집니다.
>   * 이벤트가 [레거시] TikTok for Business **Pay** 이벤트에 매핑된 경우 새 연동으로 마이그레이션하면 이 이벤트 이름이 자동으로 **Purchase**로 변경됩니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

어트리뷰션 링크는 <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns">SRN</Anchor> 또는 Advanced SRN과 관련이 없습니다.

SRN은 자체 플랫폼에서 어트리뷰션을 수행합니다. Advanced SRN에 대한 어트리뷰션은 [통합 탭](#integration-tab)에서 정의한 어트리뷰션 설정을 사용하여 인게이지먼트 데이터와 앱스플라이어의 데이터를 결합하여 수행됩니다.

</Accordion>

<div id="cost-tab-for-cost-clicks-and-impressions" />

<Accordion title="비용 탭(비용, 클릭 수, 노출 수)">

이 연동은 귀사의 캠페인, 광고 세트, 광고, 지역/국가에 대한 비용, 클릭 및 노출 수에 대한 데이터 집약형 데이터를 제공합니다. 지원되는 디멘션, 메트릭 및 기능에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">애드 네트워크 비용 연동 표</Anchor>를 참조하세요.

**참고:** 클릭 및 노출 수에 대한 데이터가 연동에 포함됩니다. 하지만 **비용 데이터에는** <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview?query=xpend">**ROI360**</Anchor> **구독**이 필요합니다.

**TikTok for Business를 통해 비용, 클릭 수, 노출 수에 대한 API 연결을 활성화하는 방법**:

1. **비용** 탭으로 이동하여 **비용 데이터 가져오기**를 켭니다.
2. **TikTok 광고에 로그인**을 클릭하세요.
3. TikTok 창이 열리면 귀사의 TikTok 계정에 로그인하고 필요한 권한을 확인하세요.
4. TikTok 창에서 성공 메시지가 나타나면 창을 닫습니다. 이제 TikTok 계정 세부 정보가 **연결된 계정**에 표시됩니다.
5. **광고주 계정 ID** > **광고주 ID**에서: TikTok 광고주 계정 ID를 입력하고 **추가**를 클릭합니다.

   > 📘 **참고**
   >
   > * 귀사의 TikTok 비즈니스 계정에서 **광고주 ID**를 가져오려면: **사용자** > **회원**으로 이동한 후 광고주 계정 아래에서 ID를 확인할 수 있습니다.
   > * 2단계에서 연결한 **TikTok 계정**과 연결된 **광고주 ID**를 추가해야 합니다. 이 계정은 데이터가 수집되는 계정입니다.
   > * 최소한 하나의 **광고주 ID**를 연결하세요. 최대 30개까지 추가할 수 있습니다.

6. **비용 저장**을 클릭하세요.

<div id="for-roi360-subscribers" />

#### ROI360 구독자용

* 기존 `bydanceglobal_int` 통합과 현재 `tiktokglobal_int` 통합에서 모두 비용 API를 사용하도록 설정한 광고주와 에이전시에게 중복된 비용 데이터가 표시될 수 있습니다. 이를 방지하려면 `bytedanceglobal_int` 통합 > **비용** 탭으로 이동하여 토글을 끕니다.  
  그러나 새 비용 연동을 활성화하면 전환일 이전 5일 동안의 비용 데이터가 자동으로 수집됩니다. 즉, 새 연동은 이전 5일 동안 중복된 비용 데이터를 표시할 것으로 예상됩니다. **예를 들어**, 이전 비용 연동이 1월 15일에 비활성화되고 새 비용 연동이 같은 날에 활성화된 경우, 1월 15일에만 활성화되었더라도 1월 10일에서 14일 사이에 새 비용 연동에 중복 비용 데이터가 표시됩니다.
* 지원되는 디멘션, 메트릭 및 기능에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">애드 네트워크 비용 연동 표</Anchor>를 참조하세요.
* <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">비용 API 상태와</Anchor> 앱스플라이어가 비용(및 광고 수익) 통합 상태 대시보드 또는 개별 광고 네트워크 대시보드에서 일치하는 비용 데이터를 가져온 마지막 시간을 확인합니다.
* <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">비용 API 활성화</Anchor>에 대해 자세히 알아보세요.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

UA 최적화를 위해 TikTok에 귀사의 광고 수익 데이터를 발송하려면 <Anchor target="_blank" href="/marketers/ko/docs/share-ad-revenue-data-with-partners">광고 수익 포스트백 또는 UA 신호</Anchor>를 구성할 수 있습니다.

Pangle로부터 광고 수익 데이터를 가져오려면, Pangle (ad revenue) 파트너 연동을 사용하세요.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

이 섹션에서는 TikTok for Business에 귀사의 데이터에 대한 액세스 권한을 부여하고 다양한 작업을 수행할 수 있는 권한을 선택할 수 있습니다.

연동이 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">비활성화</Anchor>된 후에도 **TikTok for Business 권한** 토글이 켜져 있으면 권한이 계속 부여됩니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">권한 부여</Anchor>에 대해 자세히 알아보십시오.

</Accordion>

<div id="deep-linking-with-tiktok-for-business" />

## TikTok for Business와 함께하는 딥링크

<Anchor target="_blank" href="https://ads.tiktok.com/help/article/understanding-deeplinks-and-deferred-deeplinks?lang=en">TikTok은 딥링킹과 디퍼드 딥링크를 캠페인, 광고 그룹, 그리고 광고 생성 시 광고 수준에서 다양한 캠페인 목표에 대해 지원합니다.</Anchor> 사용자가 특정 콘텐츠로 이동할 수 있는 딥링크를 만들면, TikTok 광고에 대한 유저의 인게이지먼스에 따라 맞춤형 콘텐츠를 제공할 수 있습니다.

<div id="access-tiktok-conversion-data-via-appsflyers-gcd-api-for-deep-linking" />

### AppsFlyer의 GCD API를 통해 딥링크를 위한 TikTok 전환 데이터 액세스

앱스플라이어는 디퍼드 딥링크에 다양한 솔루션을 제공합니다.

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">**통합 딥링크(UDL)**</Anchor>: TikTok 클릭에는 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#deep_link_value">deep\_link\_value</Anchor> 필드가 포함되어 있으며(광고에 딥 링크가 설정된 경우), UDL 솔루션에서 지원됩니다.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking">**GCD(전환 데이터 가져오기) API**</Anchor>: 이는 SDK 수준에서 TikTok 사용자 전환 데이터를 실시간으로 액세스할 수 있는 권장 옵션입니다. GCD API에서 반환되는 데이터에는 실제 딥 링크 목적지(앱 내 사용자 목적지)를 담고 있는 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_dp">`af_dp`</Anchor> 파라미터가 포함되어 있습니다.
* **전환 데이터 파라미터 사용:** 캠페인 이름, 광고 세트 이름 또는 TikTok 인스톨에 대한 어트리뷰션 데이터의 일부로 반환되는 다른 필드와 같은 다른 파라미터를 사용하여 사용자가 귀사의 콘텐츠로 이동할 수 있는 커스텀 로직을 생성할 수 있습니다.

<div id="web-to-app-measure-app-activity-for-non-app-campaigns" />

## 웹-투-앱: 비앱 캠페인의 앱 액티비티 측정

앱스플라이어와 TikTok의 연동을 통해, TikTok for Business의 성과로 어트리뷰션된 논앱 캠페인의 설치, 리인게이지먼트, 인앱 이벤트 등 종합적인 앱 활동 측정이 가능해집니다.

예를 들어, 광고 목적지가 웹 랜딩 페이지인 경우에도 앱 설치를 측정할 수 있어 웹 투 앱(W2A) 사용자의 여정을 파악할 수 있습니다.   
  
TikTok Ads Manager에서 아래 단계를 진행하면, TikTok 논앱 캠페인을 통한 앱 활동을 효과적으로 측정하고 사용자 행동에 대한 가치 있는 인사이트를 얻을 수 있습니다. <Anchor target="_blank" href="https://ads.tiktok.com/help/article/how-to-measure-app-activity-for-non-app-promotion-campaigns?lang=en">틱톡 문서</Anchor>도 참고할 수 있습니다.

1. TikTok 광고 캠페인 페이지로 이동하여 **광고 수정**을 클릭합니다.
2. **트래킹** > **앱 이벤트**에서 귀사의 앱을 선택하세요.
3. **저장**을 클릭하세요.
4. 이 단계들은 캠페인 내의 모든 관련 광고에 적용됩니다.

<div id="set-up-tiktok-for-business-for-agencies" />

## 에이전시를 위한 TikTok for Business 설정하기

광고주를 대신하여 일하는 에이전시는 TikTok for Business 통합을 켜고 캠페인에 대한 어트리뷰션을 받을 수 있습니다. 그러나 이 통합에는 에이전시와 관련하여 몇 가지 제한 사항이 있습니다.

<div id="agency-limitations" />

### 에이전시 제한 사항

* 에이전시는 함께 일하는 광고주가 활성화한 후에만 TikTok for Business 통합에 액세스할 수 있습니다.
* 2024년 1월 1일부터 에이전시의 연동 페이지에 표시되는 어트리뷰션 매개변수는 **보기 전용** 모드의 광고주 연동에서 상속됩니다. 즉, 에이전시는 광고주가 어트리뷰션 전환 확인 기간을 어떻게 구성했는지 확인할 수 있지만 자체적으로 구성할 수는 없습니다.
* 에이전시는 Advanced Privacy 설정을 활성화 할 수 없으며(허가를 받은 경우에도) 광고주에게만 적용됩니다.
* 광고주로부터 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#configure-inapp-event-postbacks::8743ba60">권한</Anchor>을 부여받은 경우, 대행사는 인앱 이벤트 포스트백을 구성할 수 있습니다.
* 인앱 이벤트 포스트백을 매핑할 때, 대행사와 마케터의 매핑 구성이 동일한지 확인하는 것이 좋습니다.

**대행사를 위한 TikTok for Business 설정 방법:**

1. 앱스플라이어의 **구성**에서 **파트너 마켓플레이스**로 이동합니다.
2. **TikTok for Business**를 찾아 선택하세요.
3. **TikTok 앱 ID**를 입력합니다.
4. 에이전시 **TikTok 계정 ID**를 입력합니다. 이를 통해 대행사 트래픽을 식별하고 광고주 트래픽과 구별할 수 있습니다.
5. **연동 저장**을 클릭합니다.

   <Image alt="tiktok.png" src="https://files.readme.io/b13ee9cd005b97c37019154a0caa10e03b846e7405777d9fc0e3db11bfb233b4-33379202036369.png" width="60.92%" />

> ❗️ **경고**
>
> TikTok for Business 계정 ID는 광고주 또는 에이전시 간에 공유해서는 안 됩니다. 공유된 경우 모든 광고주의 인스톨이 에이전시의 대시보드에 자동으로 어트리뷰션됩니다.

<div id="smart-plus-campaigns-reporting" />

## Smart Plus 캠페인 리포트

Smart Plus는 단일 광고 소재 단위에서 다수의 크리에이티브를 검증할 수 있는 신규 TikTok 캠페인 타입이며, 자동 크리에이티브 테스팅을 거쳐 광고 성과를 극대화할 수 있도록 지원합니다.

<Anchor target="_blank" href="https://ads.tiktok.com/help/article/about-smart-plus-campaign?lang=en">Smart Plus 캠페인에 대해 더 알아보기</Anchor>

<div id="how-smart-plus-campaigns-are-structured" />

### Smart Plus 캠페인은 어떻게 구성되나요?

캠페인, 광고 그룹, 광고의 3개 레벨로 구성된 표준 TikTok 캠페인과 달리, Smart Plus 캠페인은 네 번째 레이어 **크리에이티브** 단계를 추가로 포함합니다.

1. 캠페인
2. 광고 세트
3. 광고
4. 크리에이티브

<div id="how-smart-plus-data-is-reported-in-appsflyer" />

### Smart Plus 데이터가 앱스플라이어에 리포트되는 방식

앱스플라이어는 TikTok Smart Plus 캠페인 데이터를 다음과 같이 매핑합니다:

| 틱톡 | 앱스플라이어 | 참고 |
| --- | --- | --- |
| 캠페인 | 캠페인 | 직접 매핑됨 |
| 광고 그룹 | 광고 세트 | 직접 매핑됨 |
| 광고 | — | 앱스플라이어에 매핑되지 않음 |
| 크리에이티브 | 광고 | 앱스플라이어 광고 수준에 맞춰 매핑됨 |

> 📘 **참고**
>
> Smart Plus 캠페인에 대한 앱스플라이어의 매핑 구조는 TikTok Ads Manager와 다릅니다. TikTok Ads Manager 리포트에서는 크리에이티브 단위를 별도로 쪼개어 보지 않고, 오직 광고 단계까지만 성과 데이터를 확인할 수 있습니다. 그러나 앱스플라이어는 TikTok의 크리에이티브 데이터를 광고 레벨로 직접 매핑합니다. 결과적으로 앱스플라이어와 TikTok 간의 퍼포먼스 데이터를 비교할 때 수치 차이가 발생할 수 있습니다.

## 문제 해결

### 내 TikTok 앱 상태가 검토 대기 중으로 표시됩니다.

앱스플라이어에서 앱 레벨 또는 TikTok 파트너 레벨 중 하나라도 Aggregated Advanced Privacy(AAP) 모드가 활성화된 경우, 설치 및 인앱 이벤트 포스트백은 광고 네트워크에 기여된 설치에 대해서만 전송됩니다. 결과적으로 TikTok은 오가닉 소스로부터 필요한 포스트백을 수신하지 못할 수 있으며, 이로 인해 인증 대기 중 상태가 발생할 수 있습니다.

#### 권장 설정

1. 인증을 완료하기 위한 목적으로 오가닉 포스트백이 TikTok에 수신될 수 있도록, 앱스플라이어에서 AAP 설정을 일시적으로 비활성화할 수 있습니다. AAP 설정을 비활성화하면 광고주와 파트너사가 사용자 레벨 데이터에 접근할 수 있게 됩니다. 자세한 내용은 다음을 참조하세요. <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework#aap가-비활성화됨">AAP가 비활성화됨</Anchor>
   1. <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework#aap-central-switch">앱 수준 설정</Anchor>으로 이동하여 AAP를 비활성화합니다.
   2. [TikTok의 파트너 연동 구성](#advanced-privacy)으로 이동하여 거기에서도 AAP를 비활성화하세요
2. [포스트백 섹션](#기본-포스트백)에서 포스트백 방법을 다음과 같이 설정합니다. **오가닉을 포함한 모든 미디어 소스:**
3. TikTok이 최소 한 건 이상의 설치 또는 인앱 이벤트 포스트백을 수신할 때까지 기다립니다. 포스트백이 수신되면 TikTok 대시보드에서 앱 상태가 자동으로 인증됨으로 업데이트됩니다.
4. 인증이 완료된 후에는 회사의 개인정보 보호 환경 설정에 따라 [AAP 개인정보 보호 설정을 다시 활성화할 수 있습니다](#advanced-privacy).

> 📄 **참고 항목**
>
> * 중국 트래픽을 위한 <Anchor target="_blank" href="/marketers/ko/docs/bytedance-ads-china-campaign-configuration">ByteDance Ads (Ocean Engine</Anchor>) (bytedance\_int)
> * <Anchor target="_blank" href="/marketers/ko/docs/skan-interoperation-with-tiktok-for-business">TikTok for Business와 SKAN 상호 운용성</Anchor>

<div data-zendesk-anchors="01H8VVCC8GW5AZ3M475XFZY9JW=%EC%B0%B8%EA%B3%A0 overview=%EA%B0%9C%EC%9A%94 01H8VVCC8G3ZXZJMHSMJ67GMG4=%EA%B0%9C%EC%9A%94 setting-up-tiktok-for-business%C2%A0integration=tiktok-for-business-%EC%84%A4%EC%A0%95 01H8VVCC8GPY4SEFGK30Q1BJZ6=tiktok-for-business-%EC%84%A4%EC%A0%95 01H8VVCC8G6P25R0N5A7S3NGY7=%EC%B0%B8%EA%B3%A0-1 01H8VVCC8GY6WTH0404RH2AR9F=integration-tab activate-partner::e4f2f638=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 01H8VVCC8G0KR4AA2HD9S8QBKD=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 01H8VVCC8G0Z6ZHC10KVY9CGGQ=advanced-privacy 01H8VVCC8GC57YTDWA9EB2VP87=%EC%B0%B8%EA%B3%A0-2 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 01H8VVCC8GSDPSNN0AJPVZPR8P=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 01H8VVCC8G2JB115XW49HJQFHA=%EC%B0%B8%EA%B3%A0-3 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H8VVCC8GW677RN6R6CV35KGG=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H8VVCC8G6M8D3WQ2CM10ZNZX=%EC%B0%B8%EA%B3%A0-10 install-attribution=%EC%84%A4%EC%B9%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H8VVCC8GK8VFPBEPAMVHCAWM=%EC%84%A4%EC%B9%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01JE5ZMSXK5Q9KWKY8C6ZXEGD9=%EC%B0%B8%EA%B3%A0-5 01H8VVCC8G3YFDZVV9X9709F9M=%EC%B0%B8%EA%B3%A0-6 reinstall-attribution=%EB%A6%AC%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01K6D37PG96P2MG99BETK25GYA=%EB%A6%AC%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01K6D43X96RNY6H2RJEYW4KPCY=%EC%B0%B8%EA%B3%A0-7 reengagement-attribution=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H8VVCC8HHG5290PYF0BT29QA=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01JJM8MPX2HMWBZSSAAC4YCZ3Q=%EC%B0%B8%EA%B3%A0-8 01H8VVDWH85M34K7Z75BAT7BQW=%EC%A4%91%EC%9A%94 ignore-active-users-for-retargeting=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85%EC%9D%84-%EC%9C%84%ED%95%B4-%ED%99%9C%EC%84%B1-%EC%82%AC%EC%9A%A9%EC%9E%90-%EB%AC%B4%EC%8B%9C h_01HNWSTJZPFQVQ5C8M0JA1J0T5=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85%EC%9D%84-%EC%9C%84%ED%95%B4-%ED%99%9C%EC%84%B1-%EC%82%AC%EC%9A%A9%EC%9E%90-%EB%AC%B4%EC%8B%9C h_01HMXNJVHK9C3FT8E04RE0TH99=%EC%B0%B8%EA%B3%A0-9 inapp-event-postbacks=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H8VVCC8HHZRFQ2T1X478YZMP=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H8VVCC8HDMTY1P2SG31HD61K=%EC%B0%B8%EA%B3%A0-10 01H8VVCC8H53ZRMDBNK1436NAX=attribution-link-tab 01H8VVCC8H74GDVCNAXT0741MG=cost-tab-for-cost-clicks-and-impressions 01H8VVCC8HFJF62TC7DNXRH22A=%EC%B0%B8%EA%B3%A0-11 for-xpend-subscribers=roi360-%EA%B5%AC%EB%8F%85%EC%9E%90%EC%9A%A9 01H8VVCC8HWDC9A03FRY5BC87Y=roi360-%EA%B5%AC%EB%8F%85%EC%9E%90%EC%9A%A9 01H8VVCC8H90ANM70QAHKTQQ1S=ad-revenue-tab 01H8VVCC8HAG0XVWE2T9PRDHTK=permissions-tab deep-linking-with-tiktok-for-business=tiktok-for-business%EC%99%80-%ED%95%A8%EA%BB%98%ED%95%98%EB%8A%94-%EB%94%A5%EB%A7%81%ED%81%AC h_01JJM8MPX2X37WVR86S7786S06=tiktok-for-business%EC%99%80-%ED%95%A8%EA%BB%98%ED%95%98%EB%8A%94-%EB%94%A5%EB%A7%81%ED%81%AC accessing-tiktok-conversion-data-via-appsflyers-gcd-api-for-deep-linking=appsflyer%EC%9D%98-gcd-api%EB%A5%BC-%ED%86%B5%ED%95%B4-%EB%94%A5%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%9C%84%ED%95%9C-tiktok-%EC%A0%84%ED%99%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%95%A1%EC%84%B8%EC%8A%A4 h_01HVQR1TC5WVRDS24R9ZKD2HW2=appsflyer%EC%9D%98-gcd-api%EB%A5%BC-%ED%86%B5%ED%95%B4-%EB%94%A5%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%9C%84%ED%95%9C-tiktok-%EC%A0%84%ED%99%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%95%A1%EC%84%B8%EC%8A%A4 measuring-app-activity-for-nonapp-campaigns=%EC%9B%B9-%ED%88%AC-%EC%95%B1-%EB%B9%84%EC%95%B1-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%98-%EC%95%B1-%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%EC%B8%A1%EC%A0%95 h_01J7MYAMBQ8M0JN005FSXQDZNS=%EC%9B%B9-%ED%88%AC-%EC%95%B1-%EB%B9%84%EC%95%B1-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%98-%EC%95%B1-%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%EC%B8%A1%EC%A0%95 setting-up-tiktok-for-business-for-agencies=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C%EB%A5%BC-%EC%9C%84%ED%95%9C-tiktok-for-business-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 01H8VVCC8HVNNQ9PJS4ZQCVDNS=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C%EB%A5%BC-%EC%9C%84%ED%95%9C-tiktok-for-business-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 agency-limitations=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01HHVGS94CB9XC0T63VFDZ18JS=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD 01H8VVCC8HWJ2WQ83E0CZMEHH1=%EA%B2%BD%EA%B3%A0 smart-campaigns=smart-plus-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EB%A6%AC%ED%8F%AC%ED%8A%B8 smart-plus-campaigns-reporting=smart-plus-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01K9AGYS6XCDS3193ZAK7Z208F=smart-plus-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EB%A6%AC%ED%8F%AC%ED%8A%B8 how-smart-plus-campaigns-are-structured=smart-plus-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EA%B5%AC%EC%84%B1%EB%90%98%EB%82%98%EC%9A%94 h_01K9AGYS6XSXJ9DD6XYDHVYMYK=smart-plus-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EA%B5%AC%EC%84%B1%EB%90%98%EB%82%98%EC%9A%94 how-smart-plus-data-is-reported-in-appsflyer=smart-plus-%EB%8D%B0%EC%9D%B4%ED%84%B0%EA%B0%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EB%90%98%EB%8A%94-%EB%B0%A9%EC%8B%9D h_01K9AGYS6XYT763ST1H1T4SXT8=smart-plus-%EB%8D%B0%EC%9D%B4%ED%84%B0%EA%B0%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EB%90%98%EB%8A%94-%EB%B0%A9%EC%8B%9D h_01K9AGYS6X12RC8245TY1RGVNX=%EC%B0%B8%EA%B3%A0-12 troubleshooting=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01JQBGSDV84TBJGXGBSFWN6C4D=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 my-app-status-on-tiktok-is-%E2%80%98pending-verification%E2%80%99=%EB%82%B4-tiktok-%EC%95%B1-%EC%83%81%ED%83%9C%EA%B0%80-%EA%B2%80%ED%86%A0-%EB%8C%80%EA%B8%B0-%EC%A4%91%EC%9C%BC%EB%A1%9C-%ED%91%9C%EC%8B%9C%EB%90%A9%EB%8B%88%EB%8B%A4 h_01JQBGSKBY6C3289G3NY3WN74K=%EB%82%B4-tiktok-%EC%95%B1-%EC%83%81%ED%83%9C%EA%B0%80-%EA%B2%80%ED%86%A0-%EB%8C%80%EA%B8%B0-%EC%A4%91%EC%9C%BC%EB%A1%9C-%ED%91%9C%EC%8B%9C%EB%90%A9%EB%8B%88%EB%8B%A4 recommended-resolution=%EA%B6%8C%EC%9E%A5-%EC%84%A4%EC%A0%95 h_01JQBGWA8ASV6MBA5FKGD56DKZ=%EA%B6%8C%EC%9E%A5-%EC%84%A4%EC%A0%95 h_01HE7RY8K7HV2CTZ2S537YRCNQ=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
