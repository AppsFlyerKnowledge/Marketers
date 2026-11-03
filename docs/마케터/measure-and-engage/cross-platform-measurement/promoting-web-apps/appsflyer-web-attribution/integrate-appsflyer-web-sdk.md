---
title: '[베타] 앱스플라이어 웹 SDK 통합'
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-03T15:23:52Z'
  edited_at: '2026-10-14T10:27:19Z'
  id: 43485611331473
  locale: ko
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ko/articles/43485611331473
---
> **한눈에 보기:** 웹사이트에 앱스플라이어 웹 SDK(픽셀)를 설치하여 사용자 방문 및 이벤트를 앱스플라이어에 보고하고, 고유한 고객 사용자 ID(CUID)를 설정하여 여러 플랫폼 간의 여정을 통합하세요.

## 개요

웹 SDK를 사용하면 방문자가 웹사이트와 상호작용하는 방식을 기록하고 이 정보를 앱스플라이어로 전송할 수 있습니다. 해당 모듈은 40–60 KB 용량의 플러그인으로, 사용자의 웹사이트 방문 및 액션 데이터를 앱스플라이어 플랫폼으로 전송합니다.

설치부터 검증 및 프라이버시 제어에 이르기까지, 다음 단계에 따라 웹 SDK 연동을 완료하세요.

