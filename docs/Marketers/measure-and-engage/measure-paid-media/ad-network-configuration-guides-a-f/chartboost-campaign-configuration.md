---
title: Configuración de la campaña de Chartboost
metadata:
  keywords:
    - Chartboost
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
  created_at: '2016-03-28T08:01:01Z'
  edited_at: '2026-09-11T00:23:17Z'
  id: 209731553
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/209731553
---
> **De un vistazo:** Chartboost, un partner integrado de ad network de AppsFlyer, es una de las mayores plataformas de anuncios exclusiva para juegos móviles para aumentar los ingresos. Además de la atribución móvil basada en clics, Chartboost también ofrece atribución de costo, ingresos publicitarios y view-through, que puedes registrar con AppsFlyer.

<div id="note" />

> 📘 **Nota:**
>
> Solo es necesario integrar el SDK de Chartboost si actúas como publisher de Chartboost y quieres atribuir ingresos publicitarios. De lo contrario, solo necesitas el SDK de AppsFlyer. Para obtener más información, consulta la [sección de ingresos publicitarios](/docs/chartboost-campaign-configuration#ad-revenue-tab) de este artículo.

<div id="setting-up-chartboost" />

## Configuración de Chartboost

**Requisito previo:** una cuenta con el Partners. Si no tienes una cuenta, contacta con el Partners para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el selector **Activate partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el Partners**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña ***Integración*** está dividida en diferentes secciones, tal como se describe a continuación.

<div id="activate-partners" />

### Activar los partners

Para habilitar la configuración, en la primera visita debes <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">activar el partner</Anchor> mediante el conmutador ***Activar partner***.

<div id="general-settings" />

### Configuración general

**ID de app y firma de Chartboost**

Chartboost requiere conectarse con AppsFlyer mediante un ID de app único y una firma. Si no conoces el tuyo, puedes obtenerlo directamente de Chartboost.

**Habilitar la atribución por impresiones**

Actívalo si quieres atribuir las instalaciones view-through de Chartboost. El control deslizante de lookback de view-through está disponible en la pestaña ***enlace de atribución***.

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a Chartboost después de las instalaciones y las instalaciones rechazadas. Utiliza esta sección para definir la **fuente de los usuarios** para los postbacks.

Selecciona ***Solo este partner*** para instalaciones provenientes únicamente de usuarios atribuidos a Chartboost.  
Selecciona ***Todas las fuentes, incluidas las orgáni*cas** para que toda tu base de usuarios esté disponible para ser reportada a Chartboost.

Las instalaciones rechazadas se pueden enviar a **Este partner solo**.

<div id="launch-postbacks" />

#### Postbacks de lanzamiento

A partir del 1 de julio de 2020, ya no enviamos postbacks de lanzamiento a Chartboost. Si tu integración se configuró antes de esta fecha, puede haber cambios en tus configuraciones. La siguiente tabla explica los posibles cambios y las acciones que debes realizar, cuando corresponda:

| Tu configuración | Se actualizará a | Tus próximas acciones |
| --- | --- | --- |
| Enviar a Chartboost **todos los inicios** (de todas las fuentes de medios, incluidas las orgánicas) | Enviar a Chartboost:<ul><li>**todas las instalaciones** (de todas las fuentes de medios, incluidas las orgánicas)</li><li>**todos los eventos** `af_app_opened` (de todas las fuentes de medios, incluidas las orgánicas)</li></ul> | No se requieren más acciones. Esta actualización no tiene ningún impacto real en la configuración. |

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes configurar los postbacks de eventos in-app que se envían a Chartboost.

**Para configurar postbacks de eventos in-app:**

1. Activa ***postback de evento in-app***.
2. Elige si quieres reportar los eventos seleccionados al partner o todos.
   * Nota: Si eliges reportar todos los eventos, el evento *af\_app\_opened* no se reporta.
3. Si eliges seleccionar eventos manualmente, haz clic en ***Agregar evento*** para añadir un evento del SDK a la lista.

| Nombre del parámetro | Descripción |
| --- | --- |
| **Nombre del evento del SDK** *(obligatorio solo para la selección manual)* | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK o desde eventos de servidor a servidor.  <br />**Consejo**: si no ves el evento que quieres en la lista, actívalo en un dispositivo con una instalación no orgánica y vuelve a comprobarlo. |
| **Opción de envío** | Selecciona la opción de envío del evento:  <br />**Solo este partner** para eventos que provienen **solo** de usuarios atribuidos a Chartboost.  <br />**Todas las fuentes, incluidas las orgánicas** para que toda tu base de usuarios esté disponible para ser reportada al partner |
| **Enviar datos de eventos** | <ul><li>**Sin valores ni ingresos:** envía solo el evento en sí sin el valor del evento.</li><li>**Con valores y sin ingresos:** envía todos los parámetros, excepto el valor de ingresos.</li><li>**Con valores e ingresos**: envía todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento).</li></ul> |

4. Haz clic en ***Guardar***.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieres enviar a Chartboost para atribuir campañas, conjuntos de anuncios o anuncios individuales de Chartboost. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña** - añádela para comparar diferentes campañas en funcionamiento con Chartboost.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Chartboost.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar diferentes creatividades dentro de conjuntos de anuncios específicos, dentro de campañas específicas de Chartboost.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** y **ID de subsitio** - configura el parámetro de ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para agregar o filtrar datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo del clic a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Chartboost.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clics</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Chartboost para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a Chartboost, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro del enlace de atribución:** af\_viewthrough\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución por impresiones</Anchor>.

