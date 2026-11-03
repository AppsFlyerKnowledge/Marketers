---
title: 앱스플라이어 안드로이드 SDK 릴리스 정보
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
  created_at: '2017-03-09T20:17:19Z'
  edited_at: '2026-10-14T10:30:55Z'
  id: 115001256006
  locale: ko
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/ko/articles/115001256006
---
> **한눈에 보기:** 안드로이드 SDK의 최신 변경 사항에 대한 간략한 개요를 보려면 SDK 릴리스 정보를 확인하세요. 보다 포괄적인 세부 정보를 찾는 개발자는 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-release-notes">Dev Hub에서 안드로이드 릴리스 정보</Anchor>를 검토하세요.

**iOS 및 Android용 레거시 SDK 버전은 고정된 6개월 주기로 지원이 중단됩니다.** 이 주기는 사전 통지를 제공하여 팀이 미리 계획하고 중단 없이 전체 앱 기능을 유지할 수 있도록 설계되었습니다. 최신 SDK로 업그레이드하면 최신 기능, 향상된 안정성 및 지속적인 지원에 접근할 수 있습니다.

> 🚧 **중요!**
>
> 원활한 전환을 보장하기 위해 앱 개발자는 지원 종료 날짜 이전에 최신 SDK 버전으로 업데이트할 것을 권장합니다.

## 지원 종료 vs. 사용 중단

AppsFlyer는 지원 수준과 데이터 측정에 미치는 영향을 명확히 하기 위해 **사용 중단** 및 **지원 종료** SDK 버전을 구분합니다.

* **사용 중단된 버전** 알려진 문제로 인해 더 이상 권장되지 않는 SDK 버전, 예를 들어 치명적인 버그가 있는 경우입니다. 이 버전은 여전히 AppsFlyer에 데이터를 전송할 수 있지만, 계속 사용하지 않는 것이 권장되며 지원되는 버전으로 업그레이드하는 것이 강력히 권장됩니다.
* **지원 종료 버전:** 모든 플랫폼에서 측정이 완전히 중단된 SDK 버전입니다. Android 및 iOS 모두에서 설치, 세션 및 인앱 이벤트는 측정되지 않습니다. 이 버전에서 발생하는 모든 트래픽(제품 팀에 의해 특별히 제외되지 않는 한)은 400 상태 코드를 받게 되며, 이는 SDK가 API 호출을 평소처럼 시도하지만 AppsFlyer 서버가 이를 거부하고 데이터가 처리되지 않음을 의미합니다.

## Android SDK 릴리스

아래 표는 지원되는 Android SDK 버전의 릴리스 노트를 제공하며, 릴리스 날짜 및 개발자를 위한 주요 업데이트를 포함합니다. 개발자 정보는 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk">Android SDK 통합 가이드</Anchor>를 참조하십시오.

