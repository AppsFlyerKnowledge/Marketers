---
title: Crear campañas basadas en la web para Meta Ads
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
  created_at: '2024-06-04T16:08:28Z'
  edited_at: '2026-09-17T00:28:16Z'
  id: 25646834966033
  locale: es
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/es/articles/25646834966033
---
> **Resumen:** Usa las campañas web de Anuncios de Meta para atribuir conversiones de la web a la aplicación de Anuncios de Meta.

## Visión general

AppsFlyer admite la integración con Meta Ads (`metaweb_int`) para campañas de adquisición de usuarios basadas en la web, lo que te permite informar datos de atribución y conversión directamente a través de la API de conversiones (CAPI) de Meta. Meta utiliza estos datos para optimizar el targeting de anuncios, medir el rendimiento y crear audiencias personalizadas.

> 📘 **Nota:**
>
> Actualmente, la integración con Meta Web no admite el envío de postbacks de re-engagement a CAPI.

### Requisitos previos

Antes de activar la integración de Meta Ads, asegúrate de tener una [cuenta comercial en Meta Business Manager](https://www.facebook.com/business/help/1710077379203657?id=180505742745347).

### Cómo crear una campaña para Meta Web Ads

Este artículo contiene información y pasos sobre cómo configurar una campaña web en Meta Ads para aplicaciones móviles, PC y consolas con AppsFlyer. La configuración implica definir la integración entre Meta Ads y AppsFlyer, configurar la configuración de la campaña en ambas plataformas y crear landing pages con OneLink Smart Script o OneLink Smart Banners.  
El proceso de configuración incluye los siguientes pasos obligatorios:

* [Configurar la integración de Meta Web Ads en AppsFlyer](#configurar-la-integración-de-meta-web-ads-en-appsflyer) (Obligatorio)
* [Configurar la integración de AppsFlyer en Anuncios de Meta](#configurar-la-integración-de-appsflyer-en-anuncios-de-meta) (Obligatorio)

Y los siguientes pasos opcionales:

* [Crear una landing page con Smart Script de OneLink](#crear-una-landing-page-con-smart-script-de-onelink) (Opcional)
* [Crear una landing page con Smart Banners de OneLink](#crea-una-landing-page-con-los-smart-banners-de-onelink) (Opcional)

## Configurar la integración de Meta Web Ads en AppsFlyer

Comienza activando la integración de Anuncios de Meta y configurando los postbacks que AppsFlyer envía a CAPI.

<div id="a-activate-the-meta-ads-integration" />

<Accordion title="1. Activar la integración de Meta Web Ads">

Para activar la integración de Meta Web Ads, sigue estos pasos:

1. En AppsFlyer, en el menú lateral, ve a **Colaborar** > **Integraciones de partners** > **Marketplace de partners**.
2. Busca **Meta Web** y selecciónalo. Se te dirige a la página de configuración.
3. En la pestaña **Integración**, selecciona **Activar partner**. **Nota:** El selector debe permanecer <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activado</Anchor> mientras trabajas con el partner.
4. Apaga **Privacidad avanzada** (si está configurando una integración de aplicaciones iOS).
5. **Uso compartido de datos de Advanced Matching:** Actívalo para compartir con Meta los campos de Advanced Matching, como el correo electrónico con hash, el número de teléfono con hash, el nombre con hash, el apellido con hash y el ID de login de Facebook, si estos campos están incluidos en la información del evento enviada a AppsFlyer. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/advanced-matching-data-sharing">Uso compartido de datos de Advanced Matching</Anchor>.
6. Rellena el formulario en el campo**ID de píxel**. Puedes recuperar el ID de píxel desde el administrador de Anuncios de Meta:
   1. Desde el [Administrador de anuncios](https://www.facebook.com/ads/manager) en el menú lateral, ve a **Todas las herramientas** > **Administrador de eventos**. **Nota:** Asegúrate de tener la empresa correcta seleccionada en el menú desplegable en la parte superior derecha.
   2. En el menú lateral del **Administrador de eventos** selecciona **Orígenes de datos**. Verás una lista de tus píxeles. Si no tienes un píxel para el negocio seleccionado, puedes crear uno a través de la misma vista.
   3. Copia el ID de píxel que se muestra debajo del nombre del píxel.  
      Copia el ID de píxel que se muestra debajo del nombre del píxel  
      y pégalo en el archivo  
      **ID de píxel** en AppsFlyer.
7. Rellena el campo **Token de acceso**. Para recuperar el token de acceso, sigue [Estas instrucciones](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)
8. Activa **Limitar el uso de la información personal de los usuarios por parte de Meta Ads (CCPA)** para cumplir con las <Anchor target="_blank" href="/marketers/es/docs/send-opendsr-api-requests">leyes de protección de datos</Anchor>. **Nota:** Cumplir con las regulaciones de privacidad de la CCPA limita los datos provenientes de los usuarios de Anuncios de Meta que residen en California, EE. UU.

</Accordion>

<div id="d-enable-view-through-attribution-for-meta-web" />

<Accordion title="2. Habilitar la atribución view-through">

AppsFlyer admite la atribución view-through para campañas de Meta Web mediante un [Smart Script](#set-up-smart-script-crossplatform-landing-page) o una landing page habilitada para [Smart Banners](#set-up-smart-banners-landing-page). Esto permite la atribución mediante modelado probabilístico (PMOD) de instalaciones de aplicaciones generadas por impresiones de anuncios, incluso cuando los usuarios no hacen clic directamente en el anuncio.

Cuando un usuario hace clic en un anuncio de Meta Web y llega a una landing page habilitada para [Smart Script](#set-up-smart-script-crossplatform-landing-page) o [Smart Banner](#set-up-smart-banners-landing-page), AppsFlyer puede atribuir la instalación posterior de la aplicación. Si están disponibles, los `fbclid` se incluirán en el postback de Meta para mejorar la fidelidad de la atribución.

**Para habilitar la atribución view-through de Meta Web:**

1. En AppsFlyer, en el menú lateral, abre **Colaborar** > **Integraciones de partners > Integraciones activas** > **anuncios web de Meta**.
2. En la pestaña **Integración**, desplázate a la sección **Atribución de instalaciones**.
3. Activa la **Atribución de instalaciones por view-through**.
4. **[opcional]** Activa la opción **prioridad de atribución equitativa entre plataformas** y configura la ventana de lookback. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Habilitar igual prioridad para impresiones multiplataforma</Anchor>.
5. Abre la pestaña **Enlace de atribución**.
6. Desplázate a la sección **Atribución view-through** y configura la **ventana de lookback por view-through** (hasta 24 horas).
7. Haz clic en **Guardar integración** para aplicar tu configuración.

</Accordion>

<div id="b-set-inapp-event-postbacks" />

<Accordion title="3. Configurar postbacks de eventos in-app">

Actualmente, las instalaciones son los únicos eventos que activan postbacks automáticos predeterminados en Anuncios de Meta. Para otros tipos de eventos, puedes crear postbacks personalizados asignando los eventos de AppsFlyer a los eventos de Anuncios de Meta, que se pueden ver en el archivo[Administrador de Eventos de Meta](https://www.facebook.com/business/help/1541268312717919?id=818859032317965).  
Para configurar postbacks de eventos in-app, realiza lo siguiente:

1. Activa **postbacks de eventos in-app**.
2. Si es necesario, establece el postback de eventos in-app (obtén más información sobre la configuración de la ventana postback de eventos in-app en general en <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">Este artículo</Anchor>).
3. Clic**Agregar evento** para agregar un evento a la lista.
4. En **Evento de AppsFlyer**, selecciona el nombre del evento en el cuadro desplegable. AppsFlyer recibe el nombre del evento ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.
5. En la columna **Asignado al evento del partner,** selecciona en el cuadro desplegable el evento del partner predefinido más adecuado o selecciona PERSONALIZADO.
6. En la columna **Para los usuarios**, selecciona la opción de envío para el evento:
   * **Solo este partner**: envía postbacks solo cuando este evento se atribuya a Meta Ads.
   * **Todas las fuentes de medios, incluidas las orgánicas**, envían postbacks de eventos atribuidos a cualquier partner y eventos orgánicos.
7. En la columna **incluyendo**, selecciona si los eventos se enviarán con sus valores de ingresos. Mira <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#datos-a-incluir-en-los-postbacks">Datos a incluir en los postbacks</Anchor>.

   > 📘 **Nota:**
   >
   > Si estás configurando un evento de compra, configura la columna **incluyendo** en **Valores e ingresos**. Seleccionar cualquier otra opción hará que el postback falle.

8. [Opcional] Haz clic en el icono **Agregar condición** para  <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer condiciones</Anchor> para un evento.
9. Haz clic en **Guardar integración**.
10. [Opcional] Después de guardar la integración, desde la página de configuración, puedes integrar más de tus aplicaciones con el partner:
    1. En la esquina superior izquierda, debajo del nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
    2. Selecciona una aplicación diferente en la lista desplegable.
    3. Repite los pasos de integración para la aplicación seleccionada.

> 📘 **Nota**
>
> Si envías eventos S2S a `metaweb_int`, la carga útil S2S debe incluir los parámetros `ua` (User Agent) y `ip` (dirección IP). Estos valores son necesarios para la optimización de campañas de Meta CAPI. AppsFlyer los incluye automáticamente para los eventos enviados mediante SDK. Para los eventos S2S, los anunciantes deben enviarlos explícitamente. Consulta <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">Server-to-server events API for mobile</Anchor>.

</Accordion>

## Configurar la integración de AppsFlyer en Anuncios de Meta

Realiza los siguientes pasos en el administrador de anuncios de Meta.

<div id="a-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Establecer el tipo de campaña, el objetivo y las metas">

1. Inicia sesión en Meta Ads y crea una campaña.
2. En **Objetivo de la campaña** selecciona una de las siguientes opciones: [![](https://files.readme.io/a0cdd42ddf3bc69106de5137e5c842468178bd1dcd76805ea77ead750ba1e9bb-25646834955921.png)](https://files.readme.io/a0cdd42ddf3bc69106de5137e5c842468178bd1dcd76805ea77ead750ba1e9bb-25646834955921.png)
   * **Ventas**: esto permite que Meta se optimice hacia un evento específico (tu KPI principal).
   * **Tráfico**: esto permite que Meta se optimice hacia los clics de anuncios. Esto solo debe utilizarse si no tienes otros KPIs o si el volumen de otros eventos KPI es demasiado bajo.
3. [Opcional] Si deseas agregar un objetivo personalizado a las opciones anteriores, realiza lo siguiente:
   1. En Anuncios de meta, selecciona el evento personalizado que quieras establecer como objetivo de campaña y márcalo como una acción de conversión en Anuncios de Meta.
   2. En AppsFlyer, en la página **Integración con Meta Web**, en **Postbacks de eventos in-app** asigna un evento de AppsFlyer a un evento de partner personalizado (en la sección **Asignado al evento del partner** ) y asígnale el mismo nombre que la acción de conversión en Anuncios de Meta.

      > 📘 **Nota:**
      >
      > Para más información sobre los objetivos de la campaña de Meta, consulta la sección [Documentación de Meta](https://www.facebook.com/business/help/175683976191028).

4. En **Ubicación de conversión** selecciona **Sitio web**. [![](https://files.readme.io/32e4dcb4ced7e2011728ed709069b78cffffc4090f09a33c729a2b2e7e882e8b-25646834954257.png)](https://files.readme.io/32e4dcb4ced7e2011728ed709069b78cffffc4090f09a33c729a2b2e7e882e8b-25646834954257.png)
5. En **Píxel** ingresa el mismo ID de píxel que ingresaste para `metaweb_int` en el Partner Marketplace de AppsFlyer. Para obtener más información sobre el Meta Pixel, consulta la sección [Documentación de Meta](https://www.facebook.com/business/help/742478679120153) (se requiere un inicio de sesión).
6. Haz clic en **Siguiente**.

</Accordion>

<div id="b-set-destination-url" />

<Accordion title="2. Establecer la URL de destino">

1. Debajo de **Destino,** en el campo **URL del sitio web,** introduce la URL que sirve como destino de tu anuncio. La URL debe ser para uno de los siguientes:

   [![](https://files.readme.io/aec9109f2f3000f669799093460e70198de1934e483314b6cd7f95d8209f361d-25646834955537.png)](https://files.readme.io/aec9109f2f3000f669799093460e70198de1934e483314b6cd7f95d8209f361d-25646834955537.png)

   * **Landing page web** Se recomienda utilizar una landing page cuando:

     * Tienes una app en múltiples plataformas.
     * Quieres utilizar la landing page para brindar más información sobre el producto anunciado.
     * Deseas utilizar la landing page para recopilar más datos.

     Para todos estos casos de uso, crea una [landing page con un Smart Script](#crear-una-landing-page-con-smart-script-de-onelink) o [Smart Banner](#crea-una-landing-page-con-los-smart-banners-de-onelink).
   * **Enlaces de atribución de AF:** Se recomienda el uso de enlaces de atribución de AF (OneLink, plataforma única o multiplataforma) cuando se desea que el usuario sea redireccionado directamente a la tienda para descargar la aplicación sin visitar primero una landing page.

     > 🚧 **Importante:**
     >
     > A veces, el uso de enlaces de atribución de AF puede dar lugar a errores. Si esto ocurre, pide una solución a tus representantes de Meta o simplemente usa una landing page web como URL de destino.

2. haz clic en **Crear un parámetro de URL** para agregar los parámetros de URL a la URL (ya sea una URL de landing page o un enlace de atribución de AF).
3. Debajo de **Parámetros personalizados**haz clic **Agregar parámetro**

   [![4.png](https://files.readme.io/bbce415e16d3442f8959bf7a0c23825035d7d4740d5bf3570306c3684c8764d4-25722672143633.png)](https://files.readme.io/bbce415e16d3442f8959bf7a0c23825035d7d4740d5bf3570306c3684c8764d4-25722672143633.png)
4. Asigna los parámetros de AppsFlyer a tus valores de Meta.

   * Si la URL de destino es una **landing page, un enlace de atribución de OneLink o un enlace de atribución de una sola plataforma**, asigna los siguientes parámetros de AF a sus homólogos de Meta: 

| Parámetro de AF | Valor de Meta asignado |
| --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#pid">`PID`</Anchor> | `metaweb_int` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#c">`C`</Anchor> | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_adset">`af_conjunto de anuncios`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_ad">`af_anuncio`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_ad_id">`id_del_anuncio_af`</Anchor> | `{{ad.id}}` |

     Un ejemplo de la URL resultante debería ser:

     ```http
     https://app.appsflyer.com/{app_id}?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={https://Add-your-store-url.com}
     ```

     * Si el APK de tu aplicación NO está alojado en Google Play Store, agrega el parámetro <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor> y asígnale la URL de la tienda, por ejemplo, `https://Add-your-store-url.com`.
   * Si la URL de destino es un **PC o una tienda de consolas**, crea el enlace siguiendo las instrucciones de la tabla siguiente. Para obtener información adicional, consulta: <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Enlaces de atribución directa de CTV, PC y plataforma de consola</Anchor>

<table><thead><tr><th colspan="2">Estructura del enlace de atribución</th></tr></thead><tbody><tr><td>URL base</td><td>engagements.appsflyer.com/v1.0/c2s/click/app/</td></tr><tr><td>Parámetros de ruta obligatorios</td><td><ul><li>platform<br/>Ejemplo: steam</li><li>app_id<br/>Ejemplo: 123456</li></ul></td></tr><tr><td>Parámetros obligatorios de la consulta</td><td><ul><li>media_source</li><li>af_campaign_id</li><li>af_r</li></ul></td></tr><tr><td>Otros parámetros</td><td><a href="./ctv-pc-and-console-platform-direct-attribution-links#parámetros" target="_blank">Ver todos los parámetros</a></td></tr><tr><td>Estructura de URL</td><td><code>https://engagements.appsflyer.com/v1.0/c2s/click/app/`{platform}/{app_id}?af_media_source={media_source}&amp;af_campaign_id={campaign_id}&amp;af_r={app_store_url}`</code></td></tr></tbody></table>

     Asigna los siguientes parámetros de AppsFlyer a sus contrapartes de Meta:

| Parámetro de AF | Valor de Meta asignado |
| --- | --- |
| `media_source` | `metaweb_int` |
| `af_campaign` | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_adset">`af_conjunto de anuncios`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_ad">`af_anuncio`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_ad_id">`id_del_anuncio_af`</Anchor> | `{{ad.id}}` |

     Un ejemplo de URL multiplataforma:

     ```http
     https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
     ```

   > 📘 **Nota:**
   >
   > Meta añade `fbclid={{fbclid}}` a la URL de destino automáticamente cuando se hace clic en el anuncio.


   > 👍 **Consejo**
   >
   > Para simplificar el análisis de la campaña, incluye el tipo de campaña, web o móvil, como prefijo o sufijo en el nombre de la campaña (p.


> 📘 **Nota**
>
> Para obtener una guía completa sobre los parámetros del enlace AF, consulta <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#parámetros-del-enlace-de-atribución">Parámetros del enlace de atribución</Anchor>.

</Accordion>

<div id="c-select-tracked-events" />

<Accordion title="3. Seleccionar eventos supervisados">

Utiliza la sección de seguimiento para seleccionar los eventos de conversión promocionados por tu anuncio (la configuración de los eventos se realiza a través del [Administrador de eventos](https://www.facebook.com/business/help/898185560232180?id=1205376682832142)).

[![](https://files.readme.io/75b6136fdf3fd9790e39aeec735ccd2e1ff0b8a5f302c85f0ed3b05926fcc435-25646834958481.png)](https://files.readme.io/75b6136fdf3fd9790e39aeec735ccd2e1ff0b8a5f302c85f0ed3b05926fcc435-25646834958481.png)

> 🚧 **Importante:**
>
> Asegúrate de no elegir **Eventos de la aplicación** porque Meta reclamará esas conversiones mediante la API de SRN, lo que puede provocar problemas en los reportes y la optimización.

</Accordion>

## Crear una landing page con Smart Script de OneLink

**Viaje del usuario:** El usuario hace clic en un anuncio de Meta y es dirigido a tu sitio web móvil. Llegan una página con botones CTA que los insta a descargar tu aplicación desde una o más plataformas. Al hacer clic en el botón, se redirige al usuario a la tienda.

<div id="end-to-end-data-flow" />

<Accordion title="Flujo de datos end-to-end">

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. La URL del anuncio de Meta incluye el parámetro `pid=metaweb_int`. La URL del anuncio de Meta incluye el atributo parámetro `pid=metaweb_int` Cuando el usuario hace clic en el anuncio, un parámetro `fbclid` se anexa automáticamente a la URL en la que se ha hecho clic.
2. El usuario es redirigido a la URL de destino: una landing page que contiene un script inteligente.
3. Cuando se carga la landing page, Smart Script envía una impresión a AppsFlyer que contiene los parámetros de la URL entrante. La impresión permitirá la atribución post-impresión desde la landing page web. Para obtener más información sobre las impresiones y la atribución post-impresión, consulta <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">aquí</Anchor>.
4. Smart Script genera las URLs de salida para los botones CTA de la página en función de los parámetros de URL entrantes, incluido el parámetro `fbclid`. Los botones pueden llevar a:
   * Google Play y App Store a través de un enlace de atribución de OneLink.
   * Tiendas de múltiples plataformas (por ejemplo, CTV, Epic y Steam). En este caso de uso, Smart Script genera un único enlace de atribución de plataforma para cada plataforma, que conduce a la tienda de la plataforma especificada.
   * Descarga de un archivo APK en el dispositivo del usuario.
5. Cuando el usuario hace clic en el botón CTA, el clic se activa y se registra en AppsFlyer.
6. El usuario es redirigido a la tienda y descarga la app.
7. Cuando el usuario abre la aplicación, el evento de instalación se registra en AppsFlyer.
8. AppsFlyer atribuye la instalación en función de un modelo probabilístico o de forma determinista si un [referente de instalación](https://www.appsflyer.com/glossary/install-referrer/) está disponible.
9. Un postback que contiene el parámetro `fbclid` y otros parámetros de eventos se generan y envían a Meta a través de la API de CAPI. Meta utiliza el método `fbclid` para identificar el clic específico, mientras que los demás parámetros ayudan a optimizar la campaña.

</Accordion>

<div id="set-up-smart-script-landing-page" />

<Accordion title="Configurar una landing page de Smart Script">

Para configurar tu Smart Script, las campañas de Anuncios de Meta realizan lo siguiente:

1. Configura la plantilla para los enlaces de atribución OneLink de la campaña. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Cómo crear plantillas de OneLink</Anchor>.
2. Crea un Smart Script. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Cómo crear un Smart Script de OneLink</Anchor>.

   > 📘 **Nota:**
   >
   > Las instrucciones a continuación se centran en los pasos específicos necesarios para configurar una campaña de Anuncios de Meta con Smart Script. Para obtener una guía completa sobre cómo configurar campañas de Smart Script, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Cómo crear un Smart Script de OneLink</Anchor> de la sección del artículo <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Configuración de OneLink Smart Script V2</Anchor>.

3. Asegúrate de que todos los parámetros de URL relevantes estén anexados a la URL entrante. Para revisar los parámetros anexados a la URL entrante, abre el administrador de anuncios de Meta y verifica los parámetros de URL establecidos durante la creación de la URL de destino. Para más información, consulta: [Establecer la URL de destino](#b-set-destination-url).
4. Asigna los parámetros de URLs entrantes necesarios para la campaña de Meta Ads a los parámetros de URL de salida que se enviarán a AppsFlyer cuando el usuario haga clic en el botón CTA:
   * **PID**: Asegúrate de que Smart Script tome el parámetro `pid=metaweb_int` de la URL entrante y lo asigna a los parámetros correspondientes en la URL de salida.
   * **FBCLID**: El parámetro `fbclid` es esencial para enviar correctamente postbacks de eventos in-app a Meta. La asignación de parámetros FBCLID de la URL de salida depende de tu versión de Smart Script:

     * SDK versión 2.8.1 y superior: El parámetro `fbclid` se reenvía automáticamente al parámetro de URL de salida cuando está presente en la URL entrante, lo que elimina la necesidad de una asignación manual.
     * Versión 2.8.0 e inferior: El parámetro `fbclid` debe asignarse manualmente en la sección de **asignación de parámetros URL** de la página de **Smart Script**:
       1. En **Asignación para**, selecciona **Parámetro personalizado**.
       2. En **Parámetro URL de salida** y **Parámetros URL entrantes**, ingresa **fbclid**.

     > 📘 **Nota:**
     >
     > Para mostrar en los reportes de raw data de AppsFlyer, los datos entrantes `fbclid` también se deben asignar (además del parámetro de salida `fbclid`) a uno de los parámetros de salida `af_sub[1-5]`. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id">Facebook FBCLID</Anchor>.


</Accordion>

<div id="set-up-smart-script-crossplatform-landing-page" />

<Accordion title="Configurar una landing page multiplataforma de Smart Script">

Para configurar tus campañas de Anuncios de Meta con Smart Script para landing pages multiplataforma, haz lo siguiente:

1. Configura la plantilla para los enlaces de atribución OneLink de la campaña. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Cómo crear plantillas de OneLink</Anchor>.
   * Consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-cross-platform-links-for-multi-device-campaigns#crea-o-edita-una-plantilla-de-onelink-para-la-atribución-multiplataforma">aquí</Anchor>.
2. Asegúrate de que todos los parámetros de URL relevantes estén anexados a la URL entrante. Para revisar los parámetros anexados a la URL entrante, abre el administrador de anuncios de Meta y examina los parámetros de URL que estableciste cuando creaste la URL de destino. Para obtener más información, consulta [Establecer la URL de destino](#b-set-destination-url).
3. Decide para cada parámetro entrante el parámetro de salida al que se asignará. Por ejemplo `af_site_id` en la URL entrante se asignará a `af_site_id` en la URL de salida.
4. Decide el valor predeterminado para los parámetros de salida obligatorios que no pueden estar vacíos.
5. Envíe a tu desarrollador la siguiente información:
   * El mapeo de parámetros de entrada y salida. El desarrollador creará un script que genere una URL directa de salida basada en la asignación de parámetros de entrada - de salida.
   * Los valores predeterminados de los parámetros. El script rellenará los parámetros de la URL de salida con los valores predeterminados siempre que no haya valores de parámetros de URL entrantes correspondientes.
   * Si estás utilizando un enlace de atribución OneLink, envía el dominio y el ID de la plantilla a tu desarrollador. El desarrollador utiliza esto para crear la URL de salida de OneLink. Por ejemplo: `yourbrand.onelink.me/A1b2` o Ejemplo de dominio de marca: `click.yourbrand.com/A1b2`
   * Envía a tu desarrollador los siguientes enlaces de Dev Hub:
     * [Ejemplos de instrucciones y códigos](https://dev.appsflyer.com/hc/docs/create-direct-click-url) sobre cómo crear las URL directas de salida a las plataformas no móviles.
     * [Una demostración e instrucciones](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/) para crear una landing page multiplataforma.
   * Recuérdale a tu desarrollador que incluya el parámetro entrante `fbclid` en la URL de salida.

     > 📘 **Nota:**
     >
     > Para mostrar en los reportes de raw data de AppsFlyer, los datos entrantes `fbclid` también se debe asignar (además del parámetro saliente `fbclid`) a uno de los parámetros salientes `af_sub[1-5]`.


</Accordion>

## Crea una landing page con los Smart Banners de OneLink

**Viaje del usuario:** El usuario hace clic en un anuncio de Meta y es dirigido a tu sitio web móvil. Aterriza en una página y se muestra un Smart Banner con un CTA para descargar la aplicación de la tienda de aplicaciones.

<div id="end-to-end-data-flow::4f887e1c" />

<Accordion title="Flujo de datos de extremo a extremo">

1. La URL del anuncio de Meta incluye el parámetro `pid=metaweb_int`. La URL del anuncio de Meta incluye el atributo parámetro `pid=metaweb_int` Cuando el usuario hace clic en el anuncio, un parámetro `fbclid` se anexa automáticamente a la URL en la que se ha hecho clic.
2. El usuario es redirigido al destino de la URL: una landing page que contiene un Smart Banner.
3. Cuando se carga la landing page, el Smart Banner envía una <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">impresión</Anchor> a AppsFlyer, que incluye los parámetros de URL entrantes. Esta impresión permite la atribución view-through de la landing page. Para más información sobre las impresiones y la atribución por impresiones, consulta <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">aquí</Anchor>.
4. El Smart Script genera la URL de salida para el botón CTA en el banner. La URL de salida se basa en los parámetros de la URL entrante, incluido el parámetro `fbclid`. El Smart Script solo puede generar enlaces basados en OneLink.
5. Cuando el usuario hace clic en el botón CTA del Smart Script, el clic se activa y se registra en AppsFlyer.
6. El usuario es redirigido a la tienda y descarga la aplicación.
7. Cuando el usuario abre la app, el evento de instalación se registra en AppsFlyer.
8. AppsFlyer atribuye la instalación en función de un modelo probabilístico o de forma determinista si el referente de instalación está disponible.
9. Un postback que contiene el parámetro `fbclid` y otros parámetros de eventos se generan y envían a Meta a través de la API de CAPI. Meta utiliza el método `fbclid` para identificar el clic específico, mientras que los demás parámetros ayudan a optimizar la campaña.

</Accordion>

<div id="set-up-smart-banners-landing-page" />

<Accordion title="Configurar una landing page de Smart Banners">

Para configurar tus Smart Banners, las campañas de Anuncios de Meta realizan lo siguiente:

1. Configura la plantilla para los enlaces de atribución OneLink de la campaña. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Cómo crear plantillas de OneLink</Anchor>.
2. Crea un Smart Banner.

   > 📘 **Nota:**
   >
   > Las instrucciones que se indican a continuación se centran en los pasos específicos necesarios para configurar una campaña de Anuncios de Meta con Smart Banners. Para obtener una guía completa sobre cómo configurar campañas de Smart Banners, consulta en el artículo la sección <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers#configuración">de configuración</Anchor> del <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners: web-to-app móvil (para vendedores)</Anchor>.

3. Configura los parámetros de los Smart Banners para las campañas de Anuncios de Meta:
   * Asegúrate de que todos los parámetros de URL relevantes estén anexados a la URL entrante. Lo más importante es que el `pid=metaweb_int` y `fbclid` están disponibles en la URL entrante para permitir que el Smart Banner los recopile. Estos dos parámetros son necesarios para la atribución y para enviar postbacks a Meta Ads. Para revisar los parámetros que se anexan a la URL entrante, abre el administrador de Anuncios de Meta y revisa los parámetros de URL que estableciste cuando creaste la URL de destino.

</Accordion>

## Ver datos de atribución web-to-app

Aunque los eventos de conversión basados en web se envían a Meta con el PID de `metaweb_int` original, se reportan en el dashboard de AppsFlyer y en los reportes de raw data con el PID de `Facebook Ads`. Esto se aplica tanto a los eventos de conversión primarios como a los eventos de asistencia a la conversión.

Esta vista de reportes unificada te permite analizar el rendimiento de las campañas web y app en un solo lugar, incluidos los reportes de costos web y móvil completos.

### Ver en el dashboard

Todas las atribuciones web-to-app de Meta aparecen en `Facebook Ads` en los dashboards General y Actividad. Esto proporciona una vista única y consolidada de los resultados de la campaña en todas las plataformas. Utiliza filtros y desgloses estándar para comparar el tráfico web y de aplicaciones dentro de tus datos de Meta Ads.

### Ver en reportes raw data y API

* **Las exportaciones de raw data y las respuestas de la API** incluyen el PID `Facebook Ads` en el campo `media_source` para la actividad web de Meta. Para verificar los detalles de configuración de la campaña web, consulta el campo `original_url` que muestra `metaweb_int` como el PID utilizado durante la creación de campañas web.
* Los **reportes de postbacks** muestran a `metaweb_int` como la fuente de medios original a la que se envió el postback.

## Características y limitaciones

| Caducado | Observaciones |
| --- | --- |
| Datos de impresiones, clics y costos | Los datos de costos, clics e impresiones de Meta Ads Web (`metaweb_int`) se admiten a través de la integración de Meta Ads (`Facebook Ads`).<ul><li>Para obtener los datos, asegúrate de conectar la cuenta de la ad network al PID principal (`Facebook Ads`):<ul><li>Suscriptores del ROI360: en la página **Configuración de costos**,</li><li>ROI360 no suscriptores: en la página **Integración activa** (pestaña **Costo**).</li></ul></li><li>Para ver los datos de costos, clics e impresiones de las campañas web de Meta Ads, asegúrate de que el ID de campaña (<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_c_id">af\_c\_id</Anchor>) esté incluido en el enlace de atribución.</li><li>El enlace de atribución debe incluir la jerarquía completa de la campaña para ver los datos de costos, clics e impresiones vinculados a la atribución al nivel más granular.</li></ul> |

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01HZKNS17JYFQ3F5TKNE5Q5TJ4=visi%C3%B3n-general h_01J8CYG29BETYPZ03A1X54M3ZF=nota prerequisite=requisitos-previos h_01HZKNS17JTCXE4JMZ64NEVPS6=requisitos-previos how-to-create-a-meta-ads-campaign=c%C3%B3mo-crear-una-campa%C3%B1a-para-meta-web-ads h_01HZKNS17JERCAKZHK43ZQWARJ=c%C3%B3mo-crear-una-campa%C3%B1a-para-meta-web-ads set-up-meta-ads-integration-in-appsflyer=configurar-la-integraci%C3%B3n-de-meta-web-ads-en-appsflyer h_01HZKNS17J284R2MAN42WV7F0S=configurar-la-integraci%C3%B3n-de-meta-web-ads-en-appsflyer h_01HZKNS17JGQBENY2X8S5PHFVH=a-activate-the-meta-ads-integration h_01ZXVWB1ZYKK4DP38QY1RMEY6M=d-enable-view-through-attribution-for-meta-web h_01HZKNS17JH2ZJKATV1AP6JDWP=b-set-inapp-event-postbacks 01JJ4MGS84WXEVG4FWQ0YQ7GN6=nota-1 h_01_s2s_metaweb_ua_ip=nota-2 set-up-appsflyer-integration-in-meta-ads=configurar-la-integraci%C3%B3n-de-appsflyer-en-anuncios-de-meta h_01HZKNS17JJWX7N9W6BN05B57C=configurar-la-integraci%C3%B3n-de-appsflyer-en-anuncios-de-meta h_01HZKNS17JTVX8N5CKTKVGH0QB=a-set-the-campaign-type-objective-and-goals h_01HZKNS17JHHS7GYPBT441ND7A=nota-3 h_01HZKNS17KT8TRD2TGDBRGKBZ3=b-set-destination-url h_01HZKNS17KCNKS4YY4JHMQRM1Z=importante h_01J2V9WF300WDY0PWV68TDR9TT=nota-4 h_01K88MSNRX9QFQ49FN2MXPMADX=consejo 01J2V903C36X5K6VRPGQQGWFMW=nota-5 h_01HZKNS17K07CENP8GG7MQRKHK=c-select-tracked-events h_01HZKNS17KARAENYPMVJSM1ARQ=importante-1 create-landing-page-with-onelink-smart-script=crear-una-landing-page-con-smart-script-de-onelink h_01HZKNS17KPJMP74HQKWY022T2=crear-una-landing-page-con-smart-script-de-onelink h_01HZKNS17K5PRRXSD2JMJ54NTN=end-to-end-data-flow h_01HZKNS17KA8VAK5TDFG1NV9YN=set-up-smart-script-landing-page h_01HZKNS17K6DPA6E9CTM5F3X1A=nota-6 h_01HZKNS17K2W4XJB0BH87RZYTJ=nota-8 h_01HZKNS17K5RRAFFTNA6QT7AKJ=set-up-smart-script-crossplatform-landing-page h_01HZKNS17K03S4B3ZRQ62TRFRE=nota-8 create-landing-page-with-onelink-smart-banners=crea-una-landing-page-con-los-smart-banners-de-onelink h_01HZKNS17KH8NQ68RPZGMEAQTV=crea-una-landing-page-con-los-smart-banners-de-onelink h_01HZKNS17K4Y7WSM14EEJ2G5NC=end-to-end-data-flow::4f887e1c h_01HZKNS17KZ3YKS5R52SRKR9P2=set-up-smart-banners-landing-page h_01HZKNS17K3W3GPV6TM5RQS1WP=nota-9 meta%20view=ver-datos-de-atribuci%C3%B3n-web-to-app view-webtoapp-attribution-data-from-november-2-2025=ver-datos-de-atribuci%C3%B3n-web-to-app h_01K88J8JFNEYBZNR18133NMRP9=ver-datos-de-atribuci%C3%B3n-web-to-app view-in-the-dashboard=ver-en-el-dashboard h_01K88J8JFNMHCVZ0C34E3D7AST=ver-en-el-dashboard view-in-raw-data-and-api-reports=ver-en-reportes-raw-data-y-api h_01K88J8JFN8W2572N92466YFZQ=ver-en-reportes-raw-data-y-api traits-and-limitations=caracter%C3%ADsticas-y-limitaciones 01JEZXJNF1C932KGAEFS4P5D51=caracter%C3%ADsticas-y-limitaciones" />
