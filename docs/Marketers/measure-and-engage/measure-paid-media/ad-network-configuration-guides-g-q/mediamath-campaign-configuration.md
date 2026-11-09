---
title: Configuración de la campaña de MediaMath
metadata:
  keywords:
    - Advertisers
    - MediaMath
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-10-06T14:55:35Z'
  edited_at: '2026-08-12T12:14:29Z'
  id: 214956583
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/214956583
---
> **De un vistazo:** MediaMath, partner integrado de AppsFlyer, se especializa en tecnología de marketing programático, con plataformas de gestión de datos y DSP omnicanal. Además de la atribución móvil basada en clics, MediaMath también ofrece retargeting y atribución view-through, que puedes registrar con AppsFlyer.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mediamath.png" />

<div id="setting-up-mediamath" />

## Configuración de MediaMath

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con el partner.  
    Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación. Para ver una descripción detallada del Encabezado de la ventana de configuración de partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

Al habilitar **Uso compartido avanzado de datos**, AppsFlyer podrá enviar a MediaMath la fuente atribuida y los datos del referente para los postbacks de instalación. El interruptor «CB\_AD» hace lo mismo con los eventos in-app.

La ventana de configuración de MediaMath incluye 3 pestañas activas: Integración, enlace de atribución y permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

Para ver una descripción detallada del Partner Configuration Window Header, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="tip" />

> 👍 **Consejo**
>
> * El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">Configuración general</Anchor> en la pestaña de Integración es **obligatorio para todos los partners**.
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="note" />

> 📘 **Nota:**
>
> Como red de TODAS las instalaciones, MediaMath prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluidas las orgánicas. Para hacerlo, selecciona **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a MediaMath.

<div id="general-settings" />

### Configuración general

**ID de socio**

MediaMath se conecta con AppsFlyer mediante un ID de anunciante y un ID de píxel únicos. Si aún no tienes el ID de anunciante y el ID de píxel, debes obtenerlos de MediaMath para continuar con la integración.

**Compartición avanzada de datos**

Activa esta opción si quieres que AppsFlyer envíe información adicional a MediaMath.

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir las instalaciones view-through de MediaMath. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a MediaMath después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para los eventos procedentes únicamente de usuarios atribuidos a MediaMath.  
Selecciona **Eventos atribuidos a cualquier partner u orgánicos** para que toda tu base de usuarios esté disponible para ser reportada a MediaMath.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a MediaMath mediante postbacks.

1. Vuelve a introducir el ID de anunciante.
2. Activa los postbacks de eventos in-app.
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
4. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
5. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK integrado con tu aplicación o desde eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o el ID únicos de cada evento, según lo definido por MediaMath.  <br />Obtén el ID de evento correspondiente de MediaMath e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Cuando está marcada**: se envían todos los parámetros incluyendo el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o un <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

MediaMath no admite datos de costo.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

MediaMath no admite ingresos por anuncios.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a MediaMath, tanto si el partner actúa como ad network, agencia o incluso ambas cosas. Ten en cuenta que, aunque la atribución esté deshabilitada para MediaMath, la pestaña de permisos está activa y puedes otorgarle el control a MediaMath.

<div id="ad-network-permissions" />

### Permisos de ad network

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos***: solo a los datos de ingresos atribuidos al partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-mediamath=configuraci%C3%B3n-de-mediamath h_01HKW2X0DS3WRS3N268E2SH2HT=configuraci%C3%B3n-de-mediamath h_01HKW2X0DSW1P1RZGK26RS20QM=consejo h_01HKW2X0DSSQVB3MSSEK1HB7V7=integration-tab activate-partner=activar-socio h_01HKW2X0DS26H7GFZKBY3VJV59=activar-socio h_01HKW2X0DSBYTBEDCM4YCPHEPA=nota general-settings=configuraci%C3%B3n-general h_01HKW2X0DSQWZY0KPS42RQKCFB=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKW2X0DSAM76C6S22VMVTPGZ=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW2X0DSS1TN1B4GWP8SHY6X=configuraci%C3%B3n-de-eventos-in-app h_01HKW2X0DSWT4VW9J5DMYZ2DPJ=attribution-link-tab h_01HKW2X0DS69CD1QKF8CZM3MN4=cost-tab h_01HKW2X0DS4B391FNY0W6W9YAK=ad-revenue-tab h_01HKW2X0DTC7BR20T5FPP8PW0X=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKW2X0DTFX6A7X3F67WW0XNW=permisos-de-ad-network" />