| 버전 | 출시일 | 참고 |
| --- | --- | --- |
| 6.17.5 | 12:30: | <ul><li>안정성 개선 및 수정</li></ul> |
| 6.17.4 | $150 | <ul><li>SDK와 고급 보안 모듈 간의 통합이 업데이트되었습니다. 이 버전은 보안 모듈 v2.0.0 이상과 호환됩니다.</li><li>고급 보안 모듈을 사용 중이고 SDK를 v6.17.4로 업데이트하려면 보안 모듈도 v2.0.0으로 업데이트해야 합니다.</li></ul> |
| 6.17.3 | 2025-08-18 | <ul><li>기술 업데이트: 안정성 및 성과 개선.</li></ul> |
| 6.17.2 | 2025-08-05 | <ul><li>기술 업데이트: targetSDK버전 35로 업데이트</li></ul> |
| 6.17.1 | $475.22 | <ul><li>인앱 구매 검증 API(현재 베타)의 `validateAndLogInAppPurchase` API가 업데이트되었습니다.</li><li>Google Play를 통한 장치 무결성 검증을 가능하게 하기 위해 Google Play 무결성 API와의 통합이 추가되었습니다.</li></ul> |
| 6.17.0 | $475.22 | <ul><li>AppSet ID 수집 지원이 추가되었습니다. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id">개발자 지침 참조</Anchor></li></ul> |
| 6.16.2 | 2025-03-02 | <ul><li>SDK 연동 시 빌드 오류를 유발할 수 있는 문제를 수정했습니다.</li></ul> |
| 6.16.1 | 2025-02-17 | <ul><li>DMA 동의 데이터를 앱스플라이어에 수동으로 전송하기 위한 API가 업데이트되었습니다.</li></ul> |
| 6.16.0 | 2024-12-17 | <ul><li>삼성 프리로드 어트리뷰션에 대한 지원이 추가되었습니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-appsflyer-preload-referrer-attribution#특징-및-제약-사항">더 알아보기</Anchor>.</li><li>프라이버시 샌드박스 어트리뷰션 API(비공개 베타)에서 수익 측정에 대한 지원이 추가되었습니다.</li><li>안정성 문제를 해결하고 보안을 강화하기 위해 Dexguard를 v9.8.12로 업데이트했습니다.</li></ul> |
| 6.15.2 | 2024-10-10 | <ul><li>안정성 개선 및 수정</li><li>Privacy Sandbox Attribution API와 관련된 내부 업데이트</li></ul> |
| 6.15.1 | 2024-08-28 | 버전 업그레이드:<ul><li>targetSDKVersion: v34</li><li>Gradle: v8.7</li><li>Java: v17</li></ul> |
| 6.15.0 | 2024-07-31 | <ul><li>AppsFlyer에 광고 수익 데이터를 전송하는 `logAdRevenue` 메서드가 추가되었습니다. **참고:** 이 버전부터 AdRevenue Connector를 사용할 수 없습니다. `logAdRevenue` 메서드로 바꿔야 합니다. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">더 알아보기</Anchor></li></ul> |
| 6.14.2 | 2024-06-10 | <ul><li>Unity로 구축된 앱에서 Meta Install Referrer를 가져오는 데 발생하는 문제를 해결했습니다.</li></ul> |
| 6.14.1 | 2024-05-29 | SDK 유지 관리 |
| 6.14.0 | 2024-04-18 | <ul><li>업데이트된 구매 검증 흐름에 대한 지원이 추가되었습니다. 이 기능은 현재 비공개 베타 버전입니다. 더 알아보기.</li><li>Huawei Referrer 연동이 업데이트되었습니다. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#huawei-install-referrer">더 알아보기</Anchor>.</li></ul> |
| 6.13.1 | 2024-04-03 | SDK 유지 관리 |
| 6.13.0 | 2024-02-08 | <ul><li>Google의 새로운 EU 동의 정책(DMA)에 대한 지원이 추가되었습니다.</li></ul> |
| 6.12.6 | 2024-01-29 | SDK 유지 관리 |
| 6.12.5 | 2023-12-18 | <ul><li>ESP 해결 프로세스의 딥링킹 콜백에 파라미터 `original_link`를 추가했습니다.</li></ul> |
| 6.12.4 | 2023-10-25 | <ul><li>Dexguard는 SDK 안정성을 개선하기 위해 버전 9.4.16으로 업데이트되었습니다.</li></ul> |
| 6.12.3 | 2023-08-31 | SDK 유지 관리 |
| 6.12.2 | 2023-08-02 | <ul><li>안드로이드 8.1.0 및 안드로이드 11의 일부 기기에서 앱이 충돌할 수 있는 버그를 수정했습니다.</li></ul> |
| 6.12.1 | 2023-06-29 | <ul><li>크로스 프로모션에서 Play Store 출시가 지연되는 문제를 수정했습니다.</li><li>일부 기기에서 앱이 충돌하는 버그를 수정했습니다.</li></ul> |
| 6.12.0 | 2023-06-28 | <ul><li>사용되지 않음 - 버전 6.12.1을 사용하십시오.</li></ul> |
| 6.11.2 | 2023-06-29 | <ul><li>일부 기기에서 앱이 충돌하는 버그를 수정했습니다.</li></ul> |
| 6.11.1 | 2023-06-6 | <ul><li>사용되지 않음 - 버전 6.12.1을 사용하십시오.</li><li>SDK를 초기화한 후 앱이 가끔 다운되는 버그를 수정했습니다.</li></ul> |
| 6.11.0 | 2023-05-16 | <ul><li>SDK가 Google Play 리퍼러를 가져오려고 할 때 일부 기기에서 앱이 정지되는 문제를 수정했습니다.</li></ul> |
| 6.10.3 | 2023-04-25 | SDK 유지 관리 |
| 6.10.2 (사용 중단) |  | 사용 중단 |
| 6.10.1 | 2023-03-01 | <ul><li>SDK를 초기화할 때 가끔 삼성 디바이스의 앱이 닫히는 문제를 해결했습니다. 이 문제는 SDK V6.6.0 이상을 사용하는 앱에 영향을 미쳤습니다.</li></ul> |
| 6.10.0 | 2023년 2월 13일 | <ul><li>SDK와 앱스플라이어 서버 간의 통신을 위한 새로운 앱스플라이어 도메인입니다.</li><li>빈 값이나 null 값이 전송될 때 setHost API가 변경되었습니다. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#sethost">더 알아보기</Anchor></li></ul> |

