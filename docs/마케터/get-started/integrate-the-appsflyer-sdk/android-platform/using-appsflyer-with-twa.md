---
title: TWA와 함께 앱스플라이어 사용하기
metadata:
  keywords:
    - Web View
    - Developers
    - TWA
    - PWA
    - Trusted web activities
    - Progressive web apps
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-26T05:08:01Z'
  edited_at: '2026-10-14T10:26:10Z'
  id: 360002330178
  locale: ko
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/ko/articles/360002330178
---
> **한눈에 보기:** 신뢰할 수 있는 웹 활동(TWA)과 함께 앱스플라이어를 사용하여 인스톨 수를 측정하고 인앱 이벤트를 기록하세요.

## 소개

### 신뢰할 수 있는 웹 활동이란 무엇입니까?

신뢰할 수 있는 웹 활동(TWA)은 웹 콘텐츠를 안드로이드 앱과 통합하는 새로운 방법입니다. TWA의 과제는 인앱 이벤트를 기록하는 것입니다. 이 과제는 이 문서에서 다룹니다. TWA에 대한 자세한 내용은 <Anchor target="_blank" href="https://developers.google.com/web/updates/2019/02/using-twa">여기</Anchor>를 참조하세요.

TWA는 프로그레시브 웹 앱에서도 사용할 수 있습니다.

### 프로그레시브 웹 앱이란 무엇입니까?

프로그레시브 웹 앱(PWA)은 앱과 유사한 경험을 제공하지만 실제로는 완전히 웹 기반인 앱입니다. PWA의 한 형태로는 활동이 TWA 기반인 안드로이드 앱이 있습니다. 이것이 이 문서에서 설명할 PWA의 형태입니다. TWA를 사용하면 PWA를 독립형 안드로이드 애플리케이션에 내장하여 구글 플레이 스토어에서 기존 PWA 애플리케이션을 효과적으로 소개할 수 있습니다.

순전히 웹 기반인 다른 형식은 이 문서에서 다루지 않습니다. PWA에 대한 자세한 내용은 <Anchor target="_blank" href="https://developers.google.com/web/progressive-web-apps/">여기</Anchor>를 참조하세요.

이 탭에서는 앱 내 전체 화면 웹 브라우저인 신뢰할 수 있는 웹 활동에 내장된 PWA에 대해 설명합니다. 이러한 앱에는 <Anchor target="_blank" href="https://developer.android.com/reference/android/app/Application">안드로이드 글로벌 애플리케이션 클래스</Anchor>가 있지만 그 활동은 전적으로 웹 기반입니다.

이 형태의 PWA를 사용하면 인스톨 수를 측정할 수 있습니다. 순전히 웹 기반인 다른 형식의 PWA는 인스톨 수를 측정하는 옵션을 제공하지 않습니다.

## TWA

<div id="sending-inapp-events-from-twa" />

<Accordion title="TWA에서 인앱 이벤트 전송하기">

인앱 이벤트는 네이티브 앱 활동에서 앱스플라이어 SDK를 사용하여 전송됩니다. TWA는 웹 기반이고 네이티브 활동이 아니기 때문에 앱스플라이어 SDK를 사용하여 인앱 이벤트를 전송할 수 없습니다. 대안으로 <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">서버 간 인앱 이벤트</Anchor>를 사용할 수 있습니다. TWA를 사용하여 서버 간 이벤트를 보내려면 아래 지침을 따르십시오.

### 선행 조건

TWA에서 앱스플라이어로 이벤트 전송을 시작하기 전에 다음을 수행하세요.

1. 프로젝트 수준 Gradle 파일에 다음 저장소를 추가합니다.  

   ```java
   maven { url "https://jitpack.io"}
   ```
