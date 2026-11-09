---
title: ROI360 스토어 수익 설정
metadata:
  keywords:
    - Premium
    - Advertisters
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-22T11:05:11Z'
  edited_at: '2026-10-14T10:27:55Z'
  id: 42158608158353
  locale: ko
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/ko/articles/42158608158353
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** AppsFlyer ROI360 스토어 수익 솔루션을 설정합니다.

<div id="overview" />

## 개요

<div id="note" />

> 📘 **참고**
>
> ROI360에 대한 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/about-roi360-store-revenue">ROI360 스토어 수익에 대한 정보</Anchor>를 참조하십시오. 어떻게 작동하는지 및 AppsFlyer에서 활성화하는 방법을 포함합니다.

ROI360 스토어 수익을 설정하려면 다음 단계를 순서대로 완료하십시오:

1. 스토어 자격 증명 설정 (iOS 및 Android):
   * [iOS:](#1단계-ios-app-store-connect-키-설정) AppsFlyer에서 App Store Connect 키(인앱 구매 키, 키 ID 및 발급자 ID)를 구성합니다.
   * [Android](#1단계-안드로이드-서비스-계정-키-및-권한): Google Cloud 서비스 계정을 구성하고 Google Play Console에서 필요한 권한을 설정한 후, 서비스 계정 JSON 키를 AppsFlyer에 업로드합니다.
2. 서버 알림 구성 (iOS 및 Android):
   * [iOS](#2단계-ios-앱-스토어-서버-알림-활성화): AppsFlyer에 직접 알림을 보내거나(권장) 자신의 엔드포인트에서 전달하여 App Store 서버 알림을 설정하고 통합을 검증합니다.
   * [Android](#단계-2-안드로이드-구글-플레이-서버-알림): Google Play 실시간 개발자 알림(RTDN)을 설정합니다. Google Play가 AppsFlyer에 직접 알림을 보내도록 허용하거나(권장) Pub/Sub를 통해 전달합니다.
3. [SDK 커넥터 구현](#3단계-sdk-커넥터-구현): 개발자가 AppsFlyer 구매 SDK 커넥터를 통합할 수 있도록 준비합니다.
4. SDK 구현 확인 두 플랫폼에서 샌드박스 인앱 구매 및 구독을 테스트하여 SDK 이벤트와 서버 알림이 AppsFlyer에 의해 올바르게 수신되고 처리되는지 확인합니다.
5. [설정 확인 및 업데이트](#5단계-설정을-확인하고-업데이트하십시오): 구매 검증, 환불 처리, 구독 측정 및 스토어 통합의 상태를 검토하고 확인하여 플랫폼 간 정확하고 지속적인 수익 귀속을 보장합니다.
6. [앱 버전 출시](#5단계-sdk-커넥터를-사용한-앱-버전-출시): SDK 커넥터가 통합된 업데이트된 앱 버전을 출시하고, 샌드박스 플래그가 비활성화되고 검증 규칙이 필요한 수익 이벤트를 허용하는지 확인합니다.

<div id="step-1-ios-set-up-app-store-connect-keys" />

## 1단계 (iOS): App Store Connect 키 설정

1단계에서 App Store Connect에서 다음 자격 증명을 얻고 AppsFlyer 플랫폼의 수익 설정 페이지에 입력합니다.

* 인앱 구매 (IAP)
* 키 ID
* *발급자 ID

**시작하기 전에**:

자격 증명을 설정하는 것은 App Store Connect와 AppsFlyer 모두에서 수행되는 단계가 포함됩니다. 설정하는 동안 App Store Connect와 AppsFlyer 탭을 모두 열어 두십시오.

<div id="11-create-the-app-store-connect-keys" />

<Accordion title="1.1 App Store Connect 키 생성하기">

iOS 자격 증명을 설정하려면, 다음 단계를 따르십시오:

1. App Store Connect에서 **사용자 및 접근 권한**으로 이동하십시오.

   <Image align="center" alt="" src="https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png" />
2. **사용자 및 접근 권한**으로 가서 **통합**을 선택한 후, **키** 목록에서 **인앱 구매**를 선택하십시오.

   <Image align="center" alt="" src="https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png" />
3. 새 인앱 구매 키를 생성하려면 +을 클릭하십시오.

   <Image align="center" alt="" src="https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png" />
4. API 키의 이름을 입력하십시오.
5. **생성**을 클릭합니다.
6. 방금 생성한 키 옆에 있는 **인앱 구매 키 다운로드**을 클릭하여 다운로드하십시오. **참고**: 키는 한 번만 다운로드할 수 있습니다.
7. 방금 생성한 키의 **키 ID**를 복사하여 AppsFlyer의 구매 및 구독 설정의 **키 ID**에 붙여넣으십시오.

   <Image align="center" alt="" src="https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png" />
8. **발급자 ID**를 복사하십시오. **참고**: 페이지 상단에 **발급자 ID**가 표시되지 않으면, App Store Connect API 키를 생성하십시오(접근 수준은 상관없습니다). 그 후, 인앱 구매 키의 페이지 상단에 발급자 ID가 나타납니다.

   <Image align="center" alt="" src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw" />

</Accordion>

<div id="12-set-the-app-store-connect-key-in-appsflyer" />

<Accordion title="1.2 AppsFlyer에 App Store Connect 키 설정하기">

1. <Anchor target="_blank" href="/marketers/ko/docs/about-roi360-store-revenue#roi360-스토어-수익-활성화">ROI360 스토어 수익 활성화</Anchor>하십시오.
2. **App Store Connect 키** 단계에서 [<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png) **업로드**를 클릭하여 **인앱 구매 키** 필드에 p8 파일을 업로드하십시오.
3. **App Store Connect 키** 제목의 섹션에서 App Store Connect에서 복사한 값을 붙여넣으십시오.

   * **키 ID**

   * *발급자 ID
4. 입력한 키가 올바른지 확인하려면 **키 검증**을 클릭하십시오. **참고: 앱이 아직 App Store에 게시되지 않은 경우 검증 키**가 작동하지 않을 수 있습니다.
5. 클릭 **저장 및 다음**

</Accordion>

<div id="step-1-android-set-up-service-account-key-and-permissions" />

## 1단계 (안드로이드): 서비스 계정 키 및 권한

1단계에서 App Store Connect에서 다음 자격 증명을 얻고 이를 AppsFlyer 플랫폼의 수익 설정 페이지에 입력할 수 있습니다.

**시작하기 전에**:

* 인앱 구매 및 구독 수익 측정을 설정하는 것은 <Anchor target="_blank" href="https://cloud.google.com/">구글 클라우드 플랫폼</Anchor>, <Anchor target="_blank" href="https://play.google.com/console/">구글 플레이 콘솔</Anchor>, 및 <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">AppsFlyer UI</Anchor>에서 수행되는 단계가 포함됩니다. 설정하는 동안 세 곳 모두를 열어 두는 것을 권장합니다.
* 앱스플라이어 UI를 설정하려면 관리자 권한이 필요합니다.

<div id="11-link-your-google-play-developer-account-to-your-google-cloud-project" />

<Accordion title="1.1. 1.1 Google Play 개발자 계정을 Google Cloud 프로젝트에 연결">

**선행 조건**: 구글 플레이 콘솔 및 구글 클라우드 프로젝트에 대한 접근 권한.

**구글 플레이 개발자 계정을 구글 클라우드 프로젝트에 연결하려면 다음 단계를 따르세요**:

1. Google Play 콘솔에서 Google Play 개발자 계정으로 이동합니다.
2. 계정을 Google Cloud 프로젝트에 연결합니다. 이에 대한 시침은 이 <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#linking">Google 도움말 항목</Anchor>을 참조하십시오.
3. Google Play Developer API를 활성화합니다. 이에 대한 시침은 이 <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#enable">Google 도움말 항목</Anchor>을 참조하십시오.

   <Image align="center" alt="" src="https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png" />

</Accordion>

<div id="12-configure-your-service-account-in-the-google-cloud-platform" />

<Accordion title="1.2. 구글 클라우드 플랫폼에서 서비스 계정을 구성하세요.">

**선행 조건**: 구글 클라우드 플랫폼에 대한 접근 권한.

**서비스 계정을 구성하려면 다음 단계를 따르세요**:

1. **서비스 계정**을 생성하거나 찾으세요:
   1. <span class="af-ol-a"></span>구글 클라우드 플랫폼의 **서비스 계정** 섹션으로 가서 **서비스 계정 만들기**를 클릭하세요.

      <Image align="center" alt="" src="https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png" />
   2. 서비스 계정 세부 정보를 입력하세요.

      <Image align="center" alt="" src="https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png" />
   3. 이메일 주소를 복사하세요.

      <Image align="center" alt="" src="https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png" />
   4. **생성 및 계속하기**를 클릭합니다.

      <Image align="center" alt="" src="https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png" />
   5. **이 서비스 계정에 프로젝트에 대한 액세스 권한 부여** 단계에서  **Pub/Sub 구독자** 역할을 선택합니다.

      <Image align="center" alt="" src="https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png" />
   6. **계속하기** > **완료**를 클릭합니다.

      <Image align="center" alt="" src="https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png" />
2. **서비스 계정 개인 키**를 다운로드하세요:
   1. <span class="af-ol-a"></span>구글 클라우드 플랫폼에서 **서비스 계정** 섹션으로 가서 목록에서 원하는 계정(방금 생성한 계정)을 찾아 **추가 작업** 아이콘을 클릭하세요.
   2. **키 관리**를 클릭하세요.

      <Image align="center" alt="" src="https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png" />
   3. **키 추가** > **새 키 만들기**를 클릭하세요.

      <Image align="center" alt="" src="https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png" />
   4. **개인 키 만들기** 팝업에서 **키 유형** 아래에 **JSON**을 선택하고 **만들기**를 클릭하세요.

      <Image align="center" alt="" src="https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png" />
   5. **생성**을 클릭합니다. 개인 키 JSON 파일이 다운로드됩니다.

      <Image align="center" alt="" src="https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png" />
   6. JSON 키 파일을 저장하세요. 이 파일은 나중에 AppsFlyer에 업로드됩니다. **참고**! 키를 저장해야 합니다. 나중에 복구할 수 없습니다. 저장하지 않으면 완전히 새로운 키를 만들어야 합니다.

</Accordion>

<div id="13-set-api-access-permissions-in-google-play-console" />

<Accordion title="1.3. Google Play Console에서 API 접근 권한을 설정하십시오.">

**선행 조건**: Google Play Console에 접근합니다.

**참고**: 참고: 서비스 계정 사용자 인증 정보 및 권한을 설정한 후 사용가능할 때까지 시간이 걸릴 수 있습니다(경우에 따라 24시간까지). 이로 인해 이후 단계에서 오류가 발생할 수 있습니다.

**Google Play Console에서 API 접근 권한을 설정하려면**:

1. Google Play Console에서 **사용자 및 권한**으로 이동하여 생성한 서비스 계정을 찾고 **새 사용자 초대**를 클릭하십시오.

   <Image align="center" alt="" src="https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png" />
2. 1.2.1.3단계에서 서비스 계정을 구성할 때 복사한 **이메일 주소**을 입력하십시오.

   <Image align="center" alt="" src="https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png" />
3. **권한** 섹션에서 **계정 권한** 탭으로 이동하여 다음 두 가지를 모두 선택합니다.

   * 재무 데이터, 주문 및 취소 설문 응답을 확인하십시오.
   * 주문 및 구독 관리.[![](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)
4. **앱 권한** 탭에서 **앱 추가**를 클릭한 다음 귀하의 앱을 선택하십시오. 필요한 경우 여러 앱을 추가하십시오.

   <Image align="center" alt="" src="https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png" />
5. **사용자 초대**를 클릭하십시오.

   <Image align="center" alt="" src="https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png" />
6. 확인 팝업에서 **초대 전송**을 클릭하십시오.

   <Image align="center" alt="" src="https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png" />

</Accordion>

<div id="14-upload-the-service-account-private-key-to-appsflyer" />

<Accordion title="1.4. 서비스 계정 개인 키를 AppsFlyer에 업로드하십시오.">

[1.2단계](#12-configure-your-service-account-in-the-google-cloud-platform)에서 다운로드한 Google JSON 키를 업로드하고 검증하십시오.

**선행 조건**: AppsFlyer에 대한 관리자 접근 권한.

**서비스 계정 개인 키를 AppsFlyer에 업로드하려면 다음 단계를 따르십시오**:

1. <Anchor target="_blank" href="/marketers/ko/docs/about-roi360-store-revenue#roi360-스토어-수익-활성화">ROI360 스토어 수익 활성화</Anchor>하십시오.
2. **서비스 계정 키 및 권한** 단계에서 **Google JSON 키 업로드** 필드에 [<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.2%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png) **(업로드 아이콘).** 을 클릭하십시오.
3. [1.2단계](#12-configure-your-service-account-in-the-google-cloud-platform)에서 다운로드한 JSON 파일을 업로드하십시오.
4. **키 검증** **참고:**
   * 서비스 계정 자격 증명 및 권한을 설정한 후, 이를 사용할 수 있게 되기까지 최대 24시간이 소요될 수 있습니다. 이로 인해 키를 검증하거나 검증 테스트를 수행할 때 오류가 발생할 수 있습니다.
   * 24시간 대기 시간을 우회하기 위해 Google Play Console에서 임의의 애플리케이션으로 이동한 후, **수익화** > **제품** > **구독/인앱 제품**으로 가서 변경을 합니다. 예를 들어, 제품의 설명을 수정하고 저장합니다. 이렇게 하면 계정 자격 증명 및 권한이 즉시 업데이트됩니다. 그런 다음 변경 사항을 취소할 수 있습니다.
5. **저장 및 다음**을 클릭합니다.

</Accordion>

<div id="note-1" />

<div id="option-2---your-endpoint-as-the-primary-endpoint" />

<div id="option-1-recommended---appsflyer-as-the-primary-endpoint" />

<div id="step-2-ios-set-up-app-store-server-notifications" />

## 2단계 (iOS): 앱 스토어 서버 알림 활성화

AppsFlyer에서 App Store 알림 수신 방법을 설정합니다.

* App Store Connect에 App Store 서버 알림 엔드포인트가 이미 구성되어 있는 경우(예: 자체 백엔드 또는 다른 서비스), **옵션 1 (권장)** 또는 **옵션 2** 중에서 선택합니다.
* 아직 App Store Connect에 엔드포인트를 구성하지 않은 경우 **옵션 1**을 선택합니다.

**옵션 1 (권장) - AppsFlyer를 기본 엔드포인트로 설정**

기존 App Store Connect 알림 URL을 AppsFlyer 엔드포인트로 교체하고, AppsFlyer에서 이전 엔드포인트를 전달 목적지로 추가합니다. 현재의 구독 논리와 워크플로우는 변경되지 않으며 예상대로 계속 작동합니다.

이 옵션의 알림 흐름은 다음과 같습니다:

1. App Store Connect가 AppsFlyer에 알림을 보냅니다.
2. AppsFlyer가 ROI360을 위해 이를 처리합니다.
3. AppsFlyer가 모든 알림을 기존 엔드포인트 **실시간으로** 전달합니다.

이 옵션을 사용하려면 [2.1](#21-copy-the-appsflyer-server-notifications-endpoint), [2.2](#22-send-notifications-directly-to-appsflyer), 및 [2.4](#24-test-the-server-notifications-integration) 단계를 완료합니다.

**옵션 2 - 귀하의 엔드포인트를 기본 엔드포인트로 설정**

기존 엔드포인트를 기본 목적지로 유지하려면 서버를 구성하여 App Store 서버 알림을 AppsFlyer로 전달하십시오.

이 옵션을 사용하려면 2.1단계와 2.2단계를 건너뛰고 [2.3](#23--optional--forward-notifications-from-your-endpoint-to-appsflyer)단계와 [2.4](#24-test-the-server-notifications-integration)단계를 완료하십시오.

<div id="21-copy-the-appsflyer-server-notifications-endpoint" />

<Accordion title="앱스플라이어 서버 알림 엔드포인트">

AppsFlyer 서버 알림 엔드포인트를 복사하려면 다음 단계를 따르십시오:

1. **AppsFlyer에서** 의  **App Store 서버 알림** 단계에서 AppsFlyer 서버 알림 엔드포인트를 복사하십시오.
2. 이전에 다른 App Store 서버 알림 엔드포인트가 있었고 AppsFlyer가 알림을 해당 엔드포인트로 전달하기를 원한다면 **알림을 귀하의 서버로 전달하기 (옵션 1에만 해당).** 를 선택하십시오.
3. 표시된 텍스트 상자에 알림 전달 엔드포인트를 입력하십시오.

</Accordion>

<div id="22-send-notifications-directly-to-appsflyer" />

<Accordion title="2.2 알림을 AppsFlyer로 직접 전송하십시오.">

알림을 AppsFlyer로 직접 전송하려면 AppsFlyer를 기본 App Store 서버 알림 엔드포인트로 설정하십시오.

1. **App Store Connect**의 **앱 정보** 섹션에서 **App Store 서버 알림**으로 스크롤하고, **생산 서버 URL** 옆에 있는 **편집**을 클릭하십시오.

   <Image align="center" alt="" src="https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png" />
2. [AppsFlyer에서 복사한 AppsFlyer 서버 알림 엔드포인트](#21-copy-the-appsflyer-server-notifications-endpoint)를 붙여넣고, **버전 2 알림**을 선택한 후 **저장**을 클릭하십시오. **참고:** 버전 1 알림은 더 이상 지원되지 않습니다. 알림 버전 선택기가 Apple Store Connect에 나타나지 않으면 이미 버전 2를 사용하고 있다는 의미입니다.

   <Image align="center" alt="" src="https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png" />
3. **앱 정보** 섹션에서 **App Store 서버 알림**으로 스크롤하고, **샌드박스 서버 URL** 옆에 있는 **편집**을 클릭하십시오.

   <Image align="center" alt="" src="https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png" />
4. [AppsFlyer에서 복사한 AppsFlyer 서버 알림 엔드포인트](#21-copy-the-appsflyer-server-notifications-endpoint)를 붙여넣고, **버전 2 알림**을 선택한 후 **저장**을 클릭하십시오. **참고:** 버전 1 알림은 더 이상 지원되지 않습니다. 알림 버전 선택기가 Apple Store Connect에 나타나지 않으면 이미 버전 2를 사용하고 있다는 의미입니다.

   <Image align="center" alt="" src="https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png" />

</Accordion>

<div id="23--optional--forward-notifications-from-your-endpoint-to-appsflyer" />

<Accordion title="2.3 [선택 사항] 귀하의 엔드포인트에서 AppsFlyer로 알림을 전달하십시오.">

이 단계는 AppsFlyer로 알림을 직접 전송하는 대신 귀하의 엔드포인트를 App Store 서버 알림의 기본 목적지로 유지하려는 경우에만 사용하십시오.

이 옵션은 권장 설정이 아니며 백엔드 구현이 필요합니다. 위의 **2.2** 단계에서 이미 AppsFlyer를 기본 엔드포인트로 구성한 경우 이 단계를 건너뛰십시오.

귀하의 엔드포인트에서 AppsFlyer로 서버 알림을 전달하려면 다음 단계를 따르십시오:

1. **App Store Connect**의 **앱 정보** 섹션에서 **App Store 서버 알림**으로 스크롤하고, **생산 서버 URL** 옆에 있는 **편집**을 클릭하십시오.

   <Image align="center" alt="" src="https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png" />
2. **귀하의 서버 엔드포인트 URL**을 붙여넣으십시오.

   <Image align="center" alt="" src="https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png" />
3. **버전 2 알림을 선택하십시오. 참고:** 버전 1 알림은 더 이상 지원되지 않습니다. 알림 버전 선택기가 Apple Store Connect에 나타나지 않으면 이미 버전 2를 사용하고 있다는 의미입니다.
4. **저장**을 클릭하세요.
5. **앱 스토어 연결**의 **앱 정보** 섹션에서 **앱 스토어 서버 알림**으로 스크롤한 다음, **샌드박스 서버 URL** 옆에 있는 **편집**을 클릭하십시오.

   <Image align="center" alt="" src="https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png" />
6. **귀하의 서버 엔드포인트 URL**을 붙여넣으십시오.

   <Image align="center" alt="" src="https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png" />
7. **버전 2 알림을 선택하십시오. 참고:** 버전 1 알림은 더 이상 지원되지 않습니다.
8. **저장**을 클릭하세요.
9. 백엔드를 구성하여 Apple 서버 알림을 AppsFlyer 알림 엔드포인트 URL로 전달하십시오. 요청은 Apple로부터 수신한 앱 스토어 페이로드와 정확히 일치해야 하며, <Anchor target="_blank" href="https://developer.apple.com/documentation/appstoreserverapi/signedpayload#discussion">Apple 형식 요구 사항</Anchor>을 참조하십시오.

</Accordion>

<div id="24-test-the-server-notifications-integration" />

<Accordion title="2.4 서버 알림 통합 테스트">

AppsFlyer가 앱 스토어 서버 알림을 올바르게 수신하고 있는지 확인하거나, 최근에 엔드포인트를 구성했지만 아직 서버 알림이 도착하지 않은 경우:

1. AppsFlyer에서 **앱 스토어 서버 알림** 단계로 이동하십시오.
2. **통합 테스트**을 클릭하십시오. AppsFlyer는 Apple에 테스트 알림 요청을 보내고, 지난 7일 동안 Apple로부터 유효한 알림이 수신되었는지 확인하며, 다음 중 하나를 표시합니다:

   * 유효한 알림이 수신되었는지에 대한 확인입니다.
   * 알림이 발견되지 않았다는 상태 메시지입니다.

   <div id="note-2" />

   > 📘 **참고**
   >
   > Apple이 테스트 메시지를 보내는 데 몇 초가 걸릴 수 있습니다.


   * 상태가 여전히 유효하지 않으면 잠시 기다렸다가 다시 시도하십시오.
   * 테스트가 성공한 후, 또는 계속할 준비가 되었을 때 **저장 및 다음**을 클릭하십시오.

</Accordion>

<div id="step-2-android-set-up-google-play-server-notifications" />

## 단계 2 (안드로이드): 구글 플레이 서버 알림

Google Play에서 인앱 구매 및 구독 수익 데이터를 수신하려면 다음 옵션 중에서 선택하십시오:

* (권장) Google Play가 알림을 AppsFlyer에 직접 보냅니다. 이 옵션을 선택하면 알림 복사본을 귀하의 엔드포인트로 전달할 수 없습니다. 이 옵션을 선택하고 싶다면 [Google Play 알림을 AppsFlyer에 직접 보내기](#21-send-google-play-notifications-directly-to-appsflyer)를 확인할 수 있습니다.
* Google Play가 먼저 알림을 귀하에게 보내고, 그 후에 AppsFlyer로 전달됩니다. 이 옵션을 선택하면 [Google Play 알림을 AppsFlyer로 전달합니다.](#22--optional--forward-google-play-notifications-to-appsflyer)

**선행 조건**: Google Play Console 및 AppsFlyer UI에 대한 접근 권한입니다.

<div id="21-send-google-play-notifications-directly-to-appsflyer" />

<Accordion title="둘 중 하나 1.5 앱스플라이어에 직접 Google Play 알림 전송">

1. AppsFlyer에서 2단계 **, Google Play 서버 알림 설정**에서 **AppsFlyer 주제가 Google으로부터 RTDN 메시지를 직접 받을 수 있도록 허용**을 선택합니다.
2. 앱스플라이어 주제를 클립보드에 복사합니다.
3. **Google Play Console** > **홈**에서 귀하의 앱을 보려면 선택하십시오. 대시보드가 열립니다.

   <Image align="center" alt="" src="https://files.readme.io/1fdd2632aaf3a412987aa5dae5ad5a7350836f1ad4cd2f1c228b4cc96acdb9ff-42158608097297.png" />
4. **Play로 수익화** > **수익화 설정**으로 이동하고, **Google Play 청구** 섹션에서 **실시간 알림 활성화**가 체크되어 있는지 확인하십시오.

   <Image align="center" alt="" src="https://files.readme.io/f133ffefac1ec4b4eb9225c498f475163a69d1fd1f61b3d1c7cee7a71c42fea4-42158637562769.png" />
5. **주제 이름** 필드에 복사한 AppsFlyer 주제 주소를 붙여넣습니다.

   <Image align="center" alt="" src="https://files.readme.io/b6ac3a569210b026096b5592a575500b1bdb03376ec0641f4ceeaf9402ea4549-42158608104081.png" />
6. **알림 내용**에 대해 **구독, 무효화된 구매 및 모든 일회성 제품**을 선택합니다.

   <Image align="center" alt="" src="https://files.readme.io/8aa48cebc2f0712204d5d5c2e45727879814aaae2d03732228e0f8e607fccdc9-42158608105233.png" />
7. **변경 사항 저장**을 클릭합니다. 이 효과가 나타나기까지 시간이 걸릴 수 있습니다(때로는 24시간까지도). 따라서 테스트하기 전에 기다리십시오.

</Accordion>

<div id="22--optional--forward-google-play-notifications-to-appsflyer" />

<Accordion title="또는 1.6 Google Play 알림을 앱스플라이어에 전달">

**참고**: 이 단계는 Google Play에서 AppsFlyer로 직접 알림을 보내어 인앱 구매 및 구독 수익 데이터를 받는 권장 방법을 선택하지 않은 경우에만 해당됩니다. Google Play에서 AppsFlyer가 RTDN 알림을 직접 받는 주제를 생성하기 위한 권장 방법의 단계를 완료했다면 이 단계를 건너뛰십시오.

기존 PUB/SUB 주제에 AppsFlyer를 구독자로 설정하려면 아래 지침을 계속 진행하십시오.

**선행 조건**: Google Cloud Platform 및 AppsFlyer UI에 대한 접근 권한입니다.

**또는** 1.6 Google Play 알림을 앱스플라이어에 전달

1. AppsFlyer에서 사이드 메뉴에서 **설정** > **수익 설정**으로 이동합니다.
2. 앱을 선택합니다.
3. **구매 및 구독** 탭에서 **RTDN 주제 메시지를 AppsFlyer로 전달**을 선택합니다.
4. 엔드포인트 URL을 클립보드에 복사합니다.
5. Google Cloud 플랫폼에 있는 사용자 프로젝트에서 **Pub/Sub**를 검색합니다.

   <Image align="center" alt="" src="https://files.readme.io/fc99b942cec1dc7c1442b6d85142be12011a0b91ab40110e6d454b8b12faa5cb-42158637570705.png" />
6. **Pub/Sub** 에서 **주제** 섹션으로 이동하여 구독하려는 Pub/Sub 주제가 있는지 확인합니다.

   <Image align="center" alt="" src="https://files.readme.io/6ae2654906ba62cac901b0d8a0b54d86ea92690e947621a578b93fc7225f550e-42158608108689.png" />
7. **구독** 섹션으로 이동하여 **구독 생성**을 클릭합니다.

   <Image align="center" alt="" src="https://files.readme.io/d89659f6789cc4fd3c1888742583dc6e0aa2c8ad15229d11a8618251152864f4-42158637572369.png" />
8. 구독 ID를 입력합니다.

   <Image align="center" alt="" src="https://files.readme.io/1d4e42829a45c30253f68a164780185eb1b5723605870b7cc14450c80689f7bc-42158637574673.png" />
9. 드롭다운에서 관련 구독 pub/sub 주제를 선택합니다.

   <Image align="center" alt="" src="https://files.readme.io/b2a3f816734039821830cd6f2bf8047cb1927a27e232f1caf5757310815ee0b3-42158637581329.png" />
10. **전달 유형**에서 **푸시**를 선택합니다.

    <Image align="center" alt="" src="https://files.readme.io/cb716ee0392cf71b20e3aac9af4c050e9495a0e5c384594eb1af3d3fb5da454c-42158637584657.png" />
11. AppsFlyer에서 복사한 **엔드포인트 URL**을 붙여넣습니다.

    <Image align="center" alt="" src="https://files.readme.io/11610d67b24ea1b5afb6560c30352ec3e0bbfc5b8ebb2bf27545d838f7c999aa-42158637585681.png" />
12. **만료 기간** 아래에서 **절대 만료되지 않음**을 선택합니다.

    <Image align="center" alt="" src="https://files.readme.io/ab7d994b97137d39f77ffb11d772b37dc9033550bdb7ba95d3c9c2ff748cb54a-42158608120209.png" />
13. **생성**을 클릭합니다.

    <Image align="center" alt="" src="https://files.readme.io/bf8aed929c5f35847dda934677fc333ef111dc1f1281494582f1da4b776499c8-42158637592721.png" />
14. **구독** 섹션으로 이동하여 원하는 주제 이름을 클릭합니다.

    <Image align="center" alt="" src="https://files.readme.io/4b5f7b0c369fc4abddfbec35887a62221a55d838672872091b634343691dd9b8-42158608126993.png" />
15. 주제 이름을 클립보드에 복사합니다.

    <Image align="center" alt="" src="https://files.readme.io/3ec5abc49588477d0567a26a3f6734f5e9c0ab0f677cfee0cf4d413aab0fcc5d-42158608127505.png" />
16. **Google Play 콘솔**에서 **수익화 설정**으로 이동하여 **Google Play 청구 섹선**의 **주제** 이름 필드에 이전 단계에서 복사한 주제 이름을 붙여 넣습니다.

    <Image align="center" alt="" src="https://files.readme.io/d5368f4c9326e5c0a9d0f75167bd12ee1ddb58381379ceefedeaae3917806163-42158608128785.png" />
17. **알림 내용**에 대해 **구독, 무효화된 구매 및 모든 일회성 제품**을 선택합니다.

    <Image align="center" alt="" src="https://files.readme.io/6c1b473ee54c1db69e7359d99a86efee359113ed76d52d2cd2dfe05557f7ee91-42158637598737.png" />
18. **변경 사항 저장(Save changes)** 을 클릭합니다. 이 효과가 나타나기까지 시간이 걸릴 수 있습니다(때로는 24시간까지도). 따라서 테스트하기 전에 기다리십시오.

</Accordion>

<div id="23-send-a-test-notification-from-google-play-console" />

<Accordion title="2.3 Google Play Console에서 테스트 알림을 보냅니다.">

Google Play 실시간 개발자 알림(RTDN)이 AppsFlyer에 올바르게 수신되는지 확인하려면 Google Play Console에서 테스트 알림을 보내십시오:

1. **테스트 알림 보내기**를 클릭하십시오. 이것은 AppsFlyer에 구성된 Pub/Sub 주제로 테스트 RTDN 메시지를 전송합니다.

   <Image align="center" alt="image (16).png" src="https://files.readme.io/4d7aa79eb963373223cfde1d32db16b739119a86d8d4f0cf6ce026d42a709bf3-42170040528657.png" width="1444px" />
2. **Google Play 결제** 아래에서 주제 이름 섹션을 찾으십시오.
3. 왼쪽 메뉴에서 **Play로 수익 창출** → **수익 창출 설정**로 이동하십시오.
4. Google Play Console로 이동하십시오.

<div id="24-confirm-notification-delivery-in-appsflyer" />

<Accordion title="2.4 AppsFlyer에서 알림 전달 확인">

1. 테스트가 성공하거나 진행할 준비가 되면 **저장 및 다음**을 클릭하십시오.
2. 결과: AppsFlyer는 지난 7일 동안 수신된 알림이 있는지 표시합니다.
   * 성공하면 인터페이스에 가장 최근 알림의 날짜와 시간이 표시됩니다.
   * 수신된 알림이 없으면 인터페이스에 지난 7일 동안 알림이 발견되지 않았다고 표시됩니다.
   * 상태가 나타나지 않으면 Pub/Sub 구성을 검토하고 테스트 알림을 다시 전송하십시오.
3. **Google Play 서버 알림** 단계에서 **통합 테스트**를 클릭하십시오.

</Accordion>

</Accordion>

<div id="step-3-implement-sdk-connector" />

## 3단계: SDK 커넥터 구현

이 단계에서는 개발자가 AppsFlyer 구매 SDK 커넥터를 통합하고 테스트를 위한 샌드박스 환경을 구성하도록 준비시킵니다.

SDK 커넥터를 구현하려면 다음 단계를 따르십시오:

1. **SDK 커넥터 구현** 단계에서 대시보드에 표시된 **미리 작성된 메시지**를 복사하십시오.
2. 이를 개발자에게 전송하십시오. 여기에는 다음이 포함됩니다:
   * 앱 이름 및 앱 ID
   * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">SDK 통합 가이드</Anchor>에 대한 링크.
   * 샌드박스 환경을 구성하는 지침 (`sandbox = true`)
   * 테스트 단계 (사용 중 **TestFlight**)

이 메시지는 개발자가 통합을 완료하고 테스트를 시작하는 데 필요한 모든 정보를 제공합니다.

<div id="note-3" />

> 📘 **참고**
>
> 커넥터는 자동 거래 감지를 사용합니다. 대안으로, 각 거래를 수동으로 기록하기 위해 `validateAndLog` SDK 메서드를 구현할 수 있습니다. 이 방법은 커넥터에서 사용할 수 있는 모든 기능을 지원하지 않습니다. 두 SDK 통합 옵션에 대한 자세한 내용은 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">DevHub 문서</Anchor>를 참조하십시오.

<div id="step-4-verify-sdk-implementation" />

## 4단계: SDK 구현 확인

샌드박스 환경에서 인앱 구매 및 구독 수익 통합을 테스트하여 SDK 커넥터가 올바르게 통합되었는지 확인하고 서버 알림이 적절하게 구성되어 AppsFlyer에 의해 수신되는지 확인하십시오.

<div id="test-sdk-implementation" />

<Accordion title="테스트 SDK 구현">

지난 7일 동안 귀하의 앱에서 AppsFlyer가 유효한 구매 및 구독 이벤트 페이로드를 수신했는지 확인하려면 다음 단계를 수행하십시오:

1. **SDK 구현 확인** 단계에서 **SDK 구현 테스트**를 클릭하십시오.
2. 결과를 검토하고, AppsFlyer가 수신한 가장 최근 페이로드의 타임스탬프를 포함합니다.

   <div id="note-4" />

   > 📘 **참고**
   >
   > 이 테스트는 요청이 AppsFlyer에 도달하고 있음을 확인할 뿐이며 데이터의 완전성이나 정확성을 검증하지 않습니다.

3. 구현을 완전히 검증하려면 아래의 테스트 단계를 계속 진행하십시오.

</Accordion>

<div id="sandbox-events-and-parameters" />

<Accordion title="샌드박스 이벤트 및 매개변수">

* SDK 커넥터는 초기 샌드박스 거래에 대해서만 이벤트를 생성합니다:
  * 인앱 구매
  * 구독
* AppsFlyer는 원래 거래에 대한 SDK 이벤트가 기록된 경우에만 서버 알림을 처리합니다.
  * 인앱 구매 (IAP)
  * 구독 S2S: `af_ars_sandbox_s2s`
* SDK가 원래 거래를 기록하지 않으면 S2S 이벤트가 생성되지 않습니다.

**iOS 고려 사항**

* `af_purchase_sandbox_sdk`이 `af_sandbox_revenue`를 포함하는 경우, 이는 프로덕션 `af_purchase`에 매핑됩니다.
* 수익이 없으면, 생산 `af_purchase_free`에 매핑됩니다.

**안드로이드 고려사항**

* **라이센스 테스터**의 구매는 항상 샌드박스 이벤트를 생성합니다. 샌드박스 모드가 SDK에 구성되어 있지 않더라도 말입니다.

**테스트 이벤트를 위한 필수 매개변수**

모든 샌드박스 구매 이벤트에 다음이 포함되도록 하십시오:

* **수익 = 0** (실제 보고서에 영향을 주지 않도록).
* `af_sandbox_revenue` = 실제 제품 가격 (정확한 수익이 귀속되도록).
* `af_validated` **= true**. `false`가 돌아가서 스토어 키를 확인하십시오.
* `af_validation_type` = `receipt_validation`.

</Accordion>

<div id="test-inapp-purchase-and-subscription-revenue" />

<Accordion title="인앱 구매 및 구독 수익 측정">

**선행 조건**:

* **iOS의 경우, App Store Connect의 앱 스토어 서버 알림에서 앱스플라이어 엔드포인트가** 샌드박스 서버 URL로 구성되어 있는지 확인합니다.

  <Image align="center" alt="" src="https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png" />

인앱 구매 및 구독 수익 측정

1. 개발자에게 <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-apple-purchase-connector#-testing-the-implementation-in-sandbox">Android</Anchor> , iOS  및 Unity 지침에 따라 SDK 커넥터에서 샌드박스 환경을 구성하도록 지시합니다.
2. 테스트 구매를 하거나 <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">구글 플레이의 라이센스 테스터</Anchor>를 사용하여 구독을 시작하십시오. iOS의 경우, <Anchor target="_blank" href="https://developer.apple.com/testflight/">테스트플라이트</Anchor>를 사용하십시오. **참고**: 구독 제품은 장치당 한 번만 테스트할 수 있습니다. 실제로, 장치는 동일한 구독의 여러 테스트 구매를 등록할 수 없습니다. 추가 시도는 기록되지 않습니다.
3. <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">구글 플레이의 라이센스 테스터</Anchor>와 <Anchor target="_blank" href="https://developer.apple.com/testflight/">iOS의 테스트플라이트</Anchor>를 사용하여 테스트 환불, 구독 갱신 또는 구독 취소 이벤트를 만드십시오. **참고**: 구독 제품을 테스트하는 경우, AppsFlyer가 스토어로부터 서버 알림을 수신할 시간을 허용하십시오. 이는 일반적으로 최초 구매 후 몇 분 이내에 발생합니다.
4. **SDK 커넥터 구현 확인** 단계에서 **SDK 구현 테스트.** 를 클릭하십시오. 지난 7일 동안 Purchase Connector로부터 성공적으로 수신된 SDK 페이로드가 있는지를 나타냅니다.
5. 테스트 이벤트가 다음 방법 중 하나로 표시되는지 확인하십시오:

   * 이벤트를 <Anchor target="_blank" href="/marketers/ko/docs/testing-the-sdk-integration-for-marketers#view-live-events">실시간 이벤트 뷰어</Anchor>에서 확인하십시오.

   * 이벤트 데이터를 <Anchor target="_blank" href="/marketers/ko/docs/activity-metrics-in-my-dashboards">내 대시보드 - 활동 보기</Anchor>에서 확인하십시오.
6. 이벤트가 AppsFlyer 활동 대시보드에 나타나는지 확인하십시오. AppsFlyer에서 **분석 > 활동**으로 이동하고, **활동 추세** 차트에서 인앱 이벤트 탭을 열고 테스트할 이벤트를 선택하십시오. 자동 갱신 구독 구매는 `af_ars_s2s_sandbox`이라고 합니다. 이벤트에는 다음이 포함됩니다:
   * 수익 값 0(실제 앱스플라이어 리포트를 왜곡하지 않기 위해 필요).
   * 구매한 제품의 수익 가치를 포함하는 `af_sandbox_revenue` 매개변수로, 올바른 수익이 보고되도록 합니다.

</Accordion>

<div id="step-5-verify-and-update-settings" />

## 5단계: 설정을 확인하고 업데이트하십시오.

위의 설정 구성을 완료하고 마지막 단계를 저장한 후, 활성 구성 보기로 리디렉션되며, 다음 설정을 확인하거나 업데이트할 수 있습니다:

1. **앱 스토어로 구매 확인** 토글이 켜져 있는지 확인하십시오.
2. **구매** 아래의 다음 옵션을 확인하십시오:
   * 깨끗한 데이터를 위해 중복 구매를 방지하십시오. 이미 보고된 거래를 기록하지 않습니다.
   * 환불, 취소 및 부정 수익을 자동으로 측정합니다. 환불 관련 이벤트를 측정하고 이를 부정적인 수익으로 기록합니다.
   * 가족 공유로 인한 수익 중복 계산을 피하십시오. 가족 공유로 인한 중복 수익을 방지합니다. 이 이벤트는 `purchase_ownership_type=FAMILY_SHARED`로 표시되며 수익이 0으로 보고됩니다.
3. **자동 갱신 구독에 대한 수익 측정 및 귀속** 토글이 켜져 있는지 확인하십시오:
4. 다음 설정의 상태:
   * **앱 스토어 키** 설정
   * **서버 알림 엔드포인트** 설정
   * SDK 커넥터 구현 및 테스트

<div id="step-6-release-the-app-versions-with-the-sdk-connector" />

## 5단계: SDK 커넥터를 사용한 앱 버전 출시

이전 단계에서 모든 것이 구성되고 AppsFlyer 구매 SDK 커넥터가 앱에 통합된 상태에서, 개발자에게 SDK 커넥터가 통합된 앱 버전을 출시하도록 지시하십시오.

그러나 개발자가 새로운 앱 버전을 출시하기 전에 다음 사항을 확인하십시오:

* IAP 또는 구독으로 캡처하려는 인앱이벤트는 앱스플라이어에서 구성한 유효성 검사 규칙 중 하나에 의해 차단되지 않습니다.
* 개발자는 거짓으로 표시된 샌드박스 플래그를 가지고 있어야 합니다.

<Image align="center" alt="" src="https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png" />

SDK 커넥터가 포함된 앱이 출시되면, <Anchor target="_blank" href="/marketers/ko/docs/about-roi360-store-revenue#iaprelated-events-and-parameters">앱 내 구매</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/about-roi360-store-revenue#subscriptionrelated-events-and-parameters">구독 이벤트</Anchor>가 생성되어 모든 AppsFlyer 대시보드에서 사용할 수 있으며, <Anchor target="_blank" href="/marketers/ko/docs/revenue-etl-reports">수익 ETL</Anchor>을 포함한 집계 및 원시 데이터 보고서에서도 제공됩니다.

**참고:** 이벤트는 SDK 커넥터가 포함된 앱 버전으로 업데이트한 사용자에게만 생성됩니다. 그 결과, 업데이트된 앱 버전이 완전히 채택될 때까지 앱의 수익 데이터와 스토어 데이터 간에 불일치가 예상됩니다.

<div id="switch-to-roi360-store-revenue-from-receipt-validation" />

## ROI360 스토어 수익으로 전환(영수증 검증에서)

영수증 검증을 위한 온보딩을 완료했지만 ROI360 스토어 수익 제품을 활성화하려면 다음을 수행하십시오:

1. AppsFlyer에서 사이드 메뉴에서 [<Image alt="" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.54%" />](https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png) **설정**을 열고 **ROI360** 아래에서 **수익 설정**을 선택합니다.
2. **구매 및 구독** 탭을 엽니다. ROI360이 사용 가능하지만 활성화되지 않았다는 배너가 나타납니다.
3. **제품 비교 보기**를 클릭하여 환불 귀속, 순수익 보고 및 전체 구독 생애 주기 측정을 포함한 이점을 이해합니다.
4. **ROI360 활성화.** 를 클릭합니다.
5. **앱 스토어 서버 알림 활성화** 단계를 수행합니다. 자세한 내용은 [앱 스토어 서버 알림 설정](#2단계-ios-앱-스토어-서버-알림-활성화) 또는 [구글 플레이 서버 알림 설정](#단계-2-안드로이드-구글-플레이-서버-알림)을 참조하십시오.
6. **구매 및 구독** 섹션에서 **제품 유형**이 이제 **ROI360**으로 설정되었는지 확인합니다.
7. 필요한 ROI360 스토어 수익 기능을 지원할 수 있도록 현재 SDK 설정을 검토하십시오.

<div id="note-5" />

> 📘 **참고**
>
> ROI360 스토어 수익은 두 가지 통합 방법을 지원합니다: 구매 SDK 커넥터 및 검증 및 기록. 두 가지 중에서 **구매 SDK 커넥터**를 사용하는 것이 좋습니다.
>
> * 자동 거래 감지
> * 기존 구독자(통합 이전에 구독한 사용자)로부터의 수익 측정
> * 구독 가격 변경 지원, 가격 업데이트가 발생할 때 정확한 수익 보고를 보장합니다.
>
> 이 기능이 필요하지 않다면, 대신 **검증 및 기록** 통합을 계속 사용할 수 있습니다.
>
> **SDK 통합 방법 확인하기**
>
> 앱이 Purchase SDK 커넥터 또는 검증 및 기록을 사용하는지 확인하려면:
>
> 1. **SDK 커넥터 통합** 단계로 이동하세요.
> 2. **SDK 통합 테스트**를 클릭하세요. 최근 7일 이내에 AppsFlyer가 수신한 최신 SDK 페이로드와 그것이 **Purchase SDK 커넥터** 또는 **검증 및 기록**에서 유래했는지를 확인할 수 있습니다.

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01KD31QE0BCW0BX9BNNDK6DJRA=%EA%B0%9C%EC%9A%94 h_01KD31QE0BQAQ0CS1FJ46TV6K1=%EC%B0%B8%EA%B3%A0 step-1-ios-set-up-app-store-connect-keys=1%EB%8B%A8%EA%B3%84-ios-app-store-connect-%ED%82%A4-%EC%84%A4%EC%A0%95 h_01KD31QE0BE3ST0TV3KQ1M5AB0=1%EB%8B%A8%EA%B3%84-ios-app-store-connect-%ED%82%A4-%EC%84%A4%EC%A0%95 h_01KD31QE0BBYES1C2Y1MB665EF=11-create-the-app-store-connect-keys h_01KD31QE0B4G0NGRYBTS2TRZQR=12-set-the-app-store-connect-key-in-appsflyer step-1-android-set-up-service-account-key-and-permissions=1%EB%8B%A8%EA%B3%84-%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EC%84%9C%EB%B9%84%EC%8A%A4-%EA%B3%84%EC%A0%95-%ED%82%A4-%EB%B0%8F-%EA%B6%8C%ED%95%9C h_01KD31QE0BVQNJZ8PKKYKK9Q79=1%EB%8B%A8%EA%B3%84-%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EC%84%9C%EB%B9%84%EC%8A%A4-%EA%B3%84%EC%A0%95-%ED%82%A4-%EB%B0%8F-%EA%B6%8C%ED%95%9C h_01KD31QE0BP21EHP5RPBZ5PX2N=11-link-your-google-play-developer-account-to-your-google-cloud-project h_01KD31QE0B5G8SDGZQ8NE07QAE=12-configure-your-service-account-in-the-google-cloud-platform h_01KD31QE0CBMGHXJTXT4JPBV70=13-set-api-access-permissions-in-google-play-console h_01KD31QE0CH5M5X9M9G68N2PPZ=14-upload-the-service-account-private-key-to-appsflyer step-2-ios-set-up-app-store-server-notifications=2%EB%8B%A8%EA%B3%84-ios-%EC%95%B1-%EC%8A%A4%ED%86%A0%EC%96%B4-%EC%84%9C%EB%B2%84-%EC%95%8C%EB%A6%BC-%ED%99%9C%EC%84%B1%ED%99%94 h_01KD31QE0CZAJ7SH2EECDJ11YN=2%EB%8B%A8%EA%B3%84-ios-%EC%95%B1-%EC%8A%A4%ED%86%A0%EC%96%B4-%EC%84%9C%EB%B2%84-%EC%95%8C%EB%A6%BC-%ED%99%9C%EC%84%B1%ED%99%94 h_01KD31QE0C9YFBM01GGE2PZDNR=21-copy-the-appsflyer-server-notifications-endpoint h_01KD31QE0C4MRYPMMQ31BRAYS7=22-send-notifications-directly-to-appsflyer 23-%5Boptional%5D-forward-notifications-from-your-endpoint-to-appsflyer=23--optional--forward-notifications-from-your-endpoint-to-appsflyer h_01KD31QE0CWXTKDND5F4Q34J7G=23--optional--forward-notifications-from-your-endpoint-to-appsflyer h_01KD31QE0C2QWHBJ8AWMEMP2SD=24-test-the-server-notifications-integration h_01KD31QE0CA26Y430AMK474NTC=%EC%B0%B8%EA%B3%A0-1 step-2-android-set-up-google-play-server-notifications=%EB%8B%A8%EA%B3%84-2-%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B5%AC%EA%B8%80-%ED%94%8C%EB%A0%88%EC%9D%B4-%EC%84%9C%EB%B2%84-%EC%95%8C%EB%A6%BC h_01KD31QE0CKP0PTBQ4XCT9NDE1=%EB%8B%A8%EA%B3%84-2-%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B5%AC%EA%B8%80-%ED%94%8C%EB%A0%88%EC%9D%B4-%EC%84%9C%EB%B2%84-%EC%95%8C%EB%A6%BC h_01KD31QE0C1RYXW6ADHMQJ3908=21-send-google-play-notifications-directly-to-appsflyer 22-%5Boptional%5D-forward-google-play-notifications-to-appsflyer=22--optional--forward-google-play-notifications-to-appsflyer h_01KD31QE0CFVEBJV3E93Z5RDAP=22--optional--forward-google-play-notifications-to-appsflyer h_01KD31QE0CTFNTY52F0C9D3RY2=23-send-a-test-notification-from-google-play-console h_01KD31QE0CV17JMVVB7ZPT1G8W=24-confirm-notification-delivery-in-appsflyer step-3-implement-sdk-connector=3%EB%8B%A8%EA%B3%84-sdk-%EC%BB%A4%EB%84%A5%ED%84%B0-%EA%B5%AC%ED%98%84 h_01KD31QE0CPK1EYVT0BSYTTZFM=3%EB%8B%A8%EA%B3%84-sdk-%EC%BB%A4%EB%84%A5%ED%84%B0-%EA%B5%AC%ED%98%84 h_01KD31QE0C65DQ59ZKG8V886JW=%EC%B0%B8%EA%B3%A0-2 step-4-verify-sdk-implementation=4%EB%8B%A8%EA%B3%84-sdk-%EA%B5%AC%ED%98%84-%ED%99%95%EC%9D%B8 h_01KD31QE0C9KGGFVQR6HYR5AYM=4%EB%8B%A8%EA%B3%84-sdk-%EA%B5%AC%ED%98%84-%ED%99%95%EC%9D%B8 h_01KD31QE0C0VKWF5EBBR761C1J=test-sdk-implementation h_01KD31QE0C7RN657P9KPFV5725=%EC%B0%B8%EA%B3%A0-3 h_01KD31QE0D0CR02260J5K8V8QX=sandbox-events-and-parameters h_01KD31QE0DNEBYXH4672363WYM=test-inapp-purchase-and-subscription-revenue step-5-verify-and-update-settings=5%EB%8B%A8%EA%B3%84-%EC%84%A4%EC%A0%95%EC%9D%84-%ED%99%95%EC%9D%B8%ED%95%98%EA%B3%A0-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 h_01KD31QE0DQP78QG5HRSERR5S9=5%EB%8B%A8%EA%B3%84-%EC%84%A4%EC%A0%95%EC%9D%84-%ED%99%95%EC%9D%B8%ED%95%98%EA%B3%A0-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 step-6-release-the-app-versions-with-the-sdk-connector=5%EB%8B%A8%EA%B3%84-sdk-%EC%BB%A4%EB%84%A5%ED%84%B0%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%EC%95%B1-%EB%B2%84%EC%A0%84-%EC%B6%9C%EC%8B%9C h_01KD31QE0D3HX2DEH7FQ1JR4MS=5%EB%8B%A8%EA%B3%84-sdk-%EC%BB%A4%EB%84%A5%ED%84%B0%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%EC%95%B1-%EB%B2%84%EC%A0%84-%EC%B6%9C%EC%8B%9C switch-to-roi360-store-revenue-from-receipt-validation=roi360-%EC%8A%A4%ED%86%A0%EC%96%B4-%EC%88%98%EC%9D%B5%EC%9C%BC%EB%A1%9C-%EC%A0%84%ED%99%98%EC%98%81%EC%88%98%EC%A6%9D-%EA%B2%80%EC%A6%9D%EC%97%90%EC%84%9C h_01KD31QE0DJNJ8T5XSZFCACMQF=roi360-%EC%8A%A4%ED%86%A0%EC%96%B4-%EC%88%98%EC%9D%B5%EC%9C%BC%EB%A1%9C-%EC%A0%84%ED%99%98%EC%98%81%EC%88%98%EC%A6%9D-%EA%B2%80%EC%A6%9D%EC%97%90%EC%84%9C h_01KD31QE0DX0VDXKHDZTWTYHHX=%EC%B0%B8%EA%B3%A0-4" />
