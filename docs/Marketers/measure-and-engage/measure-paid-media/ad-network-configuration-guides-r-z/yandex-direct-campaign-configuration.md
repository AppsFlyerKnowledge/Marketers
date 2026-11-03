---
title: Configuración de la campaña de Yandex Direct
metadata:
  keywords:
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
  created_at: '2021-03-30T10:52:06Z'
  edited_at: '2026-08-12T12:16:52Z'
  id: 360018910138
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/360018910138
---
> **En resumen:** Yandex Direct es una plataforma publicitaria que te permite ejecutar campañas de adquisición de usuarios y campañas de retargeting en la Búsqueda de Yandex, así como en miles de aplicaciones y sitios web de la red publicitaria de Yandex.

## Configurar Yandex Direct

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con el partner.  
    Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación. Para ver una descripción detallada del Encabezado de la ventana de configuración de partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

La ventana de configuración de Yandex Direct incluye 3 pestañas activas: **Integración, Enlace de atribución** y **Permisos**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

### Activar socio

En tu **primera visita** aquí, tendrás que activar **Activar partner** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
<Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más sobre la activación/desactivación del partner</Anchor>.

### Privacidad avanzada

Solo para aplicaciones iOS, **Activar privacidad avanzada (para iOS 14.5 y versiones posteriores)** controla qué datos se comparten con el partner mediante postbacks y reportes. <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#b-advanced-privacy">Saber más sobre la privacidad avanzada</Anchor>.

### ID de la transacción

Solo para aplicaciones iOS. Cuando **Compartir ID de transacción de SKAN** está activado, estás <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">compartiendo el ID de transacción de los postbacks de SKAdNetwork</Anchor> con el partner. Al hacer esto, el partner podría decodificar tus valores de conversión de SKAdNetwork.

### Configuración general

Los siguientes ajustes generales están disponibles para Yandex Direct.

#### ID del contador de Yandex Ecom Feed

Introduce el número de etiqueta de Metrika en **ID del contador de Yandex Ecom Feed** si estás ejecutando campañas de Smart Banner con tu feed de productos.

#### ID de la App de Yandex

Introduce el **ID de la App de Yandex** obtenido de Yandex Direct.

### Postbacks predeterminados

Envía postbacks automáticos a Yandex Direct después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo este partner** para los eventos que provienen solo de usuarios atribuidos a Yandex Direct.  
Selecciona **Todas las fuentes de medios, incluidas las orgánicas** para que toda tu base de usuarios esté disponible para ser reportada a Yandex Direct.

Como red que registra todas las instalaciones, Yandex Direct prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde todas las fuentes, y recomienda seleccionar **Todas las fuentes de medios, incluidas las orgánicas**.

### Postbacks de eventos in-app

En esta sección, puedes configurar los postbacks de eventos in-app que se envían a Yandex Direct.

1. Activa **Postbacks de eventos in-app** .
2. Establece la **ventana de postbacks de eventos in-app**, si es necesario (lee más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">configuración de la ventana de postbacks de eventos in-app</Anchor>).
3. Haz clic en **Añadir evento** para agregar un evento de SDK a la lista.
4. <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">Completa los parámetros obligatorios</Anchor>.
5. Haz clic en **Guardar integración**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o un OneLink.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de los costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de la ad network</Anchor> para obtener detalles completos sobre las dimensiones, métricas y funciones admitidas. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>. **Nota**: Añade el ID de campaña (af\_c\_id=`{campaign_id}`) a tus enlaces para garantizar un reporte de costo preciso. <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Más información</Anchor>

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Comprueba el estado de la API de costos</Anchor> y la última vez que AppsFlyer logró obtener datos de costos coincidentes, ya sea en el dashboard de estado de la integración de costos (e ingresos publicitarios), como en el dashboard de la ad network individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los datos de ingresos por publicidad no están disponibles para este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgar a Yandex Direct, tanto si el partner actúa como ad network, como agencia o incluso como ambas. Ten en cuenta que, aunque la atribución esté deshabilitada para Yandex Direct, la pestaña de permisos está activa y puedes conceder el control a Yandex Direct. <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">Configura los permisos para Yandex Direct</Anchor>.

</Accordion>

<div data-zendesk-anchors="set-up-yandex-direct=configurar-yandex-direct h_01HJZW81YDFP6ZV188XP3H4H54=configurar-yandex-direct h_01HJZW81YD3S8BEE6MNT30VYZH=integration-tab activate-partner=activar-socio h_01HJZW81YD1JA5N01HT248PR8K=activar-socio advanced-privacy=privacidad-avanzada h_01HJZW81YDNWAEKA2DP0QPPQRC=privacidad-avanzada transaction-id=id-de-la-transacci%C3%B3n h_01HJZW81YD8QEETTP4NSG2QCPQ=id-de-la-transacci%C3%B3n general-settings=configuraci%C3%B3n-general h_01HJZW81YDT69PGFTJMQ8WTYN2=configuraci%C3%B3n-general yandex-ecom-feed-counter-id=id-del-contador-de-yandex-ecom-feed h_01HJZW81YD18MW2BNGTZCZM7ZW=id-del-contador-de-yandex-ecom-feed yandex-app-id=id-de-la-app-de-yandex h_01HJZW81YDTQ0Q4H39GVJMHYNG=id-de-la-app-de-yandex default-postbacks=postbacks-predeterminados h_01HJZW81YDZDYDES5ZPRQ5BEC3=postbacks-predeterminados inapp-events-postbacks=postbacks-de-eventos-in-app h_01HJZW81YDMTRZ2VG8S9B48GTD=postbacks-de-eventos-in-app h_01HJZW81YE8XP6Q9RA9XTCKX2T=attribution-link-tab h_01HJZW81YES6M13VVJMTAB6KXQ=cost-tab h_01HJZW81YE7CYXEDFZKWZYVYET=ad-revenue-tab h_01HJZW81YERG3X6RG9Z2CM3YSF=permissions-tab" />