2. 다음 라이브러리를 추가합니다.
   * android.support 라이브러리의 경우:
     * build.gradle에 다음을 추가합니다.  
       implementation 'com.github.GoogleChrome.custom-tabs-client:customtabs:91b4a1270b'
     * 다음 라이브러리를 가져옵니다.

       ```java
       import android.support.customtabs.CustomTabsClient;
       import android.support.customtabs.CustomTabsIntent;
       import android.support.customtabs.CustomTabsServiceConnection;
       import android.support.customtabs.CustomTabsSession;
       import android.support.customtabs.trusted.TrustedWebActivityIntentBuilder;
       import static android.support.customtabs.TrustedWebUtils.EXTRA_LAUNCH_AS_TRUSTED_WEB_ACTIVITY
       ```
   * androidX 라이브러리의 경우:
     * build.gradle에 다음을 추가합니다.  

       ```java
       implementation 'com.github.GoogleChrome:android-browser-helper:ff8dfc4ed3'
       ```
     * 다음 라이브러리를 가져옵니다.

       ```java
       import androidx.browser.customtabs.CustomTabsClient;
       import androidx.browser.customtabs.CustomTabsIntent;
       import androidx.browser.customtabs.CustomTabsServiceConnection;
       import androidx.browser.customtabs.CustomTabsSession;
       import androidx.browser.trusted.TrustedWebActivityIntentBuilder;
       ```

### 앱스플라이어 ID 가져오기

서버 간 이벤트를 보내려면 앱스플라이어 ID가 필요합니다. 앱스플라이어 안드로이드 SDK에서 앱스플라이어 ID를 얻을 수 있습니다.

먼저, <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">앱스플라이어 안드로이드 SDK를 연동</Anchor>했는지 확인하세요. 그리고 다음 SDK API를 사용하여 앱스플라이어 ID를 얻을 수 있습니다.

```java
String appsflyerId = AppsFlyerLib.getInstance().getAppsFlyerUID(this);
```

### 앱스플라이어 ID를 TWA로 보내기

다음 두 가지 방법 중 하나로 앱스플라이어 ID를 보낼 수 있습니다.

<div id="append-appsflyer-id-and-customer-user-id-to-url" />

<Accordion title="앱스플라이어 ID와 고객 유저 ID를 URL에 추가">

신뢰할 수 있는 웹 활동 인텐트를 구축할 때 해당 URL에 파라미터를 전달할 수 있습니다.

```java
private void launchTwa(String cuid, String af_id) {

    CustomTabsServiceConnection customTabsServiceonnection = new CustomTabsServiceConnection() {

        @Override
        public void onCustomTabsServiceConnected(ComponentName name, CustomTabsClient client) {
            Log.d(LOG_TAG, "onCustomTabsServiceConnected");

            // Setting up CustomTabsSession that is used to build an intent
            mClient = client;
            CustomTabsSession session = mClient.newSession(null);

            // Creating the intent to launch TWA using URL with query params that can be read by the Web App
            TrustedWebActivityIntentBuilder twaIntentBuilder = new TrustedWebActivityIntentBuilder(Uri.parse(defaultUri + "?cuid=" + cuid + "&appsflyer_id=" + af_id));
            Intent twaIntent = twaIntentBuilder.build(session);

            startActivity(twaIntent);
        }

        @Override
        public void onServiceDisconnected(ComponentName name) {
            Log.d(LOG_TAG, "onCustomTabsServiceDisconnected");
        }
    };

    CustomTabsClient.bindCustomTabsService(getApplicationContext(), "com.android.chrome", customTabsServiceonnection);
}
```

#### 앱스플라이어 ID 확인하기

웹 활동이 시작되면 간단한 JavaScript 스니펫을 사용하여 앱스플라이어 ID를 검색할 수 있습니다.

```javascript
let url = new URL(document.location.href);
    let appsflyerID;
url.searchParams.forEach((value, key) => {
    if(key === 'appsflyer_id') {
    	appsflyerID = value;
    }
})
```

앱스플라이어 ID가 있으면 나중에 사용할 수 있도록 로컬 스토리지에 저장하세요.

</Accordion>

<div id="sending-appsflyer-id-through-custom-headers" />

<Accordion title="커스텀 헤더를 통해 앱스플라이어 ID 전송하기">

