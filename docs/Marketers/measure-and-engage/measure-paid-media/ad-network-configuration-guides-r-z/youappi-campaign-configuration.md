---
title: Configuración de la campaña de YouAppi
metadata:
  keywords:
    - Advertisers
    - YouAppi
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-09-20T07:14:26Z'
  edited_at: '2026-08-12T12:16:57Z'
  id: 212932106
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/212932106
---
> **De un vistazo:** YouAppi, un partner integrado de la ad network de AppsFlyer, es una plataforma líder de marketing de crecimiento móvil para marcas móviles premium. Además de la atribución móvil basada en clics, YouAppi también ofrece atribución de costo, ingresos por publicidad, retargeting y view-through, que puedes registrar con AppsFlyer.

Para configurar tus campañas con YouAppi, sigue los pasos a continuación.

<div id="setting-up-youappi" />

## Configuración de YouAppi

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con el partner.  
    Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación. Para ver una descripción detallada del Encabezado de la ventana de configuración de partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

La configuración de YouAppi incluye 4 pestañas activas: Integración, enlace de atribución, costo y permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="tip" />

> 👍 **Consejo**
>
> * El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">Configuración general</Anchor> en la pestaña Integración es **obligatorio** para todos los partners.
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

En tu **primera visita** aquí, deberás activar el selector ***Activate Partner*** para habilitar la configuración de los parámetros de integración. El selector **debe** estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="note" />

> 📘 **Nota:**
>
> Como red de TODAS las instalaciones, YouAppi prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluida la orgánica. Para hacerlo, selecciona **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a YouAppi.

<div id="general-settings" />

### Configuración general

**trackerToken**

YouAppi se conecta con AppsFlyer a través de un trackerToken. Si aún no tienes el trackerToken, debes obtenerlo de YouAppi para continuar con la integración.

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir las instalaciones view-through de YouAppi. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a YouAppi después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos provenientes solo de usuarios atribuidos a YouAppi.  
Selecciona **Eventos atribuidos a cualquier partner u orgánico** para tener toda tu base de usuarios disponible para ser reportada a YouAppi.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a YouAppi mediante postbacks.

1. Vuelve a introducir el trackerToken.
2. Activa Postbacks de evento in-app.
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
   **- Eventos atribuidos a cualquier partner u orgánico** para tener toda tu base de usuarios disponible para ser reportada al partner.
4. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
5. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos server-to-server.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define Youappi.  <br />Obtén el ID de evento correspondiente de Youappi e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que deseas enviar a Youappi para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Youappi. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña** - añádela para comparar diferentes campañas en funcionamiento con YouAppi.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define el nombre del conjunto de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de YouAppi.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define el nombre del anuncio para comparar diferentes creatividades dentro de conjuntos de anuncios específicos de campañas específicas de YouAppi.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro de ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar la cantidad de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo del clic a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a YouAppi.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clics</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a YouAppi para que se active cuando los leads hagan clic en el anuncio correspondiente.

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a YouAppi, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro de enlace de atribución:** af\_viewthrough\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución por impresiones</Anchor>.

<div id="impressions-attribution-link" />

### Enlace de atribución de impresiones

El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Envíalo a YouAppi para que se active cuando se vea un anuncio correspondiente, normalmente durante 1 segundo o más.

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

Este partner no admite ingresos publicitarios.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a YouAppi, tanto si el partner actúa como ad network, como agencia o incluso como ambas. Ten en cuenta que, aunque la atribución esté desactivada para YouAppi, la pestaña de permisos sigue activa y puedes conceder el control a YouAppi.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

<div id="ad-network-permissions" />

### Permisos de ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos***: solo a los datos de ingresos atribuidos al partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

<div id="agency-permissions" />

### Permisos de la agencia

Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* ***Selector principal*** - Actívalo para mostrar las opciones de permisos de la agencia
* ***Permitir el acceso a tu reporte de retención*** - solo a los propios datos de retención de la agencia
* ***Permitir el acceso a datos agregados orgánicos.***
* ***Permitir la configuración de postbacks de eventos in-app*** - permite que la agencia configure la asignación de postbacks de eventos in-app a sí misma en la pestaña de integración

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos a las agencias</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-youappi=configuraci%C3%B3n-de-youappi h_01HK29DCA2B0VJM46KYCPWZ0V0=configuraci%C3%B3n-de-youappi h_01HK29DCA3XH6B98018C6G5MQY=consejo h_01HK29DCA3J3TVPAEEH00T1RS8=integration-tab activate-partner=activar-socio h_01HK29DCA3E890TQ7MZ8BEEA5J=activar-socio h_01HK29DCA3KGV3S44XQ52ZV8YM=nota general-settings=configuraci%C3%B3n-general h_01HK29DCA3SR6BGN8PD8X4R198=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HK29DCA390TAZGD1A1EM06VY=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HK29DCA3VQRZT8SYTQ5T0Z8F=configuraci%C3%B3n-de-eventos-in-app h_01HK29DCA3ESN9EA4RKE1F6HE9=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HK29DCA3CJ5J19D7MGN9ZAWB=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HK29DCA3BGEC5VVC2X00M6HQ=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HK29DCA30YW2PTWKF0HSPG9Q=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HK29DCA3DSF3D8GETECYCZXE=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HK29DCA33HGQRRNXN096W2HY=enlace-de-atribuci%C3%B3n-de-impresiones h_01HK29DCA3PRMEEYGB15JWD5N7=cost-tab h_01HK29DCA4KNSAG2XYZQNX26S9=ad-revenue-tab h_01HK29DCA4EV987C7GPPXSKS7V=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HK29DCA4ZEYMM46NYRH6VWW1=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HK29DCA4923EKBV6X8DBCWFZ=permisos-de-la-agencia" />
