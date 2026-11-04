---
title: 추천 P2P 대출 앱 이벤트
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
  created_at: '2021-04-28T09:01:59Z'
  edited_at: '2026-10-14T10:38:46Z'
  id: 360019614017
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/360019614017
---
> **한눈에 보기:** 요약: 피어 투 피어(P2P) 대출 앱에 대해 제안된 인앱 이벤트를 기록하여 사용자 여정 내내 사용자의 특성을 측정합니다.

## <Image alt="InApp_Events_lending.png" src="https://files.readme.io/e3465ee913a65a215f1c224db20d4f1fd61fd0bf488b798073c94b4e8387d252-20659507679889.png" width="100px" /> P2P lending

P2P 대출은 개인과 기업이 서로 돈을 빌려주고 돌려받을 수 있는 방법입니다. 기록할 것을 제안하는 대표적인 이벤트는 개인 대출자와 차용인의 활동, 사람들이 제공하는 대출의 종류, 대출 수락률과 거부율입니다.

이벤트 기록을 통해 수집한 데이터를 통해 신뢰할 수 있는 차용인을 강조 표시하고 더 좋은 이자율을 제시할 수 있습니다. 마찬가지로, 가장 활발하게 활동하는 대출 제공자를 파악하고 더 낮은 수수료를 제시할 수 있습니다. 또한 어떤 유형의 대출이 사용자에게 가장 인기가 있는지 알게 되고, 이러한 잠재 고객을 대상으로 하는 마케팅 캠페인을 시작할 수 있습니다.

<div id="important" />

> 🚧 **중요!**
>
> * 인앱 이벤트 구현과 관련한 마케터용 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#인앱-이벤트-설정">지침</Anchor>을 반드시 읽어보십시오.
> * 구현 프로세스를 간소화하려면 당사의 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=p2p_lending">인앱 이벤트 생성기</Anchor>를 사용하십시오. 이 도구에는 본 문서에서 설명한 일반적인 인앱 이벤트가 모두 포함되어 있으며 사용자는 비즈니스 요구사항에 따라 이벤트를 수정할 수 있습니다. 완료되면 파일을 개발사와 공유하십시오.
> * 본 문서에 포함된 각 권장 이벤트에 대해 iOS, 안드로이드 및 Unity 개발자를 위한 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=p2p_lending&view=code">코드 샘플</Anchor>이 있습니다.
> * 개발사에 대한 자세한 지침은 **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">앱스플라이어 개발자 허브</Anchor>** 에서 확인할 수 있습니다.
>
> 인앱 이벤트 기록에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트 가이드를</Anchor> 참조하십시오.

