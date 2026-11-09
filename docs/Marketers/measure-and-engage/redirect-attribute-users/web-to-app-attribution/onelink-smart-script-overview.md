---
title: Entendiendo las características de OneLink Smart Script
metadata:
  keywords:
    - OneLink
    - Adwords
    - Advertisers
    - referral
    - referal
    - landing
    - redirect
    - gclid
    - facebook
    - landing page
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2018-12-12T16:32:47Z'
  edited_at: '2026-08-12T12:25:23Z'
  id: 360000677217
  locale: es
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/es/articles/360000677217
---
> **En resumen:** Utiliza OneLink Smart Script para convertir y atribuir a los visitantes de tu sitio web móvil, procedentes de cualquier fuente, en usuarios de la aplicación móvil.

<Image align="center" alt="7901_Smart_Script_flow_1920x1080_2__1_.png" src="https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png" />

<div id="about-onelink-smart-script" />

## Sobre Smart Script de OneLink

Los usuarios llegan a tu sitio web móvil antes de llegar a la página de tu tienda de aplicaciones, ya sea orgánicamente o después de interactuar con campañas publicitarias. Sin embargo, hay dos clics:

* Directo a la página web
* Directo de la página web a la tienda de aplicaciones

En este escenario, la atribución y deep linking generan problemas. Las instalaciones de los usuarios que finalmente descargan la aplicación podrían atribuirse erróneamente o como orgánicas. Esto puede ocurrir incluso si el primer clic procede de una ad network, un clic de Google o una fuente de medios propia.

Smart Script de OneLink resuelve estos problemas de la siguiente manera:

* Utiliza las URLs entrantes que llevan a la página web para generar dinámicamente URLs largas de salida de OneLink únicas que llevan a la tienda de aplicaciones.
* Proporciona una atribución web-to-app precisa para todas las fuentes de medios, incluidas ad networks, SRNs, clics de Google y medios propios.
* Puede utilizarse para deep linking.
* Se ejecuta sin problemas en cualquier página web o landing page.
* No requiere el uso de Smart Banners.   
  **Nota**: Los Smart Banners pueden ser una gran herramienta de conversión para muchas verticales y no requieren un desarrollador para su instalación, pero añaden otro paso, el banner, al viaje del usuario.
* El marketer puede configurarlo en Google Tag Manager.

Hay dos versiones de Smart Script de OneLink:

<Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors">**OneLink Smart Script V2 (recomendado)**</Anchor>: Si estás configurando OneLink Smart Script por primera vez, esta es la versión preferida. Se puede configurar en la interfaz de usuario de AppsFlyer, la parte de trabajo del desarrollador es más sencilla, y también se puede configurar mediante Google Tag Manager.

<Anchor target="_blank" href="/marketers/es/docs/legacy-onelink-smart-script-v1-setup">**OneLink Smart Script V1 (antigua)**</Anchor>: Si ya tienes configurado Onelink Smart Script, utiliza la documentación de esta versión para mantener y editar este script. **Nota**: Aunque no es obligatorio, considera la posibilidad de migrar a la V2. 

<div id="note" />

> 📘 **Nota:**
>
> ¿No estás seguro de si Smart Script de OneLink es la solución adecuada para ti? ¿No estás seguro de si Smart Script de OneLink es la solución adecuada para ti? <Anchor target="_blank" href="/marketers/es/docs/convert-your-mobile-web-visitors-to-app-users">Compara</Anchor> Smart Script de OneLink con otras soluciones web-to-app de AppsFlyer.

<div id="examples" />

### Ejemplos

Los ejemplos de esta sección demuestran cómo se utiliza el Smart Script de OneLink para generar URLs de salida de OneLink que proporcionan una atribución precisa o funcionalidad de deep linking. Para ver casos de uso de tipos de campaña con fuentes de medios concretas, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#casos-de-uso">Casos de uso</Anchor>.

<div id="attribution" />

<Accordion title="Atribución">

Mark es el responsable de marketing de una cadena hotelera. Envía un correo electrónico anunciando unas vacaciones en un hotel de Orlando (Florida). El enlace del correo electrónico es el siguiente: https://hotel.me/pid=email&c=orlando

El enlace envía a los usuarios a la web móvil del hotel. Allí, los usuarios ven botones que los invitan a descargar la aplicación móvil del hotel. El Smart Script de OneLink genera automáticamente una URL que contiene los mismos parámetros **pid** y **c** que el enlace original del correo electrónico. El enlace es el siguiente: https://hotel.onelink.me/Ac4G?pid=email&c=orlando

Cuando los usuarios hacen clic en los botones del sitio móvil para descargar la aplicación, la instalación de la misma se atribuye a la campaña de correo electrónico de Mark sobre el hotel de Orlando.

</Accordion>

<div id="deep-linking" />

<Accordion title="Enlaces profundos">

Emma recibe un correo electrónico en el que se anuncian unas vacaciones en un hotel de Orlando (Florida).

El enlace del correo electrónico es el siguiente: https://hotel.me?type=email&campaign=Florida&city=orlando

Cuando hace clic en el enlace, se la envía al sitio web móvil del hotel. Allí, ve botones que la invitan a descargar la aplicación móvil del hotel. El Smart Script de OneLink genera automáticamente una URL que contiene los mismos parámetros **pid** y **c** que el enlace original del correo electrónico. El enlace es el siguiente: https://hotel.onelink.me/Ac4G?pid=email&c=Florida&deep_link_value=orlando

**Cuando Emma pulsa los botones del sitio web móvil, es redireccionada a la tienda de aplicaciones. Y cuando descarga e inicia la aplicación, se encuentra con la página de vacaciones de Orlando en la aplicación.**

<div id="note-1" />

> 📘 **Nota:**
>
> Deep linking está de acuerdo con la configuración de la aplicación implementada por los desarrolladores de la aplicación. <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">Saber más</Anchor>.

</Accordion>

<div data-zendesk-anchors="about-onelink-smart-script=sobre-smart-script-de-onelink h_01HE7RW9G26CNME9TP350GFGS4=sobre-smart-script-de-onelink h_01HE7RW9G2BV2NFJ0YZ9QKAA2V=nota examples=ejemplos h_01HE7RW9G2WBZ1A0RS66CJ7BNH=ejemplos h_01HE7RW9G24Y604NTZFGKJJXSS=attribution h_01HE7RW9G2ZDDWE1M1B2G175ZF=deep-linking h_01HE7RW9G3W5GKQ2CD2BZW8YAW=nota-1" />
