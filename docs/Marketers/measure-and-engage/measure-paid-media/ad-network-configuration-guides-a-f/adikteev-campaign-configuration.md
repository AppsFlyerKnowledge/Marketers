---
title: Configuración de la campaña de Adikteev
metadata:
  keywords:
    - Trademob
    - Advertisers
    - adikteev
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-04-20T15:23:26Z'
  edited_at: '2026-09-11T00:22:49Z'
  id: 115001997643
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/115001997643
---
> **De un vistazo:** Adikteev, un partner integrado de ad network de AppsFlyer, es una empresa de tecnología publicitaria centrada en el retargeting in-app y la tecnología publicitaria de engagement. Adikteev ofrece atribución móvil basada en clics y view-through. Además, Adikteev también ofrece retargeting basado en clics que puedes registrar con AppsFlyer.

## Configuración de Adikteev

**Requisito previo:** Una cuenta con el Partners. Si no tienes una cuenta, ponte en contacto con el Partners para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el selector **Activate partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el Partners**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

### Activar socio

En la **primera visita**, debes activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más información sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

Configuración general

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir instalaciones view-through de Adikteev. El control deslizante de la ventana retrospectiva por impresiones está disponible en la pestaña del enlace de atribución (se describe a continuación).

### Postbacks predeterminados

Envía postbacks automáticos a Adikteev después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permite enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos provenientes únicamente de usuarios atribuidos a Adikteev.  
Selecciona **Eventos atribuidos a cualquier partner u orgánicos** para que toda tu base de usuarios esté disponible para reportarla a Adikteev.

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a Adikteev vía postbacks.

1. Activa los postbacks de eventos in-app.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de Parámetro | Description |
| --- | --- |
| **Nombre del evento del SDK** | El nombre del evento, tal como lo recibe AppsFlyer, ya sea desde el SDK integrado en tu aplicación o desde eventos de servidor a servidor.  <br />**Consejo**: si no ves el evento que quieres en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a comprobarlo. |
| **Identificador de Evento de Partner** | El nombre único o ID de cada evento, tal como se define en Adikteev.  <br />Obtén el ID de evento correspondiente de Adikteev e introdúcelo en el campo de texto. |
| **Enviar Ingresos** | **Si no está marcada** - envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está contenido en el parámetro **af\_revenue**.  <br />**Si está marcada** - envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Adikteev para atribuir las campañas, los conjuntos de anuncios o los anuncios individuales de Adikteev. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Los parámetros que ya están definidos en el enlace de atribución pueden editarse agregándolos junto con sus valores nuevos en esta sección.

* **Campaña** - añádela para comparar distintas campañas en funcionamiento con Adikteev.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar distintos conjuntos de anuncios dentro de campañas específicas de Adikteev.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos de campañas específicas de Adikteev.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** y **ID de subsitio** - configura el parámetro ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, recomendamos limitar la cantidad de IDs de sitio utilizados y usar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

### Configuraciones de retargeting

Cuando esta opción está habilitada, AppsFlyer reconoce un enlace como un enlace de atribución de <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">retargeting</Anchor>, en lugar de un enlace de adquisición de usuarios, al añadir `&is_retargeting=true` al enlace de registro de clics. Ten en cuenta que actualmente el retargeting solo es compatible con la atribución por clics y no con la atribución por impresiones.  
**Parámetro del enlace de atribución:** is\_retargeting.

Cuando la opción de retargeting está habilitada, se muestra la siguiente configuración.

1. Enlace estándar vs. OneLink

Selecciona la opción ***enlace de atribución estándar*** si:

* No necesitas un enlace profundo con la URL o
* Planeas usar solo <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">esquemas de URI</Anchor> para Deep Linking

select ***Usar OneLink*** para:

* Utilizar un solo enlace para aplicaciones de Android y iOS, o
* Establecer enlaces profundos empleando enlaces universales o de aplicaciones.

Ten en cuenta que seleccionar OneLink cambia el enlace de registro de clics de una URL específica de la aplicación a una <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">URL de OneLink</Anchor>.

2. URL de deep link

Usa este campo si el enlace está pensado para dirigir mediante Deep Linking a los usuarios a cualquier actividad específica dentro de tu aplicación.  
**Parámetro del enlace de atribución:** af\_dp  
Puedes encontrar más información sobre la solución de AppsFlyer para Deep Linking en <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">esta guía.</Anchor>

3. Ventana de recaptación

Defina el plazo posterior al re-engagement, durante el cual los eventos in-app del usuario se atribuyen a la fuente de medios de redireccionamiento. Puede configurar el valor en días (1-90), horas (hasta 23) o incluso de por vida.

**Parámetro del enlace de atribución:** af\_reengagement\_window

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeros inicios) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Adikteev.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clics</Anchor>.

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Adikteev para que se active cuando los leads hagan clic en el anuncio correspondiente.

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo desde la impresión hasta la instalación**. Solo se atribuyen a Adikteev las instalaciones (primeros inicios) que tengan lugar dentro de esta ventana de lookback después de la impresión de un anuncio, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro del enlace de atribución:** af\_viewthrough\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución por impresiones</Anchor>.

### Enlace de atribución de impresiones

El enlace de atribución para impresiones contiene datos de atribución similares a los del enlace de registro del clic (aparte de la ventana retrospectiva diferente). Envíalo a Adikteev para que se active cuando se vea el anuncio correspondiente, normalmente durante 1 segundo o más.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costo de ad network</Anchor> para ver todos los detalles sobre las dimensiones, métricas y funciones compatibles. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes, ya sea en el Dashboard de estado de integración de costos (e ingresos por anuncios) o en el Dashboard de la ad network individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La integración de ingresos por anuncios no está disponible para Adikteev.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a Adikteev. Ten en cuenta que, incluso si la atribución está deshabilitada para Adikteev, la pestaña de permisos está activa y puedes otorgarle el control a Adikteev.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

### Permisos de ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de Usuario fiel*** - solo a los datos de Usuario fiel propios del partner
* ***Permitir acceso a tus datos agregados de eventos in-app** -* solo a los datos de eventos in-app propios del partner
* ***Permitir acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-adikteev=configuraci%C3%B3n-de-adikteev h_01HKW8X0EG5H5TNFAPSYYM5M25=configuraci%C3%B3n-de-adikteev h_01HKW8X0EG7R9GVHE6KKMPM1X3=integration-tab activate-partner=activar-socio h_01HKW8X0EGRQ9RD1H9Y75PYTVK=activar-socio default-postbacks=postbacks-predeterminados h_01HKW8X0EG7A748Y725KXR9665=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW8X0EGHSJQKV4H9RBWJ97F=configuraci%C3%B3n-de-eventos-in-app h_01HKW8X0EG6NVVGVH423JXBVS4=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW8X0EG70T02X4CZJ5AZPRF=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n retargeting-settings=configuraciones-de-retargeting h_01HKW8X0EGK8HT45848VYHBMH9=configuraciones-de-retargeting clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKW8X0EGA3FGZ86ND0SA7E9H=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW8X0EGWAC5DTTVXJYWRP0C=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HKW8X0EGS2WRVEXNRKWKG162=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW8X0EG1KS0GNXNPHF2J687=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW8X0EGWGAJQPX6QV3CGXNK=cost-tab h_01HKW8X0EGVKZ41TR1KEYQWXH3=ad-revenue-tab h_01HKW8X0EGBBDWXGXZAMTGFAG9=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKW8X0EG69GBGN395DJMMB1S=permisos-de-ad-network" />
