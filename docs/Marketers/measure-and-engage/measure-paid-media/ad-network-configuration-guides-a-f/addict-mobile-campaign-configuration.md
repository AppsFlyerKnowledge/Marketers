---
title: Configuración de campañas de Addict Mobile
metadata:
  keywords:
    - Advertisers
    - Addict Mobile
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-01-03T09:11:00Z'
  edited_at: '2026-09-11T00:22:44Z'
  id: 115000174783
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/115000174783
---
> **De un vistazo:** Addict Mobile, un partner integrado de ad network de AppsFlyer, es un experto en marketing de performance móvil para adquisición de usuarios y retargeting en móvil. Además de la atribución móvil basada en clics, Addict Mobile también ofrece atribución view-through, que puedes registrar con AppsFlyer.

<div id="setting-up-addict-mobile" />

## Configuración de Addict Mobile

**Requisito previo:** una cuenta con el Partners. Si no tienes una cuenta, ponte en contacto con el Partners para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace** .  
   (**Para editar una integración existente:** ve a la pestaña **Collaborate > Partner Integrations > Active integrations** .)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrate**.
4. En la pestaña **Integration**, activa el selector **Activate partner**.   
   **Nota:** el selector **debe permanecer activado (activo) mientras trabajes con el Partners**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">las integraciones de partner.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, debes activar el botón ***Activar Partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir instalaciones view-through de Addict Mobile. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a Addict Mobile tras las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para los eventos que provienen únicamente de usuarios atribuidos a Addict Mobile.  
Selecciona **Eventos atribuidos a cualquier partner u orgánico** para tener toda tu base de usuarios disponible para reportarla a Addict Mobile.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a Addict Mobile mediante postbacks.

1. Activa los Postbacks de eventos in-app con el selector.
2. Selecciona la Opción de envío para todos los eventos definidos por el SDK.
   * **Solo eventos atribuidos a este partner** para eventos procedentes **solo** de usuarios atribuidos a este partner.
   * **Eventos atribuidos a cualquier partner u orgánico** para tener toda tu base de usuarios disponible para reportarla al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de Parámetro | Description |
| --- | --- |
| **Nombre del evento del SDK** | El nombre del evento, tal como lo recibe AppsFlyer, ya sea desde el SDK integrado en tu aplicación o desde eventos de servidor a servidor.  <br />**Consejo**: si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a comprobarlo. |
| **Identificador de Evento de Partner** | El nombre único o el ID de cada evento, tal como se define en Addict Mobile.  <br />Obtén el ID de evento correspondiente de Addict Mobile e introdúcelo en el campo de texto. |
| **Enviar Ingresos** | **Si no está marcada**: envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Addict Mobile para atribuir las campañas, los conjuntos de anuncios o los anuncios individuales de Addict Mobile. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución que generas.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Los parámetros que ya están definidos en el enlace de atribución pueden editarse agregándolos junto con sus valores nuevos en esta sección.

* **Campaña** - añádela para comparar distintas campañas en ejecución con Addict Mobile.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjunto de anuncios para comparar distintos conjuntos de anuncios dentro de campañas específicas de Addict Mobile.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos de campañas específicas de Addict Mobile.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio utilizados y usar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones de ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo del clic a la instalación**. Solo las instalaciones (primeros inicios) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Addict Mobile.

**Parámetro de enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Addict Mobile para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a Addict Mobile, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro de enlace de atribución:** af\_viewthrough\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución view-through</Anchor>.

<div id="impressions-attribution-link" />

### Enlace de atribución de impresiones

El enlace de atribución para impresiones contiene datos de atribución similares a los del enlace de registro del clic (aparte de la ventana retrospectiva diferente). Envíalo a Addict Mobile para que se active cuando se vea el anuncio correspondiente, normalmente durante 1 segundo o más.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

La integración de costos no está disponible para Addict Mobile.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Addict Mobile no admite datos de ingresos por publicidad.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgar a Addict Mobile, tanto si el partner actúa como ad network, agencia o ambos. Ten en cuenta que, aunque la atribución esté deshabilitada para Addict Mobile, la pestaña de permisos está activa y puedes otorgar el control a Addict Mobile.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

<div id="ad-network-permissions" />

### Permisos de ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuario fiel*** - solo a los datos de usuario fiel propios del partner
* ***Permitir acceso a tus datos agregados de eventos in-app** -* solo a los datos de eventos in-app propios del partner
* ***Permitir acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

<div id="agency-permissions" />

### Permisos de la agencia

Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* ***Selector principal*** - actívalo para mostrar las opciones de permisos para agencias
* ***Permitir acceso a tu reporte de retención***: solo a los datos de retención propios de la agencia
* ***Permitir el acceso a datos agregados orgánicos.***
* ***Permitir configurar postbacks de eventos in-app***: permite que la agencia configure en la pestaña de integración la asignación de postbacks de eventos in-app a sí misma

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos a las agencias</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-addict-mobile=configuraci%C3%B3n-de-addict-mobile h_01HJR633087HDAET7KHT8E9XEB=configuraci%C3%B3n-de-addict-mobile h_01HJR63308JRT30ATJGHK8ENGD=integration-tab activate-partner=activar-socio h_01HJR6330800PFWSAB8A3GXMW4=activar-socio general-settings=configuraci%C3%B3n-general h_01HJR63308AZ4815GFH2JMV1G5=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HJR63308QQN56PHAZJJEEN46=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HJR63309W68NWQ8JBH44HJRT=configuraci%C3%B3n-de-eventos-in-app h_01HJR63309HPDZGQTG2P5429GX=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HJR63309YXMMFWC3BJ5P4QZ6=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HJR63309B694DZTGKBCEJ9Q5=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HJR633091B528NHJC60RQ9QT=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HJR63309G1W0P1Y5CZQ9MWYF=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HJR633092XASXD3STXJW5RN7=enlace-de-atribuci%C3%B3n-de-impresiones h_01HJR63309MSKSWQNCSCYC33BR=cost-tab h_01HJR633092FJD6G3P97ZBG4WA=ad-revenue-tab h_01HJR63309BHWNSKQ7Y63P2B9M=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HJR63309BKERBX97ZRPHC4EC=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HJR6330A35DEFCHZA2DC95WR=permisos-de-la-agencia" />