## 지원되지 않는 SDK 버전

다음 SDK 버전은 **지원 종료** 상태에 도달했습니다. 이러한 버전은 더 이상 앱스플라이어로 데이터를 전송할 수 없으며, 해당 버전으로부터의 모든 트래픽이 거부됩니다.

| 버전 | 출시일 | 참고 |
| --- | --- | --- |
| 6.9.4  <br />지원 종료:  <br />2025-09-08 | 2022-12-6 | <ul><li>호출을 트리거한 광고 수익 SDK 커넥터에서 전환 리스너로 광고 수익 이벤트를 전송할 때 문제가 해결되었습니다.</li><li>광고 수익 SDK 커넥터에서 광고 수익 이벤트를 전송할 때 때때로 앱이 멈추는 문제가 해결되었습니다.</li></ul> |
| 6.9.3  <br />지원 종료:  <br />2025-09-08 | 2022-11-28 | <ul><li>전환 데이터 가져오기(GCD)에 대한 내부 요청 구조가 업데이트되었습니다. **참고**: 응답 데이터는 동일하게 유지됩니다.</li><li>앱의 전환 리스너가 null로 설정된 경우 SDK가 GCD 요청을 트리거하는 문제가 해결되었습니다.</li></ul> |
| 6.9.2  <br />지원 종료:  <br />2025-09-08 | 2022-10-02 | <ul><li>validateAndLogInAppPurchase API를 사용하여 구매 유효성 검사 요청에서 발생한 지연과 관련된 문제를 해결했습니다.</li></ul> |
| 6.9.1  <br />지원 종료:  <br />2025-09-08 | 2022-09-19 | SDK 유지 관리 |
| 6.9.0  <br />지원 종료:  <br />2025-09-08 | 2022-09-12 | <ul><li>Xiaomi GetApps Store Referrer에 대한 지원이 추가되었습니다.</li><li>광고 수익 리포트를 위한 내부 API가 업데이트되었습니다. 이 버전부터는 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">일반 광고 수익 SDK 커넥터</Anchor>만 지원됩니다.</li></ul> |
| 6.8.2  <br />지원 종료:  <br />2025-09-08 | 2022-08-29 | <ul><li>V6.7.0에 도입된 SDK의 캐싱 메커니즘에서 캐시된 이벤트가 여러 번 전송되는 중대한 문제를 수정했습니다.</li></ul> |
| 6.8.1  <br />(사용 중단)  <br />지원 종료:  <br />2025-09-08 | 2022년 8월 24일 | <ul><li>**사용 중단.** V6.8.2를 사용하세요.</li></ul> |
| 6.8.0  <br />(사용 중단)  <br />지원 종료:  <br />2025-09-08 | 2022-07-18 | <ul><li>**사용 중단.** V6.8.2를 사용하세요.</li><li>SDK에서 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#enablelocationcollection">`enableLocationCollection`</Anchor> API를 제거했습니다. 앱은 여전히 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#loglocation">`logLocation`</Anchor> API를 통해 SDK에 사용자의 위치 데이터를 직접 전달하여 리포트할 수 있습니다.</li><li>SDK의 `AndroidManifest.xml`에 `com.google.android.gms.permission.AD_ID` 권한을 추가했습니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/bulletin-the-android-sdk-adds-the-ad-id-permission">여기</Anchor>를 참조하십시오.</li><li>R8을 사용한 최적화 및 난독화와 관련된 문제를 수정했습니다.</li></ul> |
| 6.7.0  <br />(사용 중단)  <br />지원 종료:  <br />2025-09-08 | 2022-06-19 | <ul><li>**사용 중단.** V6.8.2를 사용하세요.</li><li>SDK가 앱스플라이어 서버에 대한 요청을 처리하는 방법을 변경했습니다. 이 변경에 따라 첫 번째 앱 열기(전환) 리포팅 관련 요청이 인앱 이벤트 및 기타 유형의 요청보다 우선시됩니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/bulletin-adding-a-priority-queue-to-the-android-sdk">여기</Anchor>를 참조하십시오.</li><li>**새 API:**  셀룰러 네트워크에 대한 정보(이동통신사 이름, 사업자 이름) 수집을 옵트아웃하기 위한 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisablenetworkdata">`setDisableNetworkData`</Anchor></li></ul> |
| 6.6.1  <br />지원 종료:  <br />2025-03-03 | 2022-05-16 | SDK 유지 관리 |
| 6.6.0  <br />지원 종료:  <br />2025-03-03 | 2022-05-01 | <ul><li>다이렉트 딥링킹 플로우(기존 사용자)에 대한 UDL의 `onDeepLinking` 콜백에 더 많은 파라미터를 추가했습니다. <Anchor target="_blank" href="/marketers/ko/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users">더 알아보기</Anchor>.</li></ul> |
| 6.5.4  <br />지원 종료:  <br />2025-03-03 | 2022-03-23 | SDK 유지 관리 |
| 6.5.3  <br />지원 종료:  <br />2025-03-03 | 2022-03-09 | <ul><li>**버그 수정:** 영어가 아닌 문자가 포함된 앱 추천 링크를 만들 때 발생하는 문제를 해결했습니다.</li></ul> |
| 6.5.2  <br />지원 종료:  <br />2025-03-03 | 2022-01-26 | <ul><li>UDL에서 디퍼드 딥링킹의 URL을 확인할 때 발생하는 문제를 해결했습니다.</li><li>DexGuard 9.2로 업데이트했습니다.</li><li>리팩터링 및 내부 변경 사항.</li></ul> |
| 6.5.1  <br />지원 종료:  <br />2025-03-03 | 2021-12-29 | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution#channel-name">Out-of-Store with Channel 옵션</Anchor>을 사용하는 앱에 대한 UDL을 사용한 딥링크 처리</li></ul> |
| 6.5.0  <br />지원 종료:  <br />2025-03-03 | 2021-12-07 | <ul><li>리팩터링 및 내부 변경 사항.</li></ul> |
| 6.4.3  <br />지원 종료:  <br />2025-03-03 | 2021-11-14 | <ul><li>`LinkGenerator`가 포함된 `V6.4.2`에서 URL 파라미터가 누락된 링크가 생성되는 버그를 수정했습니다.</li></ul> |
| 6.4.2  <br />지원 종료:  <br />2025-03-03 | 2021-10-24 | 다음 문제가 해결되었습니다.<ul><li>`LinkGenerator`에 의해 생성된 사용자 지정 URL에 `pid` 파라미터가 두 번 추가되는 문제.</li><li>사용자 지정 URI 스키마를 만드는 데 `LinkGenerator`를 사용할 때 `af_dp` 값에 불필요한 `/`가 추가되었습니다.</li><li>앱이 둘 중 하나만 수집하는 동작을 트리거한 경우 IMEI와 AndroidID가 모두 수집되었습니다.</li></ul> |
| 6.4.1  <br />지원 종료:  <br />2025-03-03 | 2021-10-17 | V3.5.4 이전 버전의 Gradle을 사용할 때 발생하는 컴파일 오류를 해결했습니다. |
| 6.4.0  <br />지원 종료:  <br />2025-03-03 | 2021-09-12 | **새 API:** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor>를 사용하면 SDK가 데이터 공유에서 제외해야 하는 파트너를 설정할 수 있습니다.<br /><br />이 버전부터는, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilter">`setSharingFilter`</Anchor>와 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforallpartners">`setSharingFilterForAllPartners`</Anchor>가 사용 중단됩니다. |
| 6.3.2<br /><br />지원 종료: 2024-08-31 | 2021-06-06 | **새 API**: [`setDisableAdvertisingIdentifiers`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers) |
| 6.3.1  <br />지원 종료: 2024-08-31 | 2021-05-26 | <ul><li>**새 API**: [`performOnDeepLinking`](https://dev.appsflyer.com/hc/docs/conversion-data)</li><li>호출 전`start`과 호출 후`stop`에 <Anchor target="_blank" href="/marketers/ko/docs/user-invite-attribution#절차">User Invite API</Anchor>를 트리거하는 기능이 추가되었습니다.</li><li>**버그 수정**: `setCustomerUserId` 호출 후에도 `waitForCustomerUserId`에 대한 호출이 해제되지 않는 문제가 해결되었습니다.</li></ul> |
| 6.3.0  <br />지원 종료: 2024-08-31 | 2021-04-29 | <ul><li>**버그 수정**: 인앱 이벤트가 전송 요청 실패 시 `onConversionDataFail`가 잘못 호출되는 문제</li><li>**버그 수정**: 모션 센서 지표 수집(프로드 감지용)</li><li>**버그 수정**: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl">UDL</Anchor>에 대한 난독화 관련 버그를 수정했습니다.</li><li>원링크 API에 대한 기술 업데이트</li></ul> |
| 6.2.3  <br />지원 종료: 2024-08-31 | 2021-03-04 | SDK 유지 관리 |
| 6.2.0  <br />지원 종료: 2024-08-31 | 2021-02-07 | <ul><li>**새 API**: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setpartnerdata">`setPartnerData`</Anchor></li></ul> |
| 6.1.4  <br />지원 종료: 2024-08-31 | 2021-01-12 | <ul><li>DexGuard V9에 대한 지원을 추가했습니다.</li></ul> |
| 6.1.3  <br />지원 종료: 2024-08-31 | 2020-12-24 | <ul><li>**새 API**: <Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#record-push-notifications">`addPushNotificationDeepLinkPath`</Anchor>(Movable Ink 지원)</li></ul> |
| 6.1.1  <br />지원 종료: 2024-08-31 | 2020-12-03 | <ul><li>삼성 갤럭시 스토어 리퍼러 지원 추가했습니다.</li><li>사소한 버그 수정 및 성능 개선.</li></ul> |
| 6.1.0  <br />지원 종료: 2024-08-31 | 2020-11-09 | <ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl">통합 딥링킹 API</Anchor>에 대한 지원 추가</li></ul> |
| 6.0.1  <br />지원 종료: 2024-08-31 | 2020-10-28 | SDK 유지 관리 |
| 6.0.0  <br />지원 종료: 2024-08-31 | 2020-10-14 | <ul><li>사용 중단 및 메서드 이름 변경을 포함하여 SDK 기능 및 API에 대한 주요 변경 사항. [더 알아보기](/docs/appsflyer-android-sdk-release-notes#android-v600-release-notes)</li></ul> |

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-sdk-version-control-policy">앱스플라이어 SDK 버전 관리 정책</Anchor>

<div data-zendesk-anchors="h_01JVHFG6PN34YFWNZKX2CYHJV8=%EC%A4%91%EC%9A%94 end-of-support-vs-deprecated=%EC%A7%80%EC%9B%90-%EC%A2%85%EB%A3%8C-vs-%EC%82%AC%EC%9A%A9-%EC%A4%91%EB%8B%A8 h_01JVHEKR4MTFV0FDHMTQW00BCS=%EC%A7%80%EC%9B%90-%EC%A2%85%EB%A3%8C-vs-%EC%82%AC%EC%9A%A9-%EC%A4%91%EB%8B%A8 android-sdk-v6=android-sdk-%EB%A6%B4%EB%A6%AC%EC%8A%A4 h_01H9ZPCP8RWF24WAZ6YYMA1GS0=android-sdk-%EB%A6%B4%EB%A6%AC%EC%8A%A4 deprecated-versions=%EC%A7%80%EC%9B%90%EB%90%98%EC%A7%80-%EC%95%8A%EB%8A%94-sdk-%EB%B2%84%EC%A0%84 01JHFAXXV51DHADQ7P2Q6RHFX0=%EC%A7%80%EC%9B%90%EB%90%98%EC%A7%80-%EC%95%8A%EB%8A%94-sdk-%EB%B2%84%EC%A0%84 h_01HDNZ774ME3SVT89JS7R4MSKE=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
