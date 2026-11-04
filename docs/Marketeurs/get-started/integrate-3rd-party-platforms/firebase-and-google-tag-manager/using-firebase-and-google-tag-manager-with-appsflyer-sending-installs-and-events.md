---
title: >-
  Utiliser Firebase et Google Tag Manager avec AppsFlyer — Envoyer des
  installations et des événements
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
  edited_at: '2024-10-09T14:57:11Z'
  id: 4410481550609
  locale: fr
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/fr/articles/4410481550609
---
> **En bref :** Instructions pour configurer l'envoi d'événements signalés via le SDK Firebase à AppsFlyer dans votre app.

<div id="configuring-events-in-the-app" />

## Configurer des événements dans l'app

Cette section explique comment configurer et créer des événements dans l'app avec Google Tag Manager (GTM).

Lorsque l'événement est envoyé, GTM vérifie s'il existe une balise configurée pour traiter cet événement à l'aide du déclencheur d'événement. Le déclencheur d'événement est défini pour déclencher la balise chaque fois qu'un événement spécifique est envoyé. Si un événement spécifique est envoyé et qu'il a un déclencheur correspondant, la balise est activée. Lorsque la balise est activée, Google Tag Manager collecte toutes les données de l'événement. Ces données comprennent l'identifiant AppsFlyer, le nom de l'événement et les paramètres de l'événement. Après avoir collecté toutes les données, Google Tag Manager envoie l'événement à AppsFlyer.

<div id="creating-event-variables-for-revenue-and-price" />

<Accordion title="Création de variables d'événement pour le revenu et le prix">

#### Android

<Tabs>
<Tab title="Java">

1. Dans la classe MainActivity, créez une variable qui contiendra l'identifiant de l'appareil AppsFlyer :  

   ```java
   public static String appsFlyerID;
   ```
2. De retour dans la classe MainActivity, dans la méthode `onCreate` et après `super.onCreate`, transmettez l'ID AppsFlyer à la variable :

   ```java
   appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this);
   ```

</Tab>

<Tab title="Kotlin">

1. Dans la classe MainActivity, créez une variable qui contiendra l'identifiant de l'appareil AppsFlyer :  

   ```kotlin
   var appsFlyerID: String? = null
   ```
2. De retour dans la classe MainActivity, dans la méthode `onCreate` et après `super.onCreate`, transmettez la valeur de l'ID AppsFlyer à la variable :

   ```kotlin
   override fun onCreate(savedInstanceState: Bundle?) {
    ...
    appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this)
   }
   ```

</Tab>
</Tabs>

#### iOS

Pour iOS, les paramètres sont disponibles dans l'app. Vous pouvez les récupérer via l'instance AppsFlyerTracker.

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

<Accordion title="Ajouter des événements dans l'app">

La première étape consiste à configurer l'événement dans l'app. L'événement est envoyé en utilisant Firebase Event Logging. Dans l'événement, vous spécifiez l'ID AppsFlyer, le nom de l'événement et les paramètres de l'événement. L'ID d’AppsFlyer est récupéré à partir de la variable créée lors de l'<Anchor target="_blank" href="/marketers/fr/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup#configuration-de-google-tag-manager">étape de configuration</Anchor>.

<Anchor target="_blank" href="https://developers.google.com/tag-manager/ios/v5/#log-events-and-variables">Google Tag Manager utilise les événements Firebase Analytics</Anchor> pour déclencher des événements de balises. Chaque fois qu'un évènement est envoyé à Firebase, Tag Manager reconnaît l'événement et l'envoie également à AppsFlyer.

#### Android

<Tabs>
<Tab title="Java">

1. Dans l'activité souhaitée, ajoutez la déclaration d'importation pour Firebase :  

   ```java
   import com.google.firebase.analytics.FirebaseAnalytics;
   ```
2. Ajoutez le code suivant pour qu'il soit exécuté chaque fois qu'un événement d'achat se produit :

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

1. Dans l'activité souhaitée, ajoutez la déclaration d'importation pour Firebase :  

   ```kotlin
   import com.google.firebase.analytics.FirebaseAnalytics
   ```
2. Ajoutez le code suivant pour qu'il soit exécuté chaque fois qu'un événement d'achat se produit :

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

1. Dans la vue où l'événement est envoyé, ajoutez `@import Firebase`
2. Ajoutez le code suivant pour qu'il soit exécuté chaque fois qu'un événement d'achat se produit :

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

1. Dans la vue où l'événement est envoyé, ajoutez `import Firebase`
2. Ajoutez le code suivant pour qu'il soit exécuté chaque fois qu'un événement d'achat se produit :

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

<div id="sending-install-events-to-firebase" />

## Envoi d'événements d'installation à Firebase

Vous pouvez également envoyer des événements d'installation à Firebase avec toutes les données relatives à l'installation.

#### Android

<Tabs>
<Tab title="Java">

Pour envoyer des événements d'installation à Firebase dans Android, vous pouvez utiliser l'objet `conversionData`.

<div id="creating-the-send-event-method" />

#### Création de la méthode d'envoi de l'événement

