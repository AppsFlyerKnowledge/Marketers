---
title: >-
  Configuración de la integración de Snapchat—Web para aplicaciones de PC y
  consola
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
  created_at: '2025-11-28T12:53:35Z'
  edited_at: '2026-09-17T00:29:57Z'
  id: 41396370612497
  locale: es
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/es/articles/41396370612497
---
> **En resumen:** Aprende a integrar Snapchat Ads web para aplicaciones de PC y consola con AppsFlyer y a configurar campañas en Snapchat Ads web.

<div id="warning" />

> ❗️ **Advertencia**
>
> Esta integración solo está disponible para aplicaciones de PC y consola, como Steam, Epic o Native PC. Para aplicaciones móviles, consulta la página de <Anchor target="_blank" href="/marketers/es/docs/tiktok-for-business-advanced-srn-integration-setup">configuración de la integración de Snapchat Ads</Anchor> .

<div id="overview" />

## Visión general

Este artículo contiene información y pasos sobre cómo configurar y utilizar Snapchat Ads web para aplicaciones de PC y consola con AppsFlyer.

<div id="prerequisite" />

### Requisitos previos

Antes de activar la integración de Snapchat Ads web, asegúrate de tener una cuenta comercial en <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/topic/0TO8b000000KfssGAC/ads-manager?language=en_US">Snapchat Ads Manager.</Anchor>

<div id="activating-partner-in-appsflyer" />

## Activación del partner en AppsFlyer

**Para activar la integración de partners:**

1. En AppsFlyer, en el menú lateral, abre **Collaborate** > **Partner Integrations > Marketplace** tab.
2. Busca **Snapchat Ads web** (`snapweb_int`).
3. Haz clic **Integrar**. Se te redirige a la página de configuración.
4. En la pestaña **Integración** , activa **Activar partner**. El interruptor debe permanecer (<Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activado</Anchor>) mientras trabajes con el partner.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación.

<div id="setting-up-snapchat-ads-web-in-appsflyer" />

## Configuración de Snapchat Ads web en AppsFlyer

En esta parte de la configuración, también puedes configurar postbacks para Snapchat Ads web mediante la API de eventos de Snapchat. La integración de Snapchat Ads web (`snapweb_int`) utiliza una herramienta de API de eventos proporcionada por Snapchat Ads que permite a los anunciantes enviar datos desde sus **aplicaciones de PC y consola** directamente a los servidores de Snapchat. Dichos datos pueden incluir acciones del usuario, como compras, registros y otros tipos de conversiones realizadas en plataformas no móviles (sitios web o aplicaciones). Luego, Snapchat Ads utiliza los datos para optimizar el Ad Targeting, medir el rendimiento de los anuncios y crear audiencias personalizadas para el retargeting.

La integración con Snapchat Ads web solo admite el envío de postbacks para instalaciones y eventos in-app.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña **Integración** incluye varias secciones, como se describe a continuación.

**Activar socio**

Para configurar la integración, primero debes activar el **Activar partner** interruptor.

**Configuración general**

* **Pixel ID:** Ingresa el Pixel ID. Puedes crearlo u obtenerlo desde Snapchat Ads Manager siguiendo las instrucciones detalladas en la <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US">documentación oficial de Snapchat Ads</Anchor>[.](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US)
* **Token de acceso:** Ingresa el token de acceso. Para generarlo u obtenerlo, sigue las instrucciones [in](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US) la <Anchor target="_blank" href="https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted">documentación oficial de Snapchat Ads</Anchor>[.](https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted)

**Habilitar la atribución view-through**

