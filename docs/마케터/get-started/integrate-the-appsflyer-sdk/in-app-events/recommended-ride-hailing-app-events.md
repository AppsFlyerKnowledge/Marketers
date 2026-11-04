---
title: 추천 승차 호출 앱 이벤트
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
  created_at: '2021-04-29T08:42:34Z'
  edited_at: '2026-10-14T10:31:32Z'
  id: 360019651957
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/360019651957
---
> **한눈에 보기:** 요약: 승차 공유 앱에 대해 제안된 인앱 이벤트를 기록하여 사용자 여정 내내 사용자의 질을 측정합니다.

## <Image alt="InApp_Events_ride.png" src="https://files.readme.io/3901cfcc0cc821cc9c93edbe806bc2d570698be366b76b3710cb60e9aa190d91-20659532208401.png" width="100px" /> Ride-hailing

승차 공유는 최근에 점점 더 인기를 얻고 있습니다. 특히 많은 사람이 차를 소유하지 않는 도심 지역에서 더욱 인기입니다. 기록을 제안하는 대표적인 이벤트는 승차 요청 및 예약입니다.

이벤트 기록으로 다음을 확인할 수 있습니다.

* 승객과 운전사가 어떻게 서로 소통하는지 알 수 있습니다.
* 차량 공유 서비스를 더 많이 이용하는 국가를 알 수 있습니다.
* 요금, 탑승 횟수, 탑승 거리 등의 지표

<div id="important" />

> 🚧 **중요!**
>
> * 인앱 이벤트 구현과 관련한 마케터용 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#인앱-이벤트-설정">지침</Anchor>을 반드시 읽어보십시오.
> * 구현 프로세스를 간소화하려면 당사의 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ride_hailing">인앱 이벤트 생성기</Anchor>를 사용하십시오. 이 도구에는 본 문서에서 설명한 일반적인 인앱 이벤트가 모두 포함되어 있으며 사용자는 비즈니스 요구사항에 따라 이벤트를 수정할 수 있습니다. 완료되면 파일을 개발사와 공유하십시오.
> * 본 문서에 포함된 각 권장 이벤트에 대해 iOS, 안드로이드 및 Unity 개발자를 위한 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ride_hailing&view=code">코드 샘플</Anchor>이 있습니다.
> * 개발사에 대한 자세한 지침은 **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">앱스플라이어 개발자 허브</Anchor>** 에서 확인할 수 있습니다.
>
> 인앱 이벤트 기록에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트 가이드를</Anchor> 참조하십시오.

