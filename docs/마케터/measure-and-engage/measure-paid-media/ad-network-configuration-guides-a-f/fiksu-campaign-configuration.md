---
title: Awin 캠페인 구성
metadata:
  keywords:
    - Campaign
    - SDK
    - Media Source Configuration
    - Configure
    - Fiksu
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
  created_at: '2015-03-08T13:07:42Z'
  edited_at: '2026-10-14T10:32:51Z'
  id: 207033936
  locale: ko
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ko/articles/207033936
---
> **한눈에 보기:** 클릭 기반 모바일 어트리뷰션 외에도 ByteDance Ads China는 귀사가 앱스플라이어로 기록할 수 있는 뷰-쓰루 어트리뷰션도 제공합니다.


**<span id="setting-up-fiksu"></span>전제 조건:** **연동 설정 전에 반드시  <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락하여</Anchor> 계정을 개설하세요.**

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서**협업**> **파트너 마켓플레이스**를 선택합니다.  
   **편집 방법:** 앱스플라이어의 사이드 메뉴에서 **협업** > **활성 연동**을 선택합니다.
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭합니다. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고  **파트너 활성화** 을 켭니다.  
   **참고:** 토글은 파트너와 함께 작업하는 동안 켜져 있어야<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화되어야)</Anchor> 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

연동, 어트리뷰션 링크, 권한이라는 3개의 활성 탭이 있습니다. 아래 항목을 클릭하여 탭 설정에 대한 상세 설명을 참조하십시오.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

> 👍 **팁**
>
> * 연동 탭의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#d-general-settings">일반 설정</Anchor> 단계는 모든 파트너에게 **필수** 항목입니다
> * 나머지 모든 단계는 설명이거나 **선택** 항목입니다

<div id="integration-tab" />

<Accordion title="연동 탭">

<div id="activate-partners" />

### 파트너 활성화

여기서 **첫 번째 방문**에서 연동 탭의 파라미터 설정을 사용 가능하게 하려면 ***파트너 활성화*** 버튼을 켜야 합니다. 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다.  
파트너 활성화에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

<div id="note" />

> 📘 **참고사항**
>
> LINE은 모든 인스톨 네트워크로서 오가닉을 포함한 모든 소스에서 앱의 모든 신규 인스톨에 대한 포스트백을 수신하는 것을 선호합니다.

<div id="general-settings" />

### 일반 설정

**뷰-쓰루 어트리뷰션 활성화**

뷰-쓰루 룩백 슬라이더는 어트리뷰션 링크 탭에 있습니다(아래 설명 참조).

<div id="default-postbacks" />

### 기본 포스트백

사용자 설치 및 리인게이지먼트 이후 RTB House에 자동 포스트백을 보냅니다. 이 섹션을 사용하여 상기 포스트백을 보낼 수 있는 **유저 소스**를 정의할 수 있습니다.

아이언소스에 어트리뷰트된 사용자에게만 발생하는 이벤트에 대해 **이 파트너에 기여한 이벤트만** 선택합니다.  
전체 사용자 기반을 아이언소스에 리포트할 수 있도록 하려면 **파트너 또는 오가닉에 어트리뷰트되는 이벤트**를 선택합니다.

<div id="in-app-events-settings" />

### 인앱 이벤트 설정

이 섹션에서는 포스트백을 통해 앱스플라이어 이벤트를 트위터와 매핑합니다.

1. 인앱 이벤트 포스트백을 ON으로 토글합니다.
2. SDK에 설정된 모든 이벤트에 대해 보내기 옵션을 선택합니다.  
   - 이 파트너에 어트리뷰션된 유저에게서**만** 발생하는 이벤트에 대해 **이 파트너에 어트리뷰션된 이벤트만**  
   - 전체 유저 기반을 해당 파트너에게 리포트할 수 있도록 하려면 **모든 파트너 또는 오가닉에 어트리뷰션된 이벤트**
3. SDK 이벤트를 목록에 추가하려면 **이벤트 추가**를 클릭합니다.
4. 다음 파라미터를 완성합니다.

