---
title: Eventos recomendados para apps de eCommerce
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
  created_at: '2021-04-19T06:32:18Z'
  edited_at: '2026-08-12T12:01:12Z'
  id: 360019347957
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/360019347957
---
> **En resumen:** Mide la calidad de tus usuarios a lo largo de su trayectoria de usuario registrando estos eventos in-app sugeridos para tu aplicación de eCommerce.

## <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="67px" /> eCommerce

Las aplicaciones de eCommerce permiten que los compradores busquen y compren productos online con facilidad. Los eventos típicos que te recomendamos registrar son: buscar, comprar, agregar al carrito y agregar a la lista de deseos.

Registrar estos eventos puede ayudarte a determinar:

* Las categorías más populares.
* Qué buscan los compradores.
* Cuántos compradores finalizaron el checkout.
* Cuántos de los compradores son recurrentes y cuántos son compradores de una sola vez.

<div id="important" />

> 🚧 **¡Importante!**
>
> * Asegúrate de leer las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#configuración-de-eventos-in-app">instrucciones</Anchor> para marketers sobre la implementación de eventos in-app.
> * Para agilizar el proceso de implementación, usa nuestro <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=ecommerce">generador de eventos in-app</Anchor>. Esta herramienta incluye todos los eventos in-app típicos que se describen en este artículo y te permite modificar los eventos de acuerdo con tus necesidades comerciales. Una vez completado, comparte el archivo con tu desarrollador.
> * Para cada evento recomendado incluido en este artículo, hay <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=ecommerce&view=code">ejemplos de código</Anchor> para desarrolladores de iOS, Android y Unity.
> * Encontrarás instrucciones detalladas para tu desarrollador en el <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">**centro para desarrolladores de AppsFlyer**</Anchor>.
>
> Para más información sobre la grabación de eventos in-app, consulta la <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">guía de eventos in-app</Anchor>.

<Image align="center" alt="Flowchart_for_recommended_events e-Commerce_app_user_journey" src="https://files.readme.io/81af149c4fbe9185af3dad4057147dbf9882eb30d30b0724f2ffad2714517084-360020063077.png" />

<div id="recommended-structures-for-predefined-events" />

## Estructuras recomendadas para eventos predefinidos

La siguiente sección proporciona una lista de estructuras de eventos que son típicas de la vertical de eCommerce. Cada estructura incluye un nombre de evento predefinido y los parámetros del evento sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Finalidad**

Descubrir cuántos usuarios instalaron la aplicación y completaron el proceso de registro, y qué métodos de registro prefieren tus usuarios.

**Disparador**

Cuando el usuario completa el proceso de registro.

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| af\_registration\_method | Tipo de método de registro | Correo electrónico, Meta Ads |

</Accordion>

<div id="login-af_login" />

<Accordion title="Iniciar sesión (af_login)">

**Finalidad**

Comprender la retención de tus usuarios registrados.

**Disparador**

Cuando el usuario accede correctamente.

**Parámetros del evento**

Se puede enviar sin ningún parámetro adicional.

</Accordion>

<div id="search-af_search" />

<Accordion title="Búsqueda (af_search)">

**Finalidad**

Descubrir qué buscan los usuarios y qué resultados de búsqueda son los más relevantes y conducen a una compra.

**Disparador**

Una de los siguientes:

* Cuando el usuario hace clic en el botón de búsqueda.
* Cuando el usuario llega a la página de resultados de búsqueda.

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| af\_search\_string | Término de búsqueda | Vestido rojo, zapatillas para correr |
| af\_content\_list | Lista de IDs de contenido | 001, 092 |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Vista de contenido (af_content_view)">

**Finalidad**

Determinar la tasa de visualizaciones de productos específicos. Este evento puede ayudarte a:

* Correlacionar visualizaciones de productos con ventas de productos.
* Determinar cuáles categorías son las más populares según las visualizaciones de productos.
* Ver la correlación entre la divisa de los compradores y los productos que visualizan.

**Disparador**

Cuando el usuario ve la página de detalles de un producto específico.

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Precio del producto | 2000 |
| af\_content | International Article Number (EAN) cuando corresponda, u otro identificador de producto o contenido<br /><br />**Parámetro requerido para anuncios dinámicos de Meta Ads** | ABC123 |
| af\_content\_id | ID del producto<br /><br />**Parámetro requerido para anuncios dinámicos de Meta Ads** | 102 |
| af\_content\_type | Categoría del artículo<br /><br />**Parámetro requerido para anuncios dinámicos de Meta Ads**  <br />  <br />**Nota:** Al mapear `af_content_type` a `fb_content_type` de Meta, los únicos valores admitidos son `product` o `product_group`. | Zapatos |
| af\_currency | La divisa que figura en la página de detalles del producto | THB, USD |

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="Vista de lista (af_list_view)">

**Finalidad**

Registra qué listas (por ejemplo, productos recién agregados, productos relacionados o productos recomendados) ven más los compradores.

