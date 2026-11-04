---
title: 디바이스 식별자(ID)
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2021-10-12T14:16:09Z'
  edited_at: '2026-10-14T10:33:27Z'
  id: 4408847686161
  locale: ko
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ko/articles/4408847686161
---
> **한눈에 보기:** 요약: 앱스플라이어 SDK에서 지원하는 기기 식별자를 알아봅니다.

<div id="overview" />

## 개요

앱스플라이어 SDK는 어트리뷰션 목적으로 기기 식별자를 수집합니다. 식별자는 사용자의 여정을 매핑하고 선호도를 이해하는 데 도움이 될 수 있습니다.

SDK는 앱스플라이어 ID 및 Google 광고 ID(GAID)와 같은 식별자를 자동으로 수집합니다. 앱에 대한 다른 식별자를 수집하는 것은 필요에 따라 다릅니다(예: 타사 안드로이드 앱 스토어 또는 중국에서 판매되는 앱 수집).

## 모든 플랫폼에 대한 기기 식별자

SDK는 모든 플랫폼에 대해 다음 기기 식별자를 지원합니다.

| 기기 식별자 | 목적 |
| --- | --- |
| <span id="appsflyer-id"></span>앱스플라이어 ID | 앱스플라이어 ID는 앱을 인스톨할 때마다 자동으로 생성됩니다. 이 식별자를 사용하여 다음 작업을 수행할 수 있습니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">서버 간 인앱 이벤트(server-to-server in-app events)</Anchor> 보내기.</li><li>백엔드 시스템의 사용자 기록을 AppsFlyer ID와 맞추기.</li><li>풀(pull) 또는 푸시(push) API로 수신한 데이터를 병합할 때 엔트리를 매핑합니다.</li></ul> |
| <span id="customer-user-id"></span>Customer User ID | <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">고객 사용자 ID(CUID)</Anchor> 필드는 앱과 웹사이트 담당자가 설정한 고유한 사용자 식별자입니다. 앱스플라이어 SDK에서 CUID를 확인할 수 있도록 설정해두면, 서비스 자체 고유한 고객 사용자 ID와 앱스플라이어 ID 및 기타 식별자 값과 상호 참조할 수 있습니다. CUID는 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary">로데이터</Anchor> 리포트에서 이용할 수 있습니다. 또한, 귀사의 내부 ID와 교차 참조하기 위해 포스트백 API에서도 사용할 수 있습니다. |

<div id="android-device-identifiers" />

## 안드로이드 기기 식별자

SDK는 안드로이드 플랫폼에 대해 다음 기기 식별자를 지원합니다.

<div id="apps-published-on-google-play" />

#### 구글 플레이에 게시된 앱

| 기기 식별자 | 목적 |
| --- | --- |
| <span id="gaid"></span>GAID | 구글 플레이 안드로이드 사용자를 위한 사용자가 재설정가능 식별자입니다.<br /><br />SDK V4.8.0부터 앱스플라이어는 이 기기 식별자를 자동으로 수집합니다. |

<div id="apps-published-in-third-party-app-stores" />

#### 타사 앱 스토어에 게시된 앱

| 기기 식별자 | 목적 |
| --- | --- |
| <span id="amazon-advertising-id"></span>Amazon 광고 ID | Amazon Fire TV에서 사용하는 사용자 재설정가능 고유 식별자입니다. CTV 개요 보기 |
| <span id="oaid"></span>OAID | 일부 스토어 외 안드로이드 시장에서 사용하는 사용자 재설정 가능 식별자입니다.   자세한 내용은 OAID 구현 가이드를 참조하세요. |
| <span id="imei"></span>IMEI | 구글 플레이 이외의 시장에서 사용되는 재설정할 수 없는 고유한 모바일 기기 식별자입니다. SDK는 IMEI를 자동으로 수집하지 않습니다. 그러나 이러한 식별자를 수집해야 하는 경우 개발자가 수집을 구현할 수 있습니다.<br /><br />**참고:**<ul><li>안드로이드 버전 10부터 IMEI에 대한 액세스가 제한됩니다.</li><li>IMEI는 GAID와 함께 사용할 수 없습니다.</li></ul> |
| <span id="android-id"></span>안드로이드 ID | 타사 앱 스토어에서 사용되는 재설정할 수 없는 고유한 모바일 기기 식별자입니다. SDK는 안드로이드 ID를 자동으로 수집하지 않습니다. 그러나 이러한 식별자를 수집해야 하는 경우 개발자가 수집을 구현할 수 있습니다.<br /><br />**참고:** 참고: 안드로이드 ID는 GAID와 함께 사용할 수 없습니다. |

