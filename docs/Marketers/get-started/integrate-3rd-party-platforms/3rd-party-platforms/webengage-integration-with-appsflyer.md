---
title: Integración de WebEngage con AppsFlyer
metadata:
  keywords:
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
  created_at: '2022-07-25T13:44:42Z'
  edited_at: '2026-08-12T11:59:46Z'
  id: 7898288493841
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/7898288493841
---
> **De un vistazo:** WebEngage, un partner integrado de AppsFlyer, es una Intelligent Marketing Cloud creada para un mundo mobile-first.

<div id="important" />

> 🚧 **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="setting-up-webengage" />

## Configuración de WebEngage

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La ventana de configuración de WebEngage solo utiliza la pestaña **Integración**.

Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">configurar el encabezado de la página del partner.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

En tu primera visita, activa **Activar partner** para configurar la integración. El conmutador debe estar activado mientras trabajes con el partner. Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación del partner</Anchor>.

<div id="general-settings" />

### Configuración general

WebEngage se conecta con AppsFlyer mediante una clave de API y la región del centro de datos de WebEngage.

* **api\_key:** Introduce la clave de API. Para obtenerla, inicia sesión en tu cuenta de WebEngage y sigue las <Anchor target="_blank" href="https://docs.webengage.com/docs/appsflyer#step-3-add-webengage-api-key--data-center-region">instrucciones</Anchor>.
* **Región:** Introduce la región en la que se alojarán tus datos: **US** (para el centro de datos de EE. UU.) o **IN** (para el centro de datos de India). De forma predeterminada, todos los datos se almacenan en el centro de datos de EE. UU.

![web_mo_engage_general_settings_en-us.png](https://files.readme.io/1297a02a9e280b238a222b14972dc657acffe4566dc49d607178ea43fdc01a77-8089123842705.png) 

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a WebEngage después de las instalaciones y re-engagements de los usuarios.

* **Desactivado**: no envíes ningún postback de instalación.
* **Todas las fuentes de medios, incluidas las orgánicas**: Envía postbacks para eventos atribuidos a cualquier partner y para eventos orgánicos.

![web_mo_engage_default_postbacks_en-us.png](https://files.readme.io/9be309d681904a015fc0295b2ee463411f5c8fbaf450145b132e8ab37bda7665-17028057319697.png)

<div id="note" />

> 📘 **Nota:**
>
> Como red que rastrea todas las instalaciones, WebEngage prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde cualquier fuente, incluidas las orgánicas. WebEngage recomienda seleccionar **Todas las fuentes de medios, incluidas las orgánicas**.

<div id="in-app-event-settings" />

### Configuración de eventos in-app

Asocia los eventos de AppsFlyer con WebEngage mediante postbacks. Si el envío de postbacks está activado, esto incluye los eventos in-app rechazados (eventos bloqueados por Protect360 o eventos que no cumplen con las reglas de validación del targeting).

<div id="to-configure-in-app-event-postbacks" />

#### Para configurar postbacks de eventos in-app

1. Introduce la **api\_key** y la **Región**.
2. Habilite los **postbacks de eventos in-app**.
3. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista.
4. Completa los parámetros según sea necesario.
5. [Opcional] Haz clic en <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para establecer condiciones para enviar ciertos eventos in-app al partner.  
   Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">postbacks de eventos in-app condicionales</Anchor>.

| Nombre de parámetro | Nota |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibe AppsFlyer, ya sea desde el SDK integrado en tu aplicación o desde eventos server-to-server.<br />**Consejo**: ¿No encuentras el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer**, luego haz clic en **Crear personalizado**. Leer más sobre <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">la asignación de eventos personalizados.</Anchor></li></ul> |
| **Para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner**: envía postbacks solo cuando este evento se atribuye a este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks para eventos atribuidos a cualquier partner, incluidos los eventos orgánicos.</li></ul> |
| **Incluye** | <ul><li>**Sin datos (predeterminado)**: envía solo el evento en sí sin el valor del evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento).</li><li>**Valores sin ingresos**: envía todos los parámetros **excluyendo** el valor de ingresos.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

El **enlace de atribución** no es compatible con la integración con este partner.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Los **datos de costos** no son compatibles con la integración con este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los **ingresos por publicidad** no se admiten en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Los **permisos** no son compatibles con la integración con este partner.

</Accordion>

<div data-zendesk-anchors="h_01H9HWK7APBFK7RWVFH79VW0ME=importante setting-up-webengage=configuraci%C3%B3n-de-webengage h_01H9HWK7AP6Z398NP3G2BQQBTF=configuraci%C3%B3n-de-webengage h_01H9HWK7AP3ERT0TM39E6S5M79=integration-tab activate-partner=activar-socio h_01H9HWK7AP3FMR5RMANZCMQ6M0=activar-socio general-settings=configuraci%C3%B3n-general h_01H9HWK7APG1STZ4Q19QVX4KRY=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01H9HWK7AP23GK6WWJTB543FEQ=postbacks-predeterminados h_01H9HWK7APMBSZ1PG8MK88HZFS=nota inapp-event-settings=configuraci%C3%B3n-de-eventos-in-app h_01H9HWK7APFNAFE9YM2484DDHD=configuraci%C3%B3n-de-eventos-in-app to-configure-inapp-event-postbacks=para-configurar-postbacks-de-eventos-in-app h_01H9HWK7APZM8328V0EV4B5QDN=para-configurar-postbacks-de-eventos-in-app h_01H9HWK7AQTZXE7GPX5E9X2ZYN=attribution-link-tab h_01H9HWK7AQ8SXED5KHVD5T4DZZ=cost-tab h_01H9HWK7AQ2JG4BRS784M85Z6E=ad-revenue-tab h_01H9HWK7AQ5YJDY2M96CA05H6P=permissions-tab" />
