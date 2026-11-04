---
title: Configuración de la campaña de MOLOCO
metadata:
  keywords:
    - Advertisers
    - Moloco
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-12-16T07:37:12Z'
  edited_at: '2026-08-12T12:14:42Z'
  id: 360000691978
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/360000691978
---
> **De un vistazo:** MOLOCO, un partner integrado de AppsFlyer, convierte los datos de Usuario en rendimiento de Anuncio, lo que permite a las empresas móviles ejecutar programas de marketing y monetización publicitaria.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/moloco.png?v=1" width="149px" />

<div id="setting-up-moloco" />

## Configuración de MOLOCO

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con el partner.  
    Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación. Para ver una descripción detallada del Encabezado de la ventana de configuración de partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

La ventana de configuración de MOLOCO incluye 3 pestañas activas: Integración, Enlace de atribución y Permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

Para ver una descripción detallada del Encabezado de la Ventana de Configuración de Partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="tip" />

> 👍 **Consejo**
>
> * El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">Configuración general</Anchor> en la pestaña de Integración es **obligatorio para todos los partners**.
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, debes activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de Partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="note" />

> 📘 **Nota:**
>
> Como red de todas las instalaciones, MOLOCO prefiere recibir postbacks de todas las nuevas instalaciones de tu Aplicación desde cualquier fuente, incluidas las orgánicas. Para hacerlo, selecciona **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a MOLOCO.

<div id="general-settings" />

### Configuración general

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir las instalaciones view-through de MOLOCO. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a MOLOCO después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos provenientes solo de usuarios atribuidos a MOLOCO.  
Selecciona **Eventos atribuidos a cualquier partner u orgánico** para tener toda tu base de usuarios disponible para reportarla a MOLOCO.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a MOLOCO mediante postbacks.

1. Activa los Postbacks de eventos in-app con el selector.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner  
   **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos servidor a servidor.<br />**Consejo**: ¿No encuentras el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer**, luego haz clic en **Crear personalizado**. Leer más sobre <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">la asignación de eventos personalizados.</Anchor></li></ul> |
| **Asignado al evento de partner** | El ID o nombre único de cada evento, tal y como lo defina el partner. Existen varias configuraciones de asignación:<ul><li>**Campo de texto:** obtén el ID del evento correspondiente del partner.</li><li>**Cuadro desplegable:** selecciona el evento de AppsFlyer predefinido más adecuado.</li><li>**Como está**: Envía los eventos tal como están, sin asignación de nombres.</li></ul> |
| **para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner**: envía postbacks solo cuando este evento se atribuye a este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks para eventos atribuidos a cualquier partner, así como para eventos orgánicos. Según Unity Ads, se recomienda esta opción.</li></ul> |
| **Incluye** | <ul><li>**Sin datos (predeterminado)**: envía solo el evento en sí sin el valor del evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento). Según Unity Ads, se recomienda esta opción.</li><li>**Valores sin ingresos**: envía todos los parámetros **excluyendo** el valor de ingresos.</li></ul> |

<div id="note-1" />

> 📘 **Nota:**
>
> Puedes enviar <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">postbacks de ingresos publicitarios</Anchor> a MOLOCO usando el evento`af_ad_revenue` para que puedan optimizar campañas.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o un <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de redes de publicidad</Anchor> para obtener detalles completos sobre las dimensiones, métricas y funciones admitidas. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

Los datos de ayer están disponibles en MOLOCO aproximadamente a las 4:00 a. m. (según la configuración de la zona horaria de tu cuenta de MOLOCO). Por ejemplo, si el evento se produjo el lunes, AppsFlyer puede extraer los datos de costo el martes aproximadamente a las 4:00 a. m. Después de extraer los datos de Costo de MOLOCO, AppsFlyer los analiza y prepara y, una vez completado este proceso, los datos pueden consumirse.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el panel de control de estado de la integración de costos (e ingresos por publicidad) o en el panel de control de la red de publicidad individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La integración de ingresos por publicidad no está disponible para este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a MOLOCO, tanto si el partner actúa como ad network, agencia o ambas. Ten en cuenta que, aunque la Atribución esté deshabilitada para MOLOCO, la pestaña Permisos está activa y puedes otorgar el Control a MOLOCO.

<div id="-ad-network-permissions" />

#### ![MOLOCO_permissions.png](https://files.readme.io/f443306f1b56197709308c0a33e436dc26adc7a0e80e6c2887edc63a5697b6d4-360002616197.png) Permisos para Redes de Publicidad

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

* **Permitir la configuración de la integración**: permite que el partner configure la pestaña integración (con excepción de postbacks de eventos in-app).
* **Permitir configurar postbacks de eventos in-app** - permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña Integración
* **Permitir el acceso a tu reporte de retención** - solo a los datos de retención propios del partner
* **Permitir el acceso a tu dashboard de Protect360** - solo para los datos propios de Protect360 del partner, siempre que la función esté habilitada para el anunciante

Saber más sobre cómo conceder <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos de ad network</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-moloco=configuraci%C3%B3n-de-moloco h_01HBB9EEMJRHWC21713D60725N=configuraci%C3%B3n-de-moloco h_01HBB9EEMJQ9VAMJMYG2T5FX0S=consejo h_01HBB9EEMJ7X92Y5TK4YXXGSZX=integration-tab activate-partner=activar-socio h_01HBB9EEMJ0EW14NZE9WCKJR1M=activar-socio h_01HBB9EEMJ55BQDJ1ZEJT136ZF=nota general-settings=configuraci%C3%B3n-general h_01HBB9EEMJ2XSWFQZZFJ7J54VY=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HBB9EEMJV2SS4VJW0HW8D12R=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HBB9EEMJE2X04XZGMSJSSXAT=configuraci%C3%B3n-de-eventos-in-app h_01HBB9EEMJ6WA79D7R4BG8S9HS=nota-1 h_01HBB9EEMJXGFHY28K2DDHKBF8=attribution-link-tab h_01HBB9EEMJT7VSNFQJC86TS1YX=cost-tab h_01HBB9EEMJ61WDHNPKMW5A1YKM=ad-revenue-tab h_01HBB9EEMJ3Z40S2A6FZG7RJ6K=permissions-tab ad-network-permissions=-permisos-para-redes-de-publicidad h_01HBB9EEMJ54Y8KJBK4395ENPJ=-permisos-para-redes-de-publicidad" />
