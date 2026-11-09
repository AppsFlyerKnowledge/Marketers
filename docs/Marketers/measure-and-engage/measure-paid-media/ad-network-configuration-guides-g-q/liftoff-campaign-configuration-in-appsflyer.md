---
title: Configuración de la campaña de Liftoff en AppsFlyer
metadata:
  keywords:
    - liftoff
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
  created_at: '2016-03-28T09:38:23Z'
  edited_at: '2026-09-11T00:24:01Z'
  id: 209731633
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/209731633
---
> **De un vistazo:** Liftoff, un partner integrado de la ad network de AppsFlyer, es uno de los principales partners de demanda para marcas y desarrolladores de apps. Liftoff ofrece atribución móvil basada en clics y por view-through, así como retargeting basado en clics y por view-through, que puedes registrar con AppsFlyer.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/liftoff.png" />

<div id="important" />

> 🚧 **Importante:**
>
> Algunas fuentes de medios restringen el intercambio de datos con terceros. AppsFlyer no puede compartir datos de nivel de usuario de los usuarios adquiridos a través de estas fuentes de medios con plataformas o servicios de terceros. Por lo tanto, todas las instalaciones de dichas fuentes de medios se envían como orgánicas.
>
> Para obtener más detalles y una lista de las fuentes de medios que restringen el intercambio de datos con terceros, haz clic <Anchor target="_blank" href="/marketers/es/docs/user-level-data-retention">aquí</Anchor>.

<div id="setting-up-liftoff" />

## Configuración de Liftoff

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de partners > Marketplace**.  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (active) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña **Integración** está dividida en diferentes secciones, tal como se describe a continuación.

<div id="activate-partners" />

### Activar los partners

El <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">partner debe activarse</Anchor> al activar el selector **Activar partner** en la primera visita para permitir su configuración.

<div id="general-settings" />

### Configuración general

**Habilitar la atribución view-through**

Actívalo si deseas atribuir las instalaciones por view-through de Liftoff. El control deslizante de la ventana retrospectiva por view-through está disponible en la pestaña [**Enlace de atribución**](/docs/liftoff-campaign-configuration-in-appsflyer#attribution-link-tab).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a Liftoff después de las instalaciones de los usuarios, las instalaciones rechazadas y los reengagements. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo este partner** para los eventos que provienen solo de usuarios atribuidos a Liftoff.  
Selecciona **Todas las fuentes, incluidas las orgánicas** para que toda tu base de usuarios esté disponible para ser reportada a Liftoff.

<div id="note" />

> 📘 **Nota:**
>
> Como red de TODAS las instalaciones, Liftoff prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluida la orgánica. Para ello, selecciona **Todas las fuentes, incluidas las orgánicas** para enviar todos los postbacks de instalación a Liftoff.

**Para configurar postbacks de eventos in-app:**

1. Activa **Postbacks de eventos in-app**
2. Elige si quieres reportar **eventos seleccionados** al partner o **todos**.
   * Nota: Si eliges reportar todos los eventos, no se reporta el evento af\_app\_opened.
3. Si eliges seleccionar eventos manualmente, haz clic en **Agregar evento** para añadir un evento de SDK a la lista.
4. Rellena los siguientes datos:

| Nombre del parámetro | Nota |
| --- | --- |
| **Nombre del evento de SDK** (solo obligatorio para la selección manual) | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK o desde eventos de servidor a servidor.  <br />**Consejo**: si no ves el evento que quieres en la lista, actívalo en un dispositivo con una instalación no orgánica y vuelve a comprobarlo. |
| **Opción de envío** | Selecciona la opción de envío para el evento:  <br />**Solo este partner** para los eventos que provienen **solo** de usuarios atribuidos a Liftoff.  <br />**Todas las fuentes, incluidas las orgánicas** para que toda tu base de usuarios esté disponible para ser reportada al partner |
| **Enviar datos de eventos** | <ul><li>**Sin valores ni ingresos:** envía solo el evento en sí sin el valor del evento.</li><li>**Con valores y sin ingresos:** envía todos los parámetros, excepto el valor de ingresos.</li><li>**Con valores e ingresos**: envía todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento).</li></ul> |

