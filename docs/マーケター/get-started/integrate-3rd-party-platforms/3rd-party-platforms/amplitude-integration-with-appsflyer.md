---
title: AmplitudeとAppsFlyerの連携
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Amplitude
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
  created_at: '2016-08-02T05:18:03Z'
  edited_at: '2026-10-28T09:02:40Z'
  id: 211200306
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/211200306
---
> **At a glance:** AppsFlyerとAmplitudeを連携すると、ユーザーのアトリビューションデータとイベント分析データを共有し、エンゲージメント、継続率、収益をより詳しく分析できます。用途や分析の目的に応じて、**V1またはV2のいずれかの連携方式**を選択してください。

<div id="about-the-integration" />

## 連携の概要

AppsFlyerの連携済みパートナーであるAmplitudeは、プロダクト、グロース、マーケティングの各チームが、モバイルとWebにおけるユーザー行動を把握するためのプロダクト分析プラットフォームです。この連携により、AppsFlyerからインストール後の主要なイベントデータをAmplitudeに送信し、ユーザー単位で詳しく分析できます。

Amplitudeとの連携には、次の2つのバージョンがあります。

* **Amplitude V1：**  
  AmplitudeのAttribution APIを使用します。 AppsFlyerは、連携の設定完了後に収集したインストールデータを送信します。 Amplitudeは広告IDを識別子として使用します。72時間以内に一致するユーザーイベントが記録されなければ、データは破棄されます。<Anchor target="_blank" href="https://amplitude.com/docs/apis/analytics/attribution">詳細を見る</Anchor>
* **Amplitude V2：**  
  AmplitudeのHTTP V2 APIを使用します。 AppsFlyerは、連携の設定完了後にインストールとアプリ内イベントの両方のデータを送信します。識別子（user\_idとdevice\_id）には優先順位があり、一致するユーザーが見つからない場合は新規ユーザーとして記録されます。<Anchor target="_blank" href="https://amplitude.com/docs/apis/analytics/http-v2">詳細を見る</Anchor>

<span id="h_01JSE81SX1FR182N1CZJ5CQP5N"></span>**<span id="integration-methods"></span>連携バージョンの比較：**

| バージョン | 使用するAPI | 使用する識別子 | 対象イベント |
| --- | --- | --- | --- |
| **V1** | Attribution API | 広告ID（AdID） | インストールのみ |
| **V2** | HTTP V2 API | `user_id`、`device_id`（優先する識別子が使えない場合は別の識別子を使用） | インストールとアプリ内イベント |

> 🚧 **Important**
>
> **重要**
>
> * Amplitude V1またはV2のいずれかを選択してください。**両方を同時に使用しないでください**。両方のバージョンを同時に使用すると、Amplitudeにイベントが重複して送信されることがあります。
> * 一部のメディアソースでは、第三者とのデータ共有が制限されています。共有が制限されているイベントのポストバックは、設定済みでもこのパートナーには送信されません。

<div id="prerequisites" />

## 前提条件

**設定を始める前に：**

* Amplitudeのアカウントをお持ちでない場合は、Amplitudeに問い合わせて作成してください。
* Amplitudeの**V1**と**V2**のどちらを設定するか決めます。
* 重複を防ぐため、Amplitude SDKとAppsFlyerの両方から同じイベントを送信しないようにしてください。
* Amplitude V2連携の追加の前提条件も確認してください。

<div id="additional-prerequisites-for-the-amplitude-v2-integration" />

### Amplitude V2連携の追加の前提条件

V2連携では、次の設定が必要です。

