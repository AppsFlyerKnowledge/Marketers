---
title: 앱스플라이어 SDK 버전 관리 정책
metadata:
  keywords:
    - iOS
    - Android
    - SDK
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
  created_at: '2021-11-30T10:43:19Z'
  edited_at: '2026-10-14T10:34:13Z'
  id: 4412316953105
  locale: ko
  section: Previous SDK versions
  section_id: 6551300280977
  url: https://support.appsflyer.com/hc/ko/articles/4412316953105
---
> **한눈에 보기:** 요약: 앱스플라이어 SDK 버전 관리 정책 및 유지 관리하는 버전에 대해 알아봅니다.

## 버전 관리 정보

수년 동안, AppsFlyer는 SDK의 여러 버전을 출시했습니다. 각 SDK 버전은 특정 API 버전을 호출합니다. 버전 관리 정책의 목적은 API가 SDK 버전을 얼마나 오랫동안 지원할지를 정의하는 것입니다.

## 버전 제어가 필요한 이유는 무엇인가요?

버전 제어의 목적은 다음과 같습니다.

* 앱에 연동된 SDK 버전용 API가 종료되는 시기를 미리 이해하는 데 도움이 됩니다. 버전 채택에는 시간이 걸려 사용자가 최신 앱 버전으로 업그레이드할 때까지 시간이 걸릴 수 있으므로 이는 중요합니다.
* 안정성이 향상되었으므로(이전 버전과의 호환성은 2.5년 동안) 매우 오래된 SDK 버전을 사용할 때 예기치 않은 오류가 발생하지 않습니다.
* SDK 업그레이드를 필요로 하는 새로운 기능을 활용할 수 있습니다.

## SDK 버전 수명 주기

API 버전은 2.5년 동안 실행되도록 보장됩니다. SDK의 새로운 메이저 또는 마이너 버전이 출시될 때마다 앱스플라이어는 이전 마이너 버전(모든 패치 버전 포함)의 종료 날짜를 설정합니다.

**iOS 및 Android용 레거시 SDK 버전은 고정된 6개월 주기로 지원이 중단됩니다.** 이 주기는 사전 통지를 제공하여 팀이 미리 계획하고 중단 없이 전체 앱 기능을 유지할 수 있도록 설계되었습니다. 최신 SDK로 업그레이드하면 최신 기능, 향상된 안정성 및 지속적인 지원에 접근할 수 있습니다.

> 🚧 **중요!**
>
> 원활한 전환을 보장하기 위해 앱 개발자는 지원 종료 날짜 이전에 최신 SDK 버전으로 업데이트할 것을 권장합니다.

## 지원 종료 대 vs. 사용 중단

AppsFlyer는 지원 수준과 데이터 측정에 미치는 영향을 명확히 하기 위해 **Deprecated** 및 **End-of-Support** SDK 버전을 구분합니다.

* **사용 중단된 버전** 알려진 문제로 인해 더 이상 권장되지 않는 SDK 버전, 예를 들어 치명적인 버그가 있는 경우. 이 버전은 여전히 AppsFlyer에 데이터를 전송할 수 있지만, 계속 사용하는 것은 권장되지 않으며 지원되는 버전으로 업그레이드하는 것이 강력히 권장됩니다.
* **지원 종료 버전:** 모든 플랫폼에서 측정이 완전히 중단된 SDK 버전입니다. Android와 iOS 모두에 대해 설치, 세션 및 인앱 이벤트는 측정되지 않습니다. 이 버전에서 발생하는 모든 트래픽(특히 AppsFlyer에 의해 제외되지 않는 한)은 400 상태 코드를 받게 되며, 이는 SDK가 API 호출을 평소처럼 전송하려고 시도하지만, AppsFlyer 서버가 이를 거부하고 데이터가 처리되지 않음을 의미합니다.

## SDK 버전이 지원 종료 날짜에 도달하면 어떻게 됩니까?

SDK 버전이 지원 종료 날짜에 도달하면, AppsFlyer 서버는 더 이상 설치, 세션 및 인앱 이벤트를 측정하지 않습니다. 이러한 종료점에 도달하는 이벤트는 거부됩니다.

채택에는 시간이 걸리므로 개발자가 종료 날짜 훨씬 전에 최신 SDK 버전으로 업그레이드하는 것이 좋습니다 .

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-android-sdk-release-notes">앱스플라이어 안드로이드 SDK 릴리스 정보</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-ios-sdk-release-notes">앱스플라이어 iOS SDK 릴리스 정보</Anchor>

<div data-zendesk-anchors="about-versioning=%EB%B2%84%EC%A0%84-%EA%B4%80%EB%A6%AC-%EC%A0%95%EB%B3%B4 h_01HE7RHYC4YGZWF9EKK96RPMAN=%EB%B2%84%EC%A0%84-%EA%B4%80%EB%A6%AC-%EC%A0%95%EB%B3%B4 why-do-we-need-version-control=%EB%B2%84%EC%A0%84-%EC%A0%9C%EC%96%B4%EA%B0%80-%ED%95%84%EC%9A%94%ED%95%9C-%EC%9D%B4%EC%9C%A0%EB%8A%94-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 h_01HE7RHYC4QSVTA4ZCHTKYQSAT=%EB%B2%84%EC%A0%84-%EC%A0%9C%EC%96%B4%EA%B0%80-%ED%95%84%EC%9A%94%ED%95%9C-%EC%9D%B4%EC%9C%A0%EB%8A%94-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 sdk-version-lifecycles=sdk-%EB%B2%84%EC%A0%84-%EC%88%98%EB%AA%85-%EC%A3%BC%EA%B8%B0 h_01HE7RHYC41QN657ZTEQ0P45GD=sdk-%EB%B2%84%EC%A0%84-%EC%88%98%EB%AA%85-%EC%A3%BC%EA%B8%B0 h_01JVHFG6PN34YFWNZKX2CYHJV8=%EC%A4%91%EC%9A%94 end-of-support-vs-deprecated=%EC%A7%80%EC%9B%90-%EC%A2%85%EB%A3%8C-%EB%8C%80-vs-%EC%82%AC%EC%9A%A9-%EC%A4%91%EB%8B%A8 h_01JVHEKR4MTFV0FDHMTQW00BCS=%EC%A7%80%EC%9B%90-%EC%A2%85%EB%A3%8C-%EB%8C%80-vs-%EC%82%AC%EC%9A%A9-%EC%A4%91%EB%8B%A8 what-happens-when-an-sdk-version-is-sunset=sdk-%EB%B2%84%EC%A0%84%EC%9D%B4-%EC%A7%80%EC%9B%90-%EC%A2%85%EB%A3%8C-%EB%82%A0%EC%A7%9C%EC%97%90-%EB%8F%84%EB%8B%AC%ED%95%98%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%EB%90%A9%EB%8B%88%EA%B9%8C h_01HE7RHYC4EVSNA2F4DQ1594DH=sdk-%EB%B2%84%EC%A0%84%EC%9D%B4-%EC%A7%80%EC%9B%90-%EC%A2%85%EB%A3%8C-%EB%82%A0%EC%A7%9C%EC%97%90-%EB%8F%84%EB%8B%AC%ED%95%98%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%EB%90%A9%EB%8B%88%EA%B9%8C h_01HE7RPQBD858TQSF27NFGGP43=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
