---
title: TWAでのAppsFlyerの利用
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
  edited_at: '2026-10-20T13:02:20Z'
  id: 360002330178
  locale: ja
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/ja/articles/360002330178
---
> **概要：** Trusted Web Activities（TWA）でAppsFlyerを使用し、インストールの計測とアプリ内イベントの記録を行います。

<div id="introduction" />

## はじめに

<div id="what-are-trusted-web-activities" />

### Trusted Web Activitiesとは

Trusted Web Activities（TWA）は、Androidアプリ内にWebコンテンツを表示する新しい仕組みです。 TWAでは、アプリ内イベントをどのように記録するかが課題になります。この記事では、その対応方法を説明します。 TWAについて詳しくは、<Anchor target="_blank" href="https://developers.google.com/web/updates/2019/02/using-twa">こちら</Anchor>を参照してください。

TWAは、プログレッシブWebアプリでも使用できます。

<div id="what-are-progressive-web-apps" />

### プログレッシブWebアプリとは

プログレッシブWebアプリ（PWA）は、アプリのようなユーザー体験を提供する、すべてWeb技術で構成されたアプリです。 PWAの形態の1つに、TWAをベースとするアクティビティで構成されたAndroidアプリがあります。この記事では、この形態のPWAを扱います。 TWAを使用すると、PWAを独立したAndroidアプリに組み込み、既存のPWAをPlay Storeで公開できます。

Web上のみで動作するもう一方の形態のPWAは、この記事の対象外です。 PWAについて詳しくは、<Anchor target="_blank" href="https://developers.google.com/web/progressive-web-apps/">こちら</Anchor>を参照してください。

このタブでは、アプリ内の全画面WebブラウザであるTrusted Web Activityに組み込まれたPWAを説明します。このようなアプリには、<Anchor target="_blank" href="https://developer.android.com/reference/android/app/Application">Androidのアプリ全体を管理するApplicationクラス</Anchor>がありますが、画面はすべてWebベースです。

この形態のPWAでは、インストールを計測できます。 Web上のみで動作するもう一方の形態のPWAでは、インストールを計測できません。

## TWA

<div id="sending-inapp-events-from-twa" />

<Accordion title="TWAからのアプリ内イベントの送信">

通常、アプリ内イベントは、ネイティブの画面からAppsFlyer SDKを使用して送信されます。 TWAはWebベースの画面であり、ネイティブの画面ではないため、AppsFlyer SDKを使用してアプリ内イベントを送信することはできません。代わりに、<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">サーバー間通信によるアプリ内イベント</Anchor>を使用できます。 TWAでサーバー間通信によるイベントを送信するには、以下の手順に従ってください。

<div id="prerequisites" />

### 事前準備

TWAからAppsFlyerにイベントを送信する前に、次の作業を行ってください。

1. プロジェクトレベルのGradleファイルに、次のリポジトリを追加します。  

   ```java
   maven { url "https://jitpack.io"}
   ```
2. 次のライブラリを追加します。
   * android.supportライブラリの場合：
     * build.gradleに次の記述を追加します。  
       implementation 'com.github.GoogleChrome.custom-tabs-client:customtabs:91b4a1270b'
     * 次のライブラリをインポートします。

       ```java
       import android.support.customtabs.CustomTabsClient;
       import android.support.customtabs.CustomTabsIntent;
       import android.support.customtabs.CustomTabsServiceConnection;
       import android.support.customtabs.CustomTabsSession;
       import android.support.customtabs.trusted.TrustedWebActivityIntentBuilder;
       import static android.support.customtabs.TrustedWebUtils.EXTRA_LAUNCH_AS_TRUSTED_WEB_ACTIVITY
       ```
   * androidXライブラリの場合：
     * build.gradleに次の記述を追加します。  

       ```java
       implementation 'com.github.GoogleChrome:android-browser-helper:ff8dfc4ed3'
       ```
     * 次のライブラリをインポートします。

       ```java
       import androidx.browser.customtabs.CustomTabsClient;
       import androidx.browser.customtabs.CustomTabsIntent;
       import androidx.browser.customtabs.CustomTabsServiceConnection;
       import androidx.browser.customtabs.CustomTabsSession;
       import androidx.browser.trusted.TrustedWebActivityIntentBuilder;
       ```

