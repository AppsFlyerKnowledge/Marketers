---
title: Configuración de la campaña de Taptica
metadata:
  keywords:
    - taptica
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
  created_at: '2016-07-05T13:00:06Z'
  edited_at: '2026-09-08T00:25:08Z'
  id: 210118726
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/210118726
---
> **De un vistazo:** Taptica, un partner integrado de ad network de AppsFlyer, ofrece soluciones de marketing centradas en los datos que impulsan la ejecución y aportan insights de marca potentes en dispositivos móviles. Además de la atribución móvil basada en clics, Taptica ofrece atribución de costo, retargeting y view-through, que se puede registrar en AppsFlyer.

Para configurar tus campañas con Taptica, sigue los pasos a continuación.

## Configuración de Taptica

**Requisito previo:** una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace** .  
   (**Para editar una integración existente:** ve a la pestaña **Collaborate > Partner Integrations > Active integrations** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el selector **Activate partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

La ventana de configuración de Taptica incluye 3 pestañas activas: Integración, Enlace de atribución y Permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

Para ver una descripción detallada del Partner Configuration Window Header, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

> 👍 **Consejo**
>
> * El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">Configuración general</Anchor> en la pestaña de Integración es **obligatorio** para todos los partners.
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

### Activar socio

En la **primera visita** aquí, deberás activar el selector **Activar partner** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

### Configuración general

**Habilitar la atribución por impresiones**

Activa esta opción en ON si quieres atribuir las instalaciones view-through de Taptica. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

### Postbacks predeterminados

Envía postbacks automáticos a Taptica tras las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos que procedan solo de usuarios atribuidos a Taptica.  
Selecciona **Eventos atribuidos a cualquier partner u orgánicos** para que toda tu base de usuarios esté disponible para ser reportada a Taptica.

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a Taptica mediante postbacks.

1. Activa los postbacks de eventos in-app.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre único o el ID de cada evento, tal como se define en Taptica.  <br />Obtén el ID de evento correspondiente de Taptica e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Taptica para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Taptica. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña** - añádela para comparar diferentes campañas en funcionamiento con Taptica.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Taptica.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar diferentes creativos dentro de conjuntos de anuncios específicos de campañas específicas de Taptica.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de ID de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

### Configuraciones de retargeting

Cuando está habilitado, AppsFlyer reconoce un enlace como un enlace de atribución de <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">retargeting</Anchor>, en lugar de como un enlace de adquisición de usuarios, al añadir `&is_retargeting=true` al enlace de registro de clics. Ten en cuenta que actualmente el retargeting solo es compatible con la atribución click-through y no con la atribución view-through.  
**Parámetro del enlace de atribución:** is\_retargeting.

Cuando la opción de retargeting está habilitada, se muestra la siguiente configuración.

1. Enlace estándar vs. OneLink

Selecciona la opción ***enlace de atribución estándar*** si:

* No necesitas un enlace profundo con la URL o
* Planea utilizar solo <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">esquemas de URI</Anchor> para Deep Linking

selecciona ***Use OneLink*** for:

* Utilizar un solo enlace para aplicaciones de Android y iOS, o
* Establecer enlaces profundos empleando enlaces universales o de aplicaciones.

Ten en cuenta que, al seleccionar OneLink, el enlace de registro de clics cambia de uno específico de la aplicación a una <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">URL de OneLink</Anchor>.

2. URL de deep link

Utiliza este campo si el enlace está pensado para dirigir a los usuarios mediante deep linking a cualquier actividad específica de tu aplicación.  
**Parámetro de enlace de atribución:** af\_dp  
Puedes encontrar más información sobre la <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">solución de Deep Linking de AppsFlyer en esta guía.</Anchor>

3. Ventana de recaptación

Defina el plazo posterior al re-engagement, durante el cual los eventos in-app del usuario se atribuyen a la fuente de medios de redireccionamiento. Puede establecer el valor en días (1-90), horas (hasta 23) o incluso durante toda la vida.

**Parámetro de enlace de atribución:** af\_reengagement\_window

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras aperturas) que se produzcan dentro de la ventana de lookback se pueden atribuir a Taptica.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Taptica para que se active cuando los clientes potenciales hagan clic en un anuncio correspondiente.

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras aperturas) que se produzcan dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a Taptica, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro de enlace de atribución:** af\_viewthrough\_lookback

Más información sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución view-through aquí</Anchor>.

### Enlace de atribución de impresiones

El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Envíalo a Taptica para que se active cuando se vea un anuncio correspondiente, normalmente durante 1 segundo o más.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos del ad network</Anchor> para obtener todos los detalles sobre las dimensiones, métricas y funciones admitidas. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer datos de costos coincidentes en el Dashboard del estado de la integración de costos (e ingresos por anuncios) o en el Dashboard del ad network individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a Taptica, tanto si el partner actúa como ad network, agencia o incluso ambas cosas. Ten en cuenta que, aunque la atribución esté deshabilitada para Taptica, la pestaña Permisos está activa y puedes conceder el control a Taptica.

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

### Permisos de la agencia

Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* ***Interruptor principal*** - Actívalo para mostrar las opciones de permisos de la agencia
* ***Permitir el acceso a tu reporte de retención*** - solo a los datos de retención de la propia agencia
* ***Permitir el acceso a datos agregados orgánicos.***
* ***Permitir configurar postbacks de eventos in-app*** - permite que la agencia configure la asignación de postbacks de eventos in-app a sí misma en la pestaña de integración

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos a las agencias</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-taptica=configuraci%C3%B3n-de-taptica h_01HJS1NM4SSXEM83HWQPMV9JAF=configuraci%C3%B3n-de-taptica h_01HJS1NM4SNMBHCFKNFQJRJ76B=consejo h_01HJS1NM4T0TJ91WZ3PTSYS4QQ=integration-tab activate-partner=activar-socio h_01HJS1NM4TBMQFKSD8MR28XDRZ=activar-socio general-settings=configuraci%C3%B3n-general h_01HJS1NM4TY71SZX6HF2FEWDJM=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HJS1NM4T5KWZJBPW9NZX9B4E=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HJS1NM4TJC317ZJA7ZP5FG93=configuraci%C3%B3n-de-eventos-in-app h_01HJS1NM4TAXE0PSFQFZ8WY335=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HJS1NM4TY8VCKQAHAGYKC4S2=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n retargeting-settings=configuraciones-de-retargeting h_01HJS1NM4TFKAC93D0SMZD3AYJ=configuraciones-de-retargeting clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HJS1NM4T5NMQ360S8YTGMSF6=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HJS1NM4T3J870BWR9GXMR4E1=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HJS1NM4V649HCT6JY4HE6J0J=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HJS1NM4VGNJ66P6ARHJA5Z1X=enlace-de-atribuci%C3%B3n-de-impresiones h_01HJS1NM4VHFKRTYAEZ3X4FKF7=cost-tab h_01HJS1NM4VG74QAEFKJPZ3PCP7=ad-revenue-tab h_01HJS1NM4V01E1KECDG0WX3D59=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HJS1NM4VKSJT38G04FFN400F=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HJS1NM4VMP8CG58Z134BB6CW=permisos-de-la-agencia" />
