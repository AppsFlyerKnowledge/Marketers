---
title: Configuración de la campaña de Vungle
metadata:
  keywords:
    - Vungle
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
  created_at: '2016-03-03T08:53:29Z'
  edited_at: '2026-09-09T00:25:42Z'
  id: 207990186
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/207990186
---
> **De un vistazo:** Vungle, un partner integrado de ad network de AppsFlyer, ofrece una plataforma de publicidad en vídeo in-app para profesionales del marketing de rendimiento. Además de la atribución móvil basada en clics, Vungle ofrece atribución de costo y view-through, que se puede registrar en AppsFlyer.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/vungle.png?v=1" width="91px" />

<div id="setting-up-vungle" />

## Configuración de Vungle

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace** .  
    (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el conmutador **Activate partner**.   
    **Nota:** El interruptor **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas pertinentes, como se describe a continuación. Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="tip" />

> 👍 **Consejo**
>
> * El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">Configuración general</Anchor> en la pestaña de Integración es **obligatorio** para todos los partners.
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partners" />

### Activar los partners

Conéctate a Vungle activando y configurando los parámetros en la pestaña de integración. Vungle debe proporcionar su ID de red único, ***app\_id***; esto es necesario para conectarse con AppsFlyer.

<div id="note" />

> 📘 **Nota:**
>
> Como red de todas las instalaciones, Vungle prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde cualquier fuente, y recomienda seleccionar **Todas las fuentes de medios, incluidas las orgánicas** para enviar todos los postbacks de instalación a Vungle.

**Para configurar la integración**:

1. Activa ***Activar partner***. Consulta más información sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
2. **En *Ajustes generales*, activa o desactiva *la atribución view-through*:**
   * [Predeterminado] **Habilitar**: Actívalo para atribuir instalaciones view-through a Vungle. La duración de la ventana de lookback se configura en la pestaña Enlace de atribución.
   * **Desactivar**: no se atribuyen las instalaciones view-through del partner.
3. ***Postbacks predeterminados***: envía postbacks a Vungle después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir a los usuarios que son la fuente de estos postbacks. En ***Opción de envío***,

   * Selecciona **Solo eventos atribuidos a este partner** para los eventos atribuidos a usuarios de Vungle.
   * Selecciona **Eventos atribuidos a cualquier partner u orgánico** para que toda tu base de usuarios esté disponible para el reporte a Vungle.
4. ***Configuración de eventos in-app***: Para enviar postbacks a Vungle, asigna los ID de eventos in-app a los de Vungle. Configura los parámetros de la siguiente manera:
   * Introduce el app\_id de Vungle.
   * Habilita ***los postbacks de eventos in-app***.
   * Selecciona una ***opción de envío***.
   * Haz clic en ***Agregar evento*** para añadir un evento del SDK a la lista. Completa los parámetros como se describe en la siguiente tabla.

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento SDK** | Nombre del evento recibido por AppsFlyer de:<ul><li>SDK integrado en la aplicación</li><li>Eventos server-to-server (servidor a servidor)</li></ul>**Consejo:** Si el evento que necesitas no está en la lista, realiza una instalación no orgánica en un dispositivo y vuelve a comprobarlo. |
| **Identificador de evento de partner** | Nombre o ID único del evento según lo definido por Vungle.<br /><br />Obtén de Vungle el ID del evento correspondiente a tu evento del SDK e introdúcelo en el campo de texto. |
| **Enviar ingresos** | [Predeterminado] **No habilitado:** envía todos los parámetros in-app a Vungle, excepto el parámetro de ingresos (`af_revenue`).<br /><br />**Habilitado**: envía todos los parámetros in-app, incluido, cuando está disponible, el importe de los ingresos. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.  

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de ad networks</Anchor> para obtener todos los detalles sobre las dimensiones, métricas y funciones compatibles. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer datos de costos coincidentes, ya sea en el dashboard de estado de la integración de costos (y de ingresos por publicidad) o en el dashboard de la ad network individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Esta sección es pertinente si actúas como publisher y muestras anuncios del partner a tus usuarios. Como tal, con seguridad te gustaría medir el nivel de engagement de tus usuarios adquiridos a partir de distintas fuentes, a fin de identificar las fuentes que te resultan más rentables.

**Para habilitar la API de ingresos por publicidad**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">estas instrucciones de integración</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Puedes darle a Vungle permiso para ver información o configurar cambios en la integración. El tipo de permiso varía según la relación comercial (ad network/agencia de publicidad) que tengas con Vungle.

**Nota**: Es posible darle permisos a Vungle aunque no haya una integración activa con ellos.

<div id="ad-network-permissions" />

### Permisos de ad network

**Para habilitar los permisos de ad network:**

1. Habilita ***Permisos de ad network***.
2. Da a los miembros del equipo de Vungle acceso a uno o varios de los siguientes elementos:

| **Permitir configurar la integración** | Configurar la pestaña Integración (excepto los postbacks de eventos in-app). |
| --- | --- |
| Permitir la configuración de postbacks de eventos in-app | Configurar los postbacks de eventos in-app asignados a la pestaña Integración. |
| Permitir el acceso a tus reportes de retención | Datos de retención del partner |
| Permitir el acceso a tus datos agregados de los usuarios leales | Datos de usuarios fieles del partner |
| Permitir el acceso a tus datos agregados de eventos in-app | Datos de eventos in-app del partner |
| Permitir el acceso a tus datos agregados de ingresos | Datos de ingresos atribuidos al partner. |
| Permitir el procesamiento de gastos |  |
| Permitir el acceso a tu panel de control de Protect360 | [Si está habilitado] Datos de Protect360 del partner |

Saber más sobre cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos de ad network</Anchor>.

<div id="agency-permissions" />

### Permisos de la agencia

Puedes permitir que Vungle configure tu aplicación como agencia.

**Para habilitar los permisos de agencia:**

1. Habilita los permisos de ***agencia*** .
2. Concede a Vungle acceso como agencia a uno o varios de los siguientes elementos:

| **Permitir el acceso a tu panel de control de Protect360** | [Si está habilitado para tu cuenta] Datos de Protect360 de la agencia |
| --- | --- |
| **Permitir el acceso a tus reportes de retención y de cohortes** | Datos de retención y cohortes de la agencia |
| **Permitir el acceso a datos agregados orgánicos.** | Datos orgánicos agregados de la agencia |
| **Permitir la configuración de postbacks de eventos in-app** | Configura postbacks de eventos in-app asignados a la pestaña de integración. |

Saber más sobre cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos de agencia</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-vungle=configuraci%C3%B3n-de-vungle h_01HJZVD66Q6ZBPGEASQTAQNH3G=configuraci%C3%B3n-de-vungle h_01HJZVD66QE7BTR3F5QKJZFPMD=consejo h_01HJZVD66QDTZAG9GD153SM2AG=integration-tab activate-partners=activar-los-partners h_01HJZVD66QG7FHRCEAT7WX7E1R=activar-los-partners h_01HJZVD66Q9HB72WQM5Y4S60FN=nota h_01HJZVD66Q5HGF9GWKHB87GK2Y=attribution-link-tab h_01HJZVD66R0XX4DB12R25Y3PXM=cost-tab h_01HJZVD66SNVAHYSSFN2RMWHZX=ad-revenue-tab h_01HJZVD66SJT203JAYDQQ29ZEC=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HJZVD66S4680GJ0A9SFSGY4Z=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HJZVD66SC6KK9KWHR6WQYGR3=permisos-de-la-agencia" />
