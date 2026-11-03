---
title: 추천 통신 앱 이벤트
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
  created_at: '2021-05-02T11:59:16Z'
  edited_at: '2026-10-14T10:34:11Z'
  id: 360019896558
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/360019896558
---
> **요약: 요약:** 통신 앱에 대해 제안된 인앱 이벤트를 기록하여 사용자 여정 내내 사용자의 특성을 측정합니다/strong>.

## <Image alt="telecommunications_icon.png" src="https://files.readme.io/42f1aac3b825957d9d0584d83480c441b9d53665cc6cf1a6b8cd1803bb9b6121-20659194885393.png" width="100px" /> Telecommunication

통신 앱을 통해 사용자는 휴대폰 요금제, 데이터 요금제 등을 구입하고 관리할 수 있습니다. 기록을 제안하는 대표적인 이벤트는 구매, 추가 지불 및 구독입니다.

이런 이벤트 기록에 의해 다음을 확인할 수 있습니다.

* 가장 인기 있는 게이트웨이 플랜
* 사용자가 제공할 수 있는 제품 또는 패키지
* 고객으로부터 장기적인 약속을 받을 가능성이 가장 높은 플랜

> 🚧 **중요!**
>
> * 인앱 이벤트 구현과 관련한 마케터용 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#인앱-이벤트-설정">지침</Anchor>을 반드시 읽어보십시오.
> * 구현 프로세스를 간소화하려면 당사의 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=telecommunication">인앱 이벤트 생성기</Anchor>를 사용하십시오. 이 도구에는 본 문서에서 설명한 일반적인 인앱 이벤트가 모두 포함되어 있으며 사용자는 비즈니스 요구사항에 따라 이벤트를 수정할 수 있습니다. 완료되면 파일을 개발사와 공유하십시오.
> * 본 문서에 포함된 각 권장 이벤트에 대해 iOS, 안드로이드 및 Unity 개발자를 위한 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=telecommunication&view=code">코드 샘플</Anchor>이 있습니다.
> * 개발사에 대한 자세한 지침은 **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">앱스플라이어 개발자 허브</Anchor>** 에서 확인할 수 있습니다.
>
> 인앱 이벤트 기록에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트 가이드를</Anchor> 참조하십시오.

