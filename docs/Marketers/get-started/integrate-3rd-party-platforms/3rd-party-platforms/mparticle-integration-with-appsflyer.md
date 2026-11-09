---
title: integración de mParticle con AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - mParticle
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-04-03T05:31:23Z'
  edited_at: '2026-08-22T00:11:43Z'
  id: 209787323
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/209787323
---
> **At a glance:** mParticle, un partner integrado de AppsFlyer, recopila datos de clientes y los envía a diferentes plataformas de análisis, marketing y almacenamiento de datos.

> 🚧 **Important**
>
> **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="event-integrations" />

## Integraciones de eventos

El objetivo de este documento es proporcionarte detalles sobre cómo activar datos de eventos de mParticle para AppsFlyer.

1. los clientes de mParticle deben integrar el kit de AppsFlyer en su aplicación. El SDK de mParticle inicializará el SDK de AppsFlyer y también reenviará todos los eventos del ciclo de vida necesarios al SDK de AppsFlyer.

2. Consulta los repositorios de GitHub de los SDK de <Anchor target="_blank" href="https://github.com/mParticle/mParticle-apple-SDK">iOS</Anchor> y <Anchor target="_blank" href="https://github.com/mParticle/mparticle-android-sdk">Android</Anchor> para obtener información detallada sobre cómo configurar el kit de AppsFlyer con el SDK de mParticle en tu app.

<div id="configure-the-appsflyer-event-integration" />

### Configura la integración de eventos de AppsFlyer

