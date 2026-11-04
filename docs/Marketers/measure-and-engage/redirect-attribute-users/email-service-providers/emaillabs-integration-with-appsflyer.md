---
title: Integración de EmailLabs con AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2022-01-31T14:00:18Z'
  edited_at: '2026-08-22T00:33:34Z'
  id: 4419148952721
  locale: es
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/es/articles/4419148952721
---
> **At a glance:** EmailLabs, una plataforma de entrega y análisis de correo electrónico, integra AppsFlyer OneLink dentro de los correos electrónicos. Cuando los destinatarios de correo electrónico hacen clic en el enlace, se les dirige a tu aplicación mediante deep linking.

![emaillabs-af-logo.png](https://files.readme.io/467ee1fbcea8a36dff40172b1dbc97780a7e6cafd958ecb5b520a612c3308231-49839289267857.png)

<div id="introduction" />

## Introducción

Los ESP (proveedores de servicios de correo electrónico) pueden ser excelentes fuentes para el tráfico segmentado de usuarios.

Uno de los retos al usar ESP es registrar los clics sin perder la funcionalidad de deep linking. Los ESP envuelven la URL de deep linking con su propio dominio de registro de clics. Esta acción suele romper los enlaces universales de iOS.

Sin embargo, con los ESP que admiten enlaces universales además de su dominio de registro de clics, se pueden seguir realizando correctamente el deep linking y el registro de clics.

<div id="sdk-version-prerequisites" />

## Requisitos previos de la versión del SDK

<Tabs>
<Tab title="apps de iOS,">

* SDK de AppsFlyer para iOS, versión 6.0.4

</Tab>

<Tab title="Android">

* SDK de AppsFlyer para Android V6.6.0.0

</Tab>
</Tabs>

<div id="step-1-integration-setup-in-emaillabs" />

## Paso 1: Configuración de la integración en EmailLabs

**Para configurar la integración en EmailLabs:**

1. Configura tu dominio según <Anchor target="_blank" href="https://docs.emaillabs.io/get_started/getting-started/">este artículo</Anchor>
2. Configura tu dominio de registro de clics según <Anchor target="_blank" href="http://docs.emaillabs.io/user-panel/smtp-applications/whitelabel-2/">este artículo</Anchor> y la captura de pantalla que aparece a continuación.  
   ![whitelabel-section-2.png](https://files.readme.io/a5b992868a0abd94b2f24097ead760a98e6529e4f83ecfaf713d681800de4631-49839273475217.png)
3. Activa el tracking de enlaces según <Anchor target="_blank" href="http://docs.emaillabs.io/user-panel/smtp-applications/link-tracking/">este artículo</Anchor> y la captura de pantalla que aparece a continuación.  
   ![link-tracking-section-3.png](https://files.readme.io/3c1d0f13d3fcc2b49754cf4beb653592b9fffc27ad27775cf56986f78f9ea53b-49839289275153.png)
4. Ponte en contacto con el soporte de EmailLabs en [bok@emaillabs.pl](mailto:bok@emaillabs.pl) y solicita que habiliten SSL.
5. En EmailLabs, ve a **Panel** > **SMTP** **Accounts** > **Settings** > **Deep** **Links**, y marca la casilla Activated. Para las aplicaciones de iOS, introduce el <Anchor target="_blank" href="https://developer.apple.com/library/archive/documentation/General/Conceptual/DevPedia-CocoaCore/AppID.html">ID de aplicación de Apple</Anchor> en el campo correspondiente.  
   ![deeplinking-section-5.png](https://files.readme.io/15a5b45a58c1a130de6bfe2c3e9e3b379537b4fc549c1c3fcce41ef54b8653e9-49839289277073.png)

<div id="step-2-configuring-your-appsflyer-sdk" />

### Paso 2: Configuración de tu SDK de AppsFlyer

> 📘 **Note**
>
> **Nota:**
>
> Si aún no lo has hecho, asegúrate de que has configurado tu aplicación para que admita <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Deep Linking con OneLink</Anchor>.

Después de configurar tu dominio de registro de clics para que admita enlaces universales, como se ha descrito anteriormente, debes configurar tu aplicación para hacer deep linking y resolver ese enlace universal.

1. Asocia el dominio de registro de clics en Xcode:  
   ![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
2. Proporciona el dominio de registro de clics a la API del SDK `setResolveDeepLinkURLs`. Esta API debe llamarse antes de la inicialización del SDK. Para obtener más información, consulta la documentación del SDK <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">aquí</Anchor>.  

   ```objectivec
   [[AppsFlyerLib shared] resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```
3. Cuando se invoca la aplicación debido a un clic en el enlace universal, el SDK de AppsFlyer resuelve el enlace profundo y extrae el OneLink subyacente. A continuación, todos los parámetros de enlace profundo se propagan a la API onAppOpenAttribution para la ejecución de la lógica de enlace profundo.

<div id="step-3-send-emails-with-onelink-through-emaillabs" />

## Paso 3: Envía correos electrónicos con OneLink a través de EmailLabs

1. Crea una URL de OneLink en la página Administración de enlaces (o manualmente). Debes codificar en URL los valores de los parámetros.
2. [Mejores prácticas] Usa los siguientes parámetros:
   * *pid* (fuente de medios): usa una fuente de medios que identifique este uso, como EmailLabs.
   * *c* (campaña): nombre de la campaña
   * *af\_dp*: el esquema de URI de deep link al que quieres dirigir a tus usuarios.
   * *af\_web\_dp:* dónde redirigir a los usuarios que hacen clic en el enlace desde un equipo de escritorio.
   * *af\_ios\_url*: dónde redirigir a los usuarios que no tienen la aplicación y hacen clic en el enlace desde un dispositivo iOS.
   * *af\_android\_url:* dónde redirigir a los usuarios que no tienen la aplicación y hacen clic en el enlace desde un dispositivo Android.
3. Inserta la URL de OneLink en el correo electrónico.  
   Fecha y hora del toque del contributor[n]

   ```html
   <a href="links.example.com data-msys-sublink="appsflyer">¡Enlace a tu aplicación!</a>
   ```
4. Si el correo electrónico forma parte de una campaña de retargeting, añade el parámetro is\_retargeting=true.  
   Esto indica que el enlace de atribución procede de una campaña de retargeting. <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">Más información sobre retargeting</Anchor>.
5. EmailLabs envuelve el enlace con el dominio de clic definido para que un clic en ese dominio redirija al enlace de atribución de OneLink.

> 📘 **Note**
>
> **Ejemplo**
>
> Los parámetros de URL del siguiente ejemplo no están codificados para facilitar la lectura.
>
> ```http
> https://example.onelink.me/abcd?pid=emaillabs&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

<div id="step-4-test-your-links" />

## Paso 4: Prueba tus enlaces

**Para probar la integración:**

1. Configura EmailLabs.
2. Crea una URL de OneLink.
3. Inserta la URL en un correo electrónico.
4. Envíate un correo electrónico de prueba.

**Resultado esperado:**

* Si tienes la aplicación instalada, debería abrirse y te redirigirá mediante enlaces profundos a la página definida de la aplicación.
* Un clic se refleja en:
  * El dashboard de AppsFlyer, atribuido a la fuente de medios y la campaña.
  * Los datos de EmailLabs.

<div data-zendesk-anchors="introduction=introducci%C3%B3n sdk-version-prerequisites=requisitos-previos-de-la-versi%C3%B3n-del-sdk step-1-integration-setup-in-emaillabs=paso-1-configuraci%C3%B3n-de-la-integraci%C3%B3n-en-emaillabs step-2-configuring-your-appsflyer-sdk=paso-2-configuraci%C3%B3n-de-tu-sdk-de-appsflyer step-3-send-emails-with-onelink-through-emaillabs=paso-3-env%C3%ADa-correos-electr%C3%B3nicos-con-onelink-a-trav%C3%A9s-de-emaillabs step-4-test-your-links=paso-4-prueba-tus-enlaces" />
