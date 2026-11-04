---
title: >-
  Uso de Firebase y Google Tag Manager con AppsFlyer: envío de instalaciones y
  eventos
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
  edited_at: '2026-08-12T12:00:00Z'
  id: 4410481550609
  locale: es
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/es/articles/4410481550609
---
> **En resumen:** Instrucciones para configurar el envío de eventos reportados a través del SDK de Firebase a AppsFlyer en tu aplicación.

<div id="configuring-events-in-the-app" />

## Configuración de eventos en la aplicación

En esta sección se explica cómo configurar y crear eventos en la aplicación con Google Tag Manager (GTM).

Cuando se envía el evento, GTM comprueba si hay una etiqueta configurada para procesar este evento con la ayuda del activador del evento. El activador del evento está configurado para activar la etiqueta cada vez que se envía un evento específico. Si se envía un evento específico y tiene un activador correspondiente, se activa la etiqueta. Cuando se activa la etiqueta, Google Tag Manager recopila todos los datos del evento. Estos datos incluyen el ID de AppsFlyer, el nombre del evento y los parámetros del evento. Tras recopilar todos los datos, Google Tag Manager envía el evento a AppsFlyer.

<div id="creating-event-variables-for-revenue-and-price" />

<Accordion title="Creación de variables de eventos para ingresos y precios">

#### Android

<Tabs>
<Tab title="Java">

1. En la clase MainActivity, crea una variable para contener el ID de dispositivo de AppsFlyer:  

   ```java
   public static String appsFlyerID;
   ```
2. De vuelta a la clase MainActivity, en el método `onCreate` y después de `super.onCreate`, pasa el ID de AppsFlyer a la variable:

   ```java
   appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this);
   ```

</Tab>

<Tab title="Kotlin">

1. En la clase MainActivity, crea una variable para guardar el ID de dispositivo de AppsFlyer:  

   ```kotlin
   var appsFlyerID: String? = null
   ```
2. De vuelta a la clase MainActivity, en el método `onCreate` y después de `super.onCreate`, pasa el valor del ID de AppsFlyer a la variable:

   ```kotlin
   override fun onCreate(savedInstanceState: Bundle?) {
    ... {
    ...
    appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this)
   }
   ```

</Tab>
</Tabs>

<div id="ios" />

#### apps de iOS,

Para iOS, los parámetros están disponibles en toda la aplicación. Puedes recuperarlos a través de la instancia AppsFlyerTracker.

<Tabs>
<Tab title="Objective C">

1. ID de dispositivo de AppsFlyer:

   ```objectivec
   [AppsFlyerTracker sharedTracker].getAppsFlyerUID
   ```
2. ID de aplicación de Apple:

   ```objectivec
   [AppsFlyerTracker sharedTracker].appleAppID
   ```

</Tab>

<Tab title="Swift">

1. ID de dispositivo de AppsFlyer:

   ```swift
    AppsFlyerTracker.shared().getAppsFlyerUID()
   ```
2. ID de aplicación de Apple:

   ```swift
   AppsFlyerTracker.shared().appleAppID
   ```

</Tab>
</Tabs>

</Accordion>

<div id="adding-events-in-the-app" />

<Accordion title="Adición de eventos en la aplicación">

El primer paso es configurar el evento en la aplicación. El evento se envía mediante Firebase Event Logging en caso de que especifiques el ID de AppsFlyer, el nombre del evento y los parámetros del evento. El ID de AppsFlyer se recupera de la variable que se crea en el <Anchor target="_blank" href="/marketers/es/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup#configuración-de-google-tag-manager">paso de configuración</Anchor>.

<Anchor target="_blank" href="https://developers.google.com/tag-manager/ios/v5/#log-events-and-variables">Google Tag Manager usa Firebase Analytics</Anchor> Events para activar eventos de etiquetas. Siempre que se envía un evento a Firebase, Tag Manager lo reconoce y también lo envía a AppsFlyer.

#### Android

<Tabs>
<Tab title="Java">

1. En la actividad deseada, agrega la declaración de importación para Firebase:  

   ```java
   import com.google.firebase.analytics.FirebaseAnalytics;
   ```
