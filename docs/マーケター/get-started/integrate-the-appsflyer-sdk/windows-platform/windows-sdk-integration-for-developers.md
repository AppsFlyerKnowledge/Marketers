---
title: 'iOS SDKの実装 : 開発者向け'
metadata:
  keywords:
    - SDK
    - Integration
    - Windows Phone
    - In-App
    - windows universal apps
    - windows 10
    - Advertisers
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
  created_at: '2015-05-07T12:17:52Z'
  edited_at: '2026-10-14T09:30:51Z'
  id: 207032026
  locale: ja
  section: Windows platform
  section_id: 6551223206417
  url: https://support.appsflyer.com/hc/ja/articles/207032026
---
> **概要：** 概要：AppsFlyerをWindows / Xboxアプリとゲームに追加して、アプリインストール、アプリ内イベント、メディアソースなどを計測しましょう。

現在のバージョン:2.4.110ドル - 20ドル

AppsFlyer SDKはアプリインストールとイベントを記録する機能を提供します。

![SDK_Integration.jpg](https://files.readme.io/11ef01abe55ae3d53d1a3756ffd24bf3262002c3970005cd70047c9d0665b5d1-360001586617.jpg)

インストール、アップデート、セッション (起動) に加え（以下の必須のステップを実行）、アプリ内イベント（アプリ内購入、ゲームレベルなど）も計測して、ROIやユーザーのエンゲージメントレベルを評価できます。

> 🚧 **重要！**
>
> AppsFlyer Windows SDKは、Windows携帯電話、Xbox、PC、HoloLens、Surface hubなど、全ての <Anchor target="_blank" href="https://docs.microsoft.com/en-us/windows/uwp/get-started/universal-application-platform-guide">Universal Windows Platform</Anchor> (UWP) デバイスと互換性があります。

## 1.連携手順

Windows Universal SDK はNuGet Package Manager経由でインストールされます。AppsFlyer Windows SDKをNuget経由でインストールする方法：

[![](https://files.readme.io/dcce7e82d681f6b0dfa5c6da26d183f331212dde51148d027d4dc75cb57d104a-21241904425489.png)](https://files.readme.io/dcce7e82d681f6b0dfa5c6da26d183f331212dde51148d027d4dc75cb57d104a-21241904425489.png)

1. プロジェクトファイルを右クリックしてください。
2. ***Manage NuGet Packages*** をクリックしてください。
3. ***Browse*** をクリックし、*AppsFlyerLib* を検索してください。
4. ***AppsFlyerLib*** をクリックしてください。
5. ***Install*** をクリックしてください。

NuGetパッケージを使用しない場合は、AppsFlyer SDKをアプリに手動で埋め込むことができます。

2. Copy the AppsFlyerLib.winmd をプロジェクトにコピーしてください。
3. Visual Studioで、Universal Windows Platformプロジェクトの ***Add Reference*** をクリックしてください。

[![](https://files.readme.io/5606c0bcbaaffdeea5b43f9b0201263a6ad3ab5a610ccb7b7389737e84c22844-21241888352273.png)](https://files.readme.io/5606c0bcbaaffdeea5b43f9b0201263a6ad3ab5a610ccb7b7389737e84c22844-21241888352273.png)

* AppsFlyerLib.winmd を見つけて、追加してください。

[![](https://files.readme.io/fe03e297291cab276977287701e46d950c7444a47d28c01a75f01112992b57a9-21241904443153.png)](https://files.readme.io/fe03e297291cab276977287701e46d950c7444a47d28c01a75f01112992b57a9-21241904443153.png)

> 🚧 **重要！**
>
> AppsFlyer は、Newtonsoft.json パッケージを使用してください。これは、Windows で Json を解析するための標準ライブラリです。このパッケージは、Visual Studio の NuGetを使用して追加できます。これにより、DLL内のファイルが見つかりません（File Not Found）の例外が解決されます。
>
> * Visual Studioにて、References を右クリックし、NuGet Package Newtonsoft.json を選択し追加してください。
> * アプリの Manifest、または Capabilities タブの Visual Studioでインターネットアクセスを許可してください。

## 2. 3. SDKの初期化＆インストールイベント（計測の最低必須要件）

* 以下のコードを App Launchメソッドに追加してください。
* appId と DevKey を設定してください。
  * tracker.appId and tracker.devKey に値を入力してください。
  * 管理画面のアプリ設定画面にてAppsFlyer DevKeyを取得できます。

```csharp
protected override void OnLaunched(LaunchActivatedEventArgs e)
{
	this .InitializeComponent();
	this .Suspending += this .OnSuspending;
	AppsFlyerLib. AppsFlyerTracker tracker =
	AppsFlyerLib. AppsFlyerTracker .GetAppsFlyerTracker();
	tracker.appId = "YOUR_APP_ID_HERE" ;
	tracker.devKey = "YOUR_DEV_KEY_HERE" ;
	tracker.trackAppLaunch();
}
```

### アプリ起動を非同期で記録する

アプリ起動をオフラインで記録できます。これはネットワークがダウンしているか応答しないときに役立ちます。

```csharp
tracker.TrackAppLaunchAsync(Callback);
public void Callback(AppsFlyerLib.ServerStatusCode code)
{
   if(code == AppsFlyerLib.ServerStatusCode.SUCCESS) {  
      //success scenario  
   } else if(code == AppsFlyerLib.ServerStatusCode.FAIL) {  
   //failure scenario  
   }
}
```

## 3.4. アプリ内イベントの記録API（オプション）

以下のコードを追加して、インストール後のイベントを記録してください。

```csharp
public void TrackEvent(string eventName, IDictionary<string, Object> eventValues)
```

* *eventName* はイベント名を定義する任意の文字列です。推奨するイベント名の一覧は<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">こちら</Anchor>を参照してください。
* *eventValues* はイベントを構成するイベントパラメーターのディクショナリです。推奨するパラメーターの一覧は<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">こちら</Anchor>を参照してください。
* 収益をアプリ内イベントの一部としてカウントする場合は、InAppEventParameterName.REVENUE (“af\_revenue”) という定数パラメーター名を使用してください。正負を問わず、あらゆる数値を入力できます。

> 📄 **例**
>
> ```csharp
> AppsFlyerLib.AppsFlyerTracker tracker = AppsFlyerLib.AppsFlyerTracker.GetAppsFlyerTracker();
>       IDictionary<string, object> eventValues = new Dictionary<string, object>();
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.CONTENT_ID, "id123");
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.REVENUE, "10");
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.CURRENCY, "USD");
>       tracker.TrackEvent(AppsFlyerLib.AFInAppEventType.ADD_TO_CART, eventValues);
> ```

### イベントを非同期で記録する

イベントをオフライン／非同期の状態で記録することができます。これはネットワークがダウンしているか応答しないときに役立ちます。

```csharp
tracker.TrackEventAsync(AppsFlyerLib.AFInAppEventType.PURCHASE, events, Callback);
public void Callback(AppsFlyerLib.ServerStatusCode code)
{
   if(code == AppsFlyerLib.ServerStatusCode.SUCCESS) {  
      //success scenario  
   } else if(code == AppsFlyerLib.ServerStatusCode.FAIL) {  
     //failure scenario  
   }
}
```

AppsFlyerのリッチアプリ内イベントの一覧は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">こちら</Anchor>を参照してください。

## 4. 5. 高度な実装

以下のAPIは任意で実装でき、AppsFlyer SDKの高度な実装の一部です。

### 5.1 通貨コードの設定（オプション）

AppsFlyerに送信される各アプリ内イベントの一部として使用できる特定の通貨コードに加えて、以下のAPIを使用して、グローバル通貨コードを設定することができます。

USD（米ドル）がデフォルトの値です。利用できるISO通貨コードは<Anchor target="_blank" href="http://www.xe.com/iso4217.php">こちら</Anchor>を参照してください。

通貨コードを設定するには、以下のAPIを使用してください。

```csharp
tracker.currencyCode = "GBP";
```

### 5.2 getAppsFlyeruid（オプション）

AppsFlyer Unique ID は全ての新しいアプリインストールに対して発行されます。

以下のAPIを使用してこのIDを取得してください。

```csharp
public string getAppsFlyerUID()
```

### 5.3 カスタマーユーザーID（CUID）（オプション）

独自のカスタマーIDを設定すると、独自の内部IDをAppsFlyerユーザーIDやその他のデバイスIDと相互参照できるようになります。このIDは、ポストバックAPIとともにAppsFlyerのCSVレポートで確認でき、貴社の内部IDと相互参照することができます。

カスタマーユーザーIDを設定するには：

```csharp
tracker.customerUserId = "YOUR_CUSTOMER_USER_ID";
```

### 5.4 GetConversionDataAsync（オプション）

このAPIを使用して、SDKを通じてインストールごとにコンバージョンデータを受け取ることができます。以下のコードを追加して、インストール後のイベントを記録してください。

```csharp
Task.Run(async () =>
{
   AppsFlyerLib.AppsFlyerTracker tracker = AppsFlyerLib.AppsFlyerTracker.GetAppsFlyerTracker();
   string conversionData = await tracker.GetConversionDataAsync();
});
```

この機能の詳細については、こちらを参照してください。

### 5.5 C++ / CX 実装の例

```csharp
AppsFlyerLib::AppsFlyerTracker^ tracker = AppsFlyerLib::AppsFlyerTracker::GetAppsFlyerTracker();
 tracker->appId = ref new Platform::String(L"APP_KEY");
 tracker->devKey = ref new Platform::String(L"APPSFLYER_KEY");
 tracker->TrackAppLaunch();
 create_task(tracker->GetConversionDataAsync()).then([tracker](Platform::String^ conversionData)
 {
 Windows::Foundation::Collections::IMap<Platform::String^, Platform::Object^>^ eventValues
 = ref new Platform::Collections::Map<Platform::String^, Platform::Object^>();

eventValues->Insert(AppsFlyerLib::AFInAppEventParameterName::CONTENT_ID, "134");
 eventValues->Insert(AppsFlyerLib::AFInAppEventParameterName::CONTENT_TYPE, "Virtual Goods");
 eventValues->Insert(AppsFlyerLib::AFInAppEventParameterName::CURRENCY, "USD");
 eventValues->Insert(AppsFlyerLib::AFInAppEventParameterName::REVENUE, "9.99");

tracker->TrackEvent(AppsFlyerLib::AFInAppEventType::PURCHASE, eventValues);
 });
```

<div data-zendesk-anchors="h_01H9G0X6VRCJCGHXWNJ2XFAQN9=%E9%87%8D%E8%A6%81 2-initial-steps=1%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 h_01H9G0X6VRQJ860K5QS7DE9DT4=1%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 h_01H9G0X6VRJ3KKZD6XM202NEX2=%E9%87%8D%E8%A6%81-1 3-sdk-initialization-installation-event-minimum-requirement-for-attributing=2-3-sdk%E3%81%AE%E5%88%9D%E6%9C%9F%E5%8C%96%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E8%A8%88%E6%B8%AC%E3%81%AE%E6%9C%80%E4%BD%8E%E5%BF%85%E9%A0%88%E8%A6%81%E4%BB%B6 h_01H9G0X6VR9FW15TYS06M3JBYM=2-3-sdk%E3%81%AE%E5%88%9D%E6%9C%9F%E5%8C%96%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E8%A8%88%E6%B8%AC%E3%81%AE%E6%9C%80%E4%BD%8E%E5%BF%85%E9%A0%88%E8%A6%81%E4%BB%B6 recording-app-launch%C2%A0asynchronously=%E3%82%A2%E3%83%97%E3%83%AA%E8%B5%B7%E5%8B%95%E3%82%92%E9%9D%9E%E5%90%8C%E6%9C%9F%E3%81%A7%E8%A8%98%E9%8C%B2%E3%81%99%E3%82%8B h_01H9G0X6VR6JHKGPTWERQGZNMW=%E3%82%A2%E3%83%97%E3%83%AA%E8%B5%B7%E5%8B%95%E3%82%92%E9%9D%9E%E5%90%8C%E6%9C%9F%E3%81%A7%E8%A8%98%E9%8C%B2%E3%81%99%E3%82%8B 4-inapp-event-recording-api-optional=34-%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%98%E9%8C%B2api%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 h_01H9G0X6VRSBKYX4AJK5ZQ14EK=34-%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%98%E9%8C%B2api%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 h_01H9G0X6VS1RA8K4EW4K1Q8B6P=%E4%BE%8B recording-events-asynchronously=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E9%9D%9E%E5%90%8C%E6%9C%9F%E3%81%A7%E8%A8%98%E9%8C%B2%E3%81%99%E3%82%8B h_01H9G0X6VS5PYNZEZG86QJTSPJ=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E9%9D%9E%E5%90%8C%E6%9C%9F%E3%81%A7%E8%A8%98%E9%8C%B2%E3%81%99%E3%82%8B 5-advanced-integration=4-5-%E9%AB%98%E5%BA%A6%E3%81%AA%E5%AE%9F%E8%A3%85 h_01H9G0X6VSW4A5B044HF1704XH=4-5-%E9%AB%98%E5%BA%A6%E3%81%AA%E5%AE%9F%E8%A3%85 51-set-currency-code-optional=51-%E9%80%9A%E8%B2%A8%E3%82%B3%E3%83%BC%E3%83%89%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 h_01H9G0X6VSY3975EZNGD2NDSMR=51-%E9%80%9A%E8%B2%A8%E3%82%B3%E3%83%BC%E3%83%89%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 52-getappsflyeruid-optional=52-getappsflyeruid%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 h_01H9G0X6VS4MF8S85049HFJD8K=52-getappsflyeruid%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 53-customer-user-id-optional=53-%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%9E%E3%83%BC%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BCidcuid%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 h_01H9G0X6VSM167RKESECBQCPZD=53-%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%9E%E3%83%BC%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BCidcuid%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 54-getconversiondataasync-optional=54-getconversiondataasync%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 h_01H9G0X6VSJWZ3BFWP4AFMZXXY=54-getconversiondataasync%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 55-c-cx-integration-example=55-c--cx-%E5%AE%9F%E8%A3%85%E3%81%AE%E4%BE%8B h_01H9G0X6VSRNZXN8A22Q8KYYJR=55-c--cx-%E5%AE%9F%E8%A3%85%E3%81%AE%E4%BE%8B" />
