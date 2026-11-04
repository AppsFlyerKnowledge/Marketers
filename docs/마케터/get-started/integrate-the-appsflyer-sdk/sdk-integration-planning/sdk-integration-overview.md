---
title: SDK 연동 개요
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Integration
    - Advertisers
    - firetv
    - fire tv
    - Advertiser
    - Developer
    - appuid
    - anonymous
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2012-12-26T14:34:58Z'
  edited_at: '2026-10-14T10:36:57Z'
  id: 207032126
  locale: ko
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ko/articles/207032126
---
> **한눈에 보기:** 사용 가능한 앱스플라이어  SDK 기능을 알아보고 안드로이드 또는 iOS 앱에 적용할 API를 판단하세요.

<div id="about-the-sdk" />

## SDK 정보

SDK 연동에 대한 전반적인 내용을 아래 영상에서 확인하실 수 있습니다.

<Embed title="SDK 연동 개요" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/4iybquc6q3" providerUrl="https://fast.wistia.com" />

SDK는 앱 설치 및 이벤트 기록 기능을 제공합니다. 인스톨, 세션, 인앱 이벤트를 기록할 수 있습니다. 인앱 이벤트에는 예를 들어, 인앱 구매나 게임에서 레벨업하는 것이 포함됩니다. 이러한 이벤트 기록은 ROI와 유저 품질을 평가하는 데 도움이 됩니다.

이 문서는 SDK V6+의 연동 프로세스를 설명하고, 광고주(앱 소유자)와 제품 관리자가 안드로이드 또는 iOS 앱과의 앱스플라이어 SDK 연동을 계획하는 데 도움을 줍니다.

추가 문서에는 다음이 포함됩니다:

<Tabs>
<Tab title="안드로이드 네이티브">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">개발자를 위한 SDK 설치 문서</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-android-sdk-release-notes">릴리스 노트</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference">개발자를 위한 SDK 참조 문서</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/fill-out-google-safety-section-form">구글 플레이의 데이터 보안 섹션</Anchor>

</Tab>

<Tab title="iOS 네이티브">

* <Anchor target="_blank" href="/marketers/ko/docs/updating-to-ios-sdk-v6-and-plugins">iOS SDK V6으로 업데이트 중입니다</Anchor>. iOS SDK V5.4.4는 iOS 14에서 완벽하게 작동합니다. 그러나 향후 iOS 출시와의 호환성을 보장하기 위해 SDK V6.X를 채택하는 것이 좋습니다.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">개발자를 위한 SDK 설치 문서</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes">릴리스 노트</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference">개발자를 위한 SDK 참조 문서</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/preparing-for-the-app-store-review-nutrition-labels">애플 앱 스토어 검토 준비—“영양성분표”(개인정보 처리 라벨)</Anchor>

</Tab>

<Tab title="Unity">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">개발자를 위한 SDK 설치 문서</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api">개발자를 위한 SDK 참조 문서</Anchor>

</Tab>

<Tab title="React Native">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">개발자를 위한 SDK 설치 문서</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api">개발자를 위한 SDK 참조 문서</Anchor>

</Tab>
</Tabs>

<div id="sdk-compatibility" />

## SDK 호환성

앱스플라이어 SDK는 다음 플랫폼과 호환됩니다:

<Tabs>
<Tab title="안드로이드">

* 안드로이드 V4.0부터
* 스마트 TV(Amazon Fire TV 포함) 등 모바일이 아닌 Android 기반 플랫폼. <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts">CTV 개요 보기</Anchor>
* Amazon 및 Baidu와 같은 안드로이드 앱을 위한 <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution">외부 마켓</Anchor>

</Tab>

<Tab title="iOS">

