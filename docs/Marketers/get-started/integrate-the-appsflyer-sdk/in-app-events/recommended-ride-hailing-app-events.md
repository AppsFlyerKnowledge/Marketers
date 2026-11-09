---
title: Eventos de aplicación recomendados para transporte privado
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
  created_at: '2021-04-29T08:42:34Z'
  edited_at: '2026-08-12T12:01:42Z'
  id: 360019651957
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/360019651957
---
> **De un vistazo:** Mide la calidad de tus usuarios a lo largo de su trayectoria de usuario registrando estos eventos in-app sugeridos para tu aplicación de transporte privado.

<div id="-ride-hailing" />

## <Image alt="Eventos_en_la_aplicación_paseo.png" src="https://files.readme.io/3901cfcc0cc821cc9c93edbe806bc2d570698be366b76b3710cb60e9aa190d91-20659532208401.png" width="100px" /> Servicios de transporte

Recientemente, las aplicaciones de transporte privado se han vuelto muy populares, en especial en zonas urbanas donde la mayoría de los residentes no tienen automóvil. Los eventos típicos que recomendamos registrar incluyen las solicitudes y reservas de viajes.

Registrar estos eventos puede ayudarte a determinar:

* Cómo interactúan los pasajeros y los conductores.
* Los países donde más personas usan tu servicio de transporte privado.
* Las métricas relacionadas con precios, viajes y distancias de viaje.

<div id="important" />

> 🚧 **¡Importante!**
>
> * Asegúrate de leer las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#configuración-de-eventos-in-app">instrucciones</Anchor> para marketers sobre la implementación de eventos in-app.
> * Para agilizar el proceso de implementación, usa nuestro <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ride_hailing">generador de eventos in-app</Anchor>. Esta herramienta incluye todos los eventos in-app típicos que se describen en este artículo y te permite modificar los eventos de acuerdo con tus necesidades comerciales. Una vez completado, comparte el archivo con tu desarrollador.
> * Para cada evento recomendado incluido en este artículo, hay <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ride_hailing&view=code">ejemplos de código</Anchor> para desarrolladores de iOS, Android y Unity.
> * Puedes encontrar instrucciones detalladas para tu desarrollador en el **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">centro para desarrolladores de AppsFlyer</Anchor>.**
>
> Para más información sobre cómo registrar eventos in-app, consulta la <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">guía Eventos in-app enriquecidos</Anchor>.

<Image align="center" alt="Diagrama de flujo del recorrido del usuario en una app de transporte con conductor para eventos recomendados" src="https://files.readme.io/5ec4efcc699ef8749e1d5cd6e693472713f3d7945a41e1601965d0e7cdb68706-4402678863377.png" />

<div id="recommended-structures-for-predefined-events" />

## Estructuras recomendadas para eventos predefinidos

La siguiente sección proporciona una lista de estructuras de eventos que son típicas de la vertical de transporte privado. Cada estructura incluye un tipo de evento predefinido y los parámetros del evento predefinidos sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Finalidad**

Este evento puede ayudarte a:

* Saber cuáles métodos de registro prefieren tus usuarios.
* Determinar cuántos usuarios efectivamente se registran después de descargar e instalar la aplicación.
* Ver las tendencias en cuanto al registro en distintos países para determinar en cuáles países es más probable que los usuarios utilicen tu aplicación

**Disparador**

Cuando el usuario completa el proceso de registro.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_registration\_method | La plataforma o el método mediante el cual se registra el usuario. | Facebook |
| código\_de\_país | Código del país (código de teléfono) | 66 |

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

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="Agregar información de pago (af_add_payment_info)">

**Finalidad**

Te ayuda a clasificar a los usuarios. Podrás hacer lo siguiente:

* Saber cuánto tarda un usuario en agregar su información de pago.
* Cuáles son los métodos de pago más populares, por ejemplo, tarjeta de crédito o billeteras electrónicas
* Configurar campañas y colaborar con los proveedores de métodos de pago más populares.

**Disparador**

Cuando el usuario agrega la información de pago correctamente en su cuenta.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_success | Si el método de pago fue exitoso. | Verdadero |
| tipo\_de\_tarjeta\_de\_crédito | Tipo de tarjeta de crédito (opcional) | Visa, Mastercard |
| payment\_method\_type | Tipo de método de pago | tarjeta de crédito, billetera electrónica |

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="Créditos gastados (af_spent_credits)">