2. Agrega el siguiente código para que se ejecute cada vez que se produzca un evento de compra:

   ```java
   Bundle bundle = new Bundle();
     // ten en cuenta "af_id", este es el nombre del parámetro del evento 
     // para el ID de AppsFlyer que creamos en el paso anterior
     bundle.putString("af_id", appsFlyerID);
     bundle.putString("af_revenue", "200");
     bundle.putString("af_price", "250");
     mFirebaseAnalytics.logEvent("af_purchase", bundle);
   ```

</Tab>

<Tab title="Kotlin">

1. En la actividad deseada, agrega la declaración de importación para Firebase:  

   ```kotlin
   import com.google.firebase.analytics.FirebaseAnalytics
   ```
2. Agrega el siguiente código para que se ejecute cada vez que se produzca un evento de compra:

   ```kotlin
   val bundle = Bundle()
     // ten en cuenta "af_id", este es el nombre del parámetro del evento
     // para el ID de AppsFlyer que creamos en el paso anterior
     bundle.putString("af_id", appsFlyerID)
     bundle.putString("af_revenue", "200")
     bundle.putString("af_price", "250")
     FirebaseAnalytics.getInstance(this).logEvent("af_purchase", bundle)
   ```

</Tab>
</Tabs>

apps de iOS,

<Tabs>
<Tab title="Objective-C">

1. En la vista a la que se envía el evento, agrega `@import Firebase`
2. Agrega el siguiente código para que se ejecute cada vez que se produzca un evento de compra:

   ```objectivec
   NSString *id_prefix = @"id";  
   NSString *apple_app_id = [id_prefix stringByAppendingString: [AppsFlyerTracker sharedTracker].appleAppID];  

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

1. En la vista a la que se envía el evento, agrega `import Firebase`
2. Agrega el siguiente código para que se ejecute cada vez que se produzca un evento de compra:

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

## Envío eventos de instalación a Firebase

También puedes enviar eventos de instalación a Firebase con todos los datos relacionados con la instalación.

#### Android

<Tabs>
<Tab title="Java">

Para enviar eventos de instalación a Firebase en Android, puedes usar el objeto `conversionData`.

<div id="creating-the-send-event-method" />

#### Creación del método de envío de eventos

Agrega el siguiente método en la clase `AFApplication` justo debajo del método `onCreate`:

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
    } String.valueOf(new Date().getTime()) : conversionData.get("install_time"));
       bundle.putString("click_time", conversionData.get("click_time"));
       bundle.putString("media_source", conversionData.get("media_source") == null ? "organic": conversionData.get("media_source"));
       bundle.putString("campaign", conversionData.get("campaign") == null ? "organic": conversionData.get("campaign"));
       bundle.putString("install_type", conversionData.get("af_status"));
       mFirebaseAnalytics.logEvent("install", bundle);
    }
```

Este método acepta un objeto `conversionData`. El método comprueba si la hora de instalación, la fuente de medios y la campaña son nulos y, de ser así, establece la hora de instalación en la hora actual y la fuente medios y la campaña como orgánicas. De lo contrario, toma los datos del objeto `conversionData` y los envía a Firebase.

<div id="sending-the-install-event" />

#### Envío del evento de instalación

Agrega el siguiente código en el método `onConversionDataSuccess`:

```java
if(conversionData.get("is_first_launch").equals("true")){
       sendInstallToFirebase(conversionData);
    }
```

Este código comprueba si es la primera vez que se inicia la aplicación. Si es así, llama al método `sendInstallToFirebase`.

</Tab>

<Tab title="Kotlin">

Para enviar eventos de instalación a Firebase en Android, puedes usar el objeto `conversionData`.

<div id="creating-the-send-event-method-1" />

#### Creación del método de envío de eventos

Agrega el siguiente método en la clase `AFApplication` justo debajo del método `onCreate`:

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

Este método acepta un objeto `conversionData`. El método comprueba si la hora de instalación, la fuente de medios y la campaña son nulos y, de ser así, establece la hora de instalación en la hora actual y la fuente medios y la campaña como orgánicas. De lo contrario, toma los datos del objeto `conversionData` y los envía a Firebase.

<div id="sending-the-install-event-1" />

#### Envío del evento de instalación

