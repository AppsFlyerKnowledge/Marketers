---
title: Configuración de la campaña de Yeahmobi
metadata:
  keywords:
    - yeah-mobi
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
  created_at: '2016-03-28T10:00:25Z'
  edited_at: '2026-09-11T00:25:37Z'
  id: 209731663
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/209731663
---
> **De un vistazo:** Yeahmobi, un partner integrado de ad network de AppsFlyer, es una ad network de video para iOS y Android. Además de la atribución móvil basada en clics, Yeahmobi proporciona datos de costo, que se pueden registrar con AppsFlyer.

Para configurar tus campañas con Yeahmobi, sigue los pasos a continuación.

## Configuración de Yeahmobi

**Requisito previo:** una cuenta con el Partners. Si no tienes una cuenta, contacta con el Partners para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el conmutador **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

### Activar los partners

En la **primera visita** aquí, tendrás que activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector **debe** estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

### Postbacks predeterminados

Envía postbacks automáticos a Yeahmobi después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos procedentes solo de usuarios atribuidos a Yeahmobi.  
Selecciona **Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada a Yeahmobi.

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a Yeahmobi mediante postbacks.

1. Activa Postbacks de evento in-app.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que proceden **solo** de usuarios atribuidos a este partner.  
   **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de Parámetro | Description |
| --- | --- |
| **Nombre del evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a comprobarlo. |
| **Identificador de Evento de Partner** | El nombre único o ID de cada evento, tal como se define en Yeahmobi.  <br />Obtén el ID de evento correspondiente de Yeahmobi e introdúcelo en el campo de texto. |
| **Enviar Ingresos** | **Si no está marcada**: envía al Partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Yeahmobi para atribuir campañas, conjuntos de anuncios o incluso anuncios individuales de Yeahmobi. Ten en cuenta que AppsFlyer **no** guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Los parámetros que ya están definidos en el enlace de atribución pueden editarse agregándolos junto con sus valores nuevos en esta sección.

* **Campaña** - añádela para comparar diferentes campañas en funcionamiento con Yeahmobi.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjunto de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Yeahmobi.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre de anuncio**: define nombres de anuncios para comparar diferentes creatividades dentro de conjuntos de anuncios específicos de campañas específicas de Yeahmobi.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio**: configura el parámetro ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar la cantidad de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Yeahmobi.

**Parámetro de enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Yeahmobi para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Yeahmobi envía automáticamente datos de costo de CPI en el enlace de atribución para todas las instalaciones.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Este partner no admite ingresos por publicidad.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle al partner, ya sea que el partner actúe como una red de publicidad, agencia o ambas. Tenga en cuenta que, incluso si la atribución estuviera deshabilitada para el socio, la pestaña Permisos se encontraría activa y podría darle el control al socio.

### Permisos de ad network

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir el acceso a tus datos agregados de usuarios fieles*** - solo a los datos de usuarios fieles propios del partner
* ***Permitir el acceso a tus datos agregados de eventos in-app** -* solo a los datos de eventos in-app propios del partner
* ***Permitir acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al Partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

### Permisos de la agencia

Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* ***Selector principal***: actívalo para mostrar las opciones de permisos de la agencia
* ***Permitir configurar postbacks de eventos in-app***: permite que la agencia configure en la pestaña de integración la asignación de postbacks de eventos in-app a sí misma
* ***Permitir el acceso a datos agregados orgánicos.***
* ***Permitir acceso a tu reporte de retención***: solo a los datos de retención propios de la agencia

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos a las agencias</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-yeahmobi=configuraci%C3%B3n-de-yeahmobi h_01HK290F4KYKPR30MW5EH7XSTG=configuraci%C3%B3n-de-yeahmobi h_01HK290F4KJ4JB72D32RPWBA26=integration-tab activate-partners=activar-los-partners h_01HK290F4KQVRHB6VB089A9VFH=activar-los-partners default-postbacks=postbacks-predeterminados h_01HK290F4KVZPHFD23EKC88BNJ=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HK290F4KAK84A1M36VNTFM84=configuraci%C3%B3n-de-eventos-in-app h_01HK290F4KKVB38XP7VP5KSR7V=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HK290F4KV3CNJXW6DP7PSTFQ=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HK290F4M10V9K1AWF8M8JXD1=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HK290F4MV18FSH7GEPBPJESC=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HK290F4MY2F9SX963Q1GGFTV=cost-tab h_01HK290F4MHPH43P52J5ZV9ZC3=ad-revenue-tab h_01HK290F4MZ8MKZVEZPAY8ZBEV=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HK290F4MEXVTJJGAB2BAEGM5=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HK290F4MHH62HP0KRBN9FK9W=permisos-de-la-agencia" />