**Disparador**

Cuando el usuario ve una lista específica.

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| af\_content\_type | Categoría del artículo<br /><br />**Parámetro requerido para anuncios dinámicos de Meta Ads**  <br />  <br />**Nota:** Al mapear `af_content_type` a `fb_content_type` de Meta, los únicos valores admitidos son `product` o `product_group`. | Productos relacionados, recomendados, novedades |
| af\_content\_list | Lista de ID de contenido de la categoría | 001, 092 |

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Añadir a la lista de deseos (af_add_to_wishlist)">

**Finalidad**

Registrar qué productos y categorías agregan los compradores a sus listas de deseos. Cuando sepas cuáles productos se agregan con frecuencia a las listas de deseos, podrás ofrecerlos en ofertas especiales o con descuentos y así alentar a los compradores a comprarlos. También podrás usar la función de retargeting de usuarios según los productos que agregan a su lista de deseos.

**Disparador**

Cuando el usuario agrega artículos a su lista de deseos

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Precio del producto | 600 |
| af\_content\_id | ID del producto | 300 |
| af\_content\_type | Categoría del artículo<br /><br />**Parámetro requerido para anuncios dinámicos de Meta Ads**  <br />  <br />**Nota:** Al mapear `af_content_type` a `fb_content_type` de Meta, los únicos valores admitidos son `product` o `product_group`. | Zapatos, electrónica |
| af\_currency | La divisa que se muestra en la página de detalles del producto | GBP |

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="Añadir al carrito (af_add_to_cart)">

**Finalidad**

Registrar cuando un usuario agrega productos a su carrito. Este evento puede ayudarte a determinar:

* Cuántos productos en promedio agregan los compradores en una sola compra.
* Cuánto tiempo transcurre desde que se agrega un producto hasta que se agrega otro.
* Cuántos compradores abandonan su carrito.

**Disparador**

Cuando el usuario agrega un producto al carrito.

**Parámetros del evento**

| Nombre del campo | Nota | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Precio del producto | 350, 1000 |
| af\_content | International Article Number (EAN) cuando corresponda, u otro identificador de producto o contenido<br /><br />**Parámetro requerido para anuncios dinámicos de Meta Ads** | ABC123 |
| af\_content\_id | ID del producto<br /><br />**Parámetro requerido para anuncios dinámicos de Meta Ads** | 001, 092 |
| af\_content\_type | Categoría del artículo<br /><br />**Parámetro requerido para anuncios dinámicos de Meta Ads**  <br />  <br />**Nota:** Al mapear `af_content_type` a `fb_content_type` de Meta, los únicos valores admitidos son `product` o `product_group`. | Camisa, zapatos |
| af\_currency | Moneda del producto | THB, USD |
| af\_quantity | Cuántos artículos del mismo producto se agregaron al carrito | 2, 5 |

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="Inicio de pago (af_initiated_checkout)">

**Finalidad**

Entender cómo se comportan los compradores cuando realizan el checkout. Este evento puede ayudarte a determinar:

* El precio promedio cuando los compradores realizan el checkout con el precio promedio del evento de compra.
* Si los usuarios agregan o eliminan productos una vez iniciado el checkout.

**Disparador**

Cuando el usuario inicie el checkout, pero no lo haya finalizado aún.

**Parámetros del evento**

| Nombre del campo | Nota | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Precio total del carrito | 4000 |
| af\_content\_id | ID de los productos en el carrito | 221, 124 |
| af\_content\_type | Categoría del artículo<br /><br />**Parámetro requerido para anuncios dinámicos de Meta Ads**  <br />  <br />**Nota:** Al mapear `af_content_type` a `fb_content_type` de Meta, los únicos valores admitidos son `product` o `product_group`. | Camisa, pantalones |
| af\_currency | Divisa al momento del checkout | THB |
| af\_quantity | Cantidad total de artículos en el carrito | 2, 5 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Finalidad**

Conocer las tendencias de compra en tu aplicación. Este evento puede ayudarte a:

* Determinar el LTV de tus usuarios y el ROI de tus campañas en todas las agencias y ad networks.
* Determinar qué ofertas son las más populares entre tus usuarios.
* Establecer referencias cruzadas entre las campañas y los artículos comprados a fin de optimizar el targeting de las campañas.

**Disparador**

