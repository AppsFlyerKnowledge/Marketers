---
title: mParticleとAppsFlyerの連携
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - mParticle
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-04-03T05:31:23Z'
  edited_at: '2026-10-28T09:03:36Z'
  id: 209787323
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/209787323
---
> **At a glance:** AppsFlyerの連携済みパートナーであるmParticleは、顧客データを収集し、各種の分析、マーケティング、データウェアハウスのプラットフォームに送信します。

> 🚧 **Important**
>
> **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

<div id="event-integrations" />

## イベント連携

このドキュメントでは、mParticleのイベントデータをAppsFlyerで活用するための設定について説明します。

1. mParticleをご利用の場合は、アプリにAppsFlyerキットを組み込む必要があります。 mParticle SDKはAppsFlyer SDKを初期化し、必要なアプリのライフサイクルイベントをすべてAppsFlyer SDKに転送します。

2. mParticle SDKとともにAppsFlyerキットをアプリに設定する方法は、<Anchor target="_blank" href="https://github.com/mParticle/mParticle-apple-SDK">iOS</Anchor>および<Anchor target="_blank" href="https://github.com/mParticle/mparticle-android-sdk">Android</Anchor> SDKのGitHubリポジトリを参照してください。

<div id="configure-the-appsflyer-event-integration" />

### AppsFlyerのイベント連携の設定

