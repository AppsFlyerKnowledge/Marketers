---
title: Actualización al SDK V6 para iOS y a los plugins
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
  edited_at: '2026-08-22T00:14:23Z'
  id: 360011571778
  locale: es
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/es/articles/360011571778
---
> **At a glance:** Actualiza una integración existente del SDK/wrapper de AppsFlyer para iOS al SDK V6 para iOS.

## Acerca del SDK V6 para iOS

Referencia en este artículo al SDK V6.

El SDK V6 de AppsFlyer para iOS:

* Permite a los propietarios y desarrolladores de apps prepararse para el lanzamiento de iOS 14.
* Te da la opción de pedir permiso a los usuarios para recopilar el IDFA.
* Proporciona funcionalidad de atribución de aplicaciones y reporte de eventos a las aplicaciones móviles de iOS.
* Incluye cambios significativos en el método de API con respecto a versiones anteriores.

Para obtener información completa sobre el SDK V6 e integrarlo en una nueva aplicación que no tenga una versión anterior del SDK de AppsFlyer, lee nuestra <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">guía de integración del SDK para iOS para marketers</Anchor>.

## Actualización al SDK V6 para iOS

Para actualizar al SDK V6 para iOS, completa los pasos (1-5) que se indican a continuación.

<div id="1-update-sdk-version" />

<Accordion title="1. Actualizar la versión del SDK">

Descarga y añade el <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">SDK V6</Anchor> a Xcode.

</Accordion>

<div id="2-implement-sdk-v6" />

<Accordion title="2. Implementar el SDK V6">

**Añade el siguiente código a la inicialización del SDK**:

<Tabs>
<Tab title="Objective-C">

En AppDelegate.h, haz lo siguiente:

```objectivec
#import "AppDelegate.h"
#import <AppsFlyerLib/AppsFlyerLib.h>
#import <AppTrackingTransparency/AppTrackingTransparency.h>
#import <UserNotifications/UserNotifications.h>
@interface AppDelegate ()
@end
@implementation AppDelegate
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    // 1 - Obtén las preferencias de AppsFlyer del archivo .plist
    NSString *path = [[NSBundle mainBundle] pathForResource:@"afdevkey_donotpush" ofType:@".plist"];
    NSDictionary* properties = [NSDictionary dictionaryWithContentsOfFile:path];
    if (properties == nil || path == nil) {
        [NSException raise:@"Error" format:@"No se puede encontrar el archivo .plist"];
    }
    NSString* appsFlyerDevKey = [properties objectForKey:@"appsFlyerDevKey"];
    NSString* appleAppID = [properties objectForKey:@"appleAppID"];
    if (appsFlyerDevKey == nil || appleAppID == nil) {
        [NSException raise:@"Error" format:@"No se puede encontrar appsFlyerDevKey o appleAppID"];
    }
    // 2 - Sustituye 'appsFlyerDevKey' y `appleAppID` por tu DevKey y tu ID de app de Apple
    [[AppsFlyerLib shared] setAppsFlyerDevKey:appsFlyerDevKey];
    [[AppsFlyerLib shared] setAppleAppID:appleAppID];
    [AppsFlyerLib shared].delegate = self;
    //  Establece isDebug en true para ver los registros de depuración de AppsFlyer
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
// Abrir esquema de URI para iOS 9 y versiones posteriores
- (BOOL)application:(UIApplication *)application openURL:(NSURL *)url options:(NSDictionary *) options {
    [[AppsFlyerLib shared] handleOpenUrl:url options:options];
    return YES;
}
// Abrir esquema de URI para iOS 8 y versiones anteriores
- (BOOL)application:(UIApplication *)application openURL:(NSURL *)url sourceApplication:(NSString*)sourceApplication annotation:(id)annotation {
    [[AppsFlyerLib shared] handleOpenURL:url sourceApplication:sourceApplication withAnnotation:annotation];
    return YES;
}
// Abrir enlaces universales
- (BOOL)application:(UIApplication *)application continueUserActivity:(NSUserActivity *)userActivity restorationHandler:(void (^)(NSArray * _Nullable))restorationHandler {
    [[AppsFlyerLib shared] continueUserActivity:userActivity restorationHandler:restorationHandler];
    return YES;
}
// Informar de los datos de atribución de notificaciones push para los re-engagements
- (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)userInfo fetchCompletionHandler:(void (^)(UIBackgroundFetchResult))completionHandler {
    [[AppsFlyerLib shared] handlePushNotification:userInfo];
}
// Implementación de AppsFlyerLib
//Gestionar datos de conversión (deep link diferido)
-(void)onConversionDataSuccess:(NSDictionary*) installData {
    id status = [installData objectForKey:@"af_status"];
    if([status isEqualToString:@"Non-organic"]) {
        id sourceID = [installData objectForKey:@"media_source"];
        id campaign = [installData objectForKey:@"campaign"];
        NSLog(@"Se trata de una instalación no orgánica. Fuente de medios: %@  Campaña: %@",sourceID,campaign);
    } else if([status isEqualToString:@"Organic"]) {
        NSLog(@"Se trata de una instalación orgánica.");
    }
}
-(void)onConversionDataFail:(NSError *) error {
    NSLog(@"%@",error);
}
//Gestionar deep link directo
- (void) onAppOpenAttribution:(NSDictionary*) attributionData {
    NSLog(@"%@",attributionData);
}
- (void) onAppOpenAttributionFailure:(NSError *)error {
    NSLog(@"%@",error);
}
// soporte para delegado de escena
#pragma mark - Ciclo de vida de UISceneSession
- (UISceneConfiguration *)application:(UIApplication *)application configurationForConnectingSceneSession:(UISceneSession *)connectingSceneSession options:(UISceneConnectionOptions *)options API_AVAILABLE(ios(13)){
    // Se llama cuando se crea una nueva sesión de escena.
    // Usa este método para seleccionar una configuración para crear la nueva escena.
    return [[UISceneConfiguration alloc] initWithName:@"Default Configuration" sessionRole:connectingSceneSession.role];
}
- (void)application:(UIApplication *)application didDiscardSceneSessions:(NSSet *)sceneSessions  API_AVAILABLE(ios(13.0)){
    // Se llama cuando el usuario descarta una sesión de escena.
    // Si se ha descartado alguna sesión mientras la aplicación no estaba en funcionamiento, esto se llamará poco después de application:didFinishLaunchingWithOptions.
    // Usa este método para liberar los recursos específicos de las escenas descartadas, ya que no volverán.
}
@end
```

