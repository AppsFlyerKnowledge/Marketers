---
title: 추천 게임 앱 이벤트
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2021-04-06T14:46:54Z'
  edited_at: '2026-10-14T10:30:35Z'
  id: 360018941117
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/360018941117
---
> **한눈에 보기:** 요약: 게이밍 앱에 대해 제안된 인앱 이벤트를 기록하여 사용자 여정 내내 사용자의 특성을 측정합니다.

## <Image alt="InApp_Events_games.png" src="https://files.readme.io/ee2d46ddf11a6a6cacc95399ffd778d6613ecdd905d237cd971073e095cada5b-20659444711953.png" width="100px" /> Gaming

게임 앱은 아케이드, 전략, 교육용 게임 및 갬블링을 포함합니다. 기록을 제안하는 대표적인 이벤트는 인앱 구매, 소셜 미디어 공유 및 친구 초대입니다. 또한 레벨 업 및 게임 내 튜토리얼 완료 등의 이벤트를 포함할 수 있습니다.

이벤트 기록으로 다음을 확인할 수 있습니다.

* 사용자가 가장 많이 구매하는 제안
* 사용자 참여 방식
* 소셜 미디어에서 공유를 게시하는 사용자 수
* 친구에게 앱을 설치하도록 초대하는 사용자 수

이런 이벤트는 다음 플랫폼에서 실행되는 게임 앱에도 해당됩니다.

* 안드로이드 스마트 TV
* 애플 TV (tvOS)
* 아마존 파이어 TV
* 엑스박스
* Windows 모바일 기기

<div id="important" />

> 🚧 **중요!**
>
> * 인앱 이벤트 구현과 관련한 마케터용 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#인앱-이벤트-설정">지침</Anchor>을 반드시 읽어보십시오.
> * 구현 프로세스를 간소화하려면 당사의 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming">인앱 이벤트 생성기</Anchor>를 사용하십시오. 이 도구에는 본 문서에서 설명한 일반적인 인앱 이벤트가 모두 포함되어 있으며 사용자는 비즈니스 요구사항에 따라 이벤트를 수정할 수 있습니다. 완료되면 파일을 개발사와 공유하십시오.
> * 본 문서에 포함된 각 권장 이벤트에 대해 iOS, 안드로이드 및 Unity 개발자를 위한 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming&view=code">코드 샘플</Anchor>이 있습니다.
> * 개발사에 대한 자세한 지침은 **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">앱스플라이어 개발자 허브</Anchor>** 에서 확인할 수 있습니다.
>
> 인앱 이벤트 기록에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트 가이드를</Anchor> 참조하십시오.

<Image align="center" alt="Flowchart_for_recommended_events gaming_app_user_journey" src="https://files.readme.io/18546b2ca811e534d7b15527d3dadb4750edd8e985154543fa156216ad023f78-360020169778.png" />

<div id="recommended-structures-for-predefined-events" />

## 사전 정의된 이벤트에 권장되는 구조

다음 섹선에서는 게이밍 수직 구조에 일반적인 이벤트 구조 목록을 제공합니다. 각 구조에는 사용할 미리 정의된 이벤트 이름과 제안된 이벤트 파라미터가 포함됩니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

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

<div id="purchase-af_purchase" />

<Accordion title="구매 (af_purchase)">

**목적**

많은 게임 앱에서는 사용자가 예를 들어 코인, 보석, 무기와 같은 아이템을 구매할 수 있습니다. 이런 구매 기록을 통해 다음과 같은 도움이 될 수 있습니다.

* 광고 네트워크와 광고 에이전시 전반에 대한 사용자의 LTV 및 캠페인의 ROI를 알 수 있습니다.
* 사용자에게 가장 인기있는 아이템이 무엇인지 알 수 있습니다.
* 캠페인 타게팅을 최적화하기 위해서, 구매한 아이템 내역을 기반으로 크로스 캠페인을 진행할 수 있습니다.

**트리거**

사용자가 성공적인 구매 후 확인 페이지를 방문한 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> | 구매 추정 수익 | 199.99 |
| af\_통화 | 통화 코드 | THB, USD |
| af\_수량 | 구매한 아이템 개수 | 2 |
| af\_content\_id | 아이템 ID | 001, 092 |
| af\_주문\_id | 주문 ID | 9277 |
| af\_영수증\_ID | 영수증 ID | 9277 |

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="수준 달성 (af_level_achieved)">

**목적**

게임에서 사용자의 주요 목표 중 하나는 레벨을 올리는 것입니다. 레벨을 올리면 새로운 기능과 단계가 잠금 해제되고, 이에 따라 사용자는 계속해서 플레이하고 싶어집니다. 달성한 레벨을 기록하면 다음과 같은 도움이 될 수 있습니다.

