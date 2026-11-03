---
title: 추천 항공편 예약 앱 이벤트
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
  created_at: '2021-04-29T13:07:29Z'
  edited_at: '2026-10-14T10:30:59Z'
  id: 360019670857
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/360019670857
---
> **한눈에 보기:** 요약: 항공권 예약 앱에 대해 제안된 인앱 이벤트를 기록하여 사용자 여정 내내 사용자의 질을 측정합니다.

## <Image alt="InApp_Events_flight.png" src="https://files.readme.io/7a09c4a641dd5e797bffc41a6e66b20efe5660721f37abac3dd12ac83688b37b-20659533911697.png" width="100px" /> Flight booking

여행자는 항공편 예약 앱으로 가장 좋은 조건이 제시된 항공권을 쉽게 예약할 수 있습니다. 기록을 제안하는 대표적인 이벤트는 항공권 예약, 항공권 검색, 그리고 할인 행사 열람입니다.

이벤트 기록을 통해 다음을 할 수 있습니다.

* 인기 목적지를 알 수 있습니다.
* 계절별 트렌드 분석
* 사용자가 여행할 때 선호하는 인기 항공사 알아보기

> 🚧 **중요!**
>
> * 인앱 이벤트 구현과 관련한 마케터용 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#인앱-이벤트-설정">지침</Anchor>을 반드시 읽어보십시오.
> * 구현 프로세스를 간소화하려면 당사의 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=flight_booking">인앱 이벤트 생성기</Anchor>를 사용하십시오. 이 도구에는 본 문서에서 설명한 일반적인 인앱 이벤트가 모두 포함되어 있으며 사용자는 비즈니스 요구사항에 따라 이벤트를 수정할 수 있습니다. 완료되면 파일을 개발사와 공유하십시오.
> * 본 문서에 포함된 각 권장 이벤트에 대해 iOS, 안드로이드 및 Unity 개발자를 위한 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=flight_booking&view=code">코드 샘플</Anchor>이 있습니다.
> * 개발사에 대한 자세한 지침은 **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">앱스플라이어 개발자 허브</Anchor>** 에서 확인할 수 있습니다.
>
> 인앱 이벤트 기록에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트 가이드를</Anchor> 참조하십시오.

