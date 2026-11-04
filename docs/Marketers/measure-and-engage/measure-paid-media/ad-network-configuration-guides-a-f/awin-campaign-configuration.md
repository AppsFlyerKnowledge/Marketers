---
title: Configuración de la campaña de Awin
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-09-13T11:50:38Z'
  edited_at: '2026-09-11T00:23:09Z'
  id: 18532554968849
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/18532554968849
---
> **En resumen:** Awin (affiliatewindow\_int) es un partner integrado que permite a los anunciantes ejecutar campañas de UA y retargeting. La plataforma de marketing de Awin ayuda a conectar comerciantes (anunciantes) con afiliados (publishers).

![awin icon.png](https://files.readme.io/2a7f22084586fec820c0bfab7f3a256259c43d37f14d6fed8e8db3d2e9905947-18533392495377.png)

<div id="activate-partner" />

## Activar el socio

**Requisito previo:** una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace** .  
   (**Para editar una integración existente:** ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el selector **Activate partner**.   
   **Nota:** el selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="setting-up-awin" />

## Configuración de Awin

La integración con Awin soporta la atribución click-through.

La ventana de configuración incluye las siguientes pestañas: Integración, Enlace de atribución, Costo, Ingreso publicitario y Permisos. Para Awin, las pestañas disponibles son Integración, Enlace de atribución y Permisos.

<div id="note" />

> 📘 **Nota**
>
> * Algunas configuraciones difieren para dispositivos iOS y Android
> * Aprende más sobre cómo <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">configurar integraciones de partners</Anchor>

<div id="prerequisite" />

### Requisito previo

Antes de configurar la integración, asegúrate de implementar los parámetros requeridos "commission group" en el SDK, como se especifica en la <Anchor target="_blank" href="https://wiki.awin.com/index.php/Awin_AppsFlyer">documentación de Awin</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña **Integración** incluye una serie de secciones, como se describe a continuación.

<div id="activate-partner-1" />

#### Activar el socio

Para configurar la integración, primero debes <Anchor target="_blank" href="/marketers/es/docs/amazon-ads-campaign-configuration#activar-socio">activar</Anchor> el selector **Activar partner**. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">activación y desactivación de integraciones de partners</Anchor>. Para obtener más información, puedes consultar la <Anchor target="_blank" href="https://developer.awin.com/docs/appsflyer">página de integración de Awin</Anchor>.

<div id="advanced-privacy" />

#### Privacidad avanzada

Solo para aplicaciones de iOS: Tu control sobre los datos compartidos con el partner a través de postbacks y <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">reportes</Anchor> depende del estado del selector de **Privacidad avanzada (para iOS 14.5+ y posteriores)**:

| Privacidad avanzada: activada | Privacidad avanzada: desactivada |
| --- | --- |
| Los postbacks se envían solo para eventos atribuidos al partner | Los postbacks se envían según tu configuración:<ul><li>**Todas las fuentes de medios, incluidas las orgánicas**</li><li>**Solo este partner**</li></ul> |
| Los postbacks se envían de acuerdo con la <Anchor target="_blank" href="/partners/es/docs/advanced-privacy-guide-postback-macros-for-ad-networks">plantilla de Privacidad avanzada</Anchor> |  |
| <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Los datos agregados y anónimos</Anchor> se comparten con el partner, lo que significa que no se comparten datos a nivel de usuario (ID de dispositivo). |  |

<div id="general-settings" />

#### Configuración general

**ID de anunciante de Awin**

Agrega tu ID de comerciante de Awin.

<div id="note-1" />

> 📘 **Advertencia**
>
> Un ID de anunciante identifica tu cuenta de anunciante en el lado del partner y es necesario para la atribución y los postbacks de AppsFlyer. El ID debe aparecer en el enlace de atribución.

<div id="default-postbacks" />

#### Postbacks predeterminados

Los postbacks de instalación se envían únicamente a este partner.

<div id="in-app-event-settings" />

#### Configuración de eventos in-app

**ID de anunciante de Awin**

Agrega tu ID de comerciante de Awin.

<div id="in-app-event-postbacks" />

#### Postbacks de eventos in-app

Configura el mapeo de eventos in-app con eventos de Awin, enviados a través de postbacks:

1. Activa **Postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista. En la siguiente tabla se describen los campos que debes completar:

| Nombre de parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos de servidor a servidor.<br />**Consejo**: ¿No ves el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Leer más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados.</Anchor></li></ul> |
| **Asignado al evento de socio** | El ID o nombre único de cada evento, tal y como lo defina el partner. Existen varias configuraciones de asignación:<ul><li>**Campo de texto:** obtén el ID del evento correspondiente del partner.</li><li>**Cuadro desplegable:** selecciona el evento de AppsFlyer predefinido más adecuado.</li><li>**Tal como está**: envía los eventos tal como están, sin asignación de nombres.</li></ul> |
| **Para usuarios de** | **Solo para este partner:** Puedes finalizar las postbacks de eventos in-app solo cuando el evento se atribuye a este partner, es decir, el usuario que lo realizó proviene de este partner. |
| **Incluyendo** | <ul><li>**Sin datos (predeterminado)**: envía solo el evento en sí sin los valores del evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento).</li><li>**Valores sin ingresos**: envía todos los parámetros **excluyendo** el valor de ingresos.</li></ul> |

3. [Opcional] Haz clic en el icono **Agregar condición** <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer las condiciones</Anchor> de un evento.
4. Establece la **ventana de postback de eventos in-app**, si es necesario (lee más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app"> configuración de la ventana de postback de eventos in-app</Anchor>).
5. Haz clic en **Guardar integración**.
6. [Opcional] Después de guardar la integración, desde la página de configuración, puedes integrar más de tus aplicaciones con el partner:
   1. En la esquina superior izquierda, debajo del nombre del socio, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
   2. Selecciona una aplicación diferente en la lista desplegable.
   3. Repite los <Anchor target="_blank" href="/marketers/es/docs/amazon-ads-campaign-configuration#integration-tab">pasos de integración</Anchor> para la aplicación seleccionada.

<div id="note-2" />

> 📘 **Nota**
>
> Solo para aplicaciones de iOS: Tu control sobre los datos compartidos con el partner a través de postbacks y <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">reportes</Anchor> depende del **estado del selector <Anchor target="_blank" href="/marketers/es/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">Privacidad avanzada (para iOS 14.5+ y posteriores)</Anchor>**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para atribuir campañas específicas, conjuntos de anuncios o anuncios individuales, tanto para campañas de UA como de retargeting. Puedes usar un enlace de plataforma única o <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>. <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Obtén más información sobre la estructura y los parámetros del enlace de atribución</Anchor>. **Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de Costo">

Los datos sobre costos no están disponibles para Awin.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos por publicidad">

Los ingresos por publicidad no están disponibles para Awin.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Selecciona qué permisos otorgar a Awin para acceder a tus datos y realizar varias acciones.

<div id="note-3" />

> 📘 **Nota**
>
> * Cuando la integración se <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">desactiva</Anchor> mientras el selector Permisos aún está activado, se siguen otorgando permisos.
> * Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">concesión de permisos</Anchor>.

</Accordion>

<div id="deep-linking-and-deferred-deep-linking-using-onelink" />

## Deep linking y deep linking diferido mediante OneLink

AWIN envuelve cualquier enlace utilizado en su plataforma para que puedan proporcionar datos analíticos a sus clientes. Esto significa que el enlace será redireccionado al sitio de AWIN antes de enviar a los usuarios a su destino final. <Anchor target="_blank" href="https://www.appsflyer.com/blog/mobile-marketing/universal-links-app-links/#:~:text=%231%3A%20Link%20wrapping%20and%20Universal%20Links">Saber más sobre la envoltura de enlaces</Anchor>.  
AWIN como plataforma soporta un esquema URI pero **no soporta** el manejo de los enlaces universales de iOS y los métodos de enlace de aplicaciones de Android de deep linking. Esto se aplica a cualquier enlace utilizado dentro de AWIN.

Para realizar un deep link con OneLink a través de AWIN:

* <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">Configura tu URL de OneLink con un esquema de URI</Anchor>

<div id="note-4" />

> 📘 **Nota**
>
> Para las aplicaciones iOS, utiliza el parámetro `af_force_deeplink=true`en la URL de OneLink para activar el <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">esquema URI</Anchor> de deep link.

<div data-zendesk-anchors="activate-partner=activar-el-socio 01H88VAJH3B5ESK12D3ATMMVZ8=activar-el-socio setting-up-amazon-dsp-integration=configuraci%C3%B3n-de-awin 01H88VAJH3VENKYVRQY5RXN63P=configuraci%C3%B3n-de-awin 01H88VAJH3BYZSXQGGZZJQ9N0C=nota prerequisite=requisito-previo h_01HFPEEW4FXS9AFQTTEF2ZBDZW=requisito-previo 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=activar-el-socio-1 01H88VAJH34GP7FK1KTJGRDPM7=activar-el-socio-1 advanced-privacy=privacidad-avanzada 01H88VAJH3G5FAR7RRNDEPNGME=privacidad-avanzada general-settings=configuraci%C3%B3n-general 01H88VAJH3F2FJK5YP3M2V7RWD=configuraci%C3%B3n-general h_01K4VVB00RYB0XRANWQ29M6P36=advertencia default-postbacks=postbacks-predeterminados 01H88VAJH3WE9Z0971WMBRBJRS=postbacks-predeterminados inapp-event-settings=configuraci%C3%B3n-de-eventos-in-app h_01HA77JYAR06HA5FZGSRQJATHF=configuraci%C3%B3n-de-eventos-in-app inapp-event-postbacks=postbacks-de-eventos-in-app 01H88VAJH3AS37MVF75GANWX4B=postbacks-de-eventos-in-app 01H88VAJH36MYZ9W1YPWA92Z1Z=nota-1 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=nota-2 deep-linking-and-deferred-deep-linking-using-onelink=deep-linking-y-deep-linking-diferido-mediante-onelink h_01HA77Q9RWZ3FRE5KEN854ZZ78=deep-linking-y-deep-linking-diferido-mediante-onelink h_01HA78QWQVXEWHPEQE6XWBB64M=nota-3" />
