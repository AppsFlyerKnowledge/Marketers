---
title: Configuración de la campaña de NativeX
metadata:
  keywords:
    - Advertisers
    - NativeX
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-28T12:46:22Z'
  edited_at: '2026-08-22T00:25:23Z'
  id: 208209876
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/208209876
---
> **De un vistazo:** NativeX, partner integrado de AppsFlyer, es una red de publicidad móvil especializada en formatos de anuncios nativos que se integran de forma fluida en el juego o la aplicación del usuario, lo que aporta mayores ingresos a los desarrolladores. Además de la atribución móvil basada en clics, NativeX también ofrece atribución de costo y view-through, que puedes registrar con AppsFlyer.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobvista.png?v=1" width="150px" />

<div id="setting-up-nativex" />

## Configuración de NativeX

**Requisito previo:** Una cuenta con el Partners. Si no tienes una cuenta, contacta con el Partners para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Collaborate > Partner Integrations > Active integrations** .)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el selector **Activar Partners**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el Partners**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners.</Anchor>

La ventana de configuración de NativeX incluye 4 pestañas activas: Integración, enlace de atribución, costo y permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

> 📘 **Note**
>
> * El paso de configuración general en la pestaña de integración es **obligatorio** para todos los Partners
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="activate-partners" />

### Activar los partners

En la **primera visita** aquí, tendrás que activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

Configuración general

**Identificación de la aplicación**

NativeX se conecta con AppsFlyer a través de un ID de App w3i único. Si todavía no tienes un ID de App, debes obtenerlo de NativeX para continuar con la integración.

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir instalaciones view-through desde NativeX. El control deslizante de la ventana retrospectiva por impresiones está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a NativeX después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir la **fuente de los usuarios** que permite enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para los eventos procedentes únicamente de usuarios atribuidos a NativeX.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a NativeX mediante postbacks.

1. Vuelve a introducir el ID de aplicación w3i.
2. Activa los postbacks de eventos in-app.
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
4. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
5. Completa los siguientes parámetros:

| Nombre de Parámetro | Description |
| --- | --- |
| **Nombre del evento del SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de Evento de Partner** | El nombre único o ID de cada evento según se define en NativeX.  <br />Obtén el ID de evento correspondiente de NativeX y configúralo en el campo de texto. |
| **Enviar Ingresos** | **Cuando no está marcada** - se envían al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Cuando está marcada** - envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieres enviar a NativeX para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de NativeX. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Los parámetros que ya están definidos en el enlace de atribución pueden editarse agregándolos junto con sus valores nuevos en esta sección.

* **Campaña** - añádela para comparar diferentes campañas en funcionamiento con NativeX.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de NativeX.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar diferentes creatividades dentro de conjuntos de anuncios específicos, en campañas específicas de NativeX.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro de ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio utilizados y usar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo del clic a la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse a NativeX.

**Parámetro de enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a NativeX para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a NativeX, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro de enlace de atribución:** af\_viewthrough\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución view-through aquí</Anchor>.

<div id="impressions-attribution-link" />

### Enlace de atribución de impresiones

El enlace de atribución para impresiones contiene datos de atribución similares a los del enlace de registro del clic (aparte de la ventana retrospectiva diferente). Envíalo a NativeX para que se active cuando se vea el anuncio correspondiente, normalmente durante 1 segundo o más.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

NativeX envía automáticamente datos de costos CPI cifrados en el enlace de atribución para todas las instalaciones.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los datos de ingresos por publicidad no son compatibles con NativeX.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgar a NativeX, tanto si el partner actúa como ad network, agencia o incluso ambas cosas. Ten en cuenta que, aunque la atribución esté desactivada para NativeX, la pestaña Permisos sigue activa y puedes otorgar el control a NativeX.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

<div id="ad-network-permissions" />

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

<div data-zendesk-anchors="setting-up-nativex=configuraci%C3%B3n-de-nativex h_01HKW7WZR589NZ45YYQB48W2M5=configuraci%C3%B3n-de-nativex h_01HKW7WZR52157AQERBZY0VV75=integration-tab activate-partners=activar-los-partners h_01HKW7WZR5QY0Y3NAKAGMJ8W6C=activar-los-partners default-postbacks=postbacks-predeterminados h_01HKW7WZR51EWEB7Q0JDA69T2Z=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW7WZR5P648PG9P2E7E7XRM=configuraci%C3%B3n-de-eventos-in-app h_01HKW7WZR6W3ANFNEKZQ90RBTJ=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW7WZR617PKZ0GT3BME4NQH=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKW7WZR68SBAC1XFH5143FXP=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW7WZR6GQ15Y45TC5FKDX54=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HKW7WZR6QJ9P1KB54TWFD0YC=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW7WZR6Q7Q77EF1J9V3BHMR=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW7WZR6RGPNHCVPX80FW1Q6=cost-tab h_01HKW7WZR6955K4V6NA6MJ519J=ad-revenue-tab h_01HKW7WZR61N5CH1PZBE9YCNVA=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKW7WZR6KMJS50DNJX5E7KQ1=permisos-de-ad-network" />
