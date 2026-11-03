---
title: '[Beta cerrada - acceso especial] Configura tu integración de ESP con AppsFlyer'
metadata:
  keywords:
    - Premium
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2024-07-24T14:10:54Z'
  edited_at: '2026-08-12T12:24:48Z'
  id: 26967438815377
  locale: es
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/es/articles/26967438815377
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** Configura una integración de ESP con AppsFlyer para habilitar deep linking seguros y sin problemas en tus campañas de correo electrónico para un mejor engagement de usuarios y tasas de conversión.

## <Image alt="ESP final main KB image.png" src="https://files.readme.io/f14a193bb8d303adb93c01b33dcafba9053359fd92a187378cd324544a94dc88-27434531852049.png" width="613px" />

## Sobre la integración de ESP de AppsFlyer

Los marketers a menudo utilizan proveedores de servicios de correo electrónico (ESP) para enviar campañas de correo electrónico a gran escala. Y aunque este debería ser un proceso simple, que entrega viajes de usuario predecibles, a menudo no es así. La razón radica en cómo el ESP típico maneja sus análisis, lo que tiende a romper los deep links y afecta negativamente la experiencia del usuario móvil. Como resultado, a veces los usuarios son dirigidos a sitios web móviles en lugar de a tu aplicación, lo que hace que las conversiones sean menos probables.

AppsFlyer aborda este problema con una solución de integración de ESP, que permite que AppsFlyer actúe como intermediario entre el servidor ESP y tu nombre de dominio. Su función como proxy permite el suministro de archivos de asociación (AASA o enlaces de activos), lo que facilita el deep linking. Además, la solución de AppsFlyer envía datos de medición de vuelta a tu ESP, lo que te permite monitorear tus análisis de correo electrónico de manera efectiva.

Configura una integración de ESP con AppsFlyer para experiencias de deep linking seguras en tus campañas de correo electrónico, para un engagement óptimo de usuarios móviles y tasas de conversión.

La solución de integración ESP de AppsFlyer es una funcionalidad premium. Si quieres saber más o empezar, ponte en contacto con nosotros en [hello@appsflyer.com](mailto:hello@appsflyer.com).

## Configura la integración

<span id="h_01J3JHFXRP57VS9D22FEWS2JZW"></span>Esta sección describe cómo configurar tu integración de ESP con AppsFlyer.

### Requisitos previos

Antes de comenzar a configurar tu integración de ESP con AppsFlyer, necesitarás tener una cuenta con un ESP compatible*. Deberás proporcionar los siguientes elementos:

* Un nuevo **dominio de seguimiento de clics** (descrito en [Paso 1.](#step-1-create-a-onelink-template-for-your-email-campaign))
* El **endpoint de ESP**: El endpoint te lo proporciona el ESP para que puedas dirigir tus clics a sus servidores. Ejemplo de la estructura del endpoint de ESP: esp.endpoint.com.
* **Requisitos específicos de integración de ESP:**
  * **Emarsys** - Pide a tu Customer Success Manager de Emarsys que habilite la redirección HTTP.
  * **Blueshift** - Pide a tu Customer Success Manager de Blueshift que  
    cambie el código de respuesta HTTP para clics a 302 (desde el predeterminado 307).

**Para configurar la integración, sigue estos pasos:**

<div id="step-1-create-a-onelink-template-for-your-email-campaign" />

<Accordion title="Paso 1. Crea un dominio de seguimiento de clics en tu plataforma ESP (tarea de TI / administrador del sistema)">

El dominio de seguimiento de clics (CTD) es el componente de dominio de la URL que aparece en los mensajes de correo electrónico.   
Consiste en un subdominio y tu dominio principal, como mail.yourbrand.com. Diferentes ESPs pueden referirse a esto como marca de enlace, dominio de rastreo, dominio de clics, reescritura de enlaces, seguimiento de clics o etiquetado blanco. Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.

**Crear un nuevo CTD es obligatorio**, incluso si ya estás utilizando uno existente. Esto garantiza que no haya impacto en el tráfico de las campañas de correo electrónico actualmente activas.

> 📘 **Notas**
>
> * El certificado SSL será manejado por AppsFlyer (en el paso 3.).
> * En esta etapa, los enlaces de correo electrónico probablemente no estarán asegurados, lo que significa que el prefijo de la URL será HTTP en lugar de HTTPS. Esto se resolverá en el [Paso 5.](#h_01JMYDQGPF3B9GNH0RY27JW3E4)).

</Accordion>

<div id="h_01JMYD02VRGT8353RDBARRPJ2M" />

<Accordion title="Paso 2. Usa una plantilla de OneLink para tu campaña de correo electrónico">

Crea una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">plantilla de OneLink</Anchor> y configura Universal Links/App Links bajo "**Cuando la aplicación está instalada**". Esta plantilla se utilizará más tarde para crear enlaces de OneLink para tus campañas de correo electrónico.

*Si ya tienes una plantilla de OneLink existente configurada que habilita Universal Links/App Links, puedes usarla.

</Accordion>

<div id="step-3-set-your-esp-integration-in-appsflyer" />

<Accordion title="Paso 3. Configura tu integración ESP en AppsFlyer">

Ahora es el momento de configurar tu integración ESP en AppsFlyer. Ten en cuenta que este paso y el siguiente ("[Paso 4. Configura tu aplicación](#step-2-configure-your-app-developer-task)") se pueden configurar al mismo tiempo.

**Para configurar tu integración ESP en AppsFlyer:**

1. En **AppsFlyer**, desde el menú lateral, selecciona **Engage** > **integración ESP**.

<Image alt="From Engage click ESP integration.png" src="https://files.readme.io/7b731446ce6158d5033020b63be5f386105e7899a8c1b291aa3cb13662a59ee5-27063684942481.png" width="196px" />

2. Selecciona tu ESP.

<Image alt="select ESP.png" src="https://files.readme.io/526fed3aaf1e6fdbf2404243619159984e298752fdf5913fd3a65cc5a2ed9e1d-27086632495761.png" width="482px" />

3. Selecciona la plantilla OneLink que deseas usar para campañas de correo electrónico, luego haz clic en **Siguiente**.

![select OneLink template.png](https://files.readme.io/4f96b999740be8596a424ce9108a8f702bda2a7ed025ec1869c553393432d87d-27086632499729.png)

4. Asegúrate de tener una cuenta activa con el ESP seleccionado.

Necesitarás lo siguiente de tu ESP:

* El dominio de seguimiento de clics que creaste en el paso 1.
* Endpoint de ESP

Haz clic en **Siguiente**.

5. Ingresa tu dominio de seguimiento de clics y el endpoint de ESP, luego haz clic en **Validar conexión**. Esto valida que el dominio de seguimiento de clics apunte al endpoint que has registrado.

![enter your ctd and esp endpoint.png](https://files.readme.io/d068b7de020bed7ba979b25e0fe866c40a118b00bbfde06a36a4c097485ac885-27086632503441.png)

Cuando hayas terminado, haz clic en **Siguiente**.

6. **Enrutar el tráfico de enlace a AppsFlyer:**

a. **Copia y envía las instrucciones pre-fabricadas personalizadas en AppsFlyer a tu administrador de TI o de dominio.** Necesitarán redireccionar el tráfico de tu campaña de correo electrónico desde los servidores ESP a los servidores de AppsFlyer actualizando tus registros CNAME de DNS con el nuevo dominio proporcionado por AppsFlyer.

Como resultado, cada vez que se haga clic en un enlace, el clic será redireccionado a AppsFlyer, que a su vez lo redireccionará al endpoint de ESP.

<Image alt="click to Af to ESP image.png" src="https://files.readme.io/8a53fa7e8e2574246ea6b1344cfec0ac2d8f319bb181f6956ecb6db5b05cd0c5-26982377140369.png" width="374px" />

d. Después de copiar y enviar las instrucciones, haz clic en **Listo**.

Tu integración ESP ha sido creada.

**Ten en cuenta que:**

* El estado de tu integración ESP es pendiente y solo empezará a funcionar una vez que se haya asignado el registro CNAME.
* Una nueva integración puede tardar hasta 24 horas en empezar a funcionar y activarse.

</Accordion>

<div id="step-2-configure-your-app-developer-task" />

<Accordion title="Paso 4. Configura tu aplicación (tarea del desarrollador)">

Haz que tu desarrollador realice las siguientes configuraciones en tu aplicación:

* [Configura tu aplicación para soportar dominios asociados](#configura-tu-aplicación-para-soportar-dominios-asociados)
* [Configura tu aplicación para soportar deep linking](#configura-tu-aplicación-para-soportar-deep-linking)
* [Configura tu aplicación para manejar enlaces web y enlaces de aplicación](#configura-tu-aplicación-para-manejar-enlaces-web-y-enlaces-de-aplicación)

#### **Configura tu aplicación para soportar dominios asociados**

AppsFlyer aloja archivos de asociación de aplicaciones para que tu aplicación habilite <Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary#enlaces-universales">Universal Links (iOS)</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary#enlace-de-aplicación-de-android">App Links (Android)</Anchor>.

**Para configurar tu aplicación para acceder a los archivos:**

**Para iOS**  
**Requisito previo:** SDK <Anchor target="_blank" href="/marketers/es/docs/appsflyer-ios-sdk-release-notes">v6.12.3</Anchor>  
Configura tu aplicación para habilitar el Universal Link desde el mensaje de correo electrónico a tu aplicación.  
Saber más sobre cómo configurar <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">Universal Links</Anchor>.  
**Nota:** El dominio de clic debe ser añadido a los dominios actuales ya definidos en los dominios asociados.

**Para Android**  
**Requisito previo:** SDK <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk">v6.12.5</Anchor>  
Configura tu aplicación para habilitar App Links de Android desde el mensaje de correo electrónico a tu aplicación. Saber más sobre cómo configurar <Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary#enlaces-universales">App Links</Anchor> de Android.  
**Nota:** El dominio de clic debe ser añadido a los dominios actuales ya definidos en el Android Manifest.


#### **Configura tu aplicación para soportar deep linking**

Cuando se produzca un clic en un App Link o Universal Link, la aplicación debe abrirse.

**Para habilitar la aplicación para extraer el OneLink detrás del dominio de grabación de clic y resolver el deep link:**

1. Proporciona el dominio de grabación de clic a la API SDK resolveDeepLinkURLs. Esta API debe ser llamada antes de la inicialización del SDK.

* Para iOS, por favor sigue estas <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup">instrucciones</Anchor>.
* Para Android, sigue estas <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup#flow-description">instrucciones</Anchor>.

2. Utiliza la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">API Unificada de DeepLinking</Anchor> para obtener los parámetros del deep link y manejar los datos del deep link.


#### **Configura tu aplicación para manejar enlaces web y enlaces de aplicación**

El código proporcionado tiene como objetivo regular la funcionalidad de los enlaces envueltos dentro de una campaña de correo electrónico, abordando específicamente dos tipos: Enlaces web destinados a abrir un sitio web y enlaces diseñados para abrir la aplicación a través de un Universal Link o App Link.  
Para más información para desarrolladores, consulta las siguientes guías:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup">Deep linking en iOS con ESP 2.0</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup">Deep linking en Android con ESP 2.0</Anchor>

</Accordion>

<div id="h_01JMYDQGPF3B9GNH0RY27JW3E4" />

<Accordion title="Paso 5. Asegúrate de que el seguimiento de clics SSL esté activado en tu plataforma ESP">

Realiza una prueba de correo electrónico para verificar el estado del enlace.   
Si los enlaces CTD se identifican como HTTP, contacta con el equipo de ESP para habilitar el seguimiento de clics SSL.   
Esto asegurará que todos los enlaces HTTP se conviertan automáticamente a HTTPS.

Puedes utilizar el siguiente mensaje de muestra al contactar con tu ESP:

Hola equipo,  
¿Podrían habilitar el seguimiento de clics SSL para CTD XXX? Actualmente está configurado en HTTP en lugar de HTTPS.   
Agradecemos su asistencia con esta actualización.

</Accordion>

<div id="step-4-customize-the-onelink-link-for-your-email-campaign" />

<Accordion title="Paso 6. Personaliza el enlace OneLink para tu campaña de correo electrónico en AppsFlyer">

**Para crear y personalizar el enlace de OneLink para tu campaña:**

1. En AppsFlyer, crea un enlace de OneLink "Email-to-app" en la página de gestión de OneLink (o manualmente) dentro de la plantilla de OneLink que has creado anteriormente. Este es el enlace que utilizarás en tu campaña de correo electrónico que atribuirá y redireccionará a los usuarios según tus especificaciones. Aprende a crear un <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">enlace de OneLink</Anchor>.

<Image alt="email-to-app.png" src="https://files.readme.io/4e30986e039ed4cc13b9963ef3d1bb7b933061176bed812dced45a7240023d54-27082280943761.png" width="652px" />

**Mejores prácticas:** Utiliza el mismo nombre de campaña tanto en la campaña de correo electrónico de ESP como en los enlaces de OneLink de AppsFlyer utilizados en esa campaña.

</Accordion>

<div id="step-5-test-the-link" />

<Accordion title="Paso 7. Prueba la integración en tu plataforma ESP">

**Para probar la integración con el enlace de OneLink que has creado:**

Inserta la URL de OneLink en un correo electrónico de prueba que crees y envíalo a ti mismo utilizando el editor de correo electrónico de ESP.

* Desde tu dispositivo móvil, abre el correo electrónico y haz clic en el enlace. Si tienes la aplicación instalada, se abrirá y serás enviado al contenido relevante. Además, un clic móvil debería aparecer en el dashboard de AppsFlyer, atribuido a la fuente de medios y campaña proporcionadas, así como en el dashboard de análisis de tu ESP.
* Haz clic en un enlace web y verifica que redireccione al destino correcto.

Una vez que la prueba sea exitosa, estarás listo.

</Accordion>

<div id="step-6-use-the-link-in-your-email-campaigns-then-measure-the-results-use-the-link-confidently-in-your-email-campaigns" />

<Accordion title="Paso 8. Utiliza el enlace con confianza en tus campañas de correo electrónico">

¡Bien hecho! Ahora estás listo para usar enlaces en tus campañas de correo electrónico. Después, puedes ver los resultados de la campaña en tus dashboards de ESP o AppsFlyer.

</Accordion>

*Los ESPs compatibles con esta integración incluyen: Blueshift, Braze, CleverTap, Customer.io, Emarsys, Expert Sender, Klaviyo, MailExpress, MailGun, Moengage, RDStation, Reteno, Sailthru, Sendgrid, Sparkpost, y más. Consulta la <Anchor target="_blank" href="/marketers/es/docs/email-service-provider-esp-integration-guide">lista</Anchor> completa.

## Preguntas frecuentes

<div id="do-i-need-to-create-an-ssl-certificate-at-any-point" />

<Accordion title="¿Tengo que crear un certificado SSL en algún momento?">

No, AppsFlyer crea el certificado SSL por ti.

</Accordion>

<div id="if-i-have-the-appsflyer-esp-integration-and-sdk-implemented-for-basic-onelink-deep-linking-do-i-need-to-add-both-the-onelink-domain-and-the-esp-click-tracking-domain-to-ios-associated-domains" />

<Accordion title="Si tengo la integración ESP de AppsFlyer y el SDK implementado para Deep Linking básico de OneLink, ¿tengo que añadir tanto el dominio de OneLink como el dominio de tracking de clics del ESP a los Associated Domains de iOS?">

* Sí. Al configurar los enlaces universales/App Links de ESP y OneLink para Deep Linking, debes registrar ambos dominios en el entitlement de Associated Domains de tu app:
  * **El dominio de OneLink** – necesario para el Deep Linking estándar con AppsFlyer.
  * **El dominio de tracking de clics del ESP** – necesario para garantizar que los enlaces de correo electrónico impulsados por tu ESP (por ejemplo, Braze, Emarsys) se reconozcan y se apliquen correctamente mediante Deep Linking.
* **¿Quién aloja el archivo AASA del dominio de tracking de clics?**  
  En esta configuración, AppsFlyer aloja el archivo AASA del dominio de tracking de clics que se usa en los enlaces de correo electrónico del ESP. Solo tienes que añadir ese dominio a los dominios asociados de tu app, y no necesitas gestionar tú mismo el alojamiento del archivo AASA.

</Accordion>

<div data-zendesk-anchors="overview=sobre-la-integraci%C3%B3n-de-esp-de-appsflyer h_01J6RXTXCS7WC0P5X4J96T8JAP=sobre-la-integraci%C3%B3n-de-esp-de-appsflyer h_01J3JHJCCASM6E5QYJB5VHQ8HK=sobre-la-integraci%C3%B3n-de-esp-de-appsflyer set-up-your-esp-integration-with-appsflyer=configura-la-integraci%C3%B3n h_01J3JHFRGA6BTMWSK7EEEVGS6T=configura-la-integraci%C3%B3n prerequisites=requisitos-previos h_01J3JJ74GYF5AJT9R2P2CXDXE1=requisitos-previos h_01J3W0Z161XE7BKMMR62SEEZN7=step-1-create-a-onelink-template-for-your-email-campaign h_01JMYJG3CTGE9Y3SBFAECV326G=notas h_01J3W0Z161T0D075HPE3Y8H3J4=step-3-set-your-esp-integration-in-appsflyer h_01J3W0Z1613XPYM75GH65R793W=step-2-configure-your-app-developer-task configure-your-app-to-support-associated-domains=configura-tu-aplicaci%C3%B3n-para-soportar-dominios-asociados h_01J3W8XR5QS227XNCD453RWYZ9=configura-tu-aplicaci%C3%B3n-para-soportar-dominios-asociados configure-your-app-to-support-deep-linking=configura-tu-aplicaci%C3%B3n-para-soportar-deep-linking h_01J3WS4QWMRT8KSW6J3QHXM9TQ=configura-tu-aplicaci%C3%B3n-para-soportar-deep-linking h_01J3W8Y7FMSWPG7MFF6FMSXFM3=configura-tu-aplicaci%C3%B3n-para-soportar-deep-linking ::250c928e=configura-tu-aplicaci%C3%B3n-para-manejar-enlaces-web-y-enlaces-de-aplicaci%C3%B3n configure-your-app-to-handle-weblinks-and-application-links=configura-tu-aplicaci%C3%B3n-para-manejar-enlaces-web-y-enlaces-de-aplicaci%C3%B3n h_01J3WS4QWMSKZ33APWFR8CG5TZ=configura-tu-aplicaci%C3%B3n-para-manejar-enlaces-web-y-enlaces-de-aplicaci%C3%B3n h_01J3W8ZMHSXQGJPQEVR62Q28X9=configura-tu-aplicaci%C3%B3n-para-manejar-enlaces-web-y-enlaces-de-aplicaci%C3%B3n h_01J3W0Z1616GFFYCS7WPTNCCHT=step-4-customize-the-onelink-link-for-your-email-campaign h_01J3W0Z161M9NDXAN0KZFA9J4G=step-5-test-the-link h_01J3W0Z161RAYTKH3V9VBAADBM=step-6-use-the-link-in-your-email-campaigns-then-measure-the-results-use-the-link-confidently-in-your-email-campaigns faq=preguntas-frecuentes h_01K3R6V0K31816PVY95X5WZC4C=preguntas-frecuentes h_01K3R6THWT2MCCJHPSXPBAVT8Y=do-i-need-to-create-an-ssl-certificate-at-any-point h_01K3R6THWTG8G8PWPZ2ZRA1CSA=if-i-have-the-appsflyer-esp-integration-and-sdk-implemented-for-basic-onelink-deep-linking-do-i-need-to-add-both-the-onelink-domain-and-the-esp-click-tracking-domain-to-ios-associated-domains" />