신뢰할 수 있는 웹 활동에 커스텀 헤더를 전달할 수 있습니다. 서버는 이러한 헤더를 가져와 쿠키에 설정하고 브라우저로 전송합니다. 그런 다음 JavaScript를 사용하여 앱스플라이어 ID를 검색할 수 있습니다.

```java
private void launchTwa(String cuid, String af_id) { 
        CustomTabsServiceConnection customTabsServiceonnection = new CustomTabsServiceConnection() {

        @Override
        public void onCustomTabsServiceConnected(ComponentName name, CustomTabsClient client) {
            Log.d(LOG_TAG, "onCustomTabsServiceConnected");

            // Setting up CustomTabsSession that is used to build an intent
            mClient = client;
            CustomTabsSession session = mClient.newSession(null);

            // Creating the intent to launch TWA using URL with query params that can be read by the Web App
            TrustedWebActivityIntentBuilder twaIntentBuilder = new TrustedWebActivityIntentBuilder(Uri.parse(defaultUri);
            Intent twaIntent = twaIntentBuilder.build(session);

            // Passing additional custom headers to the intent so they can be read by the Web App
            Bundle customHeaders = new Bundle();
            customHeaders.putString("twa_params", "cuid=" + cuid + "&=appsflyer_id" + af_id");
            twaIntent.putExtra(Browser.EXTRA_HEADERS, customHeaders);
            startActivity(twaIntent);
        }

        @Override
        public void onServiceDisconnected(ComponentName name) {
            Log.d(LOG_TAG, "onCustomTabsServiceDisconnected");
        }
    };

    CustomTabsClient.bindCustomTabsService(getApplicationContext(), "com.android.chrome", customTabsServiceonnection);
}
```

#### 앱스플라이어 ID 확인하기

JavaScript는 개발사가 헤더에 액세스할 수 있는 API를 제공하지 않습니다. 따라서 서버는 전환 데이터를 쿠키로 웹 활동에 다시 보내야 합니다. 서버는 앱스플라이어 ID가 포함된 커스텀 헤더를 가져와 데이터를 파싱한 후 이를 웹페이지에 쿠키로 보냅니다.

페이지가 로드되면 앱스플라이어 ID 쿠키를 가져오도록 JavaScript 스니펫이 설정되어야 합니다.

```javascript
// get the conversion data cookie 
// function taken from https://plainjs.com/javascript/utilities/set-cookie-get-cookie-and-delete-cookie-5/
function getCookie(name) {
    var v = document.cookie.match('(^|;) ?' + name + '=([^;]*)(;|$)');
    return v ? v[2] : null;
}

// get the cookie
var conversionData = JSON.parse(getCookie('appsflyer_id'));
console.log(appsflyer_id);
```

</Accordion>

### 인앱 이벤트 전송하기

인앱 이벤트를 보내려면 이벤트 데이터를 서버로 보내고 서버가 이벤트를 앱스플라이어로 보내도록 해야 합니다. 인앱 이벤트 전송을 위한 몇 가지 전제 조건이 더 있습니다.

* <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">SDK 개발 키</Anchor> - **중요! SDK 개발 키는 ​​중요한 값이므로 TWA에 나타나서는 안 됩니다. TWA를 사용하고 서버 간 인앱 이벤트를 보내려는 경우 항상 SDK 개발 키를 서버 측에 안전하게 저장하세요.**
* 앱 ID - AndroidManifest.xml에 표시되는 앱 ID입니다.

이 세 가지 파라미터(앱스플라이어 ID, SDK 개발 키, 앱 ID)가 있으면 인앱 이벤트를 전송할 수 있습니다. 웹 활동에서 이벤트가 발생할 때마다 이 이벤트를 처리하기 위해 웹 서버에 요청을 보내야 합니다. 웹 서버는 이벤트와 관련된 데이터를 가져와서 이벤트를 구성하고 이를 앱스플라이어로 보냅니다.

서버 간 인앱 이벤트를 보내는 방법의 예는 <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile#모바일용-서버-투-서버-이벤트-api">여기</Anchor>를 참조하세요.