Ajoutez la méthode suivante dans la classe `AFApplication`, juste en dessous de la méthode `onCreate`:

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

Cette méthode accepte un objet `conversionData`. La méthode vérifie si l'heure d'installation, la source média et la campagne sont nulles, et, le cas échéant, définit l'heure d'installation à l'heure actuelle et la source média ainsi que la campagne comme étant organiques. Sinon, elle prend les données de l'objet `conversionData` et les envoie à Firebase.

<div id="sending-the-install-event" />

#### Envoi de l'événement d'installation

Ajoutez le code suivant dans la méthode `onConversionDataSuccess`:

```java
if(conversionData.get("is_first_launch").equals("true")){
       sendInstallToFirebase(conversionData);
    }
```

Ce code vérifie si l'app est lancée pour la première fois. Si c'est le cas, il appelle la méthode `sendInstallToFirebase`.

</Tab>

<Tab title="Kotlin">

Pour envoyer des événements d'installation à Firebase dans Android, vous pouvez utiliser l'objet `conversionData`.

<div id="creating-the-send-event-method-1" />

#### Création de la méthode d'envoi de l'événement

Ajoutez la méthode suivante dans la classe `AFApplication`, juste en dessous de la méthode `onCreate`:

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

Cette méthode accepte un objet `conversionData`. La méthode vérifie si l'heure d'installation, la source média et la campagne sont nulles, et, le cas échéant, définit l'heure d'installation à l'heure actuelle et la source média ainsi que la campagne comme étant organiques. Sinon, elle prend les données de l'objet `conversionData` et les envoie à Firebase.

<div id="sending-the-install-event-1" />

#### Envoi de l'événement d'installation

Ajoutez le code suivant dans la méthode `onConversionDataSuccess`:

```kotlin
if(conversionData?.get("is_first_launch") == true){
      sendInstallToFirebase(conversionData);
  }
```

Ce code vérifie si l'app est lancée pour la première fois. Si c'est le cas, il appelle la méthode `sendInstallToFirebase`.

**Remarque :** À partir du SDK V5, `onConversionDataSuccess` est le nom de la méthode d'obtention des données de conversion. Si vous utilisez une version du SDK inférieure à la version 5.0.0, le nom de la méthode est `onInstallConversionDataLoaded`. Nous vous recommandons une mise à niveau vers le SDK 5.0.0. Pour en savoir plus, cliquez <Anchor target="_blank" href="/marketers/fr/docs/links-to-appsflyer-sdk-release-notes">ici</Anchor>.

</Tab>
</Tabs>

#### iOS

<Tabs>
<Tab title="Objective-C">

<div id="creating-the-send-event-method-2" />

#### Création de la méthode d'envoi de l'événement

Dans AppDelegate.m, ajoutez la méthode suivante à la fin du fichier :

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

Cette méthode reçoit l'objet `installData` et vérifie si l'installation est organique ou non. Si elle est organique, elle définit l'heure d'installation à l'heure actuelle ainsi que la source média, la campagne et le type d'installation comme étant organiques.

Si l'installation n'est pas organique, la méthode récupère les données d'installation non organiques correspondantes.

Une fois les paramètres définis, la méthode envoie l'événement d'installation à Firebase.

<div id="sending-the-install-event-2" />

#### Envoi de l'événement d'installation

Dans AppDelegate.m, dans la méthode `didFinishLaunchingWithOptions`, ajoutez `[FIRApp configure]`

Dans AppDelegate.m, dans la méthode `onConversionDataSuccess`, ajoutez le code suivant à la fin de la méthode :

```objectivec
if([installData objectForKey:@"is_first_launch"]){
      [self sendInstallToFirebase: installData];
    }
```

L'extrait de code ci-dessus vérifie si l'app est lancée pour la première fois. Si c'est le cas, il appelle la méthode `sendInstallToFirebase`.

</Tab>

<Tab title="Swift">

Dans AppDelegate.swift, ajoutez la méthode suivante à la fin du fichier :

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

**Remarque :** À partir du SDK V5, `onConversionDataSuccess` est le nom de la méthode d'obtention des données de conversion. Si vous utilisez une version du SDK inférieure à la version 5.0.0, le nom de la méthode est `onConversionDataReceived`. Nous vous recommandons une mise à niveau vers le SDK 5.0.0. Pour en savoir plus, cliquez <Anchor target="_blank" href="/marketers/fr/docs/links-to-appsflyer-sdk-release-notes">ici</Anchor>.

Cette méthode accepte l'objet `installData` et vérifie si l'installation est organique. Si elle est organique, elle définit l'heure d'installation à l'heure actuelle ainsi que la source média, la campagne et le type d'installation comme étant organiques.

Si l'installation n'est pas organique, la méthode récupère les données d'installation non organiques correspondantes.

Une fois les paramètres définis, la méthode envoie l'événement d'installation à Firebase.

<div id="sending-the-install-event-3" />

#### Envoi de l'événement d'installation

Dans AppDelegate.swift, dans la méthode `didFinishLaunchingWithOptions`, ajoutez `FirebaseApp.configure();`

