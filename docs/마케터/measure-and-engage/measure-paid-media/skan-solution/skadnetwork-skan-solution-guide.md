---
title: SKAdNetwork(SKAN) 솔루션 가이드
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - SKAD
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-07-25T21:19:42Z'
  edited_at: '2026-10-14T10:30:15Z'
  id: 360011420698
  locale: ko
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ko/articles/360011420698
---
> **요약**: SKAN을 사용하여 앱 인스톨을 어트리뷰션합니다.

<Image align="center" alt="5754" src="https://files.readme.io/a970d7b0e8da300ded2138f941bf2e891f32d396c8500292534992a4b4449d71-30757780264337.png" />

## SKAN

Apple iOS의 일부인 SKAdNetwork(SKAN)는 사용자의 개인 정보를 보호하면서 캠페인 성과를 측정할 수 있게 합니다. SKAN은 IDFA나 기타 광고 ID 없이 운영됩니다. SKAN은 앱 추적 투명성(ATT) 동의 없이도 작동합니다.

<div id="tip" />

> 👍 **팁**
>
> * iOS 15부터 앱스플라이어에 <Anchor target="_blank" href="/marketers/ko/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">SKAN 포스트백 사본</Anchor>을 발송하는 것이 좋습니다. 이를 통해 앱스플라이어가 포스트백의 전환 값이 조작되지 않았음을 확인할 수 있습니다.
> * 앱스플라이어 SKAN 솔루션에 대해 더 알고 싶으신가요? 앱스플라이어 학습 포털에서 이 짧고 유익한 <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/internal/view/elearning/7810/ios14-and-skadnetwork">과정</Anchor>을 확인해 보세요.

**정의**

* <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">SDK</Anchor><Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">: 앱에 통합된 앱스플라이어 iOS SDK의 현재 버전입니다.</Anchor>
* **SKAN 측정 기간**: SKAN 4+를 위한 것입니다. 사용자 설치 후 활동이 측정되는 3개의 기간(창)이 있습니다.
  * 기간 1: 1-2일
  * 기간 2: 3-7일
  * 기간 3: 8-35일
* **전환 값(CV)**: SKAN 4 측정 기간의 끝이나 SKAN 3 이하의 경우 유저 활동 측정 기간의 끝에서 iOS가 발송한 포스트백에 보고된 유저의 가치 측정값입니다. 앱스플라이어 SDK가 귀사를 대신하여 전환 값을 설정합니다. 그러나 CV를 설정하려면 <Anchor target="_blank" href="/marketers/ko/docs/skan-cv-decode-map-your-cv-to-events">디코드</Anchor>를 사용하여 귀사의 CV 매핑 파일을 업로드하세요.
  * SKAN 4+의 경우, 세밀한 전환 값과 대략적인 전환 값이 모두 있습니다.
* **컨버전 스튜디오**: 인프라 전환 값(CV)을 이벤트에 매핑하기 위한 앱스플라이어 솔루션
* **솔루션:** SDK, 인프라, 컨버전 스튜디오 및 앱스플라이어 플랫폼이 함께 작동합니다. 앱스플라이어 SKAN 솔루션은 대시보드 분석, 보고서 및 포스트백을 통해 광고주와 광고 네트워크에 LTV(유저생애가치) 데이터를 제공합니다.
* **유저 활동 측정 기간:** SKAN 3 이하에 해당됩니다. 첫 번째 앱 실행 후 기본값은 24시간으로 설정된 기간입니다. SKAN 4 이상을 사용하시지만, 유저의 디바이스나 애드 네트워크가 아직 SKAN 4를 지원하지 않는 경우 유저 활동 측정 기간은 48시간입니다.

본 문서는 인프라와 솔루션의 관련 특성을 설명합니다. 측정을 설정하려면 <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio">SKAN 컨버전 스튜디오</Anchor>를 참조하세요.

<div id="about-apple-skan" />

<Accordion title="Apple SKAN 소개">

