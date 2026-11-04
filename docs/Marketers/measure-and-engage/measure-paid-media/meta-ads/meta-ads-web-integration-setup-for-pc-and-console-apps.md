---
title: Configuración de la integración de Meta Web para aplicaciones de PC y consola
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
  created_at: '2023-09-20T09:54:52Z'
  edited_at: '2026-09-17T00:28:28Z'
  id: 18704273772689
  locale: es
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/es/articles/18704273772689
---
> **En resumen:** Aprende a integrar Meta Web para aplicaciones de PC y consola con AppsFlyer y a configurar campañas en Meta Web.

<div id="important" />

> 🚧 **¡Importante!**
>
> Esta integración solo está disponible para aplicaciones de PC y consola, como Steam, Epic o Native PC. Para aplicaciones móviles, consulta la página de <Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup">configuración de la integración de Meta Ads</Anchor>.

<div id="overview" />

## General

Este artículo contiene información e instrucciones sobre cómo configurar y usar Meta Web para aplicaciones de PC y consola con AppsFlyer. Esto incluye:

* [Activación de la integración del partner en AppsFlyer](#activación-del-partner-en-appsflyer).
* [Configuración de Meta Web en AppsFlyer](#configuración-de-meta-web-en-appsflyer).
* [Configuración de campañas en Meta para aplicaciones de PC y consola](/docs/meta-ads-web-integration-setup-for-pc-and-console-apps#configuración-de-campañas-en-meta-web-para-aplicaciones-de-pc-y-consola).

<div id="prerequisite" />

### Requisito previo

Antes de activar la integración de Meta Web, asegúrate de tener una [cuenta comercial en Meta Business Manager](https://www.facebook.com/business/help/1710077379203657?id=180505742745347).

<div id="activating-partner-in-appsflyer" />

## Activación del partner en AppsFlyer

**Para activar la integración de partners:**

1. En AppsFlyer, en el menú lateral, ve a **Colaborar** > **Integraciones de partners > Marketplace** pestaña.
2. Busca **Meta Web**.
3. Haz clic en **Integrate**. Se te redirige a la página de configuración.
4. En la pestaña **Integración**, selecciona **Activar partner**.  
   **Nota: <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">El interruptor debe permanecer ON (</Anchor><Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activado</Anchor>) mientras trabajes con el partner.**
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación.

<div id="setting-up-meta-web-in-appsflyer" />

## Configuración de Meta Web en AppsFlyer

En esta parte de la configuración, también puedes configurar postbacks en Meta Web. La integración Meta Web (metaweb\_int) utiliza una herramienta API de conversiones proporcionada por Meta Ads para que los anunciantes envíen datos desde sus **aplicaciones de PC y consola** directamente a los servidores de Meta. Dichos datos pueden incluir acciones del usuario, como compras, registros y otros tipos de conversiones realizadas en plataformas no móviles (sitios web o aplicaciones). Luego, Meta Ads utiliza los datos para optimizar la segmentación de anuncios, medir el rendimiento de los anuncios y crear audiencias personalizadas para el retargeting.

La integración con Meta Web solo admite el envío de postbacks para instalaciones y eventos in-app.

<div id="integration-tab" />

<Accordion title="Pestaña de integración">

La pestaña **Integración** incluye una serie de secciones, como se describe a continuación.

<div id="activate-partner" />

#### Activar partner

Para configurar la integración, primero debes activar el interruptor **Activar partner**.

<div id="general-settings" />

#### Configuración general

* **ID de píxel:** Ingresa el ID de píxel. Puedes recuperarlo de tu administrador de Meta Ads:
  1. Desde el <Anchor target="_blank" href="https://www.facebook.com/ads/manager">Administrador de anuncios</Anchor> en el menú lateral, ve a **Todas las herramientas** > **Administrador de eventos**.   
     **Nota:** Asegúrate de tener la empresa correcta seleccionada en el menú desplegable en la parte superior derecha.
  2. En el menú lateral del **Administrador de eventos** selecciona **Fuentes de datos**. Verás una lista de tus píxeles. Si no tienes un píxel para el negocio seleccionado, puedes crear uno a través de la misma vista.
  3. Copia el ID de píxel que se muestra debajo del nombre del píxel y pégalo en el campo ID de píxel de la integración de AppsFlyer.  
     <Image alt="pixel id3.png" src="https://files.readme.io/77969160b04357d056f2eee435a61314b95225f43e03cb31dd21a80dceef0dae-20748699506193.png" width="283px" />
* **Token de acceso:** Ingresa el token de acceso. Para recuperarlo, sigue [estas instrucciones](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token).
* **Limitar el uso de la información personal de los usuarios en Meta Ads (CCPA):** Activa esta opción para habilitar el cumplimiento de las <Anchor target="_blank" href="/marketers/es/docs/send-opendsr-api-requests">leyes de protección de datos</Anchor>.  
  **Nota:** Cumplir con las regulaciones de privacidad de la CCPA limita los datos provenientes de los usuarios de Meta Ads que residen en California, EE.UU.

<div id="enable-view-through-attribution" />

#### Habilitar la atribución view-through

AppsFlyer admite la atribución view-through para campañas de Meta Web mediante modelos probabilísticos (PMOD) y landing pages con <Anchor target="_blank" href="/marketers/es/docs/meta-ads-create-web-based-campaigns#set-up-smart-script-crossplatform-landing-page">Smart Script</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/meta-ads-create-web-based-campaigns#set-up-smart-banners-landing-page">Smart Banner</Anchor>. Esto permite que AppsFlyer atribuya las instalaciones de aplicaciones que resultan de que los usuarios ven un anuncio y luego instalan la aplicación, incluso entre plataformas, sin necesidad de hacer clic directamente.

Cuando un usuario hace clic en un anuncio de Meta Web y llega a una landing page habilitada para <Anchor target="_blank" href="/marketers/es/docs/meta-ads-create-web-based-campaigns#set-up-smart-script-crossplatform-landing-page">Smart Script</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/meta-ads-create-web-based-campaigns#set-up-smart-banners-landing-page">Smart Banner</Anchor>, AppsFlyer puede atribuir la instalación posterior de la aplicación. Si están disponibles, los `fbclid` se incluirán en el postback de Meta para mejorar la fidelidad de la atribución.

**Habilitar la atribución view-through:**

1. En AppsFlyer, desde la barra lateral, abre **Integraciones activas** > **Meta Web Ads**.
2. En la pestaña **Integración**, desplázate a la sección **Atribución de instalaciones**.
3. Activa **Atribución de instalaciones por view-through**.
4. **[opcional]** Activa la opción **prioridad de atribución equitativa entre plataformas** y configura la ventana de lookback. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Habilitar igual prioridad para impresiones multiplataforma</Anchor>.
5. Abre la pestaña **Enlace de atribución**.
6. Desplázate a la sección **Atribución view-through** y configura la **ventana de lookback por view-through** (hasta 24 horas).
7. Haz clic en **Guardar integración** para aplicar tu configuración.

<div id="default-postbacks" />

#### Postbacks predeterminados

Los postbacks de las instalaciones se envían automáticamente a Meta Web. En el campo **For Users From**, selecciona una de las siguientes opciones:

* **Sólo este partner:** Los postbacks de eventos in-app se envían solo para eventos atribuidos a este partner, es decir, el usuario que los realizó proviene de este partner.
* **Todas las fuentes de medios, incluidas las orgánicas,** sirven para garantizar que los postbacks de eventos in-app se envíen para eventos realizados por usuarios que proceden de este partner, de otros partners o de fuentes orgánicas.

<div id="in-app-event-postbacks" />

#### Postbacks de eventos in-app

Configura la asignación de postbacks de eventos in-app enviados a Meta Web. Estos eventos se pueden ver en el <Anchor target="_blank" href="https://www.facebook.com/business/help/1541268312717919?id=818859032317965">administrador de eventos de Meta</Anchor>:

1. Activa **Postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista. La siguiente tabla describe los campos que debes completar:

| Nombre de parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos de servidor a servidor.<ul><li>Haz clic en **Agregar elemento**, ingresa el nombre del evento y haz clic en ![check.png](https://files.readme.io/66d595d0ac8a01489ce810bbd3865fca2556342086dc6b20f26fa3d7b7e3afc2-19124971382289.png).</li></ul> |
| **Asignado al evento de partner** | El ID o nombre único de cada evento, tal y como lo defina el partner.<ul><li>Selecciona en el cuadro desplegable el evento predefinido para partners que más te convenga o selecciona PERSONALIZADO.</li></ul> |
| **Para usuarios de** | <ul><li>Los postbacks de las instalaciones se envían automáticamente solo a Meta Web.</li><li>**Todas las fuentes de medios, incluidas las orgánicas,** sirven para garantizar que los postbacks de eventos in-app se envíen para eventos realizados por usuarios que proceden de este partner, de otros partners o de fuentes orgánicas.</li></ul> |
| **incluye** | **Valores e ingresos:** Todos los parámetros del evento, incluyendo el valor de los ingresos (si existe en el evento), se envían en el postback. |

3. [Opcional] Haz clic en el ícono **Agregar condiciónaltconditional-iae-postbacks-icon.pngalt para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer condiciones</Anchor> para un evento.**
4. Establece la **ventana de postbacks de eventos in-app**, si es necesario (lee más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">configuración de la ventana de postbacks de eventos in-app</Anchor>).
5. Haz clic en **Guardar integración**.
6. [Opcional] Después de guardar la integración, desde la página de configuración, puedes integrar más de tus aplicaciones con el partner:
   1. En la esquina superior izquierda, debajo del nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
   2. Selecciona una aplicación diferente en la lista desplegable.
   3. Repite los pasos de integración para la aplicación seleccionada.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlace de atribución">

La generación de un enlace de atribución en la interfaz de usuario de AppsFlyer no está disponible actualmente. Sin embargo, puedes usar una página de aterrizaje multiplataforma con SmartScript o crear un enlace de atribución directa para tu aplicación (consulta la tabla a continuación).

| Opción | Acciones | ¿Quiénes están involucrados? |
| --- | --- | --- |
| Landing page multiplataforma | **Recomendado**: Para cuando tu campaña promociona una aplicación que también está disponible en múltiples plataformas, como Epic y Steam.<br /><br /><Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Más información sobre las landing pages multiplataforma</Anchor><br /><br /><Anchor target="_blank" href="/marketers/es/docs/cross-platform-landing-pages-with-smart-script">Más información sobre cómo configurar una landing page multiplataforma</Anchor><ul><li>Asegúrate de que todos los parámetros de URL relevantes (que luego son capturados por Smart Script) se anexen a la URL del anuncio.</li><li>Asegúrate de que el script tome FBCLID de la URL entrante y lo agregue al enlace generado. Es decir, asignar el parámetro de URL saliente de FBCLID `fbclid` al parámetro de URL entrante `fbclid`.<br />[Práctica recomendada]: ¡**Importante**! Para mostrarlo en los reportes de raw data de AppsFlyer, el parámetro de entrada `fbclid` también debe asignarse a uno de los parámetros de salida `af_sub[1-5]`.</li><li>Opcional: Utiliza las macros de URL dinámicas de Meta en lugar de codificar manualmente los valores. <Anchor target="_blank" href="https://www.facebook.com/business/help/2360940870872492">Saber más</Anchor></li></ul> | Marketer (puede requerir la asistencia del desarrollador) |
| Enlace de atribución directa | Si no utilizas una landing page multiplataforma porque solo tienes 1 aplicación en 1 plataforma, puedes crear enlaces de atribución directa para colocarlos detrás de los anuncios.<br /><br /><Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprende a crear enlaces de atribución directa</Anchor><ul><li>Asegúrate de que los parámetros obligatorios estén incluidos en tu enlace:<ul><li>media\_source</li><li>af\_campaign\_id</li><li>af\_r</li></ul></li></ul>Plantilla a utilizar para el enlace del anuncio de Meta Web:<br /><br />`https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={encoded landing page and URL params}`<br /><br />Enlace de muestra de un enlace de anuncio de Meta Web que conduce a Steam: `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello`<br /><br />**Nota**: La plantilla incluye algunos parámetros de URL dinámicos admitidos por Meta. Si lo prefieres, puedes reemplazarlos por valores reales manualmente. <Anchor target="_blank" href="https://www.facebook.com/business/help/2360940870872492">Aprender más sobre los parámetros de URL dinámicos de Meta</Anchor> | Comercializador |

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costo">

El costo no está disponible para Meta Web.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos por publicidad">

Los ingresos por publicidad no están disponibles para Meta Web.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Actualmente, no se otorgan permisos a Meta Web.

</Accordion>

<div id="setting-up-campaigns-in-meta-web-for-pc-and-console-apps" />

## Configuración de campañas en Meta Web para aplicaciones de PC y consola

**Cuando configures tu nueva campaña**:

* Selecciona un objetivo de campaña. Recomendamos seleccionar una de las siguientes opciones:
  * **Ventas**: esto permite que Meta se optimice hacia un evento específico (tu KPI principal).
  * **Tráfico**: esto permite que Meta se optimice hacia los clics de anuncios. Esto solo debe usarse si no tienes otros KPI o si el volumen de otros eventos de KPI es demasiado bajo.
  * **Personalizado**: Si deseas establecer un evento personalizado (como objetivo de tu campaña). **Nota:** Para permitir que el evento personalizado aparezca como objetivo de campaña en el dashboard de Meta, primero configura el evento personalizado en AppsFlyer.
* Selecciona **Sitio web** como ubicación de conversión.
* Cuando nombres tu píxel de conversión de Facebook, ingresa el mismo ID de píxel que ingresaste para metaweb\_int en AppsFlyer Partner Marketplace.
* Cuando ingresas la URL del sitio web como destino de tu anuncio, la URL debe ser para una de las siguientes opciones:
  * Página de aterrizaje web (recomendada cuando tienes una aplicación en múltiples plataformas)
  * URL de la tienda (se recomienda cuando tu aplicación está en una sola tienda de aplicaciones, en una sola plataforma)

<div id="view-web-to-app-attribution-data" />

## Ver datos de atribución web-to-app

Aunque los eventos de conversión basados en web se envían a Meta con el PID de `metaweb_int` original, se reportan en el dashboard de AppsFlyer y en los reportes de raw data con el PID de `Facebook Ads`. Esto se aplica tanto a los eventos de conversión primarios como a los eventos de asistencia a la conversión.

Esta vista unificada de reportes te permite analizar el rendimiento de las campañas web y app en un solo lugar, incluidos reportes completos de costos web y móvil.

<div id="view-in-the-dashboard" />

### Ver en el dashboard

Todas las atribuciones web-to-app de Meta aparecen en `Facebook Ads` en los dashboards General y Actividad. Esto proporciona una vista única y consolidada de los resultados de campañas en todas las plataformas. Utiliza filtros y desgloses estándar para comparar el tráfico web y de aplicaciones dentro de tus datos de Meta Ads.

<div id="view-in-raw-data-and-api-reports" />

### Ver en reportes raw data y API

* **Las exportaciones de raw data y las respuestas de la API** incluyen el PID `Facebook Ads` en el campo `media_source` para la actividad web de Meta. Para verificar los detalles de configuración de la campaña web, consulta el campo `original_url` que muestra `metaweb_int` como el PID utilizado durante la creación de campañas web.
* Los **reportes de postbacks** muestran a `metaweb_int` como la fuente de medios original a la que se envió el postback.

<div id="traits-and-limitations" />

## Especificaciones y limitaciones

| Caducado | Nota |
| --- | --- |
| Clics e impresiones (limitación temporal) | Los clics y las impresiones de las campañas orientadas a apps de PC & consola no están disponibles temporalmente en Meta SRN (`Facebook Ads`). |

<div data-zendesk-anchors="h_01HE2XD0FSY0QMJSKVC0FHHK5P=importante overview=general h_01HK4QHRJG6WTN9P6ZG83XQ6AY=general prerequisite=requisito-previo h_01HFXV8HPGCRGYPEW0NPJ0NR0S=requisito-previo activate-partner=activaci%C3%B3n-del-partner-en-appsflyer h_01HFXV8HPH3N4DBKKTQE6DK7FK=activaci%C3%B3n-del-partner-en-appsflyer setting-up-metaweb-in-appsflyer=configuraci%C3%B3n-de-meta-web-en-appsflyer 01H88VAJH3VENKYVRQY5RXN63P=configuraci%C3%B3n-de-meta-web-en-appsflyer 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::1ca30957=activar-partner h_01HFXV8HPH6X92YETNAGZ910AV=activar-partner transaction-id=configuraci%C3%B3n-general h_01HARQDVEDA206D0BBXBC6WEHH=configuraci%C3%B3n-general enable-viewthrough-attribution=habilitar-la-atribuci%C3%B3n-view-through h_01ZXVWB1ZYKK4DP38QY1RMEY6M=habilitar-la-atribuci%C3%B3n-view-through default-postbacks=postbacks-predeterminados 01H88VAJH3WE9Z0971WMBRBJRS=postbacks-predeterminados inapp-event-postbacks=postbacks-de-eventos-in-app 01H88VAJH3AS37MVF75GANWX4B=postbacks-de-eventos-in-app 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab setting-up-campaigns-in-meta-web-for-pc-and-console-apps=configuraci%C3%B3n-de-campa%C3%B1as-en-meta-web-para-aplicaciones-de-pc-y-consola h_01HK4S03KVAN99YKXTHAKCT420=configuraci%C3%B3n-de-campa%C3%B1as-en-meta-web-para-aplicaciones-de-pc-y-consola meta%20view=ver-datos-de-atribuci%C3%B3n-web-to-app view-webtoapp-attribution-data-from-november-2-2025=ver-datos-de-atribuci%C3%B3n-web-to-app h_01K88J8JFNEYBZNR18133NMRP9=ver-datos-de-atribuci%C3%B3n-web-to-app view-in-the-dashboard=ver-en-el-dashboard h_01K88J8JFNMHCVZ0C34E3D7AST=ver-en-el-dashboard view-in-raw-data-and-api-reports=ver-en-reportes-raw-data-y-api h_01K88J8JFN8W2572N92466YFZQ=ver-en-reportes-raw-data-y-api traits-and-limitations=especificaciones-y-limitaciones h_01KB503RDVWPSFBAPAPW4CNZXM=especificaciones-y-limitaciones" />
