---
title: Configuración de la campaña de Leadbolt
metadata:
  keywords:
    - Advertisers
    - Leadbolt
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-10-05T09:37:19Z'
  edited_at: '2026-09-11T00:23:58Z'
  id: 213504346
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/213504346
---
> **De un vistazo:** Leadbolt, un partner de ad network integrado de AppsFlyer, es una plataforma de publicidad móvil de alto rendimiento para la adquisición de usuarios y la monetización in-app. Además de la atribución móvil basada en clics, Leadbolt también ofrece atribución view-through, que puedes registrar con AppsFlyer.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/leadbolt.png" width="172px" />

<div id="setting-up-leadbolt-integration" />

## Configuración de la integración de Leadbolt

**Requisito previo:** una cuenta con el Partners. Si no tienes una cuenta, ponte en contacto con el Partners para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar Partners**.   
   **Nota:** el selector **debe permanecer activado (activo) mientras trabajes con el Partners**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="h_01HKW22J9FD92D3X3TY0KZMT02" />

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, tendrás que activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="note" />

> 📘 **Nota:**
>
> Como red de TODAS las instalaciones, Leadbolt prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluidas las orgánicas. Para hacerlo, selecciona **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a Leadbolt.

<div id="general-settings" />

### Configuración general

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir instalaciones por impresiones de Leadbolt. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a Leadbolt después de las instalaciones y los re-engagements del usuario. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos procedentes solo de usuarios atribuidos a Leadbolt.  
Selecciona **Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada a Leadbolt.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer con Leadbolt mediante postbacks.

1. Activa los postbacks de eventos in-app.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de Parámetro | Description |
| --- | --- |
| **Nombre del evento del SDK** | El nombre del evento, tal como lo recibe AppsFlyer, ya sea desde el SDK integrado en tu aplicación o desde eventos de servidor a servidor.  <br />**Consejo**: si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a comprobarlo. |
| **Identificador de Evento de Partner** | El nombre único o ID de cada evento, tal como se define en Leadbolt.  <br />Obtén el ID de evento correspondiente de Leadbolt e introdúcelo en el campo de texto. |
| **Enviar Ingresos** | **Cuando no está marcada** - envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada** - envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Leadbolt para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Leadbolt. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Los parámetros que ya están definidos en el enlace de atribución pueden editarse agregándolos junto con sus valores nuevos en esta sección.

* **Campaña** - añádela para comparar diferentes campañas en funcionamiento con Leadbolt.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Leadbolt.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar diferentes creatividades dentro de conjuntos de anuncios específicos, dentro de campañas específicas de Leadbolt.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro de ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar la cantidad de IDs de sitio que usas y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo entre el clic y la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Leadbolt.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más información sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Leadbolt para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo desde la impresión hasta la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a Leadbolt, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro de enlace de atribución:** af\_viewthrough\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución view-through aquí</Anchor>.

<div id="impressions-attribution-link" />

### Enlace de atribución de impresiones

El enlace de atribución para impresiones contiene datos de atribución similares a los del enlace de registro del clic (aparte de la ventana retrospectiva diferente). Envíalo a Leadbolt para que se active cuando se vea el anuncio correspondiente, normalmente durante 1 segundo o más.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

La integración de costos no está disponible para Leadbolt.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La integración de los ingresos por publicidad no está disponible para Leadbolt.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgar a Leadbolt, tanto si el partner actúa como ad network, agencia o incluso ambas. Ten en cuenta que, aunque la atribución esté desactivada para Leadbolt, la pestaña de permisos está activa y puedes otorgar el control a Leadbolt.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

<div id="ad-network-permissions" />

### Permisos de ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles*** - solo a los datos de usuarios fieles propios de Partners
* ***Permitir acceso a tus datos agregados de eventos in-app** -* solo a los datos de eventos in-app propios de Partners
* ***Permitir acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-leadbolt-integration=configuraci%C3%B3n-de-la-integraci%C3%B3n-de-leadbolt h_01HKW22J9F43T9E4DGB7R5JQMC=configuraci%C3%B3n-de-la-integraci%C3%B3n-de-leadbolt h_01HKW22J9FPX748HK6WGYQWQW5=integration-tab activate-partner=activar-socio h_01HKW22J9FKR3G9R0ZMX3R8ESQ=activar-socio h_01HKW22J9GZ52VRVJWW5361KWP=nota general-settings=configuraci%C3%B3n-general h_01HKW22J9GARYNP2EP5MKWDHCN=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKW22J9G2P3DW3VJ0RTPVAAZ=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW22J9G2QEBT62HYFECTYGE=configuraci%C3%B3n-de-eventos-in-app h_01HKW22J9G8BB13YT8PM6WT20V=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW22J9G3P1913HASGB0BPRP=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKW22J9HJQWGQRC3E9MZJV5G=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW22J9HT8PV3FEPT4T84N3S=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HKW22J9H27S9FVV8PQ7W64T9=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW22J9HMHT0XQ99SHCEP8A7=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW22J9HK8TVMPQ67CKQ12Q8=cost-tab h_01HKW22J9HH60TCDMDXZ74D2T0=ad-revenue-tab h_01HKW22J9H3YRYRZFC5YPFWEJA=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKW22J9H187534M60RBXX33S=permisos-de-ad-network" />
