---
title: Integración de Oracle Responsys con AppsFlyer
metadata:
  keywords:
    - Oracle Responsys
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-11-20T09:26:13Z'
  edited_at: '2026-08-22T00:33:41Z'
  id: 360003798297
  locale: es
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/es/articles/360003798297
---
> **At a glance:** Oracle Responsys, una plataforma de entrega y análisis de correo electrónico, integra AppsFlyer OneLink dentro de los correos electrónicos. Los destinatarios de correo electrónico que hacen clic en el enlace deben tener enlaces profundos a tu aplicación.

<Image align="center" alt="oracle-responsys-af-logo.png" src="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png" />

Los ESP (proveedores de servicios de correo electrónico) pueden ser excelentes fuentes para el tráfico segmentado de usuarios.

Uno de los desafíos con los ESP es realizar una atribución y unos enlaces profundos correctos. Los ESP envuelven la URL del enlace profundo con el dominio de registro de clics de su propio ESP. Este procedimiento a menudo rompe la funcionalidad de los enlaces universales de iOS y los enlaces de aplicaciones de Android.

Sin embargo, los enlaces profundos y el registro de clics siguen siendo posibles con los ESP que admiten enlaces universales y enlaces de aplicaciones además de su dominio de grabación de clics. Además, puedes configurar tu propio dominio de clic para que actúe como dominio de registro de clics.

<div id="prerequisites" />

## Requisitos previos

* Configura tu aplicación para admitir <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">enlaces profundos con OneLink</Anchor>.
* Verifica la versión de tu SDK (tanto Android como iOS).

<Tabs>
<Tab title="apps de iOS,">

* Versión 4.9.0 del SDK de iOS para AppsFlyer (o superior)

</Tab>

<Tab title="Android">

* Versión 4.9.0 del SDK de Android para AppsFlyer (o superior)

</Tab>
</Tabs>

<div id="setting-up-oracle-responsys-click-domain" />

## Configuración del dominio de clic de Oracle Responsys

Sigue esta sección para configurar tu dominio de clic (dominio de registro del clic) en Oracle Responsys.

<div id="step-1-set-up-a-click-domain-in-oracle-responsys" />

### Paso 1: Configura un dominio de clic en Oracle Responsys

Para configurar un dominio de clic, sigue la guía oficial de Oracle Responsys sobre cómo <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCEA/LinkTable_Main.htm?cshid=LinkTable_Main">crear dominios de clic</Anchor>. Oracle Responsys utiliza tablas de enlaces para ayudar a registrar clics para una campaña específica

**Ten en cuenta** que, en las tablas de enlaces, puedes definir la **URL de enlace IOS** para que sea la misma que la URL de enlace:

<Image align="center" alt="Oracle-responsys-link-tracking-table.png" src="https://files.readme.io/c151c58af73cf460ba4275a9159e45c15807f311fa8d8b4b1531b0cdf7e3bc4e-49839256667665.png" />

Una vez que configures los dominios de clic en las tablas de enlaces, Responsys utiliza estos dominios para encapsular los OneLink que incluyas en campañas de correo electrónico. De esta manera, Responsys puede registrar clics en su sistema mientras conserva los OneLinks y la funcionalidad de enlaces profundos.

<div id="step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android" />

### Paso 2: Proporciona a Responsys un archivo AASA (iOS) y un archivo Asset Links (Android)

<div id="aasa-for-ios" />

<Accordion title="AASA para iOS">

Para que Responsys sea compatible con los enlaces universales de iOS, necesita un archivo AASA. Consulta las siguientes instrucciones.

Cuando configuras OneLink con enlaces universales, ya tienes un AASA asociado con OneLink. Para obtener el AASA:

1. Ve a la configuración de OneLink y busca un OneLink que esté configurado con enlaces universales.
2. Agrega **/.well-known/apple-app-site-association** al final de la URL de OneLink.
3. Pega el OneLink en la barra de direcciones del navegador y presiona enter. Por ejemplo: **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-association**. Cuando lo haces, el archivo AASA se descarga en tu computadora. Puedes abrirlo usando cualquier editor de texto simple.
4. Envía este archivo AASA a Responsys. Para obtener más información y conocer más sobre el contenido de este archivo, consulta la página 11 de la <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/pdf/ios-universal-links-dev-guide.pdf">guía de Oracle</Anchor>.

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Asset Links para Android">

Cuando configuras OneLink con enlaces de aplicaciones, ya tienes un archivo Asset Links asociado con OneLink. Para obtener el archivo Asset Links. Para obtener el archivo Asset Links:

