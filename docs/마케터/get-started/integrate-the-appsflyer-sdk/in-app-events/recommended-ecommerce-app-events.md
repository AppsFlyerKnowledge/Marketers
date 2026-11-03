---
title: 추천 이커머스 앱 이벤트
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
  created_at: '2021-04-19T06:32:18Z'
  edited_at: '2026-10-14T10:26:52Z'
  id: 360019347957
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/360019347957
---
> **한눈에 보기:** 요약: 이커머스 앱에 대해 제안된 인앱 이벤트를 기록하여 사용자 여정 내내 사용자의 질을 측정합니다.

## <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="67px" /> eCommerce

이커머스 앱을 통해 구매자는 온라인으로 쉽게 물건을 검색하고 구매할 수 있습니다. 기록할 것을 제안하는 대표적인 이벤트는 검색, 구매, 장바구니 추가, 찜한 목록 추가입니다.

이벤트 기록으로 다음을 확인할 수 있습니다.

* 가장 인기 있는 카테고리
* 구매자가 검색하는 제품
* 결제를 완료한 구매자 수
* 반복 구매하는 사용자와 한 번만 구매하는 구매자 수

> 🚧 **중요!**
>
> * 인앱 이벤트 구현과 관련한 마케터용 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#인앱-이벤트-설정">지침</Anchor>을 반드시 읽어보십시오.
> * 구현 프로세스를 간소화하려면 당사의 인앱 이벤트 생성기를 사용하십시오. 이 도구에는 본 문서에서 설명한 일반적인 인앱 이벤트가 모두 포함되어 있으며 사용자는 비즈니스 요구사항에 따라 이벤트를 수정할 수 있습니다. 완료되면 파일을 개발사와 공유하십시오.
> * 본 문서에 포함된 각 권장 이벤트에 대해 iOS, 안드로이드 및 Unity 개발자를 위한 <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=ecommerce&view=code">코드 샘플</Anchor>이 있습니다.
> * 개발사에 대한 자세한 지침은 **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">앱스플라이어 개발자 허브</Anchor>** 에서 확인할 수 있습니다.
>
> 인앱 이벤트 기록에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트 가이드를</Anchor> 참조하십시오.

