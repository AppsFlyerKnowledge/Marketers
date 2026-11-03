---
title: 앱스플라이어와 Tealium 연동
metadata:
  keywords:
    - Marketers
    - TEST ID LOC
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-22T16:09:24Z'
  edited_at: '2026-10-14T10:39:19Z'
  id: 10820404821393
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/10820404821393
---
> **한눈에 보기:**

<Image alt="Tealium_icon.png" src="https://files.readme.io/e3cc1f95e8ce2de6fa83df63ff78dd4f4f76aebe1acb8e9378aa5b6aa4134364-10820461521681.png" width="276px" />

## 개요

모바일 사용자는 Tealium과 앱스플라이어를 연동함으로써 앱스플라이어 모바일 어트리뷰션 SDK를 활용하고 어트리뷰션 전환 데이터를 Tealium AudienceStream 프로필로 직접 전송할 수 있습니다.

> 🚧 **중요!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">일부 미디어소스</Anchor>는 타사와의 데이터 공유를 제한합니다. 따라서 제한된 이벤트에 대한 포스트백은 포스트백을 보내기 위해 구성된 선택에 관계없이 이 파트너에게 전송되지 않습니다.

## Tealium 설정

다음 방법 중 하나를 선택하여 Tealium을 앱스플라이어와 연동할 수 있습니다.

* 클라이언트 측 연동
* 서버 측 사이드 연동

### 클라이언트 측 연동

iOS 및 안드로이드 라이브러리에 대한 원격 명령을 사용하여 앱스플라이어 SDK에서 네이티브 코드를 트리거할 수 있습니다.

**클라이언트 측 연동을 사용하여 Tealium을 통합하는 방법:**

* 원격 명령 연동 가이드를 따릅니다.

### 서버 측 사이드 연동

고객 데이터 허브 계정에서 앱스플라이어 앱 이벤트 커넥터를 설정하여 Tealium과 앱스플라이어 간에 실시간으로 데이터를 전송합니다.

**서버 측 연동을 사용하여 Tealium을 통합하는 방법:**

* <Anchor target="_blank" href="https://docs.tealium.com/server-side-connectors/appsflyer-app-events-connector/">앱스플라이어 앱 이벤트 커넥터 가이드를 따르십시오.</Anchor>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01H9HWK1ACY09ZVD7WHEQR4MR3=%EA%B0%9C%EC%9A%94 h_01H9HWK1ACA6A743PDY3Q1Y0KV=%EC%A4%91%EC%9A%94 setting-up-tealium=tealium-%EC%84%A4%EC%A0%95 h_01H9HWK1AC27GPZPZR13SFC3GM=tealium-%EC%84%A4%EC%A0%95 clientside-integration=%ED%81%B4%EB%9D%BC%EC%9D%B4%EC%96%B8%ED%8A%B8-%EC%B8%A1-%EC%97%B0%EB%8F%99 h_01H9HWK1ACH6K0FDTVCHAPSKME=%ED%81%B4%EB%9D%BC%EC%9D%B4%EC%96%B8%ED%8A%B8-%EC%B8%A1-%EC%97%B0%EB%8F%99 serverside-integration=%EC%84%9C%EB%B2%84-%EC%B8%A1-%EC%82%AC%EC%9D%B4%EB%93%9C-%EC%97%B0%EB%8F%99 h_01H9HWK1ACDZQEYVRZ7QWQ4KY3=%EC%84%9C%EB%B2%84-%EC%B8%A1-%EC%82%AC%EC%9D%B4%EB%93%9C-%EC%97%B0%EB%8F%99" />
