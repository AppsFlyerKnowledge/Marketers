---
title: Eventos de aplicación recomendados para préstamos P2P
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
  created_at: '2021-04-28T09:01:59Z'
  edited_at: '2026-08-12T12:01:39Z'
  id: 360019614017
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/360019614017
---
> **De un vistazo:** Mide la calidad de tus usuarios a lo largo de su trayectoria de usuario registrando estos eventos in-app sugeridos para tu aplicación de préstamos P2P.

<div id="-p2p-lending" />

## <Image alt="InApp_Events_lending.png" src="https://files.readme.io/e3465ee913a65a215f1c224db20d4f1fd61fd0bf488b798073c94b4e8387d252-20659507679889.png" width="100px" /> Préstamos P2P

Los préstamos P2P son una manera en que las personas y las empresas prestan y toman prestado dinero entre ellas. Los eventos típicos que sugerimos registrar son las actividades de prestamistas y prestatarios individuales, los tipos de préstamos que ofrecen las personas y las tasas de aceptación y rechazo de préstamos.

Los datos que recopilas del registro de eventos permiten destacar los prestatarios confiables y ofrecerles mejores tasas de interés. De manera similar, podrás ver quiénes son los prestamistas más activos y ofrecerles tarifas más bajas. Además, una vez que sepas cuáles son los tipos de préstamos más populares entre los usuarios, podrás lanzar campañas de marketing dirigidas a tales audiencias.

<div id="important" />

> 🚧 **¡Importante!**
>
> * Asegúrate de leer las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#configuración-de-eventos-in-app">instrucciones</Anchor> para marketers sobre la implementación de eventos in-app.
> * Para agilizar el proceso de implementación, usa nuestro <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=p2p_lending">generador de eventos in-app</Anchor>. Esta herramienta incluye todos los eventos in-app típicos que se describen en este artículo y te permite modificar los eventos de acuerdo con tus necesidades comerciales. Una vez completado, comparte el archivo con tu desarrollador.
> * Para cada evento recomendado incluido en este artículo, hay <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=p2p_lending&view=code">ejemplos de código</Anchor> para desarrolladores de iOS, Android y Unity.
> * Puedes encontrar instrucciones detalladas para tu desarrollador en el **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">centro para desarrolladores de AppsFlyer</Anchor>.**
>
> Para más información sobre cómo registrar eventos in-app, consulta la <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">guía Eventos in-app enriquecidos</Anchor>.

<Image align="center" alt="Diagrama de flujo del recorrido del usuario de la app de préstamos P2P para eventos recomendados" src="https://files.readme.io/597a98cf1df450e9e14eb32d8bdc14df647551ca91a2baca78895ca740eb805c-360020063617.png" />

<div id="recommended-structures-for-predefined-events" />

## Estructuras recomendadas para eventos predefinidos

La siguiente sección proporciona una lista de estructuras de eventos que son típicas de la vertical de préstamos P2P. Cada estructura incluye un tipo de evento predefinido y los parámetros del evento predefinidos sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Finalidad**

Determinar cuántos usuarios verifican realmente su identidad después de registrarse. Puedes atribuir estos usuarios a campañas y ver de las cuáles campañas generan usuarios activos.

**Disparador**

Cuando se apruebe el registro del usuario.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_registration\_method | El tipo de método de registro | correo electrónico, facebook |

</Accordion>

<div id="login-af_login" />

<Accordion title="Acceso (af_login)">

**Finalidad**

Comprender la retención de tus usuarios registrados.

**Disparador**

Cuando el usuario accede correctamente.

**Parámetros del evento**

Se puede enviar sin ningún parámetro adicional.

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estructuras recomendadas para eventos personalizados

La siguiente sección proporciona una lista de estructuras de eventos que incluye nombres de eventos personalizados y los parámetros de eventos sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="registration-submitted-registration_submitted" />

<Accordion title="Registro enviado (registration_submitted)">

**Finalidad**