[![Flowchart_for_recommended_events flight_booking_app_user_journey](https://files.readme.io/435378707a7299a8c98bc7490f0f1554b5f6c332a35c1546ce34feb1b6b86394-360020171258.png)](https://files.readme.io/435378707a7299a8c98bc7490f0f1554b5f6c332a35c1546ce34feb1b6b86394-360020171258.png)

## 사전 정의된 이벤트에 권장되는 구조

다음 섹션에서는 항공권 예약 수직 구조에 일반적인 이벤트 구조 목록을 제공합니다. 각 구조에는 사용할 미리 정의된 이벤트 이름과 제안된 이벤트 파라미터가 포함됩니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="complete-registration-af_complete_registration" />

<Accordion title="가입 완료(af_complete_registration)">

**목적**

앱을 설치하고 등록 프로세스를 완료한 사용자 수와 사용자가 선호하는 등록 방법에 대해 알아봅니다.

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

<div id="travel-booking-af_travel_booking" />

<Accordion title="여행 예약 (af_travel_booking)">

**목적**

항공권 예약은 이 앱의 핵심 기능입니다. 이 이벤트에 의해 다음을 확인할 수 있습니다.

* 인기 목적지
* 인기 항공사
* 계절별 트렌드

**트리거**

사용자가 항공권 예약을 성공적으로 마치고 예약 확인 페이지를 방문한 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> | 예약과 연결된 수익 | 647.99 |
| af\_통화 | 통화 코드 | SGD |
| af\_가격 | Price | 674 |
| af\_content\_id | 제시된 항공권 ID |  |
| af\_departing\_departure\_date | 출발일 | 2018-06-21 |
| af\_귀국 출발 날짜 | 도착일 | 2018-06-26 |
| af\_목적지\_a | 첫 번째 목적지 |  |
| af\_목적지\_b | 두 번째 목적지(해당할 경우) | SYD |
| airline\_code | 항공사 코드 | KLM |
| af\_class | 예약 항공권 클래스 | economy |
| purchase\_method | 구매에 사용한 방법 | credit card |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="콘텐츠 보기 (af_content_view)">

**목적**

이 이벤트에 의해 다음을 확인할 수 있습니다.

* 사용자의 관심이 가장 많은 항공권 제시 조건
* 검색 결과가 검색 조회와 연관이 있는지 여부

**트리거**

사용자가 검색 결과를 클릭한 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_departing\_departure\_date | 출발일 | 2018-06-21 |
| af\_귀국 출발 날짜 | 도착일 | 2018-06-26 |
| af\_목적지\_a | 첫 번째 목적지 |  |
| af\_목적지\_b | 두 번째 목적지(해당할 경우) | SYD |

</Accordion>

<div id="search-af_search" />

<Accordion title="검색 (af_search)">

**목적**

사용자는 항공권 예약 앱에서 항공권과 특가 상품을 검색합니다. 사용자 선호도에 대한 인사이트를 얻는 가장 좋은 방법은 검색 파라미터를 기록하는 것입니다. 이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 사용자가 찾고 있는 것을 알아보기
* 가장 인기있는 목적지가 어디인지 알 수 있습니다.
* 얼마나 많은 사용자가 어린이와 함께 여행하는지 알 수 있습니다.
* 일 년 중 언제 사용자가 여행을 계획하고, 여행을 하고 싶어 하는지를 알 수 있습니다.

**트리거**

사용자가 검색 양식에 기입하고 검색 버튼을 클릭한 후

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_어린이\_수 | 자녀 여행자 수 | 0 |
| af\_목적지\_a | 첫 번째 목적지 |  |
| af\_목적지\_b | 두 번째 목적지(해당할 경우) | SYD |
| af\_departing\_departure\_date | 출발일 | 2018-06-21 |
| af\_귀국 출발 날짜 | 도착일 | 2018-06-26 |
| af\_유아\_수 | 유아 여행자 수 | 0 |
| af\_성인\_수 | 성인 여행자 수 | 1 |

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="결제 정보 추가(af_add_payment_info)">

**목적**

항공권 예약 시에 결제 정보 추가 시도의 성공 여부를 기록할 수 있습니다.

**트리거**

사용자가 항공권 예약 버튼을 클릭할 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_success | 결제 수단 추가 성공 여부 | true |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="구매 (af_purchase)">

**목적**

항공권 예약 앱에서 구매 경향에 대해 알 수 있습니다. 이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

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
| af\_콘텐츠\_유형 | 아이템 카테고리 | flight |
| af\_통화 | 통화 코드 | AUD |
| af\_수량 | 장바구니에 담긴 아이템 개수 | 1 |
| af\_주문\_id | 구매한 다음에 발생한 주문 ID | X123ABC |
| af\_영수증\_ID | CRITEO 및 Google 애드워즈 리타게팅 연동에 필요한 주문 ID | X123ABC |

</Accordion>

## 사용자 지정 이벤트에 대한 권장 구조

다음 섹션에서는 사용자 지정 이벤트 이름과 사용하도록 제안된 이벤트 파라미터를 포함한 이벤트 구조 목록을 제공합니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="first-purchase-first_purchase" />

<Accordion title="첫 번째 구매(first_purchase)">

**목적**

[구매](/docs/recommended-flight-booking-app-events#purchase-af_purchase) 이벤트와 동일합니다. 또한 이 이벤트를 통해 다음을 확인할 수 있습니다.

* 새 구매자가 구매하는 데 걸리는 시간
* 최초 구매자가 구매하고 싶어 하는 제품
* 최초 구매의 평균 가격과 수익

**트리거**

사용자가 첫 구매를 완료하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> | 구매 수익 | 1205.99 |
| af\_가격 | 전체 구매액 | 4000 |
| af\_content\_id | 아이템 ID | 121, 262 |
| af\_콘텐츠\_유형 | 아이템 카테고리 | flight |
| af\_통화 | 통화 | AUD |
| af\_수량 | 장바구니에 담긴 아이템 개수 | 1 |
| af\_주문\_id | 구매한 다음에 발생한 주문 ID | X123ABC |
| af\_영수증\_ID | CRITEO 및 Google 애드워즈 리타겟팅 연동에 필요한 주문 ID | X123ABC |

</Accordion>

<div data-zendesk-anchors="flight-booking=-flight-booking h_01HGTAZRKG0SQ66XK7VN9KVGEY=-flight-booking h_01HGTAZRKGGQBBAM4XJHR4B45P=%EC%A4%91%EC%9A%94 recommended-structures-for-predefined-events=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAZRKHK1427YX16HWRDRPN=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAZRKHACHNSNX9DSZ3ZZ51=complete-registration-af_complete_registration h_01HGTAZRKHTC9TNWNPACRZW31Y=login-af_login h_01HGTAZRKHZGW442XTZF99VGV9=travel-booking-af_travel_booking h_01HGTAZRKHGY0Z83ETZWAFNSWP=content-view-af_content_view h_01HGTAZRKH8JYE8Q6NDPF1PQC7=search-af_search h_01HGTAZRKH78CR2GH0960MS8R0=add-payment-info-af_add_payment_info h_01HGTAZRKHXE8VF78ZE0KF9AF6=purchase-af_purchase recommended-structures-for-custom-events=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAZRKH4ZZEK5JGXZ7G5QDJ=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAZRKHG7GE4BKFDRHZC163=first-purchase-first_purchase" />
