---
title: Oracle ResponsysとAppsFlyerの連携
metadata:
  keywords:
    - Oracle Responsys
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-11-20T09:26:13Z'
  edited_at: '2026-10-14T09:36:34Z'
  id: 360003798297
  locale: ja
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ja/articles/360003798297
---
> **概要：** 概要: メール配信および分析プラットフォームであるOracle Responsysは、AppsFlyer OneLinkをメールに埋め込みます。リンクをクリックしたメール受信者は、アプリにディープリンクされます。

![oracle-responsys-af-logo.png](https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png)

ESP (Email Service Providers) は、セグメント化されたユーザートラフィックを獲得するための有効な手段です。

ESPの課題の1つは、正しいアトリビューションとディープリンクを実行することです。ESPは、独自のESPクリック記録ドメインでディープリンクURLを加工します。この手順では、多くの場合、iOSユニバーサルリンクとAndroidアプリリンクの機能が損なわれます。

ただし、ディープリンクとクリック記録は、クリック記録ドメイン上でユニバーサルリンクとアプリリンクをサポートするESPで引き続き可能です。さらに、クリック記録ドメインとして機能する独自のクリックドメインを設定できます。

<div id="prerequisites" />

## 前提条件

* <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLinkとのディープリンク</Anchor>をサポートするようにアプリを設定します。
* SDK のバージョンを確認する (Android と iOS の両方)

<Tabs>
<Tab title="iOS">

* AppsFlyer iOS SDK バージョン 4.9.0 (以上)

</Tab>

<Tab title="Android">

* AppsFlyer アンドロイド SDK バージョン 4.9.0 (以上)

</Tab>
</Tabs>

<div id="setting-up-oracle-responsys-click-domain" />

## Oracle Responsysのクリックドメイン設定

この項に従って、Oracle Responsysでクリックドメイン(クリックレコーディングドメイン)を設定します。

<div id="step-1-set-up-a-click-domain-in-oracle-responsys" />

### ステップ1:ステップ1: Oracle Responsysでのクリックドメイン設定

クリックドメインを設定するには、 <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCEA/LinkTable_Main.htm?cshid=LinkTable_Main">クリックドメインの作成</Anchor>方法に関するOracle Responsys公式ガイドに従ってください。Oracle Responsysでは、 リンク表を使用して、特定のキャンペーンのクリックを記録します

リンクテーブルでは、IOSリンクURLを**リンクURL**と同じに定義できる**ことに注意してください**。