Dado que los préstamos P2P son vulnerables al uso indebido, los usuarios primero deben verificar su identidad. Para eso, deben enviar una solicitud de registro. Este evento puede ayudarte a:

* Determinar cuántos usuarios se registran, pero nunca verifican su cuenta.
* Ver la correlación entre el método de registro, como correo electrónico, Facebook, Google, y las tasas de verificación.

**Activador**

Después de que el usuario envía una solicitud para registrarse.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_registration\_method | El tipo de método de registro | correo electrónico, facebook |

</Accordion>

<div id="fill-loan-form-fill_loan_form_form_name" />

<Accordion title="Completa el formulario de préstamo (fill_loan_form_&lt;FORM_NAME>)">

**Finalidad**

Determinar la tasa de abandono y reorienta a los prestatarios que no completen sus solicitudes de préstamo.

Cuando envíes el evento, incluye el nombre del formulario en el nombre del evento.

**Disparador**

Cuando un prestatario envía un formulario.

**Parámetros del evento**

Se puede enviar sin ningún parámetro adicional.

<div id="note" />

> 📘 **Nota**
>
> Es muy recomendable que asocies los préstamos con los prestamistas. Para eso, asegúrate de establecer el ID de usuario de cliente. <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">Establecer el ID de usuario de cliente</Anchor> es tu manera de hacer coincidir los prestamistas con los usuarios de tu aplicación cuando aparecen en AppsFlyer. Al establecer el ID de usuario de cliente, te aseguras de que todos los eventos se envíen con dicho ID.

<div id="submit-loan-application-submit_loan_application" />

<Accordion title="Enviar solicitud de préstamo (submit_loan_application)">

**Finalidad**

Este evento puede ayudarte a:

* Determinar la cantidad total de solicitudes de préstamos en tu aplicación.
* Conocer el importe máximo, mínimo y promedio de las solicitudes de préstamos.
* Determinar qué tipos de préstamos solicitan las personas.

**Disparador**

Cuando el usuario envía con éxito una solicitud de préstamo.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| loan\_id | ID del préstamo | 1735102 |
| loan\_amount | Cantidad solicitada | 1000 |
| tipo de préstamo | Período de préstamo | 3 meses |

</Accordion>

<div id="loan-form-loan_form" />

<Accordion title="Formulario de préstamo (loan_form)">

**Finalidad**

Revisar las solicitudes de préstamo enviadas por los prestatarios.

**Disparador**

Cuando el prestatario envía con éxito una solicitud de préstamo.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| loan\_id | ID del préstamo | 1735102 |
| loan\_amount | Cantidad solicitada | 1000 |
| tipo de préstamo | Período de préstamo | 3 meses |

</Accordion>

<div id="submit-credit-check-submit_credit_check" />

<Accordion title="Enviar verificación de crédito (submit_credit_check)">

**Finalidad**

Comprobar el historial financiero del prestatario (por ejemplo, crédito pasado, hábitos de pago y tipos de préstamos) para evaluar el nivel de riesgo.

**Disparador**

Después de que el prestamista recibe una solicitud de préstamo.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| loan\_id | ID del préstamo | 1735102 |
| loan\_amount | Cantidad solicitada | 1000 |
| tipo de préstamo | Período de préstamo | 3 meses |

</Accordion>

<div id="loan-accepted-loan_accepted" />

<Accordion title="Préstamo aceptado (loan_accepted)">

**Finalidad**

Conocer las tendencias en préstamos y otras métricas. Este evento puede ayudarte a determinar:

* Qué tipo de préstamos se aceptan.
* El monto solicitado en los préstamos que se aprueban.
* Qué prestamistas aceptan la mayor cantidad de préstamos

**Disparador**

Cuando se acepta un préstamo.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| loan\_id | ID del préstamo | 1735102 |
| loan\_amount | Cantidad solicitada | 1000 |
| tipo de préstamo | Período de préstamo | 3 meses |

</Accordion>

<div id="loan-rejected-loan_rejected" />

<Accordion title="Préstamo rechazado (loan_rejected)">

**Finalidad**

