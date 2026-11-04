---
title: >-
  Configuración de la integración web de TikTok for Business para aplicaciones
  de PC y consola
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2025-10-31T13:58:16Z'
  edited_at: '2026-09-17T00:30:11Z'
  id: 40500157955601
  locale: es
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/es/articles/40500157955601
---
> **En resumen:** Aprende a integrar TikTok Web para aplicaciones de PC y consola con AppsFlyer y a configurar campañas en TikTok Web.

<div id="warning" />

> ❗️ **Advertencia**
>
> Esta integración solo está disponible para aplicaciones de PC y consola, como Steam, Epic o Native PC. Para aplicaciones móviles, consulta la página de <Anchor target="_blank" href="/marketers/es/docs/tiktok-for-business-advanced-srn-integration-setup">configuración de la integración de anuncios de TikTok</Anchor> .

<div id="overview" />

## Visión general

Este artículo contiene información e instrucciones sobre cómo configurar y usar TikTok Web para aplicaciones de PC y consola con AppsFlyer.

<div id="prerequisite" />

### Requisitos previos

Antes de activar la integración de TikTok Web, asegúrate de tener una cuenta comercial en TikTok Ads Manager.

<div id="activating-partner-in-appsflyer" />

## Activación del partner en AppsFlyer

**Para activar la integración de partners:**

1. En AppsFlyer, desde el menú lateral, abre **Collaborate** > **Partner Integrations > Marketplace** tab.
2. Busca **TikTok Web** (`tiktokweb_int`).
3. Haz clic **Integrate**. Se te dirige a la página de configuración.
4. En la pestaña **Integración** , activa **Activar partner**. El interruptor debe permanecer (<Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activado</Anchor>) mientras trabajes con el partner.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación.

<div id="setting-up-tiktok-web-in-appsflyer" />

## Configuración de TikTok Web en AppsFlyer

En esta parte de la configuración, también puedes configurar postbacks para TikTok Web a través de la API de eventos de TikTok. La integración de TikTok Web (tiktokweb\_int) utiliza una herramienta API de eventos proporcionada por TikTok Ads para que los anunciantes envíen datos desde sus **aplicaciones de PC y consola** directamente a los servidores de TikTok. Dichos datos pueden incluir acciones del usuario, como compras, registros y otros tipos de conversiones realizadas en plataformas no móviles (sitios web o aplicaciones). Luego, TikTok Ads utiliza los datos para optimizar la segmentación de anuncios, medir el rendimiento de los anuncios y crear audiencias personalizadas para el retargeting.

La integración con TikTok Web solo admite el envío de postbacks para instalaciones y eventos in-app.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña **Integración** incluye varias secciones, como se describe a continuación.

<div id="activate-partner" />

#### Activar socio

Para configurar la integración, primero debes activar el **Activar partner** interruptor.

<div id="general-settings" />

#### Configuración general

