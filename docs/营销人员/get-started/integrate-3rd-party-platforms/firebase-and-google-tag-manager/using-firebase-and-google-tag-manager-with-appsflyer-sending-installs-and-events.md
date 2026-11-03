---
title: >-
  Using Firebase and Google Tag Manager with AppsFlyer—Sending installs and
  events
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
  edited_at: '2026-10-13T00:32:28Z'
  id: 4410481550609
  locale: zh-cn
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/zh-cn/articles/4410481550609
---
> **At a glance:** Instructions for setting up event sending reported via Firebase SDK to AppsFlyer in your app.

## Configuring events in the app

This section discusses how to set up and create events in the app with Google Tag Manager (GTM).

When the event is sent, GTM checks to see if there is a tag that is configured to process this event with the help of the event trigger. The event trigger is set to fire the tag whenever a specific event is sent. If a specific event is sent and it has a corresponding trigger, the tag is fired. When the tag is fired, Google Tag Manager collects all the data in the event. Such data includes the AppsFlyer ID,  event name, and event parameters. After collecting all the data, Google Tag Manager sends the event to AppsFlyer.

<div id="creating-event-variables-for-revenue-and-price" />

<Accordion title="Creating event variables for revenue and price">

#### Android

<Tabs>
<Tab title="Java">

1. In the MainActivity class, create a variables to hold AppsFlyer Device ID:  

   ```java
   public static String appsFlyerID;
   ```
2. Back in the MainActivity class, in the `onCreate` method and after `super.onCreate`, pass the AppsFlyer ID to the variable:

   ```java
   appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this);
   ```

</Tab>

<Tab title="Kotlin">

1. In the MainActivity class, create a variable to hold AppsFlyer Device ID:  

   ```kotlin
   var appsFlyerID: String? = null
   ```
2. Back in the MainActivity class, in the `onCreate` method and after `super.onCreate`, pass the AppsFlyer ID value to the variable:

   ```kotlin
   override fun onCreate(savedInstanceState: Bundle?) {
    ...
    appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this)
   }
   ```

</Tab>
</Tabs>

#### iOS

For iOS, parameters are available across the app. You can retrieve them through the AppsFlyerTracker instance.

<Tabs>
<Tab title="Objective C">

1. AppsFlyer Device ID -

   ```objectivec
   [AppsFlyerTracker sharedTracker].getAppsFlyerUID
   ```
2. Apple App ID -

   ```objectivec
   [AppsFlyerTracker sharedTracker].appleAppID
   ```

</Tab>

<Tab title="Swift">

1. AppsFlyer Device ID -

   ```swift
    AppsFlyerTracker.shared().getAppsFlyerUID()
   ```
2. Apple App ID -

   ```swift
   AppsFlyerTracker.shared().appleAppID
   ```

</Tab>
</Tabs>

</Accordion>

<div id="adding-events-in-the-app" />

<Accordion title="Adding events in the app">

The first step is to configure the event in the app. The event is sent using Firebase Event Logging In the event you specify the AppsFlyer ID, event name, and event parameters. The AppsFlyer ID is retrieved from the variable that is created in the <Anchor target="_blank" href="/marketers/zh/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup#google-tag-manager-setup">setup step</Anchor>.

<Anchor target="_blank" href="https://developers.google.com/tag-manager/ios/v5/#log-events-and-variables">Google Tag Manager uses Firebase Analytics</Anchor> Events to trigger tag events. Whenever an event is sent to Firebase, Tag Manager recognizes the event and sends it to AppsFlyer as well.

#### Android

<Tabs>
<Tab title="Java">

1. In the desired activity, add the import statement for Firebase:  

   ```java
   import com.google.firebase.analytics.FirebaseAnalytics;
   ```
2. Add the following code to run whenever a purchase event occurs:

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

1. In the desired activity, add the import statement for Firebase:  

   ```kotlin
   import com.google.firebase.analytics.FirebaseAnalytics
   ```
2. Add the following code to run whenever a purchase event occurs:

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

1. In the view where the event is sent add `@import Firebase`
2. Add the following code to run whenever a purchase event occurs:

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

1. In the view where the event is sent add `import Firebase`
2. Add the following code to run whenever a purchase event occurs:

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

## Sending install events to Firebase

You can also send install events to Firebase with all install-related data.

#### Android

<Tabs>
<Tab title="Java">

To send install events to Firebase in Android, you can use the `conversionData`object.

#### Creating the send event method

Add the following method in the `AFApplication` class right below the `onCreate` method:

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

This method accepts a `conversionData` object. The method checks whether install time, media source, and campaign are null and if so sets the install time to the current time and the media source and campaign organic. Otherwise, it takes the data from the `conversionData` object and sends it to Firebase.

#### Sending the install event

Add the following code in the `onConversionDataSuccess` method:

```java
if(conversionData.get("is_first_launch").equals("true")){
       sendInstallToFirebase(conversionData);
    }
```

This code checks if this is the first time the app is launched. If so, it calls the `sendInstallToFirebase` method.

</Tab>

<Tab title="Kotlin">

To send install events to Firebase in Android, you can use the `conversionData`object.

#### Creating the send event method

Add the following method in the `AFApplication` class right below the `onCreate` method:

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

This method accepts a `conversionData` object. The method checks whether install time, media source, and campaign are null and if so sets the install time to the current time and the media source and campaign organic. Otherwise, it takes the data from the `conversionData` object and sends it to Firebase.

#### Sending the install event

Add the following code in the `onConversionDataSuccess` method:

```kotlin
if(conversionData?.get("is_first_launch") == true){
      sendInstallToFirebase(conversionData);
  }
```

