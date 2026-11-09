---
title: 추천 금융 및 뱅킹 앱 이벤트
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
  created_at: '2021-04-27T12:58:44Z'
  edited_at: '2026-10-14T10:36:28Z'
  id: 360019598337
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/360019598337
---
> **한눈에 보기:** 요약: 재무 및 뱅킹 앱에 대해 제안된 인앱 이벤트를 기록하여 사용자 여정 내내 사용자의 특성을 측정합니다.


<span id="-finance-and-banking"></span><span id="finance-and-banking"></span>금융 및 은행 앱은 사용자에게 새로운 신용카드 가입이나 대출 신청과 같은 광범위한 재무 관련 목표를 수행할 수 있는 기능을 제공합니다. 기록을 제안하는 대표적인 이벤트로는 계좌 개설, 신용카드 신청, 대출 신청 등이 있습니다.

이런 이벤트 기록에 의해 다음을 확인할 수 있습니다.

* 사용자가 가장 원하며 리타게팅 아이디어를 제공하는 계정 유형
* 사용자가 신용카드로 찾아보는 이점
* 사용자가 재무 지원이 필요한 항목 및 원하는 지원 수준

<div id="important" />

> 🚧 **중요!**
>
> * 변호사의 조언: 건강 데이터는 "제한된 데이터"로 간주되며 많은 관할 구역에서 데이터의 특별한 범주로 간주됩니다. 따라서 고객은 이러한 데이터를 앱스플라이어에 보낼 수 없습니다.
> * 인앱 이벤트 구현과 관련한 마케터용 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#인앱-이벤트-설정">지침</Anchor>을 반드시 읽어보십시오.
> * 구현 프로세스를 간소화하려면 당사의 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=finance_banking">인앱 이벤트 생성기</Anchor>를 사용하십시오. 이 도구에는 본 문서에서 설명한 일반적인 인앱 이벤트가 모두 포함되어 있으며 사용자는 비즈니스 요구사항에 따라 이벤트를 수정할 수 있습니다. 완료되면 파일을 개발사와 공유하십시오.
> * 본 문서에 포함된 각 권장 이벤트에 대해 iOS, 안드로이드 및 Unity 개발자를 위한 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=finance_banking&view=code">코드 샘플</Anchor>이 있습니다.
> * 개발사에 대한 자세한 지침은 **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">앱스플라이어 개발자 허브</Anchor>** 에서 확인할 수 있습니다.
>
> 인앱 이벤트 기록에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트 가이드를</Anchor> 참조하십시오.

<Image align="center" alt="Flowchart_for_recommended_events finance_banking_app_user_journey" src="https://files.readme.io/722d2a3df606df1c61f86c7e8e1524566de8fbfd0ceb48e4cd5913a0b3ac9283-360020063337.png" />

<div id="recommended-structures-for-predefined-events" />

## 사전 정의된 이벤트에 권장되는 구조

다음 섹선에서는 재무 및 뱅킹 수직 구조에 일반적인 이벤트 구조 목록을 제공합니다. 각 구조에는 사용할 미리 정의된 이벤트 이름과 제안된 이벤트 파라미터가 포함됩니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="login-af_login" />

<Accordion title="로그인 (af_login)">

**목적**

등록된 사용자의 잔존율 파악

**트리거**

사용자가 성공적으로 로그인한 시간

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

<div id="recommended-structures-for-custom-events" />

## 사용자 지정 이벤트에 대한 권장 구조

다음 섹션에서는 사용자 지정 이벤트 이름과 사용하도록 제안된 이벤트 파라미터를 포함한 이벤트 구조 목록을 제공합니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="registration-verified-registration_verified" />

<Accordion title="등록 확인됨(registration_verified)">

**목적**

이런 이벤트를 기록하고, 다른 이벤트와 비교하여 사용자에 대해 더 자세히 이해할 수 있습니다. 예를 들어, 등록했지만 승인되지 않은 사용자 수를 알 수 있습니다.

**트리거**

등록이 확인되는 시점

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| submit\_registration | 확인된 가입 방법 유형. 개인 식별 가능 정보(PII)를 입력하지 마십시오. | 이메일, 페이스북 |

</Accordion>

<div id="submit-account-application-submit_account_application" />

<Accordion title="계좌 신청서 제출(submit_account_application)">

**목적**

이런 이벤트를 기록하고, 다른 이벤트와 비교하여 사용자에 대해 더 자세히 이해할 수 있습니다. 예를 들어, 가입했지만 계좌 개설을 신청하지 않은 사용자 수를 알 수 있습니다.

**트리거**

사용자가 계좌 신청 프로세스를 완료한 시간

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| account\_type | 신청한 계좌 유형 | 보통 예금 |
| application\_method | 신청 장소 | 앱 |
| PII\_type | 신청 시에 사용한 ID 유형 | 여권 |

</Accordion>

<div id="open-account-success-open_account_success" />

<Accordion title="계좌 개설 성공(open_account_success)">

**목적**

이런 이벤트를 기록하고, 다른 이벤트와 비교하여 사용자에 대해 더 자세히 이해할 수 있습니다. 예를 들어, 얼마나 많은 사용자가 계좌를 신청하고 승인되었는지 확인한 후 나중에 퍼널을 개선하거나 해당 사용자를 리타게팅할 수 있습니다.

**트리거**

사용자 신청이 승인되고 계좌가 개설된 경우

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| account\_type | 개설한 계좌의 유형 | 보통 예금 |
| application\_method | 신청 장소 | 앱 |
| PII\_type | 신청 시에 사용한 ID 유형 | 식별 카드 |

</Accordion>

<div id="open-account-rejected-open_account_rejected" />

<Accordion title="계좌 개설 거부(open_account_rejected)">

**목적**

이런 이벤트를 기록하고, 다른 이벤트와 비교하여 사용자에 대해 더 자세히 이해할 수 있습니다. 예를 들어, 얼마나 많은 사용자가 계좌를 신청했지만 승인되지 않았는지 확인한 후 나중에 퍼널을 개선하거나 해당 사용자를 리타게팅할 수 있습니다.

**트리거**

사용자가 등록 프로세스를 완료한 시간

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| account\_type | 신청한 계좌 유형 | 보통 예금 |

</Accordion>

<div data-zendesk-anchors="h_01HGTAXN8PV7TPNRBWD593BR4K=finance-and-banking h_01HGTAXN8Q652HG7412X583KWX=%EC%A4%91%EC%9A%94 recommended-structures-for-predefined-events=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAXN8QWEWD86FMF6GEZNZD=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAXN8Q3K0EFGXZ41XZH438=login-af_login h_01HGTAXN8Q6KFDPB8XSVT3F9E8=complete-registration-af_complete_registration recommended-structures-for-custom-events=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAXN8Q47F6CXXBEVCDPSBA=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAXN8QB911JMER3EV7RGTM=registration-verified-registration_verified h_01HGTAXN8QCYR0BQ3Q3VN0EQ9X=submit-account-application-submit_account_application h_01HGTAXN8QJ4DKQS2FY9KY0AX4=open-account-success-open_account_success h_01HGTAXN8QK1P5QYEN5SNBQ5ED=open-account-rejected-open_account_rejected" />
