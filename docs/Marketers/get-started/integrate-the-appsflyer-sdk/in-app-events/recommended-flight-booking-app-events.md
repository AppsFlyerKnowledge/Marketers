---
title: Eventos de aplicación recomendados para reservas de vuelos
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
  created_at: '2021-04-29T13:07:29Z'
  edited_at: '2026-08-12T12:00:47Z'
  id: 360019670857
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/360019670857
---
> **De un vistazo:** Mide la calidad de tus usuarios a lo largo de su trayectoria de usuario registrando estos eventos in-app sugeridos para tu aplicación de reserva de vuelos.

## <Image alt="Eventos_en_la_aplicación_vuelo.png" src="https://files.readme.io/7a09c4a641dd5e797bffc41a6e66b20efe5660721f37abac3dd12ac83688b37b-20659533911697.png" width="100px" /> Reserva de vuelo

Las aplicaciones de reserva de vuelos les permiten a los viajeros reservar vuelos con facilidad y, al mismo tiempo, elegir entre las mejores ofertas. Los eventos típicos que recomendamos atribuir son: reservar un vuelo, buscar vuelos y ver ofertas.

La atribución de eventos puede ayudarte a:

* Conocer los destinos populares
* Analizar las tendencias estacionales
* Conocer las líneas aéreas populares con las cuales prefieren viajar los usuarios

> 🚧 **¡Importante!**
>
> * Asegúrate de leer las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#configuración-de-eventos-in-app">instrucciones</Anchor> para marketers sobre la implementación de eventos in-app.
> * Para agilizar el proceso de implementación, usa nuestro <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=flight_booking">generador de eventos in-app</Anchor>. Esta herramienta incluye todos los eventos in-app típicos que se describen en este artículo y te permite modificar los eventos de acuerdo con tus necesidades comerciales. Una vez completado, comparte el archivo con tu desarrollador.
> * Para cada evento recomendado incluido en este artículo, hay <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=flight_booking&view=code">ejemplos de código</Anchor> para desarrolladores de iOS, Android y Unity.
> * Puedes encontrar instrucciones detalladas para tu desarrollador en el **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">centro para desarrolladores de AppsFlyer</Anchor>.**
>
> Para más información sobre cómo registrar eventos in-app, consulta la <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">guía Eventos in-app enriquecidos</Anchor>.

