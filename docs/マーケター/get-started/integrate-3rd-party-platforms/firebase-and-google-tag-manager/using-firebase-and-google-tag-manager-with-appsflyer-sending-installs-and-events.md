---
title: AppsFlyerでのFirebaseとGoogleタグマネージャーの活用｜インストールとイベントの送信
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:31:07Z'
  edited_at: '2026-10-28T09:04:13Z'
  id: 4410481550609
  locale: ja
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/ja/articles/4410481550609
---
> **概要：** Firebase SDKで記録したイベントをAppsFlyerに送信するための、アプリ側の設定手順を説明します。

## アプリでのイベントの設定

このセクションでは、Googleタグマネージャー（GTM）を使用する場合に、アプリでイベントを設定・作成する方法を説明します。

イベントが送信されると、GTMはイベントトリガーを使って、そのイベントを処理するタグが設定されているか確認します。イベントトリガーは、特定のイベントが送信されるたびにタグを発火させるよう設定します。送信されたイベントに対応するトリガーがあると、タグが発火します。タグが発火すると、Googleタグマネージャーがイベント内のすべてのデータを収集します。このデータには、AppsFlyer ID、イベント名、イベントパラメータなどが含まれます。データをすべて収集すると、GoogleタグマネージャーがAppsFlyerにイベントを送信します。

<div id="creating-event-variables-for-revenue-and-price" />

<Accordion title="収益と価格のイベント変数の作成">

#### Android

<Tabs>
<Tab title="Java">

1. MainActivityクラスに、AppsFlyer Device IDを保持する変数を作成します。  

   ```java
   public static String appsFlyerID;
   ```
2. MainActivityクラスの`onCreate`メソッドで、`super.onCreate`の後にAppsFlyer IDを変数に渡します。

   ```java
   appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this);
   ```

</Tab>

<Tab title="Kotlin">

1. MainActivityクラスに、AppsFlyer Device IDを保持する変数を作成します。  

   ```kotlin
   var appsFlyerID: String? = null
   ```
2. MainActivityクラスの`onCreate`メソッドで、`super.onCreate`の後にAppsFlyer IDの値を変数に渡します。

   ```kotlin
   override fun onCreate(savedInstanceState: Bundle?) {
    ...
    appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this)
   }
   ```

</Tab>
</Tabs>

#### iOS

iOSでは、アプリ全体からパラメータを利用できます。 AppsFlyerTrackerのインスタンスから取得できます。

<Tabs>
<Tab title="Objective C">

1. AppsFlyerデバイスID：

   ```objectivec
   [AppsFlyerTracker sharedTracker].getAppsFlyerUID
   ```
2. Apple App ID：

   ```objectivec
   [AppsFlyerTracker sharedTracker].appleAppID
   ```

</Tab>

<Tab title="Swift">

1. AppsFlyerデバイスID：

   ```swift
    AppsFlyerTracker.shared().getAppsFlyerUID()
   ```
2. Apple App ID：

   ```swift
   AppsFlyerTracker.shared().appleAppID
   ```

</Tab>
</Tabs>

</Accordion>

<div id="adding-events-in-the-app" />

<Accordion title="アプリへのイベントの追加">

まず、アプリでイベントを設定します。イベントはFirebaseのイベントロギング機能を使って送信します。イベントにはAppsFlyer ID、イベント名、イベントパラメータを指定します。 AppsFlyer IDは、<Anchor target="_blank" href="/marketers/ja/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup#googleタグマネージャーの設定">設定手順</Anchor>で作成した変数から取得します。

<Anchor target="_blank" href="https://developers.google.com/tag-manager/ios/v5/#log-events-and-variables">GoogleタグマネージャーはFirebase Analyticsの</Anchor>イベントをきっかけにタグを発火させます。 Firebaseにイベントが送信されるたびに、タグマネージャーがイベントを認識し、AppsFlyerにも送信します。

#### Android

<Tabs>
<Tab title="Java">

1. 対象のアクティビティに、Firebaseのimport文を追加します。  

   ```java
   import com.google.firebase.analytics.FirebaseAnalytics;
   ```
2. 購入イベントが発生するたびに実行されるよう、以下のコードを追加します。

   ```java
   Bundle bundle = new Bundle();
     // notice "af_id", this is the name of the event parameter 
     // for AppsFlyer ID that we created in the previous step
     bundle.putString("af_id", appsFlyerID);
     bundle.putString("af_revenue", "200");
     bundle.putString("af_price", "250");
     mFirebaseAnalytics.logEvent("af_purchase", bundle);
   ```

</Tab>

<Tab title="Kotlin">

1. 対象のアクティビティに、Firebaseのimport文を追加します。  

   ```kotlin
   import com.google.firebase.analytics.FirebaseAnalytics
   ```