Dans AppDelegate.swift, dans la méthode `onConversionDataSuccess`, ajoutez le code suivant à la fin de la méthode :

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

**Remarque :** À partir du SDK V5, `onConversionDataSuccess` est le nom de la méthode d'obtention des données de conversion. Si vous utilisez une version du SDK inférieure à la version 5.0.0, le nom de la méthode est `onConversionDataReceived`. Nous vous recommandons une mise à niveau vers le SDK 5.0.0. Pour en savoir plus, cliquez <Anchor target="_blank" href="/marketers/fr/docs/links-to-appsflyer-sdk-release-notes">ici</Anchor>.

L'extrait de code ci-dessus vérifie si l'app est lancée pour la première fois. Si c'est le cas, il appelle la méthode `sendInstallToFirebase`.

</Tab>
</Tabs>

<div id="warning" />

> ❗️ **Avertissement**
>
> Certaines sources média n'autorisent pas le partage de leurs données avec des plateformes et services tiers. Si vous travaillez avec des partenaires tels que Meta Ads, Twitter, Snap, Pinterest, etc., qui imposent des restrictions sur le partage de leurs données avec des plateformes et services tiers, assurez-vous de **suivre leurs directives et de supprimer toute donnée soumise à ces restrictions.**
>
> * <Anchor target="_blank" href="https://www.facebook.com/privacy/policy/">Politique de données Meta ads</Anchor>
> * <Anchor target="_blank" href="https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html">Politique de données de Twitter</Anchor>
> * <Anchor target="_blank" href="https://www.snap.com/en-US/privacy/privacy-policy/">Politique des données de Snapchat</Anchor>
> * <Anchor target="_blank" href="https://policy.pinterest.com/en/privacy-policy">Politique de données de Pinterest</Anchor>

<div data-zendesk-anchors="configuring-events-in-the-app=configurer-des-%C3%A9v%C3%A9nements-dans-lapp 01H8H2MH93M1SB9HEQNHDDJZP0=configurer-des-%C3%A9v%C3%A9nements-dans-lapp 01H8H2MH93D36ZH7788XCMHHV6=creating-event-variables-for-revenue-and-price 01H8H2MH93RNWN6N6EWE5T26V1=android 01H8H2MH93CZ5TACG3MWJ8YRFK=ios 01H8H2MH9340PQCCKB85BQZQEG=adding-events-in-the-app android::eb294e42=android-1 01H8H2MH9357Z5M1DBK4Z9N22P=android-1 sending-install-events-to-firebase=envoi-d%C3%A9v%C3%A9nements-dinstallation-%C3%A0-firebase 01H8H2MH930VDZH5YSWEPTS8BN=envoi-d%C3%A9v%C3%A9nements-dinstallation-%C3%A0-firebase android::319436d3=android-2 01H8H2MH938Y980A9KA9BPP44Y=android-2 creating-the-send-event-method=cr%C3%A9ation-de-la-m%C3%A9thode-denvoi-de-l%C3%A9v%C3%A9nement 01H8H2MH932WYSS6Z5NZJ3195X=cr%C3%A9ation-de-la-m%C3%A9thode-denvoi-de-l%C3%A9v%C3%A9nement sending-the-install-event=envoi-de-l%C3%A9v%C3%A9nement-dinstallation 01H8H2MH93H0WKMV5DAN713EY0=envoi-de-l%C3%A9v%C3%A9nement-dinstallation creating-the-send-event-method::64b5a305=cr%C3%A9ation-de-la-m%C3%A9thode-denvoi-de-l%C3%A9v%C3%A9nement 01H8H2MH93VYXGMM5H6ZQWCFZY=cr%C3%A9ation-de-la-m%C3%A9thode-denvoi-de-l%C3%A9v%C3%A9nement sending-the-install-event::aeb9cdb7=envoi-de-l%C3%A9v%C3%A9nement-dinstallation 01H8H2MH93VTPZNF51R05QPK7C=envoi-de-l%C3%A9v%C3%A9nement-dinstallation ios::95ad6e27=ios-1 01H8H2MH93AQE7PKVW4QKD2ARN=ios-1 creating-the-send-event-method::346138b1=cr%C3%A9ation-de-la-m%C3%A9thode-denvoi-de-l%C3%A9v%C3%A9nement-2 01H8H2MH93NGBRHBDQTX4DKNTY=cr%C3%A9ation-de-la-m%C3%A9thode-denvoi-de-l%C3%A9v%C3%A9nement-2 sending-the-install-event::aca3c0e3=envoi-de-l%C3%A9v%C3%A9nement-dinstallation-2 01H8H2MH93SWYFF2KTC1HJ06FF=envoi-de-l%C3%A9v%C3%A9nement-dinstallation-2 sending-the-install-event::b6997ad3=envoi-de-l%C3%A9v%C3%A9nement-dinstallation-2 01H8H2MH93Y5J8QH0YBKPQSV5N=envoi-de-l%C3%A9v%C3%A9nement-dinstallation-2 01H8H2MH93JQBAR6ZTW77HHFQR=avertissement" />
