---
title: 추천 온라인 교육 앱 이벤트
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
  created_at: '2021-04-28T12:35:57Z'
  edited_at: '2026-10-14T10:29:11Z'
  id: 360019794378
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/360019794378
---
> **한눈에 보기:** 요약: 온라인 교육 앱에 대해 제안된 인앱 이벤트를 기록하여 사용자 여정 내내 사용자의 특성을 측정합니다.

## <Image alt="education.png" src="https://files.readme.io/fb036c8f3b0cb4cc06a5284c26089bbb361273ab628bc5b740692bc49e7a2c40-20659493109393.png" width="100px" /> Online education

온라인 교육 앱을 통해 사용자는 원격으로 학습할 수 있습니다. 기록을 권장하는 대표적인 이벤트로는 등록, 튜토리얼 및 완료된 과정, 받은 인증서가 있습니다.

이벤트 기록으로 다음을 확인할 수 있습니다.

* 사용자가 가장 원하며 타게팅 아이디어를 제공하는 과정
* 과정을 완료하기 위한 추가 튜토리얼이 있음을 알리고 리타게팅할 수 있는 사용자
* 수요가 많은 과정 및 인증서

> 🚧 **중요!**
>
> * 인앱 이벤트 구현과 관련한 마케터용 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#인앱-이벤트-설정">지침</Anchor>을 반드시 읽어보십시오.
> * 구현 프로세스를 간소화하려면 당사의 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=online_education">인앱 이벤트 생성기</Anchor>를 사용하십시오. 이 도구에는 본 문서에서 설명한 일반적인 인앱 이벤트가 모두 포함되어 있으며 사용자는 비즈니스 요구사항에 따라 이벤트를 수정할 수 있습니다. 완료되면 파일을 개발사와 공유하십시오.
> * 본 문서에 포함된 각 권장 이벤트에 대해 iOS, 안드로이드 및 Unity 개발자를 위한 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=online_education&view=code">코드 샘플</Anchor>이 있습니다.
> * 개발사에 대한 자세한 지침은 **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">앱스플라이어 개발자 허브</Anchor>** 에서 확인할 수 있습니다.
>
> 인앱 이벤트 기록에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트 가이드를</Anchor> 참조하십시오.

[![Flowchart_for_recommended_events_online_education_app_user_journey](https://files.readme.io/a913f14a20a52d7d70a96be7601fd264650f790337ceb83b9c53fd0006afc8e1-360020170478.png)](https://files.readme.io/a913f14a20a52d7d70a96be7601fd264650f790337ceb83b9c53fd0006afc8e1-360020170478.png)

## 사전 정의된 이벤트에 권장되는 구조

다음 섹션에서는 온라인 교육 수직 구조에 일반적인 이벤트 구조 목록을 제공합니다. 각 구조에는 사용할 미리 정의된 이벤트 이름과 제안된 이벤트 파라미터가 포함됩니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

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

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="튜토리얼 완료 (af_tutorial_completion)">

**목적**

이 이벤트 기록에 의해 다음을 확인할 수 있습니다.

* 사용자가 어려움을 겪을 수 있는 주제
* 제대로 실행되지 않는 튜토리얼과 튜토리얼의 그것의 개선
* 수익 등의 지표와 전반적인 사용자 활동을 연결할 수 있습니다.

**트리거**

* 사용자가 튜토리얼을 완료했을 경우.
* 사용자가 튜토리얼을 시작했지만 완료하지 않고 중단했을 경우.

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_success | 사용자의 튜토리얼 완료 여부 | 네 |
| af\_튜토리얼\_아이디 | 튜토리얼 ID | 3 |
| af\_content | 튜토리얼 이름 | algebra |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="구매 (af_purchase)">

**목적**

사용자의 인앱 구매 내용을 기록하면 다음과 같은 이점이 있습니다.

* 광고 네트워크와 광고 에이전시 전반에 대한 사용자의 LTV 및 캠페인의 ROI를 알 수 있습니다.
* 사용자에게 가장 인기있는 아이템이 무엇인지 알 수 있습니다.
* 캠페인 타게팅을 최적화하기 위해서, 구매한 아이템 내역을 기반으로 크로스 캠페인을 진행할 수 있습니다.

**트리거**

사용자가 성공적인 구매 후 확인 페이지를 방문한 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> | 구매 추정 수익 | 250.99 |
| af\_통화 | 통화 코드 | USD |
| af\_content\_id | 항목의 ID | 001, 092 |
| 주문\_ID | 주문 ID | 9277 |
| af\_영수증\_ID | 영수증 ID | 9277 |

</Accordion>

## 사용자 지정 이벤트에 대한 권장 구조

다음 섹션에서는 사용자 지정 이벤트 이름과 사용하도록 제안된 이벤트 파라미터를 포함한 이벤트 구조 목록을 제공합니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="complete-exercise-complete_excercise" />

<Accordion title="연습 완료(complete_excercise)">

**목적**

이런 이벤트를 기록하고, 다른 이벤트와 비교하여 사용자에 대해 더 자세히 이해할 수 있습니다. 예를 들어, 연습을 시작했지만 완료하지 못한 사용자 수를 알 수 있습니다.

**트리거**

사용자가 연습을 완료한 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| course\_name | 과정의 이름 | algebra |
| exercise\_name | 연습의 이름 | 2 |

</Accordion>

<div id="course-completed-course_completed" />

<Accordion title="과정 완료됨(course_completed)">

**목적**

이런 이벤트를 기록하고, 다른 이벤트와 비교하여 사용자에 대해 더 자세히 이해할 수 있습니다. 예를 들어, 과정을 시작했지만 완료하지 못한 사용자 수를 알 수 있습니다.

**트리거**

사용자가 과정을 완료한 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| course\_name | 과정의 이름 | algebra |
| course\_completed | 과정 완료 여부 | 네 |

</Accordion>

<div id="certificate-issued-certificate_issued" />

<Accordion title="인증서 발행(certificate_issued)">

**목적**

이런 이벤트를 기록하고, 다른 이벤트와 비교하여 사용자에 대해 더 자세히 이해할 수 있습니다. 예를 들어, 과정을 완료한 사용자 수를 알고 다음 과정에 그들을 리타게팅할 수 있습니다.

**트리거**

사용자가 인증서를 발행한 경우

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| course\_name | 과정의 이름 | algebra |
| certificate\_received | 인증서 발행 여부 | 네 |

</Accordion>

<div data-zendesk-anchors="online-education=-online-education h_01HGTAYQ9V4Z5YEWTNCZPVMVMF=-online-education h_01HGTAYQ9VJ6GS1XVQPG198C8Z=%EC%A4%91%EC%9A%94 recommended-structures-for-predefined-events=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAYQ9VS0DYFSFNEPDCDVTG=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAYQ9VX44FA5HHBT6DGA2R=login-af_login h_01HGTAYQ9VR78MHTJZFVFCKCV4=complete-registration-af_complete_registration h_01HGTAYQ9VE8ZBF1DJ2AAA1HFF=tutorial-completion-af_tutorial_completion h_01HGTAYQ9VSXMR0J1T0KN6WK2G=purchase-af_purchase recommended-structures-for-custom-events=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAYQ9V93HET4AZ7XGE0E3V=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAYQ9VBZZJ5TC1W2S0MK3P=complete-exercise-complete_excercise h_01HGTAYQ9WQJBBEYKDJ8DP9E31=course-completed-course_completed h_01HGTAYQ9WVXX20FNDZWHGDNZ2=certificate-issued-certificate_issued" />
