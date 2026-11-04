---
title: Integración de Eulerian con AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Eulerian
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
  created_at: '2018-10-02T08:41:24Z'
  edited_at: '2026-08-12T11:58:49Z'
  id: 360001521405
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/360001521405
---
> **De un vistazo:** Eulerian, partner integrado con AppsFlyer, se centra en el análisis y la optimización en tiempo real de las operaciones de e-marketing. Basado en un sistema exhaustivo de recopilación de datos, el paquete de marketing de Eulerian ofrece una combinación de soluciones de atribución web de marketing y gestión de datos. Esta tecnología permite a los usuarios centralizar, analizar, gestionar y activar datos en tiempo real.

<div id="important" />

> 🚧 **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="setting-up-eulerian" />

## Configuración de Eulerian

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La ventana de configuración de Eulerian incluye 4 pestañas: **Integración, Enlace de atribución, Enriquecimiento de datos** y **Permisos**. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de la pestaña.

Para ver una descripción detallada del Partner Configuration Window Header, haz clic <Anchor target="_blank" href="/marketers/es/docs/user-level-data-retention">aquí</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, debes activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

**HostID**

Eulerian se conecta con AppsFlyer a través de un Host ID único. Si aún no lo tienes, debes obtenerlo de Eulerian para continuar con la integración.

![Eulerian_msc_new_2.png](https://files.readme.io/345b05c3960015bfe1b44dd2a298c4216185c2315fb859378e9e337ba2bf913a-360002665949.png)

Realiza los siguientes pasos, según sea necesario:

* Introduce el **HostID**
* Activa **Enable** para enviar todas las instalaciones a Eulerian

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a Eulerian tras las instalaciones de los usuarios. Usa esta sección para definir el envío de estos postbacks.

![Eulerian_new_2.png](https://files.readme.io/59cb41cdbec6c06dd4fc2086d238fe2015e5414a474591b23f9a18f8421fb030-360002795789.png)

Selecciona **Eventos atribuidos a cualquier partner** para enviar postbacks a Eulerian.

<div id="in-app-event-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a Eulerian mediante postbacks.

![Eulerian_new_3.png](https://files.readme.io/c190a6b05c977c8d5fa2a0e5301cdb5be239e56455b066cba93b8c1ffa6fcd9a-360002795829.png)

1. Introduce de nuevo el HostID.
2. Activa los postbacks de eventos in-app.
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
4. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
5. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define Eulerian.  <br />Obtén el ID de evento correspondiente de Eulerian y configúralo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada** - AppsFlyer envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

6. Haz clic en **Guardar**.

Una vez guardado, AppsFlyer comienza a enviar datos a Eulerian para cada instalación orgánica y no orgánica.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para Eulerian.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

El costo no se admite en la integración con Eulerian.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no se admiten en la integración con Eulerian.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para Eulerian.

</Accordion>

<div data-zendesk-anchors="h_01H9FK7FC3ME19HXCRQ0XKVQQC=importante setting-up-eulerian=configuraci%C3%B3n-de-eulerian h_01H9FK7FC309KKTAKZ1K9AHAN5=configuraci%C3%B3n-de-eulerian h_01H9FK7FC3K3Y8220AG9YK3BP8=integration-tab activate-partner=activar-socio h_01H9FK7FC316DZHE9YKSWQ5A5N=activar-socio general-settings=configuraci%C3%B3n-general h_01H9FK7FC4ZBQ2XPTFYQ4C7XH6=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01H9FK7FC4VBY3TEE6HEJZCWWT=postbacks-predeterminados inapp-event-settings=configuraci%C3%B3n-de-eventos-in-app h_01H9FK7FC4KF5QGXA9KQ4YQEA3=configuraci%C3%B3n-de-eventos-in-app h_01H9FK7FC4H7QSFGWDV1AP0YK6=attribution-link-tab h_01H9FK7FC48YAYF3TGXC2C9EB8=cost-tab h_01H9FK7FC4YAPTGA15172P5TXB=ad-revenue-tab h_01H9FK7FC46W5A1BRSVPBEGJTK=permissions-tab" />
