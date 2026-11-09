---
title: Bidease 캠페인 구성
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-11-13T13:17:18Z'
  edited_at: '2026-10-14T10:30:46Z'
  id: 20106343354129
  locale: ko
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ko/articles/20106343354129
---
> **한눈에 보기:**

<Image align="center" alt="bidease.png" src="https://files.readme.io/4a3373c0fdb73190017601c374ca7634cc0feb1954b6e23fc1bd9693c60605f9-20106376017041.png" width="298px" />

<div id="setting-up-bidease" />

## Medialyzer 설정

Bidease와의 통합은 클릭스루 및 뷰스루 어트리뷰션을 지원합니다.

구성 창에는 다음과 같은 탭이 포함되어 있습니다: 연동, 어트리뷰션 링크, 비용, 광고 수익, 권한. Bidease의 경우 사용 가능한 탭은 통합, 어트리뷰션 링크 및 권한입니다.

<div id="note" />

> 📘 **참고사항**
>
> * 일부 설정은 iOS와 안드로이드 기기마다 다릅니다.
> * <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner">파트너 연동 설정</Anchor>에 대해 더 알아보세요.

<div id="integration-tab" />

<Accordion title="연동 탭">

**연동** 탭에는 아래 설명된 여러 섹션이 포함되어 있습니다.

<div id="activate-partner" />

#### 파트너 활성화

**전제 조건:** **연동 설정 전에 반드시  <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락하여</Anchor> 계정을 개설하세요.**

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서**협업** > **파트너 마켓플레이스**를 선택합니다.  
   **편집 방법:** 앱스플라이어의 사이드 메뉴에서 **협업** > **활성 연동**을 선택합니다.
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭합니다. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고  **파트너 활성화** 을 켭니다.  
   **참고:** 토글은 파트너와 함께 작업하는 동안 켜져 있어야<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화되어야)</Anchor> 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

<div id="advanced-privacy" />

#### 프라이버시 강화 모드

iOS 앱의 경우에만: 포스트백 및 리포트를 통해 파트너와 공유되는 데이터 제어는 고급 개인정보 보호( iOS 14.5 이상) <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">토글 상태</Anchor>에 따라 달라집니다.

| 프라이버시 강화 모드: 켜기 | 프라이버시 강화 모드: 끄기 |
| --- | --- |
| 포스트백은 파트너에 어트리뷰션된 이벤트에 대해서만 전송됩니다. | 포스트백은 귀사의 설정에 따라 전송됩니다.<ul><li>**오가닉을 포함한 모든 미디어 소스**</li><li>**이 파트너사만**</li></ul> |
| 포스트백은 <Anchor target="_blank" href="/partners/ko/docs/advanced-privacy-guide-postback-macros-for-ad-networks">고급 개인정보 보호 템플릿</Anchor>에 따라 전송됩니다. |  |
| <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">집약된 익명 데이터</Anchor>는 파트너와 공유되므로 사용자 수준 데이터(디바이스 ID)가 공유되지 않습니다. |  |

<div id="transaction-id" />

#### 트랜잭션 ID

iOS 앱의 경우에만: SKAN 트랜잭션 ID 공유가 켜져 있으면 앱스플라이어가 SKAdNetwork 포스트백의 트랜잭션 ID를 파트너와 공유할 수 있습니다. 그러면 Reddit이 SKAdNetwork 전환 값을 디코딩할 수 있습니다.

<div id="install-attribution" />

#### 인스톨 어트리뷰션

Bidease의 뷰스루 인스톨을 어트리뷰션하려면 인스톨 뷰스루 어트리뷰션을 사용 설정하세요. 뷰-쓰루 룩백 슬라이더는 어트리뷰션 링크 탭에서 사용할 수 있습니다.

<div id="default-postbacks" />

#### 기본 포스트백

앱 실행 전에 발생하는 사용자 작업과 관련하여 파트너에게자동 포스트백을 보내기 위한 사용자 소스를 정의합니다.

* **설치**의 경우 다음 중 하나를 선택합니다.
  * 이 파트너사만 이 파트너만 해당: 인스톨이 이 파트너에게 어트리뷰션된 경우, 즉 앱을 설치한 사용자가 Bidease에서 온 경우에만 포스트백을 보냅니다.
  * 오가닉을 포함한 모든 미디어 소스

<div id="in-app-event-postbacks" />

#### 인앱 이벤트 포스트백