| 특성 | 설명 |
| --- | --- |
| 필수 조건 | 앱에서 SKAN 사용을 활성화하려면:<ul><li>광고주 앱(귀사의 앱)은 광고되는 앱이 앱스플라이어 SDK*를 구현하여 CV를 설정해야 합니다. 또는 <Anchor target="_blank" href="/marketers/ko/docs/skan-cv-decode-map-your-cv-to-events">디코드 모드</Anchor>를 사용하여 CV를 설정할 수 있습니다.</li><li>퍼블리셔 앱(광고를 표시하는 앱): <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app">소스 앱을 구성</Anchor>해야 합니다.</li><li><Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/registering_an_ad_network">애드 네트워크는 Apple에 등록해야 합니다.</Anchor></li></ul>**\*참고:** 귀사의 앱에 전환 값을 설정하는 다른 SDK가 통합되어 있지 않은지 확인하세요. |
| 지원됨 | <ul><li>지원되는 SKAdNetwork 버전은 iOS 버전에 따라 다릅니다:<ul><li>iOS 11-13: V1 (전환값 없는 인스톨만 지원)</li><li>iOS 14-14.5: V2+ (전환값 있음)</li><li>iOS 14.6-16: V3 (전환값 있음)</li><li>iOS 16.1+: V4+ (세 개의 기간에 대한 전환값과 세분 및 일반값 모두 제공)</li></ul></li><li>앱 간 어트리뷰션</li></ul> |
| 제한 사항 | <ul><li>Apple Search Ads는 지원하지 않습니다.</li><li>모바일 웹은 지원하지 않습니다.</li><li>SKAN 4 이전에는 캠페인 ID 번호가 <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skstoreproductparameteradnetworkcampaignidentifier">1&#126;100 범위로 제한되었습니다.</Anchor> 즉, 앱당 애드 네트워크별로 100개의 고유 값을 가집니다. 애드 네트워크는 앱스플라이어에 캠페인 ID와 이름을 제공합니다. 이는 앱스플라이어 대시보드와 보고서에 반영됩니다.</li><li>SKAN 4에서는 소스 식별자가 1-10,000 범위에 있습니다.</li><li>오가닉 인스톨: SKAN은 오가닉 인스톨을 지원하지 않습니다.</li><li>리인게이지먼트.</li></ul> |
| SKAN 어트리뷰션 원칙 | <ul><li>SKAN은 다음 <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions">어트리뷰션 모델</Anchor>을 사용합니다:<ul><li>유저가 광고를 클릭한 후 30일 이내에 앱을 인스톨(다운로드)하고, 그 이후 60일 이내에 처음으로 앱을 엽니다.</li><li>유저가 광고를 본 후 24시간 이내에 앱을 인스톨(다운로드)하고, 그 이후 60일 이내에 처음으로 앱을 엽니다.</li><li>SKAdNetwork V2.2부터 클릭-쓰루 어트리뷰션이 뷰-쓰루 어트리뷰션보다 우선시됩니다. SKAN 버전은 iOS 버전에 의존합니다.</li><li>iOS가 어트리뷰션을 받은 애드 네트워크에 포스트백을 보냅니다. iOS 15부터 광고주는 포스트백을 앱스플라이어에 직접 사본을 보낼 수 있습니다.</li></ul></li></ul> |
| 군중 익명성 | Apple은 사용자의 개인 정보를 보호하기 위해 제한된 데이터가 포함된 일부 포스트백을 발송합니다. Apple에 따르면, 개인 정보 보호 계층 제한을 위반할 경우 포스트백에 세부 전환 값 또는 대략적인 전환 값, 소스 앱 ID나 전체 소스 식별자가 포함되지 않습니다. <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows">더 보기</Anchor> |

</Accordion>

<div id="appsflyer-skan-solution" />

## 앱스플라이어 SKAN 솔루션

앱스플라이어는 iOS의 SKAN 포스트백을 사용하여 데이터 집약형 iOS 어트리뷰션 결과를 제공합니다. 이러한 포스트백은 iOS가 애드 네트워크로 발송한 후, 애드 네트워크는 이를 앱스플라이어에 전달합니다. 포스트백에는 광고주가 설정한 전환 값(CV)으로 보강된 익명화된 어트리뷰션 기록이 포함됩니다. CV는 앱 설치 후 초기 기간 동안 유저의 가치를 측정하는 지표입니다.

앱스플라이어 SKAN 솔루션은 광고주에게 다음의 기능을 제공합니다.

* 모든 애드 네트워크로부터 받은 포스트백을 집계하여 얻은 대시보드와 보고서의 SKAN 데이터는 비용 등의 추가 데이터 포인트로 보강됩니다.
* 앱스플라이어 컨버전 스튜디오를 통해 앱 코드를 변경하지 않고도 CV에서 측정하는 내용을 제어할 수 있습니다. CV는 수익, 참여 또는 전환 이벤트를 측정하는 데 사용할 수 있습니다.  
  **참고:** 전환 값을 설정할 수 있는 기능은 앱스플라이어 SDK에만 있어야 합니다. 귀사의 앱에 전환 값을 설정하는 다른 SDK가 통합되어 있지 않은지 확인하세요.

<div id="principles-and-flow" />

<Accordion title="원칙과 흐름">

<div id="skan-attribution-flow" />

#### **SKAN 어트리뷰션 흐름**

<Image align="center" alt="SKAN_흐름_-_친화도_도표_2.png" src="https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png" />

