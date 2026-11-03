---
title: Configuración de la campaña de Tyroo
metadata:
  keywords:
    - Advertisers
    - Tyroo
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-03T11:32:42Z'
  edited_at: '2026-09-11T00:25:11Z'
  id: 208270836
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/208270836
---
> **De un vistazo:** Tyroo, un partner integrado de ad network de AppsFlyer, es una plataforma líder mundial de adquisición de usuarios móviles y monetización. Además de la atribución móvil basada en clics, Tyroo ofrece atribución de costos y view-through, que se pueden registrar en AppsFlyer.

Para configurar tus campañas con Tyroo, sigue los pasos a continuación.

## Configuración de Tyroo

**Requisito previo:** Una cuenta con el socio. Si no tienes una cuenta, ponte en contacto con el socio para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace**.  
   (**Para editar una integración existente:** ve a la pestaña **Collaborate > Partner Integrations > Active integrations**.)
2. Selecciona la aplicación correspondiente.
3. Busca el socio y selecciona **Integrate**.
4. En la pestaña **Integration**, activa el interruptor **Activate partner**.   
   **Nota:** El interruptor **debe permanecer activado (activo) mientras trabajes con el socio**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas pertinentes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

### Activar socio

En la **primera visita** aquí, deberás activar el selector ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

> 📘 **Nota:**
>
> Como red de TODAS las instalaciones, Tyroo prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluida la orgánica. Para hacerlo, selecciona **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a Tyroo.

### Configuración general

**ID de socio**

Tyroo se conecta con AppsFlyer mediante una clave de acción única. Si aún no tienes la clave de acción, debes obtenerla de Tyroo para continuar con la integración.

**Habilitar la atribución por impresiones**

Actívalo si quieres atribuir las instalaciones view-through de Tyroo. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

### Postbacks predeterminados

Envía postbacks automáticos a Tyroo después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para los eventos que provengan únicamente de usuarios atribuidos a Tyroo.  
Selecciona **Eventos atribuidos a cualquier partner u orgánico** para tener toda tu base de usuarios disponible para ser reportada a Tyroo.

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a Tyroo mediante postbacks.

1. Activa los postbacks de eventos in-app
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define Tyroo.  <br />Obtén el ID de evento correspondiente de Tyroo e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Tyroo para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Tyroo. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: agrégala para comparar diferentes campañas en funcionamiento con Tyroo.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Tyroo.  
  **Parámetro del enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar diferentes creativos dentro de conjuntos de anuncios específicos, dentro de campañas específicas de Tyroo.  
  **Parámetro del enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro de ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros del enlace de atribución de AppsFlyer**</Anchor>.

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Tyroo.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clics</Anchor>.

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Tyroo para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a Tyroo, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro del enlace de atribución:** af\_viewthrough\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución por impresiones</Anchor>.

### Enlace de atribución de impresiones

El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Envíalo a Tyroo para que se active cuando se vea un anuncio correspondiente, normalmente durante 1 segundo o más.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Tyroo envía automáticamente datos de costo de CPI en el enlace de atribución para todas las instalaciones.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a Tyroo, tanto si el partner actúa como ad network, como agencia o incluso como ambas cosas. Ten en cuenta que, aunque la atribución esté deshabilitada para Tyroo, la pestaña de permisos sigue activa y puedes otorgar el control a Tyroo.

Usa estos selectores para otorgar permisos a la ad network para que gestione su propia configuración para tu App: Permisos de la ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingres*os** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-tyroo=configuraci%C3%B3n-de-tyroo h_01HJZTZ361TE694SVPQTN8Q4C1=configuraci%C3%B3n-de-tyroo h_01HJZTZ361V5G81NBA1G0ZBXJG=integration-tab activate-partner=activar-socio h_01HJZTZ361FKYED35K4E57DEJ4=activar-socio h_01HJZTZ361QM6Z3N693N3PJ1Z9=nota general-settings=configuraci%C3%B3n-general h_01HJZTZ362XG66Q54JRATHJW9X=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HJZTZ3621ZWG5TZD76Z80DHE=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HJZTZ362WMPD0C1HMG8HC2HD=configuraci%C3%B3n-de-eventos-in-app h_01HJZTZ3627FHZS6J5FABPJJ1Q=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HJZTZ362TG648JZEXWX3MK5P=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HJZTZ362TCHGN0MGRA0B9Z7P=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HJZTZ36282E6VNNH740AF9EW=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HJZTZ362V11V157Q2NFN550W=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HJZTZ362ZF2FY83NMD5ZJ89J=enlace-de-atribuci%C3%B3n-de-impresiones h_01HJZTZ362JBBAZ5RDWJ03EE2X=cost-tab h_01HJZTZ36323B1PET2X3FPD1H1=ad-revenue-tab h_01HJZTZ3637M1AMNTWXV9NPNGV=permissions-tab" />
