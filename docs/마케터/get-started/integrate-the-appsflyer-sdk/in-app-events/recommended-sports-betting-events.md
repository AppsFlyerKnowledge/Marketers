---
title: 추천 스포츠 베팅 이벤트
metadata:
  keywords:
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
  created_at: '2021-11-11T13:24:45Z'
  edited_at: '2026-10-14T10:34:05Z'
  id: 4410672219025
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/4410672219025
---
> **한눈에 보기:** 전자지갑 앱에 대해 제안된 인앱 이벤트를 기록하여 사용자 여정 내내 사용자의 특성을 측정합니다.

## <Image alt="soccer_ball.png" src="https://files.readme.io/2c5150b2c50ec166878cd976154dc81c0dc8a1e710fa8869aa582b535313b464-4413968925585.png" width="71px" /> Sports betting

이벤트 기록으로 다음을 확인할 수 있습니다.

* 사용자 참여 방식

> 🚧 **중요!**
>
> * 인앱 이벤트 구현과 관련한 마케터용 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#인앱-이벤트-설정">지침</Anchor>을 반드시 읽어보십시오.
> * 구현 프로세스를 간소화하려면 당사의 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming">인앱 이벤트 생성기</Anchor>를 사용하십시오. 이 도구에는 본 문서에서 설명한 일반적인 인앱 이벤트가 모두 포함되어 있으며 사용자는 비즈니스 요구사항에 따라 이벤트를 수정할 수 있습니다. 완료되면 파일을 개발사와 공유하십시오.
> * 본 문서에 포함된 각 권장 이벤트에 대해 iOS, 안드로이드 및 Unity 개발자를 위한 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming&view=code">코드 샘플</Anchor>이 있습니다.
> * 개발사에 대한 자세한 지침은 **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">앱스플라이어 개발자 허브</Anchor>** 에서 확인할 수 있습니다.
>
> 인앱 이벤트 기록에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트 가이드를</Anchor> 참조하십시오.

[![In_appEvents_UserJourneys_-_Sports_betting__5_.png](https://files.readme.io/7a47ba917ebc5a6e661efb23b078675c16ce43c59c41f9c6fd6fd89d37c242bf-4424606611473.png)](https://files.readme.io/7a47ba917ebc5a6e661efb23b078675c16ce43c59c41f9c6fd6fd89d37c242bf-4424606611473.png)

## 사전 정의된 이벤트에 권장되는 구조

다음 섹선에서는 승차공유 수직 구조에 일반적인 이벤트 구조 목록을 제공합니다. 각 구조에는 사용할 미리 정의된 이벤트 이름과 제안된 이벤트 파라미터가 포함됩니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

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

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_registration\_method | 가입 방법의 유형 | 이메일, 페이스북 |

</Accordion>

## 사용자 지정 이벤트에 대한 권장 구조

다음 섹션에서는 사용자정의 이벤트 이름과 사용할 제안된 이벤트 파라미터가 포함된 이벤트 구조를 제공합니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

**목적**

이 이벤트 기록에 의해 다음을 확인할 수 있습니다.

**트리거**

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> |  | 200 |
| af\_통화 |  | AUD |


**목적**

**트리거**

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> |  | 200 |
| af\_통화 |  | AUD |


**목적**

**트리거**

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 |  | 100 |
| af\_통화 |  | AUD |
| event\_number |  | 123789 |
| 이벤트 날짜 |  | 13122021 |
| event\_time |  | 17:30 |
| 거래\_ID |  | 221 |


**목적**

**트리거**

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> |  | -100 |
| af\_통화 |  | AUD |


**목적**

**트리거**

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 |  | 100 |
| af\_통화 |  | AUD |
| event\_number |  | 123789 |
| 이벤트 날짜 |  | 13122021 |
| event\_time |  | 17:30 |
| bonus\_id |  | 221 |


**목적**

이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

**트리거**

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 |  | 100 |
| af\_통화 |  | AUD |
| event\_number |  | 123789 |
| 이벤트 날짜 |  | 13122021 |
| event\_time |  | 17:30 |


**목적**

**트리거**

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 |  | 100 |
| af\_통화 |  | AUD |
| account\_number |  | 15780 |
| event\_number |  | 123789 |
| 이벤트 날짜 |  | 13122021 |
| event\_time |  | 17:30 |


**목적**

**트리거**

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_가격 |  | 100 |
| af\_통화 |  | AUD |
| account\_number |  | 15780 |
| event\_number |  | 123789 |
| 이벤트 날짜 |  | 13122021 |
| event\_time |  | 17:30 |

<div data-zendesk-anchors="sports-betting=-sports-betting h_01HGTAE0AT9KD9RKX7XPR7A4AT=-sports-betting h_01HGTAE0ATTMEART2R1BD1ZDSB=%EC%A4%91%EC%9A%94 recommended-structures-for-predefined-events=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAE0ATYW0RDDZZD5EAR7BZ=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAE0ATMBJVKS14SGWGK0DG=login-af_login h_01HGTAE0ATHZWSM0R9A6R9BV96=complete-registration-af_complete_registration recommended-structures-for-custom-events=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAE0ATJQDWWBB8D836QRJ5=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0" />