2. 購入イベントが発生するたびに実行されるよう、以下のコードを追加します。

   ```kotlin
   val bundle = Bundle()
     // notice "af_id", this is the name of the event parameter
     // for AppsFlyer ID that we created in the previous step
     bundle.putString("af_id", appsFlyerID)
     bundle.putString("af_revenue", "200")
     bundle.putString("af_price", "250")
     FirebaseAnalytics.getInstance(this).logEvent("af_purchase", bundle)
   ```

</Tab>
</Tabs>

iOS

<Tabs>
<Tab title="Objective-C">

1. イベントを送信するビューに`@import Firebase`を追加します。
2. 購入イベントが発生するたびに実行されるよう、以下のコードを追加します。

   ```objectivec
   NSString *id_prefix = @"id";  
   NSString *apple_app_id = [id_prefix stringByAppendingString:[AppsFlyerTracker sharedTracker].appleAppID];  

   [FIRAnalytics logEventWithName:@"af_purchase"
         parameters:@{
          @"apple_app_id": apple_app_id,
          @"af_id": [AppsFlyerTracker sharedTracker].getAppsFlyerUID,
          @"af_revenue": @250,
          @"af_price": @375
       }];
   ```

</Tab>

<Tab title="Swift">

1. イベントを送信するビューに`import Firebase`を追加します。
2. 購入イベントが発生するたびに実行されるよう、以下のコードを追加します。

   ```swift
   Analytics.logEvent("af_purchase", parameters: [
          "apple_app_id": "id" + AppsFlyerTracker.shared().appleAppID,
          "af_id": AppsFlyerTracker.shared().getAppsFlyerUID(),
          "af_revenue": 250,
          "af_price": 375
       ]);
   ```

</Tab>
</Tabs>

</Accordion>

## Firebaseへのインストールイベントの送信

インストールに関するすべてのデータを含むインストールイベントを、Firebaseに送信することもできます。

#### Android

<Tabs>
<Tab title="Java">

AndroidでインストールイベントをFirebaseに送信するには、`conversionData`オブジェクトを使用できます。

#### イベント送信用メソッドの作成

`AFApplication`クラスの`onCreate`メソッドのすぐ下に、以下のメソッドを追加します。

```java
public void sendInstallToFirebase(Map<String, String> conversionData){
       mFirebaseAnalytics = FirebaseAnalytics.getInstance(this);
       Bundle bundle = new Bundle();
       bundle.putString("install_time", conversionData.get("install_time") == null ? String.valueOf(new Date().getTime()) : conversionData.get("install_time"));
       bundle.putString("click_time", conversionData.get("click_time"));
       bundle.putString("media_source", conversionData.get("media_source") == null ? "organic": conversionData.get("media_source"));
       bundle.putString("campaign", conversionData.get("campaign") == null ? "organic": conversionData.get("campaign"));
       bundle.putString("install_type", conversionData.get("af_status"));
       mFirebaseAnalytics.logEvent("install", bundle);
    }
```

このメソッドは、`conversionData`オブジェクトを受け取ります。このメソッドは、インストール時刻、メディアソース、キャンペーンがnullかどうかを確認します。nullの場合、インストール時刻を現在時刻に、メディアソースとキャンペーンをorganicに設定します。それ以外の場合は、`conversionData`オブジェクトからデータを取得し、Firebaseに送信します。

#### インストールイベントの送信

`onConversionDataSuccess`メソッドに、以下のコードを追加します。

```java
if(conversionData.get("is_first_launch").equals("true")){
       sendInstallToFirebase(conversionData);
    }
```

このコードは、アプリの初回起動かどうかを確認します。条件に該当する場合は、`sendInstallToFirebase`メソッドを呼び出します。

</Tab>

<Tab title="Kotlin">

AndroidでインストールイベントをFirebaseに送信するには、`conversionData`オブジェクトを使用できます。

#### イベント送信用メソッドの作成

`AFApplication`クラスの`onCreate`メソッドのすぐ下に、以下のメソッドを追加します。

```kotlin
fun sendInstallToFirebase(conversionData: Map<String, Any>) {
      val bundle = Bundle()
      bundle.putString("install_time", conversionData["install_time"]?.toString() ?: Date().time.toString())
      bundle.putString("click_time", conversionData["click_time"]?.toString())
      bundle.putString("media_source", conversionData["media_source"]?.toString() ?: "organic")
      bundle.putString("campaign", conversionData["campaign"]?.toString() ?: "organic")
      bundle.putString("install_type", conversionData["af_status"]?.toString())
      FirebaseAnalytics.getInstance(this).logEvent("install", bundle)
  }
```

このメソッドは、`conversionData`オブジェクトを受け取ります。このメソッドは、インストール時刻、メディアソース、キャンペーンがnullかどうかを確認します。nullの場合、インストール時刻を現在時刻に、メディアソースとキャンペーンをorganicに設定します。それ以外の場合は、`conversionData`オブジェクトからデータを取得し、Firebaseに送信します。

