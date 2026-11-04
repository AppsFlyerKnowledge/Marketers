---
title: 'Pinterest: crea una integración de la aplicación web'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-06-14T13:07:07Z'
  edited_at: '2026-09-01T00:31:03Z'
  id: 47721580892433
  locale: es
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/es/articles/47721580892433
---
**Resumen:** Configura una integración de Pinterest para tu aplicación web a fin de enviar eventos de conversión web a Pinterest para la optimización de campañas y la creación de reportes.

<div id="set-up-integration" />

## **Configurar la integración**

**Requisitos previos:**

* Una cuenta de Pinterest
* Una aplicación web configurada en AppsFlyer. <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer#web">Más información</Anchor>
* El <Anchor target="_blank" href="/marketers/es/docs/integrate-appsflyer-web-sdk">SDK web</Anchor> de AppsFlyer o la <Anchor target="_blank" href="/marketers/es/docs/server-to-server-s2s-api-for-web-performance-measurement">API de servidor a servidor (S2S)</Anchor> para la atribución web

**Para activar o editar la integración:**

1. **Para activar:** En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de partners** > la pestaña **Marketplace**.  
   **Para editar:** En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de partners** > la pestaña **Integraciones activas**.
2. Selecciona tu aplicación web en el menú desplegable de arriba.
3. Busca Pinterest y haz clic en **Integrate**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.  
   **Nota:** El selector debe permanecer activado <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activado)</Anchor> mientras trabajes con Pinterest.
5. Completa la configuración en la pestaña **Integración** como se describe a continuación.

<div id="integration-tab" />

## **Pestaña de Integración**

<div id="activate-partner" />

### **Activar socio**

En la **primera visita**, activa el selector **Activar partner** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe permanecer activado mientras trabajes con Pinterest.

Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">la activación del partner</Anchor>.

<div id="in-app-event-settings" />

### **Configuración de eventos in-app**

Para enviar postbacks de eventos in-app a Pinterest, proporciona las siguientes credenciales de Pinterest. Estas credenciales se incluyen en los postbacks de eventos enviados a Pinterest.

* **ID de la cuenta publicitaria**: el identificador único de tu cuenta publicitaria de Pinterest.
* **Access Token**: un token de acceso generado en Pinterest.

Puedes encontrar el ID de la cuenta publicitaria y el Access Token en la interfaz de usuario de Pinterest Ads Manager (consulta la <Anchor target="_blank" href="https://developers.pinterest.com/docs/api-features/tracking-conversions/#getting-your-access-token-and-ad-account-id">documentación de Pinterest</Anchor>). Contacta con el soporte de Pinterest si necesitas ayuda.

**Para configurar las credenciales de Pinterest:**

1. En AppsFlyer, en la página **Integración activa** de Pinterest > pestaña **Integración**, desplázate hasta **Configuración de eventos in-app**.
2. Introduce los valores de ID de la cuenta publicitaria y Access Token en sus respectivos campos.

<div id="in-app-event-postbacks" />

### **Habilitar la atribución por impresiones**

En esta sección, asignas tus eventos web de AppsFlyer a eventos de Pinterest mediante postbacks.

1. En la configuración de integración de Pinterest, desplázate hasta **Postbacks de eventos in-app**.
2. Activa los **postbacks de eventos in-app**.
3. Configura la ventana de postbacks de eventos in-app.
4. Selecciona la configuración de postback y los mapeos para los eventos.

| **Nombre del parámetro** | **Nota** |
| --- | --- |
| **Nombre del evento de AppsFlyer** | El nombre del evento web, tal como lo recibe AppsFlyer desde el SDK web integrado en tu sitio web o desde eventos de servidor a servidor.<br /><br />**Nota:** Si no ves en la lista el evento que quieres, asegúrate de que el evento esté activado y vuelve a comprobarlo. |
| **Nombre del evento del partner** | El evento de Pinterest al que asignar, seleccionado de la lista predefinida de eventos de Pinterest. Para ver los nombres de eventos de Pinterest, consulta la <Anchor target="_blank" href="https://developers.pinterest.com/docs/api-features/track-conversion-events/#understand-conversion-events">documentación de Pinterest</Anchor>. |
| **Para usuarios de** | **Solo este partner:** Eventos que provienen únicamente de usuarios atribuidos a Pinterest.<br /><br />**Todas las fuentes de medios, incluidas las orgánicas:** Toda tu base de usuarios está disponible para reportarla al partner. |
| **Incluye** | Selecciona si los ingresos del evento o los valores de los parámetros se envían al partner en el postback. AppsFlyer puede enviar todos los parámetros del evento web enriquecido excepto el parámetro de ingresos (incluido en **af\_revenue**), o todos los parámetros, incluido el valor de ingresos (si está presente). |

> 📘 **Note**
>
> Si también ejecutas la etiqueta de Pinterest en tu sitio web, envía el mismo ID de evento tanto a AppsFlyer como a Pinterest para que AppsFlyer pueda deduplicar los eventos:
>
> * Incluye af\_customer\_event\_id en la carga útil del evento que envías a AppsFlyer, dentro de eventValue para el SDK web o de event\_value para la API S2S (server-to-server).
> * Envía el mismo valor en el evento de etiqueta correspondiente.
>
> AppsFlyer reenvía este valor a Pinterest como ID de evento. Pinterest lo usa entonces para deduplicar el evento del lado del servidor que recibe de AppsFlyer frente al evento de etiqueta, de modo que AppsFlyer cuente la conversión una sola vez.
>
> Si no envías af\_customer\_event\_id, AppsFlyer genera un ID de evento automáticamente. Este ID no coincidirá con los eventos de tu etiqueta.
>
> Para obtener más información, consulta Integrar AppsFlyer Web SDK.

5. Haz clic en **Agregar evento** para añadir un evento a la lista.

<div data-zendesk-anchors="set-up-pinterest=configurar-la-integraci%C3%B3n h_01KV339A5ZGK96JNCNR78PDMNH=configurar-la-integraci%C3%B3n integration-tab=pesta%C3%B1a-de-integraci%C3%B3n h_01KV339A67N4436STPW1VJR585=pesta%C3%B1a-de-integraci%C3%B3n activate-partner=activar-socio h_01KV339A67H0DSSJ3P84PXGQ2F=activar-socio inapp-event-settings=configuraci%C3%B3n-de-eventos-in-app h_01KV339A68YZBZZ73T8XTBE6BR=configuraci%C3%B3n-de-eventos-in-app inapp-event-postbacks=habilitar-la-atribuci%C3%B3n-por-impresiones h_01KV339A6BN0CWYX7GCJ19RN0J=habilitar-la-atribuci%C3%B3n-por-impresiones" />
