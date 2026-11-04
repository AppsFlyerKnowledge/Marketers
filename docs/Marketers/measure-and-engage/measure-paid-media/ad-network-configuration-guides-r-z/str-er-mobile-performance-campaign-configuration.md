---
title: Configuración de la campaña Ströer Mobile Performance
metadata:
  keywords:
    - Stroer
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-12-19T09:26:27Z'
  edited_at: '2026-08-12T12:16:09Z'
  id: 115000068903
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/115000068903
---
> **Resumen:** Ströer Mobile Performance, un partner integrado de ad network de AppsFlyer, ofrece exposición internacional adecuada para aplicaciones móviles a través de su red global única. Además de la atribución móvil basada en clics, Ströer Mobile Performance proporciona datos de costo, que se pueden registrar con AppsFlyer.

Para configurar tus campañas con Ströer Mobile Performance, sigue los pasos a continuación.

<div id="setting-up-ströer-mobile-performance" />

## Configuración de Ströer Mobile Performance

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con el partner.  
    Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación. Para ver una descripción detallada del Encabezado de la ventana de configuración de partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

La ventana de configuración de Ströer Mobile Performance incluye 3 pestañas activas: Integración, enlace de atribución y permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="tip" />

> 👍 **Consejo**
>
> * El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">Configuración general</Anchor> en la pestaña de Integración es **obligatorio** para todos los partners.
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partners" />

### Activar los partners

En la **primera visita** aquí, deberás activar el selector **Activar partner** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

Configuración general

**Token de seguridad**

Ströer Mobile Performance se conecta con AppsFlyer mediante un Security Token único. Si aún no lo tienes, debes obtenerlo de Ströer Mobile Performance para continuar con la integración.

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a Ströer Mobile Performance tras las instalaciones y los re-engagement de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos que provienen únicamente de usuarios atribuidos a Ströer Mobile Performance.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección puedes mapear tus eventos de AppsFlyer con Ströer Mobile Performance mediante postbacks.

1. Activa los postbacks de eventos in-app.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre único o el ID de cada evento, tal como se define del lado de Ströer Mobile Performance.  <br />Obtén el ID de evento correspondiente de Ströer Mobile Performance e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que deseas enviar a Ströer Mobile Performance para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Ströer Mobile Performance. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: agrégala para comparar diferentes campañas en ejecución con Ströer Mobile Performance.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjunto de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Ströer Mobile Performance.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre de anuncio**: define nombres de anuncios para comparar diferentes creatividades dentro de conjuntos de anuncios específicos, dentro de campañas específicas de Ströer Mobile Performance.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio**: configura el parámetro ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te sugerimos que limites la cantidad de IDs de sitio usados y utilices el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones de ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse al partner.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la ventana de lookback de clic <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">aquí</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Ströer Mobile Performance para que se active cuando los leads hagan clic en el anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Ströer Mobile Performance envía automáticamente datos de coste de CPI en el enlace de atribución para todas las instalaciones.

Para ver la lista completa de partners que admiten datos de costes, haz clic <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">aquí</Anchor>.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Este partner no admite ingresos por publicidad.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a Ströer Mobile Performance, tanto si el partner actúa como ad network, agencia o ambas. Ten en cuenta que, aunque la atribución esté desactivada para Ströer Mobile Performance, la pestaña Permisos está activa y puedes concederle el control a Ströer Mobile Performance.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación.

<div id="ad-network-permissions" />

### Permisos para Redes de Publicidad

* ***Permitir configurar la integración*** - permite que el partner configure la pestaña Integración (excepto los postbacks de eventos in-app)
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos***: solo a los datos de ingresos atribuidos al partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-str%C3%B6er-mobile-performance=configuraci%C3%B3n-de-str%C3%B6er-mobile-performance h_01HJS1HC2Q3DAFRS8VJ9F3N5DP=configuraci%C3%B3n-de-str%C3%B6er-mobile-performance h_01HJS1HC2QQKDQR5EF5DBJMYRQ=consejo h_01HJS1HC2Q5YXB8Q8XNNMGG44S=integration-tab activate-partners=activar-los-partners h_01HJS1HC2QYD5B3ZM06SVE42SK=activar-los-partners default-postbacks=postbacks-predeterminados h_01HJS1HC2QK20MTWR68JNP49QV=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HJS1HC2R1WET88A5HX3F20W7=configuraci%C3%B3n-de-eventos-in-app h_01HJS1HC2RVNDZD3AC967A38KN=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HJS1HC2RBBX2BMHVPSPW3VD5=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HJS1HC2RQADFCQ2MHD0E60NC=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HJS1HC2RMPPRFZR2X02KGDD0=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HJS1HC2R1PVYA6N2QSHHFWVZ=cost-tab h_01HJS1HC2R34B2SQDBW4D3JEC5=ad-revenue-tab h_01HJS1HC2RZX1WPTF60M0ARKTV=permissions-tab ad-network-permissions=permisos-para-redes-de-publicidad h_01HJS1HC2RW0SPDXWBA7H6SRGP=permisos-para-redes-de-publicidad" />