[![Diagrama de flujo para eventos recomendados recorrido del usuario de la app de reserva de vuelos](https://files.readme.io/435378707a7299a8c98bc7490f0f1554b5f6c332a35c1546ce34feb1b6b86394-360020171258.png)](https://files.readme.io/435378707a7299a8c98bc7490f0f1554b5f6c332a35c1546ce34feb1b6b86394-360020171258.png)

## Estructuras recomendadas para eventos predefinidos

La siguiente sección proporciona una lista de estructuras de eventos que son típicas de la vertical de reservas de vuelos. Cada estructura incluye un tipo de evento predefinido y los parámetros del evento predefinidos sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Finalidad**

Descubre cuántos usuarios instalaron la aplicación y completaron el proceso de registro, qué métodos de registro prefieren tus usuarios.

**Disparador**

Cuando el usuario completa el proceso de registro.

Parámetros del evento

| Nombre de campo | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_registration\_method | El tipo de método de registro | correo electrónico, facebook |

</Accordion>

<div id="login-af_login" />

<Accordion title="Acceso (af_login)">

**Finalidad**

Comprender la retención de tus usuarios registrados.

**Activador**

Cuando el usuario accede correctamente.

**Parámetros del evento**

Se puede enviar sin ningún parámetro adicional.

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="Reserva de viaje (af_travel_booking)">

**Finalidad**

La capacidad de reservar vuelos es la función principal de la aplicación. Este evento puede ayudarte a determinar:

* Destinos populares
* Líneas aéreas populares
* Tendencias estacionales

**Activador**

Cuando el usuario llega a la página de agradecimiento después de reservar con éxito un vuelo.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Ingresos asociados con la reserva | 647.99 |
| af\_currency | Código de moneda | SGD |
| af\_price | Precio | 674 |
| af\_content\_id | ID de la oferta de vuelo | ODIRNH |
| af\_departing\_departure\_date | La fecha de partida | 06-21-2018 |
| af\_returning\_departure\_date | La fecha de regreso | 06-26-2018 |
| af\_destination\_a | Primer destino | BKK |
| af\_destination\_b | Segundo destino (si corresponde) | SYD |
| airline\_code | Código de la línea aérea | KLM |
| af\_class | Clase del vuelo reservado | Clase turista |
| purchase\_method | Método usado para la compra | Tarjeta de crédito |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Vista de contenido (af_content_view)">

**Finalidad**

Este evento puede ayudarte a determinar:

* Cuáles son las ofertas de vuelos que les resultan más atractivas a los usuarios.
* Si los resultados de búsqueda están relacionados con las consultas de búsqueda.

**Activador**

Cuando un usuario hace clic en un resultado de búsqueda.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_departing\_departure\_date | La fecha de partida | 06-21-2018 |
| af\_returning\_departure\_date | La fecha de regreso | 06-26-2018 |
| af\_destination\_a | Primer destino | BKK |
| af\_destination\_b | Segundo destino (si corresponde) | SYD |

</Accordion>

<div id="search-af_search" />

<Accordion title="Búsqueda (af_search)">

**Finalidad**

Las aplicaciones de reserva de vuelos permiten que los usuarios busquen vuelos y ofertas. Una manera de conocer las preferencias de los usuarios es registrar los parámetros de búsqueda. Este evento puede ayudarte a:

* Saber qué es lo que buscan los usuarios.
* Saber cuáles son los destinos más populares.
* Ver cuántos usuarios viajan con niños.
* Ver en qué época del año los usuarios prefieren o planean viajar.

**Disparador**

Después de que el usuario complete el formulario de búsqueda y haga clic en el botón de búsqueda.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_num\_children | Cantidad de niños que viajan | 0 |
| af\_destination\_a | Primer destino | BKK |
| af\_destination\_b | Segundo destino (si corresponde) | SYD |
| af\_departing\_departure\_date | La fecha de partida | 06-21-2018 |
| af\_returning\_departure\_date | La fecha de regreso | 06-26-2018 |
| af\_num\_infants | Cantidad de bebés que viajan | 0 |
| af\_num\_adults | Cantidad de adultos que viajan | 1 |

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="Agregar información de pago (af_add_payment_info)">

**Finalidad**

Registrar los intentos exitosos y no exitosos de agregar la información de pago cuando se reserva un vuelo.

**Activador**

Cuando un usuario hace clic en el botón para reservar un vuelo.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_success | Si se pudo agregar el método de pago correctamente | Verdadero |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Finalidad**

Conocer las tendencias de compra en tu aplicación de reserva de vuelos. Este evento puede ayudarte a:

* Determinar el valor de vida útil (LTV) de tus usuarios y el ROI de tus campañas en todas las agencias y redes de publicidad.
* Determinar qué ofertas son las más populares entre tus usuarios.
* Establecer referencias cruzadas entre las campañas y los artículos comprados a fin de optimizar el targeting de las campañas.

**Disparador**

Cuando el usuario llega a la página de agradecimiento después de una compra exitosa.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Los ingresos estimados de la compra | 1205.99 |
| af\_price | Importe total de la compra | 4000 |
| af\_content\_id | ID del artículo | 121 |
| af\_content\_type | Categoría del artículo | vuelo |
| af\_currency | Código de moneda | AUD |
| af\_quantity | Cantidad de artículos en el carrito | 1 |
| af\_order\_id | El ID del pedido que se genera después de la compra | X123ABC |
| af\_receipt\_id | ID de pedido, necesario para la integración de retargeting de CRITEO y Google AdWords | X123ABC |

</Accordion>

## Estructuras recomendadas para eventos personalizados

La siguiente sección proporciona una lista de estructuras de eventos que incluye nombres de eventos personalizados y los parámetros de eventos sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="first-purchase-first_purchase" />

<Accordion title="Primera compra (first_purchase)">

**Finalidad**

Igual que el evento [Compra](/docs/recommended-flight-booking-app-events#purchase-af_purchase). Además, este evento puede ayudarte a determinar:

* Cuánto tiempo tarda un comprador nuevo en hacer una compra.
* Qué vuelos prefieren los compradores para comprar por primera vez
* Los ingresos y precios promedios de las compras por primera vez.

**Activador**

Cuando el usuario completa su primera compra.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Ingresos de la compra | 1205.99 |
| af\_price | Importe total de la compra | 4000 |
| af\_content\_id | ID del artículo | 121, 262 |
| af\_content\_type | Categoría del artículo | vuelo |
| af\_currency | Truemoney | AUD |
| af\_quantity | Cantidad de artículos en el carrito | 1 |
| af\_order\_id | El ID del pedido que se genera después de la compra | X123ABC |
| af\_receipt\_id | ID de pedido, necesario para la integración de retargeting de CRITEO y Google AdWords | X123ABC |

</Accordion>

<div data-zendesk-anchors="flight-booking=-reserva-de-vuelo h_01HGTAZRKG0SQ66XK7VN9KVGEY=-reserva-de-vuelo h_01HGTAZRKGGQBBAM4XJHR4B45P=importante recommended-structures-for-predefined-events=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAZRKHK1427YX16HWRDRPN=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAZRKHACHNSNX9DSZ3ZZ51=complete-registration-af_complete_registration h_01HGTAZRKHTC9TNWNPACRZW31Y=login-af_login h_01HGTAZRKHZGW442XTZF99VGV9=travel-booking-af_travel_booking h_01HGTAZRKHGY0Z83ETZWAFNSWP=content-view-af_content_view h_01HGTAZRKH8JYE8Q6NDPF1PQC7=search-af_search h_01HGTAZRKH78CR2GH0960MS8R0=add-payment-info-af_add_payment_info h_01HGTAZRKHXE8VF78ZE0KF9AF6=purchase-af_purchase recommended-structures-for-custom-events=estructuras-recomendadas-para-eventos-personalizados h_01HGTAZRKH4ZZEK5JGXZ7G5QDJ=estructuras-recomendadas-para-eventos-personalizados h_01HGTAZRKHG7GE4BKFDRHZC163=first-purchase-first_purchase" />