This code checks if this is the first time the app is launched. If so, it calls the `sendInstallToFirebase` method.

**Note:** Starting SDK V5, `onConversionDataSuccess` is the name of the method for getting conversion data. If you are using an SDK version lower than 5.0.0, the name of the method is `onInstallConversionDataLoaded`. We recommend that you upgrade to SDK 5.0.0. To learn more, click <Anchor target="_blank" href="/marketers/zh/docs/links-to-appsflyer-sdk-release-notes">here</Anchor>.

</Tab>
</Tabs>

#### iOS

<Tabs>
<Tab title="Objective-C">

#### Creating the send event method

In AppDelegate.m, add the following method at the end of the file:

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

This method receives the `installData` object and checks if the install is organic or not. If it's organic, it sets the install time to the current time and the media source, campaign, and install type to organic.

If the install is non-organic, the method gets the relevant non-organic install data.

Once the parameters are set, the method sends the install event to Firebase.

#### Sending the install event

In AppDelegate.m, in the method `didFinishLaunchingWithOptions`, add `[FIRApp configure]`

In AppDelegate.m, in the `onConversionDataSuccess` method, add the following code at the end of the method:

```objectivec
if([installData objectForKey:@"is_first_launch"]){
      [self sendInstallToFirebase: installData];
    }
```

The code snippet above checks if this is the first time the app is launched. If it is, it calls the `sendInstallToFirebase` method.

</Tab>

<Tab title="Swift">

In AppDelegate.swift, add the following method at the end of the file:

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

**Note:** Starting SDK V5, `onConversionDataSuccess` is the name of the method for getting conversion data. If you are using an SDK version lower than 5.0.0, the name of the method is `onConversionDataReceived`. We recommend that you upgrade to SDK 5.0.0. To learn more, click <Anchor target="_blank" href="/marketers/zh/docs/links-to-appsflyer-sdk-release-notes">here</Anchor>.

This method accepts the `installData` object and checks if the install is organic or not. If it's organic, it sets the install time to the current time and the media source, campaign, and install type to organic.

If the install is non-organic, the method gets the relevant non-organic install data.

Once the parameters are set, the method sends the install event to Firebase.

#### Sending the install event

In AppDelegate.swift, in the method `didFinishLaunchingWithOptions`, add `FirebaseApp.configure();`

In AppDelegate.swift, in the `onConversionDataSuccess` method, add the following code at the end of the method:

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

**Note:** Starting SDK V5, `onConversionDataSuccess` is the name of the method for getting conversion data. If you are using an SDK version lower than 5.0.0, the name of the method is `onConversionDataReceived`. We recommend that you upgrade to SDK 5.0.0. To learn more, click <Anchor target="_blank" href="/marketers/zh/docs/links-to-appsflyer-sdk-release-notes">here</Anchor>.

The code snippet above checks if this is the first time the app is launched. If it is, it calls the `sendInstallToFirebase` method.

</Tab>
</Tabs>

> ❗️ **Warning**
>
> Certain media sources don't allow their data to be shared with third-party platforms and services. If you are working with partners such as Meta ads, Twitter, Snap, Pinterest, etc. who have set restrictions on sharing their data with third-party platforms and services, please make sure **to follow their guidelines and remove any data which is under these restrictions**.
>
> * <Anchor target="_blank" href="https://www.facebook.com/privacy/policy/">Meta ads Data Policy</Anchor>
> * <Anchor target="_blank" href="https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html">Twitter Data Policy</Anchor>
> * <Anchor target="_blank" href="https://www.snap.com/en-US/privacy/privacy-policy/">Snapchat Data Policy</Anchor>
> * <Anchor target="_blank" href="https://policy.pinterest.com/en/privacy-policy">Pinterest Data Policy</Anchor>

<div data-zendesk-anchors="01H8H2MH93M1SB9HEQNHDDJZP0=configuring-events-in-the-app 01H8H2MH93D36ZH7788XCMHHV6=creating-event-variables-for-revenue-and-price 01H8H2MH93RNWN6N6EWE5T26V1=android 01H8H2MH93CZ5TACG3MWJ8YRFK=ios 01H8H2MH9340PQCCKB85BQZQEG=adding-events-in-the-app android::eb294e42=android-1 01H8H2MH9357Z5M1DBK4Z9N22P=android-1 01H8H2MH930VDZH5YSWEPTS8BN=sending-install-events-to-firebase android::319436d3=android-2 01H8H2MH938Y980A9KA9BPP44Y=android-2 01H8H2MH932WYSS6Z5NZJ3195X=creating-the-send-event-method 01H8H2MH93H0WKMV5DAN713EY0=sending-the-install-event creating-the-send-event-method::64b5a305=creating-the-send-event-method 01H8H2MH93VYXGMM5H6ZQWCFZY=creating-the-send-event-method sending-the-install-event::aeb9cdb7=sending-the-install-event 01H8H2MH93VTPZNF51R05QPK7C=sending-the-install-event ios::95ad6e27=ios-1 01H8H2MH93AQE7PKVW4QKD2ARN=ios-1 creating-the-send-event-method::346138b1=creating-the-send-event-method-2 01H8H2MH93NGBRHBDQTX4DKNTY=creating-the-send-event-method-2 sending-the-install-event::aca3c0e3=sending-the-install-event-2 01H8H2MH93SWYFF2KTC1HJ06FF=sending-the-install-event-2 sending-the-install-event::b6997ad3=sending-the-install-event-2 01H8H2MH93Y5J8QH0YBKPQSV5N=sending-the-install-event-2 01H8H2MH93JQBAR6ZTW77HHFQR=warning" />
