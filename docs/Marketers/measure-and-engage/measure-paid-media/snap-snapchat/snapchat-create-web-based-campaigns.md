---
title: Crear campañas web para Snapchat
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
  created_at: '2025-11-27T14:39:44Z'
  edited_at: '2026-09-17T00:29:54Z'
  id: 41365000854161
  locale: es
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/es/articles/41365000854161
---
> **En resumen:** Usa campañas web de Snapchat Ads para atribuir conversiones web-to-app desde Snapchat Ads

<div id="overview" />

## Visión general

AppsFlyer admite la integración con Snapchat Ads (`snapweb_int`) para campañas web de adquisición de usuarios, lo que te permite reportar datos de atribución y conversión directamente mediante la API de eventos de Snapchat. Snapchat puede utilizar estos datos para optimizar la segmentación de anuncios, medir el rendimiento y crear audiencias personalizadas.

<div id="important" />

> 🚧 **¡Importante!**
>
> Actualmente, la integración con Snapchat Web no admite el envío de postbacks de re-engagement a CAPI.

<div id="prerequisites" />

### Requisitos previos

Antes de activar la integración con Snapchat Web, asegúrate de tener una cuenta business en œœœœ.

<div id="how-to-create-a-snapchat-ads-web-campaign" />

### Cómo crear una campaña web de Snapchat Ads

Este artículo contiene información y pasos sobre cómo configurar una campaña web en Snapchat Ads para apps mobile con AppsFlyer. La configuración implica definir la integración entre Snapchat Ads y AppsFlyer, establecer la configuración de campaña en ambas plataformas y crear landing pages con OneLink Smart Script o OneLink Smart Banners.

El proceso de configuración incluye los siguientes pasos obligatorios:

* [Configurar la integración web de Snapchat Ads en AppsFlyer](#configurar-la-integración-web-de-snapchat-ads-en-appsflyer) (Obligatorio)
* [Configurar la integración de AppsFlyer en Snapchat Ads](#configurar-la-integración-de-appsflyer-en-snapchat-ads) (Obligatorio)

Y los siguientes pasos opcionales:

* [Crear una landing page con OneLink Smart Script](#crear-una-landing-page-con-onelink-smart-script) (Opcional)
* [Crear una landing page con OneLink Smart Banners](#crear-una-landing-page-con-onelink-smart-banners) (Opcional)

<div id="set-up-snapchat-ads-web-integration-in-appsflyer" />

## Configurar la integración web de Snapchat Ads en AppsFlyer

Comienza activando la integración web de Snapchat Ads. Luego configura los postbacks que AppsFlyer envía a la API de Eventos.

<div id="1-activate-the-snapchat-ads-web-integration" />

<Accordion title="1. Activar la integración web de Snapchat Ads">

Para activar la integración web de Snapchat Ads:

1. En AppsFlyer, en el menú lateral, selecciona **Collaborate** > **Partner Integrations** > **Partner Marketplace**.
2. Busca **Snapchat Web** y selecciónalo.
3. Haz clic en **Configurar integración**. Serás dirigido a la página de configuración de **Integraciones activas**.
4. En la pestaña **Integración**, selecciona **Activar partner**. El interruptor debe permanecer (<Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activado</Anchor>) mientras trabajes con el partner.
5. Desactiva **Privacidad avanzada** (si estás configurando una integración de app iOS).
6. **Uso compartido de datos de Advanced Matching:** Actívalo para compartir con Snapchat los campos de Advanced Matching, como el correo electrónico con Hashing, el número de teléfono con Hashing, el nombre con Hashing y el apellido con Hashing, si estos campos se incluyen en la información del evento enviada a AppsFlyer. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/advanced-matching-data-sharing">Uso compartido de datos de Advanced Matching</Anchor>.
7. **Pixel ID:** Ingresa el Pixel ID. Puedes generarlo u obtenerlo desde Snapchat Ads Manager siguiendo las instrucciones detalladas en la [documentación oficial de Snapchat Ads](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US).
8. **Token de acceso:** Ingresa el token de acceso. Para generarlo u obtenerlo, sigue las [instrucciones de la documentación oficial de Snapchat Ads](https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted)

</Accordion>

<div id="2-enable-viewthrough-attribution" />

<Accordion title="2. Habilitar la atribución view-through">

AppsFlyer admite atribución view-through para campañas web de Snapchat cuando utilizas una landing page habilitada con [Smart Script](#crear-una-landing-page-con-onelink-smart-script) o [Smart Banner](#set-up-smart-banners-landing-page). Esto habilita atribución mediante modelado probabilístico (PMOD) para instalaciones de apps generadas por impresiones de anuncios, incluso cuando los usuarios no hacen clic en el anuncio.

Si están disponibles, `ScCid` se incluirán en el postback de Snapchat para mejorar la fidelidad de la atribución.

**Para habilitar la atribución view-through de Snapchat Web:**

1. En AppsFlyer, desde la barra lateral, abre **Integraciones activas** > **Snapchat Ads web**.
2. En la pestaña **Integración**, desplázate hasta la sección **Atribución de instalaciones**.
3. Activa la **Atribución view-through de instalaciones**.
4. **[opcional]** Activa la **Prioridad de atribución igualitaria cross-platform** y configura su ventana de lookback. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Habilitar prioridad igualitaria para impresiones cross-platform</Anchor>.
5. Abre la pestaña **Enlace de atribución**.
6. Desplázate hasta la sección **Atribución view-through** y configura la **ventana de lookback view-through** (hasta 24 horas).
7. Haz clic en **Guardar integración** para aplicar tu configuración.

</Accordion>

<div id="3-set-inapp-event-postbacks" />

<Accordion title="3. Configurar postbacks de eventos in-app">

Actualmente, las instalaciones son los únicos eventos que activan postbacks automáticos predeterminados para Snapchat Ads. Para todos los demás tipos de eventos, puedes crear postbacks personalizados asignando eventos de AppsFlyer a eventos de Snapchat Ads. Estos postbacks pueden verse en Snapchat Ads Manager.

Para configurar postbacks de eventos in-app, realiza lo siguiente:

1. Activa **postbacks de eventos in-app**.
2. Si es necesario, configura la ventana de postback de eventos in-app (obtén más información sobre la configuración general en <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">Configuración de postbacks de eventos in-app</Anchor>).
3. Haz clic en **Agregar evento** para añadir un evento a la lista.
4. En la columna **Evento de AppsFlyer**, selecciona el nombre del evento de la lista. AppsFlyer recibe el nombre del evento desde el SDK integrado en tu app o desde eventos server-to-server.
5. En la columna **Asignado a evento del partner,** selecciona el evento predefinido más adecuado de la lista.
6. En la columna **Para usuarios de**, selecciona **Solo este partner** para asegurarte de que los postbacks de eventos in-app se envíen únicamente para eventos realizados por usuarios provenientes de este partner.
7. En la columna **incluyendo**, selecciona si deseas enviar eventos con sus valores de ingresos. Consulta <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#datos-a-incluir-en-los-postbacks">Datos para incluir en los postbacks</Anchor>.

   <div id="note" />

   > 📘 **Nota:**
   >
   > * Si estás configurando un evento de compra, establece la columna **incluyendo** en **Valores e ingresos**. Seleccionar cualquier otra opción hará que el postback falle.
   > * Actualmente, solo el evento de compra puede configurarse para incluir ingresos.

8. [Opcional] Haz clic en el ícono **Agregar condición** para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">configurar condiciones</Anchor> para un evento.
9. Haz clic en **Guardar integración**.
10. [Opcional] Después de guardar la integración y mientras permanezcas en la página de configuración, puedes integrar apps adicionales con el partner:
    1. Desde la esquina superior izquierda, selecciona el nombre de la app debajo del nombre del partner para abrir la lista de apps.
    2. Selecciona una app diferente de la lista.
    3. Repite los pasos anteriores para la app seleccionada.

</Accordion>

<div id="set-up-appsflyer-integration-in-snapchat-ads" />

## Configurar la integración de AppsFlyer en Snapchat Ads

Realiza los siguientes pasos en Snapchat Ads Manager.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Configurar el tipo de campaña, objetivo y metas">

Puedes elegir cualquier evento INAPP predefinido enviado desde AppsFlyer como objetivo de campaña, o elegir “PAGE\_VIEW” si deseas optimizar para instalaciones de apps móviles.

<div id="warning" />

> ❗️ **Advertencia**
>
> Asegúrate de no seleccionar **Eventos de la app;** de lo contrario, Snapchat reclamará esas conversiones utilizando la API de SRN, lo que puede generar inconsistencias en reportes y optimización.

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. Configurar URL de destino">

1. En **Destino,** dentro del campo **URL del sitio web,** ingresa la URL que funcionará como destino de tu anuncio. La URL debe corresponder a una de las siguientes opciones:
   * **Landing page web** Se recomienda utilizar una landing page cuando:

     * Tienes una app en múltiples plataformas.
     * Quieres utilizar la landing page para brindar más información sobre el producto anunciado.
     * Quieres utilizar la landing page para recopilar más datos.

     Para todos estos casos de uso, crea una [landing page con Smart Script](#crear-una-landing-page-con-onelink-smart-script) o un [Smart Banner](#crear-una-landing-page-con-onelink-smart-banners).
   * **Enlaces de atribución de AF:** Se recomienda utilizar enlaces de atribución de AF (OneLink, single platform o cross-platform) cuando deseas que los usuarios sean redirigidos directamente a la tienda para descargar la app sin visitar primero una landing page.
2. Haz clic en **Crear un parámetro URL** para agregar parámetros a la URL (ya sea una URL de landing page o un enlace de atribución de AF).
3. En **Parámetros personalizados**, haz clic en **Agregar parámetro**

   [<Image alt="Screenshot 2025-11-26 at 8.56.29.png" src="https://files.readme.io/cb3ceba75974f7a57d7f26c3587fd0d0c401427d26fcacff40f2514981b9b02f-small-41366139737873.png" width="2810px" />](https://files.readme.io/cb3ceba75974f7a57d7f26c3587fd0d0c401427d26fcacff40f2514981b9b02f-small-41366139737873.png)
4. Mapea los parámetros de AppsFlyer con sus valores correspondientes de Snapchat.
   * Si tu URL de destino es **una landing page, un enlace de atribución de OneLink o un link de atribución single platform**, mapea los siguientes parámetros AF con sus equivalentes en Snapchat:

| Parámetro de AF | Valor asignado en Snapchat |
| --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#pid">`PID`</Anchor> | `snapweb_int` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#c">`C`</Anchor> | `{{campaign.name}}`* |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}`* |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_adset">`af_conjunto de anuncios`</Anchor> | `{{adSet.name }}`* |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adSet.id}}`* |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_ad">`af_anuncio`</Anchor> | `{{creative.name }}` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_ad_id">`id_del_anuncio_af`</Anchor> | `{{ad.id}}`* |
| <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#attribution::1d1e08b5">`af_canal`</Anchor> | `{{site_source_name}}` |

     Un ejemplo de la URL resultante debería ser:

     ```
     https://app.appsflyer.com/{app_id}?pid=snapweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r={https://Add-your-store-url.com}
     ```

     * Si el APK de tu app NO está alojado en Google Play Store, agrega el parámetro <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor> y asígnale la URL de la tienda, por ejemplo, `https://Add-your-store-url.com`

* Si tu URL de destino es una **tienda de PC o consola**, crea el enlace siguiendo las instrucciones de la tabla a continuación. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Enlaces directos de atribución para plataformas CTV, PC y consolas</Anchor>

| Estructura del enlace de atribución |  |
| --- | --- |
| URL base | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| Parámetros obligatorios de ruta | ▪ Ejemplo de plataforma: steam  <br />▪ Ejemplo de app\_id: 123456 |
| Parámetros obligatorios de query | ▪ af\_media\_source  <br />▪ af\_campaign\_id  <br />▪ af\_r |
| Otros parámetros | <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links#parámetros">Ver todos los parámetros</Anchor> |
| Estructura de URL | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |

  Mapea los siguientes parámetros de AppsFlyer con sus equivalentes en Snapchat:

| Parámetro de AF | Valor asignado en Snapchat |
| --- | --- |
| `media_source` | `snapweb_int` |
| `af_campaign` * | `{{campaign.name}}`* |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | `{{campaign.id}}`* |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_adset">`af_conjunto de anuncios`</Anchor> | `{{adSet.name }}`* |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adSet.id}}`* |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_ad">`af_anuncio`</Anchor> | `{{creative.name }}` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_ad_id">`id_del_anuncio_af`</Anchor> | `{{ad.id}}`* |
| <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#attribution::1d1e08b5">`af_canal`</Anchor> | `{{site_source_name}}` |

  * Para simplificar el análisis de campañas, incluye el tipo de campaña, web o móvil, como prefijo o sufijo en el nombre de la campaña (por ejemplo, campaign-name\_web)

  Un ejemplo de URL cross-platform:

  ```
  https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=snapweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
  ```

  <div id="note-1" />

  > 📘 **Nota:**
  >
  > Snapchat agrega automáticamente el `ScCid={{ScCid}}` a la URL de destino cuando se hace clic en el anuncio


  > 📄
  >
  > Para una guía completa sobre los parámetros de enlaces de AF, consulta <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#parámetros-del-enlace-de-atribución">Parámetros de enlaces de atribución</Anchor>.


</Accordion>

<div id="create-a-landing-page-with-onelink-smart-script" />

## Crear una landing page con OneLink Smart Script

**Viaje del usuario:** El usuario hace clic en un anuncio de Snapchat y es dirigido a tu sitio web móvil. Llegan a una página con botones CTA que los invitan a descargar tu app desde una o más plataformas. Al hacer clic en el botón, el usuario es redirigido a la tienda.

<div id="endtoend-data-flow" />

<Accordion title="Flujo de datos end-to-end">

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. La URL del anuncio de Snapchat incluye el parámetro `pid=snapweb_int`. Cuando el usuario hace clic en el anuncio, se agrega automáticamente un parámetro `ScCid` a la URL que se hizo clic.
2. El usuario es redirigido a la URL de destino: una landing page que contiene un Smart Script.
3. Cuando se carga la landing page, Smart Script envía una impresión a AppsFlyer que contiene los parámetros de la URL entrante. La impresión permitirá la atribución view-through desde la landing page web. Para más información sobre impresiones y atribución view-through, consulta <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">aquí</Anchor>.
4. Smart Script genera las URLs salientes para los botones CTA de la página basándose en los parámetros de la URL entrante, incluido el parámetro `ScCid`. Los botones pueden dirigir a:
   * Google Play y App Store mediante un link de atribución OneLink.
   * Múltiples tiendas de plataformas (por ejemplo, CTV, Epic y Steam). En este caso de uso, Smart Script genera un enlace de atribución single platform para cada plataforma, dirigiendo a la tienda específica de esa plataforma.
   * Descarga de un archivo APK en el dispositivo del usuario.
5. Cuando el usuario hace clic en el botón CTA, el clic se activa y se registra en AppsFlyer.
6. El usuario es redirigido a la tienda y descarga la app.
7. Cuando el usuario abre la app, el evento de instalación se registra en AppsFlyer.
8. AppsFlyer atribuye la instalación mediante probabilistic modeling o de forma determinística si hay un [install referrer](https://www.appsflyer.com/glossary/install-referrer/) disponible.
9. Se genera un postback que contiene los parámetros `ScCid` y otros parámetros de eventos, y se envía a Snapchat mediante la API de eventos. Snapchat utiliza el parámetro `ScCid` para identificar el clic específico, mientras que los demás parámetros ayudan a optimizar la campaña.

</Accordion>

<div id="set-up-a-smart-script-landing-page" />

<Accordion title="Configurar una landing page con Smart Script">

Para configurar tus campañas de Snapchat Ads con Smart Script, realiza lo siguiente:

1. Configura la plantilla para los enlaces de atribución de OneLink de la campaña. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Cómo crear plantillas OneLink</Anchor>.
2. Crea un Smart Script. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Cómo crear un Smart Script de OneLink</Anchor>.

   <div id="note-2" />

   > 📘 **Nota:**
   >
   > Las instrucciones a continuación describen los pasos específicos necesarios para configurar una campaña de Snapchat Ads con Smart Script. Para una guía completa sobre cómo configurar campañas con Smart Script, consulta la sección <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Cómo crear un OneLink Smart Script</Anchor> del artículo <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Configuración de OneLink Smart Script V2</Anchor>.

3. Asegúrate de que todos los parámetros relevantes estén agregados a la URL entrante. Para revisar los parámetros agregados a la URL entrante, abre Snapchat Ads Manager y verifica los parámetros URL configurados al crear la URL de destino. Para más información, consulta [Configurar URL de destino](#2-set-destination-url).
4. Mapea los parámetros de la URL entrante requeridos para la campaña de Snapchat Ads con los parámetros de la URL saliente. Estos parámetros se envían a AppsFlyer cuando el usuario hace clic en el botón CTA:
   * **PID**: Asegúrate de que Smart Script tome el valor del parámetro `pid=snapweb_int` de la URL entrante y lo mapee a los parámetros correspondientes en la URL saliente.
   * **ScCid**: El parámetro `ScCid` es necesario para enviar correctamente postbacks de eventos in-app a Snapchat. El parámetro `ScCid` debe mapearse manualmente en la sección **Mapeo de parámetros URL** de la página **Smart Script**:

     1. En **Mapeo para**, selecciona **Parámetro personalizado**.
     2. En **Parámetro URL saliente** y **Parámetros URL entrantes**, ingresa **ScCid**.

     <div id="note-3" />

     > 📘 **Nota:**
     >
     > Para mostrarlo en los reportes raw data de AppsFlyer, también debes mapear el parámetro entrante `ScCid`, por separado del parámetro saliente `ScCid`, a uno de los parámetros salientes `af_sub[1–5]`.


</Accordion>

<div id="set-up-a-smart-script-crossplatform-landing-page" />

<Accordion title="Configurar una landing page cross-platform con Smart Script">

Para configurar tus campañas de Snapchat Ads con Smart Script para landing pages cross-platform, realiza lo siguiente:

1. Configura la plantilla para los enlaces de atribución de OneLink de la campaña. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Cómo crear plantillas OneLink</Anchor>.
   * Habilita tu plantilla OneLink para atribución cross-platform. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-cross-platform-links-for-multi-device-campaigns#crea-o-edita-una-plantilla-de-onelink-para-la-atribución-multiplataforma">Crear una plantilla OneLink para atribución cross-platform</Anchor>.
2. Asegúrate de que todos los parámetros relevantes estén agregados a la URL entrante. Para revisar los parámetros agregados a la URL entrante, abre Snapchat Ads Manager y revisa los parámetros URL que configuraste al crear la URL de destino. Para más información, consulta [Configurar URL de destino](#2-set-destination-url).
3. Decide para cada parámetro entrante el parámetro saliente al que será mapeado. Por ejemplo, el parámetro entrante `af_site_id` en la URL entrante será mapeado al parámetro `af_site_id` en la URL saliente.
4. Determina el valor predeterminado para los parámetros salientes obligatorios que no pueden quedar vacíos.
5. Envía a tu desarrollador la siguiente información:
   * Tu mapeo de parámetros entrantes y salientes. El desarrollador creará un script que genere una URL directa saliente basada en el mapeo de parámetros entrantes y salientes.
   * Los valores predeterminados de los parámetros. El script completará los parámetros URL salientes con los valores predeterminados cuando no existan valores correspondientes en los parámetros URL entrantes.
   * Si estás utilizando un enlace de atribución OneLink, envía el dominio y el ID de la plantilla a tu desarrollador. El desarrollador utilizará esto para crear la URL saliente de OneLink. Por ejemplo: `yourbrand.onelink.me/A1b2` o ejemplo de dominio personalizado: `click.yourbrand.com/A1b2`
   * Envía a tu desarrollador los siguientes enlaces de Dev Hub:
     * [Instrucciones y ejemplos de código](https://dev.appsflyer.com/hc/docs/create-direct-click-url) sobre cómo crear URLs directas salientes hacia plataformas no mobile.
     * [Una demo e instrucciones](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/) para crear una landing page cross-platform.

* Recuerda a tu desarrollador incluir el parámetro entrante `ScCid` en la URL saliente.

  <div id="note-4" />

  > 📘 **Nota:**
  >
  > Para mostrarse en los reportes de raw data de AppsFlyer, el parámetro entrante `ScCid` también debe mapearse (además del parámetro saliente `ScCid`) a uno de los parámetros salientes `af_sub[1-5]`.


</Accordion>

<div id="create-a-landing-page-with-onelink-smart-banners" />

## Crear una landing page con OneLink Smart Banners

**Viaje del usuario:** El usuario hace clic en un anuncio de Snapchat y es dirigido a tu sitio web móvil. Llegan a una página donde se muestra un Smart Banner con un CTA para descargar la app desde App Store.

<div id="endtoend-data-flow::b905b9a5" />

<Accordion title="Flujo de datos end-to-end">

1. La URL del anuncio de Snapchat incluye el parámetro `pid=snapweb_int`. Cuando el usuario hace clic en el anuncio, se agrega automáticamente un parámetro `ScCid` a la URL que se hizo clic.
2. El usuario es redirigido a la URL de destino: una landing page que contiene un Smart Banner.
3. Cuando se carga la landing page, el Smart Banner envía un evento de <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">impresión</Anchor> a AppsFlyer, que incluye los parámetros de la URL entrante. Esta impresión habilita la atribución view-through para la landing page. Para obtener más información sobre impresiones y atribución view-through, consulta <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">Crear una URL de impresión personalizada</Anchor>.
4. El Smart Banner genera la URL saliente para el botón CTA del banner. La URL saliente se basa en los parámetros de la URL entrante, incluido el parámetro `ScCid`. El Smart Banner solo puede generar enlaces basados en OneLink.
5. Cuando el usuario hace clic en el botón CTA del Smart Banner, el clic se activa y se registra en AppsFlyer.
6. El usuario es redirigido a la tienda y descarga la app.
7. Cuando el usuario abre la app, el evento de instalación se registra en AppsFlyer.
8. AppsFlyer atribuye la instalación mediante el modelado probabilístico o de forma determinística si el install referrer está disponible.
9. Se genera un postback que contiene los parámetros `ScCid` y otros parámetros de eventos, y se envía a Snapchat mediante la API de eventos. Snapchat utiliza el parámetro `ScCid` para identificar el clic específico, mientras que los demás parámetros ayudan a optimizar la campaña.

</Accordion>

<div id="set-up-a-smart-banners-landing-page" />

<Accordion title="Configurar una landing page con Smart Banners">

Para configurar tus campañas de Snapchat Ads con Smart Banners, realiza lo siguiente:

1. Configura la plantilla para los enlaces de atribución de OneLink de la campaña. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Cómo crear plantillas OneLink</Anchor>.
2. Crea un Smart Banner.

   <div id="note-5" />

   > 📘 **Nota:**
   >
   > Las instrucciones a continuación describen los pasos específicos necesarios para configurar una campaña de Snapchat Ads con Smart Banners. Para una guía completa sobre cómo configurar campañas con Smart Banners, consulta la <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers#configuración">sección de configuración</Anchor> del artículo <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners—mobile web-to-app (for marketers)</Anchor>.

3. Configura los parámetros de Smart Banner para campañas de Snapchat Ads:

   * Asegúrate de que todos los parámetros relevantes estén agregados a la URL entrante.
   * Para revisar los parámetros agregados a la URL entrante, abre Snapchat Ads Manager y revisa los parámetros URL configurados al [crear la URL de destino](#2-set-destination-url).

   <div id="note-6" />

   > 📘 **Nota:**
   >
   > Lo más importante es que `pid=snapweb_int` y `ScCid` estén disponibles en la URL entrante para permitir que Smart Banner los recopile. Estos dos parámetros son necesarios para la atribución y para enviar postbacks a Snapchat Ads.


</Accordion>

<div id="view-web-to-app-attribution-data" />

## **Ver datos de atribución web-to-app**

Aunque los eventos de conversión web se envían a Snapchat bajo el PID original `snapweb_int`, se reportan en el dashboard de AppsFlyer y en los reportes de raw data bajo el PID `snapchat_int`. Esto aplica tanto para eventos de conversión primaria como para eventos de asistencia de conversión.

Esta vista unificada de reportes te permite analizar el rendimiento de campañas web y app en un solo lugar, incluyendo reportes completos de costos mobile y web.

<div id="view-in-the-dashboard" />

### **Ver en el dashboard**

Todas las atribuciones web-to-app de Snapchat aparecen bajo `snapchat_int` en los dashboards general y actividad. Esto proporciona una vista única y consolidada de los resultados de campañas en todas las plataformas. Utiliza filtros y desgloses estándar para comparar tráfico app y web dentro de tus datos de Snapchat.

<div id="view-in-raw-data-and-api-reports" />

### **Ver en reportes raw data y API**

* **Las exportaciones raw data y las respuestas API** incluyen el PID `snapchat_int` en el campo `media_source` para actividad web de Google. Para verificar los detalles de configuración de campañas web, consulta el campo `original_url`, que muestra `snapchat_int` como el PID utilizado durante la creación de campañas web.
* Los **reportes de postbacks** muestran `snapweb_int` como la fuente de medios original a la que se envió el postback.

<div id="traits-and-limitations" />

## Características y limitaciones

| Caducado | Observaciones |
| --- | --- |
| Datos de costos | Los datos de costos para campañas web de Snapchat Ads (`snapweb_int`) no se recuperan automáticamente. En cambio, deben importarse manualmente utilizando uno de los <Anchor target="_blank" href="/marketers/es/docs/import-cost-data#procedimientos">dos métodos compatibles: carga de archivos por correo electrónico o carga manual mediante la interfaz de AppsFlyer</Anchor>. Esto aplica para todos los usuarios, incluidos los suscriptores de ROI360. |
| Clics e impresiones (limitación temporal) | Los clics e impresiones para campañas web no están disponibles temporalmente desde Snapchat SRN (`snapchat_int`). |

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01KB2W28THC55F0AJ0KZJPQ6S5=visi%C3%B3n-general h_01KB2W28THSST3148Y5Y07PJ7S=importante prerequisites=requisitos-previos h_01KB2W28THW7E6TRVTTHJZ9BP4=requisitos-previos how-to-create-a-snapchat-ads-web-campaign=c%C3%B3mo-crear-una-campa%C3%B1a-web-de-snapchat-ads h_01KB2W28THTST7HWTJA9TTGPGG=c%C3%B3mo-crear-una-campa%C3%B1a-web-de-snapchat-ads set-up-snapchat-ads-web-integration-in-appsflyer=configurar-la-integraci%C3%B3n-web-de-snapchat-ads-en-appsflyer h_01KB2W28THQJF8K4AWTRXNA3RX=configurar-la-integraci%C3%B3n-web-de-snapchat-ads-en-appsflyer h_01KB2W28TH6NZCGCJAN8K3WFGA=1-activate-the-snapchat-ads-web-integration h_01KB2W28TJ6XY7WKR4VC5XS7DS=2-enable-viewthrough-attribution h_01KB2W28TJGRKP3C50ZPQAWAS9=3-set-inapp-event-postbacks h_01KB2W28TJ14KC606KE82Q7BB7=nota set-up-appsflyer-integration-in-snapchat-ads=configurar-la-integraci%C3%B3n-de-appsflyer-en-snapchat-ads h_01KB2W28TJVZ1BX94SZYH1K5EM=configurar-la-integraci%C3%B3n-de-appsflyer-en-snapchat-ads h_01KB2W28TJ2R95JK7C1PQE644C=1-set-the-campaign-type-objective-and-goals h_01KB2W28TJ4BK88DVYJG4XYE0S=advertencia h_01KB2W28TJB1V382HD09M9Y0C3=2-set-destination-url h_01KB2W28TJT7QZ2P7AZ5X61ZXV=nota-1 create-a-landing-page-with-onelink-smart-script=crear-una-landing-page-con-onelink-smart-script h_01KB2W28TJQA1TBXXQ7MA1F0CB=crear-una-landing-page-con-onelink-smart-script h_01KB2W28TJ4J426HD3ZFHXAV4J=endtoend-data-flow h_01KB2W28TJR8S029FJ3Y81MG8Y=set-up-a-smart-script-landing-page h_01KB2W28TJBYHKYNQRMJ4ZGWYD=nota-5 h_01KB2W28TJZMQEDSNVWRZCNXYD=nota-3 h_01KB2W28TJT0TEFB97RXEGDVRM=set-up-a-smart-script-crossplatform-landing-page h_01KB2W28TJ6XWR7GW4SQQAKZH9=nota-4 create-a-landing-page-with-onelink-smart-banners=crear-una-landing-page-con-onelink-smart-banners h_01KB2W28TJM0X7K5Z7M2120MT9=crear-una-landing-page-con-onelink-smart-banners h_01KB2W28TKJZBNFR335SXKY6FC=endtoend-data-flow::b905b9a5 h_01KB2W28TKKA9NTQEC7ZA9E6EA=set-up-a-smart-banners-landing-page h_01KB2W28TKW8B6H4W0R9YJM3ZE=nota-5 h_01KB2W28TKRH3NC73J2JHNSMWD=nota-6 view-webtoapp-attribution-data=ver-datos-de-atribuci%C3%B3n-web-to-app h_01KB2W28TKDAV34JGYJKF2VT43=ver-datos-de-atribuci%C3%B3n-web-to-app view-in-the-dashboard=ver-en-el-dashboard h_01KB2W28TKNWYXJX189EP2HPN2=ver-en-el-dashboard view-in-raw-data-and-api-reports=ver-en-reportes-raw-data-y-api h_01KB2W28TKJ1MAMM00KY3M3S2W=ver-en-reportes-raw-data-y-api traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01KB2W28TKFY74YBXHD91QP9V0=caracter%C3%ADsticas-y-limitaciones" />
