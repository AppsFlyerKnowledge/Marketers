---
title: 오가닉 검색(SEO) 및 오가닉 AI 답변(AEO) 리인게이지먼트 어트리뷰션 설정
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-05-07T13:34:36Z'
  edited_at: '2026-10-29T09:19:24Z'
  id: 15123194526353
  locale: ko
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ko/articles/15123194526353
---
> **At a glance:** 오가닉 검색 엔진과 AI 답변 엔진에서 리인게이지먼트(이미 앱을 설치한 사용자)에 대한 상세한 어트리뷰션 데이터를 얻어 오가닉 검색 및 AI 기반 전환을 최적화하세요.

<div id="overview" />

## 개요

오가닉 검색(SEO) 및 오가닉 AI 답변(AEO 리인게이지먼트 어트리뷰션은 앱스플라이어 고객이 리인게이지먼트(즉, 이미 앱이 설치된 사용자의 모바일 앱 열기)를 다양한 오가닉 검색 엔진과 AI 답변 엔진에 어트리뷰션할 수 있도록 하는 어트리뷰션 솔루션입니다.

이 고유 데이터에 접근할 수 있다면 SEO(검색엔진 최적화) 및 AEO(답변엔진 최적화) 팀에 매우 유용하며, 추진 중인 SEO 및 AEO 전략의 성과에 대해 대단히 값진 피드백을 얻을 수 있습니다.

<div id="flow" />

### 흐름

![사용자가 검색 결과를 클릭한 시점부터 앱이 열리거나 사용자가 웹페이지에 도달하는 시점까지의 오가닉 검색 어트리뷰션 흐름을 보여주는 다이어그램](https://files.readme.io/4b33060cfa30a4e2786c4a3a213ca41223ae276d63c97ab7c2cb5a997a4b010c-16540659217809.png)

오가닉 검색 어트리뷰션 흐름은 다음과 같습니다.

1. 사용자가 모바일 브라우저 검색 엔진(Google, Bing 등)에서 용어를 검색합니다. 검색 엔진은 클릭 가능한 여러 결과를 표시합니다.
2. 이러한 검색결과 중 일부는 웹 개발자가 Android App Links 및 iOS Universal Links를 사용하여 모바일 앱을 열도록 매핑됩니다. 사용자가 앱을 설치한 경우 검색 결과를 클릭하면 먼저 앱 스토어로 리디렉션되지 않고 앱이 열립니다.
3. 앱 실행 시 앱스플라이어는 필요한 정보를 수집하고 열려 있는 앱을 사용자의 검색 엔진에 어트리뷰션할 수 있습니다.
4. 사용자가 앱을 설치하지 않은 경우 웹 랜딩 페이지로 이동하는 데 여기에서 사용자는 여러 앱스플라이어 웹-투-앱 솔루션(예: Smart Banners, Smart Script 또는 QR 코드) 중 하나를 사용하여 리디렉션하고 어트리뷰션할 수 있습니다.

<div id="setup" />

## 설정

**필수 사항**:

* 앱스플라이어 안드로이드 SDK V6.12.1
* 앱스플라이어 iOS SDK V6.12.1

**오가닉 검색 어트리뷰션 설정 방법**:

1. 개발팀에 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#app-opening-methods">Android App Links</Anchor> 및 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#app-opening-methods">iOS Universal Links</Anchor> 가이드(앱의 최상위 도메인 사용)를 참조하여 앱 자동 실행을 활성화하도록 요청하세요.
2. 앱스플라이어의 사이드 메뉴에서 **설정** > <Anchor target="_blank" href="/marketers/ko/docs/app-settings">앱 설정</Anchor> 선택하고 다음을 켭니다.
   * **SEO(오가닉 검색) 및 AEO 모바일 앱 리인게이지먼트 어트리뷰션.**
   * **리인게이지먼트 어트리뷰션**.

> 📘 **Note**
>
> **개발자를 위한 참고 사항**
>
> performOnDeepLinking은 호출 시 딥링크 URL을 강제로 소비하고 해석합니다. 이렇게 하면 SEO 어트리뷰션 기능이 제대로 작동하지 않고 올바른 SEO 미디어소스에 어트리뷰션을 리포트하지 못하게 됩니다.

<div id="data-availability" />

## 데이터 가용성

데이터는 다음과 같이 사용할 수 있습니다.

* 대시보드 및 리포트의 집계 데이터에서 `media_source` 필드는 사용자가 사용한 검색 엔진을 나타냅니다. 예시: `google_organic_seo`.
* 로우 데이터 리포트에서:
  * `media source` 필드는 사용자가 사용한 검색 엔진을 나타냅니다. 예시: `google_organic_seo`.
  * `http_referrer` 필드에는 사용자가 앱 또는 모바일 방문 페이지로 이동된 검색 결과 페이지의 기본 URL이 포함됩니다.
  * `channel` 필드에 오가닉 검색 트래픽 값 `seo`가 있거나 AI 답변 엔진 트래픽 값 `aeo`가 있습니다.

<div id="additional-information" />

## 추가 정보

<Accordion title="지원하는 검색 엔진 목록">

오가닉 검색 어트리뷰션은 다음 검색 엔진을 지원합니다.

* Google
* Bing
* Yahoo
* Ask
* DuckDuckGo
* Yandex
* 네이버
* 다음
* Baidu
* Ecosia
* Coccoc
* Sogou
* Yahoo Japan

> 📘 **Note**
>
> 기타 검색 엔진의 경우 기존 오가닉 검색 어트리뷰션 솔루션을 사용하세요(개발자 작업 필요).
>
> 대시보드와 데이터 리포트에서 검색 엔진은 `<search engine>`\_organic\_seo로 표시됩니다. 예시: google\_organic\_seo.

</Accordion>

<Accordion title="지원되는 AI 답변 엔진 목록">

자연 검색 어트리뷰션은 다음 AI 답변 엔진도 지원합니다.

* ChatGPT
* Claude
* Perplexity
* Manus
* Copilot
* Gemini
* Grok
* Deepseek

> 📘 **Note**
>
> 대시보드와 데이터 리포트에서 AI 답변 엔진은 `<AI engine>`\_organic\_aeo로 표시됩니다. 예시: chatgpt\_organic\_aeo.

</Accordion>

<Accordion title="FAQ">

<Accordion title="오가닉 SEO 어트리뷰션에는 추가 비용이 발생하나요?">

아니요, 이 기능은 구독에 포함되어 있습니다.

</Accordion>

<Accordion title="오가닉 SEO 전환이 내 패키지에 포함되어 있나요?">

예, 논오가닉 전환과 동일합니다.

</Accordion>

<Accordion title="SEO 미디어 소스의 이름을 사용자 지정할 수 있나요?">

아니오. 오가닉 SEO 미디어 소스의 이름은 앱스플라이어에 의해 결정되며 현재로서는 커스터마이징할 수 없습니다.

</Accordion>

<Accordion title="검색 엔진이 자연 검색 결과 옆에 설치 버튼을 표시하고 사용자가 이를 클릭하여 앱 스토어로 이동하는 경우, 앱스플라이어는 해당 설치를 해당 검색 엔진의 기여로 측정하나요?">

아니오. 이 경우 앱스플라이어는 어트리뷰션에 필요한 정보를 수집할 수 없습니다. 오가닉 검색 어트리뷰션을 사용하려면 앱이 이미 설치되어 있어야 합니다.

</Accordion>

<Accordion title="키워드 데이터를 사용할 수 있나요?">

키워드 데이터는 이 오가닉 검색 어트리뷰션 솔루션을 통해 사용할 수 없습니다. 하지만 Android에서 키워드 데이터를 사용할 수 있는 예외적인 경우가 있기도 합니다. <Anchor target="_blank" href="/marketers/ko/docs/evaluate-keyword-data#안드로이드-키워드">Android 키워드 데이터 지원 여부</Anchor>를 확인하세요.

</Accordion>

<Accordion title="설치 흐름(플로우)에서도 오가닉 검색 어트리뷰션이 지원되나요?">

예, 앱을 설치한 사용자가 웹 사이트에 도착한 페이지를 통해 확인할 수 있습니다.

Smart Script는 다음과 같은 방식으로 이를 수행합니다:

* 웹 리퍼러라고 하는 페이지의 URL 도메인 수집
* 사용자의 구체적인 유입 경로를 기반으로 관련 `pid` 생성(이후 미디어 소스로 표시됨)
* 발신 URL에서 `af_sub1`과 같이 원하는 파라미터 키에 매핑

웹 리퍼러 수집을 위한 Smart Script 설정 방법은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#seo-referrer-mapping">OneLink Smart Script V2 설정 가이드</Anchor>를 확인하세요.

</Accordion>

</Accordion>

<Accordion title="특징 및 제한 사항">

| 특징 | 설명 |
| --- | --- |
| 브라우저 | 오가닉 검색 어트리뷰션은 다음에서 지원되지 않습니다.<ul><li>Android의 FireFox</li><li>iOS의 Safari를 제외한 모든 브라우저.</li></ul> |
| SwiftUI 앱(iOS) | SwiftUI로 빌드된 iOS 앱에서는 오가닉 검색 어트리뷰션이 지원되지 않습니다. |
| 리인게이지먼트 기간 | 오가닉 검색의 리인게이지먼트 기간은 30일로 고정되어 있습니다. 기간은 변경할 수 없습니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide#포함-기간">리타겟팅 어트리뷰션 가이드</Anchor>를 참조하세요. |

</Accordion>

<div data-zendesk-anchors="organic-search-attribution=%EA%B0%9C%EC%9A%94 h_01H9G0W21SRDC6ZSR1E8AQFZFC=%EA%B0%9C%EC%9A%94 flow=%ED%9D%90%EB%A6%84 h_01H9G0W21S4RB56PNV9DAYZPB2=%ED%9D%90%EB%A6%84 setup=%EC%84%A4%EC%A0%95 h_01H9G0W21S6Z0A5QXC52KSYVQS=%EC%84%A4%EC%A0%95 data-availability=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1 h_01H9G0W21S7KVJ2Z5DRPCHZF4Z=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1 additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01H9G0W21SERW2HC44KD77FNCG=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4" />
