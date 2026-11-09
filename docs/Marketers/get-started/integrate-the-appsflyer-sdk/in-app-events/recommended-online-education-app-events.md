---
title: Eventos de aplicación recomendados para educación en línea
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
  created_at: '2021-04-28T12:35:57Z'
  edited_at: '2026-08-12T12:01:36Z'
  id: 360019794378
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/360019794378
---
> **De un vistazo:** Mide la calidad de tus usuarios a lo largo de su trayectoria de usuario registrando estos eventos in-app sugeridos para tu aplicación de educación en línea.

<div id="-online-education" />

## <Image alt="educación.png" src="https://files.readme.io/fb036c8f3b0cb4cc06a5284c26089bbb361273ab628bc5b740692bc49e7a2c40-20659493109393.png" width="100px" /> Educación en línea

Las aplicaciones de educación en línea permiten a los usuarios aprender a distancia. Los eventos típicos que recomendamos registrar incluyen el registro, tutoriales y cursos completados y certificados recibidos.

Registrar estos eventos puede ayudarte a determinar:

* Qué cursos prefieren los usuarios y brindarte ideas para el targeting.
* Qué usuarios pueden ser reorientados y recordarles que tienen tutoriales adicionales para completar un curso.
* Qué cursos y certificados son los más solicitados.

<div id="important" />

> 🚧 **¡Importante!**
>
> * Asegúrate de leer las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#configuración-de-eventos-in-app">instrucciones</Anchor> para marketers sobre la implementación de eventos in-app.
> * Para agilizar el proceso de implementación, usa nuestro <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=online_education">generador de eventos in-app</Anchor>. Esta herramienta incluye todos los eventos in-app típicos que se describen en este artículo y te permite modificar los eventos de acuerdo con tus necesidades comerciales. Una vez completado, comparte el archivo con tu desarrollador.
> * Para cada evento recomendado incluido en este artículo, hay <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=online_education&view=code">ejemplos de código</Anchor> para desarrolladores de iOS, Android y Unity.
> * Puedes encontrar instrucciones detalladas para tu desarrollador en el **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">centro para desarrolladores de AppsFlyer</Anchor>.**
>
> Para más información sobre cómo registrar eventos in-app, consulta la <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">guía Eventos in-app enriquecidos</Anchor>.

<Image align="center" alt="Diagrama de flujo del recorrido del usuario de la aplicación de educación en línea para los eventos recomendados" src="https://files.readme.io/a913f14a20a52d7d70a96be7601fd264650f790337ceb83b9c53fd0006afc8e1-360020170478.png" />

<div id="recommended-structures-for-predefined-events" />

## Estructuras recomendadas para eventos predefinidos

La siguiente sección proporciona una lista de estructuras de eventos que son típicas de la vertical de educación en línea. Cada estructura incluye un nombre de evento predefinido y los parámetros del evento sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="login-af_login" />

<Accordion title="Acceso (af_login)">

**Finalidad**

Comprender la retención de tus usuarios registrados.

**Disparador**

Cuando el usuario accede correctamente.

**Parámetros del evento**

Se puede enviar sin ningún parámetro adicional.

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Finalidad**

Descubrir cuántos usuarios instalaron la aplicación y completaron el proceso de registro, y qué métodos de registro prefieren tus usuarios.

**Disparador**

Cuando el usuario completa el proceso de registro.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_registration\_method | El tipo de método de registro | correo electrónico, facebook |

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="Finalización del tutorial (af_tutorial_completion)">

**Finalidad**

Registrar este evento puede ayudarte a determinar:

* Con qué temas pueden tener problemas los usuarios.
* Qué tutoriales no dan buenos resultados y mejorarlos.
* Asociar la actividad general de los usuarios con dimensiones como los ingresos.

**Disparador**

* Cuando un usuario finaliza el tutorial
* Cuando un usuario comienza el tutorial, pero lo abandona sin finalizarlo

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_success | Si el usuario completó el tutorial o no. | Sí |
| af\_tutorial\_id | ID del tutorial | 3 |
| af\_content | Nombre del tutorial | algebra |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Finalidad**

