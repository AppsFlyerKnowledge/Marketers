---
title: 영수증 유효성 검사 설정
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
  created_at: '2025-12-21T15:14:21Z'
  edited_at: '2026-10-14T10:27:50Z'
  id: 42137474889489
  locale: ko
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/ko/articles/42137474889489
---
> **한눈에 보기:** 수수료 검증은 앱 내 구매 및 구독으로부터의 수익을 측정하고 앱 스토어와 확인하여 정확한 광고 지출 반환 (ROAS) 결과를 보장합니다.

<div id="overview" />

## 개요

<div id="note" />

> 📘 **참고**
>
> 수수료 검증에 대한 자세한 내용은, 어떻게 작동하고 AppsFlyer에서 활성화하는 방법을 포함하여, <Anchor target="_blank" href="/marketers/ko/docs/about-receipt-validation">수수수료 검증에 대해</Anchor> 참조하십시오.

Receipt validation을 설정하려면 다음 단계를 수행하십시오.

1. 스토어 자격 증명을 설정합니다(iOS 및 Android)
   * [iOS](#단계-1-ios-app-store-connect-키-설정): AppsFlyer에서 App Store Connect 키(App 내 구매 키, 키 ID 및 발행자 ID)를 구성하여 Receipt 검증을 활성화합니다.
   * [Android](#단계-1-android-서비스-계정-키-및-권한): Google Cloud 서비스 계정을 구성하고 Google Play 콘솔에서 필요한 권한을 설정하고 서비스 계정 JSON 키를 AppsFlyer에 업로드합니다.
2. [validateAndLog SDK API 구현](#2단계-2-sdk-v6을-구현합니다): 개발자가 AppsFlyer `validateAndLog` SDK API를 통합하고 테스트를 위해 모래 상자 환경을 구성할 수 있도록 준비합니다.
3. [Test validateAndLog SDK API 구현](#3단계-sdk-구현-확인): iOS 및 Android에서 샌드박스 테스트 구매 및 구독을 수행하여 Receipt 검증 이벤트가 AppsFlyer에서 생성되고 올바르게 기록되었는지 확인합니다.
4. [설정 확인 및 업데이트](#4단계-설정-확인-및-업데이트): 제품 유형이 Receipt validation로 설정되어 있는지 확인하고 스토어 키 및 SDK 통합 상태를 검토하여 정확하고 지속적인 수익 측정을 보장합니다.
5. [validateAndLog SDK API를 사용하여 앱 버전을 출시](#5단계-validateandlog-sdk-api를-사용하여-앱-버전을-출시합니다)합니다. `validateAndLog` SDK API가 통합되어 업데이트된 앱 버전을 출시하여 샌드박스 플래그가 비활성화되고 필요한 앱 내 이벤트가 검증 규칙에 의해 차단되지 않도록 합니다.

<div id="step-1-ios-set-up-app-store-connect-keys" />

## 단계 1 (iOS) App Store Connect 키 설정

단계 1에서 다음 자격 증명을 *App Store Connect*에서 얻고 AppsFlyer 플랫폼의 **수입 설정** 페이지에 입력합니다.

* 인앱 구매 (IAP)
* 키 ID
* *발급자 ID

**시작하기 전에**:

* 자격 증명을 설정하는 것은 App Store Connect 및 AppsFlyer에서 모두 수행되는 단계를 포함합니다. 설정 중에 App Store Connect 및 AppsFlyer 탭을 모두 열려 두십시오.
* iOS 앱은 StoreKit v1 또는 v2를 필요로 하며, 이는 앱 내 구매 및 구독을 처리하는 프레임워크를 제공합니다.

<div id="11-create-the-app-store-connect-keys" />

<Accordion title="1.1 App Store Connect 키 만들기">

iOS 자격 증명을 설정하려면 다음 단계를 따르십시오.

1. App Store Connect에서 **사용자 및 액세스**로 이동합니다.

   [![](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)
2. **사용자 및 액세스** >> **통합**으로 이동하고 **키** 목록에서 **앱 내 구매**을 선택합니다.

   [![](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)
3. **+ 를** 클릭하여 새로운 앱 내 구매 키를 생성합니다.

   [![](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)
4. API 키의 이름을 입력합니다.
5. **생성**을 클릭합니다.
6. 방금 생성한 키 옆에 있는 **Download In-App Purchase Key** 를 클릭하여 다운로드합니다. **참고**: 키를 한 번만 다운로드할 수 있습니다.
7. 방금 생성한 키의 **키 ID**를 복사하고 **키 ID**의 AppsFlyer 구매 및 구독 설정에 붙여넣습니다.

   [![](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)
8. **발행자 ID** 복사 **참고**: 페이지 상단에 **출판자 ID**가 표시되지 않으면 App Store Connect API 키를 생성합니다(어떤 액세스 레벨이든). 그런 후, 앱 내 구매 키의 발행자 ID가 페이지 상단에 나타납니다.

   [![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)

</Accordion>

<div id="12-set-the-app-store-connect-key" />

<Accordion title="1.2 App Store Connect 키 설정">

1. Receipt validation를 활성화합니다. #enable-receipt-validation
2. **App Store Connect keys** 단계에서 **App In-App Purchase 키** 필드에서 [<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.45%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png) **Upload**을 클릭하여 p8 파일을 업로드합니다.
3. **App Store Connect 키**라는 섹션에서 App Store Connect에서 복사한 값을 붙여넣습니다.

   * **키 ID**
   * *발급자 ID
4. **Validate keys** 를 클릭하여 입력한 키가 정확한지 확인합니다. **참고**: 앱이 App Store에 아직 게시되지 않은 경우 **Validate keys** 작업이 작동하지 않을 수 있습니다.
5. **보관하고 다음**을 클릭합니다.

</Accordion>

<div id="step-1-android-set-up-service-account-key-and-permissions" />

## 단계 1 (Android). 서비스 계정 키 및 권한

단계 1에서 *Google Play* 및 *Google Cloud*에서 다음 자격 증명을 얻고 AppsFlyer 플랫폼의 **수입 설정** 페이지에 입력하십시오.

**시작하기 전에**:

* 앱 내 구매 및 구독 수익 측정을 설정하는 것은 <Anchor target="_blank" href="https://cloud.google.com/">Google Cloud Platform</Anchor>, <Anchor target="_blank" href="https://play.google.com/console/">Google Play Console</Anchor> 및 <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">AppsFlyer UI</Anchor>에서 수행되는 단계를 포함합니다. 우리는 세 곳의 모든 탭을 전체 설정 동안 열려있는 것을 권장합니다.
* 앱스플라이어 UI를 설정하려면 관리자 권한이 필요합니다.

<div id="11-link-your-google-play-developer-account-to-your-google-cloud-project" />

<Accordion title="1.1 Google Play 개발자 계정을 Google Cloud 프로젝트에 연결">

**선행 조건**: Google Play 콘솔 및 Google Cloud 프로젝트에 액세스할 수 있습니다.

**Google Play 개발자 계정을 Google Cloud 프로젝트에 연결하려면 다음 단계를 수행하십시오.**

1. Google Play 콘솔에서 Google Play 개발자 계정으로 이동합니다.
2. 계정을 Google Cloud 프로젝트에 연결합니다. 이에 대한 시침은 이 <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#linking">Google 도움말 항목</Anchor>을 참조하십시오.
3. Google Play Developer API를 활성화합니다. 이에 대한 시침은 이 <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#enable">Google 도움말 항목</Anchor>을 참조하십시오.

   [![](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)

</Accordion>

<div id="12-configure-your-service-account-in-the-google-cloud-platform" />

<Accordion title="1.2 Google Cloud 플랫폼에서 서비스 계정을 구성합니다.">

**선행 조건**: Google Cloud 플랫폼에 대한 액세스.

**서비스 계정을 구성하려면 다음 단계를 따르십시오.**:

1. **서비스 계정**을 만들거나 찾으십시오.

   1. Google Cloud 플랫폼의 **서비스 계정** 섹션으로 이동하고 **서비스 계정 만들기**를 클릭합니다.[![](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)
   2. 서비스 계정 세부 정보를 작성합니다.[![](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)
   3. 이메일 주소를 복사합니다.[![](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)
   4. **만들기 및 계속**을 클릭합니다.
   5. **이 서비스 계정에 프로젝트에 대한 액세스 권한 부여** 단계에서  **Pub/Sub 구독자** 역할을 선택합니다.
   6. **계속하기** > **완료**를 클릭합니다.

      [![](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)
2. 서비스 계정 개인 키 다운로드:

   1. Google 클라우드 플랫폼에서 **서비스 계정** 섹션으로 이동하여 원하는 계정(지금 만든 계정)을 목록에서 찾고 **다른 작업** 아이콘을 클릭합니다.
   2. **키 관리**를 클릭합니다.[![](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)
   3. **키 추가** > **새 키 만들기**를 클릭합니다.

      [![](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)
   4. **Create private key** 팝업에서 **Key type** 아래에서 **JSON**을 선택하고 **Create를** 클릭합니다.[![](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)
   5. **생성**을 클릭합니다. 개인 키 JSON 파일이 다운로드됩니다.

      [![](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)
   6. JSON 키 파일을 저장하고 나중에 AppsFlyer에 업로드하십시오. **참고**! 당신은 열쇠를 저장해야합니다. 그것은 나중에 검색 할 수 없습니다. 그것을 저장하지 않으면 완전히 새로운 키를 생성해야 합니다.

</Accordion>

<div id="13-set-api-access-permissions-in-google-play-console" />

<Accordion title="1.3 Google Play 콘솔에서 API 액세스 권한 설정">

**선행 조건**: Google Play 콘솔에 액세스할 수 있습니다.

**참고**: 참고: 서비스 계정 사용자 인증 정보 및 권한을 설정한 후 사용가능할 때까지 시간이 걸릴 수 있습니다(경우에 따라 24시간까지). 이것은 당신이 나중에 단계에서 오류를받을 수 있습니다.

**Google Play 콘솔에서 API 액세스 권한을 설정하려면**

1. Google Play 콘솔에서 **사용자 및 권한**으로 이동하고, 만든 서비스 계정을 찾고 **새 사용자 초대**를 클릭합니다.

   [![](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)
2. 1.2.1.3 단계에서 서비스 계정을 구성할 때 복사한 **메일 주소**를 입력합니다.

   [![](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)
3. **권한** 섹션에서 **계정 권한** 탭으로 이동하여 다음 두 가지를 모두 선택합니다.

   * 재무 데이터, 주문 및 취소 설문조사 응답을 확인합니다.
   * [주문 및 구독 관리](https://support.appsflyer.com/hc/article_attachments/51857152739985).
4. **App 권한** 탭에서 **App 추가**를 클릭한 다음 앱을 선택합니다. 필요한 경우 여러 앱을 추가합니다.

   [![](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)
5. **Invite user** 를 클릭합니다.

   [![](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)
6. 확인 팝업에서 **시청 보내기**를 클릭합니다.

   [![](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)

</Accordion>

<div id="14-upload-the-service-account-private-key-to-appsflyer" />

<Accordion title="1.4 서비스 계정의 개인 키를 AppsFlyer에 업로드">

[단계 1.2](#12-configure-your-service-account-in-the-google-cloud-platform)에서 다운로드한 Google JSON 키를 업로드하고 검증합니다.

**선행 조건**: 관리자가 AppsFlyer에 액세스합니다.

**서비스 계정의 개인 키를 AppsFlyer에 업로드하려면 다음 단계를 수행하십시오.**:

1. <Anchor target="_blank" href="/marketers/ko/docs/about-receipt-validation#영수증-검증-활성화">수신 확인을 활성화</Anchor>합니다<Anchor target="_blank" href="/marketers/ko/docs/about-receipt-validation#영수증-검증-활성화">.</Anchor>
2. **서비스 계정 키 및 권한** 단계에서 **Google JSON 키 업로드** 필드에서 [<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.23%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png) **Upload** 를 클릭합니다.
3. [단계 1.2](#12-configure-your-service-account-in-the-google-cloud-platform)에서 다운로드 한 JSON 파일을 업로드하십시오.
4. **유효성 검증 키를 클릭하세요**. **참고:**

   * 서비스 계정 사용자 인증 정보 및 권한을 설정한 후 사용가능할 때까지 시간이 걸릴 수 있습니다(경우에 따라 24시간까지). 이로 인해 키를 검증하거나 검증 테스트를 수행하려고 할 때 오류가 발생할 수 있습니다.
   * 24시간 대기 시간 주변에서 작업하려면 Google Play 콘솔에서 어떠한 애플리케이션에도 이동한 다음 **모네티즈하기** > **제품** > **계약/애플리케이션 내 제품**로 이동하여 변경을 수행합니다. 예를 들어 제품 설명을 편집하고 저장합니다. 이것은 일반적으로 즉시 계정 인증 및 권한을 업데이트합니다. 그런 다음 변경 내용을 취소할 수 있습니다.
5. **다음**을 클릭합니다. **SDK 구현** 단계가 열립니다.

</Accordion>

<div id="step-2-implement-sdk" />

## 2단계: 2. SDK V6을 구현합니다.

이 단계에서 개발자가 SDK `validateAndLog` API를 통합하고 테스트를 위해 모래 상자 환경을 설정할 수 있도록 준비합니다. 최신 `validateAndLog` API를 지원하는 최소 SDK 버전은 Android용으로는 **6.17.5**, iOS용으로는 **6.17.8**입니다.

validateAndLog SDK API를 구현하려면 다음 단계를 따르십시오.

1. **SDK 구현** 단계에서 대시보드에 표시된 **전문 메시지**을 복사합니다.
2. 개발자에게 보내십시오. 그것은 다음을 포함합니다:

   * 앱 이름 및 앱 ID
   * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">SDK 통합 가이드</Anchor> 링크입니다.
   * 모래 상자 환경(`sandbox = true`)을 구성하는 지침.
   * 테스트 단계(**TestFlight** 사용).

   이 메시지는 개발자가 통합을 완료하고 테스트를 시작하는 데 필요한 모든 정보를 제공합니다.
3. **다음**을 클릭합니다. **Verify SDK implementation** 단계가 열립니다.

<div id="step-3-verify-sdk-implementation" />

## 3단계: SDK 구현 확인

샌드박스 환경에서 IAP 및 구독 수익 연동을 검증하여 SDK 커넥터가 제대로 연동되고 서버 알림이 올바르게 구성되고 AppsFlyer가 수신하는지 확인하는 것이 가장 좋습니다.

<div id="test-sdk-implementation" />

<Accordion title="테스트 SDK 구현">

AppsFlyer가 지난 7일 동안 앱에서 유효한 `validateAndLog` 페이로드를 받았는지 확인하려면 다음 단계를 수행하십시오.

1. **Verify SDK implementation** 단계에서 **Test SDK implementation** 를 클릭합니다.
2. AppsFlyer에서 수신한 최신 유용로드의 타임스탬프를 포함하여 결과를 검토합니다. 이 검사는 요청이 AppsFlyer에 도착하는지 확인할 뿐이며 데이터의 완전성이나 정확성을 확인하지 않습니다.
3. 구현을 완전히 검증하려면 아래의 테스트 단계를 계속하십시오.

</Accordion>

<div id="sandbox-environment-considerations" />

<Accordion title="샌드박스 환경 고려 사항">

샌드박스 환경에서:

* 처음 구매 이벤트만 validateAndLog SDK API가 AppsFlyer에 의해 기록되는 이벤트를 생성합니다. 앱 내 구매 이벤트는 `af_purchase_sandbox_sdk`라고 합니다. 구독 이벤트는 `af_ars_sandbox_sdk`라고 불립니다.
* Sandbox 이벤트는 0.
* Android의 경우 SDK의 샌드박스 환경이 구성되지 않은 경우에도 License Tester가 테스트를 수행하면 샌드박스 이벤트가 발생합니다.

</Accordion>

<div id="test-inapp-purchase-and-subscription-revenue" />

<Accordion title="인앱 구매 및 구독 수익 측정">

[![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

인앱 구매 및 구독 수익 측정

1. 개발자에게 validateAndLog SDK API의 샌드박스 환경을 구성하도록 지시하십시오.
2. <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">Google Play의 라이센스 테스터</Anchor> 및 iOS의 <Anchor target="_blank" href="https://developer.apple.com/testflight/">TestFlight</Anchor>에서 테스트 구매 또는 구독을 수행합니다.
3. 테스트 이벤트가 다음 방법 중 하나로 표시되는 것을 확인합니다.

   * 이벤트를 <Anchor target="_blank" href="/marketers/ko/docs/testing-the-sdk-integration-for-marketers#view-live-events">라이브 이벤트 뷰어에서 보기.</Anchor>
   * <Anchor target="_blank" href="/marketers/ko/docs/activity-metrics-in-my-dashboards">My Dashboards - Activity View</Anchor>에서 이벤트 데이터를 확인합니다.
4. 다음 테스트 이벤트를 찾으십시오.

   * 구매 이벤트의 `af_purchase_sandbox_sdk`.
   * 구독 이벤트의 `af_ars_sandbox_sdk`.
5. 테스트 이벤트에는 다음 사항이 포함되어 있는지 확인하십시오.

   * 수익 값 0(실제 앱스플라이어 리포트를 왜곡하지 않기 위해 필요).
   * 구입한 제품의 수익 가치를 포함하는 `af_sandbox_revenue` 매개 변수로, 올바른 수익을 보고할 수 있습니다.
   * `af_validated` 매개 변수는 `true`입니다. `af_validated`가 `false`인 경우 - 위의 단계 2로 돌아가서 상점에서 제공한 키를 검증하십시오.
   * `af_validation_type` 매개 변수는 `receipt_validation`입니다.

</Accordion>

<div id="step-4-verify-and-update-settings" />

## 4단계: 설정 확인 및 업데이트

위의 설정 구성을 완료하고 위의 단계를 저장한 후 활성 구성 보기로 리디렉션됩니다. 여기에서 다음 설정을 확인하거나 업데이트할 수 있습니다.

1. **제품 유형**이 **전지 확인**인지 확인합니다.
2. **App Store에서 구매 확인**이 켜져 있는지 확인하십시오.
3. 다음 설정을 확인하거나 업데이트합니다.

   * **App Store 키** 설정
   * **SDK 통합** 설정

<div id="step-5-release-the-app-versions-with-the-validateandlog-sdk-api" />

## 5단계: validateAndLog SDK API를 사용하여 앱 버전을 출시합니다.

이전 단계의 모든 것을 구성하고 AppsFlyer validateAndLog SDK API가 앱에 통합되면, 개발자에게 validateAndLog SDK API가 통합되어 앱 버전을 출시하도록 알려줍니다.

개발자가 새로운 앱 버전을 출시하기 전에 다음을 확인하십시오.

* IAP 또는 구독으로 캡처하려는 인앱이벤트는 앱스플라이어에서 구성한 유효성 검사 규칙 중 하나에 의해 차단되지 않습니다.
* 개발자는 모든 샌드박스 플래그를 `false`로 설정했습니다.

[<Image alt="" src="https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png" width="512px" />](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

validateAndLog SDK API가 포함된 앱이 출시되면 모든 AppsFlyer 대시보드 및 집계 및 원자 데이터 보고서에서 <Anchor target="_blank" href="/marketers/ko/docs/about-receipt-validation#영수증-검증을-위한-인앱-구매-이벤트-및-매개변수">APP 내 구매 및 구독 이벤트</Anchor> 가 생성되고 사용할 수 있습니다.

이벤트는 validateAndLog SDK API가 포함된 앱 버전으로 업데이트한 사용자에게만 생성됩니다. 따라서 업데이트된 앱 버전이 완전히 적용될 때까지 앱의 수익 데이터와 스토어 데이터 간에 차이가 발생할 것으로 예상됩니다.

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01KD0RY1HMV71TGDZZX7JWM3XJ=%EA%B0%9C%EC%9A%94 h_01KD0RY1HMMSR4ZDW5GF4N05P1=%EC%B0%B8%EA%B3%A0 step-1-ios-set-up-app-store-connect-keys=%EB%8B%A8%EA%B3%84-1-ios-app-store-connect-%ED%82%A4-%EC%84%A4%EC%A0%95 h_01KD0RY1HM14KNGKADCBMHJXH6=%EB%8B%A8%EA%B3%84-1-ios-app-store-connect-%ED%82%A4-%EC%84%A4%EC%A0%95 h_01KD0RY1HM08AS4RGNR1QE598K=11-create-the-app-store-connect-keys h_01KD0RY1HMPJGGHQ19D5K70JSZ=12-set-the-app-store-connect-key step-1-android-set-up-service-account-key-and-permissions=%EB%8B%A8%EA%B3%84-1-android-%EC%84%9C%EB%B9%84%EC%8A%A4-%EA%B3%84%EC%A0%95-%ED%82%A4-%EB%B0%8F-%EA%B6%8C%ED%95%9C h_01KD0RY1HMG9DGKGEY8XVR3K7Z=%EB%8B%A8%EA%B3%84-1-android-%EC%84%9C%EB%B9%84%EC%8A%A4-%EA%B3%84%EC%A0%95-%ED%82%A4-%EB%B0%8F-%EA%B6%8C%ED%95%9C h_01KD0RY1HMRK0B1Z4FKD0DD2KQ=11-link-your-google-play-developer-account-to-your-google-cloud-project h_01KD0RY1HN9ER2FZ7XN93SGEN9=12-configure-your-service-account-in-the-google-cloud-platform h_01KD0RY1HN03Y7T4KCNYX9FWS0=13-set-api-access-permissions-in-google-play-console h_01KD0RY1HNS6EPAKZ4YY3MZZK9=14-upload-the-service-account-private-key-to-appsflyer step-2-implement-sdk=2%EB%8B%A8%EA%B3%84-2-sdk-v6%EC%9D%84-%EA%B5%AC%ED%98%84%ED%95%A9%EB%8B%88%EB%8B%A4 h_01KD0RY1HN63X3WM1RH19W2HZ5=2%EB%8B%A8%EA%B3%84-2-sdk-v6%EC%9D%84-%EA%B5%AC%ED%98%84%ED%95%A9%EB%8B%88%EB%8B%A4 step-3-verify-sdk-implementation=3%EB%8B%A8%EA%B3%84-sdk-%EA%B5%AC%ED%98%84-%ED%99%95%EC%9D%B8 h_01KD0RY1HNDMSWGDW6ZQDZ5DAM=3%EB%8B%A8%EA%B3%84-sdk-%EA%B5%AC%ED%98%84-%ED%99%95%EC%9D%B8 h_01KD0RY1HNC4VXSRFC1ZMKWWS6=test-sdk-implementation h_01KD0RY1HNDFF6J29AHG6S4EFM=sandbox-environment-considerations h_01KD0RY1HN5EBX3VGMH5PNHTA8=test-inapp-purchase-and-subscription-revenue step-4-verify-and-update-settings=4%EB%8B%A8%EA%B3%84-%EC%84%A4%EC%A0%95-%ED%99%95%EC%9D%B8-%EB%B0%8F-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8 h_01KD0RY1HN2HZEW9ANBPNRMXPP=4%EB%8B%A8%EA%B3%84-%EC%84%A4%EC%A0%95-%ED%99%95%EC%9D%B8-%EB%B0%8F-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8 step-5-release-the-app-versions-with-the-validateandlog-sdk-api=5%EB%8B%A8%EA%B3%84-validateandlog-sdk-api%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-%EC%95%B1-%EB%B2%84%EC%A0%84%EC%9D%84-%EC%B6%9C%EC%8B%9C%ED%95%A9%EB%8B%88%EB%8B%A4 h_01KD0RY1HNECTDNNHK78F9KDPS=5%EB%8B%A8%EA%B3%84-validateandlog-sdk-api%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-%EC%95%B1-%EB%B2%84%EC%A0%84%EC%9D%84-%EC%B6%9C%EC%8B%9C%ED%95%A9%EB%8B%88%EB%8B%A4" />
