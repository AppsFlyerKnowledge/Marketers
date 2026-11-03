---
title: Integración de Convertro con AppsFlyer
metadata:
  keywords:
    - Attribution
    - Convertro
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
  created_at: '2015-12-24T11:37:56Z'
  edited_at: '2026-08-12T11:58:43Z'
  id: 207040636
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/207040636
---
> **En resumen:** Convertro, un partner integrado de AppsFlyer, se esfuerza por ser la principal herramienta automatizada para que los profesionales del marketing comprendan realmente el rendimiento de sus decisiones publicitarias y actúen en función de estos insights lo más rápido posible. Han desarrollado una tecnología que no solo recopila información granular sobre el recorrido del cliente hasta la conversión, sino que también es capaz de optimizar científicamente la combinación de marketing y entender automáticamente cómo redistribuir el gasto para maximizar el ROI.

> 🚧 **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

## Configuración de Convertro

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La ventana de configuración de Convertro solo usa la pestaña **Integración**.

Para ver una descripción detallada del Partner Configuration Window Header, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

### Activar socio

En la **primera visita** aquí, deberás activar la opción siguiente. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

### Configuración general

**URL de página, ID del sitio y nombre del cliente**

Convertro se conecta con AppsFlyer mediante una URL de página, un ID del sitio y un nombre del cliente únicos. Si aún no los tienes, debes obtenerlos de Convertro para continuar con la integración o seguir las instrucciones que se indican a continuación.

[![](https://files.readme.io/74a1ea32d0667da1a4fe4797cb83f75639111b24c98f72d2caa721e6911e3015-360002220189.png)](https://files.readme.io/74a1ea32d0667da1a4fe4797cb83f75639111b24c98f72d2caa721e6911e3015-360002220189.png)

### Obtención del «nombre del cliente, URL de la página & ID del sitio» desde la plataforma de Convertro

Para obtener el nombre del cliente, la URL de página y el ID del sitio, inicia sesión en el dashboard de Convertro:

**URL de página:**

[![](https://files.readme.io/f20c2e45146f0874d94dc84c4f61658e15274970f348896a40b2806d3fe540c9-204790263.png)](https://files.readme.io/f20c2e45146f0874d94dc84c4f61658e15274970f348896a40b2806d3fe540c9-204790263.png)

**ID del sitio:**

[![](https://files.readme.io/b60897bea0b640cb393bceecb57c14370b2ba074818160af0a25a53c7a8ce26b-204790283.png)](https://files.readme.io/b60897bea0b640cb393bceecb57c14370b2ba074818160af0a25a53c7a8ce26b-204790283.png)

**Nombre del cliente:**

![](https://files.readme.io/2e5342006bdfff9e3b3c1dffdaed3e9d83ec2fe4c465b7918023a359776cee91-204595606.png)

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a las instalaciones de usuarios de Convertro. Usa esta sección para definir el envío de estos postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Selecciona **Eventos atribuidos a cualquier partner u orgánico** para enviar postbacks de cualquier usuario que descargue la App a Convertro o selecciona **Off**.

Haga clic en **Guardar**.

### Configuración de eventos in-app

[![](https://files.readme.io/5c1d6841c7f8397d797964790c1f200d60a6ab81fe67eb2162b2a5e7c73462d3-360002200405.png)](https://files.readme.io/5c1d6841c7f8397d797964790c1f200d60a6ab81fe67eb2162b2a5e7c73462d3-360002200405.png)

En esta sección, puedes asignar tus eventos de AppsFlyer a Convertro mediante postbacks.

1. Vuelve a introducir el nombre del cliente, el ID del sitio y la URL de página.
2. Activa los Postbacks de eventos in-app con el selector.
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
4. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
5. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define Convertro.  <br />Obtén el ID de evento correspondiente de Convertro y configúralo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: AppsFlyer envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

Haga clic en **Guardar**.

Una vez guardada esta configuración, AppsFlyer empieza a enviar los siguientes datos a Convertro para cada instalación orgánica y no orgánica:

* Parámetros de Convertro
* ID de dispositivo para Android y iOS
* Fuente de medios
* Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.
* Hora del clic
* IP del usuario
* Agente de usuario
* ID de usuario del cliente (opcional, si está configurado)

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para Convertro.

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

Los permisos no están disponibles para Convertro.

</Accordion>

<div data-zendesk-anchors="h_01H9FK64HSFKW54BBRVB3W9ZR0=importante setting-up-convertro=configuraci%C3%B3n-de-convertro h_01H9FK64HS75VDP07DGETASAH7=configuraci%C3%B3n-de-convertro h_01H9FK64HSK1B1Y9BRWP7AN96R=integration-tab activate-partner=activar-socio h_01H9FK64HS7VJWHF1QCWNYVBX8=activar-socio general-settings=configuraci%C3%B3n-general h_01H9FK64HSCAYHB82DZX0JA2ZX=configuraci%C3%B3n-general obtaining-the-client-name-page-url-site-id-from-the-convertro-platform=obtenci%C3%B3n-del-nombre-del-cliente-url-de-la-p%C3%A1gina--id-del-sitio-desde-la-plataforma-de-convertro h_01H9FK64HSKR8N45RXQQC3VEW1=obtenci%C3%B3n-del-nombre-del-cliente-url-de-la-p%C3%A1gina--id-del-sitio-desde-la-plataforma-de-convertro default-postbacks=postbacks-predeterminados h_01H9FK64HTPK69QQ92DJ55RNVM=postbacks-predeterminados inapp-event-settings=configuraci%C3%B3n-de-eventos-in-app h_01H9FK64HTGKXWW0FMN0T445FG=configuraci%C3%B3n-de-eventos-in-app h_01H9FK64HTCM3H0243FVFDY0ET=attribution-link-tab h_01H9FK64HT9JHKBN5W8H16E6CK=cost-tab h_01H9FK64HTSP070RX7ZCYM7KE3=ad-revenue-tab h_01H9FK64HTCXAMY6TR186EE0M9=permissions-tab" />
