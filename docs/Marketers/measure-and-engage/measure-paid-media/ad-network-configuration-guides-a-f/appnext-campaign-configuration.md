---
title: Configuración de la campaña de Appnext
metadata:
  keywords:
    - Advertisers
    - appnext
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-08-20T07:46:36Z'
  edited_at: '2026-09-11T00:22:59Z'
  id: 360001407109
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/360001407109
---
> **Resumen:** Appnext, un partner integrado de ad network de AppsFlyer, utiliza soluciones tecnológicas y de datos para la monetización móvil premium, el marketing de aplicaciones y el re-engagement. Además de la atribución móvil basada en clics, Appnext también ofrece atribución de costos, retargeting y view-through, que puedes registrar con AppsFlyer.

<div id="setting-up-appnext" />

## Configuración de Appnext

**Requisito previo:** una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, deberás activar el selector. ACTIVA el botón **Activar partner** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="general-settings" />

### Configuración general

**Habilitar la atribución por impresiones**

Activa esto si quieres atribuir las instalaciones view-through de Appnext. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

![appnext_msc_new_2.png](https://files.readme.io/f974ed2ccc5550cebb87e5070d177fb88efb0c82fe15cbc300979d54b1297a6a-50705658863249.png)

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a Appnext tras las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Nota: para las instalaciones, puedes seleccionar either **Solo eventos atribuidos a este partner** (para eventos que provienen solo de usuarios atribuidos a Appnext), o **Eventos atribuidos a cualquier partner u orgánicos** (para eventos que provienen de todos los partners). Para las instalaciones rechazadas y los re-engagements, **Solo eventos atribuidos a este partner** se pueden enviar mediante un postback.

<div id="note" />

> 📘 **Nota:**
>
> Como red de TODAS las instalaciones, Appnext prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluida la orgánica. Se recomienda seleccionar **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a Appnext.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a Appnext mediante postbacks.

1. Activa los Postbacks de eventos in-app con el selector.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define Appnext.  <br />Obtén el ID de evento correspondiente de Appnext e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes usar un enlace de una sola plataforma o un <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más sobre la estructura y los parámetros del enlace de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Appnext envía automáticamente datos de costos de CPI en el enlace de atribución para todas las instalaciones.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La integración de ingresos por publicidad no está disponible para este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos para otorgar a Appnext. Ten en cuenta que, incluso si la atribución está deshabilitada para Appnext, la pestaña de permisos está activa y puedes otorgar el control a Appnext.

<div id="ad-network-permissions" />

### Permisos de ad network

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

* **Permitir la configuración de la integración**: permite que el partner configure la pestaña integración (con excepción de postbacks de eventos in-app).
* **Permitir la configuración de postbacks de eventos in-app**: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña integración.
* **Permitir el acceso a tu reporte de retención**: solo para los datos propios de retención del partner.
* **Permitir acceso a tus datos agregados de usuarios legales**: solo para los datos propios de usuarios leales del partner.
* **Permitir acceso a tus datos agregados de eventos in-app** - solo a los datos de eventos in-app propios del partner
* **Permitir acceso a tus datos agregados de ingresos**: solo para los datos de ingresos atribuidos al partner.
* **Permitir el acceso a tu dashboard de Protect360**: solo para los datos propios de Protect360 del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

<div id="agency-permissions" />

### Permisos de la agencia

Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* **Interruptor principal** - Configúralo en ON para mostrar las opciones de permisos de agencia
* **Permitir el acceso a tu reporte de retención**: solo para los propios datos de retención de la agencia.
* **Permitir el acceso a datos agregados orgánicos.**
* **Permitir la configuración de postbacks de eventos in-app**: permite que la agencia configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña Integración.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos a las agencias</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-appnext=configuraci%C3%B3n-de-appnext h_01HKW999WPN45PNK2XN3RD9NTX=configuraci%C3%B3n-de-appnext h_01HKW999WPT67XT04P3GG7PTBS=integration-tab activate-partner=activar-socio h_01HKW999WPB6KKPN9MZ8N1GM70=activar-socio general-settings=configuraci%C3%B3n-general h_01HKW999WQK8P62W20K1AWHBEN=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKW999WQS7FM0TE95G7R56M8=postbacks-predeterminados h_01HKW999WQP04CC7YPTEJ4E6AJ=nota inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW999WQFR3DMNGEJFS6ZS7N=configuraci%C3%B3n-de-eventos-in-app h_01HKW999WQWFDDS13K2V3F2G3A=attribution-link-tab h_01HKW999WQKB9VNRSVV6JM15ES=cost-tab h_01HKW999WQ1C5CDN4JDYE1XMRZ=ad-revenue-tab h_01HKW999WQ9K1376YHF92GYW45=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKW999WQG5KB588ESQ5XS4HM=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HKW999WQZMAX4MSM3B49H63W=permisos-de-la-agencia" />
