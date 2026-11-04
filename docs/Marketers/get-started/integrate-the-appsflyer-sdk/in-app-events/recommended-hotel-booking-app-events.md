---
title: Eventos de aplicación recomendados para reservas de hoteles
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
  created_at: '2021-04-29T14:49:54Z'
  edited_at: '2026-08-12T12:01:32Z'
  id: 360019843558
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/360019843558
---
> **De un vistazo:** Mide la calidad de tus usuarios a lo largo de su trayectoria de usuario registrando estos eventos in-app sugeridos para tu aplicación de reserva de hoteles.

<div id="-hotel-booking" />

## <Image alt="Eventos_InApp_hotel.png" src="https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png" width="100px" /> Reserva de hoteles

Las aplicaciones de reserva de hoteles les permiten a los viajeros reservar hoteles con facilidad y, al mismo tiempo, elegir entre las mejores ofertas. Los eventos típicos que te recomendamos registrar son: busqueda, compra, reserva de viaje y agregar a la lista de deseos.

Registrar estos eventos puede ayudarte a determinar:

* Qué campañas y fuentes de medios atraen a los usuarios que efectivamente reservan vacaciones.
* Qué campañas y fuentes de medios atraen a los usuarios que hacen más reservas y generan la mayor cantidad de ingresos.

Podrás atribuir preferencias como la puntuación del hotel, la temporada, el país y la cantidad de niños a los usuarios provenientes de determinadas fuentes de medios. Luego, puedes optimizar tus campañas apuntando a estas preferencias de usuario.

<div id="important" />

> 🚧 **¡Importante!**
>
> * Asegúrate de leer las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#configuración-de-eventos-in-app">instrucciones</Anchor> para marketers sobre la implementación de eventos in-app.
> * Para agilizar el proceso de implementación, usa nuestro <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=hotel_booking">generador de eventos in-app</Anchor>. Esta herramienta incluye todos los eventos in-app típicos que se describen en este artículo y te permite modificar los eventos de acuerdo con tus necesidades comerciales. Una vez completado, comparte el archivo con tu desarrollador.
> * Para cada evento recomendado incluido en este artículo, hay <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=hotel_booking&view=code">muestras de código</Anchor> para desarrolladores de iOS, Android y Unity.
> * Puedes encontrar instrucciones detalladas para tu desarrollador en el **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">centro para desarrolladores de AppsFlyer</Anchor>.**
>
> Para más información sobre cómo registrar eventos in-app, consulta la <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">guía Eventos in-app enriquecidos</Anchor>.

