---
title: Configuración de la campaña de AppLovin
metadata:
  keywords:
    - Applovin
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
  created_at: '2016-03-06T12:20:32Z'
  edited_at: '2026-09-11T00:22:54Z'
  id: 208335613
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/208335613
---
> **De un vistazo:** AppLovin, un partner integrado de AppsFlyer, es una conocida ad network de tráfico de aplicaciones móviles. Además de la atribución móvil basada en clics, AppLovin también ofrece atribución de costos, ingresos por publicidad y por impresiones, que puedes registrar con AppsFlyer.

<div id="setting-up-applovin" />

## Configuración de AppLovin

**Requisito previo:** una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace** .  
   (**Para editar una integración existente:** ve a la pestaña **Collaborate > Partner Integrations > Active integrations** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="activate-partner" />

### Activar socio

En esta **primera visita**, tendrás que activar el botón **Activar partner** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="note" />

> 📘 **Advertencia**
>
> Como red de TODAS las instalaciones, AppLovin prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluidas las orgánicas. Se recomienda seleccionar *Eventos atribuidos a cualquier partner* para enviar todos los postbacks de instalación a AppLovin.

<div id="general-settings" />

### Configuración general

**Compartir indicación de orgánico/no orgánico**

Cuando esta opción está activada, si se envía un postback de instalación para todas las fuentes de medios, incluidas las orgánicas, AppLovin recibirá una indicación de si la instalación fue orgánica o no orgánica.

**Clave de SDK**

AppLovin se conecta con AppsFlyer mediante una sdk\_key única. Si todavía no tienes la sdk\_key, debes obtenerla de AppLovin para continuar con la integración.

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir instalaciones view-through de AppLovin. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a AppLovin después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para los eventos que proceden únicamente de usuarios atribuidos a AppLovin.  
Selecciona **Eventos atribuidos a cualquier partner u orgánico** para que toda tu base de usuarios esté disponible para reportarla a AppLovin.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección puedes asignar qué eventos de AppsFlyer enviar a AppLovin mediante postbacks.

1. Vuelve a configurar aquí la sdk\_key de AppLovin.
2. Activa los Postbacks de eventos in-app con el selector.
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
4. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
5. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define AppLovin.  <br />Obtén el nombre de evento correspondiente de AppLovin y configúralo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

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

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el panel de control de estado de la integración de costos (e ingresos por publicidad) o en el panel de control de la red de publicidad individual. 

<div id="applovin-billable-cost" />

> 🚧 **Costo facturable de AppLovin**
>
> A partir del 1 de agosto de 2024, AppLovin factura a todos sus clientes en función de las instalaciones probabilísticas. Antes de esa fecha, a algunos clientes se les facturaba en función de las instalaciones de SKAN. <Anchor target="_blank" href="https://support.applovin.com/hc/en-us/articles/28531589437965-iOS-Billing-Method">Consulta Applovin para obtener información adicional</Anchor>
>
> La integración de costos de AppsFlyer con AppLovin refleja con precisión este costo facturable. Esto significa que el costo en AppsFlyer coincide correctamente con el costo en la plataforma de AppLovin.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

* AppLovin proporciona mediación de ingresos por anuncios con datos agregados.
* Información sobre la <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution">atribución de ingresos por anuncios</Anchor> (monetización de anuncios)

**Para habilitar la API de ingresos por publicidad**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">estas instrucciones de integración</Anchor>.

<div id="note-1" />

> 📘 **Advertencia**
>
> * AppLovin envía los ingresos por anuncios que genera por sí mismo.
> * Los ingresos por anuncios de partners de mediación como ironSource y Unity pueden mostrarse en el dashboard de AppLovin, pero no se envían a AppsFlyer. Activa otros partners de mediación en el dashboard de AppsFlyer para enviar datos de ingresos por anuncios directamente a AppsFlyer.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a AppLovin. Ten en cuenta que, aunque la atribución esté deshabilitada para AppLovin, la pestaña de permisos está activa y puedes otorgar control a AppLovin.

<div id="ad-network-permissions" />

### Permisos de ad network

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

* **Permitir configurar la integración** - permite que el partner configure la pestaña de integración (excepto los postbacks de eventos in-app)
* **Permitir la configuración de postbacks de eventos in-app**: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña integración.
* **Permitir el acceso a tu reporte de retención**: solo para los datos propios de retención del partner.
* **Permitir acceso a tus datos agregados de usuarios legales**: solo para los datos propios de usuarios leales del partner.
* **Permitir acceso a tus datos agregados de eventos in-app**: solo para los datos de eventos in-app propios del partner.
* **Permitir acceso a tus datos agregados de ingresos**: solo para los datos de ingresos atribuidos al partner.
* **Permitir el acceso a tu dashboard de Protect360**: solo para los datos propios de Protect360 del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-applovin=configuraci%C3%B3n-de-applovin h_01HKW93TKBNYVC05MA5GB37JVH=configuraci%C3%B3n-de-applovin h_01HKW93TKCPCFYD6HV2XH1QTHS=integration-tab activate-partner=activar-socio h_01HKW93TKCG5JCQK52QJ65483M=activar-socio h_01HKW93TKC2XGTZ7WAQ2E2AGPD=advertencia general-settings=configuraci%C3%B3n-general h_01HKW93TKCZCK6GB7M4VV5C1NB=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKW93TKCCRB21JAFDA2GWH6F=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW93TKCVWKTM9C8J220Q41E=configuraci%C3%B3n-de-eventos-in-app h_01HKW93TKCCXVQMBCGW02J7JK4=attribution-link-tab h_01HKW93TKCXMG7BHMEWRFSCM6N=cost-tab h_01J43V7Z67C98TG7CE2QQGVVWE=costo-facturable-de-applovin h_01HKW93TKDDWXA2C7456E8Q8GG=ad-revenue-tab h_01HKW93TKD8Z0QQADBJWMBP962=advertencia-1 h_01HKW93TKDBCXNA68YVMQVBVP0=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKW93TKD21RF42KMNA9J9WXF=permisos-de-ad-network" />