Registrar las compras in-app realizadas por los usuarios puede ayudarte a:

* Determinar el valor de vida útil (LTV) de tus usuarios y el ROI de tus campañas en todas las agencias y redes de publicidad.
* Determinar qué ofertas son las más populares entre tus usuarios.
* Establecer referencias cruzadas entre las campañas y los artículos comprados a fin de optimizar el targeting de las campañas.

Para reportar un evento que incluye varios elementos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.

**Activador**

Cuando el usuario llega a la página de agradecimiento después de una compra exitosa.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Los ingresos estimados de la compra | 250.99 |
| af\_currency | Código de moneda | USD (Dólar estadounidense) |
| af\_content\_id | ID del elemento | 001, 092 |
| order\_id | ID del pedido | 9277 |
| af\_receipt\_id | ID del recibo | 9277 |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estructuras recomendadas para eventos personalizados

La siguiente sección proporciona una lista de estructuras de eventos que incluye nombres de eventos personalizados y los parámetros de eventos sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="complete-exercise-complete_excercise" />

<Accordion title="Completar el ejercicio (complete_excercise)">

**Finalidad**

Registra este evento y compáralo con otros datos para obtener más información sobre tus usuarios. Por ejemplo, puedes saber cuántos usuarios comienzan pero no terminan un ejercicio.

**Disparador**

Cuando el usuario completa un ejercicio.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| course\_name | Nombre del curso | algebra |
| exercise\_name | Nombre del ejercicio | 2 |

</Accordion>

<div id="course-completed-course_completed" />

<Accordion title="Curso completado (course_completed)">

**Finalidad**

Registra este evento y compáralo con otros datos para obtener más información sobre tus usuarios. Por ejemplo, puedes saber cuántos usuarios comienzan pero no terminan un curso.

**Disparador**

Cuando el usuario completa un curso.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| course\_name | Nombre del curso | algebra |
| course\_completed | Si el curso se completó. | Sí |

</Accordion>

<div id="certificate-issued-certificate_issued" />

<Accordion title="Certificado emitido (certificate_issued)">

**Finalidad**

Registra este evento y compáralo con otros datos para obtener más información sobre tus usuarios. Por ejemplo, puedes saber cuántos usuarios terminan un curso y luego reorientarlos para el próximo curso.

**Disparador**

Cuando se emite un certificado al usuario.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| course\_name | Nombre del curso | algebra |
| certificate\_received | Si el certificado se expidió | Sí |

</Accordion>

<div data-zendesk-anchors="online-education=-educaci%C3%B3n-en-l%C3%ADnea h_01HGTAYQ9V4Z5YEWTNCZPVMVMF=-educaci%C3%B3n-en-l%C3%ADnea h_01HGTAYQ9VJ6GS1XVQPG198C8Z=importante recommended-structures-for-predefined-events=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAYQ9VS0DYFSFNEPDCDVTG=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAYQ9VX44FA5HHBT6DGA2R=login-af_login h_01HGTAYQ9VR78MHTJZFVFCKCV4=complete-registration-af_complete_registration h_01HGTAYQ9VE8ZBF1DJ2AAA1HFF=tutorial-completion-af_tutorial_completion h_01HGTAYQ9VSXMR0J1T0KN6WK2G=purchase-af_purchase recommended-structures-for-custom-events=estructuras-recomendadas-para-eventos-personalizados h_01HGTAYQ9V93HET4AZ7XGE0E3V=estructuras-recomendadas-para-eventos-personalizados h_01HGTAYQ9VBZZJ5TC1W2S0MK3P=complete-exercise-complete_excercise h_01HGTAYQ9WQJBBEYKDJ8DP9E31=course-completed-course_completed h_01HGTAYQ9WVXX20FNDZWHGDNZ2=certificate-issued-certificate_issued" />
