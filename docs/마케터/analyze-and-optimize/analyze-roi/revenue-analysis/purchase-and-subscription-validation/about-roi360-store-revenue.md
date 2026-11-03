---
title: ROI360 스토어 매출
metadata:
  keywords:
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T16:34:39Z'
  edited_at: '2026-10-14T10:27:57Z'
  id: 42138855425297
  locale: ko
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/ko/articles/42138855425297
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** ROI360 스토어 수익을 사용하여 앱 내 구매 및 구독을 검증하고, 중복을 방지하고, 청구 수익을 계산합니다.

> 🚧 **중요!**
>
> ROI360 매장 수익은 ROI360 프리미엄 요금제 고객에게만 제공됩니다. 요금제를 확인하거나 업그레이드하려면 고객 성공 관리자(CSM)에게 문의하십시오.

ROI360 스토어 수익은 앱 내 구매 및 구독에서 수익을 완벽하고 정확하게 측정하는 AppsFlyer의 프리미엄 솔루션입니다. 고객의 라이프 사이클에 대한 포괄적인 뷰를 제공하여 광고 지출 반환 (ROAS)의 정확한 측정을 가능하게 합니다.

| 기능 | 세부 정보 |
| --- | --- |
| 수익 측정 범위 | <ul><li>App Store Connect(iOS) 또는 Google Play Console(Android)을 통해 관리되는 제품 및 구독의 인앱 구매에서 발생하는 모든 수익.</li><li>환불</li><li>보류 중이거나 지연되고 있는 거래 수익(안드로이드).</li><li>앱 내부와 외부에서 발생하는 구독 관련 이벤트</li><li>청구 수익, 이는 상점 수수료와 세금을 계산합니다.</li></ul> |
| 수익 검증 및 정확성 | 이 솔루션은 중복된 트랜잭션이 기록되는 것을 방지합니다. iOS에서는 가족 공유로 인한 중복을 방지하는 것도 포함됩니다. ROI360 스토어 수익은 Apple App Store 트랜잭션 데이터를 광고주에게 직접 전달할 수도 있습니다. |
| 데이터 소스 | <ul><li>Android 및 iOS용 앱스플라이어 구매 SDK 커넥터를 연동합니다.</li><li>앱 스토어 서버 알림</li><li>Google Play 실시간 개발자 알림(RTDN)</li></ul> |
| 보고 및 데이터 가용성 | 수익 데이터는 AppsFlyer 대시보드 및 보고서에서 사용할 수 있으며, 포스트백을 통해 파트너와 공유할 수도 있습니다. |

> ❗️ **경고**
>
> ROI360 스토어 수익을 사용하는 경우 앱 내 구매 이벤트를 보내지 마십시오. 이로 인해 수익 보고가 두 배로 발생합니다.

## ROI360 스토어 수익은 어떻게 작동합니까?

1. 사용자가 인앱 구매 또는 자동 갱신 구독을 합니다.
2. 앱은 앱 스토어에서 트랜잭션을 진행합니다.
3. AppsFlyer 구매 SDK 커넥터는 구매를 자동으로 감지하고 페이로드를 AppsFlyer로 전송하여 검증 및 로깅을 수행합니다.
4. 앱스플라이어는 관련 매장에서 구매의 유효성을 평가하여 사기가 아닌지 확인합니다.
   * 유효성 검사에 성공하면 앱스플라이어는 구매 또는 구독을 기록합니다.
   * 수신 확인이 실패하면 이벤트가 차단된 애플리케이션 내 이벤트 원시 데이터 보고서(Protect360 가입자가 사용할 수 있음) 및 라이브 이벤트 뷰어 페이지에서 파라미터 `af_validated` = false로 표시됩니다.
5. AppsFlyer는 응답을 SDK 커넥터로 전송하며, SDK 커넥터는 수신 확인 검증 응답(성공 또는 실패)을 앱으로 전달합니다.
6. 수신되는 모든 서버 알림은 앱스플라이어 구매 및 구독 수익 비즈니스 로직에 의해서도 처리됩니다.
   * SDK 커넥터를 통해 이전에 리포트된 트랜잭션에 대한 알림은 검증 및 처리되며, 그 결과 구매 또는 수명 주기 이벤트가 내부적으로 생성됩니다.
   * 알 수 없는 트랜잭션에 대한 알림은 삭제됩니다.
   * iOS의 경우 모든 서버 알림을 자체 서버로 다시 라우팅할 수 있습니다.

## ROI360 스토어 수익 활성화

ROI360 스토어 수익 측정을 활성화하려면 다음 단계를 따르십시오.