![Oracle-responsys-link-tracking-table.png](https://files.readme.io/c151c58af73cf460ba4275a9159e45c15807f311fa8d8b4b1531b0cdf7e3bc4e-49839256667665.png)

リンク表にクリックドメインを設定すると、Responsysはこれらのドメインを使用して、Eメールキャンペーンに含めるOneLinksをラップします。このようにして、ResponsysはOneLinkとディープリンク機能を維持しながら、システムにクリックを記録できます。

<div id="step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android" />

### ステップ2:ステップ2: ResponsysにAASA(iOS)およびAsset Linksファイル(Android)を付与します。

<div id="aasa-for-ios" />

<Accordion title="AASA (iOS)">

ResponsysでiOSユニバーサルリンクをサポートするには、AASAファイルが必要です。次の手順をご参照ください。

ユニバーサルリンクでOneLinkを設定すると、OneLinkにAASAが関連付けられます。AASA を入手するには:

1. OneLink設定に移動し、ユニバーサルリンクで構成されているOneLinkを見つけます。
2. OneLink URLの末尾に **/.well-known/apple-app-site-association**を追加します。
3. OneLinkをブラウザのアドレスバーに貼り付けて、Enterを押します。例: **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-association**.これを行うと、AASAファイルがコンピューターにダウンロードされます。シンプルテキストエディタを使用して開くことができます。
4. このAASAファイルをResponsysに送信します。このファイルの詳細やその他の情報については、<Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/pdf/ios-universal-links-dev-guide.pdf">Oracleのガイド</Anchor>の11ページを参照してください。

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Android 用アセットリンク">

アプリリンクでOneLinkを設定すると、OneLinkに関連付けられたアセットリンクファイルがすでにある状態になります。アセットリンクファイルを取得するには：

1. OneLink設定に移動し、アプリリンクで構成されているOneLinkを見つけます。
2. OneLink URLの末尾に **/.well-known/assetlinks.json** を追加します。
3. OneLinkをブラウザのアドレスバーに貼り付けて、Enterを押します。例: **`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json**.これを行うと、Asset Linksファイルがコンピューターにダウンロードされます。シンプルテキストエディタを使用して開くことができます。
4. このアセットリンクファイルをResponsysに送信します。このファイルの詳細と内容の詳細については、<Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/android/app-links/">こちらのガイド</Anchor>を参照してください。

</Accordion>

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<div id="setting-up-your-app" />

## アプリのセットアップ

<div id="adding-the-click-domain-to-the-activity-in-the-android-manifest" />

#### Androidマニフェストのアクティビティにクリックドメインを追加します

Androidマニフェストで、ディープリンク先のアクティビティのアクティビティタグにクリックドメインホストとプレフィックスを追加します。

```html Markup
<activity android:name=".DeepLinkActivity">
    <intent-filter  android:autoVerify="true">
        <action android:name="android.intent.action.VIEW" />
           <category android:name="android.intent.category.DEFAULT" />
           <category android:name="android.intent.category.BROWSABLE" />
           <data android:scheme="https"
               android:host="click.example.com"
               android:pathPrefix="/campaign" />
     </intent-filter>
</activity>
```

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<div id="setting-up-the-app-to-resolve-click-domains" />

#### クリックドメインを解決するアプリの設定

SDKは、キャンペーン詳細を取得するために、クリックドメインの背後にあるOneLinkを解決する必要があります。

クリックドメインを解決するには:

1. SDK のバージョンが 4.9.0 以上であることを確認してください。
2. このAPIを、SDK初期化の前に呼び出す必要があります。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">こちら</Anchor>のSDK実装手順をご覧ください。  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```

   * <strong>重要！</strong>Movable Ink (MI) をOracleと連携して使用している場合は、MI CNAMEと内部ドメインをMIアカウント担当者から入手し、Oracleのクリックリンクに加えて、setResolveDeepLinkURLs に追加する必要があります。例：

     ```java
     AppsFlyerLib.getInstance().setResolveDeepLinkURLs("oracle-click.example.com", "mi.example.com", "example.micpn.com");
     ```


このセクションでは、ユニバーサルリンクをサポートするアプリの設定方法について説明します。

<div id="associating-click-domains-in-xcode" />

#### Xcodeでのクリックドメインの関連付け

1. Xcodeでプロジェクトをクリックします。
3. <strong><em>Associated Domain（関連付ドメイン）</em></strong>をオンにします。
4. [+] 記号をクリックし、クリックドメインを追加します。例：applinks:click.example.com.


<div id="step-2-setting-up-the-app-to-resolve-click-domains" />

### ステップ2:クリックドメインを解決するアプリの設定

SDKは、キャンペーン詳細を取得するために、クリックドメインの背後にあるOneLinkを解決する必要があります。

クリックドメインを解決するには:

1. SDK のバージョンが 4.9.0 以上であることを確認してください。
2. このプロパティはSDK初期化前に設定する必要があります。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">こちら</Anchor>のSDK実装手順をご覧ください。  

   <Tabs>
   <Tab title="Objective-C">

   ```objectivec
   [AppsFlyerTracker sharedTracker].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Tab>

   <Tab title="Swift">

   ```swift
   AppsFlyerTracker.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Tab>
   </Tabs>

   * <strong>重要！</strong>Movable Ink (MI) をOracleと連携して使用している場合は、MI CNAMEと内部ドメインをMIアカウント担当者から入手し、Oracleのクリックリンクに加えて、setResolveDeepLinkURLs に追加する必要があります。ドメインの例:
     * Oracleドメイン: oracle-click.example.com
     * MI CNAMEドメイン: mi.example.com
     * MI 内部ドメイン: example.micpn.com
3. 次のコードを追加して、SDK がクリック記録ドメインを解決できるようにします:  

   <Tabs>
   <Tab title="Objective-C">

   このコードを AppDelegate.m に追加します：

   ```objectivec
   - (NSDictionary *)allHTTPHeaderFieldsForResolveDeepLinkURL:(NSURL *)URL {
       if ([URL.host  isEqual: @"click.example.com"]) {
           return [NSDictionary dictionary];
       }
       else {
           return nil;
       }
   }
   ```

   </Tab>

   <Tab title="Swift">

   このコードをAppDelgate.swiftに追加します

   ```swift
   func allHTTPHeaderFields(forResolveDeepLinkURL URL: URL!) -> [String : String]! {
       if (URL.host == "click.example.com") {
           /// Change User-Agent
           return [:]
       } else {
           return nil;
       }
   }
   ```

   </Tab>
   </Tabs>

<div id="sending-your-first-email" />

## 最初のEメールの送信

1. リンク管理ページにて（または手動で）OneLink URLを作成してください。
2. OneLink URLを作成する際は、必ずすべてのパラメータ値をURLエンコードしてください。
3. 次のパラメータを使用することを強く推奨します：
   * pid (メディアソース) - メディアソースを示す値を設定してください（例：Email）。
   * c (キャンペーン) - 測定するキャンペーンの名前。
   * af\_dp - ユーザーをディープリンクで遷移させたいディープリンクURIスキーム。
   * af\_web\_dp - デスクトップでクリックしたユーザーをリダイレクトしたい場所。
   * af\_ios\_url - iOS デバイスのリンクをクリックしてアプリを持っていないユーザーをリダイレクトする場所。
   * af\_android\_url - Android デバイスのリンクをクリックしてアプリを持っていないユーザーをリダイレクトする場所。
4. Responsysで作成したメールにOneLink URLを配置します。例：

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Download my great app!</a>
   ```

   この段階で、Responsysは前のステップで設定したクリックドメインで上記リンクをラップします。クリックドメインをクリックすると、OneLink計測リンクにリダイレクトされます。アプリがユーザーのデバイスにインストールされている場合、クリックドメインはアプリにディープリンクします。

<div id="note" />

> 📄 **例**
>
> この例では、読みやすくするために、URLパラメータはURLエンコードされていません。
>
> ```http
> https://greatapp.onelink.me/abcd?pid=Email&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

<div id="testing-your-links" />

### リンクのテスト

上記の必要な手順をすべて実行し、適切なOneLink URLを作成し、メールに入れた後、テストメールを自分宛てに送信してください。

予想されること

アプリがインストールされている場合は、アプリを呼び出す必要があります。関連するAppsFlyer SDKのディープリンクAPIが実装されている場合は、関連するコンテンツにディープリンクする必要があります。  
さらに、クリックは、提供されたメディアソースとキャンペーンに紐づくAppsFlyer管理画面と、Responsysデータの両方に表示されます。

<div data-zendesk-anchors="prerequisites=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01HDNSK7GR33AN2M4GP956S1FD=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 setting-up-oracle-responsys-click-domain=oracle-responsys%E3%81%AE%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E8%A8%AD%E5%AE%9A h_01HDNSK7GR84QSRTS86GH556WK=oracle-responsys%E3%81%AE%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E8%A8%AD%E5%AE%9A step-1-set-up-a-click-domain-in-oracle-responsys=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971%E3%82%B9%E3%83%86%E3%83%83%E3%83%971-oracle-responsys%E3%81%A7%E3%81%AE%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E8%A8%AD%E5%AE%9A h_01HDNSK7GRHYJZSMYCMT9RVEBW=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971%E3%82%B9%E3%83%86%E3%83%83%E3%83%971-oracle-responsys%E3%81%A7%E3%81%AE%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E8%A8%AD%E5%AE%9A step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972%E3%82%B9%E3%83%86%E3%83%83%E3%83%972-responsys%E3%81%ABaasaios%E3%81%8A%E3%82%88%E3%81%B3asset-links%E3%83%95%E3%82%A1%E3%82%A4%E3%83%ABandroid%E3%82%92%E4%BB%98%E4%B8%8E%E3%81%97%E3%81%BE%E3%81%99 h_01HDNSK7GRW57NNXMN1SWFTTFZ=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972%E3%82%B9%E3%83%86%E3%83%83%E3%83%972-responsys%E3%81%ABaasaios%E3%81%8A%E3%82%88%E3%81%B3asset-links%E3%83%95%E3%82%A1%E3%82%A4%E3%83%ABandroid%E3%82%92%E4%BB%98%E4%B8%8E%E3%81%97%E3%81%BE%E3%81%99 h_01HDNSK7GR77N60SFVBD57S9GQ=aasa-for-ios h_01HDNSK7GR6ADJCPG63ZVP19NJ=asset-links-for-android setting-up-your-app=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%82%BB%E3%83%83%E3%83%88%E3%82%A2%E3%83%83%E3%83%97 h_01HDNSK7GRN751HAPPQ3HVRMDG=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%82%BB%E3%83%83%E3%83%88%E3%82%A2%E3%83%83%E3%83%97 adding-the-click-domain-to-the-activity-in-the-android-manifest=android%E3%83%9E%E3%83%8B%E3%83%95%E3%82%A7%E3%82%B9%E3%83%88%E3%81%AE%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%93%E3%83%86%E3%82%A3%E3%81%AB%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%97%E3%81%BE%E3%81%99 h_01HDNSK7GRQNQGWXAEGHSTHADH=android%E3%83%9E%E3%83%8B%E3%83%95%E3%82%A7%E3%82%B9%E3%83%88%E3%81%AE%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%93%E3%83%86%E3%82%A3%E3%81%AB%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%97%E3%81%BE%E3%81%99 setting-up-the-app-to-resolve-click-domains=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%82%92%E8%A7%A3%E6%B1%BA%E3%81%99%E3%82%8B%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HDNSK7GRP9ND0MHC3ZHD7G8H=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%82%92%E8%A7%A3%E6%B1%BA%E3%81%99%E3%82%8B%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E8%A8%AD%E5%AE%9A associating-click-domains-in-xcode=xcode%E3%81%A7%E3%81%AE%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AE%E9%96%A2%E9%80%A3%E4%BB%98%E3%81%91 h_01HDNSK7GSRENM232MQ25EB3J3=xcode%E3%81%A7%E3%81%AE%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AE%E9%96%A2%E9%80%A3%E4%BB%98%E3%81%91 step-2-setting-up-the-app-to-resolve-click-domains=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%82%92%E8%A7%A3%E6%B1%BA%E3%81%99%E3%82%8B%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HDNSK7GSP08G2EQSNVR5G45B=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%82%92%E8%A7%A3%E6%B1%BA%E3%81%99%E3%82%8B%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E8%A8%AD%E5%AE%9A sending-your-first-email=%E6%9C%80%E5%88%9D%E3%81%AEe%E3%83%A1%E3%83%BC%E3%83%AB%E3%81%AE%E9%80%81%E4%BF%A1 h_01HDNSK7GSA9VAMTRFCX8SZGSC=%E6%9C%80%E5%88%9D%E3%81%AEe%E3%83%A1%E3%83%BC%E3%83%AB%E3%81%AE%E9%80%81%E4%BF%A1 h_01HDNSK7GS8HP7BAA8BYBVBABD=%E4%BE%8B testing-your-links=%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 h_01HDNSK7GSTAJXAP6KGKE9TD8T=%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88" />
