---
title: 추천 호텔 예약 앱 이벤트
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-04-29T14:49:54Z'
  edited_at: '2026-10-14T10:37:48Z'
  id: 360019843558
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/360019843558
---
> **한눈에 보기:** 요약: 호텔 예약 앱에 대해 제안된 인앱 이벤트를 기록하여 사용자 여정 내내 사용자의 질을 측정합니다.

## <Image alt="InApp_Events_hotel.png" src="https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png" width="100px" /> Hotel booking

여행자는 호텔 예약 앱으로 가장 좋은 조건이 제시된 호텔을 쉽게 예약할 수 있습니다. 기록할 것을 제안하는 대표적인 이벤트는 검색, 구매, 여행 예약 및 찜한 목록 추가입니다.

이벤트 기록으로 다음을 확인할 수 있습니다.

* 사용자의 실제적인 휴가 예약을 유도하는 캠페인 및 미디어소스
* 가장 많은 사용자 예약 건수와 수익을 올린 캠페인과 미디어소스

특정 미디어소스의 사용자에게 호텔 점수, 계절, 국가 및 어린이 수와 같은 선호도를 지정할 수 있습니다. 그런 다음 이런 사용자 선호도를 리타게팅하여 캠페인을 최적화할 수 있습니다.

<div id="important" />

> 🚧 **중요!**
>
> * 인앱 이벤트 구현과 관련한 마케터용 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#인앱-이벤트-설정">지침</Anchor>을 반드시 읽어보십시오.
> * 구현 프로세스를 간소화하려면 당사의 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=hotel_booking">인앱 이벤트 생성기</Anchor>를 사용하십시오. 이 도구에는 본 문서에서 설명한 일반적인 인앱 이벤트가 모두 포함되어 있으며 사용자는 비즈니스 요구사항에 따라 이벤트를 수정할 수 있습니다. 완료되면 파일을 개발사와 공유하십시오.
> * 본 문서에 포함된 각 권장 이벤트에 대해 iOS, 안드로이드 및 Unity 개발자를 위한 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=hotel_booking&view=code">코드 샘플</Anchor>이 있습니다.
> * 개발사에 대한 자세한 지침은 **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">앱스플라이어 개발자 허브</Anchor>** 에서 확인할 수 있습니다.
>
> 인앱 이벤트 기록에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트 가이드를</Anchor> 참조하십시오.