1. 광고주는 앱스플라이어 컨버전 스튜디오에서 SKAN 측정 설정을 지정합니다.
2. 유저가 처음으로 앱을 엽니다.
3. 각 기간 동안 앱스플라이어는 유저 행동과 정의된 CV 스키마를 기반으로 CV를 설정합니다.
4. 기간이 종료되면 iOS는 애드 네트워크에 포스트백을 보내고, 앱스플라이어에도 포스트백 사본을 발송합니다. 포스트백은 다소 지연되어 도착할 수 있습니다.
   * SKAN 4 측정 기간 1의 경우: 24-48시간
   * SKAN 4 측정 기간 2-3의 경우: 24-144시간
   * SKAN 3의 경우: CV값이 가장 최근에 증가한 후 24&#126;48시간.
5. iOS 디바이스에서 앱스플라이어로 직접 발송된 포스트백 사본은 광고주가 설정한 엔드포인트로 전달됩니다. <Anchor target="_blank" href="/marketers/ko/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">SKAN 포스트백 사본을 앱스플라이어로 발송</Anchor>을 참조하세요.
6. 애드 네트워크는 강화된 포스트백을 앱스플라이어로 전달하거나 SRN은 API로 포스트백 데이터를 발송합니다.
7. 앱스플라이어는 CV를 유효성 검증하고 디코딩합니다. 디코딩된 데이터는 대시보드, 보고서, API를 통해 앱스플라이어에서 제공되기 전에 기록되고 어트리뷰션됩니다.

SKAdNetwork 인프라의 기능적, 구조적 한계를 극복하기 위해 앱스플라이어 SKAN 솔루션은 다음 표의 특성을 고려합니다.