1. Ve a la configuración de OneLink y busca un OneLink que esté configurado con enlaces de aplicaciones.
2. Agrega **/.well-known/assetlinks.json** al final de la URL de OneLink.
3. Pega el OneLink en la barra de direcciones del navegador y presiona enter. Por ejemplo:**`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json**. Cuando lo haces, el archivo Asset Links se descarga en tu computadora. Puedes abrirlo usando cualquier editor de texto simple.
4. Envía este archivo Asset Links a Responsys. Para obtener más información y saber más sobre el contenido de este archivo, consulta <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/android/app-links/">esta guía</Anchor>.

</Accordion>

<div id="setting-up-your-app" />

## Configuración de tu aplicación

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<Accordion title="Paso 1 para Android: Configuración de tu aplicación para que sea compatible con App Links">

<div id="adding-the-click-domain-to-the-activity-in-the-android-manifest" />

#### Agregar el dominio de clic a la actividad en el manifiesto de Android

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

<div id="setting-up-the-app-to-resolve-click-domains" />

#### Configuración de la aplicación para resolver dominios de clic

El SDK necesita resolver el OneLink detrás del dominio de clic para obtener los detalles de la campaña. Los detalles se devuelven en el método `onAppOpenAttribution`.

Para resolver dominios de clic:

1. Asegúrate de que la versión de tu SDK sea al menos 4.9.0.
2. Enumera los dominios de clic en la API del SDK `setResolveDeepLinkURLs`. Esta API debe llamarse antes de la inicialización del SDK. Para obtener más información, consulta la documentación del SDK <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">aquí</Anchor>.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```

   * **Nota:** **Importante:** Si estás utilizando Movable Ink (MI) junto con Oracle, necesitas obtener el MI CNAME y los dominios internos de tu administrador de cuenta MI y agregarlos a `setResolveDeepLinkURLs`, además del enlace de clic para Oracle. Por ejemplo:

     ```java
     AppsFlyerLib.getInstance().setResolveDeepLinkURLs("oracle-click.example.com", "mi.example.com", "example.micpn.com");
     ```

</Accordion>

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<Accordion title="Paso 1 para iOS: Configurar tu aplicación para que sea compatible con enlaces universales">

En esta sección se explica cómo configurar tu aplicación para que sea compatible con enlaces universales.

<div id="associating-click-domains-in-xcode" />

#### Asociar dominios de clic en Xcode

