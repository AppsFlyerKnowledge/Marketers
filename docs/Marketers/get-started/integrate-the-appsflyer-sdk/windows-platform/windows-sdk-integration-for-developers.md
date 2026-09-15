---
title: "Windows SDK integration for developers"
excerpt: "Learn how to integrate the AppsFlyer SDK into your Windows apps and games to measure installs, in-app events, and media sources."
---
**At a glance:** Add AppsFlyer to Windows apps and games to measure app installs, in-app events, media sources, and more.

**Current Version: 3.1.0 (17/12/2023)**

The AppsFlyer SDK provides app installation and event recording functionality.

![SDK_Integration.jpg](https://files.readme.io/11ef01abe55ae3d53d1a3756ffd24bf3262002c3970005cd70047c9d0665b5d1-360001586617.jpg)

You can record installs, updates, and sessions (by following the mandatory steps below), and also record additional in-app events beyond app installs (including in-app purchases, game levels, etc.) to evaluate ROI and user engagement levels.

> 📘 **Important!**
>
> The AppsFlyer Windows SDK is compatible with all [Universal Windows Platform](https://docs.microsoft.com/en-us/windows/uwp/get-started/universal-application-platform-guide) (UWP) devices, including Windows mobile phones, PC, HoloLens, and Surface hub.


## 1. Integration steps

The Windows Universal SDK is installed via the NuGet Package Manager. To install the AppsFlyer Windows SDK via Nuget:

[![](https://support.appsflyer.com/hc/article_attachments/21241904425489)](https://support.appsflyer.com/hc/article_attachments/21241904425489)

1. Right-click the project file.
2. Click ***Manage NuGet Packages***.
3. Click ***Browse*** and search for *AppsFlyerLib*.
4. Click the ***AppsFlyerLib***.
5. Click ***Install***.

If you choose to not use the NuGet package you can embed the AppsFlyer SDK into your app manually:

1. Download the Universal Windows Platform App SDK [from here](https://s3-eu-west-1.amazonaws.com/download.appsflyer.com/windows-phone-sdk/AF-Windows-SDK-v3.1.0.zip).
2. Copy the AppsFlyerLib.winmd into your project.
3. In Visual Studio, click ***Add Reference*** on the Universal Windows Platform project.

[![](https://support.appsflyer.com/hc/article_attachments/21241888352273)](https://support.appsflyer.com/hc/article_attachments/21241888352273)

* Locate AppsFlyerLib.winmd and add it.

[![](https://support.appsflyer.com/hc/article_attachments/21241904443153)](https://support.appsflyer.com/hc/article_attachments/21241904443153)

> 📘 **Important!**
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

```
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

```
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

```
public void TrackEvent(string eventName, IDictionary<string, Object> eventValues)
```

* *eventName* is any string that defines the event name. You can find a list of recommended event names [here](/docs/in-app-events-overview).
* *eventValues* is a dictionary of event parameters that comprise an event. You can find a list of recommended parameters [here](/docs/in-app-events-overview).
* When counting revenue as part of in-app events, use InAppEventParameterName.REVENUE (“af\_revenue”) constant parameter name to count revenue as part of an in-app event. You can populate it with any numeric value, positive or negative.

> 📘 **Example**
>
> ```
> AppsFlyerLib.AppsFlyerTracker tracker = AppsFlyerLib.AppsFlyerTracker.GetAppsFlyerTracker();
>       IDictionary<string, object> eventValues = new Dictionary<string, object>();
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.CONTENT_ID, "id123");
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.REVENUE, "10");
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.CURRENCY, "USD");
>       tracker.TrackEvent(AppsFlyerLib.AFInAppEventType.ADD_TO_CART, eventValues);
> ```


### Recording events asynchronously

You can record events asynchronously. This is useful in cases when the network is down or unresponsive. You can handle such cases in the Callback function that you pass to the `TrackEventAsync` method.

```
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

For a complete list of AppsFlyer rich in-app events, click [here](/docs/in-app-events-overview).

## 4. Advanced integration

The following APIs are optional and are part of the advanced integration with AppsFlyer SDK.

### 4.1 set currency code (optional)

You can set a global currency code using the API below, in addition to specific currency codes that can be used as part of each in-app event sent to AppsFlyer.

USD is the default value. Acceptable ISO currency codes can be found [here](http://www.xe.com/iso4217.php).

Use the following API to set the currency code:

```
tracker.currencyCode = "GBP";
```

### 4.2 getAppsFlyeruid (optional)

An AppsFlyer Unique ID is created for every new install of an app.

Use the following API In order to get this ID:

```
public string getAppsFlyerUID()
```

### 4.3 Customer User ID (optional)

Setting your own customer ID enables you to cross-reference your own unique ID with the AppsFlyer user ID and all other device IDs. This ID is available in the AppsFlyer CSV reports along with postbacks APIs for cross-referencing with your internal IDs.

To set your Customer User ID:

```
tracker.customerUserId = "YOUR_CUSTOMER_USER_ID";
```

### 4.4 GetConversionDataAsync (optional)

You can receive the conversion data for every install through the SDK using this API. Add the following code to record post-install events:

```
Task.Run(async () =>
{
   AppsFlyerLib.AppsFlyerTracker tracker = AppsFlyerLib.AppsFlyerTracker.GetAppsFlyerTracker();
   string conversionData = await tracker.GetConversionDataAsync();
});
```

### 4.5 C++ / CX integration example

```
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