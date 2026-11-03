---
title: 추가 SDK 연동 가이드
metadata:
  keywords:
    - iOS
    - Android
    - Integration
    - Advertisers
    - firetv
    - Advertiser
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2021-10-10T11:54:14Z'
  edited_at: '2026-10-14T10:40:11Z'
  id: 4408735106193
  locale: ko
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ko/articles/4408735106193
---
> **한눈에 보기:** 요약: 앱 삭제 측정, 사용자 초대 어트리뷰션, 푸시 알림 및 프라이버시 설정과 같은 API를 구현하기 위해 개발자와 함께 사용할 수 있는 추가 SDK 기능을 고찰합니다.

## 추가 어트리뷰션 방법

TV, 앱 제거 또는 사전 설치된 앱을 측정하려는 경우 이러한 추가 어트리뷰션 방법을 고려하십시오.

**모든 플랫폼**

<div id="tv-attribution" />

<Accordion title="TV 어트리뷰션">

특정 위치 및 특정 시간에 방송된 TV 광고에 모바일 사용자를 어트리뷰트합니다.

</Accordion>

<div id="measure-uninstalls" />

<Accordion title="앱 삭제 측정">

다양한 소스에서 유입된 사용자의 앱 삭제 비율을 측정해보십시오. 앱 삭제를 측정함으로써 캠페인을 분석하고 최적화하는데 이 중요한 성과 지표를 포함시킬 수 있습니다.

<Anchor target="_blank" href="/marketers/ko/docs/measure-uninstalls">앱 삭제 측정을 설정하는 방법 알아보기.</Anchor>

</Accordion>

**안드로이드 전용**

<div id="preinstalled-apps" />

<Accordion title="사전 설치된(pre-installed) 앱">

<Anchor target="_blank" href="/marketers/ko/docs/appsflyer-factory-preinstall-using-manifest-android">사전 인스톨 캠페인</Anchor>에서 앱 소유자는 기기 제조사(OEM)와 연계하여 앱을 사전 인스톨합니다.

앱스플라이어를 사용하면, 이렇게 사전 설치된 앱의 인스톨을 쉽게 어트리뷰트 할 수 있습니다. 사용자가 앱을 최초 실행할 때, 앱스플라이어는 해당 인스톨을 사전 로드 파트너 이름 미디어소스로 어트리뷰트합니다.

</Accordion>

## 세션

일정 기간 동안 사용자 세션 수를 계산하여 앱에 대한 사용자 인게이지먼트를 측정합니다. 

**모든 플랫폼**

<div id="custom-time-between-sessions" />

<Accordion title="세션 간 시간 정의">

기본 설정으로는, 앱을 실행할 때의 간격이 적어도 5초 이상이 되어야 두 개의 별도 세션으로 집계합니다. <Anchor target="_blank" href="/marketers/ko/docs/measure-sessions#session-reporting-by-the-app-sdk">세션 집계</Anchor>에 대해 자세히 알아보기.

**너무 높은 값을 세션 간격 시간으로 설정하면** 딥링킹과 같이 세션 데이터를 사용하는 API에 문제가 발생할 수 있습니다.

</Accordion>

**안드로이드 전용**

<div id="background-sessions-for-utility-apps" />

<Accordion title="유틸리티 앱을 위한 백그라운드 세션">

<Anchor target="_blank" href="/marketers/ko/docs/measure-sessions#session-reporting-by-the-app-sdk">사용자 세션을 수동으로 리포트</Anchor>할 수 있습니다. 이 방법은 백그라운드에서 동작하는 유틸리티 앱에 유용할 수 있습니다.

</Accordion>

## 소유 매체

원링크를 사용하여 모바일 웹 사이트, 소셜 미디어, 사용자 초대 등의 온드 미디어 소스를 어트리뷰트합니다.

**모든 플랫폼**

<div id="resolve-wrapped-deep-link-urls" />

<Accordion title="래핑(wrapping)된 딥링크 URL 분석하기">

<Anchor target="_blank" href="/marketers/ko/docs/email-service-provider-esp-integration-guide">이메일 서비스 제공 업체들</Anchor> 과 같은 몇몇 외부 업체 서비스 사는 이메일 내의 링크를 자체 클릭 기록 도메인으로 래핑(wrapping)합니다. 어떤 업체는 자신의 클릭 기록 도메인을 직접 설정하도록 허용하기도 합니다. 만약 원링크가 이런 도메인들에서 래핑된다면, 원링크의 기능이 제한될 수 있습니다.