</Tab>

<Tab title="Swift">

En AppDelegate.swift, agrega lo siguiente:

```swift
import UIKit
import AppTrackingTransparency
import AppsFlyerLib
import UserNotifications
@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {
    var window:
    UIWindow?
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        // 1 - Get AppsFlyer preferences from .plist file
        guard let propertiesPath = Bundle.main.path(forResource: "afdevkey_donotpush", ofType: "plist"),
            let properties = NSDictionary(contentsOfFile: propertiesPath) as? [String:String] else {
                fatalError("No se puede encontrar `afdevkey_donotpush`")
        }
        guard let appsFlyerDevKey = properties["appsFlyerDevKey"],
                   let appleAppID = properties["appleAppID"] else {
            fatalError("No se puede encontrar la clave `appsFlyerDevKey` o `appleAppID`")
        }
        // 2 - Sustituye 'appsFlyerDevKey' y `appleAppID` por tu DevKey y tu ID de app de Apple
        AppsFlyerLib.shared().appsFlyerDevKey = appsFlyerDevKey
        AppsFlyerLib.shared().appleAppID = appleAppID
        AppsFlyerLib.shared().delegate = self
        //  Establece isDebug en true para ver los registros de depuración de AppsFlyer
        AppsFlyerLib.shared().isDebug = true

        // iOS 10 o posterior
        if #available(iOS 10, *) {
            UNUserNotificationCenter.current().requestAuthorization(options: [.badge, .alert, .sound]) { _, _ in }
            application.registerForRemoteNotifications()
        }
        // soporte para iOS 9: se proporciona como referencia. This demo app supports iOS 13 and above
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
    // func application(_ application: UIApplication, continue userActivity: UIApplication, continue userActivity: NSUserActivity, restorationHandler: @escaping ([Any]?) -> Void) -> Bool { // this line for Swift < 4.2
    func application(_ application: NSUserActivity, restorationHandler: @escaping ([UIUserActivityRestoring]?) -> Void) -> Bool {
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
                    print("Esta es una instalación no orgánica. Media source: \(sourceID)  Campaign: \(campaign)")
                }
            } else {
                print("This is an organic install.")
            }
            if let is_first_launch = data["is_first_launch"] as?
            }
            if let is_first_launch = data["is_first_launch"] as? Bool,
                is_first_launch {
                print("Primer inicio")
            } else {
                print("No es el primer inicio")
            }
        }
    }
    func onConversionDataFail(_ error: Error) {
        print("\(error)")
    }
    // Gestiona Deep Linking
    func onAppOpenAttribution(_ attributionData: [AnyHashable: Any]) {
        // Gestiona los Datos de atribución de Deep Linking
        print("Datos de onAppOpenAttribution:")
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

<Accordion title="3. Soporte de la atribución de SKAdNetwork">

<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_the_participating_apps">SKAdNetwork</Anchor> es una clase usada por iOS que valida las instalaciones de aplicaciones impulsadas por los anunciantes. El proceso de validación de la instalación de la aplicación implica la aplicación fuente y la aplicación anunciada.

Una aplicación fuente es una aplicación que participa en campañas publicitarias mostrando los anuncios firmados por una red de publicidad. La configuración de tu aplicación para mostrar anuncios no está dentro del alcance del SDK de AppsFlyer. Para configurarla, debes seguir las instrucciones de <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_the_participating_apps">iOS</Anchor>.

Para configurar la aplicación anunciada, la <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">Solución SKAdNetwork</Anchor> de AppsFlyer utiliza SKAdNetwork para proporcionar a los anunciantes y a las redes de publicidad análisis, reportes y postbacks de LTV, al tiempo que se mantiene la privacidad del usuario. Al iniciar la aplicación por primera vez, la plataforma AppsFlyer, utilizando la configuración establecida por el marketer, le indica al SDK cómo establecer el valor de conversión de SKAdNetwork.

Para usar la <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">Solución SKAdNetwork</Anchor>:

* El desarrollador no hace nada.
* El SDK de AppsFlyer llama automáticamente a las API necesarias de SKAdNetwork, es decir `registerAppForAdNetworkAttribution()` y `updateConversionValue()`. El desarrollador no debe llamarlas.
* No permitas que otros SDK llamen a las API de SKAdNet. Si así lo hacen, es posible que se retrase en el envío del postback por parte de iOS a AppsFlyer y que cambie el valor de conversión que usamos para completar el panel de control de SKAdNetwork con datos de medición de la calidad del usuario según lo configurado por el marketer en el panel de control.
* El marketer debe configurar la medición de SKAdNetwork <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">en AppsFlyer</Anchor>.

No se requiere ninguna otra acción o proceso de registro por parte del desarrollador o del marketer en el App Store.

</Accordion>

<div id="4-change-apis" />

<Accordion title="4. Cambiar las API">

El SDK V6 de AppsFlyer para iOS tiene algunos cambios en el nombre de la API. Consulta la siguiente tabla para cambiar los nombres de API de las versiones anteriores del SDK a los nombres actuales.

| Nombre de la API (antes de V6) | Nombre de la API actual (V6 y posteriores) |
| --- | --- |
| AppsFlyerTracker | AppsFlyerLib |
| disableIAdTracking | disableCollectASA |
| trackAppLaunchWithCompletionHandler | startWithCompletionHandler |
| trackLocation | logLocation |
| trackAppLaunch | comenzar |
| trackEvent | logEvent |
| disableAppleAdSupportTracking | Si llamas a `anonymizeUser` antes del `start` de la llamada, no se producirá ninguna atribución. |
| validateAndTrackInAppPurchase | validateAndLogInAppPurchase |
| isStopTracking | isStopped |
| deviceTrackingDisabled/deviceLoggingDisabled | anonymizeUser |
| sharedTracker (Objective C) | Compartido |

</Accordion>

<div id="5-ensure-push-notification-integration" />

<Accordion title="5. Garantizar la integración de notificaciones push">

Lo siguiente es necesario si la integración de notificaciones push ya está implementada.

Sigue las <Anchor target="_blank" href="/marketers/es/docs/measuring-push-notification-re-engagement-campaigns">instrucciones de notificación push</Anchor> para asegurarte de que tienes las notificaciones push integradas mediante el método handlePushNotificationData.

</Accordion>

## Plugins

Están disponibles los siguientes plugins V6:

<div id="unity" />

<Accordion title="Unity">

El plugin Unity V6 de AppsFlyer ayuda a los propietarios y desarrolladores de aplicaciones a dar soporte a iOS 14, proporcionando funcionalidad de atribución de aplicaciones y reporte de eventos a las aplicaciones móviles de Android e iOS desarrolladas en la plataforma de desarrollo Unity. El plugin es funcionalmente equivalente a los SDK de AppsFlyer para iOS y Android.

Para actualizar tu plugin desde una versión anterior, consulta nuestras guías sobre la actualización al plugin de Unity V6:

* <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-plugin/blob/master/README.md#--migration">Desde el plugin de Unity V4</Anchor> (requiere la eliminación del plugin anterior)
* <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-plugin/blob/master/README.md#--migration">Desde el plugin de Unity V5</Anchor> (requiere una actualización del paquete de Unity)

</Accordion>

<div id="react-native" />

<Accordion title="React Native">

El plugin de React Native de AppsFlyer ayuda a los propietarios y desarrolladores de aplicaciones a prepararse para iOS 14, proporcionando funcionalidad de atribución de aplicaciones y reporte de eventos a las aplicaciones móviles de Android e iOS. El plugin es funcionalmente equivalente a los SDK de AppsFlyer para iOS y Android.

Para actualizar tu plugin desde una versión anterior:

1. Elimina el plugin anterior y reemplázalo siguiendo las instrucciones de nuestra <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin/tree/dev/sdk-v6-beta">guía de GitHub</Anchor>.
2. Cambia el código de integración <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin/tree/dev/sdk-v6-beta#--v6-breaking-changes">renombrando y eliminando</Anchor> las API necesarias.

</Accordion>

<div id="segment" />

<Accordion title="Segmento">

El plugin de Segment de AppsFlyer ayuda a los propietarios y desarrolladores de aplicaciones a prepararse para iOS 14, proporcionando funcionalidad de atribución de aplicaciones y reporte de eventos a las aplicaciones móviles de Android e iOS. El plugin es funcionalmente equivalente a los SDK de AppsFlyer para iOS y Android.

Para actualizar tu plugin desde una versión anterior, elimina el plugin anterior y reemplázalo siguiendo las instrucciones de nuestra <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/segment-appsflyer-ios/tree/dev/sdk-v6-beta">guía de GitHub</Anchor>.

</Accordion>

<div id="cordova" />

<Accordion title="Cordova">

El plugin de Cordova de AppsFlyer ayuda a los propietarios y desarrolladores de aplicaciones a prepararse para iOS 14, proporcionando funcionalidad de atribución de aplicaciones y reporte de eventos a las aplicaciones móviles de Android e iOS. El plugin es funcionalmente equivalente a los SDK de AppsFlyer para iOS y Android.

Para actualizar tu plugin desde una versión anterior, elimina el plugin anterior y reemplázalo siguiendo las instrucciones de nuestra <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-cordova-plugin/tree/releases/6.x.x/6.0.x/6.0.1-beta">guía de GitHub</Anchor>.

</Accordion>

<div id="flutter" />

<Accordion title="Flutter">

El plugin de Flutter de AppsFlyer ayuda a los propietarios y desarrolladores de aplicaciones a prepararse para iOS 14, proporcionando funcionalidad de atribución de aplicaciones y reporte de eventos a las aplicaciones móviles de Android e iOS. El plugin es funcionalmente equivalente a los SDK de AppsFlyer para iOS y Android.

Para actualizar tu plugin desde una versión anterior, elimina el plugin anterior y agrega la versión V6 a `pubspec.yaml`, siguiendo las instrucciones de nuestra <Anchor target="_blank" href="https://pub.dev/packages/appsflyer_sdk">guía de pub.dev</Anchor>.

</Accordion>

<div id="adobe-air" />

<Accordion title="Adobe AIR">

El plugin de Adobe AIR de AppsFlyer ayuda a los propietarios y desarrolladores de aplicaciones a prepararse para iOS 14, proporcionando funcionalidad de atribución de aplicaciones y reporte de eventos a las aplicaciones móviles de Android e iOS. El plugin es funcionalmente equivalente a los SDK de AppsFlyer para iOS y Android.

Para actualizar tu plugin desde una versión anterior, elimina el plugin anterior y reemplázalo siguiendo las instrucciones de nuestra <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/tree/dev/sdk-v6-beta">guía de GitHub</Anchor>.

</Accordion>

<div data-zendesk-anchors="about-ios-sdk-v6=acerca-del-sdk-v6-para-ios update-to-ios-sdk-v6=actualizaci%C3%B3n-al-sdk-v6-para-ios" />
