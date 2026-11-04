---
title: Integración de Rockerbox con AppsFlyer
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
  created_at: '2020-11-23T14:55:00Z'
  edited_at: '2026-08-12T11:59:28Z'
  id: 360015760757
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/360015760757
---
> **De un vistazo:** Aprende a compartir automáticamente datos de AppsFlyer con Rockerbox, una plataforma de marketing y análisis para aplicaciones móviles y web.

![rockerbox-logo_en-us.png](https://cdn.appsflyer.com/marketplace/static/logo/rockerbox.png)

<div id="important" />

> 🚧 **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="setting-up-rockerbox" />

## Configuración de Rockerbox

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

Este selector debe estar activado mientras trabajes con el partner.  
Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">activación del partner</Anchor>.

<div id="general-settings" />

### Configuración general

**ID de cuenta de Rockerbox**

**Para conectar tu cuenta de Rockerbox con AppsFlyer,** introduce tu ID de cuenta en **ID de cuenta de Rockerbox**.   
Tu ID de cuenta de Rockerbox está disponible en la plataforma de Rockerbox, en **Settings** > **Account** > **General**.

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a Rockerbox tras las instalaciones de los usuarios. Utiliza esta sección para definir la fuente de los usuarios a los que se envían los postbacks para cada evento. Saber más sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#default-postbacks">postbacks predeterminados</Anchor>.

Para enviar postbacks de cualquier usuario que descargue la aplicación a Rockerbox, selecciona **Todas las fuentes de medios, incluidas las orgánicas**.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

![rockerbox-in-app-events_en-us.png](https://files.readme.io/3fc74bb16d6a1222d1d244bbb1083ff247e3315d0fc7060e0ec3e8ad30a07233-360013891517.png)

En esta sección, asignas los eventos de AppsFlyer al partner mediante postbacks. Saber más sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postbacks de eventos in-app.</Anchor>

**Para configurar postbacks de eventos in-app:**

1. Introduce el **ID de cuenta de Rockerbox**.
2. Habilita los **postbacks de eventos in-app.**
3. Haz clic **Agregar evento** para agregar un evento del SDK a la lista.
4. Selecciona el **nombre del evento de SDK** en el menú desplegable.
5. Selecciona la opción requerida en el menú desplegable Enviar ingresos:
   * **Sin valores ni ingresos:** envía solo el evento en sí sin el valor del evento.
   * **Con valores y sin ingresos:** envía todos los parámetros, excepto el valor de ingresos.
   * **Con valores e ingresos**: envía todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento).
6. Para completar la configuración de la integración, haz clic en **Guardar integración**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para este partner.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Los datos de costos no se aplican a la integración con este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por anuncios no se aplican a la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para este partner.

</Accordion>

<div data-zendesk-anchors="h_01H9HWJW82HZ9FR31VHHRBZ3EM=importante setting-up-rockerbox=configuraci%C3%B3n-de-rockerbox h_01H9HWJW83BKP8DSYTV6YGPHK7=configuraci%C3%B3n-de-rockerbox h_01H9HWJW83WDGQKKMM942NPA1S=integration-tab activate-partner=activar-socio h_01H9HWJW83Z4NGT000091AHX0Z=activar-socio general-settings=configuraci%C3%B3n-general h_01H9HWJW832NQBPK2VS6TS1QK7=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01H9HWJW83CGMBADDBP7EJTR9N=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01H9HWJW84H4SDVRNZAG1D6N0D=configuraci%C3%B3n-de-eventos-in-app h_01H9HWJW84G6GXMBTGMHTDPM6R=attribution-link-tab h_01H9HWJW84BZNHN4DRKA33WCVK=cost-tab h_01H9HWJW848DRTKBF3AKR5KYC5=ad-revenue-tab h_01H9HWJW84NTZWKP2FP2WK4FZD=permissions-tab" />
