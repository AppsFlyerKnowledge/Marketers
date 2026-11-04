---
title: 아이언소스 캠페인 구성
metadata:
  keywords:
    - Supersonic
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-06T10:47:23Z'
  edited_at: '2026-10-14T10:33:06Z'
  id: 208005096
  locale: ko
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ko/articles/208005096
---
> **요약:** 앱스플라이어 연동 파트너인 아이언소스는 앱 개발자, 기기 제조업체, 이동통신사 및 광고주를 위한 수익화, 인게이지먼트, 분석 및 검색 도구를 구축합니다. 아이언소스는 클릭 기반 모바일 어트리뷰션 외에도 비용, 광고 수익, 리타게팅 및 뷰-쓰루 어트리뷰션을 제공하며, 앱스플라이어로 기록할 수 있습니다.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ironsource.png?v=1" width="213px" />

> 📘 **참고사항**
>
> 아이언소스는 모든 인스톨 네트워크로서 오가닉을 포함한 모든 소스에서 앱의 모든 신규 인스톨에 대한 포스트백을 수신하는 것을 선호합니다. 이렇게 하려면 모든 파트너에 어트리뷰트된 이벤트를 선택하여 모든 인스톨 포스트백을 아이언소스로 보내야 합니다.

**전제 조건:** **연동 설정 전에 반드시  <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락하여</Anchor> 계정을 개설하세요.**

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서**협업** > **파트너 마켓플레이스**를 선택합니다.  
   **편집 방법:** 앱스플라이어의 사이드 메뉴에서 **협업** > **활성 연동**을 선택합니다.
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭합니다. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고  **파트너 활성화** 을 켭니다.  
   **참고:** 토글은 파트너와 함께 작업하는 동안 켜져 있어야<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화되어야)</Anchor> 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

연동, 어트리뷰션 링크, 비용, 광고 수익, 권한. 아래 항목을 클릭하여 탭 설정에 대한 상세 설명을 참조하십시오.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

> 👍 **팁**
>
> * 연동 탭의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#d-general-settings">일반 설정</Anchor> 단계는 모든 파트너에게 **필수** 항목입니다
> * 나머지 모든 단계는 설명이거나 **선택** 항목입니다

<div id="integration-tab" />

<Accordion title="연동 탭">

### 파트너 활성화

여기 **첫 번째 방문**에서 연동 탭의 파라미터 설정을 사용 가능하게 하려면 **파트너 활성화** 토글을 켜야 합니다. 파트너와 함께 작업하는 동안 토글은 계속 켜져 있어야 합니다.  
파트너 활성화에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

#### 프라이버시 강화 모드

iOS앱의 경우에만 **고급 개인 정보 보호(iOS 14.5+ 이상)** 가 켜져 있으면 포스트백 및 리포트를 통해 아이언소스와 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#b-advanced-privacy">공유되는 데이터를 제어할 수</Anchor> 있습니다.

### 트랜잭션 ID

iOS 앱에 한해, **SKAN 트랜잭션 ID 공유**가 켜져 있으면 앱스플라이어가 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">SKAdNetwork 포스트백의 트랜잭션 ID를 Reddit과 공유</Anchor>할 수 있습니다.

> 📘 **참고사항**
>
> 앱스플라이어와 SKAN의 상호 운용에 대해서는 아이언소스 계정 관리자에게 문의하여 <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/general/universal-skan-reporting/#step-1">SKAN 데이터를 MMP로 전송할 수 있도록 하십시오</Anchor>.

### 일반 설정

**광고주 ID**

아이언소스는 고유한 광고주 ID(6자리 숫자)와 비밀번호를 통해 앱스플라이어와 연결합니다. 아직 광고주 ID와 비밀번호가 없는 경우 아이언소스에서 광고주 ID와 비밀번호를 받아야 연동을 계속할 수 있습니다. 그렇지 않으면 ID와 비밀번호를 복사하여 해당 필드에 붙여넣어야 합니다.

<div id="note-3" />

<div id="default-postbacks" />

<div id="install-and-re-engagement-attribution" />

### 인스톨 및 리인게이지먼트 어트리뷰션

이 두 가지 토글을 통해 아이언소스의 신규 인스톨 어트리뷰션과 광고를 **보았지만** **클릭하지 않은** 유저를 리인게이지먼트할 할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/measure-view-through-engagements">뷰-쓰루 어트리뷰션</Anchor>에 대해 더 알아보세요.

**새 인스톨을 어트리뷰트하려면:**

