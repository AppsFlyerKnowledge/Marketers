---
title: 인앱 이벤트 - 이벤트 구조
metadata:
  keywords:
    - iOS
    - Android
    - In-App Events
    - In-App
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:09:16Z'
  edited_at: '2026-10-14T10:27:24Z'
  id: 4410481112081
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/4410481112081
---
> **한눈에 보기:** 사전 정의된 이벤트 이름 목록과 이벤트 파라미터를 확인하여, 앱 설치 후 인앱 이벤트(예: 로그인, 가입, 인앱 구매)를 기록하세요.

<div id="overview" />

## 개요

인앱 이벤트를 발송하려면, 귀사의 개발자가 해당 코드 구현을 해야 합니다. 본 문서는 사전 정의된 이벤트 이름과 사전 정의된 파라미터에 대해 설명합니다.

어떤 이벤트와 파라미터를 기록할지 판단하는 데 도움이 되도록, 비즈니스 분야별 예시와 흐름을 포함한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#recommended-events-by-business-vertical">문서</Anchor>를 참고하세요.

<div id="lead-lead" />

<div id="app-open-af_app_opened" />

<div id="predefined-event-names" />

## 사전 정의된 이벤트 이름

다음 섹션에서는 Meta Ads, Google Ads, TikTok, Snap, X Ads 및 Criteo에 사용되는 사전 정의된 이벤트 이름과 이벤트 매핑 목록을 제공합니다.

각 이벤트 이름에는 해당 이벤트와 관련된 일반적으로 사전 정의된 이벤트 파라미터도 포함됩니다. 귀사의 비즈니스 요구에 맞춰 이벤트 파라미터를 포함하도록 선택할 수 있습니다.

<div id="achievement-unlocked-af_achievement_unlocked" />

<Accordion title="업적 잠금 해제(af_achievement_unlocked)">

**설명**: 업적 잠금 해제 이벤트를 기록하는 데 사용됩니다.

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_achievement\_unlocked | fb\_mobile\_achievement\_unlocked | unlock\_achievement | UnlockAchievement | ACHIEVEMENT\_UNLOCKED | ACHIEVEMENT\_UNLOCKED | - | 성취 |

**일반적인 파라미터:**

링크를 클릭하여 SRN에 대한 매핑을 확인하세요.

