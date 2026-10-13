---
title: "Using Firebase and Google Tag Manager with AppsFlyer—Sending installs and events"
excerpt: "Instructions for setting up event sending reported via Firebase SDK to AppsFlyer in your app."
x-zendesk:
  id: 4410481550609
  url: https://support.appsflyer.com/hc/en-us/articles/4410481550609-Using-Firebase-and-Google-Tag-Manager-with-AppsFlyer-Sending-installs-and-events
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  position: 6
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Developers, Marketers, Localize, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2021-11-09T10:31:07Z'
  edited_at: '2023-11-23T10:09:50Z'
---
## Configuring events in the app

This section discusses how to set up and create events in the app with Google Tag Manager (GTM).

When the event is sent, GTM checks to see if there is a tag that is configured to process this event with the help of the event trigger. The event trigger is set to fire the tag whenever a specific event is sent. If a specific event is sent and it has a corresponding trigger, the tag is fired. When the tag is fired, Google Tag Manager collects all the data in the event. Such data includes the AppsFlyer ID,  event name, and event parameters. After collecting all the data, Google Tag Manager sends the event to AppsFlyer.

### Creating event variables for revenue and price

#### Android

JavaKotlin

1. In the MainActivity class, create a variables to hold AppsFlyer Device ID:  

   ```
   public static String appsFlyerID;
   ```
2. Back in the MainActivity class, in the `onCreate` method and after `super.onCreate`, pass the AppsFlyer ID to the variable:

   ```
   appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this);
   ```

1. In the MainActivity class, create a variable to hold AppsFlyer Device ID:  

   ```javascript
   var appsFlyerID: String? = null
   ```
2. Back in the MainActivity class, in the `onCreate` method and after `super.onCreate`, pass the AppsFlyer ID value to the variable:

   ```
   override fun onCreate(savedInstanceState: Bundle?) {
    ...
    appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this)
   }
   ```

#### iOS

For iOS, parameters are available across the app. You can retrieve them through the AppsFlyerTracker instance.

Objective C Swift

1. AppsFlyer Device ID -

   ```
   [AppsFlyerTracker sharedTracker].getAppsFlyerUID
   ```
2. Apple App ID -

   ```
   [AppsFlyerTracker sharedTracker].appleAppID
   ```

1. AppsFlyer Device ID -

   ```
    AppsFlyerTracker.shared().getAppsFlyerUID()
   ```
2. Apple App ID -

   ```
   AppsFlyerTracker.shared().appleAppID
   ```

### Adding events in the app

