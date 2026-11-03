---
title: iOS SDK V6로 업데이트하기 &amp; 플러그인
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
  edited_at: '2026-10-14T10:30:27Z'
  id: 360011571778
  locale: ko
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/ko/articles/360011571778
---
> **한눈에 보기:** 요약: 기존 앱스플라이어 iOS SDK/iOS SDK V6와 래퍼 연동을 업데이트합니다.

## iOS SDK V6 소개

이 문서는 SDK V6에 관련된 참고자료입니다.

앱스플라이어 iOS SDK V6는

* 앱 소유주와 앱 개발자가 iOS 14 출시에 대비하도록 지원합니다.
* 앱 사용자에게 IDFA 수집 승인 여부를 묻는 옵션을 지원합니다.
* iOS 모바일 앱에 앱 어트리뷰션과 이벤트 리포팅 기능을 제공합니다.
* API 메서드가 이전 버전과 다릅니다.

SDK V6 관련 상세 내용과 그 버전을 앱스플라이어 SDK 기존 버전이 설치되지 않은 새 앱에 설치하는 방식은 <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">마케터용 iOS SDK 연동 가이드</Anchor>를 참고하십시오.

## iOS SDK V6로 업데이트하기

iOS SDK V6로 업데이트하기 위해, 다음 절차(1-5)를 완료하십시오.

<div id="1-update-sdk-version" />

<Accordion title="1. 1. SDK 버전을 업데이트 합니다.">

SDK V6를 다운로드하고 Xcode에 추가합니다.

</Accordion>

<div id="2-implement-sdk-v6" />

<Accordion title="2. 2. SDK V6을 구현합니다.">

**다음 코드를 SDK 작동 시점에 추가하십시오.**

<Tabs>
<Tab title="Objective-C">

AppDelegate.h 에서, 다음 작업을 진행하십시오:

```objectivec
#import "AppDelegate.h"
#import <AppsFlyerLib/AppsFlyerLib.h>
#import <AppTrackingTransparency/AppTrackingTransparency.h>
#import <UserNotifications/UserNotifications.h>
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

AppDelegate.swift에서 다음을 추가하십시오.

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

<Accordion title="3. 3.3 SKAdNetwork 어트리뷰션 지원 설정">

앱 설치 검증 과정에는 소스 앱과 광고된 앱이 포함됩니다.

소스(source) 앱은 광고 네트워크가 서명한 광고를 자신의 지면에 게재하여 광고 캠페인에 참여하는 앱입니다. 광고를 표시하도록 귀사의 앱을 구성하는 것은 앱스플라이어 SDK의 영역이 아닙니다. 구성할 때 iOS 지침을 따라야 합니다.

앱이 처음 실행되면, 플랫폼은 마케터가 설정한 구성을 이용하여 SDK에 SKAdNetwork 전환 값(conversion value)을 설정하는 방식을 알려줍니다.

<Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">SKAdNetwork Solution을 사용하기 위해</Anchor>

* 개발자가 할 일은 없습니다.
* 앱스플라이어 SDK는  필요한 SKAdNetwork API를 자동으로 호출합니다.
* 앱스플라이어 외 다른 SDK가 SKAdNet API를 호출하지 않도록 하십시오. 다른 SDK가 호출하면, iOS가 앱스플라이어에 보내는 포스트백이 지연될 수 있고, 전환 값이 변경되어 전환 값을 사용하여 SKAdNetwork 대시보드에 표기되는 사용자 가치 데이터도 변경될 수 있습니다.
* 마케터는<Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">앱스플라이어</Anchor>에서 SKAdNetwork 측정 방식을 설정해야 합니다.

 App Store에서 개발자나 마케터가 해야 할 작업이나 등록 절차는 없습니다.

</Accordion>

<div id="4-change-apis" />

<Accordion title="4. 4. API를 변경합니다.">

앱스플라이어 iOS SDK V6에서는 API 이름이 일부 변경되었습니다. 아래 표에서 SDK 이전 버전과 최신 버전의 API 이름을 참조하여 API 이름을 최신 버전으로 변경하십시오.

| API 이름(V6 이전) | 현재 API 이름(V6 이상) |
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

<Accordion title="5. 6. 푸시 알림 연동이 되었는지 확인합니다.">

푸시 알림 연동이 이미 구현되어 있는 경우 다음 사항이 필요합니다.

<Anchor target="_blank" href="/marketers/ko/docs/measuring-push-notification-re-engagement-campaigns">푸시 알림 지침</Anchor>을 따라 handlePushNotificationData 메서드를 이용하여 푸시 알림이 연동되었음을 확인합니다.

</Accordion>

## 플러그인

다음과 같은 V6 플러그인이 지원됩니다.

<div id="unity" />

<Accordion title="Unity">

앱 소유주와 앱 개발자는 앱스플라이어 Unity V6 플러그인으로 iOS 14을 지원할 수 있으며, 이 플러그인은 유니티 개발 플랫폼에서 개발된 안드로이드와 iOS 앱에 어트리뷰션과 이벤트 리포팅 기능을 제공합니다. 플러그인은 앱스플라이어 iOS 및 안드로이드 SDK와 기능적으로 동일합니다.

기존 버전에서 플러그인을 업데이트하시려면, 앱스플라이어 Unity 플러그인 V6 업데이트 가이드를 참조하십시오.

* <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-plugin/blob/master/README.md#--migration">유니티 플러그인 V4에서 업데이트하기</Anchor> (구 플러그인 제거)
* <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-plugin/blob/master/README.md#--migration">유니티 플러그인 V5에서 업데이트하기</Anchor> (기존 유니티 패키지 업데이트)

</Accordion>

<div id="react-native" />

<Accordion title="React Native">

앱스플라이어 React Native 플러그인은 앱 소유주와 앱 개발자가 iOS 14에 대비하도록 지원하고 안드로이드와 iOS 앱에 어트리뷰션과 이벤트 리포팅 기능을 제공합니다. 플러그인은 앱스플라이어 iOS 및 안드로이드 SDK와 기능적으로 동일합니다.

플러그인 버전을 최신 버전으로 업데이트하려면 다음을 수행하십시오. 

1. 기존 플러그인 버전을 제거하고 <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin/tree/dev/sdk-v6-beta">앱스플라이어 GitHub 가이드</Anchor>에 따라 최신 버전을 설치하십시오.
2. <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin/tree/dev/sdk-v6-beta#--v6-breaking-changes">필수 API 이름을 변경하거나 삭제</Anchor>하여 연동을 변경하십시오.

</Accordion>

<div id="segment" />

<Accordion title="세그먼트">

앱스플라이어 Segment 플러그인은 앱 소유주와 앱 개발자가 iOS 14에 대비하도록 지원하고 안드로이드와 iOS 앱에 어트리뷰션과 이벤트 리포팅 기능을 제공합니다. 플러그인은 앱스플라이어 iOS 및 안드로이드 SDK와 기능적으로 동일합니다.

기존 플러그인 버전을 업그레이드 하기 위해, 기존 버전을 삭제하고 <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/segment-appsflyer-ios/tree/dev/sdk-v6-beta">앱스플라이어 GitHub 가이드</Anchor>에 따라 최신 버전을 설치하십시오.

</Accordion>

<div id="cordova" />

<Accordion title="Cordova">

앱스플라이어 Cordova 플러그인은 앱 소유주와 앱 개발자가 iOS 14에 대비하도록 지원하며 안드로이드와 iOS 앱에 어트리뷰션과 이벤트 리포팅 기능을 제공합니다. 플러그인은 앱스플라이어 iOS 및 안드로이드 SDK와 기능적으로 동일합니다.

기존 플러그인 버전을 업그레이드 하기 위해, 기존 버전을 삭제하고 <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-cordova-plugin/tree/releases/6.x.x/6.0.x/6.0.1-beta">앱스플라이어 GitHub 가이드</Anchor>에 따라 최신 버전을 설치하십시오.

</Accordion>

<div id="flutter" />

<Accordion title="Flutter">

앱스플라이어 Flutter 플러그인은 앱 소유주와 앱 개발자가 iOS 14에 대비하도록 지원하며 안드로이드와 iOS 앱에 어트리뷰션과 이벤트 리포팅 기능을 제공합니다. 플러그인은 앱스플라이어 iOS 및 안드로이드 SDK와 기능적으로 동일합니다.

플러그인 버전을 업데이트하려면, 기존 버전을 제거하고 V6 버전을 `pubspec.yaml`pubspec.yamlpubspec.yaml에 추가하십시오. 앱스플라이어 개발 가이드 <Anchor target="_blank" href="https://pub.dev/packages/appsflyer_sdk">pub.dev guide</Anchor>에 있는 안내사항을 따르십시오.

</Accordion>

<div id="adobe-air" />

<Accordion title="Adobe AIR">

앱스플라이어 Adobe AIR 플러그인은 앱 소유주와 앱 개발자가 iOS 14에 대비하도록 지원하며 안드로이드와 iOS 앱에 어트리뷰션과 이벤트 리포팅 기능을 제공합니다. 플러그인은 앱스플라이어 iOS 및 안드로이드 SDK와 기능적으로 동일합니다.

기존 플러그인 버전을 업그레이드 하기 위해, 기존 버전을 삭제하고 <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/tree/dev/sdk-v6-beta">앱스플라이어 GitHub 가이드</Anchor>에 따라 최신 버전을 설치하십시오.

</Accordion>

<div data-zendesk-anchors="about-ios-sdk-v6=ios-sdk-v6-%EC%86%8C%EA%B0%9C update-to-ios-sdk-v6=ios-sdk-v6%EB%A1%9C-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8%ED%95%98%EA%B8%B0 plugins=%ED%94%8C%EB%9F%AC%EA%B7%B8%EC%9D%B8" />