#### インストールイベントの送信

`onConversionDataSuccess`メソッドに、以下のコードを追加します。

```kotlin
if(conversionData?.get("is_first_launch") == true){
      sendInstallToFirebase(conversionData);
  }
```

このコードは、アプリの初回起動かどうかを確認します。条件に該当する場合は、`sendInstallToFirebase`メソッドを呼び出します。

**注意：** SDK V5以降では、コンバージョンデータを取得するメソッド名は`onConversionDataSuccess`です。 SDKバージョン5.0.0より前を使用している場合、メソッド名は`onInstallConversionDataLoaded`です。 SDK 5.0.0へのアップグレードを推奨します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/links-to-appsflyer-sdk-release-notes">こちら</Anchor>を参照してください。

</Tab>
</Tabs>

#### iOS

<Tabs>
<Tab title="Objective-C">

#### イベント送信用メソッドの作成

AppDelegate.mファイルの末尾に、次のメソッドを追加します。

```objectivec
- (void)sendInstallToFirebase:(NSDictionary *)installData{
      NSDateFormatter *dateFormatter = [[NSDateFormatter alloc] init];
      [dateFormatter setDateFormat:@"dd/MM/yyyy HH:mm:ss"];
      NSDate *date = [NSDate date];
      NSString *newDate = [dateFormatter stringFromDate:date];

      if([[installData objectForKey: @"af_status"] isEqual: @"Organic"]){
        [FIRAnalytics logEventWithName:@"install"
         parameters:@{
          @"install_time": newDate,
          @"media_source": @"organic",
          @"campaign": @"organic"

        }];
      }
      else {
        [FIRAnalytics logEventWithName:@"install"
          parameters:@{
          @"install_time": [installData objectForKey: @"install_time"],
          @"click_time": [installData objectForKey: @"click_time"],
          @"install_type": [installData objectForKey: @"af_status"],
          @"media_source": [installData objectForKey: @"media_source"],
          @"campaign": [installData objectForKey: @"campaign"]
        }];
      }
    }
```

このメソッドは`installData`オブジェクトを受け取り、インストールがオーガニックかどうかを確認します。オーガニックの場合は、インストール時刻を現在の時刻に設定し、メディアソース、キャンペーン、インストールタイプをorganicに設定します。

非オーガニックインストールの場合、対応する非オーガニックインストールのデータを取得します。

パラメータを設定すると、このメソッドがFirebaseにインストールイベントを送信します。

#### インストールイベントの送信

AppDelegate.mの`didFinishLaunchingWithOptions`メソッドに、`[FIRApp configure]`を追加します。

AppDelegate.mの`onConversionDataSuccess`メソッドの末尾に、次のコードを追加します。

```objectivec
if([installData objectForKey:@"is_first_launch"]){
      [self sendInstallToFirebase: installData];
    }
```

上記のコードは、アプリの初回起動かどうかを確認します。条件に該当する場合は、`sendInstallToFirebase`メソッドを呼び出します。

</Tab>

<Tab title="Swift">

AppDelegate.swiftファイルの末尾に、次のメソッドを追加します。

```swift
func sendInstallToFirebase(_ installData: [AnyHashable : Any]!){

        let date = Date()
        let dateFormatter = DateFormatter()
        dateFormatter.dateFormat = "dd/MM/yyyy hh:mm:ss"
        let _newDate: String = dateFormatter.string(from: date)

        if(installData["af_status"] as? String == "Organic"){
          Analytics.logEvent("install", parameters: [
            "install_time": _newDate,
            "media_source": "organic",
            "campaign": "organic"
          ]);
        } else {
          Analytics.logEvent("install", parameters: [
            "install_time": installData["install_time"],
            "click_time": installData["click_time"],
            "media_source": installData["media_source"],
            "campaign": installData["campaign"],
            "install_type": installData["af_status"]
          ]);
        }

      }
```

**注意：** SDK V5以降では、コンバージョンデータを取得するメソッド名は`onConversionDataSuccess`です。 SDK V5.0.0未満では、メソッド名は`onConversionDataReceived`です。 SDK 5.0.0へのアップグレードを推奨します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/links-to-appsflyer-sdk-release-notes">こちら</Anchor>を参照してください。

このメソッドは`installData`オブジェクトを受け取り、インストールがオーガニックかどうかを確認します。オーガニックの場合は、インストール時刻を現在の時刻に設定し、メディアソース、キャンペーン、インストールタイプをorganicに設定します。

非オーガニックインストールの場合、対応する非オーガニックインストールのデータを取得します。

パラメータを設定すると、このメソッドがFirebaseにインストールイベントを送信します。

#### インストールイベントの送信