1. En el Dashboard de mParticle ([https://app.mparticle.com](https://app.mparticle.com)), selecciona tu App (también llamada Workspace)

2. Haz clic en **Directory** en la navegación izquierda

3. Haz clic en el mosaico de AppsFlyer para ver los detalles de la integración, que incluyen información como Categorías, plataformas disponibles, versiones mínimas del SDK de mParticle (si las hay), tipos de datos, ID de usuario, ID de dispositivo, eventos disponibles y configuraciones disponibles.

<Image align="center" alt="Mosaico de AppsFlyer en el directorio de mParticle" src="https://files.readme.io/afa886e48f2cddde39007275a72ce03c4a6c4182408bb2ad4c8c183b1591b47d-115015666683.png" />

4. Haz clic en **Add AppsFlyer to Setup**.

Se abre la ventana **Add to Setup**:

<Image align="center" alt="Ventana Add to Setup de mParticle" src="https://files.readme.io/1eccc4ea365d41d4228eb07f4df88641458244b303ac8805932bf42ef4df5a74-115015476946.png" />

5. Selecciona el tipo de integración de eventos de salida y haz clic en **Add to Setup** para abrir la pantalla Event Configuration Setup, donde puedes continuar el proceso de configuración.

<Image align="center" alt="Pantalla mParticle Event Configuration Setup" src="https://files.readme.io/9a4720fef99a21a67fd017f4485e73765ebcb7aeb126f5342cc911aff4a345d2-115015476966.png" />

6. Introduce los ajustes de configuración de AppsFlyer y haz clic en **Save**:

* Nombre de la configuración
* Usa la misma configuración para desarrollo y producción
* Dev Key
* La configuración que acabas de crear se muestra en el grupo predeterminado de AppsFlyer

<Image align="center" alt="Configuración de AppsFlyer mostrada en el grupo predeterminado de AppsFlyer" src="https://files.readme.io/4d82533f311b93373152f046e92fe46c5e515cb8f5084bb89e81bfcae608172c-115015666803.png" />

El siguiente paso es establecer una conexión entre tus plataformas de entrada y la configuración de eventos de salida de AppsFlyer.

7. Haz clic en **Conexiones**.

8. Selecciona la entrada (iOS en este ejemplo) y, a continuación, haz clic en **Connect Output**.

9. Selecciona el mosaico de AppsFlyer y, a continuación, selecciona la configuración de AppsFlyer creada anteriormente.

10. Introduce la configuración de la conexión de AppsFlyer:  
ID de la app de Apple (introduce solo el número y no el prefijo del ID. Por ejemplo, si el ID de tu app es **id123456789**, introduce **123456789**)

<Image align="center" alt="Pantalla de configuración de la conexión de AppsFlyer" src="https://files.readme.io/2fb4c7480c5813bf7d893318de5c4a8edfe3649293bf51c8dae422be65db726e-115015477066.png" />

11. Haz clic en **Agregar conexión**.

AppsFlyer ahora se muestra como una salida conectada. Puede que haya más opciones disponibles, como asignaciones personalizadas. Consulta la <Anchor target="_blank" href="https://docs.mparticle.com/guides/getting-started/connect-an-event-output#outputs">documentación de mParticle</Anchor> para obtener más información.

<Image align="center" alt="AppsFlyer mostrado como una salida conectada" src="https://files.readme.io/53ea474eeb94c551677dd7a4ce190d6ed5972d65eafacd773b61d4ebd954fe2c-115015667883.png" />

<div id="feed-integrations" />

## Integraciones de feeds

Esta sección te ayuda a entender cómo conectar un feed de datos de AppsFlyer con mParticle.

Puedes encontrar información general sobre la integración de AppsFlyer en [https://docs.mparticle.com/integrations/appsflyer/feed/](https://docs.mparticle.com/integrations/appsflyer/feed/).

1. En el Dashboard de mParticle (<Anchor target="_blank" href="https://app.mparticle.com">https://app.mparticle.com</Anchor>), selecciona tu app (también llamada Workspace)

2. Haz clic en **Directory** desde la navegación de la izquierda

3. Haz clic en el mosaico de AppsFlyer para mostrar los detalles de la integración, que proporcionan información sobre la integración.

<Image align="center" alt="Mosaico de AppsFlyer en el Directory de mParticle" src="https://files.readme.io/53ea474eeb94c551677dd7a4ce190d6ed5972d65eafacd773b61d4ebd954fe2c-115015667883.png" />
<Image align="center" alt="Detalles de la integración de AppsFlyer en mParticle" src="https://files.readme.io/afa886e48f2cddde39007275a72ce03c4a6c4182408bb2ad4c8c183b1591b47d-115015666683.png" />

4. Haz clic en **Añadir AppsFlyer a Setup**.

5. Selecciona el tipo de integración del feed de entrada y haz clic en **Añadir a Setup**.

Ahora se te dirige a la pantalla de Setup, donde puedes continuar con el proceso de configuración.

6. Introduce los ajustes de configuración de AppsFlyer y haz clic en **Crear**:

* Nombre de la configuración
* Actuar como aplicación

<Image align="center" alt="Ajustes de configuración del feed de AppsFlyer" src="https://files.readme.io/b27aff8223a98b0bf4bd73b6a7a04dc73bc245fa062ac9dd47ed6f4bbeece3f2-115015668703.png" />

7. Completa la configuración en el dashboard de AppsFlyer con la información de autenticación proporcionada.

<Image align="center" alt="Configuración de autenticación del dashboard de AppsFlyer" src="https://files.readme.io/3c751a38c3891f73485375d75eacde3e07f86969a7d44cd33bf29ace6bfa1875-115015478566.png" />

<div id="deferred-deep-linking" />

## Enlaces profundos diferidos

AppsFlyer te permite acceder a los datos de atribución de los usuarios en tiempo real directamente en el nivel del SDK. Te permite personalizar la página de aterrizaje que ve el usuario la primera vez que abre una aplicación recién instalada. Esto se denomina comúnmente enlaces profundos "diferidos".

Para obtener más información sobre Deferred deep linking, haz clic <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">aquí</Anchor>.

Los datos de conversión de AppsFlyer contienen un parámetro llamado `is_First_Launch`. El valor de `is_First_Launch` es 'true' solo en el primer lanzamiento y 'false' en todos los lanzamientos posteriores. Puedes usar este parámetro para determinar en cada lanzamiento si la aplicación debe aplazar el deep link para el usuario o no.

```
af_dp → $deeplink_path
```

> 📘 **Note**
>
> **Ejemplo**
>
> ```
> $deeplink_path=product/Banana-Pet-Costume/dd67268672b345e491656c871af8aa29
> ```
>
> `af_dp` incluye el esquema de URI codificado y la ruta
>
> `af_dp` →
>
> `%20jet%3A%2F%2Fproduct%2FBanana-Pet-Costume%2Fdd67268672b345e491656c871af8aa29`

<Tabs>
<Tab title="Android">

Para Android: hazlo con Shared Preferences: <Anchor target="_blank" href="https://developer.android.com/reference/android/content/SharedPreferences.html">aquí.</Anchor>

```java
AttributionListener myListener = new AttributionListener() {
  @Override
  public void onResult(@NonNull AttributionResult attributionResult) {
   if (attributionResult.getServiceProviderId() == MParticle.ServiceProviders.APPSFLYER) {
    JSONObject attributionParams = attributionResult.getParameters();
    if (attributionParams != null && attributionParams.has(AppsFlyerKit.INSTALL_CONVERSION_RESULT)) {
     Log.d("Resultado de conversión", attributionParams.toString());
    } else if (attributionParams != null && attributionParams.has(AppsFlyerKit.APP_OPEN_ATTRIBUTION_RESULT)) {
     Log.d("Resultado de apertura de la aplicación", attributionParams.toString());
    }
   }
  }

  @Override
  public void onError(@NonNull AttributionError attributionError) {
   Log.d("Error de datos de atribución", attributionError.toString());
  }
 };

 MParticleOptions options = MParticleOptions.builder(this)
  .credentials("replaceWithAPIKey", "replace-withAPISecret")
  .attributionListener(myListener)
  .build();

 MParticle.start(options);
```

</Tab>

<Tab title="apps de iOS,">

Para iOS: haz esto en UserDefaults: <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/userdefaults">aquí</Anchor>

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
 MParticleOptions *options = [MParticleOptions optionsWithKey:@"<>" secret:@"<>"];
 options.onAttributionComplete = ^void (MPAttributionResult *_Nullable attributionResult, NSError * _Nullable error) {
  if (error) {
   NSLog(@"La obtención de atribución para kitCode=%@ ha fallado con el error=%@", error.userInfo[mParticleKitInstanceKey], error);
   return;
  }
  NSLog(@"La obtención de atribución para kitCode=%@ se ha completado con linkInfo: %@", attributionResult.kitCode, attributionResult.linkInfo);
 }
 [[MParticle sharedInstance] startWithOptions:options];
 return YES;
}
```

</Tab>
</Tabs>

<div id="appsflyermparticle-use-cases" />

### Casos de uso de AppsFlyer/mparticle

| Caso de uso | Destino de engagement | Método del SDK de AppsFlyer | Método del Kit mParticle-AF |
| --- | --- | --- | --- |
| Deferred Deep Linking | apps de iOS, | onConversionDataSuccess | checkForDeferredDeepLinkWithCompletionHandler |
| enlaces universales | apps de iOS, | continueUserActivity | continueUserActivity |
| Apertura de la aplicación | apps de iOS, | onAppOpenAttribution | checkForDeferredDeepLinkWithCompletionHandler |
| Conexión profunda diferida (también conocido como deferred deep linking) | Android | onConversionDataSuccess | checkForDeepLink |
| Enlaces de la aplicación Android | Android |  | continueUserActivity |
| Apertura de la aplicación | Android | onAppOpenAttribution | checkForDeepLink |

<div id="handling-user-flags" />

### Gestión de indicadores de usuario

AppsFlyer también te permite mostrar contenido personalizado o enviar a los usuarios existentes a ubicaciones específicas de la aplicación DESPUÉS del lanzamiento inicial. Cuando se aplica Deep Linking a usuarios existentes dentro de la aplicación, la aplicación se abre desde el método `onOpenAttribution`, que devuelve los datos de la URL de referencia.

```swift
 if let conversionData = params?[MPKitAppsFlyerConversionResultKey] as? [AnyHashable: Any], !alreadyLoggedAppsflyerConversionData {
   logAppsflyerConversionData(conversionData: conversionData)
   alreadyLoggedAppsflyerConversionData = true
   if let onelinkURL = (conversionData["af_dp"] as? String).flatMap(URL.init) {
    UIApplication.appDelegate._linkController.handle(onelinkURL, source: .appsflyer)
   }
  } else if let appOpenData = params?[MPKitAppsFlyerAppOpenResultKey] as? [AnyHashable: Any] {
   logAppsflyerAppOpenData(appOpenData: appOpenData as? [String: Any])
  }
```

AppsFlyer usa ***UserDefaults*** en iOS y ***Shared Preferences*** en Android para indicar si el usuario está abriendo la aplicación por primera vez y debe ser redirigido a la página correspondiente, o si la aplicación ya se ha abierto y el usuario ya ha sido dirigido a esa página. Para ello, el valor `alreadyLoggedAppsflyerConversionData` se lee y se escribe en UserDefaults/ SharedPreferences, para que no se tenga en cuenta el valor ***af\_dp*** en el primer inicio.

Para obtener más información sobre cómo mostrar contenido personalizado en Deep Linking, <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">haz clic aquí</Anchor>.

<div id="enabling-appsflyer-uninstall-measurement-in-mparticle" />

## Activación de la medición de desinstalación de AppsFlyer en mParticle

La medición de desinstalación de AppsFlyer no se activa automáticamente con el kit SDK de mParticle-AppsFlyer. Para medir las desinstalaciones de la aplicación, llama directamente a los métodos de AppsFlyer siguiendo la documentación sobre la medición de desinstalación de AppsFlyer.

**Para implementar la medición de desinstalación en iOS o Android:**

* Llama directamente a los métodos de AppsFlyer siguiendo nuestra documentación sobre la medición de desinstalación

<div data-zendesk-anchors="event-integrations=integraciones-de-eventos h_01H9HWJRM2612MBM2Y7C5YZ2YY=integraciones-de-eventos configure-the-appsflyer-event-integration=configura-la-integraci%C3%B3n-de-eventos-de-appsflyer h_01H9HWJRM2BJATV1QHS382J0ZN=configura-la-integraci%C3%B3n-de-eventos-de-appsflyer feed-integrations=integraciones-de-feeds h_01H9HWJRM2YV3CEH7J7EMA8E3Y=integraciones-de-feeds deferred-deep-linking=enlaces-profundos-diferidos h_01H9HWJRM2SZYRXFTSZPM1JHCJ=enlaces-profundos-diferidos appsflyermparticle-use-cases=casos-de-uso-de-appsflyermparticle h_01H9HWJRM2HCB4YF2BP9RPK2RP=casos-de-uso-de-appsflyermparticle handling-user-flags=gesti%C3%B3n-de-indicadores-de-usuario h_01H9HWJRM3HAGGWHF4YTQTTS2X=gesti%C3%B3n-de-indicadores-de-usuario known-mparticle-integration-limitation=activaci%C3%B3n-de-la-medici%C3%B3n-de-desinstalaci%C3%B3n-de-appsflyer-en-mparticle h_01H9HWJRM321PSNQ480R96BN12=activaci%C3%B3n-de-la-medici%C3%B3n-de-desinstalaci%C3%B3n-de-appsflyer-en-mparticle" />
