---
title: SDK 정보(버전 및 동의) 대시보드
metadata:
  keywords:
    - SDK Information
    - Advertisers
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
  created_at: '2017-02-15T09:32:15Z'
  edited_at: '2026-10-14T10:32:43Z'
  id: 115000805366
  locale: ko
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/ko/articles/115000805366
---
> **한눈에 보기:** 요약: SDK의 대시보드 보기, 운영 체제(iOS, 안드로이드) 채택 비율 및 iOS ATT 동의 지표.

## 버전 채택 및 ATT 동의 대시보드

대시보드의 데이터는 af\_open(세션) 이벤트에서 파생되며 인스톨 이벤트와 관련이 없습니다. 대시보드에는 다음과 같은 기본 섹션이 있습니다.

* SDK 버전 정보; 모든 플랫폼(안드로이드 및 iOS)에 대해 사용 가능
* ATT 동의 지표와 iOS 16.1 이상 채택(SKAN 4 데이터에 대한 잠재력 제공)

SDK 정보 대시보드를 보는 방법:

1. 앱스플라이어의 사이드 메뉴에서 설정 > **SDK 정보를** 선택합니다.
2. 활동 날짜 범위를 설정합니다.    
   표시되는 지표는 다음 섹션에 설명되어 있습니다.

<div id="sdk-information-ios-and-android" />

<Accordion title="SDK 정보(iOS 및 안드로이드)">

다음은 가장 최근 앱 열기(시작) 날짜를 사용하는 iOS 및 안드로이드 앱에서 사용할 수 있는 버전 지표를 보여줍니다.

