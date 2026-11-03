---
title: Mise à jour vers la V6 du SDK iOS et plugins
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
  edited_at: '2024-07-01T13:35:28Z'
  id: 360011571778
  locale: fr
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/fr/articles/360011571778
---
> **En bref :** mettre à jour l’intégration existante du SDK/Wrapper iOS AppsFlyer vers le SDK iOS V6.

## À propos du SDK iOS V6

Référence au SDK V6 dans cet article.

Le SDK iOS V6 AppsFlyer :

* Permet aux propriétaires d'apps et développeurs de préparer la sortie d'iOS 14.
* Vous permet de demander aux utilisateurs l'autorisation de collecter leur IDFA.
* Ouvre des fonctionnalités permettant aux apps mobile iOS d’attribuer les apps, et de créer des rapports d'événements.
* Modifie grandement le fonctionnement des API par rapport aux versions précédentes.

Pour obtenir plus d’infos sur le SDK V6 et savoir comment l'intégrer à une nouvelle app ne disposant pas de la version antérieure du SDK AppsFlyer, consultez notre <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">guide d'intégration du SDK iOS pour les marketeurs.</Anchor>

## Mise à jour vers le SDK iOS V6

Pour effectuer la mise à jour vers le SDK iOS V6, suivez les étapes ci-dessous (1 à 5).

<div id="1-update-sdk-version" />

<Accordion title="1. Mettre à jour la version du SDK">

Téléchargez le <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">SDK V6</Anchor> et ajoutez-le à votre Xcode.

</Accordion>

<div id="2-implement-sdk-v6" />

<Accordion title="2. Implémenter le SDK V6">

**Ajoutez le code ci-dessous à l'initialisation du SDK** :

<Tabs>
<Tab title="Objective-C">

Dans AppDelegate.h, ajoutez ce qui suit :

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

Dans AppDelegate.swift, ajoutez ce qui suit :

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

<Accordion title="3. Prise en charge de l'attribution SKAdNetwork">

<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_the_participating_apps">SkadNetwork</Anchor>  est une classe utilisée par iOS pour valider les installations d'apps pilotées par les annonceurs. Le processus de validation de l’installation d'une app inclut l'app source et l'app à promouvoir.

Une app source est une app qui participe aux campagnes publicitaires en diffusant les publicités d’un réseau publicitaire. Configurer votre app pour qu’elle affiche des publicités n’est pas du ressort du SDK AppsFlyer. Pour effectuer la configuration, vous devez suivre les <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_the_participating_apps">instructions d'iOS</Anchor>.

Pour configurer l'app à promouvoir, la solution AppsFlyer <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">SkadNetwork  utilise le SkadNetwork</Anchor> pour offrir aux annonceurs et réseaux publicitaires des analyses LTV, rapports et postbacks, tout en préservant la confidentialité des utilisateurs. Lorsque l'app est lancée pour la première fois, la plateforme AppsFlyer se base sur la configuration définie par le marketeur pour indiquer au SDK comment définir la valeur de conversion SKADNetwork.

Pour utiliser la <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">Solution SKAdNetwork</Anchor> :

* Le développeur n'a rien à faire.
* Le SDK AppsFlyer appelle automatiquement les API SKAdNetwork dont il a besoin. Le développeur ne doit pas les appeler de son côté.
* N'autorisez pas d'autres SDK à appeler les API SKAdNet. Cela risquerait de retarder l'envoi du postback à AppsFlyer par IOS, et de modifier la valeur de conversion que nous utilisons pour remplir le tableau de bord SKAdNetwork, et qui se base sur les chiffres de niveau utilisateur définis par le marketeur dans le tableau de bord.
* Le marketeur doit configurer la mesure SKAdNetwork <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">dans AppsFlyer</Anchor>.

Aucune autre action ou procédure d'inscription n'est attendue du développeur ou du marketeur dans l'app store.

</Accordion>

<div id="4-change-apis" />

<Accordion title="4. Modifier les API">

Le SDK AppsFlyer iOS V6 comporte quelques modifications concernant les noms d'API. Consultez le tableau suivant pour remplacer les noms d'API des anciennes versions du SDK par les nouveaux noms.

| Nom de l'API (avant V6) | Nouveau nom de l'API (V6 et +) |
| --- | --- |
| AppsFlyerTracker | AppsFlyerLib |
| disableIAdTracking | disableCollectASA |
| trackAppLaunchWithCompletionHandler | startWithCompletionHandler |
| trackLocation | logLocation |
| trackAppLaunch | Démarrer |
| trackEvent | logEvent |
| disableAppleAdSupportTracking | disableAdvertisingIdentifier |
| validateAndTrackInAppPurchase | validateAndLogInAppPurchase |
| isStopTracking | isStopped |
| deviceTrackingDisabled/deviceLoggingDisabled | anonymizeUser |
| sharedTracker (Objective C) | shared |

</Accordion>

<div id="5-ensure-push-notification-integration" />

<Accordion title="5. Garantir l'intégration des notifications push">