<div id="impressions-attribution-link" />

### Enlace de atribución de impresiones

El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Envíalo a Chartboost para que se active cuando se vea el anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de redes de publicidad</Anchor> para obtener detalles completos sobre las dimensiones, métricas y funciones admitidas. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el panel de control de estado de la integración de costos (e ingresos por publicidad) o en el panel de control de la red de publicidad individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Esta sección es pertinente si actúas como publisher y muestras anuncios del partner a tus usuarios. Como tal, con seguridad te gustaría medir el nivel de engagement de tus usuarios adquiridos a partir de distintas fuentes, a fin de identificar las fuentes que te resultan más rentables.

**Para habilitar la API de ingresos por publicidad**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">estas instrucciones de integración</Anchor>.

<div id="important" />

> 🚧 **Importante:**
>
> Si eres publisher de Chartboost, hay dos requisitos adicionales además de la configuración de AppsFlyer:
>
> 1. [Integra el SDK de Chartboost](https://answers.chartboost.com/en-us/child_article/ios): solo es necesario si actúas como publisher. **Si solo usas Chartboost para anunciar tu App, el SDK de AppsFlyer es todo lo que necesitas integrar**.
> 2. [Activa Chartboost S2S](https://answers.chartboost.com/en-us/child_article/s2s-setup) - este paso es necesario para permitir que AppsFlyer consulte a Chartboost los datos de ingresos por anuncios. **No debes confundir esto con** <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">**AppsFlyer S2S**</Anchor>**, que es la forma de enviar eventos in-app a AppsFlyer mediante una API específica.**

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgar a Chartboost, tanto si el partner actúa como ad network, agencia o ambas cosas. Ten en cuenta que, aunque la atribución esté deshabilitada para Chartboost, la pestaña de permisos está activa y puedes conceder el control a Chartboost.

Usa estos selectores para otorgar permisos a la ad network para gestionar su propia configuración de tu App: Permisos de la ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos***: solo a los datos de ingresos atribuidos al partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div id="discrepancies-between-chartboost-and-appsflyer" />

## Discrepancias entre Chartboost y AppsFlyer

A veces hay discrepancias entre el Dashboard de Chartboost y el Dashboard de AppsFlyer.

Los anunciantes deben tener en cuenta las siguientes razones:

| Causa | Chartboost | AppsFlyer |
| --- | --- | --- |
| **Ventana de atribución** | La ventana de atribución de Chartboost es de 21 días | La ventana de lookback de AppsFlyer es de 7 días<br /><br />**\*\* Esta es la causa principal de las discrepancias entre AppsFlyer y Chartboost** |
| **Atribución de fuentes multicanal** | La atribución de Chartboost funciona tal como se especificó anteriormente, independientemente de otras fuentes. | AppsFlyer usa la atribución de último clic (para obtener más información sobre la atribución de AppsFlyer, haz clic <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">aquí</Anchor>) |

<div id="note-1" />

> 📘 **Nota:**
>
> Si bien Chartboost muestra todas las instalaciones de una campaña de retargeting en el mismo lugar, en el dashboard de AppsFlyer las instalaciones se dividen entre la página Overview (nuevas instalaciones) y la página Retargeting (reatribución y re-engagement).

<div data-zendesk-anchors="h_01HFRFDP5V8Q9F0KTEX8X917ZX=nota setting-up-chartboost=configuraci%C3%B3n-de-chartboost h_01HFRFDP5V0CTXQ0B0JXYD0TKS=configuraci%C3%B3n-de-chartboost h_01HFRFDP5V7BEPGG4226CYWCS7=integration-tab activate-partners=activar-los-partners h_01HFRFDP5V26M3RV5986P768A7=activar-los-partners general-settings=configuraci%C3%B3n-general h_01HFRFDP5VPBY1W81DRVVWJ54D=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HFRFDP5V2GAJQ81NYKDGF16K=postbacks-predeterminados launch-postbacks=postbacks-de-lanzamiento h_01HFRFDP5VGFJ8K0J9GA0EX3K1=postbacks-de-lanzamiento inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HFRFDP5V3Z41EEASQD7ZPJRD=configuraci%C3%B3n-de-eventos-in-app h_01HFRFDP5VKTGQFHMMXTD6KQTY=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HFRFDP5VA3DQSH3TRYJC47JZ=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HFRFDP5VQFQHH6ZZ6DWXSJ9C=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HFRFDP5WAJ5Y0K27DY21NZ91=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HFRFDP5WTKE6WJ3CVS16PDF9=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HFRFDP5WSM97SFDS8YC64X31=enlace-de-atribuci%C3%B3n-de-impresiones h_01HFRFDP5W0K5A3E229PS25N9P=cost-tab h_01HFRFDP5WAB1F5YBA9BW3QYPM=ad-revenue-tab h_01HFRFDP5WMREFM3Q0DXJYTHCD=importante h_01HFRFDP5WHAKN44VT9Y90P6BJ=permissions-tab discrepancies-between-chartboost-and-appsflyer=discrepancias-entre-chartboost-y-appsflyer h_01HFRFDP5WHWZARGXQ5ZTRC8BD=discrepancias-entre-chartboost-y-appsflyer h_01HFRFDP5WN483XJN4PDV2KCR0=nota-1" />
