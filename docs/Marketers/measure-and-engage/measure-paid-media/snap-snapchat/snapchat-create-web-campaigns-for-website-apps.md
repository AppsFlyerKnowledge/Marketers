---
title: 'Snapchat: crea campañas web para aplicaciones web'
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
  created_at: '2026-04-29T09:02:24Z'
  edited_at: '2026-10-20T03:49:18Z'
  id: 46196482479249
  locale: es
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/es/articles/46196482479249
---
> **At a glance:** Configura una integración de anuncios de Snapchat para la aplicación de tu sitio web a fin de enviar señales de conversión web a Snapchat mediante la API de conversiones.

## Descripción general

AppsFlyer admite la integración con anuncios de Snapchat (`snapweb_int`) para campañas de aplicaciones de sitios web, lo que te permite reportar datos de atribución y datos de conversión directamente mediante la API de conversiones de Snapchat. Snapchat puede utilizar estos datos para optimizar la segmentación de anuncios, medir el performance y crear audiencias personalizadas.

Así funciona: un usuario hace clic en un anuncio de Snapchat y llega a tu sitio web. Cuando el usuario completa un evento del sitio web (por ejemplo, una compra o un registro), AppsFlyer envía la señal de conversión a Snapchat mediante la API de conversiones. Snapchat utiliza estos datos para optimizar la segmentación de anuncios y medir el performance de las campañas.

> 🚧 **¡Importante!**
>
> Actualmente, la integración no admite el envío de postbacks de re-engagement mediante la Conversions API.

### Requisitos previos

Antes de activar la integración de anuncios de Snapchat para la aplicación de tu sitio web, asegúrate de tener lo siguiente:

* Una aplicación web configurada en AppsFlyer
* Una cuenta empresarial en <Anchor target="_blank" href="https://ads.snapchat.com/">Snapchat Ads Manager</Anchor>

### Cómo configurar los anuncios de Snapchat para la aplicación de tu sitio web

La configuración consiste en definir la integración entre los anuncios de Snapchat y AppsFlyer, y configurar la campaña en Snapchat Ads Manager. Incluye los siguientes pasos:

* [Parte 1: Configura la integración de anuncios de Snapchat en AppsFlyer (Obligatorio)](#part-1-configura-la-integraci%C3%B3n-de-snapchat-ads-en-appsflyer)
* [Parte 2: Configura la integración de AppsFlyer en los anuncios de Snapchat (Obligatorio)](#part-2-configura-la-integraci%C3%B3n-de-appsflyer-en-snapchat-ads)

## Parte 1: Configura la integración de anuncios de Snapchat en AppsFlyer

Comienza activando la integración de anuncios de Snapchat. A continuación, configura los postbacks que AppsFlyer envía a la Conversions API.

<div id="1-activate-the-snapchat-ads-integration" />

<Accordion title="1. Activar la integración de anuncios de Snapchat">

Para activar la integración de anuncios de Snapchat:

1. En AppsFlyer, desde el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.
2. Busca **Snapchat** y selecciónalo.
3. Haz clic en **Configurar integración**. Se te redirigirá a la página de configuración de **Integraciones activas**.
4. En la pestaña **Integración**, selecciona **Activar partner**. El interruptor debe permanecer activado mientras trabajes con el partner.
5. **ID del píxel:** Introduce el ID del píxel. Puedes generarlo u obtenerlo desde Snapchat Ads Manager siguiendo las instrucciones de la <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US">documentación de anuncios de Snapchat</Anchor>.
6. **Token de acceso:** Introduce el token de acceso. Para crearlo u obtenerlo, sigue las <Anchor target="_blank" href="https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted">instrucciones de la documentación oficial de anuncios de Snapchat</Anchor>.

</Accordion>

<div id="2-set-inapp-event-postbacks" />

<Accordion title="2. Configurar postbacks de eventos in-app">

Puedes definir qué eventos de conversión web envía AppsFlyer a los anuncios de Snapchat asignando los eventos de AppsFlyer a eventos de anuncios de Snapchat. Estos postbacks pueden consultarse en Snapchat Ads Manager. Snapchat utiliza los eventos asociados para optimizar las campañas y generar reportes.

Para configurar los postbacks de eventos in-app:

1. Activa **Postbacks de eventos in-app**.
2. Si es necesario, configura la ventana de postback de eventos in-app. Leer más en <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">Configuración del postback de eventos in-app</Anchor>.
3. Haz clic en **Agregar evento** para añadir un evento a la lista.
4. En la columna **Evento de AppsFlyer**, selecciona el nombre del evento en la lista. AppsFlyer recibe el nombre del evento desde el SDK web integrado en tu sitio web o desde los eventos server-to-server (S2S) que envías a AppsFlyer.
5. En la columna **Asignado al evento del partner**, selecciona de la lista el evento del partner predefinido más adecuado.
6. En la columna **Para usuarios de**, selecciona la opción correspondiente:
   * **Solo este partner** envía eventos atribuidos a los anuncios de Snapchat.
   * **Todas las fuentes de medios, incluido el tráfico orgánico** envían todos los eventos independientemente de la fuente de atribución.
7. En la columna **Incluir**, selecciona si quieres enviar eventos con sus valores de ingresos. Consulta <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#datos-a-incluir-en-los-postbacks">Datos a incluir en los postbacks</Anchor>.
8. [Opcional] Haz clic en el icono **Agregar condición** para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer condiciones</Anchor> para un evento.

   > 📘 **Nota**
   >
   > * Si estás configurando un evento de compra, establece la columna **incluyendo** en **Valores e ingresos**. Seleccionar cualquier otra opción hace que el postback falle.
   > * Actualmente, solo puedes configurar el evento de compra para incluir ingresos.

9. Haz clic en **Guardar integración**.

> 📘 **Note**
>
> Si también usas Snap Pixel en tu sitio web, envía el mismo ID de evento a AppsFlyer y Snapchat para que AppsFlyer pueda deduplicar los eventos:
>
> * Incluye `af_customer_event_id` en el payload del evento que envías a AppsFlyer. En el SDK web, envíalo dentro de `eventValue`. En la API S2S (server-to-server), envíalo como un campo de nivel superior o dentro de `event_value`.
> * Envía el mismo valor en el evento de Pixel correspondiente.
>
> AppsFlyer reenvía este valor a Snapchat como ID del evento. Después, Snapchat lo usa para deduplicar el evento del lado del servidor que recibe de AppsFlyer frente al evento de Pixel, para que AppsFlyer cuente la conversión una sola vez.
>
> Si no envías `af_customer_event_id`, AppsFlyer genera un ID de evento automáticamente. Este ID no coincidirá con tus eventos de Pixel.
>
> Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/integrate-appsflyer-web-sdk">[Beta] Integrar AppsFlyer Web SDK</Anchor>.

> 📘 **Nota**
>
> Si envías eventos S2S y quieres que AppsFlyer envíe postbacks de esos eventos a los anuncios de Snapchat, asegúrate de que cada evento incluya `ip` o `user_agent`. Si faltan ambos, AppsFlyer no envía el postback. Para ver todos los campos de evento compatibles, consulta <Anchor target="_blank" href="/marketers/es/docs/server-to-server-s2s-api-for-web-performance-measurement#medir-un-evento">Server-to-Server (S2S) API for Medición del performance web</Anchor>.

</Accordion>

## Parte 2: Configura la integración de AppsFlyer en Snapchat Ads

Realiza los siguientes pasos en Snapchat Ads Manager.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Configurar el tipo de campaña, objetivo y metas">

Puedes elegir cualquier evento in-app predefinido enviado desde AppsFlyer como objetivo de tu campaña. Selecciona un objetivo de campaña que se ajuste a tus objetivos de conversión web; por ejemplo, generar tráfico hacia tu sitio web u optimizar las conversiones en el sitio.

</Accordion>

<div id="2-set-the-destination-url" />

<Accordion title="2. Configura la URL de destino">

1. En **Destino**, en el campo **URL del sitio web**, introduce la URL de tu sitio web, es decir, la página a la que llegan los usuarios después de hacer clic en tu anuncio. **URL del sitio web** es la opción de destino principal. Los usuarios hacen clic en el anuncio y llegan directamente a tu sitio web para completar eventos de conversión.
2. **[Alternativa] Enlace de atribución de AF (OneLink):** Si quieres redirigir a los usuarios a la app móvil con una redirección alternativa al sitio web, puedes utilizar un enlace de atribución de AF (OneLink) como URL de destino.
3. Haz clic en **Crear un parámetro de URL** para añadir parámetros de URL a la URL de destino.
4. En **Parámetros personalizados**, haz clic en **Agregar parámetro**.
5. Asocia los parámetros de AppsFlyer con sus valores correspondientes en Snapchat:

| Parámetro de AF | Valor asignado en Snapchat |
| --- | --- |
| `PID` | `snapweb_int` |
| `c` * | `{{campaign.name}}` |
| `af_c_id` | `{{campaign.id}}` |
| `af_conjunto de anuncios` | `{{adSet.name}}` |
| `af_adset_id` | `{{adSet.id}}` |
| `af_anuncio` | `{{creative.name}}` |
| `id_del_anuncio_af` | `{{ad.id}}` |
| `af_canal` | `{{site_source_name}}` |

   * Para simplificar el análisis de las campañas, incluye el tipo de campaña (web o móvil) como prefijo o sufijo en el nombre de la campaña; por ejemplo, `campaign-name_web`.

   Para conocer las prácticas recomendadas sobre la configuración de parámetros de URL y la resolución de fuentes de tráfico, consulta <Anchor target="_blank" href="/marketers/es/docs/about-traffic-source-resolution">Información sobre la resolución de fuentes de tráfico</Anchor>.

   Ejemplo de una URL resultante:

   ```http
   https://www.example.com?pid=snapweb_int&c={{campaign.name}}&af_c_id={{campaign.id}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_channel={{site_source_name}}
   ```

> 📘 **Nota**
>
> Snapchat añade automáticamente `ScCid={{ScCid}}` a la URL de destino cuando el usuario hace clic en el anuncio.

</Accordion>

## Ver datos de atribución web

Esto es lo que puedes esperar al revisar los datos de atribución después de la configuración:

* **Dashboard:** En <Anchor target="_blank" href="/marketers/es/docs/my-dashboards#crossplatform-dashboard">el dashboard multiplataforma</Anchor>, los datos web y de la aplicación se muestran uno al lado del otro, lo que te ofrece una vista unificada del rendimiento de las campañas en todas las plataformas.
* Las **exportaciones de raw data y las respuestas de la API** incluyen Snap Web en el campo `media_source` para la actividad web de Snap.

## Medir datos de atribución web con costo web

Puedes obtener una visión completa del rendimiento de los datos de atribución web y los datos de costo web de Snapchat Ads en el dashboard y en los <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">informes de Cost ETL</Anchor>. Para hacerlo, asegúrate de tener <Anchor target="_blank" href="/marketers/es/docs/roi360-onboarding-guide#sobre-roi360">el paquete ROI360</Anchor> y completa la siguiente configuración:

1. Conecta el costo a tu aplicación web mediante `snapchat_int` (no mediante `snapweb_int`) desde la pestaña **Costo** o la página **Configuración de costos**. Para más información sobre cómo conectar el costo, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enabling-cost-api">Configurar la API de costos de ROI360 para medir los datos de costos</Anchor>.
2. Incluye el ID de la campaña (`af_c_id`) en la URL de la landing page. Asegúrate de que la URL incluya la jerarquía completa de la campaña para ver los costos, clics e impresiones asociados a la atribución web con el mayor nivel de detalle posible.

## Características y limitaciones

| Caducado | Observaciones |
| --- | --- |
| Clics e impresiones | Los clics y las impresiones de las campañas web requieren una <Anchor target="_blank" href="/marketers/es/docs/roi360-onboarding-guide">suscripción a ROI360</Anchor>. |
| Reengagement | Actualmente no se admite el envío de postbacks de re-engagement mediante la Conversions API. |

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/web-performance-measurement-overview">Medición del rendimiento web: descripción general</Anchor>

<div data-zendesk-anchors="overview=descripci%C3%B3n-general h_01KQC7RA5R1PS69N3015WY4QRY=descripci%C3%B3n-general h_01KQC7RA5RAY6R70GNHCYWAMRC=importante prerequisites=requisitos-previos h_01KQC7RA5R02QV60T81NX055DM=requisitos-previos how-to-set-up-snapchat-ads-for-your-website-app=c%C3%B3mo-configurar-los-anuncios-de-snapchat-para-la-aplicaci%C3%B3n-de-tu-sitio-web h_01KQC7RA5RPWP0X927ENN6KJ9V=c%C3%B3mo-configurar-los-anuncios-de-snapchat-para-la-aplicaci%C3%B3n-de-tu-sitio-web part-1-set-up-snapchat-ads-integration-in-appsflyer=parte-1-configura-la-integraci%C3%B3n-de-anuncios-de-snapchat-en-appsflyer h_01KQC7RA5RY1HF9VHC332FVBFR=parte-1-configura-la-integraci%C3%B3n-de-anuncios-de-snapchat-en-appsflyer h_01KQC7RA5RJXR5N13SYW3QMMDQ=1-activate-the-snapchat-ads-integration h_01KQC7RA5R3TZZ8PPHHC8EXPG1=2-set-inapp-event-postbacks h_01KQC7RA5RZVTM2X3N6WXRTAT8=nota h_01M520TA4E64EARM6R1EV9QPSR=nota-1 part-2-set-up-appsflyer-integration-in-snapchat-ads=parte-2-configura-la-integraci%C3%B3n-de-appsflyer-en-snapchat-ads h_01KQC7RA5REPX0WDDHT7YWDHMC=parte-2-configura-la-integraci%C3%B3n-de-appsflyer-en-snapchat-ads h_01KQC7RA5R8MDFAF9R5YH1TFPX=1-set-the-campaign-type-objective-and-goals h_01KQC7RA5SB11HRSQR493PM121=2-set-the-destination-url h_01KQC7RA5S422C22YQX1VQ4R7A=nota-2 view-web-attribution-data=ver-datos-de-atribuci%C3%B3n-web h_01KQC7RA5SKRWGGCKV71MV8J56=ver-datos-de-atribuci%C3%B3n-web measure-web-attribution-data-with-web-cost=medir-datos-de-atribuci%C3%B3n-web-con-costo-web h_01KQC7XYSWPTHVDY5R3EG8H4K2=medir-datos-de-atribuci%C3%B3n-web-con-costo-web traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01KQC7RA5SSZB8M8G00NTXG71K=caracter%C3%ADsticas-y-limitaciones h_01KQC80MBB1KCVVNDSFSJHG5ZT=consulta-tambi%C3%A9n" />
