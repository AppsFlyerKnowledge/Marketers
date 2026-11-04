---
title: Configuración de la campaña de Criteo
metadata:
  keywords:
    - Criteo
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
  created_at: '2018-03-27T06:56:54Z'
  edited_at: '2026-09-11T00:23:24Z'
  id: 360000601785
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/360000601785
---
> **De un vistazo:** Criteo, un partner integrado de ad network de AppsFlyer, impulsa el crecimiento mediante tecnología de aprendizaje automático, datos y rendimiento a escala, y un ROI medible para sus clientes. Además de la atribución móvil basada en clics, Criteo también ofrece atribución de retargeting, que puedes registrar con AppsFlyer.

<div id="setting-up-criteo" />

## Configuración de Criteo

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace** .  
   (**Para editar una integración existente:** ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="activate-partner" />

### Activación de socios

En la **primera visita**, debes activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="note" />

> 📘 **Nota**
>
> Como red de TODAS las instalaciones, Criteo prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluida la orgánica. Se recomienda seleccionar **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a Criteo.

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a Criteo después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos provenientes solo de usuarios atribuidos a Criteo.  
Selecciona **Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada a Criteo.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a Criteo mediante postbacks.

1. Activa los Postbacks de eventos in-app con el selector.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
   **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre único o ID de cada evento según lo define Criteo.  <br />Obtén el ID de evento correspondiente de Criteo e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

<div id="warning" />

> ❗️ **Advertencia**
>
> <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#what-are-complex-inapp-events-and-how-do-i-set-them-up">Los eventos in-app complejos</Anchor> causan problemas de postback con Criteo. Si necesitas que el evento esté totalmente asignado a Criteo, envía eventos separados por cada acción del usuario (por ejemplo, envía un evento de «Agregar al carrito» por cada artículo añadido). Puedes agrupar estos eventos utilizando el raw data de los eventos in-app.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o un <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de redes de publicidad</Anchor> para obtener detalles completos sobre las dimensiones, métricas y funciones admitidas. 

**Nota**:

* Los datos de costos requieren una suscripción a ROI360.
* Los datos de costo de Criteo solo se pueden recibir para descargas procedentes de Google Play o la tienda de aplicaciones de Apple. Para Android, los datos de costo para tiendas de aplicaciones Android de terceros no son compatibles.
* El costo de la agencia solo está disponible a través de <Anchor target="_blank" href="/marketers/es/docs/view-aggregated-cost-data-for-attribution-links">clic</Anchor>; no mediante la integración de API.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el panel de control de estado de la integración de costos (e ingresos por publicidad) o en el panel de control de la red de publicidad individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La integración de los ingresos por publicidad no está disponible para Criteo.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a Criteo, tanto si el partner actúa como ad network, agencia o incluso ambos. Ten en cuenta que, incluso si la atribución está deshabilitada para Criteo, la pestaña Permisos está activa y puedes otorgarle el control a Criteo.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

Permisos para Redes de Publicidad

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos***: solo a los datos de ingresos atribuidos al partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-criteo=configuraci%C3%B3n-de-criteo h_01HKWB41KJ4XG0SGX69NHGYBYD=configuraci%C3%B3n-de-criteo h_01HKWB41KJR5H4TDH80AG7JEYQ=integration-tab activate-partner=activaci%C3%B3n-de-socios h_01HKWB41KJ2Z3RHNQ2XYJXJBKC=activaci%C3%B3n-de-socios h_01HKWB41KJRHZCFJ0CF7K3SMAS=nota default-postbacks=postbacks-predeterminados h_01HKWB41KJHZM1P6ZKJ1Q10C7D=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKWB41KJSDADQZYVAD13QYEH=configuraci%C3%B3n-de-eventos-in-app h_01HDBZW9XF33FHR418MNVH6BS2=advertencia h_01HKWB41KKPPSGDVB1EKDXD6A5=attribution-link-tab h_01HKWB41KKW3EEF3VVMS9BSZ53=cost-tab h_01HKWB41KKFT61V0TWGM5P5X8H=ad-revenue-tab h_01HKWB41KKPFBWKE748V5FD5Y3=permissions-tab" />
