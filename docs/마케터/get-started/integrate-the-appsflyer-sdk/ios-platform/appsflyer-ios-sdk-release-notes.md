---
title: 앱스플라이어 iOS SDK 릴리스 정보
metadata:
  keywords:
    - Advertisers
    - Release Notes
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
  created_at: '2017-03-09T19:49:54Z'
  edited_at: '2026-10-14T10:37:16Z'
  id: 115001224823
  locale: ko
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/ko/articles/115001224823
---
> **한눈에 보기:** SDK 릴리스 노트는 iOS SDK의 최신 변경 사항에 대한 간략한 개요를 제공합니다. 보다 포괄적인 세부 정보를 찾는 개발자는 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes">Dev Hub에서 iOS 릴리스 정보</Anchor>를 검토하세요.

**iOS 및 Android의 레거시 SDK 버전은 고정된 6개월 주기로 지원이 중단됩니다.** 이 주기는 사전 통지를 제공하도록 설계되어 팀이 미리 계획하고 중단 없이 전체 앱 기능을 유지하는 데 도움을 줍니다. 최신 SDK로 업그레이드하면 최신 기능, 향상된 안정성 및 지속적인 지원에 접근할 수 있습니다.

<div id="important" />

> 🚧 **중요!**
>
> 원활한 전환을 보장하기 위해 앱 개발자는 지원 종료 날짜 이전에 최신 SDK 버전으로 업데이트할 것을 권장합니다.

<div id="end-of-support-vs-deprecated" />

## 지원 종료 vs. 사용 중단

AppsFlyer는 지원 수준과 데이터 측정에 미치는 영향을 명확히 하기 위해 **사용 중단** 및 **지원 종료** SDK 버전을 구분합니다.

* **사용 중단된 버전** 알려진 문제로 인해 더 이상 권장되지 않는 SDK 버전, 예를 들어 치명적인 버그가 있는 경우입니다. 이 버전은 여전히 AppsFlyer에 데이터를 전송할 수 있지만, 계속 사용하지 않는 것이 권장되며 지원되는 버전으로 업그레이드하는 것이 강력히 권장됩니다.
* **지원 종료 버전:** 모든 플랫폼에서 측정이 완전히 중단된 SDK 버전입니다. Android와 iOS 모두에서 설치, 세션 및 인앱 이벤트는 측정되지 않습니다. 이 버전에서 발생하는 모든 트래픽(특히 AppsFlyer에 의해 제외되지 않는 한)은 400 상태 코드를 받게 되며, 이는 SDK가 평소처럼 API 호출을 전송하려고 시도하지만 AppsFlyer 서버가 이를 거부하고 데이터가 처리되지 않음을 의미합니다.

<div id="ios-sdk-release-notes" />

## 웹 SDK 릴리스 노트

아래 표는 지원되는 iOS SDK 버전의 릴리스 노트를 제공하며, 릴리스 날짜 및 개발자를 위한 주요 업데이트를 포함합니다. 개발자 정보는 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk">iOS SDK 통합 가이드</Anchor>를 참조하십시오.

