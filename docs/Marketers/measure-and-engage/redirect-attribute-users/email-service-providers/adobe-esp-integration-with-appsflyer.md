---
title: Integración de Adobe ESP con AppsFlyer
deprecated: false
hidden: false
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-09-23T06:43:55Z'
  edited_at: '2026-09-28T00:19:35Z'
  id: 51170889016977
  locale: es
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/es/articles/51170889016977
---
> **At a glance:** Configura una integración de Adobe ESP con AppsFlyer para habilitar Deep Linking seguro y fluido en tus campañas de correo electrónico, y mejorar el engagement de los usuarios y las tasas de conversión.

<Image align="center" alt="adobe_appsflyer_banner_updated.png" src="https://files.readme.io/95ae69b9b07c2972e03213509fac02516f7ffb300688deb72db5c9aa744e67cf-51180732192401.png" width="1855px" />

<div id="about-the-adobe-esp-integration" />

## Sobre la integración de Adobe ESP

Los marketers a menudo utilizan proveedores de servicios de correo electrónico (ESP) para enviar campañas de correo electrónico a gran escala. Y aunque este debería ser un proceso simple, que entrega viajes de usuario predecibles, a menudo no es así. La razón radica en cómo el ESP típico maneja sus análisis, lo que tiende a romper los deep links y afecta negativamente la experiencia del usuario móvil. Como resultado, a veces los usuarios son dirigidos a sitios web móviles en lugar de a tu aplicación, lo que hace que las conversiones sean menos probables.

AppsFlyer aborda este problema con una solución de integración de ESP, que permite que AppsFlyer actúe como intermediario entre el servidor ESP y tu nombre de dominio. Su función como proxy permite el suministro de archivos de asociación (AASA o enlaces de activos), lo que facilita el deep linking. Además, la solución de AppsFlyer envía datos de medición de vuelta a tu ESP, lo que te permite monitorear tus análisis de correo electrónico de manera efectiva.

Configura una integración de Adobe ESP con AppsFlyer para ofrecer experiencias de deep linking fluidas y seguras en tus campañas de correo electrónico, y lograr un engagement óptimo de los usuarios móviles y mejores tasas de conversión.

La solución de integración de ESP de AppsFlyer es una función premium. Si quieres saber más o empezar, ponte en contacto con nosotros en [hello@appsflyer.com](mailto:hello@appsflyer.com).

<div id="set-up-the-integration" />

## Configura la integración

<span id="h_01J3JHFXRP57VS9D22FEWS2JZW"></span>Esta sección describe cómo configurar tu integración de Adobe ESP con AppsFlyer.

<div id="prerequisites" />

### Prerrequisitos

Antes de empezar a configurar tu integración de Adobe ESP con AppsFlyer, necesitarás tener una cuenta de Adobe. Deberás proporcionar los siguientes elementos:

* Un nuevo **dominio de seguimiento de clics** (descrito en el [Paso 1.](/docs/adobe-esp-integration-with-appsflyer#af-accordion-1))
* El **endpoint del ESP**: el endpoint te lo proporciona el ESP para que puedas dirigir tus clics a sus servidores. Ejemplo de la estructura del endpoint de ESP: esp.endpoint.com.

**Para configurar la integración, sigue estos pasos:**

<Accordion title="Paso 1. Crea un dominio de seguimiento de clics en tu plataforma ESP (tarea de TI / administrador del sistema)">

El dominio de seguimiento de clics (CTD) es el componente de dominio de la URL que aparece en los mensajes de correo electrónico.   
Consiste en un subdominio y tu dominio principal, como mail.yourbrand.com. Distintos ESP pueden referirse a esto como marca de enlace, dominio de rastreo, dominio de clics, reescritura de enlaces, tracking de clics o white labeling.

**Es obligatorio crear un nuevo CTD**, aunque ya estés usando uno existente. Esto garantiza que no haya impacto en el tráfico de las campañas de correo electrónico actualmente activas.

<div id="notes" />

> 📘 **Notas**
>
> * El certificado SSL será manejado por AppsFlyer (en el paso 3.).
> * En esta etapa, los enlaces de correo electrónico probablemente no estarán asegurados, lo que significa que el prefijo de la URL será HTTP en lugar de HTTPS. Esto se resolverá en el [Paso 5.](#h_01JMYDQGPF3B9GNH0RY27JW3E4)).

</Accordion>

<Accordion title="Paso 2. Usa una plantilla de OneLink para tu campaña de correo electrónico">

Crea una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">plantilla de OneLink</Anchor> y configura Universal Links/App Links en "When app is installed". Esta plantilla se utilizará más tarde para crear enlaces de OneLink para tus campañas de correo electrónico.

*Si ya tienes una plantilla de OneLink existente configurada que habilita Universal Links/App Links, puedes usarla.

</Accordion>

<Accordion title="Paso 3. Configura tu integración ESP en AppsFlyer">

Ahora es el momento de configurar tu integración ESP en AppsFlyer. Ten en cuenta que este paso y el siguiente ("[Paso 4. Configura tu app](#h_01J3W0Z1613XPYM75GH65R793W)") se pueden configurar al mismo tiempo.

**Para configurar tu integración ESP en AppsFlyer:**

1. En **AppsFlyer**, en el menú lateral, selecciona **Engage** > **integración de ESP**.

<Image align="center" alt="Selección de integración de ESP en el menú Engage" src="https://files.readme.io/7b731446ce6158d5033020b63be5f386105e7899a8c1b291aa3cb13662a59ee5-27063684942481.png" width="196px" />

2. Selecciona tu ESP (Adobe).

<Image align="center" alt="Selección de tu ESP en la lista" src="https://files.readme.io/526fed3aaf1e6fdbf2404243619159984e298752fdf5913fd3a65cc5a2ed9e1d-27086632495761.png" width="482px" />

3. Selecciona la plantilla de OneLink que quieras usar para campañas de correo electrónico y, después, haz clic en **Siguiente**.

<Image align="center" alt="Seleccionar una plantilla de OneLink para la integración de ESP" src="https://files.readme.io/4f96b999740be8596a424ce9108a8f702bda2a7ed025ec1869c553393432d87d-27086632499729.png" />

4. Asegúrate de tener una cuenta activa con el ESP seleccionado.

Necesitarás lo siguiente de tu ESP:

* El dominio de seguimiento de clics que creaste en el paso 1.
* Endpoint de ESP

Haz clic en **Siguiente**.

5. Introduce tu dominio de tracking de clics y el endpoint del ESP y, después, haz clic en **Validar conexión**. Esto valida que el dominio de seguimiento de clics apunte al endpoint que has registrado.

<Image align="center" alt="Introducir el dominio de tracking de clics y el endpoint del ESP" src="https://files.readme.io/d068b7de020bed7ba979b25e0fe866c40a118b00bbfde06a36a4c097485ac885-27086632503441.png" />

Cuando hayas terminado, haz clic en **Siguiente**.

6. **Enrutar el tráfico de enlace a AppsFlyer:**

a. **Copia y envía las instrucciones pre-fabricadas personalizadas en AppsFlyer a tu administrador de TI o de dominio.** Necesitarán redireccionar el tráfico de tu campaña de correo electrónico desde los servidores ESP a los servidores de AppsFlyer actualizando tus registros CNAME de DNS con el nuevo dominio proporcionado por AppsFlyer.

Como resultado, cada vez que se haga clic en un enlace, el clic será redireccionado a AppsFlyer, que a su vez lo redireccionará al endpoint de ESP.

<Image align="center" alt="Diagrama de un clic redirigido del ESP a AppsFlyer" src="https://files.readme.io/8a53fa7e8e2574246ea6b1344cfec0ac2d8f319bb181f6956ecb6db5b05cd0c5-26982377140369.png" width="374px" />

d. Después de copiar y enviar las instrucciones, haz clic en **Listo**.

Tu integración ESP ha sido creada.

**Ten en cuenta que:**

* El estado de tu integración ESP es pendiente y solo empezará a funcionar una vez que se haya asignado el registro CNAME.
* Una nueva integración puede tardar hasta 24 horas en empezar a funcionar y activarse.

</Accordion>

<Accordion title="Paso 4. Configurar un enlace para cancelar la suscripción">

**Si utilizas un enlace de Cancelar suscripción de Adobe, haz lo siguiente:**

1. Crea *web.`<your domain>`* y configúralo como CNAME del dominio exacto de Adobe que utilizaste para crear el dominio de tracking de clics en el paso 1. Por ejemplo: *click.mydomain* → *yourdomain.cname.campaign.adobe.com*.
2. Realiza también el paso 3 para este dominio: trata este dominio como un CTD y puedes usar la misma plantilla de OneLink que usaste al crear el CTD en el paso 1.

Esto significa que, en la interfaz de usuario de integración de Adobe en AppsFlyer, tendrás 2 CTD.

**Nota:** Esta configuración es necesaria porque en el proceso del enlace para cancelar la suscripción intervienen dos dominios.

Para el **enlace para cancelar la suscripción,** no hace falta realizar pasos adicionales aparte de lo que se menciona aquí.

</Accordion>

<Accordion title="Paso 5. Configura tu aplicación (tarea del desarrollador)">

Haz que tu desarrollador realice las siguientes configuraciones en tu aplicación:

* [Configura tu aplicación para soportar dominios asociados](#configura-tu-aplicación-para-soportar-dominios-asociados)
* [Configura tu aplicación para soportar deep linking](#configura-tu-aplicación-para-soportar-deep-linking)
* [<span id="h_01J3WS4QWMSKZ33APWFR8CG5TZ"></span>Configura tu aplicación para manejar enlaces web y enlaces de aplicación](#configura-tu-aplicación-para-manejar-enlaces-web-y-enlaces-de-aplicación)

<div id="configure-your-app-to-support-associated-domains" />

#### **Configura tu aplicación para soportar dominios asociados**

AppsFlyer aloja archivos de asociación de aplicaciones para que tu aplicación habilite <Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary#enlaces-universales">Universal Links (iOS)</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary#enlace-de-aplicación-de-android">App Links (Android)</Anchor>.

**Para configurar tu aplicación para acceder a los archivos:**

**Para iOS**  
**Requisito previo:** SDK desde la versión <Anchor target="_blank" href="/marketers/es/docs/appsflyer-ios-sdk-release-notes">v6.12.3</Anchor>  
Configura tu aplicación para habilitar Universal Linking desde el mensaje de correo electrónico hasta tu aplicación.  
Saber más sobre cómo configurar <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">Universal Links</Anchor>.  
**Nota:** El dominio de clic debe añadirse a los dominios actuales ya definidos en los dominios asociados.

**Para Android**  
**Requisito previo:** SDK desde la versión <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk">v6.12.5</Anchor>  
Configura tu aplicación para habilitar Android App Linking desde el mensaje de correo electrónico hasta tu aplicación. Saber más sobre cómo configurar Android <Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary#enlace-de-aplicación-de-android">App Links</Anchor>.  
**Nota:** El dominio de clic debe añadirse a los dominios actuales ya definidos en el manifiesto de Android.

<div id="h_01J3WS4QWMRT8KSW6J3QHXM9TQ" />

<div id="configure-your-app-to-support-deep-linking" />

#### **Configura tu aplicación para soportar deep linking**

Cuando se produzca un clic en un App Link o Universal Link, la aplicación debe abrirse.

**Para habilitar la aplicación para extraer el OneLink detrás del dominio de grabación de clic y resolver el deep link:**

1. Proporciona el dominio de grabación de clic a la API SDK resolveDeepLinkURLs. Esta API debe ser llamada antes de la inicialización del SDK.

* Para iOS, sigue estas <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup">instrucciones</Anchor>.
* Para Android, sigue estas <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup#flow-description">instrucciones</Anchor>.

2. Utiliza la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">API unificada de Deep Linking</Anchor> para obtener los parámetros del enlace profundo y gestionar los datos del enlace profundo.

<div id="configure-your-app-to-handle-weblinks-and-application-links" />

#### **Configura tu aplicación para manejar enlaces web y enlaces de aplicación**

El código proporcionado tiene como objetivo regular la funcionalidad de los enlaces envueltos dentro de una campaña de correo electrónico, abordando específicamente dos tipos: enlaces web destinados a abrir un sitio web y enlaces diseñados para abrir la app mediante un enlace universal o un App Link.  
Para más información para desarrolladores, consulta las siguientes guías:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup">Deep linking en iOS con ESP 2.0</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup">Deep linking en Android con ESP 2.0</Anchor>

</Accordion>

<Accordion title="Paso 6. Asegúrate de que el seguimiento de clics SSL esté activado en tu plataforma ESP">

Realiza una prueba de correo electrónico para verificar el estado del enlace.   
Si los enlaces CTD se identifican como HTTP, contacta con el equipo de ESP para habilitar el seguimiento de clics SSL.   
Esto asegurará que todos los enlaces HTTP se conviertan automáticamente a HTTPS.

Puedes utilizar el siguiente mensaje de muestra al contactar con tu ESP:

Hola, equipo:  
¿Podríais habilitar el seguimiento de clics SSL para CTD XXX? Actualmente está configurado en HTTP en lugar de HTTPS.   
Agradecemos su asistencia con esta actualización.

</Accordion>

<Accordion title="Paso 7. Personaliza el enlace OneLink para tu campaña de correo electrónico en AppsFlyer">

**Para crear y personalizar el enlace de OneLink para tu campaña:**

1. En AppsFlyer, crea un enlace de OneLink «Email-to-app» en la página de gestión de OneLink (o manualmente) dentro de la plantilla de OneLink que has creado anteriormente. Este es el enlace que utilizarás en tu campaña de correo electrónico y que atribuirá y redireccionará a los usuarios según tus especificaciones. Aprende a crear un <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">enlace de OneLink</Anchor>.

<Image align="center" alt="Creación de un enlace de OneLink «Email-to-app» en AppsFlyer" src="https://files.readme.io/4e30986e039ed4cc13b9963ef3d1bb7b933061176bed812dced45a7240023d54-27082280943761.png" width="652px" />

**Mejor práctica:** Utiliza el mismo nombre de campaña tanto en la campaña de correo electrónico del ESP como en los enlaces de OneLink de AppsFlyer utilizados en esa campaña.

</Accordion>

<Accordion title="Paso 8. Prueba la integración en tu plataforma ESP">

**Para probar la integración con el enlace de OneLink que has creado:**

Inserta la URL de OneLink en un correo electrónico de prueba que crees y envíalo a ti mismo utilizando el editor de correo electrónico de ESP.

* Desde tu dispositivo móvil, abre el correo electrónico y haz clic en el enlace. Si tienes la aplicación instalada, se abrirá y serás enviado al contenido relevante. Además, un clic móvil debería aparecer en el dashboard de AppsFlyer, atribuido a la fuente de medios y campaña proporcionadas, así como en el dashboard de análisis de tu ESP.
* Haz clic en un enlace web y verifica que redireccione al destino correcto.

Una vez que la prueba sea exitosa, estarás listo.

</Accordion>

<Accordion title="Paso 9. Utiliza el enlace con confianza en tus campañas de correo electrónico">

¡Bien hecho! Ahora estás listo para usar enlaces en tus campañas de correo electrónico. Después, puedes ver los resultados de la campaña en tus dashboards de ESP o AppsFlyer.

</Accordion>

<div id="faq" />

## PREGUNTAS FRECUENTES

<Accordion title="¿Necesito crear un certificado SSL en algún momento?">

No, AppsFlyer crea el certificado SSL por ti.

</Accordion>

<Accordion title="Si tienes la integración de ESP de AppsFlyer y el SDK implementados para el Deep Linking básico de OneLink, ¿necesitas añadir tanto el dominio de OneLink como el dominio de tracking de clics del ESP a Associated Domains de iOS?">

* Sí. Al configurar los enlaces universales/App Links de ESP y OneLink para Deep Linking, debes registrar ambos dominios en la capacidad Associated Domains de tu app:
  * **El dominio de OneLink** – necesario para el Deep Linking estándar con AppsFlyer.
  * **El dominio de tracking de clics del ESP** – necesario para garantizar que los enlaces de correo electrónico impulsados por tu ESP (por ejemplo, Braze, Emarsys) se reconozcan y se les aplique Deep Linking correctamente.
* **¿Quién aloja el archivo AASA para el dominio de tracking de clics?**  
  En esta configuración, AppsFlyer aloja el archivo AASA para el dominio de tracking de clics utilizado en los enlaces de correo electrónico del ESP. Solo tienes que añadir ese dominio a los dominios asociados de tu app, y no necesitas gestionar tú mismo el alojamiento del AASA.

</Accordion>

<div data-zendesk-anchors="overview=sobre-la-integraci%C3%B3n-de-adobe-esp h_01J3JHJCCASM6E5QYJB5VHQ8HK=sobre-la-integraci%C3%B3n-de-adobe-esp set-up-your-esp-integration-with-appsflyer=configura-la-integraci%C3%B3n h_01J3JHFRGA6BTMWSK7EEEVGS6T=configura-la-integraci%C3%B3n prerequisites=prerrequisitos h_01J3JJ74GYF5AJT9R2P2CXDXE1=prerrequisitos h_01JMYJG3CTGE9Y3SBFAECV326G=notas configure-your-app-to-support-associated-domains=configura-tu-aplicaci%C3%B3n-para-soportar-dominios-asociados h_01J3W8XR5QS227XNCD453RWYZ9=configura-tu-aplicaci%C3%B3n-para-soportar-dominios-asociados configure-your-app-to-support-deep-linking=configura-tu-aplicaci%C3%B3n-para-soportar-deep-linking h_01J3W8Y7FMSWPG7MFF6FMSXFM3=configura-tu-aplicaci%C3%B3n-para-soportar-deep-linking configure-your-app-to-handle-weblinks-and-application-links=configura-tu-aplicaci%C3%B3n-para-manejar-enlaces-web-y-enlaces-de-aplicaci%C3%B3n h_01J3W8ZMHSXQGJPQEVR62Q28X9=configura-tu-aplicaci%C3%B3n-para-manejar-enlaces-web-y-enlaces-de-aplicaci%C3%B3n faq=preguntas-frecuentes h_01K3R6V0K31816PVY95X5WZC4C=preguntas-frecuentes" />
