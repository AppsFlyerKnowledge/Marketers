---
title: 영수증 검증에 대하여
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T14:32:24Z'
  edited_at: '2026-10-14T10:28:13Z'
  id: 42136725767569
  locale: ko
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/ko/articles/42136725767569
---
> **한눈에 보기:** 영수증 검증이 인앱 구매 및 구독에서 수익을 측정하고 이를 앱 스토어와 검증하여 정확한 수익 측정을 보장하는 방법을 이해하십시오.

광고주는 영수증 유효성 검사를 사용하여 Play 스토어 및 App Store의 인앱 구매 및 구독을 유효성 검사하고 측정할 수 있습니다.

영수증 검증은 모든 계정 플랜에 대해 무료입니다.

<div id="note" />

> 📘 **참고**
>
> 순수익 계산, 전체 구독 퍼널 커버리지, 환불 처리 및 자동 구매 감지 및 중복 제거의 혜택을 누리기 위해 프리미엄 ROI360 스토어 수익 솔루션을 사용하는 것을 고려하십시오. 구매 및 구독 유효성 검사를 위한 두 가지 솔루션에 대한 자세한 내용과 비교는 다음을 참조하십시오. <Anchor target="_blank" href="/marketers/ko/docs/purchase-and-subscription-validation-overview#the-two-solutions-for-purchase-and-subscription-validation">구매 및 구독 유효성 검사를 위한 두 가지 솔루션.</Anchor>

<div id="how-does-receipt-validation-work" />

## 영수증 검증은 어떻게 작동합니까?

영수증 검증 흐름은 다음과 같습니다:

1. 사용자가 인앱 구매를 수행합니다.
2. 앱 스토어는 성공적인 구매를 앱에 알립니다.
3. 앱 개발자는 SDK의 영수증 검증 메서드를 호출합니다: `validateAndLogInAppPurchase`
4. SDK는 AppsFlyer 검증 서비스를 호출합니다.
5. AppsFlyer는 구매가 사기인지 확인하기 위해 검증합니다.
6. 유효성 검사에 성공하면 앱스플라이어는 구매 또는 구독을 기록합니다.
7. 영수증 유효성 검사가 실패하면 해당 이벤트는 다음에 표시됩니다. <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports#blocked-inapp-events">차단된 앱 내 이벤트 원시 데이터 보고서</Anchor> (Protect360 구독자에게 제공) 및 <Anchor target="_blank" href="/marketers/ko/docs/testing-the-sdk-integration-for-marketers#view-live-events">실시간 이벤트 뷰어 페이지</Anchor> 파라미터가 `af_validated` 로 설정되어 있습니다. `false`.
8. AppsFlyer 검증 서비스는 응답을 SDK로 전송합니다.
9. SDK는 영수증 검증 응답을 앱으로 전송합니다(성공 또는 실패).

<div id="activate-receipt-validation" />

## 영수증 검증 활성화

영수증 검증을 활성화하려면 다음 단계를 따르십시오:

1. AppsFlyer에서 사이드 메뉴에서 <Image alt="settings-roi.png" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.02%" /> **설정**을 열고 **ROI360** 아래에서 **수익 설정**을 선택합니다.
2. **구매 및 구독** 탭을 엽니다.
3. **1 제품 유형 선택**에서 **영수증 검증**을 선택하십시오.
4. 계속 진행하려면 **저장 및 다음**을 클릭하여 영수증 검증을 설정하십시오.

<div id="set-up-receipt-validation" />

## 영수증 검증 설정

자세한 내용은 다음을 참조하십시오. <Anchor target="_blank" href="/marketers/ko/docs/set-up-receipt-validation">영수증 유효성 검사 설정</Anchor><Anchor target="_blank" href="/marketers/ko/docs/set-up-receipt-validation#3단계-sdk-구현-확인">.</Anchor>

<div id="in-app-purchase-events-and-parameters-for-receipt-validation" />

## 영수증 검증을 위한 인앱 구매 이벤트 및 매개변수

모든 미리 정의된 이벤트는 다음 속성을 공유합니다:

* S2S 이벤트로 처리됩니다.
* 대시보드 및 원시 데이터 보고서에서 유기적 또는 비유기적 인앱 이벤트로 사용할 수 있습니다.
* 포스트백을 통해 파트너에게 보낼 수 있습니다.
* SKAN Conversion Studio에서 사용할 수 있습니다.

**인앱 구매에 대해 기록된 이벤트는:**

* `af_purchase` - 프로덕션
* 샌드박스

구독 이벤트.

* `af_ars_trial_started` - 체험 기간이 시작된 구독.
* `af_ars_subscriptions_started` - 유료 구독(체험 기간 없음)이 시작되었습니다, 프로덕션
* `af_ars_sandbox_sdk` - 체험 또는 유료 구독이 시작되었습니다, 샌드박스

**이 이벤트에는 다음과 같은 미리 정의된 매개변수가 포함됩니다:**

* `af_product_id`
* iOS 전용
* 안드로이드 전용
* `af_revenue` (샌드박스 이벤트의 경우 - `af_sandbox_revenue`)
* `af_currency`
* `af_store` (app\_store / play\_store)
* `af_environment` (샌드박스/프로덕션)
* 영수증 검증

**추가 사용자 정의 매개변수:**

* SDK 호출에서 전송된 추가 사용자 정의 매개변수는 원시 데이터 보고서의 `custom_data` 필드에 나타납니다.