5. Haz clic en **Guardar**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes usar un enlace de plataforma única o un <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Obtén más información sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costes de ad network</Anchor> para obtener todos los detalles sobre las dimensiones, métricas y funciones compatibles. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costes</Anchor> y la última vez que AppsFlyer logró extraer los datos de costes coincidentes en el dashboard de estado de la integración de costes (e ingresos por publicidad) o en el dashboard de la ad network individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Este partner no admite ingresos por publicidad.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a Liftoff. Ten en cuenta que, incluso si la atribución está deshabilitada para Liftoff, la pestaña Permisos está activa y puedes otorgarle el control a Liftoff.

<div id="ad-network-permissions" />

### Permisos de ad network

En esta pestaña, puedes seleccionar los permisos que quieres conceder a Liftoff. Ten en cuenta que, incluso si la atribución está deshabilitada para Liftoff, la pestaña Permisos está activa y puedes otorgarle el control a liftoff.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

* **Permitir la configuración de la integración**: permite que el partner configure la pestaña integración (con excepción de postbacks de eventos in-app).
* **Permitir la configuración de postbacks de eventos in-app**: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña integración.
* **Permitir el acceso a tu reporte de retención**: solo para los datos propios de retención del partner.
* **Permitir acceso a tus datos agregados de usuarios fieles** - solo a los datos agregados de usuarios fieles propios del partner
* **Permitir acceso a tus datos agregados de eventos in-app** - solo a los datos de eventos in-app propios del partner
* **Permitir acceso a tus datos agregados de ingresos**: solo para los datos de ingresos atribuidos al partner.
* **Permitir el acceso a tu dashboard de Protect360**: solo para los datos propios de Protect360 del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

<div id="agency-permissions" />

### Permisos de la agencia

Si trabajas con Liftoff como partner de agencia, en esta sección puedes otorgarle permisos para gestionar su propia configuración para tu aplicación:

* **Selector principal** - Configurarlo en **ACTIVADO**:

  * Revela las opciones de permisos de la agencia.
  * Permite que la agencia se atribuya las instalaciones de la aplicación.
  * Permite que la agencia vea los datos promocionados de anuncios de Meta y X Ads

  **Advertencia: Las instalaciones de la agencia que se produzcan cuando el selector esté DESACTIVADO no se atribuyen a la agencia** y no aparecen en el dashboard ni en los datos de la agencia (<Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#permisos-de-la-agencia">más detalles</Anchor>).

* **Permitir el acceso a tu panel de control de Protect360**
* **Permitir el acceso a tus reportes de retención y cohortes** - datos de retención/cohortes creados únicamente por los usuarios traídos por la agencia.
* **Permitir el acceso a datos agregados orgánicos.**
* **Permitir la configuración de postbacks de eventos in-app**: permite que la agencia configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña Integración.
  * **Permisos para compartir eventos** - selecciona aquí la opción que prefieras:  
    a) **Solo este partner** - envía solo eventos del tráfico que la propia agencia lleve a la aplicación  
    b) **Todas las fuentes, incluidas las orgánicas** - envía eventos de todas las fuentes de tu tráfico, incluidas otras fuentes de medios, agencias y usuarios orgánicos
  * **Permitir enviar ingresos de eventos** - permite que la agencia envíe eventos que incluyan su valor monetario
  * Asegúrate de seleccionar los eventos específicos para los cuales quieres otorgarle permiso a la agencia. Haz clic en **Agregar evento** y elige el evento de la lista desplegable. Haz esto para cada evento que desees agregar.

Saber más sobre <Anchor target="_blank" href="/partners/es/docs/about-agency-accounts">cómo trabajar con agencias</Anchor>.

</Accordion>

