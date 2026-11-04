---
title: PBA 웹 SDK 연동 가이드
metadata:
  keywords:
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
  created_at: '2019-05-17T09:05:30Z'
  edited_at: '2026-10-14T10:32:17Z'
  id: 360001610038
  locale: ko
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ko/articles/360001610038
---
> **한눈에 보기:** 요약: 웹 SDK를 사용하여 앱스플라이어를 웹사이트에 연동하여 방문, 이벤트, 전환 및 수익을 기록하고 측정합니다.

[![5107_Infographic_Web_S2S_759x270_option1.jpg](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)

<div id="web-sdk-user-and-integration-guide" />

## Web SDK 사용자 가이드 및 연동 가이드

* 웹 SDK JavaScript 태그:
  * 여러 플랫폼에서 사용자 여정을 분석하기 위한 PBA(유저 중심 어트리뷰션) 솔루션의 일부입니다.
  * 귀사 웹사이트에 대한 사용자 방문 및 활동 내역을 앱스플라이어 플랫폼에 리포트합니다.
  * 웹사이트 플러그인 모듈 프로그래밍이 필요 없는. 웹사이트 방문자의 운영 체제와 브라우저에 구애받지 않습니다.
  * 사이즈 40-60Kb.
* 앱스플라이어 모바일 SDK와 함께 웹 SDK를 구현하여 모바일 앱 및 웹 환경 전반에서 사용자 활동을 기록하고 매핑하십시오.
* 웹사이트 밖에서 발생하는 이벤트는 <Anchor target="_blank" href="/marketers/ko/docs/web-server-to-server-events-api-for-pba-web-s2s">웹 서버 간 이벤트 API</Anchor> (Web S2S)를 사용하여 기록할 수 있습니다.

<div id="selecting-a-code-snippet" />

## 코드 스니펫 선택하기

귀하의 통합 유형 및 보안 요구 사항에 맞는 스니펫을 선택하십시오. 두 가지 옵션이 있습니다:

* [표준 웹 SDK](#표준-웹-sdk): 표준 통합입니다.
* [고급 SDK 검증](#고급-sdk-검증): 웹 SDK에 대한 공급망 보호를 추가하는 향상된 통합입니다. 이것을 사용하여 CDN 손상, DNS 하이재킹 및 중간자 공격에 대한 추가 보안 계층을 추가하십시오.

<div id="important" />

> 🚧 **중요!**
>
> 표준 웹 SDK에서 고급 SDK 검증으로 전환하는 경우 기존 스니펫을 새 스니펫으로 교체하십시오. 기존 스니펫 위에 새 스니펫을 추가하지 마십시오.

<div id="standard-web-sdk" />

### 표준 웹 SDK

이 스니펫을 사용하여 표준 웹 SDK 통합을 배포하십시오. SDK를 로드하려는 모든 페이지의  태그 상단 근처에 붙여넣으십시오.

<div id="standard-without-smart-banners" />

<Accordion title="스마트 배너 없이">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Inject SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
</script>
```

</Accordion>

<div id="standard-with-smart-banners" />

<Accordion title="스마트 배너와 함께">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Inject SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba,banners&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
  AF('banners', 'showBanner');
</script>
```

</Accordion>

<div id="advanced-sdk-verification" />

### 고급 SDK 검증

고급 SDK 검증은 웹 SDK에 대한 공급망 보호를 추가합니다. 사용자의 브라우저에서 실행되는 코드가 AppsFlyer가 게시한 코드와 정확히 일치하도록 보장합니다. SDK 소스 코드는 표준 통합과 동일하며, 배포 및 검증 메커니즘만 다릅니다.

고급 SDK 검증:

* CDN 손상, DNS 하이재킹 및 중간자 공격에 대한 추가 보안 계층을 추가합니다.
* SDK 로딩 시간에 약 250ms를 추가합니다.

고급 SDK 검증은 선택 사항입니다. 표준 통합은 완전히 지원되며, 서드파티 분석 픽셀의 시장 표준입니다. 고급 SDK 검증은 표준을 넘어서는 추가 보호 계층을 제공합니다.

웹사이트가 nonce를 사용하여 콘텐츠 보안 정책(CSP)을 시행하는 경우, 이 스니펫의 nonce 확장 변형에 대한 내용은 [콘텐츠 보안 정책(CSP)](#콘텐츠-보안-정책csp)의 개인 정보 관리 섹션을 참조하십시오.

<div id="advanced-verification-without-smart-banners" />

<Accordion title="스마트 배너 없이">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
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

<Accordion title="스마트 배너와 함께">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
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

<div id="integrating-the-web-sdk-into-the-website" />

## 웹 SDK를 웹사이트에 연동하기

<div id="installation-and-integration" />

<Accordion title="인스톨 및 연동">

<div id="considerations-and-actions-required" />

#### 고려사항 및 필수 조치

| 연동 검사목록 |
| --- |
| 방문 및 이벤트가 기록되도록 보장하려면 웹사이트의 모든 페이지에 Web SDK를 인스톨해야 합니다. |
| 페이지 범위에서 가능한 한 빨리 로드되도록 [위에서 선택한 스니펫 코드](#코드-스니펫-선택하기)를 배치하십시오. 헤드 태그의 맨 위 근처에 코드를 배치하면 됩니다. |
| Google Tag Manager(GTM)를 사용하여 SDK를 연동하는 경우:<ul><li>SDK가 페이지 로드당 한 번 로드되는지 확인합니다.</li><li><Anchor target="_blank" href="https://support.google.com/tagmanager/answer/2772421?hl=en">GTM 우선순위</Anchor>를 사용하여 페이지가 로드되자마자 SDK가 로드되도록 설정합니다.</li></ul> |
| 스마트 배너를 **사용하거나** **사용하지 않고** 웹 SDK를 구현할 수 있습니다. 다음 섹션의 관련 지침을 따르십시오. |
| 연동 필수 요구사항<ul><li>방문 기록</li><li>이벤트 기록</li><li>자세한 정보는 고객 사용자 ID 설정하기 안내를 참고하십시오. CUID가 없는 경우, 대안을 논의하기 위해 CSM에게 연락하십시오.</li></ul><Anchor target="_blank" href="/marketers/ko/docs/test-pba-web-sdk-integration">검사 도구</Anchor>를 사용한 연동 유효성 검증 |

**시작하기 전에**:

* 마케터가 <Anchor target="_blank" href="/marketers/ko/docs/pba-brand-bundles-and-settings">브랜드 번들</Anchor>을 생성했는지 확인하십시오.
* 추가 지침은 <Anchor target="_blank" href="/marketers/ko/docs/onboarding-guide-to-people-based-attribution">PBA 온보딩 안내서</Anchor>를 참조하십시오.
* 고려 사항: 고려 사항: 독립형 스마트 배너 웹 SDK가 이미 있는 경우 이를 삭제하고 스마트 배너 및 유저 중심 어트리뷰션 모두를 위한 웹 SDK로 교체하십시오. 단순히 PBA용 독립형 웹 SDK를 추가하지 마십시오.

**다음 작업을 수행하십시오.**

* 웹 SDK 웹 개발 키를 받으세요.  **참고!** 모바일 앱에서 사용하는 키와 동일하지 않습니다.
  * **웹 개발 키를 가져오는 방법:**
    1. 앱스플라이어의 상단 메뉴에서 **내 앱** 탭을 선택합니다.
    2. **View brand bundles(브랜드 번들 보기)** 를 클릭합니다.
    3. 필요한 웹 개발 키를 복사하세요. (WEB\_DEV\_KEY)
* 스마트 배너를 구현했다면 스마트 배너 키를 받으세요.
  * **스마트 배너 키를 가져오는 방법:**
    1. 앱스플라이어의 사이드 메뉴에서 **인게이지**> **웹 투 앱 >스마트 배너** 로 이동합니다.
    2. 필요한 **스마트 배너 키**를 복사합니다.
* 웹사이트의 헤드 태그에 스크립트를 추가할 수 있는 권한.
* Google Tag Manager를 사용하는 경우 이를 웹사이트에 연동해야 합니다.

**다음 옵션 중 하나를 사용하여 웹 SDK 연동을 진행하십시오.**

<Tabs>
<Tab title="네이티브">

<div id="javascript-code-snippet" />

#### JavaScript 코드 스니펫

다음 방법 중 하나를 사용하여 웹 SDK를 연동하십시오.

<div id="to-install-the-web-sdk-without-smart-banners" />

#### **스마트 배너 없이 웹 SDK를 인스톨하는 방법:**

1. 웹 사이트의 모든 페이지에서 다음 절차를 반복하십시오.
2. 다음 코드 조각에서 전제 조건에 지정된 키를 사용하여 `WEB_DEV_KEY`WEB\_DEV\_KEYWEB\_DEV\_KEY를 바꿉니다.
3. 선택한 코드 스니펫 [위에서](#코드-스니펫-선택하기)을(를) 웹사이트의 head 태그에 붙여넣으십시오. 헤드 태그의 맨 위 가까이에 붙여넣도록 하십시오.

<div id="to-implement-the-web-sdk-with-smart-banners" />

#### **스마트 배너로 웹 SDK를 구현하는 방법:**

1. 웹사이트의 모든 페이지에서 아래 절차를 반복하십시오.
2. 선택한 코드 스니펫 [위에서](#코드-스니펫-선택하기)에서 `WEB_DEV_KEY` 및 `YOUR_BANNER_KEY`을(를) 필수 조건에 지정된 키를 사용하여 교체하십시오.
3. 이 코드 스니펫을 웹사이트의 head 태그에 붙여넣으십시오. 헤드 태그의 맨 위 가까이에 붙여넣도록 하십시오.

</Tab>

<Tab title="Google Tag Manager">

**Google Tag Manager(GTM)로 웹 SDK를 구현하는 방법:**

1. <Anchor target="_blank" href="https://developers.google.com/tag-manager/quickstart">Google Tag Manager로 이동하십시오.</Anchor>
2. 앱스플라이어 웹 SDK에 대한 새 태그를 생성합니다.

   [![](https://files.readme.io/bd695bcbaf3983aac809cb7e1d63af0b89a08cea1751bbd8c2fc39863182fe7a-360002745245.png)](https://files.readme.io/bd695bcbaf3983aac809cb7e1d63af0b89a08cea1751bbd8c2fc39863182fe7a-360002745245.png)
3. **커스텀 HTML** 태그 유형을 선택합니다.
4. 태그에 의미 있는 이름을 지정하십시오.
5. 다음 중 하나를 선택하세요.
   * 스마트 배너 **없이** 웹 SDK를 연동하는 경우:
     1. 선택한 코드 스니펫 [위에서](#코드-스니펫-선택하기)을(를) **태그 구성** 창에 붙여넣으십시오.
     2. 코드 스니펫에서 전제 조건에 언급된 키를 사용하여 `WEB_DEV_KEY`WEB\_DEV\_KEYWEB\_DEV\_KEY를 바꾸십시오.
   * 스마트 배너**로** 웹 SDK를 연동하는 경우:
     1. 선택한 코드 스니펫 [위에서](#코드-스니펫-선택하기)을(를) **태그 구성** 창에 붙여넣으십시오.
     2. 코드 스니펫에서, `WEB_DEV_KEY` 및 `YOUR_BANNER_KEY`를 필수 조건에 언급된 키로 교체하십시오.
6. **저장**을 클릭하세요.
7. 다음 중 하나를 선택하세요.
   * **트리거를 모든 페이지에 추가하는 방법:**
     1. **Add Trigger(트리거 추가)** 를 클릭합니다.

        [![gtm-af-tag-sdk-trigger.png](https://files.readme.io/9cae70cdc376e57d3458fab80f8b9e57aa6981a3f3029c17d32e96b5f569fc28-360007722757.png)](https://files.readme.io/9cae70cdc376e57d3458fab80f8b9e57aa6981a3f3029c17d32e96b5f569fc28-360007722757.png)
     2. **모든 페이지(All Pages)** 를 선택합니다.
     3. **저장**을 클릭하세요.
     4. 태그 이름을 입력하고 **저장**을 클릭하십시오.  
        절차가 완료되었습니다.
   * **트리거를 특정 페이지에 추가하는 방법:**
     1. **Save Tag(태그 저장)** 를 클릭합니다.
     2. GTM 기본 창에서 **Triggers(트리거)** 를 선택합니다. New(신규)를 클릭합니다.
     3. 펜 아이콘을 클릭합니다.
     4. **Page View(페이지 보기)** 트리거 유형을 선택합니다.   
        [![PBAselectTrigger_us-en.jpg](https://files.readme.io/e62926fed956da9f3fcbf04f818858c69f07cbac892fafd839451c73d72a6741-360007811677.jpg)](https://files.readme.io/e62926fed956da9f3fcbf04f818858c69f07cbac892fafd839451c73d72a6741-360007811677.jpg)
     5. **Some Page View(일부 페이지 보기)** 를 선택합니다.
     6. 필요에 따라 페이지 및 트리거 조건을 설정하십시오.
     7. **저장**을 클릭하세요.
     8. 트리거를 앱스플라이어 웹 SDK 태그에 연결하십시오. 이렇게 하려면:
        1. GTM 기본 창에서 태그를 선택하십시오.합니다.
        2. 이전에 생성한 태그를 선택하십시오.
        3. 트리거 패널에서 펜을 클릭하십시오.
        4. 이전에 생성한 페이지 뷰 트리거를 선택하십시오.

           [![](https://files.readme.io/c4e9b2e4b4d3ce6b7377d419070be650e758eddcdf5603fa5f3c65560402f1d7-360002745305.png)](https://files.readme.io/c4e9b2e4b4d3ce6b7377d419070be650e758eddcdf5603fa5f3c65560402f1d7-360002745305.png)
        5. **저장**을 클릭하세요.

</Tab>

<Tab title="Adobe Launch Tag Manager">

1. [Adobe Experience Cloud에 속성 생성](/docs/pba-web-sdk-integration-guide#create-a-property-in-adobe-experience-cloud)
2. [Adobe Launch 속성에 웹 SDK 추가](/docs/pba-web-sdk-integration-guide#add-the-web-sdk-to-the-adobe-launch-property)
3. [Adobe Launch 태그를 웹사이트에 추가](/docs/pba-web-sdk-integration-guide#add-the-adobe-launch-tag-to-the-website)
4. [Adobe Launch 환경 게시](/docs/pba-web-sdk-integration-guide#publish-the-adobe-launch-environment)

<div id="create-a-property-in-adobe-experience-cloud" />

<Accordion title="Adobe Experience Cloud에 속성 생성">

![adobe_create_property.png](https://files.readme.io/1f97d619d5fdfe47b1dd1a2e17c0169e939c32bcda62580ba259d6e86f61d6c2-20260884824209.png)

1. **Adobe Experience Cloud** > Launch로 가십시오.
2. **Adobe Experience Cloud Launch** 아래 **Go to Launch**를 클릭합니다.
3. **New Property**를 클릭합니다.
4. 속성 이름을 지정합니다.
5. **플랫폼** 아래 **웹**을 선택합니다.
6. 귀하의 웹사이트 도메인을 입력합니다.
7. **저장**을 클릭하세요.

</Accordion>

<div id="add-the-web-sdk-to-the-adobe-launch-property" />

<Accordion title="Adobe Launch 속성에 웹 SDK 추가">

<Image alt="web_property_rules.png" src="https://files.readme.io/5f592f3ce1f5b319c8f6f96a6235618d884a4faccb1387b1f22c1fd2ce662d15-360006168098.png" width="491px" />

1. **My web property(나의 웹 속성)** 페이지에서 **Rules(규칙)** 탭을 선택합니다.
2. 규칙의 이름을 지정한다. **Load web SDK** 사용을 권장합니다.
3. **IF** 섹션에서 **이벤트** 아래 **+추가**를 클릭합니다.
   * **Event Type(이벤트 유형)** 에서 **코어 - DOM 준비**를 선택하십시오.
   * **변경 유지**를 클릭합니다.
4. **THEN** 섹션에서 **조치** 아래, **+추가**를 클릭합니다.
   * **조치 유형** > **사용자정의 코드**를 클릭하십시오.
   * **JavaScript** > **Open Editor**를 선택하고 **&lt;script> 태그 없이** 웹 SDK 스니펫을 붙여넣습니다.
   * **변경 유지**를 클릭하여 코드 편집기를 닫습니다.
5. **저장**을 클릭하세요.

</Accordion>

<div id="add-the-adobe-launch-tag-to-the-website" />

<Accordion title="Adobe Launch 태그를 웹사이트에 추가">

[![adobe_tag.png](https://files.readme.io/4da5418fc3f2591d15fe68ea1d0451f2b393cb177ae4309d5d431259e2d4003f-small-20260884828049.png)](https://files.readme.io/4da5418fc3f2591d15fe68ea1d0451f2b393cb177ae4309d5d431259e2d4003f-small-20260884828049.png)

1. **My web property** 페이지에서 **환경** 탭을 선택합니다.
2. 퍼블리시할 환경(개발 환경 혹은 실 운영 환경)이 있는 행을 찾으십시오.
   * **인스톨** 헤더 아래 관련있는 행 위의 박스 아이콘을 클릭합니다. 이는 보통 프로덕션 운영 환경입니다.
   * **Adobe Launch** 환경을 퍼블리시하는 방법에 대한 섹션을 참조하십시오.
3. **웹 설치 지침** 대화상자에서:
   * 스크립트 코드 스니펫을 복사합니다.
   * 대화 상자를 닫습니다.
4. 코드 조각을 귀하의 웹사이트 &lt;head> 태그에 붙여넣습니다.

</Accordion>

<div id="publish-the-adobe-launch-environment" />

<Accordion title="Adobe Launch 환경 게시">

[![adobe_publishing_env.png](https://files.readme.io/863b7c81a9f90d774f7f4388a22db3420dca5c5db632efc6c0dc40783702f418-small-20260884829329.png)](https://files.readme.io/863b7c81a9f90d774f7f4388a22db3420dca5c5db632efc6c0dc40783702f418-small-20260884829329.png)

1. **My web property** 페이지에서 **퍼블리싱** 탭을 선택합니다.
2. **Development** 섹션에서 **새 라이브러리 추가**를 클릭합니다.
   * 라이브러리를 명명하고 환경을 선택하세요.
   * **리소스 변경** 아래에서 **리소스 추가**를 클릭합니다.
   * **규칙** > **웹 SDK 로드** > **최신** > **새 버전 선택 및 만들기**를 클릭합니다.
   * **저장**을 클릭하세요.
3. **Development** 섹션 아래에서:
   * 새로 생성된 라이브러리 옆에 조치 메뉴(점 3개)를 클릭해서 > **Build for Development**를 선택합니다.
   * 다시 조치 메뉴를 클릭하고 > **승인을 위한 제출**을 선택합니다.
4. **제출됨** 섹션 아래에서:
   * 조치 메뉴를 클릭하고 > **Build for Staging**을 선택합니다.
   * 조치 메뉴를 클릭하고 > **퍼블리싱 승인**을 선택합니다.
5. **승인됨** 섹션에서 다음을 수행합니다.
   * 조치 메뉴를 클릭하고 > **프로덕션에 빌드 및 게시**를 선택합니다.
   * 이제 설정이 완료되었습니다.

</Accordion>

웹사이트가 모바일 기기에 로드되면 활성 광고 소재가 배너에 표시됩니다. 배너를 특정 페이지나 유저 액션에 따라서만 노출시키려면, <Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">Adobe Launch 규칙</Anchor>을 참조하십시오.

</Tab>
</Tabs>

</Accordion>

<div id="ensure-that-the-sdk-is-working" />

<Accordion title="SDK가 작동하는지 확인하십시오.">

일단 인스톨하면 방문자의 브라우저에서 앱스플라이어 웹 SDK를 호출하고 메시지가 전송되는지 확인하십시오. 브라우저에 리포트된 메시지 네트워크 연결을 검사하여 확인할 수 있습니다.

**SDK가 로드되고 작동하는지 확인하는 방법:**

1. 웹사이트로 이동하십시오.
2. 브라우저 개발 도구를 여십시오.

   ![WebSDK_us-en.jpg](https://files.readme.io/5550f0ee8c1a5852a983e6482cb0489696b669ffe5fade49d2308ee32f57201b-360009548497.jpg)
3. (A) **네트워크** 탭으로 이동합니다.
4. 페이지를 새로 고치십시오.
5. (B) **wa.** appsflyer로 필터링합니다.
6. (C) **이벤트** 메시지를 선택합니다.
7. 헤더 탭에서 (D) 다음을 확인합니다.
   * **요청 URL**은 wa.appsflyer.com/events입니다.
   * site\_id 쿼리 매개변수= `WEB_DEV_KEY`.
   * (E) **상태 코드는 200입니다**.
8. site\_id 값이 브랜드 번들 설정의 `WEB_DEV_KEY`WEB\_DEV\_KEY 값과 같은지 확인합니다.
   1. 앱스플라이어의 사이드 메뉴에서 **설정** > **브랜드 번들을 선택합니다.**
   2. **웹 개발 키**를 클릭하여 키를 복사합니다.
   3. 키를 표시할 위치(새 브라우저 탭, 노트패드)에 키를 붙여넣으십시오.
   4. site\_id와 `WEB_DEV_KEY`이 일치하는지 확인하십시오.
9. SDK가 한 번만 로드되도록 하십시오. SDK가 여러 번 로드되면 SDK 기능이 중지될 수 있습니다.

</Accordion>

<div id="sending-events-optinoptout" />

<Accordion title="이벤트 옵트인/옵트아웃 전송하기">

![5578-VistiorPrivacyOptIn_us-en.png](https://files.readme.io/cd6cbcaeb7f831f4efe74a9a6c6b20d5095602e7edf4dd38becd90864e73c2fb-360010263157.png)

웹 SDK는 방문자 이벤트 데이터를 앱스플라이어로 전송합니다. 이 섹션에 설명된 대로 이벤트 전송을 제어, 중지 또는 시작할 수 있습니다.

고려 사항:

* SDK 초기 상태 설정 SDK가 웹 페이지를 처음 로드할 때 이벤트를 전송하는지 또는 명시적인 명령을 주기 전까지 기다려야 하는지를 결정합니다. 설정은 웹 스니펫 내에 포함되어 있습니다.
* 명시적 제어 이벤트 전송을 중지하거나 시작하는 데 사용하십시오. 예를 들어, 데이터 옵트인/옵트아웃 배너(쿠키 동의 배너라고도 함)를 구현하는 경우, 배너 제어에 명시적인 명령을 통합하여 이벤트 전송을 시작하고 중지하십시오. 명시적 제어는 SDK 초기 상태 설정보다 우선하며, 다음 특성을 가진 지속적인 1차 쿠키를 사용합니다:
  * 웹사이트 도메인에서 설정합니다.
  * 웹 SDK에서 설정하거나 브라우저에서 결정한 기간이 지나면 만료됩니다. 쿠키가 만료되면 웹 SDK는 초기 상태 설정으로 되돌아갑니다.
  * 웹 SDK 쿠키는 브라우저별 쿠키 설정을 방해하지 않으며 항상 적용됩니다.

<div id="sdk-initial-state-setting" />

#### SDK 초기 상태 설정

| 설정 | 스니펫 필수 |
| --- | --- |
| [기본값] 이벤트 전송하기 | 웹 SDK 스니펫을 다음과 같이 변경하십시오. 필요한 경우, 다음과 같은 measurementStatus 파라미터를 추가하십시오.<br /><br />Set measurementStatus=true<br /><br />`{pba: {webAppId: "********-****-****-*****************", measurementStatus:true}` |
| 이벤트를 전송하지 않기 | 웹 SDK 스니펫을 다음과 같이 변경하십시오. 필요한 경우 다음과 같은 measurementStatus 파라미터를 추가하십시오.<br /><br />Set measurementStatus=false\{pba:   <br />  <br />`{pba: {webAppId: "********-****-****-*****************", measurementStatus:false}` |

<div id="explicit-control" />

#### 명시적 제어

| 옵션 | 명령 |
| --- | --- |
| 이벤트 전송 시작(옵트인) | `window.AF_SDK.PLUGINS.PBA.enableMeasurement()` |
| 이벤트 전송 중지(옵트아웃) | `window.AF_SDK.PLUGINS.PBA.disableMeasurement()` |

</Accordion>

<div id="implement-a-content-security-policy-csp-policy" />

<Accordion title="콘텐츠 보안 정책(CSP) 구현">

웹사이트가 엄격한 보안 또는 데이터 개인 정보 보호 프로토콜을 요구하는 경우, 웹 SDK가 귀하의 환경 및 데이터와 상호 작용하는 방식을 구성하기 위해 다음 메커니즘을 사용하십시오.

<div id="content-security-policy-csp" />

#### 콘텐츠 보안 정책(CSP)

웹사이트가 CSP에 의해 JavaScript가 보호되어야 하는 경우, 웹 SDK는 CSP 구성에 따라 두 가지 접근 방식을 지원합니다.

* **자체** 사용 CSP `https://websdk.appsflyersdk.com`를 `script-src` 허용 목록에 추가하십시오. 이것은 표준 웹 SDK와 고급 SDK 검증 모두에 적용됩니다.
* **nonce를 사용하는 CSP**: 정책에서 `script-src 'nonce-...'`를 사용하는 경우, [고급 SDK 검증의 nonce 확장 변형](#csp-nonce-스니펫을-사용한-고급-sdk-검증)을(를) 사용할 수 있습니다. 이것은 검증 프로세스에 필요한 세 개의 스크립트 태그에 nonce를 전달합니다. `{{CSP_NONCE}}`를 서버에서 생성된 요청별 nonce 값으로 교체하십시오.

아래 표는 nonce 확장 변형과 호환되는 CSP 정책을 보여줍니다.

| 정책 | 작동 | 참고 |
| --- | --- | --- |
| `script-src 'self'` | 아니요 | 외부 CDN 출처는 허용되지 않으며, 인라인 스크립트도 차단됩니다. |
| `script-src 'self' https://websdk.appsflyersdk.com` | 부분적 | 로더와 SDK는 허용되지만, 인라인 설정 스크립트는 여전히 차단됩니다. |
| `script-src 'nonce-...' https://websdk.appsflyersdk.com` | 예 | Nonce는 인라인 스크립트와 로더를 포함하며, SDK 태그는 로더에 의해 nonce가 전달됩니다. |
| `script-src 'nonce-...' 'strict-dynamic'` | 예 (권장) | Nonce는 인라인 스크립트와 로더를 포함하며, `strict-dynamic`은 동적으로 주입된 SDK 태그에 신뢰를 전파합니다. 허용 목록에 CDN 출처가 필요하지 않습니다. |

CSP 정책 호환성

<div id="advanced-sdk-verification-with-csp-nonce-snippets" />

#### CSP nonce 스니펫을 사용한 고급 SDK 검증

<div id="nonce-without-smart-banners" />

<Accordion title="스마트 배너 없이">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
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

<Accordion title="스마트 배너와 함께">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
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

</Accordion>

<div id="discard-query-params" />

<Accordion title="쿼리 구문 삭제">

쿼리 구문에 앱스플라이어가 기록하지 않기를 바라는 데이터가 포함된 경우, 앱스플라이어 플랫폼에 일부 또는 모든 쿼리 파라미터를 삭제하도록 지시할 수 있습니다. 이렇게 하면 삭제된 것은 로데이터나 리포트에서 사용할 수 없습니다.

URL, 참조자 및 header\_referer와 관련하여 설명된 방법을 구현할 수 있습니다.

<div id="query-discard-options" />

#### 쿼리 삭제 옵션

| 방법 | 설명 |
| --- | --- |
| 모든 쿼리 구문 삭제 | url에 `af_url=true`을 추가하십시오. |
| 지정된 쿼리 구문 삭제 | 쿼리 구문 마스크를 설정하여 삭제할 구문을 지정합니다.   param이 매개변수 이름인 `af_url_mask=param`을 사용하여 폐기 마스크를 설정하십시오.<br /><br />예시:<br /><br />**마스크를 포함한 URL:**<br /><br />`param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`<br /><br />**삭제 후 URL:**<br /><br />`param1=value1&af_url_mask=param2;param3` |

</Accordion>

<div id="principles-of-event-recording" />

## 이벤트 기록 원리

<div id="conversion-and-standard-events" />

<Accordion title="전환 및 표준 이벤트">

* SDK에서 사용자 이벤트를 기록하여 앱스플라이어 플랫폼으로 전송합니다.
* 앱스플라이어는 마케터가 설정한 <Anchor target="_blank" href="/marketers/ko/docs/pba-brand-bundles-and-settings#web-event-settings">전환 이벤트</Anchor> 목록을 사용하여 이벤트를 표준 이벤트와 전환 이벤트로 분할합니다.
* 전환 이벤트 데이터는 PBA 대시보드에서 사용할 수 있습니다.
* 전환 이벤트 및 표준 이벤트 데이터는 <Anchor target="_blank" href="/marketers/ko/docs/pba-raw-data-reports">로데이터 리포트에서 사용할 수 있습니다.</Anchor>

<div id="conversion-events" />

### 전환 이벤트

* 전환 이벤트는 마케팅 및 비즈니스 활동에 대한 통찰력을 제공합니다. 전환 이벤트에는 구매, 다운로드, 가입 및 구독이 포함됩니다.
* PBA는 전환 이벤트를 사용자가 웹사이트에 방문하도록 유도한 미디어소스로 어트리뷰트합니다.
* 어트리뷰트 미디어소스를 식별하여 다양한 미디어소스에서 가져온 사용자의 품질을 측정하고 차별화할 수 있습니다.
* 전환 이벤트는 수익을 기록하고 ROI를 계산하는 데 사용됩니다.
* 특정 미디어소스에 대한 광고 예산을 이러한 미디어소스에서 발생하는 사용자로부터 발생하는 수익과 비교하기 위해 사용합니다.

<div id="standard-events" />

### 표준 이벤트

* 표준 이벤트는 전환으로 이어지는 사용자 여정과 퍼널을 검증하는 데 사용됩니다.
* 이를 사용하여 사용자 활동을 측정하고 사용자 인게이지먼트를 유도하는 미디어소스를 강조 표시합니다.
* 사용자 활동을 기록하여 사용자를 리인게이지먼트 캠페인에 표시합니다.

<div id="recording-events" />

### 이벤트 기록

특정 조건이 충족될 때, 예를 들어 방문 페이지가 로드되거나 사용자가 웹사이트 요소와 상호작용할 때, 이벤트를 기록하도록 웹 SDK를 트리거합니다. [이벤트 기록 예시](#recording-events::f1e16eae)를 참조하십시오.

</Accordion>

<div id="identifying-users-using-customer-user-id-cuid" />

<Accordion title="고객 사용자 ID(CUID)를 사용하여 사용자 식별">

* 앱스플라이어는 할당한 고유 CUID를 사용하여 웹 사용자를 식별합니다. 일반적으로 CUID는 백엔드 서버에서 관리합니다.
* 모바일 환경에서 사용하는 동일한 CUID 값을 사용하십시오. 이렇게 하면 여러 플랫폼에서 사용자 활동에 대한 전체적인 뷰를 가질 수 있습니다. 모바일 SDK의 기능은 setCustomerUserId 함수 (<Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid#cuid-설정방법">iOS</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid#cuid-설정방법">Android, Unity</Anchor>).
* 웹 SDK에서 CUID를 설정하는 방법:
  * CUID에 액세스할 수 있는 가장 이른 시점에 CUID를 설정합니다. 다시 말하면 대부분의 경우 로그인 또는 가입을 통해 사용자가 식별될 때까지 기다려야 합니다.
  * 다음 예제와 같이 setCustomerUserId()를 호출하는 JavaScript를 실행하십시오.   
    참고: CUID를 숫자일지라도 문자열로 전송하세요. 따옴표로 묶어 그렇게 하십시오.
* 웹 S2S를 구현하는 경우 백엔드에서 CUID를 웹 방문자 ID와 연결할 때 PBA에 알려야 할 수도 있다는 점을 고려하십시오.
* CUID에는 전화번호나 이메일 주소와 같이 <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid#cuid-및-프라이버시">직접 식별할 수 있는 개인 정보</Anchor>를 포함해서는 안 됩니다.

**예시: CUID 설정**

```javascript
// Associate all current user web events to distinct ID 663274 
AF('pba', 'setCustomerUserId' , '663274')
```

</Accordion>

<div id="web-sdk-event-parameters" />

<Accordion title="웹 SDK 이벤트 파라미터">

| 파라미터 이름 | 필수 | 설명 |
| --- | --- | --- |
| 이벤트 유형 | 예 | 이벤트 유형<br /><br />형식: 문자열<br /><br />이 파라미터를 항상 EVENT로 채우십시오.<br /><br />예: eventType: "EVENT" |
| eventName | 예 | 이벤트 이름<br /><br />형식: 문자열<br /><br />예시: 구매, 구독 |
| ~~eventCategory~~ | 아니요 | 이 파라미터는 더 이상 사용되지 않으며 공지되는 날짜에 시스템에서 삭제됩니다. 대신 eventValue 파라미터를 사용합니다. |
| ~~eventLabel~~ | 아니요 | 이 파라미터는 더 이상 사용되지 않으며 공지되는 날짜에 시스템에서 삭제됩니다. 대신 eventValue 파라미터를 사용합니다. |
| 이벤트 수익 | 아니요 | 전환 이벤트에 할당된 수익<br /><br />형식: Float |
| eventRevenueCurrency | 아니요 | 수익 통화<ul><li>3자리 <Anchor target="_blank" href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</Anchor> 통화 코드</li><li>기본값: USD</li></ul>형식: 문자열 |
| eventValue | 아니요 | 이벤트를 설명하는 이벤트 파라미터 맵. 제품 SKU, 개별 항목 가격과 같은 리치 인앱 이벤트 전송에 이 파라미터를 사용하세요.<br /><br />형식: JSON<br /><br />**예시:** 예시: 단가가 $3.99인 파란색의 SKU ABC123 전송하기<br /><br />`{"sku": "ABC123", “color": "blue", "unit_price":3.99,"currency": "USD"}`<br /><br />**제한 사항:** 1000자입니다. 이 값을 초과하지 마세요. 초과하는 경우 내용이 잘릴 수 있습니다. |

</Accordion>

<div id="recording-event-scenarios" />

<Accordion title="이벤트 기록 시나리오">

이벤트 예시

```javascript
// purchase event of shoes with associated revenue
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name"}});
```

전송하는 이벤트는 웹 앱의 특성에 따라 다릅니다. 예를 들어 온라인 스토어 앱에는 뉴스 매체와는 다른 일련의 이벤트가 필요합니다. 다음 시나리오를 참조하여 전송해야 하는 이벤트와 전송 시기를 파악하십시오.

<div id="online-store" />

#### 온라인 스토어

온라인 스토어을 관리한다고 가정하겠습니다. 기록하려고 하는 몇 가지 표준 이벤트는 다음과 같을 것입니다.

* 검색: 표준 이벤트
* 장바구니에 추가: 표준 이벤트
* 장바구니에서 삭제: 표준 이벤트
* 구매: 전환 이벤트

뉴스 아울렛

새로운 아울렛을 관리하고 있다고 가정하겠습니다. 기록하려고 하는 몇 가지 이벤트는 다음과 같을 것입니다.

* 가입: 전환 이벤트
* 구독 구매: 전환 이벤트

</Accordion>

<div id="ensuring-that-events-are-sent" />

<Accordion title="이벤트 전송 여부 확인">

이 부분은 웹 개발자용입니다.

<Anchor target="_blank" href="/marketers/ko/docs/test-pba-web-sdk-integration">테스트 PBA 웹 SDK 연동:</Anchor> 실시간으로 테스트 이벤트를 봅니다.

**이벤트가 앱스플라이어에 전송되었는지 확인하는 방법**:

1. 웹사이트를 엽니다.
2. 브라우저 개발 도구를 여십시오.
   * <Anchor target="_blank" href="https://developers.google.com/web/tools/chrome-devtools/open#console">Chrome에서 개발자 도구를 여는 방법</Anchor>
   * <Anchor target="_blank" href="https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/Web_Inspector_Tutorial/EnableWebInspector/EnableWebInspector.html">Safari에서 개발자 도구를 여는 방법</Anchor>
3. 네트워크 탭으로 전환합니다.
4. 이벤트를 트리거합니다.
5. 메시지로 필터링합니다.

   ![pba_af_event.png](https://files.readme.io/394f43890d1aaf09114054a3bca1a003178526e768a5da0b554dbc8d63ef1eb4-360003502238.png)
6. 대상 wa.appsflyer.com으로 시작하는 네트워크 요청을 찾습니다. (아래 스크린샷 참조).
7. 다음을 확인하십시오.
   1. 상태 코드가 200이다.
   2. 요청 페이로드는 이벤트의 파라미터와 일치한다.

</Accordion>

<div id="examples" />

## 예시

<div id="recording-events::f1e16eae" />

<Accordion title="이벤트 기록">

제공된 코드는 설명을 위한 것입니다. 이 코드를 그대로 사용하지는 마십시오.

* 가정: 가정: 이벤트가 전송될 때 웹 SDK가 페이지에 이미 로드되어 있습니다.
* 예제 시나리오에는 다음과 같은 경우 이벤트를 기록하기 위한 코드가 포함되어 있습니다.
  * 랜딩 페이지 로드.
  * 사용자가 웹사이트와 상호작용.

<Tabs>
<Tab title="네이티브 이벤트 기록">

**방문 페이지 로드 시 이벤트 기록하기**

* 뉴스레터 구독 페이지가 있고 구독을 기록하려고 합니다.
* 또한 감사 페이지를 설정하고 구독 후 사용자를 해당 페이지로 리디렉션할 수 있습니다.

```html
<html>
    <head>
        <!-- Assume that the server returns a response with details about the newly subscribed user -->
        <!-- Alternatively, you can extract data from localStorage or cookies,
            in case data was set in either of them during the subscription process
        -->
        <script>window.onload = function(){
            AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion', eventValue: {'label' : 'newspaper'}, eventName: 'subscription',}); } </script> </head> <body> <h1>Thank You for Subscribing to Our Newsletter</h1> </body> </html>
```

* 위의 코드에는 기본 HTML 페이지가 포함되어 있습니다. 이벤트를 전송하려면 웹 페이지에서 웹 SDK를 로드해야 합니다.
* 페이지가 로드되면 사용자가 페이지로 리디렉션된 후 창 로드 메서드가 AF() 메서드를 호출하여 구독 이벤트를 앱스플라이어로 보냅니다.

**사용자가 웹사이트와 상호 작용할 때 이벤트 기록하기**

* 전자상거래 웹사이트가 있고 결제 이벤트를 기록하려고 합니다.
* 사용자가 결제 버튼을 클릭하면 웹 SDK가 앱스플라이어에 이벤트를 전송합니다.

```html
<html>
<head>
    <!-- Assume that data about products in the shopping cart
    is stored in localStorage -->
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
    <h2>Shirt</h2>
    <p>
        <ul>
            <li>Color: Blue</li>
            <li>Quantity: 2</li>
            <li>Price: $20</li>
        </ul>
    </p>
    <h2>Pants</h2>
    <p>
        <ul>
            <li>Color: Black</li>
            <li>Quantity: 3</li>
            <li>Price: $15</li>
        </ul>
    </p>
    <button id='checkout'>Checkout</button>
</body>
</html>
```

위의 코드는 기본 HTML 페이지를 보여줍니다.  이벤트를 전송하려면 웹 페이지에서 웹 SDK를 로드해야 합니다.

* 페이지가 로드되면 클릭 리스너를 **체크아웃** 버튼에 바인딩합니다.
* 사용자가 **체크아웃** 버튼을 클릭하면 콜백 함수는 다음을 수행합니다.
  * localStorage에서 데이터를 가져옵니다.
  * AF() 메서드를 호출하고 메서드에 데이터를 전달합니다.
* AF() 메서드는 이벤트를 앱스플라이어로 보냅니다.

</Tab>

<Tab title="태그 관리자 이벤트 기록">

**방문 페이지 로드 시 이벤트 기록하기**

* 뉴스레터 구독 페이지가 있고 구독 성공을 기록하려고 합니다.
* 구독 성공 후 사용자가 리디렉션되는 감사 페이지를 설정했습니다.

1. 감사 페이지 설정

   ```html Markup
   <html>
   <head>
       <script>
            // Google Tag Manager loads the Web SDK
           <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
           new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
           j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
           'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
           })(window,document,'script','dataLayer','GTM-XXXX');
       </script>
        <script>
           // Assume that the server returns a response with details about the newly subscribed user
           function getResponseFromServer() {
               return JSON.stringify({ action: 'subscribe', category: 'site actions', label: userEmail })
           }
           //Alternatively, you can extract data from localStorage or cookies,
           //in case data was set in either of them during the subscription process
           localStorage.setItem('data', JSON.stringify({ action: 'subscribe', category: 'site actions', label: 'user@email.com' }));
       </script>
   </head>
   <body>
       <h1>Thank You for Subscribing to Our Newsletter</h1>
   </body>
   </html>
   ```

   선행 코드는 GTM을 로드하며 차례로 웹 SDK를 로드합니다. 그 후 스크립트에서 두 가지 다른 조치가 발생합니다. 하나는 사용자 세부 정보가 포함된 서버로부터 응답을 받는 기능입니다. 다른 하나는 데이터를 로컬 스토리지로 설정합니다. GTM은 기능과 localStorage에 모두 액세스할 수 있습니다. GTM을 사용하여 함수를 호출하고 localStorage에 액세스할 수 있습니다.
2. 감사 페이지가 로드된 후 구독을 어트리뷰트하기 위한 새 태그가 추가됩니다.

   [![](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
3. 태그에 고유한 이름을 지정하고 **커스텀 HTML** 태그 유형 옵션을 선택합니다.
4. **커스텀 HTML**에 다음 코드를 넣습니다.

   ```html
   <script> 
   AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'}); </script>
   ```

   ![gtm_tag_after_subscribe.png](https://files.readme.io/6cf080f94a97a7f38c50899a93d154320995e91f60963c075a5dd03b3a080408-360003515298.png)
5. **고급 설정** 컨트롤을 확장한 다음 텍스트 영역 아래의 **태그 시퀀싱** 컨트롤을 확장하고 태그가 실행된 후 변환을 실행하도록 설정되어 있는지 확인합니다.

   [![](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. 전환 태그를 실행하려면 트리거를 설정하십시오. 이 예에서는 감사 페이지를 로드할 때 트리거가 시작됩니다.

   [![](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

**사용자가 웹사이트와 상호 작용할 때 이벤트 기록하기**

* 전자상거래 웹사이트가 있고 결제 이벤트를 기록하려고 합니다.
* 사용자가 결제 버튼을 클릭한 후 웹 SDK가 앱스플라이어에 이벤트를 전송합니다.

1. 결제 페이지 설정

   ```html Markup
   <html>
   <head>
       <script>
           // Google Tag Manager loads the Web SDK
           <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
           new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
           j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
           'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
           })(window,document,'script','dataLayer','GTM-XXXX');
       </script>
   </head>
   <body>
       <h1>Shopping Cart</h1>
       <h2>Shirt</h2>
       <p>
           <ul>
               <li>Color: Blue</li>
               <li>Quantity: 2</li>
               <li>Price: $20</li>
           </ul>
       </p>
       <h2>Pants</h2>
       <p>
           <ul>
               <li>Color: Black</li>
               <li>Quantity: 3</li>
               <li>Price: $15</li>
           </ul>
       </p>
       <button id='checkout'>Checkout</button>
   </body>
   </html>
   ```

   선행 코드는 GTM을 사용하여 웹 SDK를 로드합니다. 나머지는 장바구니 페이지를 모방한 HTML입니다. ID 체크아웃이 있는 **체크아웃** 버튼을 확인하십시오. 이것은 해당 버튼의 클릭을 처리하도록 GTM을 설정할 때 필요합니다.
2. GTM에서 **변수**를 클릭하고 **설정**을 클릭하고 내장 변수 목록에서 **요소를 클릭합니다.**   

   [![gtm-create-variable.png](https://files.readme.io/2f38308b4e4b9f279420f0219b220f2796d337a39a79241861c3d31bdb442b24-360002899569.png)](https://files.readme.io/2f38308b4e4b9f279420f0219b220f2796d337a39a79241861c3d31bdb442b24-360002899569.png)
3. 새 변수를 만들고 의미 있는 이름을 지정한 다음 **모든 요소** 유형을 선택합니다.   

   [![gtm-checkout-all-elements.png](https://files.readme.io/1c370646a4c21dc0fcb8351c756a9fdc81a1a8039d0557b716bc8a4ae51a3fad-360002899589.png)](https://files.readme.io/1c370646a4c21dc0fcb8351c756a9fdc81a1a8039d0557b716bc8a4ae51a3fad-360002899589.png)
4. 트리거 설정에서 **Some Clicks** 를 선택하고 #checkout의 **CSS Selector와 일치**하는 **클릭 요소**를 선택합니다.  

   [![gtm-checkout-click-elememt.png](https://files.readme.io/a101d6c27438d3e05eed9db7ea58b57df8bba9a92d4f9e30caee005366dbcf8c-360002903565.png)](https://files.readme.io/a101d6c27438d3e05eed9db7ea58b57df8bba9a92d4f9e30caee005366dbcf8c-360002903565.png)
5. 체크아웃 조치에 대한 새 태그를 만들고 커스텀 HTML 유형을 선택한 다음 트리거를 체크아웃 트리거로 설정합니다.

   ```html
   <script>
    AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'}); </script>
   ```

   ![gtm-checkout-tag.png](https://files.readme.io/8d3f99dcd3c3ff8df9e6fc13076b798237b86f8cbc5bbd26f349fa9948edb0d6-360003431857.png)

</Tab>
</Tabs>

* 이벤트가 시작되기 전에 웹 SDK 함수 태그가 로드되었는지 확인하십시오.
* 이벤트 값으로 수익 값의 통화 기호와 같은 특수 문자를 전송하지 마십시오.
* 값 문자열은 50자 미만이어야 합니다.

</Accordion>

<div id="setting-customer-user-id-after-signup" />

<Accordion title="가입 후 고객 사용자 ID 설정">

이 예제에 제공된 코드는 단지 참조용입니다. 이 코드를 그대로 사용하지는 마십시오. 이 코드의 사용 방법을 잘 모르는 경우 웹 개발자에게 문의하십시오.

가정: 가정: 이벤트가 전송되기 전에 페이지에서 웹 SDK를 로드합니다. SDK는 다시 로드되지 않았습니다.

사용자 시나리오:

* 사용자가 귀사 웹사이트에 가입합니다.
* 웹사이트 코드는 사용자 세부 정보를 수집하여 귀사 서버로 전송합니다.
* 서버는 사용자에 대해 고유한 CUID를 생성합니다.
* 가입 후 감사 페이지에서 서버에 대해 새 CUID를 쿼리합니다.
* 서버 응답을 사용하여 웹 SDK setCustomerUserId() 메서드를 사용하여 앱스플라이어 CUID를 설정합니다.

<Tabs>
<Tab title="네이티브">

가입 페이지 설정:

```html Markup
<html>
<head>
    <!-- The Web SDK script loads first -->
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        };
    // This function stores the user email sent to the server after the user reaches the thank you page
    // The response from the server is a unique CUID that should be set using the web SDK setCustomerUserId method
        function storeUserEmail (){
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Sign Up</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Name</label>
            <input type="text" name="name" id="name"></div>
        <br />
        <div> <label>Email</label>
            <input type="email" name="email" id="email"></div>
        <br />
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

위의 선행 코드는 간단한 가입 양식입니다. 양식이 제출되면 이메일이 localStorage에 저장됩니다. 사용자가 감사 페이지를 열면 사용자 이메일 주소가 서버로 전송되어 이메일 주소에 대한 고유 CUID가 생성됩니다.

가입한 사용자를 위한 감사 페이지 설정:

```html Markup
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
        // Using the fetch API to send the user email to the server
        // and get the unique user id in return	
        window.onload = function () {
            var userEmail = localStorage.getItem('user_email');
            fetch('users/' + userEmail).then(function (res) {
                   res.text().then(function (id) {
                    console.log(id);
                    AF('pba', 'setCustomerUserId', id);
                });
            });
        }  </script> 
     </head> 
     <body> 
        <h1>Thank You for Signing Up!</h1> 
     </body> 
</html>
```

코드는 fetch API를 사용합니다. 사용자가 입력한 이메일 주소를 서버에 전송합니다. 서버가 가입 시 고유한 CUID를 가진 사용자를 생성한다고 가정할 때, 이메일 주소를 서버에 전송하는 것은 고유한 CUID를 받기 위한 목적입니다. 서버는 고유한 CUID로 응답하며 이 고유한 CUID는 setCustomerUserId 메서드와 함께 전달되는 값입니다.

</Tab>

<Tab title="Google Tag Manager">

1. 가입 페이지 설정:

   ```html Markup
   <html>
   <head>
       <script>
            // Google Tag Manager loads the Web SDK
           (function (w, d, s, l, i) {
               w[l] = w[l] || []; w[l].push({
                   'gtm.start':
                       new Date().getTime(), event: 'gtm.js'
               }); var f = d.getElementsByTagName(s)[0],
                   j = d.createElement(s), dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true; j.src =
                       'https://www.googletagmanager.com/gtm.js?id=' + i + dl; f.parentNode.insertBefore(j, f);
           })(window, document, 'script', 'dataLayer', 'GTM-5VJ6C7R');

       // This function stores the user email to be sent to the server after the user reaches the thank you page
       // the response from the server is a unique CUID that should be used in the web SDK setCustomerUserId method
           function storeUserEmail (){
               var userEmail = document.getElementById('email').value;
               localStorage.setItem('user_email', userEmail);
           }
       </script>
   </head>
   <body>
       <h1>Sign Up</h1>
       <form onsubmit="storeUserEmail()" action="/signup" method="post">
           <div><label>Name</label>
               <input type="text" name="name" id="name"></div>
           <br />
           <div> <label>Email</label>
               <input type="email" name="email" id="email"></div>
           <br />
           <input type="submit" id="submit">
       </form>
   </body>
   </html>
   ```

   위의 코드는 간단한 가입 양식입니다. 양식이 제출되면 이메일 주소가 localStorage에 저장됩니다. 사용자가 감사 페이지를 열면 사용자 이메일 주소가 서버로 전송되어 해당 이메일에 대한 고유 CUID를 얻게 됩니다.
2. 가입한 사용자를 위한 감사 페이지 설정:

   ```
   (t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
   t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
   o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
   p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
       </script>
       <script>
           // using the fetch api to send the user email to the server
           // and get the unique user id in return 
           window.onload = function () {
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
                  res.text().then(function (id) {
                  console.log(id);
                  AF('pba', 'setCustomerUserId', id);
               });
            });
           } </script> 
       </head>
       <body> 
               <h1>Thank You for Signing Up!</h1> 
        </body> 
    </html>
   ```

   선행 코드는 가입 양식에서 사용자가 제공한 이메일 주소를 서버로 보내는 GTM 트리거가 있는 감사 페이지입니다.  
   가입 시 서버가 고유한 CUID를 가진 사용자를 생성한다고 가정합니다.  
   서버에 이메일을 보내는 것은 고유한 CUID를 수신하기 위한 것입니다.  
   서버는 setCustomerUserId() 메서드를 사용하여 전송된 고유한 CUID로 응답합니다.  
   트리거와 탭을 생성하려면 이 절차를 계속하십시오.
3. 감사 페이지가 로드된 후 구독을 어트리뷰트하기 위한 새 태그가 추가됩니다.[![](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
4. 태그에 고유한 이름을 지정하고 '커스텀 HTML' 태그 유형 옵션을 선택합니다.[![](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)

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
5. **고급 설정** 컨트롤을 확장한 다음 텍스트 영역 아래의 **태그 시퀀싱** 컨트롤을 확장하고 태그가 실행된 후 변환을 실행하도록 설정되어 있는지 확인합니다.

   [![](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. 전환 태그가 실행되어야 하는 시점을 나타내도록 전환 태그에 대한 트리거를 설정합니다(아래 예에서는 '감사' 페이지 로드 시 실행됨).

   [![](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

</Tab>
</Tabs>

setCustomerUserId 함수는 사용자 흐름의 모든 단계(예: 사용자 로그인 및 가입 후)에서 전송할 수 있습니다. 앱스플라이어는 전송된 가장 최근의 CUID를 사용하여 과거 또는 미래의 터치포인트 및 이벤트에 대해 현재 관찰된 사용자를 업데이트합니다.

모바일 앱의 setCustomerUserd 기능에서와 동일한 CUID 값을 사용합니다(<Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid#cuid-설정방법">iOS</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid#cuid-설정방법">안드로이드,</Anchor> Unity에 대해서는 모바일 setCustomerUserId 참조)

</Accordion>

<div id="addtional-information" />

## 추가 정보

<div id="web-sdk-cookies" />

<Accordion title="웹 SDK 쿠키">

다음 표에 기재한 쿠키는 웹사이트의 Web SDK에서 설정하거나 사용합니다.

표에서 다음 약어가 사용됩니다.

* AMP: AMP: 액셀러레이티드 모바일 페이지
* CDN: CDN: 콘텐츠 전송 네트워크
* 3PC: 3PC: 타사 쿠키

| 쿠키 이름 | 도메인 | 수명 | 사용하는 경우 | 세부 정보 |
| --- | --- | --- | --- | --- |
| afUserid | 웹사이트 도메인 | 395일 | 비 AMP | 웹 로드 및 탐색 이벤트 맥락에서 사용자 식별 |
| AF\_SYNC | 웹사이트 도메인 | 1주 | 비 AMP | <ul><li>최종 사용자 식별자가 설정되었음을 나타내는 플래그</li><li>이것은 사이트 로드 시간을 줄이는 데 사용됩니다.</li></ul> |
| af\_id | appsflyer.com | 395일 | 3PC가 허용되는 경우 비 AMP | 앱 실행 및 탐색 이벤트 맥락에서 사용자 식별 |
| af\_id | onelink.me | 395일 | 3PC가 허용되는 경우 비 AMP | 배너 인게이지먼트, 원링크 인게이지먼트 또는 둘 다를 앱 실행 이벤트에 연결합니다. |
| amp-afUserid | AMP CDN 또는 웹사이트 도메인 | 1년 | AMP의 페이지 서비스용 |  |
| AF\_DEFAULT\_MEASUREMENT\_STATUS | 웹사이트 도메인 | 395일 | PBA 동의 상태를 저장합니다. 사용자 동의가 부여될 때까지 SDK 작동을 방지합니다. 기본적으로 설정되지 않음—[동의 게이팅](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout)이 구성된 경우에만 사용됩니다. | 비 AMP |

</Accordion>

<div id="release-notes" />

<Accordion title="웹 SDK 릴리스 노트">

| 날짜 | 버전 | 참고 |
| --- | --- | --- |
| 2021년 7월 1일 | 1.0 | [쿼리 구문 삭제](/docs/pba-web-sdk-integration-guide#discard-query-params) |
| 2021년 6월 1일 | 1.0 | [콘텐츠 보안 정책(CSP) 구현](/docs/pba-web-sdk-integration-guide#implement-a-content-security-policy-csp-policy) |
| 2020-08-31 | 1.0 | [옵트인 및 옵트아웃 기능이 추가됨](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout) |
| 2020년 4월 16일 | 1.0 | customerUserId() 함수는 고유한 CUID를 보내기 위한 IDENTIFY 이벤트를 대체합니다. |
| 2020-07-30 | 1.0 | <ul><li>이벤트를 전송하기 위한 명시적 시작/중지 제어</li><li>기본 초기 상태 변경</li></ul> |

</Accordion>

<div id="deprecations" />

<Accordion title="사용 중단">

* 사용 중단 알림 기능은 기능 또는 방법 지원을 중단하려는 의도를 미리 알려줍니다. 기능 또는 방법은 사용 금지 시점까지 계속 작동합니다.
* 사용 중단 통지를 코드를 변경할 수 있는 기회로 생각하십시오.

| 사용 중단 날짜 | 운영 종료 일자 | 세부 정보 |
| --- | --- | --- |
| 2020년 4월 16일 | 통지됨 | **더 이상 사용되지 않는 방법:** 더는 사용되지 않는 메서드: eventType이 "IDENTIFY"로 설정된 이벤트 파라미터 customUserId의 고객 사용자 ID(CUID) 전송<br /><br />**현재 방법:** setCustomerUserId() 함수를 사용하여 CUID를 전송합니다. |

</Accordion>

<div data-zendesk-anchors="web-sdk-user-and-integration-guide=web-sdk-%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B0%80%EC%9D%B4%EB%93%9C-%EB%B0%8F-%EC%97%B0%EB%8F%99-%EA%B0%80%EC%9D%B4%EB%93%9C h_01HFKCMH8HAW5DN4K9H1A5Q2NJ=web-sdk-%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B0%80%EC%9D%B4%EB%93%9C-%EB%B0%8F-%EC%97%B0%EB%8F%99-%EA%B0%80%EC%9D%B4%EB%93%9C step-2-select-a-code-snippet=%EC%BD%94%EB%93%9C-%EC%8A%A4%EB%8B%88%ED%8E%AB-%EC%84%A0%ED%83%9D%ED%95%98%EA%B8%B0 h_01KP11XJV8RDV378GMFF0DVZ8V=%EC%BD%94%EB%93%9C-%EC%8A%A4%EB%8B%88%ED%8E%AB-%EC%84%A0%ED%83%9D%ED%95%98%EA%B8%B0 h_01KP3CJBZWJF8X46W2BBCS9ZVX=%EC%A4%91%EC%9A%94 standard=%ED%91%9C%EC%A4%80-%EC%9B%B9-sdk h_01KP11XJV8MN64YV17D1M0T5B9=%ED%91%9C%EC%A4%80-%EC%9B%B9-sdk h_01KP3CJBZWK17M58W9M2EP8VC3=standard-without-smart-banners h_01KP3CJBZWKW1K9P9V1XGYM5ED=standard-with-smart-banners advanced-sdk-verification=%EA%B3%A0%EA%B8%89-sdk-%EA%B2%80%EC%A6%9D h_01KP11XJV8ZGF4SDXJH6FKX18E=%EA%B3%A0%EA%B8%89-sdk-%EA%B2%80%EC%A6%9D h_01KP3CJBZWP7HDJ0GE2DF3TTE3=advanced-verification-without-smart-banners h_01KP3CJBZWJWS9H0XVHQFF758B=advanced-verification-with-smart-banners integrating-the-web-sdk-into-the-website=%EC%9B%B9-sdk%EB%A5%BC-%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8%EC%97%90-%EC%97%B0%EB%8F%99%ED%95%98%EA%B8%B0 h_01HFKCMH8HCDNGFJEN32BNA9F2=%EC%9B%B9-sdk%EB%A5%BC-%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8%EC%97%90-%EC%97%B0%EB%8F%99%ED%95%98%EA%B8%B0 h_01HFKCMH8HVTJX37PD22ZFV0AY=installation-and-integration considerations-and-actions-required=%EA%B3%A0%EB%A0%A4%EC%82%AC%ED%95%AD-%EB%B0%8F-%ED%95%84%EC%88%98-%EC%A1%B0%EC%B9%98 h_01HFKCMH8H0JBGD2GWY127428R=%EA%B3%A0%EB%A0%A4%EC%82%AC%ED%95%AD-%EB%B0%8F-%ED%95%84%EC%88%98-%EC%A1%B0%EC%B9%98 javascript-code-snippet=javascript-%EC%BD%94%EB%93%9C-%EC%8A%A4%EB%8B%88%ED%8E%AB h_01HFKCMH8HC064MHGH8D66QCYK=javascript-%EC%BD%94%EB%93%9C-%EC%8A%A4%EB%8B%88%ED%8E%AB to-install-the-web-sdk-without-smart-banners=%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88-%EC%97%86%EC%9D%B4-%EC%9B%B9-sdk%EB%A5%BC-%EC%9D%B8%EC%8A%A4%ED%86%A8%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01HFKCMH8HST7G880G44WXXXB6=%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88-%EC%97%86%EC%9D%B4-%EC%9B%B9-sdk%EB%A5%BC-%EC%9D%B8%EC%8A%A4%ED%86%A8%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 to-implement-the-web-sdk-with-smart-banners=%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88%EB%A1%9C-%EC%9B%B9-sdk%EB%A5%BC-%EA%B5%AC%ED%98%84%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01HFKCMH8HX4SQP6YCBHJH4AX5=%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88%EB%A1%9C-%EC%9B%B9-sdk%EB%A5%BC-%EA%B5%AC%ED%98%84%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01HFKCMH8JMMPMHFR4399QPRJV=create-a-property-in-adobe-experience-cloud h_01HFKCMH8J8WVHP7RZ2ENHGY9V=add-the-web-sdk-to-the-adobe-launch-property h_01HFKCMH8J2MAXJ3YVHJ2AJHWQ=add-the-adobe-launch-tag-to-the-website h_01HFKCMH8JWE1Q2749N54MAYRT=publish-the-adobe-launch-environment h_01HFKCMH8JFQQG0BEQ5CATGQ2P=ensure-that-the-sdk-is-working h_01HFKCMH8JCHH5WB5XRC8029DE=sending-events-optinoptout sdk-initial-state-setting=sdk-%EC%B4%88%EA%B8%B0-%EC%83%81%ED%83%9C-%EC%84%A4%EC%A0%95 h_01HFKCMH8JSJR95Y9KNANABBKR=sdk-%EC%B4%88%EA%B8%B0-%EC%83%81%ED%83%9C-%EC%84%A4%EC%A0%95 explicit-control=%EB%AA%85%EC%8B%9C%EC%A0%81-%EC%A0%9C%EC%96%B4 h_01HFKCMH8JG2C43P8QZ0SKZCBB=%EB%AA%85%EC%8B%9C%EC%A0%81-%EC%A0%9C%EC%96%B4 h_01HFKCMH8J9XDX87ES4F5WW4GJ=implement-a-content-security-policy-csp-policy content-security-policy-csp=%EC%BD%98%ED%85%90%EC%B8%A0-%EB%B3%B4%EC%95%88-%EC%A0%95%EC%B1%85csp h_01KGJCGCQ0QB7NK6YNZT5XJVJY=%EC%BD%98%ED%85%90%EC%B8%A0-%EB%B3%B4%EC%95%88-%EC%A0%95%EC%B1%85csp advanced-sdk-verification-with-csp-nonce-snippets=csp-nonce-%EC%8A%A4%EB%8B%88%ED%8E%AB%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%9C-%EA%B3%A0%EA%B8%89-sdk-%EA%B2%80%EC%A6%9D h_01KP11XJV88YB2NSBZJTX9K7ZQ=csp-nonce-%EC%8A%A4%EB%8B%88%ED%8E%AB%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%9C-%EA%B3%A0%EA%B8%89-sdk-%EA%B2%80%EC%A6%9D h_01KP3CJBZXQ4D538H0T7N9FZ6Z=nonce-without-smart-banners h_01KP3CJBZX8K3WK6RHQMB029VN=nonce-with-smart-banners h_01HFKCMH8JG40DT9NHXG6TPMJ1=discard-query-params query-discard-options=%EC%BF%BC%EB%A6%AC-%EC%82%AD%EC%A0%9C-%EC%98%B5%EC%85%98 h_01HFKCMH8JYSV81BEY5XQRZ24Y=%EC%BF%BC%EB%A6%AC-%EC%82%AD%EC%A0%9C-%EC%98%B5%EC%85%98 principles-of-event-recording=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EA%B8%B0%EB%A1%9D-%EC%9B%90%EB%A6%AC h_01HFKCMH8JZCKH1JPTGBVJ3QP4=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EA%B8%B0%EB%A1%9D-%EC%9B%90%EB%A6%AC h_01HFKCMH8JEDEDC48AH5A2797D=conversion-and-standard-events conversion-events=%EC%A0%84%ED%99%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8 h_01HFKCMH8JYYB7HG2W8XQ7RFPD=%EC%A0%84%ED%99%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8 standard-events=%ED%91%9C%EC%A4%80-%EC%9D%B4%EB%B2%A4%ED%8A%B8 h_01HFKCMH8JQHSJF3T8SF4ZES7W=%ED%91%9C%EC%A4%80-%EC%9D%B4%EB%B2%A4%ED%8A%B8 recording-events=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EA%B8%B0%EB%A1%9D h_01HFKCMH8J79VD5BX96ANAYAFQ=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EA%B8%B0%EB%A1%9D h_01HFKCMH8JPJZQ81TYZX5PDF91=identifying-users-using-customer-user-id-cuid h_01HFKCMH8JYPNHJGYVRK1SZFYB=web-sdk-event-parameters h_01HFKCMH8J35YT2448PX8ZRM5P=recording-event-scenarios online-store=%EC%98%A8%EB%9D%BC%EC%9D%B8-%EC%8A%A4%ED%86%A0%EC%96%B4 h_01HFKCMH8JQS3CTE6NTZY4G8ZR=%EC%98%A8%EB%9D%BC%EC%9D%B8-%EC%8A%A4%ED%86%A0%EC%96%B4 h_01HFKCMH8J1EDH3XM5V4ECYCPS=ensuring-that-events-are-sent examples=%EC%98%88%EC%8B%9C h_01HFKCMH8J4KQSZ489TMDEN426=%EC%98%88%EC%8B%9C h_01HFKCMH8JAK25DZ1BZDFS4THD=recording-events::f1e16eae h_01HFKCMH8J4XNY5B9MKAS81T6Z=setting-customer-user-id-after-signup addtional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HFKCMH8KJDZ0A15RMQ8BDMDH=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HFKCMH8KV3QD9CPBSVWM3EVE=web-sdk-cookies h_01HFKCMH8KGJTE7BMK4VSQJF33=release-notes h_01HFKCMH8KP1SHA21JZA5PTZXG=deprecations" />
