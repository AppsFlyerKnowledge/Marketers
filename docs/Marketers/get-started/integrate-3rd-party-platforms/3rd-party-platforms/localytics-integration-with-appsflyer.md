---
title: Integración de Localytics con AppsFlyer
metadata:
  keywords:
    - Localytics
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
  created_at: '2016-07-27T11:09:25Z'
  edited_at: '2026-08-12T11:59:09Z'
  id: 210748626
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/210748626
---
> **En resumen:** Localytics, un partner integrado de AppsFlyer, es una plataforma de marketing y análisis para apps móviles y web. Los análisis de aplicaciones de Localytics proporcionan análisis de retención basados en cohortes, funnels, segmentación de clientes y análisis en tiempo real para identificar grupos de usuarios con las tasas de fidelidad y el valor del ciclo de vida más altos. El marketing de aplicaciones de Localytics ofrece servicios de automatización de marketing para apps al medir el éxito a largo plazo de las campañas de adquisición de clientes y enviar mensajes in-app y push enriquecidos y procesables a los clientes pertinentes cuando pueden tener el mayor impacto.

> 🚧 **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

## Configuración de Localytics

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La ventana de configuración de Localytics incluye 4 pestañas: **Integración, Enlace de atribución, Enriquecimiento de datos** y **Permisos**. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

Para ver una descripción detallada del Partner Configuration Window Header, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

### Activar socio

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

[![](https://files.readme.io/5064c48a0851c34c51b4cfd28e2808a11e6d8d271f1cd735616f6de0d827cea8-360001902809.png)](https://files.readme.io/5064c48a0851c34c51b4cfd28e2808a11e6d8d271f1cd735616f6de0d827cea8-360001902809.png)

### Configuración general

**ID de atribución**

Localytics se conecta con AppsFlyer a través de un ID de atribución único. Si aún no lo tienes, debes obtenerlo de Localytics para continuar con la integración o seguir los pasos que se indican a continuación.

![Localytics_msc_new_3.png](https://files.readme.io/2a51018b2248a855ed5a86207c18d132addf5ab56449f4c9915df2eb754e39ca-360001902869.png)

Obtención de la App Key de Localytics en Localytics

* Inicia sesión en tu Dashboard de Localytics
* Haz clic en **Atribución** en el panel izquierdo
* Selecciona **Atribución de terceros**
* Copia la clave de atribución

[![](https://files.readme.io/dbac1c9beb6d22f4cf8f2ccfbdc0f6a22fec7e6ccad5a52e77c7c32044cab55c-207223506.png)](https://files.readme.io/dbac1c9beb6d22f4cf8f2ccfbdc0f6a22fec7e6ccad5a52e77c7c32044cab55c-207223506.png)

Configura Localytics en el dashboard de AppsFlyer.

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a Localytics tras las instalaciones de los usuarios. Usa esta sección para definir el envío de estos postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Selecciona **Events attributed to any partner or organic** para enviar postbacks a Localytics de cualquier usuario que descargue la aplicación.

Una vez que hayas completado la configuración, AppsFlyer envía los siguientes datos a Localytics por cada instalación orgánica y no orgánica:

* ID de dispositivo (IDFA / Google Advertising ID)
* Fuente de medios
* Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.

Haga clic en **Guardar**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para Localytics.

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

Los permisos no están disponibles para Localytics.

</Accordion>

## Visualización de los datos de atribución en la consola de Localytics

Ve a la pantalla de Attribution Settings de Localytics y activa Third Party Attribution en Localytics para ver los datos de AppsFlyer.

[![](https://files.readme.io/0c171096b9bfd8a559ba8e1a0ad4296559dc050c7b3b52b8987bd9707e44220a-205662666.png)](https://files.readme.io/0c171096b9bfd8a559ba8e1a0ad4296559dc050c7b3b52b8987bd9707e44220a-205662666.png)

[![](https://files.readme.io/53524088099556d72e6e7573f3997bbb55b1a89e38a2f7a74eec1a1632125c72-205663286.png)](https://files.readme.io/53524088099556d72e6e7573f3997bbb55b1a89e38a2f7a74eec1a1632125c72-205663286.png)

<div data-zendesk-anchors="h_01H9FKCBM5W16BYJQ6TH9SSBVC=importante setting-up-localytics=configuraci%C3%B3n-de-localytics h_01H9FKCBM5Z39GPE5772799DB1=configuraci%C3%B3n-de-localytics h_01H9FKCBM5JZ5V4YMB6S24JA6V=integration-tab activate-partner=activar-socio h_01H9FKCBM5PSZZ5FP1G12M9F63=activar-socio general-settings=configuraci%C3%B3n-general h_01H9FKCBM5N4RB5ZSB61W02368=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01H9FKCBM5STZ79NBP3EFYGMB9=postbacks-predeterminados h_01H9FKCBM54S067F1Z51E4FXQD=attribution-link-tab h_01H9FKCBM591RG57Q80JZ7FJWY=cost-tab h_01H9FKCBM5Q8P53V34QRQMS0BS=ad-revenue-tab h_01H9FKCBM5GGXX04JEH3DHNV78=permissions-tab viewing-the-attribution-data-in-the-localytics-console=visualizaci%C3%B3n-de-los-datos-de-atribuci%C3%B3n-en-la-consola-de-localytics h_01H9FKCBM5VBM87C2PHNZVZ4RJ=visualizaci%C3%B3n-de-los-datos-de-atribuci%C3%B3n-en-la-consola-de-localytics" />
