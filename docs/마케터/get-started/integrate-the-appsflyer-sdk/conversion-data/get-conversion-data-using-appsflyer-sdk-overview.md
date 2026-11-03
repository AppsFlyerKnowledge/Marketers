---
title: 앱스플라이어 SDK를 이용한 전환 데이터 얻기 - 개요
metadata:
  keywords:
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
  created_at: '2021-11-09T10:06:52Z'
  edited_at: '2026-10-14T10:40:25Z'
  id: 4410481069969
  locale: ko
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/ko/articles/4410481069969
---
> **요약:** 전환 데이터를 활용해 다양한 전환 상황을 파악하고 유저 경험을 맞춤 설정할 수 있습니다.

전환 데이터 활용 방법:

* 특정 활동으로 유저를 유도
* 맞춤형 콘텐츠 제공

정확도와 속도는 반비례하며 동일한 디바이스 ID의 전환 데이터는 API마다 다를 수 있습니다.

## 전환 데이터 얻기

앱스플라이어 SDK는 다음 방법으로 전환 데이터를 제공합니다:

* * `onConversionDataSuccess`: 유저 유입(UA) 및 리어트리뷰션 전환 데이터  
    * 안드로이드: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerconversionlistener#onconversiondatasuccess">onConversionDataSuccess</Anchor>
    * iOS: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlibdelegate#onconversiondatasuccess">onConversionDataSuccess</Anchor>
    * Unity: loadConversionData
  * `onAppOpenAttribution`: 리인게이지먼트 전환 데이터

<div data-zendesk-anchors="get-conversion-data=%EC%A0%84%ED%99%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%96%BB%EA%B8%B0 h_01HTZ6M409RPZAQM66R0H5HA16=%EC%A0%84%ED%99%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%96%BB%EA%B8%B0" />
