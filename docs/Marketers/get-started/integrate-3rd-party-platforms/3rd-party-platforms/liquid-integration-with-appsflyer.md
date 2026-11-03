---
title: Integración de Liquid con AppsFlyer
metadata:
  keywords:
    - Liquid
    - attribution data
    - integrated partner
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T11:36:06Z'
  edited_at: '2026-08-12T11:59:07Z'
  id: 207040626
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/207040626
---
> **De un vistazo:** Liquid, un partner integrado de AppsFlyer, automatiza tus campañas y procesos sin necesidad de llamar a tu equipo de TI. Su motor de reglas inteligente actúa en función del comportamiento de los usuarios y de análisis avanzados.

> 🚧 **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

## Configuración de Liquid

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

### Activar socio

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

### Configuración general

**Token API**

Liquid se conecta con AppsFlyer a través de un token API único. Si aún no lo tienes, debes obtenerlo de Liquid para continuar con la integración o seguir las instrucciones que se indican a continuación.

[![](https://files.readme.io/1479b1569af7d8fb95c9efd7beddf169369d92790721ad9f15f3fd1615973e0d-360002201405.png)](https://files.readme.io/1479b1569af7d8fb95c9efd7beddf169369d92790721ad9f15f3fd1615973e0d-360002201405.png)

### Obtención del token de API

Puedes encontrar el token API iniciando sesión en el dashboard de Liquid.

* Haz clic en el icono **Settings**
* Copia el token API de producción
* Introduce el APP\_TOKEN que recibiste de Liquid

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a las instalaciones de usuarios de Liquid. Usa esta sección para definir el envío de estos postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Selecciona **Events attributed to any partner or organic** para enviar postbacks a Liquid de cualquier usuario que descargue la app, o selecciona **Off**.

Haga clic en **Guardar**.

Una vez guardada esta configuración, AppsFlyer empieza a enviar los siguientes datos a Liquid para cada instalación orgánica y no orgánica:

* Token de la app
* customer\_user\_id tal como se ha establecido en el SDK
* Fuente de medios
* Nombre de la campaña

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para Liquid.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Los datos de costos no son compatibles con la integración con este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para Liquid.

</Accordion>

<div data-zendesk-anchors="h_01H9FKBW5QYQGZ7PNEJMHZ6H2R=importante setting-up-liquid=configuraci%C3%B3n-de-liquid h_01H9FKBW5QMJTARZ6KZ41QT1BN=configuraci%C3%B3n-de-liquid h_01H9FKBW5QM601CMQ6Y2PNJ1HQ=integration-tab activate-partner=activar-socio h_01H9FKBW5RRYW1JTK2S9V4V6SA=activar-socio general-settings=configuraci%C3%B3n-general h_01H9FKBW5RB52QQKVF5TMFVKKT=configuraci%C3%B3n-general obtaining-the-api-token=obtenci%C3%B3n-del-token-de-api h_01H9FKBW5RCGHVJRJEBQW4KNGD=obtenci%C3%B3n-del-token-de-api default-postbacks=postbacks-predeterminados h_01H9FKBW5RVYXPEEFDG948P1XV=postbacks-predeterminados h_01H9FKBW5RNH2BRV8S31DT8SWA=attribution-link-tab h_01H9FKBW5RRQZZC4YQNWGHQTW6=cost-tab h_01H9FKBW5R7TNN5YA5YP36EJ63=ad-revenue-tab h_01H9FKBW5RC55F56K3EMQBJGEK=permissions-tab" />
