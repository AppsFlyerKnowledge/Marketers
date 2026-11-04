---
title: LINE 광고 플랫폼 캠페인 설정
metadata:
  keywords:
    - Advertisers
    - LINE Ads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-08-10T15:26:17Z'
  edited_at: '2026-10-14T10:39:45Z'
  id: 213050543
  locale: ko
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ko/articles/213050543
---
> **한눈에 보기:** 앱스플라이어의 연동 파트너인 LINE 광고 플랫폼은 입찰과 맞춤형 타겟팅 시스템을 결합한 플랫폼입니다. LINE 광고 플랫폼은 클릭 기반 모바일 어트리뷰션 외에도 리타겟팅 어트리뷰션을 제공하며, 이는 앱스플라이어로 기록할 수 있습니다.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/lap.png" width="71px" />

<div id="setting-up-line-ads-platform" />

## LINE 광고 플랫폼 설정

**전제 조건:** 연동을 설정하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. **활성화 방법:** 앱스플라이어에서, 측면 메뉴에서 **협업** > **파트너 마켓플레이스**를 선택하세요.  
   **편집하려면:** 앱스플라이어의 사이드 메뉴에서 **협업**> **활성화된 연동**을 선택합니다.
2. 파트너를 검색하여 선택하세요.
3. **연동 설정**을 클릭합니다. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.  
   **참고:** 파트너와 협력하는 동안 토글은 반드시 켜져<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화)</Anchor> 있어야 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

LINE 광고 플랫폼의 설정 창에는 2개의 활성 탭이 있습니다. 연동 및 어트리뷰션 링크. 아래 항목을 클릭하여 탭 설정에 대한 상세 설명을 참조하십시오.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

> 👍 **팁**
>
> * 연동 탭의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#d-general-settings">일반 설정</Anchor> 단계는 모든 파트너에게 **필수** 항목입니다
> * 나머지 모든 단계는 설명이거나 **선택** 항목입니다

<div id="integration-tab" />

<Accordion title="연동 탭">

연동 탭은 아래와 같이 다양한 섹션으로 나누어져 있습니다.

<div id="note-1" />

<div id="connect-multiple-accounts-and-apps" />

<div id="note" />

> 📘 **참고**
>
> LINE은 모든 인스톨 네트워크로서 오가닉을 포함한 모든 소스에서 앱의 모든 신규 인스톨에 대한 포스트백을 수신하는 것을 선호합니다. 이렇게 하려면 **모든 파트너에 어트리뷰션된 이벤트**를 선택하여 모든 인스톨 포스트백을 LINE으로 전송합니다. 이 작업은 계정 소유자만 수행할 수 있습니다.

<div id="activate-partner" />

### 파트너 활성화

이곳을 **처음 방문**하면 아래를 토글해야 합니다. ***파트너 활성화*** 버튼을 **켜서** 연동 탭의 파라미터 설정을 활성화합니다. 파트너와 함께 작업하는 동안에는 토글이 **켜져 있어야** 합니다.  
파트너 활성화에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

<div id="general-settings" />

### 일반 설정

**계정 ID 및 앱 ID**

LINE 광고 플랫폼은 고유한 LINE\_Ad\_account\_id 및 LINE\_Ad\_app\_ID를 통해 앱스플라이어와 연결됩니다.

* 고유한 **LINE\_Ad\_account\_id 및 LINE\_Ad\_app\_ID**를 입력합니다.


<div id="example" />

> 📄 **예시**
>
> ```http
> https://app.appsflyer.com/id123456789?pid=example_int;...<mark>line_ad_account_id=A123456789123&line_ad_app_id=1234567891234&</mark>...;redirect=false
> ```

<div id="default-postbacks" />

### 기본 포스트백

유저 인스톨 및 리인게이지먼트 이후 LINE 광고 플랫폼에 자동 포스트백을 보냅니다. 이 섹션을 사용하여 상기 포스트백을 보낼 수 있는 **유저 소스**를 정의할 수 있습니다.

LINE 광고 플랫폼에 어트리뷰션된 유저에게서만 발생하는 이벤트에 대해 **이 파트너에 어트리뷰션된 이벤트만**을 선택합니다.  
전체 유저 기반을 LINE 광고 플랫폼에 리포트할 수 있도록 하려면 **모든 파트너 또는 오가닉에 어트리뷰션된 이벤트**를 선택합니다.

<div id="in-app-events-settings" />

### 인앱 이벤트 설정

이 섹션에서는 포스트백을 통해 앱스플라이어 이벤트를 LINE 광고 플랫폼과 매핑할 수 있습니다.

1. LINE\_Ad\_app\_ID 및 LINE\_Ad\_account\_id를 다시 입력합니다.
2. 인앱 이벤트 포스트백을 ON으로 토글합니다.
3. SDK에 설정된 모든 이벤트에 대해 보내기 옵션을 선택합니다.  
   - 이 파트너에 어트리뷰션된 유저에게서**만** 발생하는 이벤트에 대해 **이 파트너에 어트리뷰션된 이벤트만**  
   - 전체 유저 기반을 해당 파트너에게 리포트할 수 있도록 하려면 **모든 파트너 또는 오가닉에 어트리뷰션된 이벤트**
