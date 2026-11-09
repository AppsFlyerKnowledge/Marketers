---
title: iOS 14, ATT 및 SKAN에 대한 빠른 시작 안내서 및 FAQ
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Agencies
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-08-11T09:19:23Z'
  edited_at: '2026-10-14T10:39:18Z'
  id: 360011890298
  locale: ko
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ko/articles/360011890298
---
> **간단히 보기**: 요약: iOS 14.5부터 Apple은 <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency">AppTrackingTransparency</Anchor> (ATT) 약관을 구현하고 준수할 것을 요구합니다. ATT는 귀하의 앱이 최종 사용자에 대한 데이터를 수집하고 앱과 웹사이트 전반에서 추적할 목적으로 이를 다른 회사와 공유하는 경우 ATT 동의 프롬프트를 사용하고 게시자와 광고주 앱 모두에서 사용자 동의를 받아야 함을 의미합니다. 추적하지 않으면 프롬프트를 표시할 필요가 없습니다.

<Image align="center" alt="iOS14-consent-pre-ATT-enforcement-6522_Cover-image_917x480.jpg" src="https://files.readme.io/622b57cf6b6b7ad9472b3d072f44d9b451e82fec6b0c918427e39e9e6700602e-360019478118.jpg" />

<div id="attribution-measurement-in-an-att-environment" />

## ATT 환경에서의 어트리뷰션 측정

유료 앱-투-앱 캠페인의 경우 SKAN은 확정적 어트리뷰션 결과를 제공합니다. 온드 미디어, 웹-투-앱 및 Apple Search Ads와 같은 다른 캠페인 유형은 앱스플라이어 기존 어트리뷰션 도구를 사용합니다. 기존 도구는 장기적인 LTV 측정을 제공하는 반면 SKAN은 인스톨 후 짧은 실치후 포스트 동안 사용자 성과를 측정합니다.

요약하자면, 완전한 이해를 하기 위해 SKAN과 앱스플라이어 기존 솔루션이 서로를 보완하므로 둘 다 사용하십시오.

본 기사는 광고주에게 SKAN 및 ATT에 대한 소개를 제공합니다. 앱스플라이어 플랫폼을 잘 알고있는 광고주를 위한 것입니다.

<div id="skan-solution-principles" />

<Accordion title="SKAN 솔루션 원칙">

앱스플라이어는 iOS의 SKAN 포스트백을 사용하여 데이터 집약형 iOS 어트리뷰션 결과를 제공합니다. 이러한 포스트백은 iOS가 애드 네트워크로 발송한 후, 애드 네트워크는 이를 앱스플라이어에 전달합니다. 포스트백에는 광고주가 설정한 전환 값(CV)으로 보강된 익명화된 어트리뷰션 기록이 포함됩니다. CV는 앱 설치 후 초기 기간 동안 유저의 가치를 측정하는 지표입니다.

앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">SKAN 솔루션</Anchor>은 광고주에게 다음을 제공합니다.

* 모든 애드 네트워크로부터 받은 포스트백을 집계하여 얻은 대시보드와 보고서의 SKAN 데이터는 비용 등의 추가 데이터 포인트로 보강됩니다.
* 앱스플라이어 전환 스튜디오를 통해 앱 코드를 변경할 필요 없이 CV가 측정하는 내용을 제어할 수 있는 기능. CV는 수익, 참여 또는 전환 이벤트를 측정하는 데 사용할 수 있습니다.

**SKAN 제한 사항**

* 캠페인 캠페인: Apple Search Ads, 크로스 프로모션 캠페인 및 모바일 웹 지원 인스톨을 지원하지 않습니다.

**SKAN 플로우**

<Image align="center" alt="SKAN_흐름_-_친화도_도표_2.png" src="https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png" />

1. 광고주는 앱스플라이어 컨버전 스튜디오에서 SKAN 측정 설정을 지정합니다.
2. 사용자가 처음으로 앱을 실행합니다.
3. 각 기간 동안 앱스플라이어는 사용자 작업 및 정의된 CV 스키마를 기반으로 CV를 설정합니다.
4. 기간이 종료되면 iOS는 애드 네트워크에 포스트백을 보내고, 앱스플라이어에도 포스트백 사본을 발송합니다. 포스트백은 다소 지연되어 도착할 수 있습니다.
   * SKAN 4 측정 기간 1의 경우: 0-24시간
   * SKAN 4 측정 기간 2-3의 경우: 0-24시간
   * SKAN 3의 경우: CV값이 가장 최근에 증가한 후 24&#126;48시간.
