---
title: iOS SDK V6とプラグインへの更新
metadata:
  keywords:
    - iOS
    - SDK
    - Integration
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
  created_at: '2020-07-30T14:07:32Z'
  edited_at: '2026-10-28T09:11:35Z'
  id: 360011571778
  locale: ja
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/ja/articles/360011571778
---
> **At a glance:** 既存のAppsFlyer iOS SDK、または他の開発環境向けの連携用ライブラリを使用した実装を、iOS SDK V6に更新します。

<div id="about-ios-sdk-v6" />

## iOS SDK V6の概要

この記事では、SDK V6について説明します。

AppsFlyer iOS SDK V6は、次の機能を提供します。

* アプリの所有者と開発者が、iOS 14のリリースに備えられるようにします。
* IDFAの取得について、ユーザーに許可を求められます。
* iOSモバイルアプリに、アプリのアトリビューションとイベントの報告機能を提供します。
* 以前のバージョンから、APIメソッドに大幅な変更が加えられています。 0>

SDK V6の詳細や、AppsFlyer SDKをまだ使用していない新しいアプリへの実装方法は、<Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">マーケター向けiOS SDK実装ガイド</Anchor>を参照してください。

<div id="update-to-ios-sdk-v6" />

## iOS SDK V6への更新

iOS SDK V6に更新するには、以下の手順1～5を実行します。

<div id="1-update-sdk-version" />

<Accordion title="1. SDKバージョンの更新">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">SDK V6</Anchor>をダウンロードし、Xcodeに追加します。

</Accordion>

<div id="2-implement-sdk-v6" />

<Accordion title="2. SDK V6の実装">

**SDKの初期化処理に、以下のコードを追加します**。

<Tabs>
<Tab title="Objective-C">

AppDelegate.hに、以下のコードを追加します。

```objectivec
#import "AppDelegate.h"
#import <0>
#import <1>
#import <2>
@interface AppDelegate ()
@end
@implementation AppDelegate
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
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

- (void)applicationDidBecomeActive:(UIApplication *)application {
    [[AppsFlyerLib shared] start];
}

// Deep linking
// Open URI-scheme for iOS 9 and above
- (BOOL)application:(UIApplication *)application openURL:(NSURL *)url options:(NSDictionary *) options {
    [[AppsFlyerLib shared] handleOpenUrl:url options:options];
    return YES;
}
// Open URI-scheme for iOS 8 and below
- (BOOL)application:(UIApplication *)application openURL:(NSURL *)url sourceApplication:(NSString*)sourceApplication annotation:(id)annotation {
    [[AppsFlyerLib shared] handleOpenURL:url sourceApplication:sourceApplication withAnnotation:annotation];
    return YES;
}
// Open Universal Links
- (BOOL)application:(UIApplication *)application continueUserActivity:(NSUserActivity *)userActivity restorationHandler:(void (^)(NSArray * _Nullable))restorationHandler {
    [[AppsFlyerLib shared] continueUserActivity:userActivity restorationHandler:restorationHandler];
    return YES;
}
// Report Push Notification attribution data for re-engagements
- (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)userInfo fetchCompletionHandler:(void (^)(UIBackgroundFetchResult))completionHandler {
    [[AppsFlyerLib shared] handlePushNotification:userInfo];
}
// AppsFlyerLib implementation
//Handle Conversion Data (Deferred Deep Link)
-(void)onConversionDataSuccess:(NSDictionary*) installData {
    id status = [installData objectForKey:@"af_status"];
    if([status isEqualToString:@"Non-organic"]) {
        id sourceID = [installData objectForKey:@"media_source"];
        id campaign = [installData objectForKey:@"campaign"];
        NSLog(@"This is a none organic install. Media source: %@  Campaign: %@",sourceID,campaign);
    } else if([status isEqualToString:@"Organic"]) {
        NSLog(@"This is an organic install.");
    }
}
-(void)onConversionDataFail:(NSError *) error {
    NSLog(@"%@",error);
}
//Handle Direct Deep Link
- (void) onAppOpenAttribution:(NSDictionary*) attributionData {
    NSLog(@"%@",attributionData);
}
- (void) onAppOpenAttributionFailure:(NSError *)error {
    NSLog(@"%@",error);
}
// support for scene delegate
#pragma mark - UISceneSession lifecycle
- (UISceneConfiguration *)application:(UIApplication *)application configurationForConnectingSceneSession:(UISceneSession *)connectingSceneSession options:(UISceneConnectionOptions *)options API_AVAILABLE(ios(13)){
    // Called when a new scene session is being created.
    // Use this method to select a configuration to create the new scene with.
    return [[UISceneConfiguration alloc] initWithName:@"Default Configuration" sessionRole:connectingSceneSession.role];
}
- (void)application:(UIApplication *)application didDiscardSceneSessions:(NSSet *)sceneSessions  API_AVAILABLE(ios(13.0)){
    // Called when the user discards a scene session.
    // If any sessions were discarded while the application was not running, this will be called shortly after application:didFinishLaunchingWithOptions.
    // Use this method to release any resources that were specific to the discarded scenes, as they will not return.
}
@end
```

