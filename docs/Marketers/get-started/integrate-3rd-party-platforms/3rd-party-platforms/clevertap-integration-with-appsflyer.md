---
title: Integración de CleverTap con AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Clevertap
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
  created_at: '2018-07-12T06:26:58Z'
  edited_at: '2026-08-12T11:58:41Z'
  id: 360001299165
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/360001299165
---
> **De un vistazo:** CleverTap es una nube de retención moderna e integrada que permite a las marcas digitales orientadas al consumidor aumentar la retención de clientes y el valor del ciclo de vida del cliente.

<Image align="center" alt="clevertap-logo.png" src="https://files.readme.io/ee01a7da1ae0c77758e279c47f2f588d90fdb7f52dce51161fce3891cc5fd498-4405112002833.png" width="193px" />

<div id="important" />

> 🚧 **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="setting-up-clevertap" />

## Configuración de CleverTap

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación:

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

Este selector debe estar activado mientras trabajes con el partner.  
Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">activación del partner</Anchor>.

<div id="general-settings" />

### Configuración general

**Token de cuenta**

CleverTap se conecta con AppsFlyer mediante un token de cuenta único, una región, un código de acceso de cuenta y un ID de cuenta. Si aún no los tienes, debes obtenerlos de CleverTap para continuar con la integración o seguir los pasos que se indican a continuación.

<div id="important-1" />