Les informations suivantes sont nécessaires si l'intégration des notifications push est déjà en place.

Suivez les <Anchor target="_blank" href="/marketers/fr/docs/measuring-push-notification-re-engagement-campaigns">instructions concernant les notifications push</Anchor> pour que les notifications push soient bien intégrées via la méthode handle Push NotificationData.

</Accordion>

## Les plugins

Les plugins V6 suivants sont disponibles :

<div id="unity" />

<Accordion title="Unity">

Le plugin AppsFlyer Unity V6 permet aux propriétaires et développeurs d'apps de prendre en charge iOS 14, en offrant des fonctionnalités d'attribution d'app et de création de rapports d'événements aux apps mobile Android et iOS qui ont été développées sur la plateforme Unity. Le plugin fonctionne de la même manière que les SDK iOS et Android AppsFlyer.

Pour obtenir la dernière version de votre plugin, consultez nos guides sur la mise à jour vers le plugin Unity V6 :

* <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-plugin/blob/master/README.md#--migration">Depuis le plugin Unity V4</Anchor> (nécessite la suppression de l'ancien plugin)
* <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-plugin/blob/master/README.md#--migration">Depuis le plugin Unity V5</Anchor> (nécessite une mise à jour du package Unity)

</Accordion>

<div id="react-native" />

<Accordion title="React Native">

Le plugin AppsFlyer React Native permet aux propriétaires et développeurs d'apps de prendre en charge iOS 14, en offrant des fonctionnalités d'attribution d'app et de création de rapports d'événements aux apps mobile Android et iOS. Le plugin fonctionne de la même manière que les SDK iOS et Android AppsFlyer.

Pour mettre à jour votre plugin depuis une ancienne : 

1. Supprimez l’ancien plugin puis remplacez-le en suivant les instructions contenues dans notre <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin/tree/dev/sdk-v6-beta">guide GitHub</Anchor>.
2. Modifiez le code d'intégration en <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin/tree/dev/sdk-v6-beta#--v6-breaking-changes">renommant et en supprimant</Anchor> les API selon les besoins.

</Accordion>

<div id="segment" />

<Accordion title="Segment">

Le plugin AppsFlyer Segment permet aux propriétaires et développeurs d'apps de prendre en charge iOS 14, en offrant des fonctionnalités d'attribution d'app et de création de rapports d'événements aux apps mobile Android et iOS. Le plugin fonctionne de la même manière que les SDK iOS et Android AppsFlyer.

Pour mettre à jour votre plugin depuis une version antérieure, supprimez l'ancien plugin et remplacez-le en suivant les instructions détaillées dans notre guide <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/segment-appsflyer-ios/tree/dev/sdk-v6-beta">GitHub</Anchor>.

</Accordion>

<div id="cordova" />

<Accordion title="Cordova">

Le plugin AppsFlyer Cordova permet aux propriétaires et développeurs d'apps de prendre en charge iOS 14, en offrant des fonctionnalités d'attribution d'app et de création de rapports d'événements aux apps mobile Android et iOS. Le plugin fonctionne de la même manière que les SDK iOS et Android AppsFlyer.

Pour mettre à jour votre plugin depuis une version antérieure,supprimez l'ancien plugin et remplacez-le en suivant les instructions détaillées dans notre guide <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-cordova-plugin/tree/releases/6.x.x/6.0.x/6.0.1-beta">GitHub</Anchor>.

</Accordion>

<div id="flutter" />

<Accordion title="Flutter">

Le plugin AppsFlyer Flutter permet aux propriétaires et développeurs d'apps de prendre en charge iOS 14, en offrant des fonctionnalités d'attribution d'app et de création de rapports d'événements aux apps mobile Android et iOS. Le plugin fonctionne de la même manière que les SDK iOS et Android AppsFlyer.

Pour mettre à jour votre plugin depuis une version antérieure, supprimez l'ancien plugin et ajoutez la version V6 à `pubspec.yaml`, en suivant les instructions de notre <Anchor target="_blank" href="https://pub.dev/packages/appsflyer_sdk">guide pub.dev.</Anchor>

</Accordion>

<div id="adobe-air" />

<Accordion title="Adobe AIR">

Le plugin AppsFlyer Adobe AIR permet aux propriétaires et développeurs d'apps de prendre en charge iOS 14, en offrant des fonctionnalités d'attribution d'app et de création de rapports d'événements aux apps mobile Android et iOS. Le plugin fonctionne de la même manière que les SDK iOS et Android AppsFlyer.

Pour mettre à jour votre plugin depuis une version antérieure,supprimez l'ancien plugin et remplacez-le en suivant les instructions détaillées dans notre guide <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/tree/dev/sdk-v6-beta">GitHub</Anchor>.

</Accordion>

<div data-zendesk-anchors="about-ios-sdk-v6=%C3%A0-propos-du-sdk-ios-v6 update-to-ios-sdk-v6=mise-%C3%A0-jour-vers-le-sdk-ios-v6 plugins=les-plugins" />
