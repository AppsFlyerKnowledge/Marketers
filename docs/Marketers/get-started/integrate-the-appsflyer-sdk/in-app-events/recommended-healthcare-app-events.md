---
title: Eventos de aplicación recomendados para el cuidado de la salud
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
  created_at: '2021-05-01T10:41:05Z'
  edited_at: '2026-08-12T12:01:29Z'
  id: 360019888518
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/360019888518
---
> **De un vistazo:** Mide la calidad de tus usuarios a lo largo de su trayectoria de usuario registrando estos eventos in-app de muestra para tu aplicación del cuidado de la salud.

<div id="-healthcare" />

## <Image alt="5669_Icono_de_salud_3.png" src="https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png" width="100px" /> Cuidado de la salud

Las aplicaciones para el cuidado de la salud permiten a los usuarios realizar tareas, como adquirir seguros de salud, reservar citas y recibir consejo médico. Los eventos típicos que sugerimos registrar incluyen inicios de sesión, registros y otros eventos generales sin información personal o de salud.

<div id="important" />

> 🚧 **¡Importante!**
>
> * **Una nota de nuestros abogados**: los datos sanitarios se consideran "Datos restringidos" y se consideran una categoría especial de datos en muchas jurisdicciones. Como tales, a los clientes se les prohíbe enviar a AppsFlyer dichos datos.
> * Asegúrate de leer las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#configuración-de-eventos-in-app">instrucciones</Anchor> para marketers sobre la implementación de eventos in-app.
> * Para agilizar el proceso de implementación, usa nuestro <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=healthcare">generador de eventos in-app</Anchor>. Esta herramienta incluye todos los eventos in-app típicos que se describen en este artículo y te permite modificar los eventos de acuerdo con tus necesidades comerciales. Una vez completado, comparte el archivo con tu desarrollador.
> * Para cada evento recomendado incluido en este artículo, hay <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=healthcare&view=code">ejemplos de código</Anchor> para desarrolladores de iOS, Android y Unity.
> * Encontrarás instrucciones detalladas para tu desarrollador en el <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">centro para desarrolladores de AppsFlyer</Anchor>.
>
> Para más información sobre cómo registrar eventos in-app, consulta la <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">guía Eventos in-app enriquecidos</Anchor>.

<Image align="center" alt="In_appEvents_UserJourneys_-_Copy_of_Healthcare__1_.png" src="https://files.readme.io/54174e697c8dfe2d0d388c19fdd5fa0fbf9703c0155b9c250b40b5d0bcf19698-8232949117073.png" />

<div id="recommended-structures-for-predefined-events" />

## Estructuras recomendadas para eventos predefinidos

La siguiente sección proporciona una lista de estructuras de eventos que son típicas de la vertical del cuidado de la salud. Cada estructura incluye un nombre de evento predefinido y los parámetros del evento de muestra para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

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

**Disparador**

Cuando el usuario completa el proceso de registro.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_registration\_method | El tipo de método de registro | correo electrónico, facebook |

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="Agregar al carrito (af_add_to_cart)">

**Finalidad**

Registra cuando un usuario agrega un producto a su carrito. Este evento puede ayudarte a determinar:

* Cuántos productos en promedio agregan los compradores en una sola compra.
* Cuánto tiempo transcurre desde que se agrega un producto hasta que se agrega otro.
* Cuántos compradores abandonan su carrito.

**Disparador**

Cuando el usuario agrega un producto al carrito.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_quantity | Cantidad solicitada | 1 |
| af\_price | Precio del producto | 10 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Finalidad**

Registrar las compras in-app realizadas por los usuarios. Este evento puede ayudarte a:

* Determinar el valor de vida útil (LTV) de tus usuarios y el ROI de tus campañas en todas las agencias y redes de publicidad.
* Determinar qué ofertas son las más populares entre tus usuarios.
* Establecer referencias cruzadas entre las campañas y los artículos comprados a fin de optimizar el targeting de las campañas.

**Disparador**

Cuando el usuario llega a la página de agradecimiento después de una compra exitosa.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Ingresos de la compra | 50.55 |
| af\_currency | Código de moneda | USD (Dólar estadounidense) |
| af\_order\_id | ID del pedido | 9277 |
| payment\_method\_type | Método de pago utilizado | tarjeta de crédito, local |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estructuras recomendadas para eventos personalizados

La siguiente sección proporciona la estructura del evento, incluidos el nombre del evento personalizado y los parámetros del evento de muestra para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="topup-success-top_up_success" />

<Accordion title="Recarga exitosa (top_up_success)">

**Finalidad**

Los fondos de recarga se pueden usar para comprar cualquier paquete o servicio que se ofrezca dentro de la aplicación. Puedes registrar este evento y compararlo con otros datos para aprender más acerca de tus usuarios. Por ejemplo, puedes saber qué cantidades están dispuestas a depositar en sus cuentas y usar los montos de recarga para dirigirte a los usuarios con campañas personalizadas dentro de sus presupuestos de recarga.

**Disparador**

Cuando el usuario completa la recarga.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Cantidad de la recarga | 2000.55 |
| top\_up\_id | El ID de la recarga | 397 |
| payment\_method\_type | Método de pago utilizado | credit card, local payment |

</Accordion>

<div data-zendesk-anchors="healthcare=-cuidado-de-la-salud h_01HGTAFRKKJ22SHB4JHMTGW2TV=-cuidado-de-la-salud h_01HGTAFRKKPWC1PQTKF227WWBD=importante recommended-structures-for-predefined-events=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAFRKKRB8EY8KJ9NXM4Z2T=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAFRKK35Q5W5ADQC2KYHR9=login-af_login h_01HGTAFRKK8E52FRVWQXP4Y3VV=complete-registration-af_complete_registration h_01HGTAFRKN6NJPDB053YYYH202=add-to-cart-af_add_to_cart h_01HGTAFRKNJVFECSFGSWG8B7GN=purchase-af_purchase recommended-structures-for-custom-events=estructuras-recomendadas-para-eventos-personalizados h_01HGTAFRKN29RJRW2V2WCH2AXT=estructuras-recomendadas-para-eventos-personalizados h_01HGTAFRKNDWHDDR9KDRKJ4H8E=topup-success-top_up_success" />
