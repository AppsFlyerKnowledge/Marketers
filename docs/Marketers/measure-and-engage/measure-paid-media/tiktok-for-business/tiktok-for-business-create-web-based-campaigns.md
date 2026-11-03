---
title: TikTok for Business—Crea campañas basadas en la web
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2025-10-31T12:09:51Z'
  edited_at: '2026-09-17T00:30:08Z'
  id: 40496161157521
  locale: es
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/es/articles/40496161157521
---
> **Resumen:** Usa las campañas web de TikTok Ads para atribuir conversiones Web-to-app de TikTok Ads

## Visión general

AppsFlyer admite la integración con TikTok Ads (`tiktokweb_int`) para campañas web de adquisición de usuarios, lo que te permite reportar datos de atribución y conversión directamente mediante la API de eventos de TikTok. TikTok puede utilizar estos datos para optimizar la segmentación de anuncios, medir el rendimiento y crear audiencias personalizadas.

> 🚧 **Importante:**
>
> Actualmente, la integración con TikTok Web no admite el envío de postbacks de re-engagement a CAPI.

### Prerrequisitos

Antes de activar la integración de TikTok Web, asegúrate de tener una cuenta comercial en [TikTok Ads Manager](https://getstarted.tiktok.com/grow-your-business-gb?lang=en&attr_source=google&attr_source=google&attr_medium=search-br-ad&attr_medium=search-br-ad&attr_adgroup_id=155057567247&attr_adgroup_id=155057567247&attr_term=tiktok%20ads%20manager&attr_term=tiktok%20ads%20manager&no_parent_redirect=1&no_parent_redirect=1&creative=%7BGenZCopy%7D&matchtype=e&gad_source=1&gad_campaignid=20368896948&gbraid=0AAAAACeGRgRdqveOjiUJwxN0-j9g7VjPg&gclid=Cj0KCQjwmYzIBhC6ARIsAHA3IkTKsL0d1xAZLIO_9GIkDDIJR-jZs9jDGVa1hTDbsLzcxZl2j6p7ITcaAhf1EALw_wcB).

### Cómo crear una campaña de TikTok Web Ads

Este artículo contiene información y pasos sobre cómo configurar una campaña web en TikTok Ads para aplicaciones móviles con AppsFlyer. La configuración implica definir la integración entre TikTok Ads y AppsFlyer, establecer la configuración de la campaña en ambas plataformas y crear landing pages con OneLink Smart Script o OneLink Smart Banners.

El proceso de configuración incluye los siguientes pasos obligatorios:

* [Configurar la integración de TikTok Web Ads en AppsFlyer](#configura-la-integración-de-tiktok-web-ads-en-appsflyer) (Obligatorio)
* [Configurar la integración de AppsFlyer en TikTok Ads](#configura-la-integración-de-appsflyer-en-tiktok-ads) (Obligatorio)

Y los siguientes pasos opcionales:

* <Anchor target="_blank" href="/marketers/es/docs/meta-ads-create-web-based-campaigns#crear-una-landing-page-con-smart-script-de-onelink">#create-a-landing-page-with-onelink-smart-script</Anchor> (Opcional)
* [Crear una landing page con OneLink Smart Banners](#crear-una-landing-page-con-onelink-smart-banners) (Opcional)

## Configura la integración de TikTok Web Ads en AppsFlyer

Para empezar, activa la integración de TikTok Web y configura los postback que AppsFlyer envía a la API de eventos.

<div id="1-activate-the-tiktok-web-ads-integration" />

<Accordion title="1. Activa la integración de TikTok Web Ads">

Para activar la integración de TikTok Web Ads:

1. En AppsFlyer, en el menú lateral, abre **Colaborar** > **Integraciones de partners** > **Marketplace de partners**.
2. Busca **TikTok Web** (o `tiktokweb_int`) y selecciónalo. Se te redirige a la página de configuración.
3. En la pestaña **Integración**, selecciona **Activar partner**. El interruptor debe permanecer (<Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activado</Anchor>) mientras trabajes con el partner.
4. Desactiva **Privacidad avanzada** (si estás configurando una integración de app iOS).
5. **Uso compartido de datos de Advanced Matching:** Actívalo para compartir con TikTok los campos de Advanced Matching, como el correo electrónico con hash, el número de teléfono con hash, el nombre con hash y el apellido con hash, si estos campos se incluyen en la información del evento enviada a AppsFlyer. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/advanced-matching-data-sharing">Uso compartido de datos de Advanced Matching</Anchor>.
6. **Pixel ID:** Ingresa el Pixel ID. Puedes generarlo u obtenerlo desde tu TikTok Ads Manager siguiendo las instrucciones detalladas <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">AQUÍ</Anchor>.
7. **Token de acceso:** Ingresa el token de acceso. Para generarlo u obtenerlo, sigue <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">estas instrucciones</Anchor>
8. **Limitar el uso de la información personal de los usuarios en anuncios de TikTok (CCPA):** Activa esta opción para habilitar el cumplimiento de las <Anchor target="_blank" href="/marketers/es/docs/send-opendsr-api-requests">leyes de protección de datos</Anchor>.

   > 📘 **Nota:**
   >
   > Cumplir con la normativa de privacidad de la CCPA limita los datos procedentes de los usuarios de anuncios de TikTok ubicados en California y en otros estados sensibles de EE. UU.


</Accordion>

<div id="2-enable-viewthrough-attribution" />

<Accordion title="2. Habilitar la atribución view-through">

AppsFlyer admite la atribución view-through para campañas de TikTok Web mediante una landing page habilitada para [Smart Script](#crear-una-landing-page-con-onelink-smart-script) o [Smart Banner](#crear-una-landing-page-con-onelink-smart-banners). Esto permite la atribución de instalaciones de aplicaciones mediante modelado probabilístico (PMOD) desencadenadas por impresiones de anuncios, incluso cuando los usuarios no hacen clic directamente en el anuncio.

Cuando un usuario hace clic en un anuncio de TikTok Web y llega a una landing page habilitada para [Smart Script](#crear-una-landing-page-con-onelink-smart-script) o [Smart Banner](#crear-una-landing-page-con-onelink-smart-banners), AppsFlyer puede atribuir la instalación posterior de la aplicación. Si está disponible, el `ttclid` se incluirá en el postback a TikTok para mejorar la fidelidad de la atribución.

**Para habilitar la atribución view-through de TikTok Web:**

1. En AppsFlyer, desde la barra lateral, abre **Integraciones activas** > **TikTok web ads**.
2. En la pestaña **Integración**, desplázate hasta la sección **Atribución de instalaciones**.
3. Activa la **Atribución view-through de instalaciones**.
4. **[opcional]** Activa la **Prioridad de atribución igualitaria cross-platform** y configura su ventana de lookback. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Habilitar prioridad igualitaria para impresiones cross-platform</Anchor>.
5. Abre la pestaña **Enlace de atribución**.
6. Desplázate hasta la sección **Atribución view-through** y configura la **ventana de lookback view-through** (hasta 24 horas).
7. Haz clic en **Guardar integración** para aplicar tu configuración.

</Accordion>

<div id="3-set-inapp-event-postbacks" />

<Accordion title="3. Configurar postbacks de eventos in-app">

Actualmente, las instalaciones son los únicos eventos que activan postbacks automáticos predeterminados a TikTok Ads. Para otros tipos de eventos, puedes crear postbacks personalizados asignando eventos de AppsFlyer a eventos de TikTok Ads, que pueden verse en el TikTok Ads Manager.

Para configurar postbacks de eventos in-app, realiza lo siguiente:

1. Activa **postbacks de eventos in-app**.
2. Si es necesario, configura la ventana de postback del evento in-app (lee más sobre la configuración de la ventana de postback del evento in-app en general in <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">este artículo</Anchor>).
3. Haz clic en **Agregar evento** para añadir un evento a la lista.
4. En la columna **Evento de AppsFlyer**, selecciona el nombre del evento en el cuadro desplegable. AppsFlyer recibe el nombre del evento desde el SDK integrado en tu app o desde eventos server-to-server.
5. En la columna **asignado al evento del partner** column, selecciona en el cuadro desplegable el evento del partner predefinido más adecuado.
6. En la columna **Para usuarios de** column, selecciona **Solo este partner** para asegurarte de que los postbacks de eventos in-app se envíen exclusivamente para los eventos realizados por usuarios provenientes de este partner.
7. En la columna **incluyendo** column, selecciona si los eventos se enviarán con sus valores de ingresos. Consulta <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#datos-a-incluir-en-los-postbacks">Datos para incluir en los postbacks</Anchor>.

   > 📘 **Nota:**
   >
   > * Si estás configurando un evento de compra, establece la columna **incluyendo** en **Valores e ingresos**. Seleccionar cualquier otra opción hará que el postback falle.
   > * Actualmente, solo se puede configurar el evento de compra para incluir los ingresos.

8. [Opcional] Haz clic en el ícono **Agregar condición** para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">configurar condiciones</Anchor> para un evento.
9. Haz clic en **Guardar integración**.
10. [Opcional] Después de guardar la integración, desde la página de configuración, puedes integrar más de tus aplicaciones con el partner:
    1. En la esquina superior izquierda, debajo del nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
    2. Selecciona una aplicación diferente en la lista desplegable.
    3. Repite los pasos de integración para la aplicación seleccionada.

</Accordion>

## Configura la integración de AppsFlyer en TikTok Ads

Realiza los siguientes pasos en TikTok Ads Manager.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Configurar el tipo de campaña, objetivo y metas">

Puedes elegir cualquier evento INAPP predefinido enviado desde AppsFlyer como objetivo de campaña, o elegir «Download» si deseas optimizar para la instalación de la app en una aplicación móvil.

> ❗️ **Advertencia**
>
> Si quieres asegurarte de que tus eventos de conversión activados de Web-to-app se envíen mediante la API de eventos de TikTok, omite <Anchor target="_blank" href="/marketers/es/docs/tiktok-for-business-advanced-srn-integration-setup#measuring-app-activity-for-nonapp-campaigns">estos pasos</Anchor> al crear la campaña; de lo contrario, TikTok atribuirá esas conversiones a través de la API de SRN, lo que puede provocar desajustes en el reporte y en la optimización.

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. Configurar URL de destino">

1. En **Destino,** dentro del campo **URL del sitio web,** ingresa la URL que funcionará como destino de tu anuncio. La URL debe corresponder a una de las siguientes opciones:
   * **Landing page web** Se recomienda utilizar una landing page cuando:
     * Tienes una app en múltiples plataformas.
     * Quieres utilizar la landing page para brindar más información sobre el producto anunciado.
     * Quieres utilizar la landing page para recopilar más datos.

       Para todos estos casos de uso, crea una landing page habilitada con [Smart Script](#crear-una-landing-page-con-onelink-smart-script) o [Smart Banner](#crear-una-landing-page-con-onelink-smart-banners)-enabled landing page.
   * **Enlaces de atribución de AF:** Se recomienda el uso de enlaces de atribución de AF (OneLink, plataforma única o multiplataforma) cuando quieres que el usuario sea redirigido directamente a la tienda para descargar la aplicación sin visitar antes una landing page.
2. Haz clic en **Crear un parámetro URL** para agregar parámetros a la URL (ya sea una URL de landing page o un enlace de atribución de AF).
3. En **Parámetros personalizados**, haz clic en **Agregar parámetro**
4. Asocia los parámetros de AppsFlyer con sus valores correspondientes en TikTok. Los parámetros que asignes dependerán de si la URL de destino apunta a una landing page, un enlace de atribución o una tienda de PC o consola.

   #### Landing page o enlace de atribución

   Si tu URL de destino es **una landing page, un enlace de atribución de OneLink o un enlace de atribución de plataforma única**, asigna los siguientes parámetros de AF a sus equivalentes de TikTok:

| Parámetro de AF | Valor correspondiente en TikTok |
| --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#pid">`PID`</Anchor> | `tiktokweb_int` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#c">`c`</Anchor>* | **\_\_campaign\_name\_\_** |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | **\_\_campaign\_id\_\_** |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_adset">`af_conjunto de anuncios`</Anchor> | **\_\_aid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | **\_\_aid\_\_** |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_ad">`af_anuncio`</Anchor> | **\_\_cid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_ad_id">`id_del_anuncio_af`</Anchor> | **\_\_cid\_\_** |

   * Para simplificar el análisis de campañas, incluye el tipo de campaña, web o móvil, como prefijo o sufijo en el nombre de la campaña (por ejemplo, campaign-name\_web)

   Un ejemplo de la URL resultante debería ser:

   ```
   https://app.appsflyer.com/{app_id}?pid=tiktokweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r={https://Add-your-store-url.com}
   ```

   Si el APK de tu app NO está alojado en Google Play Store, agrega el parámetro <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor> y asígnale la URL de la tienda, por ejemplo, `https://Add-your-store-url.com`

   #### Tienda de PC o consola

   Si tu URL de destino es una **tienda de PC o consola**, crea el enlace siguiendo las instrucciones de la tabla a continuación. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Enlaces directos de atribución para plataformas CTV, PC y consolas</Anchor>

| Componente del enlace | value |
| --- | --- |
| URL base | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| Parámetros obligatorios de ruta | ▪ ejemplo de plataforma: steam  <br />▪ ejemplo de app\_id: 123456 |
| Parámetros obligatorios de query | ▪ af\_media\_source  <br />▪ af\_campaign\_id  <br />▪ af\_r |
| Otros parámetros | <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links#parámetros">Ver todos los parámetros</Anchor> |
| Estructura de URL | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |

   Asigna los siguientes parámetros de AppsFlyer a sus equivalentes de TikTok:

| Parámetro de AF | Valor correspondiente en TikTok |
| --- | --- |
| `media_source` | `tiktokweb_int` |
| `af_campaign` * | **\_\_campaign\_name\_\_** |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | **\_\_campaign\_id\_\_** |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_adset">`af_conjunto de anuncios`</Anchor> | **\_\_aid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | **\_\_aid\_\_** |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_ad">`af_anuncio`</Anchor> | **\_\_cid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_ad_id">`id_del_anuncio_af`</Anchor> | **\_\_cid\_\_** |

   * Para simplificar el análisis de campañas, incluye el tipo de campaña, web o móvil, como prefijo o sufijo en el nombre de la campaña (por ejemplo, campaign-name\_web)

   Un ejemplo de URL cross-platform:

   ```
   https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=tiktokweb_int&af_campaign_id=__campaign_id__&af_campaign=__campaign_name__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
   ```

   > 📘 **Nota:**
   >
   > TikTok añade el `ttclid={{ttclid}}` a la URL de destino automáticamente cuando se hace clic en el anuncio


</Accordion>

## Crear una landing page con OneLink Smart Script

**Viaje del usuario:** El usuario hace clic en un anuncio de TikTok y es dirigido a tu web móvil. Llegan una página con botones CTA que los insta a descargar tu aplicación desde una o más plataformas. Al hacer clic en el botón, el usuario es redirigido a la tienda.

<div id="endtoend-data-flow" />

<Accordion title="Flujo de datos end-to-end">

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. La URL del anuncio de TikTok incluye el  `pid=tiktokweb_int` parámetro. Cuando el usuario hace clic en el anuncio, se añade automáticamente un `ttclid` parámetro a la URL en la que hizo clic.
2. El usuario es redirigido a la URL de destino: una landing page que contiene un Smart Script.
3. Cuando se carga la landing page, Smart Script envía una impresión a AppsFlyer que contiene los parámetros de la URL entrante. La impresión permitirá la atribución view-through desde la landing page web. Para más información sobre impresiones y atribución view-through, consulta <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">aquí</Anchor>.
4. Smart Script genera las URL salientes para los botones CTA de la página basándose en los parámetros de la URL entrante, incluido el parámetro `ttclid` . Los botones pueden dirigir a:
   * Google Play y App Store mediante un link de atribución OneLink.
   * Múltiples tiendas de plataformas (por ejemplo, CTV, Epic y Steam). En este caso de uso, Smart Script genera un enlace de atribución single platform para cada plataforma, dirigiendo a la tienda específica de esa plataforma.
   * Descarga de un archivo APK en el dispositivo del usuario.
5. Cuando el usuario hace clic en el botón CTA, el clic se activa y se registra en AppsFlyer.
6. El usuario es redirigido a la tienda y descarga la app.
7. Cuando el usuario abre la app, el evento de instalación se registra en AppsFlyer.
8. AppsFlyer atribuye la instalación basándose en el modelado probabilístico o, si hay disponible un [referente de instalación](https://www.appsflyer.com/glossary/install-referrer/) , de forma determinística.
9. Se genera un postback que contiene los parámetros `ttclid` y otros parámetros de evento, y se envía a TikTok mediante la API de eventos. TikTok utiliza el parámetro `ttclid` para identificar el clic específico, mientras que los demás parámetros ayudan a optimizar la campaña.

</Accordion>

<div id="set-up-a-smart-script-landing-page" />

<Accordion title="Configurar una landing page con Smart Script">

Para configurar tus campañas de TikTok Ads con Smart Script, haz lo siguiente:

1. Configura la plantilla para los enlaces de atribución de OneLink de la campaña. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Cómo crear plantillas OneLink</Anchor>.
2. Crea un Smart Script. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Cómo crear un Smart Script de OneLink</Anchor>.

   > 📘 **Nota:**
   >
   > Las instrucciones a continuación se centran en los pasos específicos necesarios para configurar una campaña de TikTok Ads con Smart Script. Para una guía completa sobre cómo configurar campañas con Smart Script, consulta la sección <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Cómo crear un OneLink Smart Script</Anchor> del artículo <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Configuración de OneLink Smart Script V2</Anchor>.

3. Asegúrate de que todos los parámetros relevantes estén agregados a la URL entrante. Para revisar los parámetros añadidos a la URL entrante, abre TikTok Ads Manager y verifica los parámetros de URL establecidos durante la creación de la URL de destino. Para más información, consulta  [Configurar URL de destino](#2-set-destination-url)[URL](#set-destination-url).
4. Asigna los parámetros de URL entrantes necesarios para la campaña de TikTok Ads a los parámetros de URL salientes que se enviarán a AppsFlyer cuando el usuario haga clic en el botón CTA:
   * **PID**: Asegúrate de que Smart Script tome el valor del parámetro `pid=tiktokweb_int` de la URL entrante y lo asigne a los parámetros correspondientes en la URL saliente.
   * **TTCLID**: El parámetro `ttclid` es esencial para enviar correctamente postbacks de eventos in-app a TikTok. El parámetro `ttclid` debe mapearse manualmente en la sección **Mapeo de parámetros de URL** de la página **Smart Script** :

     1. En **Mapeo para**, selecciona **Parámetro personalizado**.
     2. En **Parámetro URL saliente** y **Parámetros URL entrantes** introduce **ttclid**.

     > 📘 **Nota:**
     >
     > Para mostrarse en los reportes de raw data de AppsFlyer, el parámetro entrante `ttclid` también debe mapearse (además del parámetro saliente `ttclid` ) a uno de los parámetros salientes `af_sub[1-5]` .


</Accordion>

<div id="set-up-a-smart-script-crossplatform-landing-page" />

<Accordion title="Configurar una landing page cross-platform con Smart Script">

Para configurar tus campañas de TikTok Ads con Smart Script para landing pages multiplataforma, haz lo siguiente:

1. Configura la plantilla para los enlaces de atribución de OneLink de la campaña. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Cómo crear plantillas OneLink</Anchor>.
   * Activa tu plantilla de OneLink para la Atribución multiplataforma; consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-cross-platform-links-for-multi-device-campaigns#crea-o-edita-una-plantilla-de-onelink-para-la-atribución-multiplataforma">aquí</Anchor>.
2. Asegúrate de que todos los parámetros relevantes estén agregados a la URL entrante. Para revisar los parámetros añadidos a la URL entrante, abre TikTok Ads Manager y examina los parámetros de URL que estableciste al crear la URL de destino. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/meta-ads-create-web-based-campaigns#b-set-destination-url">Configurar URL de destino</Anchor>.
3. Decide para cada parámetro entrante el parámetro saliente al que será mapeado. Por ejemplo, el parámetro entrante `af_site_id` en la URL entrante será mapeado al parámetro `af_site_id` en la URL saliente.
4. Determina el valor predeterminado para los parámetros salientes obligatorios que no pueden quedar vacíos.
5. Envía a tu desarrollador la siguiente información:
   * Tu mapeo de parámetros entrantes y salientes. El desarrollador creará un script que genere una URL directa saliente basada en el mapeo de parámetros entrantes y salientes.
   * Los valores predeterminados de los parámetros. El script completará los parámetros URL salientes con los valores predeterminados cuando no existan valores correspondientes en los parámetros URL entrantes.
   * Si estás utilizando un enlace de atribución OneLink, envía el dominio y el ID de la plantilla a tu desarrollador. El desarrollador utilizará esto para crear la URL saliente de OneLink. Por ejemplo: `yourbrand.onelink.me/A1b2` o ejemplo de dominio personalizado: `click.yourbrand.com/A1b2`
   * Envía a tu desarrollador los siguientes enlaces de Dev Hub:
     * [Instrucciones y ejemplos de código](https://dev.appsflyer.com/hc/docs/create-direct-click-url) sobre cómo crear URLs directas salientes hacia plataformas no mobile.
     * [Una demo e instrucciones](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/) para crear una landing page cross-platform.

* Recuerda a tu desarrollador que incluya el parámetro entrante `ttclid` en la URL saliente.

  > 📘 **Nota:**
  >
  > Para mostrarse en los reportes de raw data de AppsFlyer, el parámetro entrante `ttclid` también debe mapearse (además del parámetro saliente `ttclid` ) a uno de los parámetros salientes `af_sub[1-5]` parámetros.


</Accordion>

## Crear una landing page con OneLink Smart Banners

**Viaje del usuario:** El usuario hace clic en un anuncio de TikTok y es dirigido a tu sitio web móvil. Llegan a una página donde se muestra un Smart Banner con un CTA para descargar la app desde App Store.

<div id="endtoend-data-flow::e62b5c1b" />

<Accordion title="Flujo de datos end-to-end">

1. La URL del anuncio de TikTok incluye el `pid=tiktokweb_int` parámetro. Cuando el usuario hace clic en el anuncio, un `ttclid` parámetro se añade automáticamente a la URL en la que se ha hecho clic.
2. El usuario es redirigido a la URL de destino: una landing page que contiene un Smart Banner.
3. Cuando se carga la landing page, el Smart Banner envía un evento de <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">impresión</Anchor> a AppsFlyer, que incluye los parámetros de la URL entrante. Esta impresión habilita la atribución view-through para la landing page. Para más información sobre impresiones y atribución view-through, consulta <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">aquí</Anchor>.
4. El Smart Banner genera la URL saliente para el botón CTA del banner. La URL saliente se basa en los parámetros de la URL entrante, incluido el `ttclid` parámetro. El Smart Banner solo puede generar enlaces basados en OneLink.
5. Cuando el usuario hace clic en el botón CTA del Smart Script, el clic se activa y se registra en AppsFlyer.
6. El usuario es redirigido a la tienda y descarga la app.
7. Cuando el usuario abre la app, el evento de instalación se registra en AppsFlyer.
8. AppsFlyer atribuye la instalación mediante el modelado probabilístico o de forma determinística si el install referrer está disponible.
9. Se genera un postback que contiene los `ttclid` parámetros y otros parámetros de evento, y se envía a TikTok mediante la API de eventos. TikTok utiliza el `ttclid` parámetro para identificar el clic específico, mientras que los demás parámetros ayudan a optimizar la campaña.

</Accordion>

<div id="set-up-a-smart-banners-landing-page" />

<Accordion title="Configurar una landing page con Smart Banners">

Para configurar tus campañas de TikTok Ads de Smart Banners, haz lo siguiente:

1. Configura la plantilla para los enlaces de atribución de OneLink de la campaña. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Cómo crear plantillas OneLink</Anchor>.
2. Crea un Smart Banner.

   > 📘 **Nota:**
   >
   > Las instrucciones que se indican a continuación se centran en los pasos específicos necesarios para configurar una campaña de TikTok Ads con Smart Banners. Para una guía completa sobre cómo configurar campañas con Smart Banners, consulta la <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers#configuración">sección de configuración</Anchor> del artículo <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners—mobile web-to-app (for marketers)</Anchor>.

3. Configura los parámetros de Smart Banner para las campañas de TikTok Ads:
   * Asegúrate de que todos los parámetros de URL relevantes estén anexados a la URL entrante. Lo más importante es que `pid=tiktokweb_int` y `ttclid` están disponibles en la URL entrante para permitir que Smart Banner los recopile. Estos dos parámetros son necesarios para la atribución y para enviar postbacks a TikTok Ads. Para revisar los parámetros que se añaden a la URL entrante, abre TikTok Ads Manager y revisa los parámetros de URL que configuraste al crear la URL de destino. Consulta: <Anchor target="_blank" href="/marketers/es/docs/meta-ads-create-web-based-campaigns#b-set-destination-url">Configurar la URL de destino</Anchor>.

</Accordion>

## Ver datos de atribución web-to-app

Aunque los eventos de conversión basados en web se envían a TikTok con el PID original `tiktokweb_int`, se reportan en el dashboard de AppsFlyer y en los reportes de raw data con el PID `tiktokglobal_int`. Esto se aplica tanto a los eventos de conversión primarios como a los eventos de asistencia a la conversión.

Esta vista unificada de reportes te permite analizar el rendimiento de las campañas web y de app en un solo lugar, incluidos reportes completos de costos web y móviles.

### Ver en el dashboard

Todas las atribuciones Web-to-app de TikTok aparecen bajo `tiktokglobal_int` en los dashboards Overview y Activity. Esto proporciona una vista única y consolidada de los resultados de campañas en todas las plataformas. Utiliza filtros y desgloses estándar para comparar el tráfico de app y web dentro de tus datos de TikTok Ads.

### Ver en reportes raw data y API

Las exportaciones de raw data y las respuestas de la API incluyen el PID `tiktokglobal_int` en el campo `media_source` para la actividad web de TikTok. Para verificar los detalles de configuración de la campaña web, consulta el campo `original_url`, que muestra el PID `tiktokweb_int` utilizado durante la creación de la campaña web.

## Medir costos, clics e impresiones

Puedes medir el costo, los clics y las impresiones de TikTok junto con tus datos de atribución Web-to-app en el dashboard y en los reportes Cost ETL (solo para clientes de ROI360):

1. Conecta TikTok como integración de costos en tu aplicación móvil:  
   Ve a la pestaña **Cost** o a la página **Cost Settings** y conecta mediante `tiktokglobal_int`. Para obtener instrucciones paso a paso, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data">Configurar la API de costo de ROI360 para medir datos de costo</Anchor>.
2. Añade el ID de la campaña a la URL de tu página de destino:  
   Incluye `af_c_id` junto con toda la jerarquía de la campaña en la URL de la página de destino. Esto garantiza que el costo, los clics y las impresiones coincidan con tus datos de atribución web en el nivel más granular.

> 📘 **Advertencia**
>
> Los datos de costo están disponibles solo para clientes de ROI360. Los clics y las impresiones están disponibles para todos los clientes que completen esta configuración.

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01K8X2TS8CYRY1XVQNEABWHVF4=visi%C3%B3n-general h_01K8X2TS8C356J1VSAG70EB8HF=importante prerequisites=prerrequisitos h_01K8X2TS8CEFSS92A9MRE7MQD1=prerrequisitos how-to-create-a-tiktok-web-ads-campaign=c%C3%B3mo-crear-una-campa%C3%B1a-de-tiktok-web-ads h_01K8X2TS8CXP0R5WQN14W8S8G3=c%C3%B3mo-crear-una-campa%C3%B1a-de-tiktok-web-ads set-up-tiktok-web-ads-integration-in-appsflyer=configura-la-integraci%C3%B3n-de-tiktok-web-ads-en-appsflyer h_01K8X2TS8CQDNNX59WDW38V24X=configura-la-integraci%C3%B3n-de-tiktok-web-ads-en-appsflyer h_01K8X2TS8CYNWESDXCCFCE4TTA=1-activate-the-tiktok-web-ads-integration h_01K8X2TS8C4HNWR2Z3MTMKQ92Q=nota h_01K8X2TS8C3RDCEX0R8HJGCARH=2-enable-viewthrough-attribution h_01K8X2TS8CP915Y7C5WSEYAJQV=3-set-inapp-event-postbacks h_01K8X2TS8CYD41E31EJ0ES76HP=nota-1 set-up-appsflyer-integration-in-tiktok-ads=configura-la-integraci%C3%B3n-de-appsflyer-en-tiktok-ads h_01K8X2TS8CNQEQCB9SBVESBJ9H=configura-la-integraci%C3%B3n-de-appsflyer-en-tiktok-ads h_01K8X2TS8CZCGK55A71SVDRFXJ=1-set-the-campaign-type-objective-and-goals h_01K8X2TS8C8AFR6M3ME0SPP4QN=advertencia h_01K8X2TS8CC4ZTST3Y5Q2RRVTC=2-set-destination-url landing-page-or-attribution-link=landing-page-o-enlace-de-atribuci%C3%B3n h_01K8X5E9VSFTD53NCA03KYT80P=landing-page-o-enlace-de-atribuci%C3%B3n pc-or-console-store=tienda-de-pc-o-consola h_01K8X5XC69TDW2DNFWFYRN9TMF=tienda-de-pc-o-consola h_01K8X2TS8DQ70RSFHBGM7ZHRYE=nota-2 create-a-landing-page-with-onelink-smart-script=crear-una-landing-page-con-onelink-smart-script h_01K8X2TS8DZ62VHY2W7SCBSWEN=crear-una-landing-page-con-onelink-smart-script h_01K8X2TS8D7X7YT9FBDPZPVAH3=endtoend-data-flow h_01K8X2TS8DJ54M3H11PTXVE2JF=set-up-a-smart-script-landing-page h_01K8X2TS8DFS70S7YNA89R6N95=nota-3 h_01K8X2TS8DZT5GG7BW41A3FA4B=nota-5 h_01K8X2TS8DMTGJNQX3B3VXAM0W=set-up-a-smart-script-crossplatform-landing-page h_01K8X2TS8DZEY18AMT5J14VW42=nota-5 create-a-landing-page-with-onelink-smart-banners=crear-una-landing-page-con-onelink-smart-banners h_01K8X2TS8DAAN8JGJNJGJKD6PP=crear-una-landing-page-con-onelink-smart-banners h_01K8X2TS8DC94419514NK8Y98S=endtoend-data-flow::e62b5c1b h_01K8X2TS8E5EHDFX6RW34TQN4A=set-up-a-smart-banners-landing-page h_01K8X2TS8EC16VZXC9JZJ9Y3VG=nota-6 TikTok-view=ver-datos-de-atribuci%C3%B3n-web-to-app view-webtoapp-attribution-data-from-november-2-2025=ver-datos-de-atribuci%C3%B3n-web-to-app h_01K88J8JFNEYBZNR18133NMRP9=ver-datos-de-atribuci%C3%B3n-web-to-app view-in-the-dashboard=ver-en-el-dashboard h_01K88J8JFNMHCVZ0C34E3D7AST=ver-en-el-dashboard view-in-raw-data-and-api-reports=ver-en-reportes-raw-data-y-api h_01K88J8JFN8W2572N92466YFZQ=ver-en-reportes-raw-data-y-api h_01_measure-cost-clicks-impressions-tiktok-w2a=medir-costos-clics-e-impresiones measure-cost-clicks-impressions-tiktok-w2a=medir-costos-clics-e-impresiones h_01_tiktok_w2a_cost_note=advertencia-1" />
