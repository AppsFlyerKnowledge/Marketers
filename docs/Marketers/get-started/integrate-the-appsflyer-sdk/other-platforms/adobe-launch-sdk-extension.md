---
title: Extensión del SDK de Adobe Launch
metadata:
  keywords:
    - SDK
    - Adobe
    - Advertisers
    - AppsFlyer SDK
    - Adobe Experience Platform
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
  created_at: '2019-02-13T08:03:45Z'
  edited_at: '2026-08-22T00:14:33Z'
  id: 360000939097
  locale: es
  section: Other platforms
  section_id: 6551244207121
  url: https://support.appsflyer.com/hc/es/articles/360000939097
---
> **At a glance:** Envía datos al SDK de Adobe Launch y al SDK de AppsFlyer con la implementación única de la extensión del SDK de Adobe Launch de AppsFlyer.

## Visión general

El SDK de Adobe Launch es una parte integral de Adobe Experience Platform. Adobe Experience Platform permite a las empresas recopilar, consolidar y analizar datos de varias aplicaciones y plataformas. Permite a los propietarios y desarrolladores de negocios comprender mejor el comportamiento de los clientes para optimizar la experiencia y la entrega de contenido. Si tu aplicación implementa tanto el SDK de Adobe Launch como el SDK de AppsFlyer, puedes enviar datos a ambos con una sola implementación de la **extensión del SDK de Adobe Launch de AppsFlyer**. Reduce la complejidad general de tu proceso de desarrollo y hace que la base de código sea más limpia y fácil de mantener.

> 📘 **Note**
>
> **Nota:**
>
> Si utilizas la extensión de Adobe Launch, no es necesaria la <Anchor target="_blank" href="/marketers/es/docs/adobe-analytics-integration-with-appsflyer">integración estándar de Adobe Analytics</Anchor>.

## Requisitos previos

Se requieren algunas cosas antes de integrar la extensión del SDK de Adobe de AppsFlyer.

<div id="get-your-appsflyer-dev-key" />

<Accordion title="Obtén tu clave de desarrollador de AppsFlyer">

