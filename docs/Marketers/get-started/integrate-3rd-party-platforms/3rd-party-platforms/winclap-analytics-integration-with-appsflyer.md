---
title: Integración de Winclap Analytics con AppsFlyer
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
  created_at: '2019-09-04T11:07:12Z'
  edited_at: '2026-09-17T00:11:32Z'
  id: 360002403537
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/360002403537
---
> **De un vistazo:** Winclap Analytics, partner integrado de AppsFlyer, utiliza los datos de atribución de AppsFlyer para BI y análisis posteriores a la atribución.

> 🚧 **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

## Configuración de Winclap

La configuración se realiza desde la página **Integraciones activas**, pero para encontrar al partner primero debes ir al <Anchor target="_blank" href="/marketers/es/docs/partner-integrations">Marketplace</Anchor>.

> 📘 **Nota:**
>
> **Requisito previo:** una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.
>
> **Para configurar una nueva integración:**
>
> 1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de partners > Marketplace** .
>    (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de partners > Integraciones activas**.)
> 2. Selecciona la aplicación correspondiente.
> 3. Busca el partner y selecciona **Integrar**.
> 4. En la pestaña **Integración**, activa el conmutador **Activar partner**.
>    **Nota:** El conmutador **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
> 5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners</Anchor>.

La configuración de Winclap Analytics utiliza solo la pestaña ***Integración***.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

### Activar socio

En la **primera visita** aquí, debes activar el selector ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/user-level-data-retention">aquí</Anchor>.

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a Winclap Analytics tras las instalaciones de usuarios y los re-engagements. Utiliza esta sección para definir la **fuente de los usuarios** que permite enviar estos postbacks.

![integración de Winclap Analytics: postbacks predeterminados](https://files.readme.io/a45d8d7ab4687876d8dea4b026580d80f4b34c151b00c3c47a701771d16582aa-50896714399761.png)

Para las **instalaciones**, selecciona:

* (Predeterminado) ***Solo este partner*** para eventos que provienen únicamente de usuarios atribuidos a Winclap.
* ***Todas las fuentes de medios, incluidas las orgánicas*** para enviar postbacks de cualquier Usuario que descargue la Aplicación a Winclap.

Para los **re-engagements**, los postbacks se pueden enviar para ***Solo este partner***.

Una vez guardada esta configuración, AppsFlyer envía los siguientes datos a Winclap Analytics para cada instalación, tanto orgánica como no orgánica:

* ID de clic
* Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.
* Agente de usuario
* Horario del clic
* IP
* País
* Ciudad en la conversión
* Subanunciante
* ID de dispositivo para Android & iOS
* Operador
* API de ingresos reales
* Identificación de la aplicación
* Versión de la aplicación
* Nombre de aplicación
* Tiempo de instalación

### Configuración de eventos in-app

En esta sección, puedes asignar qué eventos in-app enviar a Winclap Analytics mediante postbacks:

[![winclap analytics - configuración del postback de eventos in-app](https://files.readme.io/f14f801a50b3c699f71141a387a9d75586bae7b91aad88f29f97778408ee12fb-50896714404369.png)](https://files.readme.io/f14f801a50b3c699f71141a387a9d75586bae7b91aad88f29f97778408ee12fb-50896714404369.png)

1. Cambia el interruptor ***Postbacks de eventos in-app*** a ON.
2. Establece la ***ventana de postback de eventos in-app***, si es necesario (Leer más sobre <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">la configuración de la ventana de postback de eventos in-app</Anchor>).
3. Haz clic en ***Agregar evento*** para añadir un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: ¿No encuentras el evento que buscas? Escribe su nombre de evento del SDK, haz clic en **Crear personalizado** y asigna normalmente. Leer más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados</Anchor>. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento, tal como lo define Winclap.  <br />Obtén de Winclap el ID correspondiente de cada uno de los eventos que quieras reportarles e introdúcelo en este campo. |
| **Opción de envío** | Selecciona la opción de envío para el evento:  <br />**Solo este partner** para eventos que provienen **solo** de usuarios atribuidos a este partner  <br />**Todas las fuentes de medios, incluidas las orgánicas** para que toda tu base de usuarios esté disponible para reportarla al partner |
| **Enviar datos de eventos** | <ul><li>**Sin valores ni ingresos:** envía solo el evento en sí sin el valor del evento.</li><li>**Con valores y sin ingresos:** envía todos los parámetros, excepto el valor de ingresos.</li><li>**Con valores e ingresos**: envía todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento).</li></ul> |

5. Haz clic en ***Guardar***.

Una vez guardada esta configuración, AppsFlyer envía los siguientes datos a Winclap Analytics para cada evento no orgánico:

* ID de clic
* Tasa del impuesto sobre los ingresos netos
* Valor del evento
* Modelo de dispositivo: iPhone7
* Evento in-app
* Ingresos del evento en USD
* Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.
* Agente de usuario
* Horario del clic
* IP
* País
* Ciudad en la conversión
* Sub publisher
* ID de dispositivo para Android & iOS
* Operador
* API de ingresos reales
* Identificación de la aplicación
* Versión de la aplicación
* Nombre de aplicación
* Tiempo de instalación

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para Winclap Analytics.

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

Los permisos no están disponibles para Winclap Analytics.

</Accordion>

<div data-zendesk-anchors="h_01H9HWQK6JA2194MPE8PVQJ346=importante setting-up-winclap=configuraci%C3%B3n-de-winclap h_01H9HWQK6JAQ2GCHHGQ57PJ570=configuraci%C3%B3n-de-winclap h_01H9HWQK6JRZ1KVDJK00PZR7T9=nota h_01H9HWQK6JX9MAD64MQ1HPK4T0=integration-tab activate-partner=activar-socio h_01H9HWQK6JKRB5MDE43RKV3SEH=activar-socio default-postbacks=postbacks-predeterminados h_01H9HWQK6JP4HQHRFC011KW6XQ=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01H9HWQK6J1MEK67XDMAMKAQKW=configuraci%C3%B3n-de-eventos-in-app h_01H9HWQK6JBH1M2MZQM12R0SAR=attribution-link-tab h_01H9HWQK6JG46BGNRMR8ZM9W2J=cost-tab h_01H9HWQK6J7HHJWKVB55WE1VW9=ad-revenue-tab h_01H9HWQK6J6BD0ER2M9Z7GYGSM=permissions-tab" />