1. AppsFlyer에서 옆 메뉴에서 <Image alt="settings-roi.png" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.17%" /> **Settings** 를 열고 **ROI360** 아래에서 **Revenue Settings** 을 선택합니다.
2. **입고 및 구독** 탭을 엽니다.
3. **1 제품 유형 선택** 아래에서 **ROI360**을 선택합니다.
4. 계속하려면 **다음**을 클릭합니다.

## ROI360 스토어 매출 설정

<Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-store-revenue">ROI360 스토어 수익 설정</Anchor> 문서를 참조하십시오.

## 참고

다음 섹션에서는 ROI360 인앱 구매(IAP) 및 구독 수익 측정의 다양한 측면에 대해 자세히 설명합니다. 이들은 IAP 및 구독 이벤트에 대한 이벤트 및 매개 변수, 브루트-넷 수익 계산을 지원하는 청구 수익, ROI360 IAP 및 구독 수익 측정 솔루션의 일반적인 특성 및 제한 사항을 포함합니다.

> 📘 **참고**
>
> 인앱 이벤트와 함께 추가 사용자 정의 매개변수를 보내려면 **사용자 정의 데이터 소스**를 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-connector">구매 SDK 커넥터</Anchor>에서 설정하십시오. 이를 통해 구매 및 구독 이벤트에 자체 비즈니스 로직이나 메타데이터를 추가할 수 있습니다.
> 이 매개변수는 원시 데이터 보고서의 `custom_data` 필드에서 사용할 수 있습니다.

<div id="iaprelated-events-and-parameters" />

<Accordion title="인앱 구매(IAP) 관련 이벤트 및 파라미터">

