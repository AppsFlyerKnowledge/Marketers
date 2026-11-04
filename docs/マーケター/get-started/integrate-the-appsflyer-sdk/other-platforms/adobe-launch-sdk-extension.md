---
title: Adobe Launch SDK 拡張機能
metadata:
  keywords:
    - SDK
    - Adobe
    - Advertisers
    - AppsFlyer SDK
    - Adobe Experience Platform
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2019-02-13T08:03:45Z'
  edited_at: '2026-10-14T09:26:05Z'
  id: 360000939097
  locale: ja
  section: Other platforms
  section_id: 6551244207121
  url: https://support.appsflyer.com/hc/ja/articles/360000939097
---
> **概要：** AppsFlyer Adobe Launch SDK 拡張機能の単一実装で、Adobe Launch SDK と AppsFlyer SDK にデータを送信します。

<div id="overview" />

## 概要

Adobe Launch SDK は、Adobe Experience プラットフォームに不可欠な要素です。Adobe Experience Platform は、企業が複数のアプリケーションやプラットフォームからデータを収集、統合、分析できるようにします。これにより、ビジネス・オーナーやデベロッパーは、顧客の行動をよりよく理解し、エクスペリエンスやコンテンツ配信を最適化することができます。アプリが Adobe Launch SDK と AppsFlyer SDK の両方を実装している場合、**AppsFlyer Adobe Launch SDK 拡張機能を**1つ実装するだけで、両方にデータを送信できます。開発プロセスの全体的な複雑さを軽減し、よりクリーンで保守性の高いコードベースを実現します。

<div id="note" />

> 📘 **注**
>
> Adobe Launch 拡張機能を使用している場合、標準の<Anchor target="_blank" href="/marketers/ja/docs/adobe-analytics-integration-with-appsflyer">Adobe Analytics との統合は</Anchor>必要ありません。

<div id="prerequisites" />

## 前提条件

AppsFlyer Adobe SDK 拡張機能を統合する前に、いくつかのことが必要です。

<div id="get-your-appsflyer-dev-key" />

<Accordion title="AppsFlyer 開発キー の取得">

<Image alt="dev_key.png" src="https://files.readme.io/bf25b5d583f3eaab57c230b68764f08c49806a50401955a511993d8a847e7d42-360006050318.png" width="357px" />

1. アプリの管理画面上で、左メニュー内の***設定***の下にある***アプリ設定***をクリックしてください。
2. ***SDK のインストール***の下にある、***開発キー***をコピーしてください。

</Accordion>

<div id="get-your-app-id" />

<Accordion title="アプリ ID の取得">

* Android の場合 - アプリ ID はパッケージ名。例：example.com.app.
* iOS の場合 - アプリ ID はアプリの iTunes ID から*id*プレフィックスを除いたものです（例：123456748）。

</Accordion>

<div id="step-1-configuring-adobe-launch" />

## ステップ1:Adobe Launch の設定

Adobe Launch を設定するには、こちらの手順に従ってください。

<div id="11-creating-a-new-property-in-adobe-launch" />

<Accordion title="1.1 Adobe Launch で新しいプロパティを作成する">