| 파라미터 이름 | 설명 |
| --- | --- |
| **SDK 이벤트 이름** | 앱에 연동된 SDK 또는 서버 간(S2S) 이벤트에서 앱스플라이어가 수신한 이벤트의 이름입니다.  <br />**팁** - 원하는 이벤트가 목록에 없으면, 논오가닉으로 인스톨한 기기에서 이벤트를 실행하고 다시 점검해 봅니다. |
| **파트너 이벤트 식별자** | Reddit 측에 정의된 각 이벤트의 고유 이름 또는 ID입니다.  <br />아이언소스에서 해당 이벤트 ID를 가져와서 텍스트 항목에 설정합니다. |
| **수익 전송** | **체크하지 않은 경우** - **af\_revenue** 파라미터에 포함된 수익 파라미터를 제외하고, 리치 인앱 이벤트의 모든 파라미터를 파트너에게 전송합니다.  <br />**선택한 경우** - 수익 값(이벤트에 존재하는 경우)을 포함하여 모든 파라미터를 전송합니다. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

앱스플라이어는 생성된 파트너 어트리뷰션 링크를 저장하지 않음을 주의하십시오.

이 탭은 여러 섹션으로 나눠집니다.

<div id="attribution-link-parameters" />

### 어트리뷰션 링크 파라미터

이 섹션에서는 어트리뷰션 링크에 추가하고 싶은 파라미터를 선택합니다.

여기서 파라미터를 어트리뷰션 링크에 추가하면, 나중에 심층 분석을 수행할 수 있습니다. 이미 정의된 어트리뷰션 링크 파라미터를 여기에서 새 값을 추가하여 편집할 수 있습니다.

* **어트리뷰션 링크 파라미터:** c
* **어트리뷰션 링크 파라미터:** af\_adset
* **광고 이름** - 온드 미디어소스의 특정 캠페인에서 특정 광고 세트의 다양한 창작물을 비교하기 위해 광고 세트 이름을 설정합니다.  
  **어트리뷰션 링크 파라미터:** ad\_ad
* **사이트 ID** 및 **하위 사이트 ID** - 설치를 특정 퍼블리셔로 어트리뷰션 설정하려면 사이트 ID 파라미터를 설정합니다. 여러 퍼블리셔가 존재하는 경우 사이트 ID 제한을 초과하지 않도록 사용된 사이트 ID 수를 제한하고 하위 사이트 ID 파라미터를 사용하는 것이 좋습니다.  
  **어트리뷰션 링크 파라미터:** af\_siteid 및 af\_sub\_siteid
* **보조 파라미터** - 유용한 값을 삽입하기 위해 5개의 보조 파라미터 중 하나를 사용합니다. 이러한 파라미터는 분석되어 로데이터 리포트에 표시됩니다. 그래서 데이터 집계나 필터링에 매우 편리합니다.  
  **어트리뷰션 링크 파라미터:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

다른 파라미터를 새 파라미터 상자에 입력하기만 하면, 어트리뷰션 링크에 추가할 수 있습니다. 더 많은 정보는 **앱스플라이어 어트리뷰션 링크 구조와 파라미터**에서 참조하십시오.

<div id="click-through-attribution" />

### 클릭-쓰루 어트리뷰션

**클릭에서 인스톨까지의 최대 시간**을 이 슬라이더에서 설정할 수 있습니다. 기여 기간 내에 일어난 인스톨(앱 최초 실행)만 트위터로 어트리뷰션됩니다.

**어트리뷰션 링크 파라미터:** af\_click\_lookback

<Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">클릭 룩백 윈도우 관련 상세 내용은 여기</Anchor>를 참조하십시오.

<div id="click-attribution-link" />

### 클릭 어트리뷰션 링크

이것은 설정해둔 모든 설정 정보를 포함하는 어트리뷰션 링크입니다.

<div id="view-through-attribution-lookback-window" />

### 뷰-쓰루 어트리뷰션 룩백 윈도우

이 슬라이더는 **노출에서 인스톨까지의 최대 시간**을 설정합니다. 해당 인스톨에 연관된 다른 광고 클릭이 없다면, 광고 노출 이후에 이 기여 기간 내에 일어난 인스톨(앱 최초 실행)만 X Ads로 어트리뷰션됩니다.

이 값을 1-23시간 또는 1-7일로 사용자 정의할 수 있습니다.

**어트리뷰션 링크 변수:** af\_viewthrough\_lookback

더 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">여기에서 뷰-쓰루 어트리뷰션</Anchor> 항목을 참조하십시오.

<div id="impressions-attribution-link" />

### 노출 어트리뷰션 링크

노출 어트리뷰션 링크는 다른 룩백 윈도우를 제외하고 클릭 기록 링크와 유사한 어트리뷰션 데이터를 포함합니다. 일반적으로 1초 이상 광고가 노출되면 활성화되도록 파트너에게 발송합니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