* **Pixel ID:** Ingresa el Pixel ID. Puedes generarlo u obtenerlo desde TikTok Ads Manager siguiendo las instrucciones detalladas [AQUÍ](https://business-api.tiktok.com/portal/docs?id=1771100865818625).
* **Token de acceso:** Ingresa el token de acceso. Para generarlo u obtenerlo, sigue [estas instrucciones](https://business-api.tiktok.com/portal/docs?id=1771100865818625)
* **Limitar el uso que TikTok Ads hace de la información personal de los usuarios (CCPA):** Activa este interruptor para habilitar el cumplimiento de las <Anchor target="_blank" href="/marketers/es/docs/send-opendsr-api-requests">leyes de protección de datos</Anchor>.

  <div id="note" />

  > 📘 **Nota:**
  >
  > El cumplimiento de la normativa de privacidad de la CCPA limita los datos procedentes de los usuarios de TikTok Ads ubicados en California u otros estados sensibles de EE. UU.


<div id="enable-view-through-attribution" />

#### Habilitar la atribución view-through

AppsFlyer admite la atribución view-through para campañas de TikTok Web mediante modelado probabilístico (PMOD) y una [Smart Script](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21) o [Smart Banner](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21)-enabled landing page. Esto permite que AppsFlyer atribuya las instalaciones de aplicaciones que resultan de que los usuarios ven un anuncio y luego instalan la aplicación, incluso entre plataformas, sin necesidad de hacer clic directamente.

Cuando un usuario hace clic en un anuncio de TikTok Web y llega a una [Smart Script](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21) o [Smart Banner](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21)-enabled landing page, AppsFlyer puede atribuir la instalación posterior de la aplicación. Si está disponible, el `ttclid` se incluirá en el postback a TikTok para mejorar la fidelidad de la atribución.

Habilitar la atribución view-through:

1. En AppsFlyer, en el menú lateral, abre **Collaborate** > **Partner Integrations** > **Active Integrations** > **TikTok web ads**.
2. En la pestaña **Integración**, desplázate hasta la sección **Atribución de instalaciones**.
3. Activa la **Atribución view-through de instalaciones**.
4. **[opcional]** Activa la **Prioridad de atribución igualitaria cross-platform** y configura su ventana de lookback. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Habilitar prioridad igualitaria para impresiones cross-platform</Anchor>.
5. Abre la pestaña **Enlace de atribución**.
6. Desplázate hasta la sección **Atribución view-through** y configura la **ventana de lookback view-through** (hasta 24 horas).
7. Haz clic en **Guardar integración** para aplicar tu configuración.

<div id="default-postbacks" />

#### Postbacks predeterminados

Los postbacks de las instalaciones se envían automáticamente solo a TikTok Web.

<div id="in-app-event-postbacks" />

#### Habilitar la atribución por impresiones

Configura la asignación de postbacks de eventos in-app enviados a TikTok Web. Estos eventos se pueden ver en el TikTok Ads Manager

1. Activa **Postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista. La siguiente tabla describe los campos que debes completar:

| **Nombre del parámetro** | **Nota** |
| --- | --- |
| Evento de AppsFlyer | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos de servidor a servidor.<ul><li>Haz clic en Agregar elemento, escribe el nombre del evento y haz clic.</li></ul> |
| Asignado al evento asociado | El nombre o ID único de cada evento, tal como lo define el partner.<ul><li>Selecciona en el menú desplegable el evento predefinido para Partners más adecuado</li></ul> |
| Para usuarios de | Solo para este socio: Los postbacks de eventos in-app se envían solo para eventos atribuidos a este socio, es decir, el usuario que lo realizó vino de este socio. |
| Incluye | Valores e ingresos: Todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento), se envían en el postback. |

3. [Opcional] Haz clic en el ícono **Add condition** icon to <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">set conditions</Anchor> for an event.
4. Establece la **ventana de postbacks de eventos in-app**, si es necesario (lee más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">configuración de la ventana de postbacks de eventos in-app</Anchor>).
5. Haz clic en **Guardar integración**.
6. [Opcional] Después de guardar la integración, desde la página de configuración, puedes integrar más de tus aplicaciones con el partner:
   1. <span class="af-ol-a"></span>En la esquina superior izquierda, debajo del nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
   2. Selecciona una aplicación diferente en la lista desplegable.
   3. Repite los pasos de integración para la aplicación seleccionada.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

La generación de un enlace de atribución en la interfaz de usuario de AppsFlyer no está disponible actualmente. Sin embargo, puedes usar una página de aterrizaje multiplataforma con SmartScript o crear un enlace de atribución directa para tu aplicación (consulta la tabla a continuación).

<Table>
  <thead>
    <tr>
      <th>
        Opción
      </th>
      <th>
        Acciones
      </th>
      <th>
        ¿Quién participa?
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Landing page multiplataforma
      </td>
      <td>
        **Recomendado**: Para cuando tu campaña promociona una aplicación que también está disponible en múltiples plataformas, como Epic y Steam.  
        <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Más información sobre las páginas de destino multiplataforma</Anchor>  
        <Anchor target="_blank" href="/marketers/es/docs/cross-platform-landing-pages-with-smart-script">Aprende a configurar una página de destino multiplataforma</Anchor>

        * Asegúrate de que todos los parámetros de URL relevantes (que luego son capturados por Smart Script) se anexen a la URL del anuncio.
        * Asegúrate de que el script tome TTCLID de la URL entrante y lo agregue al enlace generado. Es decir, asigna el parámetro de URL saliente TTCLID URL param ttclid to the incoming URL param ttclid.   
          [Práctica recomendada]: Para mostrarlo en los reportes de raw data de AppsFlyer, el parámetro entrante ttclid param must also mapped to one of the outgoing params  `af_sub[1-5]`.
        * Opcional: Utiliza las macros de URL dinámicas de TikTok en lugar de codificar manualmente los valores. [Saber más](https://ads.tiktok.com/help/article/track-offsite-web-events-with-utm-parameters)
      </td>
      <td>
        Marketer (puede requerir la asistencia del desarrollador)
      </td>
    </tr>
    <tr>
      <td>
        Enlace de atribución directa
      </td>
      <td>
        Si no utilizas una landing page multiplataforma porque solo tienes 1 aplicación en 1 plataforma, puedes crear enlaces de atribución directa para colocarlos detrás de los anuncios.   
        <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprende a crear enlaces de atribución directa</Anchor>

        * Asegúrate de que los parámetros obligatorios estén incluidos en tu enlace:
          * `media_source`
          * `af_campaign_id`
          * `af_r`
        * Utiliza las siguientes macros recomendadas para el parámetro `af_os_version`:
          * Clic: `__OS_VERSION__`
          * Impresión: `__TPL_OS_VERSION__`

        Plantilla a utilizar para el enlace del anuncio de TikTok Web:

        ```http
        https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source=tiktokweb_int&af_campaign_id=__CAMPAIGN_ID__&af_campaign=__CAMPAIGN_NAME__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_r={encoded landing page and URL params}&af_os_version=__TPL_OS_VERSION__
        ```

        Enlace de muestra de un enlace de anuncio de TikTok Web que conduce a Steam:

        ```http
        https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=tiktokweb_int&af_campaign_id=__CAMPAIGN_ID__&af_campaign=__CAMPAIGN_NAME__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello&af_os_version=__OS_VERSION__
        ```

        **Nota**: La plantilla incluye algunos parámetros de URL dinámicos admitidos por TikTok. Si lo prefieres, puedes reemplazarlos por valores reales manualmente.
      </td>
      <td>
        Comercializador
      </td>
    </tr>
  </tbody>
</Table>

<div id="tip" />

> 👍 **Consejo**
>
> Para simplificar el análisis de campañas, incluye el tipo de campaña, web o móvil, como prefijo o sufijo en el nombre de la campaña (por ejemplo, campaign-name\_web)

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

El costo no está disponible para TikTok Web.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no están disponibles para TikTok Web.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Actualmente, no se otorgan permisos a TikTok Web.

</Accordion>

<div id="setting-up-campaigns-in-tiktok-web-for-pc-and-console-apps" />

## Configuración de campañas en TikTok Web para aplicaciones de PC y consola

Cuando configuras tu nueva campaña:

* Selecciona **Website** como ubicación de conversión.
* Cuando nombres tu píxel de conversión de TikTok, introduce el mismo ID de píxel que introdujiste para `tiktokweb_int` en el *AppsFlyer Partner Marketplace*.
* Cuando ingresas la URL del sitio web como destino de tu anuncio, la URL debe ser para una de las siguientes opciones:
  * Página de aterrizaje web (recomendada cuando tienes una aplicación en múltiples plataformas)
  * URL de la tienda (se recomienda cuando tu aplicación está en una sola tienda de aplicaciones, en una sola plataforma)

<div id="view-web-to-app-attribution-data" />

## Ver datos de atribución web-to-app

Aunque los eventos de conversión basados en web se envían a TikTok con el PID original `tiktokweb_int`, se reportan en el dashboard de AppsFlyer y en los reportes de raw data con el PID `tiktokglobal_int`. Esto se aplica tanto a los eventos de conversión primarios como a los eventos de asistencia a la conversión.

Esta vista unificada de reportes te permite analizar el rendimiento de campañas web y app en un solo lugar, incluidos reportes completos de costos web y móvil.

<div id="view-in-the-dashboard" />

### Ver en el dashboard

Todas las atribuciones Web-to-app de TikTok aparecen en `tiktokglobal_int` en los dashboards de resumen y actividad. Esto proporciona una vista única y consolidada de los resultados de campañas en todas las plataformas. Utiliza filtros y desgloses estándar para comparar el tráfico de la app y de la web dentro de tus datos de TikTok Ads.

<div id="view-in-raw-data-and-api-reports" />

### Ver en reportes raw data y API

Las exportaciones de raw data y las respuestas de la API incluyen el PID `tiktokglobal_int` en el campo `media_source` para la actividad web de TikTok. Para verificar los detalles de configuración de la campaña web, consulta el campo `original_url`, que muestra el PID `tiktokweb_int` utilizado durante la creación de la campaña web.

<div id="traits-and-limitations" />

## Especificaciones y limitaciones

| Caducado | Nota |
| --- | --- |
| Clics e impresiones (limitación temporal) | Los clics e impresiones de las campañas dirigidas a apps de PC & consola no están disponibles temporalmente en TikTok SRN. |

<div data-zendesk-anchors="h_01K8X90869H29Q9N873FAT8BM4=advertencia overview=visi%C3%B3n-general h_01K8X90869QTX2RG0KHHM8EHAT=visi%C3%B3n-general prerequisite=requisitos-previos h_01K8X9086AJ6B9BKNF0EZQASCJ=requisitos-previos activating-partner-in-appsflyer=activaci%C3%B3n-del-partner-en-appsflyer h_01K8X9086ADTE56DR3MK8MXAFR=activaci%C3%B3n-del-partner-en-appsflyer setting-up-tiktok-web-in-appsflyer=configuraci%C3%B3n-de-tiktok-web-en-appsflyer h_01K8X9086AMHZR7GADTH8N07DZ=configuraci%C3%B3n-de-tiktok-web-en-appsflyer h_01K8X9086AHN8761VPM4QA7E6S=integration-tab activate-partner=activar-socio h_01K8XAAM5SH1XXNX0DNGGS5NHT=activar-socio general-settings=configuraci%C3%B3n-general h_01K8XAATC3M5NW722QD93DRN94=configuraci%C3%B3n-general h_01K8X9086A2FFDCRE2JHXQHGET=nota enable-viewthrough-attribution=habilitar-la-atribuci%C3%B3n-view-through h_01K8XAB2SK68WTGYZY7EGHR4SZ=habilitar-la-atribuci%C3%B3n-view-through default-postbacks=postbacks-predeterminados h_01K8XABK08NCFQSRN41ASKQ7SY=postbacks-predeterminados inapp-event-postbacks=habilitar-la-atribuci%C3%B3n-por-impresiones h_01K8XAC3NAYY8S012K2W60TKBJ=habilitar-la-atribuci%C3%B3n-por-impresiones h_01K8X9086A001XKD94G50XY708=attribution-link-tab h_01K88N0TDSFDX5J22YWZPF2J1N=consejo h_01K8X9086AFH7J75J9K1QRV1DR=cost-tab h_01K8X9086ACM5WBH6GW243A0PZ=ad-revenue-tab h_01K8X9086AEHV42XZZKA0ATBH2=permissions-tab setting-up-campaigns-in-tiktok-web-for-pc-and-console-apps=configuraci%C3%B3n-de-campa%C3%B1as-en-tiktok-web-para-aplicaciones-de-pc-y-consola h_01K8X9086AARVTEDRMQW32BABF=configuraci%C3%B3n-de-campa%C3%B1as-en-tiktok-web-para-aplicaciones-de-pc-y-consola TikTok-view=ver-datos-de-atribuci%C3%B3n-web-to-app view-webtoapp-attribution-data-from-november-2-2025=ver-datos-de-atribuci%C3%B3n-web-to-app h_01K88J8JFNEYBZNR18133NMRP9=ver-datos-de-atribuci%C3%B3n-web-to-app view-in-the-dashboard=ver-en-el-dashboard h_01K88J8JFNMHCVZ0C34E3D7AST=ver-en-el-dashboard view-in-raw-data-and-api-reports=ver-en-reportes-raw-data-y-api h_01K88J8JFN8W2572N92466YFZQ=ver-en-reportes-raw-data-y-api traits-and-limitations=especificaciones-y-limitaciones h_01KB58BEK7MDZGT7G7RQ9VK9MZ=especificaciones-y-limitaciones" />