* iOS 9+ (아이폰, 아이팟, 아이패드)
* tvOS 9+ (Apple TV)
* Apple <Anchor target="_blank" href="https://developer.apple.com/library/content/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/UnderstandingandPreparingfortheIPv6Transition/UnderstandingandPreparingfortheIPv6Transition.html#//apple_ref/doc/uid/TP40010220-CH213-SW1">IPv6 DNS64/NAT64</Anchor> 네트워크와 호환됩니다.

SDK는 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model">여러 어트리뷰션 방법</Anchor>을 지원합니다. 사용되는 어트리뷰션 방법은 다음 사항에 따라 판단됩니다.

* 사용자 디바이스에 설치된 iOS 버전
* 앱에 설치된 iOS SDK 버전

<table><thead><tr><th><span>지원되는 어트리뷰션 방법</span></th><th><span>iOS 버전</span></th><th><span>iOS SDK 지원</span></th><th><span>주의 사항</span></th></tr></thead><tbody><tr><td rowspan="2"><span>확률적 모델링</span></td><td><p><span>8 – 14.4</span></p></td><td>5.0.0+</td><td> </td></tr><tr><td><p><span>14.5+</span></p></td><td><span>6.0.3+</span></td><td><span>확률적 모델링은 온드 미디어, 크로스 프로모션, 동의된 웹-앱 흐름의 컨텍스트로 제한됩니다.</span></td></tr><tr><td rowspan="2"> <span>ID 매칭</span><br/><span></span><br/> </td><td><span>8 - 13</span></td><td>5.0.0+</td><td><span>사용자는 LAT(광고 추적 제한)를 이용해 옵트아웃할 수 있습니다.</span></td></tr><tr><td><span>14.5+</span></td><td><span>6.0.3+</span></td><td><p>앱 추적 투명성(ATT) 및 사용자 동의가 필요합니다. 더 자세한 내용은  <a href="./basic-sdk-integration-guide#configure-app-tracking-transparency-att-support" target="_blank">iOS SDK에서 ATT 지원 설정</a>을 참고하세요.</p></td></tr><tr><td rowspan="2"><p><a href="./skadnetwork-skan-solution-guide" target="_blank"><span>SKAdNetwork</span></a></p></td><td><p><span>11.3 - 13</span></p></td><td rowspan="2"><p><span>6.2.3</span><br/><span></span><br/></p></td><td><p>SKAdNetwork(SKAN) 솔루션은 <span> 인스톨 어트리뷰션 용도로 </span><a href="https://developer.apple.com/documentation/storekit/skadnetwork" target="_blank">SKAN</a> <span> 사양에 따라 제한되며, 전환 값은 없습니다.</span></p></td></tr><tr><td><p><span>14+</span></p></td><td><ul><li>SKAN은 ATT 설정에 관계없이 항상 iOS 및 SDK 수준에서 가능합니다.</li><li>마케터는 앱스플라이어 대시보드에서 SKAN을 활성화할 수 있습니다.</li></ul></td></tr></tbody></table>

SDK V6.0.8부터 <Anchor target="_blank" href="/marketers/ko/docs/apple-app-clips-integration-guide">Apple App Clips 어트리뷰션</Anchor>이 가능합니다. Apple App Clips에 대한 <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/apple-app-clips">블로그 포스트</Anchor>도 읽어보세요.

</Tab>
</Tabs>

<div id="sdk-integration" />

## SDK 연동

SDK를 설치하고 연동하는 과정에는 제품 관리자와 모바일 개발자가 함께 협력해야 합니다. **앱에 SDK를 연동하기 전에**, 모든 연동 작업을 검토하고 앱에서 사용할 기능을 고려하세요.

<div id="sdk-planning-checklist" />

### SDK 계획 체크리스트

시작을 돕기 위해서, 계획 과정에 도움을 줄 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTD4OimHC93iw2AJCcAY45yAc9lOBfJe8PskI_0NFZTnWnrIq1hjPBvCztkbom9acMDDd4d1d5mMFfi/pub?output=xlsx">체크 리스트</Anchor>를 준비했습니다. 각 작업에 대한 마케터 및 개발자 문서 링크가 있습니다.