1. En Xcode, haz clic en tu proyecto.
2. Haz clic en ***Capabilities***. ![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
3. Activa ***Associated Domains***.
4. Haz clic en el signo + y agrega tu dominio de clic. Por ejemplo, applinks:click.example.com.

</Accordion>

<div id="step-2-setting-up-the-app-to-resolve-click-domains" />

### Paso 2: Configurar la aplicación para resolver dominios de clic

El SDK necesita resolver el OneLink detrás del dominio de clic para obtener los detalles de la campaña. Los detalles se devuelven en el método `onAppOpenAttribution`.

Para resolver dominios de clic:

1. Asegúrate de que la versión de tu SDK sea al menos 4.9.0.
2. Enumera los dominios de clic en la propiedad del SDK `resolveDeepLinkURLs`. Esta propiedad debe establecerse antes de la inicialización del SDK. Para obtener más información, consulta la documentación del SDK <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">aquí</Anchor>.  

   <Tabs>
   <Tab title="Objective-C">

   ```objectivec
   [AppsFlyerTracker sharedTracker].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Tab>

   <Tab title="Swift">

   ```swift
   AppsFlyerTracker.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Tab>
   </Tabs>

   * **Nota:** **Importante:** Si estás utilizando Movable Ink (MI) junto con Oracle, necesitas obtener el MI CNAME y los dominios internos de tu administrador de cuenta MI y agregarlos a `setResolveDeepLinkURLs`, además del enlace de clic para Oracle. Ejemplos de dominios:
     * Dominio de Oracle: oracle-click.example.com
     * Dominio MI CNAME: mi.example.com
     * Dominio interno de MI: ejemplo.micpn.com
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

<div id="sending-your-first-email" />

## Envío de tu primer correo electrónico

1. Crea una URL de OneLink en la página de Gestión de enlaces (o manualmente).
2. Al crear la URL de OneLink, asegúrate de codificar por URL todos los valores de los parámetros.
3. Los siguientes parámetros son muy recomendables para usar:
   * pid (media source): utiliza una fuente de medios que signifique este uso, por ejemplo Email.
   * c (campaña): el nombre de la campaña que se quiere medir.
   * af\_dp: el esquema de URI de enlace profundo al que deseas enlazar profundamente a tus usuarios.
   * af\_web\_dp: dónde redirigir a los usuarios haciendo clic en el enlace en un dispositivo de escritorio.
   * af\_ios\_url - Dónde redirigir a los usuarios que no tienen la aplicación al hacer clic en el enlace en un dispositivo iOS.
   * af\_android\_url - Dónde redirigir a los usuarios que no tienen la aplicación al hacer clic en el enlace en un dispositivo Android.
4. Introduce la URL de OneLink en el correo electrónico que hayas creado en Responsys. Ejemplo:

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Download my great app!</a>
   ```

   En esta etapa, Responsys envuelve el enlace anterior con el dominio de clic que configuraste en los pasos anteriores. Cualquier clic en el dominio de clic redirige al enlace de atribución de OneLink. Si la aplicación está instalada en el dispositivo del usuario, el dominio de clic se enlaza profundamente a la aplicación.

> 📘 **Note**
>
> **Ejemplo**
>
> Los parámetros de URL no están codificados por URL en este ejemplo, para que sean legibles.
>
> ```http
> https://greatapp.onelink.me/abcd?pid=Email&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

<div id="testing-your-links" />

### Prueba tus enlaces

Después de seguir todos los pasos requeridos mencionados anteriormente, crear la URL de OneLink adecuada y colocarla en un correo electrónico, envíate un correo electrónico de prueba.

¿Qué debes esperar?

Si tienes la aplicación instalada, la aplicación debe ser invocada. Si se implementan las API de enlaces profundos relevantes del SDK de AppsFlyer, debes tener un enlace profundo al contenido relevante.  
Además, debe aparecer un clic tanto en el panel de control de AppsFlyer, atribuido a la fuente de medios y campaña proporcionadas, como también en los datos de Responsys.

<div data-zendesk-anchors="prerequisites=requisitos-previos h_01HDNSK7GR33AN2M4GP956S1FD=requisitos-previos setting-up-oracle-responsys-click-domain=configuraci%C3%B3n-del-dominio-de-clic-de-oracle-responsys h_01HDNSK7GR84QSRTS86GH556WK=configuraci%C3%B3n-del-dominio-de-clic-de-oracle-responsys step-1-set-up-a-click-domain-in-oracle-responsys=paso-1-configura-un-dominio-de-clic-en-oracle-responsys h_01HDNSK7GRHYJZSMYCMT9RVEBW=paso-1-configura-un-dominio-de-clic-en-oracle-responsys step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android=paso-2-proporciona-a-responsys-un-archivo-aasa-ios-y-un-archivo-asset-links-android h_01HDNSK7GRW57NNXMN1SWFTTFZ=paso-2-proporciona-a-responsys-un-archivo-aasa-ios-y-un-archivo-asset-links-android h_01HDNSK7GR77N60SFVBD57S9GQ=aasa-for-ios h_01HDNSK7GR6ADJCPG63ZVP19NJ=asset-links-for-android setting-up-your-app=configuraci%C3%B3n-de-tu-aplicaci%C3%B3n h_01HDNSK7GRN751HAPPQ3HVRMDG=configuraci%C3%B3n-de-tu-aplicaci%C3%B3n h_01HDNSK7GRHCK378A8XKMK7ZZF=step-1-for-android-setting-up-your-app-to-support-app-links adding-the-click-domain-to-the-activity-in-the-android-manifest=agregar-el-dominio-de-clic-a-la-actividad-en-el-manifiesto-de-android h_01HDNSK7GRQNQGWXAEGHSTHADH=agregar-el-dominio-de-clic-a-la-actividad-en-el-manifiesto-de-android setting-up-the-app-to-resolve-click-domains=configuraci%C3%B3n-de-la-aplicaci%C3%B3n-para-resolver-dominios-de-clic h_01HDNSK7GRP9ND0MHC3ZHD7G8H=configuraci%C3%B3n-de-la-aplicaci%C3%B3n-para-resolver-dominios-de-clic h_01HDNSK7GRJ682QYAMPB4PSGRZ=step-1-for-ios-setting-up-your-app-to-support-universal-links associating-click-domains-in-xcode=asociar-dominios-de-clic-en-xcode h_01HDNSK7GSRENM232MQ25EB3J3=asociar-dominios-de-clic-en-xcode step-2-setting-up-the-app-to-resolve-click-domains=paso-2-configurar-la-aplicaci%C3%B3n-para-resolver-dominios-de-clic h_01HDNSK7GSP08G2EQSNVR5G45B=paso-2-configurar-la-aplicaci%C3%B3n-para-resolver-dominios-de-clic sending-your-first-email=env%C3%ADo-de-tu-primer-correo-electr%C3%B3nico h_01HDNSK7GSA9VAMTRFCX8SZGSC=env%C3%ADo-de-tu-primer-correo-electr%C3%B3nico testing-your-links=prueba-tus-enlaces h_01HDNSK7GSTAJXAP6KGKE9TD8T=prueba-tus-enlaces" />
