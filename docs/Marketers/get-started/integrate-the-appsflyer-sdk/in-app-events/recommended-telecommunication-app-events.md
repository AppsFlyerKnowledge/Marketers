---
title: Eventos de aplicación recomendados para las telecomunicaciones
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
  created_at: '2021-05-02T11:59:16Z'
  edited_at: '2026-08-12T12:01:49Z'
  id: 360019896558
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/360019896558
---
> **De un vistazo:** Mide la calidad de tus usuarios a lo largo de su trayectoria de usuario registrando estos eventos in-app sugeridos para tu aplicación de telecomunicaciones.

<div id="-telecommunication" />

## <Image alt="icono_de_telecomunicaciones.png" src="https://files.readme.io/42f1aac3b825957d9d0584d83480c441b9d53665cc6cf1a6b8cd1803bb9b6121-20659194885393.png" width="100px" /> Telecomunicaciones

Las aplicaciones de telecomunicaciones permiten a los usuarios comprar y gestionar planes de telefonía móvil, planes de datos, etc. Los eventos típicos que recomendamos registrar incluyen las compras, las recargas y las suscripciones.

Registrar estos eventos puede ayudarte a determinar:

* Qué planes de acceso son los más populares.
* Qué productos o paquetes pueden pagar los usuarios.
* Qué planes tienen más probabilidades de conseguir un compromiso a largo plazo por parte de los clientes.

<div id="important" />

> 🚧 **¡Importante!**
>
> * Asegúrate de leer las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#configuración-de-eventos-in-app">instrucciones</Anchor> para marketers sobre la implementación de eventos in-app.
> * Para agilizar el proceso de implementación, usa nuestro <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=telecommunication">generador de eventos in-app</Anchor>. Esta herramienta incluye todos los eventos in-app típicos que se describen en este artículo y te permite modificar los eventos de acuerdo con tus necesidades comerciales. Una vez completado, comparte el archivo con tu desarrollador.
> * Para cada evento recomendado incluido en este artículo, hay <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=telecommunication&view=code">ejemplos de código</Anchor> para desarrolladores de iOS, Android y Unity.
> * Puedes encontrar instrucciones detalladas para tu desarrollador en el **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">centro para desarrolladores de AppsFlyer</Anchor>.**
>
> Para más información sobre cómo registrar eventos in-app, consulta la <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">guía Eventos in-app enriquecidos</Anchor>.

<Image align="center" alt="Diagrama de flujo del recorrido del usuario de la app de telecomunicaciones para eventos recomendados" src="https://files.readme.io/ae4c696208b49aa546ffc0a15f76b148b35af43984a76e699d1df7c54507352c-4404604045457.png" />

<div id="recommended-structures-for-predefined-events" />

## Estructuras recomendadas para eventos predefinidos

La siguiente sección proporciona una lista de estructuras de eventos que son típicas de la vertical de telecomunicaciones. Cada estructura incluye un tipo de evento predefinido y los parámetros del evento predefinidos sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

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

<div id="content-view-af_content_view" />

<Accordion title="Vista de contenido (af_content_view)">

**Finalidad**

Determinar la tasa de visualizaciones de productos específicos y:

* Correlacionar visualizaciones de productos con ventas de productos.
* Determinar cuáles categorías son las más populares según las visualizaciones de productos.
* Ver la correlación entre la divisa de los compradores y los productos que visualizan.

**Disparador**

Cuando el usuario ve la página de detalles de un producto específico.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Precio del producto | 200 |
| af\_content\_id | ID del producto | 102 |
| af\_content\_type | Categoría de producto | Paquetes de Internet |
| af\_currency | La moneda que figura en la página de detalles del producto | THB, USD |

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="Vista de lista (af_list_view)">

**Finalidad**

Registrar qué listas (por ejemplo, productos recién agregados, productos relacionados o productos recomendados) ven más los compradores.

**Disparador**

Cuando el usuario ve una lista específica.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_content\_type | Tipo de lista | Productos relacionados, recomendados, novedades |
| af\_content\_list | Lista de ID de contenido de la categoría | 001, 092 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Finalidad**

Muchas aplicaciones de telecomunicaciones permiten a los usuarios comprar artículos, como datos adicionales. La atribución de este evento puede ayudarte a:

* Determinar el valor de vida útil (LTV) de tus usuarios y el ROI de tus campañas en todas las agencias y redes de publicidad.
* Determinar qué ofertas son las más populares entre tus usuarios.
* Establecer referencias cruzadas entre las campañas y los artículos comprados a fin de optimizar el targeting de las campañas.

