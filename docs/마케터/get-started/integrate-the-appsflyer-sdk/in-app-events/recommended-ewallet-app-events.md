---
title: 권장되는 전자지갑 앱 이벤트
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
  created_at: '2021-06-10T11:36:07Z'
  edited_at: '2026-10-14T10:33:25Z'
  id: 4402425586065
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/4402425586065
---
> **한눈에 보기:** 전자지갑 앱에 대해 제안된 인앱 이벤트를 기록하여 사용자 여정 내내 사용자의 특성을 측정합니다.

## <Image alt="InApp_Events_eWallet.png" src="https://files.readme.io/4d2ed4994bbe8e8eca7009b8ec8f5dbf22a626421a7a1efb213ddb4a12c7b487-4402543191825.png" width="67px" /> 전자지갑

사용자는 전자지갑 앱을 사용하여 자신의 기기에서 디지털 결제 또는 구매를 할 수 있습니다. 기록할 것을 권장하는 일반적인 이벤트에는 자금 추가, 콘텐츠 보기, 판매자 선택, 프로모션 보기, 거래 완료 등이 있습니다.

이런 이벤트 기록에 의해 다음을 확인할 수 있습니다.

* 사용자의 인기를 끌고 유사하거나 연관된 제품을 제공할 수 있는 콘텐츠와 프로모션의 유형
* 사용자가 대금 결제 시 전자지갑을 사용하는 가장 인기 있는 서비스 유형
* 가장 인기 있는 판매자

> 🚧 **중요!**
>
> * 인앱 이벤트 구현과 관련한 마케터용 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#인앱-이벤트-설정">지침</Anchor>을 반드시 읽어보십시오.
> * 구현 프로세스를 간소화하려면 당사의 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ewallet">인앱 이벤트 생성기</Anchor>를 사용하십시오. 이 도구에는 본 문서에서 설명한 일반적인 인앱 이벤트가 모두 포함되어 있으며 사용자는 비즈니스 요구사항에 따라 이벤트를 수정할 수 있습니다. 완료되면 파일을 개발사와 공유하십시오.
> * 본 문서에 포함된 각 권장 이벤트에 대해 iOS, 안드로이드 및 Unity 개발자를 위한 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ewallet&view=code">코드 샘플</Anchor>이 있습니다.
> * 개발사에 대한 자세한 지침은 **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">앱스플라이어 개발자 허브</Anchor>** 에서 확인할 수 있습니다.
>
> 인앱 이벤트 기록에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트 가이드를</Anchor> 참조하십시오.

