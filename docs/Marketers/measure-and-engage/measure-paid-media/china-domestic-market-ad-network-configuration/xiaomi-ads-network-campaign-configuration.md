---
title: Configuración de la campaña de la red de anuncios de Xiaomi
metadata:
  keywords:
    - XiaoMi
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
  created_at: '2017-03-28T11:08:46Z'
  edited_at: '2026-09-17T00:26:36Z'
  id: 115001605286
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/115001605286
---
> **Resumen:** Xiaomi, partner integrado de ad network de AppsFlyer, opera la tienda de aplicaciones Android de Xiaomi, que se encuentra entre las 5 principales plataformas de distribución de aplicaciones Android en China, con 5 billion descargas de aplicaciones al mes. Además de la atribución móvil basada en clics, Xiaomi también ofrece atribución por impresiones, que puedes registrar con AppsFlyer.

<div id="setting-up-xiaomi" />

## Configuración de Xiaomi

**Requisito previo:** una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace** .  
   (**Para editar una integración existente:** ve a la pestaña **Collaborate > Partner Integrations > Active integrations** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota importante:** el selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La ventana de configuración de Xiaomi incluye 3 pestañas activas: Integración, Enlace de atribución y Permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="activate-partner" />

### Activar socio

En la **primera visita**, tendrás que activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

Configuración general

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir instalaciones view-through de Xiaomi. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<Image align="center" alt="" src="https://files.readme.io/c01732abe8d1bb3c68acdf84bab50cc46d4f4923b7220e3ca51c399074113c1e-50899866307217.png" />

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a Xiaomi después de las instalaciones y re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

<Image align="center" alt="xiaomi-default-postbacks.png" src="https://files.readme.io/ae215140550604649e4345729a7106fa08c15713e003cec534199e3889122b5e-50899866309265.png" />

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes usar un enlace de plataforma única o un <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

La integración de datos de costo no tiene soporte actualmente con Xiaomi.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La integración de ingresos publicitarios no es compatible actualmente con Xiaomi.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a Xiaomi, tanto si el partner actúa como ad network, agencia o incluso ambos. Ten en cuenta que, incluso si la atribución estuviera deshabilitada para Xiaomi, la pestaña de permisos se encontraría activa y podrías otorgarle el control a Xiaomi.

<Image align="center" alt="ad_network_permissions.png" src="https://files.readme.io/8d8c3d5eb38384d92e52afdc01b0631d8fe5c9590dd618386cbf6ce90fc978f3-50612307452817.png" />

Utiliza estos selectores para otorgarle permisos a la red de publicidad para que gestione su propia configuración para tu aplicación:

<div id="ad-network-permissions" />

### Permisos de ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app)
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-xiaomi=configuraci%C3%B3n-de-xiaomi h_01HKW6ZDW8D6CD60S25FVQ80FC=configuraci%C3%B3n-de-xiaomi h_01HKW6ZDW8JK323YYPCSYZ1PKB=integration-tab activate-partner=activar-socio h_01HKW6ZDW8B60R3QAZRMPHVC31=activar-socio default-postbacks=postbacks-predeterminados h_01HKW6ZDW8GW51XT1XXPE7DZ02=postbacks-predeterminados h_01HKW6ZDW8ERH0MQ2W2YGC5SXB=attribution-link-tab h_01HKW6ZDW8SHGTTVC4V7R1R90K=cost-tab h_01HKW6ZDW8ENFJN342XN66TM19=ad-revenue-tab h_01HKW6ZDW89CE47NF67TJM4AX9=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKW6ZDW8Y85VBJPQ40MZ5CV5=permisos-de-ad-network" />
