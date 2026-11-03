---
title: 기본 SDK 연동 가이드
metadata:
  keywords:
    - sdk
    - iOS
    - Android
    - Integration
    - Advertisers
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2013-08-22T16:09:08Z'
  edited_at: '2026-10-14T10:35:41Z'
  id: 207032066
  locale: ko
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ko/articles/207032066
---
> **한눈에 보기:** 모바일 또는 CTV 앱 개발자와 함께 안드로이드 또는 iOS 앱에 SDK를 연동하고 인스톨하세요. 기본 연동 작업이 완료되면 귀사의 앱은 인스톨 어트리뷰션과 인앱 이벤트 측정을 할 준비가 됩니다.

## **애플리케이션 내 개발 키 구현**

앱스플라이어는 개발 키를 사용하여 귀사의 계정을 고유하게 식별합니다. 개발 키는 SDK가 귀사의 계정에 속한 데이터를 안전하게 발송하고 검색할 수 있도록 하는 필수 항목입니다. 개발자가 SDK를 인스톨하고 연동하며 개발 키를 내장해야 합니다.

#### 개발 키 검색

개발자가 SDK를 인스톨하고 연동하기 전에 개발 키를 검색해야 합니다.

1. 앱스플라이어의 사이드 메뉴에서 **설정** > **앱 설정**을 선택합니다.
2. Dev key를 복사하여 모바일 개발자에게 전달하세요.[![](https://files.readme.io/5078fdabbcce4d3977f3d32351b61bacbc8af406a68911f2c6b4cdca458712a5-30603573703057.png)](https://files.readme.io/5078fdabbcce4d3977f3d32351b61bacbc8af406a68911f2c6b4cdca458712a5-30603573703057.png)

#### 개발자에게 Dev key 제공

개발자에게 Dev Key, App ID 및 AppsFlyer API v2 토큰을 제공하고 다음 지침을 따르도록 요청하십시오.

* 자동화된 SDK 설치 및 연동을 위해 <Anchor target="_blank" href="https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration">SDK 연동 마법사</Anchor>를 사용
* 단계별 지침을 사용하여 SDK를 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">설치</Anchor>하고 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-integration">연동</Anchor>하기

## **SDK, 어디에서 시작할까요?**

앱스플라이어 SDK 연동을 계획할 때 가장 먼저 결정해야 할 것은 앱 실행 흐름에서 SDK를 어디서 초기화하고 시작할지입니다.

기본 원칙은 애플리케이션을 실행한 후 가능한 한 빨리 SDK가 데이터를 전송하도록 하는 것입니다. **이렇게 하면 SDK는 인스톨 이벤트를 포함해 해당 세션 동안 발생하는 모든 인앱 이벤트를 정확하게 수집할 수 있습니다.**

그러나 GDPR 및 CCPA와 같은 개인정보 보호 규정을 준수하기 위해, 사용자가 정보 제공에 동의할 때까지 앱스플라이어로의 데이터 전송을 지연해야 하는 경우가 많습니다.

<Tabs>
<Tab title="안드로이드 native">

### 안드로이드 네이티브에서 SDK 시작

#### SDK를 어느 클래스에서 시작할지 선택하세요

글로벌 `Application` 클래스 또는 `Activity` 클래스에서 SDK를 시작할지 선택하세요.

* **글로벌** 클래스에서 SDK 시작:** 일반적으로 글로벌 `Application` 클래스 또는 하위 클래스에서 SDK를 초기화하는 것은 좋은 방법입니다. 이 `Application` 클래스가 앱 UI가 표시되기 전에 로드되고 초기화되기 때문입니다. 이렇게 함으로써 딥링킹을 포함한 모든 시나리오에서 SDK를 시작할 수 있습니다.**
* 사용자가 데이터 공유를 선택할 수 있도록 클래스에서 지연된 시작으로** SDK를 시작합니다. 이는 사용자 동의를 얻기 위해서는 `Activity` 클래스에서 렌더링된 사용자 인터페이스(UI)가 필요하기 때문입니다.**

#### 안드로이드 개발자 지침

* 다음 사항에 대한 결정을 개발자에게 알려 주세요.
  * 어떤 클래스에서 SDK를 시작할 것인지: `Application` 또는 `Activity`?
  * 어떤 옵트인/옵트아웃 시나리오를 사용할 것인지?
* 다음 참조 링크를 개발자에게 발송하세요:
  * [지연된 시작 수행 방법](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#starting-the-android-sdk)

</Tab>

<Tab title="iOS native">

<div id="starting-the-sdk-in-ios" />

### iOS 네이티브에서 SDK 시작하기

<div id="delay-the-sdk-start-in-ios" />

#### iOS에서 SDK 시작 지연

SDK 시작 방법을 계획할 때 중요한 고려 사항은 사용자 동의가 이루어질 때까지 `start`을 지연할지 여부입니다.

SDK는 `waitForATTUserAuthorization` 메서드를 제공하며, 이를 통해 **사용자 동의를 기다리는 시간을 설정할 수 있습니다**. 앱스플라이어 서버로 데이터를 발송하기 전에

메서드 데이터 흐름과 iOS 앱 추적 투명성 프레임워크와의 상호작용에 대한 자세한 내용은 [앱 추적 투명성(ATT) 지원 구성](/docs/basic-sdk-integration-guide#waitforattuserauthorization-개요) 섹션을 참조하세요.

<div id="ios-developer-instructions" />

#### iOS 개발자 지침

다음 정보를 개발자와 공유하세요:

* 앱스플라이어로 데이터를 발송하기 전의 시간 초과는 몇 초입니까?
* 개발자 링크:
  * 개발자 가이드 및 SDK 시작 방법에 관한 참고 자료를 보려면 [iOS SDK 시작](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#starting-the-ios-sdk)을 참조하세요.
  * iOS 앱 추적 투명성(ATT) 프레임워크와의 상호작용 및 [메서드 데이터 흐름에 대한 정보는](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support) [앱 추적 투명성(ATT) 지원 구성](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support)을 참조하세요.
  * [앱 추적 투명성(ATT) 지원 활성화](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support)에 대한 개발자 가이드 및 참조 자료를 [에 대해 확인하세요.](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support)

</Tab>

<Tab title="Unity">

<div id="starting-the-sdk-in-Unity" />

### Unity에서 SDK 시작하기

SDK를 시작하는 방법에 대한 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#manual-integration">Dev Hub 문서</Anchor>를 개발자에게 발송하세요.

</Tab>

<Tab title="React Native">

<div id="starting-the-sdk-in-react" />

### React Native에서 SDK 시작하기

SDK를 시작하는 방법에 대한 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#startsdk">Dev Hub 문서</Anchor>를 개발자에게 발송하세요.

</Tab>
</Tabs>

## 개인 정보 보호 전략을 선택하세요

**사용자 개인 정보를 보호하는 방법**을 선택하세요. 예를 들어, SDK를 설치 시 중지하거나, 데이터 공유를 타사와 방지하고, 사용자 데이터를 익명화하거나 특정 식별자를 비활성화하는 방법 중 선택하세요.

사용 가능한 다양한 개인정보 보호 방법에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/apply-privacy-preserving-sdk-methods">SDK의 개인정보 보호 방법</Anchor>을 참조하세요.

## **어트리뷰션**

SDK는 어트리뷰션 목적으로 <Anchor target="_blank" href="/marketers/ko/docs/about-device-identifiers">식별자</Anchor>를 수집합니다. 인스톨이 올바르게 기록되고 어트리뷰션되는지 확인하려면 다음 지침을 검토하고 따르세요.

**모든 플랫폼**

<div id="unique-identifier-for-installs" />

<Accordion title="인스톨을 위한 고유 식별자">

새로운 앱 설치 시마다 앱스플라이어 ID가 자동으로 생성됩니다. 마케터는 별도의 조치가 필요하지 않습니다.

이 식별자를 사용하여 다음 작업을 수행할 수 있습니다.

* <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">서버-투-서버 인앱 이벤트</Anchor>를 발송하세요.
* 앱스플라이어 ID를 귀사의 백엔드 시스템의 유저 기록과 매칭하세요.
* <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">로데이터 인앱 이벤트 리포트</Anchor>를 다운로드하여 **appsflyer\_id**를 사용해 유저 행동과 여정을 분석하세요.

</Accordion>

<div id="integrate-unique-identifiers-from-your-bi-system-with-appsflyer" />

<Accordion title="귀사의 BI 시스템의 고유 식별자를 앱스플라이어와 연동하세요.">

앱스플라이어 SDK에서 귀사의 고객 유저 ID(CUID)를 설정하여 BI 시스템의 고유 ID를 앱스플라이어 ID 및 기타 식별자와 교차 참조합니다. CUID는 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary">로데이터</Anchor> 리포트에서 확인할 수 있습니다. 또한, 귀사의 내부 ID와 교차 참조하기 위해 포스트백 API에서도 사용할 수 있습니다.

CUID에 대해 더 알고 싶다면, <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">이 문서</Anchor>를 참조하세요.

</Accordion>

**안드로이드만 해당**

다음 섹션에서는 구글 플레이 스토어나 써드 파티 앱 스토어에 대한 어트리뷰션 고려사항을 설명합니다.

<div id="attribute-apps-published-on-google-play" />

<Accordion title="구글 플레이에 게시된 앱 속성">

#### GOOGLE PLAY INSTALL REFERRER

[구글 플레이 인스톨 리퍼러 API](https://developer.android.com/google/play/installreferrer)는 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#어트리뷰션-메서드">어트리뷰션</Anchor> 정확도를 향상하고, 설치 프로드를 방지하며, 구글 플레이에서 앱의 추천 데이터를 안전하게 가져올 수 있도록 해줍니다(예: 앱이 처음 설치되었을 때의 앱 버전).

개발자에게 [구글 플레이 인스톨 리퍼러 API 추가 방법](https://developer.android.com/google/play/installreferrer/library)을 제공하는 것이 좋습니다.

#### GAID

SDK V4.8.0부터 앱스플라이어는 이 기기 식별자를 자동으로 수집합니다.

</Accordion>

<div id="attribute-apps-in-thirdparty-app-stores" />

<Accordion title="써드 파티 앱 스토어에서 앱 어트리뷰트">

앱스플라이어를 사용하면 Amazon, Opera, GetJar, Baidu, Huawei와 같은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution">써드 파티 앱 스토어에서 발생한 인스톨을 어트리뷰트할 수 있습니다.</Anchor> 이를 통해 귀사의 앱을 구글 플레이 스토어가 없는 시장에서도 홍보하고 더 많은 오디언스를 확보할 수 있습니다.

앱스플라이어는 다음과 같이 써드 파티 앱 스토어 컨텍스트에서의 어트리뷰션을 지원합니다.

* **IMEI 또는 안드로이드 ID:** SDK가 IMEI나 안드로이드 ID를 자동으로 수집하지 않습니다. 그러나 이러한 식별자를 수집해야 하는 경우(예: <Anchor target="_blank" href="/marketers/ko/docs/measure-attribution-in-the-chinese-domestic-market#attribution-android-apps-in-the-chinese-domestic-market">중국 내수 시장의 앱</Anchor>), 귀사의 개발자는 다음 중 하나의 수집 방법을 구현할 수 있습니다.
  * 수동 수집: 앱은 `setImeiData` 또는 `setAndroidIdData` API를 사용하여 IMEI 또는 안드로이드 ID를 SDK로 전달합니다(아래 탭의 함수 참조를 확인하세요). SDK가 앱스플라이어 서버로 데이터를 전송합니다.

    <Tabs>
    <Tab title="안드로이드 네이티브">

    안드로이드 SDK 참조를 확인하세요.

    </Tab>

    <Tab title="유니티">

    Unity SDK 참조를 확인하세요.

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setimeidata">`setImeiData`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">`setAndroidIdData`</Anchor>

    </Tab>
    </Tabs>

  * 디바이스 ID 수집 옵트인: setCollectIMEI 및 setCollectAndroidID를 사용하여 SDK가 함수를 사용하여 IMEI 또는 Android ID를 수집하도록 설정할 수 있습니다.(아래 탭에서 함수 참조 확인)

    <Tabs>
    <Tab title="안드로이드 native">

    안드로이드 SDK 참조를 확인하세요.

    </Tab>

    <Tab title="UnityReact Native">

    Unity SDK 참조를 확인하세요.

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectimei">`setCollectIMEI`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectandroidid">`setCollectAndroidID`</Anchor>

    </Tab>
    </Tabs>

* **OAID:** 써드 파티 안드로이드 앱 스토어에서 인스톨을 어트리뷰션합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/android-oaid-implementation-in-the-sdk">OAID 구현 가이드</Anchor>를 참조하세요.
* **인스톨 리퍼러:** SDK가 Samsung Gallery 및 Huawei AppGallery에서 앱 추천 데이터를 검색하는 것을 지원합니다.

</Accordion>

**iOS 전용**

다음 섹션에는 iOS 14+ 디바이스 지원에 대한 중요한 정보가 포함되어 있습니다.

<div id="configure-app-tracking-transparency-att-support" />

<Accordion title="앱 추적 투명성(ATT) 지원 구성">

**배경**

iOS 14.5부터 IDFA 수집에는 사용자의 동의가 필요합니다. 실제로, 이는 IDFA 액세스가 [**앱 추적 투명성**](https://developer.apple.com/documentation/apptrackingtransparency) (ATT) 프레임워크에 의해 관리된다는 것을 의미합니다. iOS 14+ 디바이스에서 SDK가 ATT 프레임워크를 사용하여 디바이스 IDFA에 액세스합니다. ATT에 대한 소개는 <Anchor target="_blank" href="/marketers/ko/docs/about-att-and-skan#att-principles">ATT 원칙</Anchor>을 참조하세요.

<Tabs>
<Tab title="iOS 네이티브">

ATT 구현을 위한 개발자 지침은 Dev Hub에서 를 참조하세요.

</Tab>

<Tab title="유니티">

ATT 구현을 위한 개발자 지침은 Dev Hub에서 를 참조하세요.

</Tab>
</Tabs>

IDFA를 사용하여 어트리뷰션이 이루어질 때는 IDFA가 **앱 최초 오픈 시 전송되는 것이 중요합니다. `waitForATTUserAuthorization`이러한 이유로 SDK는 `waitForATTUserAuthorization` 메서드를 제공합니다.**

#### waitForATTUserAuthorization 개요

> 🚧 **중요!**
>
> 앱 추적 투명성 프롬프트를 호출하지 않으려면 `waitForATTUserAuthorization`을 호출하지 마세요.

`waitForATTUserAuthorization`을 활용하여 SDK가 앱스플라이어 서버로 데이터를 전송하기 전에 앱 추적 투명성(ATT) 상태를 기다리는 시간을 설정할 수 있습니다.

유저가 앱을 시작하면 앱 추적 투명성(ATT) 상태는 **notDetermined**입니다.  [시간 동안 SDK는](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#offline-in-app-events) [오프라인 이벤트가 기록되는 방식](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#offline-in-app-events)과 유사하게 메모리에 런치 이벤트와 연속적인 인앱 이벤트를 대기열에 넣습니다.

* 유저가 앱 추적 투명성(ATT) 프롬프트(IDFA 수집)에 **동의**하면:
  * SDK는 IDFA를 캐시된 이벤트에 추가합니다.
  * SDK가 시작되어 IDFA와 함께 캐시된 이벤트를 전송합니다(시간 초과가 끝날 때까지 기다리지 않고).
* 유저가 앱 추적 투명성(ATT) 프롬프트를 **거부**하는 경우: SDK가 시작되어 IDFA 없이 캐시된 이벤트를 전송합니다(시간 초과가 끝날 때까지 기다리지 않고).
* 시간 초과가 끝나고 앱 추적 투명성(ATT) 상태가 **notDetermined 상태로 남아 있으면:** SDK가 시작되어 IDFA 없이 캐시된 이벤트를 전송합니다.

**고려 사항**

* 을(를) 설정하지 않고 [호출하면 iOS 14+ 디바이스에서는 IDFA 없이 런치 및 이벤트가 전송됩니다.](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/3547037-requesttrackingauthorization)
* 유저가 시간 초과 중에 앱을 백그라운드로 이동한 경우:
  * 타이머는 앱이 다시 포그라운드로 돌아올 때까지 중지됩니다.
  * 이벤트는 메모리에 캐시됩니다.
* 유저가 앱을 종료하면, 이는 시간 초과 중에 종료됩니다.
  * 다음 앱 실행 시 타이머가 다시 시작됩니다.
  * 캐시된 이벤트는 사라집니다.

</Accordion>

<div id="customize-att-consent-dialog" />

<Accordion title="앱 추적 투명성(ATT) 동의 대화 상자를 사용자 정의">

앱 추적 투명성(ATT) 프롬프트를 사용자 정의할 수 있습니다. 요청 목적을 명확히 밝힌 메시지는 유저 가입률을 높이는 데 도움이 될 수 있습니다.

메시지를 작성할 때 다음을 유념하세요:

* 앱이 유저 동의를 요구하는 이유를 명확히 설명할 수 있는 표현을 사용하세요.
* 유저에게 그들의 데이터가 어떻게 사용될지를 알려주세요.  [유저 개인정보 보호 및 데이터 사용에 대해 더 보기](https://developer.apple.com/app-store/user-privacy-and-data-use/)

메시지가 완성되면 개발자에게 텍스트와 구현 지침을 제공하세요.

<Tabs>
<Tab title="iOS 네이티브">

앱 추적 투명성(ATT) 동의 대화 상자 사용자 지정에 대한 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#customizing-the-att-consent-dialog">개발자 지침</Anchor>은 Dev Hub를 참조하세요.

</Tab>

<Tab title="유니티">

앱 추적 투명성(ATT) 동의 대화 상자 사용자 지정에 대한 [개발자 지침](https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager)은 Dev Hub를 참조하세요.

</Tab>
</Tabs>

<div id="support-for-skan-attribution" />

<Accordion title="SKAN 어트리뷰션 지원">

> 📘 **참고**
>
> SKAN 어트리뷰션을 완벽하게 지원하려면 iOS SDK V6.2.3+로 업그레이드하세요.

SKAN은 iOS에서 광고주가 주도하는 앱 설치를 검증하기 위해 사용하는 클래스입니다. 앱 설치 검증 과정에는 소스 앱과 광고된 앱이 포함됩니다.

소스 앱은 애드 네트워크의 광고를 표시하여 광고 캠페인에 참여하는 앱입니다. 광고를 표시하도록 귀사의 앱을 구성하는 것은 앱스플라이어 SDK의 영역이 아닙니다. 구성하려면 [Apple 지침](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app)을 따르세요.

광고된 앱(앱스플라이어 SDK가 포함된 앱)은 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">SKAN 솔루션</Anchor>을 통해 SKAN을 사용하여 어트리뷰션 포스트백을 제공합니다. 앱스플라이어는 개인 정보를 유지하면서 데이터를 수집, 변환 및 집계합니다. 앱이 처음 실행될 때, 앱스플라이어 플랫폼은 마케터가 설정한 구성을 통해 SDK에 SKAN 전환 값을 설정하는 방법을 지시합니다.

SKAN 솔루션을 사용하려면:

* 마케터는 앱스플라이어에서 SKAN 측정을 구성해야 합니다. 개발자는 어떠한 작업도 수행할 필요가 없습니다.
* 앱스플라이어 SDK가 필요한 SKAN API를 자동으로 호출합니다.
* 앱스플라이어로 SKAN 어트리뷰션을 진행하려면 다른 SDK에서 SKAN 호출을 비활성화해야 합니다.
* 애플 앱 스토어에서는 개발자나 마케터가 별도로 할 작업이나 등록 절차가 필요하지 않습니다.

SKAN 어트리뷰션을 비활성화하려면 개발자에게 SDK에서 이를 비활성화하도록 요청하세요.

<Tabs>
<Tab title="iOS 네이티브">

SKAN 어트리뷰션 비활성화하려면 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableskadnetwork">`disableSKAdNetwork`</Anchor>을 사용하세요.

</Tab>

<Tab title="Unity React 네이티브">

SKAN 어트리뷰션 비활성화하려면 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#disableskadnetwork">`disableSKAdNetwork`</Anchor>을 사용하세요.

</Tab>
</Tabs>

</Accordion>

</Accordion>

## **인앱 이벤트 기록**

인앱 이벤트(IAE)는 귀사의 앱에서 발생하는 상황에 대한 통찰력을 제공합니다. 인앱 이벤트를 기록하면 ROI (투자수익률)와 LTV(유저생애가치)와 같은 KPI를 측정하는 데 도움이 됩니다. 기록하려는 이벤트를 미리 정의하는 것을 권장합니다.

측정하고자 하는 인앱 이벤트를 결정한 후, 이벤트 이름, 파라미터와 함께 다음 링크를 개발자에게 전송하세요.

* 인앱 이벤트를 위한 전용 여정이 포함된 [SDK 설치 마법사](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration).
* <Anchor target="_blank" href="http://dev.appsflyer.com/hc/docs/in-app-events-sdk">SDK에서 인앱 이벤트를 구현하기 위한 단계별 구현 지침.</Anchor>

인앱 이벤트를 정의하고 이를 개발자에게 전달하는 방법을 알아보려면, <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트 개요 가이드</Anchor>를 참고하세요.

**모든 플랫폼**

<div id="record-revenue" />

<Accordion title="수익 기록">

모든 인앱 이벤트와 함께 수익을 발송할 수 있습니다. 수익을 포함하려면 **af\_revenue** 파라미터를 사용해야 합니다. 이는 앱스플라이어 대시보드와 로데이터 리포트에서 실제 수익으로 계산되는 유일한 Event Parameter입니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">더 알아보기</Anchor>.

<Tabs>
<Tab title="안드로이드 네이티브">

수익 이벤트 정의에 대한 개발자 지침은 [여기](https://dev.appsflyer.com/hc/docs/in-app-events-android#logging-revenue)를 참조하세요.

</Tab>

<Tab title="iOS 네이티브Unity">

수익 이벤트 정의에 대한 개발자 지침은 [여기](https://dev.appsflyer.com/hc/docs/in-app-events-ios#logging-revenue)를 참조하세요.

</Tab>
</Tabs>

</Accordion>

<div id="validate-inapp-purchases" />

<Accordion title="인앱 구매 검증">

앱스플라이어 SDK는 인앱 구매에 대한 서버 검증을 제공합니다. 인앱 구매를 검증하면 자동으로 인앱 구매 이벤트가 앱스플라이어로 전송됩니다. 이 이벤트를 직접 보내면 이벤트 리포팅이 중복됩니다.

</Accordion>

<div id="industry-verticals" />

<Accordion title="업계 업종별, 앱 카테고리별">

여행, 게임, 이커머스 등 업종별, 앱 카테고리별 추천 인앱 이벤트 목록<Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#recommended-events-by-business-vertical">을 확인하세요.</Anchor>

</Accordion>

## **원링크를 사용한 딥링킹**

원링크는 멀티 플랫폼 어트리뷰션, **리디렉션, 딥링킹**을 위한 앱스플라이어 솔루션입니다.

**모든 플랫폼**

<div id="device-detection-and-redirection" />

<Accordion title="디바이스 감지 및 리디렉션">

앱이 설치되지 않은 사용자의 경우, 원링크가 디바이스 유형을 감지하여 올바른 대상으로 리디렉션합니다 (예: 구글 플레이, Apple 애플 앱 스토어, 써드 파티 앱 스토어 또는 웹 페이지). 이는 귀사의 원링크 템플릿 설정에 기반합니다. <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template">더 보기</Anchor>

</Accordion>

<div id="deep-linking" />

<Accordion title="딥링킹">

앱이 설치된 사용자의 경우, 원링크가 앱을 엽니다. 앱을 여는 것 외에도, 사용자를 앱 내의 특정 액티비티나 페이지로 딥링크할 수 있습니다. 이를 위해서는 개발자가 통합 딥링킹(UDL)을 구현해야 합니다.

* 딥링킹 구현를 위한 전용 여정이 포함된 [SDK 설치 마법사](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration), 혹은
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">통합 딥링크를 위한 단계별 SDK 구현 지침</Anchor>.

**참고**:

* UDL을 구현하려면 SDK V6.1 이상이 필요합니다.
* 이미 딥링킹에 원링크를 사용하고 있는 고객은 UDL 대신 [기존 메서드](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking)를 사용하고 있을 수 있습니다.

<Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">딥링크 및 디퍼드 딥링크</Anchor> 설정에 대한 가이드를 참조하세요.

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="디퍼드 딥링킹">

앱이 설치되지 않은 사용자의 경우, 원링크가 디바이스 유형을 감지하고 올바른 대상으로 리디렉션합니다. 구글 플레이, Apple 애플 앱 스토어, 써드 파티 앱 스토어 또는 웹 페이지에서. 사용자가 앱을 실행하면, 디퍼드 딥링킹을 사용하여 앱 내의 특정 액티비티나 페이지로 리디렉션할 수 있습니다.

이를 위해서는 개발자가 디퍼드 디퍼드 딥링킹을 구현해야 합니다.

* 딥링킹 구현를 위한 전용 여정이 포함된 [SDK 설치 마법사](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration), 혹은
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking">디퍼드 딥링크를 위한 단계별 SDK 구현 지침</Anchor>.

**참고**:

* UDL을 구현하려면 SDK V6.1 이상이 필요합니다.
* 디퍼드 딥링킹에 원링크를 이미 사용하고 있는 고객은 UDL 대신 [기존 메서드](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking)를 사용하고 있을 수 있습니다.

<Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">딥링크 및 디퍼드 딥링크</Anchor> 설정에 대한 가이드를 참조하세요.

</Accordion>

## **어트리뷰션 및 딥링킹 데이터 액세스**

다음 표는 어트리뷰션 및 딥링킹 데이터를 검색하는 데 사용할 수 있는 방법을 설명합니다.

| 방법 | 누가 관련되어 있나요? | 결과 반환 | 검색 방법 | 어트리뷰션 데이터 | 딥링킹 데이터 | 유효성 |
| --- | --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/push-api-streaming-raw-data">**Push API**</Anchor> | • 마케터 • 백엔드 개발자 | 일반적으로 몇 분 이내 | 백엔드 | Y | N | 프리미엄 |
| <Anchor target="_blank" href="/marketers/ko/docs/pull-api-raw-data">**Pull API**</Anchor> | • 마케터 • 백엔드 개발자 | • 주기적(실시간 아님). • 원시 데이터 리포트 다운로드를 예약할 수 있습니다. | 백엔드 | Y | Y | 원시 데이터 리포트에 대한 프리미엄 |
| <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers">**데이터 락커**</Anchor> | • 마케터 • 백엔드 개발자 | 시간별 리포트는 1-3시간 이내에 이용 가능합니다. | 다음 옵션을 통한 클라우드 스토리지: • AWS에 있는 앱스플라이어 소유 버킷 • 사용자가 소유한 스토리지(AWS 또는 GCS) | Y | Y | 프리미엄 |
| <Anchor target="_blank" href="/marketers/ko/docs/conversion-data-payloads-and-scenarios#overview">**전환 데이터 가져오기(GCD)**</Anchor> | • 마케터 • 모바일 개발자 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking">개발자 문서를 참조하세요</Anchor> | 최대 5초 | SDK | Y | Y | 모든 계정 |
| <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template">**통합 딥링킹(UDL)**</Anchor> | • 마케터 • 모바일 개발자 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">개발자 문서를 참조하세요</Anchor> | 최대 1초 | SDK | N | Y | 모든 계정 |

iOS 14.5 이상 동의하지 않은 사용자들의 경우 다음 사항을 유의하세요.

* 유료 및 소유 매체에서 UDL을 사용하는 경우, 딥링킹 데이터를 사용할 수 있습니다.
* 페이드 미디어에 GCD를 사용할 경우, 제공되는 데이터는 제한적이며 어트리뷰션 및 딥링크 관련 세부 정보가 포함되지 않습니다.

> 👍 **팁**
>
> 다음을 추천합니다.
>
> * Push API를 사용하여 어트리뷰션 데이터를 가져와 귀사의 서버로 발송하여 추가 처리하세요. 이 메서드는 데이터가 준비될 때까지 기다리므로 정확도가 높고 실시간에 가깝습니다. GCD는 실시간으로 데이터를 반환하지만, 최종 어트리뷰션 결정이 5초 이상 소요될 경우 정확하지 않을 수 있습니다.
> * Pull API를 사용하여 주기적으로(예: 매일) 실시간 어트리뷰션 데이터를 보완하고, 발생할 수 있는 통신 오류를 보상하세요.

## **SDK 연동 테스트**

SDK 연동이 완료되면 앱스플라이어 대시보드로 이동하여 SDK 연동 테스트 페이지에서 오가닉 및 논오가닉 인스톨, 인앱 이벤트, 딥링킹(리타겟팅)을 시험하세요. 이를 통해 인스톨과 인앱 이벤트가 정확하게 기록되고 어트리뷰션됩니다.

시험 시나리오와 지침은 <Anchor target="_blank" href="/marketers/ko/docs/testing-the-sdk-integration-for-marketers">SDK 연동 시험</Anchor>을 참조하세요.

**참고:** 어트리뷰션 시험을 수행할 때, <Anchor target="_blank" href="/marketers/ko/docs/registering-test-devices">시험 디바이스(안드로이드 또는 iOS)를 등록하여</Anchor> 각 인스톨이 새 인스톨로 기록되도록 합니다. 등록된 시험 디바이스는 인스톨이 재인스톨로 기록되는 것을 방지합니다.

> 📄 **또한 참조하세요**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC 및 콘솔 플랫폼 개요</Anchor>

<div data-zendesk-anchors="retrieving-the-dev-key=%EC%95%A0%ED%94%8C%EB%A6%AC%EC%BC%80%EC%9D%B4%EC%85%98-%EB%82%B4-%EA%B0%9C%EB%B0%9C-%ED%82%A4-%EA%B5%AC%ED%98%84 h_01HAWCK9K4QBRE74JAS8Q7MEXW=%EC%95%A0%ED%94%8C%EB%A6%AC%EC%BC%80%EC%9D%B4%EC%85%98-%EB%82%B4-%EA%B0%9C%EB%B0%9C-%ED%82%A4-%EA%B5%AC%ED%98%84 retrieve-the-dev-key=%EA%B0%9C%EB%B0%9C-%ED%82%A4-%EA%B2%80%EC%83%89 h_01HHHKTARNPQTBXQ6CQGEHMJRG=%EA%B0%9C%EB%B0%9C-%ED%82%A4-%EA%B2%80%EC%83%89 embed-the-dev-key=%EA%B0%9C%EB%B0%9C%EC%9E%90%EC%97%90%EA%B2%8C-dev-key-%EC%A0%9C%EA%B3%B5 h_01HHHKXMBGV6EM0CCW842RQQZ6=%EA%B0%9C%EB%B0%9C%EC%9E%90%EC%97%90%EA%B2%8C-dev-key-%EC%A0%9C%EA%B3%B5 where-to-start-the-sdk=sdk-%EC%96%B4%EB%94%94%EC%97%90%EC%84%9C-%EC%8B%9C%EC%9E%91%ED%95%A0%EA%B9%8C%EC%9A%94 h_01HAWCK9K4MBS0F0HE6QE1W1AN=sdk-%EC%96%B4%EB%94%94%EC%97%90%EC%84%9C-%EC%8B%9C%EC%9E%91%ED%95%A0%EA%B9%8C%EC%9A%94 starting-the-sdk-in-android=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EB%84%A4%EC%9D%B4%ED%8B%B0%EB%B8%8C%EC%97%90%EC%84%9C-sdk-%EC%8B%9C%EC%9E%91 h_01HAWCK9K45HCJEDRW761WHKES=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EB%84%A4%EC%9D%B4%ED%8B%B0%EB%B8%8C%EC%97%90%EC%84%9C-sdk-%EC%8B%9C%EC%9E%91 select-in-what-class-to-start-the-sdk=sdk%EB%A5%BC-%EC%96%B4%EB%8A%90-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%97%90%EC%84%9C-%EC%8B%9C%EC%9E%91%ED%95%A0%EC%A7%80-%EC%84%A0%ED%83%9D%ED%95%98%EC%84%B8%EC%9A%94 h_01HAWCK9K428SDFBFCCSZ15X9J=sdk%EB%A5%BC-%EC%96%B4%EB%8A%90-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%97%90%EC%84%9C-%EC%8B%9C%EC%9E%91%ED%95%A0%EC%A7%80-%EC%84%A0%ED%83%9D%ED%95%98%EC%84%B8%EC%9A%94 android-developer-instructions=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%A7%80%EC%B9%A8 h_01HAWCK9K4XR1HZHP7Y15Q2Q4N=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%A7%80%EC%B9%A8 h_01HAWCK9K4693729EX1WYFR6XT=starting-the-sdk-in-ios h_01HAWCK9K4QSBP874RX2ZRA7EB=delay-the-sdk-start-in-ios h_01HAWCK9K4VHDFB9CYHC144BZN=ios-developer-instructions select-the-optoutin-scenario::ae4c6e25=%EA%B0%9C%EC%9D%B8-%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8-%EC%A0%84%EB%9E%B5%EC%9D%84-%EC%84%A0%ED%83%9D%ED%95%98%EC%84%B8%EC%9A%94 h_01HAWCK9K4EXBA2F0BPVBXFAMG=%EA%B0%9C%EC%9D%B8-%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8-%EC%A0%84%EB%9E%B5%EC%9D%84-%EC%84%A0%ED%83%9D%ED%95%98%EC%84%B8%EC%9A%94 attribution=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HAWCK9K41T5GGWDB3ABYGRHW=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HAWCK9K4HY8NZC0VM3NBF4H9=unique-identifier-for-installs h_01HAWCK9K44GRVGBB1P3FWBX4A=integrate-unique-identifiers-from-your-bi-system-with-appsflyer h_01HAWCK9K4SE4YWTQYF3R1WH2Z=attribute-apps-published-on-google-play h_01HAWCK9K4V91MPQHXDZBD0HKR=google-play-install-referrer h_01HAWCK9K4YD8CYQDB2YRA8W1F=gaid h_01HAWCK9K4EFCGWJ45K8VRAFFM=attribute-apps-in-thirdparty-app-stores h_01HAWCK9K5VKBZS5MSF27WNG1G=configure-app-tracking-transparency-att-support waitforattuserauthorization-overview=waitforattuserauthorization-%EA%B0%9C%EC%9A%94 h_01HAWCK9K5JHDWS8KTBTTGSS9G=waitforattuserauthorization-%EA%B0%9C%EC%9A%94 h_01HAWCK9K5X4Z9DWRT1VDSFEPH=%EC%A4%91%EC%9A%94 h_01HAWCK9K5FY2H211JFQQDSXHK=customize-att-consent-dialog h_01HAWCK9K5HV3SBY82A28ZD4KN=support-for-skan-attribution h_01HAWCK9K5HS9Y836X33YMV21C=%EC%B0%B8%EA%B3%A0 recording-inapp-events=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EA%B8%B0%EB%A1%9D h_01HAWCK9K5ZZYQR8KPCWANZEA5=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EA%B8%B0%EB%A1%9D h_01HAWCK9K50T438WCG0PKP5M3G=record-revenue h_01HAWCK9K5Z0N6DP38VCB3K3B2=validate-inapp-purchases h_01HAWCK9K5A3W2XKCM7XRNGKQK=industry-verticals deep-linking-with-onelink=%EC%9B%90%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%EB%94%A5%EB%A7%81%ED%82%B9 h_01HAWCK9K5PK9RE7WZQVCY97KC=%EC%9B%90%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%EB%94%A5%EB%A7%81%ED%82%B9 h_01HAWCK9K593KCJ9QQQV0E0E71=device-detection-and-redirection h_01HAWCK9K5SNBFHNFXYBBC20HN=deep-linking h_01HAWCK9K5YJSB78Z4RJSAP1KM=deferred-deep-linking accessing-attribution-and-deep-linking-data=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%B0%8F-%EB%94%A5%EB%A7%81%ED%82%B9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%95%A1%EC%84%B8%EC%8A%A4 h_01HAWCK9K5ACPZ2WKBTVR3VVTD=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%B0%8F-%EB%94%A5%EB%A7%81%ED%82%B9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%95%A1%EC%84%B8%EC%8A%A4 h_01HAWCK9K6N405V344RDEGC0QJ=%ED%8C%81 testing-your-sdk-integration=sdk-%EC%97%B0%EB%8F%99-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01HAWCK9K6JQ33T32RYKYH20P1=sdk-%EC%97%B0%EB%8F%99-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01H9FHRVKE88CXGH8G7E26ZXT2=%EB%98%90%ED%95%9C-%EC%B0%B8%EC%A1%B0%ED%95%98%EC%84%B8%EC%9A%94" />
