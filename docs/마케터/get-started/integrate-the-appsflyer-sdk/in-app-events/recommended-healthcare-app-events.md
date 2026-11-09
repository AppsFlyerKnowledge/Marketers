---
title: 추천 헬스케어 앱 이벤트
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
  created_at: '2021-05-01T10:41:05Z'
  edited_at: '2026-10-14T10:26:21Z'
  id: 360019888518
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/360019888518
---
> **한눈에 보기:** 요약: 헬스케어 앱에 대한 샘플 인앱이벤트를 기록하여 사용자 여정 내내 사용자의 품질을 측정합니다.

## <Image alt="5669_Healthcare_icon_3.png" src="https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png" width="100px" /> Healthcare

헬스케어 앱을 통해 사용자는 건강보험 가입하기, 예약하기, 의료 자문 받기 등의 작업을 수행할 수 있습니다. 기록되는 일반적인 이벤트에는 로그인, 등록 및 개인 정보나 건강 정보가 없는 기타 일반 이벤트가 포함됩니다.

<div id="important" />

> 🚧 **중요!**
>
> * 변호사의 조언: 건강 데이터는 "제한된 데이터"로 간주되며 많은 관할 구역에서 데이터의 특별한 범주로 간주됩니다. 따라서 고객은 이러한 데이터를 앱스플라이어에 보낼 수 없습니다.
> * 인앱 이벤트 구현과 관련한 마케터용 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#인앱-이벤트-설정">지침</Anchor>을 반드시 읽어보십시오.
> * 구현 프로세스를 간소화하려면 당사의 인앱 이벤트 생성기를 사용하십시오. 이 도구에는 본 문서에서 설명한 일반적인 인앱 이벤트가 모두 포함되어 있으며 사용자는 비즈니스 요구사항에 따라 이벤트를 수정할 수 있습니다. 완료되면 파일을 개발사와 공유하십시오.
> * 본 문서에 포함된 각 권장 이벤트에 대해 iOS, 안드로이드 및 Unity 개발자를 위한 <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=healthcare&view=code">코드 샘플</Anchor>이 있습니다.
> * 개발사에 대한 자세한 지침은 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">앱스플라이어 개발자 허브</Anchor>에서 확인할 수 있습니다.
>
> 인앱 이벤트 기록에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트 가이드를</Anchor> 참조하십시오.

<Image align="center" alt="In_appEvents_UserJourneys_-_Copy_of_Healthcare__1_.png" src="https://files.readme.io/54174e697c8dfe2d0d388c19fdd5fa0fbf9703c0155b9c250b40b5d0bcf19698-8232949117073.png" />

<div id="recommended-structures-for-predefined-events" />

## 사전 정의된 이벤트에 권장되는 구조

다음 섹선에서는 의료 서비스 수직 구조에 일반적인 이벤트 구조 목록을 제공합니다. 각 구조에는 사용할 미리 정의된 이벤트 이름과 샘플 이벤트 파라미터가 포함됩니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="login-af_login" />

<Accordion title="로그인 (af_login)">

**목적**

등록된 사용자의 잔존율 파악

**트리거**

사용자가 성공적으로 로그인할 때마다

**이벤트 파라미터**

추가 파라미터 없이 전송 가능

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="등록 완료 (af_complete_registration)">

**목적**

앱을 설치하고 등록 프로세스를 완료한 사용자 수와 사용자가 선호하는 등록 방법에 대해 알아봅니다.

**트리거**

사용자가 등록 프로세스를 완료한 시간

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_registration\_method | 가입 방법의 유형 | 이메일, 페이스북 |

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="장바구니에 추가 (af_add_to_cart)">

**목적**

이 이벤트에 의해 다음을 확인할 수 있습니다.

* 구매자가 한 번의 구매에 추가하는 평균 제품 개수
* 두 개의 다른 제품을 추가할 때 걸리는 시간 간격
* 장바구니를 버리는 구매자 수

**트리거**

사용자가 제품을 장바구니에 추가하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_수량 | 주문 금액 | 1 |
| af\_가격 | 제품의 가격 | 10 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="구매 (af_purchase)">

**목적**

사용자의 인앱 구매를 기록합니다. 이 이벤트는 다음을 제공합니다.

* 광고 네트워크와 광고 에이전시 전반에 대한 사용자의 LTV 및 캠페인의 ROI를 알 수 있습니다.
* 사용자에게 가장 인기있는 아이템이 무엇인지 알 수 있습니다.
* 캠페인 타게팅을 최적화하기 위해서, 구매한 아이템 내역을 기반으로 크로스 캠페인을 진행할 수 있습니다.

**트리거**

사용자가 성공적인 구매 후 확인 페이지를 방문한 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> | 구매 수익 | 50.55 |
| af\_통화 | 통화 코드 | USD |
| af\_주문\_id | 주문 ID | 9277 |
| payment\_method\_type | 사용한 결제 수단 | 신용 카드, 현지 |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## 사용자 지정 이벤트에 대한 권장 구조

다음 섹션에서는 사용자 지정 이벤트 이름과 사용할 샘플 이벤트 파라미터를 포함하는 이벤트 구조를 제공합니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="topup-success-top_up_success" />

<Accordion title="톱업 성공(top_up_success)">

**목적**

톱업 펀드는 앱 내에서 제공되는 패키지나 서비스를 구매하는 데 사용할 수 있습니다. 이런 이벤트를 기록하고, 다른 이벤트와 비교하여 사용자에 대해 더 자세히 이해할 수 있습니다. 예를 들어, 사람들이 자신의 계정에 예치할 의향이 있는 금액을 확인하고 보충 예산 내에서 맞춤형 캠페인을 통해 사용자를 대상으로 톱업 금액을 사용할 수 있습니다.

**트리거**

사용자가 톱업을 완료하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> | 톱업의 금액 | 2000.55 |
| top\_up\_id | 톱업의 ID | 397 |
| payment\_method\_type | 사용한 결제 수단 | 신용 카드, 지역 결제 |

</Accordion>

<div data-zendesk-anchors="healthcare=-healthcare h_01HGTAFRKKJ22SHB4JHMTGW2TV=-healthcare h_01HGTAFRKKPWC1PQTKF227WWBD=%EC%A4%91%EC%9A%94 recommended-structures-for-predefined-events=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAFRKKRB8EY8KJ9NXM4Z2T=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAFRKK35Q5W5ADQC2KYHR9=login-af_login h_01HGTAFRKK8E52FRVWQXP4Y3VV=complete-registration-af_complete_registration h_01HGTAFRKN6NJPDB053YYYH202=add-to-cart-af_add_to_cart h_01HGTAFRKNJVFECSFGSWG8B7GN=purchase-af_purchase recommended-structures-for-custom-events=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAFRKN29RJRW2V2WCH2AXT=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAFRKNDWHDDR9KDRKJ4H8E=topup-success-top_up_success" />
