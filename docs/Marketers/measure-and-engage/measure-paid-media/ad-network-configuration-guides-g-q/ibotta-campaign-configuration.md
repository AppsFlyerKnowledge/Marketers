---
title: Configuración de la campaña de Ibotta
metadata:
  keywords:
    - Advertisers
    - Ibotta
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-02-18T07:55:23Z'
  edited_at: '2026-09-10T00:24:12Z'
  id: 360000295445
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/360000295445
---
> **De un vistazo:** Ibotta, un partner de ad network integrado con AppsFlyer, facilita a los consumidores obtener cashback en sus compras diarias a través de una única app para smartphone.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ibotta.png?v=1" width="119px" />

## Configuración de Ibotta

**Requisito previo:** una cuenta con el socio. Si no tienes\n una cuenta, ponte en contacto con el socio para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña\n **Collaborate > Partner Integrations > Marketplace** .  
    (**Para editar una integración existente:** Ve a la pestaña **Collaborate > Partner Integrations > Active integrations** .)
2. Selecciona la aplicación correspondiente.
3. Busca el socio y selecciona **Integrate**.
4. En la pestaña **Integration**, activa el conmutador **Activate partner**.   
    **Nota:** El conmutador **debe permanecer activado (activo) mientras trabajes con el socio**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber\n más sobre\n <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

> 👍 **Consejo**
>
> * El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">Configuración general</Anchor> en la pestaña de Integración es **obligatorio** para todos los partners.
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

### Activar socio

En la **primera visita**, tendrás que activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

Postbacks predeterminados

Envía postbacks automáticos a Ibotta tras las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos procedentes solo de usuarios atribuidos a Ibotta.

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a Ibotta mediante postbacks.

> 👍 **Consejo**
>
> Para una integración simple y rápida, selecciona **Enviar todos los eventos excluyendo su valor de ingresos** o **Enviar todos los eventos incluyendo su valor de ingresos**

1. Activa los postbacks de eventos in-app.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK integrado con tu aplicación, o desde eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define Ibotta.  <br />Obtén el ID de evento correspondiente de Ibotta e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Cuando está marcada**: se envían todos los parámetros incluyendo el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Ibotta para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Ibotta. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña** - añádela para comparar distintas campañas en ejecución con Ibotta.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar distintos conjuntos de anuncios dentro de campañas específicas de Ibotta.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos de campañas específicas de Ibotta.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre **<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">la estructura y los parámetros de los enlaces de atribución de AppsFlyer</Anchor>.**

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Ibotta.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Ibotta para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

La integración de costos no está disponible para este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La integración de ingresos por publicidad no está disponible para este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a Ibotta, tanto si el partner actúa como ad network, agencia o incluso como ambas cosas. Ten en cuenta que, aunque la atribución esté deshabilitada para Ibotta, la pestaña Permisos está activa y puedes otorgarle el control a Ibotta.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

### Permisos de ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles*** - solo a los datos de usuarios fieles propios del socio
* ***Permitir acceso a tus datos agregados de eventos in-app** -* solo a los datos de eventos in-app propios del socio
* **Permitir acceso a tus datos agregados de ingresos**: solo a los datos de ingresos atribuidos al partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-ibotta=configuraci%C3%B3n-de-ibotta h_01HKA2KDA0JDAF8VEXFH57Q9DP=configuraci%C3%B3n-de-ibotta h_01HKA2KDA0TVNGZQ7EN899112F=consejo h_01HKA2KDA05VRNN6YYTBS0AAYD=integration-tab activate-partner=activar-socio h_01HKA2KDA0GA8GHDP2177EYV3Z=activar-socio inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKA2KDA0J38WY51ZCP77J7A6=configuraci%C3%B3n-de-eventos-in-app h_01HKA2KDA0HKAP9ACF2V8ZCPHX=consejo-1 h_01HKA2KDA0QG78TCTKQKPZR0JV=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKA2KDA0YP8SYP4YJ5NG5QSN=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKA2KDA0VPPYRMPY3S11ASX5=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKA2KDA0CZSSXW8DTCBTQ022=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKA2KDA18SHG1YAZNTE3TBZ8=cost-tab h_01HKA2KDA1JS9YF2WEEHR2K5TD=ad-revenue-tab h_01HKA2KDA1EF0F3JG3F81V3FHG=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKA2KDA1Y2XEFHMV3XWQDDKW=permisos-de-ad-network" />
