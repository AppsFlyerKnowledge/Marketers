---
title: 'TikTok for Business: crea campañas web para aplicaciones web'
metadata:
  keywords:
    - Web Attribution
    - Web Attribution SDK
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-04-29T07:09:07Z'
  edited_at: '2026-09-01T00:32:28Z'
  id: 46191822292113
  locale: es
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/es/articles/46191822292113
---
> **Resumen:** Configura una integración de TikTok Web Ads para tu aplicación web a fin de enviar señales de conversión web a TikTok mediante la Events API.

## Descripción general

AppsFlyer admite la integración con TikTok Web Ads (`tiktokweb_int`) para campañas de aplicaciones web, lo que te permite reportar datos de atribución y conversión directamente mediante la Events API de TikTok. TikTok puede utilizar estos datos para optimizar la segmentación de anuncios, medir el performance y crear audiencias personalizadas.

Así es como funciona: cuando un usuario hace clic en un anuncio de TikTok, llega a tu sitio web y completa un evento web (por ejemplo, una compra o un registro), AppsFlyer envía la señal de conversión a TikTok mediante la Events API. TikTok utiliza estos datos para optimizar la segmentación de anuncios y medir el performance de las campañas.

> 📄 **Ver también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/web-performance-measurement-overview">Medición del rendimiento web: descripción general</Anchor>

> 🚧 **¡Importante!**
>
> Actualmente, la integración no admite el envío de postbacks de re-engagement mediante la Events API.

### Requisitos previos

Antes de activar la integración de TikTok Web Ads para tu aplicación web, asegúrate de tener lo siguiente:

* Una aplicación web configurada en AppsFlyer
* Una cuenta empresarial en <Anchor target="_blank" href="https://getstarted.tiktok.com/grow-your-business-gb">TikTok Ads Manager</Anchor>

### Cómo configurar TikTok Web Ads para tu aplicación web

La configuración consiste en definir la integración entre TikTok Web Ads y AppsFlyer, y configurar la campaña en TikTok Ads Manager. Incluye las siguientes partes:

* [Parte 1: Configura la integración de TikTok Web Ads en AppsFlyer](#parte-1-configura-la-integración-de-tiktok-web-ads-en-appsflyer) (obligatorio)
* [Parte 2: Configura la integración de AppsFlyer en TikTok Web Ads](#parte-2-configura-la-integración-de-appsflyer-en-tiktok-web-ads) (obligatorio)

## Parte 1: Configura la integración de TikTok Web Ads en AppsFlyer

Para empezar, activa la integración de TikTok Web Ads y configura los postbacks que AppsFlyer envía a la Events API.

<div id="1-activate-the-tiktok-ads-integration" />

<Accordion title="1. Activa la integración de TikTok Web Ads">

Para activar la integración de TikTok Web Ads:

1. En AppsFlyer, en el menú lateral, ve a **Colaborar** > **Partner Marketplace**.
2. Busca **TikTok For Business - Advanced SRN** (o `tiktokweb_int`) y selecciónalo.
3. Haz clic en **Configurar integración**. Se te redirigirá a la página de configuración de **Integraciones activas**.
4. En la pestaña **Integración**, activa **Activar partner**. El interruptor debe permanecer activado mientras trabajes con el partner.
5. **ID del píxel:** Introduce el ID del píxel. Puedes generarlo u obtenerlo desde TikTok Ads Manager siguiendo las instrucciones de la <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">documentación de TikTok</Anchor>.
6. **Token de acceso:** Introduce el token de acceso. Para generarlo u obtenerlo, sigue las instrucciones de la misma <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">documentación de TikTok</Anchor>.
7. **Limitar el uso que TikTok Web Ads hace de la información personal de los usuarios (CCPA):** Activa este interruptor para cumplir con las <Anchor target="_blank" href="/marketers/es/docs/send-opendsr-api-requests">leyes de protección de datos</Anchor>.

> 📘 **Nota**
>
> Al habilitar el cumplimiento de la CCPA, se limitan los datos procedentes de los usuarios de TikTok Web Ads ubicados en California y en otros estados sensibles de EE.UU.

</Accordion>

<div id="2-set-inapp-event-postbacks" />

<Accordion title="2. Configurar postbacks de eventos in-app">

Puedes definir qué eventos de conversión web envía AppsFlyer a TikTok Ads asociando los eventos de AppsFlyer con los eventos de TikTok Web Ads. Estos postbacks pueden consultarse en TikTok Ads Manager, y TikTok utiliza los eventos asociados para optimizar las campañas y generar reportes.

Para configurar los postbacks de eventos in-app:

1. Activa **postbacks de eventos in-app**.
2. Si es necesario, configura la ventana de postback de eventos in-app. Leer más\n sobre la configuración de la ventana de postback de eventos in-app en\n <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">Configuración de postback de eventos in-app</Anchor>.
3. Haz clic en **Agregar evento** para añadir un evento a la lista.
4. En la columna **evento de AppsFlyer**, selecciona el nombre del evento en la lista desplegable. AppsFlyer recibe el nombre del evento desde el SDK web integrado en tu sitio web o desde los eventos server-to-server (S2S) que envías a AppsFlyer.
5. En la columna **asignado al evento de partner**, selecciona el evento de partner predefinido más adecuado.
6. En la columna **Para usuarios de**, selecciona la opción correspondiente:
   * **Solo este partner**, para enviar eventos atribuidos solo a TikTok Web Ads.
   * **Todas las fuentes de medios, incluido el tráfico orgánico**,\n para enviar todos los eventos independientemente de la fuente de atribución.
7. En la columna **incluyendo**, selecciona si los eventos se enviarán con sus valores de ingresos. Consulta <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#datos-a-incluir-en-los-postbacks">Datos que se deben incluir en los postbacks</Anchor>.

   > 📘 **Nota**
   >
   > * Si estás configurando un evento de compra, establece la columna **incluyendo** en **Valores e ingresos**. Si seleccionas cualquier otra opción, el postback fallará.
   > * Actualmente, solo el evento de compra se puede configurar para incluir ingresos.

8. [Opcional] Haz clic en el icono **Agregar condición** para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer condiciones</Anchor> para un evento.
9. Haz clic en **Guardar integración**.

> 📘 **Note**
>
> Si también ejecutas TikTok Pixel en tu sitio web, envía el mismo ID de evento tanto a AppsFlyer como a TikTok para que AppsFlyer pueda deduplicar los eventos:
>
> * Incluye `af_customer_event_id` en la carga útil del evento que envías a AppsFlyer, dentro de `eventValue` para el SDK web o `event_value` para la API S2S (server-to-server).
> * Envía el mismo valor en el evento correspondiente de Pixel.
>
> AppsFlyer reenvía este valor a TikTok como ID del evento. TikTok lo usa entonces para deduplicar el evento del servidor que recibe de AppsFlyer frente al evento de Pixel, de modo que AppsFlyer cuente la conversión una sola vez.
>
> Si no envías `af_customer_event_id`, AppsFlyer genera un ID de evento automáticamente. Este ID no coincidirá con tus eventos de Pixel.
>
> Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/integrate-appsflyer-web-sdk">[Beta] Integrar el SDK web de AppsFlyer</Anchor>.

</Accordion>

## Parte 2: Configura la integración de AppsFlyer en TikTok Web Ads

Completa los siguientes pasos en TikTok Ads Manager.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Configurar el tipo de campaña, objetivo y metas">

Puedes elegir cualquier evento in-app predefinido enviado desde AppsFlyer como objetivo de tu campaña. Selecciona un objetivo de campaña que se ajuste a tus objetivos de conversión web; por ejemplo, generar tráfico hacia tu sitio web u optimizar las conversiones en el sitio.

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. Configurar URL de destino">

1. En **Destino**, en el campo **URL del sitio web**, introduce la URL de tu sitio web, es decir, la página a la que llegan los usuarios después de hacer clic en tu anuncio.

   **URL del sitio web** es la opción de destino principal. Los usuarios hacen clic en el anuncio y llegan directamente a tu sitio web para completar eventos de conversión.
2. **[Alternativa] Enlace de atribución de AF (OneLink):** Si quieres redirigir a los usuarios a la app móvil con una redirección alternativa al sitio web, puedes utilizar un enlace de atribución de AF (OneLink) como URL de destino.
3. Haz clic en **Crear un parámetro de URL** para añadir parámetros de URL a la URL de destino.
4. En **Parámetros personalizados**, haz clic en **Agregar parámetro**.
5. Asocia los parámetros de AppsFlyer con sus valores correspondientes en TikTok:

| Parámetro de AF | Valor correspondiente en TikTok |
| --- | --- |
| `PID` | `tiktokweb_int` |
| `C` | `__campaign_name__` |
| `af_c_id` | `__campaign_id__` |
| `af_conjunto de anuncios` | `__aid_name__` |
| `af_adset_id` | `__aid__` |
| `af_anuncio` | `__cid_name__` |
| `id_del_anuncio_af` | `__cid__` |

   > 📘 **Nota**
   >
   > Para simplificar el análisis de las campañas, incluye el tipo de campaña (web o móvil) como prefijo o sufijo en el nombre de la campaña; por ejemplo, `campaign-name_web`.


   Para conocer las prácticas recomendadas sobre la configuración de parámetros de URL y la resolución de fuentes de tráfico, consulta <Anchor target="_blank" href="/marketers/es/docs/about-traffic-source-resolution">Información sobre la resolución de fuentes de tráfico</Anchor>.

   Ejemplo de una URL resultante:

   ```http
   https://www.example.com?pid=tiktokweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__
   ```

   > 📘 **Nota**
   >
   > TikTok añade automáticamente `ttclid={{ttclid}}` a la URL de destino cuando el usuario hace clic en el anuncio.


</Accordion>

## Ver datos de atribución web

Los eventos de conversión web se reportan con el PID `tiktokweb_int` en el campo `media_source`. Para ver los datos de atribución web, utiliza los reportes de raw data y filtra por `media_source = tiktokweb_int` para aislar las conversiones de aplicaciones web de TikTok.

Los reportes en el dashboard para campañas de aplicaciones web aún no están disponibles. Está previsto incorporar en una futura versión una vista unificada de reportes que te permitirá analizar el performance de las campañas web junto con el de otros canales.

## Mide el costo, los clics y las impresiones

Mide el costo, los clics y las impresiones de TikTok junto con tus datos de atribución web en el dashboard y en los reportes de Cost ETL (solo para clientes de ROI360).

1. Los datos de costos de las campañas de aplicaciones web de TikTok Ads (`tiktokglobal_int`) no se muestran en el dashboard ni en los reportes Cost ETL, excepto en el reporte **Todos los costos**.   
   Para obtener los datos de costos de TikTok para las campañas de aplicaciones web en el reporte **Todos los costos**, conecta tu cuenta publicitaria de TikTok a la integración de costos de TikTok (`tiktokglobal_int`) desde la página **Configuración de costos** o la pestaña **Costo**.
2. **Añade el ID de campaña a la URL de tu página de destino:** Incluye `af_c_id` junto con toda la jerarquía de la campaña en la URL de la página de destino. Esto garantiza que el costo, los clics y las impresiones se correspondan con tus datos de atribución web al nivel más granular.

## Características y limitaciones

| Caducado | Observaciones |
| --- | --- |
| Reengagement | Actualmente no se admite el envío de postbacks de re-engagement mediante la Events API. |

<div data-zendesk-anchors="overview=descripci%C3%B3n-general h_01KQC152Q49R7P96BPMMZGVZWS=descripci%C3%B3n-general h_01KQC25PY3PPRTQBJ7K8NV3JWQ=ver-tambi%C3%A9n h_01KQC152Q42VT7XKTGCEJV7V7S=importante prerequisites=requisitos-previos h_01KQC152Q4A31VJ1JTXWJG6CN0=requisitos-previos how-to-set-up-tiktok-ads-for-your-website-app=c%C3%B3mo-configurar-tiktok-web-ads-para-tu-aplicaci%C3%B3n-web h_01KQC152Q4S1VTK7BGWPHHD27W=c%C3%B3mo-configurar-tiktok-web-ads-para-tu-aplicaci%C3%B3n-web part-1-set-up-tiktok-ads-integration-in-appsflyer=parte-1-configura-la-integraci%C3%B3n-de-tiktok-web-ads-en-appsflyer h_01KQC152Q4J5ZCSFVM8EZ8ZBTZ=parte-1-configura-la-integraci%C3%B3n-de-tiktok-web-ads-en-appsflyer h_01KQC152Q4WDH8W6AVV679JPGS=1-activate-the-tiktok-ads-integration h_01KQC152Q492SBJMJ3J10B1R84=nota h_01KQC152Q4QWF2996MBS0BYCK7=2-set-inapp-event-postbacks h_01KQC152Q4561EWHVKB7A1AWDX=nota-1 part-2-set-up-appsflyer-integration-in-tiktok-ads=parte-2-configura-la-integraci%C3%B3n-de-appsflyer-en-tiktok-web-ads h_01KQC152Q4NKQHF75Y14XCCFNH=parte-2-configura-la-integraci%C3%B3n-de-appsflyer-en-tiktok-web-ads h_01KQC152Q4TMJ0F09Q1PZYV71A=1-set-the-campaign-type-objective-and-goals h_01KQC152Q414XNHHR0Q2B8ZCST=2-set-destination-url h_01KQC152Q4F3WQKETR34WRHACT=nota-2 h_01KQC152Q4BYHRW52BYBJHBGJ4=nota-3 view-web-attribution-data=ver-datos-de-atribuci%C3%B3n-web h_01KQC152Q45QE5M5BGD4RJNFR9=ver-datos-de-atribuci%C3%B3n-web h_01KQD9Z1XY7AB3CDE4FGHTKLM=mide-el-costo-los-clics-y-las-impresiones measure-cost-clicks-and-impressions=mide-el-costo-los-clics-y-las-impresiones traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01KQC152Q45WC7HNZ64T98JJ6Y=caracter%C3%ADsticas-y-limitaciones" />
