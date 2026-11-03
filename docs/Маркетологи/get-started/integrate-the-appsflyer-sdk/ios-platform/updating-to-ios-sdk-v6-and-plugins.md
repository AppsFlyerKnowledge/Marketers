---
title: Обновление до iOS SDK V6 и обновление плагинов
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
  edited_at: '2026-08-19T00:14:20Z'
  id: 360011571778
  locale: ru
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/ru/articles/360011571778
---
> **At a glance:** Обновите существующую интеграцию SDK/wrapper AppsFlyer для iOS до SDK iOS V6.

## Об SDK iOS V6

В этой статье идет речь об SDK V6.

SDK AppsFlyer для iOS V6:

* Позволяет владельцам и разработчикам приложений подготовиться к выходу iOS 14.
* Дает возможность запрашивать у пользователей разрешение на сбор IDFA.
* Предоставляет функции для атрибуции приложений и отчетности о событиях для мобильных приложений iOS.
* Удалите предыдущий плагин и замените его, следуя инструкциям в нашем <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin/tree/dev/sdk-v6-beta">руководство на GitHub</Anchor>.

Для получения полной информации о SDK V6 и о том, как интегрировать его в новое приложение, не имеющее более ранней версии AppsFlyer SDK, читайте наше <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">руководство по интеграции iOS SDK для маркетологов</Anchor>.

## Обновление до iOS SDK V6

Чтобы обновить SDK до iOS SDK V6, выполните следующие процедуры (1-5).

<div id="1-update-sdk-version" />

<Accordion title="1. Обновление версии SDK">

Загрузите и добавьте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">SDK V6</Anchor> в свой Xcode.

</Accordion>

<div id="2-implement-sdk-v6" />

<Accordion title="2. Внедрение SDK V6">

**Добавьте следующий код в инициализацию SDK**:

<Tabs>
<Tab title="Objective C">

В файле AppDelegate.h выполните следующие действия:

```objectivec
#import "AppDelegate.h"
#import <AppsFlyerLib/AppsFlyerLib.h>
#import <AppTrackingTransparency/AppTrackingTransparency.h>
#import <UserNotifications/UserNotifications.h>
@interface AppDelegate ()
@end
@implementation AppDelegate
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    // 1 - Получите настройки AppsFlyer из файла .plist
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
    // 2 - Замените 'appsFlyerDevKey' и `appleAppID` на ваш DevKey и идентификатор приложения Apple
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
        NSLog(@"This is a none organic install.", Media source: %@  Campaign: %@",sourceID,campaign);
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
    // Called when a new scene session is being created. // Используйте этот метод, чтобы выбрать конфигурацию для создания новой сцены. return [[UISceneConfiguration alloc] initWithName:@"Default Configuration" sessionRole:connectingSceneSession.role];
}
- (void)application:(UIApplication *)application didDiscardSceneSessions:(NSSet *)sceneSessions  API_AVAILABLE(ios(13.0)){
    // Вызывается, когда пользователь закрывает сессию сцены. // Если какие-либо сессии были закрыты, пока приложение не было запущено, этот метод будет вызван вскоре после application:didFinishLaunchingWithOptions. Media source: %@  Campaign: %@",sourceID,campaign);
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
    // Используйте этот метод, чтобы выбрать конфигурацию для создания новой сцены.
    return [[UISceneConfiguration alloc] initWithName:@"Default Configuration" sessionRole:connectingSceneSession.role];
}
- (void)application:(UIApplication *)application didDiscardSceneSessions:(NSSet *)sceneSessions  API_AVAILABLE(ios(13.0)){
    // Вызывается, когда пользователь закрывает сессию сцены.
    // Если какие-либо сессии были закрыты, пока приложение не было запущено, этот метод будет вызван вскоре после application:didFinishLaunchingWithOptions.
    // Используйте этот метод, чтобы освободить все ресурсы, которые были специфичны для закрытых сцен, так как они не будут восстановлены.
}
@end
```

</Tab>

<Tab title="Swift">

В файле AppDelegate.swift добавьте следующее:

```swift
import UIKit
import AppTrackingTransparency
import AppsFlyerLib
import UserNotifications
@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {
    var window: UIWindow?
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        // 1 - Get AppsFlyer preferences from .plist file
        guard let propertiesPath = Bundle.main.path(forResource: "afdevkey_donotpush", ofType: "plist"),
            let properties = NSDictionary(contentsOfFile: propertiesPath) as? func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
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
    func application(_ application: UIApplication, continue userActivity: NSUserActivity, restorationHandler: @escaping ([UIUserActivityRestoring]?) This demo app supports iOS 13 and above
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
            if let is_first_launch = data["is_first_launch"] as?
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

<Accordion title="3. Поддержка атрибуции в SKAdNetwork">

<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_the_participating_apps">SKAdNetwork</Anchor> — это класс, используемый в iOS для проверки установки приложений в результате просмотра рекламы. Для проверки установки нужны приложение-источник и рекламируемое приложения.

Приложение-источник — это приложение, которое участвует в рекламной кампании и показывает объявления, подписанные рекламной сетью. Настройка вашего приложения для показа рекламы не входит в задачи SDK AppsFlyer. Для настройки необходимо следовать <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_the_participating_apps">инструкциям iOS</Anchor>.

Для настройки рекламируемого приложения <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide">решение SKAdNetwork</Anchor> от AppsFlyer использует SKAdNetwork, чтобы предоставить рекламодателям и рекламным сетям аналитику LTV, отчеты и постбэки, сохраняя при этом конфиденциальность пользователей. При первом запуске приложения платформа AppsFlyer, используя конфигурацию, заданную маркетологом, указывает SDK, как установить значение конверсии SKAdNetwork.

Чтобы использовать решение <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide">SKAdNetwork</Anchor>:

* Разработчику не нужно что-либо делать.
* SDK AppsFlyer автоматически  вызывает необходимые API SKAdNetwork, то есть `registerAppForAdNetworkAttribution()` и `updateConversionValue()`. Разработчик не должен их вызывать.
* Не позволяйте другим SDK вызывать API SKAdNet. Это может привести к задержке отправки постбэков с iOS в AppsFlyer и изменению значения конверсии, которое мы используем для заполнения дэшборда SKAdNetwork данными измерения качества пользователей, настроенными маркетологом на дэшборде.
* Маркетолог должен настроить измерение SKAdNetwork <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide">в AppsFlyer</Anchor>.

В магазине приложений не требуется каких-либо действий или регистраций со стороны разработчика или маркетолога.

</Accordion>

<div id="4-change-apis" />

<Accordion title="4. Изменение API">

В SDK AppsFlyer для iOS V6 произошли некоторые изменения в названиях API. Чтобы изменить названия API из предыдущих версий SDK на текущие, смотрите следующую таблицу.

| Название API (до V6) | Текущее название API (V6 и более поздние версии) |
| --- | --- |
| AppsFlyerTracker | AppsFlyerLib |
| disableIAdTracking | disableCollectASA |
| trackAppLaunchWithCompletionHandler | startWithCompletionHandler |
| trackLocation | logLocation |
| trackAppLaunch | начать |
| trackEvent | logEvent |
| disableAppleAdSupportTracking | Согласие на сбор данных или отказ от него при запуске |
| validateAndTrackInAppPurchase | validateAndLogInAppPurchase |
| isStopTracking | isStopped |
| deviceTrackingDisabled/deviceLoggingDisabled | anonymizeUser |
| sharedTracker (Objective C) | Общий |

</Accordion>

<div id="5-ensure-push-notification-integration" />

<Accordion title="5. Обеспечьте интеграцию push-уведомлений">

Если интеграция push-уведомлений уже реализована, необходимо выполнить следующие действия.

Следуйте <Anchor target="_blank" href="/marketers/ru/docs/measuring-push-notification-re-engagement-campaigns">инструкциям по работе с push-уведомлениями</Anchor>, чтобы обеспечить интеграцию push-уведомлений с помощью метода handlePushNotificationData.

</Accordion>

## Плагины

Доступны следующие плагины V6:

<div id="unity" />

<Accordion title="Unity">

Плагин Unity V6 от AppsFlyer помогает владельцам и разработчикам приложений поддерживать iOS 14, предоставляя функции атрибуции приложений и отчетности о событиях в мобильных приложениях для Android и iOS, созданных на платформе разработки Unity. По функциональности этот плагин эквивалентен SDK AppsFlyer для iOS и Android.

Чтобы обновить свой плагин с более ранней версии, смотрите наши руководства по обновлению плагина до Unity V6:

* <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-plugin/blob/master/README.md#--migration">От плагина Unity V4</Anchor> (требуется удаление старого плагина)
* <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-plugin/blob/master/README.md#--migration">От плагина Unity V5</Anchor> (требуется обновление пакета Unity)

</Accordion>

<div id="react-native" />

<Accordion title="iOS native UnityReact Native">

Плагин React Native от AppsFlyer помогает владельцам и разработчикам приложений подготовиться к выходу iOS 14, предоставляя функции атрибуции приложений и отчетности о событиях в мобильных приложениях для Android и iOS. По функциональности этот плагин эквивалентен SDK AppsFlyer для iOS и Android.

Чтобы обновить плагин с более ранней версии:

1. Удалите предыдущий плагин и замените его, следуя инструкциям в нашем <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin/tree/dev/sdk-v6-beta">руководство на GitHub</Anchor>.
2. Измените код интеграции, <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin/tree/dev/sdk-v6-beta#--v6-breaking-changes">переименовав и удалив</Anchor> необходимые API.

</Accordion>

<div id="segment" />

<Accordion title="Подписка IAP">

Плагин Segment от AppsFlyer помогает владельцам и разработчикам приложений подготовиться к выходу iOS 14, предоставляя функции атрибуции приложений и отчетности о событиях для мобильных приложений на Android и iOS. По функциональности этот плагин эквивалентен SDK AppsFlyer для iOS и Android.

Чтобы обновить плагин с более ранней версии, удалите предыдущий плагин и замените его, следуя инструкциям в нашем <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/segment-appsflyer-ios/tree/dev/sdk-v6-beta">руководстве на GitHub</Anchor>.

</Accordion>

<div id="cordova" />

<Accordion title="Cordova">

Плагин Cordova от AppsFlyer помогает владельцам и разработчикам приложений подготовиться к выходу iOS 14, предоставляя функции атрибуции приложений и отчетности о событиях для мобильных приложений на Android и iOS. По функциональности этот плагин эквивалентен SDK AppsFlyer для iOS и Android.

Чтобы обновить плагин с более ранней версии, удалите предыдущий плагин и замените его, следуя инструкциям в нашем <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-cordova-plugin/tree/releases/6.x.x/6.0.x/6.0.1-beta">руководстве на GitHub</Anchor>.

</Accordion>

<div id="flutter" />

<Accordion title="Flutter">

Плагин Flutter от AppsFlyer помогает владельцам и разработчикам приложений подготовиться к выходу iOS 14, предоставляя функции атрибуции приложений и отчетности о событиях для мобильных приложений на Android и iOS. По функциональности этот плагин эквивалентен SDK AppsFlyer для iOS и Android.

Чтобы обновить свой плагин с более ранней версии, удалите его и добавьте версию V6 в `pubspec.yaml`, следуя инструкциям в нашем <Anchor target="_blank" href="https://pub.dev/packages/appsflyer_sdk">руководстве pub.dev</Anchor>.

</Accordion>

<div id="adobe-air" />

<Accordion title="Adobe AIR">

Плагин Adobe AIR от AppsFlyer помогает владельцам и разработчикам приложений подготовиться к выходу iOS 14, предоставляя функции атрибуции приложений и отчетности о событиях для мобильных приложений на Android и iOS. По функциональности этот плагин эквивалентен SDK AppsFlyer для iOS и Android.

Чтобы обновить плагин с более ранней версии, удалите предыдущий плагин и замените его, следуя инструкциям в нашем <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/tree/dev/sdk-v6-beta">руководстве на GitHub</Anchor>.

</Accordion>

<div data-zendesk-anchors="about-ios-sdk-v6=%D0%BE%D0%B1-sdk-ios-v6 update-to-ios-sdk-v6=%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%BE-ios-sdk-v6 plugins=%D0%BF%D0%BB%D0%B0%D0%B3%D0%B8%D0%BD%D1%8B" />
