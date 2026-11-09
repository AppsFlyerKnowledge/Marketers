---
title: 유저 중심 어트리뷰션(PBA)—개요
metadata:
  keywords:
    - People Based Analysis
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-08-19T11:53:56Z'
  edited_at: '2026-10-14T10:40:36Z'
  id: 360002274017
  locale: ko
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ko/articles/360002274017
---
> **요약: 요약: 유저 중심 어트리뷰션(PBA, People-Based Attribution)은 여러 채널과 플랫폼, 기기를 거치는 고객 여정에 대한 통합적인 시야를 제공합니다.**

<Image align="center" alt="PBANoSilos_us-en.gif" src="https://files.readme.io/1ac3614eb1b9d4c01bffbe904f1a060d1facd681ff32c274b12f0a15612a2e4a-360009359798.gif" />

<div id="pba-principles" />

## PBA 원리

* PBA 데이터는 PBA 대시보드와 로데이터 리포트에 나타나며, 마케팅 분석과 캠페인 최적화에 사용할 수 있습니다.
* 데이터는 웹사이트 방문과 사용자 이벤트로 구성되며, <Anchor target="_blank" href="/marketers/ko/docs/pba-web-sdk-integration-guide">SDK 및/또는 API</Anchor>를 통해 얻습니다.
* 웹사이트 방문 시: 방문을 유도하는 데 관여하는 미디어소스가 결정됩니다. 결과 이벤트(전환)는 방문을 유발하는 미디어소스에 <Anchor target="_blank" href="/marketers/ko/docs/pba-media-source-attribution-rules">어트리뷰트됩니다</Anchor>.

<div id="pba-analytics-dashboards-and-raw-data" />

### PBA 애널리틱스 대시보드 및 로데이터

* PBA 데이터는 분석 대시보드 또는 리포트에 표시되며 다음에 대한 정보를 제공합니다.
  * 웹사이트 어트리뷰션
  * 웹 인스톨 어시스트
  * 로데이터(Raw data) 보고서
* 대시보드 데이터는 모바일 플랫폼, 미디어 채널 및 미디어 타입과 같은 기준으로 <Anchor target="_blank" href="/marketers/ko/docs/using-pba-dashboards">필터링 및 그룹화</Anchor>를 하여 데이터를 상세히 검색하고 분석할 수 있습니다.

<div id="website-attribution" />

### <Anchor target="_blank" href="/marketers/ko/docs/pba-website-attribution-dashboard">웹사이트 어트리뷰션</Anchor>

<Image align="center" alt="WebsiteAttributionTable_us-en.jpg" src="https://files.readme.io/46f03ee216dc23f3f184663aeef7d6b64ae6fb9a64e7a161ff0482e4d2eab204-360013057757.jpg" />

웹 사이트에 대한 사용자 방문 및 전환을 추동하는 웹 트래픽 소스 및 마케팅 캠페인을 분석합니다. 광고 수준까지 성과 차이를 파악합니다. 사용자를 앱스플라이어 서버로 리디렉션할 필요 없이 링크의 모든 앱스플라이어 쿼리 매개 변수를 지원합니다.

<div id="web-assisted-installs" />

### <Anchor target="_blank" href="/marketers/ko/docs/pba-web-assisted-installs">웹 인스톨 어시스트</Anchor>

<Image align="center" alt="AppsFlyer-Web-to-App_us.en.gif" src="https://files.readme.io/4a278b57379c999d80fd7f1dfea750049f56c03ed32051f9af92577b2a51742a-360009705058.gif" />

웹 기여 인스톨을 사용하여 모바일 앱 인스톨을 추동하는 데 대한 웹 마케팅 노력의 영향과 결과를 검토합니다.

* 다양한 미디어 타입(페이드, 온드, 언드 미디어), 미디어 채널(다이렉트, 소셜 미디어, 오가닉 검색) 및 미디어 소스별로 각각 전반적인 유저 유입 마케팅 성과에 어떤 영향을 끼치는지 파악할 수 있는 인사이트를 제공합니다.
* 귀사의 웹 마케팅으로 발생한 오가닉 인스톨을 어트리뷰션 합니다.
* 웹 마케팅과 논오가닉 인스톨 사이의 관계를 분석합니다.

<div id="raw-data" />

### <Anchor target="_blank" href="/marketers/ko/docs/pba-raw-data-reports">로데이터</Anchor>

로데이터 리포트는 데이터 락커를 통해 제공됩니다 로데이터는 깊이 있는 통찰력을 제공하며 사용자를 웹사이트로 유입시킨 데 기여하거나 원인을 제공한 미디어소스를 포함합니다.

* 웹 방문: 웹 사이트에 대한 방문
* 웹 이벤트: 웹사이트에서 수행된 행동. 예: 구독, 구매
* BI 툴로 로데이터를 분석해 또다른 인사이트를 얻을 수 있습니다.

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/onboarding-guide-to-people-based-attribution">PBA 온보딩 가이드</Anchor>

<div data-zendesk-anchors="pba-principles=pba-%EC%9B%90%EB%A6%AC 01ECF26CMJ8TB4ADT6VN277EMQ=pba-%EC%9B%90%EB%A6%AC pba-analytics-dashboards-and-raw-data=pba-%EC%95%A0%EB%84%90%EB%A6%AC%ED%8B%B1%EC%8A%A4-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EB%B0%8F-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0 01ECF26CMJDA1HBC22DGRWY2EA=pba-%EC%95%A0%EB%84%90%EB%A6%AC%ED%8B%B1%EC%8A%A4-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EB%B0%8F-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0 website-attribution=%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01ECF26CMK0T5C9JKQ0SYMXQVM=%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 webassisted-installs=%EC%9B%B9-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%EC%8B%9C%EC%8A%A4%ED%8A%B8 01ECF26CMKDS16XWRBQ1SDAX2Q=%EC%9B%B9-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%EC%8B%9C%EC%8A%A4%ED%8A%B8 raw-data=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0 01ECF26CMM4KHX9W94DND4BY8C=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01HE0Y2KTXS06WHN57MQ91AD09=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