5. iOS 디바이스에서 앱스플라이어로 직접 발송된 포스트백 사본은 광고주가 설정한 엔드포인트로 전달됩니다. SKAN 포스트백 사본을 앱스플라이어로 발송을 참조하세요.
6. 광고 네트워크는 개선된 포스트백을 앱스플라이어로 전달하거나 SRN은 API에 의한 포스트백 데이터를 전달합니다.
7. 앱스플라이어는 CV를 유효성 검증하고 디코딩합니다. 디코딩된 데이터는 대시보드, 보고서, API를 통해 앱스플라이어에서 제공되기 전에 기록되고 어트리뷰션됩니다.

</Accordion>

<div id="att-principles" />

<Accordion title="ATT 원칙">

ATT 프롬프트는 광고주가 데이터를 수집하고 공유할 수 있도록 명시적인 사용자 동의를 얻을 수 있는 방법을 광고주에게 제공합니다. iOS 14.5에서 시작하여 IDFA는 사용자가 프롬프트를 통해 동의한 경우에만 사용할 수 있습니다.

게시자 및 광고주 앱 모두 프롬프트를 표시합니다. 사용자가 두 앱 모두에서 동의를 제공하면 사용자가 *추적*에 동의한다는 의미이며 Apple은 광고주가 다른 회사 소유의 앱 간에 사용자를 추적하도록 허용합니다.

**ATT 설정**

ATT는 다음 표에 나열된 값 중 하나로 설정됩니다.  처음에 iOS는 ATT를 결정되지 않음 또는 제한됨으로 설정합니다.

사용자를 *확인되지 않음*에서 *승인됨*으로 변환하기 위해 동의 프롬프트를 사용하는 것은 선택 사항입니다. 단, 프롬프트를 표시하지 않으면 *인증*을 받을 수 없습니다.

| ATT 값 | 사용 가능 IDFA | 비고 |
| --- | --- | --- |
| 제한된 | 아니요 | <ul><li>사용자 연령 및 기타 기준에 따라 Apple에서 결정합니다. 기기 사용자가 변경할 수 없습니다.</li><li>이 사용자에게 프롬프트를 표시할 수 없습니다.</li></ul> |
| 미정(iOS 14.4까지) | 예 | 기본값 |
| 정해지지 않음<br /><br />(iOS 14.5부터) | 아니요 | 기본값 |
| 거부됨 | 아니요 | 다음 중 하나라도 해당되면 발생합니다:<ul><li>프롬프트 표시 후 설정</li><li>유저가 *앱 추적 요청 허용*(디바이스 수준의 마스터 스위치)을 껐습니다.</li><li>디바이스에 iOS 14를 설치하기 전에 LAT가 켜져 있었습니다.</li></ul> |
| 승인됨 | 예 | 프롬프트 표시 후 설정 |

**ATT 영향**

ATT로 인해 많은 사용자가 동의하지 않고 IDFA를 사용할 수 없으며 추적이 허용되지 않습니다. 결과적으로 iOS 14.5까지 사용자 수준 어트리뷰션 리포트에 의존했던 광고주는 일부 분석을 집약형 어트리뷰션 방법 및 리포트로 전환해야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model">앱스플라이어 어트리뷰션 모델</Anchor>.

앱의 어트리뷰션 관련 데이터는 다양한 소스에서 제공됩니다. 사용 가능한 식별자와 사용하는 식별자가 다릅니다. 대부분의 데이터는 기존의 어트리뷰션 도구를 사용하여 표시됩니다. 그러나 SKAN을 사용한 인스톨에 대한 리포트는 SKAN 대시보드를 통해 이루어집니다.

</Accordion>

<div id="which-dashboard-has-the-install" />

<Accordion title="어떤 대시보드가 설치되어 있습니까?">

iOS14에서 인스톨은 기존 대시보드와 SKAN 대시보드 모두에 어트리뷰트할 수 있습니다. 또한 미디어 소스 컨텍스트에 따라 한 대시보드에서는 오가닉으로, 다른 대시보드에서는 논오가닉으로 표시될 수 있습니다.

</Accordion>

