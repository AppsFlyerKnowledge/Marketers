---
title: Guía de integración de IBM UBX con AppsFlyer
metadata:
  keywords:
    - Analytics
    - IBM
    - UBX
    - integrated partner
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
  created_at: '2016-07-03T09:06:26Z'
  edited_at: '2026-08-12T11:58:54Z'
  id: 210093266
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/210093266
---
> **De un vistazo:** IBM UBX (Universal Behavior Exchange), un partner integrado de AppsFlyer, es una función de IBM Marketing Cloud y de otras soluciones de IBM Commerce que permite a los profesionales del marketing tomar el control de toda la integración de los datos de sus clientes mediante una consola fácil de usar. Esta capacidad de intercambio abierto de datos proporciona una visión contextual de los comportamientos de compra de los clientes en todos los canales, dispositivos e interacciones, para que los profesionales del marketing puedan diseñar e implementar rápidamente campañas eficaces, ofreciendo experiencias significativas al instante e impulsando el ROI.

> 🚧 **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

## Configuración de IBM

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La ventana de configuración de IBM solo utiliza la pestaña **Integración**.

Para ver una descripción detallada del Partner Configuration Window Header, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

### Activar socio

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

### Configuración general

**Clave de autorización**

IBM se conecta con AppsFlyer a través de una clave de autorización única. Si aún no la tienes, debes obtenerla de IBM para continuar con la integración o seguir los pasos que se indican a continuación.

![IBM_msc_new_2.png](https://files.readme.io/d6dddd7232ba7ecba2ed5bd944f98669902689fc0953afc558fbc6586be8b5cf-360002219269.png)

### Obtención de la clave de autorización

El primer paso para configurar un endpoint publisher de eventos genérico de AppsFlyer es crear un endpoint en blanco en la interfaz de IMB UBX.

Para ello, inicia sesión en tu cuenta de UBX y ve a la pestaña **Endpoints**

![](https://files.readme.io/8c0833f890c5e2ed2df1c0a8904e1764b341a82f3381c0a1a3fb6effe4f76673-205128323.png)

A continuación, haz clic en **Register new endpoint**

![](https://files.readme.io/23c8d4a88eda765fce1b42f9eb2e74b1325160e6d0602dc65a8ab05488598b9e-205053206.png)

A continuación, selecciona **AppsFlyer** y haz clic en **Next**.

![IBM_1.png](https://files.readme.io/f30b7b27d2ffecf3e562cbe651367306a581d1881325dd141c950b39efac016c-115002600286.png)

Después de la implementación, regresa al **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado**y confirma que ha actualizado el último certificado de AppsFlyer

![Pasted_image_at_2017_02_23_02_48_PM.png](https://files.readme.io/11a94c4d9f4c9282c230e4cf69f31e0d39f4eb88196313b3cfc103a5bbaba9a4-115002600326.png)

Haz clic en los 3 puntos del lado derecho del endpoint de AppsFlyer recién generado y haz clic en **endpoint details**.

![IBM_3.png](https://files.readme.io/70edd2e14c6c344188dcc65b65b3a8d92081401dd34909f5a4e0dd6bd137b8df-115002599203.png)

Copia la clave de autenticación:

![IBM_Endpoint_details.png](https://files.readme.io/3706f4dd665d8d2a26de9013b03c0e6575d051f2fa5500033e172312a63f09ea-115002601006.png)

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a las instalaciones de usuarios de IBM. Usa esta sección para definir el envío de estos postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Selecciona **Events attributed to any partner or organic** para enviar postbacks a IBM de cualquier usuario que descargue la aplicación, o selecciona **Off**.

Haga clic en **Guardar**.

### Configuración de eventos in-app

[![](https://files.readme.io/c945ee3c04f49076e54c9966389506aea441406e01daa49d737a86da9f5bd2bc-360002219429.png)](https://files.readme.io/c945ee3c04f49076e54c9966389506aea441406e01daa49d737a86da9f5bd2bc-360002219429.png)

En esta sección puedes asignar tus eventos de AppsFlyer a IBM mediante postbacks.

1. Introduce de nuevo la clave de autorización.
2. Activa los postbacks de eventos in-app.
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
4. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
5. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK integrado con tu app o desde eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define IBM.  <br />Obtén el ID de evento correspondiente de IBM e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Cuando no está marcada** - AppsFlyer envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para IBM.

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

Los permisos no están disponibles para IBM.

</Accordion>

<div data-zendesk-anchors="h_01H9FK8FS5T9KZ30N87B76QVT5=importante setting-up-ibm=configuraci%C3%B3n-de-ibm h_01H9FK8FS5QPJYSA7JVY4QNB3S=configuraci%C3%B3n-de-ibm h_01H9FK8FS5J30GZS634NMG62BQ=integration-tab activate-partner=activar-socio h_01H9FK8FS5SYTBF8A3QX4QGESM=activar-socio general-settings=configuraci%C3%B3n-general h_01H9FK8FS5YXRCN83RHG6QBAKS=configuraci%C3%B3n-general obtaining-the-authorization-key=obtenci%C3%B3n-de-la-clave-de-autorizaci%C3%B3n h_01H9FK8FS5ZVGX5RK7K72SH6K6=obtenci%C3%B3n-de-la-clave-de-autorizaci%C3%B3n default-postbacks=postbacks-predeterminados h_01H9FK8FS5SVF4YQC8AG2V6N8D=postbacks-predeterminados inapp-event-settings=configuraci%C3%B3n-de-eventos-in-app h_01H9FK8FS54N196VQ0XCXJ763Q=configuraci%C3%B3n-de-eventos-in-app h_01H9FK8FS50TB7TZH9JKEH3Y7H=attribution-link-tab h_01H9FK8FS54P1MYVXGR46TXN7D=cost-tab h_01H9FK8FS600SP0MS1T6PTBMH4=ad-revenue-tab h_01H9FK8FS65VMZK13D2BE5DT09=permissions-tab" />
