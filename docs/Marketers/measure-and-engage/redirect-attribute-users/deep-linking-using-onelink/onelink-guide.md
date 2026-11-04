---
title: Guía de OneLink
metadata:
  keywords:
    - Marketers
    - start
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2017-10-19T08:53:16Z'
  edited_at: '2026-08-12T12:24:09Z'
  id: 115005248543
  locale: es
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/es/articles/115005248543
---
> **En resumen:** Crear enlaces con capacidades de atribución, redirección y deep linking que convierten a los usuarios de medios propios o pagos en usuarios de la aplicación, independientemente del dispositivo, sistema operativo, canal o plataforma. Estos enlaces te ayudan a proporcionar la mejor experiencia a tus usuarios, sin importar desde cuál de tus fuentes de medios propias realicen la conversión: sitios web, banners, publicaciones en redes sociales, correos electrónicos, textos y más.

<div id="introduction-video" />

## Video de introducción

<Embed title="Guía de OneLink" typeOfEmbed="youtube" url="https://www.youtube.com/embed/golT4p9D8MA" providerUrl="https://www.youtube.com" />

<div id="benefits" />

## Ventajas

El paquete de experiencia del cliente y deep linking de AppsFlyer impulsado por OneLink te permite crear enlaces para medir campañas de marketing móvil en todos los canales principales. Los enlaces que creas te permiten:

* Interactuar con tus clientes en distintos puntos de contacto online y offline.
* Aumentar las conversiones proporcionando a los usuarios las mejores experiencias contextuales desde cualquier punto de contacto; desde el clic hasta la instalación de la aplicación.
* Obtener una atribución y mediciones precisas con respecto a los resultados de tu campaña.
* Enviar nuevos usuarios sin tu aplicación a la tienda de aplicaciones o URL web correcta, independientemente del dispositivo, sistema operativo, canal o plataforma.
* Enviar a los usuarios existentes con tu aplicación instalada directamente a la aplicación (usando enlaces de aplicaciones, enlaces universales y esquemas URI).
* Enlazar a los usuarios a páginas o experiencias específicas in-app.

Las funciones de OneLink están disponibles a través de <Anchor target="_blank" href="/marketers/es/docs/account-management-plans-payments-and-billing#appsflyer-plans">los planes de suscripción de AppsFlyer</Anchor>. Para que tus experiencias de OneLink sigan en funcionamiento sin problemas, asegúrate de que tu plan siga activo.

<div id="experiences" />

## Experiencias

El paquete de experiencia del cliente y deep linking de AppsFlyer con tecnología OneLink te permite crear enlaces que proporcionen una experiencia óptima a tus usuarios, independientemente de su procedencia. Las experiencias del cliente que puedes configurar incluyen:

* **Social-to-app**: Interactúa con tus usuarios en redes sociales y envíalos desde los feeds de redes sociales a tu aplicación.
* **De aplicación a aplicación**: Lleva a los usuarios a tu aplicación desde otras aplicaciones.
* <Anchor target="_blank" href="/marketers/es/docs/convert-your-mobile-web-visitors-to-app-users">**De la web a la aplicación**</Anchor>: Convierte a los visitantes de tu sitio web móvil en nuevos usuarios de la aplicación móvil utilizando Smart Banners y Smart Script.
* **De QR a aplicación**: Utiliza códigos QR para impulsar las instalaciones de aplicaciones haciendo que los usuarios escanéen un código QR en puntos clave durante su experiencia de cliente fuera de línea. También puedes colocar códigos QR en tu sitio de escritorio o en anuncios de TV y CTV para dirigir a los usuarios a tu aplicación.
* **De correo electrónico a aplicación**: Utiliza proveedores de servicios de correo electrónico (ESP) para interactuar con los usuarios mediante correo electrónico y envíalos desde su bandeja de entrada a tu aplicación.
* **De texto a aplicación**: Crea enlaces para tus campañas de SMS y mensajería e interactúa con los usuarios a través de mensajes de texto.
* **De referencia a aplicación**: Crea enlaces de invitación que permiten a usuarios e influencers invitar a otros a tu aplicación o compartir contenido específico dentro de la aplicación, como un artículo.
* Personalizado: No importa de dónde provengan tus usuarios, ya sea a través de ordenadores o dispositivos móviles, online y offline, medios propios o de pago, utiliza OneLink para enviar fácilmente a tus usuarios al lugar correcto.

<div id="setting-up-onelink" />

## Configuración de OneLink

Para proporcionar a tus usuarios la experiencia de cliente deseada desde el enlace hasta la instalación de la aplicación a través de la interfaz de usuario de AppsFlyer, se requiere lo siguiente:

* Dos roles diferentes dentro de una organización (marketers y desarrolladores) trabajando juntos.
* <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">Crear una plantilla de OneLink</Anchor> que represente la lógica de enrutamiento en el núcleo de todos tus enlaces, para redirigir a:
  * Nuevos usuarios sin tu aplicación instalada a la tienda de aplicaciones correcta o a la URL web.
  * Usuarios existentes con tu aplicación instalada en la aplicación a través de enlaces de aplicaciones de Android, enlaces universales de iOS y esquema URI.

    * Si estos no están definidos, los usuarios tendrán la misma configuración predeterminada que los nuevos usuarios sin tu aplicación instalada (URL web o tienda de aplicaciones).

    **Nota**: Una plantilla de OneLink no es un enlace donde se puede hacer clic; es la base para generar muchos enlaces personalizados. En función de la plantilla, puedes crear muchos enlaces personalizados de OneLink para que los usuarios hagan clic. Es raro necesitar más de una o dos plantillas de OneLink durante la vida útil de una aplicación (sin contar con las pruebas).
