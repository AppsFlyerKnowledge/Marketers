---
title: Configuración de campaña Persona.ly RTB
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
  created_at: '2023-09-20T07:13:43Z'
  edited_at: '2026-08-12T12:15:08Z'
  id: 18699025653265
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/18699025653265
---
> **En resumen:** Persona.ly RTB (personalyrtb\_int), un partner integrado de AppsFlyer, es un DSP basado en dispositivos móviles que opera en todo el mundo. Mediante el uso de algoritmos propios de oferta y aprendizaje automático, Persona.ly ofrece soluciones de UA y retargeting transparentes, impulsadas por el rendimiento y altamente específicas.

<Image alt="persona.ly_logo.png" src="https://files.readme.io/b0dacbdc4c2e884610a040b5049a1410a88214f8275320163764bcf09f90305b-18699636413969.png" width="234px" />

<div id="setting-up-personaly-rtb" />

## Configuración de Persona.ly RTB

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activar:** En AppsFlyer, en el menú lateral, selecciona**Colaborar** > **Partner Marketplace**.  
   **Para editar:** En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones Activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la pestaña **Integración**, haz clic en **Activar socio**.  
    **Nota:** El selector debe permanecer <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activado</Anchor> mientras trabajes con el socio. Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación. Para ver una descripción detallada del Encabezado de la ventana de configuración de partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

La integración con Persona.ly RTB soporta la atribución click-through y view-through.  
La ventana de configuración incluye las siguientes pestañas: Integración, Enlace de atribución, Costo, Ingreso publicitario y Permisos. Para Persona.ly RTB, las pestañas disponibles son Integración, Enlace de atribución, Costo y Permisos.

<div id="note" />

> 📘 **Nota**
>
> * Algunas configuraciones difieren para dispositivos iOS y Android
> * Aprende más sobre cómo <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">configurar integraciones de partners</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de integración">

La pestaña **Integración** incluye una serie de secciones, como se describe a continuación.

<div id="activate-partner" />

#### Activar partner

Para configurar la integración, primero debes <Anchor target="_blank" href="/marketers/es/docs/amazon-ads-campaign-configuration#activar-socio">activar</Anchor> el selector **Activar partner**. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">activación y desactivación de integraciones de partners</Anchor>.

<div id="note-1" />

> 📘 **Nota**
>
> Como red de instalación completa, Persona.ly RTB prefiere recibir postbacks para todas las nuevas instalaciones de tu aplicación desde cualquier fuente. Para ello, selecciona **Todas las fuentes de medios, incluidas las orgánicas** para enviar todos los postbacks de instalación a Persona.ly RTB.

<div id="advanced-privacy" />

#### Privacidad Avanzada

Solo para aplicaciones de iOS: Tu control sobre los datos compartidos con el partner a través de postbacks y <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">reportes</Anchor> depende del estado del selector de **Privacidad avanzada (para iOS 14.5+ y posteriores)**:

| Privacidad avanzada: activada | Privacidad avanzada: desactivada |
| --- | --- |
| Los postbacks se envían solo para eventos atribuidos al partner | Los postbacks se envían según tu configuración:<ul><li>**Todas las fuentes de medios, incluidas las orgánicas**</li><li>**Solo este partner**</li></ul> |
| Los postbacks se envían de acuerdo con la <Anchor target="_blank" href="/partners/es/docs/advanced-privacy-guide-postback-macros-for-ad-networks">plantilla de Privacidad avanzada</Anchor> |  |
| <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Los datos agregados y anónimos</Anchor> se comparten con el partner, lo que significa que no se comparten datos a nivel de usuario (ID de dispositivo). |  |

<div id="transaction-id" />

#### ID de transacción

Solo para aplicaciones iOS, cuando **Compartir ID de transacción SKAN** está activado, estás permitiendo que AppsFlyer <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">comparta el ID de transacción de los postbacks de SKadNetwork</Anchor> con Reddit. Al hacerlo, Reddit podría decodificar tus valores de conversión de SkadNetwork.

<div id="install-attribution" />

#### Atribución de instalación.

