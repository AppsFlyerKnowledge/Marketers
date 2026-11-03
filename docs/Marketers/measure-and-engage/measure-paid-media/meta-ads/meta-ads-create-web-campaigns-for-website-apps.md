---
title: 'Meta Ads: crea campañas web para aplicaciones web'
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
  created_at: '2026-04-28T14:18:14Z'
  edited_at: '2026-10-20T03:48:33Z'
  id: 46172666260241
  locale: es
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/es/articles/46172666260241
---
> **At a glance:** Configura una integración de Meta Ads para la app de tu sitio web a fin de enviar señales de conversión web a Meta mediante la Conversions API (CAPI). Meta utiliza estas señales para optimizar el targeting de anuncios y medir la performance de la campaña.

## Descripción general

AppsFlyer admite la integración con Meta Ads (`metaweb_int`) para campañas de aplicaciones web. La integración te permite reportar datos de atribución y conversión directamente mediante la Conversions API (CAPI) de Meta, que Meta utiliza para optimizar la segmentación de anuncios, medir el performance y crear audiencias personalizadas.

Así es como funciona: un usuario hace clic en un anuncio de Meta y llega a tu sitio web. AppsFlyer registra los eventos de conversión que complete el usuario, como una compra o un registro, y envía esa señal a Meta mediante CAPI. Meta utiliza estos datos para perfeccionar la segmentación y evaluar los resultados de las campañas.

> 📘 **Nota**
>
> La integración actual de Meta Web no admite el envío de postbacks de re-engagement a CAPI.

### Requisitos previos

Antes de activar la integración de Meta Ads, asegúrate de tener lo siguiente:

* Una aplicación web configurada en AppsFlyer. Para más información, consulta:
  * <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer#web">Añadir una aplicación web</Anchor>
  * <Anchor target="_blank" href="/marketers/es/docs/configure-web-performance-measurement-settings">Configurar los ajustes de atribución web de AppsFlyer</Anchor>
* Una <Anchor target="_blank" href="https://www.facebook.com/business/help/1710077379203657?id=180505742745347">cuenta empresarial en Meta Business Manager</Anchor>.

## Configura campañas web de Meta Ads para aplicaciones web

La configuración consiste en definir la integración entre Meta Ads y AppsFlyer y configurar la campaña en ambas plataformas. Completa ambas partes en orden.