[![Flowchart_for_recommended_events e-Wallet_app_user_journey](https://files.readme.io/cf1f91f9c89d1f45448a6172e48b7f59fdce767f00c893d91b12a5f2d043945f-4404610923409.png)](https://files.readme.io/cf1f91f9c89d1f45448a6172e48b7f59fdce767f00c893d91b12a5f2d043945f-4404610923409.png)

## 사전 정의된 이벤트에 권장되는 구조

다음 섹선에서는 전자지갑 수직 구조에 일반적인 이벤트 구조 목록을 제공합니다. 각 구조에는 사용할 미리 정의된 이벤트 이름과 제안된 이벤트 파라미터가 포함됩니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="complete-registration-af_complete_registration" />

<Accordion title="가입 완료(af_complete_registration)">

**목적**

앱을 설치하고 등록 프로세스를 완료한 사용자 수와 사용자가 선호하는 등록 방법에 대해 알아봅니다.

**트리거**

사용자가 등록 프로세스를 완료한 시간

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_registration\_method | 가입 방법 유형 | 이메일, Facebook, Google |

</Accordion>

<div id="login-af_login" />

<Accordion title="로그인(af_login)">

**목적**

등록된 사용자의 잔존율 파악

**트리거**

사용자가 성공적으로 로그인한 시간

**이벤트 파라미터**

추가 파라미터 없이 전송 가능

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="콘텐츠 조회(af_content_view)">

**목적**

특정 콘텐츠의 조회율을 확인합니다. 이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 사용자에게 가장 인기 있는 콘텐츠 유형을 파악한 다음 마케팅 캠페인 최적화
* 품목 조회수와 판매자 간의 상관 관계 확인

**트리거**

사용자가 특정 품목 또는 카테고리 콘텐츠를 볼 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| 품목 | 품목 유형 | 영화관 티켓 |
| merchant\_name | 판매자 이름 | cineplex |

</Accordion>

## 사용자 지정 이벤트에 대한 권장 구조

다음 섹션에서는 사용자 지정 이벤트 이름과 사용하도록 제안된 이벤트 파라미터를 포함한 이벤트 구조 목록을 제공합니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="wallet-complete-topup-wallet_complete_topup" />

<Accordion title="지갑 충전 완료(wallet_complete_topup)">

**목적**

톱업 펀드는 앱 내에서 제공되는 패키지나 다른 서비스를 구매하는 데 사용할 수 있습니다. 이런 이벤트를 기록하고, 다른 이벤트와 비교하여 사용자에 대해 더 자세히 이해할 수 있습니다. 예를 들어, 사람들이 자신의 계정에 예치할 의향이 있는 금액을 확인하고 예산 내에서 맞춤형 캠페인을 통해 그들을 대상으로 톱업 금액을 사용할 수 있습니다.

**트리거**

사용자가 은행 또는 신용카드에서 전자지갑 앱으로 충전을 완료할 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| top\_up\_amount | 결제 금액 | 100 |
| top\_up\_method | 결제 수단 유형 | 은행 송금 |

</Accordion>

<div id="payment-transaction-completed-payment_transaction_completed" />

<Accordion title="결제 거래 완료( payment_transaction_completed )">

**목적**

이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 거래에서 결제를 완료한 사용자를 강조 표시합니다.
* 대규모 거래를 식별한 다음 큰 금액을 충전하는 사용자를 리타겟팅합니다.

**트리거**

특정 구매의 거래가 완료될 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| 품목 | 결제한 품목 | 선불 카드 재충전 |
| quantity | 결제 금액 | 1 |
| transaction\_amount | 거래 금액 | 50 |

</Accordion>

<div id="bill-payment-success-bill_payment_success" />

<Accordion title="대금 결제 성공(bill_payment_success)">

**목적**

이 이벤트를 통해 사용자가 가장 많이 대금을 결제하는 서비스 유형(예: 수도 요금, 전기 요금, 신용카드 사용 금액 지불)을 확인할 수 있습니다.

**트리거**

사용자가 청구서, 신용카드 명세서, 영화 티켓 등의 결제를 위해 전자지갑을 사용할 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| merchant\_name | 판매자 이름 | 전기 제공업체 |
| payment\_amount | 결제 금액 | 100 |
| category | 서비스 유형 | 전기 |

</Accordion>

<div id="promo-promo" />

<Accordion title="프로모션(promo)">

**목적**

이 이벤트에 의해 다음을 확인할 수 있습니다.

* 제공 중인 프로모션이 사용자에게 인기가 있는지 여부
* 프로모션이 사용자에게 추가 제품을 교차 판매하는 데 도움이 되는지 여부

**트리거**

사용자가 앱 내에서 사용 가능한 프로모션을 선택할 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| promo\_type | 제공 중인 프로모션의 유형 | 30% 할인 |

</Accordion>

<div id="voucher-redeem-voucher_redeem" />

<Accordion title="바우처 사용(voucher_redeem)">

**목적**

이 이벤트에 의해 다음을 확인할 수 있습니다.

* 프로모션 코드를 사용하는 사용자 수
* 사용자가 선호하는 바우처 및 할인의 유형

**트리거**

사용자 프로모션 코드를 사용할 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| voucher\_ID | 바우처의 ID | 1735103 |
| merchant\_name | 판매자 이름 | cineplex |

</Accordion>

<div id="select-merchant-select_merchant" />

<Accordion title="판매자 선택( select_merchant )">

**목적**

이 이벤트를 통해 가장 인기 있는 판매자를 확인한 다음 이 데이터를 사용하여 유사한 판매자가 전자지갑 서비스에 가입하도록 유도할 수 있습니다.

**트리거**

사용자가 이용 가능한 판매자 목록에서 판매자를 선택할 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| merchant\_name | 판매자 이름 | cineplex |
| type | 비즈니스 유형 | cinema |
| amount | 광고주가 사용하는 통화 | USD |
| merchant\_ID | 거래에 관련된 결제 처리 시스템에 어떤 자금을 어디로 보낼지 알려주는 비즈니스에 연결된 특정 ID | 123456 |

</Accordion>

<div id="scan-barcode-success-scan_barcode_success" />

<Accordion title="바코드 스캔 성공( scan_barcode_success )">

**목적**

이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 사용자가 판매자와 특정 거래를 완료하는 시점 파악
* 가장 인기 있는 판매자 확인

**트리거**

사용자가 전자지갑 앱을 사용하여 방문한 각 판매자의 QR 코드를 스캔할 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| merchant\_name | 판매자 이름 | cineplex |
| merchant\_ID | 거래에 관련된 결제 처리 시스템에 어떤 자금을 어디로 보낼지 알려주는 비즈니스에 연결된 특정 ID | 123456 |

</Accordion>

<div data-zendesk-anchors="ewallet=-%EC%A0%84%EC%9E%90%EC%A7%80%EA%B0%91 h_01HGTAEVWFZXCA7AV0P35W992F=-%EC%A0%84%EC%9E%90%EC%A7%80%EA%B0%91 h_01HGTAEVWFR4QS6XAT1T28N1R5=%EC%A4%91%EC%9A%94 recommended-structures-for-predefined-events=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAEVWF8SVYTQMQ12219HX0=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAEVWFBA3CD7ZA40VCER95=complete-registration-af_complete_registration h_01HGTAEVWGDBN8B3P2YHQJ5RYF=login-af_login h_01HGTAEVWGYFYEZBD3ZED7GGFG=content-view-af_content_view recommended-structures-for-custom-events=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAEVWG39P9A84P926BG3VE=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAEVWGNYC5Z0ACHV8CFVNQ=wallet-complete-topup-wallet_complete_topup h_01HGTAEVWG36K4V4Z0NN8QYDNV=payment-transaction-completed-payment_transaction_completed h_01HGTAEVWG136M86GM1JPV74RH=bill-payment-success-bill_payment_success h_01HGTAEVWG34EXM28GW2ZN0NRC=promo-promo h_01HGTAEVWG0EHESWPQHCX4P3SH=voucher-redeem-voucher_redeem h_01HGTAEVWGKGC7N8ZB0MMQJ4YE=select-merchant-select_merchant h_01HGTAEVWG20101JC5VVK29Y0E=scan-barcode-success-scan_barcode_success" />
