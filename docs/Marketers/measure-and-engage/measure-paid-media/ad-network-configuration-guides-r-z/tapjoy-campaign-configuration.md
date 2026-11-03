---
title: Configuración de la campaña de Tapjoy
metadata:
  keywords:
    - Tapjoy
    - SDK
    - configuration
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
  created_at: '2015-06-10T14:19:38Z'
  edited_at: '2026-09-10T00:25:24Z'
  id: 207033956
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/207033956
---
> **De un vistazo:** Tapjoy, un partner integrado de ad network de AppsFlyer, es una plataforma de anuncios y monetización de aplicaciones. Además de la atribución móvil basada en clics, Tapjoy ofrece atribución view-through, que se puede registrar con AppsFlyer.

Para configurar tus campañas con Tapjoy, sigue los pasos a continuación.

## Configuración de Tapjoy

**Requisito previo:** Una cuenta con Partners. Si no tienes\n una cuenta, ponte en contacto con Partners para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña\n **Colaborar > Integraciones de Partners > Marketplace** .  
    (**Para editar una integración existente:** ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca Partners y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el\n selector **Activar partner**.   
   \n **Nota:** El selector\n **debe permanecer activado (activo) mientras trabajes con Partners**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber\n más sobre\n <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña ***Integración*** está dividida en diferentes secciones, tal como se describe a continuación.

### Activar los partners

Para habilitar su configuración, debes <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">activar el partner</Anchor> en la primera visita mediante el selector ***Activar partner***.

### Configuración general

#### id\_aplicación

Tapjoy se conecta con AppsFlyer a través de un ID de red exclusivo. Si aún no tienes el ID de la aplicación, debes obtenerlo de Tapjoy para continuar con la integración.

#### Habilitar la atribución por impresiones

Actívalo si quieres atribuir instalaciones view-through de Tapjoy. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

### Postbacks predeterminados

Envía postbacks automáticos a Tapjoy después de las instalaciones y las instalaciones rechazadas. Utiliza esta sección para definir la **fuente de los usuarios** para los postbacks.

Selecciona ***Solo este partner*** para instalaciones procedentes únicamente de usuarios atribuidos a Tapjoy.  
Selecciona **Todas las fuentes, incluidas las orgánicas** para que toda tu base de usuarios esté disponible para ser reportada a Tapjoy.

Las instalaciones rechazadas se pueden enviar para **Solo este partner**.

#### Postbacks de lanzamiento

Desde el 1 de julio de 2020, ya no enviamos postbacks de lanzamiento a Tapjoy. Si tu integración se configuró antes de esta fecha, puede haber cambios en tus configuraciones. La siguiente tabla explica los posibles cambios y las acciones que debes realizar, cuando corresponda:

| Tu configuración | Se actualizará a | Tus próximos pasos |
| --- | --- | --- |
| Enviar a Tapjoy **todos los lanzamientos** (de todas las fuentes de medios, incluido el orgánico) | Enviar a Tapjoy:<ul><li>**todas las instalaciones** (de todas las fuentes de medios, incluidas las orgánicas)</li><li>**todos los eventos `af_app_opened`** (de todas las fuentes de medios, incluidas las orgánicas)</li></ul> | No se requiere ninguna acción adicional. Esta actualización no tiene ningún impacto real en la configuración. |
| Enviar a Tapjoy **solo los primeros lanzamientos atribuidos** | Enviar a Tapjoy **instalaciones** atribuidas solo a Tapjoy | Si también quieres enviar eventos `af_app_open`:<ul><li>En AppsFlyer, en la página de integración de Tapjoy, configura el envío del evento en la sección ***Postbacks de eventos in-app***</li></ul> |
| Enviar a Tapjoy **todos los lanzamientos** (de todas las fuentes de medios, incluido el orgánico)<br /><br />**PERO**<br /><br />No se atribuyó ninguna conversión a Tapjoy en los 3 meses anteriores al 1/07/2020 | Enviar **todas las instalaciones**<br /><br />**Y**<br /><br />Durante 30 días a partir del 1/07/2020, **todos los lanzamientos** | Si también quieres enviar eventos `af_app_open`:<ul><li>En AppsFlyer, en la página de integración de Tapjoy, configura el envío del evento en la sección ***Postbacks de eventos in-app***.</li></ul>Si lo haces durante el periodo de 30 días, dejaremos de enviar todos los lanzamientos y empezaremos a enviar en su lugar todos los eventos `af_app_open`.<br /><br />Si lo haces después del periodo de 30 días, dejaremos de enviar lanzamientos y no enviaremos eventos `af_app_open` hasta que se configure lo contrario. |

### Configuración de eventos in-app

En esta sección, puedes configurar los postbacks de eventos in-app que se envían a Tapjoy.

**Para configurar postbacks de eventos in-app:**

1. Activa los **postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para añadir un evento SDK o de servidor a lista.
3. Rellena los siguientes datos: 

| Nombre del parámetro | Nota |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos server-to-server.<br />**Consejo**: ¿No encuentras el evento que buscas?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Lee más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados</Anchor>.</li></ul> |
| **Asignado al evento asociado** | El nombre o ID único de cada evento, tal como lo define el partner. Existen varias configuraciones de asignación:<ul><li>**Campo de texto:** Obtén el ID del evento correspondiente del partner.</li><li>**Cuadro desplegable:** Selecciona el evento de AppsFlyer predefinido más adecuado.</li><li>**Como está**: Envía los eventos tal como están, sin asignación de nombres.</li></ul> |
| **Para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner**: envía postbacks solo cuando el evento se atribuya a este partner, es decir, el usuario que lo realizó provino de este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks de eventos atribuidos a cualquier partner y de eventos orgánicos, es decir, el usuario que los realizó provino de cualquier fuente de medios.</li></ul> |
| **Incluye** | <ul><li>**Sin datos (por defecto)**: Envía solo el evento en sí, sin ningún valor de evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, incluidos los valores de ingresos (si existen en el evento).</li><li>**Valores sin ingresos**: envía todos los parámetros del evento, excluyendo los valores de ingresos.</li></ul> |

4. [Opcional] Haz clic en Añadir condición![image.png](https://files.readme.io/8e650caf6472b316bd49bc25c45cc4c9d63b67770dd1c920fb873118b82ff868-17023682954385.png) icono de un evento para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">configurar condiciones para el evento</Anchor> enviado a Tapjoy.   

   > 📘 **Nota:**
   >
   > Tapjoy recomienda no añadir condiciones a los eventos que se le envían, ya que esto podría causar problemas con el sistema propietario de recompensas de Tapjoy y podría afectar negativamente a la experiencia de usuario.

5. Haz clic en **Guardar integración**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

**Nota:** TapJoy no informa de impresiones de Offerwall a AppsFlyer. Por lo tanto, las instalaciones posteriores a las impresiones de Offerwall no se contabilizan en AppsFlyer. Saber más sobre las [impresiones de Offerwall](https://www.tapjoy.com/offerwall/).

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de los costos por API. Consulta <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">la tabla de integración de costos de redes de publicidad</Anchor> para obtener más información sobre las dimensiones, métricas y funciones admitidas. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<div id="cost-data-sync-status" />

<Accordion title="Estado de sincronismo de datos de costos">

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el panel de control de estado de la integración de costos (e ingresos por publicidad) o en el panel de control de la red de publicidad individual.

</Accordion>

> 📘 **Notas**
>
> * Si se pasan macros de coste en el enlace de atribución, no se puede habilitar la integración de la API. Habilitar la integración de la API de costos mientras existan macros de costo en el enlace de atribución puede causar reportes de costos duplicados. Ponte en contacto con tu Account Manager de TapJoy y con tu CSM de AppsFlyer para eliminar todas las macros de coste de los enlaces de atribución existentes.
> * Una vez que hayas establecido el costo de TapJoy, no cambies el nombre de ninguna campaña, conjunto de anuncios o anuncio único activo, ni uses macros dinámicas con el parámetro del nombre de la campaña, ya que pueden provocar discrepancias importantes o la falta de datos de costos.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Esta sección es pertinente si actúas como publisher y muestras anuncios de partners a tus usuarios. Como tal, con seguridad te gustaría medir el nivel de engagement de tus usuarios adquiridos a partir de distintas fuentes, a fin de identificar las fuentes que te resultan más rentables. Saber más sobre la <Anchor target="_blank" href="https://dev.tapjoy.com/en/graphql-api/Appsflyer#iap-and-ad-revenue-configuration-for-roas">configuración de ingresos por publicidad de Tapjoy</Anchor>.

**Para habilitar la API de ingresos por publicidad**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">estas instrucciones de integración</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a Tapjoy, tanto si el partner actúa como ad network, agencia o incluso ambas. Ten en cuenta que, incluso si la atribución está deshabilitada para Tapjoy, la pestaña de permisos está activa y puedes otorgarle el control a Tapjoy.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación.

### Permisos para Redes de Publicidad

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles*** - solo a los datos de usuarios fieles propios de Partners
* ***Permitir acceso a tus datos agregados de eventos in-app** -* solo a los datos de eventos in-app propios de Partners
* **Permitir acceso a tus datos agregados de ingresos**: solo a los datos de ingresos atribuidos al partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">los permisos de ad network</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-tapjoy=configuraci%C3%B3n-de-tapjoy h_01HJS1SANCA03NGA11EA2359Z9=configuraci%C3%B3n-de-tapjoy h_01HJS1SANC560TH8VJ2R2ZRKZA=integration-tab activate-partners=activar-los-partners h_01HJS1SANC0KMZ3HFM2MNJ6SCV=activar-los-partners general-settings=configuraci%C3%B3n-general h_01HJS1SANCN7RXVCKCQD4N8B2S=configuraci%C3%B3n-general app_id=id_aplicaci%C3%B3n h_01HJS1SANCSQ8Z3YB41V7KHAZD=id_aplicaci%C3%B3n enable-viewthrough-attribution=habilitar-la-atribuci%C3%B3n-por-impresiones h_01HJS1SANCR3DEAPQW0F1S0YP9=habilitar-la-atribuci%C3%B3n-por-impresiones default-postbacks=postbacks-predeterminados h_01HJS1SANCN0KQ7APJBPAVD7G7=postbacks-predeterminados launch-postbacks=postbacks-de-lanzamiento h_01HJS1SANCZTZ2NR3XTEPVRKXG=postbacks-de-lanzamiento inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HJS1SANDCNEXH91VMY2E0KYJ=configuraci%C3%B3n-de-eventos-in-app h_01HJS1SAND8DY0SNRZKGBFAZKK=nota h_01HJS1SANDQK7DT52KF9011YZB=attribution-link-tab h_01HJS1SAND247NKAB9FQBBCSPQ=cost-tab h_01HJS1SANDWEMAHC3SJ64EMR7F=cost-data-sync-status h_01HJS1SANDVWHSW4GPQHS0ZM6G=notas h_01HJS1SANDTWFDTAZYEHB3KKEH=ad-revenue-tab h_01HJS1SAND4S7S8NW05N4R20NB=permissions-tab ad-network-permissions=permisos-para-redes-de-publicidad h_01HJS1SANDAW1MH9EYRZSD5BTG=permisos-para-redes-de-publicidad" />
