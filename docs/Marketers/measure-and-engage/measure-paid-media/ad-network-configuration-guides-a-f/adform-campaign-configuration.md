---
title: Configuración de la campaña de Adform
metadata:
  keywords:
    - adform
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
  created_at: '2016-05-01T07:23:12Z'
  edited_at: '2026-08-12T12:12:38Z'
  id: 208641516
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/208641516
---
> **Descripción general:** Adform, un partner integrado de ad network de AppsFlyer, proporciona tecnologías abiertas y transparentes que conectan a anunciantes y agencias con publisher para habilitar la publicidad digital en todos los dispositivos. Además de la atribución móvil basada en clics, Adform también ofrece la atribución view-through, que puedes registrar con AppsFlyer.

<div id="setting-up-adform" />

## Configuración de Adform

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con el partner.  
    Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación. Para ver una descripción detallada del Encabezado de la ventana de configuración de partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

La ventana de configuración de Adform incluye 2 pestañas activas: **Integración** y **Enlace de atribución**. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="tip" />

> 👍 **Consejo**
>
> * El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">Configuración general</Anchor> en la pestaña de Integración es **obligatorio** para todos los partners.
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="note" />

> 📘 **Nota:**
>
> Como red de TODAS las instalaciones, Adform prefiere recibir postbacks de todas las nuevas instalaciones de tu app desde CUALQUIER fuente, incluida la orgánica. Se recomienda seleccionar **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a Adform.

<div id="general-settings" />

### Configuración general

**ID de tracking del cliente**

Adform se conecta con AppsFlyer a través de un ID de tracking del cliente único. Si aún no lo tienes, debes obtenerlo de Adform para continuar con la integración.

![adform_msc_new_2.png](https://files.readme.io/d3d72b295a6d3bdc7f097128a6399bd4cd60309118750b4e2217a2b01ca5362a-360002140925.png)

**Habilitar la atribución por impresiones**

Cambia esta opción a ON si quieres atribuir las instalaciones view-through de Adform. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a Adform tras las instalaciones y los re-engagement de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos procedentes solo de usuarios atribuidos a Adform.  
Selecciona **Eventos atribuidos a cualquier partner u orgánico** para que toda tu base de usuarios esté disponible para reportarla a Adform.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a Adform mediante postbacks.

1. Vuelve a introducir el Client\_Tracking\_ID y la contraseña.
2. Activa los postbacks de eventos in-app.
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
4. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
5. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define Adform.  <br />Obtén el ID de evento correspondiente de Adform e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Aprende más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

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

No hay permisos que conceder a Adform.

</Accordion>

<div data-zendesk-anchors="setting-up-adform=configuraci%C3%B3n-de-adform h_01HJR630HMJCK05KSJ1P57KJD1=configuraci%C3%B3n-de-adform h_01HJR630HMXT2T93RH2DZ709Z6=consejo h_01HJR630HMT23996KHW0Z2Z9BT=integration-tab activate-partner=activar-socio h_01HJR630HM3QQVARD5YN3WG6D4=activar-socio h_01HJR630HMR742Z6N1HWFGDM4Z=nota general-settings=configuraci%C3%B3n-general h_01HJR630HMYXE1R9WBDBBV5K39=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HJR630HMHMC5WP2F4CYP8GG0=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HJR630HM4XGH1DYSHYH7EPQ4=configuraci%C3%B3n-de-eventos-in-app h_01HJR630HM00A090TQNW6Z11RY=attribution-link-tab h_01HJR630HMP3AE90YEWNVHN19Q=cost-tab h_01HJR630HMSE5DFR6Y4T3TP34C=ad-revenue-tab h_01HJR630HMF4ZJFNX6RAGT8PJA=permissions-tab" />