**Finalidad**

El evento [Finalización de reserva de viaje](/docs/recommended-ride-hailing-app-events#ride-booking-completed-ride_booking_completed) incluye un parámetro llamado `credits_earned`. Este parámetro registra los créditos que un pasajero gana por cada viaje. A continuación, los pasajeros puede canjear estos créditos por vales o descuentos.

Este evento puede ayudarte a:

* Ver cuántos pasajeros canjean créditos por vales.
* Ver qué tipos de vales y descuentos prefieren los pasajeros.

**Activador**

Cuando un pasajero gasta créditos.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_content | Tipo de cupón o descuento | Entrada de cine individual |
| credits\_used | Cuántos créditos se usaron | 1000 |
| créditos\_restantes | Cuántos créditos quedan en la cuenta | 2090 |
| id\_de\_factura | El ID de la factura que se crea por gastar créditos | KO215123SD |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estructuras recomendadas para eventos personalizados

La siguiente sección proporciona una lista de estructuras de eventos que incluye nombres de eventos personalizados y los parámetros de eventos sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="ride-booking-requested-ride_booking_requested" />

<Accordion title="Reserva de viaje solicitada (ride_booking_requested)">

**Finalidad**

Este evento puede ayudarte a:

* Conocer los destinos populares
* Conocer las tendencias, adónde y desde dónde viajan las personas.
* Ver la distancia promedio de un viaje.
* Ver de qué ciudades, regiones y países proviene la mayor cantidad de usuarios.

Además, el registro de este evento, junto con otros eventos relacionados con la reserva, puede ayudarte a registrar las transacciones correctas. Luego, podrás comparar transacciones exitosas con transacciones fallidas. Por ejemplo, podrás ver cuántas reservas de viaje se solicitan y cuántas se finalizan o se cancelan.

**Activador**

Cuando el pasajero creó una solicitud de reserva de viaje.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Precio cotizado del viaje | 22.4 |
| af\_currency | Truemoney | SGD |
| af\_destination\_a | Punto de partida | Plaza Singapura |
| af\_destination\_b | Punto de llegada | Marina Bay Sands |
| distance | La distancia entre dos destinos | 5.2 |
| af\_content\_type | Tipo de transporte | Taxi |
| payment\_method\_type | Tipo de método de pago | tarjeta de crédito, billetera electrónica |
| af\_city | La ciudad donde se reserva el viaje | Singapur |
| af\_region | La región donde se reserva el viaje | SFA |
| af\_country | El país donde se reserva el viaje | Singapur |
| order\_id | ID del pedido | 135790 |

</Accordion>

<div id="ride-booking-confirmed-ride_booking_confirmed" />

<Accordion title="Reserva de viaje confirmada (ride_booking_confirmed)">

**Finalidad**

Este evento puede ayudarte a:

* Saber quiénes son los conductores más activos.
* Ver cuáles son los destinos más frecuentes entre conductores.
* Ver los precios de viajes promedio y totales de cada conductor.

Además, el registro de este evento, junto con los otros tres eventos relacionados con la reserva de viajes, puede ayudarte a entender mejor la actividad de los conductores. Podrás ver qué conductores confirman la mayor cantidad de solicitudes de reserva de viajes, qué conductores eligen viajes cortos en lugar de viajes largos, etc.

<div id="trigger" />

#### **Activador**

Cuando un conductor acepta la reserva.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Precio cotizado del viaje | 22.4 |
| af\_currency | Truemoney | SGD |
| af\_destination\_a | Punto de partida | Plaza Singapura |
| af\_destination\_b | Punto de llegada | Marina Bay Sands |
| distance | La distancia entre dos destinos | 5.2 |
| af\_content\_type | Tipo de transporte | Taxi |
| id\_del\_conductor | El ID del conductor que realizó el viaje | 1706 |
| payment\_method\_type | Tipo de método de pago | tarjeta de crédito, billetera electrónica |
| af\_city | La ciudad donde se reserva el viaje | Singapur |
| af\_region | La región donde se reserva el viaje | SFA |
| af\_country | El país donde se reserva el viaje | Singapur |
| af\_order\_id | ID del pedido | 135790 |

</Accordion>

<div id="ride-booking-canceled-ride_booking_canceled" />

<Accordion title="Reserva de viaje cancelada (ride_booking_canceled)">

**Finalidad**

Este evento puede ayudarte a:

* Registrar los conductores o pasajeros que cancelan viajes constantemente.
* Saber cuántos viajes se cancelan.
* Correlacionar la tasa de cancelación con atributos como el precio, el destino, la distancia y las ciudades.
* Conocer los motivos por los cuales se cancela un viaje.

**Activador**

Cuando se cancela la reserva.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Precio cotizado del viaje | 22.4 |
| af\_currency | Truemoney | SGD |
| af\_destination\_a | Punto de partida | Plaza Singapura |
| af\_destination\_b | Punto de llegada | Marina Bay Sands |
| distance | La distancia entre dos destinos | 5.2 |
| af\_content\_type | Tipo de transporte | Taxi |
| id\_del\_conductor | El ID del conductor que confirmó el viaje | 1706 |
| motivo\_de\_cancelación | El motivo por el cual se cancela el viaje | El precio es muy alto, el conductor no apareció, el pasajero no apareció |
| payment\_method\_type | Tipo de método de pago | tarjeta de crédito, billetera electrónica |
| af\_city | La ciudad donde se reserva el viaje | Singapur |
| af\_region | La región donde se reserva el viaje | SFA |
| af\_country | El país donde se reserva el viaje | Singapur |
| order\_id | ID del pedido | 135790 |
| cancelado\_por | Si al viaje lo cancela el pasajero o el conductor | Pasajero |

</Accordion>

<div id="ride-booking-completed-ride_booking_completed" />

<Accordion title="Reserva de viaje completada (ride_booking_completed)">

**Finalidad**

Este evento puede ayudarte a:

* Conocer cuánto gastan los pasajeros y cuánto ganan los conductores.
* Correlacionar los viajes finalizados con atributos como el destino, la distancia, el tipo de pago y el ID del conductor.
* Ver la distancia promedio y total para conductores y pasajeros.
* Comparar los viajes finalizados con los cancelados.
* Registrar la puntuación de los conductores.

**Activador**

Cuando el viaje se complete.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Precio cotizado del viaje | 22.4 |
| af\_currency | Truemoney | SGD |
| af\_destination\_a | Punto de partida | Plaza Singapura |
| af\_destination\_b | Punto de llegada | Marina Bay Sands |
| distance | La distancia entre dos destinos | 5.2 |
| af\_content\_type | Tipo de transporte | Taxi |
| id\_del\_conductor | El ID del conductor que realizó el viaje | 1706 |
| payment\_method\_type | Tipo de método de pago | tarjeta de crédito, billetera electrónica |
| af\_city | La ciudad donde se reserva el viaje | Singapur |
| af\_region | La región donde se reserva el viaje | SFA |
| af\_country | El país donde se reserva el viaje | Singapur |
| order\_id | ID del pedido | 135790 |
| credits\_earned | Los créditos que ganó el pasajero por finalizar un viaje | 248 |

</Accordion>

<div data-zendesk-anchors="ridehailing=-servicios-de-transporte h_01HGTAZ7J64RZE35JP8XPKMTPZ=-servicios-de-transporte h_01HGTAZ7J6N36EH492QDXCQYB1=importante recommended-structures-for-predefined-events=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAZ7J6FJ8R9VXKK0F1A1E1=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAZ7J6FQQKV7JB0Z9MG8CD=complete-registration-af_complete_registration h_01HGTAZ7J6YM8DJ96E7Q4M4Y8Q=login-af_login h_01HGTAZ7J67MNJ8T9B9W4NJ5Y9=add-payment-info-af_add_payment_info h_01HGTAZ7J6Z3EX03JTPZFHJJF6=spent-credits-af_spent_credits recommended-structures-for-custom-events=estructuras-recomendadas-para-eventos-personalizados h_01HGTAZ7J6Z6NE8D5A10CRJJH4=estructuras-recomendadas-para-eventos-personalizados h_01HGTAZ7J6WCY2BQJPSNSTJRQ0=ride-booking-requested-ride_booking_requested h_01HGTAZ7J78J1X3VAYMH8Q3ZBA=ride-booking-confirmed-ride_booking_confirmed trigger=activador h_01HGTAZ7J7C4R7A7KT2S95835J=activador h_01HGTAZ7J797KA791H1621F9TE=ride-booking-canceled-ride_booking_canceled h_01HGTAZ7J789CJ8P6X8B0V7A64=ride-booking-completed-ride_booking_completed" />