> 🚧 **Importante:**
>
> Para permitir el envío de postbacks a CleverTap, asegúrate de completar **ambos** pasos siguientes:
>
> * Completa al menos **uno** de los siguientes campos: account\_token, account\_passcode o account\_id
> * En el SDK de AppsFlyer, configura el valor del ID de usuario del cliente (<Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid#configuración-del-cuid">iOS, Android</Anchor>). Consulta la [documentación de CleverTap](https://developer.clevertap.com/docs/appsflyer#section-step-2-integration) para obtener directrices sobre qué parámetro se recomienda usar como ID de usuario del cliente. Ten en cuenta que, si el ID de usuario del cliente está vacío, no se enviarán postbacks a CleverTap.

<Image align="center" alt="CleverTap_msc_new_2.png" src="https://files.readme.io/dd3f79fdce7dc4d48605f18021e328754d3e78aae98cb5214466c7489fd29fdf-360002305685.png" />

<div id="obtain-clevertap-account-token" />

### Obtener el token de cuenta de CleverTap

**Para obtener tokens de cuenta de CleverTap:**

1. En el dashboard de CleverTap, ve a **Settings**, en la esquina superior derecha.

   <Image align="center" alt="CleverTap_msc_new_4.png" src="https://files.readme.io/2fd248582c3e267b2eaacfc6bf49068bdd4c6811b066c8286f0059e18d8535ae-360002541969.png" />
   En la parte superior de la vista «Settings», verás el ID de cuenta, el token de cuenta y el código de acceso de tu cuenta de CleverTap junto a «Account ID», «Account token» y «Passcode», respectivamente:

   <Image align="center" alt="CleverTap_msc_new_5.png" src="https://files.readme.io/795086dfc16cdee369b470e0b598b5089fff6469c77d0ccbf929e230d94191c8-360002537945.png" />
2. Para mostrar los valores, haz clic en los iconos de «ojo» junto a cada campo.
3. Copia los valores y pégalos en la página de CleverTap de AppsFlyer.

   <div id="note" />

   > 📘 **Nota:**
   >
   > * La región depende de la URL del dashboard de CleverTap de tu cuenta:
   > * Si la URL de tu cuenta es <Anchor target="_blank" href="https://eu1.dashboard.clevertap.com/">https://eu1.dashboard.clevertap.com</Anchor>, la región es EU1, lo que significa que los datos de la cuenta se alojan en un centro de datos de la UE.
   > * Si la URL de tu cuenta es <Anchor target="_blank" href="https://in1.dashboard.clevertap.com">https://in1.dashboard.clevertap.com</Anchor>, la región es IN1, lo que significa que los datos de la cuenta se alojan en un centro de datos con sede en IN.
   > * Si la URL de tu cuenta es [https://aps3.dashboard.clevertap.com](https://aps3.dashboard.clevertap.com), la región es ID, lo que significa que los datos de la cuenta se alojan en un centro de datos de Indonesia.* La configuración de región distingue entre mayúsculas y minúsculas y debe usarse únicamente con letras mayúsculas. Si usas letras minúsculas, el postback se enviará al servidor predeterminado (EU1).

4. Finaliza la integración según la <Anchor target="_blank" href="https://developer.clevertap.com/docs/appsflyer#section-step-2-integration">documentación de CleverTap</Anchor>.

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a CleverTap tras las instalaciones de los usuarios. Utiliza esta sección para definir la fuente de los usuarios a los cuales se envían los postbacks de cada evento. Saber más sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#default-postbacks">postbacks predeterminados</Anchor>.

<Image align="center" alt="clevertap-default-postbacks_en-us.png" src="https://files.readme.io/58424df9f5e8ba0e30e2390e26e0ecec7fc827baa43f3b812181caa2283dca0a-360014085238.png" />

**Para enviar postbacks de cualquier usuario que descargue la aplicación a CleverTap:** selecciona **Todas las fuentes de medios, incluidas las orgánicas**.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

<Image align="center" alt="clevertap-in-app-events_en-us.png" src="https://files.readme.io/2ccc8a5a62cd601c45647d72caff0d94af814f78d9e1a8ae1548f973ed4c554f-360014005017.png" />

En esta sección, asignas los eventos de AppsFlyer al partner mediante postbacks.  
Saber más sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postbacks de eventos in-app.</Anchor>

**Para configurar postbacks de eventos in-app:**

1. Introduce todos los tokens necesarios.
2. Habilita los **postbacks de eventos in-app.**
3. Haz clic **Agregar evento** para añadir un evento del SDK a la lista.
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

Los datos de costos no se aplican a este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los datos de ingresos por publicidad no se aplican a este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para CleverTap.

</Accordion>

<div id="measure-clevertap-owned-media" />

## Medir los medios propios de CleverTap

Como CleverTap es una plataforma que utiliza correos electrónicos, SMS, notificaciones push, etc. con fines de Automatización de marketing, puedes usar <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">AppsFlyer OneLink</Anchor> como solución para medir los medios propios que se originan en CleverTap.

<div data-zendesk-anchors="h_01H9FK5JT1TM77CAH0JTDCV376=importante setting-up-clevertap=configuraci%C3%B3n-de-clevertap h_01H9FK5JT1ATCHY6WAVB6E2YEW=configuraci%C3%B3n-de-clevertap h_01HKW9C39FKN3QN21NKDS6N3BQ=integration-tab activate-partner=activar-socio h_01H9FK5JT12Z1M6WW3GQQF5QVN=activar-socio general-settings=configuraci%C3%B3n-general h_01H9FK5JT1FMC6JANBP9KBB0V2=configuraci%C3%B3n-general h_01H9FK5JT1MQKT7KWJ3EVNEA1E=importante-1 obtain-clevertap-account-token=obtener-el-token-de-cuenta-de-clevertap h_01H9FK5JT1RVJ1V0CGXSH1XZPM=obtener-el-token-de-cuenta-de-clevertap h_01H9FK5JT2QV9CKSZ1N3S4WTGE=nota default-postbacks=postbacks-predeterminados h_01H9FK5JT2CE0WQ9HAGVGAQA5B=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01H9FK5JT2YS7G5WDD4F5MPYVZ=configuraci%C3%B3n-de-eventos-in-app h_01H9FK5JT2939VDXQCDDG7MZ0R=attribution-link-tab h_01H9FK5JT2AEDDCD11K77WJHBX=cost-tab h_01H9FK5JT2WYWRGZAS1HBYYBSJ=ad-revenue-tab h_01H9FK5JT2FD6WN3Z1RET108JZ=permissions-tab measure-clevertap-owned-media=medir-los-medios-propios-de-clevertap h_01H9FK5JT2AZTT5936DD88ZZV3=medir-los-medios-propios-de-clevertap" />