1. mParticle管理画面（[https://app.mparticle.com](https://app.mparticle.com)）で、対象のアプリ（Workspace）を選択します。

2. 左側のナビゲーションで**Directory**をクリックします。

3. AppsFlyerのタイルをクリックすると、カテゴリ、対応プラットフォーム、必要なmParticle SDKの最小バージョン（該当する場合）、データ型、ユーザーID、デバイスID、利用可能なイベントや設定など、連携の詳細が表示されます。

![mParticleのDirectoryにあるAppsFlyerのタイル](https://files.readme.io/afa886e48f2cddde39007275a72ce03c4a6c4182408bb2ad4c8c183b1591b47d-115015666683.png)

4. ［**Add AppsFlyer to Setup**］をクリックします。

**Add to Setup**ウィンドウが開きます。

![mParticleのAdd to Setupウィンドウ](https://files.readme.io/1eccc4ea365d41d4228eb07f4df88641458244b303ac8805932bf42ef4df5a74-115015476946.png)

5. Output Event Integration Typeを選択し、**Add to Setup**をクリックします。Event Configuration Setup画面が開き、設定を続けられます。

![mParticleのEvent Configuration Setup画面](https://files.readme.io/9a4720fef99a21a67fd017f4485e73765ebcb7aeb126f5342cc911aff4a345d2-115015476966.png)

6. AppsFlyerの設定情報を入力し、**Save**をクリックします。

* 設定名
* 開発環境と本番環境に同じ設定を使用
* Devキー
* 作成した設定が、AppsFlyer Default Groupの下に表示されます。

![AppsFlyer Default Groupの下に表示されたAppsFlyerの設定](https://files.readme.io/4d82533f311b93373152f046e92fe46c5e515cb8f5084bb89e81bfcae608172c-115015666803.png)

次に、入力元のプラットフォームとAppsFlyerの出力イベント設定を接続します。

7. **Connections**をクリックします。

8. 入力元（この例ではiOS）を選択し、**Connect Output**をクリックします。

9. AppsFlyerのタイルを選択し、先ほど作成したAppsFlyerの設定を選択します。

10. AppsFlyerの接続設定を入力します。  
Apple App ID（IDの接頭辞を付けず、数字のみを入力します。たとえば、App IDが**id123456789**の場合は、**123456789**と入力します。）

![AppsFlyerの接続設定画面](https://files.readme.io/2fb4c7480c5813bf7d893318de5c4a8edfe3649293bf51c8dae422be65db726e-115015477066.png)

11. **Add Connection**をクリックします。

AppsFlyerがConnected Outputとして表示されます。Custom Mappingsなどの追加オプションを利用できる場合もあります。詳細は、<Anchor target="_blank" href="https://docs.mparticle.com/guides/getting-started/connect-an-event-output#outputs">mParticleのドキュメント</Anchor>を参照してください。

![Connected Outputとして表示されたAppsFlyer](https://files.readme.io/53ea474eeb94c551677dd7a4ce190d6ed5972d65eafacd773b61d4ebd954fe2c-115015667883.png)

<div id="feed-integrations" />

## フィード連携

このセクションでは、AppsFlyerからmParticleへのデータフィードの接続方法を説明します。

AppsFlyerとの連携の概要は、[https://docs.mparticle.com/integrations/appsflyer/feed/](https://docs.mparticle.com/integrations/appsflyer/feed/)を参照してください。

1. mParticle管理画面（<Anchor target="_blank" href="https://app.mparticle.com">https://app.mparticle.com</Anchor>）で、対象のアプリ（Workspace）を選択します。

2. 左側のナビゲーションで**Directory**をクリックします。

3. AppsFlyerのタイルをクリックすると、連携の詳細が表示されます。

![mParticleのDirectoryにあるAppsFlyerのタイル](https://files.readme.io/53ea474eeb94c551677dd7a4ce190d6ed5972d65eafacd773b61d4ebd954fe2c-115015667883.png)
![mParticleに表示されたAppsFlyer連携の詳細](https://files.readme.io/afa886e48f2cddde39007275a72ce03c4a6c4182408bb2ad4c8c183b1591b47d-115015666683.png)

4. ［**Add AppsFlyer to Setup**］をクリックします。

5. Input Feed Integration Typeを選択し、**Add to Setup**をクリックします。

Setup画面に移動し、設定を続けられます。

6. AppsFlyerの設定情報を入力し、**Create**をクリックします。

* 設定名
* アプリケーションとして動作

![AppsFlyerのフィード設定](https://files.readme.io/b27aff8223a98b0bf4bd73b6a7a04dc73bc245fa062ac9dd47ed6f4bbeece3f2-115015668703.png)

7. 表示された認証情報を使って、AppsFlyer管理画面で設定を完了します。

![AppsFlyer管理画面の認証設定](https://files.readme.io/3c751a38c3891f73485375d75eacde3e07f86969a7d44cd33bf29ace6bfa1875-115015478566.png)

<div id="deferred-deep-linking" />

## ディファードディープリンク

AppsFlyerでは、SDKからユーザーのアトリビューションデータにリアルタイムで直接アクセスできます。これにより、ユーザーがアプリを新規インストールした後、初めて開いたときに表示するページをカスタマイズできます。これは一般に「ディファードディープリンク」と呼ばれます。

ディファードディープリンクの詳細は、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">こちら</Anchor>を参照してください。

AppsFlyerのコンバージョンデータには、`is_First_Launch`というパラメータがあります。 `is_First_Launch`は、初回起動時のみtrueになり、2回目以降の起動ではfalseになります。このパラメータを使って、起動のたびに、ディファードディープリンクでユーザーを誘導する必要があるかどうかを判断できます。

```
af_dp → $deeplink_path
```

> 📘 **Note**
>
> **例**
>
> ```
> $deeplink_path=product/Banana-Pet-Costume/dd67268672b345e491656c871af8aa29
> ```
>
> `af_dp`には、エンコードされたURIスキームとパスが含まれます。
>
> `af_dp` →
>
> `%20jet%3A%2F%2Fproduct%2FBanana-Pet-Costume%2Fdd67268672b345e491656c871af8aa29`

<Tabs>
<Tab title="Android">

Androidの場合：Shared Preferencesを使用します。<Anchor target="_blank" href="https://developer.android.com/reference/android/content/SharedPreferences.html">こちらを参照してください。</Anchor>

```java
AttributionListener myListener = new AttributionListener() {
  @Override
  public void onResult(@NonNull AttributionResult attributionResult) {
   if (attributionResult.getServiceProviderId() == MParticle.ServiceProviders.APPSFLYER) {
    JSONObject attributionParams = attributionResult.getParameters();
    if (attributionParams != null && attributionParams.has(AppsFlyerKit.INSTALL_CONVERSION_RESULT)) {
     Log.d("Conversion result", attributionParams.toString());
    } else if (attributionParams != null && attributionParams.has(AppsFlyerKit.APP_OPEN_ATTRIBUTION_RESULT)) {
     Log.d("App open result", attributionParams.toString());
    }
   }
  }

  @Override
  public void onError(@NonNull AttributionError attributionError) {
   Log.d("Attribution Data Error", attributionError.toString());
  }
 };

 MParticleOptions options = MParticleOptions.builder(this)
  .credentials("replaceWithAPIKey", "replace-withAPISecret")
  .attributionListener(myListener)
  .build();

 MParticle.start(options);
```

</Tab>

<Tab title="iOS">

iOSの場合：UserDefaultsを使用します。<Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/userdefaults">こちらを参照してください。</Anchor>

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
 MParticleOptions *options = [MParticleOptions optionsWithKey:@"<>" secret:@"<>"];
 options.onAttributionComplete = ^void (MPAttributionResult *_Nullable attributionResult, NSError * _Nullable error) {
  if (error) {
   NSLog(@"Attribution fetching for kitCode=%@ failed with error=%@", error.userInfo[mParticleKitInstanceKey], error);
   return;
  }
  NSLog(@"Attribution fetching for kitCode=%@ completed with linkInfo: %@", attributionResult.kitCode, attributionResult.linkInfo);
 }
 [[MParticle sharedInstance] startWithOptions:options];
 return YES;
}
```

</Tab>
</Tabs>

<div id="appsflyermparticle-use-cases" />

### AppsFlyer／mParticleのユースケース

| ユースケース | プラットフォーム | AppsFlyer SDKのメソッド | mParticle-AFキットのメソッド |
| --- | --- | --- | --- |
| ディファードディープリンク | iOS | onConversionDataSuccess | checkForDeferredDeepLinkWithCompletionHandler |
| ユニバーサルリンク | iOS | continueUserActivity | continueUserActivity |
| アプリの起動 | iOS | onAppOpenAttribution | checkForDeferredDeepLinkWithCompletionHandler |
| ディファードディープリンク | Android | onConversionDataSuccess | checkForDeepLink |
| Android App Links | Android |  | continueUserActivity |
| アプリの起動 | Android | onAppOpenAttribution | checkForDeepLink |

<div id="handling-user-flags" />

### ユーザーフラグの処理

AppsFlyerでは、初回起動後も、パーソナライズしたコンテンツを表示したり、既存ユーザーをアプリ内の特定の場所に誘導したりできます。既存ユーザーがディープリンクでアプリを開くと、`onOpenAttribution`メソッドから、参照元URLのデータが返されます。

```swift
 if let conversionData = params?[MPKitAppsFlyerConversionResultKey] as? [AnyHashable: Any], !alreadyLoggedAppsflyerConversionData {
   logAppsflyerConversionData(conversionData: conversionData)
   alreadyLoggedAppsflyerConversionData = true
   if let onelinkURL = (conversionData["af_dp"] as? String).flatMap(URL.init) {
    UIApplication.appDelegate._linkController.handle(onelinkURL, source: .appsflyer)
   }
  } else if let appOpenData = params?[MPKitAppsFlyerAppOpenResultKey] as? [AnyHashable: Any] {
   logAppsflyerAppOpenData(appOpenData: appOpenData as? [String: Any])
  }
```

AppsFlyerは、iOSの***UserDefaults***とAndroidの***Shared Preferences***を使って、ユーザーの初回起動で適切なページへの誘導が必要なのか、それともすでに起動済みで誘導も完了しているのかを判別します。この処理では、UserDefaults／SharedPreferencesに`alreadyLoggedAppsflyerConversionData`の値を読み書きし、初回起動時に***af\_dp***の値を参照しないようにします。

ディープリンクでパーソナライズしたコンテンツを表示する方法の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">こちら</Anchor>を参照してください。

<div id="enabling-appsflyer-uninstall-measurement-in-mparticle" />

## mParticleでAppsFlyerのアンインストール計測を有効にする

mParticle-AppsFlyer SDKキットでは、AppsFlyerのアンインストール計測は自動では有効になりません。アンインストールを計測するには、AppsFlyerのアンインストール計測のドキュメントに従って、AppsFlyerのメソッドを直接呼び出してください。

**iOSまたはAndroidでアンインストール計測を実装するには、次の手順に従います。**

* アンインストール計測のドキュメントに従って、AppsFlyerのメソッドを直接呼び出します。

<div data-zendesk-anchors="event-integrations=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E9%80%A3%E6%90%BA h_01H9HWJRM2612MBM2Y7C5YZ2YY=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E9%80%A3%E6%90%BA configure-the-appsflyer-event-integration=appsflyer%E3%81%AE%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWJRM2BJATV1QHS382J0ZN=appsflyer%E3%81%AE%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A feed-integrations=%E3%83%95%E3%82%A3%E3%83%BC%E3%83%89%E9%80%A3%E6%90%BA h_01H9HWJRM2YV3CEH7J7EMA8E3Y=%E3%83%95%E3%82%A3%E3%83%BC%E3%83%89%E9%80%A3%E6%90%BA deferred-deep-linking=%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF h_01H9HWJRM2SZYRXFTSZPM1JHCJ=%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF appsflyermparticle-use-cases=appsflyermparticle%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B9%E3%82%B1%E3%83%BC%E3%82%B9 h_01H9HWJRM2HCB4YF2BP9RPK2RP=appsflyermparticle%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B9%E3%82%B1%E3%83%BC%E3%82%B9 handling-user-flags=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%83%95%E3%83%A9%E3%82%B0%E3%81%AE%E5%87%A6%E7%90%86 h_01H9HWJRM3HAGGWHF4YTQTTS2X=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%83%95%E3%83%A9%E3%82%B0%E3%81%AE%E5%87%A6%E7%90%86 known-mparticle-integration-limitation=mparticle%E3%81%A7appsflyer%E3%81%AE%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC%E3%82%92%E6%9C%89%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B h_01H9HWJRM321PSNQ480R96BN12=mparticle%E3%81%A7appsflyer%E3%81%AE%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC%E3%82%92%E6%9C%89%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B" />
