---
title: Integración de Spoteffects con AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Webeffects
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
  created_at: '2017-09-06T14:38:15Z'
  edited_at: '2026-08-12T11:59:35Z'
  id: 115004574426
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/115004574426
---
> **De un vistazo:** Spoteffects, un partner integrado de AppsFlyer, desarrolla y comercializa la solución de software como servicio. La solución permite a los planificadores de medios optimizar sus campañas de TV para tiendas online y sitios web en función de las visitas y conversiones generadas inmediatamente por cada anuncio.

<div id="important" />

> 🚧 **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="setting-up-spoteffects" />

## Configurar Spoteffects

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La ventana de configuración de Spoteffects solo utiliza la pestaña ***integration***.

Para ver una descripción detallada del Partner Configuration Window Header, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a las instalaciones de usuarios de Spoteffects. Usa esta sección para definir el envío de estos postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Selecciona **Eventos atribuidos a cualquier partner u orgánico** para enviar postbacks a Spoteffects para cualquier usuario que descargue la app, o selecciona **Off**.

Haga clic en **Guardar**.

<div id="in-app-event-settings" />

### Configuración de eventos in-app

[![](https://files.readme.io/97da1d47ab9bfa3855d18dcd60f3a263b8a631c477b354dc32486170b7708e96-360002201165.png)](https://files.readme.io/97da1d47ab9bfa3855d18dcd60f3a263b8a631c477b354dc32486170b7708e96-360002201165.png)

En esta sección, puedes asignar tus eventos de AppsFlyer con Spoteffects mediante postbacks.

1. Activa los postbacks de eventos in-app.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento tal y como se define en Spoteffects.  <br />Obtén el ID de evento correspondiente de Spoteffects e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: AppsFlyer envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

Haga clic en **Guardar**.

Una vez que hayas guardado la configuración, AppsFlyer envía los siguientes datos a Spoteffects para cada instalación orgánica y no orgánica:

* ID de dispositivo (IDFA / Google Advertising ID)
* Fuente de medios
* Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para Spoteffects.

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

Los permisos no están disponibles para Spoteffects.

</Accordion>

<div data-zendesk-anchors="h_01H9HWJYD7AZTFXKESY1KHW52S=importante setting-up-spoteffects=configurar-spoteffects h_01H9HWJYD75MTKJBMSZRFAG66Q=configurar-spoteffects h_01H9HWJYD7MAWK9S226YWPZJ8G=integration-tab activate-partner=activar-socio h_01H9HWJYD7X6KEFF3VEZEP4PGM=activar-socio default-postbacks=postbacks-predeterminados h_01H9HWJYD7PW2TCYJRA815YNQE=postbacks-predeterminados inapp-event-settings=configuraci%C3%B3n-de-eventos-in-app h_01H9HWJYD7SK47G91GF9J9Q2ZB=configuraci%C3%B3n-de-eventos-in-app h_01H9HWJYD8RJM9BDX9RKSCC4RY=attribution-link-tab h_01H9HWJYD81VXJPT5D2TKQQN9C=cost-tab h_01H9HWJYD8XBV0V0KDNY955JCT=ad-revenue-tab h_01H9HWJYD8B9AQMVVMT16EH602=permissions-tab" />
