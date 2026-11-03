---
title: Configuración de la campaña de Fyber
metadata:
  keywords:
    - fyber
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
  created_at: '2016-03-28T08:29:40Z'
  edited_at: '2026-09-11T00:23:32Z'
  id: 208209366
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/208209366
---
> **De un vistazo:** Fyber, un partner integrado de ad network de AppsFlyer, desarrolla una plataforma de monetización de última generación para publishers móviles.

## Configurar Fyber

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

### Activar los partners

En la **primera visita** aquí, tendrás que activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

### Configuración general

**Identificación de la aplicación**

Fyber se conecta con AppsFlyer a través de un ID de red único. Si aún no tienes el ID de red, debes obtenerlo de Fyber para continuar con la integración.

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir instalaciones view-through de Fyber. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

### Postbacks predeterminados

Envía postbacks automáticos a Fyber tras las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos procedentes solo de usuarios atribuidos a Fyber.  
Selecciona **Eventos atribuidos a cualquier partner u orgánicos** para que toda tu base de usuarios esté disponible para ser reportada a Fyber.

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a Fyber mediante postbacks.

1. Vuelve a configurar aquí el ID de la App de Fyber
2. Activa los postbacks de eventos in-app.
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
4. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
5. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK integrado con tu aplicación o desde eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define Fyber.  <br />Obtén el ID de evento correspondiente de Fyber e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Fyber para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Fyber. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: añádela para comparar distintas campañas en funcionamiento con Fyber.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Fyber.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define los nombres de los conjuntos de anuncios para comparar diferentes creatividades dentro de conjuntos de anuncios específicos, en campañas específicas de Fyber.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio**: configura el parámetro ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te sugerimos que limites la cantidad de IDs de sitio utilizados y que uses el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder los límites del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo del clic a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Fyber.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Fyber para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a Fyber, siempre que no haya habido ningún otro clic en un anuncio relevante.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro del enlace de atribución:** af\_viewthrough\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución por impresiones aquí</Anchor>.

### Enlace de atribución de impresiones

El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Envíalo a Fyber para que se active cuando se vea un anuncio correspondiente.

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

Fyber ofrece mediación de ingresos publicitarios con <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">granularidad a nivel de usuario</Anchor>.

**Para habilitar la API de ingresos por publicidad**:

* Leer más sobre cómo Unity Ads define los clics y las visualizaciones.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a Fyber, tanto si el partner actúa como ad network, agencia o incluso ambos. Ten en cuenta que, incluso si la atribución estuviera deshabilitada para Fyber, la pestaña de permisos seguirá activa y podrás otorgarle el control a Fyber.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

### Permisos de ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos***: solo a los datos de ingresos atribuidos al partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

### Permisos de la agencia

Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* ***Selector principal***: actívalo para mostrar las opciones de permisos para agencias
* ***Permitir el acceso a tu reporte de retención***: solo a los datos de retención de la propia agencia
* ***Permitir el acceso a datos agregados orgánicos.***
* ***Permitir configurar postbacks de eventos in-app***: permite que la agencia configure en la pestaña de integración la asignación de postbacks de eventos in-app a sí misma

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos a las agencias</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-fyber=configurar-fyber h_01HKWB8PSR5213FW7TGX1JCFK7=configurar-fyber h_01HKWB8PSR74F5HSKRMQME3ST5=integration-tab activate-partners=activar-los-partners h_01HKWB8PSRKA27MMN1K10VBVP2=activar-los-partners general-settings=configuraci%C3%B3n-general h_01HKWB8PSRZ2368WVS2C1R0Q10=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKWB8PSRB9TP5K2KQJF6QQ42=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKWB8PSRR23YPXFVF1VT7M30=configuraci%C3%B3n-de-eventos-in-app h_01HKWB8PSR25D98WNZ3XDPE775=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKWB8PSR3CP2AM6MJCQS00GD=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKWB8PSRHXBX3CZS1E5ETTFM=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKWB8PSRJX6F3PFKERSBQEXS=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HKWB8PSR77KA62D1FGC9ACAD=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKWB8PSRX6A88172AH7AW2XB=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKWB8PSRM9BPYE0D2VJ5A4P9=cost-tab h_01HKWB8PSRZGAW17781A32G6MX=ad-revenue-tab h_01HKWB8PSRAE1DTHFSPB7AA7CW=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKWB8PSRE3Q76977BK6D1Z0E=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HKWB8PSR0B2F8QAX35EJK751=permisos-de-la-agencia" />