Twitter에 대해서는 비용 연동을 할 수 없습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

이 파트너는 광고 수익 데이터를 지원하지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

이 탭에서는 X Ads에 애드 네트워크, 에이전시 또는 양쪽 모두로 활동하는지에 따라 부여할 권한을 선택할 수 있습니다. X Ads에 대한 어트리뷰션이 비활성화되어 있더라도 권한 탭은 활성화되어 있으며 X Ads에 제어 권한을 부여할 수 있습니다.

<div id="ad-network-permissions" />

### 애드 네트워크 권한

이 토글을 사용하여, 앱에 대한 자체 설정 권한을 애드 네트워크에 부여할 수 있습니다.

* ***파트너 연동 설정 허용*** - 파트너가 연동 탭을 설정할 수 있도록 허용 (인앱 이벤트 포스트백 제외)
* ***인앱 이벤트 포스트백 설정 허용*** - 파트너가 연동 탭에서 자사와 인앱 이벤트 포스트백을 매핑할 수 있도록 허용
* ***리텐션 리포트 액세스 허용*** - 파트너가 유입시킨 유저의 리텐션 데이터만 해당
* ***종합 로열 유저 데이터 접근 허용*** - 파트너 자사만의 로열 유저에만 해당
* ***통합 인앱 이벤트 데이터 액세스 허용** -* 파트너가 유입시킨 유저의 인앱 이벤트 데이터만 해당
* ***종합 수익 테이터 접근 허용*** - 파트너 자사에 어트리뷰션되는 수익 데이터만 해당
* ***Protect360 대시보드 접근 허용*** - 파트너 자사의 Protect360 데이터에만 해당되며, 이 기능을 사용하고 있는 광고주만 부여 가능

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">애드 네트워크 권한 부여</Anchor>에 대해 자세히 알아보십시오.

<div id="agency-permissions" />

### 에이전시 권한

이러한 토글을 사용하여 앱에 대한 설정 권한을 에이전시에 부여합니다.

* ***기본 토글*** - 에이전시 권한 옵션을 표시하려면 ON으로 설정
* *리텐션 리포트에 액세스 허용* - 해당 에이전시의 고유 리텐션 데이터에만 해당
* 통합 오가닉 데이터에 액세스 허용
* *인앱이벤트 포스트백 설정 허용* - 에이전시가 연동 탭에서 자사와 인앱이벤트 포스트백을 매핑할 수 있도록 허용

더 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#에이전시-권한">에이전시 권한 부여</Anchor>에서 확인하세요.

</Accordion>

<div data-zendesk-anchors="h_01HKWB9WVVQ64QR9YX3MH7VGEQ=setting-up-fiksu h_01HKWB9WVV59Q811JN679TP0SV=%ED%8C%81 h_01HKWB9WVVB2KTKYH4H71KYSPH=integration-tab activate-partners=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HKWB9WVWEM3JV591Y10JKSJX=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HKWB9WVWFXCANSKQ6BHSP7AC=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01HKWB9WVWZW406F39Q1Q05PPF=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HKWB9WVW2JJV6GXS6PAW8Z5D=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-events-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HKWB9WVWRWKH9YBPBA0KJXXW=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HKWB9WVWSN05C4QGGZJ1E07E=attribution-link-tab attribution-link-parameters=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HKWB9WVW907GFS5DD4Y8BA22=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 clickthrough-attribution=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HKWB9WVW55W199VX5NBVVKFK=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 click-attribution-link=%ED%81%B4%EB%A6%AD-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01HKWB9WVWK0HNABYVH9MVFYB6=%ED%81%B4%EB%A6%AD-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC viewthrough-attribution-lookback-window=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01HKWB9WVWKNPP1Y4FET06W02S=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 impressions-attribution-link=%EB%85%B8%EC%B6%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01HKWB9WVW0DE7Z290K91HVN92=%EB%85%B8%EC%B6%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01HKWB9WVXWCA9FQAS7E6V3JR8=cost-tab h_01HKWB9WVX2TETG4366S0YQAB9=ad-revenue-tab h_01HKWB9WVX4697WV73434RGZ9R=permissions-tab ad-network-permissions=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C h_01HKWB9WVXNCKD1E5Y9AG54B08=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C agency-permissions=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EA%B6%8C%ED%95%9C h_01HKWB9WVXSFDH3309H2ST85NS=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EA%B6%8C%ED%95%9C" />
