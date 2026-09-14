---
title: "Adobe Launch SDK extension"
excerpt: "Send data to Adobe Launch SDK and AppsFlyer SDK with the single implementation of AppsFlyer Adobe Launch SDK Extension."
---
## Overview

The Adobe Launch SDK is an integral part of the Adobe Experience Platform. Adobe Experience Platform helps businesses gather, consolidate, and analyze data from multiple apps and platforms. It allows business owners and developers to better understand customer behavior in order to optimize experience and content delivery. If your app implements both the Adobe Launch SDK and the AppsFlyer SDK, you can send data to both with a single implementation of **AppsFlyer Adobe Launch SDK Extension**. It reduces the overall complexity of your development process and makes for a cleaner and maintainable codebase.

> 📘 Note
>
> If you're using the Adobe Launch extension, there's no need for the standard [Adobe Analytics integration](https://support.appsflyer.com/hc/articles/115003326706).

## Prerequisites

A few things are required before integrating AppsFlyer Adobe SDK Extension.

Get your AppsFlyer dev key

![dev_key.png](https://files.readme.io/bf25b5d583f3eaab57c230b68764f08c49806a50401955a511993d8a847e7d42-360006050318.png)

1. In your app's dashboard, click on _**App Settings**_ under _**Configuration**_ in the left-hand menu.
2. Under _**SDK Installation**_, copy the _**Dev Key**_.

Get your app ID

- For Android - the app ID is the package name, e.g. example.com.app.
- For iOS - the app ID is the app's iTunes ID without the _id_ prefix, e.g. 123456748.

## Step 1: Configuring Adobe Launch

Follow the instructions here to configure Adobe Launch.

1.1 Creating a new property in Adobe Launch

![Creating a new property in Adobe Launch](https://files.readme.io/d03e61047c536785e7601d4f0efbd9b6488bd41c92efdd6e0d1021b42a5bec3a-small-360005983477.png)

1. Log in to Adobe Experience Cloud.
2. Select _**Launch**_.
3. Click _**Go to Launch**_.
4. Click _**New Property**_.
5. Give the property a name and select _**Mobile**_.
6. Click _**Save**_.

1.2 Installing required Adobe Launch extensions

Install the following extensions in Adobe Launch:

![adboe_extensions.png](https://files.readme.io/bf0c0652c3807d4da0819a62b600ac875af1f8764387a36cc3f256a58e1ea852-360005983597.png)

- Adobe Analytics - connects the recorded data from the SDK to the Adobe Analytics module.
- AppsFlyer SDK Extension - sends data and events to both Adobe and AppsFlyer using the Adobe Launch SDK.
- Adobe Profile - allows the SDK to store data into a client-side profile.
- Adobe Mobile Core - allows configuration of the mobile SDK and provides access to default lifecycle events and conditions.

#### Installing Adobe Analytics extension

1. Log in to Adobe Analytics.
2. [Create a report suite](https://docs.adobe.com/help/en/analytics/admin/admin-console/create-report-suite.html).
3. Log back into Adobe Launch.
4. From the list of properties, click on the property that you created earlier.
5. Click _**Extensions**_.
6. Search for and install _**Adobe Analytics**_.
7. Under _**Report Suites**_, specify the report suite that you created in step 2.
8. Click _**Save**_.

#### Installing AppsFlyer SDK Extension

1. Select _**Extensions**_ again.
2. Search for and install _**AppsFlyer SDK Extension**_.
3. Under _**AppsFlyer iOS App ID**_, specify the iOS app ID that you got in the prerequisites step.
4. Under _**AppsFlyer Dev Key**_ specify the dev key that you got in the prerequisites step.
5. Enable _**Send attribution data to Adobe Analytics**_. Note that there are some [restrictions on sharing user-level data with 3rd-party analytics platforms](https://support.appsflyer.com/hc/articles/360006091197).
6. Click _**Save**_.

#### Install Profile and Mobile Core extension

1. Select _**Extensions**_ again.
2. Search for and install _**Profile**_.
3. Search for and install _**Mobile Core**_.
   - When installing Mobile Core, simply save the extension as is. There is no need to specify the _**Experience Cloud Server**_.

## Step 2: Implementing AppsFlyer Adobe SDK Extension

Follow the instructions in this section to Implement the Adobe SDK Extension into your app.

2.1 Adding the SDK to the app

![adobe_sdk.png](https://files.readme.io/076e6cc5911a0a515e5510a8da233bcefcb4144c92cf49190416b593fcdecc8f-small-360006050518.png)

1. Inside your Adobe property, select _**Environments**_.
2. Select the environment for which you want to deploy the SDK.
3. On the right-hand side, click the box icon.
4. Copy the code snippets from the window that opens and follow the instructions. If you're the marketer configuring Adobe, send these code snippets to your app developer.

2.2 Publishing the environment

To complete the SDK implementation, you need to publish the environment to a library.

![adobe_publishing.png](https://files.readme.io/4e9ad08fce291ef59e7a3567726c678754ae3a3c96de75f4ae27cd80a84945d1-small-360006050558.png)

1. Inside your Adobe property, select _**Publishing**_.
2. Click _**Add New Library**_.
3. Give it a name and under Environment, select _**Development**_.
4. Click _**Save & Build for Development**_.
5. Once the build completes, under _**Development**_, click the three dots next to the library and select _**Submit for Approval**_.
6. Under _**Submitted**_, click the three dots next to the library and select _**Build for Staging**_.
7. Once the build completes, click the three dots next to the library and select _**Approve for Publishing**_.
8. Under _**Approve**_, click the three dots next to the library and select _**Build & Publish to Production**_.

2.3 Adding Android install referrer to your app

The Android Install Referrer improves attribution accuracy, protects from install fraud, and more. It is supported from AppsFlyer Android SDK version 4.8.6.

> 📘 Note
>
> Google deprecated the [BroadcastReceiver](https://android-developers.googleblog.com/2019/11/still-using-installbroadcast-switch-to.html) in March 2020.
>
> - This change does not affect the app.
> - You may still need the BroadcastReceiver for out-of-store attribution. Check with the store where the app is listed to make sure.
> - Implementing the install referrer is now mandatory.

There are two ways to add the install referrer to your app:

<Tabs>
<Tab title="Adding the install referrer using Gradle">

Add the Android Install Referrer as a dependency. You can find the latest version [here](https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0).

1. 
```java
dependencies {
//make sure to use the latest SDK version: https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk
   	implementation 'com.appsflyer:af-android-sdk:5.+'
   	implementation 'com.android.installreferrer:installreferrer:1.1'
}
```

2. Sync the project to retrieve the dependencies - see the following screenshot:
![android_af_sdk_sync_gradle.png](https://files.readme.io/f8835cf76d51d7ddeb51206707d95b7214e398c5960299893118ad57ccffe890-22939234622609.png)

If you are using ProGuard and want to use Google's new referrer API, set the following ProGuard rule: `-dontwarn com.android.installreferrer`

</Tab>
<Tab title="Manually adding the install referrer">

1. [Download the Install Referrer aar](https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0)
2. [Add it to the project](https://stackoverflow.com/questions/16682847/how-to-manually-include-external-aar-package-using-new-gradle-android-build-syst)
3. Add the following permission to the manifest: `com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE`

</Tab>
</Tabs>

2.4 Setting required permissions

Adding permissions helps increase the rate of [Probabilistic modeling attribution](https://support.appsflyer.com/hc/articles/207447053-AppsFlyer-s-Attribution-Model#probabilistic-modeling). It also allows the SDK to send more data like Wifi and carrier network data. You can find this data in [raw data reports](https://support.appsflyer.com/hc/articles/209680773) and use it for analysis and optimization of campaigns.

#### Add Required Permissions

1. Add the following permissions to AndroidManifest.xml:

```markup
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
<uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
<!-- Optional : -->
<uses-permission android:name="android.permission.READ_PHONE_STATE" />
```

## Using the Adobe SDK extension

Now you can start using the Adobe SDK extension to send data to Adobe and AppsFlyer.

> 📘 Note
>
> Currently, the Adobe Launch SDK extension only supports getting conversion data and sending events. However, when you add Adobe Launch SDK extension to your app, AppsFlyer SDK is also added. Therefore, any functionality currently missing from Adobe SDK extension can be implemented using AppsFlyer SDK.

Sending events

In-App events provide insight into what is happening in your app. We recommend taking the time and defining the events you want to record. Recording in-app events helps you measure KPIs such as ROI (Return on Investment) and LTV (Lifetime Value).

Adobe Launch SDK extension allows you to send in-app event data to both Adobe and AppsFlyer. You can then use Adobe Analytics to analyze user behavior and AppsFlyer to analyze ROI and LTV.

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

Sending the events as specified in the code above creates an event in AppsFlyer dashboard called af\_purchase with a revenue of 200 USD. This event is also sent to and appears in Adobe Analytics.

All [conversion data](https://dev.appsflyer.com/docs/direct-deep-linking-1) that is sent with events is prefixed by _**appsflyer**_. See the following table for examples:

| Prefixed conversion data variables |
| --- |
| appsflyer.af\_click\_lookback |
| appsflyer.install\_time |
| appsflyer.cost\_cents\_USD |
| appsflyer.media\_source |
| appsflyer.af\_adset |
| appsflyer.click\_time |
| appsflyer.orig\_cost |
| appsflyer.campaign |

Conversion data is available in the Analysis Workspace in Adobe Analytics. For more information about how to migrate Adobe Mobile Services processing rules to Adobe Analytics, see [the Adobe documentation](https://experienceleague.adobe.com/en/docs/analytics/technotes/migrate-mobile).

Getting data for deep linking and deferred deep linking

Deep linking and deferred deep linking allow you to improve your user experience. They allow you to open the app in specific activities and customize the content according to the campaign data.

To get data from deep linking, implement the extension callbacks.

<Tabs>
<Tab title="Android">

In the global application class, implement the following code:

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

In AppDelegate.m, implement the following code:

```objectivec
[AppsFlyerAdobeExtension registerCallbacks:^(NSDictionary *dictionary) {\
        NSLog(@"[AppsFlyerAdobeExtension] Received callback: %@", dictionary);\
        if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onConversionDataReceived"]){\
            if([[dictionary objectForKey:@"is_first_launch"] boolValue] == YES){\
                NSString* af_status = [dictionary objectForKey:@"af_status"];\
                if([af_status isEqualToString:@"Non-organic"]){\
                    NSLog(@"this is first launch and a non organic install!");\
                }\
            }\
        } else if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onAppOpenAttribution"]) {\
            NSLog(@"onAppOpenAttribution Received");\
        }\
     }];\
    [AppsFlyerAdobeExtension callbacksErrorHandler:^(NSError *error) {\
          NSLog(@"[AppsFlyerAdobeExtension] Error recieving callback: %@" , error);\
    }];
```

</Tab>
</Tabs>

## Connecting AppsFlyer conversion data

Conversion data is sent with events to the Adobe platform. These variables allow you to apply logic and rules to reporting dimensions, metrics, or filters.

1. Log in to your Adobe Analytics account.
   ![Adobe Analytics login screenshot](https://files.readme.io/d56f170695893dbbde00c50c838ce8a5c2cfe418a17692f372e208d458ed2d6c-31205379096465.png)
2. Navigate to **Admin** > **Report Suites**
3. Select the Report Suite that was configured during the Adobe Analytics implementation.
4. Select **General** > **Processing rules**.
5. Create processing rules to map the AppsFlyer Context Data variables to eVars.

See the following table for mapping AppsFlyer Context Data variables:

| **Recommended name to map** | **Conversion data** |
| --- | --- |
| AppsFlyer Lookback Window | appsflyer.af\_click\_lookback |
| AppsFlyer Install Time | appsflyer.install\_time |
| AppsFlyer Cost Cents US | appsflyer.cost\_cents\_USD |
| AppsFlyer MediaSource | appsflyer.media\_source |
| AppsFlyer Adset | appsflyer.af\_adset |
| AppsFlyer Click Time | appsflyer.click\_time |
| AppsFlyer Original Cost | appsflyer.orig\_cost |
| AppsFlyer Campaign | appsflyer.campaign |

### Using AppsFlyer mapped conversion data for Analytics and Analysis

All data coming from the SDK is available in the Adobe Analytics report suite that is connected to the app.

The data and its related dimensions and metrics can be used across your generated Adobe Analytics reports and dashboards. This data is also available in the AppsFlyer dashboard for attribution and in-app event analysis.