* [AmplitudeデバイスID](/docs/amplitude-integration-with-appsflyer#amplitudeデバイスid)
* [カスタマーユーザーID](/docs/amplitude-integration-with-appsflyer#カスタマーユーザーid)
* [AmplitudeセッションID](/docs/amplitude-integration-with-appsflyer#amplitudeセッションid)

<div id="amplitude-device-id" />

#### AmplitudeデバイスID

ユーザー単位のアトリビューションを有効にするには、Amplitude Device IDをAppsFlyer SDKに渡す必要があります。この値は、各ポストバックで送信されます。

<Tabs>
<Tab title="Android">

```java
AppsFlyerLib.getInstance().setAdditionalData("AmplitudeDeviceId", amplitude.getDeviceId())
```

**言語：** Java/Kotlin

**ドキュメント：** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata">Android SDKリファレンス</Anchor>, <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/android/android-kotlin-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="iOS (Objective-C)">

```objectivec
[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeDeviceId": [[Amplitude instance] getDeviceId]}];
```

**言語：** Objective-C

**ドキュメント：** [iOS SDKリファレンス](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata), <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="iOS (Swift)">

```swift
AppsFlyerLib.shared().customData = ["AmplitudeDeviceId": Amplitude.instance().getDeviceId()]
```

**言語：** Swift

**ドキュメント：** [iOS SDKリファレンス](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata), <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> customData = new Dictionary<string, string>();
customData.Add("AmplitudeDeviceId", Amplitude.getInstance().getDeviceId());
AppsFlyer.setAdditionalData(customData);
```

**言語：** C#

**ドキュメント：** [Unity SDKリファレンス](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>

<Tab title="React Native">

```javascript
appsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()},
(res) => {
//...
}
);
```

**言語：** JavaScript

**ドキュメント：** [React Native SDKリファレンス](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin)

</Tab>

<Tab title="Cordova">

```javascript
appsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()});
```

**言語：** JavaScript

**ドキュメント：** N/A

</Tab>

<Tab title="Flutter">

```
var data = {"AmplitudeDeviceId": amplitude.getDeviceId()};
appsFlyerSdk.setAdditionalData(data);
```

**言語：** Dart

**ドキュメント：** [Flutter SDKリファレンス](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

<div id="customer-user-id" />

#### カスタマーユーザーID

カスタマーユーザーID（CUID）を設定します。通常、アプリの所有者がユーザー登録時に生成・設定する  
一意の識別子です。<Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid?utm_source=chatgpt.com">詳細を見る</Anchor>

<div id="amplitude-session-id" />

#### AmplitudeセッションID

AmplitudeのセッションIDを設定し、AppsFlyerに渡します。<Anchor target="_blank" href="https://amplitude.com/docs/data/sources/instrument-track-sessions">詳細を見る</Anchor>

<Tabs>
<Tab title="Android">

```java
AppsFlyerLib.getInstance().setAdditionalData("AmplitudeSessionId", amplitude.getSessionId())
```

**言語：** Java/Kotlin

**ドキュメント：** [Android SDKリファレンス](https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata)

</Tab>

<Tab title="iOS (Objective-C)">

```objectivec
[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeSessionId": [[Amplitude instance] getSessionId]}];
```

**言語：** Objective-C

**ドキュメント：** [iOS SDKリファレンス](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>

<Tab title="iOS (Swift)">

```swift
AppsFlyerLib.shared().customData = ["AmplitudeSessionId": Amplitude.instance().getSessionId()]
```

**言語：** Swift

**ドキュメント：** [iOS SDKリファレンス](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> customData = new Dictionary<string, string>();
customData.Add("AmplitudeSessionId", Amplitude.getInstance().getSessionId());
AppsFlyer.setAdditionalData(customData);
```

**言語：** C#

**ドキュメント：** [Unity SDKリファレンス](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>

<Tab title="React Native">

```javascript
appsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()},
(res) => {
//...
}
);
```

**言語：** JavaScript

**ドキュメント：** [React Native SDKリファレンス](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin)

</Tab>

<Tab title="Cordova">

```javascript
appsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()});
```

**言語：** JavaScript

**ドキュメント：** N/A

</Tab>

<Tab title="Flutter">

```
var data = {"AmplitudeSessionId": amplitude.getSessionId()};
appsFlyerSdk.setAdditionalData(data);
```

**言語：** Dart

**ドキュメント：** [Flutter SDKリファレンス](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

<div id="set-up-the-integration" />

## 連携の設定

**連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで<strong>［連携］</strong>＞<strong>［パートナー連携］＞［マーケットプレイス］</strong>タブに移動します。
2. Amplitude V1連携を設定する場合は、**Amplitude V1**（テクノロジーパートナー）を選択します。

   <Image alt="Select Amplitude V1 doctored.png" src="https://files.readme.io/71721bb1a48dda061ce2a099522edf9baed39ef2d67edad8ac14277b42cd2d70-36713632837777.png" width="511px" />

   Amplitude V2連携を設定する場合は、**Amplitude V2**（テクノロジーパートナー）を選択します。

   <Image alt="Select Amplitude V2.png" src="https://files.readme.io/4bbf57727a2b6e16e5205505b459a78f8642f02d1bb1c4e8f72e26b3bd9e1bd3-36713631187857.png" width="503px" />
3. Amplitudeのバージョンを選択したら、<strong>［連携を設定］</strong>をクリックします。

   ![Click set up integration.png](https://files.readme.io/c13fef10fb4cf0ea12f44d56f8c3b64936376ce181a1d12c9f096ad6103c29a6-36713632857617.png)
4. <strong>［連携］</strong>タブで、次の設定を行います。
   * 対象のアプリを選択します。
   * <strong>［パートナーを有効化］</strong>をオンにします。

     <Image alt="Activate partner blurred.png" src="https://files.readme.io/5e0e7ae537cd89b2c561c8561de9ebc160f6d6eb0fedc5c7ba0c761ddb73632a-36713631194641.png" width="521px" />
5. 残りのタブで設定を完了します。

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

<div id="activate-partner" />

### パートナーを有効化

**初めて設定する場合**は、<strong>［パートナーを有効化］</strong>をオンにすると、［連携］タブのパラメータを設定できます。このパートナーと連携している間は、オンにしておく必要があります。  
詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">パートナーの有効化</Anchor>を参照してください。

<div id="general-settings" />

### 一般設定

<div id="advanced-data-sharing" />

#### 拡張データ共有

追加のインストール情報をAmplitudeと共有するには、<strong>［拡張データ共有］</strong>をオンにします。オンにすると、インストールについて次のデータがAmplitudeに送信され、表に記載されたAmplitudeプロパティに対応付けられます。アプリ内イベントは対象外です。

| Amplitudeプロパティ | AppsFlyerのデータ項目 |
| --- | --- |
| sub\_publisher | af\_siteid |
| network\_name | pid |
| adgroup\_name | af\_adset |
| creative\_name | af\_ad\_id |
| installed\_at | install\_timestamp |
| search\_term | af\_keywords |
| channel | af\_channel |
| user\_id | af\_customer\_user\_id |
| af\_sub1 | af\_sub1 |
| af\_sub2 | af\_sub2 |
| af\_sub3 | af\_sub3 |
| af\_sub4 | af\_sub4 |
| af\_sub5 | af\_sub5 |
| app\_version | app\_version |

<div id="amplitude-eu-data-center" />

#### AmplitudeのEUデータセンター

<strong>［Amplitude EU Data Center］</strong>がオフの場合、インストールポストバックは米国のデータセンターに送信されます。  
AmplitudeのEUデータセンターにインストールポストバックを送信するには、［Amplitude EU Data Center］をオンにします。

<div id="api-key" />

#### APIキー

AmplitudeとAppsFlyerの接続には、固有のAPIキーを使用します。まだ取得していない場合は、連携の設定を進める前にAmplitudeから取得するか、以下の手順で取得してください。

<span id="obtaining-the-api-key-from-amplitude"></span>**AmplitudeからAPIキーを取得する**

**注意**：APIキーにアクセスできるのは、AmplitudeでAdminまたはManagerのロールを持つユーザーのみです。

1. Amplitudeアカウントにログインします。
2. ページ右上の設定アイコン＞**Organization Settings**をクリックします。

   <Image alt="Amplitude" src="https://files.readme.io/214df773c045239924b65a4a1e6b0a1957f6b7ea09e225af80d83ffa0a469c26-16258070772625.png" width="240px" />
3. **Projects**をクリックし、AppsFlyerにデータを送信するプロジェクトを選択します。

   ![amplitude](https://files.readme.io/eaf158e4505f47f8da0fdae4f97be773ab32910352b50cab5ca5d4de3e8782ac-16335170399505.png)
4. **Project**タブからAPIキーをコピーします。

   <Image alt="Amplitude" src="https://files.readme.io/cf65648a9a8c122febe2b36fd4bd0b9f7f436cac49cfeec7f41870f614a16c6c-16258070773649.png" width="648px" />
5. AppsFlyer管理画面でAmplitudeの設定に進みます。

<div id="default-postbacks" />

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にAmplitudeへポストバックを自動送信できます。インストールとリエンゲージメント（リアトリビューションを含む）が対象です。リエンゲージメントとは、すでにアプリをインストールしているユーザーが、キャンペーンをクリックした後にアプリを開くことです。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#default-postbacks">デフォルトポストバック</Anchor>を参照してください。

<Image alt="Screenshot 2025-12-03 at 1.57.03 PM.png" src="https://files.readme.io/3454ca573ee63ea076251459a9c619a747fc5640862e83582b2d10a985c2489a-41748033847953.png" width="703px" />

<div id="in-app-event-settings" />

### アプリ内イベントの設定

* APIキーを入力します。
* <strong>［Amplitude Data Center］</strong>がオフの場合、アプリ内イベントのポストバックは米国のデータセンターに送信されます。  
  **AmplitudeのEUデータセンターにアプリ内イベントのポストバックを送信するには、［Amplitude Data Center］をオンにします。**

設定を保存すると、AppsFlyerからAmplitudeに次のデータが送信されます。

* デバイスID（IDFV／Google広告ID）
* メディアソース
* キャンペーン名

iOSデバイスのIDFAを送信できるかどうかは、<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">ユーザーのATT同意と高度なプライバシー設定</Anchor>によって決まります。

<div id="in-app-event-postbacks" />

### アプリ内イベントポストバック

Amplitudeへの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">アプリ内イベントポストバックの送信を設定</Anchor>します。

</Accordion>

<Accordion title="計測リンクタブ">

Amplitudeでは、計測リンクは利用できません。

</Accordion>

<Accordion title="コストタブ">

このパートナーとの連携では、コストデータには対応していません。

</Accordion>

<Accordion title="広告収益タブ">

このパートナーとの連携では、広告収益データには対応していません。

</Accordion>

<Accordion title="権限タブ">

Amplitudeでは、権限の設定は利用できません。

</Accordion>

<div id="viewing-attribution-data-in-the-amplitude-console" />

## Amplitudeコンソールでアトリビューションデータを確認する

AppsFlyerからAmplitudeに送信されたアトリビューションデータは、ダッシュボードに **[AppsFlyer]** で始まるイベントやプロパティとして表示されます。

![amplitude-properties.png](https://files.readme.io/bf52831ea6060172ce251136f47962ffb7f1ec9ffce13b9e35c614c4178e77f1-360009623597.png)

> 🚧 **Important**
>
> **重要**
>
> AppsFlyerから送信されたデータが、Amplitudeで「Blocked」と表示される場合があります。 AmplitudeでAppsFlyerのデータが表示されない場合は、ブロック対象のイベントに設定されていないか確認してください。

<div id="sending-amplitude-events-to-appsflyer" />

## AmplitudeのイベントをAppsFlyerに送信する

この連携では、サーバー間APIを使用してAmplitudeのイベントをAppsFlyerに送信することもできます。手順については、<Anchor target="_blank" href="https://www.docs.developers.amplitude.com/data/destinations/appsflyer/">Amplitudeのドキュメント</Anchor>を参照してください。

<div data-zendesk-anchors="about-the-integration=%E9%80%A3%E6%90%BA%E3%81%AE%E6%A6%82%E8%A6%81 h_01JSE81SX1B1RH978Y08W1XXX8=%E9%80%A3%E6%90%BA%E3%81%AE%E6%A6%82%E8%A6%81 set-up-the-integration=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01JSE958V510B9P6VEQTXC55S7=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 additional-prerequisites-for-the-v2-integration=amplitude-v2%E9%80%A3%E6%90%BA%E3%81%AE%E8%BF%BD%E5%8A%A0%E3%81%AE%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01JSKEMMEB00PERVQWPYNF5V2E=amplitude-v2%E9%80%A3%E6%90%BA%E3%81%AE%E8%BF%BD%E5%8A%A0%E3%81%AE%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 amplitude-device-id=amplitude%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9id h_01JSKFH7KPSE5P0CRPVJ3FJ2WN=amplitude%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9id customer-user-id=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%9E%E3%83%BC%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BCid h_01JSKFK4BFH3PP98XAZ0W8GG11=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%9E%E3%83%BC%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BCid amplitude-session-id=amplitude%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3id h_01JSKFQXPPJVCW68C4H9B4EJ76=amplitude%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3id set-up-the-integration::45aa5acf=%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01JSKFQAZ8Q76KF1JJKZTAPVBQ=%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 01H8KPA9JKDRA680Y0WPZ172EM=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A 01H8KPA9JKF4VCA4S22SYT40WT=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A advanced-data-sharing=%E6%8B%A1%E5%BC%B5%E3%83%87%E3%83%BC%E3%82%BF%E5%85%B1%E6%9C%89 01H8KPA9JKJ2XN1AEPV74QVJYZ=%E6%8B%A1%E5%BC%B5%E3%83%87%E3%83%BC%E3%82%BF%E5%85%B1%E6%9C%89 amplitude-data-center=amplitude%E3%81%AEeu%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BB%E3%83%B3%E3%82%BF%E3%83%BC 01H8KPA9JKP0T0FDND97VA23EY=amplitude%E3%81%AEeu%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BB%E3%83%B3%E3%82%BF%E3%83%BC api-key=api%E3%82%AD%E3%83%BC 01H8KPA9JKDYDPDGRXZSH2BAV8=api%E3%82%AD%E3%83%BC 01H8KPA9JK510YKV47816DT7E7=obtaining-the-api-key-from-amplitude default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H8KRBGYQ973CT3H8GHZ8R0BH=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-event-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A 01H8KPA9JKM4S79160BEYN3B6V=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H8KSQ76XE9Z191P1RMANF6EQ=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF viewing-attribution-data-in-the-amplitude-console=amplitude%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%81%A7%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B 01H8KPA9JK75TA0H8T4P65BMSE=amplitude%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%81%A7%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B sending-amplitude-events-to-appsflyer=amplitude%E3%81%AE%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92appsflyer%E3%81%AB%E9%80%81%E4%BF%A1%E3%81%99%E3%82%8B h_01HPYFZDX1WWDWJEBZ4DK706B4=amplitude%E3%81%AE%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92appsflyer%E3%81%AB%E9%80%81%E4%BF%A1%E3%81%99%E3%82%8B" />