<div id="ios-attribution-and-privacy-important-knowledge" />

## iOS 14 중요한 지식

<div id="ios-attribution-skan-and-privacy-articles-and-links" />

#### iOS 14 및 SKAN 기사 및 링크

| 영역 | 기사 |  |
| --- | --- | --- |
| SKAN | <Anchor target="_blank" href="/marketers/ko/docs/skan-raw-data-reports">SKAN 로데이터 필드</Anchor> | did\_win 및 SKAN 3.0을 지원하는 추가 로데이터 SKAN 필드 |
| SKAN | <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">SKAN 솔루션</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">앱 인스톨에서 대시보드 업데이트까지의 시간</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#organic-metrics-in-the-context-of-skadnetwork">SKAN의 문맥에서 오가닉 지표</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#appsflyer-attribution-vs-skan-attribution">앱스플라이어 어트리뷰션 대 SKAN 어트리뷰션</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#faq-skan-discrepancies">FAQ SKAN 차이</Anchor></li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/ko/docs/skan-interoperation">SKAN 파트너 상호 운용성</Anchor> (문서 섹션) | <Anchor target="_blank" href="/marketers/ko/docs/skan-integrated-partners-list">SKAN 연동 파트너 목록</Anchor> |
| SKAN | <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-interoperation-with-meta-ads">메타 광고 및 앱스플라이어 SKAN 통합</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq">문제 해결 및 불일치</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook">측정 및 타이밍 차이</Anchor></li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/ko/docs/skan-interoperation-with-snapchat">스냅챗과 앱스플라이어 SKAN 상호 운용성</Anchor> | <Anchor target="_blank" href="/marketers/ko/docs/skan-interoperation-with-snapchat#discrepancies-guide">불일치 가이드</Anchor> |
| 프라이버시 | <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">데이터 집약형 고급 프라이버시 보호(AAP)</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework#aap-영향을-받는-기능">AAP 영향을 받는 기능</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework#aap-central-switch">AAP 끄기 및 켜기</Anchor></li></ul> |
| 프라이버시 | <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">제한된 미디어 소스</Anchor> | <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields">제한된 로데이터 필드</Anchor> |
| iOS 14 | <Anchor target="_blank" href="/marketers/ko/docs/preparing-for-the-app-store-review-nutrition-labels">영양 라벨 - 앱 스토어 검토 준비</Anchor> |  |
| iOS 14 | <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">앱에서 ATT 설정</Anchor> (SDK 안내 개발자) |  |
| iOS 14 | <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns">Google, 메타 광고 등과 같은 자체 보고 네트워크(SRN) 정보</Anchor> | SRN 인스톨은 어디에 리포트됩니까? |
| 결제 | <Anchor target="_blank" href="https://content.appsflyer.com/ios-14-hub/billing/">iOS 앱에 대한 청구</Anchor> |  |

<div id="ios-14-impact-on-attribution-and-measurement" />

<Accordion title="iOS 14가 어트리뷰션 및 측정에 미치는 영향">

<div id="metrics" />

#### **측정 지표**

ATT로 인해 ATT 동의하지 않은 사용자와 관련된 지표가 다음과 같이 영향을 받을 수 있음을 고려하십시오.

| 측정 지표 | 증가 | 감소 | 비고 |
| --- | --- | --- | --- |
| 논오가닉 대 오가닉 | 오가닉 | 논오가닉 |  |
| 리인스톨 대 인스톨 | 인스톨 | 재설치 |  |
| 리타겟팅 | 오가닉 인스톨 및 인앱이벤트 | 리인게이지먼트, 리어트리뷰션 |  |
| Apple Search Ads | -- | -- | 변경되지 않음. 동의하는 사용자와 동의하지 않은 사용자 모두 올바르게 어트리뷰트됩니다. |

<div id="deep-linking" />

#### **딥링킹**

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-legacy-apis#deferred-deep-linking">onConversionDataSuccess의 레거시 메서드</Anchor>를 사용하는 디퍼드 딥링크는 개인 정보 보호로 인해 사용할 수 없는 어트리뷰션 데이터가 필요하기 때문에 iOS 14.5 이상에서 작동하지 않을 수 있습니다.

 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl-1">통합 딥링킹(UDL)</Anchor>를 사용하는 것이 좋습니다. 더 알아보기

</Accordion>