[![Flowchart_for_recommended_events_telecommunication_app_user_journey](https://files.readme.io/ae4c696208b49aa546ffc0a15f76b148b35af43984a76e699d1df7c54507352c-4404604045457.png)](https://files.readme.io/ae4c696208b49aa546ffc0a15f76b148b35af43984a76e699d1df7c54507352c-4404604045457.png)

## 사전 정의된 이벤트에 권장되는 구조

다음 섹션에서는 통신 수직 구조에 일반적인 이벤트 구조 목록을 제공합니다. 각 구조에는 사용할 미리 정의된 이벤트 이름과 제안된 이벤트 파라미터가 포함됩니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

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

<div id="content-view-af_content_view" />

<Accordion title="콘텐츠 보기 (af_content_view)">

**목적**

특정 제품의 열람률을 확인합니다.

* 제품 판매와 열람과의 상관 관계를 알 수 있습니다.
* 어떤 카테고리가 가장 인기가 있는지 제품 열람을 통해 알 수 있습니다.
* 구매자가 보고 있는 제품과 통화와의 상관 관계를 알 수 있습니다.

**트리거**

사용자가 특정 제품 세부 사항 페이지 열람 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 | 제품 가격 | 200 |
| af\_content\_id | 제품 ID | 102 |
| af\_콘텐츠\_유형 | 제품 카테고리 | 인터넷 패키지 |
| af\_통화 | 제품 상세 정보 페이지의 통화 | THB, USD |

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="목록 보기 (af_list_view)">

**목적**

구매자가 가장 많이 보는 목록(예: 새로 추가된 제품, 관련 제품 또는 권장 제품)을 기록합니다.

**트리거**

사용자가 특정 목록을 보는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_콘텐츠\_유형 | 목록 유형 | 연관, 추천, 신상품 |
| af\_content\_list | 카테고리의 콘텐츠 ID 목록 | 001, 092 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="구매 (af_purchase)">

**목적**

많은 통신 앱에서 사용자는 추가 데이터와 같은 아이템을 구매할 수 있습니다. 이 이벤트 기록을 통해 다음을 할 수 있습니다:

* 광고 네트워크와 광고 에이전시 전반에 대한 사용자의 LTV 및 캠페인의 ROI를 알 수 있습니다.
* 사용자에게 가장 인기있는 아이템이 무엇인지 알 수 있습니다.
* 캠페인 타게팅을 최적화하기 위해서, 구매한 아이템 내역을 기반으로 크로스 캠페인을 진행할 수 있습니다.

**트리거**

사용자가 성공적인 구매 후 확인 페이지를 방문한 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> | 구매 추정 수익 | 2050.50 |
| af\_통화 | 통화 코드 | THB |
| af\_콘텐츠\_유형 | 구입한 패키지 이름 | 5G |
| af\_주문\_id | 주문 ID | 9277 |
| payment\_method\_type | 결제 수단 유형 | 신용 카드, 지역 결제 |

</Accordion>

## 사용자 지정 이벤트에 대한 권장 구조

다음 섹션에서는 사용자정의 이벤트 이름과 사용할 제안된 이벤트 파라미터가 포함된 이벤트 구조를 제공합니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="select-package-select_package" />

<Accordion title="패키지 선택(select_package)">

**목적**

**트리거**

사용자가 패키지를 선택하였지만 결제를 완료하지 못한 경우

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| 가격 | 구독 가격 | 50000 |
| af\_콘텐츠\_유형 | 사용자가 선택한 콘텐츠 유형 | 데이터 5GB |

</Accordion>

<div id="topup-success-top_up_success" />

<Accordion title="톱업 성공(top_up_success)">

**목적**

톱업 펀드는 앱 내에서 제공되는 패키지나 다른 서비스를 구매하는 데 사용할 수 있습니다. 이런 이벤트를 기록하고, 다른 이벤트와 비교하여 사용자에 대해 더 자세히 이해할 수 있습니다. 예를 들어, 사람들이 자신의 계정에 예치할 의향이 있는 금액을 확인하고 예산 내에서 맞춤형 캠페인을 통해 그들을 대상으로 톱업 금액을 사용할 수 있습니다.

**트리거**

사용자가 톱업을 완료하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> | 톱업의 금액 | 2050.50 |
| top\_up\_id | 톱업의 ID | 397 |
| payment\_method\_type | 결제 수단 유형 | 신용 카드, 지역 결제 |

</Accordion>

<div id="topup-unsuccessful-top_up_unsuccessful" />

<Accordion title="톱업 실패(top_up_unsuccessful)">

**목적**

이런 이벤트를 기록하고, 다른 이벤트와 비교하여 사용자에 대해 더 자세히 이해할 수 있습니다. 예를 들어, 몇 명의 사용자가 톱업을 시도하지만 실패했는지 알 수 있습니다.

**트리거**

사용자가 톱업을 시도했지만 조치가 실패했을 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| error\_reason | 톱업 실패 이유 | exceeded\_daily\_limit |

</Accordion>

<div id="subscription-complete-subscription_complete" />

<Accordion title="구독 완료(subscription_complete)">

**목적**

이 이벤트 기록을 통해 다음을 할 수 있습니다:

* 사용자를 구독까지 유도한 캠페인이 무엇인지 알 수 있습니다.
* 구독한 사용자와 구독하지 않은 사용자 수를 비교합니다.
* 구독에서 발생한 수익을 기록하고 캠페인이나 미디어소스로 어트리뷰트 할 수 있습니다.

**트리거**

* 사용자가 성공적으로 구독 신청을 했을 때
* 구독이 갱신되었을 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| subscription\_type | 구독 유형 | 월 30GB |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 구독 금액 | 555.50 |

</Accordion>

<div data-zendesk-anchors="telecommunication=-telecommunication h_01HGTAGFNFWKWYHPG6F5EK17YD=-telecommunication h_01HGTAGFNG1Z8NAFJ71DP0YSYD=%EC%A4%91%EC%9A%94 recommended-structures-for-predefined-events=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAGFNG99PQC03F13WQ4CVK=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAGFNGQ56C8CN7A325SQ7M=login-af_login h_01HGTAGFNG1W5QWGN1D969JHGY=complete-registration-af_complete_registration h_01HGTAGFNGRJHD89332473DZFE=content-view-af_content_view h_01HGTAGFNG10GNZVMDNXRJSYJ9=list-view-af_list_view h_01HGTAGFNGV82NQSZ29B96YJCQ=purchase-af_purchase recommended-structures-for-custom-events=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAGFNG3A2A6KCX8GGQAJBX=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAGFNGE3MKZEDKDZ0B9XDD=select-package-select_package h_01HGTAGFNGFSE2DAYRGG039GT9=topup-success-top_up_success h_01HGTAGFNGXBBYWJEMBVMN1YQS=topup-unsuccessful-top_up_unsuccessful h_01HGTAGFNGT3CJFRS2YC7R57KG=subscription-complete-subscription_complete" />