필요에 따라 인앱이벤트 포스트 **백 창을 설정합니다(인앱이벤트 포스트백** <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">창 구성에 대해</Anchor> 자세히 알아보기).

포스트백을 통해 전송된 Bidease 이벤트와 인앱 이벤트 매핑을 구성합니다.

1. **인앱 이벤트 포스트백**을 활성화하세요.
2. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버-투-서버 이벤트를 추가하세요. 다음 표는 작성해야 할 필드를 설명합니다.  

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 설치된 디바이스에서 이벤트를 활성화하고 다시 확인하세요.</li><li>**앱스플라이어 이벤트에** 입력한 후 **Create custom(사용자 정의 생성**)을 클릭합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">커스텀 이벤트 매핑</Anchor>에 대해 더 알아보세요.</li></ul> |
| **사용자용** | 이벤트 발송 옵션을 선택하세요:<ul><li>**이 파트너만**: 이 이벤트가 이 파트너에 어트리뷰션되었을 때만 포스트백을 전송합니다.</li><li>**오가닉 미디어 소스를 포함한 모든 미디어 소스**: 모든 파트너와 오가닉 이벤트에 어트리뷰션된 이벤트에 대해 포스트백을 전송합니다.</li></ul> |
| **포함** | <ul><li>**데이터 없음(기본값)**: 이벤트 값이 없는 상태에서 이벤트 자체만 전송합니다.</li><li>**가치와 수익**: 수익 값이 있는 경우 이를 **포함한** 모든 이벤트 파라미터를 전송합니다.</li><li>**수익 없는 값**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li></ul> |

3. [선택 사항] **조건 추가**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> 아이콘을 클릭하여 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>합니다.
4. **연동 저장**을 클릭하세요.
5. [선택 사항] 연동을 저장한 후 구성 페이지에 남아 있는 동안 더 많은 앱을 파트너와 연동할 수 있습니다.
   1. 왼쪽 상단 모서리의 파트너 이름 아래에서 앱 이름을 클릭하면 앱 목록이 열립니다.
   2. 드롭다운 목록에서 다른 앱을 선택합니다.
   3. 선택한 앱에 대해 <Anchor target="_blank" href="/marketers/ko/docs/amazon-ads-campaign-configuration#integration-tab">통합 단계를</Anchor> 반복합니다.

<div id="note-1" />

> 📘 **참고사항**
>
> **iOS 앱의 경우:** 포스트백 및 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">리포트</Anchor>를 통해 파트너와 공유되는 데이터 제어는 **고급 개인정보 보호( iOS 14.5 이상)** <Anchor target="_blank" href="/marketers/ko/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">토글 상태</Anchor>에 따라 달라집니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

UA 및 리타겟팅 캠페인 모두에 대한 특정 캠페인, 광고 세트 또는 단일 광고를 어트리뷰션하기 위해 어트리뷰션 링크를 생성하고 저장한 후 파트너에게 보냅니다. 단일 플랫폼 링크 또는 원링크를 사용할 수 있습니다. 어트리뷰션 링크 구조 및 파라미터에 대해 더 알아보기.

**어트리뷰션 링크를 생성하려면** 다음 지침을 따르십시오.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

<Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-cost-and-revenue-data">비용 데이터는</Anchor> Bidease에서 사용할 수 없습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

<Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution">광고 수익</Anchor> 은 Bidease에서 사용할 수 없습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

데이터에 액세스하고 다양한 작업을 수행할 수 있도록 Bidease <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">에 부여할 권한을</Anchor> 선택합니다.

<div id="note-2" />

> 📘 **참고사항**
>
> 권한 토글이 계속 켜져 있는 동안 연동이 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">비활성화</Anchor>되어도 권한은 계속 부여됩니다.

</Accordion>

<div data-zendesk-anchors="setting-up-bidease=medialyzer-%EC%84%A4%EC%A0%95 h_01HF4ED4B5QHY92B03426260QY=medialyzer-%EC%84%A4%EC%A0%95 h_01HF4DWFAP55JRXTR8Z65YAR68=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01HF4DWFAP4S45241VR1PJ3RFC=integration-tab activate-partner::b746d215=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HF4DWFAP9BS1G612WS5HNQ6S=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 advanced-privacy=%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94-%EB%AA%A8%EB%93%9C h_01HF4DWFAQHEJATJG6DRVMKA34=%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94-%EB%AA%A8%EB%93%9C transaction-id=%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98-id h_01HF4DWFAQ1Y1AVQ0EV63H5YJ1=%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98-id install-attribution=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HF4DWFAQQRR8XH5S7NW2NCB6=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HF4DWFAQG4YEEH3HMD61GEWE=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-event-postbacks=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HF4DWFAQQCM4TK3JJNMSM6RD=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HF4DWFAQQ3C7GBA4Q4SA6G0Y=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-1 h_01HF4DWFAQ9D9BV6PG4BEYX788=attribution-link-tab h_01HF4DWFAQT2PD4863N6EB7HHH=cost-tab h_01HF4DWFAQXMNDHWT0Y4C0M6EN=ad-revenue-tab h_01HF4DWFAQJWNFMFDEZ8XT0DM5=permissions-tab h_01HF4DWFAQJ9HRMD1FE717F1WK=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-2" />
