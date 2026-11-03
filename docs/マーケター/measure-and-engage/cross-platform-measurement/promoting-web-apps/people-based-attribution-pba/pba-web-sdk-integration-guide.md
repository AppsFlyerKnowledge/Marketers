---
title: PBA Web SDK 実装ガイド
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
  edited_at: '2026-10-14T09:29:31Z'
  id: 360001610038
  locale: ja
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ja/articles/360001610038
---
> **概要：概要**：Web SDKを使用してAppsFlyerをWebサイトに実装し、サイトトラフィック、イベント、コンバージョン、収益などを計測しましょう。

[![5107_Infographic_Web_S2S_759x270_option1.jpg](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)

## Web SDKの利用・実装ガイド

* Web SDK JavaScriptタグは、以下の特徴を持ちます：
  * 複数のプラットフォームをまたいだユーザージャーニーを分析する、People-Based Attribution（PBA）ソリューションの一部です。
  * Webサイト上でのユーザーの訪問および行動をAppsFlyerプラットフォームに送信します。
  * プログラミング不要で導入できるWebサイト用プラグインモジュールです。Webサイト訪問者のOSやブラウザに依存しません。
  * サイズ：40 - 60KB
* モバイルアプリとWeb環境をまたいだユーザー行動を記録・紐付けるために、AppsFlyerモバイルSDKとあわせてWeb SDKを実装してください。
* Webサイト外で発生するイベントは、<Anchor target="_blank" href="/marketers/ja/docs/web-server-to-server-events-api-for-pba-web-s2s">Web server-to-server events API</Anchor>（Web S2S）を使用して記録できます。

## コードスニペットの選択

統合タイプとセキュリティ要件に一致するスニペットを選択してください。以下の項目が選択可能です：

* [スタンダードWeb SDK](#スタンダードweb-sdk)：標準的な実装です。
* [アドバンスSDK検証](#アドバンスsdk検証)：Web Web SDKにサプライチェーン保護を追加する強化版インテグレーションです。CDNの侵害、DNSハイジャック、中間者攻撃（MITM）に対する追加のセキュリティレイヤーを提供します。

> 🚧 **【重要】**
>
> スタンダードWeb SDKからアドバンスSDK検証へ移行する場合は、既存のスニペットを新しいものに置き換えてください。既存のスニペットの上に新しいスニペットを追加しないでください。

### スタンダードWeb SDK

このスニペットを使用して、スタンダードWeb SDK連携を導入します。SDKを読み込みたいすべてのページのタグの上部付近に貼り付けてください。

<div id="standard-without-smart-banners" />

<Accordion title="Smart Banners なし">

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

<Accordion title="Smart Banners あり">

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

### アドバンスSDK検証

アドバンスSDK検証は、Web SDKにサプライチェーン保護を追加する仕組みです。これにより、ユーザーのブラウザ上で実行されるコードが、AppsFlyerによって提供されたものと完全に一致していることが保証されます。SDKのソースコード自体はスタンダードインテグレーションと同一であり、異なるのは配信および検証の仕組みのみです。

アドバンスSDK検証の特徴は以下の通りです：

* CDNの侵害、DNSハイジャック、中間者攻撃（MITM）に対する追加のセキュリティレイヤーを提供
* SDKの読み込み時間が約250ms増加

アドバンスSDK検証は任意であり、スタンダードインテグレーションも引き続き完全にサポートされています。標準インテグレーションはサードパーティ分析ピクセルにおける一般的な実装方法であり、アドバンスSDK検証はそれに対して追加の保護レイヤーを提供します。

なお、ウェブサイトでnonceを用いたContent Security Policy（CSP）を適用している場合は、「プライバシー管理」セクションの[CSPに関する項目](#コンテンツセキュリティポリシーcsp)をご参照ください。

<div id="advanced-verification-without-smart-banners" />

<Accordion title="Smart Banners なし">

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

<Accordion title="Smart Banners あり">

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

## Web SDKのWebサイトへの実装

<div id="installation-and-integration" />

<Accordion title="インストールと実装">

#### 考慮事項と必要なアクション

| 実装チェックリスト |
| --- |
| 訪問とイベントを記録できるようにするため、Web SDKはWebサイト内のすべてのページにインストールする必要があります。 |
| [上記で選択した](#コードスニペットの選択)スニペットコードを、ページスコープ内でできるだけ早く読み込まれるように配置してください。そのため、head タグのなるべく上部にコードを配置します。 |
| Googleタグマネージャー(GTM)を使用してSDKを実装する場合：<ul><li>SDKが1ページ読み込みにつき1回のみ読み込まれるようにしてください。</li><li><Anchor target="_blank" href="https://support.google.com/tagmanager/answer/2772421?hl=en">GTM の優先度設定</Anchor>を使用して、ページ読み込み時にできるだけ早くSDKが読み込まれるように設定してください。</li></ul> |
| Web SDKは、Smart Banners **あり**／**なし**のいずれでも実装できます。以降の該当セクションの手順に従ってください。 |
| 実装の必須要件<ul><li>サイト訪問の計測</li><li>イベントの計測</li><li>[カスタマーユーザーID](/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid)(CUID)の設定：CUIDがない場合は、代替案についてCSMに連絡してください。</li></ul><Anchor target="_blank" href="/marketers/ja/docs/test-pba-web-sdk-integration">テストツール</Anchor>を使用して実装を検証してください |

**はじめる前に**

* マーケターに<Anchor target="_blank" href="/marketers/ja/docs/pba-brand-bundles-and-settings">ブランドバンドル</Anchor>が作成済みであることを確認してください。
* 詳細なガイダンスについては、<Anchor target="_blank" href="/marketers/ja/docs/onboarding-guide-to-people-based-attribution">PBA 導入ガイド</Anchor>を参照してください。
* 注意：すでにstandalone Smart Banners web SDKを導入している場合は、それを削除し、Smart BannersとPeople-based Attributionの両方に対応するWeb SDKへ置き換えてください。standalone Web SDK for PBAを単純に追加するだけでは対応しないでください。

**以下を実施してください：**

* Web SDKのWeb Dev Keyを入手してください。  **注意：** これは、アプリのSDK実装時に使用するDev Keyとは異なります。
  * **Web Dev Key の取得方法：**
    1. AppsFlyerの管理画面上、上部メニューから**マイアプリ**タブを選択します。
    2. ［**ブランドバンドルを表示**］をクリックします。
    3. 必要な**Web Dev Keyをコピーしてください。(WEB\_DEV\_KEY)**
* Smart Bannersを実装する場合は、Smart Banner keyも取得します。
  * **Smart Banner Keyを取得するには：**
    1. AppsFlyer のサイドメニューから、**Engage**>**Web-to-app**>**Smart Banners**を選択してください。
    2. 必要な **Smart Banner Key** をコピーしてください。
* Webサイト上で head タグにスクリプトを追加する権限が必要です。
* Googleタグマネージャーを使用する場合は、ウェブサイトに統合する必要があります。

**以下のいずれかの方法でWeb SDKの実装を進めてください。**

<Tabs>
<Tab title="Native">

#### JavaScriptコードスニペット

以下のいずれかの方法を使用して、Web SDKを実装してください。

#### **Smart BannerなしでWeb SDKを実装するには：**

1. 以下の手順を、Webサイト上のすべてのページで繰り返してください。
2. 以下のコードスニペット内の `WEB_DEV_KEY` を、事前準備で取得したキーに置き換えてください。
3. [上記で選択した](#コードスニペットの選択)コードスニペットをウェブサイトのheadタグに貼り付けてください。head タグのなるべく上部に配置してください。

#### **Smart Bannerと一緒にWeb SDKを実装するには：**

1. ウェブサイトのすべてのページで以下の手順を繰り返してください。
2. [上記で選択した](#コードスニペットの選択)コードスニペット内で、`WEB_DEV_KEY`と`YOUR_BANNER_KEY`を前提条件で指定されたキーを使用して置き換えてください。
3. このコードスニペットをウェブサイトのheadタグに貼り付けてください。head タグのなるべく上部に配置してください。

</Tab>

<Tab title="Google Tag Manager">

**Googleタグマネージャー（GTM）でWeb SDKを実装するには：**

1. <Anchor target="_blank" href="https://developers.google.com/tag-manager/quickstart">Googleタグマネージャーに移動してください。</Anchor>
2. AppsFlyer Web SDK用に、新しいタグを作成してください。

   [![](https://files.readme.io/bd695bcbaf3983aac809cb7e1d63af0b89a08cea1751bbd8c2fc39863182fe7a-360002745245.png)](https://files.readme.io/bd695bcbaf3983aac809cb7e1d63af0b89a08cea1751bbd8c2fc39863182fe7a-360002745245.png)
3. **カスタム HTML** のタグタイプを選択してください。
4. タグに名前を付けます。
5. 次のいずれかを実行してください：
   * Smart Banner**無し**でWeb SDKを実装する場合：
     1. [上記で選択した](#コードスニペットの選択)コードスニペットを**タグ設定**ウィンドウに貼り付けてください。
     2. コード スニペット内の`WEB_DEV_KEY`を、事前準備で取得したキーに置き換えてください。
   * Web SDKをSmart Bannerと**一緒に**実装する場合：
     1. [上記で選択した](#コードスニペットの選択)コードスニペットを**タグ設定**ウィンドウに貼り付けてください。
     2. 以下のコードスニペット内の `WEB_DEV_KEY` と `YOUR_BANNER_KEY` を、事前準備で取得したキーに置き換えてください。
6. **保存**をクリックしてください。
7. 次のいずれかを実行してください：
   * **すべてのページにトリガーを追加するには：**
     1. [**トリガーの追加**] をクリックします。

        [![gtm-af-tag-sdk-trigger.png](https://files.readme.io/9cae70cdc376e57d3458fab80f8b9e57aa6981a3f3029c17d32e96b5f569fc28-360007722757.png)](https://files.readme.io/9cae70cdc376e57d3458fab80f8b9e57aa6981a3f3029c17d32e96b5f569fc28-360007722757.png)
     2. [**すべてのページ**] を選択してください。
     3. **保存**をクリックしてください。
     4. タグ名を入力し、**保存**をクリックしてください。  
        これで手順は完了です。
   * **特定のページにトリガーを追加するには：**
     1. ［**タグを保存**］ をクリックします。
     2. GTMのメイン画面で、**トリガーを選択し、**［**New**］（新規作成）をクリックしてください。
     3. ペンのアイコンをクリックしてください。
     4. **［Page View］**（ページビュー）のトリガータイプを選択してください。  
        [![PBAselectTrigger_us-en.jpg](https://files.readme.io/e62926fed956da9f3fcbf04f818858c69f07cbac892fafd839451c73d72a6741-360007811677.jpg)](https://files.readme.io/e62926fed956da9f3fcbf04f818858c69f07cbac892fafd839451c73d72a6741-360007811677.jpg)
     5. [**Some Page Views**]（一部ページビュー）を選択します。
     6. 必要に応じてページとトリガーの条件を設定してください。
     7. **保存**をクリックしてください。
     8. そのトリガーをAppsFlyer Web SDKタグに関連付けてください。設定方法：
        1. GTMのメインウィンドウで[タグ]を選択してください。
        2. 以前に作成したタグを選択してください。
        3. トリガーパネルで、ペンのアイコンをクリックしてください。
        4. 前に作成したページビュートリガーを選択してください。

           [![](https://files.readme.io/c4e9b2e4b4d3ce6b7377d419070be650e758eddcdf5603fa5f3c65560402f1d7-360002745305.png)](https://files.readme.io/c4e9b2e4b4d3ce6b7377d419070be650e758eddcdf5603fa5f3c65560402f1d7-360002745305.png)
        5. **保存**をクリックしてください。

</Tab>

<Tab title="Adobe Launch Tag Manager">

1. [Adobe Experience Cloudでプロパティを作成してください。](/docs/pba-web-sdk-integration-guide#create-a-property-in-adobe-experience-cloud)
2. [Adobe LaunchのプロパティにWeb SDKを追加してください。](/docs/pba-web-sdk-integration-guide#add-the-web-sdk-to-the-adobe-launch-property)
3. [Adobe LaunchのタグをWebサイトに追加してください。](/docs/pba-web-sdk-integration-guide#add-the-adobe-launch-tag-to-the-website)
4. [Adobe Launch環境を公開してください。](/docs/pba-web-sdk-integration-guide#publish-the-adobe-launch-environment)

<div id="create-a-property-in-adobe-experience-cloud" />

<Accordion title="Adobe Experience Cloudでプロパティを作成してください。">

![adobe_create_property.png](https://files.readme.io/1f97d619d5fdfe47b1dd1a2e17c0169e939c32bcda62580ba259d6e86f61d6c2-20260884824209.png)

1. **Adobe Experience Cloud** > **Launch** へ移動
2. [**Adobe Experience Cloud Launch**] の下にある [**Go to Launch**] をクリックします。
3. [**New Property**]（新しいプロパティ）をクリックします。
4. プロパティに名前を付けてください。
5. **Platform** の下にある、 **Web** を選択します。
6. ウェブサイトのドメインを入力してください。
7. **保存**をクリックしてください。

</Accordion>

<div id="add-the-web-sdk-to-the-adobe-launch-property" />

<Accordion title="Adobe LaunchのプロパティにWeb SDKを追加してください。">

<Image alt="web_property_rules.png" src="https://files.readme.io/5f592f3ce1f5b319c8f6f96a6235618d884a4faccb1387b1f22c1fd2ce662d15-360006168098.png" width="491px" />

1. **My web property** ページで、[**Rules**] タブを選択します。
2. ルールに名前を付けます。使用することを推奨し、 **Load web SDK** 。
3. [**IF**] セクションの**EVENTS** 下にある [**+Add**] をクリックします。
   * [**Event Type**] にある [**Core - DOM Ready**] を選択します
   * [**Keep Changes**]（変更を保存）をクリックします。
4. **THEN** セクションの **Actions**にある、**+Add** をクリックします。
   * [**Action Type**] > [**Custome Code**] をクリックします。
   * [**JavaScript**] > [**Open Editor**] を選択し、**&lt;script> タグなし**でWeb SDK スニペットを貼り付けます。
   * [**Keep Changes**]（変更を保存）をクリックして、コードエディターを閉じます。
5. **保存**をクリックしてください。

</Accordion>

<div id="add-the-adobe-launch-tag-to-the-website" />

<Accordion title="Adobe LaunchのタグをWebサイトに追加してください。">

[![adobe_tag.png](https://files.readme.io/4da5418fc3f2591d15fe68ea1d0451f2b393cb177ae4309d5d431259e2d4003f-small-20260884828049.png)](https://files.readme.io/4da5418fc3f2591d15fe68ea1d0451f2b393cb177ae4309d5d431259e2d4003f-small-20260884828049.png)

1. [**My web property**] ページで、[**Environments**] タブを選択します。
2. 公開する環境（開発または本番）を含む行を見つけます。
   * **INSTALL** ヘッダーに含まれる、関連する行のボックスアイコンをクリックします。これは通常、実稼働環境です。
   * **Adobe Launch** 環境の公開に関するセクションを参照してください。
3. **Web Install Instructions** のダイアログボックスにて、次の手順を行います。
   * スクリプトコードsnippetをコピーします。
   * ダイアログボックスを閉じます。
4. コードスニペットをWebサイトの &lt;head> タグの中に貼り付けます。

</Accordion>

<div id="publish-the-adobe-launch-environment" />

<Accordion title="Adobe Launch環境を公開してください。">

[![adobe_publishing_env.png](https://files.readme.io/863b7c81a9f90d774f7f4388a22db3420dca5c5db632efc6c0dc40783702f418-small-20260884829329.png)](https://files.readme.io/863b7c81a9f90d774f7f4388a22db3420dca5c5db632efc6c0dc40783702f418-small-20260884829329.png)

1. [**My web property**] ページで、[**Publishing**] タブに移動します。
2. [**Development**]セクションの、[**Add New Library**] をクリックします。
   * ライブラリに名前を付けて、環境を選択します。
   * [**RESOURCE CHANGES**] にある、[**Add a Resource**]（リソースの追加）をクリックします。
   * **Rules** > **Load web SDK** > **Latest** > **Select & Create a New Revision** をクリックします。
   * **保存**をクリックしてください。
3. [**Development**] セクションにて、次を実行します。
   * 新しく作成されたライブラリの横にあるアクションメニュー（3つのドット）をクリックし、[**Build for Developers**] を選択します。
   * アクションメニューをもう一度クリックし、[**Submit for Approval**] を選択します。
4. [**Submitted**] セクションにて、次を実行します。
   * アクションメニューをクリックし、[**Build for Staging**] を選択します。
   * アクションメニューをもう一度クリックし、[**Approve for Publishing**] を選択します。
5. [**Approved**] セクションにて、次を実行します。
   * アクションメニューをクリックし、[**Build & Publish to Production**] を選択します。
   * これでプロセスは完了です。

</Accordion>

ウェブサイトがモバイル端末で読み込まれると、アクティブなクリエイティブがバナーに表示されます。特定のページやユーザーアクションに応じてバナーを表示するには、<Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">Adobe Launchルール</Anchor>を参照してください。

</Tab>
</Tabs>

</Accordion>

<div id="ensure-that-the-sdk-is-working" />

<Accordion title="SDKの動作確認">

インストールしたら、AppsFlyer Web SDKが訪問者のブラウザーによって呼び出され、メッセージが送信されていることを確認してください。これは、ブラウザで報告されたメッセージネットワーク接続を調べることによって行います。

**SDKが読み込まれていることを確認するには：**

1. ウェブサイトに移動してください。
2. デベロッパーコンソールを開きます。

   ![WebSDK_us-en.jpg](https://files.readme.io/5550f0ee8c1a5852a983e6482cb0489696b669ffe5fade49d2308ee32f57201b-360009548497.jpg)
3. (A)［**Network**］ タブへ移動してください。
4. ページを更新（リロード）します。
5. (B) **wa.** appsflyer で絞り込みます。
6. (C) **events** メッセージを選択してください。
7. (D)ヘッダータブで、以下のことを確認してください。
   * **Request URL** が wa.appsflyer.com/events であること。
   * site\_id query parameter= `WEB_DEV_KEY`.
   * (E) **ステータスコードが200であること。**
8. site\_id の値が、ブランドバンドル設定の `WEB_DEV_KEY` の値と同じであることを確認してください。
   1. AppsFlyerの管理画面上では、サイドメニューから**設定** > **ブランドバンドル**を選択してください。
   2. [**Web dev key**] をクリックすると、キーがコピーされます。
   3. キーを任意の場所（新しいブラウザやノートパッド）に貼り付け、キーを表示します。
   4. site\_idと`WEB_DEV_KEY`が一致していることを確認してください。
9. SDKが一度だけ読み込まれるようにしてください。何度かSDKをロードすると、SDKの機能が停止する場合があります。

</Accordion>

<div id="sending-events-optinoptout" />

<Accordion title="オプトイン/オプトアウトのイベント送信">

![5578-VistiorPrivacyOptIn_us-en.png](https://files.readme.io/cd6cbcaeb7f831f4efe74a9a6c6b20d5095602e7edf4dd38becd90864e73c2fb-360010263157.png)

Web SDKは訪問者のイベントデータをAppsFlyerに送信します。このセクションでは、イベント送信の制御、停止、開始の方法について説明します。

注意：

* **SDK初期状態設定**：Webページの初回読み込み時にSDKがイベント送信を開始するか、明示的なコマンドがあるまで待機するかを決定します。この設定はWebスニペット内に含まれます。
* 明示的コントロールイベント送信の停止または開始に使用します。たとえば、データのオプトイン/オプトアウトバナー（いわゆるcookie consent banner）を実装する場合は、イベント送信の開始・停止コマンドをそのバナーの制御に組み込んでください。明示的なコントロールははSDKの初期状態設定より優先され、以下の特性を持つ永続的なファーストパーティCookieを使用します。
  * Webサイトのドメイン上に設定される
  * Web SDKで設定された期間、またはブラウザにより決定される期間で失効する。Cookie失効後、Web SDKは初期状態設定に戻ります。
  * Web SDKのCookieは、ブラウザ固有のCookie設定に干渉せず、常にその設定に従います。

#### SDK初期状態設定

| 設定 | 必要なスニペット |
| --- | --- |
| ［デフォルト］イベントを送信 | Web SDKスニペットに次の変更を加えます。 必要に応じて、measurementStatus パラメーターを追加してください：<br /><br />measurementStatus=true に設定します。<br /><br />`{pba: {webAppId: "********-****-****-*****************", measurementStatus:true}` |
| イベントを送信しない | Web SDKスニペットに次の変更を加えます。必要に応じて、measurementStatus パラメーターを追加してください：<br /><br />Set measurementStatus=false  <br />  <br />`{pba: {webAppId: "********-****-****-*****************", measurementStatus:false}` |

#### 明示的コントロール

| 任意 | コマンド |
| --- | --- |
| イベント送信開始 (オプトイン) | `window.AF_SDK.PLUGINS.PBA.enableMeasurement()` |
| イベント送信停止 (オプトアウト) | `window.AF_SDK.PLUGINS.PBA.disableMeasurement()` |

</Accordion>

<div id="implement-a-content-security-policy-csp-policy" />

<Accordion title="コンテンツ・セキュリティ・ポリシー（CSP）ポリシーの導入">

ウェブサイトで厳格なセキュリティ要件またはデータプライバシー要件が求められる場合は、以下の仕組みを使用して、Web SDKがあなたの環境およびデータとどのように連携するかを設定してください。

#### コンテンツ・セキュリティ・ポリシー（CSP）

ウェブサイトでJavaScriptをCSPによって保護する必要がある場合、Web SDKはCSPの構成に応じて2つの方法をサポートしています。

* **selfを使用すたCSP**：`script-src`の許可リストに `https://websdk.appsflyersdk.com` を追加してください。これは、スタンダードWeb SDKとアドバンスSDK検証の両方で機能します。
* **nonceを使用したCSP**：ポリシーで `script-src 'nonce-...'` を使用している場合は、[アドバンスSDK検証のnonce拡張版](#csp-nonce対応のアドバンスsdk検証用スニペット)を利用できます。これにより、検証プロセスで必要となる3つのscriptタグすべてにnonceが引き渡されます。`{{CSP_NONCE}}`は、サーバー側でリクエストごとに生成されるnonce値に置き換えてください。

以下の表は、どのCSPポリシーがnonce拡張版と互換性があるかを示しています。

| ポリシー | 作業 | 備考 |
| --- | --- | --- |
| `script-src 'self'` | いいえ | 外部CDNオリジンが許可されておらず、インラインスクリプトもブロックされます。 |
| `script-src 'self' https://websdk.appsflyersdk.com` | 一部可能 | ローダーおよびSDKは許可されますが、インラインのセットアップスクリプトは引き続きブロックされます。 |
| `script-src 'nonce-...' https://websdk.appsflyersdk.com` | はい | nonceによってインラインスクリプトとローダーが許可され、SDKタグにはローダー経由でnonceが引き渡されます。 |
| `script-src 'nonce-...' 'strict-dynamic'` | はい（推奨） | nonceによってインラインスクリプトとローダーが許可され、`strict-dynamic` により動的に挿入されるSDKタグにも信頼が引き継がれます。許可リストにCDNオリジンを追加する必要はありません。 |

CSPポリシーとの互換性

#### CSP nonce対応のアドバンスSDK検証用スニペット

<div id="nonce-without-smart-banners" />

<Accordion title="Smart Banners なし">

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

<Accordion title="Smart Banners あり">

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

<Accordion title="クエリパラメータの破棄">

クエリパラメータにAppsFlyerへ記録したくないデータが含まれている場合、AppsFlyerプラットフォームに対して一部またはすべてのクエリパラメータを破棄するよう指示できます。これにより、それらはraw dataやレポートでは利用できなくなります。

この方法は、URL、referrer、header\_refererに関連して実装できます。

#### クエリ破棄のオプション

| メソッド | 説明 |
| --- | --- |
| すべてのクエリパラメータの破棄 | URLに`af_url=true`を追加します |
| 特定のクエリ・パラメータの破棄 | Query param maskを設定することで、どのパラメータを破棄するか指定できます。  param がパラメータ名として、af\_url\_mask=param を設定します。<br /><br />例：<br /><br />**マスク付きのURL：**<br /><br />`param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`<br /><br />**破棄後のURL：**<br /><br />`param1=value1&af_url_mask=param2;param3` |

</Accordion>

## イベント記録の原則

<div id="conversion-and-standard-events" />

<Accordion title="コンバージョンとスタンダードイベント">

* ユーザーイベントはSDKによって記録され、SDKはイベントをAppsFlyerに送信します。
* マーケティング担当者が設定した<Anchor target="_blank" href="/marketers/ja/docs/pba-brand-bundles-and-settings#web-event-settings">コンバージョンイベント</Anchor>リストを使用して、AppsFlyerはイベントをスタンダードイベントとコンバージョンイベントに分割します。
* コンバージョンイベントデータはPBAの管理画面でも利用できます。
* コンバージョンおよびスタンダードイベントデータは、 <Anchor target="_blank" href="/marketers/ja/docs/pba-raw-data-reports">ローデータレポート</Anchor> 内で利用できます。

### コンバージョンイベント

* コンバージョンイベントはマーケティング施策やビジネス成果に関するインサイトを提供します。具体的には、購入、ダウンロード、サインアップ、サブスクリプション登録などが含まれます。
* ユーザーをWebサイトに導いたメディアソースにコンバージョンイベントを紐付けることが、Web SDKにより可能になります。
* 紐付けるメディアソースを特定することで、さまざまなメディアソースによってもたらされるユーザーの質を計測および区別できるようになります。
* コンバージョンイベントでは、収益の計測やROIの計算も可能になります。
* 特定のメディアソースの予算をそのメディアソースのユーザーによる収益と比較するために使用してください。

### スタンダードイベント

* スタンダードイベントは、コンバージョンにつながるユーザージャーニーとファネルを評価するのに役立ちます。
* さらに、ユーザーアクティビティを計測し、エンゲージメントの高いユーザーが多いメディアソースをハイライトすることができます。
* ユーザーアクティビティを計測することで、リエンゲージメントキャンペーンを実施するべきユーザーの選定にも活用できます。

### イベントの計測

ランディングページが読み込まれたときやユーザーがWebサイト上で何らかの操作したときなど、特定の条件が満たされたときにWeb SDKをトリガーしてイベントを記録してください。[計測イベントの例](#recording-events::f1e16eae)を参照してください。

</Accordion>

<div id="identifying-users-using-customer-user-id-cuid" />

<Accordion title="カスタマーユーザーID（CUID）を使用したユーザーの識別">

* Webユーザーは、割り当てた一意のCUIDを使用してAppsFlyer上で識別されます。通常、CUIDはお客様側のバックエンドサーバーで管理されます。
* モバイル環境で使用しているものと同じCUID値を使用してください。これにより、複数のプラットフォームをまたいだユーザー行動を包括的に把握できます。モバイルSDKの関数はsetCustomerUserIdです。（<Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid#cuidの設定">iOS</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid#cuidの設定">Android, Unity</Anchor>）
* Web SDKでCUIDを設定するには：
  * CUIDにアクセスできるようになった最も早い時点で設定してください。多くの場合、ユーザーがログインまたはサインアップして識別された後になります。
  * 以下の例のように、setCustomerUserId() を設定するJavaScript呼び出しを実行してください。  
    注意：　CUIDが数値であっても、文字列として送信してください。引用符で囲んでください。
* Web S2Sを実装する場合は、バックエンドでCUIDをWeb Visitor IDに<Anchor target="_blank" href="/marketers/ja/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method">紐付けた際</Anchor>に、PBAへ通知する必要が生じる可能性がある点を考慮してください。
* CUIDには、 <Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid#cuidとプライバシー">直接識別できる個人情報</Anchor> (電話番号や電子メールアドレスなど)は含めないでください。

**例：CUIDの設定**

```javascript
// Associate all current user web events to distinct ID 663274 
AF('pba', 'setCustomerUserId' , '663274')
```

</Accordion>

<div id="web-sdk-event-parameters" />

<Accordion title="Web SDKのイベントパラメータ">

| パラメーター名 | 必須 | 説明 |
| --- | --- | --- |
| eventType | はい | イベントタイプ<br /><br />形式：文字列<br /><br />このパラメーターには常にEVENTを入力してください。<br /><br />例: eventType:"EVENT" |
| eventName | はい | イベント名<br /><br />形式：文字列<br /><br />例：Purchase, Subscription |
| ~~eventCategory~~ | いいえ | このパラメータは非推奨であり、後日案内される日付にシステムから削除されます。代わりに eventValue パラメータを使用してください。 |
| ~~eventLabel~~ | いいえ | このパラメータは非推奨であり、後日案内される日付にシステムから削除されます。代わりに eventValue パラメータを使用してください。 |
| eventRevenue | いいえ | Conversion eventに紐づく収益<br /><br />形式：Float |
| eventRevenueCurrency | いいえ | 収益通貨<ul><li>3文字の <Anchor target="_blank" href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</Anchor> 通貨コード</li><li>デフォルト：USD</li></ul>形式：文字列 |
| eventValue | いいえ | イベントを説明する、イベントパラメータの一覧。このパラメーターを使用して、製品、アイテム価格などの情報をリッチアプリ内イベントで送信してください。<br /><br />形式：JSON<br /><br />**例：** 青色で単価が3.99ドルの、商品(sku)" ABC123"を送信するには<br /><br />`{"sku": "ABC123", “color": "blue", "unit_price":3.99,"currency": "USD"}`<br /><br />**制限：** 1000文字まで。これを超えると切り捨てられます。 |

</Accordion>

<div id="recording-event-scenarios" />

<Accordion title="イベント計測シナリオ">

イベントの例

```javascript
// purchase event of shoes with associated revenue
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name"}});
```

送信するイベントは、Webサービスの性質によって異なります。たとえば、オンラインストアのアプリで必要となるイベント群は、ニュースメディアのアプリとは異なります。以下のシナリオを参考に、どのようなイベントを、どのタイミングで送信すべきかを把握してください。

#### オンラインストア

オンラインストアを運営しているとします。記録したいスタンダードイベントの例は以下のとおりです。

* 検索：スタンダードイベント
* カート追加：スタンダードイベント
* カート削除：スタンダードイベント
* 購入：コンバージョンイベント

ニュースサイト

ニュースサイトを運営しているとします。記録したいイベントは次のとおりです:

* サインアップ - コンバージョンイベント
* 定期購読の登録 - コンバージョンイベント

</Accordion>

<div id="ensuring-that-events-are-sent" />

<Accordion title="イベントが送信されているかの確認">

このパートはWeb開発者向けです。

<Anchor target="_blank" href="/marketers/ja/docs/test-pba-web-sdk-integration">PBAのWeb SDK実装テスト：</Anchor>テストイベントをリアルタイムで表示します。

**イベントがAppsFlyerへ送信されているかの確認**：

1. Webサイトを開いてください。
2. ブラウザー開発者ツールを開きます。
   * <Anchor target="_blank" href="https://developers.google.com/web/tools/chrome-devtools/open#console">Chromeでのデベロッパーコンソールの開き方</Anchor>
   * <Anchor target="_blank" href="https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/Web_Inspector_Tutorial/EnableWebInspector/EnableWebInspector.html">Safariでのデベロッパーコンソールの開き方</Anchor>
3. Networkタブに切り替えてください。
4. イベントを発火させます。
5. message で絞り込んでください。

   ![pba_af_event.png](https://files.readme.io/394f43890d1aaf09114054a3bca1a003178526e768a5da0b554dbc8d63ef1eb4-360003502238.png)
6. wa.appsflyer.com で始まるネットワークリクエストを探してください（以下スクリーンショットを参照してください）。
7. 以下を確認してください。
   1. ステータスコードが200であること
   2. Request Payload がイベントのパラメーターと一致していること

</Accordion>

## 例

<div id="recording-events::f1e16eae" />

<Accordion title="イベントの計測">

ここで示すコードは、あくまで説明用です。そのまま使用しないでください。

* 前提条件:前提条件：イベント送信時点で、ページ上ですでにWeb SDKが読み込まれていること。
* 以下のシナリオ例では、次の場合にイベントを記録するコードを示します。
  * ランディングページが読み込まれる時：
  * ユーザーがWebサイト上で行動した時：

<Tabs>
<Tab title="ネイティブイベント計測">

**ランディングページのロード時のイベント計測**

* メルマガの定期購読登録のページがあり、その登録数を計測したい場合。
* 登録完了したユーザーを、予め作成したサンキューページにリダイレクトさせることも可能です。

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

* 上記のコードは基本的なHTMLページです。イベントを送信するには、そのWebページでWeb SDKが読み込まれている必要があります。
* ユーザーがリダイレクトされた後にページが読み込まれると、ウィンドウロードメソッドが、AF() APIメソッドを呼び出して、定期購読 (サブスクリプション) のイベントをAppsFlyerに送信します。

**ユーザーのウェブサイト上の行動を計測**

* ECサイトを運営していて、購入イベントを計測したい場合。
* ユーザーが購入ボタンをクリックすると、WebSDKがイベントをAppsFlyerに送信します。

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

上記のコードは基本的なHTMLページです。 イベントを送信するには、そのWebページでWeb SDKが読み込まれている必要があります。

* ページが読み込まれると、クリックリスナーと**チェックアウト**ボタンが紐づきます。
* ユーザーが**購入**ボタンをクリックすると、コールバック関数が次のことを実行します：
  * localStorageからデータを取得します。
  * AF() メソッドを呼び出してデータを渡します。
* AF() メソッドは、AppsFlyerにイベントを送信します。

</Tab>

<Tab title="タグマネージャー経由イベント計測">

**ランディングページのロード時のイベント計測**

* メルマガの定期購読登録ページがあり、その登録数を計測したい場合は、
* 定期購読登録完了後、ユーザーがサンキューページにリダイレクトされるように設定します。

1. サンキューページの作成

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

   上記のコードにより、GTMがロードされ、Web SDKもロードします。そのほかに2つのアクションがこのスクリプトで実行されます。1つ目は、ユーザー情報をサーバーから取得します。もう1つは、データをローカルストレージに設定します。GTMはfunctionとlocalStorageの両方にアクセスでき、GTMを使用してfunctionを呼び出し、localStorageにアクセスすることも可能です。
2. サブスクリプションを計測するために、サンキューページがロード後に発火するタグを追加してください。。

   [![](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
3. タグに名前をつけ、タグタイプは **Custom HTML** を選択してください。
4. 次のコードを **Custom HTML**に設定します。

   ```html
   <script> 
   AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'}); </script>
   ```

   ![gtm_tag_after_subscribe.png](https://files.readme.io/6cf080f94a97a7f38c50899a93d154320995e91f60963c075a5dd03b3a080408-360003515298.png)
5. **Advanced Settings**の中の**Tag Sequencing**を開き、タグが発火した後にのみコンバージョンタグが発火するように設定してください。

   [![](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. コンバージョンタグを発火させるために、トリガーを設定してください。この例では、サンキューページが読み込まれた時にトリガーが発火します。

   [![](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

**ユーザーのウェブサイト上の行動を計測**

* ECサイトを運営していて、購入イベントを計測したい場合。
* ユーザーが購入ボタンをクリックすると、WebSDKがイベントをAppsFlyerに送信します。

1. チェックアウトページの設定

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

   上記のコードは、GTMを使ってWeb SDKをロードします。残りのHTMLはショッピングカートページの内容を単にコピーしているだけです。**Checkout**ボタンの箇所に、id='checkout'の記載があることに注意してください。GTMでボタンのクリックを取得したい場合にはこの設定が必須となります。
2. GTMで、**Variables** をクリックし、**Configure** をクリックして、**Built-In Variables**のリストにある**Click Element** をチェックしてください。  

   [![gtm-create-variable.png](https://files.readme.io/2f38308b4e4b9f279420f0219b220f2796d337a39a79241861c3d31bdb442b24-360002899569.png)](https://files.readme.io/2f38308b4e4b9f279420f0219b220f2796d337a39a79241861c3d31bdb442b24-360002899569.png)
3. 新しい変数 (variable) を作成して、名前をつけてください。タイプは**All Elements(全ての要素)** を選択します。  

   [![gtm-checkout-all-elements.png](https://files.readme.io/1c370646a4c21dc0fcb8351c756a9fdc81a1a8039d0557b716bc8a4ae51a3fad-360002899589.png)](https://files.readme.io/1c370646a4c21dc0fcb8351c756a9fdc81a1a8039d0557b716bc8a4ae51a3fad-360002899589.png)
4. トリガー設定で **Some Clicks** を選択し、#checkout の **CSS Selector に一致する** **Click Element** を選択します。  

   [![gtm-checkout-click-elememt.png](https://files.readme.io/a101d6c27438d3e05eed9db7ea58b57df8bba9a92d4f9e30caee005366dbcf8c-360002903565.png)](https://files.readme.io/a101d6c27438d3e05eed9db7ea58b57df8bba9a92d4f9e30caee005366dbcf8c-360002903565.png)
5. チェックアウトアクションに対して新しいタグを作成してください。タイプはカスタムHTML、トリガーはチェックアウトトリガーにしてください。

   ```html
   <script>
    AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'}); </script>
   ```

   ![gtm-checkout-tag.png](https://files.readme.io/8d3f99dcd3c3ff8df9e6fc13076b798237b86f8cbc5bbd26f349fa9948edb0d6-360003431857.png)

</Tab>
</Tabs>

* イベントが発生する前に、Web SDKのfunctionsタグがロードされていることを確認してください。
* イベントの値で特殊文字・記号を送信しないようにしてください（例：通貨マークなど）
* 値は半角50文字以下に設定してください。

</Accordion>

<div id="setting-customer-user-id-after-signup" />

<Accordion title="サインアップ後のカスタマーユーザーIDの設定">

これらの例で示しているコードは、あくまで参考用です。このコードをそのまま使用しないでください。コードの使い方がわからない場合は、Web開発者に相談してください。

前提条件:どちらの例も、イベントが送信される前にWeb SDKがページによって既にロードされていることを前提としています。Web SDKを再度読み込まないでください。

ユーザーシナリオ：

* ユーザーがウェブサイトでサインアップを完了しました。
* Webサイトのコードがユーザー情報を収集し、サーバーに送信します。
* サーバーは、ユーザー対してユニークなCUIDを付与します。
* サインアップ完了後のサンキューページにおいて、新しくCUIDをサーバーから取得します。
* サーバーのレスポンスを使用して、Web SDKの setCustomerUserId() のメソッドを使用してAppsFlyerのCUIDを設定してください。

<Tabs>
<Tab title="ネイティブ">

サインアップ(登録)ページの設定

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

上記のコードはシンプルなサインアップフォームです。フォームが送られると、メールアドレスがローカルストレージに保存されます。ユーザーがサンクスページに到達すると、そのメールアドレスがサーバーへ送信され、そのメールアドレスに対応する一意のCUIDが生成されます。

サインアップ完了後のサンクスページの設定

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

このコードはfetch APIを使用しています。ユーザーが入力したメールアドレスをサーバーに送信します。サーバーがサインアップ時に一意のCUIDを生成すると仮定すると、メールアドレスをサーバーへ送信する目的は、その一意のCUIDを受け取ることにあります。サーバーは一意のCUIDを返し、そのCUIDがsetCustomerUserId メソッドに渡される値になります。

</Tab>

<Tab title="Googleタグマネージャー">

1. サインアップ(登録)ページの設定

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

   上記はシンプルな登録フォームのコードになります。フォームが送信されると、メールアドレスが localStorage に保存されます。ユーザーがサンクスページに到達すると、そのメールアドレスがサーバーへ送信され、そのメールアドレスに対応する一意のCUIDが取得されます。
2. サインアップ完了後のサンクスページの設定

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

   上記のコードは、サインアップフォームでユーザーが入力したメールアドレスをサーバーへ送信するGTMトリガーを持つサンクスページです。  
   サインアップした際に、サーバーがユニークなCUIDを作成することを想定の上、  
   ユニークなCUIDを取得するためにメールアドレスをサーバーへ送信します。  
   サーバーは、setCustomerUserId() メソッドを使ってユニークなCUIDを返します。  
   この手順を繰り返して、トリガーとタブを作成してください。
3. 定期購読を計測するために、サンキューページがロードされた後に発火するタグを追加してください。[![](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
4. タグに名前をつけ、タグタイプは “Custom HTML” を選択してください。[![GoogleTag.jpg](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)

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
5. **Advanced Settings** を展開し、その下の **Tag Sequencing** を開いて、タグ実行後にコンバージョンが発火するよう設定されていることを確認してください。

   [![](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. コンバージョンタグをいつ発火させるかを示すため、コンバージョンタグ用のトリガーを設定します（以下の例では、「Thank you」ページの読み込み時 に発火します）。

   [![](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

</Tab>
</Tabs>

setCustomerUserIdのfunctionは、ユーザーのログインとサインアップの後など、ユーザーフローのどの段階でも送信できます。AppsFlyerは、最新のCUIDを使用して、過去または未来のタッチポイントとイベントのユーザー情報を更新します。

モバイルアプリの setCustomerUserd 関数で実行したのと同じCUID値を使用してください（モバイルの setCustomerUserId を参照してください：<Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid#cuidの設定">iOS</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid#cuidの設定">Android</Anchor>、Unity）

</Accordion>

## 追加情報

<div id="web-sdk-cookies" />

<Accordion title="Web SDK cookies">

以下の表に記載されたCookieは、Web SDKによってWebサイト上で設定または使用されます。

表の中では以下のような略語が使われています。

* AMP：Accelerated Mobile Pages
* CDN：コンテンツ・デリバリー・ネットワーク (Content Delivery Network)
* 3PC：サードパーティCookie

| Cookie名 | ドメイン | 有効期間 | 使用条件 | 詳細 |
| --- | --- | --- | --- | --- |
| afUserId | お客様のウェブサイトのドメイン | 395日 | non-AMP | Webページの読み込みおよびナビゲーションイベントの文脈でユーザーを識別します |
| AF\_SYNC | お客様のウェブサイトのドメイン | 1週間 | non-AMP | <ul><li>最終的なユーザー識別子が設定されていることを示すフラグ。</li><li>サイトの読み込み時間を短縮するために使用されます</li></ul> |
| af\_id | appsflyer.com | 395日 | 3PCが許可されている場合はnon-AMP | アプリ起動およびナビゲーションイベントの文脈でユーザーを識別します |
| af\_id | onelink.me | 395日 | 3PCが許可されている場合はnon-AMP | バナー経由のエンゲージメント、またはOneLink経由のエンゲージメント（またはその両方）をアプリ起動イベントに紐付けます |
| amp-afUserid | AMP CDN もしくは あなたのウェブサイトのドメイン | 1年 | AMPで配信されるページ |  |
| AF\_DEFAULT\_MEASUREMENT\_STATUS | お客様のウェブサイトのドメイン | 395日 | PBAの同意状態を保存します。ユーザーの同意が得られるまでSDKの動作を停止します。デフォルトでは設定されず、同意管理（[consent gating](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout)）を構成した場合のみ使用されます | non-AMP |

</Accordion>

<div id="release-notes" />

<Accordion title="Web SDKリリースノート">

| 日付 | バージョン | 備考 |
| --- | --- | --- |
| 2021-07-01 | 1.0 | [クエリパラメータの破棄](/docs/pba-web-sdk-integration-guide#discard-query-params) |
| 2021-06-01 | 1.0 | [コンテンツ・セキュリティ・ポリシー（CSP）の導入](/docs/pba-web-sdk-integration-guide#implement-a-content-security-policy-csp-policy) |
| 2020-08-31 | 1.0 | [オプトイン / オプトアウト機能の追加](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout) |
| 2020-04-16 | 1.0 | customerUserId() 関数は、一意のCUIDを送信するための IDENTIFY イベントを置き換えます。 |
| 2020-07-30 | 1.0 | <ul><li>イベントを送信するための明示的な開始/停止コントロール</li><li>デフォルトの初期状態の変更</li></ul> |

</Accordion>

<div id="deprecations" />

<Accordion title="廃止通知">

* 廃止の通知は、機能またはメソッドのサポートを停止するというAppsFlyerからの事前連絡になります。この機能またはメソッドは、サポート終了日までは機能し続けます。
* この廃止の通知を、コードを変更する機会と見なしてご活用ください。

| 廃止通知日 | サポート終了日 | 詳細 |
| --- | --- | --- |
| 2020-04-16 | 未定 | **非推奨のメソッド：** eventTypeを "IDENTIFY" に設定して、顧客ユーザーID (CUID) をイベントパラメータ customUserid で送信しないでください。<br /><br />**現在のメソッド：** setCustomerUserId() 関数を使用してCUIDを送信してください。 |

</Accordion>

<div data-zendesk-anchors="web-sdk-user-and-integration-guide=web-sdk%E3%81%AE%E5%88%A9%E7%94%A8%E5%AE%9F%E8%A3%85%E3%82%AC%E3%82%A4%E3%83%89 h_01HFKCMH8HAW5DN4K9H1A5Q2NJ=web-sdk%E3%81%AE%E5%88%A9%E7%94%A8%E5%AE%9F%E8%A3%85%E3%82%AC%E3%82%A4%E3%83%89 step-2-select-a-code-snippet=%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E3%81%AE%E9%81%B8%E6%8A%9E h_01KP11XJV8RDV378GMFF0DVZ8V=%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E3%81%AE%E9%81%B8%E6%8A%9E h_01KP3CJBZWJF8X46W2BBCS9ZVX=%E9%87%8D%E8%A6%81 standard=%E3%82%B9%E3%82%BF%E3%83%B3%E3%83%80%E3%83%BC%E3%83%89web-sdk h_01KP11XJV8MN64YV17D1M0T5B9=%E3%82%B9%E3%82%BF%E3%83%B3%E3%83%80%E3%83%BC%E3%83%89web-sdk h_01KP3CJBZWK17M58W9M2EP8VC3=standard-without-smart-banners h_01KP3CJBZWKW1K9P9V1XGYM5ED=standard-with-smart-banners advanced-sdk-verification=%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9sdk%E6%A4%9C%E8%A8%BC h_01KP11XJV8ZGF4SDXJH6FKX18E=%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9sdk%E6%A4%9C%E8%A8%BC h_01KP3CJBZWP7HDJ0GE2DF3TTE3=advanced-verification-without-smart-banners h_01KP3CJBZWJWS9H0XVHQFF758B=advanced-verification-with-smart-banners integrating-the-web-sdk-into-the-website=web-sdk%E3%81%AEweb%E3%82%B5%E3%82%A4%E3%83%88%E3%81%B8%E3%81%AE%E5%AE%9F%E8%A3%85 h_01HFKCMH8HCDNGFJEN32BNA9F2=web-sdk%E3%81%AEweb%E3%82%B5%E3%82%A4%E3%83%88%E3%81%B8%E3%81%AE%E5%AE%9F%E8%A3%85 h_01HFKCMH8HVTJX37PD22ZFV0AY=installation-and-integration considerations-and-actions-required=%E8%80%83%E6%85%AE%E4%BA%8B%E9%A0%85%E3%81%A8%E5%BF%85%E8%A6%81%E3%81%AA%E3%82%A2%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3 h_01HFKCMH8H0JBGD2GWY127428R=%E8%80%83%E6%85%AE%E4%BA%8B%E9%A0%85%E3%81%A8%E5%BF%85%E8%A6%81%E3%81%AA%E3%82%A2%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3 javascript-code-snippet=javascript%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88 h_01HFKCMH8HC064MHGH8D66QCYK=javascript%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88 to-install-the-web-sdk-without-smart-banners=smart-banner%E3%81%AA%E3%81%97%E3%81%A7web-sdk%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF h_01HFKCMH8HST7G880G44WXXXB6=smart-banner%E3%81%AA%E3%81%97%E3%81%A7web-sdk%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF to-implement-the-web-sdk-with-smart-banners=smart-banner%E3%81%A8%E4%B8%80%E7%B7%92%E3%81%ABweb-sdk%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF h_01HFKCMH8HX4SQP6YCBHJH4AX5=smart-banner%E3%81%A8%E4%B8%80%E7%B7%92%E3%81%ABweb-sdk%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF h_01HFKCMH8JMMPMHFR4399QPRJV=create-a-property-in-adobe-experience-cloud h_01HFKCMH8J8WVHP7RZ2ENHGY9V=add-the-web-sdk-to-the-adobe-launch-property h_01HFKCMH8J2MAXJ3YVHJ2AJHWQ=add-the-adobe-launch-tag-to-the-website h_01HFKCMH8JWE1Q2749N54MAYRT=publish-the-adobe-launch-environment h_01HFKCMH8JFQQG0BEQ5CATGQ2P=ensure-that-the-sdk-is-working h_01HFKCMH8JCHH5WB5XRC8029DE=sending-events-optinoptout sdk-initial-state-setting=sdk%E5%88%9D%E6%9C%9F%E7%8A%B6%E6%85%8B%E8%A8%AD%E5%AE%9A h_01HFKCMH8JSJR95Y9KNANABBKR=sdk%E5%88%9D%E6%9C%9F%E7%8A%B6%E6%85%8B%E8%A8%AD%E5%AE%9A explicit-control=%E6%98%8E%E7%A4%BA%E7%9A%84%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AD%E3%83%BC%E3%83%AB h_01HFKCMH8JG2C43P8QZ0SKZCBB=%E6%98%8E%E7%A4%BA%E7%9A%84%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AD%E3%83%BC%E3%83%AB h_01HFKCMH8J9XDX87ES4F5WW4GJ=implement-a-content-security-policy-csp-policy content-security-policy-csp=%E3%82%B3%E3%83%B3%E3%83%86%E3%83%B3%E3%83%84%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E3%83%9D%E3%83%AA%E3%82%B7%E3%83%BCcsp h_01KGJCGCQ0QB7NK6YNZT5XJVJY=%E3%82%B3%E3%83%B3%E3%83%86%E3%83%B3%E3%83%84%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E3%83%9D%E3%83%AA%E3%82%B7%E3%83%BCcsp advanced-sdk-verification-with-csp-nonce-snippets=csp-nonce%E5%AF%BE%E5%BF%9C%E3%81%AE%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9sdk%E6%A4%9C%E8%A8%BC%E7%94%A8%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88 h_01KP11XJV88YB2NSBZJTX9K7ZQ=csp-nonce%E5%AF%BE%E5%BF%9C%E3%81%AE%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9sdk%E6%A4%9C%E8%A8%BC%E7%94%A8%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88 h_01KP3CJBZXQ4D538H0T7N9FZ6Z=nonce-without-smart-banners h_01KP3CJBZX8K3WK6RHQMB029VN=nonce-with-smart-banners h_01HFKCMH8JG40DT9NHXG6TPMJ1=discard-query-params query-discard-options=%E3%82%AF%E3%82%A8%E3%83%AA%E7%A0%B4%E6%A3%84%E3%81%AE%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 h_01HFKCMH8JYSV81BEY5XQRZ24Y=%E3%82%AF%E3%82%A8%E3%83%AA%E7%A0%B4%E6%A3%84%E3%81%AE%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 principles-of-event-recording=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E8%A8%98%E9%8C%B2%E3%81%AE%E5%8E%9F%E5%89%87 h_01HFKCMH8JZCKH1JPTGBVJ3QP4=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E8%A8%98%E9%8C%B2%E3%81%AE%E5%8E%9F%E5%89%87 h_01HFKCMH8JEDEDC48AH5A2797D=conversion-and-standard-events conversion-events=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HFKCMH8JYYB7HG2W8XQ7RFPD=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 standard-events=%E3%82%B9%E3%82%BF%E3%83%B3%E3%83%80%E3%83%BC%E3%83%89%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HFKCMH8JQHSJF3T8SF4ZES7W=%E3%82%B9%E3%82%BF%E3%83%B3%E3%83%80%E3%83%BC%E3%83%89%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 recording-events=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%88%E6%B8%AC h_01HFKCMH8J79VD5BX96ANAYAFQ=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%88%E6%B8%AC h_01HFKCMH8JPJZQ81TYZX5PDF91=identifying-users-using-customer-user-id-cuid h_01HFKCMH8JYPNHJGYVRK1SZFYB=web-sdk-event-parameters h_01HFKCMH8J35YT2448PX8ZRM5P=recording-event-scenarios online-store=%E3%82%AA%E3%83%B3%E3%83%A9%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%82%A2 h_01HFKCMH8JQS3CTE6NTZY4G8ZR=%E3%82%AA%E3%83%B3%E3%83%A9%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%82%A2 h_01HFKCMH8J1EDH3XM5V4ECYCPS=ensuring-that-events-are-sent examples=%E4%BE%8B h_01HFKCMH8J4KQSZ489TMDEN426=%E4%BE%8B h_01HFKCMH8JAK25DZ1BZDFS4THD=recording-events::f1e16eae h_01HFKCMH8J4XNY5B9MKAS81T6Z=setting-customer-user-id-after-signup addtional-information=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HFKCMH8KJDZ0A15RMQ8BDMDH=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HFKCMH8KV3QD9CPBSVWM3EVE=web-sdk-cookies h_01HFKCMH8KGJTE7BMK4VSQJF33=release-notes h_01HFKCMH8KP1SHA21JZA5PTZXG=deprecations" />