상기 문제를 해결하려면 개발자가 해당 API를 사용하여 앱을 설정해야 합니다.

<Tabs>
<Tab title="Android">

</Tab>

<Tab title="iOS네이티브 Unity">

</Tab>

<Tab title="">

</Tab>
</Tabs>

</Accordion>

<div id="record-push-notifications" />

<Accordion title="푸시 알림 기록하기">

앱스플라이어는 Google 클라우드 메시징 또는 Apple 푸시 알림 서비스를 포함하여 모든 벤더의 푸시 알림 캠페인 측정을 지원합니다.

<Anchor target="_blank" href="/marketers/ko/docs/measuring-push-notification-re-engagement-campaigns">푸시 알림 측정에 대해 자세히 알아보기</Anchor>.

</Accordion>

<div id="user-invite-attribution" />

<Accordion title="앱 추천 어트리뷰션">

기존 사용자가 친구나 아는 사람을 앱의 신규 사용자로 초대할 수 있도록 만드는 것은 추가적인 앱 설치를 유도하는 핵심 성장 요소가 될 수 있습니다. 앱스플라이어를 사용하면 앱 내 사용자 초대에서 발생한 설치를 어트리뷰트하고 기록할 수 있습니다.

<Anchor target="_blank" href="/marketers/ko/docs/user-invite-attribution">사용자 초대 어트리뷰션에 대해 자세히 알아보기</Anchor>.

</Accordion>

<div id="crosspromotion-attribution" />

<Accordion title="크로스 프로모션 어트리뷰션">

크로스 프로모션 앱은 앱의 추가 설치를 이끄는 주된 성장 요소가 될 수 있습니다. 앱스플라이어는 사용자가 현재 가지고 있는 앱에서 다른 앱으로 크로스 프로모션으로 시작된 인스톨을 어트리뷰트하고 기록할 수 있게 합니다.  

<Anchor target="_blank" href="/marketers/ko/docs/cross-promotion-attribution-for-marketers">크로스 프로모션 어트리뷰션에 대해 자세히 알아보기</Anchor>.

</Accordion>

<div id="attribute-app-sessions-initiated-from-owned-websites-domains" />

<Accordion title="광고주 소유 웹사이트(도메인)로부터 발생한 앱 세션을 어트리뷰션 합니다.">

(원링크 없이) 딥링킹에 대해 앱 링크 또는 유니버설 링크를 사용하는 앱 소유자는 자신의 앱(<Anchor target="_blank" href="https://developer.android.com/studio/write/app-link-indexing#associatesite">안드로이드</Anchor>/<Anchor target="_blank" href="https://developer.apple.com/documentation/xcode/supporting-associated-domains?preferredLanguage=occ">iOS</Anchor>)과 연결된 도메인을 통해 시작된 세션으로 어트리뷰트하는 SDK를 구성할 수 있습니다.

예를 들어:

* 사용자는 Google을 검색하여 사용자의 도메인 **www.example.com**을 클릭합니다.
* 이 때, 엔드유저의 기기에 앱이 설치되지 않았으면 웹사이트(www.example.com)으로 리디렉션 됩니다.
* 기기에 앱이 설치되어 있으면, www.example.com과 연관된 앱으로 딥링킹됩니다. 세션은 SDK에 설정된 미디어 소스(`pid`pidpid 파라미터)로 어트리뷰트됩니다.

개발사 설명서는 다음과 같이 제공됩니다.

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">안드로이드 SDK 참조</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">iOS SDK 참조</Anchor>

**팁!** 팁! <Anchor target="_blank" href="/marketers/ko/docs/convert-your-mobile-web-visitors-to-app-users#attribution-solutions">원링크 스마트 스크립트</Anchor>는 앱 소유자가 웹사이트 방문자를 앱 사용자로 전환하도록 지원합니다.

</Accordion>

## 사용자 프라이버시

GDPR과 CCPA 및 비즈니스 요구 사항과 같은 규정을 검토하고 구현할 옵트인 및 옵트아웃 정책을 결정합니다.

**모든 플랫폼**

<div id="optout-policy" />

<Accordion title="옵트아웃 정책">

