---
title: Windows SDK integration for developers
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
  edited_at: '2026-05-25T10:09:27Z'
  id: 207032026
  locale: en-us
  section: Windows platform
  section_id: 6551223206417
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207032026-Windows-SDK-integration-for-developers
---
**At a glance:** Add AppsFlyer to Windows apps and games to measure app installs, in-app events, media sources, and more.

**Current Version: 3.1.0 (17/12/2023)**

The AppsFlyer SDK provides app installation and event recording functionality.

![SDK_Integration.jpg](https://files.readme.io/11ef01abe55ae3d53d1a3756ffd24bf3262002c3970005cd70047c9d0665b5d1-360001586617.jpg)

You can record installs, updates, and sessions (by following the mandatory steps below), and also record additional in-app events beyond app installs (including in-app purchases, game levels, etc.) to evaluate ROI and user engagement levels.

> 🚧 **Important!**
>
> The AppsFlyer Windows SDK is compatible with all <Anchor target="_blank" href="https://docs.microsoft.com/en-us/windows/uwp/get-started/universal-application-platform-guide">Universal Windows Platform</Anchor> (UWP) devices, including Windows mobile phones, PC, HoloLens, and Surface hub.

## 1. Integration steps

The Windows Universal SDK is installed via the NuGet Package Manager. To install the AppsFlyer Windows SDK via Nuget:

[![](https://files.readme.io/dcce7e82d681f6b0dfa5c6da26d183f331212dde51148d027d4dc75cb57d104a-21241904425489.png)](https://files.readme.io/dcce7e82d681f6b0dfa5c6da26d183f331212dde51148d027d4dc75cb57d104a-21241904425489.png)

1. Right-click the project file.
2. Click ***Manage NuGet Packages***.
3. Click ***Browse*** and search for *AppsFlyerLib*.
4. Click the ***AppsFlyerLib***.
5. Click ***Install***.

If you choose to not use the NuGet package you can embed the AppsFlyer SDK into your app manually:

1. Download the Universal Windows Platform App SDK <Anchor target="_blank" href="https://s3-eu-west-1.amazonaws.com/download.appsflyer.com/windows-phone-sdk/AF-Windows-SDK-v3.1.0.zip">from here</Anchor>.
2. Copy the AppsFlyerLib.winmd into your project.
3. In Visual Studio, click ***Add Reference*** on the Universal Windows Platform project.

[![](https://files.readme.io/5606c0bcbaaffdeea5b43f9b0201263a6ad3ab5a610ccb7b7389737e84c22844-21241888352273.png)](https://files.readme.io/5606c0bcbaaffdeea5b43f9b0201263a6ad3ab5a610ccb7b7389737e84c22844-21241888352273.png)

* Locate AppsFlyerLib.winmd and add it.

[![](https://files.readme.io/fe03e297291cab276977287701e46d950c7444a47d28c01a75f01112992b57a9-21241904443153.png)](https://files.readme.io/fe03e297291cab276977287701e46d950c7444a47d28c01a75f01112992b57a9-21241904443153.png)

> 🚧 **Important!**
>
> AppsFlyer uses a Newtonsoft.json package. This is a standard library for parsing Json in Windows. You can add this package using NuGet in Visual Studio. This solves the File Not Found exception in the DLL.
>
> * In Visual Studio, right-click References and select NuGet Package Newtonsoft.json and add it.
> * Allow Internet access in the app manifest, or use Visual Studio in the Capabilities tab.

## 2. SDK initialization & installation event (minimum requirement for attributing)

* Add the following code into your App Launch method.
* Set your appId and DevKey:
  * Populate tracker.appId and tracker.devKey with your values.
  * You can get your AppsFlyer DevKey on our dashboard under SDK Integration.

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

### Recording App Launch Asynchronously

You can record app launch asynchronously. This is useful in cases when the network is down or unresponsive. You can handle such cases in the Callback function that you pass to the `TrackAppLaunchAsync` method.

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

## 3. In-app event recording API (optional)

This API enables AppsFlyer to record post-install events. These events are defined by the advertiser and include an event name in addition to optional event values. Add the following code to record post-install events:

```csharp
public void TrackEvent(string eventName, IDictionary<string, Object> eventValues)
```

* *eventName* is any string that defines the event name. You can find a list of recommended event names <Anchor target="_blank" href="/marketers/docs/in-app-events-overview">here</Anchor>.
* *eventValues* is a dictionary of event parameters that comprise an event. You can find a list of recommended parameters <Anchor target="_blank" href="/marketers/docs/in-app-events-overview">here</Anchor>.
* When counting revenue as part of in-app events, use InAppEventParameterName.REVENUE (“af\_revenue”) constant parameter name to count revenue as part of an in-app event. You can populate it with any numeric value, positive or negative.

> 📄 **Example**
>
> ```csharp
> AppsFlyerLib.AppsFlyerTracker tracker = AppsFlyerLib.AppsFlyerTracker.GetAppsFlyerTracker();
>       IDictionary<string, object> eventValues = new Dictionary<string, object>();
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.CONTENT_ID, "id123");
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.REVENUE, "10");
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.CURRENCY, "USD");
>       tracker.TrackEvent(AppsFlyerLib.AFInAppEventType.ADD_TO_CART, eventValues);
> ```

### Recording events asynchronously

You can record events asynchronously. This is useful in cases when the network is down or unresponsive. You can handle such cases in the Callback function that you pass to the `TrackEventAsync` method.

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

For a complete list of AppsFlyer rich in-app events, click <Anchor target="_blank" href="/marketers/docs/in-app-events-overview">here</Anchor>.

## 4. Advanced integration

The following APIs are optional and are part of the advanced integration with AppsFlyer SDK.

### 4.1 set currency code (optional)

You can set a global currency code using the API below, in addition to specific currency codes that can be used as part of each in-app event sent to AppsFlyer.

USD is the default value. Acceptable ISO currency codes can be found <Anchor target="_blank" href="http://www.xe.com/iso4217.php">here</Anchor>.

Use the following API to set the currency code:

```csharp
tracker.currencyCode = "GBP";
```

### 4.2 getAppsFlyeruid (optional)

An AppsFlyer Unique ID is created for every new install of an app.

Use the following API In order to get this ID:

```csharp
public string getAppsFlyerUID()
```

### 4.3 Customer User ID (optional)

Setting your own customer ID enables you to cross-reference your own unique ID with the AppsFlyer user ID and all other device IDs. This ID is available in the AppsFlyer CSV reports along with postbacks APIs for cross-referencing with your internal IDs.

To set your Customer User ID:

```csharp
tracker.customerUserId = "YOUR_CUSTOMER_USER_ID";
```

### 4.4 GetConversionDataAsync (optional)

You can receive the conversion data for every install through the SDK using this API. Add the following code to record post-install events:

```csharp
Task.Run(async () =>
{
   AppsFlyerLib.AppsFlyerTracker tracker = AppsFlyerLib.AppsFlyerTracker.GetAppsFlyerTracker();
   string conversionData = await tracker.GetConversionDataAsync();
});
```

### 4.5 C++ / CX integration example

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

<div data-zendesk-anchors="h_01H9G0X6VRCJCGHXWNJ2XFAQN9=important 2-initial-steps=1-integration-steps h_01H9G0X6VRQJ860K5QS7DE9DT4=1-integration-steps h_01H9G0X6VRJ3KKZD6XM202NEX2=important-1 3-sdk-initialization-installation-event-minimum-requirement-for-attributing=2-sdk-initialization--installation-event-minimum-requirement-for-attributing h_01H9G0X6VR9FW15TYS06M3JBYM=2-sdk-initialization--installation-event-minimum-requirement-for-attributing recording-app-launch%C2%A0asynchronously=recording-app-launchasynchronously h_01H9G0X6VR6JHKGPTWERQGZNMW=recording-app-launchasynchronously 4-inapp-event-recording-api-optional=3-in-app-event-recording-api-optional h_01H9G0X6VRSBKYX4AJK5ZQ14EK=3-in-app-event-recording-api-optional h_01H9G0X6VS1RA8K4EW4K1Q8B6P=example h_01H9G0X6VS5PYNZEZG86QJTSPJ=recording-events-asynchronously 5-advanced-integration=4-advanced-integration h_01H9G0X6VSW4A5B044HF1704XH=4-advanced-integration 51-set-currency-code-optional=41-set-currency-code-optional h_01H9G0X6VSY3975EZNGD2NDSMR=41-set-currency-code-optional 52-getappsflyeruid-optional=42-getappsflyeruid-optional h_01H9G0X6VS4MF8S85049HFJD8K=42-getappsflyeruid-optional 53-customer-user-id-optional=43-customer-user-id-optional h_01H9G0X6VSM167RKESECBQCPZD=43-customer-user-id-optional 54-getconversiondataasync-optional=44-getconversiondataasync-optional h_01H9G0X6VSJWZ3BFWP4AFMZXXY=44-getconversiondataasync-optional 55-c-cx-integration-example=45-c--cx-integration-example h_01H9G0X6VSRNZXN8A22Q8KYYJR=45-c--cx-integration-example" />
