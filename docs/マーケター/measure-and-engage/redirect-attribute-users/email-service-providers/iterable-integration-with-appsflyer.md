---
title: AppsFlyerとの単一連携。
metadata:
  keywords:
    - OneLink
    - Advertisers
    - ESP
    - Developers
    - Iterable
    - Deep Likning
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-09-16T13:14:19Z'
  edited_at: '2026-10-14T09:28:59Z'
  id: 360002522337
  locale: ja
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ja/articles/360002522337
---
> **概要：**

![iterable-af-logo.png](https://files.readme.io/e339ea75a54e53711f3c577c7f82339151af13e6c086cc1435cbb57cf1fae3f0-49839295443089.png)

<div id="introduction" />

## はじめに

ESP (Email Service Providers) は、セグメント化されたユーザートラフィックを獲得するための有効な手段です。

ESPは、独自のESPクリック記録ドメインでディープリンクURLを加工します。

<div id="prerequisites" />

## 前提条件

<Tabs>
<Tab title="iOS">

* AppsFlyer iOS SDK バージョン 4.9.0

</Tab>

<Tab title="Android">

* AppsFlyer Android SDK バージョン 4.9.0

</Tab>
</Tabs>


<div id="step-1-setting-up-link-branding-in-iterable" />

<div id="setting-up-iterable" />

### ステップ1:

<div id="step-2-uploading-your-ssl-certificate-to-iterable" />

### ステップ2:

<div id="step-2-give-iterable-an-aasa-ios-and-an-asset-links-file-android" />

### ステップ2:

<div id="aasa-for-ios" />

<Accordion title="AASA (iOS)">

ResponsysでiOSユニバーサルリンクをサポートするには、AASAファイルが必要です。次の手順をご参照ください。

ユニバーサルリンクでOneLinkを設定すると、OneLinkにAASAが関連付けられます。AASA を入手するには:

2. OneLink URLの末尾に **/.well-known/apple-app-site-association**を追加します。
3. OneLinkをブラウザのアドレスバーに貼り付けて、Enterを押します。例: **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-association**.これを行うと、AASAファイルがコンピューターにダウンロードされます。シンプルテキストエディタを使用して開くことができます。
4. 詳細は<Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035496511">こちら</Anchor>を参照してください。
5. このファイルの詳細と内容の詳細については、<Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035496511-iOS-Universal-Lin">こちらのガイド</Anchor>を参照してください。

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Android 用アセットリンク">

アプリリンクでOneLinkを設定すると、OneLinkに関連付けられたアセットリンクファイルがすでにある状態になります。取得するには：

2. OneLink URLの末尾に **/.well-known/assetlinks.json** を追加します。
3. OneLinkをブラウザのアドレスバーに貼り付けて、Enterを押します。例: **`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json**.これを行うと、Asset Linksファイルがコンピューターにダウンロードされます。シンプルテキストエディタを使用して開くことができます。
4. このファイルの詳細と内容の詳細については、<Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035127392">こちらのガイド</Anchor>を参照してください。

</Accordion>

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<div id="setting-up-your-app" />

## アプリのセットアップ

<div id="step-1-adding-the-click-domain-to-the-activity-in-the-android-manifest" />

#### ステップ1:Androidマニフェストのアクティビティにクリックドメインを追加します

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

<div id="step-2-setting-up-the-app-to-resolve-click-domains" />

#### ステップ2: クリックドメインを解決するアプリの設定

SDKは、キャンペーン詳細を取得するために、クリックドメインの背後にあるOneLinkを解決する必要があります。

クリックドメインを解決するには:

1. SDK のバージョンが 4.9.0 以上であることを確認してください。
2. このAPIを、SDK初期化の前に呼び出す必要があります。  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```


このセクションでは、ユニバーサルリンクをサポートするアプリの設定方法について説明します。

<div id="step-2-for-ios-resolve-deep-links" />

<div id="step-2-for-android-resolve-deep-links" />

<div id="step-1-associating-click-domains-in-xcode" />

#### ステップ1:Xcodeでのクリックドメインの関連付け

1. Xcodeでプロジェクトをクリックします。
3. <strong><em>Associated Domain（関連付ドメイン）</em></strong>をオンにします。
4. [+] 記号をクリックし、クリックドメインを追加します。例：applinks:click.example.com.


SDKは、キャンペーン詳細を取得するために、クリックドメインの背後にあるOneLinkを解決する必要があります。

クリックドメインを解決するには:

1. SDK のバージョンが 4.9.0 以上であることを確認してください。
2. このプロパティはSDK初期化前に設定する必要があります。  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("clickdomain.com", "myclickdomain.com", "anotherclickdomain.com");
   ```


SDKは、キャンペーン詳細を取得するために、クリックドメインの背後にあるOneLinkを解決する必要があります。

クリックドメインを解決するには:

1. SDK のバージョンが 4.9.0 以上であることを確認してください。
2. このプロパティはSDK初期化前に設定する必要があります。  

   <Tabs>
   <Tab title="Objective-C">

   ```objectivec
   [AppsFlyerLib shared].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Tab>

   <Tab title="Swift">

   ```swift
   AppsFlyerLib.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Tab>
   </Tabs>

3. 次のコードを追加して、SDK がクリック記録ドメインを解決できるようにします:  

   <Tabs>
   <Tab title="Objective-C">

   このコードをAppDelgate.swiftに追加します

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


<div id="note" />

<div id="sending-your-first-email" />

## 最初のEメールの送信

1. リンク管理ページにて（または手動で）<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink URLを作成</Anchor>してください。
2. OneLink URLを作成する際は、必ずすべてのパラメータ値をURLエンコードしてください。
3. 次のパラメータを使用することを強く推奨します：
   * pid (メディアソース) - メディアソースを示す値を設定してください（例：Email）。
   * c (キャンペーン) - 測定するキャンペーンの名前。
   * af\_dp - ユーザーをディープリンクで遷移させたいディープリンクURIスキーム。
   * af\_web\_dp：デスクトップでクリックしたユーザーをリダイレクトしたい場所。
   * af\_ios\_url - iOS デバイスのリンクをクリックしてアプリを持っていないユーザーをリダイレクトする場所。
   * af\_android\_url - Android デバイスのリンクをクリックしてアプリを持っていないユーザーをリダイレクトする場所。
4. Responsysで作成したメールにOneLink URLを配置します。例：

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Download my great app!</a>
   ```

   この段階で、Responsysは前のステップで設定したクリックドメインで上記リンクをラップします。クリックドメインをクリックすると、OneLink計測リンクにリダイレクトされます。アプリがユーザーのデバイスにインストールされている場合、クリックドメインはアプリにディープリンクします。

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

<div data-zendesk-anchors="introduction=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01HV6PJQRMT8037JMVMMXDPWGN=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB prerequisites=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01HV6PJQRM5N1K6CY0NSSFXT3X=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 setting-up-iterable=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971 step-1-setting-up-link-branding-in-iterable=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971 h_01HV6PJQRMX18FRB3NMZH6NCH0=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971 h_01HV6PJQRMMYV3A5ZSEGTT7993=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971 step-2-uploading-your-ssl-certificate-to-iterable=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972 h_01HV6PJQRMYDDWK9AKGN258TTM=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972 step-2-give-iterable-an-aasa-ios-and-an-asset-links-file-android=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972-1 h_01HV6PJQRMFJ23627KS83D4C6A=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972-1 h_01HV6PJQRMNSYK8N7QEE00KSPE=aasa-for-ios h_01HV6PJQRMSMZCVJ5XRXZ3SWEH=asset-links-for-android setting-up-your-app=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%82%BB%E3%83%83%E3%83%88%E3%82%A2%E3%83%83%E3%83%97 h_01HV6PJQRMJHDF94JSAT8N8SP9=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%82%BB%E3%83%83%E3%83%88%E3%82%A2%E3%83%83%E3%83%97 step-1-adding-the-click-domain-to-the-activity-in-the-android-manifest=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971android%E3%83%9E%E3%83%8B%E3%83%95%E3%82%A7%E3%82%B9%E3%83%88%E3%81%AE%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%93%E3%83%86%E3%82%A3%E3%81%AB%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%97%E3%81%BE%E3%81%99 h_01HV6PJQRM2V31JAJ52Q3FHQWH=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971android%E3%83%9E%E3%83%8B%E3%83%95%E3%82%A7%E3%82%B9%E3%83%88%E3%81%AE%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%93%E3%83%86%E3%82%A3%E3%81%AB%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%97%E3%81%BE%E3%81%99 step-2%C2%A0setting-up-the-app-to-resolve-click-domains=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%82%92%E8%A7%A3%E6%B1%BA%E3%81%99%E3%82%8B%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HV6PJQRMCRFM90QSP5SS72SE=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%82%92%E8%A7%A3%E6%B1%BA%E3%81%99%E3%82%8B%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E8%A8%AD%E5%AE%9A step-1-associating-click-domains-in-xcode=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971xcode%E3%81%A7%E3%81%AE%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AE%E9%96%A2%E9%80%A3%E4%BB%98%E3%81%91 h_01HV6PJQRNRW8Y97JWHP0MSXZF=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971xcode%E3%81%A7%E3%81%AE%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AE%E9%96%A2%E9%80%A3%E4%BB%98%E3%81%91 sending-your-first-email=%E6%9C%80%E5%88%9D%E3%81%AEe%E3%83%A1%E3%83%BC%E3%83%AB%E3%81%AE%E9%80%81%E4%BF%A1 h_01HV6PJQRN2H29D8HKXHBYE1NB=%E6%9C%80%E5%88%9D%E3%81%AEe%E3%83%A1%E3%83%BC%E3%83%AB%E3%81%AE%E9%80%81%E4%BF%A1 h_01HV6PJQRNB327E42Y0ZJM9306=%E4%BE%8B testing-your-links=%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 h_01HV6PJQRNET2J17ZGGZE0K0Q6=%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88" />