| 특성 | 설명 |
| --- | --- |
| <span id="data-collection"></span>데이터 수집 | <ul><li>광고주를 위해, SKAdNetwork 포스트백은 여러 애드 네트워크에서 수집됩니다.</li><li>광고주는 각 애드 네트워크와 개별적으로 연동할 필요가 없습니다. 이는 복잡하고 번거로운 작업입니다.</li></ul> |
| <span id="data-validation"></span>데이터 유효성 검증 | <ul><li>포스트백이 Apple에서 서명되도록 보장하여 포스트백 조작 가능성을 줄입니다.</li><li>트랜잭션 ID 필드를 사용하여 포스트백이 고유한지 확인합니다.</li></ul> |
| <span id="data-enrichment"></span>데이터 강화 | <ul><li>다른 데이터 포인트를 통해 SKAdNetwork 포스트백 데이터를 강화하여 완전한 ROI (투자수익률) 분석을 제공합니다. 예를 들어, 애드 네트워크에서 제공한 캠페인 이름 등이 있습니다.</li><li>데이터 포인트에는 노출, 클릭 수, 비용 등이 포함됩니다.</li></ul> |
| <span id="data-delivery"></span>데이터 전달 | 다음을 사용하여 강화된 SKAdNetwork 데이터를 활용할 수 있습니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAdNetwork 솔루션 대시보드</Anchor></li><li>[다운로드 가능한 보고서](/docs/skadnetwork-skan-solution-guide#reporting-options)</li></ul> |
| <span id="seamless-integration"></span>원활한 연동 | <ul><li>완벽한 캡슐화를 통해 앱 설정 페이지에서 광고주가 거의 노력을 들이지 않아도 됩니다.</li><li>코딩이 필요하지 않습니다. 앱에는 최신 SDK 버전이 필요합니다.</li><li>Apple에서 SKAdNetwork 인프라의 예상 변경 사항에 대한 지원이 포함되어 있습니다.</li></ul> |
| <span id="agility"></span>신속성 | 광고주는 필요에 따라 대시보드에서 측정 구성을 변경할 수 있습니다. |

</Accordion>

<div id="conversion-studio" />

<Accordion title="컨버전 스튜디오">

앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio">컨버전 스튜디오</Anchor>는 SKAN 솔루션의 핵심입니다. 이 스튜디오는 모든 전환 값을 최대한 활용할 수 있는 유연성을 제공합니다. CV에 어떤 측정 데이터를 인코딩해야 하는지 정확하게 판단하세요. 여기에는 앱 설치 후 기간 동안 어떤 액티비티를 얼마 동안 측정해야 하는지가 포함됩니다. 여러 측정 모드를 사용하여 귀사의 CV 설정을 구성할 수 있습니다.

| 유형 | 측정 모드 | 설명 | 유저 활동 측정 기간 |
| --- | --- | --- | --- |
| 유연성 | SKAN 4.0<br /><br />[모범 사례] | 설정 가능한 측정 기간 동안 수익, 전환(인앱 이벤트), 인게이지먼트 측정의 조합을 설정하세요. | <ul><li>기간 1: 1-2일</li><li>기간 2: 3-7일</li><li>기간 3: 8-35일</li></ul> |
| 유연성 | <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio#custom">커스텀</Anchor> | 설정 가능한 유저 활동 측정 기간 동안 수익, 전환(인앱 이벤트), 인게이지먼트 측정의 조합을 설정하세요. | 12시간-63일 |
| 고정 | 수익<br /><br />[기본값]<br /><br />[기존] | 다음의 범위 중 하나로 수익을 측정합니다.<ul><li>$1-$630 (10달러 간격)</li><li>$1-$63 ($1 간격)</li><li>$0.01-$0.63 ($0.01 간격)</li></ul> | 24시간 |
| 고정 | 전환<br /><br />[기존] | 1&#126;6개의 인앱 이벤트를 선택하세요. | 24시간 |
| 고정 | 인게이지먼트<br /><br />[기존] | 사용자가 이벤트를 수행하는 횟수 | 24시간 |
| 유연한 | <Anchor target="_blank" href="/marketers/ko/docs/skan-cv-decode-map-your-cv-to-events">디코드</Anchor> | <ul><li>자체 전환 값을 이벤트에 매핑하여 앱에서 직접 설정하세요. 앱스플라이어 SDK를 앱에 연동할 수 없는 경우 이 옵션을 사용하세요. 디코드를 사용하려면 **SKAN 컨버전 스튜디오**에 가서 옵션(⋮)을 클릭한 다음 **커스텀 디코드 매핑 파일 업로드**를 선택하세요.</li></ul> | 12-1512시간(63일) |

</Accordion>

<div id="additional-skadnetwork-information" />

## 추가 SKAdNetwork 정보

<div id="reporting-options" />

<Accordion title="리포팅 옵션">

SKAdNetwork 리포트에는 유저 수준 식별자가 포함되지 않습니다.

| 리포트 이름 | 유형 | 앱스플라이어에서 보강됨 | 전달 방법 | 프리미엄 기능 |
| --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/skan-aggregated-performance-report-api">SKAN 데이터 집약형 성과 리포트.</Anchor><br /><br />인스톨, 인앱 이벤트, 수익의 데이터 집약형 결과입니다. 이 데이터는 SKAN 대시보드에서 찾을 수 있는 데이터와 유사합니다. | 인스톨 날짜 또는 포스트백 도착 날짜를 사용하여 집계합니다. | 예 | API | 아니요 |
| <Anchor target="_blank" href="/marketers/ko/docs/skan-aggregated-postback-arrival-date-api">SKAN 데이터 집약형 포스트백 리포트</Anchor>.<br /><br />SKAN 포스트백을 가능한 가장 세밀한 수준으로 데이터 집약형으로 만듭니다. | 포스트백 도착 날짜를 사용하여 포스트백 집계 | 아니요 | API | 아니요 |
| <Anchor target="_blank" href="/marketers/ko/docs/skan-raw-data-reports#raw-data-report-types">데이터 락커를 통한 SKAN 로데이터(행 수준) 리포트</Anchor>(예시 포함).<br /><br />사용 가능한 리포트:<ul><li>애드 네트워크 파트너가 제공한 데이터 보강을 통해 iOS에서 보낸 포스트백</li><li>인스톨</li><li>재다운로드</li><li>인앱 이벤트</li><li>SRN 광고 차원</li></ul> |  | 예 | 데이터 락커 | 예. 로데이터가 필요합니다. 데이터 락커 구독은 필요하지 않습니다. |
| Push API를 통한 SKAN 데이터 |  | 예 | Push API | 예 |

</Accordion>

<div id="skadnetwork-solution-implementation-checklist" />

<Accordion title="SKAdNetwork 솔루션 구현 체크리스트">

| 아니오. | 조치 | 설명 | 책임 |
| --- | --- | --- | --- |
| 1 | 준비 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">SKAdNetwork 솔루션 가이드</Anchor> 읽기</li><li>추가 자료: <Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">iOS 14에 맞게 앱 준비하기</Anchor></li></ul> | 마케터, 개발자 |
| 2 | 구성 | 앱스플라이어에서 <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio">SKAN 컨버전 스튜디오</Anchor>에서 SKAdNetwork 솔루션을 구성합니다. | 마케터 |
| 3 | 앱 준비 | 앱을 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">V6 SDK</Anchor>로 마이그레이션<ul><li>앱 로직이나 코드를 변경할 필요가 없습니다.</li><li>앱스플라이어 SKAN 솔루션은 인앱 이벤트에 의존하여 전통적인 방식으로 인앱 이벤트를 설정합니다. SKAN 솔루션에 대한 특정 테스트는 필요하지 않습니다.</li><li>앱을 애플 앱 스토어에 제출</li><li>앱 스토어에서 SKAdNetwork 등록이나 프로세스가 필요하지 않습니다.</li></ul> | 개발자 |
| 4 | 파트너 연동 | 애드 네트워크 파트너는 SKAdNetwork 통합을 사용하여 앱스플라이어와 연동해야 합니다. 주의! 앱스플라이어 SKAdNetwork 시뮬레이션에는 현재 연동 상태와 관계없이 모든 파트너의 데이터가 포함되어 있습니다. 이는 SKAdNetwork 포스트백에서 보고되는 실시간 데이터에는 해당되지 않습니다.<br /><br />귀사의 캠페인을 운영하는 파트너와 관련하여 다음 항목을 완료하세요:<br /><br />**비 SRN**:<ol><li>파트너가 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#c-transaction-id">SKAdNetwork 기능 배지</Anchor>를 보유하고 있는지, 그리고 파트너 UI에서 SKAdNetwork 캠페인 리포팅이 활성화되어 있는지 확인하세요.</li><li>귀사의 [인앱 이벤트 이름이 매핑](#sending-postbacks-to-integrated-partners)되었는지 파트너 인앱 이벤트 이름에 확인하세요.</li></ol>**Meta 광고**:<ul><li><Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-interoperation-with-meta-ads">Meta 광고와 앱스플라이어 SKAdNetwork 상호 운용성 구성</Anchor></li></ul> | 마케터 |

</Accordion>

<div id="troubleshooting-guide" />

<Accordion title="문제 해결 가이드">

| 증상 | 설명 |
| --- | --- |
| 대시보드에 논오가닉 인스톨이 포함되어 있지 않습니다. | <ol><li>**SKAdNetwork 측정**이 켜져 있는지 확인하세요.<ol><li>**설정** > **SKAN 컨버전 스튜디오**로 이동합니다.</li><li>옵션(⋮)**을 클릭하고** SKAN 측정 설정을 검토합니다.</li></ol></li><li>SDK 버전이 6.2.6 이상인지 확인하세요.<ul><li>이렇게 하려면 **통합** > **SDK 정보 > SDK 버전별 사용자로 이동합니다.**</li></ul></li><li>SDK 플러그인을 사용하는 경우 앱스플라이어 SKAdNetwork를 지원하는 버전이 구현되었는지 확인하세요.</li><li>애드 네트워크 파트너가 앱스플라이어와 통합되어 있고 iOS 포스트백을 앱스플라이어로 전송하는지 확인하세요.</li></ol> |
| 대시보드에는 논오가닉 인스톨이 포함되지만 인앱 이벤트는 전혀 없습니다. | <ol><li>SDK 버전이 6.2.6 이상인지 확인하세요.<ul><li>이렇게 하려면 **통합** > **SDK 정보 > SDK 버전별 사용자로 이동합니다.**</li></ul></li><li>SDK 플러그인을 사용하는 경우 앱스플라이어 SKAdNetwork를 지원하는 버전이 구현되었는지 확인하세요.</li><li>서버-투-서버(S2S)를 사용하여 이벤트를 발송하시나요? 그렇다면 **서버-투-서버 API로 전송된 인앱 이벤트 기록**이 켜져 있는지 확인하세요.<ol><li>**설정** > **SKAN 컨버전 스튜디오**로 이동합니다.</li><li>**옵션(⋮)을 클릭하고 S2S 구성이 켜져 있는지 확인하세요.** 참고: 커스텀 및 디코드 측정 모드에서는 이 설정이 항상 켜져 있으며 변경할 수 없습니다.</li></ol></li></ol> |
| 대시보드에는 인스톨과 일부 인앱 이벤트가 포함되어 있습니다. 일부 인앱 이벤트가 누락되었습니다. | <ol><li>서버-투-서버(S2S)를 사용하여 이벤트를 발송하시나요? 그렇다면 **서버-투-서버 API로 전송된 인앱 이벤트 기록**이 켜져 있는지 확인하세요.<ol><li>**설정** > **SKAN 컨버전 스튜디오**로 이동합니다.</li><li>**옵션(⋮)을 클릭하고 S2S 구성이 켜져 있는지 확인하세요.** 참고: 커스텀 및 디코드 측정 모드에서는 이 설정이 항상 켜져 있으며 변경할 수 없습니다.</li></ol></li><li>귀사의 <Anchor target="_blank" href="/marketers/ko/docs/skan-raw-data-reports#raw-data-report-types">포스트백 로데이터</Anchor>를 검사하여 모든 이벤트가 보고되었는지 확인하세요.</li></ol> |
| 지역(국가) 정보가 혼동될 수 있습니다. | 지역 데이터는 다음과 같이 도출됩니다.<ul><li>캠페인과 연관된 국가에 따라 애드 네트워크가 앱스플라이어에 보고합니다.</li><li>디바이스 IP 주소를 사용합니다. iOS 14.6부터, 이 주소는 프록시 주소로 실제 유저의 지리적 위치를 나타내지 않습니다.</li></ul> |

</Accordion>

<div id="timing-from-app-install-until-dashboard-and-reports-update" />

<Accordion title="앱 설치 후 대시보드 및 보고서가 업데이트되는 시간">

| 키 | 요소 이름 | 설명 | 예시 A | 예시 B | 예시 C | 예시 D | 예시 E |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A | SKAN 4 측정 기간 1 | <ul><li>이 기간 동안, CV는 앱에서 설정됩니다.</li><li>0-2일</li><li>컨버전 스튜디오에서 2일 전에 기간을 잠글 수 있습니다.</li></ul> | - | - | 2일 | - | - |
| B | SKAN 4 측정 기간 2 | <ul><li>이 기간 동안, CV는 앱에서 설정됩니다.</li><li>3-7일</li><li>컨버전 스튜디오에서 7일 전에 기간을 잠글 수 있습니다.</li></ul> | - | - | - | 7일 | - |
| C | SKAN 4 측정 기간 3 | <ul><li>이 기간 동안, CV는 앱에서 설정됩니다.</li><li>8-35일</li><li>컨버전 스튜디오에서 35일 전에 기간을 잠글 수 있습니다.</li></ul> | - | - |  | - | 35일 |
| D | SKAN 4 측정 기간 1 포스트백 지연 | 24-48시간 | - | - | 24-48시간 | - | - |
| E | SKAN 4 측정 기간 2-3 지연 | 24-144시간 | - | - | - | 24-144시간 | 24-144시간 |
| F | 유저 활동 측정 기간<br /><br />(SKAN 4와 관련이 없습니다) | <ul><li>이 기간 동안 앱에서 CV를 설정합니다.</li><li>앱을 처음 열 때 이 기간이 시작됩니다.</li><li>12시간 - 63일.</li></ul> | 24시간 | 72시간 | - | - | - |
| G | SKAdNetwork 타이머<br /><br />(SKAN 4와 관련이 없습니다) | <ul><li>카운트다운 타이머: 24시간</li><li>CV가 늘어날 때마다 타이머가 재설정됩니다. 즉, 24시간부터 카운트다운이 시작됩니다.</li></ul> | 0-24시간 | 0-24시간 | - | - | - |
| H | SKAdNetwork 랜덤 지연<br /><br />(SKAN 4와 관련이 없습니다) | 무작위 포스트백 지연 시간. F+G로 정의된 기간이 끝난 후 카운트다운이 시작됩니다. | 0-24시간 | 0-24시간 | - | - | - |
| I | 앱스플라이어 처리 | 특정 날짜에 수신된 포스트백은 UTC 기준으로 다음 날 00:01부터 하루가 끝날 때 처리됩니다. 데이터는 8시간 후에 액세스할 수 있습니다. 즉, 처리에는 8&#126;32시간이 소요됩니다. 평균 지연 시간은 20시간입니다. 예를 들어, 월요일에 수신된 포스트백은 화요일에 처리됩니다. 대시보드는 UTC 기준 오전 8시에 업데이트됩니다. | 8-32시간 | 8-32시간 | 8-32시간 | 8-32시간 | 8-32시간 |
| 제이 | 요약 | 소요될 수 있는 총 시간 | 32시간&#126;104시간 | 80-152시간 | 80&#126;128시간 | 200-344시간 | 872-1016시간 |

</Accordion>

<div id="organic-metrics-in-the-context-of-skadnetwork" />

<Accordion title="SKAdNetwork 내의 오가닉 지표">

SKAdNetwork 대시보드의 오가닉 지표는 다음 메커니즘을 통해 계산됩니다.

* 유기적 수익은 고정 모드 또는 레거시 모드의 수익에만 사용할 수 있습니다.
* 유기적인 인앱 이벤트는 고정 또는 레거시 모드에서만 "전환"에 대해 사용할 수 있습니다.
* 비유산 모드(SKAN4, 사용자 정의 인코드 및 디코드 모드)에서는 유기적 데이터가 설치에 대해서만 제공됩니다.
* Apple SKAdNetwork는 미디어 소스와 상호작용한 후 인스톨한 사용자와 관련된 포스트백을 전송합니다. 이는 논오가닉 지표를 제공합니다.
* 앱스플라이어 어트리뷰션 대시보드는 소스와 관계없이 모든 인스톨의 지표를 포함합니다.  <Anchor target="_blank" href="/marketers/ko/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side">SKAN 어트리뷰션과 앱스플라이어 어트리뷰션을 나란히 보기</Anchor>를 참조하세요.
* 이 데이터를 사용하여 오가닉 지표는 A-B로 계산됩니다. 여기서:
  * A = 기존 개요 대시보드를 기반으로 한 모든 사용자의 총합
  * B = SKAdNetwork 포스트백에서 보고된 논오가닉 사용자

**Apple Search Ads와 관련된 주의사항**: 기존 대시보드에서 Apple Search Ads를 통한 인스톨은 논오가닉입니다. 그러나 SKAdNetwork 문맥에서는 오가닉 지표의 일부가 됩니다.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징과 제한사항">

| 특징 | 비고 |
| --- | --- |
| 광고 네트워크 액세스 | 광고 네트워크에 포스트백이 제공됩니다. |
| 에이전시 | 지원되지 않음. 즉, 에이전시는 SKAdNetwork 캠페인을 운영하는 광고 네트워크를 활성화해서는 안 됩니다. 에이전시! 광고주에게 광고 네트워크를 활성화하도록 요청하고 직접 활성화하지 마세요. 에이전시는 <Anchor target="_blank" href="/partners/ko/docs/getting-started-agency-onboarding#skadnetwork-에이전시-캠페인">SKAN 에이전시 인식</Anchor>을 구현하여 사용자를 유치했음을 표시할 수 있습니다. |
| 에이전시 투명성 | 해당 사항 없음 |
| 시간대 | UTC |
| 통화 | USD |
| 오가닉 데이터 | SDK 이벤트 데이터를 기반으로 합니다. 예를 들어, 오가닉 인스톨 지표는 다음과 같이 계산됩니다: SDK에 의해 보고된 모든 인스톨 데이터에서 SKAdNetworks에서 보고한 논오가닉 인스톨을 제외한 값입니다. |
| 논오가닉 데이터 | SKAdNetwork 포스트백을 기반으로 함 |
| 데이터 최신성 | 일일 |
| 기록 데이터 | iOS 14의 최초 출시일(2020년 9월 16일) |
| 유저 액세스 | 계정 사용자들은 <Anchor target="_blank" href="/marketers/ko/docs/user-management">필요한 권한</Anchor>을 가져야 합니다. |
| 앱 클립 | 앱 클립은 SKAdNetwork 대시보드에서 오가닉에 귀속됩니다. 개요 대시보드를 사용하여 호출 매체 소스를 확인하세요. |

</Accordion>

<div id="skan-integrated-partners" />

## SKAN 연동 파트너

<div id="recording-ad-revenue" />

<Accordion title="광고 수익 기록">

SKAdNetwork 측정 기간 동안 발생한 광고 수익은 사용자를 유치한 캠페인에 귀속합니다. 현재 이 기능은 SDK를 통해 일반적인 노출 수준 광고 수익과 연동된 광고주에 한해 제공됩니다.

SKAN 대시보드에서 광고 수익을 기록하려면:

* 귀사의 앱에 <Anchor target="_blank" href="/marketers/ko/docs/integrate-the-roi360-ad-revenue-sdk-api">일반 노출 수준 광고 수익 SDK</Anchor>를 연동하세요.
* SKAN 컨버전 스튜디오 고정 모드(기존)를 사용하는 경우 <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio#report-events-by-servertoserver-api">SKAdNetwork 서버-투-서버 지원</Anchor>을 활성화하세요.

**참고**: 미디에이션에 사용할 수 있는 광고 소스에 대한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/integrate-the-roi360-ad-revenue-sdk-api">일반 SDK 커넥터</Anchor> 문서를 참조하세요.

</Accordion>

<div id="sending-postbacks-to-integrated-partners" />

<Accordion title="통합된 파트너에게 포스트백 보내기">

앱스플라이어는 SKAN 어트리뷰션과 관련된 포스트백을 통합 파트너에게 전송합니다 (단, SKAN 4의 경우 기간 1에 대해서만 포스트백을 전송합니다).

다음 표에서 다양한 옵션과 요구 사항을 확인하세요.

| 주제 | 설명 |
| --- | --- |
| <span id="transaction-id-sharing"></span>거래 ID 공유 | **필요한 조치**: 통합 파트너에게 <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/verifying_an_install_validation_postback">거래 ID</Anchor>가 필요한지 확인하고, 이에 따라 설정을 구성하세요.<br /><br />앱스플라이어가 해당 애드 네트워크 파트너에게 포스트백을 보냅니다. 즉, iOS에서 받은 SKAdNetwork 포스트백의 사본이 아닌 디코딩된 포스트백을 의미합니다. 이러한 포스트백에는 사용자가 유저 활동 측정 기간 동안 수행한 작업의 인스톨 및 관련 인앱 이벤트 데이터가 포함된 디코딩된 CV 데이터가 포함되어 있습니다.<br /><br />거래 ID는 귀사의 CV를 해독하는 데 사용될 수 있으므로 귀사의 허락 없이는 이를 공유하지 않습니다.<br /><br />**거래 ID 공유**<br /><br />광고주는 다음과 같이 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#b-advanced-privacy">거래 ID 공유를 활성화</Anchor>합니다. 앱스플라이어에서 **협업** > **활성화된 연동** > 파트너 선택 > **연동 탭** > **데이터 공유**로 이동합니다. |
| <span id="inapp-event-mapping-verification"></span>인앱 이벤트 매핑 검증 | **<span id="1611499069.009700"></span>필요한 조치**: 파트너가 포스트백을 올바르게 기록할 수 있도록 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#매핑-방법">인앱 이벤트를</Anchor> 해당 파트너 이벤트 이름에 매핑해야 합니다.<br /><br />SKAdNetwork 캠페인을 운영하는 각 파트너에 대해, 인앱 이벤트가 선택한 앱 측정 유형에 따라 설정되었는지 확인하세요.<br /><br />**파트너 인앱 이벤트 매핑을 확인하고 변경하려면**:<ol><li>앱스플라이어에서 **협업** > **활성화된 연동**으로 이동합니다.</li><li>파트너를 선택하세요.</li><li>**연동** 탭으로 이동합니다.</li><li>다음과 같이 확인하고 필요한 경우 설정을 변경하세요.<ol><li>**인앱 이벤트 포스트백**을 켭니다.</li><li>SKAdNetwork 측정에서 설정한 인앱 이벤트(**SDK 이벤트 이름**)가 **파트너 이벤트 식별자**에 매핑되었는지 확인하세요.</li></ol></li><li>**연동 저장**을 클릭합니다.</li></ol> |

</Accordion>

<div id="see-also" />

> 📄 **참고 사항**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/about-att-and-skan">iOS 14, 앱 추적 투명성(ATT), SKAN의 빠른 시작 가이드 및 FAQ</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio">SKAN 컨버전 스튜디오를 사용하여 측정 설정(SKAdNetwork 설정)</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">앱스플라이어 SKAN 대시보드</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/skan-integrated-partners-list">SKAN 연동 파트너 목록</Anchor>
> * 앱스플라이어에서 설정이 필요한 SKAN 파트너 상호 운용성:
>   * <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-interoperation-with-meta-ads">Meta Ads</Anchor>
>   * <Anchor target="_blank" href="/marketers/ko/docs/get-skan-postback-data-from-google-ads">Google Ads</Anchor>
>   * <Anchor target="_blank" href="/marketers/ko/docs/skan-interoperation-with-tiktok-for-business">Tik Tok for Business</Anchor>
>   * <Anchor target="_blank" href="/marketers/ko/docs/skan-interoperation-with-snapchat">스냅챗</Anchor>

<div data-zendesk-anchors="01H7Z06Z03AQY25A3E45Z47A9G=skan 01H7Z06Z03CSKH1ZB9RQP6SHA8=%ED%8C%81 01H7Z06Z03MRE6BCSG1AEXN947=about-apple-skan appsflyer-skan-solution=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-skan-%EC%86%94%EB%A3%A8%EC%85%98 01H7Z06Z04G479NAKBEA33SGSZ=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-skan-%EC%86%94%EB%A3%A8%EC%85%98 01H7Z06Z05CAVK3CR7F5FBKFC5=principles-and-flow skan-attribution-flow=skan-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84 01H7Z06Z05EGK5QBDK6G7BJQJK=skan-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84 01H7Z06Z053M2H3CJ6SV4VDZPZ=conversion-studio additional-skadnetwork-information=%EC%B6%94%EA%B0%80-skadnetwork-%EC%A0%95%EB%B3%B4 01H7Z06Z05556NQ35HMR4E2TRY=%EC%B6%94%EA%B0%80-skadnetwork-%EC%A0%95%EB%B3%B4 01H7Z06Z05G0YB56GDG5E196QM=reporting-options 01H7Z06Z05M3BPSBTCMJ3NHK5D=skadnetwork-solution-implementation-checklist 01H7Z06Z05YF4J0MPMJ40EG7BX=troubleshooting-guide 01H7Z06Z0502NW8KFJ7XRZFWJR=timing-from-app-install-until-dashboard-and-reports-update 01H7Z06Z068462E4QTGTSMNS7H=organic-metrics-in-the-context-of-skadnetwork 01H7Z06Z0615QHCY6JZ4MAMTJ8=traits-and-limitations skadnetwork-integrated-partners=skan-%EC%97%B0%EB%8F%99-%ED%8C%8C%ED%8A%B8%EB%84%88 01H7Z06Z06KGT6ESN42XTJSK2F=skan-%EC%97%B0%EB%8F%99-%ED%8C%8C%ED%8A%B8%EB%84%88 01H7Z06Z06NWJQ6W50MCD3P352=recording-ad-revenue 01H7Z06Z06K2ZB949GGTJV6MJP=sending-postbacks-to-integrated-partners h_01HE7TC49KRRX1RVGX1FY7C52T=%EC%B0%B8%EA%B3%A0-%EC%82%AC%ED%95%AD" />