[![Diagrama de flujo del recorrido del usuario en la aplicación de reservas de hoteles para eventos recomendados](https://files.readme.io/f425bc8865d731eb4934b6f32123156c7016ea1f75472e8878e76636aa593073-4402679204241.png)](https://files.readme.io/f425bc8865d731eb4934b6f32123156c7016ea1f75472e8878e76636aa593073-4402679204241.png)

<div id="recommended-structures-for-predefined-events" />

## Estructuras recomendadas para eventos predefinidos

La siguiente sección proporciona una lista de estructuras de eventos que son típicas de la vertical de reservas de hoteles. Cada estructura incluye un tipo de evento predefinido y los parámetros del evento predefinidos sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Finalidad**

Descubrir cuántos usuarios instalaron la aplicación y completaron el proceso de registro, qué métodos de registro prefieren tus usuarios y qué fuentes de medios atraen a los usuarios que efectivamente se registran.

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

<div id="search-af_search" />

<Accordion title="Búsqueda (af_search)">

**Finalidad**

Descubrir qué buscan los usuarios y qué resultados de búsqueda son los más relevantes y conducen a una compra. Además, podrás ver lo que los usuarios de determinadas ubicaciones geográficas están buscando y apuntar a ellos en las distintas fuentes de medios.

**Disparador**

Cuando el usuario realiza una búsqueda.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_date\_a | Fecha de entrada | 07/2018/26 |
| af\_date\_b | Fecha de salida | 2018/08/01 |
| af\_destination\_a | Ubicación del usuario | Londres |
| af\_destination\_b | Ubicación del hotel | Madrid |
| af\_num\_adults | Cantidad de huéspedes | 2 |
| af\_num\_children | Cantidad de niños | 0 |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Vista de contenido (af_content_view)">

**Finalidad**

Este evento puede ayudarte a determinar:

* Si los resultados de búsqueda están relacionados con las consultas de búsqueda.
* Qué tipos de propiedades buscan los usuarios.
* Tendencias estacionales
* Destinos populares.
* Qué fuentes de medios atraen a los usuarios y luego reorientan a estos usuarios en anuncios y promociones.

**Disparador**

Cuando el usuario está viendo una propiedad.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Precio de lista del hotel | 674 |
| af\_content\_id | ID del hotel | ODIRNH |
| af\_date\_a | Fecha de entrada | 07/2018/26 |
| af\_date\_b | Fecha de salida | 2018/08/01 |
| af\_destination\_a | Ubicación del usuario | Londres |
| af\_destination\_b | Ubicación del hotel | Madrid |
| af\_class | Tipo de habitación | De lujo |
| af\_num\_adults | Cantidad de huéspedes | 2 |
| af\_num\_children | Cantidad de niños | 0 |
| af\_hotel\_score | Puntuación del hotel según reseñas | 9.6 |
| af\_preferred\_star\_ratings | Calificación por estrellas como hotel preferido | 5 |
| af\_preferred\_neighborhoods | Zona en la que se encuentra el hotel | Centro |

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Agregar a la lista de deseos (af_add_to_wishlist)">

**Finalidad**

Registrar en qué hoteles y destinos los usuarios están interesados en reservar. Cuando sepas, por ejemplo, qué hoteles, regiones y las calificaciones de estrellas que buscan los usuarios, puedes utilizar estos datos para reorientar a los usuarios.

**Disparador**

Cuando un usuario agrega un listado a su lista de deseos.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Precio de lista del hotel | 674 |
| af\_content\_id | ID del hotel | ODIRNH |
| af\_date\_a | Fecha de entrada | 07/2018/26 |
| af\_date\_b | Fecha de salida | 2018/08/01 |
| af\_destination\_a | Ubicación del usuario | Londres |
| af\_destination\_b | Ubicación del hotel | Madrid |
| af\_class | Tipo de habitación | De lujo |
| af\_num\_adults | Cantidad de huéspedes | 2 |
| af\_num\_children | Cantidad de niños | 0 |
| af\_hotel\_score | Puntuación del hotel según reseñas | 9.6 |
| af\_preferred\_star\_ratings | Calificación por estrellas como hotel preferido | 5 |
| af\_preferred\_neighborhoods | Zona en la que se encuentra el hotel | Centro |
| purchase\_method | Método de compra | Tarjeta de crédito |
| af\_coupon\_code | Código de promoción o puntos de recompensa por lealtad | SUM2018 |
| property\_type | Tipo de propiedad | Hotel |

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="Checkout iniciado (af_initiated_checkout)">

**Finalidad**

Entiende cómo se comportan los compradores cuando realizan el checkout. Este evento puede ayudarte a determinar:

* Qué método de compra se utilizó, por ejemplo, tarjeta de crédito o billetera electrónica
* Si los usuarios terminan el checkout.

**Disparador**

Cuando el usuario agrega la información de su tarjeta de crédito o se conecta con su billetera electrónica

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Precio de lista del hotel | 674 |
| af\_content\_id | ID del hotel | ODIRNH |
| af\_date\_a | Fecha de entrada | 07/2018/26 |
| af\_date\_b | Fecha de salida | 2018/08/01 |
| af\_destination\_a | Ubicación del usuario | Londres |
| af\_destination\_b | Ubicación del hotel | Madrid |
| af\_class | Tipo de habitación | De lujo |
| af\_num\_adults | Cantidad de huéspedes | 2 |
| af\_num\_children | Cantidad de niños | 0 |
| af\_hotel\_score | Puntuación del hotel según reseñas | 9.6 |
| af\_preferred\_star\_ratings | Calificación por estrellas como hotel preferido | 5 |
| af\_preferred\_neighborhoods | Zona en la que se encuentra el hotel | Centro |
| purchase\_method | Método de compra | Tarjeta de crédito |
| af\_coupon\_code | Código de promoción o puntos de recompensa por lealtad | SUM2018 |
| property\_type | Tipo de propiedad | Hotel |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Finalidad**

Conocer las tendencias de compra en tu aplicación de reserva de hoteles. Este evento puede ayudarte a:

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
| af\_content\_type | Categoría del artículo | hotel |
| af\_currency | Código de moneda | AUD |
| af\_quantity | Cantidad de artículos en el carrito | 1 |
| af\_order\_id | El ID del pedido que se genera después de la compra | X123ABC |
| af\_receipt\_id | ID de pedido, necesario para la integración de retargeting de CRITEO y Google AdWords | X123ABC |

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="Reserva de viaje (af_travel_booking)">

**Finalidad**

Determinar la tarifa de reserva general en tu aplicación. Este evento puede ayudarte a:

* Registrar los ingresos generados a partir de las reservas.
* Determinar la cantidad de usuarios que reservan hoteles con niños.
* Comprender las tendencias estacionales.
* Determinar qué hoteles son populares.

**Disparador**

Cuando el usuario llega a la página de agradecimiento después de reservar un hotel.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Ingresos de la reserva | 647.95 |
| af\_currency | Código de moneda | GBP |
| af\_price | Precio de lista del hotel | 674 |
| af\_content\_id | ID del hotel | ODIRNH |
| af\_date\_a | 07/2018/26 | Fecha de entrada |
| af\_date\_b | Fecha de salida | 2018/08/01 |
| af\_destination\_a | Ubicación del usuario | Londres |
| af\_destination\_b | Ubicación del hotel | Madrid |
| af\_class | Tipo de habitación | De lujo |
| af\_num\_adults | Cantidad de huéspedes | 2 |
| af\_num\_children | Cantidad de niños | 0 |
| af\_hotel\_score | Puntuación del hotel según reseñas | 9.6 |
| af\_preferred\_star\_ratings | Calificación por estrellas como hotel preferido | 5 |
| af\_preferred\_neighborhoods | Zona en la que se encuentra el hotel | Centro |
| purchase\_method | Método de compra | Tarjeta de crédito |
| af\_coupon\_code | Código de promoción o puntos de recompensa por lealtad | SUM2018 |
| property\_type | Tipo de propiedad | Hotel |
| new\_booking | La primera reserva del usuario | Verdadero |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estructuras recomendadas para eventos personalizados

La siguiente sección proporciona una lista de estructuras de eventos que incluye nombres de eventos personalizados y los parámetros de eventos sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="first-purchase-first_purchase" />

<Accordion title="Primera compra (first_purchase)">

**Finalidad**

Igual que el evento [Compra](/docs/recommended-hotel-booking-app-events#purchase-af_purchase). Además, este evento puede ayudarte a determinar:

* Cuánto tiempo tarda un comprador nuevo en hacer una compra.
* Cuáles son los productos que prefieren los compradores por primera vez.
* Los ingresos y precios promedios de las compras por primera vez.

**Disparador**

Cuando el usuario completa su primera compra.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Ingresos de la compra | 1205.95 |
| af\_price | Importe total de la compra | 4000 |
| af\_content\_id | ID del artículo | 121, 262 |
| af\_content\_type | Categoría del artículo | hotel |
| af\_currency | Truemoney | AUD |
| af\_quantity | Cantidad de artículos en el carrito | 1 |
| af\_order\_id | El ID del pedido que se genera después de la compra | X123ABC |
| af\_receipt\_id | ID de pedido, necesario para la integración de retargeting de CRITEO y Google AdWords | X123ABC |

</Accordion>

<div data-zendesk-anchors="hotel-booking=-reserva-de-hoteles h_01HGTB0APWWTRER6GAWJ7TJ05S=-reserva-de-hoteles h_01HGTB0APWQDX7VN96GM7520ZH=importante recommended-structures-for-predefined-events=estructuras-recomendadas-para-eventos-predefinidos h_01HGTB0APW933179Q90HFASW1V=estructuras-recomendadas-para-eventos-predefinidos h_01HGTB0APWRKRGCJ5TFKTPHH33=complete-registration-af_complete_registration h_01HGTB0APW1XY5R69CJ8PSQV6C=login-af_login h_01HGTB0APW5YF2DASC0HYDPTA9=search-af_search h_01HGTB0APXTQWBS4EXJ8D724G0=content-view-af_content_view h_01HGTB0APXS95QGK17RE8B3Y1E=add-to-wishlist-af_add_to_wishlist h_01HGTB0APX1XX2W3YX85W75F6B=initiated-checkout-af_initiated_checkout h_01HGTB0APXGPW16FRY3C7VSMDM=purchase-af_purchase h_01HGTB0APXJFHMPGYC63ZTV4R9=travel-booking-af_travel_booking recommended-structures-for-custom-events=estructuras-recomendadas-para-eventos-personalizados h_01HGTB0APXP6WVM1AVEMEY6KVS=estructuras-recomendadas-para-eventos-personalizados h_01HGTB0APX4ND0NGVTK9FA38QR=first-purchase-first_purchase" />
