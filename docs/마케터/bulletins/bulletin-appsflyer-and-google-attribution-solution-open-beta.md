---
title: '업데이트 알림: AppsFlyer 및 Google 귀속 솔루션'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2025-08-06T13:24:32Z'
  edited_at: '2026-10-14T10:28:35Z'
  id: 37857301293457
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/37857301293457
---
<Embed title="YouTube video player" typeOfEmbed="youtube" url="https://www.youtube.com/embed/5u2sK5dfrR4?si=6TpIQXP1YU93MmI6" providerUrl="https://www.youtube.com" />

| 섹션 | 세부 내용 |
| --- | --- |
| **새로운 소식** | Google의 통합 전환 측정(ICM) 솔루션은 설치 및 재귀속을 측정하기 위해 Google Ads를 사용하는 모든 클라이언트에게 제공됩니다. |
| **시행일** | <ul><li>**iOS:** $475.22</li><li>**안드로이드:** $475.22</li></ul> |
| **주요 변경 사항:** | <ul><li>ICM은 AppsFlyer가 장치 ID 없이도 개인 정보 보호 방법을 사용하여 Google Ads에 설치를 귀속할 수 있게 합니다.</li><li>Google은 AppsFlyer에 비결정론적 설치 청구를 보냅니다.<br />AppsFlyer의 데이터로 검증된 경우, 이러한 청구는 귀속에 사용됩니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-advertisers#고급-데이터-공유를-활용한-google-ads-어트리뷰션-흐름">Google Ads 귀속 흐름 및 고급 데이터 공유</Anchor>를 참조하십시오.</li></ul> |
| **필요한 조치** | <ul><li>SDK 요구 사항<ul><li>**iOS:** AppsFlyer <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes">iOS SDK 버전 6.17.5</Anchor> 이상 또는 *및* Google <Anchor target="_blank" href="https://github.com/firebase/firebase-ios-sdk/releases">Firebase SDK 버전 11.14.0</Anchor> 이상 또는 독립형 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/16384720">Google ODM SDK</Anchor>가 필요합니다.</li><li>**안드로이드:** SDK 업데이트가 필요하지 않습니다.</li></ul></li><li>**고급 데이터 공유 토글:** iOS 및 Android `googleadwords_int` 통합 모두에 대한 새로운 설정:<ul><li>**활성화된 경우**: AppsFlyer는 장치 ID 없이도 모든 설치 이벤트를 Google에 보냅니다.</li><li>**비활성화된 경우**: 사용 가능한 장치 ID 또는 GCLID가 있는 설치 이벤트만 공유되며, ICM의 효과가 제한됩니다.</li></ul></li><li>**중요:** iOS용 ICM은 현재 EU 사용자에게 **사용할 수 없습니다**.</li></ul> |