<div id="faqios-attribution-and-att" />

## FAQ—iOS 14 이상

<div id="what-happens-to-an-app-using-an-sdk-version-before-v6" />

<Accordion title="V6 이상의 SDK 버전을 사용하는 앱은 어떻게 됩니까?">

V6.0 이전 SDK 버전을 사용하는 앱의 경우:

* SKAdNetwork 및 Apple Search 광고는 작동하지 않습니다.
* 앱을 앱 스토어에 제출하면 거부될 것으로 예상합니다.

</Accordion>

<div id="is-it-mandatory-to-display-the-att-prompt" />

<Accordion title="ATT 프롬프트를 반드시 표시해야 합니까?">

아닙니다. 사용자를 *추적*하거나, IDFA를 수집하거나, 또는 둘 다를 수행하려는 경우에만 ATT 동의를 요청하면 됩니다.

</Accordion>

## FAQ—SKAN

<div id="how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4" />

<Accordion title="포스트백이 언제 수신되고 SKAN 3인지 SKAN 4인지 어떻게 알 수 있습니까?">

수신하는 SKAN 포스트백 유형은 Conversion Studio에서 사용하는 모드, 사용하는 광고 네트워크, 사용자의 iOS 버전 등 다양한 요인에 따라 결정됩니다.

이러한 요인은 다음에 영향을 미칩니다.

* <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#principles-and-flow">더 알아보기</Anchor>
* SKAN 3의 경우 활동 기간에 따라 다릅니다. 참고: 일러두기: Conversion Studio가 SKAN 4는 아니지만 광고 네트워크 서명이 있는 경우 기간은 액티비티 추적 기간 또는 48시간 중 더 짧은 기간을 기준으로 합니다.
* 이는 기간이 종료되는 시기에 따라 다릅니다. <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide?query=skan%20faq#timing-from-app-install-until-dashboard-and-reports-update">더 알아보기</Anchor>
* 롤링 타이머: SKAN 3의 경우 활동 기간을 최대 63일까지 연장할 수 있습니다. 포스트백은 기간이 종료된 후에만 도착합니다.

다음 순서도에서 이에 대해 자세히 설명합니다.

<Image align="center" alt="SKAN_4_matrix_-_Page_8__1_.png" src="https://files.readme.io/0dbd4cae34d9f9fed80dbe835485789dab75d46dbb38de055f454d01efb97350-13756140934545.png" />

</Accordion>

<div id="in-skan-am-i-limited-to-100-campaign-ids-per-ad-network" />

<Accordion title="SKAN에서는 광고 네트워크당 특정 수의 소스 식별자/캠페인 ID로 제한됩니까?">

네. 예. 이전에는 캠페인 ID 100개로 제한되었습니다. 그러나 SKAN 4부터 캠페인 ID를 계층적 소스 식별자라고 하며 제한은 10,000개입니다. 소스 식별자는 4자리 정수입니다.

광고 네트워크는 SKAN 소스 식별자를 캠페인 ID에 매핑합니다.

</Accordion>

<div id="what-is-the-use-case-for-skan-raw-data" />

<Accordion title="SKAN 로데이터의 사용 사례는 무엇입니까?">

* 로데이터를 사용하여 집계 API를 통해 사용할 수 없는 차원을 집계합니다.
* SKAN 로데이터를 사용하도록 기존 로데이터 가져오기 프로세스를 쉽게 조정합니다.

</Accordion>

<div id="why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio" />

<Accordion title="제가 받은 전환 가치가 앱스플라이어 Conversion Studio의 저의 설정과 일치하지 않는 이유는 무엇입니까?">

일반적으로 전환 가치를 설정할 수 있는 기능을 가진 앱의 다른 SDK 및 이것이 앱스플라이어 SDK 및 앱스플라이어에서 구성한 전환 가치와 충돌하기 때문입니다. 귀사의 앱에 전환 값을 설정하는 다른 SDK가 통합되어 있지 않은지 확인하세요.

</Accordion>

<div id="why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports" />

<Accordion title="SKAN 대시보드의 집계 데이터가 SKAN 데이터 락커 리포트의 로데이터 수치와 일치하지 않는 이유는 무엇입니까?">