| 사용자 그룹 분류 | 예시 |
| --- | --- |
| 앱 버전 | 2021년 5월 20일 앱 버전 V1.4.28의 도입 알림<br /><br />[![UsersByAppVersion__1_.png](https://files.readme.io/87bbf8aba8295e44430098c7c6fe4dc290cafca229e271a4185c763c609e9833-4402595560337.png)](https://files.readme.io/87bbf8aba8295e44430098c7c6fe4dc290cafca229e271a4185c763c609e9833-4402595560337.png) |
| SDK 버전 | SDK V6.1.4의 소개 알림 2021년 5월 20일<br /><br />[![UsersBySDKVersion.png](https://files.readme.io/df7b4a1f380cd10162b3a13efc5da1ccc4b96e47d994e4c42b2674bfd4930bb6-4402589094033.png)](https://files.readme.io/df7b4a1f380cd10162b3a13efc5da1ccc4b96e47d994e4c42b2674bfd4930bb6-4402589094033.png) |
| 운영 체제 버전 | [![UsersByOsVersion.png](https://files.readme.io/d56f8b43155bb226adaa1a276e00634fe721a01b74b5114d273ae66e74034dd9-4402589093521.png)](https://files.readme.io/d56f8b43155bb226adaa1a276e00634fe721a01b74b5114d273ae66e74034dd9-4402589093521.png) |
| 기기 유형 | [![UsersByDevice.png](https://files.readme.io/2f320f91d6a5a9f4bca0e3715cd33dfff2ac971af29e961592b4494bafe721f0-4402595560977.png)](https://files.readme.io/2f320f91d6a5a9f4bca0e3715cd33dfff2ac971af29e961592b4494bafe721f0-4402595560977.png) |

</Accordion>

<div id="att-metrics-ios-14" />

<Accordion title="iOS 및 ATT 지표">

사용자가 채택하는 iOS 버전에 따라 사용 가능한 데이터의 종류가 달라질 수 있습니다. 예를 들어, 사용자가 iOS 16.1 이상을 사용하는 경우 SKAN 4 데이터를 사용할 수 있습니다.

<Anchor target="_blank" href="/marketers/ko/docs/att-implications-ios-14-and-deprecation-of-lat">ATT 상태</Anchor>는 iOS에서 설정하며 앱을 통해 앱스플라이어에 리포트됩니다. 가능한 ATT 상태 값은 다음과 같습니다.

* 허용됨 권한 부여됨: 사용자가 추적할 명시적 계약을 부여했습니다.
* 거부됨 거부됨: 사용자가 명시적으로 추적에 동의하지 않았거나, 사용자가 iOS 14 이상으로 업그레이드하기 전에 LAT가 켜져 있었습니다.
* 미결정
* 제한되지 않습니다.

**고려 사항:**

* 차트 지표는 주어진 날짜에 고유한 사용자 앱 실행 이벤트를 사용하여 계산합니다. 즉, 사용자가 지정된 날짜에 앱을 열지 않은 경우 사용자는 해당 날짜의 지표에서 계수되지 않습니다.
* iOS 및 ATT 지표에는 <Anchor target="_blank" href="/marketers/ko/docs/att-implications-ios-14-and-deprecation-of-lat#apple에서-정의한-att-값">Apple에서 정의한 ATT 값</Anchor>만 포함됩니다. 앱스플라이어에서 정의한 추가 값이 아닙니다.

#### iOS 앱의 ATT 및 iOS 채택 지표

| 차트 | 예제 및 설명 |
| --- | --- |
| 앱 열기의 ATT 상태 | [![AttStatusByDate.png](https://files.readme.io/8e41e1602125903267e91a71b49305d43ca018aec77a2a991d0af08cb396825a-4402691807377.png)](https://files.readme.io/8e41e1602125903267e91a71b49305d43ca018aec77a2a991d0af08cb396825a-4402691807377.png)<br /><br />지정된 날짜에 앱을 실행하는 iOS 14 이상을 갖는 사용자를 대상으로 합니다. 이는 지표가 지정된 날짜에 사용자의 ATT 상태를 표시함을 의미합니다. |
| 앱 버전에 의한 동의 | [![ATTAppVersion.png](https://files.readme.io/1f19917998f142180d0fdfb5448c90b280b2d6536844c63ce630d3656719f656-4402589092113.png)](https://files.readme.io/1f19917998f142180d0fdfb5448c90b280b2d6536844c63ce630d3656719f656-4402589092113.png) |
| 동의 추세 | [![ConsentTrend.png](https://files.readme.io/bae0c55c603e83b87fa50ba6d16c628443d565417c1aceee4536a5b96dd9435e-4402589093265.png)](https://files.readme.io/bae0c55c603e83b87fa50ba6d16c628443d565417c1aceee4536a5b96dd9435e-4402589093265.png) |
| iOS 14.5 사용자 채택률 | [![iso_user_adoption_rate.png](https://files.readme.io/2a29749fd968354f9836595cf20f07954be1aedce97df140d1d14452eb7306b3-15478514320529.png)](https://files.readme.io/2a29749fd968354f9836595cf20f07954be1aedce97df140d1d14452eb7306b3-15478514320529.png) |

</Accordion>

<div data-zendesk-anchors="version-adoption-and-att-consent-dashboard=%EB%B2%84%EC%A0%84-%EC%B1%84%ED%83%9D-%EB%B0%8F-att-%EB%8F%99%EC%9D%98-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C h_01HGX98Q4FRVS2B35BVT683D5W=%EB%B2%84%EC%A0%84-%EC%B1%84%ED%83%9D-%EB%B0%8F-att-%EB%8F%99%EC%9D%98-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C h_01HGX98Q4F8PQYRSC0J2WE4RQX=sdk-information-ios-and-android h_01HGX98Q4FKWD5496P446FB31B=att-metrics-ios-14 att-and-ios-adoption-metrics-for-ios-apps=ios-%EC%95%B1%EC%9D%98-att-%EB%B0%8F-ios-%EC%B1%84%ED%83%9D-%EC%A7%80%ED%91%9C h_01HGX98Q4G0C4XTC1DSVP96M19=ios-%EC%95%B1%EC%9D%98-att-%EB%B0%8F-ios-%EC%B1%84%ED%83%9D-%EC%A7%80%ED%91%9C" />
