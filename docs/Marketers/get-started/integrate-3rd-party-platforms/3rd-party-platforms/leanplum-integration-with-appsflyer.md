---
title: Integración de Leanplum con AppsFlyer
metadata:
  keywords:
    - Leanplum
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
  created_at: '2016-08-08T13:41:18Z'
  edited_at: '2026-08-12T11:59:04Z'
  id: 211487846
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/211487846
---
> **De un vistazo:** Leanplum, partner integrado de AppsFlyer, es una plataforma de marketing móvil diseñada para la acción inteligente. Su solución integrada ofrece engagement a través de los mensajes y la experiencia in-app. Leanplum ofrece Mensajes, automatización, edición de apps, personalización, pruebas A/B y analíticas.

<div id="important" />

> 🚧 **Dos puntos (:)**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="setting-up-leanplum" />

## Configuración de Leanplum

Los clientes de Leanplum pueden integrarse con AppsFlyer enviando a Leanplum un postback que contenga información del publisher. Esto te permite ver estos datos en las analíticas de Leanplum, así como usarlos para el targeting en pruebas A/B o campañas de marketing, mediante el menú de targeting y segmentación de Leanplum.

Antes de activar la integración con AppsFlyer, primero debes confirmar que tu integración de Leanplum utiliza el mismo ID de dispositivo que AppsFlyer. Esto es importante, ya que Leanplum hace coincidir la instalación del usuario con el postback mediante el ID de dispositivo, por lo que, si no coinciden, Leanplum no puede reportar los datos.

De forma predeterminada, Leanplum recopila el IDFV para iOS y el hash MD5 de la dirección MAC para Android, pero esto puede cambiarse fácilmente a IDFA para iOS y GAID para Android con una sola línea de código. Para obtener información sobre cómo cambiar el formato del ID de dispositivo para Android e iOS, haz clic <Anchor target="_blank" href="https://docs.leanplum.com/docs/which-device-id-format-should-i-use">aquí</Anchor>.

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Configurar la integración de ASA**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La ventana de configuración de Leanplum solo utiliza la pestaña **Integration**.

Para ver una descripción detallada del Partner Configuration Window Header, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, tendrás que activar el botón ***Activate Partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

**ID de la app y clave de cliente**

Leanplum se conecta con AppsFlyer mediante un ID de la app y una clave de cliente únicos. Si aún no los tienes, debes obtenerlos de Leanplum para continuar con la integración o seguir los pasos que se indican a continuación.

<Image align="center" alt="Leanplum_msc_new_3.png" src="https://files.readme.io/0ef9adb16568192e922b33688a0525a3e61bc0f18dfc63e3717390adc34a66c4-360001904209.png" />

**Envío de IDFA o IDFV**

Si la opción está activa, el IDFV se envía en un postback. Si no se encuentra ningún IDFV, se envía el IDFA como alternativa.

Si la opción está inactiva, el IDFA se envía en un postback. Si no se encuentra ningún IDFA, se envía el IDFV como alternativa.

Si no hay ninguno disponible, no se envía ningún postback.

<div id="obtaining-the-app-id-and-client-key" />

### Obtener el ID de la app y la clave de cliente

Haz clic en tu nombre en la parte superior derecha de la pantalla y selecciona **App Settings**

<Image align="center" alt="" src="https://files.readme.io/fcb9bb4fab1eec1db130904c2c4856529f58582bd8c9c04f08200ed82c0fcb80-206117303.png" />

Selecciona una aplicación y haz clic en **Keys & Settings**

<Image align="center" alt="" src="https://files.readme.io/5608bddb2c31b1569e3d2e262946e239f3e637e5ac5d95bc24a03c3ff0d8d763-206117323.png" />

<Image align="center" alt="" src="https://files.readme.io/cd638732b197f03c6194b8bae7b8f726a6e4c16661702fdad48054a35ce333e5-206117343.png" />

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a las instalaciones de usuarios de Leanplum. Usa esta sección para definir el envío de estos postbacks.

<Image align="center" alt="Swrve_msc_new_4.png" src="https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png" />

Selecciona **Eventos atribuidos a cualquier partner u orgánico** para enviar postbacks a Leanplum para cualquier usuario que descargue la aplicación.

Haga clic en **Guardar**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para Leanplum.

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

Los permisos no están disponibles para Leanplum.

</Accordion>

<div id="viewing-user-attribution-data-in-leanplum" />

## Visualización de datos de atribución de usuarios en Leanplum

Una vez que hayas configurado la integración entre Leanplum y AppsFlyer, podrás acceder a la información mediante el menú de targeting y segmentación de Leanplum:

<Image align="center" alt="" src="https://files.readme.io/5685cfe357930bd57611365d7f47fff1608a8e7c345110070763af26374e01bc-206117523.png" />

Este menú está disponible en las secciones Analytics, Messages, A/B Tests y Users de la plataforma Leanplum. Puedes filtrar, agrupar y crear cohortes con estos datos en Analytics, filtrar por estos datos en la sección Users y hacer targeting con estos datos en Analytics y A/B Tests.

<div data-zendesk-anchors="h_01H9FKB51R253NAXWEKSYVRZ3P=dos-puntos- setting-up-leanplum=configuraci%C3%B3n-de-leanplum h_01H9FKB51RA35X0G19ZPN2KAQ7=configuraci%C3%B3n-de-leanplum h_01H9FKB51VVVS5C4WEQ4FKHH4H=integration-tab activate-partner=activar-socio h_01H9FKB51VY7QASRV8XW8KRZK1=activar-socio general-settings=configuraci%C3%B3n-general h_01H9FKB51VA8A6XZYM3W6AVNMH=configuraci%C3%B3n-general obtaining-the-app-id-and-client-key=obtener-el-id-de-la-app-y-la-clave-de-cliente h_01H9FKB51VFGCW21AG0BYWGFXZ=obtener-el-id-de-la-app-y-la-clave-de-cliente default-postbacks=postbacks-predeterminados h_01H9FKB51V63GPAS3R1GBWNTWR=postbacks-predeterminados h_01H9FKB51VR8160P1RQK994DGZ=attribution-link-tab h_01H9FKB51VEJWHZXKENFASR9NG=cost-tab h_01H9FKB51V7C44MGTWR3RNX4D8=ad-revenue-tab h_01H9FKB51VY9V478W297NB58EM=permissions-tab viewing-user-attribution-data-in-leanplum=visualizaci%C3%B3n-de-datos-de-atribuci%C3%B3n-de-usuarios-en-leanplum h_01H9FKB51VHAYS1STK6GQE4515=visualizaci%C3%B3n-de-datos-de-atribuci%C3%B3n-de-usuarios-en-leanplum" />