* 활동적인 사용자를 가장 많이 생성하는 캠페인이 무엇인지 알 수 있습니다.
* 어떤 유형의 사용자가 가장 활발하게 참여하는지 알 수 있습니다.
* 수익 등의 지표와 전반적인 사용자 활동을 연결할 수 있습니다.

**트리거**

사용자가 레벨 완료 페이지를 방문했을 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_수준 | 유저가 달성한 수준 | 3 |
| af\_score | 사용자 달성과 연관된 점수 | 500 |

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="튜토리얼 완료 (af_tutorial_completion)">

**목적**

튜토리얼은 사용자에게 앱 사용 방법에 대한 지침을 제공합니다. 이 이벤트 기록에 의해 다음을 확인할 수 있습니다.

* 사용자가 어려움을 겪을 수 있는 주제
* 제대로 수행되지 않은 튜토리얼

**트리거**

* 사용자가 튜토리얼을 완료했을 경우.
* 사용자가 튜토리얼을 시작했지만 완료하지 않고 중단했을 경우.

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_success | 사용자의 튜토리얼 완료 여부 | true |
| af\_튜토리얼\_아이디 | 튜토리얼 ID | 3 |
| af\_content | 튜토리얼 이름 | 시작하기 |

</Accordion>

<div id="share-af_share" />

<Accordion title="공유 (af_share)">

**목적**

사용자는 게임에서 얻은 성과를 소셜 미디어에서 공유하고 싶어합니다. 공유는 브랜드 인지도를 높이고 더 많은 사용자가 앱을 다운로드하고 설치하도록 유도할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/user-invite-attribution">공유 기록 및 초대</Anchor>에 대해 자세히 알아보십시오.

**트리거**

사용자가 소셜 미디어에서 공유를 성공적으로 게시하는 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_설명 | 소셜 미디어에서 예를 들어 최고 기록 또는 레벨 업을 공유하는 이유 | 최고 기록 갱신, 레벨 업, 게임 승리 |
| 플랫폼 | 공유를 게시하는 데 사용하는 플랫폼 | 페이스북, 왓츠앱, 이메일 |

</Accordion>

<div id="invite-af_invite" />

<Accordion title="초대 (af_invite)">

**목적**

사용자가 초대장을 보낼 소셜 미디어 사이트와 앱을 다운로드하고 설치하도록 친구를 초대하는 사용자가 몇 명인지 알아봅니다.

**트리거**

사용자가 앱을 다운로드하고 설치하도록 친구를 성공적으로 초대한 경우

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_설명 | 초대 상황 | 이 앱 사용 |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## 사용자 지정 이벤트에 대한 권장 구조

다음 섹션에서는 사용자정의 이벤트 이름과 사용할 제안된 이벤트 파라미터가 포함된 이벤트 구조를 제공합니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="bonus-claimed-bonus_claimed" />

<Accordion title="보너스 청구(bonus_claimed)">

**목적**

자신에게 제공되는 보너스를 청구한 사용자가 얼마나 되는지 확인하고, 청구된 보너스를 사용자 활동 및 참여와 연관시킵니다.

**트리거**

사용자가 보너스를 청구하고 계좌에 업데이트한 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| bonus\_type | 사용자가 청구한 보너스 유형 | 코인 |

</Accordion>

<div data-zendesk-anchors="gaming=-gaming h_01HGTAVT1XSEY0TS9T2R1H1KXV=-gaming h_01HGTAVT1XTXYHV1MTFR20BR6J=%EC%A4%91%EC%9A%94 recommended-structures-for-predefined-events=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAVT1X4QQS6GREKC0N0VK6=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAVT1XAAPGHBTXE6DT9927=login-af_login h_01HGTAVT1X4V41YCXBEXTV0KFR=complete-registration-af_complete_registration h_01HGTAVT1X64710WYNZHTHD7R5=purchase-af_purchase h_01HGTAVT1X24N9J3BMDHV3S54M=level-achieved-af_level_achieved h_01HGTAVT1X5RN4A1MAE0BFB3B4=tutorial-completion-af_tutorial_completion h_01HGTAVT1X952BV07KGZHK68P6=share-af_share h_01HGTAVT1X7KSTYXZGAKEPCXZM=invite-af_invite recommended-structures-for-custom-events=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAVT1YXGTF0E5YQX1C3CJN=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAVT1YNH0YAFYX4PR7D6DH=bonus-claimed-bonus_claimed" />