4. 드롭다운 목록에서 ***SDK 이벤트 이름***을 선택합니다.
5. ***파트너 이벤트 식별자*** 드롭다운 목록에서 해당 옵션을 선택합니다.
6. ***이벤트 추가***를 클릭하여 부가적인 이벤트 이름을 추가합니다.
7. 다음 파라미터를 완성하세요.

| 파라미터 이름 | 설명 |
| --- | --- |
| **SDK 이벤트 이름** | 앱에 연동된 SDK 또는 서버 간(S2S) 이벤트에서 앱스플라이어가 수신한 이벤트의 이름입니다.  <br />**팁** - 원하는 이벤트가 목록에 없으면, 논오가닉으로 인스톨한 기기에서 이벤트를 실행하고 다시 점검해 봅니다. |
| **파트너 이벤트 식별자** | LINE 광고 플랫폼 측에 정의되어 있는 각 이벤트의 고유 이름 또는 ID입니다.  <br />LINE 광고 플랫폼에서 해당 이벤트 ID를 가져와서 텍스트 필드에 설정합니다. |
| **수익 전송** | **체크하지 않은 경우** - **af\_revenue** 파라미터에 포함된 수익 파라미터를 제외하고, 리치 인앱 이벤트의 모든 파라미터를 파트너에게 전송합니다.  <br />**선택한 경우** - 수익 값(이벤트에 존재하는 경우)을 포함하여 모든 파라미터를 전송합니다. |

<div id="custom-in-app-events-mapping" />

### 커스텀 인앱 이벤트 매핑

앱스플라이어를 사용하면 **커스텀** 파트너 이벤트 식별자 옵션을 사용하여 LINE으로 전송할 커스텀 인앱 이벤트를 매핑할 수 있습니다.

SDK에서 구성된 이벤트 이름 및 이벤트 값(이벤트 파라미터 포함)은 LINE으로 그대로 전달됩니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

UA 및 리타겟팅 캠페인 모두에 대한 특정 캠페인, 광고 세트 또는 단일 광고를 어트리뷰션하기 위해 어트리뷰션 링크를 생성하고 저장한 후 파트너에게 보냅니다. 단일 플랫폼 링크 또는 원링크를 사용할 수 있습니다.  
<Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">어트리뷰션 링크 구조 및 파라미터에 대해 더 알아보기</Anchor>.

**어트리뷰션 링크를 생성하려면** <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">다음 지침</Anchor>을 따르십시오.

<Anchor target="_blank" href="https://lineforbusiness.com/th-en/service/line-ads/manual">다음 지침에 따라</Anchor> LINE 광고 플랫폼에서 어트리뷰션 링크를 활성화하세요.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

이 파트너는 비용 데이터를 지원하지 않습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

이 파트너는 광고 수익을 지원하지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

LINE 광고 플랫폼에는 권한 설정이 제공되지 않습니다.

</Accordion>

<div data-zendesk-anchors="setting-up-line-ads-platform=line-%EA%B4%91%EA%B3%A0-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%84%A4%EC%A0%95 h_01HKW2TJ83EZSV30XH3CM0HHB7=line-%EA%B4%91%EA%B3%A0-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%84%A4%EC%A0%95 h_01HKW2TJ83XGFNKRFA672675TS=%ED%8C%81 h_01HKW2TJ83RG7W6F2PZMAY7BXZ=integration-tab h_01HKW2TJ83VEK727ZH9FPH6TPJ=%EC%B0%B8%EA%B3%A0 activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HKW2TJ83VPWD1GK99S4MY3ZB=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01HKW2TJ83PFS3TCPHKZ9HY5PE=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 connect-multiple-accounts-and-apps=%EC%B0%B8%EA%B3%A0 h_01JAA89AWAQ4JZS3522EVZZN8D=%EC%B0%B8%EA%B3%A0 01JB6YF9SFD2TWTZGR0RPVEBTC=%EC%B0%B8%EA%B3%A0 01JAT9SYW9C06P185S9TWKAFM0=%EC%98%88%EC%8B%9C default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HKW2TJ838FFTAR7NQC9WX295=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-events-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HKW2TJ833VC6SGSRNJSZ53WR=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 custom-inapp-events-mapping=%EC%BB%A4%EC%8A%A4%ED%85%80-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 h_01HKW2TJ83GQ7SFKV6YPM49QP1=%EC%BB%A4%EC%8A%A4%ED%85%80-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 h_01HKW2TJ83JPB6DSW8Z5PCY1SC=attribution-link-tab h_01HKW2TJ839R8NS3PFHCAJGXTZ=cost-tab h_01HKW2TJ835JT0WD3GN4H3XHT5=ad-revenue-tab h_01HKW2TJ83MPGHKGEMDQQYGGJ1=permissions-tab" />