다음 섹션에서는 AppsFlyer가 측정하는 IAP 관련 이벤트와 각 이벤트별로 기록되는 매개변수를 보여줍니다. 각 파라미터에 대한 자세한 설명은 [이벤트 파라미터 사전](#parameter-dictionary)을 참조하십시오.

**생성된 모든 이벤트에는 다음과 같은 속성이 있습니다.**

* 서버-투-서버(S2S) 이벤트.
* 로데이터 보고서(오가닉 또는 논오가닉 인앱 이벤트로)에서 확인할 수 있으며, 수익 ETL 저장소 보고서에도 포함됩니다.
* 포스트백을 통해 파트너에게 보낸다.
* SKAN Conversion Studio에서 지원됩니다.

<div id="purchase-af_purchase" />

<Accordion title="구매 (af_purchase)">

**설명**

사용자가 구매할 때 기록됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code
* af\_net\_revenue\_factors

</Accordion>

<div id="purchase-af_purchase_free" />

<Accordion title="무료 구매(af_purchase_free)">

**설명**

사용자가 수익 금액이 없는 구매를 할 때 기록됩니다. 모든 수익 파라미터는 0으로 표시됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code
* af\_net\_revenue\_factors

</Accordion>

<div id="purchase-canceled-af_purchase_canceled" />

<Accordion title="구매 취소됨(af_purchase_canceled)">

**설명**

사용자가 구매를 취소할 때 기록됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment

</Accordion>

<div id="purchase-pending-af_purchase_pending" />

<Accordion title="구매 보류 중(af_purchase_pending)">

**설명**

사용자가 구매했지만 결제가 아직 처리되지 않은 경우 기록됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment

</Accordion>

<div id="refund-af_purchase_refund" />

<Accordion title="환불 (af_purchase_refund)">

**설명**

구매가 환불될 때 기록됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue(수익이 0을 초과하는 경우 이벤트에 포함)
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="test-purchase-af_purchase_sandbox_sdk" />

<Accordion title="테스트 구매(af_purchase_sandbox_sdk)">

**설명**

샌드박스 환경에서 SDK를 통해 기록된 구매를 테스트할 때 기록됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_purchase\_state
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_net
* af\_sandbox\_revenue

</Accordion>

<div id="test-purchase-af_purchase_sandbox_s2s" />

<Accordion title="테스트 구매(af_purchase_sandbox_s2s)">

**설명**

샌드박스 환경에서 S2S를 통해 리포트된 구매를 테스트할 때 기록됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_purchase\_state
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_net
* af\_sandbox\_revenue

</Accordion>

</Accordion>

<div id="subscriptionrelated-events-and-parameters" />

<Accordion title="구독 관련 이벤트 및 파라미터">

다음 섹션에는 앱스플라이어가 측정하는 구독 관련 이벤트와 각 이벤트에 대해 기록되는 파라미터가 표시됩니다. 각 파라미터에 대한 자세한 설명은 [이벤트 파라미터 사전](#parameter-dictionary)을 참조하십시오.

생성된 모든 이벤트는:

* S2S 이벤트로 간주됩니다.
* 로데이터 리포트(오가닉 또는 논오가닉 인앱이벤트)에서 액세스할 수 있습니다.
* 포스트백을 통해 파트너에게 보낼 수 있습니다.
* SKAN Conversion Studio에서 사용할 수 있습니다.

**참고:** 참고: 사용자 장치 플랫폼에 따라 인앱이벤트에 대해 일부 파라미터가 항상 채워지는 것은 아닙니다.

<div id="trial-started-af_ars_trial_started" />

<Accordion title="평가판 시작(af_ars_trial_started)">

**설명**

구독자가 평가판 기간을 시작할 때 기록됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="trial-canceled-af_ars_trial_canceled" />

<Accordion title="평가판 취소(af_ars_trial_canceled)">

**설명**

구독자가 평가판 기간 동안 구독의 자동 갱신을 취소할 때 기록됩니다. 사용자가 체험 기간 내에 자동 갱신을 복원하지 않으면 이탈 이벤트가 발생합니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="trial-churned-af_ars_trial_churned" />

<Accordion title="평가판 이탈 (af_ars_trial_churned)">

**설명**

평가판 기간 후 구독자가 이탈할 때 기록됩니다. 이는 자동 갱신 취소 및 평가판 기간 만료 후에 발생합니다. 또한 갱신과 관련된 청구 또는 기술 문제로 인해 이탈이 발생할 수도 있습니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_reason

</Accordion>

<div id="trial-converted-af_ars_trial_converted" />

<Accordion title="평가판 변환 (af_ars_trial_converted)">

**설명**

평가판 기간 후 전체 가격 갱신이 시작될 때 기록됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* store\_commission
* af\_revenue (수익이 0을 초과하는 경우에만 이벤트에 포함됨)
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-started-af_ars_subscription_started" />

<Accordion title="구독 시작됨(af_ars_subscription_started)">

**설명**

할인된 구독 또는 정액이 책정된 구독이 시작될 때 기록됩니다.

**참고**:

* 새 구독은 SDK 커넥터를 통해서만 기록할 수 있습니다.
* iOS의 경우, 구독자가 이미 소유한 구독을 재구매하면 SDK 커넥터가 성공적인 영수증 검증을 앱에 다시 리포트하지만 앱스플라이어에 새 트랜잭션을 기록하지는 않습니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue(수익이 0을 초과하는 경우 이벤트에 포함)
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-canceled-af_ars_subscription_canceled" />

<Accordion title="구독 취소(af_ars_subscription_canceled)">

**설명**

청구 기간 중간에 자동 갱신 구독이 취소될 때 기록됩니다. 사용자가 동일한 결제 기간 내에 자동 갱신을 복원하지 않으면 이탈 이벤트가 발생합니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-paused-af_ars_subscription_paused-android-only" />

<Accordion title="구독 일시 중지됨(af_ars_subscription_paused) - 안드로이드만 해당">

**설명**

사용자가 활성 구독을 일시 중지할 때 기록됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-resumed-af_ars_subscription_resumed" />

<Accordion title="구독 재개 (af_ars_subscription_resumed)">

**설명**

이탈 또는 환불된 구독 후 전체 가격의 구독이 다시 시작될 때 기록됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* af\_reason
* event\_revenue (이벤트 수익이 0을 초과하는 경우 이벤트에 포함)
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors

</Accordion>

<div id="subscription-churned-af_ars_subscription_churned" />

<Accordion title="구독 이탈(af_ars_subscription_churned)">

**설명**

구독자가 이탈할 때 기록됩니다. 이는 일반적으로 자동 갱신 취소 또는 청구 기간 만료 후에 발생합니다. 또한 청구 또는 기술적 문제에 이어 발생할 수 있으며, 갱신이 이탈로 이어질 수 있습니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_reason

</Accordion>

<div id="subscription-refunded-af_ars_subscription_refunded" />

<Accordion title="구독료 환불됨(af_ars_subscription_refunded)">

**설명**

구독자가 환불을 받을 때 기록됩니다.

**참고:**

* 이 이벤트는 일반적으로 음수 값과 함께 생성됩니다. 환불된 거래를 감지할 수 없거나 환불 세부 정보가 알림에 포함되지 않은 경우 환불 이벤트에 값이 표시되지 않습니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_reason
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_refunded\_transaction\_ids
* event\_revenue\_usd
* event\_revenue(수익이 0을 초과하는 경우 이벤트에 포함)
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_store
* af\_environment
* af\_period\_type
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-billing-grace-af_ars_subscription_billing_grace" />

<Accordion title="구독 청구 유예(af_ars_subscription_billing_grace)">

**설명**

청구 문제로 인해 구독 갱신이 실패하고 구독자가 청구 유예 기간에 들어갈 때 기록됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-renewed-af_ars_subscription_renewed" />

<Accordion title="구독 갱신 (af_ars_subscription_renewed)">

**설명**

자동 갱신 구독이 발생할 때 기록됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue(수익이 0을 초과하는 경우 이벤트에 포함)
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors

</Accordion>

<div id="subscription-changed-af_ars_subscription_xgraded" />

<Accordion title="구독 변경(af_ars_subscription_xgraded)">

**설명**

구독자가 다른 제품으로 업그레이드, 다운그레이드 또는 교차 등급을 지정할 때 기록됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue(수익이 0을 초과하는 경우 이벤트에 포함)
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors

</Accordion>

<div id="existing-subscriber-af_ars_existing_subscriber" />

<Accordion title="기존 구독자(af_ars_existing_subscriber)">

**설명**

SDK 커넥터가 청구 주기 중간에 구독자에 대한 알림을 받을 때 기록되며, 구독자를 다른 관련 수명 주기 단계로 전환하는 후속 서버 알림을 받기 전에 기록됩니다. 이 이벤트는 일반적으로 온보딩 및 SDK 커넥터 채택 기간 동안 생성됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* country
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated

</Accordion>

<div id="test-purchase-af_ars_sandbox_sdk" />

<Accordion title="테스트 구매(af_ars_sandbox_sdk)">

**설명**

샌드박스 환경에서 SDK를 통해 기록된 구매를 테스트할 때 기록됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* country
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated
* af\_net
* af\_sandbox\_revenue

</Accordion>

<div id="test-purchase-af_ars_sandbox_s2s" />

<Accordion title="테스트 구매(af_ars_sandbox_s2s)">

**설명**

샌드박스 환경에서 S2S를 통해 리포트된 구매를 테스트할 때 기록됩니다.

**파라미터**

* app\_id
* customer\_user\_id
* country
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated
* af\_net
* af\_sandbox\_revenue

</Accordion>

</Accordion>

<div id="parameter-dictionary" />

<Accordion title="파라미터 사전">

IAP 및 정기 결제 이벤트의 파라미터는 로데이터 리포트에 자체 열로 표시되거나 **이벤트 값의**일부로 채워집니다.

자체 열이 있는 파라미터는 다음과 같습니다.

* app\_id
* customer\_user\_id
* country\_code
* af\_currency
* event\_revenue\_usd
* af\_revenue
* android\_id
* ip
* idfa
* appsflyer\_id

이러한 파라미터에 대한 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary">데이터 필드 사전</Anchor> 을 참조하십시오.

다음 표에서는 ARS 및 VIAP 이벤트에서 사용할 수 있는 로데이터 파라미터에 대해 설명합니다.

| 파라미터 | 비고 | 제품 |
| --- | --- | --- |
| af\_cancelation\_date\_ms | 취소 날짜 | 인앱 결제 (IAP) |
| af\_cuids | <ul><li>ARS의 컨텍스트에서는 이 매개변수에 모든 CUID가 포함된 배열이 들어 있습니다.</li><li>CUID 배열은 디바이스 ID와 상관없이 표시됩니다. 따라서 동일한 CUID가 여러 디바이스 ID에 표시될 수 있습니다.</li></ul> | 구독 |
| af\_discount\_id | 사용자가 최초로 구매할 때 제시된 할인(또는 프로모션) ID입니다. 할인 코드가 있는 경우에만 ID가 채워집니다. | <ul><li>인앱 결제 (IAP)</li><li>구독</li></ul> |
| af\_discount\_type | 유저가 사용한 할인 유형입니다. 가능한 값:<ul><li>iOS<ul><li>introductory</li><li>프로모션</li><li>offer\_codes</li><li>win\_back</li></ul></li><li>안드로이드<ul><li>intro price</li><li>one\_time\_code</li><li>vanity\_code</li></ul></li></ul> | 구독 |
| af\_environment | 데이터가 수신되는 환경(프로덕션 또는 샌드박스). | <ul><li>인앱 결제 (IAP)</li><li>구독</li></ul> |
| af\_expires\_date\_ms | 현재 구독 청구 주기의 만료 날짜 | 구독 |
| af\_net\_revenue | 모든 요인을 기준으로 계산한 순수익입니다. af\_net\_revenue\_factors를 참조하세요. | <ul><li>인앱 결제(IAP)</li><li>구독</li></ul> |
| af\_net\_revenue\_country | <ul><li>세금이 적용되는 <Anchor target="_blank" href="https://www.nationsonline.org/oneworld/country_code_list.htm">두 글자 ISO 국가 코드</Anchor> 입니다.</li><li>예시: CA</li><li>참고: 영국의 코드는 GB가 아닌 UK로 구현되었습니다.</li></ul> | <ul><li>인앱결제 (IAP)</li><li>구독</li></ul> |
| af\_net\_revenue\_factors | <ul><li>리포트된 af\_net\_revenue 금액을 생성하는 모든 요인 이유를 나타내는 배열입니다.</li><li>예시 값: store\_commission</li></ul> | <ul><li>인앱결제 (IAP)</li><li>구독</li></ul> |
| af\_net\_revenue\_postal\_code | <ul><li>문자 및/또는 숫자 문자열</li><li>예시: L4J8E3</li></ul> | <ul><li>인앱결제 (IAP)</li><li>구독</li></ul> |
| af\_net\_revenue\_subdivision | <ul><li>일부 국가의 경우 추가적인 주/하위 행정구역이 있을 수 있습니다. 이는 ISO 3166-2 하위 구분 코드에 따라 처리됩니다.</li><li>국가 코드와 구역 코드가 포함됩니다.</li><li>예시: US-CA</li></ul> | <ul><li>인앱결제 (IAP)</li><li>구독</li></ul> |
| af\_net\_revenue\_tax\_exclusive | <ul><li>boolean 파라미터로, true나 false 중 하나입니다.</li><li>false는 세금이 전체 수익에 포함됨을 의미합니다.</li><li>true는 세금이 전체 언급된 수익에 추가됨을 의미합니다.</li></ul> | <ul><li>인앱 결제 (IAP)</li><li>구독</li></ul> |
| af\_net\_revenue\_tax\_name | <ul><li>특정 세금 유형을 설명하는 고객 청구서에 표시되는 이름입니다.</li><li>예시: Sales, VAT, GST</li></ul> | <ul><li>인앱 결제(IAP)</li><li>구독</li></ul> |
| af\_net\_revenue\_tax\_rate | <ul><li>4자리 소수점까지의 세율을 나타냅니다.</li><li>예시: 7.25</li></ul> | <ul><li>인앱 결제(IAP)</li><li>구독</li></ul> |
| af\_offer\_id | <ul><li>거래에 적용된 제안 ID, 관련(예: 할인 또는 프로모션 제안).</li><li>안드로이드 전용</li></ul> | <ul><li>인앱 결제(IAP)</li><li>구독</li></ul> |
| af\_order\_id | <ul><li>거래에 대한 주문 ID</li><li>안드로이드 전용</li></ul> | <ul><li>인앱 결제 (IAP)</li><li>구독</li></ul> |
| af\_original\_transaction\_id | <ul><li>초기 거래 ID</li><li>iOS 전용</li></ul> | <ul><li>인앱 결제 (IAP)</li><li>구독</li></ul> |
| af\_original\_transaction\_id | <ul><li>트랜잭션의 기존 ID</li><li>iOS 전용</li></ul> | <ul><li>인앱 결제 (IAP)</li><li>구독</li></ul> |
| af\_period\_type | <ul><li>구독 또는 체험 기간 유형.</li><li>가능한 값:<ul><li>trial</li><li>intro</li><li>normal</li></ul></li></ul> | 구독 |
| af\_product\_id | 구독 제품 ID | <ul><li>인앱 결제 (IAP)</li><li>구독</li></ul> |
| af\_purchase\_date\_ms | 신고된 제품 ID 인앱 이벤트에 대한 구매 날짜 | <ul><li>인앱 결제 (IAP)</li><li>구독</li></ul> |
| af\_purchase\_option\_id | <ul><li>거래와 관련된 구매 옵션 ID.</li><li>안드로이드 전용</li></ul> | 인앱 결제 (IAP) |
| af\_purchase\_option\_type | 거래의 구매 옵션 유형입니다. 사용 가능한 값(Android):<ul><li>구매</li><li>렌트</li></ul> | 인앱 결제 (IAP) |
| af\_purchase\_state | 가능한 값:<ul><li>Purchased (구매함)</li><li>Canceled (취소됨)</li><li>Pending (보류중)</li></ul> | 인앱 결제(IAP) |
| af\_purchase\_token | <ul><li>거래에 대한 구매 토큰</li><li>안드로이드 전용</li></ul> | <ul><li>인앱 결제 (IAP)</li><li>구독</li></ul> |
| af\_reason | [ 콘텐츠 변경되지 않음] | <ul><li>인앱 결제 (IAP)</li><li>구독</li></ul> |
| af\_refunded\_transaction\_ids | <ul><li>환불된 모든 거래 ID의 목록</li><li>iOS 전용</li></ul> | <ul><li>인앱 결제(IAP)</li><li>구독</li></ul> |
| af\_store | 구독 제품을 구매한 앱 스토어 | <ul><li>인앱 결제(IAP)</li><li>구독</li></ul> |
| af\_subscription\_ownership\_type | FAMILY\_SHARED는 유저가 가족 공유를 통해 액세스할 수 있음을 의미합니다. PURCHASED는 결제 유저가 구매했음을 의미합니다. | 구독 |
| af\_transaction\_id | <ul><li>트랜잭션의 ID</li><li>iOS 전용</li></ul> | <ul><li>인앱 결제 (IAP)</li><li>구독</li></ul> |
| store\_commission | <ul><li>상점이 구매한 제품에서 받는 계산된 수수료 비율입니다.</li><li>소수로 표시됩니다.</li><li>예시: 30</li></ul> | <ul><li>인앱 결제 (IAP)</li><li>구독</li></ul> |

</Accordion>

<div id="true-revenue" />

<Accordion title="순수익">

순수익은 ROI360 Store 수익 솔루션을 제공하기 위해 구축된 비즈니스 로직 계층입니다. 들어오는 각 트랜잭션의 순수익 가치를 실시간으로 자동 계산하여 리포트에 포함합니다.

> 📘 **참고**
>
> 순수익은 원시 데이터 보고서에 표시되며 앱 내 이벤트 포스트백을 통해 실시간으로 전송할 수 있습니다. 또한 <Anchor target="_blank" href="/marketers/ko/docs/my-dashboards">내 대시보드에서</Anchor> 순 지표 (순수익, 순ROI, 순ROAS, 순ARPU, 순매출총이익) 로도 사용할 수 있습니다.
>
> 넷 수익을 포스트백으로 보내려면 옵션과 함께 인앱 이벤트를 구성하십시오. **값, 수익 및 넷 수익**. 보기 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#포스트백에-포함할-데이터">앱 내 이벤트 포스트백 구성</Anchor> 자세한 내용은 을 참조하십시오.

> 📘 **팁**
>
> 또한 앱 내 이벤트 포스트백을 구성하여 표준 수익(금전적) 매개변수에서 총수익 대신 순수익을 보낼 수도 있습니다. 이 구성에 액세스하려면 고객 성공 관리자(CSM)에게 문의하십시오.

순매출액은 총매출액에서 순매출액을 산출할 때 다음 요소를 고려합니다:

* **스토어 수수료**:
  * 자동으로 계산되어 리포트됩니다. 고객님께서는 아무런 조치도 취할 필요가 없습니다.
  * 구매(인앱 구매)의 경우 기본 상점 수수료는 상점에 따라 다릅니다.
    * App Store - 일본: 26%. 중국 본토(CN): 25%. 전 세계: 30%.
    * 플레이 스토어: 30%.
  * 구독의 경우 수수료는 구독자의 평생 기준으로 구독자당 자동으로 계산됩니다.
    * 앱 스토어 — 첫 12개월: 일본 26%, 중국 본토(CN) 25%, 기타 국가 30%입니다. 13개월째부터: 일본은 15%, 중국 본토(CN)는 12%, 그 외 지역은 15%입니다.
    * 플레이 스토어: 첫날부터 15%입니다.
  * 관련 순수익 파라미터는 로데이터 리포트에서 확인할 수 있습니다.
  * 기본값과 다른 매장 수수료율을 설정하려면 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-7">순수익 API</Anchor> 를 사용하십시오. 예를 들어, 앱이 Apple의 소기업 프로그램에 등록되어 있고 수수료율이 15%(중국 본토(CN)는 12%)인 경우에 유용합니다.
* **세금**:
  * 세금은 기본 세율 구성을 사용하여 ROI360으로 측정된 모든 거래에 대해 기본적으로 보고됩니다.
  * 이는 세금 포함 국가(스티커 가격에 세금이 포함된 국가)에 적용됩니다. 예를 들어, 영국에서는 AppsFlyer가 세금과 상점 수수료의 금액을 인출합니다. 세금이 포함되지 않는 국가(예: 미국)의 경우 목록 가격에 세금이 포함되지 않으므로 수익 및 순수익 매개 변수에는 기본적으로 세금이 포함되지 않습니다.
  * 구성은 다음을 사용하여 편집할 수 있습니다. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-7">순수익 API</Anchor>. 지원되는 국가와 기본 세율을 확인하려면 다음을 참조하십시오. <Anchor target="_blank" href="https://docs.google.com/document/d/e/2PACX-1vSl3DwlK2Gt2aa5gmDzD3-K3CtnIM85oMNrqx3PCTamwCERWYU48GugNpD31BFjA2PJjZnqaXIVe2Hx/pub">이 JSON 파일</Anchor>. 개발자는 이를 수정하거나 API에서 그대로 사용할 수 있습니다.

보고서에서 실제 수익을 볼 때 다음 매개변수에는 순수익 데이터가 포함됩니다. 자세한 내용은 파라미터 사전을 참조하십시오.

| 파라미터 | 순수익 계수 |
| --- | --- |
| `store_commission` | 스토어 수수료 |
| `af_net_revenue_tax_name` | 세금 |
| `af_net_revenue_tax_rate` | 세금 |
| `af_net_revenue_tax_exclusive` | 세금 |
| `af_net_revenue_postal_code` | 세금 |
| `af_net_revenue_country` | 세금 |
| `af_net_revenue_subdivision` | 세금 |
| `af_net_revenue` | <ul><li>스토어 수수료</li><li>세금</li></ul> |
| `af_net_revenue_factors` | <ul><li>스토어 수수료</li><li>세금</li></ul> |

</Accordion>

<div id="troubleshooting-and-disprepancies" />

<Accordion title="문제 해결 및 불일치">

| 증상 | 설명 / 해결책 |
| --- | --- |
| AppsFlyer는 실제 앱 스토어보다 인앱 구매 및 구독 이벤트를 더 적게 표시합니다. | AppsFlyer에서는 SDK 커넥터가 포함된 앱 버전으로 업데이트한 사용자에 대해서만 이벤트가 생성됩니다. 한편, 앱 스토어는 사용자의 앱 버전과 관계없이 모든 이벤트를 기록합니다. 따라서 업데이트된 앱 버전이 완전히 적용될 때까지 앱의 수익 데이터와 스토어 데이터 간에 차이가 발생할 것으로 예상됩니다. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 사양 | 제품 | 비고 |
| --- | --- | --- |
| 할부 구독 (안드로이드) | 구독 수익 | 지원되지 않음 |
| 구독 보류 중  <br />거래 (안드로이드) | 구독 수익 | 지원되지 않음 |
| 새 구독 | 구독 수익 | 앱스플라이어 구매 SDK를 통해서만 기록됩니다. |
| 가격 변동 | 구독 수익 | 구독 수익이 새 제품 가격을 포함한 SDK에서 생성된 알림을 수신하지 못할 경우, 구독 수익은 계속해서 이전 제품 가격을 수익으로 보고합니다. 구매 SDK에서 새 제품 가격이 수신되면 새 가격이 기록됩니다. |
| 총 수익 | <ul><li>인앱 결제 (IAP)</li><li>구독 수익</li></ul> | 지원됨 |
| 순수익 | <ul><li>인앱 결제 (IAP)</li><li>구독 수익</li></ul> | 로데이터 및 내 대시보드에서 지원됨 (Net 메트릭으로) |
| 환불 | 인앱 결제 (IAP) | 최초 구매 후 180일까지 신고할 수 있습니다. |
| 중복 | <ul><li>인앱 결제 (IAP)</li><li>구독 수익</li></ul> | 이벤트 날짜로부터 최대 180일까지 보고된 거래에 대해 지원됩니다. |
| SDK 엄격 모드 | <ul><li>인앱 결제 (IAP)</li><li>구독 수익</li></ul> | ROI360 구독 및 인앱 구매는 다음의 SDK 엄격 모드에서 지원됩니다:<ul><li>AppsFlyer iOS 구매 SDK 커넥터 V6.13.0</li><li>Unity 구매 SDK 커넥터 V2.0.1</li></ul> |
| 통화 | <ul><li>인앱 결제 (IAP)</li><li>구독 수익</li></ul> | 수익은 원래 통화(event\_revenue 파라미터 사용)와 USD(event\_revenue\_usd 파라미터 사용)로 리포트됩니다. |
| 데이터 최신성 | <ul><li>인앱 결제 (IAP)</li><li>구독 수익</li></ul> | <ul><li>거래 수준 스토어 매출 리포트: 시간별</li><li>장치 수준의 스토어 수익 보고서: 8시간마다</li></ul> |
| StoreKit 2 | <ul><li>인앱 결제 (IAP)</li><li>구독 수익</li></ul> | <ul><li>StoreKit 2는 구매 SDK 커넥터 버전 6.16.2부터 지원됩니다.</li><li>앱이 업데이트된 App Store 자격 증명을 사용하고 있는지<Anchor target="_blank" href="/marketers/ko/docs/bulletin-update-app-store-credentials-for-ios-roi360-receipt-validation">여기</Anchor>에서 확인하세요.</li></ul> |
| Google 일회용 제품 | 인앱 결제 (IAP) | <ul><li>지원되는 구매 옵션: 구매 및 임대</li><li>사전 주문: 지원되지 않음</li></ul> |

</Accordion>

<div data-zendesk-anchors="h_01KSAJW61CZZBWBQ112VR5095C=%EC%A4%91%EC%9A%94 h_01KD0W3J6105033NV6FYKGQ8BQ=%EA%B2%BD%EA%B3%A0 how-does-roi360-store-revenue-work=roi360-%EC%8A%A4%ED%86%A0%EC%96%B4-%EC%88%98%EC%9D%B5%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%A9%EB%8B%88%EA%B9%8C h_01KD2JZQ0JYVF8S1E2W3N91KYV=roi360-%EC%8A%A4%ED%86%A0%EC%96%B4-%EC%88%98%EC%9D%B5%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%A9%EB%8B%88%EA%B9%8C enable-roi360-store-revenue=roi360-%EC%8A%A4%ED%86%A0%EC%96%B4-%EC%88%98%EC%9D%B5-%ED%99%9C%EC%84%B1%ED%99%94 h_01KD2JZQ0JS9YQ2SPNN6NHAJEH=roi360-%EC%8A%A4%ED%86%A0%EC%96%B4-%EC%88%98%EC%9D%B5-%ED%99%9C%EC%84%B1%ED%99%94 set-up-roi360-store-revenue=roi360-%EC%8A%A4%ED%86%A0%EC%96%B4-%EB%A7%A4%EC%B6%9C-%EC%84%A4%EC%A0%95 h_01KD2JZQ0JD53598CES8ECAHR3=roi360-%EC%8A%A4%ED%86%A0%EC%96%B4-%EB%A7%A4%EC%B6%9C-%EC%84%A4%EC%A0%95 reference=%EC%B0%B8%EA%B3%A0 h_01JKWGTJQY938NV6VCJ7KKS23E=%EC%B0%B8%EA%B3%A0 h_01KD6B3KC75RFDV08G9RT1BX1M=%EC%B0%B8%EA%B3%A0-1 h_01HDEPSK8DFQ24EZ5T0EPBSVS4=iaprelated-events-and-parameters 01H8VJJP1ER9N6BPAES8H8CK4T=purchase-af_purchase h_01J50N58GYF2BYC57HA7THSWW6=purchase-af_purchase_free 01H8VJJP1EXYE1EQS08CK8BG02=purchase-canceled-af_purchase_canceled 01H8VJJP1ET5TAAQ17EMK6TVRE=purchase-pending-af_purchase_pending 01H8VJJP1E8JKPGT2V9CCB1XW8=refund-af_purchase_refund 01H8VJJP1ECQMS49M8Z1X1FT4B=test-purchase-af_purchase_sandbox_sdk 01H8VJJP1E3X7YZNYT5D8REVEW=test-purchase-af_purchase_sandbox_s2s h_01HDEQBACTTPZ04YYD1KV49SEZ=subscriptionrelated-events-and-parameters 01H8VJJP1EHAZBGT82WRWB00JT=trial-started-af_ars_trial_started 01H8VJJP1ETCHTK6JMK9ERS5A5=trial-canceled-af_ars_trial_canceled 01H8VJJP1EC45X8PJVPWT3G7S3=trial-churned-af_ars_trial_churned 01H8VJJP1EYPQM50JVX1KPZXAZ=trial-converted-af_ars_trial_converted 01H8VJJP1EA4WTCEJWBB1HPRJF=subscription-started-af_ars_subscription_started 01H8VJJP1EF744NE425Y30VG0M=subscription-canceled-af_ars_subscription_canceled 01H8VJJP1EMKBP27070NRR9CZ5=subscription-paused-af_ars_subscription_paused-android-only 01H8VJJP1EGHNQ35JM1TWV4ND0=subscription-resumed-af_ars_subscription_resumed 01H8VJJP1EM2GJ28VBE6V76SBG=subscription-churned-af_ars_subscription_churned 01H8VJJP1E28XXAQSGZ9PYDT08=subscription-refunded-af_ars_subscription_refunded 01H8VJJP1E399B2AVWP9VKZ0D4=subscription-billing-grace-af_ars_subscription_billing_grace 01H8VJJP1EEZZ0DE75VXAZQP3E=subscription-renewed-af_ars_subscription_renewed 01H8VJJP1FGXHRK3J0XB2G4PCQ=subscription-changed-af_ars_subscription_xgraded 01H8VJJP1FKC8KZ2HKJVGZEV23=existing-subscriber-af_ars_existing_subscriber 01H8VJJP1F720QT97Q0TW4SEM2=test-purchase-af_ars_sandbox_sdk 01H8VJJP1FSRHG26EXMEG3325P=test-purchase-af_ars_sandbox_s2s 01H8VJJP1F0ZV2PX39D9JCG6B4=parameter-dictionary 01H8VJJP1FF219YN3XHRCGW7Z3=true-revenue h_01KBFWTM4XJ417930YVDD36ASK=%EC%B0%B8%EA%B3%A0-2 h_01KRKEP613DR8RZ5Q2A5H7KZAH=%ED%8C%81 01JHZG8FFHTYE2PMRWWS8WNR6X=troubleshooting-and-disprepancies 01H8VJJP1FP2MPRF8AN77REXD0=traits-and-limitations" />
