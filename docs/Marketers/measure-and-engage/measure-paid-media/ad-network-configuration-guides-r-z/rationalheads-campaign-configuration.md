---
title: Configuración de la campaña de RationalHeads
metadata:
  keywords:
    - rationalheads
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
  created_at: '2016-04-04T15:30:57Z'
  edited_at: '2026-08-12T12:15:30Z'
  id: 208277926
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/208277926
---
> **En resumen:** Remerge, un partner integrado de ad network de AppsFlyer, permite a los profesionales del marketing de aplicaciones ofrecer anuncios personalizados y mejor ubicados. Además de la atribución móvil basada en clics, Remerge ofrece atribución móvil view-through y retargeting basado en clics, que pueden registrarse con AppsFlyer.

<div id="setting-up-rationalheads" />

## Configurar RationalHeads

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con el partner.  
    Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación. Para ver una descripción detallada del Encabezado de la ventana de configuración de partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

La ventana de configuración de RationalHeads incluye 3 pestañas activas: Integración, enlace de atribución y permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

Para ver una descripción detallada del Partner Configuration Window Header, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="tip" />

> 👍 **Consejo**
>
> * El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">Configuración general</Anchor> en la pestaña de Integración es **obligatorio para todos los partners**.
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="general-settings" />

### Configuración general

**ID de pieza**

RationalHeads se conecta con AppsFlyer a través de un ID de parte único. Si aún no tienes el ID de parte y la contraseña, debes obtenerlos de RationalHeads para continuar con la integración.

<Image alt="Rationalheads_msc_new_2.png" src="https://files.readme.io/7e93003c13d4fa1e60bee4120307691b618757a7c55a271561827823005b86c3-360002076529.png" width="317px" />

<div id="default-postbacks" />

### Postbacks predeterminados

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

Envía postbacks automáticos a RationalHeads tras las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos provenientes solo de usuarios atribuidos a RationalHeads.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a RationalHeads mediante postbacks.

1. Activa los Postbacks de eventos in-app con el selector.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo definido en RationalHeads.  <br />Obtén el ID de evento correspondiente de RationalHeads y configúralo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieres enviar a RationalHeads para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de RationalHeads. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: añádela para comparar distintas campañas de RationalHeads.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de RationalHeads.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio**: establece nombres de anuncios para comparar diferentes creatividades dentro de conjuntos de anuncios específicos, dentro de campañas específicas de RationalHeads.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio**: configura el parámetro ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar la cantidad de ID de sitio que usas y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder los límites del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeros lanzamientos) que tengan lugar dentro de la ventana de lookback pueden atribuirse a RationalHeads.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a RationalHeads para que se active cuando los leads hagan clic en el anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Los datos de costos no son compatibles con la integración con este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgar a RationalHeads, tanto si el partner actúa como ad network, agencia o incluso como ambas. Ten en cuenta que, aunque la atribución esté deshabilitada para RationalHeads, la pestaña de permisos está activa y puedes conceder el control a RationalHeads.

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

</Accordion>

<div data-zendesk-anchors="setting-up-rationalheads=configurar-rationalheads h_01HJRZB6JCPYZZJ3QWS9BRJPSX=configurar-rationalheads h_01HJRZB6JC4GDCV3RVGJBFTPAT=consejo h_01HJRZB6JCE5G700RRHGJY3M4A=integration-tab general-settings=configuraci%C3%B3n-general h_01HJRZB6JCXARZ29M8RCP30VBD=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HJRZB6JCXR6ZHH3YV05W6JY1=postbacks-predeterminados activate-partner=activar-socio h_01HJRZB6JCW3C1AWRS4041SKJP=activar-socio inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HJRZB6JDH6A108JYXEST4AQY=configuraci%C3%B3n-de-eventos-in-app h_01HJRZB6JDG7YQD0ANE4W8C55C=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HJRZB6JDM91MC9B4VXCHEW6Z=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HJRZB6JDQ148X9J0XCFPVZD1=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HJRZB6JDZ27KM6N7GVZX54CW=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HJRZB6JDJG6HVCEXMC5S30NM=cost-tab h_01HJRZB6JDTJE0K27Y4XTJG7QX=ad-revenue-tab h_01HJRZB6JDD32KPQ13CTEEMEBB=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HJRZB6JD6412B28R5N8MRVH3=permisos-de-ad-network" />
