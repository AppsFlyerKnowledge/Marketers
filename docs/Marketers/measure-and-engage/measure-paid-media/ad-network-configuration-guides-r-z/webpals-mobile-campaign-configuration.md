---
title: Configuración de campañas de Webpals Móvil
metadata:
  keywords:
    - ClicksMob
    - Advertisers
    - Webpals mobile
    - Webpals
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-06-27T13:49:23Z'
  edited_at: '2026-09-11T00:25:26Z'
  id: 211395903
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/211395903
---
> **Resumen:** Webpals Móvil, un partner integrado de ad network de AppsFlyer con cobertura global, es líder en adquisición de usuarios móviles y maximización de ingresos.

Para configurar tus campañas con Webpals Mobile, sigue los pasos que se indican a continuación.

<div id="setting-up-webpals-mobile" />

## Configuración de Webpals Móvil

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de partners > Marketplace** .  
   (**Para editar una integración existente:** ve a la pestaña **Colaborar > Integraciones de partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas pertinentes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

La configuración de Webpals Mobile incluye 3 pestañas activas: **Integración**, **Enlace de atribución**, y **Permisos**. Haz clic en las pestañas de abajo para leer sobre la configuración de las pestañas.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, deberás activar el selector **Activar partner** para habilitar la configuración de los parámetros de la pestaña Integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a Webpals Móvil tras las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para los eventos que provienen solo de usuarios atribuidos a Webpals Mobile.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a Webpals Móvil mediante postbacks.

1. Activa los postbacks de eventos in-app
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de Parámetro | Description |
| --- | --- |
| **Nombre del evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a comprobarlo. |
| **Identificador de Evento de Partner** | El nombre único o ID de cada evento, tal como se define en Webpals Móvil.  <br />Obtén el ID de evento correspondiente de Webpals Móvil e introdúcelo en el campo de texto. |
| **Enviar Ingresos** | **Si no está marcada**: envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Webpals Mobile para atribuir campañas, conjuntos de anuncios o incluso anuncios individuales de Webpals Mobile. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Los parámetros que ya están definidos en el enlace de atribución pueden editarse agregándolos junto con sus valores nuevos en esta sección.

* **Campaña** - añádela para comparar diferentes campañas en ejecución con Webpals Mobile.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Webpals Mobile.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de conjuntos de anuncios para comparar diferentes creativos dentro de conjuntos de anuncios específicos, dentro de campañas específicas de Webpals Móvil.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro de ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar la cantidad de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones de ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Obtén más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Webpals Mobile.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Webpals Mobile para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

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

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a Webpals Mobile, ya sea que el partner actúe como ad network, agencia o ambas. Ten en cuenta que, aunque la atribución esté desactivada para Webpals Mobile, la pestaña de permisos está activa y puedes otorgarle el control a Webpals Mobile.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

<div id="ad-network-permissions" />

### Permisos de ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles*** - solo a los datos de usuarios fieles propios del partner
* ***Permitir acceso a tus datos agregados de eventos in-app** -* solo a los datos de eventos in-app propios del partner
* ***Permitir acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

<div id="agency-permissions" />

### Permisos de la agencia

Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* ***Selector principal*** - actívalo para mostrar las opciones de permisos para agencias
* ***Permitir configurar postbacks de eventos in-app*** - permite que la agencia configure en la pestaña de integración la asignación a sí misma de postbacks de eventos in-app
* ***Permitir el acceso a tu reporte de retención*** - solo a los datos de retención de la propia agencia

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos a las agencias</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-webpals-mobile=configuraci%C3%B3n-de-webpals-m%C3%B3vil h_01HJZW1R6FFQZ5WETP6FCMW7VN=configuraci%C3%B3n-de-webpals-m%C3%B3vil h_01HJZW1R6F51BEYH46VPZ23X1B=integration-tab activate-partner=activar-socio h_01HJZW1R6GKV9ZD222NSWDXVNE=activar-socio default-postbacks=postbacks-predeterminados h_01HJZW1R6G1S7M82QVKQPKKDSE=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HJZW1R6GWT322E28533S7F8N=configuraci%C3%B3n-de-eventos-in-app h_01HJZW1R6G3Z21RK8ANKRP5BRY=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HJZW1R6GVEGEWJHWAW8N368X=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HJZW1R6G6F4Z010A7FYG6HF9=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HJZW1R6GC6G4T3NV3FZYZ0RN=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HJZW1R6GHK1TKD0BC72QFB0S=cost-tab h_01HJZW1R6GHP4S7BFTZZS6NDPA=ad-revenue-tab h_01HJZW1R6GV3AB25V5SA0Y3YR2=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HJZW1R6G1486DSCDP92P4MGJ=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HJZW1R6HXXRVWM3773VSM8WC=permisos-de-la-agencia" />