[![Flowchart_for_recommended_events P2P_lending_app_user_journey](https://files.readme.io/597a98cf1df450e9e14eb32d8bdc14df647551ca91a2baca78895ca740eb805c-360020063617.png)](https://files.readme.io/597a98cf1df450e9e14eb32d8bdc14df647551ca91a2baca78895ca740eb805c-360020063617.png)

<div id="recommended-structures-for-predefined-events" />

## 사전 정의된 이벤트에 권장되는 구조

다음 섹선에서는 P2P 대출 수직 구조에 일반적인 이벤트 구조 목록을 제공합니다. 각 구조에는 사용할 미리 정의된 이벤트 이름과 제안된 이벤트 파라미터가 포함됩니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="complete-registration-af_complete_registration" />

<Accordion title="가입 완료(af_complete_registration)">

**목적**

등록 이후 신원을 실제 확인하는 사용자 수를 알 수 있습니다. 이러한 사용자를 캠페인별로 어트리뷰트 하고, 어떤 캠페인이 활성 사용자를 생성하는지 알 수 있습니다.

**트리거**

사용자 등록이 승인되는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
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

<div id="recommended-structures-for-custom-events" />

## 사용자 지정 이벤트에 대한 권장 구조

다음 섹션에서는 사용자 지정 이벤트 이름과 사용하도록 제안된 이벤트 파라미터를 포함한 이벤트 구조 목록을 제공합니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="registration-submitted-registration_submitted" />

<Accordion title="등록 제출(registration_submitted)">

**목적**

P2P 대출은 오남용의 우려가 있으므로 먼저 사용자 확인이 필요합니다. 이 확인은 등록 요청 제출을 통해 할 수 있습니다. 이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 등록은 하지만 계정 확인을 하지 않는 사용자의 수를 확인합니다.
* 이메일, 페이스북, 구글과 같은 등록 방법과 사용자 확인 비율 간의 상관 관계를 알 수 있습니다.

**트리거**

사용자가 등록 요청을 제출한 이후

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_registration\_method | 가입 방법의 유형 | 이메일, 페이스북 |

</Accordion>

<div id="fill-loan-form-fill_loan_form_form_name" />

<Accordion title="대출 양식 작성(fill_loan_form_&lt;FORM_NAME>)">

**목적**

대출 포기율을 확인하고 대출 신청서를 작성하지 않은 신청인을 리타게팅합니다.

이벤트를 전송할 때, 이벤트 이름에 양식 이름을 포함해야 합니다.

**트리거**

대출 신청인이 양식을 제출하는 시기

**이벤트 파라미터**

추가 파라미터 없이 전송 가능

<div id="note" />

> 📘 **참고사항**
>
> 대출 제공자와 대출을 서로 연결하는 것을 권장합니다. 이를 위해서는 고객 사용자 ID를 설정해야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">고객 사용자 ID 설정</Anchor>은 대출 제공자와 앱스플라이어에 표시되는 앱 사용자를 매칭시키는 방법입니다. 고객 사용자 ID 설정을 하면 모든 이벤트가 이 고객 사용자 ID와 함께 전송됩니다.

<div id="submit-loan-application-submit_loan_application" />

<Accordion title="대출 신청서 제출(submit_loan_application)">

**목적**

이 이벤트는 다음을 제공합니다.

* 앱에서 전체 대출 신청 건수 확인
* 대출 신청 시의 최대, 최소, 평균 금액을 알 수 있습니다.
* 사람들이 신청하는 대출 유형 확인

**트리거**

사용자가 대출 신청서를 제출하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| loan\_id | 대출 ID | 1735102 |
| loan\_amount | 요청 금액 | 1000 |
| loan\_type | 대출 기간 | 3 months |

</Accordion>

<div id="loan-form-loan_form" />

<Accordion title="대출 양식(loan_form)">

**목적**

대출자가 제출한 대출 신청서 검토

**트리거**

대출자가 대출 신청서를 성공적으로 제출한 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| loan\_id | 대출 ID | 1735102 |
| loan\_amount | 요청 금액 | 1000 |
| loan\_type | 대출 기간 | 3 months |

</Accordion>

<div id="submit-credit-check-submit_credit_check" />

<Accordion title="신용 조회 제출(submit_credit_check)">

**목적**

대출자의 재무 내역(예: 과거 신용, 지불 습관 및 대출 유형)을 확인하여 위험 수준을 평가합니다.

**트리거**

대출자가 대출 요청을 접수한 후

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| loan\_id | 대출 ID | 1735102 |
| loan\_amount | 요청 금액 | 1000 |
| loan\_type | 대출 기간 | 3 months |

</Accordion>

<div id="loan-accepted-loan_accepted" />

<Accordion title="대출 접수함(loan_accepted)">

**목적**

대출 및 기타 지표의 추세에 동향에 대해 알 수 있습니다. 이 이벤트에 의해 다음을 확인할 수 있습니다.

* 승인된 대출의 종류
* 승인된 대출에서 요청한 금액
* 대출을 가장 많이 받는 대출 기관

**트리거**

대출 승인 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| loan\_id | 대출 ID | 1735102 |
| loan\_amount | 요청 금액 | 1000 |
| loan\_type | 대출 기간 | 3 months |

</Accordion>

<div id="loan-rejected-loan_rejected" />

<Accordion title="거부된 대출(loan_rejected)">

**목적**

대출이 거부된 이유를 알게 됩니다. 대출 금액, 대출 기간, 거절률 사이의 상관 관계를 알 수 있습니다. 대출 승인이 거절된 사용자를 리타케팅하여 더 적은 금액 대출을 제안할 수 있습니다.

**트리거**

대출자가 대출을 거부하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| loan\_id | 대출 ID | 1735102 |

</Accordion>

<div id="payment-payment" />

<Accordion title="결제(payment)">

**목적**

대출자를 신뢰할 수 있는 사람으로 표시하도록 도와줍니다. 신용도가 높은 차용인은 대출 상환 의무를 잘 이행하는 사람입니다. 차용인을 유입 캠페인에 어트리뷰트하고, 어떤 캠페인이 신용도 높은 차용인을 생성하는지 알 수 있습니다. 또한 이 이벤트를 통해 최소, 최대, 평균 지불 금액에 대한 데이터를 모을 수 있습니다.

**트리거**

대출자가 대출금을 상환하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| loan\_id | 대출 ID | 1735102 |
| payment\_amount | 결제 금액 | 100 |
| payment\_id | 상환 ID | AE12SF |

</Accordion>

<div id="payment-completed-payment_completed" />

<Accordion title="상환 완료(payment_completed)">

**목적**

대출을 상환해야 할 의무를 따르는 대출자를 강조합니다. 이러한 차용인에게 더 낮은 이자 수수료나 다른 프로모션을 제시하는 등의 리타게팅을 할 수 있습니다.

**트리거**

대출이 전액 상환되는 시기

**이벤트 파라미터**

| 필드 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| loan\_id | 대출 ID | 1735102 |

</Accordion>

<div id="payment-received-payment_received" />

<Accordion title="지불 받기(payment_received)">

**목적**

대출자가 대출 약관에 따라 대출금 상환을 완료하는지 확인합니다.

**트리거**

대출자가 대출금을 상환하는 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| loan\_id | 대출 ID | 1735102 |
| payment\_amount | 결제 금액 | 100 |
| payment\_id | 상환 ID | AE12SF |

</Accordion>

</Accordion>

<div data-zendesk-anchors="p2p-lending=-p2p-lending h_01HGTAY6DHKXCTP52P2EPHXN5H=-p2p-lending h_01HGTAY6DHDDG3MVCXEM705MTK=%EC%A4%91%EC%9A%94 recommended-structures-for-predefined-events=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAY6DH1V6S5NKJEFCVW1PF=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAY6DHHGW3M6NQ0K3J6HTC=complete-registration-af_complete_registration h_01HGTAY6DHZTKJR94T8B6WEYZ6=login-af_login recommended-structures-for-custom-events=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAY6DH00660DSP5RX3PA9C=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAY6DHETK285KPGW54YV5Z=registration-submitted-registration_submitted h_01HGTAY6DHCQKWMG4YRZDHBMZT=fill-loan-form-fill_loan_form_form_name h_01HGTAY6DHHNJ9EKV3FQ6BKKBF=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01HGTAY6DH4D6NV1NHV5717CDH=submit-loan-application-submit_loan_application h_01HGTAY6DHVWFEFJYB4TGK1B9W=loan-form-loan_form h_01HGTAY6DH7V1JSPCDHDTFR4YA=submit-credit-check-submit_credit_check h_01HGTAY6DH22HRQQJ5NQ2T71QM=loan-accepted-loan_accepted h_01HGTAY6DHTMJ22KQSXHNBJ8B3=loan-rejected-loan_rejected h_01HGTAY6DHD8A2H61XKFPXW589=payment-payment h_01HGTAY6DJWJDQBW52RPG7W7P4=payment-completed-payment_completed h_01HGTAY6DJE0K3VC0YNVWAXT29=payment-received-payment_received" />
