---
title: Configuración de la campaña de Avow GmbH
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-09-13T07:21:40Z'
  edited_at: '2026-08-12T12:13:10Z'
  id: 18523546870929
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/18523546870929
---
> **En resumen:** AVOW GmbH (avow1\_int) es un socio integrado con redes publicitarias y cuentas de agencia, que permite a los anunciantes ejecutar campañas de adquisición de usuarios en dispositivos móviles. Además de la atribución móvil basada en clics, Avow GmbH también ofrece atribución view-through, que los anunciantes pueden grabar con AppsFlyer.

![avow_icon.png](https://files.readme.io/f6dc549357d6c7a6ddaec67752570484289529f85defaf0316ccd925868deab7-18523559800465.png)

## Activar partner

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activar:** En AppsFlyer, en el menú lateral, selecciona**Colaborar**> **Partner Marketplace.**   
   **Para editar:** En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la pestaña **Integración** , selecciona la aplicación para la integración y activa **Activar partner**  .  
    El selector debe estar activado mientras trabajes con el partner.  
    **Nota:** El botón debe estar on <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activado)</Anchor> mientras trabajes con el partner.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Para ver una descripción detallada del Encabezado de la ventana de configuración de partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

## Configuración de Avow GmbH

La integración con Avow GmbH admite la atribución click-through y view-through. La ventana de configuración incluye las siguientes pestañas: Integración, Enlace de atribución, Costo, Ingresos por publicidad y Permisos. Para Avow GmbH, las pestañas disponibles son Integración, Enlace de atribución y Permisos.

> 📘 **Nota**
>
> * Algunas configuraciones cambian para dispositivos iOS y Android
> * Aprende más sobre cómo <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">configurar integraciones de partners</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña **Integración** incluye una serie de secciones, como se describe a continuación.

#### Activar partner

Para configurar la integración, primero debes <Anchor target="_blank" href="/marketers/es/docs/amazon-ads-campaign-configuration#activar-socio">activar</Anchor> el selector **Activar partner**. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">activación y desactivación de integraciones de partners</Anchor>.

#### Privacidad Avanzada

Solo para aplicaciones de iOS: Tu control sobre los datos compartidos con el partner a través de postbacks y <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">reportes</Anchor> depende del estado del selector de **Privacidad avanzada (para iOS 14.5+ y posteriores)**:

| Privacidad avanzada: activada | Privacidad avanzada: desactivada |
| --- | --- |
| Los postbacks se envían solo para eventos atribuidos al partner | Los postbacks se envían según tu configuración:<ul><li>**Todas las fuentes de medios, incluidas las orgánicas**</li><li>**Solo este partner**</li></ul> |
| Los postbacks se envían de acuerdo con la <Anchor target="_blank" href="/partners/es/docs/advanced-privacy-guide-postback-macros-for-ad-networks">plantilla de Privacidad avanzada</Anchor> |  |
| <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Los datos agregados y anónimos</Anchor> se comparten con el partner, lo que significa que no se comparten datos a nivel de usuario (ID de dispositivo). |  |

#### Configuración general

**Token**

Agrega el token de verificación proporcionado por el Especialista AVOW (AM/BDM).

#### Atribución de instalación.

Para atribuir instalaciones de visualización a través de Avow GmbH, activa **Instalar atribución view-through**. El control deslizante de view-through está disponible en la pestaña del enlace de atribución (descrito a continuación).

#### Postbacks predeterminados

Los postbacks para instalaciones e instalaciones rechazadas se envían únicamente a este partner.

#### Configuración de eventos in-app

**Token**

Agrega el token de verificación proporcionado por el Especialista AVOW (AM/BDM).

#### Postbacks de eventos in-app

Configura el mapeo de eventos in-app+ con eventos de Avow GmbH, enviados a través de postbacks:

1. Activa **Postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista. En la siguiente tabla se describen los campos que debes completar:

| Nombre de parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos de servidor a servidor.<br />**Consejo**: ¿No ves el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a comprobarlo.</li><li>Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Leer más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados.</Anchor></li></ul> |
| **Asignado al evento del partner** | El ID o nombre único de cada evento, tal y como lo defina el partner. Existen varias configuraciones de asignación:<ul><li>**Campo de texto:** obtén el ID del evento correspondiente del partner.</li><li>**Cuadro desplegable:** selecciona el evento de AppsFlyer predefinido más adecuado.</li><li>**Tal como está**: envía los eventos tal como están, sin asignación de nombres.</li></ul> |
| **Para usuarios de** | **Solo para este partner:** Los postbacks de eventos in-app se envían solo para eventos atribuidos a este partner, es decir, el usuario que lo realizó vino de este socio. |
| **Incluyendo** | <ul><li>**Sin datos (predeterminado)**: envía solo el evento en sí sin los valores del evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento).</li><li>**Valores sin ingresos**: envía todos los parámetros **excluyendo** el valor de ingresos.</li></ul> |

3. [Opcional] Haz clic en el icono **Agregar condición** <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer las condiciones</Anchor> de un evento.
4. Establece la **ventana de postback de eventos in-app**, si es necesario (lee más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app"> configuración de la ventana de postback de eventos in-app</Anchor>).
5. Haz clic en **Guardar integración**.
6. [Opcional] Después de guardar la integración, desde la página de configuración, puedes integrar más de tus aplicaciones con el partner:
   1. En la esquina superior izquierda, debajo del nombre del socio, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
   2. Selecciona una aplicación diferente en la lista desplegable.
   3. Repite los <Anchor target="_blank" href="/marketers/es/docs/amazon-ads-campaign-configuration#integration-tab">pasos de integración</Anchor> para la aplicación seleccionada.

> 📘 **Nota**
>
> Solo para aplicaciones de iOS: Tu control sobre los datos compartidos con el partner a través de postbacks y <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">reportes</Anchor> depende del **estado del selector <Anchor target="_blank" href="/marketers/es/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">Privacidad avanzada (para iOS 14.5+ y posteriores)</Anchor>**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para atribuir campañas específicas, conjuntos de anuncios o anuncios individuales, tanto para campañas de UA como de retargeting. Puedes usar un enlace de plataforma única o <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>. <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Obtén más información sobre la estructura y los parámetros del enlace de atribución</Anchor>. **Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costo">

Avow GmbH no dispone de datos sobre el costo.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos por publicidad">

Avow GmbH no dispone de ingresos por publicidad.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Selecciona qué permisos otorgar a Avow GmbH para acceder a tus datos y realizar diversas acciones.

> 📘 **Nota**
>
> * Cuando la integración se <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">desactiva</Anchor> mientras el selector Permisos aún está activado, se siguen otorgando permisos.
> * Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">concesión de permisos</Anchor>.

</Accordion>

<div data-zendesk-anchors="activate-partner=activar-partner 01H88VAJH3B5ESK12D3ATMMVZ8=activar-partner setting-up-amazon-dsp-integration=configuraci%C3%B3n-de-avow-gmbh 01H88VAJH3VENKYVRQY5RXN63P=configuraci%C3%B3n-de-avow-gmbh 01H88VAJH3BYZSXQGGZZJQ9N0C=nota 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=activar-partner-1 01H88VAJH34GP7FK1KTJGRDPM7=activar-partner-1 advanced-privacy=privacidad-avanzada 01H88VAJH3G5FAR7RRNDEPNGME=privacidad-avanzada general-settings=configuraci%C3%B3n-general 01H88VAJH3F2FJK5YP3M2V7RWD=configuraci%C3%B3n-general install-attribution=atribuci%C3%B3n-de-instalaci%C3%B3n h_01HA6PNN6RJYTNXRAS3M9EA4M4=atribuci%C3%B3n-de-instalaci%C3%B3n default-postbacks=postbacks-predeterminados 01H88VAJH3WE9Z0971WMBRBJRS=postbacks-predeterminados inapp-event-settings=configuraci%C3%B3n-de-eventos-in-app h_01HA79D908WB6G9FFDKDJNVHEM=configuraci%C3%B3n-de-eventos-in-app inapp-event-postbacks=postbacks-de-eventos-in-app 01H88VAJH3AS37MVF75GANWX4B=postbacks-de-eventos-in-app 01H88VAJH36MYZ9W1YPWA92Z1Z=nota-1 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=nota-2" />
