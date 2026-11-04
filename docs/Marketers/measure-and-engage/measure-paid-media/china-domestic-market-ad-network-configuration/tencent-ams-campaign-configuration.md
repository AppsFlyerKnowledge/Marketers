---
title: Configuración de campaña de Tencent AMS
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - China
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-02-01T18:20:01Z'
  edited_at: '2026-09-17T00:26:24Z'
  id: 360017577338
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/360017577338
---
> **Información general:** Tencent AMS, partner integrado de ad network de AppsFlyer, opera propiedades de redes sociales y utilidades móviles en China, y permite a los profesionales del marketing ejecutar campañas de instalación de la app en: WeChat, la plataforma de comunicación móvil de la empresa, QQ, el servicio de mensajería instantánea, QQ Music, QQ Browser, Myapp, y más.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/tencentams.png" width="120px" />

<div id="setting-up-tencent-ams" />

## Configurar Tencent AMS

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Collaborate > Partner Integrations > Active integrations** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="general-settings" />

### Configuración general

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación. Para integrar TencentAMS con AppsFlyer, necesitas las siguientes credenciales: **account\_id, user\_action\_set\_id y access\_token**. Si aún no tienes estos valores, solicítalos directamente a Tencent AMS antes de continuar con la integración.

<Image alt="tencent.png" src="https://files.readme.io/56bfdc43b976f1f29f5ba121986aa66228cd79029025e84278cb3c304989fc3e-38300461521041.png" width="248px" />

<div id="note" />

> 📘 **Advertencia**
>
> El **access\_token** lo emite Tencent AMS y tiene una validez de 30 días. Según el requisito de Tencent, tú (o la agencia que te gestiona) debes **actualizar manualmente el token cada 30 días e introducirlo en el campo anterior**.
>
> * Si el token caduca, los postbacks a Tencent AMS fallarán hasta que se introduzca un token nuevo.
> * Si no sabes cómo obtener o actualizar el token, ponte en contacto con tu gestor de cuenta de Tencent AMS para que te oriente.
>
> **Tráfico gestionado por agencia:** Si una agencia promociona tu tráfico, **la agencia también debe completar y mantener el token por su parte**.

<div id="enable-view-through-attribution" />

#### Habilitar la atribución por impresiones

Para habilitar la atribución de instalación view-through, activa esta opción.  
El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

#### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a Tencent AMS tras las instalaciones de los usuarios. Esta sección muestra el **origen de los usuarios** que permiten enviar estos postbacks.

<div id="in-app-event-settings" />

#### Configuración de eventos in-app

En esta sección, puedes configurar los postbacks de eventos in-app que se envían a Tencent AMS.

**Para configurar postbacks de eventos in-app**,

1. Activa **postback de evento in-app**.
2. Establece la **ventana de postbacks de eventos in-app**, si es necesario (lee más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">configuración de la ventana de postbacks de eventos in-app</Anchor>).
3. Haz clic en **Añadir evento** para agregar un evento de SDK a la lista.
4. Completa los siguientes parámetros en la tabla de abajo

| Nombre del parámetro | Nota |
| --- | --- |
| **Nombre de evento SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK o desde eventos de servidor a servidor.  <br />**Consejo**: si no ves el evento que quieres en la lista, actívalo en un dispositivo con una instalación no orgánica y vuelve a comprobarlo. |
| **Identificador de evento de partner** | El nombre exclusivo o ID de cada evento definido por el socio. Selecciona el evento predefinido más adecuado para tu evento SDK. |
| **Opción de envío** | Selecciona la opción de envío del evento:  <br />**Solo este partner** para los eventos que provienen **solo** de usuarios atribuidos a Tencent AMS.  <br />**Todas las fuentes, incluidas las orgánicas** para que toda tu base de usuarios esté disponible para ser reportada al partner. |
| **Enviar datos de eventos** | <ul><li>**Sin valores ni ingresos:** envía solo el evento en sí sin el valor del evento.</li><li>**Con valores y sin ingresos:** envía todos los parámetros, excepto el valor de ingresos.</li><li>**Con valores e ingresos**: envía todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento).</li></ul> |

5. Haz clic en **Guardar integración**.

</Accordion>

<div id="attribution-link" />

<Accordion title="Enlace de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o un <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de redes de publicidad</Anchor> para obtener detalles completos sobre las dimensiones, métricas y funciones admitidas. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el dashboard de estado de la integración de costos (e ingresos por publicidad) o en el dashboard de la red de publicidad individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La integración de los ingresos por publicidad no está disponible para Tencent AMS.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a Tencent AMS. Ten en cuenta que, incluso si la atribución está deshabilitada para Tencent AMS, la pestaña de permisos está activa y puedes otorgar control a Tencent AMS.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

* **Permitir configurar la integración** - permite que el partner configure la pestaña de integración (excepto los postbacks de eventos in-app)
* **Permitir la configuración de postbacks de eventos in-app**: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña integración.
* **Permitir el acceso a tu reporte de retención**: solo para los datos propios de retención del partner.
* **Permitir acceso a tus datos agregados de usuarios fieles** - solo a los datos de usuarios fieles propios del partner
* **Permitir acceso a tus datos agregados de eventos in-app** - solo a los datos de eventos in-app propios del partner
* **Permitir acceso a tus datos agregados de ingresos**: solo para los datos de ingresos atribuidos al partner.
* **Permitir la ingesta de gasto** - permite que el partner envíe datos de gasto publicitario en archivos; solo para esta aplicación.
* **Permitir el acceso a tu dashboard de Protect360 & raw data** - solo a los datos de Protect360 propios del partner, siempre que la función esté habilitada para el anunciante

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-ad-network">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-tencent-ams=configurar-tencent-ams h_01HJNQZJX2TX4C8ZR2Y9JCANGC=configurar-tencent-ams h_01HJNQZJX26YHHDX8GBBGBG68M=integration-tab general-settings=configuraci%C3%B3n-general h_01HJNQZJX2QSYR4D6EWB8S1BHQ=configuraci%C3%B3n-general h_01KXZFXJJGZHGQT345V190R5RJ=advertencia enable-viewthrough-attribution=habilitar-la-atribuci%C3%B3n-por-impresiones h_01HJNQZJX2VSCTVPE1B63P24TQ=habilitar-la-atribuci%C3%B3n-por-impresiones default-postbacks=postbacks-predeterminados h_01HJNQZJX2K7EJZ89TQBKF8SB7=postbacks-predeterminados inapp-event-settings=configuraci%C3%B3n-de-eventos-in-app h_01HJNQZJX2W7F5HCEGNVQHMTVE=configuraci%C3%B3n-de-eventos-in-app h_01HJNQZJX2XFD0Q8J3XSCN6ZVP=attribution-link h_01HJNQZJX2R4R6FQ01BTAR184H=cost-tab h_01HJNQZJX2T985MXFNSHAP58Y9=ad-revenue-tab h_01HJNQZJX29H2ZTR0PSRHMXAM8=permissions-tab" />