</Accordion>

<div id="customizing-web-content-with-conversion-data" />

<Accordion title="전환 데이터로 웹 콘텐츠 커스터마이징하기">

앱스플라이어 SDK는 두 가지 API를 통해 전환 데이터를 제공합니다.

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">전환 데이터 가져오기</Anchor> - 설치 후 처음으로 앱이 실행될 때와 후속 앱 실행 시 호출됩니다.
* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/api-reference#onappopenattribution">앱 오픈 어트리뷰션 시</Anchor> - 앱이 원링크를 사용하여 딥링크될 때 호출됩니다.

전환 데이터를 사용하여 웹 콘텐츠를 커스터마이징할 수 있습니다.

### TWA로 전환 데이터 보내기

위에 나열된 방법 중 하나로 전환 데이터를 얻은 후에는 이를 웹 서버로 보낼 수 있습니다. 그렇게 하려면 커스텀 헤더를 사용하세요.

```java
private void launchTwa(Map<String, String> conversionData, String cuid, String af_id) { 
        CustomTabsServiceConnection customTabsServiceonnection = new CustomTabsServiceConnection() {

        @Override
        public void onCustomTabsServiceConnected(ComponentName name, CustomTabsClient client) {
            Log.d(LOG_TAG, "onCustomTabsServiceConnected");

            // Setting up CustomTabsSession that is used to build an intent
            mClient = client;
            CustomTabsSession session = mClient.newSession(null);

            // Creating the intent to launch TWA using URL with query params that can be read by the Web App
            TrustedWebActivityIntentBuilder twaIntentBuilder = new TrustedWebActivityIntentBuilder(Uri.parse(defaultUri);
            Intent twaIntent = twaIntentBuilder.build(session);

            // Passing additional custom headers to the intent so they can be read by the Web App
            Bundle customHeaders = new Bundle();
            customHeaders.putString("twa_params", "cuid=" + cuid + "&=" + af_id");
            customHeaders.putString("conversion_data", conversionData);
            twaIntent.putExtra(Browser.EXTRA_HEADERS, customHeaders);
            startActivity(twaIntent);
        }

        @Override
        public void onServiceDisconnected(ComponentName name) {
            Log.d(LOG_TAG, "onCustomTabsServiceDisconnected");
        }
    };

    CustomTabsClient.bindCustomTabsService(getApplicationContext(), "com.android.chrome", customTabsServiceonnection);
}
```

### 클라이언트 측에서 전환 데이터 가져오기

JavaScript는 개발사가 헤더에 액세스할 수 있는 API를 제공하지 않습니다. 따라서 서버는 전환 데이터를 쿠키로 웹 활동에 다시 보내야 합니다. 서버는 전환 데이터가 포함된 커스텀 헤더를 가져오고 데이터를 파싱한 후 웹페이지에 쿠키로 보냅니다.

페이지가 로드되면 전환 데이터 쿠키를 가져오고 이에 따라 콘텐츠를 커스터마이징하기 위한 JavaScript 스니펫이 설정되어야 합니다. 예를 들어, 유저가 항공편 특가 캠페인에서 앱을 설치하는 경우 캠페인이 홍보하는 특가와 관련된 콘텐츠로 웹 활동을 채울 수 있습니다.

```javascript
// get the conversion data cookie 
// function taken from https://plainjs.com/javascript/utilities/set-cookie-get-cookie-and-delete-cookie-5/
function getCookie(name) {
    var v = document.cookie.match('(^|;) ?' + name + '=([^;]*)(;|$)');
    return v ? v[2] : null;
}

// get the cookie
var conversionData = JSON.parse(getCookie('conversion_data'));
console.log(conversionData);
/*
conversion data example:
{ 
        campaign: "CAMPAIGN_NAME", // "None" if not specified on the link
        media_source: "MEDIA_SOURCE", //"None" if not specified on the link     
        cost_cents_USD : "0",
        is_first_launch: true,
        install_time: "2018-12-30 23:59:39.330",
        orig_cost: "0.0",
        af_click_lookback: "7d",
        click_time: "2018-12-30 23:59:09",
        cost_cents_USD: "0",
        af_status: "Non-organic"
}
*/
```

