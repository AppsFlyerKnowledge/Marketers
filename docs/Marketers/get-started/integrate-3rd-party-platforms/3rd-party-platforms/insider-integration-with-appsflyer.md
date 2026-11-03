---
title: Integración de Insider con AppsFlyer
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
  created_at: '2021-01-03T11:23:45Z'
  edited_at: '2026-08-12T11:58:56Z'
  id: 360016827838
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/360016827838
---
> **En resumen:** Insider, un partner integrado de AppsFlyer, es una plataforma de marketing y análisis para apps móviles y web. Insider ofrece segmentación predictiva en tiempo real y personalización en canales web, web móvil, aplicación móvil y anuncios.

![rockerbox-logo_en-us.png](https://cdn.appsflyer.com/marketplace/static/logo/useinsider.png?v=1)

> 🚧 **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

## Configuración de Insider

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

Este selector debe estar activado mientras trabajes con el partner.  
Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">activación del partner</Anchor>.

### Configuración general

Insider se conecta con AppsFlyer a través de un identificador de partner único.

**Para obtener tu identificador,** inicia sesión en la plataforma de **Insider** y copia tu identificador en la esquina superior derecha del Dashboard.

![insider-partner-ID_en-us.png](https://files.readme.io/5755dcc63db5714eb651c74b89e24bee769f792190d9aad0bfc0a742d321eb47-360015601658.png)

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a Insider tras las instalaciones de los usuarios. Utiliza esta sección para definir la fuente de los usuarios a los cuales se envían los postbacks de cada evento. Saber más sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#default-postbacks">postbacks predeterminados</Anchor>.

**Para enviar postbacks de cualquier usuario que descargue la aplicación a Insider**, selecciona **Todas las fuentes de medios, incluidas las orgánicas**.

### Configuración de eventos in-app

![insider-partner-field.png](https://files.readme.io/ad4b4a5e9d688be93b20ccf645c779c361390cc95e2a2acbab7299408b7478bf-4403354160785.png)

En esta sección, asignas los eventos de AppsFlyer al partner mediante postbacks. Saber más sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postbacks de eventos in-app</Anchor>

**Para configurar postbacks de eventos in-app:**

1. Introduce el **partner de Insider**, que encontrarás en la esquina superior derecha del Dashboard de **Insider**.

   ![insider-partner-ID_en-us.png](https://files.readme.io/5755dcc63db5714eb651c74b89e24bee769f792190d9aad0bfc0a742d321eb47-360015601658.png)
2. En AppsFlyer, habilita **postback de evento in-app.**
3. Haz clic en **Add Event** para añadir un evento de SDK a la lista.
4. Selecciona el **nombre del evento de SDK** en el menú desplegable.
5. Introduce el **identificador de evento de partner**.
6. Selecciona la **opción de envío**.
7. Selecciona la opción requerida en el menú desplegable Enviar ingresos:
   * **Sin valores ni ingresos:** envía solo el evento en sí sin el valor del evento.
   * **Con valores y sin ingresos:** envía todos los parámetros, excepto el valor de ingresos.
   * **Con valores e ingresos**: envía todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento).
8. Para completar la configuración de la integración, haz clic en **Guardar integración**.

> 📘 **Advertencia**
>
> Para habilitar los postbacks, establece el InsiderID como CUID.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para este partner.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Los datos de costos no son aplicables en la integración con este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por anuncios no son aplicables en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para este partner.

</Accordion>

<div data-zendesk-anchors="h_01H9FK8YZMFS4XHX69CG90A18K=importante setting-up-insider=configuraci%C3%B3n-de-insider h_01H9FK8YZM63N7HF514RVFPMJY=configuraci%C3%B3n-de-insider h_01H9FK8YZN7D4R6TBABMDB3K3K=integration-tab activate-partner=activar-socio h_01H9FK8YZNMN9QBRS33WPZQWPB=activar-socio general-settings=configuraci%C3%B3n-general h_01H9FK8YZNAFP5G2B277YPNY68=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01H9FK8YZNZWSD64K3R2TVHCE2=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01H9FK8YZN15KPHHA58XRABRD4=configuraci%C3%B3n-de-eventos-in-app h_01K88DMNP3SKDE93SXGXJXTE0C=advertencia h_01H9FK8YZNJ86KQT59H9RD5CJA=attribution-link-tab h_01H9FK8YZN99ZBQQFBZF26HJZJ=cost-tab h_01H9FK8YZNAJ1XW7TSQWT7PYPW=ad-revenue-tab h_01H9FK8YZQTKN1SFMN9M0CKVYM=permissions-tab" />