1. [키 얻기.](#1-키-얻기) Web SDK ID(또한 Web 개발자 키라고도 함)를 얻습니다.
2. [코드 조각 선택.](#2-코드-스니펫-선택) 통합 유형과 보안 요구 사항과 일치하는 스냅트를 선택합니다.
3. [Web SDK 구축.](#3-deploy-the-스냅트) Native Snippet, Google Tag Manager 또는 Adobe Launch Tag Manager를 사용하여 SDK를 구축합니다.
4. [SDK 작동여부 확인.](#2-sdk가-작동하는지-확인하십시오) 브라우저 개발자 도구에서 네트워크 호출을 확인하여 SDK가 요청을 보내는지 확인합니다.
5. [이벤트 설정 및 기록.](#3-설정-및-이벤트-기록) 기본 JavaScript 또는 Google 태그 관리자를 사용하여 페이지 로드 또는 사용자 상호 작용에 맞춤 이벤트를 정의하고 전송합니다.
6. [고객 사용자 ID 설정.](#4-고객-사용자-id-설정하기) 지속적인 CUID를 설정하여 웹 활동을 다른 플랫폼과 통합합니다.
7. [개인 정보 관리.](#5-개인-정보-관리) 측정 옵트인(opt-in) 및 옵트아웃(opt-out) 여부를 관리하고, 보안 및 데이터 필터링(콘텐츠 보안 정책 및 쿼리 파라미터 제외 설정)을 설정하세요.
8. [Web SDK 쿠키 참조.](#웹-sdk-쿠키-참조) Web SDK가 설정하거나 사용하는 쿠키, 목적, 수명 및 범위를 포함하여 검토합니다.

## 1. 키 얻기

**Web SDK ID(웹 개발자 키라고도 함):**

1. AppsFlyer에서 상단 메뉴에서 열면 됩니다 **앱 설정**.
2. 페이지 상단의 앱 선택기에서 웹 앱(웹사이트 도메인에 "website-"이 붙은 곳)을 선택하세요.
3. 언더로 **SDK 인증**, 복사했습니다 **웹 SDK ID**.

**Smart Banner 키(필요한 경우):**

1. 앱스플라이어 측면 메뉴에서 **인게이지(Engage)** > **웹-to-앱(Web to App)** > **스마트 배너(Smart Banners)** 를 선택합니다.
2. 필요한 스마트 배너 키를 복사합니다.

## 2. 코드 스니펫 선택

연동 유형 및 보안 요구 사항에 맞는 코드 스니펫을 선택하세요. 두 가지 옵션:

* [Standard Web SDK](#표준-웹-sdk): 표준 통합.
* [Advanced SDK Verification](#고급-sdk-검증): Web SDK를 위한 공급망 보호 기능을 추가하는 향상된 통합 기능. 이를 사용하여 CDN 타협, DNS 납치 및 중간에 있는 사람 공격에 대한 보안을 추가합니다.

> 🚧 **중요!**
>
> Standard Web SDK에서 Advanced SDK Verification로 전환하는 경우 기존 스냅트를 새 스냅트로 교체합니다. 기존 스냅트 위에 새 스냅트를 추가하지 마십시오.

### 표준 웹 SDK

이 스냅트를 사용하여 표준 Web SDK 통합을 배포합니다. SDK를 로드하려는 모든 페이지의  태그 상단에 붙여넣습니다.

<div id="standard-without-smart-banners" />

<Accordion title="스마트 배너 없음">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Inject SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  // Replace WEB_DEV_KEY with your Web SDK ID
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
</script>
```

</Accordion>

<div id="standard-with-smart-banners" />

<Accordion title="스마트 배너">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Inject SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  // Replace WEB_DEV_KEY with your Web SDK ID
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba,banners&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
  AF('banners', 'showBanner');
</script>
```

</Accordion>

### 고급 SDK 검증

Advanced SDK Verification는 Web SDK에 공급망 보호 기능을 추가합니다. 이것은 사용자의 브라우저에서 실행되는 코드가 AppsFlyer가 게시한 정확한 것으로 보장합니다. SDK 소스 코드는 표준 통합과 동일합니다. 전달 및 검증 메커니즘만 다릅니다.

Advanced SDK 검증:

* CDN 타협, DNS 납치 및 Man-in-the-Middle 공격에 대한 추가 보안 층을 추가합니다.
* SDK 로딩 시간에 약 250ms를 추가합니다.

Advanced SDK SDK Verification 는 선택 사항입니다. 표준 통합은 여전히 완전히 지원되고 타사 분석 픽셀의 시장 표준입니다. Advanced SDK Verification 는 해당 표준 이외의 추가적인 보호 층을 제공합니다.

웹 사이트에서 nonce를 사용하여 콘텐츠 보안 정책(CSP)을 적용하는 경우, 이 스냅트의 nonce 확장 버전을 관리하는 개인 정보 보호 섹션의 [Content 보안 정책(CSP)](#콘텐츠-보안-정책csp)을 참조하십시오.

<div id="advanced-verification-without-smart-banners" />

<Accordion title="스마트 배너 없음">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"]
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<div id="advanced-verification-with-smart-banners" />

<Accordion title="스마트 배너">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"]
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

## 3. Deploy the 스냅트

단계 2에서 선택한 스냅트를 다음 방법 중 하나를 사용하여 배포합니다. SDK가 페이지 로드당 한 번 로드되는지 확인합니다.

<div id="option-a-add-directly-to-your-website" />

<Accordion title="옵션 A: 직접 귀하의 웹사이트에 추가">

모든 페이지에서 이렇게 반복하십시오:

1. 2단계의 스냅트에서 `WEB_DEV_KEY`를 Web SDK ID(및 `YOUR_BANNER_KEY`)로 대체합니다.
2. 스냅트를 웹사이트의  태그의 상단에 붙여넣습니다.

</Accordion>

<div id="option-b-deploy-via-google-tag-manager" />

<Accordion title="옵션 B: Google 태그 관리자(GTM)를 통해 구축">

SDK가 페이지 로드 당 한 번 로드되었는지 확인하고 GTM 우선 순위를 사용하여 페이지가 로드되면 로드하도록 설정하십시오.

1. Google Tag Manager를 사용합니다.
2. 앱스플라이어 웹 SDK에 대한 새 태그를 생성합니다.
3. **Custom HTML** 태그 유형을 선택합니다.
4. 태그에 의미 있는 이름을 지정하십시오.
5. Step 2의 스냅트를 **태그 구성**에 붙여넣습니다.
6. **저장**을 클릭하세요.
7. 트리거 추가:
   * 모든 페이지:
     1. **Add Trigger(트리거 추가)** 를 클릭합니다.
     2. **모든 페이지(All Pages)** 를 선택합니다.
     3. **저장**을 클릭하세요.
     4. 태그 이름을 입력하고 **저장**을 클릭합니다.
   * 특정 페이지:
     1. **Save Tag(태그 저장)** 를 클릭합니다.
     2. GTM 기본 창에서 **Triggers(트리거)** 를 선택합니다. New(신규)를 클릭합니다.
     3. 펜 아이콘을 클릭합니다.
     4. **Page View(페이지 보기)** 트리거 유형을 선택합니다.
     5. **Some Page View(일부 페이지 보기)** 를 선택합니다.
     6. 필요에 따라 페이지 및 트리거 조건을 설정하십시오.
     7. **저장**을 클릭하세요.
     8. 트리거를 앱스플라이어 웹 SDK 태그에 연결하십시오.
        1. GTM 기본 창에서 태그를 선택하십시오.합니다.
        2. 이전에 생성한 태그를 선택하십시오.
        3. 트리거 패널에서 펜 아이콘을 클릭하십시오.
        4. 이전에 생성한 페이지 뷰 트리거를 선택하십시오.
        5. **저장**을 클릭하세요.

> 📘 **참고**
>
> 고급 SDK 인증은 GTM 사용자 지정 템플릿을 지원하지 않습니다. 그들의 샌드박스 환경에서는 인증에 필요한 `integrity` 속성을 설정할 수 없습니다. 대신 **Custom HTML** 태그 유형을 사용합니다.

</Accordion>

<div id="option-c-deploy-via-adobe-launch-tag-manager" />

<Accordion title="옵션 B: Adobe Launch Tag Manager를 통해 구축">

#### Adobe Experience Cloud에 속성 생성

1. Adobe Experience Cloud > Launch로 가십시오.
2. **Adobe Experience Cloud Launch** 아래 Go to Launch를 클릭합니다.
3. **New Property**를 클릭합니다.
4. 속성 이름을 지정합니다.
5. **플랫폼** 아래 **웹**을 선택합니다.
6. 귀하의 웹사이트 도메인을 입력합니다.
7. **저장**을 클릭하세요.

#### Adobe Launch 속성에 스냅트 추가

1. **My web property(나의 웹 속성)** 페이지에서 **Rules(규칙)** 탭을 선택합니다.
2. 규칙의 이름을 지정한다. 권장: 웹 SDK 로드.
3. **'만약'** 절에서, **이벤트** 아래 **+추가** 버튼을 클릭하세요.
   * **Event Type(이벤트 유형)** 에서 **코어 - DOM 준비**를 선택하십시오.
   * **변경 유지**를 클릭합니다.
4. **'그런 다음'** 절에서, **액션** 아래 **+추가** 버튼을 클릭하세요.
   * **Action Type** 아래에서 **Custom Code**을 선택합니다.
   * **JavaScript** > **Open Editor를** 선택하고 2단계의 스크립트를 붙여 넣습니다.
   * **변경 유지**를 클릭하여 코드 편집기를 닫습니다.
5. **저장**을 클릭하세요.

#### Adobe Launch 태그를 웹사이트에 추가

1. **My web property** 페이지에서 **환경** 탭을 선택합니다.
2. 퍼블리시할 환경(개발 환경 혹은 실 운영 환경)이 있는 행을 찾으십시오.
3. **Install** 열 아래에 해당 행의 상자 아이콘을 클릭합니다.
4. **웹 설치 지침** 대화 상자에서 스크립트 코드 조각을 복사하고 대화 상자를 닫습니다.
5. 코드 조각을 귀하의 웹사이트 &lt;head> 태그에 붙여넣습니다.

#### Adobe Launch 환경 게시

1. **My web property** 페이지에서 **퍼블리싱** 탭을 선택합니다.
2. **Development** 섹션에서 **새 라이브러리 추가**를 클릭합니다.
   * 라이브러리를 명명하고 환경을 선택하세요.
   * **리소스 변경** 영역에서 **리소스 추가** 버튼을 클릭하세요.
   * **규칙** > **웹 SDK 로드** > **최신** > **새 버전 선택 및 만들기를** 클릭합니다.
   * **저장**을 클릭하세요.
3. **Development** 섹션 아래에서:
   * 새로 생성된 라이브러리 옆에 조치 메뉴(점 3개)를 클릭해서 > **Build for Development**를 선택합니다.
   * 다시 조치 메뉴를 클릭하고 > **승인을 위한 제출**을 선택합니다.
4. **제출됨** 섹션 아래에서:
   * 조치 메뉴를 클릭하고 > **Build for Staging**을 선택합니다.
   * 조치 메뉴를 클릭하고 > **퍼블리싱 승인**을 선택합니다.
5. **승인됨** 섹션에서 다음을 수행합니다.
   * 조치 메뉴를 클릭하고 > **프로덕션에 빌드 및 게시**를 선택합니다.

</Accordion>

## 2. SDK가 작동하는지 확인하십시오.

설치 후, 브라우저의 개발자 도구에서 네트워크 요청을 확인하여 SDK가 요청을 전송하는지 확인합니다.

[<Image alt="DevTools 스크린샷" src="https://files.readme.io/a1bb1f22e9d30059830239e7a4d13d7cde106a3363502cb9e8a054d6e8d65dff-43492318562833.png" width="1015px" />](https://files.readme.io/a1bb1f22e9d30059830239e7a4d13d7cde106a3363502cb9e8a054d6e8d65dff-43492318562833.png)

**SDK가 작동하는지 확인하려면 다음 단계를 수행하십시오.**

1. 웹사이트를 엽니다.
2. 브라우저 개발 도구를 여십시오.
3. (A) **네트워크** 탭으로 이동합니다.
4. 페이지를 새로 고치십시오.
5. 필터링 기준 두 가지 요청이 나타날 수 있습니다:
   * **SDK loader** — 요청 URL은 `https://websdk.appsflyersdk.com`로 시작합니다. 이것은 SDK 스크립트가 올바르게 로드 된 것을 확인합니다.
   * **사건 데이터** — 요청 URL은 `https://wa.appsflyer.com/events`로 시작합니다. 이것은 SDK가 이벤트 데이터를 AppsFlyer로 전송하는 것을 확인합니다.
6. (C) **events** 메시지를 선택합니다(`wa.appsflyer.com` 호출).
7. 헤더 아래, (D) 확인:
   * 요청 URL은 `https://wa.appsflyer.com/events?site-id=`로 시작합니다.
   * 쿼리 파라미터
   * (E) 상태 코드는 200입니다.
8. `site_id`가 AppsFlyer > 상단 메뉴 > **내 앱**의 `WEB_SDK_KEY`와 일치하는지 확인합니다.
9. SDK가 한 번만 로드되도록 하십시오. SDK가 여러 번 로드되면 SDK 기능이 중지될 수 있습니다.

## 3. 설정 및 이벤트 기록

Web SDK를 초기화한 후 기본 방문을 측정하여 특정 사용자 작업을 캡처할 수 있습니다. 이 섹션은 **네이티브 JavaScript** 또는 **Google Tag Manager**을 사용하여 구매 또는 등록과 같은 사용자 지정 이벤트를 정의하고 기록하는 방법을 안내합니다.

<div id="set-events" />

<Accordion title="이벤트 설정">

이벤트는 웹 측정의 기본적인 구성 요소이며, 비즈니스에 가치를 부여하는 특정 사용자 작업을 나타냅니다. 이러한 상호 작용을 기록하려면 각 이벤트에 대한 논리와 매개 변수를 정의해야 하며, 수익 및 사용자 지정 메타데이터와 같은 올바른 이벤트 매개 변수를 AppsFlyer 플랫폼으로 전달해야 합니다.

**예제 이벤트(사용 이벤트와 관련된 수익)**

```javascript
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name"}});
```

<div id="web-sdk-event-parameters-table" />

<Accordion title="Web SDK 이벤트 파라미터 테이블">

| 파라미터 이름 | 필수 | 설명 |
| --- | --- | --- |
| `eventType` | 예 | 이벤트 유형 형식: 문자열입니다. 이 파라미터를 항상 EVENT로 채우십시오. 예시: `eventType: "EVENT"` |
| `eventName` | 예 | 이벤트 이름 형식: 문자열입니다. 예시: 구매, 구독 |
| `eventRevenue` | 아니요 | 전환 이벤트에 할당된 수익 형식: Float |
| `eventRevenueCurrency` | 아니요 | 수익 통화 3자리 ISO 4217 통화 코드 기본값: USD. 형식: 문자열 |
| `eventValue` | 아니요 | 이벤트를 설명하는 이벤트 파라미터 맵. 제품 SKU, 개별 항목 가격과 같은 리치 인앱 이벤트 전송에 이 파라미터를 사용하세요. 형식: JSON 예시: 제한 사항: 1000자입니다. 이 값을 초과하지 마세요. 초과하는 경우 내용이 잘릴 수 있습니다. |

</Accordion>

</Accordion>

<div id="record-events-on-page-load" />

<Accordion title="페이지 로드에서 이벤트를 기록">

이것은 **감사** 또는 확인 페이지와 같은 리디렉션으로 끝나는 변환에 대한 표준 접근 방식입니다.

이 트리거를 **네이티브 JavaScript**에 창 로드 방법을 추가하거나 **Google 태그 관리자**에서 페이지 보기 트리거를 구성하여 구현할 수 있습니다.

> ❗️ **경고**
>
> 다음 코드 예제는 설명적 목적으로 제공됩니다. **이 코드를 사용하지 마십시오**; 당신의 사이트의 특정 구조에 적응.

<div id="example-record-event-via-af-web-sdk" />

<Accordion title="예시: AF 웹 SDK를 통해 이벤트를 기록">

이 접근 방식은 뉴스 레터 구독에 대한 감사 페이지와 같은 리디렉션을 통해 발생하는 변환을 기록하는 데 이상적입니다.

사용 사례 사용자는 뉴스 레터 등록을 완료하고 확인 페이지로 리디렉션됩니다. 해당 페이지가 표시되면 즉시 구독 이벤트를 기록하려면.

**네이티브 페이지 로드 예:**

```javascript
window.onload = function(){
  AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion'}, eventName: 'subscription'});
}
```

작동 원리

1. 페이지는 필요한 콘텐츠를 로드합니다.
2. 창이 완전히 로드되면 (`window.onload`) 스크립트가 자동으로 `AF()` 방법을 호출합니다.
3. **계약** 이벤트와 관련된 메타데이터( 카테고리 및 레이블)는 AppsFlyer에 직접 전송됩니다.

</Accordion>

<div id="example-record-event-via-gtm" />

<Accordion title="예시: GTM를 통해 이벤트 기록">

이 접근법은 "감사합니다" 페이지가 로드될 때 태그를 촬영하여 뉴스레터 구독과 같은 성공적인 변환을 기록하는 데 사용됩니다.

#### 1. 감사 페이지 설정

다음 HTML 구조는 GTM를 로드하여 Web SDK를 로드합니다. 또한 기능이나 `localStorage`을 통해 GTM에 데이터를 제공하는 방법도 보여줍니다.

```html
<html>
<head>
    <script>
        // Google Tag Manager loads the Web SDK
        (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
        })(window,document,'script','dataLayer','GTM-XXXX');
    </script>
    <script>
        function getResponseFromServer() {
            return JSON.stringify({ action: 'subscribe', category: 'site actions', label: userEmail })
        }
        localStorage.setItem('data', JSON.stringify({ action: 'subscribe', category: 'site actions', label: 'user@email.com' }));
    </script>
</head>
<body>
    <h1>Thank You for Subscribing to Our Newsletter</h1>
</body>
</html>
```

#### 2. GTM 태그 구성

1. GTM에서 새 태그를 생성하고 **Custom HTML** 태그 유형을 선택합니다.
2. 별도의 이름(예: "AF 구독 이벤트")을 제공합니다.
3. 다음 스크립트를 HTML 텍스트 영역에 붙여넣습니다.

   ```javascript
   AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'});
   ```
4. **Advanced Settings** > **Tag Sequencing**을 확장합니다. 기본 Web SDK 초기화 태그 후에 촬영하도록 구성되어 있는지 확인합니다.
5. "Thank You" 페이지의 **페이지 보기**에서 이 태그를 켜는 트리거를 설정합니다.

</Accordion>

</Accordion>

<div id="record-events-on-user-interaction" />

<Accordion title="사용자 상호 작용에 대한 이벤트 기록">

이 기능을 사용하여 페이지 재로드 없이 작업을 추적하십시오(버튼 클릭, 다운로드, 카트 추가).

이러한 상호 작용은 일반적으로 클릭 청취기를 **네이티브 HTML 요소**에 연결하거나 **Google 태그 관리자** 변수를 사용하여 특정 요소 ID 또는 CSS 선택자를 식별하고 측정하여 처리됩니다.

> ❗️ **경고**
>
> 다음 코드 예제는 설명적 목적으로 제공됩니다. **이 코드를 사용하지 마십시오**; 당신의 사이트의 특정 구조에 적응.

<div id="example-record-event-via-af-web-sdk-interaction" />

<Accordion title="예시: AF 웹 SDK를 통해 이벤트를 기록">

이 방법을 사용하여 사용자가 페이지에서 수행하는 특정 작업을 추적하십시오. 예를 들어 **결정** 또는 **다운로드** 버튼을 클릭하십시오.

사용 사례 당신은 전자 상거래 사이트를 운영하고 사용자가 자신의 쇼핑 카트에서 **체크 아웃** 버튼을 클릭 한 순간에 **체크 아웃** 이벤트를 캡처하고 싶습니다.

**네이티브 사용자 상호 작용 예:**

```html
<html>
<head>
    <script>
        window.onload = function () {
            document.getElementById('checkout').addEventListener('click', function () {
                AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
            });
        }
    </script>
</head>
<body>
    <h1>Shopping Cart</h1>
    <button id='checkout'>Checkout</button>
</body>
</html>
```

작동 원리

1. 페이지가 로드되면 스크립트는 ID `checkout`가 있는 요소에 **클릭** 이벤트 청취기를 연결합니다.
2. 사용자가 버튼을 클릭하면 콜백 함수는 다음을 수행합니다.
3. 이 함수는 관련 데이터(예를 들어, `localStorage`에서)를 가져와 `AF()` 방법으로 전달할 수 있습니다.
4. 그런 다음 SDK는 **체크아웃** 이벤트를 AppsFlyer 플랫폼으로 전송합니다.

</Accordion>

<div id="example-record-event-via-gtm-interaction" />

<Accordion title="예시: GTM를 통해 이벤트 기록">

이 방법은 GTM의 내장 변수와 트리거를 사용하여 특정 작업을 캡처합니다. 예를 들어 **결정** 버튼을 클릭하는 것과 같은 작업을 캡처합니다.

#### 1. 결제 페이지 설정

```html
<html>
<head>
    <script>
        (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
        })(window,document,'script','dataLayer','GTM-XXXX');
    </script>
</head>
<body>
    <h1>Shopping Cart</h1>
    <button id='checkout'>Checkout</button>
</body>
</html>
```

#### 2. GTM 변수 및 트리거 구성

1. GTM에서 **Variables** > **Configure를** 클릭하고 Built-In Variables 목록에서 **Click Element를** 활성화합니다.
2. 새로운 사용자 정의 변수를 만듭니다(Type: **모든 요소**).
3. 새 **트리거** 만들기:
   * 트리거 유형: **클릭 - 모든 요소**.
   * 이 트리거는 화재 : **어떤 클릭**.
   * 조건 **Element를 클릭하면** CSS Selector `#checkout`가 일치합니다.

#### 3. Interaction 태그 만들기

1. 결제 작업을 위해 새 **Custom HTML** 태그를 생성합니다.
2. 인터랙션 스크립트를 붙여넣으십시오:

   ```html
   <script>
     AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
   </script>
   ```
3. 이전 단계에서 만든 "Checkout Click" 트리거를 할당합니다.

</Accordion>

</Accordion>

<div id="event-implementation-best-practices" />

<Accordion title="이벤트 구현의 Best Practice">

데이터 정확성과 성공적인 전송을 보장하려면 다음 기술 요구 사항을 고려하십시오.

* **로드 순서:** 이벤트 호출을 수행하기 전에 Web SDK 기능 태그가 페이지 범위에 완전히 로드되어 있는지 확인합니다.
* **데이터 포맷:** 이벤트 값에 특별 문자를 포함하지 마십시오. 예를 들어, 통화 상징을 포함하는 대신 수익에 대한 숫자 값을 사용하십시오(`$10.50` 대신 `10.50` 사용).
* **체어 제한:** `event_value` 문자열을 간결하게 유지하십시오. 4000자 이상의 값은 단축됩니다.

</Accordion>

## 4. 고객 사용자 ID 설정하기

이벤트 측정을 구현한 후, `setCustomerUserId`를 사용하여 다른 플랫폼(모바일, PC, CTV)과 웹 활동을 연결하는 지속적인 ID를 설정하여 플랫폼 간의 사용자 여행에 대한 통합된 뷰를 얻습니다.

**주요 규칙**

* **일관성:** 모바일 앱 구현과 동일한 CUID 값을 사용하세요(<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk">iOS</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-android-sdk#setting-the-customer-user-id">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id">Unity</Anchor>의 모바일 `setCustomerUserId` 참조).
* **타이밍:** 당신은 어떤 단계에서 CUID를 보낼 수 있습니다 (예를 들어, 로그인 또는 등록 후). CUID를 가능한 한 빨리 설정하면, 당신이 그것에 액세스 할 수 있습니다. 다시 말하면 대부분의 경우 로그인 또는 가입을 통해 사용자가 식별될 때까지 기다려야 합니다.
* **구문:** 값을 문자열로 전송합니다(문자 표시에 포함되어 있습니다). 예시
* 프라이버시 이메일 주소 또는 전화 번호와 같은 개인 식별 정보를 포함하지 마십시오.

<div id="example-setting-cuid-after-signup-native" />

<Accordion title="예시: 등록 후 CUID 설정 (네이티브)">

이 예제에 제공된 코드는 단지 참조용입니다. 이 코드를 그대로 사용하지는 마십시오. 이 코드의 사용 방법을 잘 모르는 경우 웹 개발자에게 문의하십시오.

가정: 이벤트가 전송되기 전에 웹 SDK가 페이지에 로드됩니다. 다시 로드하지 마십시오.

사용자 시나리오:

* 사용자가 귀사 웹사이트에 가입합니다.
* 웹사이트 코드는 사용자 세부 정보를 수집하여 귀사 서버로 전송합니다.
* 서버는 사용자에 대해 고유한 CUID를 생성합니다.
* 가입 후 감사 페이지에서 서버에 대해 새 CUID를 쿼리합니다.
* 서버 응답을 사용하여 웹 SDK `setCustomerUserId()` 메서드를 사용하여 AppsFlyer CUID를 설정합니다.

#### A sign-up form 예

아래 코드는 간단한 가입 양식입니다. 양식이 제출되면 이메일 주소가 localStorage에 저장됩니다. 사용자가 감사 페이지를 열면 사용자 이메일 주소가 서버로 전송되어 해당 이메일에 대한 고유 CUID를 얻게 됩니다.

```html
<html>
<head>
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        function storeUserEmail() {
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Sign Up</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Name</label><input type="text" name="name" id="name"></div>
        <br/>
        <div><label>Email</label><input type="email" name="email" id="email"></div>
        <br/>
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

#### 감사 페이지 예

이 코드는 Fetch API를 사용합니다. 그것은 사용자가 입력 한 이메일 주소를 서버로 전송합니다. 서버가 등록 시 고유 CUID가 있는 사용자를 생성한다고 가정하면 서버에 이메일 주소를 보내면 고유 CUID가 반환됩니다. 서버는 고유한 CUID로 응답하며, 이 고유한 CUID는 `setCustomerUserId` 방법으로 전달되는 값입니다.

```html
<html>
<head>
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        window.onload = function () {
            var userEmail = localStorage.getItem('user_email');
            fetch('users/' + userEmail).then(function (res) {
                res.text().then(function (id) {
                    console.log(id);
                    AF('pba', 'setCustomerUserId', id);
                });
            });
        }
    </script>
</head>
<body>
    <h1>Thank You for Signing Up!</h1>
</body>
</html>
```

</Accordion>

<div id="example-setting-cuid-after-signup-google-tag-manager" />

<Accordion title="예시: 등록 후 CUID 설정 (Google 태그 관리자)">

1. 가입 페이지 설정:

   아래의 코드 예는 간단한 등록 양식입니다. 양식이 제출되면 이메일 주소가 localStorage에 저장됩니다. 사용자가 감사 페이지를 열면 사용자 이메일 주소가 서버로 전송되어 해당 이메일에 대한 고유 CUID를 얻게 됩니다.

   ```html
   <html>
   <head>
       <script>
           (function (w, d, s, l, i) {
               w[l] = w[l] || []; w[l].push({ 'gtm.start': new Date().getTime(), event: 'gtm.js' });
               var f = d.getElementsByTagName(s)[0], j = d.createElement(s),
                   dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true;
               j.src = 'https://www.googletagmanager.com/gtm.js?id=' + i + dl;
               f.parentNode.insertBefore(j, f);
           })(window, document, 'script', 'dataLayer', 'GTM-5VJ6C7R');
           function storeUserEmail() {
               var userEmail = document.getElementById('email').value;
               localStorage.setItem('user_email', userEmail);
           }
       </script>
   </head>
   <body>
       <h1>Sign Up</h1>
       <form onsubmit="storeUserEmail()" action="/signup" method="post">
           <div><label>Name</label><input type="text" name="name" id="name"></div>
           <br />
           <div><label>Email</label><input type="email" name="email" id="email"></div>
           <br />
           <input type="submit" id="submit">
       </form>
   </body>
   </html>
   ```
2. 가입한 사용자를 위한 감사 페이지 설정: 선행 코드는 가입 양식에서 사용자가 제공한 이메일 주소를 서버로 보내는 GTM 트리거가 있는 감사 페이지입니다. 서버가 등록 시 고유한 CUID를 가진 사용자를 생성한다고 가정하면 서버에 이메일을 보내면 고유한 CUID를 반환합니다. 서버는 `setCustomerUserId()` 메서드를 사용하여 전송된 고유한 CUID로 응답합니다.

   ```html
   <script>
       window.onload = function () {
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
               res.text().then(function (id) {
                   console.log(id);
                   AF('pba', 'setCustomerUserId', id);
               });
           });
       }
   </script>
   ```
3. 감사 페이지가 로드된 후 구독을 어트리뷰트하기 위한 새 태그 추가

   [![](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
4. 태그에 고유한 이름을 지정하고 '커스텀 HTML' 태그 유형 옵션을 선택합니다.

   [![](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)

   ```html
   <script>
       var userEmail = localStorage.getItem('user_email');
       fetch('users/' + userEmail).then(function (res) {
           res.text().then(function (id) {
               console.log(id);
               AF('pba', 'setCustomerUserId', id);
           });
       });
   </script>
   ```
5. **고급 설정**을 확장한 다음 텍스트 영역 아래의 **태그 시퀀싱 컨트롤**을 확장하고 태그가 실행된 후 변환을 실행하도록 설정되어 있는지 확인합니다.

   [![](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. 전환 태그가 실행되어야 하는 시점을 나타내도록 전환 태그에 대한 트리거를 설정합니다(아래 예에서는 '감사' 페이지 로드 시 실행됨).

   [![](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

</Accordion>

## 5. 개인 정보 관리

이벤트 측정을 구현한 후에는 조직 또는 지역 표준을 준수하기 위해 특정 보안 및 개인 정보 보호 제약을 적용해야 할 수도 있습니다.

<div id="opt-in-or-opt-out-of-sending-events" />

<Accordion title="이벤트 보내기를 선택하거나 선택하지 않음">

측정을 두 가지 방법으로 제어할 수 있습니다.

#### SDK 초기 상태 설정 ( snippet)

SDK가 웹 페이지가 처음 로드되었을 때 이벤트를 전송하거나 이벤트 전송을 시작하도록 명시적으로 알려줄 때까지 기다리는지 여부를 결정합니다. 이 설정은 웹 스냅트에서 정의됩니다.

* 이벤트 보내기
* 이벤트를 보내지 마십시오: `{pba: {webAppId: "...", measurementStatus:false}}`

> 📘 **참고**
>
> `measurementStatus`가 비어 있거나 `NULL`인 경우 AppsFlyer는 `measurementStatus:true`로 간주합니다.

#### 명시적 제어

명시적인 제어는 초기 상태 설정보다 우선 순위를 차지하며 지속적인 첫 번째 당사자 쿠키를 사용합니다.

* 웹사이트 도메인에서 설정합니다.
* Web SDK 또는 브라우저에서 설정한 기간이 지나면 만료됩니다.
* 항상 브라우저 쿠키 설정에 적용됩니다.

**명령**

* 이벤트 전송 시작(옵트인)
* 이벤트 전송 중지(옵트아웃)

</Accordion>

<div id="secure-and-filter-data" />

<Accordion title="보안 및 필터 데이터">

웹 사이트에 엄격한 보안 또는 데이터 보호 프로토콜이 필요하다면 Web SDK가 환경과 데이터와 상호 작용하는 방법을 구성하려면 다음 메커니즘을 사용하십시오.

#### 콘텐츠 보안 정책(CSP)

웹사이트가 CSP에서 JavaScript를 보호해야 하는 경우, Web SDK는 CSP 구성과 2단계에서 선택한 스냅트에 따라 두 가지 접근 방식을 지원합니다.

* **자체** 사용 CSP `https://websdk.appsflyersdk.com`를 `script-src` 허용 목록에 추가합니다. 이것은 표준 웹 SDK 및 고급 SDK 검증 모두에서 작동합니다.
* **nonce를 사용하는 CSP**: 정책에 `script-src 'nonce-...'`가 사용되는 경우 아래의 Advanced SDK Verification의 nonce 확장 버전을 사용합니다. 이것은 검증 프로세스에 필요한 모든 세 개의 스크립트 태그에 nonce를 전달합니다. `{{CSP_NONCE}}`를 서버에서 생성한 요청별 nonce 값으로 대체합니다.

아래 표에서는 어떤 CSP 정책이 nonce 확장 변형과 호환되는지 보여줍니다.

| 정책 | 작품 | 참고 |
| --- | --- | --- |
| `script-src 'self'` | 아니요 | 외부 CDN 출처는 허용되지 않습니다; 인라인 스크립트도 차단됩니다. |
| `script-src 'self' https://websdk.appsflyersdk.com` | 부분적 | 로더 및 SDK를 허용하지만 인라인 설정 스크립트는 여전히 차단됩니다. |
| `script-src 'nonce-...' https://websdk.appsflyersdk.com` | 예 | Nonce는 인라인 스크립트와 로더를 커버합니다. SDK 태그는 로더에서 nonce를 전달합니다. |
| `script-src 'nonce-...' 'strict-dynamic'` | 예 ( 추천) | Nonce는 인라인 스크립트와 로더를 담고 있습니다. `strict-dynamic`는 동적으로 삽입된 SDK 태그에 대한 신뢰를 전파합니다. 허용 목록에 CDN 원본이 필요하지 않습니다. |

CSP 정책 호환성

#### CSP nonce 스냅킷을 사용한 고급 SDK 검증

<div id="nonce-without-smart-banners" />

<Accordion title="스마트 배너 없음">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config — nonce forwarded to the injected SDK <script> tag
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<div id="nonce-with-smart-banners" />

<Accordion title="스마트 배너">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config — nonce forwarded to the injected SDK <script> tag
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

#### 쿼리 파라미터 삭제

URL 쿼리 매개 변수에 민감한 정보가 포함되어 있는 경우 AppsFlyer에 해당 정보(URL, 참조자 및 `header_referer`)를 폐기하도록 지시합니다.

* **모든** 쿼리 매개 변수를 제거합니다. add `af_url=true`
* **특정** 매개 변수를 버리십시오: `af_url_mask=param`(`;`로 여러 개의 매개 변수를 분리)

예시:

* 원본
* 결과:

</Accordion>

## 웹 SDK 쿠키 참조

Web SDK는 다음 쿠키를 설정하거나 사용합니다.

| 쿠키 이름 | 도메인 | 수명 | 사용하는 경우 | 세부 정보 |
| --- | --- | --- | --- | --- |
| afUserid | 웹사이트 도메인 | 395일 | AMP: 액셀러레이티드 모바일 페이지 | 웹 페이지 로드 및 탐색 이벤트 맥락에서 사용자를 식별합니다. |
| AF\_SYNC | 웹사이트 도메인 | 1주 | AMP: 액셀러레이티드 모바일 페이지 | 최종 사용자 식별자가 설정되었음을 나타내는 플래그. 사이트 로드 시간을 줄이는 데 사용됩니다. |
| af\_id | <Anchor target="_blank" href="http://appsflyer.com/">appsflyer.com</Anchor> | 395일 | 제3자 쿠키가 허용되는 비 가속 모바일 페이지 | 앱 실행 및 탐색 이벤트 맥락에서 사용자 식별 |
| af\_id | <Anchor target="_blank" href="http://onelink.me/">onelink.me</Anchor> | 395일 | 제3자 쿠키가 허용되는 비 가속 모바일 페이지 | 배너 인게이지먼트, 원링크 인게이지먼트 또는 둘 다를 앱 실행 이벤트에 연결합니다. |
| amp-afUserid | AMP CDN 또는 웹사이트 도메인 | 1년 | AMP: 액셀러레이티드 모바일 페이지 |  |
| AF\_DEFAULT\_MEASUREMENT\_STATUS | 웹사이트 도메인 | 395일 | AMP: 액셀러레이티드 모바일 페이지 | 동의 상태를 저장합니다. 사용자가 동의를 부여할 때까지 SDK가 작동하지 못하게 합니다. 기본적으로 설정되지 않습니다. <Anchor target="_blank" href="/marketers/ko/docs/pba-web-sdk-integration-guide#sending-events-optinoptout">인권 게이트</Anchor>이 구성된 경우에만 사용됩니다. |

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01KGJCGCPZDJ446QHW80H9Z4C3=%EA%B0%9C%EC%9A%94 step-1-obtain-your-keys=1-%ED%82%A4-%EC%96%BB%EA%B8%B0 h_01KP11XJV8B56W7FK2KAAFH0NE=1-%ED%82%A4-%EC%96%BB%EA%B8%B0 step-2-select-a-code-snippet=2-%EC%BD%94%EB%93%9C-%EC%8A%A4%EB%8B%88%ED%8E%AB-%EC%84%A0%ED%83%9D h_01KP11XJV8RDV378GMFF0DVZ8V=2-%EC%BD%94%EB%93%9C-%EC%8A%A4%EB%8B%88%ED%8E%AB-%EC%84%A0%ED%83%9D h_01KP3CJBZWJF8X46W2BBCS9ZVX=%EC%A4%91%EC%9A%94 standard=%ED%91%9C%EC%A4%80-%EC%9B%B9-sdk h_01KP11XJV8MN64YV17D1M0T5B9=%ED%91%9C%EC%A4%80-%EC%9B%B9-sdk h_01KP3CJBZWK17M58W9M2EP8VC3=standard-without-smart-banners h_01KP3CJBZWKW1K9P9V1XGYM5ED=standard-with-smart-banners advanced-sdk-verification=%EA%B3%A0%EA%B8%89-sdk-%EA%B2%80%EC%A6%9D h_01KP11XJV8ZGF4SDXJH6FKX18E=%EA%B3%A0%EA%B8%89-sdk-%EA%B2%80%EC%A6%9D h_01KP3CJBZWP7HDJ0GE2DF3TTE3=advanced-verification-without-smart-banners h_01KP3CJBZWJWS9H0XVHQFF758B=advanced-verification-with-smart-banners step-3-deploy-the-snippet=3-deploy-the-%EC%8A%A4%EB%83%85%ED%8A%B8 h_01KP11XJV8JQ5S2BBS18RV2H2R=3-deploy-the-%EC%8A%A4%EB%83%85%ED%8A%B8 h_01KP3CJBZWSKRZBRB66419E3TR=option-a-add-directly-to-your-website h_01KP3CJBZW1PE1VNCV6MSNWT8Q=option-b-deploy-via-google-tag-manager h_01KP3CJBZWWNXX6N5DBJKKGN6M=%EC%B0%B8%EA%B3%A0 h_01KP3CJBZWF4SW63KA6XCQ3BBD=option-c-deploy-via-adobe-launch-tag-manager create-a-property-in-adobe-experience-cloud=adobe-experience-cloud%EC%97%90-%EC%86%8D%EC%84%B1-%EC%83%9D%EC%84%B1 h_01KP11XJV9RWY4TTWACW69YGJH=adobe-experience-cloud%EC%97%90-%EC%86%8D%EC%84%B1-%EC%83%9D%EC%84%B1 add-the-snippet-to-the-adobe-launch-property=adobe-launch-%EC%86%8D%EC%84%B1%EC%97%90-%EC%8A%A4%EB%83%85%ED%8A%B8-%EC%B6%94%EA%B0%80 h_01KP11XJV9ZHMP9M85S3KG0V6R=adobe-launch-%EC%86%8D%EC%84%B1%EC%97%90-%EC%8A%A4%EB%83%85%ED%8A%B8-%EC%B6%94%EA%B0%80 add-the-adobe-launch-tag-to-the-website=adobe-launch-%ED%83%9C%EA%B7%B8%EB%A5%BC-%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8%EC%97%90-%EC%B6%94%EA%B0%80 h_01KP11XJVBV5J9E0HV5DM9HS7B=adobe-launch-%ED%83%9C%EA%B7%B8%EB%A5%BC-%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8%EC%97%90-%EC%B6%94%EA%B0%80 publish-the-adobe-launch-environment=adobe-launch-%ED%99%98%EA%B2%BD-%EA%B2%8C%EC%8B%9C h_01KP11XJVB0Y4RCBS9QCFBAKRD=adobe-launch-%ED%99%98%EA%B2%BD-%EA%B2%8C%EC%8B%9C 2-make-sure-the-sdk-is-working=2-sdk%EA%B0%80-%EC%9E%91%EB%8F%99%ED%95%98%EB%8A%94%EC%A7%80-%ED%99%95%EC%9D%B8%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 h_01KGJCGCPZ38XZAY8SXB48YWBD=2-sdk%EA%B0%80-%EC%9E%91%EB%8F%99%ED%95%98%EB%8A%94%EC%A7%80-%ED%99%95%EC%9D%B8%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 3-set-and-record-events=3-%EC%84%A4%EC%A0%95-%EB%B0%8F-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EA%B8%B0%EB%A1%9D h_01KGJCGCPZMPX1FH58MVGM9VQS=3-%EC%84%A4%EC%A0%95-%EB%B0%8F-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EA%B8%B0%EB%A1%9D h_01KP3CJBZXQRMCG9CCH7N1RQ7Y=set-events h_01KP3CJBZXV66CCP4N0482DG1N=web-sdk-event-parameters-table h_01KP3CJBZXEA5SN763P1ZX8EH3=record-events-on-page-load h_01KP3CJBZXHTGFHR9D4KM6S6GH=%EA%B2%BD%EA%B3%A0 h_01KP3CJBZXB328CABH2QCRXTHX=example-record-event-via-af-web-sdk h_01KP3CJBZXM3WK0JYB6S8P6SMQ=example-record-event-via-gtm 1-set-up-a-thank-you-page=1-%EA%B0%90%EC%82%AC-%ED%8E%98%EC%9D%B4%EC%A7%80-%EC%84%A4%EC%A0%95 h_01KGJCGCPZQDP9KVBSE1Z1GT48=1-%EA%B0%90%EC%82%AC-%ED%8E%98%EC%9D%B4%EC%A7%80-%EC%84%A4%EC%A0%95 2-configure-the-gtm-tag=2-gtm-%ED%83%9C%EA%B7%B8-%EA%B5%AC%EC%84%B1 h_01KGJCGCPZ2YVRY6VYJ0BTC14N=2-gtm-%ED%83%9C%EA%B7%B8-%EA%B5%AC%EC%84%B1 h_01KP3CJBZXZ2F32FJG9GENBPWW=record-events-on-user-interaction h_01KP3CJBZX6763D546AK5AS1TN=%EA%B2%BD%EA%B3%A0-1 h_01KP3CJBZXD6MPTQ0KCPMTM1Y9=example-record-event-via-af-web-sdk-interaction h_01KP3CJBZX53G1HABG3TKN2X6S=example-record-event-via-gtm-interaction 1-set-up-a-checkout-page=1-%EA%B2%B0%EC%A0%9C-%ED%8E%98%EC%9D%B4%EC%A7%80-%EC%84%A4%EC%A0%95 h_01KGJCGCQ0858AAJC82Y2G0GNP=1-%EA%B2%B0%EC%A0%9C-%ED%8E%98%EC%9D%B4%EC%A7%80-%EC%84%A4%EC%A0%95 2-configure-gtm-variables-and-triggers=2-gtm-%EB%B3%80%EC%88%98-%EB%B0%8F-%ED%8A%B8%EB%A6%AC%EA%B1%B0-%EA%B5%AC%EC%84%B1 h_01KGJCGCQ0GGYDQBP9CJNM9AXQ=2-gtm-%EB%B3%80%EC%88%98-%EB%B0%8F-%ED%8A%B8%EB%A6%AC%EA%B1%B0-%EA%B5%AC%EC%84%B1 3-create-the-interaction-tag=3-interaction-%ED%83%9C%EA%B7%B8-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01KGJCGCQ0EV557QF3CGZ6YB4X=3-interaction-%ED%83%9C%EA%B7%B8-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01KP3CJBZX5K72JC1NK1P1S1S8=event-implementation-best-practices 4-set-customer-user-id=4-%EA%B3%A0%EA%B0%9D-%EC%82%AC%EC%9A%A9%EC%9E%90-id-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01KGJCGCQ0RNBW7V5T4PXVXQW1=4-%EA%B3%A0%EA%B0%9D-%EC%82%AC%EC%9A%A9%EC%9E%90-id-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01KP3CJBZXXKM662TJP0M5BJAR=example-setting-cuid-after-signup-native a-sign-up-form-example=a-sign-up-form-%EC%98%88 h_01KGJCGCQ0M0ESXFMK45PJ3SX9=a-sign-up-form-%EC%98%88 a-thank-you-page-example=%EA%B0%90%EC%82%AC-%ED%8E%98%EC%9D%B4%EC%A7%80-%EC%98%88 h_01KGJCGCQ0FMKFKM2SWV2794T5=%EA%B0%90%EC%82%AC-%ED%8E%98%EC%9D%B4%EC%A7%80-%EC%98%88 h_01KP3CJBZX4BXQSGN70TRJDNX1=example-setting-cuid-after-signup-google-tag-manager 5-manage-privacy=5-%EA%B0%9C%EC%9D%B8-%EC%A0%95%EB%B3%B4-%EA%B4%80%EB%A6%AC h_01KGJCGCQ01PQWT44ZWE329DWX=5-%EA%B0%9C%EC%9D%B8-%EC%A0%95%EB%B3%B4-%EA%B4%80%EB%A6%AC h_01KP3CJBZXVR16943T16XT82G5=opt-in-or-opt-out-of-sending-events sdk-initial-state-setting-in-the-snippet=sdk-%EC%B4%88%EA%B8%B0-%EC%83%81%ED%83%9C-%EC%84%A4%EC%A0%95--snippet h_01KGJCGCQ0AQM3Y9NNCJF2XP9G=sdk-%EC%B4%88%EA%B8%B0-%EC%83%81%ED%83%9C-%EC%84%A4%EC%A0%95--snippet h_01KP3CJBZX8V6TGE5NVR6SW49G=%EC%B0%B8%EA%B3%A0-1 explicit-control=%EB%AA%85%EC%8B%9C%EC%A0%81-%EC%A0%9C%EC%96%B4 h_01KGJCGCQ07KKYGN5JZF41A6W7=%EB%AA%85%EC%8B%9C%EC%A0%81-%EC%A0%9C%EC%96%B4 h_01KP3CJBZXZBFCXD1E38JKWW6H=secure-and-filter-data content-security-policy-csp=%EC%BD%98%ED%85%90%EC%B8%A0-%EB%B3%B4%EC%95%88-%EC%A0%95%EC%B1%85csp h_01KGJCGCQ0QB7NK6YNZT5XJVJY=%EC%BD%98%ED%85%90%EC%B8%A0-%EB%B3%B4%EC%95%88-%EC%A0%95%EC%B1%85csp advanced-sdk-verification-with-csp-nonce-snippets=csp-nonce-%EC%8A%A4%EB%83%85%ED%82%B7%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%9C-%EA%B3%A0%EA%B8%89-sdk-%EA%B2%80%EC%A6%9D h_01KP11XJV88YB2NSBZJTX9K7ZQ=csp-nonce-%EC%8A%A4%EB%83%85%ED%82%B7%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%9C-%EA%B3%A0%EA%B8%89-sdk-%EA%B2%80%EC%A6%9D h_01KP3CJBZXQ4D538H0T7N9FZ6Z=nonce-without-smart-banners h_01KP3CJBZX8K3WK6RHQMB029VN=nonce-with-smart-banners discard-query-parameters=%EC%BF%BC%EB%A6%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EC%82%AD%EC%A0%9C h_01KGJCGCQ010K4RMFMGHD5NDC3=%EC%BF%BC%EB%A6%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EC%82%AD%EC%A0%9C web-sdk-cookies-reference=%EC%9B%B9-sdk-%EC%BF%A0%ED%82%A4-%EC%B0%B8%EC%A1%B0 h_01KGJCGCQ03A1H7NA5ZGPSGKP3=%EC%9B%B9-sdk-%EC%BF%A0%ED%82%A4-%EC%B0%B8%EC%A1%B0" />