Agrega el siguiente código en el método `onConversionDataSuccess`:

```kotlin
if(conversionData?.get("is_first_launch") == true){
      sendInstallToFirebase(conversionData);
  }
```

Este código comprueba si es la primera vez que se inicia la aplicación. Si es así, llama al método `sendInstallToFirebase`.

**Nota:** A partir del SDK V5, `onConversionDataSuccess` es el nombre del método para obtener los datos de conversión. Si estás utilizando una versión del SDK inferior a 5.0.0, el nombre del método es `onInstallConversionDataLoaded`. Recomendamos que actualices al SDK 5.0.0. Para aprender más, haz clic <Anchor target="_blank" href="/marketers/es/docs/links-to-appsflyer-sdk-release-notes">aquí</Anchor>.

</Tab>
</Tabs>

<div id="ios-1" />

#### apps de iOS,

<Tabs>
<Tab title="Objective-C">

<div id="creating-the-send-event-method-2" />

#### Creación del método de envío de eventos

En AppDelegate.m, agrega el siguiente método al final del archivo:

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

Este método recibe el objeto `installData` y comprueba si la instalación es orgánica o no. Si es orgánica, establece la hora de instalación en la hora actual y la fuente de medios, la campaña y el tipo de instalación como orgánicos.

Si la instalación no es orgánica, el método obtiene los datos de instalación no orgánica pertinentes.

Una vez establecidos los parámetros, el método envía el evento de instalación a Firebase.

<div id="sending-the-install-event-2" />

#### Envío del evento de instalación

En AppDelegate.m, en el método `didFinishLaunchingWithOptions`, agrega `[FIRApp configure]`.

En AppDelegate.m, en el método `onConversionDataSuccess`, agrega el siguiente código al final del método:

```objectivec
if([installData objectForKey:@"is_first_launch"]){
      [self sendInstallToFirebase: installData];
    }
```

El fragmento de código anterior comprueba si es la primera vez que se inicia la aplicación. Si es así, llama al método `sendInstallToFirebase`

</Tab>

<Tab title="Swift">

En AppDelegate.swift, agrega el siguiente método al final del archivo:

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

**Nota:** A partir del SDK V5, `onConversionDataSuccess` es el nombre del método para obtener los datos de conversión. Si estás utilizando una versión del SDK inferior a 5.0.0, el nombre del método es `onConversionDataReceived`. Recomendamos que actualices al SDK 5.0.0. Para aprender más, haz clic <Anchor target="_blank" href="/marketers/es/docs/links-to-appsflyer-sdk-release-notes">aquí</Anchor>.

Este método acepta el objeto `installData` y comprueba si la instalación es orgánica o no. Si es orgánica, establece la hora de instalación en la hora actual y la fuente de medios, la campaña y el tipo de instalación como orgánicos.

Si la instalación no es orgánica, el método obtiene los datos de instalación no orgánica pertinentes.

Una vez establecidos los parámetros, el método envía el evento de instalación a Firebase.

<div id="sending-the-install-event-3" />

#### Envío del evento de instalación

En AppDelegate.swift, en el método`didFinishLaunchingWithOptions`, agrega `FirebaseApp.configure();`

En AppDelegate.swift, en el método `onConversionDataSuccess`, agrega el siguiente código al final del método:

```swift
if let is_first_launch = data["is_first_launch"] , let launch_code = is_first_launch as? Int {
      if(launch_code == 1){
        print("Primer inicio")
        sendInstallToFirebase(installData)
      } else {
        print("No es el primer inicio")
      }
    }
```

**Nota:** A partir del SDK V5, `onConversionDataSuccess` es el nombre del método para obtener los datos de conversión. Si estás utilizando una versión del SDK inferior a 5.0.0, el nombre del método es `onConversionDataReceived`. Recomendamos que actualices al SDK 5.0.0. Para aprender más, haz clic <Anchor target="_blank" href="/marketers/es/docs/links-to-appsflyer-sdk-release-notes">aquí</Anchor>.

El fragmento de código anterior comprueba si es la primera vez que se inicia la aplicación. Si es así, llama al método `sendInstallToFirebase`

</Tab>
</Tabs>