<div id="sdk-integration-tasks" />

### SDK 연동 작업

기본 SDK 연동에는 다음 작업들이 포함됩니다. 시간 추정은 일반적인 지침으로만 제공합니다.

| 기본 SDK 연동 작업 | 계획 시간 |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#애플리케이션-내-개발-키-구현">앱스플라이어 개발 키</Anchor>를 검색하여 설치 및 연동 지침과 함께 개발자에게 링크를 발송하세요. | 15분 |
| <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#어트리뷰션">어트리뷰션 고려사항</Anchor>을 검토하고 수집할 디바이스 식별자를 판단하세요. | 30분 |
| 측정할 <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#인앱-이벤트-기록">인앱 이벤트</Anchor>를 정하고  이벤트 이름과 파라미터를 개발자에게 발송하세요. | 1시간 |
| 사용할 <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#원링크를-사용한-딥링킹">딥링킹 메서드</Anchor>를 정하세요. | 30분 |
| 어트리뷰션 데이터에 <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#어트리뷰션-및-딥링킹-데이터-액세스">액세스할</Anchor> 방법을 판단하세요. | 30분 |
| 기본 연동이 완료되면, 앱스플라이어 대시보드에 액세스 권한을 가진 모든 계정 사용자가 <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#sdk-연동-테스트">기본 테스트</Anchor>를 수행할 수 있습니다.<br /><br />개발자는 <Anchor target="_blank" href="/marketers/ko/docs/testing-the-sdk-integration-for-marketers#testing-in-the-development-environment">개발 환경</Anchor>에서 디버그 로그를 활용할 수 있습니다. | 1시간 |

귀사의 모바일 개발자와 협력하여 SDK에 이러한 추가 API를 구현하세요.

| 추가 SDK 연동 작업 | 계획 시간 |
| --- | --- |
| 귀사의 앱에서 <Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#추가-어트리뷰션-방법">추가 어트리뷰션</Anchor> 설정(예: 앱 삭제 측정 또는 써드 파티 앱 스토어의 인스톨 어트리뷰션)이 필요한지 판단하세요. | 30분 |
| <Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#세션">유저 세션 리포팅</Anchor>을 판단하세요. | 30분 |
| <Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#소유-매체">온드(owned) 미디어 소스</Anchor>에 사용할 어트리뷰션 방법을 판단하세요. | 1시간 |
| 앱이 개인정보 보호 규정(GDPR, CCPA)을 준수하도록 <Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#사용자-프라이버시">유저 개인정보 보호</Anchor> 정책을 관리하세요. | 1시간 |

<div id="note" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC 및 콘솔 플랫폼 개요</Anchor>

<div data-zendesk-anchors="about-the-sdk=sdk-%EC%A0%95%EB%B3%B4 h_01H9FHRVKE6BHGW05G6YMKF737=sdk-%EC%A0%95%EB%B3%B4 sdk-compatibility=sdk-%ED%98%B8%ED%99%98%EC%84%B1 h_01H9FHRVKEQ837Q0GFECNPPAN2=sdk-%ED%98%B8%ED%99%98%EC%84%B1 sdk-integration=sdk-%EC%97%B0%EB%8F%99 h_01H9FHRVKEN0MMGTSD362FTWPS=sdk-%EC%97%B0%EB%8F%99 sdk-planning-checklist=sdk-%EA%B3%84%ED%9A%8D-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8 h_01H9FHRVKE468M1RTMF7VTYV1R=sdk-%EA%B3%84%ED%9A%8D-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8 sdk-integration-tasks=sdk-%EC%97%B0%EB%8F%99-%EC%9E%91%EC%97%85 h_01H9FHRVKERHXY19R97EN86EGP=sdk-%EC%97%B0%EB%8F%99-%EC%9E%91%EC%97%85 h_01H9FHRVKE88CXGH8G7E26ZXT2=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