AppDelegate.swiftの`didFinishLaunchingWithOptions`メソッドに、`FirebaseApp.configure();`を追加します。

AppDelegate.swiftの`onConversionDataSuccess`メソッドの末尾に、次のコードを追加します。

```swift
if let is_first_launch = data["is_first_launch"] , let launch_code = is_first_launch as? Int {
      if(launch_code == 1){
        print("First Launch")
        sendInstallToFirebase(installData)
      } else {
        print("Not First Launch")
      }
    }
```

**注意：** SDK V5以降では、コンバージョンデータを取得するメソッド名は`onConversionDataSuccess`です。 SDK V5.0.0未満では、メソッド名は`onConversionDataReceived`です。 SDK 5.0.0へのアップグレードを推奨します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/links-to-appsflyer-sdk-release-notes">こちら</Anchor>を参照してください。

上記のコードは、アプリの初回起動かどうかを確認します。条件に該当する場合は、`sendInstallToFirebase`メソッドを呼び出します。

</Tab>
</Tabs>

> ❗️ **警告**
>
> 一部のメディアソースは、サードパーティのプラットフォームやサービスとのデータ共有を許可していません。 Meta広告、Twitter、Snap、Pinterestなど、サードパーティのプラットフォームやサービスへのデータ共有を制限しているパートナーを利用する場合は、必ず**各社のガイドラインに従い、制限対象のデータを除外してください**。
>
> * <Anchor target="_blank" href="https://www.facebook.com/privacy/policy/">Meta広告のデータポリシー</Anchor>
> * <Anchor target="_blank" href="https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html">Twitterのデータポリシー</Anchor>
> * <Anchor target="_blank" href="https://www.snap.com/en-US/privacy/privacy-policy/">Snapchatのデータポリシー</Anchor>
> * <Anchor target="_blank" href="https://policy.pinterest.com/en/privacy-policy">Pinterestのデータポリシー</Anchor>

<div data-zendesk-anchors="configuring-events-in-the-app=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%A7%E3%81%AE%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A 01H8H2MH93M1SB9HEQNHDDJZP0=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%A7%E3%81%AE%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A 01H8H2MH93D36ZH7788XCMHHV6=creating-event-variables-for-revenue-and-price 01H8H2MH93RNWN6N6EWE5T26V1=android 01H8H2MH93CZ5TACG3MWJ8YRFK=ios 01H8H2MH9340PQCCKB85BQZQEG=adding-events-in-the-app android::eb294e42=android-1 01H8H2MH9357Z5M1DBK4Z9N22P=android-1 sending-install-events-to-firebase=firebase%E3%81%B8%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%80%81%E4%BF%A1 01H8H2MH930VDZH5YSWEPTS8BN=firebase%E3%81%B8%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%80%81%E4%BF%A1 android::319436d3=android-2 01H8H2MH938Y980A9KA9BPP44Y=android-2 creating-the-send-event-method=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E9%80%81%E4%BF%A1%E7%94%A8%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AE%E4%BD%9C%E6%88%90 01H8H2MH932WYSS6Z5NZJ3195X=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E9%80%81%E4%BF%A1%E7%94%A8%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AE%E4%BD%9C%E6%88%90 sending-the-install-event=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%80%81%E4%BF%A1 01H8H2MH93H0WKMV5DAN713EY0=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%80%81%E4%BF%A1 creating-the-send-event-method::64b5a305=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E9%80%81%E4%BF%A1%E7%94%A8%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AE%E4%BD%9C%E6%88%90 01H8H2MH93VYXGMM5H6ZQWCFZY=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E9%80%81%E4%BF%A1%E7%94%A8%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AE%E4%BD%9C%E6%88%90 sending-the-install-event::aeb9cdb7=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%80%81%E4%BF%A1 01H8H2MH93VTPZNF51R05QPK7C=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%80%81%E4%BF%A1 ios::95ad6e27=ios-1 01H8H2MH93AQE7PKVW4QKD2ARN=ios-1 creating-the-send-event-method::346138b1=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E9%80%81%E4%BF%A1%E7%94%A8%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AE%E4%BD%9C%E6%88%90-2 01H8H2MH93NGBRHBDQTX4DKNTY=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E9%80%81%E4%BF%A1%E7%94%A8%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AE%E4%BD%9C%E6%88%90-2 sending-the-install-event::aca3c0e3=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%80%81%E4%BF%A1-2 01H8H2MH93SWYFF2KTC1HJ06FF=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%80%81%E4%BF%A1-2 sending-the-install-event::b6997ad3=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%80%81%E4%BF%A1-2 01H8H2MH93Y5J8QH0YBKPQSV5N=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%80%81%E4%BF%A1-2 01H8H2MH93JQBAR6ZTW77HHFQR=%E8%AD%A6%E5%91%8A" />
