---
title: 스마트 스크립트를 사용한 크로스 플랫폼 랜딩 페이지
metadata:
  keywords:
    - CTV
    - Marketers
    - gaming
    - cross-platform
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2023-09-10T07:17:21Z'
  edited_at: '2026-10-14T10:34:18Z'
  id: 18440789126289
  locale: ko
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/ko/articles/18440789126289
---
> **간단히 보기:** 앱스플라이어 스마트 스크립트를 운영하는 크로스 플랫폼 랜딩 페이지를 사용하여 웹-앱 어트리뷰션을 수행합니다. 즉, 웹 광고를 본 사용자를 CTV, PC, 콘솔 또는 모바일 플랫폼의 앱 사용자로 전환합니다.

## 개요

앱스플라이어 스마트 스크립트를 운영하는 크로스 플랫폼 랜딩 페이지를 사용하면 웹-앱 어트리뷰션을 수행할 수 있습니다. 이는 모든 플랫폼에서 발생한 인스톨을 웹에 표시된 광고에 어트리뷰션할 수 있다는 의미입니다.

크로스 플랫폼 랜딩 페이지의 스마트 스크립트는 들어오는 링크 (웹 광고의 링크)를 사용하여 원래 미디어 소스와 웹 광고가 인스톨과 함께 어트리뷰션되도록 하는 두 가지 작업을 수행합니다.

* 앱스플라이어에 노출을 전송하는 크로스 플랫폼 원링크 링크를 만듭니다.
* 각 앱/플랫폼에 대한 직접 어트리뷰션 링크를 생성합니다.

## 설정

#### 작업 범위

| **참여 대상**<ul><li>**광고주**:<ul><li>스마트 스크립트의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#arguments">인수</Anchor>에 따라 나가는 [크로스 플랫폼 노출](#create-crossplatform-impression-link) 및 [직접 어트리뷰션 링크](#create-direct-attribution-links)에 포함되어야 할 내용을 결정합니다. 이는 들어오는 URL을 조작하거나 특정 값을 강제로 지정하여 나가는 URL에 추가되는 어트리뷰션 데이터를 결정합니다.</li><li>웹사이트로 연결되는 모든 캠페인에 스크립트가 처리할 수 있는 파라미터가 있는 수신 URL이 있는지 확인합니다.</li><li><Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">스마트 스크립트를 테스트합니다</Anchor>.</li></ul></li><li>**웹 개발자**:<ul><li>스크립트에 인수를 추가하고 랜딩 페이지에 스마트 스크립트를 구현합니다.</li><li>스마트 스크립트를 테스트합니다.</li></ul></li></ul> |
| --- |
| **전제 조건**<ul><li>최소 1개 이상의 앱이 있는 앱스플라이어 계정이 필요합니다.</li><li>노출 URL 예시: 크로스 플랫폼 어트리뷰션이 활성화된  <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿</Anchor> .</li></ul> |

<div id="create-crossplatform-impression-link" />

<Accordion title="크로스 플랫폼 노출 링크 생성">

**앱스플라이어에 노출을 보내는 크로스 플랫폼 원링크 링크를 생성하려면** :

1. 수신 링크 파라미터를 노출 링크에 포함되어야 하는 파라미터(미디어 소스, 캠페인, 광고 이름 등)에 매핑합니다.
   * 들어오는 URL을 처리하는 스크립트의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#arguments">인수</Anchor>에 대해 더 보기를 참조하세요.
   * 이 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#arguments">OneLinkURL 인수</Anchor>의 값은 크로스 플랫폼 어트리뷰션이 활성화된 원링크 템플릿의 도메인+ID입니다.
2. 개발자에게 스마트 스크립트 인수를 초기화하고 스마트 스크립트 메서드를 호출하도록 지시하세요. `generateOneLinkURL` <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">개발자 데모 및 지침을 확인하세요</Anchor>.  
   **참고:** `af_xplatform=true` 파라미터는 크로스 플랫폼 어트리뷰션을 활성화하는 데 필수입니다.

</Accordion>

<div id="create-direct-attribution-links" />

<Accordion title="직접 어트리뷰션 링크 만들기">

1. 유입 링크 파라미터를 나가는 직접 어트리뷰션 링크에 포함해야 하는 파라미터(미디어 소스, 캠페인, 광고 이름 등)에 매핑합니다. 들어오는 URL을 처리하는 스크립트의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#arguments">인수</Anchor>에 대해 더 알아보세요.
2. 개발자에게 스마트 스크립트 인수를 초기화하고 스마트 스크립트 메서드를 실행하여  각 플랫폼/앱에 대한 링크를 생성하도록 요청하세요. 개발자 <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">데모</Anchor> 및 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/create-direct-click-url">지침</Anchor>을 확인하세요.  
   참고: 개발자는 다음 파라미터를 추가해야 합니다.  

| 파라미터/인수 | 비고 | 개발자 또는 사용자가 참고할 수 있도록 응답 내용을 기록하세요 |
| --- | --- | --- |
| 플랫폼 | 플랫폼을 설명하는 문자열은 다음 목록 중 하나여야 합니다.<ul><li>스마트캐스트</li><li>티젠</li><li>로쿠</li><li>웨보스</li><li>비다</li><li>플레이스테이션</li><li>안드로이드</li><li>iOS</li><li>스팀</li><li>퀘스트</li><li>배틀넷</li><li>네이티브PC</li></ul> |  |
| 앱\_ID | <ul><li>앱 ID</li><li>예시: 123456</li></ul> |  |
| 리다이렉트URL | <ul><li>플랫폼/앱 사용자가 리다이렉션되어야 할 URL입니다.</li><li>예시:</li></ul> |  |


</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 01H8V0RV7X8JEVEJ36TJB1X43D=%EA%B0%9C%EC%9A%94 setup=%EC%84%A4%EC%A0%95 01H8V0RV7X0K157JTDQMJSQYKF=%EC%84%A4%EC%A0%95 scope-of-work=%EC%9E%91%EC%97%85-%EB%B2%94%EC%9C%84 h_01H95PGMNWPBRHSZBPMKNJ2PS6=%EC%9E%91%EC%97%85-%EB%B2%94%EC%9C%84 01H8EQ4KS75Q62Z7WVNSTDXBZX=create-crossplatform-impression-link 01H8EQ4KS7C6HADNKQZYNTTFMF=create-direct-attribution-links" />