[![](https://files.readme.io/d03e61047c536785e7601d4f0efbd9b6488bd41c92efdd6e0d1021b42a5bec3a-small-360005983477.png)](https://files.readme.io/d03e61047c536785e7601d4f0efbd9b6488bd41c92efdd6e0d1021b42a5bec3a-small-360005983477.png)

1. Adobe Experience Cloud にログインします。
2. ***起動***を選択します。
3. ***起動する***をクリックします。
4. ***新しいプロパティ***をクリックします。
5. プロパティに名前を付け ***モバイル***を選択します。
6. <strong><em>[保存]</em></strong>をクリックします。

</Accordion>

<div id="12-installing-required-adobe-launch-extensions" />

<Accordion title="1.2 必要な Adobe Launch 拡張機能のインストール">

Adobe Launch に以下の拡張機能をインストールします：

[![adboe_extensions.png](https://files.readme.io/bf0c0652c3807d4da0819a62b600ac875af1f8764387a36cc3f256a58e1ea852-360005983597.png)](https://files.readme.io/bf0c0652c3807d4da0819a62b600ac875af1f8764387a36cc3f256a58e1ea852-360005983597.png)

* Adobe Analytics - SDK から記録されたデータを Adobe Analytics モジュールに接続します。
* AppsFlyer SDK E拡張機能 - Adobe Launch SDK を使用して、Adobe と AppsFlyer の両方にデータとイベントを送信します。
* Adobe プロファイル - SDK がクライアント側のプロファイルにデータを保存できるようにします。
* Adobe Mobile Core - モバイル SDK の設定を可能にし、デフォルトのライフサイクルイベントと条件へのアクセスを提供します。

<div id="installing-adobe-analytics-extension" />

#### Adobe Analytics 拡張機能のインストール

1. Adobe Analytics にログインします。
2. <Anchor target="_blank" href="https://docs.adobe.com/help/en/analytics/admin/admin-console/create-report-suite.html">レポート・スイートを作成</Anchor>する。
3. Adobe Launch にログインします。
4. プロパティのリストから、先ほど作成したプロパティをクリックします。
5. ***拡張機能***をクリックします。
6. ***Adobe Analytics***を検索してインストールします。
7. ***レポート・スイート***で、ステップ2で作成したレポート・を指定します。
8. <strong><em>[保存]</em></strong>をクリックします。

<div id="installing-appsflyer-sdk-extension" />

#### AppsFlyer SDK 拡張機能のインストール

1. ***拡張機能***をもう一度選択します。
2. ***AppsFlyer SDK 拡張機能***を検索してインストールします。
3. ***AppsFlyer iOS アプリ ID***で、前提条件のステップで取得した iOS アプリ ID を指定します。
4. ***AppsFlyer 開発キー***で、前提条件のステップで取得した開発キーを指定します。
5. ***アトリビューションデータを Adobe Analytics に送信する***を有効にします。<Anchor target="_blank" href="/marketers/ja/docs/user-level-data-retention">ユーザーレベルのデータをサードパーティのアナリティクスプラットフォームと共有するには、いくつかの制限が</Anchor>あることに注意してください。
6. ***保存***をクリックします。

<div id="install-profile-and-mobile-core-extension" />

#### プロファイルとモバイルコア拡張機能のインストール

1. ***拡張機能***をもう一度選択します。
2. ***プロフィール***を検索してインストールします。
3. ***モバイルコア***を検索してインストールします。
   * モバイルコアをインストールする際は、拡張機能をそのまま保存してください。***エクスペリエンス・クラウド・サーバー***を指定する必要はありません。

</Accordion>

<div id="step-2-implementing-appsflyer-adobe-sdk-extension" />

## ステップ2:AppsFlyer Adobe SDK 拡張機能の実装

このセクションの指示に従って、アプリに Adobe SDK 拡張機能を実装します。

<div id="21-adding-the-sdk-to-the-app" />

<Accordion title="2.1 SDK をアプリに追加する">

[![adobe_sdk.png](https://files.readme.io/076e6cc5911a0a515e5510a8da233bcefcb4144c92cf49190416b593fcdecc8f-small-360006050518.png)](https://files.readme.io/076e6cc5911a0a515e5510a8da233bcefcb4144c92cf49190416b593fcdecc8f-small-360006050518.png)

1. Adobe のプロパティで ***環境***を選択します。
2. SDK をデプロイする環境を選択します。
3. 右側のボックスアイコンをクリックします。
4. 開いたウィンドウからコード・スニペットをコピーし、指示に従ってください。あなたが Adobe を設定するマーケティング担当者である場合は、これらのコードスニペットをアプリ開発者に送ってください。

</Accordion>

<div id="22-publishing-the-environment" />

<Accordion title="2.2 環境の公開">

SDK の実装を完了するには、環境をライブラリに公開する必要があります。

[![adobe_publishing.png](https://files.readme.io/4e9ad08fce291ef59e7a3567726c678754ae3a3c96de75f4ae27cd80a84945d1-small-360006050558.png)](https://files.readme.io/4e9ad08fce291ef59e7a3567726c678754ae3a3c96de75f4ae27cd80a84945d1-small-360006050558.png)

1. Adobe のプロパティで、 ***公開***を選択します。
2. ***新しいライブラリの追加***をクリックします。
3. 名前を付け、「環境」で ***開発***を選択します。
4. ***保存して開発用にビルドする***をクリックします。
5. ビルドが完了したら ***開発***で、ライブラリの横にある三点リーダーをクリックして ***承認のために提出***を選択します。
6. ***送信***で、ライブラリの横にある三点リーダーをクリックして ***ステージング用にビルド***を選択します。
7. ビルドが完了したら、ライブラリの横にある三点リーダーをクリックし、 ***公開を承認する***を選択します。
8. ***承認***で、ライブラリの横にある三点リーダーをクリックし、***ビルドして製品に公開する***を選択します。

</Accordion>

<div id="23-adding-android-install-referrer-to-your-app" />

<Accordion title="2.3 アプリに Android インストールリファラを追加する">

Android インストールリファラはアトリビューションの精度を改善し、不正インストールなどから守ります。APIはAppsFlyerのAndroid SDKバージョン4.8.6以降よりサポートされています。

<div id="note-1" />

> 📘 **注**
>
> Google は[2020年3月に](https://android-developers.googleblog.com/2019/11/still-using-installbroadcast-switch-to.html) BroadcastReceiverを廃止しました。
>
> * この変更はアプリには影響しません。
> * 店外アトリビューションのために BroadcastReceiver が必要な場合もあります。アプリが掲載されているストアで確認してください。
> * インストールリファラに実装が必須になりました。

アプリにインストールリファラを追加するには、2つの方法があります。

* Gradleを使用する（推奨）
* インストールリファラを手動で追加する

<Tabs>
<Tab title="インストールリファラを手動で追加する">

dependency としてAndroid インストールリファラを追加します。最新バージョンは<Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">こちら</Anchor>を参照してください。

1.
   ```java
   dependencies {
   //make sure to use the latest SDK version: https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk
   	implementation 'com.appsflyer:af-android-sdk:5.+'
   	implementation 'com.android.installreferrer:installreferrer:1.1'
   }
   ```
2. 次のスクリーンショットを参考に dependencies を取得して、プロジェクトを同期してください。  

   [![android_af_sdk_sync_gradle.png](https://files.readme.io/f8835cf76d51d7ddeb51206707d95b7214e398c5960299893118ad57ccffe890-22939234622609.png)](https://files.readme.io/f8835cf76d51d7ddeb51206707d95b7214e398c5960299893118ad57ccffe890-22939234622609.png)

ProGuard を使用中で、Google の新しいリファラ API を使用したい場合は、以下の ProGuard ルールを設定する必要があります。`-dontwarn com.android.installreferrer`

</Tab>

<Tab title="使って、インストールリファラを追加する">

1. <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">インストールリファラ aar のダウンロード</Anchor>
2. <Anchor target="_blank" href="https://stackoverflow.com/questions/16682847/how-to-manually-include-external-aar-package-using-new-gradle-android-build-syst">プロジェクトに追加する</Anchor>
3. マニフェストに以下の権限を追加します： `com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE`

</Tab>
</Tabs>

</Accordion>

<div id="24-setting-required-permissions" />

<Accordion title="2.4 必須権限の設定">

権限を追加することで、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#probabilistic-modeling">確率論的モデリングのアトリビューション</Anchor>率を高めることができます。SDKがWifiやキャリアネットワークデータなどのデータを送信できるようにします。このデータは<Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">ローデータレポート</Anchor>にも反映され、キャンペーンの分析や最適化に使用できます。

<div id="add-required-permissions" />

#### 必須パーミッションの追加

1. 次の権限を AndroidManifest.xml に追加します。  

   ```html Markup
   <uses-permission android:name="android.permission.INTERNET" />
   <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
   <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
   <!-- Optional : -->
   <uses-permission android:name="android.permission.READ_PHONE_STATE" />
   ```

</Accordion>

<div id="using-the-adobe-sdk-extension" />

## Adobe SDK 拡張機能の使用

これで、Adobe SDK 拡張機能を使って Adobe と AppsFlyer にデータを送信できるようになります。

<div id="note-2" />

> 📘 **注**
>
> 現在、Adobe Launch SDK 拡張機能は、コンバージョンデータの取得とイベントの送信のみをサポートしています。ただし、アプリに Adobe Launch SDK 拡張機能を追加すると、AppsFlyer SDK も追加されます。そのため、現在 Adobe SDK 拡張機能に欠けている機能はすべて、AppsFlyer SDK を使用して実装することができます。

<div id="sending-events" />

<Accordion title="イベントの送信">

アプリ内イベントにより、アプリ内でのユーザーの動きに関するインサイトを得ることができます。時間をかけて、記録したいイベントを定義することをお勧めします。アプリ内イベントを記録すると、ROI（投資収益率）やLTV（顧客生涯価値）といったKPIを測定することができます。

Adobe Launch SDK 拡張機能を使用すると、アプリ内イベントデータを Adobe と AppsFlyer の両方に送信できます。その後、Adobe Analytics を使用してユーザーの行動を分析し、AppsFlyer を使用して ROI と LTV を分析することができます。

<Tabs>
<Tab title="Android">

```java
final Map<String,String> eventMap = new HashMap<>();  
eventMap.put("currency", "USD");  
eventMap.put("revenue", "200");  
eventMap.put("freehand", "param");

MobileCore.trackAction("af_purchase", eventMap);
```

</Tab>

<Tab title="iOS">

```java
[ACPCore trackAction:@"af_purchase data:@{@"revenue":@"200",@"currency":@"USD"];
```

</Tab>
</Tabs>

上記のコードで指定されたとおりにイベントを送信すると、AppsFlyer 管理画面に af\_purchase という収益200米ドルのイベントが作成されます。このイベントは Adobe Analytics にも送信され、表示されます。

イベントとともに送信されるすべての<Anchor target="_blank" href="https://dev.appsflyer.com/docs/direct-deep-linking-1">コンバージョンデータの</Anchor>先頭には ***appsflyer***という接頭辞が付けられます。例については、次の表を参照してください。

| 接頭辞付きコンバージョンデータ変数 |
| --- |
| appsflyer.af\_click\_lookback |
| appsflyer.install\_time |
| appsflyer.cost\_cents\_USD |
| appsflyer.media\_source |
| appsflyer.af\_adset |
| appsflyer.click\_time |
| appsflyer.orig\_cost |
| appsflyer.campaign |

</Accordion>

<div id="getting-data-for-deep-linking-and-deferred-deep-linking" />

<Accordion title="ディープリンクとディファードディープリンク用のデータの取得">

ディープリンクとディファードディープリンクによって、ユーザーエクスペリエンスを向上させることができます。特定のアクティビティでアプリを開き、キャンペーンデータに応じてコンテンツをカスタマイズすることができる用になります。

ディープリンクからデータを取得するには、拡張コールバックを実装します。

<Tabs>
<Tab title="Android">

グローバル・アプリケーション・クラスで、以下のコードを実装します：

```java
AppsFlyerAdobeExtension.registerAppsFlyerExtensionCallbacks(new AppsFlyerExtensionCallbacksListener() {
		@Override
		public void onCallbackReceived(Map<String, String> callback) {
			Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			if(callback.get("callback_type").equals("onConversionDataReceived")){
				// conversion data returned 
				if(callback.get("is_first_launch").equals("true")){
					String af_status = callback.get("af_status");
					if(af_status.equals("Non-organic")){
						Log.d(AppsFlyerLibCore.LOG_TAG, "this is first launch and a non organic install!");
					}
				}
			} else if(callback.get("callback_type").equals("onAppOpenAttribution")){
				// direct deeplink - redirect user
				Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			}
		}
		@Override
		public void onCallbackError(String errorMessage) {
			Log.d("TAG", errorMessage);
		}
	});
```

</Tab>

<Tab title="iOS">

AppDelegate.m で、以下のコードを実装します：

```objectivec
[AppsFlyerAdobeExtension registerCallbacks:^(NSDictionary *dictionary) {
        NSLog(@"[AppsFlyerAdobeExtension] Received callback: %@", dictionary);
        if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onConversionDataReceived"]){
            if([[dictionary objectForKey:@"is_first_launch"] boolValue] == YES){
                NSString* af_status = [dictionary objectForKey:@"af_status"];
                if([af_status isEqualToString:@"Non-organic"]){
                    NSLog(@"this is first launch and a non organic install!");
                }
            }
        } else if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onAppOpenAttribution"]) {
            NSLog(@"onAppOpenAttribution Received");
        }
     }];
    [AppsFlyerAdobeExtension callbacksErrorHandler:^(NSError *error) {
          NSLog(@"[AppsFlyerAdobeExtension] Error recieving callback: %@" , error);
    }];
```

</Tab>
</Tabs>

</Accordion>

<div id="connecting-appsflyer-conversion-data" />

## AppsFlyer のコンバージョンデータの取得

コンバージョンデータは、イベントとともに Adobe プラットフォームに送信されます。これらの変数を使用すると、レポートのディメンション、メトリクス、またはフィルタにロジックやルールを適用できます。

1. [![](https://files.readme.io/d56f170695893dbbde00c50c838ce8a5c2cfe418a17692f372e208d458ed2d6c-31205379096465.png)](https://files.readme.io/d56f170695893dbbde00c50c838ce8a5c2cfe418a17692f372e208d458ed2d6c-31205379096465.png)

AppsFlyer Context 変数のマッピングについては、以下の表を参照してください：

| **マッピングの推奨名称** | **コンバージョンデータ** |
| --- | --- |
| AppsFlyer ルックバック期間 | appsflyer.af\_click\_lookback |
| AppsFlyer インストール時間 | appsflyer.install\_time |
| AppsFlyer コストセント米国 | appsflyer.cost\_cents\_USD |
| AppsFlyer メディアソース | appsflyer.media\_source |
| AppsFlyer 広告 | appsflyer.af\_adset |
| AppsFlyer クリック時間 | appsflyer.click\_time |
| AppsFlyer オリジナル・コスト | appsflyer.orig\_cost |
| AppsFlyer キャンペーン | appsflyer.campaign |

<div id="using-appsflyer-mapped-conversion-data-for-analytics-and-analysis" />

### AppsFlyer のマッピングされたコンバージョンデータを分析および解析に使用する

SDK から送られてくるすべてのデータは、アプリに接続されている Adobe Analytics のレポート・スイートで利用できます。

生成された Adobe Analytics レポートや管理画面で、データと関連するディメンションおよびメトリクスを使用できます。このデータは、アトリビューションやアプリ内イベント分析のために、AppsFlyer の管理画面でも利用できます。

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01HQQN1Y7MP7B0GXJFP5330G80=%E6%A6%82%E8%A6%81 h_01HQQNCMYNN0YH7S8Q5F2EWFG5=%E6%B3%A8 prerequisites=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01HQQN1JWAQZZ9S3YV7VXTMRWM=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01HQQN1JWA4JYET26CB11JGY46=get-your-appsflyer-dev-key h_01HQQN1JWAHYQBRY43EWANQ57Z=get-your-app-id step-1-configuring-adobe-launch=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971adobe-launch-%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HQQN1JWAAR873B679QGA9NSX=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971adobe-launch-%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HQQN1JWAE1T7SP3DHTFB55TK=11-creating-a-new-property-in-adobe-launch h_01HQQN1JWA8FDWMNZ4Y17AWYKW=12-installing-required-adobe-launch-extensions installing-adobe-analytics-extension=adobe-analytics-%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BD%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB h_01HQQN1JWAMB8607K8V2F3YKHE=adobe-analytics-%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BD%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB installing-appsflyer-sdk-extension=appsflyer-sdk-%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BD%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB h_01HQQN1JWAYHP9243MTFZ4B2EF=appsflyer-sdk-%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BD%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB install-profile-and-mobile-core-extension=%E3%83%97%E3%83%AD%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%A8%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%B3%E3%82%A2%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BD%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB h_01HQQN1JWA1TEBQY1NH3YP2HQB=%E3%83%97%E3%83%AD%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%A8%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%B3%E3%82%A2%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BD%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB step-2-implementing-appsflyer-adobe-sdk-extension=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972appsflyer-adobe-sdk-%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BD%E3%81%AE%E5%AE%9F%E8%A3%85 h_01HQQN1JWB3B24RHP9QMNPJK8J=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972appsflyer-adobe-sdk-%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BD%E3%81%AE%E5%AE%9F%E8%A3%85 h_01HQQN1JWBMP4ARMH2VPX35TGH=21-adding-the-sdk-to-the-app h_01HQQN1JWBV3144WY92PAX6PW2=22-publishing-the-environment h_01HQQN1JWBRRCTGA6Q9RDC41KN=23-adding-android-install-referrer-to-your-app h_01HQQN1JWB40T4K3ZJB6AE42WQ=%E6%B3%A8-1 h_01HQQN1JWB19NTCNTWX9QRP8AC=24-setting-required-permissions add-required-permissions=%E5%BF%85%E9%A0%88%E3%83%91%E3%83%BC%E3%83%9F%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E8%BF%BD%E5%8A%A0 h_01HQQN1JWBVVVGRRXGX9ZJTBT8=%E5%BF%85%E9%A0%88%E3%83%91%E3%83%BC%E3%83%9F%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E8%BF%BD%E5%8A%A0 using-the-adobe-sdk-extension=adobe-sdk-%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BD%E3%81%AE%E4%BD%BF%E7%94%A8 h_01HQQN1JWBFD2CZ4PMCBRM3JN8=adobe-sdk-%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BD%E3%81%AE%E4%BD%BF%E7%94%A8 h_01HQQN1JWBSBVFVB911WH54Q32=%E6%B3%A8-2 h_01HQQN1JWBVZDAVAZD4NXMBG4S=sending-events h_01HQQN1JWBXG0JCE9RKA659H6V=getting-data-for-deep-linking-and-deferred-deep-linking connecting-appsflyer-conversion-data=appsflyer-%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97 h_01HQQN1JWBMBXGQFKGWHE058VT=appsflyer-%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97 using-appsflyer-mapped-conversion-data-for-analytics-and-analysis=appsflyer-%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%81%95%E3%82%8C%E3%81%9F%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%88%86%E6%9E%90%E3%81%8A%E3%82%88%E3%81%B3%E8%A7%A3%E6%9E%90%E3%81%AB%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B h_01HQQN1JWB0WBD6HZXQN6STJY9=appsflyer-%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%81%95%E3%82%8C%E3%81%9F%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%88%86%E6%9E%90%E3%81%8A%E3%82%88%E3%81%B3%E8%A7%A3%E6%9E%90%E3%81%AB%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B" />