전환 데이터 사용 사례에 대해 자세히 알아보려면 <Anchor target="_blank" href="/marketers/ko/docs/conversion-data-payloads-and-scenarios">여기</Anchor>를 참조하세요.

</Accordion>

## PWA

<div id="measuring-installs-for-pwa" />

<Accordion title="PWA 인스톨 측정">

다른 안드로이드 앱과 마찬가지로 앱스플라이어 SDK를 PWA와 연동하여 인스톨 수를 측정하고 전환 데이터를 얻을 수 있습니다.

인스톨 수를 측정하려면 <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">여기</Anchor>에 나온 지침에 따라 SDK를 연동하기만 하면 됩니다.

</Accordion>

<div id="customizing-content-using-conversion-data" />

<Accordion title="전환 데이터를 사용하여 콘텐츠 커스터마이징하기">

유저에게 앱을 설치하도록 유도하는 캠페인에 따라 웹 콘텐츠를 커스터마이징할 수 있습니다. 예를 들어 유저가 웹 스토어의 제품에 대해 20% 할인을 제공하는 캠페인을 통해 앱을 설치하는 경우입니다. 앱이 웹 활동을 시작하자마자 전환 데이터를 얻고 할인을 적용할 수 있습니다.

전환 데이터를 사용하여 웹 콘텐츠를 커스터마이징하는 방법을 알아보려면 [여기](/docs/using-appsflyer-with-twa#twa로-전환-데이터-보내기)에 나온 지침을 따르세요.

</Accordion>

<div id="recording-events-in-pwa" />

<Accordion title="PWA의 이벤트 기록">

PWA가 사용하는 것은 기본적으로 웹 활동인 TWA입니다. TWA는 웹 기반이고 네이티브 활동이 아니기 때문에 앱스플라이어 SDK를 사용하여 인앱 이벤트를 전송할 수 없습니다. 대안으로 서버 간 인앱 이벤트를 사용할 수 있습니다.

PWA용 인앱 이벤트를 보내는 방법을 알아보려면 [여기](/docs/using-appsflyer-with-twa#sending-inapp-events-from-twa)에 나온 지침을 따르세요.

</Accordion>

<div data-zendesk-anchors="introduction=%EC%86%8C%EA%B0%9C what-are-trusted-web-activities=%EC%8B%A0%EB%A2%B0%ED%95%A0-%EC%88%98-%EC%9E%88%EB%8A%94-%EC%9B%B9-%ED%99%9C%EB%8F%99%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C what-are-progressive-web-apps=%ED%94%84%EB%A1%9C%EA%B7%B8%EB%A0%88%EC%8B%9C%EB%B8%8C-%EC%9B%B9-%EC%95%B1%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C prerequisites=%EC%84%A0%ED%96%89-%EC%A1%B0%EA%B1%B4 getting-the-appsflyer-id=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-id-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0 sending-the-appsflyer-id-to-twa=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-id%EB%A5%BC-twa%EB%A1%9C-%EB%B3%B4%EB%82%B4%EA%B8%B0 retrieving-the-appsflyer-id=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-id-%ED%99%95%EC%9D%B8%ED%95%98%EA%B8%B0 retrieving-the-appsflyer-id::a3f31d46=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-id-%ED%99%95%EC%9D%B8%ED%95%98%EA%B8%B0-1 sending-the-inapp-event=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%A0%84%EC%86%A1%ED%95%98%EA%B8%B0 sending-conversion-data-to-twa=twa%EB%A1%9C-%EC%A0%84%ED%99%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EB%82%B4%EA%B8%B0 fetching-the-conversion-data-from-the-clientside=%ED%81%B4%EB%9D%BC%EC%9D%B4%EC%96%B8%ED%8A%B8-%EC%B8%A1%EC%97%90%EC%84%9C-%EC%A0%84%ED%99%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0" />