**Disparador**

Cuando el usuario llega a la página de agradecimiento después de una compra exitosa.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Los ingresos estimados de la compra | 2050.50 |
| af\_currency | Código de moneda | THB |
| af\_content\_type | Nombre del paquete comprado | 5G |
| af\_order\_id | ID del pedido | 9277 |
| payment\_method\_type | Tipo de método de pago | credit card, local payment |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estructuras recomendadas para eventos personalizados

La siguiente sección proporciona una estructura de evento que incluye un nombre de evento personalizado y los parámetros del evento sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="select-package-select_package" />

<Accordion title="Seleccionar paquete (select_package)">

**Finalidad**

Registra cuándo un usuario decide comprar un paquete pero aún no ha realizado el pago. Puedes utilizar estos datos, por ejemplo, para reorientar a los usuarios y enviarles ofertas sobre otros servicios.

**Disparador**

Cuando el usuario selecciona un paquete pero no ha completado el pago.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| price | Precio de la suscripción | 50000 |
| af\_content\_type | Tipo de contenido que seleccionó el usuario | Data 5 GB |

</Accordion>

<div id="topup-success-top_up_success" />

<Accordion title="Recarga exitosa (top_up_success)">

**Finalidad**

Los fondos de recarga se pueden usar para comprar cualquier paquete o cualquier otro servicio que se ofrezca dentro de la aplicación. Registra este evento y compáralo con otros datos para obtener más información sobre tus usuarios. Por ejemplo, puedes saber qué cantidades están dispuestas a depositar en sus cuentas y usar los montos de recarga para dirigirte a los usuarios con campañas personalizadas dentro de sus presupuestos de recarga.

**Disparador**

Cuando el usuario completa la recarga.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Cantidad de la recarga | 2050.50 |
| top\_up\_id | El ID de la recarga | 397 |
| payment\_method\_type | Tipo de método de pago | credit card, local payment |

</Accordion>

<div id="topup-unsuccessful-top_up_unsuccessful" />

<Accordion title="Recarga fallida (top_up_unsuccessful)">

**Finalidad**

Registra este evento y compáralo con otros datos para obtener más información sobre tus usuarios. Por ejemplo, puedes saber cuántos usuarios intentan recargar pero fallan.

**Disparador**

Cuando el usuario intenta recargar pero la acción falla.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| error\_reason | Razón de la falla de la recarga | exceeded\_daily\_limit |

</Accordion>

<div id="subscription-complete-subscription_complete" />

<Accordion title="Suscripción completa (subscription_complete)">

**Finalidad**

La atribución de este evento puede ayudarte a:

* Ver qué campañas atraen a usuarios que se suscriben.
* Comparar el número de usuarios suscritos con el de usuarios no suscritos.
* Registrar los ingresos generados a partir de las suscripciones y atribuirlos a campañas y fuentes de medios.

**Disparador**

* Cuando el usuario se suscribe correctamente.
* Cuando se renueva una suscripción.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| subscription\_type | Tipo de suscripción | Monthly 30 GB |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Monto de la suscripción | 555.50 |

</Accordion>

<div data-zendesk-anchors="telecommunication=-telecomunicaciones h_01HGTAGFNFWKWYHPG6F5EK17YD=-telecomunicaciones h_01HGTAGFNG1Z8NAFJ71DP0YSYD=importante recommended-structures-for-predefined-events=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAGFNG99PQC03F13WQ4CVK=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAGFNGQ56C8CN7A325SQ7M=login-af_login h_01HGTAGFNG1W5QWGN1D969JHGY=complete-registration-af_complete_registration h_01HGTAGFNGRJHD89332473DZFE=content-view-af_content_view h_01HGTAGFNG10GNZVMDNXRJSYJ9=list-view-af_list_view h_01HGTAGFNGV82NQSZ29B96YJCQ=purchase-af_purchase recommended-structures-for-custom-events=estructuras-recomendadas-para-eventos-personalizados h_01HGTAGFNG3A2A6KCX8GGQAJBX=estructuras-recomendadas-para-eventos-personalizados h_01HGTAGFNGE3MKZEDKDZ0B9XDD=select-package-select_package h_01HGTAGFNGFSE2DAYRGG039GT9=topup-success-top_up_success h_01HGTAGFNGXBBYWJEMBVMN1YQS=topup-unsuccessful-top_up_unsuccessful h_01HGTAGFNGT3CJFRS2YC7R57KG=subscription-complete-subscription_complete" />