AppsFlyer admite la atribución view-through para campañas de Snapchat Ads web mediante modelado probabilístico (PMOD) y una landing page habilitada con [Smart Script](#create-a-landing-page-with-onelink-smart-script) o [Smart Banner](#create-a-landing-page-with-onelink-smart-banners). Esto permite que AppsFlyer atribuya las instalaciones de aplicaciones que resultan de que los usuarios ven un anuncio y luego instalan la aplicación, incluso entre plataformas, sin necesidad de hacer clic directamente.

Cuando un usuario hace clic en un anuncio de Snapchat en la web y llega a una landing page habilitada para [Smart Script](#create-a-landing-page-with-onelink-smart-script) o [Smart Banner](#create-a-landing-page-with-onelink-smart-banners), AppsFlyer puede atribuir la instalación posterior de la aplicación. Si está disponible, el `ScCid` se incluirá en el postback a Snapchat para mejorar la fidelidad de la atribución.

**Habilitar la atribución view-through:**

1. En AppsFlyer, desde la barra lateral, abre **Integraciones activas** > **Snapchat Ads web ads**.
2. En la pestaña **Integración**, desplázate hasta la sección **Atribución de instalaciones**.
3. Activa la **Atribución view-through de instalaciones**.
4. **[opcional]** Activa la **Prioridad de atribución igualitaria cross-platform** y configura su ventana de lookback. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Habilitar prioridad igualitaria para impresiones cross-platform</Anchor>.
5. Abre la pestaña **Enlace de atribución**.
6. Desplázate hasta la sección **Atribución view-through** y configura la **ventana de lookback view-through** (hasta 24 horas).
7. Haz clic en **Guardar integración** para aplicar tu configuración.

**Postbacks predeterminados**

Los postbacks de instalaciones se envían automáticamente solo a Snapchat Ads web.

**Habilitar la atribución por impresiones**

Configura la asignación de postbacks de eventos in-app que se envían a Snapchat Ads web. Estos eventos se pueden ver en el [Snapchat Ads Manager](https://businesshelp.snapchat.com/s/topic/0TO8b000000KfssGAC/ads-manager?language=en_US).

1. Activa **Postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista. La siguiente tabla enumera y describe los campos:

| **Nombre del parámetro** | **Nota** |
| --- | --- |
| Evento de AppsFlyer | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos de servidor a servidor.<ul><li>Haz clic en Agregar elemento e introduce el nombre del evento.</li></ul> |
| Asignado al evento asociado | El ID o nombre único de cada evento, tal y como lo defina el partner.<ul><li>Selecciona de la lista el evento de socio predefinido más adecuado.</li></ul> |
| Para usuarios de | Solo este partner: Los postbacks de eventos in-app se envían solo para los eventos atribuidos a este partner. |
| Incluye | Valores e ingresos: Todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento), se envían en el postback. |

3. [Opcional] Haz clic en el **Agregar condición** icono para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">configurar condiciones</Anchor> para un evento. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">postbacks de eventos in-app condicionales</Anchor>.
4. Configura la **ventana de postback de eventos in-app**. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">Configuración de la ventana de postback de eventos in-app</Anchor>.
5. Haz clic en **Guardar integración**.
6. [Opcional] Después de guardar la integración, desde la página de configuración, puedes integrar más de tus aplicaciones con el partner:
   1. <span class="af-ol-a"></span>En la esquina superior izquierda, debajo del nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
   2. Selecciona una aplicación diferente en la lista desplegable.
   3. Repite los pasos de integración para la aplicación seleccionada.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

La generación de un enlace de atribución en la interfaz de usuario de AppsFlyer no está disponible actualmente. Puedes usar una landing page multiplataforma con SmartScript o crear un enlace de atribución directa para tu aplicación. Consulta la tabla a continuación.

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
        **Recomendado.** Usa esta opción cuando tu campaña promocione una aplicación que esté disponible en varias plataformas, como Epic y Steam.  
        <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Más información sobre las landing pages multiplataforma</Anchor>  

        <Anchor target="_blank" href="/marketers/es/docs/cross-platform-landing-pages-with-smart-script">Aprende a configurar una landing page multiplataforma</Anchor>  
        Asegúrate de que todos los parámetros de URL relevantes (que luego captura el Smart Script) se añadan a la URL del anuncio

        * Asegúrate de que el script tome el valor `ScCid` de la URL de entrada y lo añada al enlace generado. Esto significa que debes asignar el parámetro de URL saliente `ScCid` al parámetro entrante `ScCid`.  
          **Nota:** Para mostrar `ScCid` en los reportes de raw data de AppsFlyer, el parámetro entrante `ScCid` también debe asignarse a uno de los parámetros salientes `af_sub[1–5]`.
        * Opcional: Puedes usar las macros de URL dinámicas de Snapchat en lugar de codificar manualmente los valores. Para más información, consulta la [documentación oficial de Snapchat](https://businesshelp.snapchat.com/s/article/add-url-macros?language=en_US).
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
        Si no utilizas una landing page multiplataforma porque solo tienes una aplicación en una plataforma, puedes crear enlaces de atribución directa para colocarlos detrás de los anuncios.   
        <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprende a crear enlaces de atribución directa</Anchor>

        Asegúrate de que los parámetros obligatorios estén incluidos en tu enlace:

        * `media_source`
        * `af_campaign_id`
        * `af_r`

        **Plantilla que debes usar para el enlace del anuncio web de Snapchat Ads:**

        ```
        https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source=snapweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_channel={{site_source_name}}&af_r={encoded landing page and URL params}
        ```

        **Enlace de muestra de un enlace de anuncio web de Snapchat que dirige a Steam:**

        ```
        https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=snapweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
        ```

        **Nota**: La plantilla incluye algunos parámetros de URL dinámicos admitidos por Snapchat. Si lo prefieres, puedes reemplazarlos por valores reales manualmente.
      </td>
      <td>
        Comercializador
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

El costo no está disponible para Snapchat Ads web.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos publicitarios no están disponibles para Snapchat Ads Web.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Actualmente, no se conceden permisos para Snapchat Ads Web.

</Accordion>

<div id="setting-up-campaigns-in-snapchat-ads-web-for-pc-and-console-apps" />

## Configuración de campañas en Snapchat Ads Web para aplicaciones de PC y consola

Configura tu campaña en Snapchat Ads Manager. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/snapchat-create-web-based-campaigns#configurar-la-integración-de-appsflyer-en-snapchat-ads">Configurar la integración de AppsFlyer en Snapchat Ads</Anchor>.

Cuando configuras tu nueva campaña:

* Selecciona **Sitio web** como ubicación de conversión.
* Cuando nombres tu píxel de conversión de Snapchat, introduce el mismo ID de píxel que introdujiste para `snapweb_int` en *AppsFlyer Partner Marketplace*.
* Cuando ingresas la URL del sitio web como destino de tu anuncio, la URL debe ser para una de las siguientes opciones:
  * Página de aterrizaje web (recomendada cuando tienes una aplicación en múltiples plataformas)
  * URL de la tienda (se recomienda cuando tu aplicación está en una sola tienda de aplicaciones, en una sola plataforma)

<div id="view-web-to-app-attribution-data" />

## Ver datos de atribución web-to-app

Aunque los eventos de conversión web se envían a Snapchat bajo el PID original `snapweb_int`, se reportan en el Dashboard de AppsFlyer y en los Reportes de raw data bajo el PID `snapchat_int`. Esto se aplica tanto a los eventos de conversión primarios como a los eventos de asistencia a la conversión.

Esta vista unificada de reportes te permite analizar el rendimiento de campañas web y de aplicación en un solo lugar, incluidos reportes completos de costos web y móvil.

<div id="view-in-the-dashboard" />

### Ver en el dashboard

Todas las atribuciones web-to-app de Snapchat aparecen bajo `snapchat_int` en los dashboards Overview y Activity. Esto proporciona una vista única y consolidada de los resultados de campañas en todas las plataformas. Utiliza filtros y desgloses estándar para comparar el tráfico de aplicaciones y web dentro de tus datos de Snapchat Ads.

<div id="view-in-raw-data-and-api-reports" />

### Ver en reportes raw data y API

* **Las exportaciones de raw data y las respuestas de la API** incluyen el PID `snapchat_int` en el campo `media_source` para la actividad web de Snapchat. Para verificar los detalles de configuración de la campaña web, consulta el campo `original_url`, que muestra `snapweb_int` como el PID utilizado durante la creación de campañas web.
* **Los reportes de postbacks** muestran `snapweb_int` como la fuente de medios original a la que se envió el postback.

<div id="traits-and-limitations" />

## Especificaciones y limitaciones

| Caducado | Nota |
| --- | --- |
| Clics e impresiones (limitación temporal) | Los clics e impresiones de las campañas dirigidas a aplicaciones de PC & consola no están disponibles temporalmente desde Snapchat SRN. |

<div data-zendesk-anchors="h_01KB58BEK73PMXZXB8RA59YHM2=advertencia overview=visi%C3%B3n-general h_01KB58BEK78P4C35JYZXKJFPHW=visi%C3%B3n-general prerequisite=requisitos-previos h_01KB58BEK77YP1T2XCHZJ00V7S=requisitos-previos activating-partner-in-appsflyer=activaci%C3%B3n-del-partner-en-appsflyer h_01KB58BEK7A3MJT4C9ZA9ZFGDA=activaci%C3%B3n-del-partner-en-appsflyer setting-up-snapchat-ads-web-in-appsflyer=configuraci%C3%B3n-de-snapchat-ads-web-en-appsflyer h_01KB58BEK7CGYB1DZJCG2WMH0Y=configuraci%C3%B3n-de-snapchat-ads-web-en-appsflyer h_01KB58BEK7SE837F67MKRFY6K2=integration-tab h_01KB58BEK74Q2K3SNCPFQSCJ2B=attribution-link-tab h_01KB58BEK7WAVABV4YBR728FCF=cost-tab h_01KB58BEK7ESEZFARRQ3HB6P8H=ad-revenue-tab h_01KB58BEK7WXEFMSSB0QRE4E6B=permissions-tab setting-up-campaigns-in-snapchat-ads-web-for-pc-and-console-apps=configuraci%C3%B3n-de-campa%C3%B1as-en-snapchat-ads-web-para-aplicaciones-de-pc-y-consola h_01KB58BEK7D8760J2ZWJ9B1K3Y=configuraci%C3%B3n-de-campa%C3%B1as-en-snapchat-ads-web-para-aplicaciones-de-pc-y-consola view-webtoapp-attribution-data=ver-datos-de-atribuci%C3%B3n-web-to-app h_01KB58BEK7M96WYN7YMERH7CWW=ver-datos-de-atribuci%C3%B3n-web-to-app view-in-the-dashboard=ver-en-el-dashboard h_01KB58BEK70FB5SYQAV938CB5W=ver-en-el-dashboard view-in-raw-data-and-api-reports=ver-en-reportes-raw-data-y-api h_01KB58BEK7YWM10A7RCNV7YDEM=ver-en-reportes-raw-data-y-api traits-and-limitations=especificaciones-y-limitaciones h_01KB58BEK7MDZGT7G7RQ9VK9MZ=especificaciones-y-limitaciones" />
