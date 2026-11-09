---
title: Eventos de aplicación recomendados para eWallet
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
  created_at: '2021-06-10T11:36:07Z'
  edited_at: '2026-08-12T12:01:18Z'
  id: 4402425586065
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/4402425586065
---
> **En resumen:** mida la calidad de tus usuarios a lo largo de su recorrido registrando estos eventos in-app sugeridos para tu aplicación eWallet.

## <Image alt="InApp_Events_eWallet.png" src="https://files.readme.io/4d2ed4994bbe8e8eca7009b8ec8f5dbf22a626421a7a1efb213ddb4a12c7b487-4402543191825.png" width="67px" /> eWallet

Las aplicaciones de monedero electrónico permiten a los usuarios realizar pagos o compras digitales desde sus dispositivos. Los eventos típicos que sugerimos registrar incluyen agregar fondos, ver contenido, seleccionar comerciantes, ver promociones y completar transacciones.

Registrar estos eventos puede ayudarte a determinar:

* Qué tipo de contenido y promociones son populares entre los usuarios y luego les ofrecen productos similares o relacionados
* ¿Cuáles son los tipos de servicios más populares para los que los usuarios utilizan eWallet cuando pagan sus facturas?
* Qué comerciantes son los más populares

<div id="important" />

> 🚧 **Importante:**
>
> * Asegúrate de leer las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#configuración-de-eventos-in-app">instrucciones</Anchor> para marketers sobre la implementación de eventos in-app.
> * Para agilizar el proceso de implementación, usa nuestro <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ewallet">generador de eventos in-app</Anchor>. Esta herramienta incluye todos los eventos in-app típicos que se describen en este artículo y te permite modificar los eventos de acuerdo con tus necesidades comerciales. Una vez completado, comparte el archivo con tu desarrollador.
> * Para cada evento recomendado incluido en este artículo, hay <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ewallet&view=code">ejemplos de código</Anchor> para desarrolladores de iOS, Android y Unity.
> * Puedes encontrar instrucciones detalladas para tu desarrollador en el **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">centro para desarrolladores de AppsFlyer</Anchor>.**
>
> Para obtener más información sobre la grabación de eventos in-app, consulta la <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">guía de eventos in-app</Anchor>.

<Image align="center" alt="Flowchart_for_recommended_events e-Wallet_app_user_journey" src="https://files.readme.io/cf1f91f9c89d1f45448a6172e48b7f59fdce767f00c893d91b12a5f2d043945f-4404610923409.png" />

<div id="recommended-structures-for-predefined-events" />

## Estructuras recomendadas para eventos predefinidos

La siguiente sección proporciona una lista de las estructuras de eventos que son típicas de la vertical de eWallet. Cada estructura incluye un nombre de evento predefinido y los parámetros del evento sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Finalidad**

Descubrir cuántos usuarios instalaron la aplicación y completaron el proceso de registro, y qué métodos de registro prefieren tus usuarios.

**Disparador**

Cuando el usuario completa el proceso de registro.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_registration\_method | El tipo de método de registro | Correo electrónico, Facebook, Google |

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

<div id="content-view-af_content_view" />

<Accordion title="Vista de contenido (af_content_view)">

**Finalidad**

Determina la tasa de visualización de un contenido específico. Este evento puede ayudarte a:

* Comprender qué tipo de contenido es el más popular entre tus usuarios y, a continuación, intenta optimizar tus campañas de marketing
* Correlacionar las visualizaciones de artículos con las de los comerciantes

**Disparador**

Cuando el usuario ve el contenido de un artículo o categoría específico

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| Producto | Tipo de producto | entrada de cine |
| merchant\_name | Nombre del vendedor | cineplex |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estructuras recomendadas para eventos personalizados

La siguiente sección proporciona una lista de estructuras de eventos que incluye nombres de eventos personalizados y los parámetros de eventos sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="wallet-complete-topup-wallet_complete_topup" />

<Accordion title="Recarga completa de monedero digital (wallet_complete_topup)">

**Finalidad**

La recarga de fondos se puede usar para comprar cualquier paquete o cualquier otro servicio que se ofrezca dentro de la aplicación. Registra este evento y compáralo con otros datos para obtener más información sobre tus usuarios. Por ejemplo, puedes saber qué cantidades están dispuestas a depositar en sus cuentas y usar los montos de recarga para dirigirte a los usuarios con campañas personalizadas dentro de sus presupuestos de recarga.

**Disparador**

Cuando el usuario complete la recarga desde su banco o tarjeta de crédito a la aplicación eWallet

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| top\_up\_amount | Total del pago | 100 |
| top\_up\_method | Tipo de método de pago | transferencia bancaria |

</Accordion>

<div id="payment-transaction-completed-payment_transaction_completed" />

<Accordion title="Transacción de pago completada ( payment_transaction_completed )">

**Finalidad**

Este evento puede ayudarte a:

* Resaltar los usuarios que completaron el pago de una transacción.
* Identificar las transacciones grandes y, luego, volver a segmentar a los usuarios que hagan una recarga con una gran suma de dinero.