<div id="getting-the-appsflyer-id" />

### AppsFlyer IDの取得

サーバー間通信によるイベントを送信するには、AppsFlyer IDが必要です。 AppsFlyer IDは、AppsFlyer Android SDKから取得できます。

まず、<Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">AppsFlyer Android SDKを実装</Anchor>してください。その後、次のSDK APIでAppsFlyer IDを取得できます。

```java
String appsflyerId = AppsFlyerLib.getInstance().getAppsFlyerUID(this);
```

<div id="sending-the-appsflyer-id-to-twa" />

### TWAへのAppsFlyer IDの送信

AppsFlyer IDは、次の2つの方法のいずれかで送信できます。

<div id="append-appsflyer-id-and-customer-user-id-to-url" />

<Accordion title="URLへのAppsFlyer IDと顧客ユーザーIDの追加">

TWAを起動するインテントを作成する際に、そのURLにパラメータを渡すことができます。

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

<div id="retrieving-the-appsflyer-id" />

#### AppsFlyer IDの取得

Webベースの画面が起動したら、次の簡単なJavaScriptコードでAppsFlyer IDを取得できます。

```javascript
let url = new URL(document.location.href);
    let appsflyerID;
url.searchParams.forEach((value, key) => {
    if(key === 'appsflyer_id') {
    	appsflyerID = value;
    }
})
```

取得したAppsFlyer IDは、後で使用できるようローカルストレージに保存します。

</Accordion>

<div id="sending-appsflyer-id-through-custom-headers" />

<Accordion title="カスタムヘッダーによるAppsFlyer IDの送信">

TWAには、カスタムヘッダーを渡すことができます。サーバーはこれらのヘッダーを取得し、Cookieに設定してブラウザに送信します。その後、次のJavaScriptコードでAppsFlyer IDを取得できます。

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

<div id="retrieving-the-appsflyer-id-1" />

#### AppsFlyer IDの取得

JavaScriptには、ヘッダーにアクセスするためのAPIがありません。そのため、サーバーはコンバージョンデータをCookieとしてWebベースの画面に返す必要があります。サーバーは、AppsFlyer IDを含むカスタムヘッダーを取得し、データを解析してCookieとしてWebページに送信します。

ページの読み込み時に、AppsFlyer IDのCookieを取得するJavaScriptコードが実行されるようにしてください。

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

<div id="sending-the-in-app-event" />

### アプリ内イベントの送信

アプリ内イベントを送信するには、イベントデータを自社のサーバーに送信し、そのサーバーからAppsFlyerにイベントを送信します。アプリ内イベントを送信するには、以下の情報も必要です。

* <Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">SDKのdev key</Anchor> — **重要！ SDKのdev keyは機密情報であり、TWA内に含めてはいけません。 TWAを使用してサーバー間通信によるアプリ内イベントを送信する場合は、SDKのdev keyを必ずサーバー側で安全に保管してください。**
* アプリID：AndroidのManifest.xmlに記載されているアプリIDです。

AppsFlyer ID、SDKのdev key、アプリIDの3つのパラメータが揃うと、アプリ内イベントを送信できます。 Webベースの画面でイベントが発生するたびに、Webサーバーにリクエストを送信してイベントを処理します。 Webサーバーは、イベントに関連するデータを取得してイベントデータを構成し、AppsFlyerに送信します。

サーバー間通信によるアプリ内イベントの送信例は、<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile#サーバー間イベントapi-for-モバイル">こちら</Anchor>を参照してください。

</Accordion>

<div id="customizing-web-content-with-conversion-data" />

<Accordion title="コンバージョンデータによるWebコンテンツのカスタマイズ">

AppsFlyer SDKは、次の2つのAPIを通じてコンバージョンデータを提供します。

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">Get conversion data</Anchor>：インストール後の初回起動時と、その後のアプリ起動時に呼び出されます。
* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/api-reference#onappopenattribution">On app open attribution</Anchor>：OneLinkによるディープリンクでアプリが開かれた際に呼び出されます。

コンバージョンデータを使用して、Webコンテンツをカスタマイズできます。

<div id="sending-conversion-data-to-twa" />

### TWAへのコンバージョンデータの送信

