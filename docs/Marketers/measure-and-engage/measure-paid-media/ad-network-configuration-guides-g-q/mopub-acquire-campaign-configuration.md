---
title: Configuración de la campaña de MoPub Acquire
metadata:
  keywords:
    - CrossInstall
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
  created_at: '2016-06-20T11:27:42Z'
  edited_at: '2026-09-11T00:24:18Z'
  id: 211187263
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/211187263
---
> **En resumen:** MoPub Acquire (anteriormente Crossinstall, una empresa de X Ads) es un partner integrado de AppsFlyer. MoPub Acquire es una plataforma de demanda solo para móvil especializada en anuncios jugables a escala. Además de la atribución móvil basada en clics, MoPub Acquire también ofrece atribución de costo y view-through, que puedes registrar con AppsFlyer.

<Image align="center" alt="MoPub Acquire, una empresa de Twitter" src="https://cdn.appsflyer.com/marketplace/static/logo/crossinstall.png" width="104px" />

<div id="setting-up-mopub-acquire" />

## Configuración de MoPub Acquire

**Requisito previo:** una cuenta con el Partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace**.  
   (**Para editar una integración existente:** ve a la pestaña **Collaborate > Partner Integrations > Active integrations**.)
2. Selecciona la aplicación correspondiente.
3. Busca el Partner y selecciona **Integrate**.
4. En la pestaña **Integration**, activa el selector **Activate partner**.   
   **Nota:** el selector **debe permanecer activado (activo) mientras trabajes con el Partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

**Para habilitar la integración de este partner**, activa **Activar partner**.  
El conmutador debe estar activado mientras trabajes con el partner. Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">activación del partner</Anchor>.

**Habilitar la atribución por impresiones**

Actívala si quieres atribuir las instalaciones view-through de MoPub Acquire. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a MoPub Acquire después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos provenientes solo de usuarios atribuidos a MoPub Acquire.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a MoPub Acquire mediante postbacks.

**Para configurar postbacks de eventos in-app:**

1. Activa **Postback de evento in-app**.
2. Establece la **ventana de postback de eventos in-app** (lee más sobre <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">la configuración de la ventana de postback de eventos in-app</Anchor>).
3. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista.
4. Completa los parámetros según sea necesario:

| Nombre de parámetro | Nota |
| --- | --- |
| Nombre de evento SDK | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK integrado con tu aplicación o desde eventos de servidor a servidor.  <br />**Consejo**: ¿No encuentras el evento que buscas? Escribe su nombre de evento del SDK, haz clic en **Crear personalizado** y asígnalo normalmente. Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados</Anchor>. |
| Opción de envío | Selecciona la opción de envío para el evento:<ul><li>**Solo eventos atribuidos a este partner** para eventos procedentes **solo** de usuarios atribuidos a este partner.</li><li>**Eventos atribuidos a cualquier partner u orgánicos** para que toda tu base de usuarios esté disponible para ser reportada al partner.</li></ul> |
| Enviar ingresos | <ul><li>**Sin valores ni ingresos:** envía solo el evento en sí sin el valor del evento.</li><li>**Con valores y sin ingresos:** envía todos los parámetros, excepto el valor de ingresos.</li><li>**Con valores e ingresos**: envía todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento).</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieres enviar a MoPub Acquire para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de MoPub Acquire.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña** - añádela para comparar diferentes campañas en ejecución con MoPub Acquire.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de MoPub Acquire.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar diferentes creatividades dentro de conjuntos de anuncios específicos, en campañas específicas de MoPub Acquire.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio**: configura el parámetro de ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio utilizados y usar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar agregación o filtrado de datos  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo del clic a la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse a MoPub Acquire.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clics</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a MoPub Acquire para que se active cuando los leads hagan clic en el anuncio correspondiente.

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a MoPub Acquire, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro del enlace de atribución:** af\_viewthrough\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución por impresiones</Anchor>.

<div id="impressions-attribution-link" />

### Enlace de atribución de impresiones

El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Envíalo a MoPub Acquire para que se active cuando se vea un anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de los costos por API. Consulta <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">la tabla de integración de costos de redes de publicidad</Anchor> para obtener más información sobre las dimensiones, métricas y funciones admitidas. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el panel de control de estado de la integración de costos (e ingresos por publicidad) o en el panel de control de la red de publicidad individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a MoPub Acquire. Ten en cuenta que, aunque la atribución esté desactivada para MoPub Acquire, la pestaña de permisos está activa y puedes conceder el control a MoPub Acquire. <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">Descubre qué permisos puedes conceder a MoPub Acquire</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-mopub-acquire=configuraci%C3%B3n-de-mopub-acquire h_01HFP4C4JDPYDGM3RBSQCNHC3T=configuraci%C3%B3n-de-mopub-acquire h_01HFP4C4JDRMK87B48F4MV5B91=integration-tab activate-partner=activar-socio h_01HFP4C4JD5A9RZP6HBBM2WFHZ=activar-socio default-postbacks=postbacks-predeterminados h_01HFP4C4JDAK0N210GAH978CM0=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HFP4C4JDEW2YBFCFR0MN6G91=configuraci%C3%B3n-de-eventos-in-app h_01HFP4C4JDWBC03HBEZ13HP3NS=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HFP4C4JDWAWKMT1CSPQSCNMZ=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HFP4C4JDW2DRVVHXJ8ZAT9W5=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HFP4C4JDTXJYH4S1EZ4HYJWG=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HFP4C4JDDWH23CVQMJNH2V70=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HFP4C4JDYXBYAP5AYBN54A4B=enlace-de-atribuci%C3%B3n-de-impresiones h_01HFP4C4JDP8NDDRHGXM0Y7XM7=cost-tab h_01HFP4C4JDBWCER854NDKTYRW8=ad-revenue-tab h_01HFP4C4JDRYYPW6W2PNA8J8P3=permissions-tab" />