[![Flowchart_for_recommended_events_hotel_booking_app_user_journey](https://files.readme.io/f425bc8865d731eb4934b6f32123156c7016ea1f75472e8878e76636aa593073-4402679204241.png)](https://files.readme.io/f425bc8865d731eb4934b6f32123156c7016ea1f75472e8878e76636aa593073-4402679204241.png)

<div id="recommended-structures-for-predefined-events" />

## 사전 정의된 이벤트에 권장되는 구조

다음 섹션에서는 호텔 예약 수직 구조에 일반적인 이벤트 구조 목록을 제공합니다. 각 구조에는 사용할 미리 정의된 이벤트 이름과 제안된 이벤트 파라미터가 포함됩니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="complete-registration-af_complete_registration" />

<Accordion title="가입 완료(af_complete_registration)">

**목적**

앱을 설치하고 등록 프로세스를 완료한 사용자 수, 사용자가 선호하는 등록 방법 및 실제로 가입하는 사용자를 유도하는 미디어소스가 무엇인지 알 수 있습니다.

**트리거**

사용자가 등록 프로세스를 완료한 시간

이벤트 파라미터

| 필드 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_registration\_method | 가입 방법의 유형 | 이메일, 페이스북 |

</Accordion>

<div id="login-af_login" />

<Accordion title="로그인 (af_login)">

**목적**

등록된 사용자의 잔존율 파악

**트리거**

사용자가 성공적으로 로그인한 시간

**이벤트 파라미터**

추가 파라미터 없이 전송 가능

</Accordion>

<div id="search-af_search" />

<Accordion title="검색 (af_search)">

**목적**

사용자가 무엇을 찾고 있는지, 어떤 검색 결과가 가장 관련성이 높고 구매로 이어지는지 알아봅니다. 또한, 특정 지역의 사용자가 무엇을 검색하는지를 파악하고 미디어소스를 통해 타게팅할 수도 있습니다.

**트리거**

사용자가 검색을 수행하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_date\_a | 체크인 날짜 | 2018/07/26 |
| af\_date\_b | 체크아웃 날짜 | 2018/08/01 |
| af\_목적지\_a | 사용자 위치 | 런던 |
| af\_목적지\_b | 호텔 위치 | Madrid |
| af\_성인\_수 | 숙박 인원수 | 2 |
| af\_어린이\_수 | 어린이 인원수 | 0 |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="콘텐츠 보기 (af_content_view)">

**목적**

이 이벤트에 의해 다음을 확인할 수 있습니다.

* 검색 결과가 검색 조회와 연관이 있는지 여부
* 사용자가 찾고 있는 속성 유형
* 계절별 트렌드
* 인기 장소
* 사용자를 유도하고 광고와 프로모션을 통해 이런 사용자를 리타케팅하는 미디어소스

**트리거**

사용자가 속성을 보는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 | 호텔 요금 목록 | 674 |
| af\_content\_id | 호텔 ID |  |
| af\_date\_a | 체크인 날짜 | 2018/07/26 |
| af\_date\_b | 체크아웃 날짜 | 2018/08/01 |
| af\_목적지\_a | 사용자 위치 | 런던 |
| af\_목적지\_b | 호텔 위치 | Madrid |
| af\_class | 객실 유형 | Deluxe |
| af\_성인\_수 | 숙박 인원수 | 2 |
| af\_어린이\_수 | 어린이 인원수 | 0 |
| af\_호텔\_점수 | 리뷰별 호텔 평점 | 9.6 |
| af\_선호\_별점\_평가 | 선호 호텔 등급 | 5 |
| af\_선호하는\_지역 | 호텔이 위치한 지역 | Centro |

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="위시리스트에 추가 (af_add_to_wishlist)">

**목적**

예약 시 사용자가 관심이 있는 호텔과 목적지를 기록합니다. 예를 들어 사용자가 찾고 있는 호텔, 지역 및 별점 등급을 알고 있는 경우 이 데이터를 사용하여 사용자를 리타게팅할 수 있습니다.

**트리거**

사용자가 찜 목록에 목록을 추가하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 | 호텔 요금 목록 | 674 |
| af\_content\_id | 호텔 ID |  |
| af\_date\_a | 체크인 날짜 | 2018/07/26 |
| af\_date\_b | 체크아웃 날짜 | 2018/08/01 |
| af\_목적지\_a | 사용자 위치 | 런던 |
| af\_목적지\_b | 호텔 위치 | Madrid |
| af\_class | 객실 유형 | Deluxe |
| af\_성인\_수 | 숙박 인원수 | 2 |
| af\_어린이\_수 | 어린이 인원수 | 0 |
| af\_호텔\_점수 | 리뷰별 호텔 평점 | 9.6 |
| af\_선호\_별점\_평가 | 선호 호텔 등급 | 5 |
| af\_선호하는\_지역 | 호텔이 위치한 지역 | Centro |
| purchase\_method | 결제 수단 | Credit card |
| af\_coupon\_code | 프로모션 코드 또는 보상 포인트 | SUM2018 |
| property\_type | 속성 유형 | Hotel |

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="결제 시작(af_initiated_checkout)">

**목적**

구매자가 결제를 진행할 때 어떻게 행동하는지 이해합니다. 이 이벤트에 의해 다음을 확인할 수 있습니다.

* 사용된 결제 수단(예: 신용카드 또는 전자 지갑)
* 사용자가 결제 프로세스 종료 여부

**트리거**

사용자가 신용카드 정보를 추가하거나 전자 지갑에 연결하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 | 호텔 요금 목록 | 674 |
| af\_content\_id | 호텔 ID |  |
| af\_date\_a | 체크인 날짜 | 2018/07/26 |
| af\_date\_b | 체크아웃 날짜 | 2018/08/01 |
| af\_목적지\_a | 사용자 위치 | 런던 |
| af\_목적지\_b | 호텔 위치 | Madrid |
| af\_class | 객실 유형 | Deluxe |
| af\_성인\_수 | 숙박 인원수 | 2 |
| af\_어린이\_수 | 어린이 인원수 | 0 |
| af\_호텔\_점수 | 리뷰별 호텔 평점 | 9.6 |
| af\_선호\_별점\_평가 | 선호 호텔 등급 | 5 |
| af\_선호하는\_지역 | 호텔이 위치한 지역 | Centro |
| purchase\_method | 결제 수단 | Credit card |
| af\_coupon\_code | 프로모션 코드 또는 보상 포인트 | SUM2018 |
| property\_type | 속성 유형 | Hotel |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="구매 (af_purchase)">

**목적**

호텔 예약 앱에서 구매 경향에 대해 알 수 있습니다. 이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 광고 네트워크와 광고 에이전시 전반에 대한 사용자의 LTV 및 캠페인의 ROI를 알 수 있습니다.
* 사용자에게 가장 인기있는 아이템이 무엇인지 알 수 있습니다.
* 캠페인 타게팅을 최적화하기 위해서, 구매한 아이템 내역을 기반으로 크로스 캠페인을 진행할 수 있습니다.

**트리거**

사용자가 성공적인 구매 후 확인 페이지를 방문한 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> | 구매 추정 수익 | 1205.99 |
| af\_가격 | 전체 구매액 | 4000 |
| af\_content\_id | 아이템 ID | 121 |
| af\_콘텐츠\_유형 | 아이템 카테고리 | hotel |
| af\_통화 | 통화 코드 | AUD |
| af\_수량 | 장바구니에 담긴 아이템 개수 | 1 |
| af\_주문\_id | 구매한 다음에 발생한 주문 ID | X123ABC |
| af\_영수증\_ID | CRITEO 및 Google 애드워즈 리타겟팅 연동에 필요한 주문 ID | X123ABC |

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="여행 예약 (af_travel_booking)">

**목적**

앱에서 전체 예약률을 확인합니다. 이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 예약에서 발생한 수익 기록
* 어린이와 함께 호텔을 예약한 사용자 수 확인
* 계절적 경향 이해
* 유명 호텔 확인

**트리거**

호텔 예약 후 사용자가 감사 페이지를 방문하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> | 예약으로 발생한 수익 | 647.95 |
| af\_통화 | 통화 코드 | GBP |
| af\_가격 | 호텔 요금 목록 | 674 |
| af\_content\_id | 호텔 ID |  |
| af\_date\_a | 2018/07/26 | 체크인 날짜 |
| af\_date\_b | 체크아웃 날짜 | 2018/08/01 |
| af\_목적지\_a | 사용자 위치 | 런던 |
| af\_목적지\_b | 호텔 위치 | Madrid |
| af\_class | 객실 유형 | Deluxe |
| af\_성인\_수 | 숙박 인원수 | 2 |
| af\_어린이\_수 | 어린이 인원수 | 0 |
| af\_호텔\_점수 | 리뷰별 호텔 평점 | 9.6 |
| af\_선호\_별점\_평가 | 선호 호텔 등급 | 5 |
| af\_선호하는\_지역 | 호텔이 위치한 지역 | Centro |
| purchase\_method | 결제 수단 | Credit card |
| af\_coupon\_code | 프로모션 코드 또는 보상 포인트 | SUM2018 |
| property\_type | 속성 유형 | Hotel |
| new\_booking | 첫 번째 예약인지 여부 | true |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## 사용자 지정 이벤트에 대한 권장 구조

다음 섹션에서는 사용자 지정 이벤트 이름과 사용하도록 제안된 이벤트 파라미터를 포함한 이벤트 구조 목록을 제공합니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="first-purchase-first_purchase" />

<Accordion title="첫 번째 구매(first_purchase)">

**목적**

[구매](/docs/recommended-hotel-booking-app-events#purchase-af_purchase) 이벤트와 동일합니다. 또한 이 이벤트를 통해 다음을 확인할 수 있습니다.

* 새 구매자가 구매하는 데 걸리는 시간
* 최초 구매자가 구매하려고 하는 제품
* 최초 구매의 평균 가격과 수익

**트리거**

사용자가 첫 구매를 완료하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> | 구매 수익 | 1205.95 |
| af\_가격 | 전체 구매액 | 4000 |
| af\_content\_id | 아이템 ID | 121, 262 |
| af\_콘텐츠\_유형 | 아이템 카테고리 | hotel |
| af\_통화 | 통화 | AUD |
| af\_수량 | 장바구니에 담긴 아이템 개수 | 1 |
| af\_주문\_id | 구매한 다음에 발생한 주문 ID | X123ABC |
| af\_영수증\_ID | CRITEO 및 Google 애드워즈 리타겟팅 연동에 필요한 주문 ID | X123ABC |

</Accordion>

<div data-zendesk-anchors="hotel-booking=-hotel-booking h_01HGTB0APWWTRER6GAWJ7TJ05S=-hotel-booking h_01HGTB0APWQDX7VN96GM7520ZH=%EC%A4%91%EC%9A%94 recommended-structures-for-predefined-events=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTB0APW933179Q90HFASW1V=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTB0APWRKRGCJ5TFKTPHH33=complete-registration-af_complete_registration h_01HGTB0APW1XY5R69CJ8PSQV6C=login-af_login h_01HGTB0APW5YF2DASC0HYDPTA9=search-af_search h_01HGTB0APXTQWBS4EXJ8D724G0=content-view-af_content_view h_01HGTB0APXS95QGK17RE8B3Y1E=add-to-wishlist-af_add_to_wishlist h_01HGTB0APX1XX2W3YX85W75F6B=initiated-checkout-af_initiated_checkout h_01HGTB0APXGPW16FRY3C7VSMDM=purchase-af_purchase h_01HGTB0APXJFHMPGYC63ZTV4R9=travel-booking-af_travel_booking recommended-structures-for-custom-events=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTB0APXP6WVM1AVEMEY6KVS=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTB0APX4ND0NGVTK9FA38QR=first-purchase-first_purchase" />