上記のいずれかの方法で取得したコンバージョンデータは、Webサーバーに送信できます。送信には、次のようにカスタムヘッダーを使用します。

```java
private void launchTwa(Map<0> conversionData, String cuid, String af_id) { 
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

<div id="fetching-the-conversion-data-from-the-client-side" />

### クライアント側でのコンバージョンデータの取得

JavaScriptには、ヘッダーにアクセスするためのAPIがありません。そのため、サーバーはコンバージョンデータをCookieとしてWebベースの画面に返す必要があります。サーバーは、コンバージョンデータを含むカスタムヘッダーを取得し、データを解析してCookieとしてWebページに送信します。

ページの読み込み時に、コンバージョンデータのCookieを取得し、その内容に応じてコンテンツをカスタマイズするJavaScriptコードが実行されるようにしてください。例えば、航空券の特別価格を訴求するキャンペーンからユーザーがアプリをインストールした場合、そのキャンペーンで紹介した特別価格に関連するコンテンツをWebベースの画面に表示できます。

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

コンバージョンデータの活用例については、<Anchor target="_blank" href="/marketers/ja/docs/conversion-data-payloads-and-scenarios">こちら</Anchor>を参照してください。

</Accordion>

## PWA

<div id="measuring-installs-for-pwa" />

<Accordion title="PWAのインストール計測">

他のAndroidアプリと同様に、アプリにAppsFlyer SDKを実装して、インストールを計測し、コンバージョンデータを取得できます。

インストールを計測するには、<Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">こちらの手順</Anchor>に従ってSDKを実装するだけです。

</Accordion>

<div id="customizing-content-using-conversion-data" />

<Accordion title="コンバージョンデータを使用したコンテンツのカスタマイズ">

ユーザーのアプリインストールにつながったキャンペーンに応じて、Webコンテンツをカスタマイズできます。例えば、Webストアの商品を20%割引で購入できるキャンペーンから、ユーザーがアプリをインストールしたとします。コンバージョンデータを取得し、アプリでWebベースの画面が開かれた時点で割引を適用できます。

コンバージョンデータによるWebコンテンツのカスタマイズについては、[こちらの手順](/docs/using-appsflyer-with-twa#twaへのコンバージョンデータの送信)に従ってください。

</Accordion>

<div id="recording-events-in-pwa" />

<Accordion title="PWAでのイベントの記録">

PWAは、実質的にWebベースの画面であるTWAを使用します。 TWAはWebベースの画面であり、ネイティブの画面ではないため、AppsFlyer SDKを使用してアプリ内イベントを送信することはできません。代わりに、サーバー間通信によるアプリ内イベントを使用できます。

PWAのアプリ内イベントを送信する方法は、[こちらの手順](/docs/using-appsflyer-with-twa#sending-inapp-events-from-twa)を参照してください。

</Accordion>

<div data-zendesk-anchors="introduction=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB what-are-trusted-web-activities=trusted-web-activities%E3%81%A8%E3%81%AF what-are-progressive-web-apps=%E3%83%97%E3%83%AD%E3%82%B0%E3%83%AC%E3%83%83%E3%82%B7%E3%83%96web%E3%82%A2%E3%83%97%E3%83%AA%E3%81%A8%E3%81%AF prerequisites=%E4%BA%8B%E5%89%8D%E6%BA%96%E5%82%99 getting-the-appsflyer-id=appsflyer-id%E3%81%AE%E5%8F%96%E5%BE%97 sending-the-appsflyer-id-to-twa=twa%E3%81%B8%E3%81%AEappsflyer-id%E3%81%AE%E9%80%81%E4%BF%A1 retrieving-the-appsflyer-id=appsflyer-id%E3%81%AE%E5%8F%96%E5%BE%97-1 retrieving-the-appsflyer-id::a3f31d46=appsflyer-id%E3%81%AE%E5%8F%96%E5%BE%97-2 sending-the-inapp-event=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%80%81%E4%BF%A1 sending-conversion-data-to-twa=twa%E3%81%B8%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E9%80%81%E4%BF%A1 fetching-the-conversion-data-from-the-clientside=%E3%82%AF%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%83%88%E5%81%B4%E3%81%A7%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97" />
