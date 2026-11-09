---
title: Eventos de aplicación recomendados para finanzas y banca
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-04-27T12:58:44Z'
  edited_at: '2026-08-12T12:01:22Z'
  id: 360019598337
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/360019598337
---
> **De un vistazo:** Mide la calidad de tus usuarios a lo largo de su trayectoria de usuario registrando estos eventos in-app sugeridos para tu aplicación de finanzas y banca.

<div id="-finance-and-banking" />

## <Image alt="bancos.png" src="https://files.readme.io/260638f807a43f42c6ff99bb72b8d4113b2df09436b9322a820888ad3f8a01ae-20659476893969.png" width="100px" /> Finanzas y banca

Las aplicaciones de finanzas y banca ofrecen a los usuarios la posibilidad de llevar a cabo una amplia gama de objetivos relacionados con las finanzas, entre ellos, la suscripción de tarjetas de crédito nuevas o la solicitud de préstamos. Los típicos eventos que recomendamos registrar incluyen aperturas de cuentas, solicitudes de tarjetas de crédito y solicitudes de préstamos.

Registrar estos eventos puede ayudarte a determinar:

* Qué tipo de cuenta prefieren los usuarios y brindarte ideas para el retargeting.
* Qué beneficios buscan los usuarios en una tarjeta de crédito.
* Para qué necesitan los usuarios asistencia financiera y cuánta asistencia quieren.

<div id="important" />

> 🚧 **¡Importante!**
>
> * **Una nota de nuestros abogados**: los datos sanitarios se consideran "Datos restringidos" y se consideran una categoría especial de datos en muchas jurisdicciones. Como tales, a los clientes se les prohíbe enviar a AppsFlyer dichos datos.
> * Asegúrate de leer las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#configuración-de-eventos-in-app">instrucciones</Anchor> para marketers sobre la implementación de eventos in-app.
> * Para agilizar el proceso de implementación, usa nuestro <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=finance_banking">generador de eventos in-app</Anchor>. Esta herramienta incluye todos los eventos in-app típicos que se describen en este artículo y te permite modificar los eventos de acuerdo con tus necesidades comerciales. Una vez completado, comparte el archivo con tu desarrollador.
> * Para cada evento recomendado incluido en este artículo, hay <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=finance_banking&view=code">ejemplos de código</Anchor> para desarrolladores de iOS, Android y Unity.
> * Puedes encontrar instrucciones detalladas para tu desarrollador en el **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">centro para desarrolladores de AppsFlyer</Anchor>.**
>
> Para más información sobre cómo registrar eventos in-app, consulta la <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">guía Eventos in-app enriquecidos</Anchor>.

<Image align="center" alt="Diagrama_de_flujo_para_eventos_recomendados recorrido_del_usuario_de_la_aplicación_de_finanzas_y_banca" src="https://files.readme.io/722d2a3df606df1c61f86c7e8e1524566de8fbfd0ceb48e4cd5913a0b3ac9283-360020063337.png" />

<div id="recommended-structures-for-predefined-events" />

## Estructuras recomendadas para eventos predefinidos

La siguiente sección proporciona una lista de estructuras de eventos que son típicas de la vertical de finanzas y bancos. Cada estructura incluye un tipo de evento predefinido y los parámetros del evento predefinidos sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="login-af_login" />

<Accordion title="Acceso (af_login)">

**Finalidad**

Comprender la retención de tus usuarios registrados.

**Activador**

Cuando el usuario accede correctamente.

**Parámetros del evento**

Se puede enviar sin ningún parámetro adicional.

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Finalidad**

Descubrir cuántos usuarios instalaron la aplicación y completaron el proceso de registro, y qué métodos de registro prefieren tus usuarios.

**Activador**

Cuando el usuario completa el proceso de registro.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_registration\_method | El tipo de método de registro | correo electrónico, facebook |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estructuras recomendadas para eventos personalizados

La siguiente sección proporciona una lista de estructuras de eventos que incluye nombres de eventos personalizados y los parámetros de eventos sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="registration-verified-registration_verified" />

<Accordion title="Registro verificado (registration_verified)">

**Finalidad**

Puedes registrar este evento y compararlo con otros datos para aprender más acerca de tus usuarios. Por ejemplo, puedes saber cuántos usuarios se registran pero no son aceptados. 

**Disparador**

Cuando se verifique el registro.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| submit\_registration | Tipo de método de registro verificado. No completes la información de identificación personal (PII). | correo electrónico, facebook |

</Accordion>

<div id="submit-account-application-submit_account_application" />

<Accordion title="Enviar solicitud de cuenta (submit_account_application)">

**Finalidad**

Puedes registrar este evento y compararlo con otros datos para aprender más acerca de tus usuarios. Por ejemplo, puedes saber cuántos usuarios se registran pero no solicitan abrir una cuenta.

**Disparador**

Cuando el usuario completa el proceso de solicitud de cuenta.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| account\_type | Tipo de cuenta solicitada | savings |
| application\_method | Donde se hizo la solicitud | aplicación |
| PII\_type | Tipo de ID utilizado durante la solicitud | passport |

</Accordion>

<div id="open-account-success-open_account_success" />

<Accordion title="Cuenta abierta satisfactoriamente (open_account_success)">

**Finalidad**

Puedes registrar este evento y compararlo con otros datos para aprender más acerca de tus usuarios. Por ejemplo, puedes saber cuántos usuarios solicitan cuentas y son aceptados, y tratar de mejorar el embudo o volver a captar a esos usuarios más tarde.

**Disparador**

Cuando se acepta la solicitud de usuario y se abre la cuenta.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| account\_type | Tipo de cuenta abierta | savings |
| application\_method | Donde se hizo la solicitud | aplicación |
| PII\_type | Tipo de ID utilizado durante la solicitud | identification card |

</Accordion>

<div id="open-account-rejected-open_account_rejected" />

<Accordion title="Cuenta abierta rechazada (open_account_rejected)">

**Finalidad**

Puedes registrar este evento y compararlo con otros datos para aprender más acerca de tus usuarios. Por ejemplo, puedes saber cuántos usuarios solicitan cuentas pero no son aceptados, y tratar de mejorar el embudo o volver a captar a esos usuarios más tarde.

**Activador**

Cuando el usuario completa el proceso de registro.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| account\_type | Tipo de cuenta solicitada | savings |

</Accordion>

<div data-zendesk-anchors="finance-and-banking=-finanzas-y-banca h_01HGTAXN8PV7TPNRBWD593BR4K=-finanzas-y-banca h_01HGTAXN8Q652HG7412X583KWX=importante recommended-structures-for-predefined-events=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAXN8QWEWD86FMF6GEZNZD=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAXN8Q3K0EFGXZ41XZH438=login-af_login h_01HGTAXN8Q6KFDPB8XSVT3F9E8=complete-registration-af_complete_registration recommended-structures-for-custom-events=estructuras-recomendadas-para-eventos-personalizados h_01HGTAXN8Q47F6CXXBEVCDPSBA=estructuras-recomendadas-para-eventos-personalizados h_01HGTAXN8QB911JMER3EV7RGTM=registration-verified-registration_verified h_01HGTAXN8QCYR0BQ3Q3VN0EQ9X=submit-account-application-submit_account_application h_01HGTAXN8QJ4DKQS2FY9KY0AX4=open-account-success-open_account_success h_01HGTAXN8QK1P5QYEN5SNBQ5ED=open-account-rejected-open_account_rejected" />