The first step is to configure the event in the app. The event is sent using Firebase Event Logging In the event you specify the AppsFlyer ID, event name, and event parameters. The AppsFlyer ID is retrieved from the variable that is created in the [setup step](/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup#google-tag-manager-setup).

[Google Tag Manager uses Firebase Analytics](https://developers.google.com/tag-manager/ios/v5/#log-events-and-variables) Events to trigger tag events. Whenever an event is sent to Firebase, Tag Manager recognizes the event and sends it to AppsFlyer as well.

#### Android

JavaKotlin

1. In the desired activity, add the import statement for Firebase:  

   ```
   import com.google.firebase.analytics.FirebaseAnalytics;
   ```
2. Add the following code to run whenever a purchase event occurs:

   ```
   Bundle bundle = new Bundle();
     // notice "af_id", this is the name of the event parameter 
     // for AppsFlyer ID that we created in the previous step
     bundle.putString("af_id", appsFlyerID);
     bundle.putString("af_revenue", "200");
     bundle.putString("af_price", "250");
     mFirebaseAnalytics.logEvent("af_purchase", bundle);
   ```

1. In the desired activity, add the import statement for Firebase:  

   ```
   import com.google.firebase.analytics.FirebaseAnalytics
   ```
2. Add the following code to run whenever a purchase event occurs:

   ```
   val bundle = Bundle()
     // notice "af_id", this is the name of the event parameter
     // for AppsFlyer ID that we created in the previous step
     bundle.putString("af_id", appsFlyerID)
     bundle.putString("af_revenue", "200")
     bundle.putString("af_price", "250")
     FirebaseAnalytics.getInstance(this).logEvent("af_purchase", bundle)
   ```

iOS

Objective-C Swift

1. In the view where the event is sent add `@import Firebase`
2. Add the following code to run whenever a purchase event occurs:

   ```
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

1. In the view where the event is sent add `import Firebase`
2. Add the following code to run whenever a purchase event occurs:

   ```
   Analytics.logEvent("af_purchase", parameters: [
          "apple_app_id": "id" + AppsFlyerTracker.shared().appleAppID,
          "af_id": AppsFlyerTracker.shared().getAppsFlyerUID(),
          "af_revenue": 250,
          "af_price": 375
       ]);
   ```

## Sending install events to Firebase

You can also send install events to Firebase with all install-related data.

#### Android

Java Kotlin

To send install events to Firebase in Android, you can use the `conversionData`object.

#### Creating the send event method

Add the following method in the `AFApplication` class right below the `onCreate` method:

```
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

```
if(conversionData.get("is_first_launch").equals("true")){
       sendInstallToFirebase(conversionData);
    }
```

This code checks if this is the first time the app is launched. If so, it calls the `sendInstallToFirebase` method.

To send install events to Firebase in Android, you can use the `conversionData`object.

#### Creating the send event method

Add the following method in the `AFApplication` class right below the `onCreate` method:

```
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

```
if(conversionData?.get("is_first_launch") == true){
      sendInstallToFirebase(conversionData);
  }
```

This code checks if this is the first time the app is launched. If so, it calls the `sendInstallToFirebase` method.

**Note:** Starting SDK V5, `onConversionDataSuccess` is the name of the method for getting conversion data. If you are using an SDK version lower than 5.0.0, the name of the method is `onInstallConversionDataLoaded`. We recommend that you upgrade to SDK 5.0.0. To learn more, click [here](/docs/links-to-appsflyer-sdk-release-notes).

#### iOS

Objective-C Swift

#### Creating the send event method

In AppDelegate.m, add the following method at the end of the file:

```
- (void) sendInstallToFirebase:(NSDictionary *) installData{
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

```
if([installData objectForKey:@"is_first_launch"]){
      [self sendInstallToFirebase: installData];
    }
```

The code snippet above checks if this is the first time the app is launched. If it is, it calls the `sendInstallToFirebase` method.

In AppDelegate.swift, add the following method at the end of the file:

```
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

**Note:** Starting SDK V5, `onConversionDataSuccess` is the name of the method for getting conversion data. If you are using an SDK version lower than 5.0.0, the name of the method is `onConversionDataReceived`. We recommend that you upgrade to SDK 5.0.0. To learn more, click [here](/docs/links-to-appsflyer-sdk-release-notes).

This method accepts the `installData` object and checks if the install is organic or not. If it's organic, it sets the install time to the current time and the media source, campaign, and install type to organic.

If the install is non-organic, the method gets the relevant non-organic install data.

Once the parameters are set, the method sends the install event to Firebase.

#### Sending the install event

In AppDelegate.swift, in the method `didFinishLaunchingWithOptions`, add `FirebaseApp.configure();`

In AppDelegate.swift, in the `onConversionDataSuccess` method, add the following code at the end of the method:

```
if let is_first_launch = data["is_first_launch"] , let launch_code = is_first_launch as? Int {
      if(launch_code == 1){
        print("First Launch")
        sendInstallToFirebase(installData)
      } else {
        print("Not First Launch")
      }
    }
```

**Note:** Starting SDK V5, `onConversionDataSuccess` is the name of the method for getting conversion data. If you are using an SDK version lower than 5.0.0, the name of the method is `onConversionDataReceived`. We recommend that you upgrade to SDK 5.0.0. To learn more, click [here](/docs/links-to-appsflyer-sdk-release-notes).

The code snippet above checks if this is the first time the app is launched. If it is, it calls the `sendInstallToFirebase` method.

> 📘 **Warning**
>
> Certain media sources don't allow their data to be shared with third-party platforms and services. If you are working with partners such as Meta ads, Twitter, Snap, Pinterest, etc. who have set restrictions on sharing their data with third-party platforms and services, please make sure **to follow their guidelines and remove any data which is under these restrictions**.
>
> * [Meta ads Data Policy](https://www.facebook.com/privacy/policy/)
> * [Twitter Data Policy](https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html)
> * [Snapchat Data Policy](https://www.snap.com/en-US/privacy/privacy-policy/)
> * [Pinterest Data Policy](https://policy.pinterest.com/en/privacy-policy)