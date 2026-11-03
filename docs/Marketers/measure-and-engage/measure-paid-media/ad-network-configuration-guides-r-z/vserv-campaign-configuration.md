---
title: Configuración de la campaña de Vserv
metadata:
  keywords:
    - Vserv
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
  created_at: '2016-04-04T14:16:31Z'
  edited_at: '2026-09-11T00:25:19Z'
  id: 208277106
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/208277106
---
> **De un vistazo:** Vserv, un partner integrado de ad network de AppsFlyer, es una de las principales plataformas de datos auténticos para marketing móvil en India y el Sudeste Asiático.

## Configuración de Vserv

**Requisito previo:** una cuenta con el Partners. Si no tienes una cuenta, contacta con el Partners para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar Partners**.   
   **Nota:** el selector **debe permanecer activado (activo) mientras trabajes con el Partners**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas pertinentes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

### Activar los partners

En la **primera visita** aquí, tendrás que activar el botón ***Activar Partners*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

> 📘 **Nota:**
>
> Como red de TODAS las instalaciones, Vserv prefiere recibir postbacks de todas las nuevas instalaciones de tu App desde CUALQUIER fuente, incluida la orgánica. Para hacerlo, selecciona **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a Vserv.

### Postbacks predeterminados

Envía postbacks automáticos a Vserv después de las instalaciones y re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos procedentes solo de usuarios atribuidos a Vserv.

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a Vserv mediante postbacks.

1. Activa los postbacks de eventos in-app.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define Vserv.  <br />Obtén el ID de evento correspondiente de Vserv e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Vserv para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Vserv. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña** - añádela para comparar diferentes campañas en funcionamiento con Vserv.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Vserv.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar diferentes creativos dentro de conjuntos de anuncios específicos de campañas específicas de Vserv.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** y **ID de subsitio** - configura el parámetro ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones de ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros de enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Vserv.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic</Anchor>.

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Vserv para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

La integración de costos no está disponible para Vserv.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los datos de ingresos por publicidad no son compatibles con Vserv.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a Vserv, tanto si el partner actúa como ad network, agencia o incluso ambas cosas. Ten en cuenta que, incluso si la atribución está deshabilitada para Vserv, la pestaña de permisos está activa y puedes otorgarle el control a Vserv.

### Permisos de ad network

* ***Permitir configurar la integración*** - permite que el partner configure la pestaña de integración (excepto los postbacks de eventos in-app)
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-vserv=configuraci%C3%B3n-de-vserv h_01HJZVBAHC7Y1T02AZK42AT59S=configuraci%C3%B3n-de-vserv h_01HJZVBAHC6SYY021F2Z1W4RGR=integration-tab activate-partners=activar-los-partners h_01HJZVBAHCXS16GYP3016EH1SF=activar-los-partners h_01HJZVBAHCN1992B9A1883TFQM=nota default-postbacks=postbacks-predeterminados h_01HJZVBAHC6C7QZ2J6ZEX091JP=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HJZVBAHCB071S91V63BQW5EG=configuraci%C3%B3n-de-eventos-in-app h_01HJZVBAHDV2MDHCCZ928X1GNW=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HJZVBAHDJ754YN20BZ2S69MS=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HJZVBAHD5YVQ6MV9KAHETQVQ=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HJZVBAHD04E14BE61W10Y5HJ=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HJZVBAHDBY5F580GCRWH3BNG=cost-tab h_01HJZVBAHDR79RZ69T4E78T6SR=ad-revenue-tab h_01HJZVBAHD4BAADJXZMK4QSX58=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HJZVBAHDEFT99AY91S264205=permisos-de-ad-network" />
