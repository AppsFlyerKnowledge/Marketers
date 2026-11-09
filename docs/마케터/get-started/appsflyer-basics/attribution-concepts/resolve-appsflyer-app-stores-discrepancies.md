---
title: 앱스플라이어와 앱스토어 간 어트리뷰션 수치 차이
metadata:
  keywords:
    - Google Play
    - AppsFlyer
    - iTunes
    - installs
    - Discrepancies
    - App Stre
    - Compare
    - Account
    - Advertisers
    - app store
    - appstore
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-12-24T12:52:53Z'
  edited_at: '2026-10-14T10:40:18Z'
  id: 207040726
  locale: ko
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ko/articles/207040726
---
> **한눈에 보기:** 요약: 앱스플라이어와 앱스토어 사이 수치 차이를 유발하는 주요 원인과 그 차이를 최소화할 수 있는 팁을 찾아봅니다.

<div id="attribution-discrepancies" />

## 어트리뷰션 수치 차이

모바일 어트리뷰션 생태계의 모든 참여자가 사용하는 어트리뷰션 모델 사이에는 타고난 차이가 있습니다. 앱스플라이어와 주요 앱스토어 (iOS의 앱스토어와 안드로이드의 구글 플레이)에도 동일하게 적용됩니다.  **참고**: 참고: 이 문서에서 부르는 앱스토어는 이 두개의 앱스토어를 뜻합니다.

어트리뷰션 모델 차이로 인해, 어떤 경우에는 앱스토어가 앱스플라이어보다 더 많은 인스톨을 기록하기도 합니다. 다른 경우에는, 앱스플라이어가 앱스토어보다 더 많은 인스톨을 기록하기도 합니다.

<Image align="center" alt="AF_vs_app_stores.png" src="https://files.readme.io/6f81aac30cdf1ab2331cd08e7a221c154e1f7104c15d47c47690baabaace856a-34114275895825.png" width="605px" />

<div id="note" />

> 📘 **참고사항**
>
> 수치 차이는 **논오가닉** 인스톨 집계의 정확성에는 영향을 주지 않습니다. 왜냐하면 앱스플라이어 어트리뷰션 모델은 광고 클릭당 하나의 인스톨에만 성과를 인정하기 때문입니다. 이는 특정 사용자가 앱스토어에 둘 이상의 디바이스를 등록해둔 경우에도 해당됩니다.

<div id="why-appsflyer-attributes-less" />

### 왜 앱스플라이어가 더 적게 어트리뷰션 합니까?

다음은 앱스플라이어가 더 적게 어트리뷰션하는 원인입니다.

| 1. 일으키다. 2. 발생시키다. | 앱스토어 | 앱스플라이어 | 앱스플라이어 팁 |
| --- | --- | --- | --- |
| **인스톨 정의** | 앱스토어는 사용자의 앱 실행 여부에 상관없이, 사용자가 앱을 다운로드 받고 설치하면 인스톨로 기록합니다. | 앱스플라이어는 앱이 첫 실행된 이후에만 신규 인스톨을 기록합니다.<br /><br />사용자가 앱을 다운로드 받고 설치하더라도 (앱스토어 정의에 따라), 앱을 전혀 실행하지 않은 사용자는 앱스플라이어에 집계되지 않습니다. | 약 90%의 모바일 앱 다운로드는 적어도 한 번의 실행을 가져옵니다. 하지만 지역이나 업종에 따라 이 수치는 상당히 다를 수 있습니다. |
| **인스톨 기록 날짜** | 앱스토어는 다운로드 날짜를 인스톨 날짜로 기록합니다. | 앱스플라이어는 앱 첫 실행 날짜를 인스톨 날짜로 기록합니다. | 이 차이를 줄이기 위해, 앱스플라이어에서 데이터 확인 기간을 정할 때, 더 긴 기간을 선택합니다. |
| **시간대** | 광고주의 현지 시간대에 따라 데이터가 표시됩니다. | 기본 설정으로는 UTC±00:00 시간대를 사용하여 데이터가 표시됩니다. | 이 차이를 줄이기 위해, 앱 별로 선호하는 시간대를 설정할 수 있습니다. (<Anchor target="_blank" href="/marketers/ko/docs/changing-app-time-zone-settings">상세 내용 참고</Anchor>) |
| 앱을 삭제했다가, 설정된 리어트리뷰션 윈도우 **이내에** 재설치한 안드로이드 사용자 | 구글 플레이는, 어떤 보기 화면에서는 첫 인스톨과의 시간 차이에 상관없이 동일한 사용자에게 두 개의 **고유 인스톨**을 표시합니다. 다른 보기 화면에서는 고유 사용자 수를 표시하여 앱스플라이어와 좀 더 가깝습니다. | 원래의 인스톨 시점으로부터 시작한 리어트리뷰션 기간(기본값 3개월) 이내에는, 재인스톨이 일어나더라도 해당 사용자는 앱스플라이어에서 신규로 간주되지 않습니다. | <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">리어트리뷰션 윈도우</Anchor>를 1 - 24개월로 설정할 수 있습니다. |
| 앱을 삭제했다가, 설정된 리어트리뷰션 윈도우 **이내에** 재설치한 iOS 사용자 | iTunes는 사용자가 앱을 삭제하고 재설치할 때마다 신규 인스톨로 집계합니다. | 원래의 인스톨 시점으로부터 시작한 리어트리뷰션 기간(기본값 3개월) 이내에는, 재인스톨이 일어나더라도 해당 사용자는 앱스플라이어에서 신규로 간주되지 않습니다. | <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">리어트리뷰션 윈도우</Anchor>를 1 - 24개월로 설정할 수 있습니다. |

