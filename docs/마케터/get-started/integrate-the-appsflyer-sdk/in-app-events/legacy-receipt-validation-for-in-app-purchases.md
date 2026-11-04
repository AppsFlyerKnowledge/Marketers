---
title: 인앱구매 영수증 검증 기능
deprecated: true
metadata:
  keywords:
    - iOS
    - Android
    - Receipt
    - Validation
    - Receipt Validation
    - SDK
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
  created_at: '2015-02-26T10:30:58Z'
  edited_at: '2026-10-14T10:26:40Z'
  id: 207032106
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/207032106
---
<div id="important" />

> 🚧 **중요!**
>
> 이 문서에서는 더 이상 사용되지 않는 영수증 검증 기능에 대해 설명합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/bulletin-legacy-receipt-validation-is-deprecated">게시판을 참조하십시오: 구식 영수증 검증은 더 이상 사용되지 않습니다</Anchor>

> **한눈에 보기:** iOS 및 Android 앱 스토어에서 발생한 사기성 인앱 구매를 방지하기 위해 영수증 검증을 구현하고, 보고된 대로 인앱 구매가 발생했는지 확인하십시오. **참고**: 이것은 레거시 기능입니다. 새롭고 완전 자동화된 개선된 <Anchor target="_blank" href="/marketers/ko/docs/purchase-and-subscription-validation-overview">인앱 구매 검증 메커니즘</Anchor>에 대해 자세히 알아보십시오.

<div id="receipt-validation-flow" />

## 영수증 검증 흐름

영수증 검증 흐름은 다음과 같습니다:

1. 사용자가 인앱 구매를 수행합니다.
2. 앱 스토어가 성공적인 구매를 앱에 알립니다.
3. 앱 개발자가 SDK 영수증 검증 기능을 호출합니다.

   ```
   validateAndLogInAppPurchase
   ```
4. SDK가 AppsFlyer 검증 서비스를 호출합니다.
5. AppsFlyer가 구매를 검증하여 사기성이 아님을 확인합니다.
6. 성공 시, AppsFlyer는 내부적으로 일반 af\_purchase 이벤트를 생성합니다. 그렇지 않으면 생성된 이벤트는 사기로 표시됩니다(Protect360을 통해 사용 가능).
7. AppsFlyer 검증 서비스가 응답을 SDK로 전송합니다.
8. SDK가 영수증 검증 응답을 앱으로 전송합니다(성공 또는 실패).  
   영수증 검증에 실패하면 차단된 인앱 이벤트 로데이터 리포트(Protect360 가입자가 사용할 수 있음)에 이벤트가 표시됩니다.

영수증 검증 구현에 대한 자세한 내용은 개발자 SDK 문서를 참조하십시오:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-android#validating-purchases">안드로이드</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-ios#purchase-validation-using-validateandloginapppurchase">iOS</Anchor>

**참고:**

* iOS의 경우 샌드박스 앱, 즉 App Store에 라이브가 아닌 앱의 경우, 영수증 검증에는 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/validate-and-log-purchase-ios#testing-purchase-validation-in-sandbox-mode">추가 코드가 필요합니다</Anchor>.
* 샌드박스 환경에서 이루어진 구매는 일반 af\_purchase 이벤트로 기록되며, 그 수익은 AppsFlyer 대시보드와 보고서에 반영됩니다.
* AppsFlyer 영수증 검증 서비스 모든 계정 플랜에 대해 무료입니다.
* Android의 경우, 영수증 검증은 `null` 결과를 반환할 수 있으며, 최종 사용자가 구매 중 인터넷에 접속할 수 없는 경우 검증이 실패한 것으로 간주됩니다.

<div id="important-1" />

> 🚧 **중요!**
>
> `validateAndLogInAppPurchase` 호출은 **af\_purchase** 인앱 이벤트도 생성합니다. 따라서 검증할 때 af\_purchase 이벤트를 생성하지 마십시오. 이렇게 하면 중복 수익 이벤트가 발생합니다.

<div id="note" />

> 📘 **참고**
>
> * *T*여기 설명된 레거시 영수증 검증은 *StoreKit v2*를 지원하지 않습니다. 현재 버전은 iOS 앱 스토어와의 통합 설정.을 참조하십시오.
> * 서드파티 Android 앱 스토어에 대한 인앱 구매의 영수증 검증은 지원되지 않습니다.

<div data-zendesk-anchors="h_01KDJ7QZD8X692EVP1XXGV0KY4=%EC%A4%91%EC%9A%94 receipt-validation-flow=%EC%98%81%EC%88%98%EC%A6%9D-%EA%B2%80%EC%A6%9D-%ED%9D%90%EB%A6%84 01JDSM0JDAQXH8QX8ZAXNB0ZMB=%EC%98%81%EC%88%98%EC%A6%9D-%EA%B2%80%EC%A6%9D-%ED%9D%90%EB%A6%84 01JDSM0JDT6Q3WYW9K484QHY2M=%EC%A4%91%EC%9A%94-1 01JDSM0JD90J3EDMVN6D6Z9J40=%EC%B0%B8%EA%B3%A0" />