* <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Crear un enlace OneLink</Anchor>. <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Creando un enlace OneLink</Anchor> Se trata del enlace clicable o del QR code escaneable que aparece en tus anuncios. Durante la configuración del enlace, puedes definir la experiencia del cliente deseada y agregar los parámetros deseados.

La siguiente tabla describe los detalles de las tareas del marketer y del desarrollador y proporciona enlaces a sus recursos.

| Tarea | Detalles | Recursos |
| --- | --- | --- |
| Crear plantilla de OneLink | <ul><li>El marketer/gerente de producto configura la plantilla en AppsFlyer.</li><li>El desarrollador de Android configura los métodos de apertura de la aplicación para los usuarios existentes (Android App Link y esquema URI).</li><li>El desarrollador de iOS configura los métodos de apertura de aplicaciones para los usuarios existentes (iOS Universal Links y esquema URI).</li></ul> | <ul><li>Dashboard de AppsFlyer</li><li><Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">Instrucciones para el marketer</Anchor></li><li>Instrucciones para desarrolladores de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#app-opening-methods">Android</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup">iOS</Anchor></li></ul> |
| Crear enlace de OneLink | <ul><li>El marketer/gerente de producto configura el enlace en AppsFlyer, incluida la selección de la experiencia del cliente deseada y agregando cualquier atribución deseada o parámetros de deep linking.</li><li>Los desarrolladores de Android e iOS implementan el método UDL para deep linking (si se requieren).</li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Instrucciones para el marketer</Anchor></li><li>Instrucciones para desarrolladores de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_unified_deep_linking">Android</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_unified_deep_linking">iOS</Anchor></li><li>Aplicaciones de muestra (Github)</li></ul> |

<div id="additional-options" />

## Opciones adicionales

Después de completar una parte o la totalidad de la configuración en la interfaz de usuario, considera la posibilidad de implementar las funciones adicionales que se describen a continuación.

* <Anchor target="_blank" href="/marketers/es/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API de OneLink</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/perform-onelink-bulk-actions-via-csv">creación de enlaces masivos</Anchor>: Escala y ejecuta múltiples campañas a la vez, y crea miles de enlaces OneLink de manera rápida y sencilla, ahorrándote tiempo y esfuerzo, y permitiéndote concentrarte en tu campaña y esfuerzos de marketing.
* <Anchor target="_blank" href="/marketers/es/docs/export-onelink-urls">Exportar URL de OneLink</Anchor>: Descarga todas las URLs de OneLink creadas en la interfaz de usuario de AppsFlyer (las URL de OneLink creadas a través de SDK, API de OneLink o carga masiva no están incluidas).
* <Anchor target="_blank" href="/marketers/es/docs/measuring-push-notification-re-engagement-campaigns">Medir las campañas de re-engagement mediante push notifications</Anchor>: Utilice notificaciones push con OneLink para medir la reactivación de los usuarios móviles.
* <Anchor target="_blank" href="/marketers/es/docs/cross-promotion-attribution-for-marketers">Atribución de promoción cruzada</Anchor>: Los usuarios de tu aplicación existente son excelentes candidatos para instalar tus otras aplicaciones nuevas. Aprende a usar los métodos del SDK para crear y medir fácilmente las campañas de promoción cruzada.
* <Anchor target="_blank" href="/marketers/es/docs/understand-onelink-short-vs-long-urls">URLs largas</Anchor>: Agrega parámetros a tus enlaces personalizados de OneLink o genera una gran cantidad de enlaces personalizados de OneLink aplicando tus propias fórmulas simples en una hoja de cálculo.
* <Anchor target="_blank" href="/marketers/es/docs/redirect-app-users-to-a-website">Redirección app-to-web</Anchor>: Redirecciona a los usuarios desde tu aplicación a un sitio web o página de redes sociales.

<div id="troubleshooting-and-faq" />

## Resolución de problemas y preguntas frecuentes

Encuentra rápidamente soluciones para probar y depurar problemas de comportamiento y redirección de enlaces personalizados de OneLink con nuestra <Anchor target="_blank" href="/marketers/es/docs/onelink-troubleshooting-and-faq">guía de resolución de problemas de OneLink</Anchor>.

<div id="limitations" />

## Limitaciones

* OneLink no es compatible con el objetivo de instalación de aplicaciones móviles de Meta, donde solo se aceptan los Meta App Links.
* Si tu plan de suscripción pagado caduca, algunos enlaces y funciones de OneLink dejarán de estar disponibles. Esto puede afectar a los enlaces de ESP y de dominios de marca, desactivar la creación de enlaces y las solicitudes de SDK y API (a menos que se hayan adquirido por separado) y revocar el acceso a Web-to-app y a la creación masiva de enlaces.

<div data-zendesk-anchors="introduction-video=video-de-introducci%C3%B3n h_01HGE1D5JZ4Y603BD55W2P7DPW=video-de-introducci%C3%B3n benefits=ventajas h_01HGE1D5JZJGY8BZX8ZTSXQ635=ventajas experiences=experiencias h_01HGE1D5JZV65E9YWG424HYRNW=experiencias setup=configuraci%C3%B3n-de-onelink h_01HGE1D5K0RKHHV9SVH4VREMXQ=configuraci%C3%B3n-de-onelink additional-options=opciones-adicionales h_01HGE1D5K2VCKYJY3Y8MKYVT2V=opciones-adicionales troubleshooting-and-faq=resoluci%C3%B3n-de-problemas-y-preguntas-frecuentes h_01HGE1D5K24FG3F8G54DYTK599=resoluci%C3%B3n-de-problemas-y-preguntas-frecuentes limitations=limitaciones h_01HGE1D5K2M0VMJPMP4EJ0QGPY=limitaciones" />
