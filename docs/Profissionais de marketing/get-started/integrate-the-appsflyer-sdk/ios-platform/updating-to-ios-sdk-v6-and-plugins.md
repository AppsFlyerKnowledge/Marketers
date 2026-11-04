---
title: Atualização para o iOS SDK V6 e plug-ins
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
  edited_at: '2026-08-19T00:14:15Z'
  id: 360011571778
  locale: pt
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/pt/articles/360011571778
---
> **At a glance:** **Visão geral:** Atualize uma integração existente do SDK/wrapper do iOS da AppsFlyer para o SDK V6 do iOS.

<div id="about-ios-sdk-v6" />

## Sobre o iOS SDK V6

Referência neste artigo ao SDK V6.

O SDK V6 para iOS da AppsFlyer:

* Permite que os proprietários de aplicativo e os desenvolvedores se preparem para o lançamento do iOS 14.
* Oferece a opção de pedir autorização aos usuários para coletar IDFA.
* Fornece atribuição do app e funcionalidade de reportar eventos para apps móveis iOS.
* Inclui alterações significativas dos métodos API relativamente às versões anteriores.

Para obter informações completas sobre o SDK V6 e para integrá-lo a um novo app que não tenha uma versão anterior do SDK da AppsFlyer, leia nosso <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">guia de integração do SDK do iOS para profissionais de marketing</Anchor>.

<div id="update-to-ios-sdk-v6" />

## Atualização para iOS SDK V6

Para atualizar para o iOS SDK V6, execute os procedimentos (1-5) abaixo:

<div id="1-update-sdk-version" />

<Accordion title="1. Atualize a versão do SDK">

Baixe e adicione o <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">SDK V6</Anchor> ao seu Xcode.

</Accordion>

<div id="2-implement-sdk-v6" />

<Accordion title="2. Implemente o SDK V6">

**Adicione o seguinte código à inicialização do SDK**:

<Tabs>
<Tab title="Objetivo-C">

Em AppDelegate.h, faça o seguinte:

```objectivec
#import "AppDelegate.h"
#import <AppsFlyerLib/AppsFlyerLib.h>
#import <AppTrackingTransparency/AppTrackingTransparency.h>
#import <UserNotifications/UserNotifications.h>
@interface AppDelegate ()
@end
@implementation AppDelegate
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    // 1 - Obtenha as preferências da AppsFlyer no arquivo .plist
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
    // 2 - Substitua 'appsFlyerDevKey' e `appleAppID` pela sua DevKey e pelo Apple App ID
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
// Abra o esquema de URI para iOS 9 e versões posteriores
- (BOOL)application:(UIApplication *)application openURL:(NSURL *)url options:(NSDictionary *) options {
    [[AppsFlyerLib shared] handleOpenUrl:url options:options];
    return YES;
}
// Abra o esquema de URI para iOS 8 e versões anteriores
- (BOOL)application:(UIApplication *)application openURL:(NSURL *)url sourceApplication:(NSString*)sourceApplication annotation:(id)annotation {
    [[AppsFlyerLib shared] handleOpenURL:url sourceApplication:sourceApplication withAnnotation:annotation];
    return YES;
}
// Abra links universais
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
    // Use este método para selecionar uma configuração para criar a nova cena com ela.
    return [[UISceneConfiguration alloc] initWithName:@"Default Configuration" sessionRole:connectingSceneSession.role];
}
- (void)application:(UIApplication *)application didDiscardSceneSessions:(NSSet *)sceneSessions  API_AVAILABLE(ios(13.0)){
    // Chamado quando o usuário descarta uma sessão de cena.
    // Se alguma sessão tiver sido descartada enquanto o aplicativo não estava em execução, isso será chamado logo após application:didFinishLaunchingWithOptions.
    // Use este método para liberar quaisquer recursos específicos das cenas descartadas, pois elas não retornarão.
}
@end
```

</Tab>

<Tab title="Swift">

Em AppDelegate.swift, adicione o seguinte:

