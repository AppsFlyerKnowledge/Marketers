---
title: RTB House 캠페인 구성
metadata:
  keywords:
    - Advertisers
    - RTB
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-07-05T08:30:48Z'
  edited_at: '2026-10-14T10:35:20Z'
  id: 360001274325
  locale: ko
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ko/articles/360001274325
---
> **한눈에 보기:** 앱스플라이어 애드 네트워크 통합 파트너인 RTB House는 이커머스 및 게임 기업을 위한 리타겟팅 기술을 제공합니다. RTB House는 실시간 입찰 모델에서 온라인 광고를 구매하기 위한 딥 러닝 알고리즘을 기반으로 하는 자체 리타겟팅 솔루션을 개발했습니다. RTB House는 클릭 기반 모바일 어트리뷰션 외에도 리타겟팅 어트리뷰션을 제공하며, 이는 앱스플라이어로 기록할 수 있습니다.

## RTB House 설정

**전제 조건:**  연동 설정 전에 반드시  <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락하여</Anchor> 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서협업<strong>></strong>파트너 마켓플레이스**를 선택합니다.  
   **편집 방법:** 앱스플라이어의 사이드 메뉴에서 **협업** > 활성 연동을 선택합니다.**
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 선택합니다.  
   **참고:** 파트너와 함께 작업하는 동안에는 토글이 켜져 있어야(<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">활성화</Anchor>) 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

RTB House의 구성 창에는 연동, 어트리뷰션 링크, 권한이라는 3개의 활성 탭이 있습니다. 아래 항목을 클릭하여 탭 설정에 대한 상세 설명을 참조하십시오.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

> 👍 **팁**
>
> * 연동 탭의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#d-general-settings">일반 설정</Anchor> 단계는 모든 파트너에게 **필수** 항목입니다
> * 나머지 모든 단계는 설명이거나 **선택** 항목입니다

<div id="integration-tab" />

<Accordion title="연동 탭">

연동 탭은 아래와 같이 다양한 섹션으로 나누어져 있습니다.

### 파트너 활성화

여기 **첫 번째 방문**에서 연동 파라미터 설정을 사용 가능하게 하려면 **파트너 활성화**를 설정해야 합니다. 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다.  
파트너 활성화에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

### 기본 포스트백

사용자 설치 및 리인게이지먼트 이후 RTB House에 자동 포스트백을 보냅니다. 이 섹션을 사용하여 상기 포스트백을 보낼 수 있는 **유저 소스**를 정의할 수 있습니다.

> 📘 **참고**
>
> RTB House는 모든 인스톨 네트워크로서 오가닉을 포함한 모든 소스에서 앱의 모든 신규 인스톨에 대한 포스트백을 수신하는 것을 선호합니다. 이렇게 하려면 **모든 파트너에 어트리뷰션된 이벤트**를 선택하여 모든 인스톨 포스트백을 RTB House로 전송합니다.

### 인앱 이벤트 설정

이 섹션에서는 포스트백을 통해 앱스플라이어 이벤트를 RTB House와 매핑합니다.

#### 리전

RTB House 데이터 센터의 리전을 입력합니다. 가능한 옵션은 **emea**, **us**, **asia**입니다.

#### 인앱 이벤트 포스트백 설정

1. 인앱 이벤트 포스트백을 켭니다.
2. SDK에 설정된 모든 이벤트에 대해 보내기 옵션을 선택합니다.  
   - 이 파트너에 어트리뷰션된 유저에게서**만** 발생하는 이벤트에 대해 **이 파트너에 어트리뷰션된 이벤트만**  
   - 전체 유저 기반을 해당 파트너에게 리포트할 수 있도록 하려면 **모든 파트너 또는 오가닉에 어트리뷰션된 이벤트**
3. SDK 이벤트를 목록에 추가하려면 **이벤트 추가**를 클릭합니다.
4. 다음 파라미터를 완성합니다.

| 파라미터 이름 | 설명 |
| --- | --- |
| **SDK 이벤트 이름** | 앱에 연동된 SDK 또는 서버 간(S2S) 이벤트로부터 앱스플라이어가 수신한 이벤트 이름입니다.  <br />**팁** - 원하는 이벤트가 목록에 없으면, 논오가닉으로 인스톨한 기기에서 이벤트를 실행하고 다시 점검해 봅니다. |
| **파트너 이벤트 식별자** | RTB House 측에 정의된 각 이벤트의 고유 이름 또는 ID입니다.  <br />RTB House에서 해당 이벤트 ID를 가져와 텍스트 필드에 설정합니다. |
| **수익 전송** | **체크하지 않은 경우** - **af\_revenue** 파라미터에 포함된 수익 파라미터를 제외하고, 리치 인앱 이벤트의 모든 파라미터를 파트너에게 전송합니다.  <br />**선택한 경우** - 수익 값(이벤트에 존재하는 경우)을 포함하여 모든 파라미터를 전송합니다. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

UA 및 리타겟팅 캠페인 모두에 대한 특정 캠페인, 광고 세트 또는 단일 광고를 어트리뷰션하기 위해 어트리뷰션 링크를 생성하고 저장한 후 파트너에게 보냅니다. 단일 플랫폼 링크 또는 <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">원링크</Anchor>를 사용할 수 있습니다.  
<Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">어트리뷰션 링크 구조 및 파라미터에 대해 더 알아보기</Anchor>.  

**어트리뷰션 링크를 생성하려면** <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">다음 지침</Anchor>을 따르십시오.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

이 파트너와 연동 시 비용 데이터는 지원되지 않습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

이 파트너와 연동 시 광고 수익은 지원되지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

이 탭에서는 RTB House에 애드 네트워크, 에이전시 또는 양쪽 모두로 활동하는지에 따라 부여할 권한을 선택할 수 있습니다. RTB House에 대한 어트리뷰션이 비활성화되어 있더라도 권한 탭은 활성화되어 있으며 RTB House에 제어 권한을 부여할 수 있습니다.

### 애드 네트워크 권한

이 토글을 사용하여, 앱에 대한 자체 설정 권한을 애드 네트워크에 부여할 수 있습니다.

* ***파트너 연동 설정 허용*** - 파트너가 연동 탭을 설정할 수 있도록 허용 (인앱 이벤트 포스트백 제외)
* ***인앱 이벤트 포스트백 구성 허용*** - 파트너가 통합 탭에서 자체적으로 매핑되는 인앱 이벤트 포스트백을 설정하도록 허용
* ***리텐션 리포트 액세스 허용*** - 파트너가 유입시킨 유저의 리텐션 데이터만 해당
* ***종합 로열 유저 데이터 접근 허용*** - 파트너 자사만의 로열 유저에만 해당
* ***통합 인앱 이벤트 데이터 액세스 허용** -* 파트너가 유입시킨 유저의 인앱 이벤트 데이터만 해당
* ***종합 수익 테이터 접근 허용*** - 파트너 자사에 어트리뷰션되는 수익 데이터만 해당
* ***Protect360 대시보드 접근 허용*** - 파트너 자사의 Protect360 데이터에만 해당되며, 이 기능을 사용하고 있는 광고주만 부여 가능

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">애드 네트워크 권한 부여</Anchor>에 대해 자세히 알아보십시오.

</Accordion>

<div data-zendesk-anchors="setting-up-rtb-house=rtb-house-%EC%84%A4%EC%A0%95 h_01HJRZXXH277REM62TJA907WX0=rtb-house-%EC%84%A4%EC%A0%95 h_01HJRZXXH2P8Q15V7DKQT7AVTT=%ED%8C%81 h_01HJRZXXH2DJ8WMYPQ0NV08R05=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HJRZXXH309BVZZ2VRRJQ02N8=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HJRZXXH3X46N8KQ8GTP4BYYP=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HJRZXXH3SDCH4K86YV4VC5VH=%EC%B0%B8%EA%B3%A0 inapp-events-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HJRZXXH3HJP28D34NW8A8EZN=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 region=%EB%A6%AC%EC%A0%84 h_01HJRZXXH3E7STC8XVRDP39282=%EB%A6%AC%EC%A0%84 inapp-event-postback-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%84%A4%EC%A0%95 h_01HJRZXXH3336ZJZZD1P8408GP=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%84%A4%EC%A0%95 h_01HJRZXXH3R7F4QA9PYWY7EYZZ=attribution-link-tab h_01HJRZXXH30PDV0S32THB0C4FM=cost-tab h_01HJRZXXH37CHDD10ASEXPN7VH=ad-revenue-tab h_01HJRZXXH3CASE2ZTRJDSW9545=permissions-tab ad-network-permissions=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C h_01HJRZXXH3TJSTVG4Z8ZDQBATG=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C" />
