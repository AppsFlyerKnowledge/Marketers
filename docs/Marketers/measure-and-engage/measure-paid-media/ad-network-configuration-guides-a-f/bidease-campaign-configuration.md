---
title: Configuración de la campaña de Bidease
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
  created_at: '2023-11-13T13:17:18Z'
  edited_at: '2026-09-11T00:23:12Z'
  id: 20106343354129
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/20106343354129
---
> **En resumen:** Bidease (bidease\_int), un socio integrado de AppsFlyer, es un DSP totalmente transparente para los mobile marketers. Utilizando tecnología propia de publicidad programática, aprendizaje automático y datos de first-party, Bidease optimiza las campañas en todos los principales formatos móviles para lograr los comportamientos deseados después de la instalación sin riesgo para sus clientes.

<Image alt="bidease.png" src="https://files.readme.io/4a3373c0fdb73190017601c374ca7634cc0feb1954b6e23fc1bd9693c60605f9-20106376017041.png" width="100px" />

## Configuración de Bidease

La integración con Bidease soporta la atribución click-through y view-through.

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de partners > Marketplace**.  
   (**Para editar una integración existente:** ve a la pestaña **Colaborar > Integraciones de partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** el selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners</Anchor>

La ventana de configuración incluye las siguientes pestañas: Integración, Enlace de atribución, Costo, Ingreso publicitario y Permisos. Para Bidease, las pestañas disponibles son Integración, Enlace de atribución y Permisos.

> 📘 **Nota**
>
> * Algunas configuraciones difieren para dispositivos iOS y Android
> * Aprende más sobre cómo <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">configurar integraciones de partners</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña **Integración** incluye una serie de secciones, como se describe a continuación.

#### Activar partner

Activa el selector **Activar partner** .  
**Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner.**

#### Privacidad avanzada

**Solo para aplicaciones de iOS:** Tu control sobre los datos compartidos con el partner a través de postbacks y <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">reportes</Anchor> depende del estado del selector de **Privacidad avanzada (para iOS 14.5+ y posteriores)**:

| Privacidad avanzada: activada | Privacidad avanzada: desactivada |
| --- | --- |
| Los postbacks se envían solo para eventos atribuidos al partner | Los postbacks se envían según tu configuración:<ul><li>**Todas las fuentes de medios, incluidas las orgánicas**</li><li>**Solo este partner**</li></ul> |
| Los postbacks se envían de acuerdo con la <Anchor target="_blank" href="/partners/es/docs/advanced-privacy-guide-postback-macros-for-ad-networks">plantilla de Privacidad avanzada</Anchor> |  |
| <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Los datos agregados y anónimos</Anchor> se comparten con el partner, lo que significa que no se comparten datos a nivel de usuario (ID de dispositivo). |  |

#### ID de transacción

**Solo para aplicaciones iOS:** Cuando **Compartir ID de transacción SKAN** está activado, estás permitiendo que AppsFlyer <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">comparta el ID de transacción de los postbacks de SKadNetwork</Anchor> con Reddit. Al hacerlo, Reddit podría decodificar tus valores de conversión de SkadNetwork .

#### Atribución de instalación.

Para atribuir instalaciones de visualización a través de Bidease, activa **Instalar atribución view-through**. El control deslizante de view-through está disponible en la [pestaña Enlace de atribución](#attribution-link-tab).

#### Postbacks predeterminados

Define el origen de los usuarios para enviar postbacks automáticos a los partners en relación con las acciones de los usuarios que se producen antes del lanzamiento de la aplicación:

* Para **Instalaciones**, selecciona una de las siguientes opciones:
  * **Solo este partner:** Envía postbacks solo cuando la instalación se atribuya a este partner, es decir, el usuario que instaló la aplicación provenía de Bidease.
  * **Todas las fuentes de medios, incluidas las orgánicas:** Envía postbacks para las instalaciones atribuidas a cualquier partner y para eventos orgánicos, es decir, el usuario que instaló la aplicación provenía de cualquier fuente de medios.
* Para **instalaciones rechazadas** y **Re-engagements:** Los postbacks se envían únicamente a Bidease.

#### Postbacks de eventos in-app

Establece la **ventana de postback de eventos in-app**, según sea necesario (lee más sobre la configuración de la ventana de postback de eventos in-app).

Configura el mapeo de eventos en la aplicación con eventos de Bidease, enviados a través de postbacks:

1. Activa **Postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista. En la siguiente tabla se describen los campos que debes completar:

| Nombre de parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos de servidor a servidor.<br />**Consejo**: ¿No ves el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Leer más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación personalizada de eventos</Anchor>.</li></ul> |
| **para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner**: envía postbacks solo cuando este evento se atribuya a este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks para eventos atribuidos a cualquier partner, así como para eventos orgánicos.</li></ul> |
| **incluyendo** | <ul><li>**Sin datos (predeterminado)**: envía solo el evento en sí sin los valores del evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento).</li><li>**Valores sin ingresos**: envía todos los parámetros **excluyendo** el valor de ingresos.</li></ul> |

3. [Opcional] Haz clic en el icono **Agregar condición** <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer las condiciones</Anchor> de un evento.
4. Haz clic en **Guardar integración**.
5. [Opcional] Después de guardar la integración, desde la página de configuración, puedes integrar más de tus aplicaciones con el partner:
   1. En la esquina superior izquierda, debajo del nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
   2. Selecciona una aplicación diferente en la lista desplegable.
   3. Repite los pasos de integración para la aplicación seleccionada.

> 📘 **Nota**
>
> **Solo para aplicaciones de iOS:** Tu control sobre los datos compartidos con el partner a través de postbacks y <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">reportes</Anchor> depende del <Anchor target="_blank" href="/marketers/es/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">estado del selector</Anchor> **Privacidad avanzada (para iOS 14.5+ y posteriores)**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda los enlaces de atribución y envíalos al partner para atribuir campañas específicas, conjuntos de anuncios o anuncios individuales, tanto para UA como para campañas de retargeting. Puedes usar un enlace de plataforma única o  <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>. <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Aprende más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>. 

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de Costo">

<Anchor target="_blank" href="/marketers/es/docs/roi360-guide-cost-and-revenue-data">Los datos de costos</Anchor> no están disponibles para Bidease.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

<Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution">Los ingresos por publicidad</Anchor> no están disponibles para Bidease.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Selecciona qué <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos otorgar</Anchor> a Bidease para acceder a tus datos y realizar diversas acciones.

> 📘 **Nota**
>
> Cuando la integración se <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">desactiva</Anchor> mientras el selector Permisos aún está activado, se siguen otorgando permisos.

</Accordion>

<div data-zendesk-anchors="setting-up-bidease=configuraci%C3%B3n-de-bidease h_01HF4ED4B5QHY92B03426260QY=configuraci%C3%B3n-de-bidease h_01HF4DWFAP55JRXTR8Z65YAR68=nota h_01HF4DWFAP4S45241VR1PJ3RFC=integration-tab activate-partner::b746d215=activar-partner h_01HF4DWFAP9BS1G612WS5HNQ6S=activar-partner advanced-privacy=privacidad-avanzada h_01HF4DWFAQHEJATJG6DRVMKA34=privacidad-avanzada transaction-id=id-de-transacci%C3%B3n h_01HF4DWFAQ1Y1AVQ0EV63H5YJ1=id-de-transacci%C3%B3n install-attribution=atribuci%C3%B3n-de-instalaci%C3%B3n h_01HF4DWFAQQRR8XH5S7NW2NCB6=atribuci%C3%B3n-de-instalaci%C3%B3n default-postbacks=postbacks-predeterminados h_01HF4DWFAQG4YEEH3HMD61GEWE=postbacks-predeterminados inapp-event-postbacks=postbacks-de-eventos-in-app h_01HF4DWFAQQCM4TK3JJNMSM6RD=postbacks-de-eventos-in-app h_01HF4DWFAQQ3C7GBA4Q4SA6G0Y=nota-1 h_01HF4DWFAQ9D9BV6PG4BEYX788=attribution-link-tab h_01HF4DWFAQT2PD4863N6EB7HHH=cost-tab h_01HF4DWFAQXMNDHWT0Y4C0M6EN=ad-revenue-tab h_01HF4DWFAQJWNFMFDEZ8XT0DM5=permissions-tab h_01HF4DWFAQJ9HRMD1FE717F1WK=nota-2" />