* [af\_설명](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="ad-click-af_ad_click" />

<Accordion title="광고 클릭(af_ad_click)">

**설명**: 앱에 표시된 광고의 클릭을 기록하는 데 사용됩니다.

**이벤트 매핑**:

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_ad\_click | AdClick | - | InAppADClick | AD\_CLICK | - | - | - |

**일반적인 파라미터:**

링크를 클릭하여 SRNs에 대한 매핑을 확인하세요.

* [af\_광고\_유형](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="ad-view-af_ad_view" />

<Accordion title="광고 보기(af_ad_view)">

**설명**: 앱에 표시된 광고의 조회수를 기록하는 데 사용됩니다.

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_ad\_view | AdImpression | - | InAppADImpr | AD\_VIEW | - | - | - |

**일반적인 파라미터:**

링크를 클릭하여 SRNs에 대한 매핑을 확인하세요.

* [af\_광고\_유형](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="결제 정보 추가(af_add_payment_info)">

**설명**: 결제 정보 구성 상태를 기록하는 데 사용됩니다.

**다음 업종에 나타납니다: <Anchor target="_blank" href="/marketers/ko/docs/recommended-ride-hailing-app-events#add-payment-info-af_add_payment_info">라이드 헤일링</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-flight-booking-app-events#add-payment-info-af_add_payment_info">항공편 예약</Anchor>**

**이벤트 매핑**:

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_add\_payment\_info | fb\_mobile\_add\_payment\_info | 결제정보 추가 | AddPaymentInfo | ADD\_BILLING | ADDED\_PAYMENT\_INFO | - | ADD\_BILLING |

**일반적인 파라미터:**

링크를 클릭하여 SRN에 대한 매핑을 확인하세요.

* [af\_success](/docs/in-app-events-event-structure#af_success)

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="장바구니에 추가 (af_add_to_cart)">

**설명**: 특정 품목의 장바구니 추가 이벤트를 기록하는 데 사용됩니다. 여러 항목이 포함된 이벤트를 리포트하려면 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">여기</Anchor>를 클릭하세요.

**다음 업종에 나타남:** <Anchor target="_blank" href="/marketers/ko/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart">이커머스</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-healthcare-app-events#add-to-cart-af_add_to_cart">헬스케어</Anchor>

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_add\_to\_cart | fb\_mobile\_add\_to\_cart | add\_to\_cart | AddToCart | ADD\_CART | ADD\_TO\_CART | ADD\_TO\_SHOPPING\_CART | viewBasket |

**일반적인 파라미터:**

링크를 클릭하여 SRNs에 대한 매핑을 확인하세요.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="위시리스트에 추가 (af_add_to_wishlist)">

**설명**: 특정 항목을 위시리스트에 추가하는 이벤트를 기록하는 데 사용됩니다. 여러 항목이 포함된 이벤트를 리포트하려면 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">여기</Anchor>를 클릭하세요.

**다음 업종에 나타남:** <Anchor target="_blank" href="/marketers/ko/docs/recommended-ecommerce-app-events#add-to-wishlist-af_add_to_wishlist">이커머스</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-hotel-booking-app-events#add-to-wishlist-af_add_to_wishlist">호텔 예약</Anchor>

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_add\_to\_wishlist | fb\_mobile\_add\_to\_wishlist | add\_to\_wishlist | AddToWishlist | ADD\_TO\_WISHLIST | ADD\_TO\_WISHLIST | - | - |

**일반적인 파라미터:**

링크를 클릭하여 SRNs에 대한 매핑을 확인하세요.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="등록 완료 (af_complete_registration)">

**설명**: 유저 등록 방법을 기록하는 데 사용됩니다.

**다음 업종에 나타납니다:** <Anchor target="_blank" href="/marketers/ko/docs/recommended-gaming-app-events#complete-registration-af_complete_registration">게임</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-ecommerce-app-events#complete-registration-af_complete_registration">이커머스</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-entertainment-app-events#complete-registration-af_complete_registration">엔터테인먼트</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-finance-and-banking-app-events#complete-registration-af_complete_registration">금융 및 은행업</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-p2p-lending-app-events#complete-registration-af_complete_registration">P2P 대출</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-online-education-app-events#complete-registration-af_complete_registration">온라인 교육</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-ride-hailing-app-events#complete-registration-af_complete_registration">택시 호출</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-hotel-booking-app-events#complete-registration-af_complete_registration">호텔 예약</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-healthcare-app-events#complete-registration-af_complete_registration">헬스케어</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-telecommunication-app-events#complete-registration-af_complete_registration">통신</Anchor>

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_complete\_registration | fb\_mobile\_complete\_registration | sign\_up | Registration | SIGN\_UP | SIGN\_UP | SIGN\_UP | - |

**일반적인 파라미터:**

링크를 클릭하여 SRN에 대한 매핑을 확인하세요.

* [af\_registration\_method](/docs/in-app-events-event-structure#af_registration_method)

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="콘텐츠 보기 (af_content_view)">

**설명**: 콘텐츠 보기 이벤트를 기록하는 데 사용됩니다. 여러 항목이 포함된 이벤트를 리포트하려면 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">여기</Anchor>를 클릭하세요.

**다음 업종에 나타남:** <Anchor target="_blank" href="/marketers/ko/docs/recommended-ecommerce-app-events#content-view-af_content_view">이커머스</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-flight-booking-app-events#content-view-af_content_view">항공편 예약</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-hotel-booking-app-events#content-view-af_content_view">호텔 예약</Anchor>

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_content\_view | fb\_mobile\_content\_view | view\_item | ViewContent | VIEW\_CONTENT | CONTENT\_VIEW | PAGE\_VIEW | viewProduct |

**일반적인 파라미터:**

귀사의 비즈니스에 맞는 파라미터를 클릭하여 SRN 매핑을 확인하세요.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_추천\_호텔](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_호텔\_점수](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_구매\_화폐](/docs/in-app-events-event-structure#af_purchase_currency)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="결제 시작(af_initiated_checkout)">

**설명**: 결제 이벤트를 기록하는 데 사용됩니다. 여러 항목이 포함된 이벤트를 리포트하려면 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">여기</Anchor>를 클릭하세요.

**관련 분야:** <Anchor target="_blank" href="/marketers/ko/docs/recommended-ecommerce-app-events#initiated-checkout-af_initiated_checkout">이커머스</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-hotel-booking-app-events#initiated-checkout-af_initiated_checkout">호텔 예약</Anchor>

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_initiated\_checkout | fb\_모바일\_결제\_시작 | 결제 시작 | 결제 | 시작\_결제 | 결제\_시작됨 | 결제 | viewBasket |

**일반적인 파라미터:**

귀사의 비즈니스에 맞는 파라미터를 클릭하여 SRN 매핑을 확인하세요.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)
* [af\_payment\_info\_available](/docs/in-app-events-event-structure#af_payment_info_available)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_추천\_호텔](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_호텔\_점수](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_구매\_화폐](/docs/in-app-events-event-structure#af_purchase_currency)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="invite-af_invite" />

<Accordion title="초대 (af_invite)">

**설명**: 초대(소셜) 이벤트를 기록하는 데 사용됩니다.

**다음 업종에 나타납니다:** <Anchor target="_blank" href="/marketers/ko/docs/recommended-gaming-app-events#invite-af_invite">게임</Anchor>

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_초대 | - | 초대 | - | 초대 | 초대 | - | - |

**일반적인 파라미터:**

링크를 클릭하여 SRN에 대한 매핑을 확인하세요.

* [af\_설명](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="수준 달성 (af_level_achieved)">

**설명**: 게임 수준 이벤트를 기록하는 데 사용됩니다.

**다음 업종에 나타납니다: <Anchor target="_blank" href="/marketers/ko/docs/recommended-gaming-app-events#level-achieved-af_level_achieved">게임</Anchor>**

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_수준\_달성 | fb\_모바일\_수준\_달성 | 레벨업 | 수준\_달성 | 수준\_완료 | 수준\_달성 | - | 사용자 수준 |

**일반적인 파라미터:**

링크를 클릭하여 SRNs에 대한 매핑을 확인하세요.

* [af\_수준](/docs/in-app-events-event-structure#af_level)
* [af\_점수](/docs/in-app-events-event-structure#af_score)

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="목록 보기 (af_list_view)">

**설명**: 목록 보기 이벤트를 기록하는 데 사용됩니다.

**관련 분야:** <Anchor target="_blank" href="/marketers/ko/docs/recommended-ecommerce-app-events#list-view-af_list_view">이커머스</Anchor>

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_목록\_보기 | - | 항목\_목록\_보기 | - | 목록\_보기 | - | - | 목록\_보기 |

**일반적인 파라미터:**

링크를 클릭하여 SRNs에 대한 매핑을 확인하세요.

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)

</Accordion>

<div id="login-af_login" />

<Accordion title="로그인 (af_login)">

**설명**: 유저 로그인 이벤트를 기록하는 데 사용됩니다.

**다음 업종에 나타납니다:** <Anchor target="_blank" href="/marketers/ko/docs/recommended-gaming-app-events#login-af_login">게임</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-ecommerce-app-events#login-af_login">이커머스</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-entertainment-app-events#login-af_login">엔터테인먼트</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-finance-and-banking-app-events#login-af_login">금융 및 은행업</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-online-education-app-events#login-af_login">온라인 교육</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-hotel-booking-app-events#login-af_login">호텔 예약</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-healthcare-app-events#login-af_login">헬스케어</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-telecommunication-app-events#login-af_login">통신</Anchor>

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_로그인 | - | 로그인 | 로그인 | 로그인 | 로그인 | - | - |

</Accordion>

<div id="opened-from-push-notification-af_opened_from_push_notification" />

<Accordion title="푸시 알림에서 열림(af_opened_from_push_notification)">

**설명**: 푸시 알림에서 앱 오픈을 기록하는 데 사용됩니다.

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_opened\_from\_push\_notification | - | 알림\_열림 | - | - | - | - | - |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="구매 (af_purchase)">

**설명**: 구매 이벤트를 기록하고 수익을 연관시키는 데 사용됩니다. 앱스플라이어에서 지원하는 통화 기호 목록을 보려면 <Anchor target="_blank" href="https://docs.openexchangerates.org/docs/supported-currencies">여기</Anchor>를 클릭하세요. 여러 항목이 포함된 이벤트를 리포트하려면 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">여기</Anchor>를 클릭하세요.

**관련 분야: <Anchor target="_blank" href="/marketers/ko/docs/recommended-gaming-app-events#purchase-af_purchase">게임</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-ecommerce-app-events#purchase-af_purchase">이커머스</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-online-education-app-events#purchase-af_purchase">온라인 교육</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-healthcare-app-events#purchase-af_purchase">헬스케어</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-telecommunication-app-events#purchase-af_purchase">통신</Anchor>**

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_구매 | fb\_mobile\_purchase | 앱 내 구매 | Purchase | PURCHASE | PURCHASE | OFF\_AMAZON\_PURCHASES | transactionConfirmation |

**일반적인 파라미터:**

귀사의 비즈니스에 맞는 파라미터를 클릭하여 SRN 매핑을 확인하세요.

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)
* [af\_검증됨](/docs/in-app-events-event-structure#af_validated)
* [af\_영수증\_ID](/docs/in-app-events-event-structure#af_receipt_id)
* [af\_주문\_ID](/docs/in-app-events-event-structure#af_order_id)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_추천\_호텔](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_호텔\_점수](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_구매\_화폐](/docs/in-app-events-event-structure#af_purchase_currency)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="rate-af_rate" />

<Accordion title="평가 (af_rate)">

**설명**: 앱/항목 평가 이벤트를 기록하는 데 사용됩니다. 여러 항목이 포함된 이벤트를 리포트하려면 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">여기</Anchor>를 클릭하세요.

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_rate | fb\_모바일\_평가 | 평가\_제출 | 평가 | 평가 | 평가 완료됨 | - | - |

**일반적인 파라미터:**

링크를 클릭하여 SRNs에 대한 매핑을 확인하세요.

* [af\_rating\_value](/docs/in-app-events-event-structure#af_rating_value)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_max\_rating\_value](/docs/in-app-events-event-structure#af_max_rating_value)

</Accordion>

<div id="reengage-af_re_engage" />

<Accordion title="리인게이지 (af_re_engage)">

**설명**: 유저 리인게이지먼트 이벤트를 기록하는 데 사용됩니다.

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_re\_engage | - | 커스텀 이벤트 | - | 리인게이지 | - | - |

**일반적인 파라미터:**

링크를 클릭하여 SRN에 대한 매핑을 확인하세요.

* [af\_설명](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="search-af_search" />

<Accordion title="검색 (af_search)">

**설명**: 검색 이벤트를 기록하는 데 사용됩니다

**다음 산업 분야에서 사용:** <Anchor target="_blank" href="/marketers/ko/docs/recommended-ecommerce-app-events#search-af_search">이커머스</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-flight-booking-app-events#search-af_search">항공편 예약</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-hotel-booking-app-events#search-af_search">호텔 예약</Anchor>

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_search | fb\_mobile\_search | 검색 결과 보기 | 검색 | 검색 | 검색 | 검색 | viewSearch |

**일반적인 파라미터:**

귀사의 비즈니스에 맞는 파라미터를 클릭하여 SRN 매핑을 확인하세요.

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_search\_string](/docs/in-app-events-event-structure#af_search_string)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_추천\_호텔](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_호텔\_점수](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_구매\_화폐](/docs/in-app-events-event-structure#af_purchase_currency)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="share-af_share" />

<Accordion title="공유 (af_share)">

**설명**: 공유 이벤트를 기록하는 데 사용됩니다

**다음 업종에 나타납니다:** <Anchor target="_blank" href="/marketers/ko/docs/recommended-gaming-app-events#share-af_share">게임</Anchor>

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_share | - | share | - | SHARE | SHARE | - | - |

**일반적인 파라미터:**

링크를 클릭하여 SRN에 대한 매핑을 확인하세요.

* [af\_설명](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="지출된 크레딧 (af_spent_credits)">

**설명**: 크레딧 지출 이벤트를 기록하는 데 사용합니다. 여러 항목이 포함된 이벤트를 리포트하려면 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">여기</Anchor>를 클릭하세요.

**세로 섹션에 나타남:** <Anchor target="_blank" href="/marketers/ko/docs/recommended-ride-hailing-app-events#spent-credits-af_spent_credits">승차 공유 서비스</Anchor>

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_spent\_credits | fb\_mobile\_spent\_credits | 가상 화폐 지출 | 지출크레딧 | SPENT\_CREDITS | SPENT\_CREDITS | - | transactionConfirmation |

**일반적인 파라미터:**

링크를 클릭하여 SRNs에 대한 매핑을 확인하세요.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="start-trial-af_start_trial" />

<Accordion title="체험 시작 (af_start_trial)">

**설명**: 제품의 무료 체험 시작을 기록하기 위해 사용됩니다.

**다음 업종에 나타납니다:** <Anchor target="_blank" href="/marketers/ko/docs/recommended-entertainment-app-events#start-trial-af_start_trial">엔터테인먼트</Anchor>

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_start\_trial | StartTrial | - | StartTrial | START\_TRIAL | - | - | - |

**일반적인 파라미터:**

링크를 클릭하여 SRNs에 대한 매핑을 확인하세요.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

<div id="note" />

> 📘 **참고**
>
> 이 이벤트를 Meta ads StartTrial 이벤트와 매핑하고 수익을 연관시키려면 af\_revenue 대신 af\_price 파라미터를 사용하세요.

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="구독 (af_subscribe)">

**설명**: 유료 구독 구매를 기록하는 데 사용됩니다.

**다음 업종에 나타납니다:** <Anchor target="_blank" href="/marketers/ko/docs/recommended-entertainment-app-events#subscription-af_subscribe">엔터테인먼트</Anchor>

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_subscribe | Subscribe | - | Subscribe | SUBSCRIBE | - | SUBSCRIBE | SUBSCRIBE |

**일반적인 파라미터:**

링크를 클릭하여 SRNs에 대한 매핑을 확인하세요.

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="여행 예약 (af_travel_booking)">

**설명**: 여행 예약 이벤트를 기록하고 이에 수익을 연관하는 데 사용됩니다. 여러 항목이 포함된 이벤트를 리포트하려면 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">여기</Anchor>를 클릭하세요.

**다음 업종에 나타납니다:** <Anchor target="_blank" href="/marketers/ko/docs/recommended-flight-booking-app-events#travel-booking-af_travel_booking">항공편 예약</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-hotel-booking-app-events#travel-booking-af_travel_booking">호텔 예약</Anchor>

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_travel\_booking | fb\_mobile\_purchase | ecommerce\_purchase | Purchase | RESERVE | PURCHASE | - | transactionConfirmation |

**일반적인 파라미터:**

귀사의 비즈니스에 맞는 파라미터를 클릭하여 SRN 매핑을 확인하세요.

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_customer\_user\_id](/docs/in-app-events-event-structure#af_customer_user_id)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_추천\_호텔](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_호텔\_점수](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_구매\_화폐](/docs/in-app-events-event-structure#af_purchase_currency)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)
* [af\_주문\_ID](/docs/in-app-events-event-structure#af_order_id)

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="튜토리얼 완료 (af_tutorial_completion)">

**설명**: 튜토리얼 완료를 기록하는 데 사용됩니다. 여러 항목이 포함된 이벤트를 리포트하려면 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">여기</Anchor>를 클릭하세요.

**다음 업종에 나타납니다:** <Anchor target="_blank" href="/marketers/ko/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">게임</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">온라인 교육</Anchor>

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_tutorial\_completion | fb\_mobile\_tutorial\_completion | tutorial\_complete | CompleteTutorial | COMPLETE\_TUTORIAL | TUTORIAL\_COMPLETE | - | - |

**일반적인 파라미터:**

링크를 클릭하여 SRNs에 대한 매핑을 확인하세요.

* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="update-af_update" />

<Accordion title="업데이트 (af_update)">

**설명**: 업데이트 이벤트를 기록하는 데 사용됩니다. 여러 항목이 포함된 이벤트를 리포트하려면 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">여기</Anchor>를 클릭하세요.

**이벤트 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_update | - | app\_update | - | UPDATE | - | - |

**일반적인 파라미터:**

링크를 클릭하여 SRN에 대한 매핑을 확인하세요.

* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)

</Accordion>

<div id="note-1" />

> 📘 **참고**
>
> 이 섹션에서 설명된 미리 정의된 이벤트 이름 이외에도 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-in-app-event-mapping#사전-정의된-이벤트-매핑">Meta Ads는 속성 없이 전송되는 추가 이벤트</Anchor>를 제공합니다.

<div id="predefined-event-parameters" />

## 미리 정의된 Event Parameter

다음 섹션에서는 미리 정의된 Event Parameter 목록을 제공합니다. 각 Event Parameter는 Meta Ads, Google Ads, Snap, X Ads 및 Criteo에 대한 매핑이 포함되어 있습니다. 이벤트에 Event Parameter를 포함하도록 선택할 수 있습니다.

<div id="h_01NEWAFNETREVENUE0001" />

<div id="note-3" />

<div id="note-2" />

> 📘 **참고**
>
> 이벤트 값 열에서 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">로데이터 리포트</Anchor>에서 Event Parameter를 확인할 수 있습니다(프리미엄 기능).

<div id="af_adrev_ad_type" />

<Accordion title="af_광고_유형">

**설명**: 광고 유형 (예: 배너 또는 전면광고)

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_광고\_유형 | ad\_type | - | - | - | - | - |

</Accordion>

<div id="af_city" />

<Accordion title="af_city">

**설명**: 승차를 예약한 도시

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_city | fb\_city | - | - | - | flight\_city | - |

</Accordion>

<div id="af_class" />

<Accordion title="af_class">

**설명**: 항공편에 예약된 여행 등급

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_class | fb\_travel\_class | travel\_class | - | - | flight\_class | - |

</Accordion>

<div id="af_content" />

<Accordion title="af_content">

**설명**: 콘텐츠 제목 (예: 노래 제목 또는 TV 쇼 제목 및 에피소드)

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_content | fb\_content | - | - | - | - | - |

</Accordion>

<div id="af_content_id" />

<Accordion title="af_content_id">

**설명**: 항목의 ID

**참고:** 스냅챗에 사전 정의된 `af_content_id` 및 `af_content_id` 이벤트는 동일한 Event Parameter를 공유합니다. 두 이벤트가 동시에 기록되면 `af_content_list` 이벤트만 스냅챗으로 전송됩니다.

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_content\_id | fb\_content\_id | item\_id | item\_ids | content\_id | content\_id | id |

</Accordion>

<div id="af_content_list" />

<Accordion title="af_content_list">

**설명**: 콘텐츠 ID 목록

**참고:** 스냅챗에 사전 정의된 `af_content_id` 및 `af_content_id` 이벤트는 동일한 Event Parameter를 공유합니다. 두 이벤트가 동시에 기록되면 `af_content_list` 이벤트만 스냅챗으로 전송됩니다.

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_content\_list | - | item\_id | item\_ids | - | - | - |

</Accordion>

<div id="af_content_type" />

<Accordion title="af_content_type">

**설명**: 제품 카테고리

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_content\_type | fb\_content\_type | item\_category | item\_category | content\_type | content\_type | - |

</Accordion>

<div id="af_country" />

<Accordion title="af_country">

**설명**: 승차를 예약한 국가

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_country | fb\_국가 | - | - | - | 비행 국가 | - |

</Accordion>

<div id="af_currency" />

<Accordion title="af_통화">

**설명**: 통화 코드

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_통화 | fb\_통화 | 화폐\_코드 | 통화 | 가격\_통화 | 통화 | 통화 | 통화 |

</Accordion>

<div id="af_customer_user_id" />

<Accordion title="af_고객_유저_ID">

**설명**: 고객의 ID

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_고객\_유저\_ID | - | 고객\_유저\_  <br />id | - | - | - | cid |

</Accordion>

<div id="af_date_a" />

<Accordion title="af_date_a">

**설명**: 체크인 날짜

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_date\_a | fb\_체크인\_날짜 | 시작날짜 | - | - | 체크인 날짜 | din |

</Accordion>

<div id="af_date_b" />

<Accordion title="af_date_b">

**설명**: 체크아웃 날짜

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_date\_b | fb\_체크아웃\_날짜 | 종료일 | - | - | 체크아웃 날짜 | dout |

</Accordion>

<div id="af_departing_arrival_date" />

<Accordion title="af_departing_arrival_date">

**설명**: 도착일

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_departing\_arrival\_date | fb\_출발\_도착\_날짜 | - | - | - | - | - |

</Accordion>

<div id="af_departing_departure_date" />

<Accordion title="af_departing_departure_date">

**설명**: 출발일

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| 출발\_출발\_날짜 | fb\_departing\_출발\_날짜 | - | - | - | 출발날짜 | - |

</Accordion>

<div id="af_description" />

<Accordion title="af_설명">

**설명**: 짧은 설명 (문자열)

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_설명 | fb\_설명 | 설명 | 설명 | 설명 | 설명 | ui\_업적 |

</Accordion>

<div id="af_destination_a" />

<Accordion title="af_목적지_a">

**설명**: 첫 번째 목적지

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_목적지\_a | fb\_출발지\_공항 | 출발지 | - | - | 출발공항 | - |

</Accordion>

<div id="af_destination_b" />

<Accordion title="af_목적지_b">

**설명**: 두 번째 목적지

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_목적지\_b | fb\_목적지\_  <br />공항 | 목적지 | - | - | 목적지\_공항 | - |

</Accordion>

<div id="af_destination_list" />

<Accordion title="af_목적지_목록">

**설명**: 목적지 카탈로그에 포함된 목적지 목록(예: 호텔 근처의 박물관 또는 레스토랑 목록)

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_목적지\_목록 | fb\_목적지\_ID | - | - | - | - | - |

</Accordion>

<div id="af_hotel_score" />

<Accordion title="af_호텔_점수">

**설명**: 리뷰별 호텔 평점

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_호텔\_점수 | fb\_호텔\_점수 | - | - | - | - | - |

</Accordion>

<div id="af_level" />

<Accordion title="af_수준">

**설명**: 유저가 달성한 수준

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_수준 | fb\_수준 | 레벨업 | 수준 | 수준 | - | ui\_수준 |

</Accordion>

<div id="af_max_rating_value" />

<Accordion title="af_max_rating_value">

**설명**: 최고 평점 (예: 5/5)

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_max\_rating\_value | fb\_최대\_평가\_값 | 최대 등급 | - | 최대\_평가\_값 | - | - |

</Accordion>

<div id="af_num_adults" />

<Accordion title="af_성인_수">

**설명**: 여행하는 성인의 수

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_성인\_수 | fb\_성인\_수 | - | - | - | 사람 수 | - |

</Accordion>

<div id="af_num_children" />

<Accordion title="af_어린이_수">

**설명**: 여행하는 어린이 수

파라미터 매핑:

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_어린이\_수 | fb\_어린이\_수 | - | - | - | 어린이 수 | - |

</Accordion>

<div id="af_num_infants" />

<Accordion title="af_유아_수">

**설명**: 여행하는 유아의 수

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_유아\_수 | fb\_유아\_수 | - | - | - | - | - |

</Accordion>

<div id="af_order_id" />

<Accordion title="af_주문_ID">

**설명**: 거래의 ID

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_주문\_ID | fb\_주문\_ID | 주문\_ID | 거래\_ID | - | 주문\_ID | 거래\_ID |

</Accordion>

<div id="af_payment_info_available" />

<Accordion title="af_결제_정보_사용 가능">

**설명**: 유저의 결제 정보가 사용 가능한지 여부

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_결제\_정보\_사용 가능 | fb\_결제\_정보\_사용 가능 | 결제 정보  <br />사용 가능 | 결제 정보 사용 가능 | 유저 결제\_  <br />정보 | - | - |

</Accordion>

<div id="af_preferred_neighborhoods" />

<Accordion title="af_선호하는_지역">

**설명**: 호텔이 위치한 지역

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_선호하는\_지역 | fb\_선호\_지역 | - | - | - | - | - |

</Accordion>

<div id="af_preferred_num_stops" />

<Accordion title="af_선호하는_경유지">

**설명**: 유저가 찾고 있는 경유 횟수(예: 직항 또는 직항편)

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_선호하는\_경유지 | fb\_선호\_정류장\_수 | - | - | - | - | - |

</Accordion>

<div id="af_preferred_price_range" />

<Accordion title="af_선호_가격대">

**설명**: 호텔의 선호 가격대

파라미터 매핑:

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_선호\_가격대 | fb\_선호\_가격대 | - | - | - | - | - |

</Accordion>

<div id="af_preferred_star_ratings" />

<Accordion title="af_선호_별점_평가">

**설명**: 호텔의 선호 별점

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_선호\_별점\_평가 | fb\_선호\_별점\_평가 | - | - | - | - | - |

</Accordion>

<div id="af_price" />

<Accordion title="af_가격">

**설명**: 제품의 가격 af\_price를 수익으로 간주되지 않는 금액 파라미터로 사용할 수 있습니다 (예: 장바구니에 추가 이벤트). 이 파라미터는 개별 항목의 가격을 의미합니다. 모든 구매의 총액은 [af\_revenue](/docs/in-app-events-event-structure#af_revenue) 파라미터에 표시됩니다.

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_가격 | fb\_가격 | 가격 | 가격 | 가격 마이크로 | 가격 | 가격 |

</Accordion>

<div id="af_projected_revenue" />

<Accordion title="af_예상_수익">

실제 수익이 실현되기 전에 유저의 초기 상호작용이나 행동에 근거하여 광고주가 유저로부터 기대하는 예상 수익입니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#projected-revenue">예상 수익에 대해 더 보기</Anchor>.

</Accordion>

<div id="af_purchase_currency" />

<Accordion title="af_구매_화폐">

**설명**: 구매에 사용된 화폐

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_구매\_화폐 | fb\_구매\_화폐 | - | - | - | - | - |

</Accordion>

<div id="af_quantity" />

<Accordion title="af_수량">

**설명**: 항목 수

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_수량 | fb\_항목\_수 | 수량 | 항목\_개수 | 항목\_개수 | 수량 | 수량 |

</Accordion>

<div id="af_rating_value" />

<Accordion title="af_등급_값">

**설명**: 선택된 평가 값

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_등급\_값 | \_valueToSum | value | - | 가격 마이크로 | - | - |

</Accordion>

<div id="af_receipt_id" />

<Accordion title="af_영수증_ID">

**설명**: 영수증의 ID

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_영수증\_ID | - | 거래\_ID | - | - | - | 거래\_ID |

</Accordion>

<div id="af_region" />

<Accordion title="af_지역">

**설명**: 승차 예약 지역

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_지역 | fb\_지역 | - | - | - | 비행\_지역 | - |

</Accordion>

<div id="af_registration_method" />

<Accordion title="af_registration_method">

**설명**: 가입 방법의 유형

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_registration\_method | fb\_registration\_method | registration\_method | 가입 방법 | registration\_method | - | - |

</Accordion>

<div id="af_returning_arrival_date" />

<Accordion title="af_귀국 도착 날짜">

**설명**: 귀국 여정이 끝나는 날짜와 시간

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_귀국 도착 날짜 | fb\_귀국 도착 날짜 | - | - | - | - | - |

</Accordion>

<div id="af_returning_departure_date" />

<Accordion title="af_귀국 출발 날짜">

**설명**:  귀국 여정이 시작되는 날짜와 시간

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_귀국 출발 날짜 | fb\_귀국 출발 날짜 | - | - | - | 귀국 날짜 | - |

</Accordion>

<div id="af_revenue" />

<Accordion title="af_수익">

**설명**: 총 구매 금액. af\_revenue는 앱스플라이어 플랫폼에서 수익으로 계산됩니다. 취소 또는 환불로 인한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">음수 수익</Anchor>도 포함됩니다.

<div id="important" />

> 🚧 **중요 사항!**
>
> 수익 값에는 쉼표, 통화, 특수 문자 또는 텍스트가 포함되지 않아야 합니다. 예를 들어, 수익 값은 1234.56이어야 합니다. 앱스플라이어는 소수점 다섯 자리까지의 정확도로 수익 가치를 제공합니다.

수익 파라미터 사용법에 대한 자세한 내용을 보려면 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">여기</Anchor>를 클릭하세요.

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_수익 | \_valueToSum | value | 가격 | 가격 마이크로 | value | eventValue | ui\_revenue |

</Accordion>

<div id="af_score" />

<Accordion title="af_score">

**설명**: 사용자의 업적과 관련된 점수

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_score | - | - | - | 점수 | - | - |

</Accordion>

<div id="af_search_string" />

<Accordion title="af_search_string">

**설명**: 검색어

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_search\_string | fb\_search\_string | search\_string | search\_string | search\_string | - | - |

</Accordion>

<div id="af_subscription_id" />

<Accordion title="af_subscription_id">

**설명**: 사용자 구독 ID

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_subscription\_id | subscription\_id | - | - | - | - | - |

</Accordion>

<div id="af_success" />

<Accordion title="af_success">

**설명**: 작업이 성공적으로 완료되었는지 여부

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_success | fb\_success | success | success | - | - | - |

</Accordion>

<div id="af_suggested_destinations" />

<Accordion title="af_suggested_destinations">

**설명**: 제안된 목적지 목록

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_suggested\_destinations | fb\_suggested\_destinations | - | - | - | - | - |

</Accordion>

<div id="af_suggested_hotels" />

<Accordion title="af_suggested_hotels">

**설명**: 추천 호텔 목록

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_suggested\_hotels | fb\_suggested\_hotels | - | - | - | - | - |

</Accordion>

<div id="af_travel_end" />

<Accordion title="af_travel_end">

**설명**: 여행 종료일

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_travel\_end | fb\_travel\_end | - | - | - | - | - |

</Accordion>

<div id="af_travel_start" />

<Accordion title="af_travel_start">

**설명**: 여행 시작일

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_travel\_start | fb\_travel\_start | - | - | - | - | - |

</Accordion>

<div id="af_user_score" />

<Accordion title="af_user_score">

**설명**: 사용자가 광고주에게 미치는 상대적 중요성

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_user\_score | fb\_user\_score | - | - | - | - | - |

</Accordion>

<div id="af_validated" />

<Accordion title="af_validated">

**설명**: 구매를 검증

**파라미터 매핑:**

| 앱스플라이어 | Meta Ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_validated | - | validated | success | - | - | - |

</Accordion>

다음은 SRN 매핑을 포함하지 않는 미리 정의된 이벤트 파라미터 목록입니다:

* af\_achievement\_id
* af\_coupon\_code
* af\_customer\_segment
* af\_deep\_link
* af\_event\_end
* af\_event\_start
* af\_lat
* af\_long
* af\_new\_version
* af\_old\_version
* af\_param\_1
* af\_param\_2
* af\_param\_3
* af\_param\_4
* af\_param\_5
* af\_param\_6
* af\_param\_7
* af\_param\_8
* af\_param\_9
* af\_param\_10
* af\_리뷰\_텍스트
* af\_튜토리얼\_아이디
* af\_가상\_화폐\_이름
* af\_기간\_초

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration">인앱 이벤트 포스트백 구성</Anchor>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01H9HT8C713A4NV9WCB0FJZJ4R=%EA%B0%9C%EC%9A%94 predefined-event-names=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%9D%B4%EB%A6%84 h_01H9HT8C7189W1JXAR3J3KT8KV=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%9D%B4%EB%A6%84 h_01H9HT8C71MV7V7C75MB6ESHMM=achievement-unlocked-af_achievement_unlocked h_01H9HT8C7171PB7KAC83MYBWQ8=ad-click-af_ad_click h_01H9HT8C72KJ6ZA663SH7HJ7MP=ad-view-af_ad_view h_01H9HT8C72HSM88DJG0PDV5140=add-payment-info-af_add_payment_info h_01H9HT8C72BWFSPKWDVQW926WG=add-to-cart-af_add_to_cart h_01H9HT8C7228B57XKAACPZG8NK=add-to-wishlist-af_add_to_wishlist h_01H9HT8C72DX0DXBDHRJFG19G2=complete-registration-af_complete_registration h_01H9HT8C72SPY9VQ9AD648AKZK=content-view-af_content_view h_01H9HT8C722T2VH6A9257Q7T4P=initiated-checkout-af_initiated_checkout h_01H9HT8C72F0RZ4JS9929SE465=invite-af_invite h_01H9HT8C72VFGC08Q858EX7XTN=level-achieved-af_level_achieved h_01H9HT8C72DZW77YTQ9KB0XEVG=list-view-af_list_view h_01H9HT8C720W10QEBCTPAGMRFB=login-af_login h_01H9HT8C72QC4WV10Z4JZTZM7D=opened-from-push-notification-af_opened_from_push_notification h_01H9HT8C7263J0YSX5K10R497N=purchase-af_purchase h_01H9HT8C73MPYMG8KSYE04DKDZ=rate-af_rate h_01H9HT8C734DAC6GPJE58DB5JD=reengage-af_re_engage h_01H9HT8C73YSYBK0YSDPRWDBNW=search-af_search h_01H9HT8C734GJ07V67QC9V3TVC=share-af_share h_01H9HT8C73H4VT2M0P3M1SYG88=spent-credits-af_spent_credits h_01H9HT8C73YWDCKAZPY0BVRS6F=start-trial-af_start_trial h_01H9HT8C736BF2VNRCFSJSVXWS=%EC%B0%B8%EA%B3%A0 h_01H9HT8C73N69S45H82NWQ5FN1=subscription-af_subscribe h_01H9HT8C73CD6HNT5GA6B4CHQ9=travel-booking-af_travel_booking h_01H9HT8C73NFDPS1P5AVXXZEX7=tutorial-completion-af_tutorial_completion h_01H9HT8C73JPH6Q9XFKA3GNYT8=update-af_update h_01H9HT8C74SGGK2FW92JH4BJPZ=%EC%B0%B8%EA%B3%A0-1 predefined-event-parameters=%EB%AF%B8%EB%A6%AC-%EC%A0%95%EC%9D%98%EB%90%9C-event-parameter h_01H9HT8C74N4TJZ5ZVBTKAX810=%EB%AF%B8%EB%A6%AC-%EC%A0%95%EC%9D%98%EB%90%9C-event-parameter h_01H9HT8C74VQ9ZWF079V50E5HE=%EC%B0%B8%EA%B3%A0-2 h_01H9HT8C74Y0BWS565DFTY75KJ=af_adrev_ad_type h_01H9HT8C742NHGXFKWSS4P07K2=af_city h_01H9HT8C7442PFZEK7QC6R0K67=af_class h_01H9HT8C7462KG3030WWZ2XGZW=af_content h_01H9HT8C74ZX07907NXFHKGJ91=af_content_id h_01H9HT8C744CMWSYHJB74JFSS5=af_content_list h_01H9HT8C74GKGG5V4X54BCAADC=af_content_type h_01H9HT8C74RD08Z9EBZTKY5KSD=af_country h_01H9HT8C75BJYK4R3WYSN4BF43=af_currency h_01H9HT8C752E2PK6QKTA2GNGH5=af_customer_user_id h_01H9HT8C75BN0A92X9BRY4A74T=af_date_a h_01H9HT8C75406KV9264ZZT9DKM=af_date_b h_01H9HT8C7526AEHJAA7FM7442E=af_departing_arrival_date h_01H9HT8C75W9X61ZH0849EPDBY=af_departing_departure_date h_01H9HT8C75VEV3C8CJBDN6X5HW=af_description h_01H9HT8C75Z8TBZEPEY9EGSR4Y=af_destination_a h_01H9HT8C751G216VB6GYTPEPE1=af_destination_b h_01H9HT8C75CVM0MHSKTK2CZ8HD=af_destination_list h_01H9HT8C75CVVDFABSTN5R4MWT=af_hotel_score h_01H9HT8C75GEMHE2NHEFK9J7NT=af_level h_01H9HT8C7505H4CMY70EMDQWSF=af_max_rating_value h_01H9HT8C75ST9XBDC3SR6XFDPB=af_num_adults h_01H9HT8C75NNZ5NP6PRPXDSKP8=af_num_children h_01H9HT8C757X70AAGNWFV0CKRY=af_num_infants h_01H9HT8C75A0HESE5FD10VD1P8=af_order_id h_01H9HT8C75B488VKY8SW9M4GG4=af_payment_info_available h_01H9HT8C75W7SRB0KF4E5FB2YF=af_preferred_neighborhoods h_01H9HT8C75GC61D1A0P6P42TMR=af_preferred_num_stops h_01H9HT8C76XRY6CD1TJEPCJJTR=af_preferred_price_range h_01H9HT8C76Y9ZQQ2X4EJT2DC14=af_preferred_star_ratings h_01H9HT8C76KCDRJKBWSM9JKFE1=af_price 01J9XHWVFHXPN6N3EZF1P8XWYM=af_projected_revenue h_01H9HT8C767ZNWCBYC3X680PGQ=af_purchase_currency h_01H9HT8C76Y5VXBKF3TBVVJG1C=af_quantity h_01H9HT8C768WXZ126Q425PHDWX=af_rating_value h_01H9HT8C76XX9J6FZ6RWQB6B6R=af_receipt_id h_01H9HT8C760S0F7QZMFYW1BKRD=af_region h_01H9HT8C76N4S3SGES5SQ2J4AC=af_registration_method h_01H9HT8C76ZR36A4CM2PY6PJ10=af_returning_arrival_date h_01H9HT8C760JPVXYC5WH9ZSDPX=af_returning_departure_date h_01H9HT8C76PYB14WPCQKSEK69J=af_revenue h_01H9HT8C762BGPRHFX228APEHR=%EC%A4%91%EC%9A%94-%EC%82%AC%ED%95%AD h_01H9HT8C76P55HN8K6D7PHFS2J=af_score h_01H9HT8C76TB4KNTZVD6JVPEYQ=af_search_string h_01H9HT8C762R2PJ573W8TJFJHG=af_subscription_id h_01H9HT8C76VZ6FA20K471V0EKK=af_success h_01H9HT8C76029H94AY5EHCZX6X=af_suggested_destinations h_01H9HT8C76N6C694TCPVCK4EC3=af_suggested_hotels h_01H9HT8C765EM1SAEJ67FNXZDE=af_travel_end h_01H9HT8C76YP8VEM5E6WB9NQ7T=af_travel_start h_01H9HT8C771SYQWQ8VBTPA2V2E=af_user_score h_01H9HT8C771XFSQJX42QVBNZAJ=af_validated h_01HDNZ30NH2QXSHD7B4EMFG4T5=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