[![Flowchart_for_recommended_events e-Commerce_app_user_journey](https://files.readme.io/81af149c4fbe9185af3dad4057147dbf9882eb30d30b0724f2ffad2714517084-360020063077.png)](https://files.readme.io/81af149c4fbe9185af3dad4057147dbf9882eb30d30b0724f2ffad2714517084-360020063077.png)

## 사전 정의된 이벤트에 권장되는 구조

다음 섹선에서는 이커머스 수직 구조에 일반적인 이벤트 구조 목록을 제공합니다. 각 구조에는 사용할 미리 정의된 이벤트 이름과 제안된 이벤트 파라미터가 포함됩니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="complete-registration-af_complete_registration" />

<Accordion title="가입 완료(af_complete_registration)">

**목적**

앱을 설치하고 등록 프로세스를 완료한 사용자 수와 사용자가 선호하는 등록 방법에 대해 알아봅니다.

**트리거**

사용자가 등록 프로세스를 완료한 시간

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_registration\_method | 가입 방법의 유형 | 이메일, 메타 광고 |

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

사용자가 무엇을 찾고 있는지, 어떤 검색 결과가 가장 관련성이 높고 구매로 이어지는지 알아봅니다.

**트리거**

다음 중 하나입니다.

* 사용자가 검색 버튼을 클릭했을 때
* 사용자가 검색 결과 페이지를 방문했을 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_search\_string | 검색어 | 빨간색 드레스, 운동화 |
| af\_content\_list | 콘텐츠 ID 목록 | 001, 092 |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="콘텐츠 보기 (af_content_view)">

**목적**

특정 제품의 열람률을 알아봅니다. 이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 제품 판매와 열람과의 상관 관계를 알 수 있습니다.
* 어떤 카테고리가 가장 인기가 있는지 제품 열람을 통해 알 수 있습니다.
* 구매자가 보고 있는 제품과 통화와의 상관 관계를 알 수 있습니다.

**트리거**

사용자가 특정 제품 세부 사항 페이지 열람 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 | 제품 가격 | 2000 |
| af\_content | 해당되는 경우 국제 상품 번호(EAN) 또는 기타 제품 또는 콘텐츠 식별자<br /><br />**메타 광고** 다이내믹 광고의 필수 매개변수 | ABC123 |
| af\_content\_id | 제품 ID<br /><br />**메타 광고** 다이내믹 광고의 필수 매개변수 | 102 |
| af\_콘텐츠\_유형 | 제품 카테고리<br /><br />**메타 광고** 다이내믹 광고의 필수 매개변수 | 신발 |
| af\_통화 | 제품 상세 정보 페이지의 통화 | THB, USD |

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="목록 보기 (af_list_view)">

**목적**

구매자가 가장 많이 보는 목록(예를 들어, 새로 추가된 제품, 관련 제품 또는 권장 제품)을 기록합니다.

**트리거**

사용자가 특정 목록을 보는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_콘텐츠\_유형 | 목록 유형 | 연관, 추천, 신상품 |
| af\_content\_list | 카테고리의 콘텐츠 ID 목록 | 001, 092 |

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="위시리스트에 추가 (af_add_to_wishlist)">

**목적**

구매자가 찜한 목록에 추가하는 제품 및 카테고리를 기록합니다. 어떤 제품이 위시리스트에 가장 자주 추가되는지를 알게 되면, 이 제품을 할인 판매하거나 좋은 조건을 제시하여 구매를 촉진할 수 있습니다. 찜한 목록에 추가한 제품에 따라 사용자를 리타겟팅할 수도 있습니다.

**트리거**

사용자가 아이템을 찜한 목록에 추가하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 | 제품의 가격 | 600 |
| af\_content\_id | 제품 ID | 300 |
| af\_콘텐츠\_유형 | 제품 카테고리 | 신발, 전자 제품 |
| af\_통화 | 제품 세부 사항 페이지에 표시되는 통화 | GBP |

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="장바구니에 추가 (af_add_to_cart)">

**목적**

사용자가 장바구니에 제품을 추가하는 시기를 기록합니다. 이 이벤트에 의해 다음을 확인할 수 있습니다.

* 구매자가 한 번의 구매에 추가하는 평균 제품 개수
* 두 개의 다른 제품을 추가할 때 걸리는 시간 간격
* 장바구니를 버리는 구매자 수

**트리거**

사용자가 제품을 장바구니에 추가하는 시기

**이벤트 파라미터**

| 필드 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 | 제품 가격 | 350, 1000 |
| af\_content | 해당되는 경우 국제 상품 번호(EAN) 또는 기타 제품 또는 콘텐츠 식별자<br /><br />**메타 광고** 다이내믹 광고의 필수 매개변수 | ABC123 |
| af\_content\_id | 제품 ID<br /><br />**메타 광고** 다이내믹 광고의 필수 매개변수 | 001, 092 |
| af\_콘텐츠\_유형 | 제품 유형<br /><br />**메타 광고** 다이내믹 광고의 필수 매개변수 | 셔츠, 신발 |
| af\_통화 | 제품 통화 | THB, USD |
| af\_수량 | 동일한 제품을 장바구니에 추가한 개수 | 2, 5 |

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="결제 시작(af_initiated_checkout)">

**목적**

구매자가 결제를 진행할 때 어떻게 행동하는지 이해합니다. 이 이벤트에 의해 다음을 확인할 수 있습니다.

* 구매 이벤트에서 평균 가격 대비 구매자가 결제할 때의 평균 가격
* 사용자가 결제 진행 후 제품을 추가 또는 삭제하는지 여부

**트리거**

사용자가 결제를 시작했지만 아직 완료하지 않은 경우

**이벤트 파라미터**

| 필드 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 | 장바구니에 담긴 총금액 | 4000 |
| af\_content\_id | 장바구니에 담긴 제품 ID | 221, 124 |
| af\_콘텐츠\_유형 | 제품 카테고리 목록 | 셔츠, 바지 |
| af\_통화 | 결제 시기의 통화 | THB |
| af\_수량 | 장바구니에 담긴 총 아이템 개수 | 2, 5 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="구매 (af_purchase)">

**목적**

앱에서 구매 경향에 대해 알 수 있습니다. 이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 광고 네트워크와 광고 에이전시 전반에 대한 사용자의 LTV 및 캠페인의 ROI를 알 수 있습니다.
* 사용자에게 가장 인기 있는 아이템이 어느 것인지 알 수 있습니다.
* 캠페인 타게팅을 최적화하기 위해서, 구매한 아이템 내역을 기반으로 크로스 캠페인을 진행할 수 있습니다.

**트리거**

사용자가 성공적인 구매 후 확인 페이지를 방문한 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> | 구매 추정 수익 | 1205.99 |
| af\_가격 | 전체 구매액 | 4000 |
| af\_content | 해당되는 경우 국제 상품 번호(EAN) 또는 기타 제품 또는 콘텐츠 식별자<br /><br />메타 광고**다이내믹 광고** **의 필수 매개변수** | ABC123 |
| af\_content\_id | 아이템 ID<br /><br />**메타 광고** 다이내믹 광고의 필수 매개변수 | 121, 262 |
| af\_콘텐츠\_유형 | 아이템 카테고리<br /><br />**메타 광고** 다이내믹 광고의 필수 매개변수 | 신발, 바지 |
| af\_통화 | 통화 코드 | AUD |
| af\_수량 | 장바구니에 담긴 아이템 개수 | 2, 5 |
| af\_주문\_id | 구매한 다음에 발생한 주문 ID | X123ABC |
| af\_영수증\_ID | 주문 ID<br /><br />**구매 유효성 검증을 위한 CRITEO 및 Google Ad Words의 필수 파라미터** | X123ABC |

</Accordion>

## 사용자 지정 이벤트에 대한 권장 구조

다음 섹션에서는 사용자 지정 이벤트 이름과 사용하도록 제안된 이벤트 파라미터를 포함한 이벤트 구조 목록을 제공합니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="first-purchase-first_purchase" />

<Accordion title="첫 번째 구매(first_purchase)">

**목적**

[구매](/docs/recommended-ecommerce-app-events#purchase-af_purchase) 이벤트와 동일합니다. 또한 이 이벤트를 통해 다음을 확인할 수 있습니다.

* 새 구매자가 구매하는 데 걸리는 시간
* 최초 구매자가 구매하려고 하는 제품
* 최초 구매의 평균 가격과 수익

**트리거**

사용자가 첫 구매를 완료하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> | 구매 수익 | 1205.99 |
| af\_가격 | 전체 구매액 | 4000 |
| af\_content | 해당되는 경우 국제 상품 번호(EAN) 또는 기타 제품 또는 콘텐츠 식별자<br /><br />**메타 광고** 다이내믹 광고의 필수 매개변수 | ABC123 |
| af\_content\_id | 아이템 ID<br /><br />**메타 광고** 다이내믹 광고의 필수 매개변수 | 121, 262 |
| af\_콘텐츠\_유형 | 아이템 카테고리<br /><br />**메타 광고** 다이내믹 광고의 필수 매개변수 | 신발, 바지 |
| af\_통화 | 통화 | AUD |
| af\_수량 | 장바구니에 담긴 아이템 개수 | 2, 5 |
| af\_주문\_id | 구매한 다음에 발생한 주문 ID | X123ABC |
| af\_영수증\_ID | 주문 ID<br /><br />CRITEO 및 Google Ad Words 리타게팅 연동에 필요한 파라미터 | X123ABC |

</Accordion>

<div id="remove-from-cart-remove_from_cart" />

<Accordion title="장바구니에서 삭제(remove_from_cart)">

**목적**

이 이벤트 기록을 통해 다음을 할 수 있습니다:

* 구매자가 장바구니에서 삭제하는 항목 확인
* 구매자가 장바구니에서 삭제하는 제품 아이템 카테고리 확인
* [장바구니에 담기](/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart) 이벤트의 데이터와 비교하여, 결제하지 않은 제품에 대한 통찰력을 얻을 수 있습니다.

**트리거**

사용자가 장바구니에서 아이템을 삭제하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_content\_id | 아이템 또는 제품 ID | 521 |
| af\_콘텐츠\_유형 | 아이템 또는 제품 카테고리 | 신발 |

</Accordion>

<div data-zendesk-anchors="ecommerce=-ecommerce h_01HGTAWG2166CZYKJE9166G12J=-ecommerce h_01HGTAWG21Z0C9SR2G54W68G8Q=%EC%A4%91%EC%9A%94 recommended-structures-for-predefined-events=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAWG2115VB3A8J2WG3DJKK=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAWG21EQ0FE40WGFJRDJY5=complete-registration-af_complete_registration h_01HGTAWG22HFZ24V2BDCH3RFN8=login-af_login h_01HGTAWG22B5Z9AXENDATKR67T=search-af_search h_01HGTAWG22PSKS80ZQNAC0K24M=content-view-af_content_view h_01HGTAWG2219SVQ86PT1K3TVV9=list-view-af_list_view h_01HGTAWG22EQMVWXJCXC2KQDX8=add-to-wishlist-af_add_to_wishlist h_01HGTAWG23T81SPFJEA6BY5F2W=add-to-cart-af_add_to_cart h_01HGTAWG23FPKQ6RHJ9VYET63Y=initiated-checkout-af_initiated_checkout h_01HGTAWG2385E9Q0FXZXEW38YK=purchase-af_purchase recommended-structures-for-custom-events=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAWG235EXE17EJ5DWQYERM=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAWG23NTG0Q70B9A3685AD=first-purchase-first_purchase h_01HGTAWG239TQ51Z7FQW4FC1TZ=remove-from-cart-remove_from_cart" />