<div id="warning" />

> ❗️ **Advertencia**
>
> Algunas fuentes de medios no permiten que sus datos se compartan con plataformas y servicios de terceros. Si trabajas con partners como Anuncios de Meta, Twitter, Snap, Pinterest, etc., que tienen restricciones para compartir sus datos con plataformas y servicios de terceros, asegúrate de **seguir sus lineamientos y eliminar cualquier dato que se encuentre bajo estas restricciones**.
>
> * <Anchor target="_blank" href="https://www.facebook.com/privacy/policy/">Política de datos de Anuncios de Meta</Anchor>
> * <Anchor target="_blank" href="https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html">Política de datos de Twitter</Anchor>
> * <Anchor target="_blank" href="https://www.snap.com/en-US/privacy/privacy-policy/">Política de datos de Snapchat</Anchor>
> * <Anchor target="_blank" href="https://policy.pinterest.com/en/privacy-policy">Política de datos de Pinterest</Anchor>

<div data-zendesk-anchors="configuring-events-in-the-app=configuraci%C3%B3n-de-eventos-en-la-aplicaci%C3%B3n 01H8H2MH93M1SB9HEQNHDDJZP0=configuraci%C3%B3n-de-eventos-en-la-aplicaci%C3%B3n 01H8H2MH93D36ZH7788XCMHHV6=creating-event-variables-for-revenue-and-price 01H8H2MH93RNWN6N6EWE5T26V1=android ios=apps-de-ios 01H8H2MH93CZ5TACG3MWJ8YRFK=apps-de-ios 01H8H2MH9340PQCCKB85BQZQEG=adding-events-in-the-app android::eb294e42=android-1 01H8H2MH9357Z5M1DBK4Z9N22P=android-1 sending-install-events-to-firebase=env%C3%ADo-eventos-de-instalaci%C3%B3n-a-firebase 01H8H2MH930VDZH5YSWEPTS8BN=env%C3%ADo-eventos-de-instalaci%C3%B3n-a-firebase android::319436d3=android-2 01H8H2MH938Y980A9KA9BPP44Y=android-2 creating-the-send-event-method=creaci%C3%B3n-del-m%C3%A9todo-de-env%C3%ADo-de-eventos 01H8H2MH932WYSS6Z5NZJ3195X=creaci%C3%B3n-del-m%C3%A9todo-de-env%C3%ADo-de-eventos sending-the-install-event=env%C3%ADo-del-evento-de-instalaci%C3%B3n 01H8H2MH93H0WKMV5DAN713EY0=env%C3%ADo-del-evento-de-instalaci%C3%B3n creating-the-send-event-method::64b5a305=creaci%C3%B3n-del-m%C3%A9todo-de-env%C3%ADo-de-eventos 01H8H2MH93VYXGMM5H6ZQWCFZY=creaci%C3%B3n-del-m%C3%A9todo-de-env%C3%ADo-de-eventos sending-the-install-event::aeb9cdb7=env%C3%ADo-del-evento-de-instalaci%C3%B3n 01H8H2MH93VTPZNF51R05QPK7C=env%C3%ADo-del-evento-de-instalaci%C3%B3n ios::95ad6e27=apps-de-ios-1 01H8H2MH93AQE7PKVW4QKD2ARN=apps-de-ios-1 creating-the-send-event-method::346138b1=creaci%C3%B3n-del-m%C3%A9todo-de-env%C3%ADo-de-eventos-2 01H8H2MH93NGBRHBDQTX4DKNTY=creaci%C3%B3n-del-m%C3%A9todo-de-env%C3%ADo-de-eventos-2 sending-the-install-event::aca3c0e3=env%C3%ADo-del-evento-de-instalaci%C3%B3n-2 01H8H2MH93SWYFF2KTC1HJ06FF=env%C3%ADo-del-evento-de-instalaci%C3%B3n-2 sending-the-install-event::b6997ad3=env%C3%ADo-del-evento-de-instalaci%C3%B3n-2 01H8H2MH93Y5J8QH0YBKPQSV5N=env%C3%ADo-del-evento-de-instalaci%C3%B3n-2 01H8H2MH93JQBAR6ZTW77HHFQR=advertencia" />