| 버전 | 출시일 | 참고 |
| --- | --- | --- |
| 6.17.7 | $150 | <ul><li>구글의 ICM 라이브러리에서 데이터를 가져오는 문제를 수정했습니다.</li></ul> |
| 6.17.6 | $150 | <ul><li>SDK가 ICM 데이터를 AppsFlyer에 전송하려고 할 때 충돌을 일으킬 수 있는 v6.17.3에서 도입된 문제를 수정했습니다.</li></ul> |
| 6.17.5  <br />사용 중단 | $150 | <ul><li>**이 버전은 더 이상 지원되지 않으며 사용해서는 안 됩니다.**</li></ul> |
| 6.17.4  <br />사용 중단 | $150 | <ul><li>**이 버전은 더 이상 지원되지 않으며 사용해서는 안 됩니다.**</li><li>SDK가 초기화될 때 드물게 앱이 충돌하는 문제를 수정했습니다.</li></ul> |
| 6.17.3  <br />사용 중단 | $150 | <ul><li>**이 버전은 더 이상 지원되지 않으며 사용해서는 안 됩니다.**</li><li>정확성을 높이기 위해 구글의 ICM 라이브러리에서 데이터를 가져오는 로직을 업데이트했습니다.</li></ul> |
| 6.17.2 | 2025-07-15 | <ul><li>`validateAndLogInAppPurchase` API(베타)를 업데이트했습니다.</li><li>ATT(앱 추적 투명성) 동의를 수집하는 앱에 대한 Apple Search Ads(ASA) 토큰 처리 개선.</li></ul> |
| 6.17.1 | $475.22 | <ul><li><Anchor target="_blank" href="https://support.google.com/google-ads/answer/16203286">Google 통합 전환</Anchor> (ICM) 측정을 위한 지원 추가.</li><li>개발 환경에서 SDK를 실행할 때 App Store 로그인 팝업이 나타나는 문제를 수정했습니다.</li></ul> |
| 6.17.0 | $475.22 | <ul><li>안정성 및 성능 개선</li></ul> |
| 6.16.2 | 2025-03-10 | <ul><li>이 버전을 플러그인으로 출시하기 위해 필요한 기술 업데이트</li></ul> |
| 6.16.1 | 2025-02-18 | <ul><li>DMA 동의 데이터를 앱스플라이어에 수동으로 전송하기 위한 API가 업데이트되었습니다.</li></ul> |
| 6.16.0 | 2025-01-19 | <ul><li>Purchase Connector를 통한 구독 및 인앱 구매 리포팅를 위해 Apple의 StoreKit 2 API 지원이 추가되었습니다. 이 기능은 현재 비공개 베타 버전입니다.</li></ul> |
| 6.15.3 | 2024-09-23 | SDK 유지 관리 |
| 6.15.2 | 2024-08-28 | <ul><li>Purchase Connector에서 이벤트 전송과 관련된 문제를 해결했습니다. 이번 수정 사항은 Purchase Connector의 어떤 프로덕션 버전에도 영향을 미치지 않으며, 버전 6.15.x 업데이트와 관련이 있습니다.</li></ul> |
| 6.15.1 | 2024-08-19 | <ul><li>동일한 공급업체의 앱 두 개 이상이 디바이스에 설치된 경우 발생하는 재설치 감지 문제를 해결했습니다.</li></ul> |
| 6.15.0 | 2024-08-06 | <ul><li>앱스플라이어로 광고 수익 데이터를 전송하는 `logAdRevenue` API를 추가했습니다. **참고:** 이 버전부터 AdRevenue Connector를 더 이상 사용할 수 없으며, `logAdRevenue` 메서드로 바꿔야 합니다. 자세한 내용은 [여기](https://dev.appsflyer.com/hc/docs/ad-revenue-2)를 참조하세요.</li><li>Purchase Connector와 관련된 내부 업데이트를 진행했습니다. Purchase Connector를 사용하고 이 SDK 릴리스 버전으로 업데이트하는 앱은 Purchase Connector도 v6.15.0으로 업데이트해야 합니다.</li></ul> |
| 6.14.6 | 2024-07-24 | <ul><li>새 세션을 시작할 때 SDK가 `getConversionData` API(GCD)를 중복 호출하는 문제를 수정했습니다. 이 문제는 측정에는 영향을 미치지 않습니다.</li></ul> |
| 6.14.5 | 2024-07-03 | <ul><li>앱에서 설정한 수동 동의 데이터의 전송 코드가 제거된 경우에도 수동 동의 데이터가 SDK에서 계속 전송되는 문제를 수정했습니다.</li></ul> |
| 6.14.4 | 2024-06-10 | <ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">엄격 모드(Strict-Mode) SDK</Anchor>에 대한 프라이버시 매니페스트가 업데이트되었습니다.</li></ul> |
| 6.14.3 | 2024-04-26 | <ul><li>Cocoapods를 사용하는 앱에서 개인정보 보호 매니페스트의 자동 병합 문제를 수정했습니다.</li></ul> |
| 6.14.2 | 2024-04-19 | SDK 유지 관리 |
| 6.14.1 | 2024-04-18 | <ul><li>업데이트된 구매 검증 흐름에 대한 지원이 추가되었습니다. 이 기능은 현재 비공개 베타 버전입니다. 더 알아보기.</li></ul> |
| 6.14.0 | 2024-04-07 | <ul><li>개인정보 보호 매니페스트 지원이 추가되었습니다. <Anchor target="_blank" href="/marketers/ko/docs/implement-privacy-manifest-in-your-app">앱스플라이어에서의 개인정보 보호 매니페스트에 대해 자세히 알아보세요</Anchor>.</li><li>SDK에 XCFramework 서명을 추가하여 Xcode 15를 사용하는 개발자가 SDK의 출처와 진위성을 검증할 수 있게 되었습니다.</li></ul> |
| 6.13.2 | 2024-03-26 | <ul><li>Xcode 15.3에서 SPM을 사용하는 앱의 릴리스가 실패하는 문제를 수정했습니다. 자세한 내용은<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes#version-6132">개발자 릴리스 노트를</Anchor>참조하세요.</li></ul> |
| 6.13.1 | 2024-03-05 | <ul><li>CMP 동의 흐름(DMA)에서 비 GDPR 사용자에 대한 동의 데이터 전송 문제를 수정했습니다.</li></ul> |
| 6.13.0   <br />사용 중단 | 2024-02-08 | <ul><li>구글의 새로운 EU 동의 정책에 대한 지원이 추가되었습니다.</li></ul> |
| 6.12.3 | 2024-01-04 | <ul><li>이메일 서비스 제공업체(ESP) 해결 플로우 내의 딥링킹 콜백에 새로운 `original_link` 파라미터가 추가되었습니다.</li><li>iAd 프레임워크에 대한 모든 참조가 제거되었습니다.</li></ul> |
| 6.12.2 | 2023-08-24 | SDK 유지 관리 |
| 6.12.1 | 2023-07-20 | <ul><li>SKAdNetwork 4.0에서 Coarse 전환 값이 "없음"으로 리포트되는 문제를 수정했습니다.</li><li>tvOS 구현의 비정상 종료가 수정되었습니다.</li></ul> |
| 6.12.0 | 2023-06-28 | SDK에서 비트코드 지원을 삭제했습니다. |
| 6.11.2 | 2023-06-13 | v6.11.0에 도입된 문제, 즉 `validateAndLogInAppPurchase` (구매 유효성 검사 및 로깅을 위한 레거시 API)를 호출해도 구매 이벤트가 기록되지 않는 문제를 수정했습니다.   <br />  <br />**중요:** `v6.11.0`또는 `v6.11.1`, 그리고 `validateAndLogInAppPurchase`를 사용하고 있으시면, API를 이 버전으로 업그레이드하세요. |
| 6.11.1 | 2023-05-24 | SDK 유지 관리 |
| 6.11.0 | 2023-04-25 | <ul><li>SDK가 앱스플라이어 서버에 요청을 전송하기 위해 URL의 새 앱스플라이어 도메인 이름을 사용합니다.</li><li>빈 값 또는 null 값이 전송될 때 setHost API의 동작이 변경되었습니다. [더 알아보기](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#sethost)</li></ul> |
| 6.10.1 | 2023-04-02 | 다이렉트 딥 링킹 시나리오의 UDL 페이로드에 `link` 파라미터를 추가했습니다. |
| 6.10.0 | 2023-02-15 | SKAdNetwork 4.0 지원. <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">앱스플라이어 SKAdNetwork 솔루션에 대해 자세히 알아보기</Anchor> |

<div id="unsupported-sdk-versions" />

## 지원되지 않는 SDK 버전

다음 SDK 버전은 **지원 종료** 상태에 도달했습니다. 이 버전은 더 이상 AppsFlyer에 데이터를 전송할 수 없으며, 이들로부터의 모든 트래픽은 거부됩니다.

| 버전 | 출시일 | 참고 |
| --- | --- | --- |
| 6.9.2  <br />지원 종료:  <br />2025-09-08 | 2023-01-31 | 전환 데이터 가져오기(GCD)에 대한 내부 요청 구조가 업데이트되었습니다. **참고**: 응답 데이터는 동일하게 유지됩니다. |
| 6.9.1  <br />지원 종료:  <br />2025-09-08 | 2022-11-28 | 전환 데이터 가져오기(GCD)에 대한 내부 요청 구조가 업데이트되었습니다. **참고**: 응답 데이터는 동일하게 유지됩니다. |
| 6.9.0  <br />지원 종료:  <br />2025-09-08 | 2022-11-06 | 광고 수익 리포트를 위한 내부 API가 업데이트되었습니다. 이 버전부터는 [AdRevenue용 일반 커넥터](https://dev.appsflyer.com/hc/docs/ad-revenue-2)만 지원됩니다.<br /><br />이 버전의 SDK는 AdRevenue Connector `V6.9.0`과 호환됩니다. |
| 6.8.1  <br />지원 종료:  <br />2025-09-08 | 2022-08-09 | **재설치 감지**: 디바이스 내 저장소를 사용하여 앱의 재설치를 감지하고 리포트하는 기능이 개선되었습니다. 이 기능은 앱스플라이어 대시보드의 <Anchor target="_blank" href="/marketers/ko/docs/app-settings">앱 설정 페이지(App Setting page)</Anchor>에서 제어할 수 있습니다. |
| 6.8.0  <br />지원 종료:  <br />2025-03-03 | 2022-07-19 | 재설치 감지의 경우 SDK V6.8.1+를 사용하십시오. |
| 6.7.0  <br />지원 종료:  <br />2025-03-03 | 2022-06-19 | iOS 15.4에 도입된 업데이트된 Apple API `updatePostbackConversionValue`를 사용하도록 SKAdNetwork 구현을 업데이트합니다.<br /><br />이는 SKAdNetwork에서 전송되는 데이터에는 영향을 미치지 않으며 앱 코드를 변경할 필요가 없습니다. |
| 6.6.1  <br />지원 종료:  <br />2025-03-03 | 2022-05-16 | SDK 유지 관리 |
| 6.6.0  <br />지원 종료:  <br />2025-03-03 | 2022-05-01 | 다이렉트 딥링킹 플로우(기존 사용자)에 대한 UDL의 `didResolveDeepLink` 콜백에 더 많은 파라미터를 추가했습니다. <Anchor target="_blank" href="/marketers/ko/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users">더 알아보기</Anchor>. |
| 6.5.4  <br />지원 종료:  <br />2025-03-03 | 2022-03-23 | SDK 유지 관리 |
| 6.5.3  <br />지원 종료:  <br />2025-03-03 | 2022-03-02 | **버그 수정:** URI 스킴을 기반으로 하는 링크의 이중 호출 `didResolveDeepLink` 문제를 수정했습니다. |
| 6.5.2  <br />지원 종료:  <br />2025-03-03 | 2022-01-26 | SDK 유지 관리 |
| 6.5.1  <br />지원 종료:  <br />2025-03-03 | 2022-01-03 | SDK 유지 관리 |
| 6.5.0  <br />지원 종료:  <br />2025-03-03 | 2021-12-22 | 리팩터링 및 내부 변경 사항. |
| 6.4.4  <br />지원 종료:  <br />2025-03-03 | 2021-12-12 | SDK 유지 관리 |
| 6.4.3  <br />지원 종료:  <br />2025-03-03 | 2021-11-30 | xcframework를 사용하여 MacOS 10.14.6에 대한 안정성이 수정되었습니다. |
| 6.4.2  <br />지원 종료:  <br />2025-03-03 | 2021-10-28 | SDK 유지 관리 |
| 6.4.1  <br />지원 종료:  <br />2025-03-03 | 2021-10-24 | Unity 앱의 안정성이 해결되었습니다. |
| 6.4.0  <br />지원 종료:  <br />2025-03-03 | 2021-09-12 | **추가된 API:** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor>를 사용하면 SDK가 데이터 공유에서 제외해야 하는 파트너를 설정할 수 있습니다.<br /><br />이 버전부터는 `setSharingFilter`그리고 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforallpartners">`setSharingFilterForAllPartners`</Anchor>가 더 이상 지원되지 않습니다. |
| 6.3.5  <br />지원 종료: 2024-08-31 | 2021-08-19 | **API 추가**: [`setCurrentDeviceLanguage`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setcurrentdevicelanguage)<br /><br />이 버전부터 SDK는 더 이상 언어를 자동으로 수집하지 않습니다. |
| 6.3.4  <br />지원 종료: 2024-08-31 | 2021-07-21 | <ul><li>**버그 수정:** XCode 12.5 시뮬레이터에서 SDK를 실행할 때 발생하는 문제가 해결되었습니다.</li><li>사소한 수정 및 업데이트.</li></ul> |
| 6.3.2  <br />지원 종료: 2024-08-31 | 2021-06-17 | 디버그 로그가 개선되었습니다. |
| 6.3.1  <br />지원 종료: 2024-08-31 | 2021-06-02 | SDK 유지 관리 |
| 6.3.0  <br />지원 종료: 2024-08-31 | 2021-05-13 | <ul><li>Apple Silicon 지원: M1 칩셋이 내장된 Mac 컴퓨터를 사용하여 시뮬레이터에서 SDK를 실행할 수 있도록 지원이 추가되었습니다.</li><li>이 버전부터 SDK는 iOS `9` 이상을 지원합니다. iOS `8`은 더 이상 지원되지 않습니다.</li><li>iOS 엄격 모드(Strict mode) SDK: Carthage 종속성 관리자에 대한 지원이 추가됨</li><li>원링크 API에 대한 기술 업데이트</li></ul> |
| 6.2.6  <br />지원 종료: 2024-08-31 | 2021-04-25 | <ul><li>버그 수정: SKAdNetwork 규칙이 `didFinishLaunchingWithOptions` 이후 SDK 초기화가 발생했을 때 로드되지 않았습니다.</li><li>버그 수정: `waitForATTUserAuthorization`사용자 동의가 주어졌더라도 IDFA 없이 출시 이벤트가 전송되는 엣지 케이스</li><li>iOS 8 장치에서 SDK를 실행하도록 허용</li><li>사용하지 않는 코드 및 데이터 정리 및 제거</li></ul> |
| 6.2.5  <br />지원 종료: 2024-08-31 | 2021-04-06 | SDK에서 사용되지 않는 데이터 리팩터링, 정리 및 제거.<br /><br />해당 버전 부터:<ul><li>`setShouldCollectDeviceName` 메서드는 더 이상 사용되지 않으며 디바이스 이름을 반환하지 않습니다.</li><li>SDK에서 전송된 `wifi` 파라미터를 `False`로 설정</li></ul> |
| 6.2.4  <br />지원 종료: 2024-08-31 | 2021-03-15 | SKAdNetwork 수익 측정 모드 및 `AF_REVENUE` 파라미터가 포함된 인앱 이벤트와 관련된 버그가 수정되었습니다.<br /><br />이번 버전부터 수익 측정의 경우, `AF_REVENUE`을 포함하는 모든 이벤트가 전환 값에 영향을 미칩니다. 이 변경 전에는 전환 값이 `AF_PURCHASE` 이벤트의 프레임워크에 있는 경우에만 설정되었습니다.<br /><br />**참고:** SKAdNetwork 수익 측정을 구현하려면, 이 버전으로 업그레이드해야 합니다. |
| 6.2.3  <br />지원 종료: 2024-08-31 | 2021-03-07 | SKAdNetwork의 `updateConversionValue` 호출에 관련된 버그 수정. |
| 6.2.2  <br />지원 종료: 2024-08-31 | 2021-02-18 | SDK 유지 관리 |
| 6.2.1  <br />지원 종료: 2024-08-31 | 2021-02-15 | <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S에 의한 이벤트 리포팅</Anchor> 지원 |
| 6.2.0  <br />지원 종료: 2024-08-31 | 2021-02-07 | 추가 API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setpartnerdata">setPartnerData</Anchor> |
| 6.1.4  <br />지원 종료: 2024-08-31 | 2021-01-12 | SDK 유지 관리 |
| 6.1.3  <br />지원 종료: 2024-08-31 | 2020-12-24 | <ul><li>추가 API: <Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#record-push-notifications">`addPushNotificationDeepLinkPath`</Anchor> (Movable Ink 지원)</li><li><Anchor target="_blank" href="https://developer.apple.com/documentation/adservices">Apple AdServices 프레임워크</Anchor> 지원</li></ul> |
| 6.1.2  <br />지원 종료: 2024-08-31 | 2020-12-03 | SDK 유지 관리 |
| 6.1.1  <br />지원 종료: 2024-08-31 | 2020-11-17 | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">엄격 모드(Strict mode) SDK</Anchor> 도입 |
| 6.1.0  <br />지원 종료: 2024-08-31 | 2020-11-09 | <Anchor target="_blank" href="https://dev.appsflyer.com/docs/ios-unified-deep-linking">통합 딥링킹 API</Anchor> 지원 |
| 6.0.8  <br />지원 종료: 2024-08-31 | 2020-10-28 | <Anchor target="_blank" href="/marketers/ko/docs/apple-app-clips-integration-guide">Apple 앱 클립(App Clips)</Anchor> 어트리뷰션 지원 |
| 6.0.7  <br />지원 종료: 2024-08-31 | 2020-10-21 | SDK 유지 관리 |
| 6.0.6  <br />지원 종료: 2024-08-31 | 2020-10-20 | SDK 유지 관리 |
| 6.0.5  <br />지원 종료: 2024-08-31 | 2020-10-08 | SDK 유지 관리 |
| 6.0.4  <br />지원 종료: 2024-08-31 | 2020-09-30 | ESP에서 발생하는 다중 리디렉션 지원 |
| 6.0.3  <br />지원 종료: 2024-08-31 | 2020-09-06 | <ul><li>API 이름 변경:<br />waitForAdvertisingIdentifier --> waitForATTUserAuthorization</li><li>SDK는 iOS 14에서도 기본적으로 IDFA를 수집합니다.(이전 iOS 버전과 동일)</li></ul> |
| 6.0.2   <br />지원 종료: 2024-08-31 | 2020-08-27 | <ul><li>API 이름 변경:<br />deviceLoggingDisabled --> anonymizeUser</li><li>iOS 14용 IDFA를 수집하려면 AppTrackingTransparency(ATT) 대화상자가 필요합니다.</li><li>IDFV 크로스 프로모션 어트리뷰션에 대한 지원 추가</li></ul> |
| 6.0.1 베타  <br />지원 종료: 2024-08-31 | 2020-08-06 | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">SKAdNetwork 어트리뷰션</Anchor>에 대한 지원이 추가되어 광고주가 사용자의 개인 정보를 보호하면서 캠페인의 성과를 측정할 수 있습니다.</li></ul> |
| 6.0.0 베타  <br />지원 종료: 2024-08-31 | 2020-08-04 | <ul><li>확장된 디버깅 기능</li><li>SDK 기능 및 API에 대한 주요 변경 사항. [더 알아보기](/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes)</li></ul> |

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/about-att-and-skan">iOS 14, ATT 및 SKAdNetwork에 대한 빠른 시작 가이드</Anchor>

<div data-zendesk-anchors="h_01JVHFG6PN34YFWNZKX2CYHJV8=%EC%A4%91%EC%9A%94 end-of-support-vs-deprecated=%EC%A7%80%EC%9B%90-%EC%A2%85%EB%A3%8C-vs-%EC%82%AC%EC%9A%A9-%EC%A4%91%EB%8B%A8 h_01JVHEKR4MTFV0FDHMTQW00BCS=%EC%A7%80%EC%9B%90-%EC%A2%85%EB%A3%8C-vs-%EC%82%AC%EC%9A%A9-%EC%A4%91%EB%8B%A8 ios-sdk-v6=%EC%9B%B9-sdk-%EB%A6%B4%EB%A6%AC%EC%8A%A4-%EB%85%B8%ED%8A%B8 01H8W3DDM1BYRSPMFTA3TCY8EQ=%EC%9B%B9-sdk-%EB%A6%B4%EB%A6%AC%EC%8A%A4-%EB%85%B8%ED%8A%B8 unsupported-sdk-versions=%EC%A7%80%EC%9B%90%EB%90%98%EC%A7%80-%EC%95%8A%EB%8A%94-sdk-%EB%B2%84%EC%A0%84 h_01JVHGN5NVRMGN9SJ5DWEAJYN3=%EC%A7%80%EC%9B%90%EB%90%98%EC%A7%80-%EC%95%8A%EB%8A%94-sdk-%EB%B2%84%EC%A0%84 h_01HE7RE2EPQX872DKNDBJ2G2QE=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