<div id="switch-from-roi360-store-revenue-to-receipt-validation" />

## ROI360 스토어 수익에서 영수증 검증으로 전환

현재 ROI360 스토어 수익을 사용 중이고 영수증 검증으로 전환하려면 다음 단계를 따르세요:

1. AppsFlyer에서 사이드 메뉴에서 <Image alt="settings-roi.png" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.02%" /> **설정**을 열고 **ROI360** 아래에서 **수익 설정**을 선택합니다.
2. **구매 및 구독** 탭에서 **제품 유형**이 현재 **ROI360**으로 설정되어 있는지 확인하세요.
3. <Image alt="제목 없음 3.png" src="https://files.readme.io/c27f864253e6749f883047b4529ad292153500db5aebd452568a6aa04407472e-34623601366033.png" width="2.07%" />를 클릭하세요.
4. 영수증 검증으로 전환할 때의 영향에 대한 메시지가 나타납니다:
   * 환불 귀속, 구독 갱신 측정 및 순수익 계산과 같은 ROI360 기능이 비활성화됩니다.
   * 데이터 정확성이 감소할 수 있습니다.
   * 구매 커넥터는 영수증 검증에서 지원되지 않습니다.
   * 오직 `validateAndLogInAppPurchase` SDK 방법만 지원됩니다.
5. 필요한 경우 '**제품 비교 보기**'를 클릭하여 비교 표를 검토하세요.
6. 계속 진행하려면 **전환**을 클릭하여 변경 사항을 확인하세요.
7. 전환 후 **제품 유형**이 **영수증 검증,** 으로 업데이트되며 화면에 간소화된 구성이 반영됩니다.
8. 다음 항목을 다시 검증해야 합니다:
   * **SDK 구현** validateAndLog 메서드에 대한

<div id="traits-and-limitations" />

## 특징 및 제약 사항

| 특성 | 비고 |
| --- | --- |
| 지원되는 스토어 | • Play 스토어  <br />앱스토어  <br />• 다른 (타사) 스토어의 경우, 인앱 구매 이벤트를 수동으로 전송해야 합니다. |
| iOS 샌드박스 앱 | iOS 샌드박스 앱의 경우, App Store에 라이브되지 않은 앱을 의미하며, '키 검증'은 항상 유효하지 않은 상태로 표시됩니다. |

<div data-zendesk-anchors="h_01KD0PBEK0P2PACH8PX8M068S1=%EC%B0%B8%EA%B3%A0 how-does-receipt-validation-work=%EC%98%81%EC%88%98%EC%A6%9D-%EA%B2%80%EC%A6%9D%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%A9%EB%8B%88%EA%B9%8C h_01KD0PBEK0M2NEZJ95QXBA1H3W=%EC%98%81%EC%88%98%EC%A6%9D-%EA%B2%80%EC%A6%9D%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%A9%EB%8B%88%EA%B9%8C enable-receipt-validation=%EC%98%81%EC%88%98%EC%A6%9D-%EA%B2%80%EC%A6%9D-%ED%99%9C%EC%84%B1%ED%99%94 h_01KD0PBEK0BZNW8YP02EW0DHH4=%EC%98%81%EC%88%98%EC%A6%9D-%EA%B2%80%EC%A6%9D-%ED%99%9C%EC%84%B1%ED%99%94 set-up-receipt-validation=%EC%98%81%EC%88%98%EC%A6%9D-%EA%B2%80%EC%A6%9D-%EC%84%A4%EC%A0%95 h_01KD0PBEK1GZSJQPTP0P2TJMNJ=%EC%98%81%EC%88%98%EC%A6%9D-%EA%B2%80%EC%A6%9D-%EC%84%A4%EC%A0%95 inapp-purchase-events-and-parameters-for-receipt-validation=%EC%98%81%EC%88%98%EC%A6%9D-%EA%B2%80%EC%A6%9D%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%9D%B8%EC%95%B1-%EA%B5%AC%EB%A7%A4-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B0%8F-%EB%A7%A4%EA%B0%9C%EB%B3%80%EC%88%98 h_01KD0PBEK1DVMRXR64EMSWT75W=%EC%98%81%EC%88%98%EC%A6%9D-%EA%B2%80%EC%A6%9D%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%9D%B8%EC%95%B1-%EA%B5%AC%EB%A7%A4-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B0%8F-%EB%A7%A4%EA%B0%9C%EB%B3%80%EC%88%98 switch-from-roi360-store-revenue-to-receipt-validation=roi360-%EC%8A%A4%ED%86%A0%EC%96%B4-%EC%88%98%EC%9D%B5%EC%97%90%EC%84%9C-%EC%98%81%EC%88%98%EC%A6%9D-%EA%B2%80%EC%A6%9D%EC%9C%BC%EB%A1%9C-%EC%A0%84%ED%99%98 h_01KD0PBEK1AKE1XM2XVTCNTJ68=roi360-%EC%8A%A4%ED%86%A0%EC%96%B4-%EC%88%98%EC%9D%B5%EC%97%90%EC%84%9C-%EC%98%81%EC%88%98%EC%A6%9D-%EA%B2%80%EC%A6%9D%EC%9C%BC%EB%A1%9C-%EC%A0%84%ED%99%98 traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01KD0PBEK1HQKTGM7JP2KYPJAR=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