</Tab>

<Tab title="Swift">

AppDelegate.swiftに、以下のコードを追加します。

```swift
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

</Tab>
</Tabs>

</Accordion>

<div id="3-support-for-skadnetwork-attribution" />

<Accordion title="3. SKAdNetworkのアトリビューションへの対応">

<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_the_participating_apps">SKAdNetwork</Anchor>は、広告によるアプリのインストールを検証するために、iOSが使用するクラスです。アプリのインストール検証には、広告を表示するアプリと、広告の対象となるアプリの両方が関わります。 0>

広告を表示するアプリは、アドネットワークが署名した広告を表示して、広告キャンペーンに参加します。アプリに広告を表示するための設定は、AppsFlyer SDKの対応範囲外です。設定するには、<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_the_participating_apps">iOSの手順</Anchor>に従ってください。

広告の対象となるアプリについては、AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">SKAdNetworkソリューション</Anchor>がSKAdNetworkを利用して、ユーザーのプライバシーを保護しながら、広告主やアドネットワークにLTV分析、レポート、ポストバックを提供します。アプリの初回起動時に、AppsFlyerプラットフォームはマーケターが設定した内容に基づき、SKAdNetworkのコンバージョン値の設定方法をSDKに指示します。

AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">SKAdNetworkソリューション</Anchor>を利用する場合：

* 開発者による作業は不要です。
* AppsFlyer SDKが自動的に、必要なSKAdNetwork APIである`registerAppForAdNetworkAttribution()`と`updateConversionValue()`を呼び出します。開発者がこれらのAPIを呼び出してはいけません。 0>
* 他のSDKがSKAdNetwork APIを呼び出さないようにしてください。他のSDKが呼び出すと、iOSからAppsFlyerへのポストバック送信が遅れたり、コンバージョン値が変更されたりする可能性があります。AppsFlyerはこのコンバージョン値を使い、マーケターがダッシュボードで設定した内容に基づいて、ユーザーの質を示す計測データをSKAdNetworkダッシュボードに表示します。
* マーケターは、<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">AppsFlyerで</Anchor> SKAdNetworkの計測を設定する必要があります。 0>

開発者、マーケターともに、App Storeで追加の操作や登録を行う必要はありません。

</Accordion>

<div id="4-change-apis" />

<Accordion title="4. APIの変更">

AppsFlyer iOS SDK V6では、一部のAPI名が変更されています。以下の表を参照し、以前のSDKバージョンのAPI名を現在の名称に変更してください。

| API名（V6より前） | 現在のAPI名（V6以降） |
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

<Accordion title="5. プッシュ通知の実装確認">

すでにプッシュ通知を実装している場合は、次の対応が必要です。

<Anchor target="_blank" href="/marketers/ja/docs/measuring-push-notification-re-engagement-campaigns">プッシュ通知の手順</Anchor>に従い、handlePushNotificationDataメソッドを使って、プッシュ通知が実装されていることを確認してください。

</Accordion>

<div id="plugins" />

## プラグイン

次のV6プラグインを利用できます。

<div id="unity" />

<Accordion title="Unity">

AppsFlyerのUnity V6プラグインは、アプリの所有者と開発者によるiOS 14への対応を支援し、Unityで開発したAndroidとiOSのモバイルアプリに、アプリのアトリビューションとイベントの報告機能を提供します。このプラグインの機能は、AppsFlyerのiOS SDKおよびAndroid SDKと同等です。

以前のバージョンから更新する場合は、UnityプラグインV6への更新ガイドを参照してください。

* <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-plugin/blob/master/README.md#--migration">UnityプラグインV4からの更新</Anchor>（旧プラグインの削除が必要です）
* <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-plugin/blob/master/README.md#--migration">UnityプラグインV5からの更新</Anchor>（Unityパッケージの更新が必要です）

</Accordion>

<div id="react-native" />

<Accordion title="React Native">

AppsFlyerのReact Nativeプラグインは、アプリの所有者と開発者によるiOS 14への対応を支援し、AndroidとiOSのモバイルアプリに、アプリのアトリビューションとイベントの報告機能を提供します。このプラグインの機能は、AppsFlyerのiOS SDKおよびAndroid SDKと同等です。

以前のバージョンから更新する方法：

1. 旧プラグインを削除し、<Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin/tree/dev/sdk-v6-beta">GitHubのガイド</Anchor>に従って置き換えます。 0>
2. 必要なAPIの<Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin/tree/dev/sdk-v6-beta#--v6-breaking-changes">名称変更と削除</Anchor>を行い、実装コードを変更します。

</Accordion>

<div id="segment" />

<Accordion title="Segment">

AppsFlyerのSegmentプラグインは、アプリの所有者と開発者によるiOS 14への対応を支援し、AndroidとiOSのモバイルアプリに、アプリのアトリビューションとイベントの報告機能を提供します。このプラグインの機能は、AppsFlyerのiOS SDKおよびAndroid SDKと同等です。

以前のバージョンから更新する場合は、旧プラグインを削除し、<Anchor target="_blank" href="https://github.com/AppsFlyerSDK/segment-appsflyer-ios/tree/dev/sdk-v6-beta">GitHubのガイド</Anchor>に従って置き換えます。

</Accordion>

<div id="cordova" />

<Accordion title="Cordova">

AppsFlyerのCordovaプラグインは、アプリの所有者と開発者によるiOS 14への対応を支援し、AndroidとiOSのモバイルアプリに、アプリのアトリビューションとイベントの報告機能を提供します。このプラグインの機能は、AppsFlyerのiOS SDKおよびAndroid SDKと同等です。

以前のバージョンから更新する場合は、旧プラグインを削除し、<Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-cordova-plugin/tree/releases/6.x.x/6.0.x/6.0.1-beta">GitHubのガイド</Anchor>に従って置き換えます。

</Accordion>

<div id="flutter" />

<Accordion title="Flutter">

AppsFlyerのFlutterプラグインは、アプリの所有者と開発者によるiOS 14への対応を支援し、AndroidとiOSのモバイルアプリに、アプリのアトリビューションとイベントの報告機能を提供します。このプラグインの機能は、AppsFlyerのiOS SDKおよびAndroid SDKと同等です。

以前のバージョンから更新する場合は、旧プラグインを削除し、`pubspec.yaml`にV6バージョンを追加します。<Anchor target="_blank" href="https://pub.dev/packages/appsflyer_sdk">pub.devのガイド</Anchor>に従ってください。

</Accordion>

<div id="adobe-air" />

<Accordion title="Adobe AIR">

AppsFlyerのAdobe AIRプラグインは、アプリの所有者と開発者によるiOS 14への対応を支援し、AndroidとiOSのモバイルアプリに、アプリのアトリビューションとイベントの報告機能を提供します。このプラグインの機能は、AppsFlyerのiOS SDKおよびAndroid SDKと同等です。

以前のバージョンから更新する場合は、旧プラグインを削除し、<Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/tree/dev/sdk-v6-beta">GitHubのガイド</Anchor>に従って置き換えます。

</Accordion>

<div data-zendesk-anchors="about-ios-sdk-v6=ios-sdk-v6%E3%81%AE%E6%A6%82%E8%A6%81 update-to-ios-sdk-v6=ios-sdk-v6%E3%81%B8%E3%81%AE%E6%9B%B4%E6%96%B0 plugins=%E3%83%97%E3%83%A9%E3%82%B0%E3%82%A4%E3%83%B3" />
