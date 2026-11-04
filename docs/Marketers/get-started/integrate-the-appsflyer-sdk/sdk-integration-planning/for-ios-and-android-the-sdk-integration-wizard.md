---
title: 'Para iOS y Android: el asistente de integración de SDK'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2024-04-10T12:17:00Z'
  edited_at: '2026-08-22T00:15:03Z'
  id: 24073235369617
  locale: es
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/es/articles/24073235369617
---
> **At a glance:** Crea y prueba automáticamente tu código de integración del SDK.

<div id="about-the-sdk-integration-wizard" />

## Acerca del asistente de integración de SDK

Deja que nuestro <Anchor target="_blank" href="https://dj.dev.appsflyer.com/?sourceos=android&utm_source=kb&utm_medium=sdk-int-wizard-orvw">asistente de integración del SDK</Anchor> guíe al Desarrollador de apps a través del proceso de integración del SDK. El desarrollador de apps solo tiene que proporcionar algunas credenciales y opciones de personalización, y el asistente genera fragmentos de código para copiarlos y pegarlos en el proyecto.

Este artículo te permite recopilar y enviar al Desarrollador de apps todos los datos de entrada y las credenciales que requieren los flujos del asistente de integración. El asistente admite dos viajes para desarrolladores:

* [El viaje del desarrollador de instalación e integración](#el-flujo-de-instalación-e-integración): el asistente lleva al desarrollador desde la instalación hasta la prueba satisfactoria de la integración.
* [El viaje del desarrollador de eventos in-app](#el-flujo-de-adición-de-eventos-in-app): el asistente guía al desarrollador desde la definición de eventos in-app hasta la prueba satisfactoria de su transmisión a AppsFlyer.

<div id="the-installation-and-integration-flow" />

## El flujo de instalación e integración

Una vez que el desarrollador de apps haya completado correctamente la instalación y la configuración con el asistente de integración, el SDK de AppsFlyer estará listo para empezar a enviar datos de atribución. Para verificar que la integración se ha completado correctamente, el flujo incluye una prueba que comprueba si un "evento de instalación" se reporta correctamente a AppsFlyer cuando se instala tu app.

La tabla siguiente enumera las preguntas que los desarrolladores deben responder durante la configuración del asistente. Usa las instrucciones especificadas en la tabla para recopilar la información necesaria y proporcionarla a los desarrolladores.

| Preguntas | Descubre más |
| --- | --- |
| ¿Cuál es tu ID de app? (Requerido) | <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer#introduce-los-detalles-de-la-aplicación">Descubre cómo obtener el ID de app en cada tienda.</Anchor> |
| ¿Cuál es tu clave de desarrollador de AppsFlyer? (Obligatoria) | <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#recuperar-la-clave-de-desarrollo">Descubre cómo obtener la clave de desarrollador.</Anchor> |
| ¿Qué modo de SDK quieres integrar? ¿Normal o estricto? | <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#strictmode-sdk">Descubre los modos del SDK</Anchor>. |
| ¿Debe el SDK obtener datos de conversión? | <Anchor target="_blank" href="/marketers/es/docs/get-conversion-data-using-appsflyer-sdk-overview">Descubre los datos de conversión en el SDK</Anchor>. |
| ¿Debe el SDK recibir la confirmación de que se ha iniciado correctamente? | Descubre el método de inicio del SDK con un controlador de finalización ([Android](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#starting-with-a-response-listener), [iOS](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#start-with-completion-handler)). |
| ¿Debe el SDK ser compatible con AppTrackingTransparency (ATT)? | <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">Descubre más sobre ATT</Anchor>. |
| ¿Cuál es tu token de autenticación v2 de AppsFlyer? (Solo es obligatorio si sigues el flujo de prueba automático.) | <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens#cómo-llegar-a-la-página-de-tokens">Descubre cómo recuperar tu token v2</Anchor>. |

<div id="the-add-in-app-event-flow" />

## El flujo de adición de eventos in-app

Después de que el desarrollador de apps complete el asistente de instalación e integración, el SDK de AppsFlyer se integrará correctamente en tu app. El flujo incluye una prueba de evento in-app que confirma que AppsFlyer lo recibe cuando se instala la app.

La tabla siguiente enumera las preguntas que los desarrolladores deben responder durante la configuración del asistente. Usa las instrucciones especificadas en la tabla para recopilar la información necesaria y proporcionársela a los desarrolladores.

| Preguntas | Descubre más |
| --- | --- |
| Elige el nombre del evento y sus parámetros | <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer#introduce-los-detalles-de-la-aplicación">Descubre qué eventos predefinidos tienes disponibles.</Anchor> La descripción de cada evento incluye sus parámetros habituales.  <br />También puedes usar nuestro   <br />[generador de eventos in-app](https://evgen.appsflyer.com/). |
| ¿Debe el SDK recibir una confirmación de que AppsFlyer ha recibido el evento in-app? | Más información sobre el código que verifica que los eventos se han recibido correctamente en AppsFlyer (<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-android#handling-event-submission-success-and-failure">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-ios#handling-event-submission-success-and-failure">iOS</Anchor>). |
| ¿Cuál es tu token de autenticación v2 de AppsFlyer? (Solo es obligatorio si sigues el flujo de prueba automático.) | <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens#cómo-llegar-a-la-página-de-tokens">Descubre cómo recuperar tu token v2</Anchor>. |

<div id="traits-and-limitations" />

## Especificaciones y limitaciones

| Rasgo | Comentarios |
| --- | --- |
| Plan Zero | El asistente de integración del SDK no está incluido en el <Anchor target="_blank" href="/marketers/es/docs/account-management-plans-payments-and-billing#appsflyer-plans">plan Zero</Anchor>. |

<div data-zendesk-anchors="about-the-sdk-integration-wizard=acerca-del-asistente-de-integraci%C3%B3n-de-sdk h_01J6730Y7WE1AJXNXFZ0QX23T8=acerca-del-asistente-de-integraci%C3%B3n-de-sdk the-installation-and-integration-flow=el-flujo-de-instalaci%C3%B3n-e-integraci%C3%B3n h_01J5K2A8BZS9CTZA45FB5VX8C0=el-flujo-de-instalaci%C3%B3n-e-integraci%C3%B3n the-add-in-app-event-flow=el-flujo-de-adici%C3%B3n-de-eventos-in-app h_01J5K2CG0H1G0BCSWHBJ8DPQWA=el-flujo-de-adici%C3%B3n-de-eventos-in-app traits-and-limitations=especificaciones-y-limitaciones h_01J6S6HS0H0M6GQ81WGZ3XT0P9=especificaciones-y-limitaciones" />
