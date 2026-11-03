---
title: Configuración de la campaña de Mobusi
metadata:
  keywords:
    - Advertisers
    - Mobusi
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-11-14T09:59:36Z'
  edited_at: '2026-09-11T00:24:14Z'
  id: 217909583
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/217909583
---
> **De un vistazo:** Mobusi, partner integrado de AppsFlyer, es una empresa de adquisición de usuarios móviles y servicios de marketing con experiencia en publicidad de rendimiento.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobusi.png?v=1" width="119px" />

## Configuración de Mobusi

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

### Activar socio

En la **primera visita** aquí, debes activar el botón ***Activate Partner*** para habilitar la configuración de los parámetros de la pestaña Integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

### Postbacks predeterminados

Envía postbacks automáticos a Mobusi después de las instalaciones y los re-engagements de usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

### Configuración de postbacks de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a Mobusi mediante postbacks.

1. Activa los postbacks de eventos in-app.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre único o ID de cada evento según lo define Mobusi.  <br />Obtén el ID de evento correspondiente de Mobusi y configúralo en el campo de texto. |
| **Enviar ingresos** | **Si no está marcada** - se envían al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada** - se envían todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Mobusi para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Mobusi. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución aquí te permite realizar análisis detallados más adelante. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña** - añádela para comparar distintas campañas en ejecución con Mobusi.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar distintos conjuntos de anuncios dentro de campañas específicas de Mobusi.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de conjuntos de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos dentro de campañas específicas de Mobusi.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** y **ID de subsitio** - configura el parámetro ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio utilizados y usar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros del suscriptor** - usa cualquiera de los 5 parámetros del suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Mobusi.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clics</Anchor>.

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Mobusi para que se active cuando los leads hagan clic en el anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

La integración de costos no está disponible para Mobusi.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Mobusi no admite los ingresos por publicidad.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a Mobusi, tanto si el partner actúa como ad network, agencia o ambos. Ten en cuenta que, aunque la atribución esté deshabilitada para Mobusi, la pestaña de permisos está activa y puedes otorgarle el control a Mobusi.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

### Permisos de ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-mobusi=configuraci%C3%B3n-de-mobusi h_01HKW6QHJZQ1FJ0GWJNPN4NNCF=configuraci%C3%B3n-de-mobusi h_01HKW6QHK0B8EK4AA8R7SF706S=integration-tab activate-partner=activar-socio h_01HKW6QHK07P5N6SQGAY5MPJ65=activar-socio default-postbacks=postbacks-predeterminados h_01HKW6QHK0DCP5VMNDE41TVSNE=postbacks-predeterminados inapp-event-postbacks-settings=configuraci%C3%B3n-de-postbacks-de-eventos-in-app h_01HKW6QHK0Z6HEB561G5TK0D3M=configuraci%C3%B3n-de-postbacks-de-eventos-in-app h_01HKW6QHK09DD7AX0XJ43FHT37=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW6QHK0NE8NBPAK2M7SJY42=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKW6QHK0ZWZYDJ9YV65A2QWK=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW6QHK0A6J59W4RN5Z9MW9P=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW6QHK0R77NY5CDRQEV1EB1=cost-tab h_01HKW6QHK0B3252ZXHPYM4BP7B=ad-revenue-tab h_01HKW6QHK0HDSBTAKEWZETYH02=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKW6QHK0H2SMDE61MSXNZP9D=permisos-de-ad-network" />
