---
title: '업데이트 알림: 레거시 영수증 유효성 검사는 더 이상 사용되지 않음'
metadata:
  keywords:
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T11:33:45Z'
  edited_at: '2026-10-14T10:28:14Z'
  id: 42133487071121
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/42133487071121
---
| 섹션 | 세부 정보 |
| --- | --- |
| **새로운 소식** | <ul><li>인앱 구매를 위한 <Anchor target="_blank" href="/marketers/ko/docs/legacy-receipt-validation-for-in-app-purchases">레거시 영수증 유효성 검사</Anchor> 솔루션은 이제 AppsFlyer SDK 전반에서 공식적으로 사용 중단되었습니다.</li><li>다음 SDK 버전부터 레거시 `validateAndLogInAppPurchase` 방법이 사용하지 않도록 설정됨으로 표시됨:<ul><li>안드로이드 SDK V6</li><li>iOS SDK(네이티브): v6.17.8</li><li>플러그인(Flutter, Unity, React Native 등): v6.17.8</li></ul></li><li>더 이상 사용되지 않는 메서드는 향후 SDK 릴리스에서 완전히 제거됩니다.</li><li>레거시 영수증 검증 제품은 완전히 중단되며 이후에는 더 이상 작동하지 않습니다. **2026년 7월 1일**.</li></ul> |
| **발효일** | <ul><li>업데이트 날짜 12:30:</li><li>완전히 중단되는 날짜: 2018년 7월</li></ul> |
| **핵심 내용** | <ul><li>사용되지 않는 `validateAndLogInAppPurchase` 방법은 위에 나열된 SDK 버전에 여전히 존재하지만 향후 업데이트에서는 제거될 예정입니다.</li><li>이 메서드를 사용하는 앱은 제거되면 AppsFlyer를 통해 앱 내 구매를 더 이상 유효성 검사할 수 없습니다.</li><li>AppsFlyer는 두 가지 지원되는 대안을 제공합니다:<ul><li>영수증 검증 새로운 앱 스토어를 사용하여 구매를 검증하는 무료 솔루션 `validateAndLog` SDK 메서드.</li><li>**ROI360 매장 수익**. 환불 추적, 전체 구독 수명 주기 가시성 및 순 매출 계산을 포함하는 프리미엄 수익 측정 솔루션입니다.</li></ul></li></ul> |
| **필요한 조치** | 중단을 피하고 AppsFlyer로 구매를 계속 검증하려면 두 가지 사용 가능한 솔루션에 대해 자세히 알아보고 그 중 하나로 마이그레이션하십시오.<br /><br />자세한 내용은 다음을 참조하십시오. <Anchor target="_blank" href="/marketers/ko/docs/purchase-and-subscription-validation-overview">구매 및 구독 유효성 검사 - 개요</Anchor> |