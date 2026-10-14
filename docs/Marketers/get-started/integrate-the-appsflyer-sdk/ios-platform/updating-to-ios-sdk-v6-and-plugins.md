---
title: "Updating to iOS SDK V6 and plugins"
excerpt: "Update an existing AppsFlyer iOS SDK/wrapper integration to iOS SDK V6."
x-zendesk:
  id: 360011571778
  url: https://support.appsflyer.com/hc/en-us/articles/360011571778-Updating-to-iOS-SDK-V6-and-plugins
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: iOS platform
  section_id: 6551263106577
  position: 2
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [iOS, SDK, Integration, Advertisers, Developers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2020-07-30T14:07:32Z'
  edited_at: '2026-08-14T16:22:40Z'
---
## About iOS SDK V6

Reference in this article to SDK V6.

The AppsFlyer iOS SDK V6:

* Allows app owners and developers to prepare for iOS 14 release.
* Give you the option to ask users for permission to collect IDFA.
* Provides app attribution and event reporting functionality to iOS mobile apps.
* Includes significant API method changes from previous versions.

For full information about the SDK V6, and to integrate it into a new app that does not have an earlier version of the AppsFlyer SDK, read our [iOS SDK integration guide for marketers](/docs/sdk-integration-overview).

## Update to iOS SDK V6

To update to iOS SDK V6, complete the procedures (1-5) that follow.

<div id="1-update-sdk-version" />

<Accordion title="1. Update SDK version">

Download and add the [SDK V6](https://dev.appsflyer.com/hc/docs/install-ios-sdk) to your Xcode.

</Accordion>

<div id="2-implement-sdk-v6" />

<Accordion title="2. Implement SDK V6">

**Add the following code to the SDK initialization**:

<Accordion title="Objective-C">

In AppDelegate.h, do the following:

```
#import "AppDelegate.h"
#import <AppsFlyerLib/AppsFlyerLib.h>
#import <AppTrackingTransparency/AppTrackingTransparency.h>
#import <UserNotifications/UserNotifications.h>
@interface AppDelegate ()
@end
@implementation AppDelegate
- (BOOL) application:(UIApplication *) application didFinishLaunchingWithOptions:(NSDictionary *) launchOptions {
    // 1 - Get AppsFlyer preferences from .plist file
    NSString *path = [[NSBundle mainBundle] pathForResource:@"afdevkey_donotpush" ofType:@".plist"];
    NSDictionary* properties = [NSDictionary dictionaryWithContentsOfFile:path];
    if (properties == nil || path == nil) {
        [NSException raise:@"Error" format:@"Cannot find .plist file"];
    }
    NSString* appsFlyerDevKey = [properties objectForKey:@"appsFlyerDevKey"];
    NSString* appleAppID = [properties objectForKey:@"appleAppID"];
    if (appsFlyerDevKey == nil || appleAppID == nil) {
        [NSException raise:@"Error" format:@"Cannot find appsFlyerDevKey or appleAppID"];
    }
    // 2 - Replace 'appsFlyerDevKey', `appleAppID` with your DevKey, Apple App ID
    [[AppsFlyerLib shared] setAppsFlyerDevKey:appsFlyerDevKey];
    [[AppsFlyerLib shared] setAppleAppID:appleAppID];
    [AppsFlyerLib shared].delegate = self;
    //  Set isDebug to true to see AppsFlyer debug logs
    [AppsFlyerLib shared].isDebug = true;

    if (@available(iOS 10, *)) {
        UIUserNotificationSettings *settings = [UIUserNotificationSettings settingsForTypes: UIUserNotificationTypeAlert | UIUserNotificationTypeSound | UIUserNotificationTypeBadge categories:nil];
        [[UIApplication sharedApplication] registerUserNotificationSettings:settings];
        [[UIApplication sharedApplication] registerForRemoteNotifications];
    }
    return YES;
}

- (void) applicationDidBecomeActive:(UIApplication *) application {
    [[AppsFlyerLib shared] start];
}

// Deep linking
// Open URI-scheme for iOS 9 and above
- (BOOL) application:(UIApplication *) application openURL:(NSURL *) url options:(NSDictionary *) options {
    [[AppsFlyerLib shared] handleOpenUrl:url options:options];
    return YES;
}
// Open URI-scheme for iOS 8 and below
- (BOOL) application:(UIApplication *) application openURL:(NSURL *) url sourceApplication:(NSString*) sourceApplication annotation:(id) annotation {
    [[AppsFlyerLib shared] handleOpenURL:url sourceApplication:sourceApplication withAnnotation:annotation];
    return YES;
}
// Open Universal Links
- (BOOL) application:(UIApplication *) application continueUserActivity:(NSUserActivity *) userActivity restorationHandler:(void (^) (NSArray * _Nullable)) restorationHandler {
    [[AppsFlyerLib shared] continueUserActivity:userActivity restorationHandler:restorationHandler];
    return YES;
}
// Report Push Notification attribution data for re-engagements
- (void) application:(UIApplication *) application didReceiveRemoteNotification:(NSDictionary *) userInfo fetchCompletionHandler:(void (^) (UIBackgroundFetchResult)) completionHandler {
    [[AppsFlyerLib shared] handlePushNotification:userInfo];
}
// AppsFlyerLib implementation
//Handle Conversion Data (Deferred Deep Link)
-(void) onConversionDataSuccess:(NSDictionary*) installData {
    id status = [installData objectForKey:@"af_status"];
    if([status isEqualToString:@"Non-organic"]) {
        id sourceID = [installData objectForKey:@"media_source"];
        id campaign = [installData objectForKey:@"campaign"];
        NSLog(@"This is a none organic install. Media source: %@  Campaign: %@",sourceID,campaign);
    } else if([status isEqualToString:@"Organic"]) {
        NSLog(@"This is an organic install.");
    }
}
-(void) onConversionDataFail:(NSError *) error {
    NSLog(@"%@",error);
}
//Handle Direct Deep Link
- (void) onAppOpenAttribution:(NSDictionary*) attributionData {
    NSLog(@"%@",attributionData);
}
- (void) onAppOpenAttributionFailure:(NSError *) error {
    NSLog(@"%@",error);
}
// support for scene delegate
#pragma mark - UISceneSession lifecycle
- (UISceneConfiguration *) application:(UIApplication *) application configurationForConnectingSceneSession:(UISceneSession *) connectingSceneSession options:(UISceneConnectionOptions *) options API_AVAILABLE(ios(13)){
    // Called when a new scene session is being created.
    // Use this method to select a configuration to create the new scene with.
    return [[UISceneConfiguration alloc] initWithName:@"Default Configuration" sessionRole:connectingSceneSession.role];
}
- (void) application:(UIApplication *) application didDiscardSceneSessions:(NSSet *) sceneSessions  API_AVAILABLE(ios(13.0)){
    // Called when the user discards a scene session.
    // If any sessions were discarded while the application was not running, this will be called shortly after application:didFinishLaunchingWithOptions.
    // Use this method to release any resources that were specific to the discarded scenes, as they will not return.
}
@end
```

</Accordion>

<Accordion title="Swift">

In AppDelegate.swift, add the following:

```
import UIKit
import AppTrackingTransparency
import AppsFlyerLib
import UserNotifications
@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {
    var window: UIWindow?
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        // 1 - Get AppsFlyer preferences from .plist file
        guard let propertiesPath = Bundle.main.path(forResource: "afdevkey_donotpush", ofType: "plist"),
            let properties = NSDictionary(contentsOfFile: propertiesPath) as? [String:String] else {
                fatalError("Cannot find `afdevkey_donotpush`")
        }
        guard let appsFlyerDevKey = properties["appsFlyerDevKey"],
                   let appleAppID = properties["appleAppID"] else {
            fatalError("Cannot find `appsFlyerDevKey` or `appleAppID` key")
        }
        // 2 - Replace 'appsFlyerDevKey', `appleAppID` with your DevKey, Apple App ID
        AppsFlyerLib.shared().appsFlyerDevKey = appsFlyerDevKey
        AppsFlyerLib.shared().appleAppID = appleAppID
        AppsFlyerLib.shared().delegate = self
        //  Set isDebug to true to see AppsFlyer debug logs
        AppsFlyerLib.shared().isDebug = true

        // iOS 10 or later
        if #available(iOS 10, *) {
            UNUserNotificationCenter.current().requestAuthorization(options: [.badge, .alert, .sound]) { _, _ in }
            application.registerForRemoteNotifications()
        }
        // iOS 9 support - Given for reference. This demo app supports iOS 13 and above
        else {
            UIApplication.shared.registerUserNotificationSettings(UIUserNotificationSettings(types: [.badge, .sound, .alert], categories: nil))
            UIApplication.shared.registerForRemoteNotifications()
        }
        return true
    }
    func applicationDidBecomeActive(_ application: UIApplication) {
        // Start the SDK (start the IDFA timeout set above, for iOS 14 or later)
        AppsFlyerLib.shared().start()
    }
    // Open Univerasal Links
    // For Swift version < 4.2 replace function signature with the commented out code
    // func application(_ application: UIApplication, continue userActivity: NSUserActivity, restorationHandler: @escaping ([Any]?) -> Void) -> Bool { // this line for Swift < 4.2
    func application(_ application: UIApplication, continue userActivity: NSUserActivity, restorationHandler: @escaping ([UIUserActivityRestoring]?) -> Void) -> Bool {
        AppsFlyerLib.shared().continue(userActivity, restorationHandler: nil)
        return true
    }
    // Open Deeplinks
    // Open URI-scheme for iOS 8 and below
    func application(_ application: UIApplication, open url: URL, sourceApplication: String?, annotation: Any) -> Bool {
        AppsFlyerLib.shared().handleOpen(url, sourceApplication: sourceApplication, withAnnotation: annotation)
        return true
    }
    // Open URI-scheme for iOS 9 and above
    func application(_ app: UIApplication, open url: URL, options: [UIApplication.OpenURLOptionsKey : Any] = [:]) -> Bool {
        AppsFlyerLib.shared().handleOpen(url, options: options)
        return true
    }
    // Report Push Notification attribution data for re-engagements
    func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
        AppsFlyerLib.shared().handlePushNotification(userInfo)
    }
}
extension AppDelegate: AppsFlyerLibDelegate {
    // Handle Organic/Non-organic installation
    func onConversionDataSuccess(_ data: [AnyHashable: Any]) {
        print("onConversionDataSuccess data:")
        for (key, value) in data {
            print(key, ":", value)
        }
        if let status = data["af_status"] as? String {
            if (status == "Non-organic") {
                if let sourceID = data["media_source"],
                    let campaign = data["campaign"] {
                    print("This is a Non-Organic install. Media source: \(sourceID)  Campaign: \(campaign)")
                }
            } else {
                print("This is an organic install.")
            }
            if let is_first_launch = data["is_first_launch"] as? Bool,
                is_first_launch {
                print("First Launch")
            } else {
                print("Not First Launch")
            }
        }
    }
    func onConversionDataFail(_ error: Error) {
        print("\(error)")
    }
    // Handle Deeplink
    func onAppOpenAttribution(_ attributionData: [AnyHashable: Any]) {
        //Handle Deep Link Data
        print("onAppOpenAttribution data:")
        for (key, value) in attributionData {
            print(key, ":",value)
        }
    }
    func onAppOpenAttributionFailure(_ error: Error) {
        print("\(error)")
    }
}
```

</Accordion>

</Accordion>

<div id="3-support-for-skadnetwork-attribution" />

<Accordion title="3. Support for SKAdNetwork attribution">

[SKAdNetwork](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_the_participating_apps) is a class used by iOS that validates advertiser-driven app installations. The app install validation process involves the source app and the advertised app.

A source app is an app that participates in ad campaigns by displaying ads signed by an ad network. Configuring your app to display ads is not within the scope of the AppsFlyer SDK. To configure, you must follow the [iOS instructions](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_the_participating_apps).

For configuring the advertised app, the AppsFlyer [SKAdNetwork Solution](/docs/skadnetwork-skan-solution-guide) uses the SKAdNetwork to provide advertisers and ad networks with LTV analytics, reports, and postbacks, while maintaining user privacy. On launching the app for the first time, the AppsFlyer platform, using the configuration set by the marketer, instructs the SDK how to set the SKAdNetwork conversion value.

To use the [SKAdNetwork Solution](/docs/skadnetwork-skan-solution-guide):

* The developer does nothing.
* AppsFlyer SDK automatically calls the necessary SKAdNetwork APIs, meaning `registerAppForAdNetworkAttribution()` and `updateConversionValue()`. The developer must not call them.
* Don't allow other SDKs to call SKAdNet APIs. Doing so can delay iOS in sending the postback to AppsFlyer and change the conversion value which we use to populate the SKAdNetwork dashboard with user quality measurement data as configured by the marketer in the dashboard.
* The marketer needs to configure SKAdNetwork measurement [in AppsFlyer](/docs/skadnetwork-skan-solution-guide).

There is no other action or registration process required by either the developer or the marketer in the App Store.

</Accordion>

<div id="4-change-apis" />

<Accordion title="4. Change APIs">

The AppsFlyer iOS SDK V6 has some API name changes. See the following table to change the API names from the earlier SDK versions to the current names.

| API name (before V6) | Current API name (V6 and later) |
| --- | --- |
| AppsFlyerTracker | AppsFlyerLib |
| disableIAdTracking | disableCollectASA |
| trackAppLaunchWithCompletionHandler | startWithCompletionHandler |
| trackLocation | logLocation |
| trackAppLaunch | start |
| trackEvent | logEvent |
| disableAppleAdSupportTracking | disableAdvertisingIdentifier |
| validateAndTrackInAppPurchase | validateAndLogInAppPurchase |
| isStopTracking | isStopped |
| deviceTrackingDisabled/deviceLoggingDisabled | anonymizeUser |
| sharedTracker (Objective C) | shared |

</Accordion>

<div id="5-ensure-push-notification-integration" />

<Accordion title="5. Ensure push notification integration">

The following is required if push notification integration is already implemented.

Follow the [push notification instructions](/docs/measuring-push-notification-re-engagement-campaigns) to ensure you have push notifications integrated using the handlePushNotificationData method.

</Accordion>

## Plugins

The following V6 plugins are available:

<div id="unity" />

<Accordion title="Unity">

The AppsFlyer Unity V6 plugin helps app owners and developers support iOS 14, providing app attribution and event reporting functionality to Android and iOS mobile apps developed on the Unity development platform. The plugin is functionally equivalent to the AppsFlyer iOS and Android SDKs.

To update your plugin from an earlier version, see our guides on updating to the Unity plugin V6:

* [From Unity plugin V4](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin/blob/master/README.md#--migration) (requires removal of the old plugin)
* [From Unity plugin V5](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin/blob/master/README.md#--migration) (requires an update of the Unity package)

</Accordion>

<div id="react-native" />

<Accordion title="React Native">

The AppsFlyer React Native plugin helps app owners and developers prepare for iOS 14, providing app attribution and event reporting functionality to Android and iOS mobile apps. The plugin is functionally equivalent to the AppsFlyer iOS and Android SDKs.

To update your plugin from an earlier version:

1. Remove the earlier plugin and replace it following the instructions in our [GitHub guide](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin/tree/dev/sdk-v6-beta).
2. Change the integration code by [renaming and deleting](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin/tree/dev/sdk-v6-beta#--v6-breaking-changes) the necessary APIs.

</Accordion>

<div id="segment" />

<Accordion title="Segment">

The AppsFlyer Segment plugin helps app owners and developers prepare for iOS 14, providing app attribution and event reporting functionality to Android and iOS mobile apps. The plugin is functionally equivalent to the AppsFlyer iOS and Android SDKs.

To update your plugin from an earlier version, remove the earlier plugin and replace it following the instructions in our [GitHub guide](https://github.com/AppsFlyerSDK/segment-appsflyer-ios/tree/dev/sdk-v6-beta).

</Accordion>

<div id="cordova" />

<Accordion title="Cordova">

The AppsFlyer Cordova plugin helps app owners and developers prepare for iOS 14, providing app attribution and event reporting functionality to Android and iOS mobile apps. The plugin is functionally equivalent to the AppsFlyer iOS and Android SDKs.

To update your plugin from an earlier version, remove the earlier plugin and replace it following the instructions in our [GitHub guide](https://github.com/AppsFlyerSDK/appsflyer-cordova-plugin/tree/releases/6.x.x/6.0.x/6.0.1-beta).

</Accordion>

<div id="flutter" />

<Accordion title="Flutter">

The AppsFlyer Flutter plugin helps app owners and developers prepare for iOS 14, providing app attribution and event reporting functionality to Android and iOS mobile apps. The plugin is functionally equivalent to the AppsFlyer iOS and Android SDKs.

To update your plugin from an earlier version, remove the earlier plugin and add the V6 version to `pubspec.yaml`, following the instructions in our [pub.dev guide](https://pub.dev/packages/appsflyer_sdk).

</Accordion>

<div id="adobe-air" />

<Accordion title="Adobe AIR">

The AppsFlyer Adobe AIR plugin helps app owners and developers prepare for iOS 14, providing app attribution and event reporting functionality to Android and iOS mobile apps. The plugin is functionally equivalent to the AppsFlyer iOS and Android SDKs.

To update your plugin from an earlier version, remove the earlier plugin and replace it following the instructions in our [GitHub guide](https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/tree/dev/sdk-v6-beta).

</Accordion>