```swift
import UIKit
import AppTrackingTransparency
import AppsFlyerLib
import UserNotifications
@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {
    var window: UIWindow?
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication. LaunchOptionsKey: Any]?) -> Bool {
        // 1 - Get AppsFlyer preferences from .plist file
        guard let propertiesPath = Bundle.main.path(forResource: "afdevkey_donotpush", ofType: "plist"),
            let properties = NSDictionary(contentsOfFile: propertiesPath) as? [String:String] else {
                fatalError("Não foi possível encontrar `afdevkey_donotpush`")
        }
        guard let appsFlyerDevKey = properties["appsFlyerDevKey"],
                   let appleAppID = properties["appleAppID"] else {
            fatalError("Não foi possível encontrar a chave `appsFlyerDevKey` ou `appleAppID`")
        }
        // 2 - Substitua 'appsFlyerDevKey' e `appleAppID` pela sua DevKey e pelo Apple App ID
        AppsFlyerLib.shared().appsFlyerDevKey = appsFlyerDevKey
        AppsFlyerLib.shared().appleAppID = appleAppID
        AppsFlyerLib.shared().delegate = self
        //  Set isDebug to true to see AppsFlyer debug logs
        AppsFlyerLib.shared().isDebug = true

        // iOS 10 ou posterior
        if #available(iOS 10, *) {
            UNUserNotificationCenter.current().requestAuthorization(options: [.badge, .alert, .sound]) { _, _ in }
            application.registerForRemoteNotifications()
        }
        // suporte ao iOS 9 - Fornecido como referência. This demo app supports iOS 13 and above
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
    func application(_ app: UIApplication, open url: URL, options: -> Void) -> Bool { // esta linha para Swift < 4.2
    func application(_ application: UIApplication, continue userActivity: NSUserActivity, restorationHandler: @escaping ([UIUserActivityRestoring]?) -> Void) -> Bool {
        AppsFlyerLib.shared().continue(userActivity, restorationHandler: nil)
        return true
    }
    // Abrir deeplinks
    // Abra o esquema de URI para iOS 8 e versões anteriores
    func application(_ application: UIApplication, open url: URL, sourceApplication: String?, annotation: Any) -> Bool {
        AppsFlyerLib.shared().handleOpen(url, sourceApplication: sourceApplication, withAnnotation: annotation)
        return true
    }
    // Abra o esquema de URI para iOS 9 e versões posteriores
    func application(_ app: UIApplication, open url: URL, options: [UIApplication.OpenURLOptionsKey : Any] = [:]) -> Bool {
        AppsFlyerLib.shared().handleOpen(url, options: options)
        return true
    }
    // Reporte os dados de atribuição da notificação push para reengajamentos
    func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
        AppsFlyerLib.shared().handlePushNotification(userInfo)
    }
}
extension AppDelegate: AppsFlyerLibDelegate {
    // Tratar instalação orgânica/não orgânica
    func onConversionDataSuccess(_ data: [AnyHashable: Any]) {
        print("dados de onConversionDataSuccess:")
        for (key, value) in data {
            print(key, ":", value)
        }
        if let status = data["af_status"] as? String {
            if (status == "Non-organic") {
                if let sourceID = data["media_source"],
                    let campaign = data["campaign"] {
                    print("Esta é uma instalação não orgânica. Media source: \(sourceID)  Campaign: \(campaign)")
                }
            } else {
                print("This is an organic install.")
            }
            if let is_first_launch = data["is_first_launch"] as?
            }
            if let is_first_launch = data["is_first_launch"] as? Bool,
                is_first_launch {
                print("Primeira inicialização")
            } else {
                print("Não é a primeira inicialização")
            }
        }
    }
    func onConversionDataFail(_ error: Error) {
        print("\(error)")
    }
    // Tratar deeplink
    func onAppOpenAttribution(_ attributionData: [AnyHashable: Any]) {
        //Tratar dados de Deep Link
        print("dados de onAppOpenAttribution:")
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

<Accordion title="3. Compatibilidade com atribuição do SkadNetwork">

<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_the_participating_apps">SKAdNetwork</Anchor> é uma classe usada pelo iOS que valida as instalações de apps impulsionadas pelos anunciantes. O processo de validação da instalação do app envolve o app de origem e o app anunciado.

Um app de fonte é um app que participa de campanhas publicitárias exibindo anúncios assinados por uma ad network. Configurar seu aplicativo para exibir anúncios não está dentro do escopo do SDK da AppsFlyer. Para configurar, é necessário seguir as <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_the_participating_apps">instruções do iOS</Anchor>.

Para configurar o app anunciado,  a<Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">solução SKAdNetwork</Anchor> da AppsFlyer  usa a SKAdNetwork para fornecer aos anunciantes e às ad networks análises, relatórios e postbacks de LTV, mantendo a privacidade do usuário. Ao lançar o app pela primeira vez, a plataforma AppsFlyer, usando a configuração definida pelo profissional de marketing, instrui o SDK sobre como definir o valor de conversão SKAdNetwork.

Para usar a <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">solução SkadNetwork</Anchor>:

* O desenvolvedor não faz nada.
* O SDK da AppsFlyer chama automaticamente as APIs do SKAdNetwork necessárias, ou seja `registerAppForAdNetworkAttribution()` e `updateConversionValue()`. O desenvolvedor não deve chamá-las.
* Não permita que outros SDKs chamem APIs SKADnet. Isso pode atrasar o iOS no envio do postback para a AppsFlyer e alterar o valor de conversão que usamos para preencher o painel do SkadNetwork com dados de mensuração de qualidade do usuário, conforme configurado pelo profissional de marketing no painel.
* O profissional de marketing precisa configurar a métrica do SkadNetwork <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">na AppsFlyer</Anchor> .

Não há outra ação ou processo de registro exigido pelo desenvolvedor ou pelo profissional de marketing na App Store.

</Accordion>

<div id="4-change-apis" />

<Accordion title="4. Alterar APIs">

O SDK V6 do iOS da AppsFlyer tem algumas alterações no nome da API. Consulte a tabela seguinte para alterar os nomes das API das versões anteriores do SDK para os nomes atuais.

| Nome da API (antes da V6) | Nome atual da API (V6 em diante) |
| --- | --- |
| AppsFlyerTracker | AppsFlyerLib |
| disableIAdTracking | disableCollectASA |
| trackAppLaunchWithCompletionHandler | startWithCompletionHandler |
| trackLocation | logLocation |
| trackAppLaunch | iniciar |
| trackEvent | logEvent |
| disableAppleAdSupportTracking | Se você chamar `anonymizeUser` antes de chamar `start`, nenhuma atribuição ocorrerá. |
| validateAndTrackInAppPurchase | validateAndLogInAppPurchase |
| isStopTracking | isStopped |
| deviceTrackingDisabled/deviceLoggingDisabled | anonymizeUser |
| sharedTracker (Objective C) | Compartilhado |

</Accordion>

<div id="5-ensure-push-notification-integration" />

<Accordion title="5. Garanta a integração da notificação push">

O seguinte é necessário se a integração de notificações push já estiver implementada.

Siga as <Anchor target="_blank" href="/marketers/pt/docs/measuring-push-notification-re-engagement-campaigns">instruções da notificação push</Anchor> para garantir que tem notificações push integradas usando o método handlePushNotificationData.

</Accordion>

## Plugins

Estão disponíveis os seguintes plugins V6:

<div id="unity" />

<Accordion title="Unity">

O plugin Unity V6 da AppsFlyer ajuda a proprietários e desenvolvedores de apps a serem compatíveis com iOS 14, proporcionando a funcionalidade de atribuição de apps e relatórios de eventos para aplicativos mobile de Android e iOS, que foram desenvolvidos na plataforma de desenvolvimento Unity. Em termos de funcionalidade, o plugin é equivalente aos SDKs da AppsFlyer para iOS e Android.

Para atualizar o seu plugin a partir de uma versão anterior, consulte os nossos guias sobre a atualização para o plugin Unity V6:

* <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-plugin/blob/master/README.md#--migration">Do plugin Unity V4</Anchor> (requer a remoção do plugin antigo)
* <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-plugin/blob/master/README.md#--migration">Do plugin Unity V5</Anchor> (requer uma atualização do pacote Unity)

</Accordion>

<div id="react-native" />

<Accordion title="React Nativo">

O plugin Native React da AppsFlyer ajuda a proprietários e desenvolvedores de apps a se prepararem para o iOS 14, proporcionando a funcionalidade de atribuição de apps e relatórios de eventos para aplicativos mobile de Android e iOS. Em termos de funcionalidade, o plugin é equivalente aos SDKs da AppsFlyer para iOS e Android.

Para atualizar o seu plugin a partir de uma versão anterior:

1. Remova o plugin anterior e substitua-o seguindo as instruções do nosso <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin/tree/dev/sdk-v6-beta">guia do GitHub</Anchor>.
2. Altere o código de integração renomeando <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin/tree/dev/sdk-v6-beta#--v6-breaking-changes">e eliminando</Anchor> as APIs necessárias.

</Accordion>

<div id="segment" />

<Accordion title="Segmento">

O plugin Segment da AppsFlyer ajuda a proprietários e desenvolvedores de apps a se prepararem para o iOS 14, proporcionando a funcionalidade de atribuição de apps e relatórios de eventos para aplicativos mobile de Android e iOS. Em termos de funcionalidade, o plugin é equivalente aos SDKs da AppsFlyer para iOS e Android.

Para atualizar o seu plugin a partir de uma versão anterior, remova o plugin anterior e substitua-o seguindo as instruções do nosso <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/segment-appsflyer-ios/tree/dev/sdk-v6-beta">guia do GitHub</Anchor>.

</Accordion>

<div id="cordova" />

<Accordion title="Cordova">

O plugin Cordova da AppsFlyer ajuda a proprietários e desenvolvedores de apps a se prepararem para o iOS 14, proporcionando a funcionalidade de atribuição de apps e relatórios de eventos para aplicativos mobile de Android e iOS. Em termos de funcionalidade, o plugin é equivalente aos SDKs da AppsFlyer para iOS e Android.

Para atualizar o seu plugin a partir de uma versão anterior, remova o plugin anterior e substitua-o seguindo as instruções do nosso <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-cordova-plugin/tree/releases/6.x.x/6.0.x/6.0.1-beta">guia do GitHub</Anchor>.

</Accordion>

<div id="flutter" />

<Accordion title="Flutter">

O plugin Flutter da AppsFlyer ajuda a proprietários e desenvolvedores de apps a se prepararem para o iOS 14, proporcionando a funcionalidade de atribuição de apps e relatórios de eventos para aplicativos mobile de Android e iOS. Em termos de funcionalidade, o plugin é equivalente aos SDKs da AppsFlyer para iOS e Android.

Para atualizar o seu plugin a partir de uma versão anterior, remova o plugin anterior e adicione a versão V6 a `pubspec.yaml`, seguindo as instruções no nosso <Anchor target="_blank" href="https://pub.dev/packages/appsflyer_sdk">guia pub.dev</Anchor>.

</Accordion>

<div id="adobe-air" />

<Accordion title="Adobe AIR">

O plugin Adobe AIR da AppsFlyer ajuda a proprietários e desenvolvedores de apps a se prepararem para o iOS 14, proporcionando a funcionalidade de atribuição de apps e relatórios de eventos para aplicativos mobile de Android e iOS. Em termos de funcionalidade, o plugin é equivalente aos SDKs da AppsFlyer para iOS e Android.

Para atualizar o seu plugin a partir de uma versão anterior, remova o plugin anterior e substitua-o seguindo as instruções do nosso <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/tree/dev/sdk-v6-beta">guia do GitHub</Anchor>.

</Accordion>

<div data-zendesk-anchors="about-ios-sdk-v6=sobre-o-ios-sdk-v6 update-to-ios-sdk-v6=atualiza%C3%A7%C3%A3o-para-ios-sdk-v6" />