어떤 경우에는 개발자에게 앱스플라이어 SDK를 설정하여 데이터 수집을 중지하거나 제한하도록(예를 들어, GDPR 및 CCPA 규정을 준수하도록) 지시해야 할 수도 있습니다.

</Accordion>

<div id="exclude-partners-from-getting-data" />

<Accordion title="파트너사와 데이터 공유 차단하기">

광고주는 특정 사용자들의 사용자 레벨 데이터를 광고 네트워크/파트너와 공유하지 않을 경우가 있습니다. 사용자 정보를 공유하지 않는 이유는 다음과 같습니다.

* CCPA나 GDPR과 같은 개인정보 보호 정책 준수
* 사용자 옵트아웃(개인정보 제 3자와의 공유 거부)
* 파트너사(애드 네트워크, 타사)가 경쟁사이기도 한 경우

<Tabs>
<Tab title="안드로이드 네이티브">

</Tab>

<Tab title="iOS 네이티브">

</Tab>

<Tab title="Unity">

</Tab>

<Tab title="React Native">

</Tab>
</Tabs>

</Accordion>

* 또는

<Tabs>
<Tab title="Android">

</Tab>

<Tab title="iOS 네이티브">

</Tab>
</Tabs>


**iOS 전용**

<div id="strictmode-sdk" />

<Accordion title="Strict 모드 SDK">

앱스플라이어 strict mode SDK를 사용하여 IDFA 수집 기능과 AdSupport 프레임워크 의존성을 완전히 제거합니다. (예를 들어 <Anchor target="_blank" href="https://developer.apple.com/app-store/review/guidelines/#kids-category">자녀용 앱</Anchor> 개발 시)

자녀용 앱을 판매할 경우 개발자는 일반 SDK 대신 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">Strict 모드 SDK</Anchor>를 인스톨해야 합니다. **참고:** 참고: IDFV는 계속 사용 가능합니다.

</Accordion>

<div id="disable-ad-frameworks" />

<Accordion title="광고 프레임워크를 비활성화합니다.">

AdSupport와 iAd framework를 비활성화하기 위해, 앱스플라이어 SDK는 다음과 같은 setter를 제공합니다.

<Tabs>
<Tab title="iOS native">

</Tab>

<Tab title="Unity">

</Tab>
</Tabs>

</Accordion>

<div data-zendesk-anchors="additional-attribution-methods=%EC%B6%94%EA%B0%80-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%B0%A9%EB%B2%95 01H8W01DRHQHJKNMJA24PR5S2T=%EC%B6%94%EA%B0%80-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%B0%A9%EB%B2%95 01H8W01DRHXR0BRCB9RECH7KS1=tv-attribution 01H8W01DRHMZN2P0FKADM0NQ96=measure-uninstalls 01H8W01DRH2HM3N06YAGRZ030F=preinstalled-apps sessions=%EC%84%B8%EC%85%98 01H8W01DRHD3EZBQT0ZKDMM1QB=%EC%84%B8%EC%85%98 01H8W01DRH2SR3NBQSMSQ6QR6K=custom-time-between-sessions 01H8W01DRH4NGYYABE274DJ1A5=background-sessions-for-utility-apps owned-media=%EC%86%8C%EC%9C%A0-%EB%A7%A4%EC%B2%B4 01H8W01DRHV8H3QFJX5QKABK5E=%EC%86%8C%EC%9C%A0-%EB%A7%A4%EC%B2%B4 01H8W01DRHJS8MM3ZQX2RX4JJG=resolve-wrapped-deep-link-urls 01H8W01DRHHDEEXP8GDFX9134R=record-push-notifications 01H8W01DRHZDB82AB63JKE1B6V=user-invite-attribution 01H8W01DRHVR8JHZCJ6SW8TAA6=crosspromotion-attribution 01H8W01DRHXSYWCS6RW2ZVDKXT=attribute-app-sessions-initiated-from-owned-websites-domains user-privacy=%EC%82%AC%EC%9A%A9%EC%9E%90-%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C 01H8W01DRHJFB71DVJ64QWJME4=%EC%82%AC%EC%9A%A9%EC%9E%90-%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C 01H8W01DRHD7FDERJZFJP9GG0T=optout-policy 01H8W01DRHYNYYFTF82XZ21J3P=exclude-partners-from-getting-data 01H8W01DRJD0XRX4VX03T3YEKX=strictmode-sdk 01H8W01DRJKJFFMBMJ4KNTXPXE=disable-ad-frameworks" />
