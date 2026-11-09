---
title: Configuración de la campaña de Mobio
metadata:
  keywords:
    - mobio
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
  created_at: '2016-06-20T13:07:24Z'
  edited_at: '2026-08-12T12:14:33Z'
  id: 209587526
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/209587526
---
> **De un vistazo:** Mobio, uno de los partners integrados de AppsFlyer, es una plataforma de marketing de aplicaciones móviles con la cartera de estudios de casos de éxito n.º 1 de Rusia. Además de la atribución móvil basada en clics, Mobio también ofrece atribución de costos, ingresos por publicidad, retargeting y atribución view-through, que puedes registrar con AppsFlyer.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobio.png?v=1" />

<div id="setting-up-mobio" />

## Configuración de Mobio

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con el partner.  
    Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación. Para ver una descripción detallada del Encabezado de la ventana de configuración de partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

La ventana de configuración de Mobio incluye 3 pestañas activas: Integración, Enlace de atribución y Permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

Para ver una descripción detallada del Encabezado de la Ventana de Configuración de Partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="tip" />

> 👍 **Consejo**
>
> * El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">Configuración general</Anchor> en la pestaña de Integración es **obligatorio para todos los partners**.
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación. Configuración general

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a Mobio después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para los eventos procedentes solo de usuarios atribuidos a Mobio.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a Mobio mediante postbacks.

1. Activa los postbacks de eventos in-app.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK integrado con tu aplicación o desde eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre único o ID de cada evento según lo define Mobio.  <br />Obtén el ID de evento correspondiente de Mobio e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Cuando está marcada**: se envían todos los parámetros incluyendo el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Mobio para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Mobio. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: añádela para comparar distintas campañas en funcionamiento con Mobio.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjunto de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Mobio.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio**: define nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos de campañas específicas de Mobio.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio**: configura el parámetro de ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de datos sin procesar, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Mobio.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Mobio para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

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

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a Mobio, tanto si el partner actúa como ad network, agencia o incluso ambas cosas. Ten en cuenta que, incluso si la atribución estuviera deshabilitada para Mobio, la pestaña de permisos está activa y puedes otorgarle el control a Mobio.

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

<div id="agency-permissions" />

### Permisos de la agencia

Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* ***Selector principal*** - configúralo en On para mostrar las opciones de permisos para agencias
* ***Permitir el acceso a tu reporte de retención*** - solo a los datos de retención propios de la agencia
* ***Permitir el acceso a datos agregados orgánicos.***
* ***Permitir la configuración de postbacks de eventos in-app*** - permite que la agencia configure la asignación de postbacks de eventos in-app a sí misma en la pestaña de integración

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos a las agencias</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-mobio=configuraci%C3%B3n-de-mobio h_01HKW34PW1Y7S78Z05CNZPGV7J=configuraci%C3%B3n-de-mobio h_01HKW34PW12V6JMYTFG61324AG=consejo h_01HKW34PW18K29N92EAC2Q3D9E=integration-tab activate-partner=activar-socio h_01HKW34PW1HDFQ8YEF9XR8HFG9=activar-socio default-postbacks=postbacks-predeterminados h_01HKW34PW1SJPB24MBD9BXBDJ9=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW34PW178WVKP0M3032R2H9=configuraci%C3%B3n-de-eventos-in-app h_01HKW34PW20BNZYP8KAZA6B0CG=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW34PW212DPA337Y60HB979=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKW34PW2ZV9BGDD5Q9E48ABA=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW34PW2ASJ1Q12SKDYH1EPV=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW34PW2MVBPEE4KXCCZ1V1J=cost-tab h_01HKW34PW2M447QXS82266Y497=ad-revenue-tab h_01HKW34PW28TK2Z5Y8817E16D1=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKW34PW2A8FKTCR03WXDTPZ2=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HKW34PW2HPQJ5047R02AWX97=permisos-de-la-agencia" />
