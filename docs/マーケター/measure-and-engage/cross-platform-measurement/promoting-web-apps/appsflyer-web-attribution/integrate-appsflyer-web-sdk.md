---
title: Integrate AppsFlyer Web SDK
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
  edited_at: '2026-10-14T09:23:43Z'
  id: 43485611331473
  locale: ja
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ja/articles/43485611331473
---
> **概要：** AppsFlyer Web SDK（ピクセルとも呼ばれます）をWebサイトに実装することで、ユーザーの訪問やイベントをAppsFlyerへ送信できるようになります。また、永続的なカスタマーユーザーID（CUID）を設定することで、複数プラットフォームにまたがるユーザージャーニーを統合できます。

<div id="note" />

<div id="integrate-the-sdk-with-an-ai-coding-agent" />

<div id="integrate-the-sdk-manually" />

<div id="overview" />

## 概要

Web SDK を使用すると、訪問者がWebサイト上でどのように行動したかを記録し、その情報をAppsFlyerへ送信できます。これは40〜60KBのプラグインモジュールで、Webサイト上でのユーザー訪問やアクションをAppsFlyerプラットフォームへレポートします。

以下の手順に従って、インストールから検証、プライバシー制御まで、Web SDK の実装を完了してください。

1. [キーの取得：Web](#1-キーの取得) SDK ID（Web Dev Keyとも呼ばれます）を取得します。
2. [コードスニペットの選択：](#2-コードスニペットの選択)連携タイプとセキュリティ要件に合ったスニペットを選択します。
3. [Web SDKのデプロイ：](#3-スニペットのデプロイ)ネイティブスニペット、Google Tag Manager、またはAdobe Launch Tag Managerを使用してSDKをデプロイします。
4. [SDKが機能していることを確認：](#2-sdkが正しく動作していることを確認する)ブラウザのデベロッパーツールでネットワークコールを確認し、SDKがリクエストを送信していることを検証します。
5. [イベントの設定・記録：](#3-イベントの設定記録)ネイティブJavaScriptまたはGoogle Tag Managerを使用して、ページ読み込み時またはユーザー操作時にカスタムイベントを定義し、送信します。
6. [カスタマーユーザーIDの設定：](#4-カスタマーユーザーidの設定)永続的なCUIDを設定し、Web上のアクティビティを他のプラットフォームと統合します。
7. [プライバシー設定の管理：](#5-プライバシーの管理)計測のオプトインまたはオプトアウトを管理し、セキュリティとデータフィルタリング（Content Security Policyおよびクエリパラメータの破棄）を設定します。
8. [Web SDK Cookieのリファレンス：Web](#web-sdk-cookieリファレンス) SDKが設定または使用するCookieについて、目的、有効期間、スコープを確認します。

<div id="1-obtain-your-keys" />

## 1. キーの取得

**Web SDK ID（Web Dev Keyとも呼ばれます）を取得します。**

1. AppsFlyer管理画面の左メニューから、**アプリ設定**を開きます。
2. ページ上部のアプリ選択メニューから、Webアプリ（「website-」の接頭辞が付いたWebサイトのドメイン）を選択します。
3. **SDK認証**のセクションで、**Web SDK ID**をコピーします。

**Smart Bannerのキーを取得します（必要な場合）：**

1. AppsFlyer のサイドメニューから、**Engage**>**Web-to-app**>**Smart Banners**を選択してください。
2. 必要な Smart Bannerのキーをコピーしてください。

<div id="warning" />

<div id="2-select-a-code-snippet" />

## 2. コードスニペットの選択

連携タイプとセキュリティ要件に合ったスニペットを選択します。利用できるオプションは2つあります。

* [スタンダードWeb SDK](#スタンダードweb-sdk)：標準の連携方法です。
* [アドバンスSDK検証](#アドバンスsdk検証)：Web SDKにサプライチェーン保護を追加する、強化された連携方法です。CDNの侵害、DNSハイジャック、中間者攻撃に対するセキュリティをさらに高めるために使用します。

> 🚧 **【重要】**
>
> スタンダードWeb SDKからアドバンスSDK検証へ移行する場合は、既存のスニペットを新しいものに置き換えてください。既存のスニペットに新しいスニペットを追加しないでください。

<div id="standard-web-sdk" />

### スタンダードWeb SDK

標準のWeb SDK連携を導入する場合は、このスニペットを使用します。SDKを読み込みたいすべてのページで、タグの上部付近に貼り付けてください。

<div id="standard-without-smart-banners" />

<Accordion title="Smart Bannersを使用しない場合">

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

<Accordion title="Smart Bannersを使用する場合">

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

<div id="advanced-sdk-verification" />

### アドバンスSDK検証

アドバンスSDK検証は、Web SDKにサプライチェーン保護を追加する仕組みです。ユーザーのブラウザで実行されるコードが、AppsFlyerによって公開されたコードそのものであることを保証します。SDKのソースコード自体はスタンダード連携と同一であり、異なるのは配信および検証の仕組みのみです。

アドバンスSDK検証の特徴は以下の通りです：

* CDN改ざん、DNSハイジャック、中間者攻撃（MITM）に対する追加のセキュリティレイヤーを提供
* SDKの読み込み時間が約250ms増加

アドバンスSDK検証は任意機能です。スタンダードな連携も引き続き完全にサポートされており、サードパーティ分析ピクセルにおける一般的な実装方式となっています。アドバンスSDK検証はそれに対して更に追加の保護レイヤーを提供します。

Webサイトでnonceを使用したContent Security Policy（CSP）を適用している場合は、「プライバシー管理」セクション内の「[Content Security Policy（CSP）](#コンテンツセキュリティポリシーcsp)」を参照し、このスニペットのnonce対応版を使用してください。

<div id="advanced-verification-without-smart-banners" />

<Accordion title="Smart Bannersを使用しない場合">

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

<Accordion title="Smart Bannersを使用する場合">

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

<div id="note-1" />

<div id="3-deploy-the-snippet" />

## 3. スニペットのデプロイ

手順2で選択したスニペットを、以下いずれかの方法でデプロイします。SDKがページごとに1回だけ読み込まれるよう設定してください。

<div id="option-a-add-directly-to-your-website" />

<Accordion title="選択肢 A：Webサイトに直接追加する">

すべてのページで以下を実施します：

1. 手順2のスニペット内にある `WEB_DEV_KEY` を、ご利用のWeb SDK IDに置き換えます（必要に応じて `YOUR_BANNER_KEY` も置き換えます）。
2. スニペットをWebサイトの  タグ上部付近に貼り付けます。

</Accordion>

<div id="option-b-deploy-via-google-tag-manager" />

<Accordion title="選択肢 B：Google Tag Manager（GTM）経由でデプロイする">

SDKがページごとに1回のみ読み込まれるように設定し、GTMの優先度設定を利用して、ページ読み込み直後に実行されるようにしてください。

1. Google Tag Managerを開きます。
2. AppsFlyer Web SDK用の新しいタグを作成します。
3. タグタイプで「**Custom HTML**」を選択します。
4. タグ名をわかりやすい名前に設定します。
5. 「**Tag Configuration**」に、手順2のスニペットを貼り付けます。
6. **保存**をクリックします。
7. トリガーを追加する：
   * すべてのページで実行する場合：
     1. [**トリガーの追加**] をクリックします。
     2. [**すべてのページ**] を選択してください。
     3. **保存**をクリックします。
     4. タグ名を入力し、<strong>［保存］</strong>をクリックします。
   * 特定ページのみで実行する場合：
     1. ［**タグを保存**］ をクリックします。
     2. GTMメイン画面で「**トリガー**」を選択し、「**New（新規作成）**」をクリックします。
     3. ペンのアイコンをクリックしてください。
     4. トリガータイプとして「**ページビュー（Page View）**」を選択します。
     5. [**Some Page Views**]（一部ページビュー）を選択します。
     6. 必要に応じてページ条件とトリガー条件を設定します。
     7. **保存**をクリックします。
     8. 作成したトリガーをAppsFlyer Web SDKタグに関連付ける
        1. <span class="af-ol-a"></span> **GTM**のメイン画面で「**Tags**」を選択します。
        2. 以前に作成したタグを選択してください。
        3. トリガーパネル内のペンアイコンをクリックします。
        4. 前に作成したページビュートリガーを選択してください。
        5. **保存**をクリックします。

> 📘 **注意**
>
> GTMのCustom Templatesは、アドバンスSDK検証ではサポートされていません。これは、Custom Templatesのサンドボックス環境では、検証に必要な `integrity` 属性を設定できないためです。代わりに、**Custom HTML**のタグタイプを使用してください。

</Accordion>

<div id="option-c-deploy-via-adobe-launch-tag-manager" />

<Accordion title="選択肢 C：Adobe Launch Tag Manager経由でデプロイする">

<div id="create-a-property-in-adobe-experience-cloud" />

#### Adobe Experience Cloudでプロパティを作成する

1. Adobe Experience Cloud > Launch へ移動してください。
2. Adobe Experience Cloud Launch の下にある **Go to Launch** をクリックします 。
3. [**New Property**]（新しいプロパティ）をクリックします。
4. プロパティに名前を付けてください。
5. **Platform** の下にある、 **Web** を選択します。
6. Webサイトのドメインを入力してください。
7. **保存**をクリックします。

<div id="add-the-snippet-to-the-adobe-launch-property" />

#### Adobe Launchプロパティにスニペットを追加する

1. **My web property** ページで、**Rules**タブを選択します。
2. ルールに名前を付けます。推奨名：Load web SDK
3. **If** セクションで、**Events**の下にある **+Add** をクリックしてください。
   * **Event Type** にある **Core - DOM Ready** を選択します
   * **Keep Changes**（変更を保存）をクリックします。
4. **Then** セクションで、**Actions** の下にある **+Add** をクリックしてください。
   * **アクションの種類**で**カスタムコード**を選択します。
   * 「**JavaScript**」>「**エディタを開く**」を選択し、手順2のスニペットを貼り付けます（ラッパー行は含めないでください）。
   * [**Keep Changes**]（変更を保存）をクリックして、コードエディターを閉じます。
5. **保存**をクリックします。

<div id="add-the-adobe-launch-tag-to-the-website" />

#### Adobe LaunchタグをWebサイトに追加する

1. [**My web property**] ページで、[**Environments**] タブを選択します。
2. 公開したい環境（developmentまたはproduction）の行を探します。
3. 「**Install**」列の該当行にあるボックスアイコンをクリックします。
4. 「**Web Install Instructions**」ダイアログで、スクリプトコードスニペットをコピーし、ダイアログを閉じます。
5. コピーしたコードスニペットをWebサイトの &lt;head> セクションに貼り付けます。

<div id="publish-the-adobe-launch-environment" />

#### Adobe Launch環境を公開する

1. [**My web property**] ページで、[**Publishing**] タブに移動します。
2. [**Development**]セクションの、[**Add New Library**] をクリックします。
   * ライブラリに名前を付けて、環境を選択します。
   * **Resource Changes** の下にある **Add a Resource** をクリックしてください。
   * **Rules** > **Load web SDK** > **Latest** > **Select & Create a New Revision** をクリックします。
   * **保存**をクリックします。
3. **Development**のセクションで実施する操作：
   * 新しく作成したライブラリ横のアクションメニュー（3点アイコン）をクリックし、「**Build for Development**」を選択します。
   * 再度アクションメニューをクリックし、「**Submit for Approval**」を選択します。
4. **Submitted**のセクションで実施する操作：
   * アクションメニューをクリックし、「**Build for Staging**」を選択します。
   * 再度アクションメニューをクリックし、「**Approve for Publishing**」を選択します。
5. **Approved**のセクションで実施する操作：
   * アクションメニューをクリックし、「**Build & Publish to Production**」を選択します。

</Accordion>

<div id="note-2" />

<div id="4-make-sure-the-sdk-is-working" />

## 2. SDKが正しく動作していることを確認する

インストール後、ブラウザのデベロッパーツールでネットワークリクエストを確認し、SDKが正常にリクエストを送信していることを検証してください。

[<Image alt="DevTools screenshot" src="https://files.readme.io/a1bb1f22e9d30059830239e7a4d13d7cde106a3363502cb9e8a054d6e8d65dff-43492318562833.png" width="1015px" />](https://files.readme.io/a1bb1f22e9d30059830239e7a4d13d7cde106a3363502cb9e8a054d6e8d65dff-43492318562833.png)

**SDKが正しく動作していることを確認するには、以下の手順を実施します：**

1. Webサイトを開いてください。
2. デベロッパーコンソールを開きます。
3. （A）「**Network**」タブを開きます。
4. ページを再読み込みします。
5. （B）`appsflyer` でフィルタリングします。以下2種類のリクエストが表示される場合があります：
   * **SDK loader** — リクエストURLが `https://websdk.appsflyersdk.com` で始まります。これは、SDKスクリプトが正しく読み込まれていることを示します。
   * **Event data** — リクエストURLが `https://wa.appsflyer.com/events` で始まります。これは、SDKがイベントデータをAppsFlyerへ送信していることを示します。
6. （C）**events**メッセージ（`wa.appsflyer.com` のコール）を選択します。
7. 「Headers」タブで、(D)以下を確認します。
   * Request URLが `https://wa.appsflyer.com/events?site-id=` で始まっていること
   * `site_id` クエリパラメータが `WEB_SDK_KEY` と一致していること
   * ステータスコードが 200 であること
8. `site_id` が、AppsFlyer > 上部メニュー > My Apps に表示されている `WEB_SDK_KEY` と一致していることを確認します。
9. SDKが1回だけ読み込まれていることを確認してください。SDKが複数回読み込まれると、正常に動作しなくなる可能性があります。

<div id="important" />

<div id="5-set-and-record-events" />

## 3. イベントの設定・記録

Web SDKの初期化後は、単なる訪問計測から、特定のユーザーアクションの計測へ移行できます。このセクションでは、購入や会員登録などのカスタムイベントを定義・記録する方法を、**ネイティブJavaScript**または**Google Tag Manager**を用いて説明します。

<div id="set-events" />

<Accordion title="イベントを設定する">

イベントはWeb計測の基本要素であり、ビジネス上価値のある特定のユーザーアクションを表します。これらのユーザー行動を計測するには、各イベントのロジックとパラメータを定義し、収益情報やカスタムメタデータなどの適切なイベントパラメータをAppsFlyerプラットフォームへ送信する必要があります。

**購入イベントと関連収益を含むイベント例**

```javascript
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name"}});
```

<div id="web-sdk-event-parameters-table" />

<Accordion title="Web SDKのイベントパラメータ一覧">

| パラメーター名 | 必須 | 説明 |
| --- | --- | --- |
| `eventType` | 必須 | イベントタイプ。形式：String常に `EVENT` を設定してください。例： `eventType: "EVENT"` |
| `eventName` | 必須 | イベント名。形式：String例：Purchase, Subscription |
| `eventRevenue` | 任意 | コンバージョンイベントに紐づく収益。形式：Float |
| `eventRevenueCurrency` | 任意 | 収益通貨。3文字の ISO 4217 通貨コード。デフォルト：USD形式：String |
| `eventValue` | 任意 | イベント内容を表すイベントパラメータの一覧。SKUや商品単価など、詳細なイベント情報を送信する際に使用します。形式：JSON例：`{"sku": "ABC123", "color": "blue", "unit_price": 3.99, "currency": "USD"}` （制限：文字数は1000文字まで。超過した場合は切り捨てられます。） |

</Accordion>

</Accordion>

<div id="record-events-on-page-load" />

<Accordion title="ページ読み込み時にイベントを記録する">

これは、**Thank You**ページや確認ページなど、リダイレクトで完了するコンバージョンを計測する際の一般的な実装方法です。

このトリガーは、**ネイティブJavaScript**でwindowロードメソッドを追加する方法、または**Google Tag Manager**でページビュートリガーを設定する方法のいずれかで実装できます。

> ❗️ **注意**
>
> 以下のコード例はあくまで参考例です。**そのまま使用せず**、必ずご利用サイトの構成に合わせて調整してください。

<div id="example-record-event-via-af-web-sdk" />

<Accordion title="例：AF Web SDKを使用してイベントを記録する">

この方法は、ニュースレター登録後のThank Youページなど、リダイレクトを伴うコンバージョン計測に適しています。

**ユースケース：** ユーザーがニュースレター登録を完了し、確認ページへリダイレクトされ、確認ページが表示されたタイミングでsubscriptionイベントを記録したい場合。

**ネイティブページロードの例：**

```javascript
window.onload = function(){
  AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion'}, eventName: 'subscription'});
}
```

**動作概要：**

1. ページが必要なコンテンツを読み込みます。
2. windowが完全に読み込まれると（`window.onload`）、スクリプトが自動的に `AF()` メソッドを呼び出します。
3. **subscription**イベントと関連メタデータ（categoryおよびlabel）が、AppsFlyerへ直接送信されます。

</Accordion>

<div id="example-record-event-via-gtm" />

<Accordion title="例：GTM経由でイベントを記録する">

この方法では、「Thank You」ページが読み込まれたタイミングでタグを発火させることで、ニュースレター登録などの完了済みコンバージョンを記録します。

<div id="1-set-up-a-thank-you-page" />

#### 1. Thank Youページを設定する

以下のHTML構造ではGTMを読み込み、GTM経由でWeb SDKを読み込みます。また、関数や`localStorage`を使って、GTMで利用できるデータを用意する方法も示しています。

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

<div id="important-1" />

<div id="2-configure-the-gtm-tag" />

#### 2. GTMタグを設定する

1. GTMで新しいタグを作成し、タグタイプとして「**Custom HTML**」を選択します。
2. その際、わかりやすい名前を付けてください。（例：「AF Subscription Event」など）
3. HTMLのテキストエリアに、以下のスクリプトを貼り付けます。

   ```javascript
   AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'});
   ```
4. 「**Advanced Settings**」>「**Tag Sequencing**」を展開し、メインのWeb SDK初期化タグの後に発火するよう設定されていることを確認してください。
5. このタグが「Thank You」ページの**Page View**で発火するよう、トリガーを設定してください。

</Accordion>

</Accordion>

<div id="record-events-on-user-interaction" />

<Accordion title="ユーザー操作時にイベントを記録する">

ページを再読み込みせずに発生するアクション（ボタンクリック、ダウンロード、カート追加など）を計測する場合に使用します。

通常、このような操作は、**ネイティブHTML要素**にクリックリスナーを紐づける方法、または**Google Tag Manager**の変数を使って特定の要素IDやCSSセレクタを識別・計測する方法で処理します。

> ❗️ **注意**
>
> 以下のコード例はあくまで参考例です。**そのまま使用せず**、必ずご利用サイトの構成に合わせて調整してください。

<div id="example-record-event-via-af-web-sdk-interaction" />

<Accordion title="例：AF Web SDKを使用してイベントを記録する">

このメソッドは、<strong>［チェックアウト］</strong>ボタンや<strong>［ダウンロード］</strong>ボタンのクリックなど、ユーザーがページ上で行う特定のアクションを追跡する場合に使用します。

**ユースケース：** ECサイトを運営しており、ユーザーがショッピングカート内の**Checkout**ボタンをクリックした瞬間に、**checkout**イベントを取得したい場合。

**ネイティブユーザー操作の例：**

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

**動作概要：**

1. ページが読み込まれると、スクリプトは `checkout` というIDを持つ要素に**クリック**イベントリスナーを設定します。
2. ユーザーがボタンをクリックすると、コールバック関数が実行されます。
3. この関数では、`localStorage`などから関連データを取得し、`AF()` メソッドに渡すことができます。
4. その後、SDKが**checkout**イベントをAppsFlyerプラットフォームへ送信します。

</Accordion>

<div id="example-record-event-via-gtm-interaction" />

<Accordion title="例：GTM経由でイベントを記録する">

この方法では、GTMの組み込み変数とトリガーを使用して、**Checkout**ボタンのクリックなどの特定アクションを取得します。

<div id="1-set-up-a-checkout-page" />

#### 1. checkoutページの設定

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

<div id="2-configure-gtm-variables-and-triggers" />

#### 2. GTM変数とトリガーの設定

1. <span class="af-ol-a"></span>GTMで「**Variables**」>「**Configure**」をクリックし、Built-In Variablesリストで「**Click Element**」を有効にします。
2. 新しいユーザー定義変数(タイプ:**すべての要素**).
3. 新しい**トリガー**を作成し、以下のとおり設定します：
   * トリガータイプ:**クリック - 全要素**.
   * このトリガーは以下で発射されます:**いくつかのキック**.
   * 条件：**Click Element**が CSS Selector `#checkout`と一致した場合

<div id="3-create-the-interaction-tag" />

#### 3. インタラクションタグを作成する

1. <span class="af-ol-a"></span>checkoutアクション用に、新しい**Custom HTML**タグを作成します。
2. 以下のインタラクションスクリプトを貼り付けます。

   ```html
   <script>
     AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
   </script>
   ```
3. 前の手順で作成した「Checkout Click」トリガーを割り当てます。

</Accordion>

</Accordion>

<div id="event-implementation-best-practices" />

<Accordion title="イベント実装のベストプラクティス">

データの正確性と正常な送信を担保するため、以下の技術要件を確認してください。

* **読み込み順序：** イベント呼び出しが行われる前に、Web SDKの関数タグがページスコープ内で完全に読み込まれていることを確認してください。
* **データ形式：** イベント値には特殊文字を含めないでください。たとえば、収益には通貨記号を含めず、数値で指定してください（`$10.50` ではなく `10.50` を使用します）。
* **文字数制限：**`event_value` の文字列は簡潔にしてください。4000文字を超える値は切り捨てられます。

</Accordion>

<div id="6-set-customer-user-id" />

## 4. カスタマーユーザーIDの設定

イベント計測の実装後は、`setCustomerUserId` を使用して永続的なユーザーIDを設定します。これにより、Web上のアクティビティを他のプラットフォーム（モバイル、PC、CTV）と紐づけ、プラットフォームをまたいだユーザージャーニーを統合的に把握できます。

**重要なルール**

* **一貫性：** モバイルアプリ実装で使用しているCUIDと同じ値を使用してください（<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk">iOS</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-android-sdk#setting-the-customer-user-id">Android</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id">Unity</Anchor>のモバイル向け `setCustomerUserId` を参照してください）。
* **設定タイミング：** CUIDは、ログイン後や新規登録後など、任意のタイミングで送信できます。CUIDを取得でき次第、可能な限り早い段階で設定してください。多くの場合、ユーザーがログインまたは新規登録によって自身を識別するまで、CUIDを設定することはできません。
* **シンタックス：** 値は文字列として送信してください（引用符で囲みます）。**例：** `AF('pba', 'setCustomerUserId', '663274')`
* **プライバシー：** メールアドレスや電話番号など、個人を特定できる情報（PII）は含めないでください。

<div id="example-setting-cuid-after-signup-native" />

<Accordion title="例：サインアップ後にCUIDを設定する（ネイティブ）">

これらの例で提供されているコードは参照専用です。このコードをそのまま使用しないでください。このコードの使用方法が不明な場合は、Web開発者に相談してください。

前提条件：イベント送信前にWeb SDKがページ上で読み込まれていること。SDKを再度読み込まないでください。

ユーザーシナリオ：

* ユーザーがWebサイトでサインアップします。
* Webサイト側のコードがユーザー情報を取得し、サーバーへ送信します。
* サーバーがユーザーに対して一意のCUIDを生成します。
* サインアップ後のThank Youページで、新しいCUIDをサーバーに問い合わせます。
* サーバーからのレスポンスを使用し、Web SDKの `setCustomerUserId()` メソッドでAppsFlyerのCUIDを設定します。

<div id="a-sign-up-form-example" />

#### サインアップフォームの例

以下は、シンプルなサインアップフォームのコード例です。フォーム送信時にメールアドレスを `localStorage` に保存します。ユーザーがThank Youページに到達すると、そのメールアドレスがサーバーへ送信され、該当メールアドレスに対応する一意のCUIDを取得します。

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

<div id="a-thank-you-page-example" />

#### Thank Youページの例

このコードではFetch APIを使用します。ユーザーが入力したメールアドレスをサーバーへ送信します。サインアップ時にサーバー側で一意のCUIDを持つユーザーが作成される前提で、メールアドレスをサーバーへ送信すると、一意のCUIDが返されます。サーバーから返された一意のCUIDが、`setCustomerUserId` メソッドに渡される値になります。

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

<Accordion title="例：サインアップ後にCUIDを設定する（Google Tag Manager）">

1. サインアップページを設定します。

   以下のコード例は、シンプルなサインアップフォームです。フォーム送信時にメールアドレスを `localStorage` に保存します。ユーザーがThank Youページに到達すると、そのメールアドレスがサーバーへ送信され、該当メールアドレスに対応する一意のCUIDを取得します。

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
2. サインアップしたユーザー向けのThank Youページを設定します。以下のコードは、GTMトリガーを含むThank Youページの例です。サインアップフォームでユーザーが入力したメールアドレスをサーバーへ送信します。サインアップ時にサーバー側で一意のCUIDを持つユーザーが作成される前提で、メールアドレスをサーバーへ送信すると、一意のCUIDが返されます。サーバーから返された一意のCUIDは、`setCustomerUserId()` メソッドを使用して送信されます。

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
3. Thank Youページの読み込み後にサブスクリプションをアトリビューションするため、新しいタグを追加します。

   [![](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
4. タグにわかりやすい名前を付け、タグタイプとして「**Custom HTML**」を選択します。

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
5. テキストエリア下部の「**Advanced Settings**」を展開し、続いて「**Tag Sequencing**」を開きます。タグの実行後にコンバージョンが発火するよう設定されていることを確認してください。

   [![](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. コンバージョンタグをいつ発火させるかを指定するため、コンバージョンタグにトリガーを設定します（以下の例では、「Thank you」ページの読み込み時に発火します）。

   [![](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

</Accordion>

<div id="7-manage-privacy" />

## 5. プライバシーの管理

イベント計測の実装後は、組織や地域の基準に準拠するため、特定のセキュリティ・プライバシー制御を適用する必要がある場合があります。

<div id="opt-in-or-opt-out-of-sending-events" />

<Accordion title="イベント送信をオプトイン／オプトアウトする">

計測は以下2つの方法で制御できます。

<div id="note-3" />

<div id="sdk-initial-state-setting-in-the-snippet" />

#### SDKの初期状態設定（スニペット内）

Webページ初回読み込み時に、SDKがイベント送信を開始するか、明示的な指示があるまで待機するかを定義します。この設定はWebスニペット内で指定します。

* イベント送信を有効化：`{pba: {webAppId: "...", measurementStatus:true}}`
* イベント送信を無効化：`{pba: {webAppId: "...", measurementStatus:false}}`

> 📘 **注意**
>
> `measurementStatus` が空、または `NULL` の場合、AppsFlyerは `measurementStatus:true` として扱います。

<div id="explicit-control" />

#### 明示的な制御

明示的な制御は初期状態設定より優先され、永続的なファーストパーティCookieを使用します：

* Webサイトドメイン上に設定されます。
* Cookieの有効期限は、Web SDKまたはブラウザ設定に従います。
* 常にブラウザのCookie設定の影響を受けます。

**コマンド**

* イベント送信を開始する（オプトイン）：`window.AF_SDK.PLUGINS.PBA.enableMeasurement()`
* イベント送信を停止する（オプトアウト）：`window.AF_SDK.PLUGINS.PBA.disableMeasurement()`

</Accordion>

<div id="secure-and-filter-data" />

<Accordion title="データを安全に管理・フィルタリングする">

Webサイトで厳格なセキュリティ要件やデータプライバシー要件が求められる場合は、以下の仕組みを使用して、Web SDKが環境やデータとどのように連携するかを制御できます。

<div id="content-security-policy-csp" />

#### コンテンツ・セキュリティ・ポリシー（CSP）

WebサイトでCSPによるJavaScript保護を適用している場合、Web SDKはCSP設定および手順2で選択したスニペットに応じて、2種類の方法をサポートします。

* **CSPで self を使用する場合**：`script-src` の許可リストに `https://websdk.appsflyersdk.com` を追加してください。これはスタンダードWeb SDKおよびアドバンスSDK検証の両方で利用できます。
* **CSPでnonceを使用する場合**：ポリシーで `script-src 'nonce-...'` を使用している場合は、以下のアドバンスSDK検証向けのnonce対応版スニペットを使用してください。これにより、検証プロセスで必要となる3つのscriptタグすべてにnonceが引き継がれます。`{{CSP_NONCE}}` を、サーバー側でリクエストごとに生成するnonce値へ置き換えてください。

以下の表は、nonce対応版スニペットと互換性のあるCSPポリシーを示しています。

| ポリシー | 動作可否 | 備考 |
| --- | --- | --- |
| `script-src 'self'` | 不可 | 外部CDNオリジンが許可されず、インラインスクリプトもブロックされます。 |
| `script-src 'self' https://websdk.appsflyersdk.com` | 部分的 | ローダーおよびSDKは許可されますが、インライン設定スクリプトはブロックされます。 |
| `script-src 'nonce-...' https://websdk.appsflyersdk.com` | 可能 | nonceによってインラインスクリプトとローダーが許可され、SDKタグにもnonceが引き継がれます。 |
| `script-src 'nonce-...' 'strict-dynamic'` | 可能 (推奨) | nonceによってインラインスクリプトとローダーが許可され、`strict-dynamic` により動的に挿入されたSDKタグにも信頼が引き継がれます。許可リストへのCDNオリジン追加は不要です。 |

CSPポリシーの互換性

<div id="advanced-sdk-verification-with-csp-nonce-snippets" />

#### アドバンスSDK検証 + CSP nonce対応スニペット

<div id="nonce-without-smart-banners" />

<Accordion title="Smart Bannersを使用しない場合">

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

<Accordion title="Smart Bannersを使用する場合">

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

<div id="discard-query-parameters" />

#### クエリパラメータを破棄する

URLクエリパラメータに機密情報が含まれる場合、AppsFlyerに対してクエリパラメータ（URL、referrer、`header_referer`）を破棄するよう指示できます。

* **すべて**のクエリパラメータを破棄する場合：`af_url=true`を追加
* **特定の**パラメータのみを破棄する場合：`af_url_mask=param`を使用（複数のパラメータを指定する場合は`;`で区切る)

例：

* 元のURL：`param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`
* 結果：`param1=value1&af_url_mask=param2;param3`

</Accordion>

<div id="web-sdk-cookies-reference" />

## Web SDK Cookieリファレンス

Web SDKは、以下のCookieを設定または使用します。

| Cookie名 | ドメイン | 有効期間 | 使用タイミング | 詳細 |
| --- | --- | --- | --- | --- |
| afUserId | お客様のWebサイトのドメイン | 395日 | 非AMP（Accelerated Mobile Pages）環境 | Webページの読み込みおよびナビゲーションイベントにおいて、ユーザー識別に使用されます。 |
| AF\_SYNC | お客様のWebサイトのドメイン | 1週間 | 非AMP（Accelerated Mobile Pages）環境 | 最終的なユーザー識別子が設定済みであることを示します。サイトの読み込み時間短縮に使用されます。 |
| af\_id | <Anchor target="_blank" href="http://appsflyer.com/">appsflyer.com</Anchor> | 395日 | サードパーティCookieが許可されている非AMP環境 | アプリ起動およびナビゲーションイベントにおいて、ユーザー識別に使用されます。 |
| af\_id | <Anchor target="_blank" href="http://onelink.me/">onelink.me</Anchor> | 395日 | サードパーティCookieが許可されている非AMP環境 | Link BannerやOneLink経由のエンゲージメント、またはその両方を、アプリ起動イベントへ紐づけます。 |
| amp-afUserid | AMP CDNまたはお客様のWebサイトのドメイン | 1年 | Accelerated Mobile Pages |  |
| AF\_DEFAULT\_MEASUREMENT\_STATUS | お客様のWebサイトのドメイン | 395日 | 非AMP（Accelerated Mobile Pages）環境 | 同意状態を保存します。ユーザーが同意するまでSDKの動作を停止します。デフォルトでは設定されません。<Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#sending-events-optinoptout">同意管理</Anchor>（consent gating）を設定している場合のみ使用されます。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01KGJCGCPZDJ446QHW80H9Z4C3=%E6%A6%82%E8%A6%81 step-1-obtain-your-keys=1-%E3%82%AD%E3%83%BC%E3%81%AE%E5%8F%96%E5%BE%97 h_01KP11XJV8B56W7FK2KAAFH0NE=1-%E3%82%AD%E3%83%BC%E3%81%AE%E5%8F%96%E5%BE%97 step-2-select-a-code-snippet=2-%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E3%81%AE%E9%81%B8%E6%8A%9E h_01KP11XJV8RDV378GMFF0DVZ8V=2-%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E3%81%AE%E9%81%B8%E6%8A%9E h_01KP3CJBZWJF8X46W2BBCS9ZVX=%E9%87%8D%E8%A6%81 standard=%E3%82%B9%E3%82%BF%E3%83%B3%E3%83%80%E3%83%BC%E3%83%89web-sdk h_01KP11XJV8MN64YV17D1M0T5B9=%E3%82%B9%E3%82%BF%E3%83%B3%E3%83%80%E3%83%BC%E3%83%89web-sdk h_01KP3CJBZWK17M58W9M2EP8VC3=standard-without-smart-banners h_01KP3CJBZWKW1K9P9V1XGYM5ED=standard-with-smart-banners advanced-sdk-verification=%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9sdk%E6%A4%9C%E8%A8%BC h_01KP11XJV8ZGF4SDXJH6FKX18E=%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9sdk%E6%A4%9C%E8%A8%BC h_01KP3CJBZWP7HDJ0GE2DF3TTE3=advanced-verification-without-smart-banners h_01KP3CJBZWJWS9H0XVHQFF758B=advanced-verification-with-smart-banners step-3-deploy-the-snippet=3-%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E3%81%AE%E3%83%87%E3%83%97%E3%83%AD%E3%82%A4 h_01KP11XJV8JQ5S2BBS18RV2H2R=3-%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E3%81%AE%E3%83%87%E3%83%97%E3%83%AD%E3%82%A4 h_01KP3CJBZWSKRZBRB66419E3TR=option-a-add-directly-to-your-website h_01KP3CJBZW1PE1VNCV6MSNWT8Q=option-b-deploy-via-google-tag-manager h_01KP3CJBZWWNXX6N5DBJKKGN6M=%E6%B3%A8%E6%84%8F h_01KP3CJBZWF4SW63KA6XCQ3BBD=option-c-deploy-via-adobe-launch-tag-manager create-a-property-in-adobe-experience-cloud=adobe-experience-cloud%E3%81%A7%E3%83%97%E3%83%AD%E3%83%91%E3%83%86%E3%82%A3%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B h_01KP11XJV9RWY4TTWACW69YGJH=adobe-experience-cloud%E3%81%A7%E3%83%97%E3%83%AD%E3%83%91%E3%83%86%E3%82%A3%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B add-the-snippet-to-the-adobe-launch-property=adobe-launch%E3%83%97%E3%83%AD%E3%83%91%E3%83%86%E3%82%A3%E3%81%AB%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B h_01KP11XJV9ZHMP9M85S3KG0V6R=adobe-launch%E3%83%97%E3%83%AD%E3%83%91%E3%83%86%E3%82%A3%E3%81%AB%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B add-the-adobe-launch-tag-to-the-website=adobe-launch%E3%82%BF%E3%82%B0%E3%82%92web%E3%82%B5%E3%82%A4%E3%83%88%E3%81%AB%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B h_01KP11XJVBV5J9E0HV5DM9HS7B=adobe-launch%E3%82%BF%E3%82%B0%E3%82%92web%E3%82%B5%E3%82%A4%E3%83%88%E3%81%AB%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B publish-the-adobe-launch-environment=adobe-launch%E7%92%B0%E5%A2%83%E3%82%92%E5%85%AC%E9%96%8B%E3%81%99%E3%82%8B h_01KP11XJVB0Y4RCBS9QCFBAKRD=adobe-launch%E7%92%B0%E5%A2%83%E3%82%92%E5%85%AC%E9%96%8B%E3%81%99%E3%82%8B 2-make-sure-the-sdk-is-working=2-sdk%E3%81%8C%E6%AD%A3%E3%81%97%E3%81%8F%E5%8B%95%E4%BD%9C%E3%81%97%E3%81%A6%E3%81%84%E3%82%8B%E3%81%93%E3%81%A8%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B h_01KGJCGCPZ38XZAY8SXB48YWBD=2-sdk%E3%81%8C%E6%AD%A3%E3%81%97%E3%81%8F%E5%8B%95%E4%BD%9C%E3%81%97%E3%81%A6%E3%81%84%E3%82%8B%E3%81%93%E3%81%A8%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B 3-set-and-record-events=3-%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A%E8%A8%98%E9%8C%B2 h_01KGJCGCPZMPX1FH58MVGM9VQS=3-%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A%E8%A8%98%E9%8C%B2 h_01KP3CJBZXQRMCG9CCH7N1RQ7Y=set-events h_01KP3CJBZXV66CCP4N0482DG1N=web-sdk-event-parameters-table h_01KP3CJBZXEA5SN763P1ZX8EH3=record-events-on-page-load h_01KP3CJBZXHTGFHR9D4KM6S6GH=%E6%B3%A8%E6%84%8F-2 h_01KP3CJBZXB328CABH2QCRXTHX=example-record-event-via-af-web-sdk h_01KP3CJBZXM3WK0JYB6S8P6SMQ=example-record-event-via-gtm 1-set-up-a-thank-you-page=1-thank-you%E3%83%9A%E3%83%BC%E3%82%B8%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01KGJCGCPZQDP9KVBSE1Z1GT48=1-thank-you%E3%83%9A%E3%83%BC%E3%82%B8%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B 2-configure-the-gtm-tag=2-gtm%E3%82%BF%E3%82%B0%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01KGJCGCPZ2YVRY6VYJ0BTC14N=2-gtm%E3%82%BF%E3%82%B0%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01KP3CJBZXZ2F32FJG9GENBPWW=record-events-on-user-interaction h_01KP3CJBZX6763D546AK5AS1TN=%E6%B3%A8%E6%84%8F-2 h_01KP3CJBZXD6MPTQ0KCPMTM1Y9=example-record-event-via-af-web-sdk-interaction h_01KP3CJBZX53G1HABG3TKN2X6S=example-record-event-via-gtm-interaction 1-set-up-a-checkout-page=1-checkout%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KGJCGCQ0858AAJC82Y2G0GNP=1-checkout%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E8%A8%AD%E5%AE%9A 2-configure-gtm-variables-and-triggers=2-gtm%E5%A4%89%E6%95%B0%E3%81%A8%E3%83%88%E3%83%AA%E3%82%AC%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KGJCGCQ0GGYDQBP9CJNM9AXQ=2-gtm%E5%A4%89%E6%95%B0%E3%81%A8%E3%83%88%E3%83%AA%E3%82%AC%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A 3-create-the-interaction-tag=3-%E3%82%A4%E3%83%B3%E3%82%BF%E3%83%A9%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%BF%E3%82%B0%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B h_01KGJCGCQ0EV557QF3CGZ6YB4X=3-%E3%82%A4%E3%83%B3%E3%82%BF%E3%83%A9%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%BF%E3%82%B0%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B h_01KP3CJBZX5K72JC1NK1P1S1S8=event-implementation-best-practices 4-set-customer-user-id=4-%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%9E%E3%83%BC%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BCid%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KGJCGCQ0RNBW7V5T4PXVXQW1=4-%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%9E%E3%83%BC%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BCid%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KP3CJBZXXKM662TJP0M5BJAR=example-setting-cuid-after-signup-native a-sign-up-form-example=%E3%82%B5%E3%82%A4%E3%83%B3%E3%82%A2%E3%83%83%E3%83%97%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%AE%E4%BE%8B h_01KGJCGCQ0M0ESXFMK45PJ3SX9=%E3%82%B5%E3%82%A4%E3%83%B3%E3%82%A2%E3%83%83%E3%83%97%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%AE%E4%BE%8B a-thank-you-page-example=thank-you%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BE%8B h_01KGJCGCQ0FMKFKM2SWV2794T5=thank-you%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BE%8B h_01KP3CJBZX4BXQSGN70TRJDNX1=example-setting-cuid-after-signup-google-tag-manager 5-manage-privacy=5-%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%81%AE%E7%AE%A1%E7%90%86 h_01KGJCGCQ01PQWT44ZWE329DWX=5-%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%81%AE%E7%AE%A1%E7%90%86 h_01KP3CJBZXVR16943T16XT82G5=opt-in-or-opt-out-of-sending-events sdk-initial-state-setting-in-the-snippet=sdk%E3%81%AE%E5%88%9D%E6%9C%9F%E7%8A%B6%E6%85%8B%E8%A8%AD%E5%AE%9A%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E5%86%85 h_01KGJCGCQ0AQM3Y9NNCJF2XP9G=sdk%E3%81%AE%E5%88%9D%E6%9C%9F%E7%8A%B6%E6%85%8B%E8%A8%AD%E5%AE%9A%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E5%86%85 h_01KP3CJBZX8V6TGE5NVR6SW49G=%E6%B3%A8%E6%84%8F-3 explicit-control=%E6%98%8E%E7%A4%BA%E7%9A%84%E3%81%AA%E5%88%B6%E5%BE%A1 h_01KGJCGCQ07KKYGN5JZF41A6W7=%E6%98%8E%E7%A4%BA%E7%9A%84%E3%81%AA%E5%88%B6%E5%BE%A1 h_01KP3CJBZXZBFCXD1E38JKWW6H=secure-and-filter-data content-security-policy-csp=%E3%82%B3%E3%83%B3%E3%83%86%E3%83%B3%E3%83%84%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E3%83%9D%E3%83%AA%E3%82%B7%E3%83%BCcsp h_01KGJCGCQ0QB7NK6YNZT5XJVJY=%E3%82%B3%E3%83%B3%E3%83%86%E3%83%B3%E3%83%84%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E3%83%9D%E3%83%AA%E3%82%B7%E3%83%BCcsp advanced-sdk-verification-with-csp-nonce-snippets=%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9sdk%E6%A4%9C%E8%A8%BC--csp-nonce%E5%AF%BE%E5%BF%9C%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88 h_01KP11XJV88YB2NSBZJTX9K7ZQ=%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9sdk%E6%A4%9C%E8%A8%BC--csp-nonce%E5%AF%BE%E5%BF%9C%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88 h_01KP3CJBZXQ4D538H0T7N9FZ6Z=nonce-without-smart-banners h_01KP3CJBZX8K3WK6RHQMB029VN=nonce-with-smart-banners discard-query-parameters=%E3%82%AF%E3%82%A8%E3%83%AA%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%82%92%E7%A0%B4%E6%A3%84%E3%81%99%E3%82%8B h_01KGJCGCQ010K4RMFMGHD5NDC3=%E3%82%AF%E3%82%A8%E3%83%AA%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%82%92%E7%A0%B4%E6%A3%84%E3%81%99%E3%82%8B web-sdk-cookies-reference=web-sdk-cookie%E3%83%AA%E3%83%95%E3%82%A1%E3%83%AC%E3%83%B3%E3%82%B9 h_01KGJCGCQ03A1H7NA5ZGPSGKP3=web-sdk-cookie%E3%83%AA%E3%83%95%E3%82%A1%E3%83%AC%E3%83%B3%E3%82%B9" />
