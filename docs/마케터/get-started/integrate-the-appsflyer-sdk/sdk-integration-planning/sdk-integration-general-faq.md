---
title: SDK 연동 관련 자주 묻는 질문
metadata:
  keywords:
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
  created_at: '2015-01-18T11:13:24Z'
  edited_at: '2026-10-14T10:31:08Z'
  id: 207033546
  locale: ko
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ko/articles/207033546
---
> **한눈에 보기:** 앱스플라이어 SDK를 사용하면 귀사의 앱 광고, 어트리뷰션 설정, 딥링크와 모바일 유저의 행동 정보 수집을 안전하게 할 수 있습니다. 몇 분 만에 애드 네트워크 및/또는 플랫폼과 작업을 설정하고 착수할 수 있습니다. 몇 주나 몇 달 걸리지 않습니다!

## 앱스플라이어 SDK를 설치 및 업데이트하는 방법은?

앱스플라이어 SDK의 설치 및 업데이트 방법은 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">개발자 허브</Anchor>에서 확인하세요. **참고**: SDK를 업그레이드하면 앱스토어에 새 버전의 앱을 출시해야 합니다.

## 앱스플라이어 SDK를 통합하는 것이 어려운가요?

경험 많은 개발자라면 1시간도 안 되어 앱을 어트리뷰션용으로 준비시킬 수 있습니다. 그 다음에는 앱 당 몇 분만으로 충분합니다.앱 당 몇 분만 투자하면 됩니다./span>

<Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">안드로이드</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">iOS</Anchor>, Unity 및 이러한 <Anchor target="_blank" href="/marketers/ko/docs/other-platforms">기타 플랫폼</Anchor>에 대한 앱스플라이어 SDK 연동 가이드를 확인해보세요.

## 앱스플라이어 SDK가 앱 다운로드 시간에 영향을 끼치나요?

*앱스플라이어 SDK 패키지*는 앱의 성능에 거의 영향을 주지 않도록 설계되고 코딩되었습니다. 모든 SDK 버전은 경량이며, 앱의 크기 중에서 불과 1% 미만을 차지합니다. 즉, **전체 앱 다운로드 시간에 대한 영향은 거의 없습니다**.

* **iOS SDK:** 약 3.4MB

## 앱스플라이어 SDK가 앱의 성능에 영향을 주나요?

*앱스플라이어 SDK API는 주로 *setter*/getter 또는 앱스플라이어 서버와 데이터를 송수신하는 빠른 비동기 웹 서비스 방법을 사용합니다. 이는 SDK API가 앱 성능에 미미한 영향을 준다는 뜻입니다.*

**결론적으로,** 앱스플라이어 SDK는 앱 성능이나 사용자 경험에 아무런 영향을 끼치지 않습니다.

## 앱 외부에서 발생하는 인앱 이벤트도 기록할 수 있나요?

<Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S API를 사용하여 앱 외부에서 발생하는 이벤트를 보고</Anchor>할 수 있습니다. 예를 들어 사용자는 웹 인터페이스를 사용하여 구독을 갱신합니다. 이 구독 갱신 이벤트가 S2S 이벤트로 기록되면, 앱스플라이어 플랫폼 내 대시보드, 로데이터 리포트, 애널리틱스 기능에서 모두 확인할 수 있습니다.

<div data-zendesk-anchors="how-to-install-and-update-the-appsflyer-sdk=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-sdk%EB%A5%BC-%EC%84%A4%EC%B9%98-%EB%B0%8F-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80 h_01HSXBYM9WMD9CDX03RFHM0JY1=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-sdk%EB%A5%BC-%EC%84%A4%EC%B9%98-%EB%B0%8F-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80 is-it-hard-to-integrate-the-appsflyer-sdk=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-sdk%EB%A5%BC-%ED%86%B5%ED%95%A9%ED%95%98%EB%8A%94-%EA%B2%83%EC%9D%B4-%EC%96%B4%EB%A0%A4%EC%9A%B4%EA%B0%80%EC%9A%94 h_01HMTWQHQRGE6Z2BM1BBQY04H1=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-sdk%EB%A5%BC-%ED%86%B5%ED%95%A9%ED%95%98%EB%8A%94-%EA%B2%83%EC%9D%B4-%EC%96%B4%EB%A0%A4%EC%9A%B4%EA%B0%80%EC%9A%94 does-the-appsflyer-sdk-affect-app-download-time=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-sdk%EA%B0%80-%EC%95%B1-%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C-%EC%8B%9C%EA%B0%84%EC%97%90-%EC%98%81%ED%96%A5%EC%9D%84-%EB%81%BC%EC%B9%98%EB%82%98%EC%9A%94 h_01HMTWQHQRQQ47CAJCA4Y0AASZ=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-sdk%EA%B0%80-%EC%95%B1-%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C-%EC%8B%9C%EA%B0%84%EC%97%90-%EC%98%81%ED%96%A5%EC%9D%84-%EB%81%BC%EC%B9%98%EB%82%98%EC%9A%94 does-the-appsflyer-sdk-affect-app-performance=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-sdk%EA%B0%80-%EC%95%B1%EC%9D%98-%EC%84%B1%EB%8A%A5%EC%97%90-%EC%98%81%ED%96%A5%EC%9D%84-%EC%A3%BC%EB%82%98%EC%9A%94 h_01HMTWQHQRXBPQN75J0KM48AJ2=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-sdk%EA%B0%80-%EC%95%B1%EC%9D%98-%EC%84%B1%EB%8A%A5%EC%97%90-%EC%98%81%ED%96%A5%EC%9D%84-%EC%A3%BC%EB%82%98%EC%9A%94 can-i-record-inapp-events-that-occur-outside-my-app=%EC%95%B1-%EC%99%B8%EB%B6%80%EC%97%90%EC%84%9C-%EB%B0%9C%EC%83%9D%ED%95%98%EB%8A%94-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EB%8F%84-%EA%B8%B0%EB%A1%9D%ED%95%A0-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 h_01HMTWQHQSP646Y8KVZSBA01TF=%EC%95%B1-%EC%99%B8%EB%B6%80%EC%97%90%EC%84%9C-%EB%B0%9C%EC%83%9D%ED%95%98%EB%8A%94-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EB%8F%84-%EA%B8%B0%EB%A1%9D%ED%95%A0-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94" />