Para atribuir instalaciones view-through a través de Persona.ly RTB, activa **Instalar atribución view-through**. El control deslizante de view-through está disponible en la [pestaña Enlace de atribución](#attribution-link-tab).

<div id="default-postbacks" />

#### Postbacks predeterminados

Define el origen de los usuarios para enviar postbacks automáticos a los partners en relación con las acciones de los usuarios que se producen antes del lanzamiento de la aplicación:

* Para **Instalaciones**, selecciona una de las siguientes opciones:
  * **Solo este partner:** Envía postbacks solo cuando la instalación se atribuya a este partner, es decir, el usuario que instaló la aplicación provenía de Persona.ly RTB.
  * **Todas las fuentes de medios, incluidas las orgánicas:** Envía postbacks para las instalaciones atribuidas a cualquier partner y para eventos orgánicos, es decir, el usuario que instaló la aplicación provenía de cualquier fuente de medios.
* Para **instalaciones rechazadas** y **Re-engagements:** Los postbacks se envían únicamente a Persona.ly RTB.

<div id="in-app-event-postbacks" />

#### Postbacks de eventos in-app

Configura el mapeo de eventos in-app con eventos Persona.ly RTB, enviados a través de postbacks:

1. Activa **Postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista. En la siguiente tabla se describen los campos que debes completar:

| Nombre de parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos de servidor a servidor.<br />**Consejo**: ¿No ves el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Leer más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados.</Anchor></li></ul> |
| **Asignado al evento de socio** | El ID o nombre único de cada evento, tal y como lo defina el partner. Existen varias configuraciones de asignación:<ul><li>**Campo de texto:** obtén el ID del evento correspondiente del partner.</li><li>**Cuadro desplegable:** selecciona el evento de AppsFlyer predefinido más adecuado.</li><li>**Tal como está**: envía los eventos tal como están, sin asignación de nombres.</li></ul> |
| **para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner**: envía postbacks solo cuando este evento se atribuya a este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks para eventos atribuidos a cualquier partner, así como para eventos orgánicos.</li></ul> |
| **incluyendo** | <ul><li>**Sin datos (predeterminado)**: envía solo el evento en sí sin los valores del evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento).</li><li>**Valores sin ingresos**: envía todos los parámetros **excluyendo** el valor de ingresos.</li></ul> |

3. [Opcional] Haz clic en el icono **Agregar condición** <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer las condiciones</Anchor> de un evento.
4. Establece la **ventana de postback de eventos in-app**, si es necesario (lee más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app"> configuración de la ventana de postback de eventos in-app</Anchor>).
5. Haz clic en **Guardar integración**.
6. [Opcional] Después de guardar la integración, desde la página de configuración, puedes integrar más de tus aplicaciones con el partner:
   1. En la esquina superior izquierda, debajo del nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
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

AppsFlyer obtiene los detalles de costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de redes de publicidad</Anchor> para obtener detalles completos sobre las dimensiones, métricas y funciones admitidas. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el dashboard de estado de la integración de costos (e ingresos por publicidad) o en el dashboard de la red de publicidad individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos publicitarios">

Los ingresos por publicidad no están disponibles para Persona.ly RTB.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Selecciona qué <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos otorgar a</Anchor> Persona.ly RTB para acceder a tus datos y realizar diversas acciones.

<div id="note-3" />

> 📘 **Nota**
>
> Cuando la integración se <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">desactiva</Anchor> mientras el selector Permisos aún está activado, se siguen otorgando permisos.

</Accordion>

<div data-zendesk-anchors="setting-up-amazon-dsp-integration=configuraci%C3%B3n-de-personaly-rtb 01H88VAJH3VENKYVRQY5RXN63P=configuraci%C3%B3n-de-personaly-rtb 01H88VAJH3BYZSXQGGZZJQ9N0C=nota 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=activar-partner 01H88VAJH34GP7FK1KTJGRDPM7=activar-partner h_01HBB9EEMJ55BQDJ1ZEJT136ZF=nota-1 advanced-privacy=privacidad-avanzada 01H88VAJH3G5FAR7RRNDEPNGME=privacidad-avanzada transaction-id=id-de-transacci%C3%B3n h_01HARQDVEDA206D0BBXBC6WEHH=id-de-transacci%C3%B3n install-attribution=atribuci%C3%B3n-de-instalaci%C3%B3n h_01HA6PNN6RJYTNXRAS3M9EA4M4=atribuci%C3%B3n-de-instalaci%C3%B3n default-postbacks=postbacks-predeterminados 01H88VAJH3WE9Z0971WMBRBJRS=postbacks-predeterminados inapp-event-postbacks=postbacks-de-eventos-in-app 01H88VAJH3AS37MVF75GANWX4B=postbacks-de-eventos-in-app 01H88VAJH36MYZ9W1YPWA92Z1Z=nota-2 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=nota-3" />