1. **뷰-쓰루 어트리뷰션 설치**를 켭니다.
2. **어트리뷰션 링크 탭**에서 [뷰-쓰루](/docs/ironsource-campaign-configuration#attribution-link-tab) 기여 기간의 길이를 설정합니다.

**기존 사용자의 신규 리인게이지먼트를 어트리뷰션하려면:**

1. **리인게이지먼트 뷰-쓰루 어트리뷰션**을 켭니다.
2. **어트리뷰션 링크 탭**에서 [뷰-쓰루](/docs/ironsource-campaign-configuration#attribution-link-tab) 기여 기간의 길이를 설정합니다.

### 기본 포스트백

사용자 설치 및 리인게이지먼트 이후 아이언소스에 자동 포스트백을 보냅니다. 이 섹션을 사용하여 상기 포스트백을 보낼 수 있는 **유저 소스**를 정의할 수 있습니다.

아이언소스에 어트리뷰트된 사용자에게만 발생하는 이벤트에 대해 **이 파트너에 기여한 이벤트만** 선택합니다.  
전체 사용자 기반을 아이언소스에 리포트할 수 있도록 하려면 **파트너 또는 오가닉에 어트리뷰트되는 이벤트**를 선택합니다.

> 📘 **참고**
>
> 아이언소스는 모든 인스톨 네트워크로서 오가닉을 포함한 모든 소스에서 앱의 모든 신규 인스톨에 대한 포스트백을 수신하는 것을 선호합니다. 이렇게 하려면 **모든 파트너 또는 오가닉에 어트리뷰트된 이벤트**를 선택하여 모든 인스톨 포스트백을 아이언소스로 보내야 합니다.

<div id="in-app-event-postbacks" />

### 인앱 이벤트 포스트백

포스트백을 통해 전송된 ironSource 이벤트와 인앱이벤트의 매핑을 구성합니다.

1. **인앱 이벤트 포스트백**을 활성화하세요.
2. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버-투-서버 이벤트를 추가하세요. 다음 표는 작성해야 할 필드를 설명합니다.  

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 설치된 디바이스에서 이벤트를 활성화하고 다시 확인하세요.</li><li>**앱스플라이어 이벤트**에 입력한 다음 **사용자 지정 생성**을 클릭합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">커스텀 이벤트 매핑</Anchor>에 대해 더 알아보세요.</li></ul> |
| **파트너 이벤트에 매핑** | 파트너 측에서 정의한 각 이벤트의 고유한 이름 또는 ID입니다. 가능한 매핑 구성은 다음과 같습니다.<ul><li>**텍스트 필드:** 파트너로부터 해당 이벤트 ID를 받으세요.</li><li>**드롭다운 상자:** 가장 적합한 사전 정의된 앱스플라이어 이벤트를 선택합니다.</li><li>**그대로**: 이름 매핑 없이 이벤트를 있는 그대로 전송합니다.</li></ul> |
| **사용자용** | 이벤트 발송 옵션을 선택하세요:<ul><li>**이 파트너만**: 이 이벤트가 이 파트너에 어트리뷰션되었을 때만 포스트백을 전송합니다.</li><li>**오가닉 미디어 소스를 포함한 모든 미디어 소스**: 모든 파트너와 오가닉 이벤트에 어트리뷰션된 이벤트에 대해 포스트백을 전송합니다.</li></ul> |
| **포함** | <ul><li>**데이터 없음(기본값)**: 이벤트 값이 없는 상태에서 이벤트 자체만 전송합니다.</li><li>**가치와 수익**: 수익 값이 있는 경우 이를 **포함한** 모든 이벤트 파라미터를 전송합니다.</li><li>**수익 없는 값**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li></ul> |

3. [선택 사항] **조건 추가**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> 아이콘을 클릭하여 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>합니다.
4. **연동 저장**을 클릭하세요.
5. [선택 사항] 연동을 저장한 후 구성 페이지에 남아 있는 동안 파트너와 더 많은 귀사의 앱을 연동할 수 있습니다.
   1. 왼쪽 상단 모서리에서 파트너 이름 아래에 있는 앱 이름을 클릭하여 앱 목록을 엽니다.
   2. 드롭다운 목록에서 다른 앱을 선택합니다.
   3. 선택한 앱에 대해 <Anchor target="_blank" href="/marketers/ko/docs/amazon-ads-campaign-configuration#integration-tab">연동 단계</Anchor>를 반복합니다.

<div id="permissions-tab" />

<div id="ad-revenue-tab" />

<div id="attribution-link-tab" />

<div id="agency-permissions" />

<div id="ad-network-permissions" />

<div id="note-4" />

> 📘 **참고사항**
>
> * iOS 앱의 경우: 포스트백 및 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">리포트</Anchor>를 통해 파트너와 공유되는 데이터 제어는 **고급 개인정보 보호( iOS 14.5 이상)** <Anchor target="_blank" href="/marketers/ko/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">토글 상태</Anchor>에 따라 달라집니다.
> * <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">광고 수익 포스트백을 IronSource로 보내 광고 수익 데이터를 사용하여 캠페인을 최적화할 수 있습니다.</Anchor>광고 수익 포스트백을 IronSource로 보내 광고 수익 데이터를 사용하여 캠페인을 최적화할 수 있습니다.광고 수익 포스트백을 IronSource로 보내 광고 수익 데이터를 사용하여 캠페인을 최적화할 수 있습니다.
>   * **이벤트 이름:** af\_ad\_revenue
>   * 매핑 위치: adRevenue

<Accordion title="어트리뷰션 링크 탭">

UA 및 리타게팅 캠페인 모두에 대한 특정 캠페인, 광고 세트 또는 단일 광고를 제공하기 위해 어트리뷰션 링크를 생성하고 저장한 후 파트너에게 보냅니다. 단일 플랫폼 링크 또는 <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">원링크</Anchor>를 사용할 수 있습니다.  
<Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">어트리뷰션 링크 구조 및 파라미터에 대해 자세히 알아보십시오</Anchor>.

**어트리뷰션 링크를 생성하려면** <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">다음 지침</Anchor>을 따르십시오.  
아이언소스에서 클릭 및 뷰를 정의하는 방법에 대한 자세한 정보를 읽으십시오.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

앱스플라이어는 비용 API로 트위터 비용 정보를 가져옵니다. 지원되는 기준, 지표 및 기능에 대한 세부 정보를 얻으려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">애드 네트워크 비용 연동 표</Anchor>를 참조하세요. **참고**: 비용 데이터를 사용하려면 ROI360 구독이 필요합니다.

**비용 API를 활성화 하려면**:

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">다음 연동 지침을 따르십시오.</Anchor>

<Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">비용 API 상태와</Anchor> 앱스플라이어가 비용(및 광고 수익) 통합 상태 대시보드 또는 개별 광고 네트워크 대시보드에서 일치하는 비용 데이터를 가져온 마지막 시간을 확인합니다.

</Accordion>

<Accordion title="광고 수익 탭">

* S2S API를 통한 집약형 수준
* 기기 단위(S2S API를 통해)
* 노출 수준(SDK를 통해)
* 노출 수준(SDK를 통해)과 디바이스 수준(S2S API를 통해)

광고 수익 어트리뷰션에 대해 자세히 알아보십시오.광고 수익 어트리뷰션에 대해 자세히 알아보십시오.

* <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">이 연동 지침</Anchor>을 따르세요.

</Accordion>

<Accordion title="권한 탭">

이 탭에서는 아이언소스에 애드 네트워크, 에이전시 또는 양쪽 모두로 활동하는지에 따라 부여할 권한을 선택할 수 있습니다. 아이언소스 어트리뷰션이 비활성화되어 있더라도 권한 탭은 활성 상태이므로, 아이언소스에 권한을 부여할 수 있습니다.

이 토글을 사용하여, 앱에 대한 자체 설정 권한을 애드 네트워크에 부여할 수 있습니다.

### 애드 네트워크 권한

* **파트너 연동 설정 허용** - 파트너가 연동 탭을 설정할 수 있도록 허용(인앱이벤트 포스트백 제외)
* **인앱이벤트 포스트백 설정 허용** - 파트너가 연동 탭에서 자사와 인앱이벤트 포스트백을 매핑할 수 있도록 허용
* **리텐션 리포트 액세스 허용** - 파트너가 유입시킨 유저의 리텐션 데이터만 해당
* **종합 로열 유저 데이터 접근 허용** - 파트너 자사만의 로열 유저에만 해당
* **통합 인앱이벤트 데이터 액세스 허용** - 파트너가 유입시킨 유저의 인앱이벤트 데이터만 해당
* **종합 수익 데이터 접근 허용** - 파트너 자사에 어트리뷰션되는 수익 데이터만 해당
* **Protect360 대시보드 액세스 허용** - 파트너 자사의 Protect360 데이터에만 해당되며, 이 기능을 사용하고 있는 광고주만 부여 가능

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">애드 네트워크 권한 부여</Anchor>에 대해 자세히 알아보십시오.

### 에이전시 권한

이러한 토글을 사용하여 앱에 대한 설정 권한을 에이전시에 부여합니다.

* **기본 토글** - 에이전시 권한 옵션을 표시하려면 ON으로 설정
* **리텐션 리포트에 액세스 허용** - 해당 에이전시의 고유 리텐션 데이터에만 해당
* **통합 오가닉 데이터에 액세스 허용**
* **인앱이벤트 포스트백 설정 허용** - 에이전시가 연동 탭에서 자사와 인앱이벤트 포스트백을 매핑할 수 있도록 허용

더 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#에이전시-권한">에이전시 권한 부여</Anchor>에서 확인하세요.

</Accordion>

</Accordion>