<div id="apple-device-identifiers" />

## Apple 기기 식별자

SDK는 iOS 플랫폼에 대해 다음과 같은 기기 식별자를 지원합니다.

| 기기 식별자 | 목적 |
| --- | --- |
| <span id="idfa"></span>IDFA | Apple iOS 또는 tvOS(Apple TV) 사용자를 위한 고유한 사용자 재설정 가능 식별자입니다. iOS 14.5 출시 이후 IDFA는 사용자가 ATT 프롬프트를 통해 동의한 경우에만 사용할 수 있습니다. |
| <span id="idfv"></span>IDFV | 디바이스에서 **동일한 공급업체**의 모든 앱이 공유하는 기기 식별자입니다. 첫 번째 앱이 설치되면 ID가 할당되고 동일한 공급업체의 다른 앱에는 동일한 IDFV가 할당됩니다. 다른 공급업체의 앱에는 다른 IDFV가 할당됩니다.<br /><br />또한 특정 벤더의 모든 앱이 제거되면 해당 벤더의 IDFV가 삭제되고 새로 인스톨 시 새로운 IDFV가 할당됩니다. |


| <span id="ctv--pc-and-console-app-device-identifiers"></span><span id="ctv-device-identifiers"></span>플랫폼 | 디바이스 ID |
| --- | --- |
| 안드로이드 TV | advertising\_id |
| tvOS(Apple TV) | idfa |
| 아마존 파이어 TV | amazon\_fire\_id |
| 크롬캐스트 | advertising\_id |
| 로쿠 | rida |
| Vizio | Vida |
| Samsung | tifa |
| LG | <ul><li>LG WebOS=lgudid</li></ul> |
| 엑스박스 | 커스텀 |
| 비다 | vidaaid |
| Steam |  |
| Meta Quest (Oculus) | 커스텀 |
| 에픽 게임즈 |  |
| 플레이스테이션 | psid |
| 네이티브 PC | 커스텀 |
|  | Android 식별자 |

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01H9YXEYC3PA271B3G3Y3GM9PS=%EA%B0%9C%EC%9A%94 device-identifiers-for-all-platforms=%EB%AA%A8%EB%93%A0-%ED%94%8C%EB%9E%AB%ED%8F%BC%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B8%B0%EA%B8%B0-%EC%8B%9D%EB%B3%84%EC%9E%90 h_01H9YXEYC3RCB3RDBKRW19WYQD=%EB%AA%A8%EB%93%A0-%ED%94%8C%EB%9E%AB%ED%8F%BC%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B8%B0%EA%B8%B0-%EC%8B%9D%EB%B3%84%EC%9E%90 android-device-identifiers=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B8%B0%EA%B8%B0-%EC%8B%9D%EB%B3%84%EC%9E%90 h_01H9YXEYC3D95A6G70EGNR8ENK=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B8%B0%EA%B8%B0-%EC%8B%9D%EB%B3%84%EC%9E%90 apps-published-on-google-play=%EA%B5%AC%EA%B8%80-%ED%94%8C%EB%A0%88%EC%9D%B4%EC%97%90-%EA%B2%8C%EC%8B%9C%EB%90%9C-%EC%95%B1 h_01H9YXEYC3RG2XCVVW8MJ5VZSC=%EA%B5%AC%EA%B8%80-%ED%94%8C%EB%A0%88%EC%9D%B4%EC%97%90-%EA%B2%8C%EC%8B%9C%EB%90%9C-%EC%95%B1 apps-published-in-thirdparty-app-stores=%ED%83%80%EC%82%AC-%EC%95%B1-%EC%8A%A4%ED%86%A0%EC%96%B4%EC%97%90-%EA%B2%8C%EC%8B%9C%EB%90%9C-%EC%95%B1 h_01H9YXEYC3JA3DPN6P43J1ZXR9=%ED%83%80%EC%82%AC-%EC%95%B1-%EC%8A%A4%ED%86%A0%EC%96%B4%EC%97%90-%EA%B2%8C%EC%8B%9C%EB%90%9C-%EC%95%B1 apple-device-identifiers=apple-%EA%B8%B0%EA%B8%B0-%EC%8B%9D%EB%B3%84%EC%9E%90 h_01H9YXEYC3733B1A85TEF35EAY=apple-%EA%B8%B0%EA%B8%B0-%EC%8B%9D%EB%B3%84%EC%9E%90 h_01H9YXEYC3DFPWVXA5Y3XANQ3P=ctv-device-identifiers" />
