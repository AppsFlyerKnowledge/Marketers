---
title: Configuración de campañas de Cheetah Mobile
metadata:
  keywords:
    - cheetah mobile
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
  created_at: '2016-03-28T10:23:35Z'
  edited_at: '2026-09-11T00:23:19Z'
  id: 209731703
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/209731703
---
> **De un vistazo:** Cheetah Mobile, un partner integrado de ad network de AppsFlyer, tiene como objetivo ofrecer apps líderes a usuarios de móvil de todo el mundo y conectar a los usuarios con contenido personalizado en la plataforma móvil. Además de la atribución móvil basada en clics, Cheetah Mobile también ofrece atribución de costos y view-through, que puedes registrar con AppsFlyer.

## Configuración de Cheetah Mobile

**Requisito previo:** una cuenta con el Partners. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar Partners**.   
   **Nota:** el selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

### Activar los partners

En la **primera visita** aquí, debes activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

> 📘 **Nota:**
>
> Como red de TODAS las instalaciones, Cheetah Mobile prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluidas las orgánicas. Se recomienda seleccionar **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a Cheetah Mobile.

### Configuración general

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir las instalaciones view-through de Cheetah Mobile. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

### Postbacks predeterminados

Envía postbacks automáticos a Cheetah Mobile después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos procedentes solo de usuarios atribuidos a Cheetah Mobile.  
Selecciona **Eventos atribuidos a cualquier partner u orgánicos** para que toda tu base de usuarios esté disponible para ser reportada a Cheetah Mobile.

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a Cheetah Mobile mediante postbacks.

1. Activa los Postbacks de eventos in-app con el selector.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento, tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define Cheetah Mobile.  <br />Obtén el ID de evento correspondiente de Cheetah Mobile y configúralo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieres enviar a Cheetah Mobile para atribuir campañas, conjuntos de anuncios o anuncios individuales de Cheetah Mobile. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña** - añádela para comparar distintas campañas en ejecución con Cheetah Mobile.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar distintos conjuntos de anuncios dentro de campañas específicas de Cheetah Mobile.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos de campañas específicas de Cheetah Mobile.  
  **Parámetro del enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro de ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre la <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Cheetah Mobile.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Cheetah Mobile para que se active cuando los leads hagan clic en un anuncio correspondiente.

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras ejecuciones) que tienen lugar dentro de esta ventana de lookback, después de una impresión de anuncio, se atribuyen a Cheetah Mobile, siempre que no haya habido otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro del enlace de atribución:** af\_viewthrough\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución por impresiones aquí</Anchor>.

### Enlace de atribución de impresiones

El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Envíalo a Cheetah Mobile para que se active cuando se vea un anuncio correspondiente, normalmente durante 1 segundo o más.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Cheetah Mobile envía automáticamente datos cifrados de costo de CPI en el enlace de atribución para todas las instalaciones.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Este partner no admite ingresos por publicidad.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a Cheetah Mobile, tanto si el partner actúa como ad network, agencia o ambos. Ten en cuenta que, aunque la atribución esté desactivada para Cheetah Mobile, la pestaña de permisos está activa y puedes conceder el control a Cheetah Mobile.

### Permisos de ad network

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

* ***Permitir configurar la integración*** - permite que el partner configure la pestaña de integración (excepto los postbacks de eventos in-app)
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

### Permisos de la agencia

Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* ***Selector principal*** - actívalo para mostrar las opciones de permisos de la agencia
* ***Permitir configurar postbacks de eventos in-app*** - permite que la agencia configure en la pestaña de integración la asignación de postbacks de eventos in-app a sí misma
* ***Permitir el acceso a datos agregados orgánicos.***
* ***Permitir el acceso a tu reporte de retención*** - solo a los datos de retención de la propia agencia

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos a las agencias</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-cheetah-mobile=configuraci%C3%B3n-de-cheetah-mobile h_01HKWB1JWHPMM479MHE32NEN3Q=configuraci%C3%B3n-de-cheetah-mobile h_01HKWB1JWHSGXPW48YRC2XRBK4=integration-tab activate-partners=activar-los-partners h_01HKWB1JWHQH9FT3TW5CP8G45T=activar-los-partners h_01HKWB1JWHXRJGWJD2J8RAYFZM=nota general-settings=configuraci%C3%B3n-general h_01HKWB1JWHHH6F8H8MA8DYD486=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKWB1JWHMAKZDHQG3MNCFFND=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKWB1JWHSW1S1DSTJEBD4ZW0=configuraci%C3%B3n-de-eventos-in-app h_01HKWB1JWHAGA1EVKGX1EHWSW5=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKWB1JWH7DFXA38WJ0Y2RCV5=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKWB1JWJS6QM7VPSGAY6Y296=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKWB1JWJTM5SH99NH5X8GVRX=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HKWB1JWJANK35Q2RJQ07Y19T=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKWB1JWJN47XHK6WY252SR28=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKWB1JWJG9KX8W7GS5HV0ZVY=cost-tab h_01HKWB1JWJJ4G8TK7F15T7CB4Z=ad-revenue-tab h_01HKWB1JWJS5RF65RD0KMA19GF=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKWB1JWJF19NSD07RBKEZTYX=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HKWB1JWJQ61908VTXKXABGEK=permisos-de-la-agencia" />