Cuando el usuario llega a la página de agradecimiento después de una compra exitosa.

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Los ingresos estimados de la compra | 1205.99 |
| af\_price | Importe total de la compra | 4000 |
| af\_content | International Article Number (EAN) cuando corresponda, u otro identificador de producto o contenido<br /><br />Parámetro requerido para **anuncios dinámicos** de Meta Ads | ABC123 |
| af\_content\_id | ID del artículo<br /><br />**Parámetro requerido para anuncios dinámicos de Meta Ads** | 121, 262 |
| af\_content\_type | Categoría del artículo<br /><br />**Parámetro requerido para anuncios dinámicos de Meta Ads**  <br />  <br />**Nota:** Al mapear `af_content_type` a `fb_content_type` de Meta, los únicos valores admitidos son `product` o `product_group`. | grupo\_de\_productos |
| af\_currency | Código de la moneda | AUD |
| af\_quantity | Cantidad de artículos en el carrito | 2, 5 |
| af\_order\_id | El ID del pedido que se genera después de la compra | X123ABC |
| af\_receipt\_id | ID de pedido<br /><br />**Parámetro obligatorio para CRITEO y Google Ad Words para la validación de compra** | X123ABC |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estructuras recomendadas para eventos personalizados

La siguiente sección proporciona una lista de estructuras de eventos que incluye nombres de eventos personalizados y los parámetros de eventos sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="first-purchase-first_purchase" />

<Accordion title="Primera compra (first_purchase)">

**Finalidad**

Igual que el evento [Compra](/docs/recommended-ecommerce-app-events#purchase-af_purchase). Además, este evento puede ayudarte a determinar:

* Cuánto tiempo tarda un comprador nuevo en hacer una compra.
* Cuáles son los productos que prefieren los compradores por primera vez.
* Los ingresos y precios promedios de las compras por primera vez.

**Disparador**

Cuando el usuario completa su primera compra.

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Ingresos de la compra | 1205.99 |
| af\_price | Importe total de la compra | 4000 |
| af\_content | International Article Number (EAN) cuando corresponda, u otro identificador de producto o contenido<br /><br />**Parámetro requerido para anuncios dinámicos de Meta Ads** | ABC123 |
| af\_content\_id | ID del artículo<br /><br />**Parámetro requerido para anuncios dinámicos de Meta Ads** | 121, 262 |
| af\_content\_type | Categoría del artículo<br /><br />**Parámetro requerido para anuncios dinámicos de Meta Ads**  <br />  <br />**Nota:** Al mapear `af_content_type` a `fb_content_type` de Meta, los únicos valores admitidos son `product` o `product_group`. | Zapatos, pantalones |
| af\_currency | Truemoney | AUD |
| af\_quantity | Cantidad de artículos en el carrito | 2, 5 |
| af\_order\_id | El ID del pedido que se genera después de la compra | X123ABC |
| af\_receipt\_id | ID de pedido<br /><br />**Parámetro obligatorio para la integración de retargeting de CRITEO y Google AdWords** | X123ABC |

</Accordion>

<div id="remove-from-cart-remove_from_cart" />

<Accordion title="Eliminar del carrito (remove_from_cart)">

**Finalidad**

La atribución de este evento puede ayudarte a:

* Determinar qué artículos los compradores eliminan del carrito.
* Determinar las categorías de productos de los artículos que los compradores eliminan del carrito.
* Comparar los datos del evento [Agregar al carrito](/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart) para saber qué productos no llegan al checkout.

**Disparador**

Cuando el usuario elimina un artículo del carrito.

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| af\_content\_id | ID del artículo o producto | 521 |
| af\_content\_type | Categoría del artículo<br /><br />**Parámetro requerido para anuncios dinámicos de Meta Ads**  <br />  <br />**Nota:** Al mapear `af_content_type` a `fb_content_type` de Meta, los únicos valores admitidos son `product` o `product_group`. | Zapatos |

</Accordion>

<div data-zendesk-anchors="ecommerce=-ecommerce h_01HGTAWG2166CZYKJE9166G12J=-ecommerce h_01HGTAWG21Z0C9SR2G54W68G8Q=importante recommended-structures-for-predefined-events=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAWG2115VB3A8J2WG3DJKK=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAWG21EQ0FE40WGFJRDJY5=complete-registration-af_complete_registration h_01HGTAWG22HFZ24V2BDCH3RFN8=login-af_login h_01HGTAWG22B5Z9AXENDATKR67T=search-af_search h_01HGTAWG22PSKS80ZQNAC0K24M=content-view-af_content_view h_01HGTAWG2219SVQ86PT1K3TVV9=list-view-af_list_view h_01HGTAWG22EQMVWXJCXC2KQDX8=add-to-wishlist-af_add_to_wishlist h_01HGTAWG23T81SPFJEA6BY5F2W=add-to-cart-af_add_to_cart h_01HGTAWG23FPKQ6RHJ9VYET63Y=initiated-checkout-af_initiated_checkout h_01HGTAWG2385E9Q0FXZXEW38YK=purchase-af_purchase recommended-structures-for-custom-events=estructuras-recomendadas-para-eventos-personalizados h_01HGTAWG235EXE17EJ5DWQYERM=estructuras-recomendadas-para-eventos-personalizados h_01HGTAWG23NTG0Q70B9A3685AD=first-purchase-first_purchase h_01HGTAWG239TQ51Z7FQW4FC1TZ=remove-from-cart-remove_from_cart" />
