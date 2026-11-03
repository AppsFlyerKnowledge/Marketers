---
title: Integración de Iterable con AppsFlyer
metadata:
  keywords:
    - OneLink
    - Advertisers
    - ESP
    - Developers
    - Iterable
    - Deep Likning
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-09-16T13:14:19Z'
  edited_at: '2026-08-22T00:33:36Z'
  id: 360002522337
  locale: es
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/es/articles/360002522337
---
> **At a glance:** Integra los enlaces de atribución basados en OneLink con el sistema Iterable para <Anchor target="_blank" href="/marketers/es/docs/email-service-provider-esp-integration-guide">Deep Linking desde correos electrónicos</Anchor>. La integración utiliza la compatibilidad de Iterable con enlaces universales, además de los dominios de registro de clics de marca.

![iterable-af-logo.png](https://files.readme.io/e339ea75a54e53711f3c577c7f82339151af13e6c086cc1435cbb57cf1fae3f0-49839295443089.png)

## Introducción

Los ESP (proveedores de servicios de correo electrónico) pueden ser excelentes fuentes para el tráfico segmentado de usuarios.

Uno de los problemas con los ESP es registrar los clics mientras se mantiene intacta la funcionalidad de enlaces profundos. Los ESP envuelven las URL de enlaces profundos con su propio dominio de registro de clics del ESP. Este procedimiento a veces interrumpe el proceso de enlaces universales de iOS.

Con Iterable, que admite enlaces universales además de su dominio de registro de clics, se pueden seguir realizando enlaces profundos y registro de clics.

## Requisitos previos

<Tabs>
<Tab title="apps de iOS,">

* SDK de AppsFlyer para iOS, versión 4.9.0

</Tab>

<Tab title="Android">

* SDK de AppsFlyer para Android, versión 4.9.0

Iterable no es compatible con los enlaces de aplicaciones de Android. Sin embargo, <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">admite los enlaces profundos de esquema URI</Anchor>. No se requieren acciones especiales en el lado de Iterable para admitir enlaces profundos en Android.

</Tab>
</Tabs>

## Configuración de Iterable

### Paso 1: Configurar la marca del enlace en Iterable

Crea un dominio de registro de clics dedicado y configura un subdominio (por ejemplo, [click.example.com](http://click.example.com)). Puedes hacerlo comprando un dominio designado o utilizando tu propio dominio.

Para obtener más información sobre cómo configurar un dominio de registro de clics con Iterable, consulta <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/115002651226-Setting-up-mail-domains">aquí</Anchor>.

### Paso 2: Subir tu certificado SSL a Iterable

Tu dominio de registro de clics debe incluir el certificado SSL de tu dominio. El certificado SSL debe estar instalado en tu cuenta de Iterable. Las instrucciones para instalar tus certificados SSL se pueden encontrar <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/115000427446-How-to-Set-up-HTTPS-for-Links-for-Click-Tracking">aquí</Anchor>.

### Paso 2: Proporcionar a Iterable un archivo AASA (iOS) y un archivo de enlaces de recursos (Android)

<div id="aasa-for-ios" />

<Accordion title="AASA para iOS">

Para que Iterable admita los enlaces universales de iOS, necesita un archivo AASA. Consulta las siguientes instrucciones.

Cuando configuras OneLink con enlaces universales, ya tienes un AASA asociado con OneLink. Para obtener el AASA:

1. Ve a ***Plantillas de OneLink*** y busca un OneLink que esté configurado con enlaces universales.
2. Agrega **/.well-known/apple-app-site-association** al final de la URL de OneLink.
3. Pega el OneLink en la barra de direcciones del navegador y presiona Enter. Por ejemplo: **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-association**. Cuando lo hagas, el archivo AASA se descargará en tu computadora. Puedes abrirlo usando cualquier editor de texto simple.
4. Define las reglas de reescritura de los enlaces. Para más información, consulta <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035496511">aquí</Anchor>.
5. Envía este archivo AASA a Iterable. Para obtener más información y saber más sobre el contenido de este archivo, consulta la <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035496511-iOS-Universal-Lin">guía de Iterable</Anchor>.

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Enlaces de recursos para Android">

Cuando configuras OneLink con enlaces de aplicaciones, ya tienes un archivo de enlaces de recursos asociado con OneLink. Para obtener el archivo de enlaces de recursos:

1. Ve a ***Plantillas de OneLink*** y busca un OneLink que esté configurado con enlaces de aplicaciones.
2. Agrega **/.well-known/assetlinks.json** al final de la URL de OneLink.
3. Pega el OneLink en la barra de direcciones del navegador y presiona Enter. Por ejemplo:**`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json**. Cuando lo hagas, el archivo de enlaces de recursos se descargará en tu computadora. Puedes abrirlo usando cualquier editor de texto simple.
4. Envía este archivo de enlaces de recursos a Iterable. Para obtener más información y saber más sobre el contenido de este archivo, consulta la <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035127392">guía de Iterable</Anchor>.

</Accordion>

## Configuración de tu aplicación

Consulta lo siguiente para configurar tus aplicaciones para que admitan enlaces universales y de aplicaciones.

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<Accordion title="Paso 1 para Android: Configurar la aplicación para que admita enlaces de aplicaciones">

#### Paso 1: Agregar el dominio de clic a la actividad en el manifiesto de Android

En el manifiesto de Android, agrega el host del dominio de clic y cualquier prefijo en la etiqueta de actividad de la actividad a la que quieres hacer un enlace profundo.

```html Markup
<activity android:name=".DeepLinkActivity">
    <intent-filter  android:autoVerify="true">
        <action android:name="android.intent.action.VIEW" />
           <category android:name="android.intent.category.DEFAULT" />
           <category android:name="android.intent.category.BROWSABLE" />
           <data android:scheme="https"
               android:host="click.example.com"
               android:pathPrefix="/campaign" />
     </intent-filter>
</activity>
```

#### Paso 2: Configurar la aplicación para resolver dominios de clic

El SDK necesita resolver el OneLink detrás del dominio de clic para obtener los detalles de la campaña. Los detalles se devuelven en el método `onAppOpenAttribution`.

Para resolver dominios de clic:

1. Asegúrate de que la versión de tu SDK sea al menos 4.9.0.
2. Enumera los dominios de clic en la API del SDK `setResolveDeepLinkURLs`. Esta API debe llamarse antes de la inicialización del SDK. Para obtener más información, consulta la documentación del SDK <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">aquí</Anchor>.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```

</Accordion>

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<Accordion title="Paso 1 para iOS: Configurar la aplicación para que admita enlaces universales">

En esta sección se explica cómo configurar tu aplicación para que admita enlaces universales.

#### Paso 1: Asociar dominios de clic en Xcode

1. En Xcode, haz clic en tu proyecto.
2. Haz clic en ***Capabilities***. ![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
3. Activa ***Associated Domains***.
4. Haz clic en el signo + y agrega tu dominio de clic. Por ejemplo, applinks:click.example.com.

</Accordion>

Consulta lo siguiente para configurar el SDK para resolver enlaces profundos.

<div id="step-2-for-android-resolve-deep-links" />

<Accordion title="Paso 2 para Android: resolver enlaces profundos">

El SDK necesita resolver el OneLink detrás del dominio de clic para obtener los detalles de la campaña. Los detalles se devuelven en el método `onAppOpenAttribution`.

Para resolver dominios de clic:

1. Asegúrate de que la versión de tu SDK sea al menos 4.9.0.
2. Enumera los dominios de clic en la propiedad del SDK `resolveDeepLinkURLs`. Esta propiedad debe configurarse antes de la inicialización del SDK. Para obtener más información, consulta la documentación del SDK <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">aquí</Anchor>.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("clickdomain.com", "myclickdomain.com", "anotherclickdomain.com");
   ```

</Accordion>

<div id="step-2-for-ios-resolve-deep-links" />

<Accordion title="Paso 2 para iOS: resolver enlaces profundos">

El SDK necesita resolver el OneLink detrás del dominio de clic para obtener los detalles de la campaña. Los detalles se devuelven en el método `onAppOpenAttribution`.

Para resolver dominios de clic:

1. Asegúrate de que la versión de tu SDK sea al menos 4.9.0.
2. Enumera los dominios de clic en la propiedad del SDK `resolveDeepLinkURLs`. Esta propiedad debe configurarse antes de la inicialización del SDK. Para obtener más información, consulta la documentación del SDK <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">aquí</Anchor>.  

   <Tabs>
   <Tab title="Objective-C">

   ```objectivec
   [AppsFlyerLib shared].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Tab>

   <Tab title="Swift">

   ```swift
   AppsFlyerLib.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Tab>
   </Tabs>

3. Agrega el siguiente código para que el SDK pueda resolver el dominio de registro de clics:  

   <Tabs>
   <Tab title="Objective-C">

   Agrega este código en AppDelegate.m

   ```objectivec
   - (NSDictionary *)allHTTPHeaderFieldsForResolveDeepLinkURL:(NSURL *)URL {
       if ([URL.host  isEqual: @"click.example.com"]) {
           return [NSDictionary dictionary];
       }
       else {
           return nil;
       }
   }
   ```

   </Tab>

   <Tab title="Swift">

   Agrega este código en AppDelgate.swift

   ```swift
   func allHTTPHeaderFields(forResolveDeepLinkURL URL: -> [String : String]! URL!) -> [String : String]! {
       if (URL.host == "click.example.com") {
           /// Change User-Agent
           return [:]
       } else {
           return nil;
       }
   }
   ```

   </Tab>
   </Tabs>

</Accordion>

## Envío de tu primer correo electrónico

1. Crea una URL de OneLink en la página Administración de enlaces (o manualmente).
2. Al crear la URL de OneLink, asegúrate de codificar en la URL todos los valores de los parámetros.
3. Los siguientes parámetros son muy recomendables para usar:
   * pid (fuente de medios): utiliza una fuente de medios que signifique este uso, por ejemplo, correo electrónico.
   * c (campaña): el nombre de la campaña que se quiere medir.
   * af\_dp: el esquema de URI de enlace profundo al que deseas enlazar profundamente a tus usuarios.
   * af\_web\_dp: dónde redirigir a los usuarios haciendo clic en el enlace en el escritorio.
   * af\_ios\_url: dónde redirigir a los usuarios que no tienen la aplicación haciendo clic en el enlace en un dispositivo iOS.
   * af\_android\_url: dónde redirigir a los usuarios que no tienen la aplicación haciendo clic en el enlace en un dispositivo Android.
4. Coloca la URL de OneLink en el correo electrónico que crees en Iterable. Ejemplo:

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Download my great app!</a>
   ```

   En este punto, Iterable envuelve el enlace anterior con el dominio de clic que configuraste en los pasos anteriores. Cualquier clic en el dominio de clic redirige al enlace de atribución de OneLink. Si la aplicación está instalada en el dispositivo del usuario, el dominio de clic se enlaza profundamente a la aplicación.

> 📘 **Note**
>
> **Ejemplo**
>
> Los parámetros de la URL no están codificados en la URL en este ejemplo, para que sean legibles:
>
> ```http
> https://greatapp.onelink.me/abcd?pid=Email&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

### Prueba tus enlaces

Después de seguir todos los pasos requeridos mencionados anteriormente, crear la URL de OneLink adecuada y colocarla en un correo electrónico, envíate un correo electrónico de prueba.

¿Qué debes esperar?

Si tienes la aplicación instalada, la aplicación debe ser invocada. Si se implementan las API de enlaces profundos relevantes del SDK de AppsFlyer, debes tener un enlace profundo al contenido relevante.  
Además, debe aparecer un clic tanto en el panel de control de AppsFlyer, atribuido a la fuente de medios y campaña proporcionadas, como también en los datos de Iterable.

<div data-zendesk-anchors="introduction=introducci%C3%B3n h_01HV6PJQRMT8037JMVMMXDPWGN=introducci%C3%B3n prerequisites=requisitos-previos h_01HV6PJQRM5N1K6CY0NSSFXT3X=requisitos-previos setting-up-iterable=configuraci%C3%B3n-de-iterable h_01HV6PJQRMX18FRB3NMZH6NCH0=configuraci%C3%B3n-de-iterable step-1-setting-up-link-branding-in-iterable=paso-1-configurar-la-marca-del-enlace-en-iterable h_01HV6PJQRMMYV3A5ZSEGTT7993=paso-1-configurar-la-marca-del-enlace-en-iterable step-2-uploading-your-ssl-certificate-to-iterable=paso-2-subir-tu-certificado-ssl-a-iterable h_01HV6PJQRMYDDWK9AKGN258TTM=paso-2-subir-tu-certificado-ssl-a-iterable step-2-give-iterable-an-aasa-ios-and-an-asset-links-file-android=paso-2-proporcionar-a-iterable-un-archivo-aasa-ios-y-un-archivo-de-enlaces-de-recursos-android h_01HV6PJQRMFJ23627KS83D4C6A=paso-2-proporcionar-a-iterable-un-archivo-aasa-ios-y-un-archivo-de-enlaces-de-recursos-android h_01HV6PJQRMNSYK8N7QEE00KSPE=aasa-for-ios h_01HV6PJQRMSMZCVJ5XRXZ3SWEH=asset-links-for-android setting-up-your-app=configuraci%C3%B3n-de-tu-aplicaci%C3%B3n h_01HV6PJQRMJHDF94JSAT8N8SP9=configuraci%C3%B3n-de-tu-aplicaci%C3%B3n h_01HV6PJQRM5S772CTH219MGY44=step-1-for-android-setting-up-your-app-to-support-app-links step-1-adding-the-click-domain-to-the-activity-in-the-android-manifest=paso-1-agregar-el-dominio-de-clic-a-la-actividad-en-el-manifiesto-de-android h_01HV6PJQRM2V31JAJ52Q3FHQWH=paso-1-agregar-el-dominio-de-clic-a-la-actividad-en-el-manifiesto-de-android step-2%20setting-up-the-app-to-resolve-click-domains=paso-2-configurar-la-aplicaci%C3%B3n-para-resolver-dominios-de-clic h_01HV6PJQRMCRFM90QSP5SS72SE=paso-2-configurar-la-aplicaci%C3%B3n-para-resolver-dominios-de-clic h_01HV6PJQRMVJB6J6GV41DCYAVQ=step-1-for-ios-setting-up-your-app-to-support-universal-links step-1-associating-click-domains-in-xcode=paso-1-asociar-dominios-de-clic-en-xcode h_01HV6PJQRNRW8Y97JWHP0MSXZF=paso-1-asociar-dominios-de-clic-en-xcode h_01HV6PJQRNHFH8XGMCEWVGSPA5=step-2-for-android-resolve-deep-links h_01HV6PJQRN4NYPWS2XQQSJAM5R=step-2-for-ios-resolve-deep-links sending-your-first-email=env%C3%ADo-de-tu-primer-correo-electr%C3%B3nico h_01HV6PJQRN2H29D8HKXHBYE1NB=env%C3%ADo-de-tu-primer-correo-electr%C3%B3nico testing-your-links=prueba-tus-enlaces h_01HV6PJQRNET2J17ZGGZE0K0Q6=prueba-tus-enlaces" />