종종 이러한 불일치는 잘못된 위치에서 데이터 락커 리포트를 보는 것으로 하여 발생합니다. Google의 데이터를 수신하는 데는 최대 13일이 소요될 수 있습니다. 그리고 로데이터 리포트에서 데이터는 누적되지 않고 수신된 날에 기록됩니다. 따라서 특정 날짜와 관련된 인스톨에 대한 올바른 지표를 얻으려면 해당 날짜 이후 13일 후의 모든 리포트도 확인해야 합니다.

예시: 예시: 6월 12일 리포트에 6월 11일에 발생한 Google의 인스톨 100건이 표시됩니다. 6 월 24 일 리포트에는 6 월 11 일에 100 건의 인스톨이 더 발생했다고 기록되어 있습니다. 지난 13일(6월 12일부터 6월 24일까지)의 모든 리포트를 살펴보고 인스톨 시간 또는 광고 네트워크 타임스탬프를 기준으로 집계해야 6월 11일에 발생한 총 인스톨 수 200건을 정확하게 파악할 수 있습니다.

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/getting-started-onboarding-for-marketers#3단계-귀속-설정">앱스플라이어 단계별 시작하기</Anchor>

<div data-zendesk-anchors="attribution-measurement-in-an-att-environment=att-%ED%99%98%EA%B2%BD%EC%97%90%EC%84%9C%EC%9D%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%B8%A1%EC%A0%95 h_01HE0C8YXSXSX003X0671Z97KZ=att-%ED%99%98%EA%B2%BD%EC%97%90%EC%84%9C%EC%9D%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%B8%A1%EC%A0%95 h_01HE0C8YXSCA8M57F1RG4CJ7HK=skan-solution-principles h_01HE0C8YXSSCTQJAPDE27FB1H8=att-principles h_01HE0C8YXS0BFA2M16D1Q2PQYW=which-dashboard-has-the-install ios-14-important-knowledge=ios-14-%EC%A4%91%EC%9A%94%ED%95%9C-%EC%A7%80%EC%8B%9D h_01HE0C8YXS3BH109DF1Y1KNK5P=ios-14-%EC%A4%91%EC%9A%94%ED%95%9C-%EC%A7%80%EC%8B%9D ios-14-and-skan-articles-and-links=ios-14-%EB%B0%8F-skan-%EA%B8%B0%EC%82%AC-%EB%B0%8F-%EB%A7%81%ED%81%AC h_01HE0C8YXSPZKBWXC51Z2636R0=ios-14-%EB%B0%8F-skan-%EA%B8%B0%EC%82%AC-%EB%B0%8F-%EB%A7%81%ED%81%AC h_01HE0C8YXSTCVA8YYR4BQVHVXS=ios-14-impact-on-attribution-and-measurement metrics=%EC%B8%A1%EC%A0%95-%EC%A7%80%ED%91%9C h_01HE0C8YXSJMYN81FKPCA8ATK7=%EC%B8%A1%EC%A0%95-%EC%A7%80%ED%91%9C deep-linking=%EB%94%A5%EB%A7%81%ED%82%B9 h_01HE0C8YXS6ADG1SQCMVP0W69B=%EB%94%A5%EB%A7%81%ED%82%B9 faq%E2%80%94ios-14=faqios-14-%EC%9D%B4%EC%83%81 h_01HE0C8YXSV9VSK1NPG9RCTQW1=faqios-14-%EC%9D%B4%EC%83%81 h_01HE0C8YXS1FFYQJ8YZXP9W9ZV=what-happens-to-an-app-using-an-sdk-version-before-v6 h_01HE0C8YXSKA0325YJSXV81ZB9=is-it-mandatory-to-display-the-att-prompt faq%E2%80%94skan=faqskan h_01HE0C8YXSQKH8ER1Q5VS6Z0NM=faqskan how-do-i-know-when-i%E2%80%99ll-receive-postbacks-and-if-they%E2%80%99ll-be-skan-3-or-skan-4=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXS44YXAN2DV2ZR03GE=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXSCWM892QH0N7YQ8HP=in-skan-am-i-limited-to-100-campaign-ids-per-ad-network h_01HE0C8YXSSWHV45M6P7SQGCRD=what-is-the-use-case-for-skan-raw-data h_01HE0C8YXS8GJKFC23S1R9TWW0=why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio why-doesn%E2%80%99t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE0C8YXS1VW1T50ARJE0MP62=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE7SNR02VQDKG55QP06ECNAR=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