* [Parte 1: Configura la integración de Meta Ads en AppsFlyer](#parte-1-configura-la-integración-de-meta-ads-en-appsflyer) (obligatorio)
* [Parte 2: Configura la integración de AppsFlyer en Meta Ads](#parte-2-configurar-la-integración-de-appsflyer-en-anuncios-de-meta) (obligatorio)

## Parte 1: Configura la integración de Meta Ads en AppsFlyer

Para empezar, activa la integración de Meta Ads y configura los postbacks que AppsFlyer envía a CAPI.

<div id="step-1-activate-the-meta-ads-integration" />

<Accordion title="Paso 1: Activa la integración de Meta Ads">

Para activar la integración de Meta Ads:

1. En AppsFlyer, en el menú lateral, ve a **Colaborar** > **Partner Marketplace**.
2. Busca **Meta Ads** y selecciónalo.
3. Haz clic en **Configurar integración**. Se te redirigirá a la página de configuración de **Integraciones activas**.
4. En la pestaña **Integración**, selecciona **Activar partner**.

   > 📘 **Nota**
   >
   > El interruptor debe permanecer (<Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activado</Anchor>) mientras trabajes con el partner.

5. Completa el campo **ID del píxel**. Para obtener el ID del píxel desde Meta Ads Manager:
   1. En el menú lateral de <Anchor target="_blank" href="https://www.facebook.com/ads/manager">Administrador de anuncios</Anchor>, ve a **Todas las herramientas** > **Administrador de eventos**.

      > 📘 **Nota**
      >
      > Asegúrate de haber seleccionado la empresa correcta en el menú desplegable de la esquina superior derecha.

   2. En el menú lateral del **Administrador de eventos** selecciona **Fuentes de datos**. Verás una lista de tus píxeles. Si no tienes un píxel para la empresa seleccionada, puedes crear uno desde esa misma vista.
   3. Copia el ID del píxel que aparece debajo del nombre del píxel y pégalo en el campo **ID del píxel** de AppsFlyer.
6. Completa el campo **Token de acceso**. Para obtener el token de acceso, sigue <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token">estas instrucciones</Anchor>.
7. Activa **Limitar el uso que Meta Ads hace de la información personal de los usuarios (CCPA)** para cumplir con las <Anchor target="_blank" href="/marketers/es/docs/send-opendsr-api-requests">leyes de protección de datos</Anchor>.

   > 📘 **Nota**
   >
   > Cumplir con las regulaciones de privacidad de la CCPA limita los datos provenientes de los usuarios de Anuncios de Meta que residen en California, EE. UU.


</Accordion>

<div id="step-2-set-inapp-event-postbacks" />

<Accordion title="Paso 2: Configurar postbacks de eventos in-app">

Puedes definir qué eventos de conversión web envía AppsFlyer a Meta Ads asociando los eventos de AppsFlyer con los eventos de Meta Ads. Estos postbacks pueden consultarse en el <Anchor target="_blank" href="https://www.facebook.com/business/help/1541268312717919?id=818859032317965">Administrador de eventos de Meta</Anchor>. Meta utiliza los eventos asociados para optimizar las campañas y generar reportes.

Para configurar los postbacks de eventos in-app:

1. Activa **postbacks de eventos in-app**.
2. Si es necesario, configura la ventana de postback de eventos in-app. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">Configuración de la ventana de postback de eventos in-app</Anchor>.
3. Haz clic en **Agregar evento** para añadir un evento a la lista.
4. En la columna **Evento de AppsFlyer**, selecciona el nombre del evento en el menú desplegable. AppsFlyer recibe el nombre del evento desde el SDK web integrado en tu sitio web o desde los eventos server-to-server (S2S) que envías a AppsFlyer.
5. En la columna **Asignado al evento de partner**, selecciona en la lista desplegable el evento de partner predefinido más adecuado o selecciona **PERSONALIZADO**.
6. En la columna **Para usuarios de**, selecciona la opción de envío del evento:
   * **Solo este partner**: Envía postbacks solo cuando este evento se atribuya a Meta Ads.
   * **Todas las fuentes de medios, incluidas las orgánicas**: Envía postbacks para los eventos atribuidos a cualquier partner y para los eventos orgánicos.
7. En la columna **Incluyendo**, selecciona si los eventos se envían con sus valores de ingresos. Consulta <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#datos-a-incluir-en-los-postbacks">Datos a incluir en los postbacks</Anchor>.

   > 🚧 **¡Importante!**
   >
   > Si estás configurando un evento de compra, configura la columna **Incluyendo** en **Valores e ingresos**. Seleccionar cualquier otra opción hará que el postback falle.

8. [Opcional] Haz clic en el icono **Agregar condición** para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer condiciones</Anchor> para un evento.
9. Haz clic en **Guardar integración**.

> 📘 **Note**
>
> Si también ejecutas el Meta Pixel en tu sitio web, envía el mismo ID de evento tanto a AppsFlyer como a Meta para que AppsFlyer pueda deduplicar los eventos:
>
> * Incluye `af_customer_event_id` en el payload del evento que envías a AppsFlyer. En el caso del SDK web, envíalo dentro de `eventValue`. En la API S2S (server-to-server), envíalo como un campo de nivel superior o dentro de `event_value`.
> * Envía el mismo valor en el evento de Pixel correspondiente.
>
> AppsFlyer reenvía este valor a Meta como ID del evento. Meta lo utiliza después para deduplicar el evento del servidor que recibe de AppsFlyer con el evento de Pixel, de modo que AppsFlyer cuente la conversión una sola vez.
>
> Si no envías `af_customer_event_id`, AppsFlyer genera un ID de evento automáticamente. Este ID no coincidirá con tus eventos de Pixel.
>
> Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/integrate-appsflyer-web-sdk">[beta] Integrate AppsFlyer Web SDK</Anchor>.

> 📘 **Nota**
>
> Si envías eventos S2S y quieres que AppsFlyer envíe postbacks para Meta Ads, asegúrate de que cada evento incluya al menos uno de estos campos: `ip`, `user_agent` o `customer_user_id`. Si faltan los tres, AppsFlyer no envía el postback. Para ver todos los campos de evento compatibles, consulta <Anchor target="_blank" href="/marketers/es/docs/server-to-server-s2s-api-for-web-performance-measurement#medir-un-evento">Server-to-Server (S2S) API for Web Performance Measurement</Anchor>.

</Accordion>

## Parte 2: Configurar la integración de AppsFlyer en Anuncios de Meta

Completa los siguientes pasos en Meta Ads Manager.

<div id="step-1-set-the-campaign-type-objective-and-goals" />

<Accordion title="Paso 1: Configurar el tipo de campaña, objetivo y metas">

1. Inicia sesión en Meta Ads y crea una campaña.
2. En **Objetivo de la campaña**, selecciona una de las siguientes opciones:
   * **Ventas**: Permite que Meta optimice hacia un evento específico (tu KPI principal).
   * **Tráfico**: Permite que Meta optimice hacia clics en anuncios. Utiliza esta opción solo si no tienes otros KPIs o si el volumen de eventos correspondientes a otros KPIs es demasiado bajo.
3. [Opcional] Para añadir un objetivo personalizado, haz lo siguiente:

   1. En Meta Ads, selecciona el evento personalizado que quieras establecer como objetivo de la campaña y márcalo como acción de conversión.
   2. En AppsFlyer, en la página **integración de Meta Web**, en **Postback de eventos in-app**, asigna un evento de AppsFlyer a un evento de partner personalizado en la columna **Mapped to partner event**. Asígnale el mismo nombre que la acción de conversión en Meta Ads.

   > 📘 **Nota**
   >
   > Para más información sobre los objetivos de campaña de Meta, consulta la <Anchor target="_blank" href="https://www.facebook.com/business/help/175683976191028">documentación de Meta</Anchor>.

4. En **Ubicación de la conversión**, selecciona **Sitio web**.
5. En **Píxel**, introduce el mismo ID del píxel que introdujiste para `metaweb_int` en AppsFlyer Partner Marketplace. Para más información sobre Meta Pixel, consulta la <Anchor target="_blank" href="https://www.facebook.com/business/help/742478679120153">documentación de Meta</Anchor> (es necesario iniciar sesión).
6. Haz clic en **Siguiente**.

</Accordion>

<div id="step-2-set-destination-url" />

<Accordion title="Paso 2: Configurar URL de destino">

1. En **Destino**, en el campo **URL del sitio web**, introduce la URL que servirá como destino de tu anuncio. Elige una de las siguientes opciones:

   * **URL del sitio web**: Utiliza la URL de tu sitio web cuando quieras que los usuarios lleguen directamente a él y completen eventos de conversión web, como una compra o un registro.
   * **Enlace de atribución de AF (OneLink)**: Utiliza un enlace de atribución de AF cuando quieras redirigir a los usuarios a tu app móvil, con una redirección alternativa a tu sitio web si la app no está instalada. Esto resulta útil cuando tu campaña se dirige tanto a usuarios de la aplicación como a usuarios de la web. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">los enlaces y experiencias de OneLink</Anchor> .

   > 🚧 **¡Importante!**
   >
   > En algunos casos, el uso de enlaces de atribución de AF puede provocar errores. Si esto ocurre, consulta con tu representante de Meta para encontrar una solución o utiliza la URL de tu sitio web como URL de destino.

2. Haz clic en **Crear un parámetro de URL** para añadir parámetros de URL a la URL de destino.
3. En **Parámetros personalizados**, haz clic en **Agregar parámetro**.
4. Asocia los parámetros de AppsFlyer con sus valores correspondientes en Meta, como se muestra en la siguiente tabla:

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

Ejemplo de una URL resultante:

```http
https://www.example.com?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}
```

> 📘 **Nota**
>
> Meta añade automáticamente `fbclid={{fbclid}}` a la URL de destino cuando el usuario hace clic en el anuncio.

> 👍 **Consejo**
>
> Para simplificar el análisis de las campañas, incluye el tipo de campaña (web o móvil) como prefijo o sufijo en el nombre de la campaña; por ejemplo, `campaign-name_web`.

> 📄 **Consulta también**
>
> * Para conocer las prácticas recomendadas para crear la URL de tu anuncio con todos los parámetros pertinentes, consulta <Anchor target="_blank" href="/marketers/es/docs/about-traffic-source-resolution">Información sobre la resolución de fuentes de tráfico</Anchor>.

</Accordion>

<div id="step-3-select-tracked-events" />

<Accordion title="Paso 3: Seleccionar eventos supervisados">

Utiliza la sección **Seguimiento** para seleccionar los eventos de conversión promocionados por tu anuncio. Configura los eventos mediante el <Anchor target="_blank" href="https://www.facebook.com/business/help/898185560232180?id=1205376682832142">Administrador de eventos</Anchor>.

> 🚧 **¡Importante!**
>
> No selecciones **Eventos de la app**. Si lo haces, Meta atribuirá esas conversiones mediante la API de SRN, lo que puede provocar discrepancias en los reportes y la optimización.

</Accordion>

## Ver datos de atribución web

Esto es lo que puedes esperar al revisar los datos de atribución después de la configuración:

* **Dashboard:** En <Anchor target="_blank" href="/marketers/es/docs/my-dashboards#crossplatform-dashboard">el dashboard multiplataforma</Anchor>, los datos web y de la app se muestran uno al lado del otro, lo que te ofrece una vista unificada del rendimiento de las campañas en todas las plataformas.
* Las **exportaciones de raw data y las respuestas de la API** incluyen Meta Web en el campo `media_source` para la actividad web de Meta.

## Medir datos de atribución web con costo web

Puedes obtener una vista completa del rendimiento de los datos de atribución web y los datos de costo de Meta Ads en el dashboard y en los <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">reportes de Cost ETL</Anchor>. Para hacerlo, asegúrate de tener <Anchor target="_blank" href="/marketers/es/docs/roi360-onboarding-guide#sobre-roi360">el paquete ROI360</Anchor> y completa la siguiente configuración:

1. Conecta el costo a tu aplicación web mediante `facebook_int` (no mediante `metaweb_int`) desde la pestaña **Costo** o la página **Configuración de costos**. Para más información sobre cómo conectar el costo, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enabling-cost-api">Configurar la API de costos de ROI360 para medir los datos de costos</Anchor>.
2. Incluye el ID de la campaña (`af_c_id`) en la URL de la landing page. Asegúrate de que la URL incluya la jerarquía completa de la campaña para ver los costos, clics e impresiones asociados a la atribución web con el mayor nivel de detalle posible.

## Características y limitaciones

| Caducado | Observaciones |
| --- | --- |
| Clics e impresiones | Los clics y las impresiones de las campañas web requieren una <Anchor target="_blank" href="/marketers/es/docs/roi360-onboarding-guide">suscripción a ROI360</Anchor>. |
| Reengagement | Actualmente no se admite el envío de postbacks de re-engagement a través de CAPI. |

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/web-performance-measurement-overview">Medición del rendimiento web: descripción general</Anchor>

<div data-zendesk-anchors="overview=descripci%C3%B3n-general h_01KQA78RE9FRENQAK31Q641C0N=descripci%C3%B3n-general h_01KQA78RE9F82ZBVF4YZHZTEEX=nota prerequisites=requisitos-previos h_01KQA78RE93B09A9YH2FRB3XRR=requisitos-previos set-up-meta-ads-web-campaigns=configura-campa%C3%B1as-web-de-meta-ads-para-aplicaciones-web h_01KQA78RE9J681CJ8DQNWJC37H=configura-campa%C3%B1as-web-de-meta-ads-para-aplicaciones-web part-1-set-up-meta-ads-integration-in-appsflyer=parte-1-configura-la-integraci%C3%B3n-de-meta-ads-en-appsflyer h_01KQA78RE93JYCV2P0DDZC0A4B=parte-1-configura-la-integraci%C3%B3n-de-meta-ads-en-appsflyer h_01KQA78RE94B1JSVJFWR1V9QE5=step-1-activate-the-meta-ads-integration h_01KQA78REA5VN1229F2J3QH794=nota-1 h_01KQA78REANHAQ88N4MXWM832D=nota-2 h_01KQA78REA08SNB0BKCJDJZ2R0=nota-3 h_01KQA78REACR7QTMQWJMV6VJSF=step-2-set-inapp-event-postbacks h_01KQA78REA1EB5ZHX4HKJSW7ZD=importante h_01M520Y7YQYY70W2S24N2AXRG4=nota-4 part-2-set-up-appsflyer-integration-in-meta-ads=parte-2-configurar-la-integraci%C3%B3n-de-appsflyer-en-anuncios-de-meta h_01KQA78REAEZQPDSKZ0GRNKEJJ=parte-2-configurar-la-integraci%C3%B3n-de-appsflyer-en-anuncios-de-meta h_01KQA78REASX8JX1H37075WT82=step-1-set-the-campaign-type-objective-and-goals h_01KQA78REA5JZ44C4BE77JCHG8=nota-5 h_01KQA78REAKBGQRC713FZ3J02P=step-2-set-destination-url h_01KQA78REAXZ1BFGC5BR75ZB5X=importante-1 h_01KQA78REARWGQDCJ4KN3FM120=nota-6 h_01KQA78REA7MZSG5JZ1XX2C65P=consejo h_01KQA78REA3ZW7W9M3VFSQASB6=consulta-tambi%C3%A9n h_01KQA78REASTZH19CM58M5Z43R=step-3-select-tracked-events h_01KQA78REBHCR1AHA254BTFZC6=importante-2 view-web-attribution-data=ver-datos-de-atribuci%C3%B3n-web h_01KQA78REBK1PWXNA1PM9118TA=ver-datos-de-atribuci%C3%B3n-web measure-web-attribution-data-with-web-cost=medir-datos-de-atribuci%C3%B3n-web-con-costo-web h_01KNM00RR9TF8JRTJXWN23MF1S=medir-datos-de-atribuci%C3%B3n-web-con-costo-web traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01KQAE3JKMQ6ZEATDAEXBC4PT6=caracter%C3%ADsticas-y-limitaciones h_01KQC27K5KWP3A6HMM2W7N3MVB=consulta-tambi%C3%A9n-1" />
