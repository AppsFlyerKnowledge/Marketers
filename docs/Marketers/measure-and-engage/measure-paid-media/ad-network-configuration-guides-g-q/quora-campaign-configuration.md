---
title: Configuración de la campaña de Quora
metadata:
  keywords:
    - Advertisers
    - Quora
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-02-17T12:56:30Z'
  edited_at: '2026-08-12T12:15:21Z'
  id: 360000974737
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/360000974737
---
> **De un vistazo:** Quora, uno de los Partners integrados de AppsFlyer, es una de las comunidades de preguntas & respuestas en línea más populares. Más de 300 millones de visitantes únicos acuden a Quora cada mes para hacer preguntas y leer respuestas reveladoras. La amplia y comprometida audiencia de Quora es una de las principales razones por las que los profesionales del marketing han tenido éxito al anunciarse en Quora.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/quora.png?v=1" width="83px" />

## Configuración de Quora

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La ventana de configuración de Quora incluye 3 pestañas activas: **Integración, Enlace de atribución** y **Permisos**. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

Para ver una descripción detallada del Encabezado de la Ventana de Configuración de Partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

> 👍 **Consejo**
>
> * El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">Configuración general</Anchor> en la pestaña de Integración es **obligatorio para todos los partners**.
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

### Activar socio

En la **primera visita**, tendrás que activar el botón ***Activar Partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

Postbacks predeterminados

Envía postbacks automáticos a Quora después de las instalaciones de los usuarios.

> 📘 **Nota:**
>
> La opción **Only events attributed to this partner** es la única opción con Quora y se selecciona de forma predeterminada.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o un <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

La integración de costos no está disponible para este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La integración de ingresos por publicidad no está disponible para este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a Quora, tanto si el partner actúa como ad network, agencia o ambas cosas. Ten en cuenta que, incluso si la atribución está deshabilitada para Quora, la pestaña de permisos está activa y puedes otorgarle el control a Quora.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

### Permisos de ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos***: solo a los datos de ingresos atribuidos al partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-quora=configuraci%C3%B3n-de-quora h_01HKW851RK4MHYEW1AY2E2KH5Q=configuraci%C3%B3n-de-quora h_01HKW851RK9KMV6PJ7YEN7ZMW2=consejo h_01HKW851RKYQ0T9XY74EXB4GWX=integration-tab activate-partner=activar-socio h_01HKW851RKD56502S4PSX8096T=activar-socio h_01HKW851RM09VR496Q7XFB3EMY=nota h_01HKW851RM4HP8EVGKD2EJH529=attribution-link-tab h_01HKW851RM4DGBABR81ZJZHBYW=cost-tab h_01HKW851RMQ0KY4CMWP7N4F2T4=ad-revenue-tab h_01HKW851RMV5A43RS3ZFZEPW8Z=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKW851RM2G6Y4J4KQBHAEF3A=permisos-de-ad-network" />
