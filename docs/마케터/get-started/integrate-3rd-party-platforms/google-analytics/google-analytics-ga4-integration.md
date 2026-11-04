---
title: 구글 애널리틱스(GA4) 통합
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
  created_at: '2024-06-06T15:26:00Z'
  edited_at: '2026-10-14T10:29:14Z'
  id: 25707682812561
  locale: ko
  section: Google Analytics
  section_id: 6551226043793
  url: https://support.appsflyer.com/hc/ko/articles/25707682812561
---
> **한눈에 보기:** AppsFlyer와 구글 애널리틱스(GA4)의 통합은 광고주가 AppsFlyer에서 GA4로 귀속 데이터와 선택된 인앱 이벤트를 전송할 수 있게 해줍니다. 이 통합은 이미 [구글 애널리틱스 포 파이어베이스 SDK](https://firebase.google.com/docs/analytics)가 구현된 iOS 및 안드로이드 앱에서 작동합니다.

<div id="important" />

> 🚧 **중요!**
>
> 이 통합은 이미 [구글 애널리틱스 포 파이어베이스 SDK가 구현된](https://firebase.google.com/docs/analytics) iOS 및 안드로이드 앱에서 작동합니다.  통합이 성공하려면, AppsFlyer SDK가 Firebase SDK에서 `app_instance_id` 값을 수집해야 합니다. Firebase SDK에서 앱 인스턴스 ID를 검색하는 방법에 대한 지침을 참조하세요 [여기](#5-retrieve-app-instance-id-in-appsflyer-sdk).

<div id="how-does-it-work" />

## 어떻게 작동하나요?

* **새로운 설치가 발생할 때** **AppsFlyer가** **터치포인트 세부정보— 미디어 소스, 캠페인 이름 및 캠페인 ID를 GA4로 전송합니다.** 또한 Firebase SDK의 `app_instance_id`를 전송하여 해당 사용자의 GA4에 터치포인트가 기록되도록 합니다.
* **인앱 이벤트가 발생할 때** **GA4는** 마지막 터치포인트에 이벤트를 귀속시킵니다.

<div id="set-up-google-analytics-ga4-integration" />

## 구글 애널리틱스(GA4) 통합 설정

아래 지침을 따라 구글 애널리틱스(GA4)와의 통합을 구성하세요.

<div id="1-select-google-analytics-ga4-in-the-partner-marketplace" />

<Accordion title="1. 파트너 마켓플레이스에서 구글 애널리틱스(GA4)를 선택하세요.">

**전제 조건:** 연동을 설정하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. **활성화 방법:** 앱스플라이어에서, 측면 메뉴에서 **협업** > **파트너 마켓플레이스**를 선택하세요. **편집 방법**: 앱스플라이어의 사이드 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. **구글 애널리틱스(GA4)** 를 검색하고 선택하세요.
3. **연동 설정**을 클릭합니다. 연동 설정 페이지로 이동합니다.

구글 애널리틱스 구성에는 **통합** 탭만 포함됩니다.

파트너 설정 창 헤더에 대한 자세한 설명은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하세요.

</Accordion>

<div id="2-set-ga4-integration-in-appsflyer" />

<Accordion title="2. AppsFlyer에서 GA4 통합 설정">

다음 설정을 구성하세요:

1. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.

   **참고:** 파트너와 작업하는 동안 토글이 켜져<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화됨)</Anchor> 있어야 합니다.

   파트너 활성화에 대한 자세한 내용을 보려면 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.
2. **파이어베이스 앱 ID**에 파이어베이스 앱의 식별자를 입력하세요. 파이어베이스 앱 ID를 찾는 방법은 <Anchor target="_blank" href="https://firebase.google.com/support/faq#find-app-id">파이어베이스 문서</Anchor>를 참조하세요.
3. **API 비밀**에 구글 애널리틱스에 대한 포스트백을 인증하기 위한 API 비밀을 입력하세요. API 비밀은 구글 애널리틱스 사용자 인터페이스를 통해 생성됩니다. 비밀을 보거나 편집하거나 생성하려면 <Anchor target="_blank" href="https://support.google.com/analytics/answer/9814495?sjid=5179426966283787649-EU">Google 문서</Anchor>의 지침을 따르십시오. **웹 데이터 스트림을 선택하라는 지시를 받으면 Android 또는 iOS 데이터 스트림을 선택하십시오.**
4. 광고 ID(IDFA) 대신 고객 사용자 ID(CUID)를 전송하려면 **고객 사용자 ID**를 활성화하십시오.
5. **기본 포스트백** 섹션에서 **사용자 출처**에 대해 **유기적을 포함한 모든 미디어 소스**를 선택하십시오.

   <div id="note" />

   > 📘 **참고**
   >
   > 설치 포스트백에는 터치포인트(미디어 소스, 캠페인 이름 및 캠페인 ID)의 세부정보만 포함됩니다.


</Accordion>

<div id="3-set-in-app-event-postbacks" />

<Accordion title="3. 인앱 이벤트 포스트백을 설정합니다.">

**통합** 탭에서 AppsFlyer 인앱 이벤트를 Google Analytics(GA4) 이벤트에 매핑하고 포스트백을 통해 전송합니다.

<div id="note-1" />

> 📘 **참고**
>
> * 모바일 인앱 이벤트를 S2S를 통해 전송하는 포스트백은 지원되지 않습니다.
> * GA4는 Firebase SDK와 AppsFlyer에서 전송된 이벤트를 중복 제거하지 않습니다. 따라서 Firebase SDK를 통해 GA4에 이미 전송되지 않은 이벤트에 대해서만 인앱 이벤트 포스트백을 구성하는 것이 좋습니다.

1. **인앱 이벤트 포스트백**을 켭니다.
2. **이벤트 추가**를 클릭하여 SDK 이벤트를 목록에 추가합니다. 다음 표는 작성해야 할 필드를 설명합니다.

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱에 통합된 AppsFlyer SDK에서 수신한 이벤트의 이름입니다.<br /><br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 인스톨 및 재확인을 통해 기기에서 이벤트가 활성화되었는지 확인합니다.</li><li>앱스플라이어 이벤트에 입력한 다음 커스텀 생성을 클릭합니다.</li></ul><Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">사용자정의 이벤트 매핑</Anchor>에 대해 더 자세히 알아보십시오. |
| **mapped to partner event** | 파트너 측에서 정의한 각 이벤트의 고유한 이름 또는 ID입니다. 가능한 매핑 구성은 다음과 같습니다.<ul><li>**텍스트 필드:** 파트너로부터 해당 이벤트 ID를 받으세요.</li><li>**드롭다운 상자:** 사전 정의된 앱스플라이어 이벤트 중 가장 적합한 것을 선택합니다.</li><li>**변경 없이**: 이름 매핑 없이 이벤트를 있는 그대로 전송합니다.</li></ul> |
| **유입 출처** | 이벤트의 전송 옵션을 선택합니다.<ul><li>**오가닉을 포함한 모든 미디어 소스:** 어트리뷰션된 모든 파트너 이벤트 및 오가닉 이벤트에 대해서도 포스트백을 보냅니다.</li></ul> |
| **포함** | <ul><li>**데이터 없음(기본값)**: 이벤트 값 없이 이벤트 자체만 전송합니다.</li><li>**값 및 수익**: 이벤트에 수익 값이 포함되어 있다면, 수익 값을 포함한 모든 이벤트 파라미터를 전송해 주세요.</li><li>**수익 없는 값**: 수익 값을 제외한 모든 파라미터를 전송합니다.</li></ul> |

3. [선택 사항] **조건 추가** 아이콘 (<Image alt="condition-2.png" src="https://files.readme.io/959329be2b1286507b5c87b033785e91ab135592ae37cf3200539400832490c0-25709762755857.png" width="19px" />)을 클릭하여 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">이벤트에 대한 조건 설정</Anchor>을 합니다.
4. **연동 저장**을 클릭합니다.
5. 이벤트 포스트백 매핑 전송

</Accordion>

<div id="4-send-your-developer-the-postback-event-mapping" />

<Accordion title="4. 개발자에게 포스트백 이벤트 매핑 전송">

인앱 이벤트 매핑을 설정한 후, 각 매핑된 이벤트가 다음 열이 있는 행에 해당하는 표를 개발자에게 전송하십시오:

* **AF 이벤트:** AppsFlyer 이벤트의 이름입니다.
* **Google 이벤트에 매핑됨:** Google Analytics의 이벤트 이름입니다.

  <div id="important-1" />

  > 🚧 **중요!**
  >
  > 사용자 정의 Google Analytics 이벤트의 이름으로 [Google 예약 이벤트](#예약된-google-이벤트-이름) 중 어떤 것도 사용하지 마십시오.

* **AF 이벤트 매개변수(필수):** Google Analytics에 전송되는 이벤트 포스트백에 포함되어야 하는 미리 정의된 AppsFlyer 이벤트 매개변수입니다.

  <div id="important-2" />

  > 🚧 **중요!**
  >
  > 이벤트 정의에 모든 미리 정의된 AF 이벤트 매개변수를 표에 나열된 대로 정확히 포함하는 것은 필수입니다. 이를 준수하지 않으면 Google Analytics가 포스트백을 거부합니다.


<div id="the-event-mapping-table" />

#### 이벤트 매핑 테이블

다음 표에는 모든 Google Analytics 이벤트와 그에 대한 미리 정의된 AppsFlyer 매개변수가 포함되어 있습니다. 개발자에게 매핑한 이벤트만 포함된 표를 보내십시오.

| AF 추천 이름 (선택 사항) | Google Ads 이벤트 이름 | 미리 정의된 AF 이벤트 매개변수 (필수) |
| --- | --- | --- |
| af\_add\_payment\_info | [결제정보 추가](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_payment_info) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [add\_shipping\_info](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_shipping_info) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_add\_to\_cart | [add\_to\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_to_cart) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_add\_to\_wishlist | [add\_to\_wishlist](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_to_wishlist) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_initiated\_checkout | [begin\_checkout](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#begin_checkout) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [campaign\_details](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#campaign_details) | 캠페인 ID, 캠페인 이름 |
| af\_spent\_credits | [earn\_virtual\_currency](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#earn_virtual_currency) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | [generate\_lead](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#generate_lead) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>,<Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | Join\_group |  |
| af\_level\_achieved | [레벨업](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#level_up) |  |
| af\_login | [로그인](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#login) |  |
|  | [post\_score](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#post_score) | af\_user\_score |
| af\_purchase | [purchase](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#purchase) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content">af\_content</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_receipt_id">af\_receipt\_id</Anchor> |
|  | [refund](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#refund) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content">af\_content</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_receipt_id">af\_receipt\_id</Anchor> |
|  | [remove\_from\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#remove_from_cart) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [screen\_view](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#screen_view) |  |
| af\_search | 검색 |  |
|  | [select\_content](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_content) |  |
|  | [select\_item](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_item) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [select\_promotion](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_promotion) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [share](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#share) |  |
|  | [sign\_up](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#sign_up) |  |
|  | [spend\_virtual\_currency](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#spend_virtual_currency) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | [tutorial\_begin](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#tutorial_begin) |  |
| af\_tutorial\_completion | [tutorial\_complete](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#tutorial_complete) |  |
| af\_achievement\_unlocked | [Unlock\_achievement](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#unlock_achievement) | af\_achievement\_id |
|  | [view\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_cart) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_item](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_item) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [항목\_목록\_보기](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_item_list) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_promotion](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_promotion) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [검색 결과 보기](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_search_results) |  |
| af\_ad\_view | [ad\_impression](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#ad_impression) | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |

<div id="reserved-google-event-names" />

#### 예약된 Google 이벤트 이름

다음 이벤트 이름은 예약되어 있으며 사용자 정의 이벤트 이름으로 사용할 수 없습니다:

* `ad_activeview`
* `ad_click`
* `ad_exposure`
* `ad_query`
* `ad_reward`
* `adunit_exposure`
* `app_clear_data`
* `app_exception`
* `app_install`
* `app_remove`
* `app_store_refund`
* `app_update`
* `app_upgrade`
* `dynamic_link_app_open`
* `dynamic_link_app_update`
* `dynamic_link_first_open`
* `error`
* `firebase_campaign`
* `firebase_in_app_message_action`
* `firebase_in_app_message_dismiss`
* `firebase_in_app_message_impression`
* `first_open`
* `first_visit`
* `in_app_purchase`
* `notification_dismiss`
* `notification_foreground`
* `notification_open`
* `notification_receive`
* `notification_send`
* `os_update`
* `session_start`
* `user_engagement`

</Accordion>

<div id="5-retrieve-app-instance-id-in-appsflyer-sdk" />

<Accordion title="5. AppsFlyer SDK에서 앱 인스턴스 ID를 검색하십시오.">

앱 인스턴스 ID는 Firebase 앱의 특정 설치를 고유하게 식별합니다. 이 값은 Firebase SDK에서 SDK에 의해 검색되어야 합니다.

개발자가 다음을 구현하도록 하십시오:

1. Firebase에서 `app_instance_id` 필드를 수집하십시오.
2. 첫 번째 실행 전에 `setAdditionalData`을 호출하여 앱 인스턴스 ID(및 사용되는 경우 `ga_session_id`)를 설치, 세션 및 인앱 이벤트에 포함합니다.

<div id="important-3" />

> 🚧 **중요!**
>
> `setAdditionalData` (안드로이드 / 유니티 / 리액트 네이티브) 및 `customData` (iOS)는 **키-값 쌍의 매핑**을 수락합니다. 앱이 `app_instance_id`와 `ga_session_id`를 모두 전송하는 경우(참조: [6단계](#h_01HZQ5SESSIONID)), **같은 매핑에 함께 전송**하여 두 값이 모두 포함되도록 합니다. **별도의** `setAdditionalData` 호출로 전송하는 경우, 나중에 전송된 것이 이전 것을 덮어씁니다.

<Tabs>
<Tab title="안드로이드 native">

**Kotlin**

```kotlin
FirebaseAnalytics.getInstance(this).appInstanceId.addOnCompleteListener { task ->
   if (task.isSuccessful) {
       AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.result)
    }
}
```

java

```java
FirebaseAnalytics.getInstance(this).getAppInstanceId().addOnCompleteListener(task -> {
       if (task.isSuccessful()) {
           AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.getResult());
       }
  });
```

API 참조: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="iOS native">

**iOS native**

```swift
let appInstanceId = Analytics.appInstanceID()
    AppsFlyerLib.shared().customData = ["app_instance_id": appInstanceId]
```

**Objective C**

```objectivec
(void) fetchAnalyticsInstanceId {
           NSString *instanceID = [FIRAnalytics appInstanceID];
           [[AppsFlyerLib shared] setAdditionalData:@{@"app_instance_id": instanceID}];
}
```

API 참조: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">customData</Anchor>

</Tab>

<Tab title="Unity">

```java
using Firebase.Analytics;
    public class AnalyticsManager : MonoBehaviour
    {
        private async void Start()
        {
           AppsFlyer.initSDK(devKey, appID, this);
           string appInstanceId = await FirebaseAnalytics.GetAnalyticsInstanceIdAsync();
           Dictionary <string, string> customData = new Dictionary<string, string>();
           customData.Add("app_instance_id", appInstanceId);
           AppsFlyer.setAdditionalData(appInstanceId);
           AppsFlyer.startSDK();
        }
}
```

API 참조: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="React Native">

API 참조: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setadditionaldata">setAdditionalData</Anchor>

</Tab>
</Tabs>

</Accordion>

<div id="h_01HZQ5SESSIONID" />

<Accordion title="6. AppsFlyer SDK에서 GA4 세션 ID를 검색합니다.">

`ga_session_id`는 Firebase 앱의 세션을 고유하게 식별합니다. 이 값은 Firebase SDK에서 검색하여 `setAdditionalData` API를 사용하여 GA4로 전송해야 합니다.

개발자가 다음을 구현하도록 하십시오:

1. Firebase에서 `ga_session_id` 필드를 수집하십시오.
2. 첫 번째 실행 전에 `setAdditionalData`을 호출하여 세션 ID(및 사용되는 경우 `app_instance_id`)를 포함합니다.
3. API를 호출할 때 `ga_session_id` 키를 사용하십시오.

<div id="important-4" />

> 🚧 **중요!**
>
> `setAdditionalData` (안드로이드 / 유니티 / 리액트 네이티브) 및 `customData` (iOS)는 **키-값 쌍의 매핑**을 수락합니다. 앱이 `app_instance_id`와 `ga_session_id`를 모두 전송하는 경우(참조: [5단계](#5-retrieve-app-instance-id-in-appsflyer-sdk)), **같은 매핑에 함께 전송**하여 두 값이 모두 포함되도록 합니다. **별도의** `setAdditionalData` 호출로 전송하는 경우, 나중에 전송된 것이 이전 것을 덮어씁니다.

<Tabs>
<Tab title="Android">

**Kotlin**

```kotlin
FirebaseAnalytics.getInstance(this).sessionId.addOnCompleteListener { task ->
    if (task.isSuccessful) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.result)
    }
}
```

java

```java
FirebaseAnalytics.getInstance(this).getSessionId().addOnCompleteListener(task -> {
    if (task.isSuccessful()) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.getResult());
    }
});
```

API 참조: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="iOS네이티브 Unity">

**Swift**

```swift
if #available(iOS 14.0, *) {
    Analytics.sessionID { sessionID, error in
        if let sessionID = sessionID {
            AppsFlyerLib.shared().customData = ["ga_session_id": sessionID]
        }
    }
}
```

**Objective-C**

```objectivec
- (void)fetchAnalyticsSessionId {
    if (@available(iOS 14.0, *)) {
        [FIRAnalytics sessionIDWithCompletion:^(NSString * _Nullable sessionID, NSError * _Nullable error) {
            if (sessionID) {
                [[AppsFlyerLib shared] setAdditionalData:@{@"ga_session_id": sessionID}];
            }
        }];
    }
}
```

API 참조: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">customData</Anchor>

</Tab>

<Tab title="">

```csharp
using Firebase.Analytics;
using System.Threading.Tasks;
using AppsFlyerSDK;
using UnityEngine;
using System.Collections.Generic;

public class AnalyticsManager : MonoBehaviour
{
    private async void Start()
    {
        AppsFlyer.initSDK("yourDevKey", "yourAppID", this);

        // Get session ID
        string sessionId = await FirebaseAnalytics.GetSessionIdAsync();

        Dictionary<string, string> customData = new Dictionary<string, string>();
        customData.Add("ga_session_id", sessionId);
        AppsFlyer.setAdditionalData(customData);

        AppsFlyer.startSDK();
    }
}
```

API 참조: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setadditionaldata">setAdditionalData</Anchor>

</Tab>
</Tabs>

</Accordion>

<div id="6-validate-the-ga4-integration" />

<Accordion title="7. GA4 통합 검증">

GA4에 전송하는 포스트백의 이벤트가 Google Analytics에 등록되고 읽히는지 확인하십시오. 광고주가 데이터를 보기 위해 사용할 수 있는 두 가지 방법이 있습니다:

* [GA4 Explorations](https://support.google.com/analytics/answer/7579450?hl=en&ref_topic=12153537,12153943,2986333,&sjid=20462331341270448-EU&visit_id=638532662145815538-1056226594&rd=1#access-analysis&zippy=%2Cin-this-article)을 사용하면 모든 관련 매개변수와 함께 원시 이벤트 데이터를 탐색할 수 있습니다. **전제 조건:** [Big Query export](https://support.google.com/analytics/answer/9823238)는 귀하의 속성에서 설정해야 합니다.)
* **The Events report**는 광고주가 포스트백 이벤트를 볼 수 있게 해줍니다. 보고서는 하나 이상의 보고서 컬렉션에서 찾을 수 있습니다.  
  예를 들어, 이벤트 보고서는 [Life cycle](https://support.google.com/analytics/answer/12924233?hl=en) 또는 [Games reporting](https://support.google.com/analytics/answer/12925133?hl=en&sjid=5454549956257318969-NC) 컬렉션에서 **Engagement** > **Events** 아래에서 찾을 수 있습니다.   
  이벤트 보고서에 대한 자세한 내용은 [Google 문서](https://support.google.com/analytics/answer/12926615?sjid=5454549956257318969-NC)을 참조하십시오. [![](https://files.readme.io/01625878b13a46b8a87c34bf465c0ef6494a0f528960d62ce5535b69b29e7d0a-25707728713745.png)](https://files.readme.io/01625878b13a46b8a87c34bf465c0ef6494a0f528960d62ce5535b69b29e7d0a-25707728713745.png)
* **The Traffic acquisition report**는 웹사이트 및 앱 방문자가 어디에서 오는지 이해하는 데 도움이 됩니다.

  [Life cycle collection](https://support.google.com/analytics/answer/12924233?hl=en) 아래에서 **Acquisition** > **Traffic Acquisition**으로 이동하십시오.)

  트래픽 획득 보고서에 대한 자세한 내용은 [Google 문서](https://support.google.com/analytics/answer/12923437?hl=en&sjid=5454549956257318969-NC#zippy=%2Chow-do-i-filter-out-traffic-sources-from-the-report)을 참조하십시오.

  [![](https://files.readme.io/fa51e22d1a7941666224eb668efcbfc5a3bb8cce42cf373a82f3b1e096d2a9db-25707770926353.png)](https://files.readme.io/fa51e22d1a7941666224eb668efcbfc5a3bb8cce42cf373a82f3b1e096d2a9db-25707770926353.png)

</Accordion>

<div data-zendesk-anchors="01J9BA4J7TPNMPTWK576VG3BP4=%EC%A4%91%EC%9A%94 set-up-google-analytics-ga4-integration=%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%98%EB%82%98%EC%9A%94 h_01HZXY8R12MQWKNHX2BXA68MR3=%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%98%EB%82%98%EC%9A%94 h_01J35AP3FF599P0XA8VPWTS5R9=%EA%B5%AC%EA%B8%80-%EC%95%A0%EB%84%90%EB%A6%AC%ED%8B%B1%EC%8A%A4ga4-%ED%86%B5%ED%95%A9-%EC%84%A4%EC%A0%95 h_01HZQ4ABBMC8D23K36V5P8T23R=1-select-google-analytics-ga4-in-the-partner-marketplace h_01HZQ4ABBMKEF619ZTDXVYWHEK=2-set-ga4-integration-in-appsflyer h_01J35CWSD6MGAR0Y76EEEHKFH6=%EC%B0%B8%EA%B3%A0 h_01HZQ4ABBME2A42V738S6K84HX=3-set-in-app-event-postbacks h_01J35DVVAVW9DSVTX0VRSYH5KX=%EC%B0%B8%EA%B3%A0-1 h_01HZQ4ABBMQZMCYGMMAE20TRXV=4-send-your-developer-the-postback-event-mapping h_01HZQ4ABBMR9REVXRDC09B25QT=%EC%A4%91%EC%9A%94-1 h_01HZQ4ABBN6VC1DX3CK39RNEFG=%EC%A4%91%EC%9A%94-2 the-event-mapping-table=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91-%ED%85%8C%EC%9D%B4%EB%B8%94 h_01HZQ4ABBN0YEVFJXBNS0HTSQ5=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91-%ED%85%8C%EC%9D%B4%EB%B8%94 reserved-google-event-names=%EC%98%88%EC%95%BD%EB%90%9C-google-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%9D%B4%EB%A6%84 h_01HZQ4ABBN6ZEB7RJQMFS0AB73=%EC%98%88%EC%95%BD%EB%90%9C-google-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%9D%B4%EB%A6%84 h_01HZQ4ABBN3D3T8A2Y5N428884=5-retrieve-app-instance-id-in-appsflyer-sdk h_01KH6GJX5RM895G51ZXN8VJDMF=%EC%A4%91%EC%9A%94-4 6-retrieve-ga4-session-id-in-the-appsflyer-sdk=h_01HZQ5SESSIONID h_01KH6HDB7A2FH4ZQY1PRKPQBPM=%EC%A4%91%EC%9A%94-4 h_01HZQ4ABBN4JA16D9RZHERFE63=6-validate-the-ga4-integration" />
