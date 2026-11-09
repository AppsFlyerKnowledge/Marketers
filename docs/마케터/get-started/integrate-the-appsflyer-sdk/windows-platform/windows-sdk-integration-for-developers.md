---
title: AppsFlyer SDK 연동 가이드 - iOS
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
  edited_at: '2026-10-14T10:33:30Z'
  id: 207032026
  locale: ko
  section: Windows platform
  section_id: 6551223206417
  url: https://support.appsflyer.com/hc/ko/articles/207032026
---
> **한눈에 보기:**

0 - 5달러

앱스플라이어 SDK는 앱 설치와 인앱 이벤트 측정 기능을 제공합니다.

<Image align="center" alt="SDK_Integration.jpg" src="https://files.readme.io/11ef01abe55ae3d53d1a3756ffd24bf3262002c3970005cd70047c9d0665b5d1-360001586617.jpg" />

앱스플라이어 SDK를 통해 설치, 업데이트, 세션을 기록할 수 있고, 또한 앱 설치 이 외에도 인앱 구매나 게임 레벨 달성과 같은 인앱 이벤트를 추가로 기록하여 ROI 및 사용자 인게이지먼트 수준을 파악할 수 있습니다.

<div id="important-1" />

<div id="1-integration-steps" />

## 1. 통합 단계

<Image align="center" alt="" src="https://files.readme.io/dcce7e82d681f6b0dfa5c6da26d183f331212dde51148d027d4dc75cb57d104a-21241904425489.png" />

[altalt](https://support.appsflyer.com/hc/article_attachments/51857613739153)

[altalt](https://support.appsflyer.com/hc/article_attachments/51857613739409)

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

* 양수 또는 음수의 모든 숫자를 입력할 수 있습니다.

<div id="recording-events-asynchronously" />

<div id="example" />

> 📄 **예시**
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

## 4. 고급 연동


<span id="41-set-currency-code-optional"></span><span id="51-set-currency-code-optional"></span>AppsFlyer로 전송된 각 인앱이벤트의 일부로 사용할 수 있는 특정 통화 코드 이외에도 다음 API를 이용해서 국제 통화 코드를 설정할 수 있습니다.

통화 코드를 설정하려면 다음의 API를 사용하세요:

```csharp
tracker.currencyCode = "GBP";
```


<span id="42-getappsflyeruid-optional"></span><span id="52-getappsflyeruid-optional"></span>고유 앱스플라이어 ID가 앱이 새로 설치될 때마다 발급됩니다.

```csharp
public string getAppsFlyerUID()
```


<span id="43-customer-user-id-optional"></span><span id="53-customer-user-id-optional"></span>이 ID는 내부 ID와 상호 참조할 수 있도록 포스트백 API와 AppsFlyer CSV 보고서에 보여집니다.

다음을 통해 고객 사용자 ID를 설정하세요:

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

<div data-zendesk-anchors="2-initial-steps=1-%ED%86%B5%ED%95%A9-%EB%8B%A8%EA%B3%84 h_01H9G0X6VRQJ860K5QS7DE9DT4=1-%ED%86%B5%ED%95%A9-%EB%8B%A8%EA%B3%84 h_01H9G0X6VRJ3KKZD6XM202NEX2=1-%ED%86%B5%ED%95%A9-%EB%8B%A8%EA%B3%84 3-sdk-initialization-installation-event-minimum-requirement-for-attributing=2 h_01H9G0X6VR9FW15TYS06M3JBYM=2 recording-app-launch%C2%A0asynchronously=2 h_01H9G0X6VR6JHKGPTWERQGZNMW=2 4-inapp-event-recording-api-optional=3 h_01H9G0X6VRSBKYX4AJK5ZQ14EK=3 h_01H9G0X6VS1RA8K4EW4K1Q8B6P=%EC%98%88%EC%8B%9C recording-events-asynchronously=%EC%98%88%EC%8B%9C h_01H9G0X6VS5PYNZEZG86QJTSPJ=%EC%98%88%EC%8B%9C 5-advanced-integration=4-%EA%B3%A0%EA%B8%89-%EC%97%B0%EB%8F%99 h_01H9G0X6VSW4A5B044HF1704XH=4-%EA%B3%A0%EA%B8%89-%EC%97%B0%EB%8F%99 h_01H9G0X6VSY3975EZNGD2NDSMR=51-set-currency-code-optional h_01H9G0X6VS4MF8S85049HFJD8K=52-getappsflyeruid-optional h_01H9G0X6VSM167RKESECBQCPZD=53-customer-user-id-optional 54-getconversiondataasync-optional=4-%EA%B3%A0%EA%B8%89-%EC%97%B0%EB%8F%99 h_01H9G0X6VSJWZ3BFWP4AFMZXXY=4-%EA%B3%A0%EA%B8%89-%EC%97%B0%EB%8F%99 55-c-cx-integration-example=4-%EA%B3%A0%EA%B8%89-%EC%97%B0%EB%8F%99 h_01H9G0X6VSRNZXN8A22Q8KYYJR=4-%EA%B3%A0%EA%B8%89-%EC%97%B0%EB%8F%99" />