<div id="set-up-skadnetwork-integration-with-liftoff" />

## Configura la integración de SKAdNetwork con Liftoff

**Para recibir datos de SKAdNetwork de Liftoff:**

1. <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">Para dar soporte a SKAdNetwork, actualiza tu SDK de AppsFlyer a la versión más reciente</Anchor>.
2. En AppsFlyer Conversion Studio, <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#configuración-de-valores-de-conversión-en-skan-conversion-studio">configura los valores de conversión para medir los eventos que quieras</Anchor>.
3. Comparte con Liftoff el objetivo de tu campaña y el evento final con el que quieres optimizar tus campañas. Se recomienda que tu evento final se correlacione con tu evento preferido y ocurra cerca del momento de la instalación.  
   Por ejemplo,
   * **Campañas de CPA:** Comparte el evento requerido y el objetivo de CPA que se usarán para la optimización de campañas de SKAdNetwork.
   * **Campañas de CPI:** Comparte el objetivo de CPI que se usará para la optimización de campañas de SKAdNetwork.
4. Ponte en contacto con tu equipo de cuentas de Liftoff para confirmar que los postbacks de SKAdNetwork se están enviando con valores de conversión.
5. [Opcional] Para compartir el ID de transacción de SKAdNetwork con Liftoff, activa **Compartir ID de transacción en modo SKAdNetwork**.  
   Saber más sobre el <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">ID de transacción.</Anchor>

<div id="product-feed-retargeting-with-liftoff" />

## Retargeting del feed de productos con Liftoff

Para que la atribución de eventos de producto funcione correctamente, Liftoff necesita recibir los ID de los productos asociados a cada uno de tus eventos. Por ejemplo, los ID de productos específicos que los usuarios compran o añaden al carrito.

Estos ID deben vincularse de nuevo con los ID únicos que envías a Liftoff en tu feed de productos. Liftoff es compatible con la <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#parámetros-de-evento-predefinidos">convención estándar de AppsFlyer para compartir estos datos</Anchor> mediante atributos af\_content\_id de forma predeterminada.

Si tienes una implementación no estándar de datos de eventos, ponte en contacto con tu CSM de Liftoff para ver si la integración es posible.

<div data-zendesk-anchors="h_01HGFR9QYBQ3BK3TM364SJDKWZ=importante setting-up-liftoff=configuraci%C3%B3n-de-liftoff h_01HGFR9QYBPY2XR4KMWMJKHHMQ=configuraci%C3%B3n-de-liftoff h_01HGFR9QYBJG0WD6X203X8MYFV=integration-tab activate-partners=activar-los-partners h_01HGFR9QYBXAQQKPRW1KKF6989=activar-los-partners general-settings=configuraci%C3%B3n-general h_01HGFR9QYBPCYCJRY20S1TCF6R=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HGFR9QYB8JHTAAB591QQ1P6J=postbacks-predeterminados h_01HGFR9QYBW8DFZK63EZ3V5622=nota h_01HGFR9QYB42YK8FJD308YWXC7=attribution-link-tab h_01HGFR9QYBJ20T4F0W5486B4NW=cost-tab h_01HGFR9QYBV9ZCGJ1D6BD1T9JG=ad-revenue-tab h_01HGFR9QYB9DA5XYXPEARZSCHF=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HGFR9QYB0VCPG7YCX64BBKY9=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HGFR9QYBR3W0JXY7MHQ8PZT7=permisos-de-la-agencia set-up-skadnetwork-integration-with-liftoff=configura-la-integraci%C3%B3n-de-skadnetwork-con-liftoff h_01HGFR9QYBG4830DKGMGV716B7=configura-la-integraci%C3%B3n-de-skadnetwork-con-liftoff product-feed-retargeting-with-liftoff=retargeting-del-feed-de-productos-con-liftoff h_01HGFR9QYB302DVBYXMK0XY4ED=retargeting-del-feed-de-productos-con-liftoff" />