**Disparador**

Cuando se completa la transacción de una compra específica

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| Producto | Artículo pagado | recarga de tarjeta prepaga |
| cantidad | Total pagado | 1 |
| transaction\_amount | Importe de la transacción | 50 |

</Accordion>

<div id="bill-payment-success-bill_payment_success" />

<Accordion title="Pago de facturas exitoso (bill_payment_success)">

**Finalidad**

Este evento puede ayudarte a determinar el tipo de servicio más popular para el que los usuarios utilizan eWallet para pagar sus facturas (por ejemplo, facturas de agua, facturas de electricidad o saldos de tarjetas de crédito).

**Disparador**

Cuando el usuario utiliza la billetera electrónica para realizar pagos, como facturas, extractos de tarjetas de crédito o entradas de cine

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| merchant\_name | Nombre del comerciante | Proveedor de electricidad |
| payment\_amount | Total pagado | 100 |
| categoría | Tipo de servicio | Electricidad |

</Accordion>

<div id="promo-promo" />

<Accordion title="Promoción (promoción)">

**Finalidad**

Este evento puede ayudarte a determinar:

* Si la promoción que se ofrece es popular entre los usuarios
* Si la promoción ayuda a la venta cruzada de productos adicionales a los usuarios

**Disparador**

Cuando el usuario selecciona la promoción disponible en la aplicación

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| promo\_type | Tipo de promoción que se ofrece | 30% DE DESCUENTO |

</Accordion>

<div id="voucher-redeem-voucher_redeem" />

<Accordion title="Canjeo de cupones (voucher_redeem)">

**Finalidad**

Este evento puede ayudarte a determinar:

* Cuántos usuarios canjean códigos promocionales
* Qué tipo de cupones y descuentos prefieren los usuarios

**Disparador**

Cuando se canjea un código de promoción de usuario

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| voucher\_ID | ID del bono | 1735103 |
| merchant\_name | Nombre del comerciante | cineplex |

</Accordion>

<div id="select-merchant-select_merchant" />

<Accordion title="Selecciona un comerciante ( select_merchant )">

**Finalidad**

Este evento puede ayudarte a determinar qué comerciante es el más popular y luego usar estos datos para intentar que comerciantes similares se unan al servicio eWallet.

**Disparador**

Cuando el usuario selecciona un comerciante de la lista de comerciantes disponibles

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| merchant\_name | Nombre del comerciante | cineplex |
| tipo | Tipo de negocio | cine |
| cantidad | Moneda utilizada por el anunciante | USD (Dólar estadounidense) |
| merchant\_ID | ID específico adjunto a una empresa que indica a los sistemas de procesamiento de pagos involucrados en una transacción a dónde enviar qué fondos | 123456 |

</Accordion>

<div id="scan-barcode-success-scan_barcode_success" />

<Accordion title="El escaneo del código de barras se realizó correctamente ( scan_barcode_success )">

**Finalidad**

Este evento puede ayudarte a:

* Comprende cuándo un usuario completa una transacción específica con un comerciante
* Determina qué comerciantes son los más populares

**Disparador**

Cuando el usuario escanea el código QR de cada comerciante que visitó mediante la aplicación eWallet

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| merchant\_name | Nombre del comerciante | cineplex |
| merchant\_ID | ID específico adjunto a una empresa que indica a los sistemas de procesamiento de pagos involucrados en una transacción a dónde enviar qué fondos | 123456 |

</Accordion>

<div data-zendesk-anchors="ewallet=-ewallet h_01HGTAEVWFZXCA7AV0P35W992F=-ewallet h_01HGTAEVWFR4QS6XAT1T28N1R5=importante recommended-structures-for-predefined-events=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAEVWF8SVYTQMQ12219HX0=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAEVWFBA3CD7ZA40VCER95=complete-registration-af_complete_registration h_01HGTAEVWGDBN8B3P2YHQJ5RYF=login-af_login h_01HGTAEVWGYFYEZBD3ZED7GGFG=content-view-af_content_view recommended-structures-for-custom-events=estructuras-recomendadas-para-eventos-personalizados h_01HGTAEVWG39P9A84P926BG3VE=estructuras-recomendadas-para-eventos-personalizados h_01HGTAEVWGNYC5Z0ACHV8CFVNQ=wallet-complete-topup-wallet_complete_topup h_01HGTAEVWG36K4V4Z0NN8QYDNV=payment-transaction-completed-payment_transaction_completed h_01HGTAEVWG136M86GM1JPV74RH=bill-payment-success-bill_payment_success h_01HGTAEVWG34EXM28GW2ZN0NRC=promo-promo h_01HGTAEVWG0EHESWPQHCX4P3SH=voucher-redeem-voucher_redeem h_01HGTAEVWGKGC7N8ZB0MMQJ4YE=select-merchant-select_merchant h_01HGTAEVWG20101JC5VVK29Y0E=scan-barcode-success-scan_barcode_success" />
