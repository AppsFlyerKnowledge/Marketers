---
title: 适用于开发者的IOS SDK 对接
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
  edited_at: '2026-10-14T10:07:35Z'
  id: 207032026
  locale: zh-cn
  section: Windows platform
  section_id: 6551223206417
  url: https://support.appsflyer.com/hc/zh-cn/articles/207032026
---
> **概要：**

6257(1)

AppsFlyer SDK为移动应用提供安装和应用内事件的追踪。

您可以追踪安装、更新和互动以及应用安装以外的其他应用内事件（包括应用内购买、游戏级别等），以评估 ROI 和用户互动水平。

<div id="important-1" />

<div id="1-integration-steps" />

## 1. 对接流程

<Image align="center" alt="" src="https://files.readme.io/dcce7e82d681f6b0dfa5c6da26d183f331212dde51148d027d4dc75cb57d104a-21241904425489.png" />

<Image align="center" alt="" src="https://files.readme.io/5606c0bcbaaffdeea5b43f9b0201263a6ad3ab5a610ccb7b7389737e84c22844-21241888352273.png" />

<Image align="center" alt="" src="https://files.readme.io/fe03e297291cab276977287701e46d950c7444a47d28c01a75f01112992b57a9-21241904443153.png" />

<div id="recording-app-launchasynchronously" />

<div id="2-sdk-initialization--installation-event-minimum-requirement-for-attributing" />

## 2.

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

<div id="3-in-app-event-recording-api-optional" />

## 3.

```csharp
public void TrackEvent(string eventName, IDictionary<string, Object> eventValues)
```

* 您可以输入任意正负数值。

<div id="recording-events-asynchronously" />

<div id="example" />

> 📄 **示例**
>
> ```csharp
> AppsFlyerLib.AppsFlyerTracker tracker = AppsFlyerLib.AppsFlyerTracker.GetAppsFlyerTracker();
>       IDictionary<string, object> eventValues = new Dictionary<string, object>();
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.CONTENT_ID, "id123");
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.REVENUE, "10");
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.CURRENCY, "USD");
>       tracker.TrackEvent(AppsFlyerLib.AFInAppEventType.ADD_TO_CART, eventValues);
> ```


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

<div id="45-c--cx-integration-example" />

<div id="44-getconversiondataasync-optional" />

<div id="4-advanced-integration" />

## 4. 高级对接


<span id="41-set-currency-code-optional"></span><span id="51-set-currency-code-optional"></span>除了随着应用内事件发送到 AppsFlyer 的指定货币代码外，您还可以使用下面的 API 来设置全球货币代码。

使用以下 API 设置货币代码：

```csharp
tracker.currencyCode = "GBP";
```


<span id="42-getappsflyeruid-optional"></span><span id="52-getappsflyeruid-optional"></span>用户每次安装一个应用后，AF都会为其匹配一个非重的AppsFlyer ID。

```csharp
public string getAppsFlyerUID()
```


<span id="43-customer-user-id-optional"></span><span id="53-customer-user-id-optional"></span>该 ID 可以通过 Postback API 在 AppsFlyer CSV 报告中得到，用于与您的内部 ID 交叉引用。

请按以下方式设置您的客户用户ID：

```csharp
tracker.customerUserId = "YOUR_CUSTOMER_USER_ID";
```


```csharp
Task.Run(async () =>
{
   AppsFlyerLib.AppsFlyerTracker tracker = AppsFlyerLib.AppsFlyerTracker.GetAppsFlyerTracker();
   string conversionData = await tracker.GetConversionDataAsync();
});
```


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

<div data-zendesk-anchors="2-initial-steps=1-%E5%AF%B9%E6%8E%A5%E6%B5%81%E7%A8%8B h_01H9G0X6VRQJ860K5QS7DE9DT4=1-%E5%AF%B9%E6%8E%A5%E6%B5%81%E7%A8%8B h_01H9G0X6VRJ3KKZD6XM202NEX2=1-%E5%AF%B9%E6%8E%A5%E6%B5%81%E7%A8%8B 3-sdk-initialization-installation-event-minimum-requirement-for-attributing=2 h_01H9G0X6VR9FW15TYS06M3JBYM=2 recording-app-launch%C2%A0asynchronously=2 h_01H9G0X6VR6JHKGPTWERQGZNMW=2 4-inapp-event-recording-api-optional=3 h_01H9G0X6VRSBKYX4AJK5ZQ14EK=3 h_01H9G0X6VS1RA8K4EW4K1Q8B6P=%E7%A4%BA%E4%BE%8B recording-events-asynchronously=%E7%A4%BA%E4%BE%8B h_01H9G0X6VS5PYNZEZG86QJTSPJ=%E7%A4%BA%E4%BE%8B 5-advanced-integration=4-%E9%AB%98%E7%BA%A7%E5%AF%B9%E6%8E%A5 h_01H9G0X6VSW4A5B044HF1704XH=4-%E9%AB%98%E7%BA%A7%E5%AF%B9%E6%8E%A5 h_01H9G0X6VSY3975EZNGD2NDSMR=51-set-currency-code-optional h_01H9G0X6VS4MF8S85049HFJD8K=52-getappsflyeruid-optional h_01H9G0X6VSM167RKESECBQCPZD=53-customer-user-id-optional 54-getconversiondataasync-optional=4-%E9%AB%98%E7%BA%A7%E5%AF%B9%E6%8E%A5 h_01H9G0X6VSJWZ3BFWP4AFMZXXY=4-%E9%AB%98%E7%BA%A7%E5%AF%B9%E6%8E%A5 55-c-cx-integration-example=4-%E9%AB%98%E7%BA%A7%E5%AF%B9%E6%8E%A5 h_01H9G0X6VSRNZXN8A22Q8KYYJR=4-%E9%AB%98%E7%BA%A7%E5%AF%B9%E6%8E%A5" />