![dev_key.png](https://files.readme.io/bf25b5d583f3eaab57c230b68764f08c49806a50401955a511993d8a847e7d42-360006050318.png)

1. En el dashboard de tu app, haz clic en ***App Settings*** en ***Configuration***, en el menú de la izquierda.
2. En ***SDK Installation***, copia la ***Dev Key***.

</Accordion>

<div id="get-your-app-id" />

<Accordion title="Obtén tu ID de aplicación">

* Para Android: el ID de la aplicación es el nombre del paquete, por ejemplo, example.com.app.
* Para iOS: el ID de la aplicación es el ID de iTunes de la aplicación sin el prefijo *id*; por ejemplo, 123456748.

</Accordion>

## Paso 1: Configuración de Adobe Launch

Sigue las instrucciones que se indican aquí para configurar Adobe Launch.

<div id="11-creating-a-new-property-in-adobe-launch" />

<Accordion title="1.1 Creación de una nueva propiedad en Adobe Launch">

![Creación de una nueva propiedad en Adobe Launch](https://files.readme.io/d03e61047c536785e7601d4f0efbd9b6488bd41c92efdd6e0d1021b42a5bec3a-small-360005983477.png)

1. Inicia sesión en Adobe Experience Cloud.
2. Selecciona ***Launch***.
3. Haz clic en ***Go to Launch***.
4. Haz clic en ***New Property***.
5. Asigna un nombre a la propiedad y selecciona ***Móvil***.
6. Haz clic en ***Save***.

</Accordion>

<div id="12-installing-required-adobe-launch-extensions" />

<Accordion title="1.2 Instalación de las extensiones necesarias de Adobe Launch">

Instala las siguientes extensiones en Adobe Launch:

![adboe_extensions.png](https://files.readme.io/bf0c0652c3807d4da0819a62b600ac875af1f8764387a36cc3f256a58e1ea852-360005983597.png)

* Adobe Analytics: conecta los datos registrados del SDK al módulo de Adobe Analytics.
* Extensión del SDK de AppsFlyer: envía datos y eventos tanto a Adobe como a AppsFlyer mediante el SDK de Adobe Launch.
* Adobe Profile: permite que el SDK almacene datos en un perfil del lado del cliente.
* Adobe Mobile Core: permite la configuración del SDK móvil y proporciona acceso a los eventos y condiciones predeterminados del ciclo de vida.

#### Instalación de la extensión de Adobe Analytics

1. Inicia sesión en Adobe Analytics.
2. <Anchor target="_blank" href="https://docs.adobe.com/help/en/analytics/admin/admin-console/create-report-suite.html">Crea un grupo de reportes</Anchor>.
3. Vuelve a iniciar sesión en Adobe Launch.
4. En la lista de propiedades, haz clic en la propiedad que creaste anteriormente.
5. Haz clic en ***Extensions*** (Extensiones).
6. Busca e instala ***Adobe Analytics***.
7. En ***Report Suites*** (Grupos de reportes), especifica el grupo de reportes que creaste en el paso 2.
8. Haz clic en ***Save*** (Guardar).

#### Instalación de la extensión del SDK de AppsFlyer

1. Vuelve a seleccionar ***Extensions*** (Extensiones).
2. Busca e instala la ***extensión del SDK de AppsFlyer***.
3. En ***AppsFlyer iOS App ID*** (ID de la aplicación de iOS de AppsFlyer), especifica el ID de la aplicación de iOS que obtuviste en el paso de requisitos previos.
4. En ***AppsFlyer Dev Key*** (Clave de desarrollador de AppsFlyer), especifica la clave de desarrollador que obtuviste en el paso de requisitos previos.
5. Habilita ***Send attribution data to Adobe Analytics*** (Enviar datos de atribución a Adobe Analytics). Ten en cuenta que existen algunas <Anchor target="_blank" href="/marketers/es/docs/user-level-data-retention">restricciones para compartir datos a nivel de usuario con plataformas de análisis de terceros</Anchor>.
6. Haz clic en ***Save*** (Guardar).

#### Instalación de la extensión de Profile y Mobile Core

1. Vuelve a seleccionar ***Extensions*** (Extensiones).
2. Busca e instala ***Profile***.
3. Busca e instala ***Mobile Core***.
   * Al instalar Mobile Core, simplemente guarda la extensión tal como está. No es necesario especificar el ***servidor de Experience Cloud***.

</Accordion>

## Paso 2: Implementación de la extensión del SDK de Adobe de AppsFlyer

Sigue las instrucciones de esta sección para implementar la extensión del SDK de Adobe en tu aplicación.

<div id="21-adding-the-sdk-to-the-app" />

<Accordion title="2.1 Adición del SDK a la aplicación">

![adobe_sdk.png](https://files.readme.io/076e6cc5911a0a515e5510a8da233bcefcb4144c92cf49190416b593fcdecc8f-small-360006050518.png)

1. Dentro de la propiedad de Adobe, selecciona ***Environments*** (Entornos).
2. Selecciona el entorno para el que deseas implementar el SDK.
3. En el lado derecho, haz clic en el icono de cuadro.
4. Copia los fragmentos de código de la ventana que se abre y sigue las instrucciones. Si eres el marketer que configura Adobe, envía estos fragmentos de código al desarrollador de la aplicación.

</Accordion>

<div id="22-publishing-the-environment" />

<Accordion title="2.2 Publicación del entorno">

Para completar la implementación del SDK, debes publicar el entorno en una biblioteca.

![adobe_publishing.png](https://files.readme.io/4e9ad08fce291ef59e7a3567726c678754ae3a3c96de75f4ae27cd80a84945d1-small-360006050558.png)

1. Dentro de la propiedad de Adobe, selecciona ***Publishing*** (Publicación).
2. Haz clic en ***Add New Library*** (Agregar nueva biblioteca).
3. Asígnale un nombre y, en Environment (Entorno), selecciona ***Development*** (Desarrollo).
4. Haz clic en ***Save & Build for Development*** (Guardar y compilar para desarrollo).
5. Una vez completada la compilación, en ***Development*** (Desarrollo) haz clic en los tres puntos situados junto a la biblioteca y selecciona ***Submit for Approval*** (Enviar para aprobación).
6. En ***Submitted*** (Enviado), haz clic en los tres puntos situados junto a la biblioteca y selecciona ***Build for Staging*** (Crear para ensayo).
7. Una vez completada la compilación, haz clic en los tres puntos situados junto a la biblioteca y selecciona ***Approve for Publishing*** (Aprobar para publicación).
8. En ***Approve*** (Aprobar), haz clic en los tres puntos junto a la biblioteca y selecciona ***Build & Publish to Production*** (Crear y publicar en producción).

</Accordion>

<div id="23-adding-android-install-referrer-to-your-app" />

<Accordion title="2.3 Adición del referente de instalación de Android a tu aplicación">

El referente de instalación de Android mejora la precisión de la atribución, protege contra las instalaciones fraudulentas y mucho más. Es compatible con la versión 4.8.6 del SDK de AppsFlyer para Android.

> 📘 **Note**
>
> **Nota:**
>
> Google dejó de usar [BroadcastReceiver](https://android-developers.googleblog.com/2019/11/still-using-installbroadcast-switch-to.html) en marzo de 2020.
>
> * Este cambio no afecta a la aplicación.
> * Es posible que aún necesites BroadcastReceiver para la atribución fuera de la tienda. Verifica con la tienda donde aparece la aplicación para asegurarte de que así sea.
> * La implementación del referente de instalación ahora es obligatoria.

Existen dos maneras de agregar el referente de instalación a tu aplicación:

* Mediante Gradle (opción recomendada)
* Agregando manualmente el referente de instalación

<Tabs>
<Tab title="Añadir la referencia de instalación con Gradle">

Agrega el referente de instalación de Android como dependencia. Puedes encontrar la última versión <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">aquí</Anchor>.

1.
   ```java
   dependencies {
   //asegúrate de usar la última versión del SDK: https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk
   	implementation 'com.appsflyer:af-android-sdk:5.+'
   	implementation 'com.android.installreferrer:installreferrer:1.1'
   }
   ```
2. Sincroniza el proyecto para recuperar las dependencias: consulta la siguiente captura de pantalla: ![android_af_sdk_sync_gradle.png](https://files.readme.io/f8835cf76d51d7ddeb51206707d95b7214e398c5960299893118ad57ccffe890-22939234622609.png)

Si utilizas ProGuard y quieres utilizar la nueva API de referente de Google, establece la siguiente regla de ProGuard: `-dontwarn com.android.installreferrer`

</Tab>

<Tab title="Agregando manualmente el referente de instalación">

1. <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">Descarga el aar del referente de instalación.</Anchor>
2. <Anchor target="_blank" href="https://stackoverflow.com/questions/16682847/how-to-manually-include-external-aar-package-using-new-gradle-android-build-syst">Agrégalo al proyecto.</Anchor>
3. Agrega el siguiente permiso al manifiesto: `com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE`

</Tab>
</Tabs>

</Accordion>

<div id="24-setting-required-permissions" />

<Accordion title="2.4 Configuración de los permisos necesarios">

Agregar permisos ayuda a aumentar la velocidad de la <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#probabilistic-modeling">atribución de modelo probabilístico</Anchor>. Esto también permite que el SDK envíe más datos como los datos de redes de proveedores y WiFi. Puedes encontrar estos datos en los <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">reportes de raw data</Anchor> y usarlos para analizar y optimizar las campañas.

#### Agregar los permisos necesarios

1. Agrega los siguientes permisos a AndroidManifest.xml:  

   ```html Markup
   <uses-permission android:name="android.permission.INTERNET" />
   <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
   <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
   <!-- Opcional: -->
   <uses-permission android:name="android.permission.READ_PHONE_STATE" />
   ```

</Accordion>

## Uso de la extensión del SDK de Adobe

Ahora puedes empezar a utilizar la extensión del SDK de Adobe para enviar datos a Adobe y AppsFlyer.

> 📘 **Note**
>
> **Nota:**
>
> Actualmente, la extensión del SDK de Adobe Launch solo admite la obtención de datos de conversión y el envío de eventos. Sin embargo, cuando agregas la extensión del SDK de Adobe Launch a tu aplicación, también se agrega el SDK de AppsFlyer. Por lo tanto, cualquier funcionalidad que falte actualmente en la extensión del SDK de Adobe se puede implementar utilizando el SDK de AppsFlyer.

<div id="sending-events" />

<Accordion title="Envío de eventos">

Los eventos in-app brindan información sobre lo que está sucediendo en tu aplicación. Te recomendamos que te tomes un tiempo para definir los eventos que deseas registrar. El registro de eventos in-app te ayuda a medir los KPI como el retorno de la inversión (ROI) y el valor de vida útil (LTV).

La extensión del SDK de Adobe Launch te permite enviar datos de eventos in-app tanto a Adobe como a AppsFlyer. A continuación, puedes utilizar Adobe Analytics para analizar el comportamiento de los usuarios y AppsFlyer para analizar el ROI y el LTV.

<Tabs>
<Tab title="Android">

```java
final Map<String,String> eventMap = new HashMap<>();
eventMap.put("currency", "USD");
eventMap.put("revenue", "200");
eventMap.put("freehand", "param");

MobileCore.trackAction("af_purchase", eventMap);
```

</Tab>

<Tab title="apps de iOS,">

```java
[ACPCore trackAction:@"af_purchase data:@{@"revenue":@"200",@"currency":@"USD"];
```

</Tab>
</Tabs>

Al enviar los eventos como se especifica en el código anterior, se crea un evento en el panel de control de AppsFlyer llamado af\_purchase con unos ingresos de 200 USD. Este evento también se envía a Adobe Analytics y aparece en él.

Todos los <Anchor target="_blank" href="https://dev.appsflyer.com/docs/direct-deep-linking-1">datos de conversión</Anchor> que se envían con eventos tienen el prefijo ***appsflyer***. Consulta la siguiente tabla para ver algunos ejemplos:

| Variables de datos de conversión con prefijo |
| --- |
| appsflyer.af\_click\_lookback |
| appsflyer.install\_time |
| appsflyer.cost\_cents\_USD |
| appsflyer.media\_source |
| appsflyer.af\_adset |
| appsflyer.click\_time |
| appsflyer.orig\_cost |
| appsflyer.campaign |

Los datos de conversión están disponibles en Analysis Workspace en Adobe Analytics. Para obtener más información sobre cómo migrar las reglas de procesamiento de Adobe Mobile Services a Adobe Analytics, consulta [la documentación de Adobe](https://experienceleague.adobe.com/en/docs/analytics/technotes/migrate-mobile).

</Accordion>

<div id="getting-data-for-deep-linking-and-deferred-deep-linking" />

<Accordion title="Obtención de datos para enlaces profundos y enlaces profundos diferidos">

Los enlaces profundos y los enlaces profundos diferidos te permiten mejorar tu experiencia de usuario. Permiten abrir la aplicación en actividades específicas y personalizar el contenido según los datos de la campaña.

Para obtener datos de enlaces profundos, implementa la extensión de devolución de llamada.

<Tabs>
<Tab title="Android">

En la clase de aplicación global, implementa el siguiente código:

```java
AppsFlyerAdobeExtension.registerAppsFlyerExtensionCallbacks(new AppsFlyerExtensionCallbacksListener() {
		@Override
		public void onCallbackReceived(Map<String, String> callback) {
			Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			if(callback.get("callback_type").equals("onConversionDataReceived")){
				// datos de conversión devueltos
				if(callback.get("is_first_launch").equals("true")){
					String af_status = callback.get("af_status");
					if(af_status.equals("Non-organic")){
						Log.d(AppsFlyerLibCore.LOG_TAG, "¡Esta es la primera apertura y una instalación no orgánica!");
					}
				}
			} else if(callback.get("callback_type").equals("onAppOpenAttribution")){
				// deep link directo: redirigir al usuario
				Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			}
		}
		@Override
		public void onCallbackError(String errorMessage) {
			Log.d("TAG", errorMessage);
		}
	});
```

</Tab>

<Tab title="apps de iOS,">

En AppDelegate.m, implementa el código siguiente:

```objectivec
[AppsFlyerAdobeExtension registerCallbacks:^(NSDictionary *dictionary) {
        NSLog(@"[AppsFlyerAdobeExtension] Callback recibido: %@", dictionary);
        if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onConversionDataReceived"]){
            if([[dictionary objectForKey:@"is_first_launch"] boolValue] == YES){
                NSString* af_status = [dictionary objectForKey:@"af_status"];
                if([af_status isEqualToString:@"Non-organic"]){
                    NSLog(@"this is first launch and a non organic install!");
                }
            }
        } else if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onAppOpenAttribution"]) {
            NSLog(@"onAppOpenAttribution Received");
        }
     }];
    [AppsFlyerAdobeExtension callbacksErrorHandler:^(NSError *error) {
          NSLog(@"[AppsFlyerAdobeExtension] Error recieving callback: %@" , error);
    }];
```

</Tab>
</Tabs>

</Accordion>

## Conexión de datos de conversión de AppsFlyer

Los datos de conversión se envían con eventos a la plataforma de Adobe. Estas variables te permiten aplicar lógica y reglas a las dimensiones, métricas o filtros de los reportes.

1. Inicia sesión en tu cuenta de Adobe Analytics.

   ![Captura de pantalla del login de Adobe Analytics](https://files.readme.io/d56f170695893dbbde00c50c838ce8a5c2cfe418a17692f372e208d458ed2d6c-31205379096465.png)
2. Ve a **Admin** > **Report Suites**
3. Selecciona la Report Suite que se configuró durante la implementación de Adobe Analytics.
4. Selecciona **General** > **Processing rules**.
5. Crea reglas de procesamiento para asignar las variables de contexto de AppsFlyer a eVars.

Consulta la siguiente tabla para asignar las variables de contexto de AppsFlyer:

| **Nombre recomendado para asignar** | **Datos de conversión** |
| --- | --- |
| Ventana retrospectiva de AppsFlyer | appsflyer.af\_click\_lookback |
| Hora de instalación de AppsFlyer | appsflyer.install\_time |
| Costo de AppsFlyer en centavos de dólar | appsflyer.cost\_cents\_USD |
| Fuente de medios de AppsFlyer | appsflyer.media\_source |
| Conjunto de anuncios de AppsFlyer | appsflyer.af\_adset |
| Hora de clic de AppsFlyer | appsflyer.click\_time |
| Costo original de AppsFlyer | appsflyer.orig\_cost |
| Campaña de AppsFlyer | appsflyer.campaign |

### Uso de datos de conversión asignados de AppsFlyer para Analytics y Análisis

Todos los datos procedentes del SDK están disponibles en el grupo de reportes de Adobe Analytics que está conectado a la aplicación.

Puedes utilizar los datos y sus dimensiones y métricas relacionadas en los reportes y paneles de Adobe Analytics generados. Estos datos también están disponibles en el panel de control de AppsFlyer para la atribución y el análisis de eventos in-app.

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01HQQN1Y7MP7B0GXJFP5330G80=visi%C3%B3n-general prerequisites=requisitos-previos h_01HQQN1JWAQZZ9S3YV7VXTMRWM=requisitos-previos h_01HQQN1JWA4JYET26CB11JGY46=get-your-appsflyer-dev-key h_01HQQN1JWAHYQBRY43EWANQ57Z=get-your-app-id step-1-configuring-adobe-launch=paso-1-configuraci%C3%B3n-de-adobe-launch h_01HQQN1JWAAR873B679QGA9NSX=paso-1-configuraci%C3%B3n-de-adobe-launch h_01HQQN1JWAE1T7SP3DHTFB55TK=11-creating-a-new-property-in-adobe-launch h_01HQQN1JWA8FDWMNZ4Y17AWYKW=12-installing-required-adobe-launch-extensions installing-adobe-analytics-extension=instalaci%C3%B3n-de-la-extensi%C3%B3n-de-adobe-analytics h_01HQQN1JWAMB8607K8V2F3YKHE=instalaci%C3%B3n-de-la-extensi%C3%B3n-de-adobe-analytics installing-appsflyer-sdk-extension=instalaci%C3%B3n-de-la-extensi%C3%B3n-del-sdk-de-appsflyer h_01HQQN1JWAYHP9243MTFZ4B2EF=instalaci%C3%B3n-de-la-extensi%C3%B3n-del-sdk-de-appsflyer install-profile-and-mobile-core-extension=instalaci%C3%B3n-de-la-extensi%C3%B3n-de-profile-y-mobile-core h_01HQQN1JWA1TEBQY1NH3YP2HQB=instalaci%C3%B3n-de-la-extensi%C3%B3n-de-profile-y-mobile-core step-2-implementing-appsflyer-adobe-sdk-extension=paso-2-implementaci%C3%B3n-de-la-extensi%C3%B3n-del-sdk-de-adobe-de-appsflyer h_01HQQN1JWB3B24RHP9QMNPJK8J=paso-2-implementaci%C3%B3n-de-la-extensi%C3%B3n-del-sdk-de-adobe-de-appsflyer h_01HQQN1JWBMP4ARMH2VPX35TGH=21-adding-the-sdk-to-the-app h_01HQQN1JWBV3144WY92PAX6PW2=22-publishing-the-environment h_01HQQN1JWBRRCTGA6Q9RDC41KN=23-adding-android-install-referrer-to-your-app h_01HQQN1JWB19NTCNTWX9QRP8AC=24-setting-required-permissions add-required-permissions=agregar-los-permisos-necesarios h_01HQQN1JWBVVVGRRXGX9ZJTBT8=agregar-los-permisos-necesarios using-the-adobe-sdk-extension=uso-de-la-extensi%C3%B3n-del-sdk-de-adobe h_01HQQN1JWBFD2CZ4PMCBRM3JN8=uso-de-la-extensi%C3%B3n-del-sdk-de-adobe h_01HQQN1JWBVZDAVAZD4NXMBG4S=sending-events h_01HQQN1JWBXG0JCE9RKA659H6V=getting-data-for-deep-linking-and-deferred-deep-linking connecting-appsflyer-conversion-data=conexi%C3%B3n-de-datos-de-conversi%C3%B3n-de-appsflyer h_01HQQN1JWBMBXGQFKGWHE058VT=conexi%C3%B3n-de-datos-de-conversi%C3%B3n-de-appsflyer using-appsflyer-mapped-conversion-data-for-analytics-and-analysis=uso-de-datos-de-conversi%C3%B3n-asignados-de-appsflyer-para-analytics-y-an%C3%A1lisis h_01HQQN1JWB0WBD6HZXQN6STJY9=uso-de-datos-de-conversi%C3%B3n-asignados-de-appsflyer-para-analytics-y-an%C3%A1lisis" />