<div id="why-appsflyer-attributes-more" />

### 왜 앱스플라이어가 더 많이 어트리뷰션 합니까?

다음은 앱스플라이어가 더 많이 어트리뷰션하는 원인입니다.

| 1. 일으키다. 2. 발생시키다. | 앱스토어 | 앱스플라이어 | 앱스플라이어 팁 |
| --- | --- | --- | --- |
| **기존의 앱을 앱스플라이어 SDK를 포함하지 않은 버전에서 포함한 버전으로 업그레이드** | 앱스토어는 이를 동일한 사용자로 간주하여 신규 인스톨로 표시하지 않습니다. | 앱스플라이어는 이 업그레이드를 오가닉 인스톨로 표시합니다. | <ul><li>대부분의 사용자가 앱 업그레이드를 완료하는 며칠이 지나면 이런 수치 상승은 다시 내려옵니다.</li><li>새 계정은 앱스플라이어 상 수치 상승을 피하기 위해, <Anchor target="_blank" href="/marketers/ko/docs/migration-to-appsflyer-from-other-vendors#device-migration%E2%80%94optional">기존 사용자를 마이그레이션</Anchor> 할 수 있습니다.</li></ul> |
| **디바이스 ID 재설정 및 광고 추적 제한 프로드** | 앱스토어는 이를 동일한 사용자로 간주하여 신규 인스톨로 표시하지 않습니다. | 앱스플라이어는 이를 새 기기에서의 신규 인스톨로 봅니다. | 만약 앱이 이런 유형의 프로드에 시달린다면, 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/protect360-anti-fraud-guide">프로텍트360 프로드 방지 솔루션</Anchor>이 감지합니다. |
| **구글 플레이와 앱스토어 외 다른 곳(out of store)** 에서의 인스톨 및 <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution">사전 설치</Anchor> | Google Play는 이러한 인스톨을 기록하지 않습니다. | 앱스플라이어는 이러한 인스톨을 계수합니다. | 만약 <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution">구글 플레이 외 안드로이드 앱 마켓</Anchor>에서 광고한다면, 정확한 설정을 위해 문서를 참고하십시오. |
|  | 구글 플레이는, 어떤 보기 화면에서는 첫 인스톨과의 시간 차이에 상관없이 동일한 사용자에게 두 개의 고유 인스톨을 표시합니다. 다른 보기 화면에서는 고유 사용자 수를 표시하여 앱스플라이어와 좀 더 가깝습니다. |  | <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">리어트리뷰션 윈도우</Anchor>를 1 - 24개월로 설정할 수 있습니다. |

<div data-zendesk-anchors="attribution-discrepancies=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%88%98%EC%B9%98-%EC%B0%A8%EC%9D%B4 h_01HNWP7A6GQC5ZX6WKBW411DVG=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%88%98%EC%B9%98-%EC%B0%A8%EC%9D%B4 h_01HNWP7A6GZJS246548Q5AFPZR=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD why-appsflyer-attributes-less=%EC%99%9C-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EA%B0%80-%EB%8D%94-%EC%A0%81%EA%B2%8C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%95%A9%EB%8B%88%EA%B9%8C h_01HNWP7A6G85PR1R66Q3KCRPNW=%EC%99%9C-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EA%B0%80-%EB%8D%94-%EC%A0%81%EA%B2%8C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%95%A9%EB%8B%88%EA%B9%8C why-appsflyer-attributes-more=%EC%99%9C-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EA%B0%80-%EB%8D%94-%EB%A7%8E%EC%9D%B4-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%95%A9%EB%8B%88%EA%B9%8C h_01HNWP7A6GVVWMV6HECXQFTJT6=%EC%99%9C-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EA%B0%80-%EB%8D%94-%EB%A7%8E%EC%9D%B4-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%95%A9%EB%8B%88%EA%B9%8C" />