[![Flowchart_for_recommended_events_ride_hailing_app_user_journey](https://files.readme.io/5ec4efcc699ef8749e1d5cd6e693472713f3d7945a41e1601965d0e7cdb68706-4402678863377.png)](https://files.readme.io/5ec4efcc699ef8749e1d5cd6e693472713f3d7945a41e1601965d0e7cdb68706-4402678863377.png)

<div id="recommended-structures-for-predefined-events" />

## 사전 정의된 이벤트에 권장되는 구조

다음 섹선에서는 승차공유 수직 구조에 일반적인 이벤트 구조 목록을 제공합니다. 각 구조에는 사용할 미리 정의된 이벤트 이름과 제안된 이벤트 파라미터가 포함됩니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="complete-registration-af_complete_registration" />

<Accordion title="가입 완료(af_complete_registration)">

**목적**

이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 사용자가 선호하는 가입 방법이 무엇인지 알 수 있습니다.
* 앱을 다운로드하고 설치한 후에 얼마나 많은 사용자가 가입하는지 알 수 있습니다.
* 앱을 가장 많이 이용하는 사용자가 속한 국가를 파악하여 국가 전반의 등록 트렌드를 알 수 있습니다.

**트리거**

사용자가 등록 프로세스를 완료한 시간

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_registration\_method | 사용자가 가입하는 방법 또는 플랫폼 | Facebook |
| country\_code | 국가 코드(전화 코드) | 66 |

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

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="결제 정보 추가(af_add_payment_info)">

**목적**

사용자 분류에 도움을 줍니다. 다음을 수행할 수 있습니다.

* 사용자가 결제 정보를 추가하는 데 얼마나 걸리는지 알 수 있습니다.
* 가장 선호하는 결제 수단(예: 신용카드 또는 전자 지갑)
* 많이 사용되는 결제 수단의 제공업체와 캠페인을 설정하여 협업할 수 있습니다.

**트리거**

사용자가 계정에 결제 정보를 성공적으로 추가하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_success | 지급 방법의 성공 여부 | true |
| credit\_card\_type | 신용카드 유형(옵션) | 비자, 마스터카드 |
| payment\_method\_type | 결제 수단 유형 | 신용 카드, 전자 지갑 |

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="지출된 크레딧 (af_spent_credits)">

**목적**

이 파라미터는 탑승할 때마다 승객이 받는 크레딧을 기록합니다. 승객은 크레딧을 바우처나 요금 할인으로 교환할 수 있습니다.

이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 얼마나 많은 승객이 크레딧을 바우처로 교환했는지 알 수 있습니다.
* 승객이 선호하는 바우처나 요금 할인은 어떤 것인지 알 수 있습니다.

**트리거**

승객이 크레딧을 소비할 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_content | 바우처 또는 할인 유형 | 단일 영화 티켓 |
| credits\_used | 사용한 크레딧 | 1000 |
| credits\_remaining | 계정에 남은 크레딧 | 2090 |
| invoice\_id | 사용한 크레딧에 대해 생성된 청구서의 ID | KO215123SD |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## 사용자 지정 이벤트에 대한 권장 구조

다음 섹션에서는 사용자 지정 이벤트 이름과 사용하도록 제안된 이벤트 파라미터를 포함한 이벤트 구조 목록을 제공합니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="ride-booking-requested-ride_booking_requested" />

<Accordion title="승차 예약 요청함(ride_booking_requested)">

**목적**

이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 인기 목적지를 알 수 있습니다.
* 사람들이 어디에서 어디로 가는지 트렌드를 알 수 있습니다.
* 평균 탑승 거리를 알 수 있습니다.
* 가장 많은 사용자가 있는 도시, 지역, 국가를 알 수 있습니다.

추가로, 다른 예약 관련 이벤트와 함께 이 이벤트를 기록함으로써 성공한 건을 기록할 수 있습니다. 그런 다음, 성공한 건을 성공하지 못한 건과 비교할 수 있습니다. 예를 들어, 얼마나 많은 예약이 요청되었고, 얼마나 많은 탑승 예약이 완료되었거나 취소되었는지 알 수 있습니다.

**트리거**

승객이 승차 예약 요청을 한 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 | 탑승 견적 가격 | 22.4 |
| af\_통화 | 통화 | SGD |
| af\_목적지\_a | 출발지 | Plaza Singapura |
| af\_목적지\_b | 도착지 | Marina Bay Sands |
| distance | 두 목적지 사이의 거리 | 5.2 |
| af\_콘텐츠\_유형 | 운송 유형 | Taxi |
| payment\_method\_type | 결제 수단 유형 | 신용 카드, 전자 지갑 |
| af\_city | 승차를 예약한 도시 | 싱가포르 |
| af\_지역 | 승차 예약 지역 | SFA |
| af\_country | 승차를 예약한 국가 | 싱가포르 |
| 주문\_ID | 주문 ID | 135790 |

</Accordion>

<div id="ride-booking-confirmed-ride_booking_confirmed" />

<Accordion title="탑승 예약 확인됨(ride_booking_confirmed)">

**목적**

이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 가장 활발하게 활동하는 운전자가 누구인지 알 수 있습니다.
* 운전자 사이에서 공통적인 목적지를 알 수 있습니다.
* 각 운전자의 평균 및 전체 탑승 요금을 알 수 있습니다.

추가로, 다른 세 가지 예약 관련 이벤트와 함께 이 이벤트를 기록하면 운전자 활동에 대해 더 잘 이해할 수 있습니다. 어느 운전자가 승차 예약 요청을 가장 많이 확인하고, 어느 운전자가 단거리 또는 장거리를 선택하는지 등을 알 수 있습니다.

<div id="trigger" />

#### **트리거**

운전자가 예약을 승인한 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 | 탑승 견적 가격 | 22.4 |
| af\_통화 | 통화 | SGD |
| af\_목적지\_a | 출발지 | Plaza Singapura |
| af\_목적지\_b | 도착지 | Marina Bay Sands |
| distance | 두 목적지 사이의 거리 | 5.2 |
| af\_콘텐츠\_유형 | 운송 유형 | Taxi |
| driver\_id | 탑승 수행을 확인한 운전자 ID | 1706 |
| payment\_method\_type | 결제 수단 유형 | 신용 카드, 전자 지갑 |
| af\_city | 승차를 예약한 도시 | 싱가포르 |
| af\_지역 | 승차 예약 지역 | SFA |
| af\_country | 승차를 예약한 국가 | 싱가포르 |
| af\_주문\_id | 주문 ID | 135790 |

</Accordion>

<div id="ride-booking-canceled-ride_booking_canceled" />

<Accordion title="승차 예약 취소됨(ride_booking_canceled)">

**목적**

이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 계속 취소하는 운전자나 승객을 기록할 수 있습니다.
* 얼마나 많은 탑승이 취소되었는지 알 수 있습니다.
* 요금, 목적지, 거리 및 도시의 속성과 취소율의 상관 관계를 알 수 있습니다.
* 탑승 취소 이유를 알 수 있습니다.

**트리거**

예약이 취소될 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 | 탑승 견적 가격 | 22.4 |
| af\_통화 | 통화 | SGD |
| af\_목적지\_a | 출발지 | Plaza Singapura |
| af\_목적지\_b | 도착지 | Marina Bay Sands |
| distance | 두 목적지 사이의 거리 | 5.2 |
| af\_콘텐츠\_유형 | 운송 유형 | Taxi |
| driver\_id | 탑승을 확인한 운전자 ID | 1706 |
| cancelation\_reason | 탑승 취소 이유 | 가격이 너무 비쌉니다, 운전자가 없습니다, 승객이 없습니다. |
| payment\_method\_type | 결제 수단 유형 | 신용 카드, 전자 지갑 |
| af\_city | 승차를 예약한 도시 | 싱가포르 |
| af\_지역 | 승차 예약 지역 | SFA |
| af\_country | 승차를 예약한 국가 | 싱가포르 |
| 주문\_ID | 주문 ID | 135790 |
| canceled\_by | 취소 당사자가 운전자인지 승객인지 여부 | Passenger |

</Accordion>

<div id="ride-booking-completed-ride_booking_completed" />

<Accordion title="탑승 예약 완료됨(ride_booking_completed)">

**목적**

이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 승객의 지출 내역 및 운전자의 수입 내역을 알 수 있습니다.
* 목적지, 거리, 결제 수단, 운전자 ID 등의 속성과 탑승 완료와의 상관 관계를 알 수 있습니다.
* 운전자 및 승객의 평균 및 전체 탑승 거리를 알 수 있습니다.
* 완료된 탑승과 취소된 탑승을 비교할 수 있습니다.
* 운전자 평가 점수를 기록하고 기록할 수 있습니다.

**트리거**

운행이 완료되었을 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 | 탑승 견적 가격 | 22.4 |
| af\_통화 | 통화 | SGD |
| af\_목적지\_a | 출발지 | Plaza Singapura |
| af\_목적지\_b | 도착지 | Marina Bay Sands |
| distance | 두 목적지 사이의 거리 | 5.2 |
| af\_콘텐츠\_유형 | 운송 유형 | Taxi |
| driver\_id | 탑승 수행을 확인한 운전자 ID | 1706 |
| payment\_method\_type | 결제 수단 유형 | 신용 카드, 전자 지갑 |
| af\_city | 승차를 예약한 도시 | 싱가포르 |
| af\_지역 | 승차 예약 지역 | SFA |
| af\_country | 승차를 예약한 국가 | 싱가포르 |
| 주문\_ID | 주문 ID | 135790 |
| credits\_earned | 탑승을 완료할 때 승객이 받는 크레딧 | 248 |

</Accordion>

<div data-zendesk-anchors="ridehailing=-ride-hailing h_01HGTAZ7J64RZE35JP8XPKMTPZ=-ride-hailing h_01HGTAZ7J6N36EH492QDXCQYB1=%EC%A4%91%EC%9A%94 recommended-structures-for-predefined-events=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAZ7J6FJ8R9VXKK0F1A1E1=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAZ7J6FQQKV7JB0Z9MG8CD=complete-registration-af_complete_registration h_01HGTAZ7J6YM8DJ96E7Q4M4Y8Q=login-af_login h_01HGTAZ7J67MNJ8T9B9W4NJ5Y9=add-payment-info-af_add_payment_info h_01HGTAZ7J6Z3EX03JTPZFHJJF6=spent-credits-af_spent_credits recommended-structures-for-custom-events=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAZ7J6Z6NE8D5A10CRJJH4=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAZ7J6WCY2BQJPSNSTJRQ0=ride-booking-requested-ride_booking_requested h_01HGTAZ7J78J1X3VAYMH8Q3ZBA=ride-booking-confirmed-ride_booking_confirmed trigger=%ED%8A%B8%EB%A6%AC%EA%B1%B0 h_01HGTAZ7J7C4R7A7KT2S95835J=%ED%8A%B8%EB%A6%AC%EA%B1%B0 h_01HGTAZ7J797KA791H1621F9TE=ride-booking-canceled-ride_booking_canceled h_01HGTAZ7J789CJ8P6X8B0V7A64=ride-booking-completed-ride_booking_completed" />