Comprender los motivos por los que se rechazan los préstamos. Podrás ver la correlación entre el importe y el período del préstamo y las tasas de rechazo. También podrás usar la función de retargeting con los usuarios a quienes les hayan rechazado un préstamo y sugerirles un préstamo más pequeño.

**Disparador**

Cuando un prestamista rechaza un préstamo.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| loan\_id | ID del préstamo | 1735102 |

</Accordion>

<div id="payment-payment" />

<Accordion title="Pago (payment)">

**Finalidad**

Te ayuda a marcar a los prestatarios como confiables. Los prestatarios confiables son aquellos que cumplen con la obligación de pagar los préstamos. Podrás atribuir los prestatarios a campañas y saber cuáles de las campañas generaron prestatarios confiables. Además, este evento puede ayudarte a recopilar datos sobre el importe mínimo, máximo y promedio de los pagos.

**Disparador**

Cuando un prestatario realiza un pago de su préstamo.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| loan\_id | ID del préstamo | 1735102 |
| payment\_amount | Importe pagado | 100 |
| id de pago | ID del pago | AE12SF |

</Accordion>

<div id="payment-completed-payment_completed" />

<Accordion title="Pago completado (payment_completed)">

**Finalidad**

Destacar a los prestatarios que siguen su obligación de cubrir un préstamo. También puedes usar la función de retargeting con tales prestatarios y ofrecerles una menor tasa de interés u otras promociones.

**Disparador**

Cuando un préstamo se devuelve por completo.

**Parámetros del evento**

| Nombre de campo | Descripción | Valor de ejemplo |
| --- | --- | --- |
| loan\_id | ID del préstamo | 1735102 |

</Accordion>

<div id="payment-received-payment_received" />

<Accordion title="Pago recibido (payment_received)">

**Finalidad**

Verificar que el prestatario complete los pagos del préstamo de acuerdo con los términos del acuerdo del préstamo.

**Disparador**

Cuando un prestatario realiza un pago de su préstamo.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| loan\_id | ID del préstamo | 1735102 |
| payment\_amount | Importe pagado | 100 |
| id de pago | ID del pago | AE12SF |

</Accordion>

</Accordion>

<div data-zendesk-anchors="p2p-lending=-pr%C3%A9stamos-p2p h_01HGTAY6DHKXCTP52P2EPHXN5H=-pr%C3%A9stamos-p2p h_01HGTAY6DHDDG3MVCXEM705MTK=importante recommended-structures-for-predefined-events=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAY6DH1V6S5NKJEFCVW1PF=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAY6DHHGW3M6NQ0K3J6HTC=complete-registration-af_complete_registration h_01HGTAY6DHZTKJR94T8B6WEYZ6=login-af_login recommended-structures-for-custom-events=estructuras-recomendadas-para-eventos-personalizados h_01HGTAY6DH00660DSP5RX3PA9C=estructuras-recomendadas-para-eventos-personalizados h_01HGTAY6DHETK285KPGW54YV5Z=registration-submitted-registration_submitted h_01HGTAY6DHCQKWMG4YRZDHBMZT=fill-loan-form-fill_loan_form_form_name h_01HGTAY6DHHNJ9EKV3FQ6BKKBF=nota h_01HGTAY6DH4D6NV1NHV5717CDH=submit-loan-application-submit_loan_application h_01HGTAY6DHVWFEFJYB4TGK1B9W=loan-form-loan_form h_01HGTAY6DH7V1JSPCDHDTFR4YA=submit-credit-check-submit_credit_check h_01HGTAY6DH22HRQQJ5NQ2T71QM=loan-accepted-loan_accepted h_01HGTAY6DHTMJ22KQSXHNBJ8B3=loan-rejected-loan_rejected h_01HGTAY6DHD8A2H61XKFPXW589=payment-payment h_01HGTAY6DJWJDQBW52RPG7W7P4=payment-completed-payment_completed h_01HGTAY6DJE0K3VC0YNVWAXT29=payment-received-payment_received" />
