---
title: Integración de GameAnalytics con AppsFlyer
metadata:
  keywords:
    - GameAnalytics
    - integrated partner
    - Advertisers
    - Ad Networks
    - game
    - game analytics
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
  created_at: '2015-12-24T11:42:56Z'
  edited_at: '2026-08-12T11:58:51Z'
  id: 207447143
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/207447143
---
> **Resumen:** Game Analytics, un partner integrado de AppsFlyer, es una herramienta gratuita y potente que ayuda a los desarrolladores a entender el comportamiento de los jugadores para mejorar el engagement, reducir el abandono y perfeccionar la monetización. Ayuda a visualizar los KPI principales de juegos en una sola vista práctica y ofrece benchmarking in-game para ver cómo se comparan tus métricas con las de más de 14.000 títulos similares.

Solo se tarda unos minutos en configurarlo y es totalmente gratuito: ¡sin límites de uso ni funciones premium ocultas! Si prefieres ver la plataforma en acción antes de integrarla con tu título, solo tienes que registrarte para ver un juego de demo con datos precargados.

La plataforma cuenta con la confianza de más de 40.000 desarrolladores de juegos de todo el mundo, desde indies hasta estudios de renombre mundial, y procesa más de cinco mil millones de eventos únicos cada día en más de 2+ mil millones de dispositivos. GameAnalytics está ampliamente integrado, con SDK para los principales motores de juego y plataformas. Puedes registrarte gratis hoy mismo en https://gameanalytics.com/

<div id="important" />

> 🚧 **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="setting-up-gameanalytics" />

## Configuración de GameAnalytics

**Requisito previo:** Antes de configurar la integración, asegúrate de [ponerte en contacto con el partner](#) y abrir una cuenta con ellos. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación:

La ventana de configuración de Game Analytics solo utiliza la pestaña ***integración***.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, tendrás que activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

**Clave de juego**

Game Analytics se conecta con AppsFlyer mediante una clave de juego única. Si aún no la tienes, debes obtenerla de Game Analytics para continuar con la integración.

<Image align="center" alt="Game_Analytics_msc_new_2.png" src="https://files.readme.io/0c629a74c16d6d8a861ee3ec344de68516a6224e9d6f5afb4b7d89fe78baa49f-360002199865.png" />

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a las instalaciones de usuarios de Game Analytics. Usa esta sección para definir el envío de estos postbacks.

<Image align="center" alt="Swrve_msc_new_4.png" src="https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png" />

Selecciona **Eventos atribuidos a cualquier partner u orgánico** para enviar postbacks de cualquier usuario que descargue la app a Game Analytics, o selecciona **Off**.

<div id="in-app-event-settings" />

### Configuración de eventos in-app

<Image align="center" alt="" src="https://files.readme.io/64dd102e95aacda70cb8c0cde471c5c31d6b744543089a2d00a1ab1640fbb1c3-360002219789.png" />

En esta sección puedes asignar tus eventos de AppsFlyer a Game Analytics mediante postbacks.

1. Vuelve a introducir la Game Key.
2. Activa los postbacks de eventos in-app.
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
4. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
5. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK integrado con tu aplicación o desde eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento tal como se define del lado de Game Analytics.  <br />Obtén el ID de evento correspondiente de Game Analytics e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: AppsFlyer envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

Haga clic en **Guardar**.

Una vez guardada esta configuración, AppsFlyer empieza a enviar los siguientes datos a Game Analytics para cada instalación no orgánica:

* game\_key
* Fuente de medios
* Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para Game Analytics.

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

Los permisos no están disponibles para Game Analytics.

</Accordion>

<div data-zendesk-anchors="h_01H9FK7ZH27GNEHRZ5KKVH5CHY=importante setting-up-gameanalytics=configuraci%C3%B3n-de-gameanalytics h_01H9FK7ZH24E9AD7Z0J94NS0JJ=configuraci%C3%B3n-de-gameanalytics h_01H9FK7ZH3VPBE965Z8MCVXSMQ=integration-tab activate-partner=activar-socio h_01H9FK7ZH3D2H5AWW0DMBQP9R3=activar-socio general-settings=configuraci%C3%B3n-general h_01H9FK7ZH3E32TT8EGAYWPRWBE=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01H9FK7ZH3P0HSQGR2409BFA2F=postbacks-predeterminados inapp-event-settings=configuraci%C3%B3n-de-eventos-in-app h_01H9FK7ZH366RDSY36QVVWJMJN=configuraci%C3%B3n-de-eventos-in-app h_01H9FK7ZH39J4Q7W5XSFZAEZWH=attribution-link-tab h_01H9FK7ZH37FQ6RN80E90TH4K9=cost-tab h_01H9FK7ZH3GE3G69AA03KJK499=ad-revenue-tab h_01H9FK7ZH3RQJQPAYSZBR208H7=permissions-tab" />
