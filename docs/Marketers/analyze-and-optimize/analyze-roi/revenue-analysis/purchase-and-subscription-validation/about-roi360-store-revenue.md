---
title: Sobre Store Revenue de ROI360
metadata:
  keywords:
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T16:34:39Z'
  edited_at: '2026-10-07T00:01:57Z'
  id: 42138855425297
  locale: es
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/es/articles/42138855425297
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** usa los ingresos de tienda de ROI360 para validar las compras y suscripciones in-app, evitar duplicados y calcular los ingresos netos.

> 🚧 **Dos puntos (:)**
>
> Los ingresos de la tienda ROI360 solo están disponibles para los clientes del plan premium de ROI360. Para verificar tu plan o realizar una actualización, ponte en contacto con tu Customer Success Manager (CSM).

Los ingresos de tienda de ROI360 son la solución premium de AppsFlyer para la medición completa y precisa de los ingresos procedentes de compras y suscripciones in-app. Proporciona una visión integral del ciclo de vida del cliente, lo que permite medir con precisión el retorno de la inversión publicitaria (ROAS).

| Función | Detalles |
| --- | --- |
| Alcance de la medición de ingresos | <ul><li>Ingresos procedentes de todas las compras in-app de productos y suscripciones gestionados a través de App Store Connect (iOS) y Google Play Console (Android)</li><li>Reembolsos</li><li>Ingresos por transacciones pendientes y diferidas (Android)</li><li>Eventos relacionados con suscripciones que se producen tanto dentro como fuera de la aplicación</li><li>Ingresos netos, que tienen en cuenta las comisiones de la tienda y los impuestos</li></ul> |
| Validación y precisión de los ingresos | La solución evita que se registren transacciones duplicadas. En iOS, esto también incluye evitar la duplicación causada por el uso compartido en familia. Los ingresos de tienda de ROI360 también pueden reenviar directamente a los anunciantes los datos de transacciones de la tienda de aplicaciones de Apple. |
| Fuentes de datos | <ul><li>Conector del SDK de compra de AppsFlyer para Android e iOS</li><li>Notificaciones del servidor de la App Store</li><li>Notificaciones para desarrolladores en tiempo real de Google Play (RTDN)</li></ul> |
| Reportes y disponibilidad de datos | Los datos de ingresos están disponibles en los dashboards y reportes de AppsFlyer, y también se pueden compartir con partners mediante postbacks. |

> ❗️ **Advertencia**
>
> Cuando uses los ingresos de tienda de ROI360, no envíes eventos de compra in-app, ya que esto dará lugar a informes de ingresos duplicados.

## ¿Cómo funcionan los ingresos de tienda de ROI360?

1. Un usuario realiza una compra in-app o una suscripción autorrenovable.
2. La aplicación realiza una transacción en la tienda de aplicaciones.
3. El conector del SDK de compra de AppsFlyer detecta automáticamente las compras y envía sus cargas útiles a AppsFlyer para su validación y registro.
4. AppsFlyer valida la compra con la tienda correspondiente para garantizar que no sea fraudulenta.
   * Tras una validación correcta, AppsFlyer registra el evento in-app de compra o suscripción.
   * Si la validación de recibos falla, el evento se muestra en el reporte de raw data de eventos in-app bloqueados (disponible para suscriptores de Protect360) y en la página Live events viewer con el parámetro `af_validated` = false.
5. AppsFlyer transfiere la respuesta al conector del SDK, que a su vez transfiere a la aplicación la respuesta de validación de recibos (correcta o fallida).
6. Todas las notificaciones entrantes del servidor de las tiendas de aplicaciones también se procesan mediante la lógica de negocio de AppsFlyer para ingresos por compras y suscripciones.
   * Las notificaciones sobre transacciones previamente reportadas a través del conector del SDK se validan y procesan, y dan como resultado la creación interna de un evento de compra o ciclo de vida.
   * Se eliminan las notificaciones relativas a transacciones desconocidas.
   * Para iOS, todas las notificaciones del servidor se pueden redirigir a tus propios servidores.

## Activa los ingresos de tienda de ROI360

Para activar la medición de ingresos de tienda de ROI360, sigue estos pasos:

1. En AppsFlyer, desde el menú lateral, abre <Image alt="settings-roi.png" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.17%" /> **Settings** y, en **ROI360** selecciona **Revenue Settings**.
2. Abre la pestaña **Compras y suscripciones**.
3. En **1 Choose Product type**, selecciona **ROI360**.
4. Haz clic en **Siguiente** para continuar.

## Configuración de Store Revenue de ROI360

Consulta el artículo <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-store-revenue">Configurar los ingresos de tienda de ROI360</Anchor>

## Referencia

En las siguientes secciones se ofrecen más detalles sobre aspectos clave de la medición de compras in-app (IAP) e ingresos por suscripción de ROI360. Esto incluye eventos y parámetros para eventos de IAP y suscripción, ingresos netos, que admiten cálculos de ingresos brutos a netos, y las características generales y limitaciones de la solución de medición de ingresos de IAP y suscripción de ROI360.

> 📘 **Nota:**
>
> Para enviar parámetros personalizados adicionales con tus eventos in-app, configura una **fuente de datos personalizada** en el <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-connector">Conector del SDK de Compra</Anchor>. Esto te permite enriquecer los eventos de compra y suscripción con tu propia lógica de negocio o metadatos.
> Estos parámetros estarán disponibles en el campo `custom_data` del reporte de raw data.

<div id="iaprelated-events-and-parameters" />

<Accordion title="Eventos y parámetros relacionados con IAP">

Las siguientes secciones muestran los eventos relacionados con IAP que AppsFlyer mide y los parámetros que se registran para cada evento. Consulta el [diccionario de parámetros de eventos](#parameter-dictionary) para obtener una explicación de los parámetros incluidos.

**Todos los eventos generados tienen las siguientes propiedades:**

* Eventos de servidor a servidor (S2S).
* Están disponibles en los reportes de raw data como eventos in-app orgánicos o no orgánicos, y se incluyen en los reportes de Revenue ETL Stores.
* Se envían a los Partners mediante postbacks.
* Compatible con SKAN Conversion Studio.

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Nota**

Se registra cuando un usuario realiza una compra.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_revenue
* af\_purchase\_currency
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code
* af\_net\_revenue\_factors

</Accordion>

<div id="purchase-af_purchase_free" />

<Accordion title="Compra gratuita (af_purchase_free)">

**Nota**

Se registra cuando un usuario realiza una compra que no tiene importe de ingreso. Todos los parámetros de ingresos mostrarán 0.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_revenue
* af\_purchase\_currency
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code
* af\_net\_revenue\_factors

</Accordion>

<div id="purchase-canceled-af_purchase_canceled" />

<Accordion title="Compra cancelada (af_purchase_canceled)">

**Nota**

Se registra cuando un usuario cancela una compra.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment

</Accordion>

<div id="purchase-pending-af_purchase_pending" />

<Accordion title="Compra pendiente (af_purchase_pending)">

**Nota**

Se registra cuando un usuario realiza una compra pero el pago aún no se ha procesado.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment

</Accordion>

<div id="refund-af_purchase_refund" />

<Accordion title="Reembolso (af_purchase_refund)">

**Nota**

Se registra cuando se reembolsa una compra.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* tipo de descuento af
* ingresos\_evento\_usd
* event\_revenue (incluido en el evento cuando los ingresos superan cero)
* store\_commission
* af\_revenue
* af\_purchase\_currency
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="test-purchase-af_purchase_sandbox_sdk" />

<Accordion title="Compra de prueba (af_purchase_sandbox_sdk)">

**Nota**

Se registra cuando se prueba una compra registrada a través del SDK en un entorno de pruebas.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_purchase\_state
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_net
* af\_sandbox\_revenue

</Accordion>

<div id="test-purchase-af_purchase_sandbox_s2s" />

<Accordion title="Compra de prueba (af_purchase_sandbox_s2s)">

**Nota**

Se registra cuando se prueba una compra registrada a través de S2S en un entorno de pruebas.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_purchase\_state
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_net
* af\_sandbox\_revenue

</Accordion>

</Accordion>

<div id="subscriptionrelated-events-and-parameters" />

<Accordion title="Eventos y parámetros relacionados con la suscripción">

Las siguientes secciones muestran los eventos relacionados con la suscripción que AppsFlyer mide, y los parámetros que se registran para cada evento. Consulta el [diccionario de parámetros de eventos](#parameter-dictionary) para obtener una explicación de los parámetros incluidos.

Todos los eventos generados:

* Se consideran eventos S2S.
* Son accesibles en los reportes de raw data (como eventos in-app orgánicos o no orgánicos).
* Se pueden enviar a los partners mediante postbacks.
* Se puede utilizar en SKAN Conversion Studio.

**Nota:** Dependiendo de la plataforma del dispositivo del usuario, algunos parámetros no siempre se completan para un evento in-app.

<div id="trial-started-af_ars_trial_started" />

<Accordion title="Prueba iniciada (af_ars_trial_started)">

**Nota**

Se registra cuando un suscriptor comienza un período de prueba.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_period\_type

</Accordion>

<div id="trial-canceled-af_ars_trial_canceled" />

<Accordion title="Prueba cancelada (af_ars_trial_canceled)">

**Nota**

Se registra cuando un abonado cancela la renovación automática de la suscripción durante el periodo de prueba. Si un usuario no restablece la renovación automática dentro del periodo de prueba, se produce un evento de churn.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_period\_type

</Accordion>

<div id="trial-churned-af_ars_trial_churned" />

<Accordion title="Prueba abandonada (af_ars_trial_churned)">

**Nota**

Se registra cuando un abonado se da de baja tras un periodo de prueba. Esto sucede después de la cancelación de la renovación automática y la expiración del período de prueba. También puede deberse a un problema técnico o de facturación con la renovación que provoque la pérdida de clientes.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_period\_type
* af\_motivo

</Accordion>

<div id="trial-converted-af_ars_trial_converted" />

<Accordion title="Prueba convertida (af_ars_trial_converted)">

**Nota**

Se registra cuando comienza una renovación a precio completo, después de un período de prueba.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_period\_type
* ID de descuento de af
* tipo de descuento af
* ingresos\_evento\_usd
* store\_commission
* af\_revenue (incluido en el evento solo cuando los ingresos superan cero)
* af\_purchase\_currency
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-started-af_ars_subscription_started" />

<Accordion title="Suscripción iniciada (af_ars_subscription_started)">

**Nota**

Se registra cuando se inicia una suscripción con descuento o a precio completo.

**Nota**:

* Las nuevas suscripciones solo pueden registrarse a través del conector del SDK.
* En el caso de iOS, si un suscriptor vuelve a comprar una suscripción que ya posee, el conector del SDK reporta a la aplicación una validación de recibos correcta, pero no registra una nueva transacción en AppsFlyer.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_period\_type
* ID de descuento de af
* tipo de descuento af
* ingresos\_evento\_usd
* event\_revenue (incluido en el evento cuando los ingresos superan cero)
* store\_commission
* af\_revenue
* af\_purchase\_currency
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-canceled-af_ars_subscription_canceled" />

<Accordion title="Suscripción cancelada (af_ars_subscription_canceled)">

**Nota**

Se registra cuando se cancela una suscripción de renovación automática en medio de un período de facturación. Si un usuario no restaura la renovación automática dentro del mismo período de facturación, sigue un evento de abandono.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-paused-af_ars_subscription_paused-android-only" />

<Accordion title="Suscripción en pausa (af_ars_subscription_paused) - Solo Android">

**Nota**

Se registra cuando un usuario detiene una suscripción activa.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-resumed-af_ars_subscription_resumed" />

<Accordion title="Suscripción reanudada (af_ars_subscription_resumed)">

**Nota**

Se registra cuando se reanuda una suscripción de precio completo después de una suscripción abandonada o reembolsada.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_period\_type
* ID de descuento de af
* tipo de descuento af
* af\_motivo
* event\_revenue (incluido en el evento cuando los ingresos por eventos superan cero)
* store\_commission
* af\_revenue
* af\_purchase\_currency
* af\_net\_revenue\_factors

</Accordion>

<div id="subscription-churned-af_ars_subscription_churned" />

<Accordion title="Suscripción abandonada (af_ars_subscription_churned)">

**Nota**

Se registra cuando un abonado se da de baja. Esto suele ocurrir tras la cancelación de la renovación automática o la expiración del período de facturación. También puede deberse a un problema técnico o de facturación, y la renovación puede provocar una pérdida de clientes.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_period\_type
* af\_motivo

</Accordion>

<div id="subscription-refunded-af_ars_subscription_refunded" />

<Accordion title="Suscripción reembolsada (af_ars_subscription_refunded)">

**Nota**

Se registra cuando se emite un reembolso al suscriptor.

**Note:**

* Este evento suele generarse junto con un valor negativo. En los casos en los que es imposible detectar qué transacciones fueron reembolsadas, o los detalles del reembolso no están incluidos en la notificación, el evento de reembolso no muestra ningún valor.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_motivo
* af\_subscription\_ownership\_type
* ID de descuento de af
* tipo de descuento af
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_refunded\_transaction\_ids
* ingresos\_evento\_usd
* event\_revenue (incluido en el evento cuando los ingresos superan cero)
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* tienda\_af
* af\_environment
* af\_period\_type
* store\_commission
* af\_revenue
* af\_purchase\_currency
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-billing-grace-af_ars_subscription_billing_grace" />

<Accordion title="Gracia de facturación de la suscripción (af_ars_subscription_billing_grace)">

**Nota**

Se registra cuando una renovación de la suscripción falla por un problema de facturación y el suscriptor entra en el periodo de gracia de facturación.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-renewed-af_ars_subscription_renewed" />

<Accordion title="Suscripción renovada (af_ars_subscription_renewed)">

**Nota**

Se registra cuando tiene lugar una suscripción con renovación automática.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_period\_type
* ID de descuento de af
* tipo de descuento af
* ingresos\_evento\_usd
* event\_revenue (incluido en el evento cuando los ingresos superan cero)
* store\_commission
* af\_revenue
* af\_purchase\_currency
* af\_net\_revenue\_factors

</Accordion>

<div id="subscription-changed-af_ars_subscription_xgraded" />

<Accordion title="Suscripción modificada (af_ars_subscription_xgraded)">

**Nota**

Se registra cuando un suscriptor actualiza, baja de categoría o cambia de producto.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_period\_type
* ID de descuento de af
* tipo de descuento af
* ingresos\_evento\_usd
* event\_revenue (incluido en el evento cuando los ingresos superan cero)
* store\_commission
* af\_revenue
* af\_purchase\_currency
* af\_net\_revenue\_factors

</Accordion>

<div id="existing-subscriber-af_ars_existing_subscriber" />

<Accordion title="Suscriptor existente (af_ars_existing_subscriber)">

**Nota**

Se registra cuando se notifica al conector del SDK sobre un suscriptor en medio de un ciclo de facturación, antes de recibir una notificación de seguimiento del servidor que transfiere al suscriptor a otra etapa del ciclo de vida relevante. Este evento generalmente se genera durante tu periodo de onboarding y adopción del conector del SDK.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* País
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated

</Accordion>

<div id="test-purchase-af_ars_sandbox_sdk" />

<Accordion title="Compra de prueba (af_ars_sandbox_sdk)">

**Nota**

Se registra cuando se prueba una compra registrada a través del SDK en un entorno de pruebas.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* País
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* ID de descuento de af
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated
* af\_net
* af\_sandbox\_revenue

</Accordion>

<div id="test-purchase-af_ars_sandbox_s2s" />

<Accordion title="Compra de prueba (af_ars_sandbox_s2s)">

**Nota**

Se registra cuando se prueba una compra registrada a través de S2S en un entorno de pruebas.

**Parámetros**

* id\_aplicación
* id\_usuario\_cliente
* País
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* ID de descuento de af
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* id\_transacción\_af
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* tienda\_af
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated
* af\_net
* af\_sandbox\_revenue

</Accordion>

</Accordion>

<div id="parameter-dictionary" />

<Accordion title="Diccionario de parámetros">

Los parámetros de los eventos de IAP y suscripción se muestran en los reportes de raw data, ya sea como sus propias columnas o rellenados como parte del **valor del evento**.

Los parámetros que tienen sus propias columnas son:

* id\_aplicación
* id\_usuario\_cliente
* código\_de\_país
* af\_currency
* ingresos\_evento\_usd
* af\_revenue
* android\_id
* ip
* idfa
* appsflyer\_id

Consulta el <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary">diccionario de campos de datos</Anchor> para obtener más información sobre estos parámetros.

En la siguiente tabla se describen los parámetros de raw data disponibles en los eventos ARS y VIAP.

| Parámetro | Nota | Producto |
| --- | --- | --- |
| af\_cancelation\_date\_ms | Push API: siempre contiene ambos campos, USD y moneda seleccionada. | IAP |
| af\_cuids | <ul><li>Limitar el seguimiento de anuncios</li><li>El array de CUIDs se muestra independientemente de los ID de dispositivo. De esta manera, los mismos CUIDs pueden mostrarse para más de un ID de dispositivo.</li></ul> | Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>. |
| ID de descuento de af | El ID de la oferta presentado al usuario durante la compra inicial. El ID se completa solo cuando hay un código de descuento. | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| tipo de descuento af | El tipo de descuento utilizado por el usuario. Posibles valores:<ul><li>IOS<ul><li>Valor real del click-ID proveniente de la URL de destino, utilizado para enviar señales y resolver la jerarquía completa de la campaña mediante APIs de partners.</li><li>promocional</li><li>offer\_codes</li><li>win\_back</li></ul></li><li>Android<ul><li>El ID devuelto por la ad network como identificador de palabra clave.</li><li>one\_time\_code</li><li>vanity\_code</li></ul></li></ul> | Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>. |
| af\_environment | **Clics**: | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_expires\_date\_ms | ciudad | Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>. |
| af\_purchase\_currency | Ingresos netos calculados en función de todos los factores considerados. Consulta af\_net\_revenue\_factors. | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_net\_revenue\_country | <ul><li><Anchor target="_blank" href="https://www.nationsonline.org/oneworld/country_code_list.htm">Código ISO de dos letras del país</Anchor> al que se aplica el impuesto.</li><li>Ejemplo: CA</li><li>Nota: Para el Reino Unido, el código aplicado es UK, no GB.</li></ul> | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_net\_revenue\_factors | <ul><li>Una matriz que representa todas las razones factorizadas que producen la cantidad reportada de net\_revenue.</li><li>Ejemplo de valor: store\_commission</li></ul> | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_net\_revenue\_postal\_code | <ul><li>Si es verdadero, la campaña recibe la atribución por generar la instalación.</li><li>Regla de motivo de bloqueo (obsoleta)</li></ul> | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_net\_revenue\_subdivision | <ul><li>Para algunos países, puede existir un estado/subdivisión adicional. Esto se maneja según los <Anchor target="_blank" href="https://service.unece.org/trade/locode/2023-1%20SubdivisionCodes.htm">códigos de subdivisión ISO 3166-2</Anchor>.</li><li>MARCA DE TIEMPO</li><li>Si es verdadero, la app se volvió a descargar.</li></ul> | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_net\_revenue\_tax\_exclusive | <ul><li>Entorno</li><li>MARCA DE TIEMPO</li><li>Verdadero significa que el impuesto se suma a los ingresos totales declarados.</li></ul> | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_net\_revenue\_tax\_name | <ul><li>UA: Reinstalar</li><li>Campaña del contributor[n]</li></ul> | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_net\_revenue\_tax\_rate | <ul><li>PBA - evento</li><li>Ubicación del anuncio que contiene el enlace de la siguiente manera:</li></ul> | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_offer\_id | <ul><li>El ID de la oferta aplicado a la transacción, cuando corresponda (por ejemplo, en ofertas con descuento o promocionales).</li><li>Solo para Android</li></ul> | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_order\_id | <ul><li>El ID del pedido de la transacción</li><li>Solo para Android</li></ul> | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_original\_transaction\_id | <ul><li>Plataforma del dispositivo: android, ios, windowsphone, smartcast, tizen, roku, webos, vidaa, playstation, xbox, switch, steam, epic, nativepc, quest</li><li>Sólo iOS</li></ul> | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_original\_transaction\_id | <ul><li>El ID original de la transacción</li><li>Sólo iOS</li></ul> | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_period\_type | <ul><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li><li>Posibles valores:<ul><li>Prueba</li><li>intro</li><li>Normal</li></ul></li></ul> | Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>. |
| af\_product\_id | Valores posibles: preload, click\_to\_download, click\_to\_app, engaged\_click, engaged\_view, view, listening, click\_unspecified, impression\_unspecified | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_purchase\_date\_ms | Redireccionamiento | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_purchase\_option\_id | <ul><li>Nuevas instalaciones</li><li>Solo para Android</li></ul> | IAP |
| af\_purchase\_option\_type | El tipo de opción de compra de la transacción. Valores posibles (Android):<ul><li>comprar</li><li>alquilar</li></ul> | IAP |
| af\_purchase\_state | Posibles valores:<ul><li>Idéntico a [idfv](#device-info::8471310d).</li><li>El valor representa la fuente de anuncios web atribuibles.</li><li>ID de publicidad para dispositivos Android</li></ul> | IAP |
| af\_purchase\_token | <ul><li>Si este campo está vacío, la ad network no pudo completarlo.</li><li>Solo para Android</li></ul> | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_motivo | [sin cambios] | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_refunded\_transaction\_ids | <ul><li>Enlace</li><li>Sólo iOS</li></ul> | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| tienda\_af | sin valores | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| af\_subscription\_ownership\_type | FAMILY\_SHARED significa que el usuario tiene acceso mediante el uso compartido familiar. PURCHASED significa que el usuario que pagó realizó la compra. | Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>. |
| id\_transacción\_af | <ul><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li><li>Sólo iOS</li></ul> | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |
| store\_commission | <ul><li>Entero</li><li>Cadena</li><li>Cadena</li></ul> | <ul><li>IAP</li><li>Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.</li></ul> |

</Accordion>

<div id="true-revenue" />

<Accordion title="Ejemplo">

Los ingresos netos son una capa de lógica empresarial creada para dar servicio a la solución de ingresos de tienda de ROI360. Calcula automáticamente el valor de los ingresos netos de cada transacción entrante en tiempo real y lo incluye en los reportes.

> 📘 **Advertencia**
>
> Los ingresos netos se muestran en los reportes de raw data y se pueden enviar en tiempo real mediante postbacks de eventos in-app. También está disponible en <Anchor target="_blank" href="/marketers/es/docs/my-dashboards">My Dashboards</Anchor> como métricas netas (ingresos netos, ROI neto, ROAS neto, ARPU neto, beneficio neto).
>
> Para enviar los ingresos netos en los postbacks, configura el evento in-app con la opción **Valores, ingresos & ingresos netos**. Consulta <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#datos-a-incluir-en-los-postbacks">Configuración del postback de eventos in-app</Anchor> para obtener más información.

> 📘 **Consejo**
>
> También puedes configurar los postbacks de tus eventos in-app para enviar los ingresos netos en lugar de los ingresos brutos para el parámetro estándar de ingresos (monetario). Para obtener acceso a esta configuración, ponte en contacto con tu Customer Success Manager (CSM).

Los ingresos netos tienen en cuenta los siguientes factores en el cálculo de los ingresos brutos a netos:

* **Comisión de la tienda**:
  * Se calcula y se reporta automáticamente. No se requiere ninguna acción de tu parte.
  * En las compras (IAP), la comisión predeterminada de la tienda depende del escaparate:
    * App Store — Japón y países de la UE: 26%. China continental (CN): 25%. Resto del mundo: 30%.
    * Tienda Play: 30%.
  * En las suscripciones, la comisión se calcula automáticamente por suscriptor, según la antigüedad del suscriptor.
    * App Store — primeros 12 meses: 26% en Japón y los países de la UE, 25% en China continental (CN) y 30% en el resto del mundo. A partir del mes 13: 15% en Japón, 12% en China continental (CN) y 15% en el resto del mundo.
    * Tienda Play: 15% desde el primer día.
  * Los parámetros de ingresos netos relacionados están disponibles en los reportes de raw data.
  * Usa <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-7">la API de ingresos netos</Anchor> para establecer una tasa de comisión de la tienda distinta de la predeterminada. Esto es útil, por ejemplo, si tu aplicación está inscrita en el programa para pequeñas empresas de Apple, donde la tasa de comisión es del 15% (12% en China continental (CN)).
* **Impuesto**:
  * El impuesto es reportado por defecto para cualquier transacción medida por ROI360 usando la configuración de tasa de impuesto por defecto.
  * Esto se aplica a los países con impuestos incluidos (donde los impuestos están incluidos en el precio de lista). Así, por ejemplo, en el Reino Unido, AppsFlyer deduce la suma de los impuestos y la comisión de la tienda. En los países sin impuestos incluidos, como EE. UU., donde el precio de lista no incluye impuestos, los parámetros de ingresos e ingresos netos no incluyen impuestos de forma predeterminada.
  * La configuración puede editarse con <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-7">la API de ingresos netos</Anchor>. Para saber qué países son compatibles y cuáles son sus tipos impositivos predeterminados, consulta <Anchor target="_blank" href="https://docs.google.com/document/d/e/2PACX-1vSl3DwlK2Gt2aa5gmDzD3-K3CtnIM85oMNrqx3PCTamwCERWYU48GugNpD31BFjA2PJjZnqaXIVe2Hx/pub">este archivo JSON</Anchor>. El desarrollador puede editarlo o utilizarlo tal y como está en la API.

Cuando se visualizan los ingresos netos en los reportes, los siguientes parámetros contienen los datos de los ingresos netos. Consulta el [diccionario de parámetros](#parameter-dictionary) para obtener más detalles.

| Parámetro | Factor de ingresos netos |
| --- | --- |
| `store_commission` | Entero |
| `af_net_revenue_tax_name` | Impuesto |
| `af_net_revenue_tax_rate` | Impuesto |
| `af_net_revenue_tax_exclusive` | Impuesto |
| `af_net_revenue_postal_code` | Impuesto |
| `af_net_revenue_country` | Impuesto |
| `af_net_revenue_subdivision` | Impuesto |
| `af_purchase_currency` | <ul><li>Entero</li><li>Impuesto</li></ul> |
| `af_net_revenue_factors` | <ul><li>Entero</li><li>Impuesto</li></ul> |

</Accordion>

<div id="troubleshooting-and-disprepancies" />

<Accordion title="Resolución de problemas y discrepancias">

| Síntoma | Explicación / Solución |
| --- | --- |
| AppsFlyer muestra menos eventos de compra in-app y suscripción que las tiendas de aplicaciones reales. | En AppsFlyer, los eventos solo se generan para los usuarios que han actualizado a una versión de la aplicación que incluye el conector SDK. Mientras tanto, las tiendas de aplicaciones registran cada evento, independientemente de la versión de la aplicación del usuario. En consecuencia, hasta que se adopte por completo la versión actualizada de la aplicación, es normal que haya una discrepancia entre los datos de ingresos de la aplicación y los de la tienda. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Especificaciones y limitaciones">

| Especificación | Producto | Nota |
| --- | --- | --- |
| Suscripciones a plazos (Android) | Ingresos por suscripción | No compatible |
| Transacciones de suscripción  <br />pendientes (Android) | Ingresos por suscripción | No compatible |
| Nuevas suscripciones | Ingresos por suscripción | Solo registrados a través del SDK de compra de AppsFlyer |
| Cambio de precio | Ingresos por suscripción | Si los ingresos por suscripción no reciben una notificación generada por el SDK con el nuevo precio del producto, siguen reportando el precio anterior del producto como ingresos. Una vez que se recibe el nuevo precio del producto desde el SDK de compra, se registra. |
| Ingresos brutos | <ul><li>IAP</li><li>Ingresos por suscripción</li></ul> | Compatible |
| Ejemplo | <ul><li>IAP</li><li>Ingresos por suscripción</li></ul> | Compatible con raw data y con My Dashboards (como las métricas Net) |
| Reembolsos | IAP | Se pueden reportar hasta 180 días después de la compra original. |
| Eliminación de duplicados | <ul><li>IAP</li><li>Ingresos por suscripción</li></ul> | Compatible con transacciones reportadas hasta 180 días después de la fecha del evento. |
| Modo estricto del SDK | <ul><li>IAP</li><li>Ingresos por suscripción</li></ul> | Las suscripciones ROI360 y el IAP son compatibles con el modo estricto del SDK desde el:<ul><li>AppsFlyer iOS purchase SDK connector V6.13.0</li><li>Unity purchase SDK connector V2.0.1</li></ul> |
| Truemoney | <ul><li>IAP</li><li>Ingresos por suscripción</li></ul> | Los ingresos se reportan en la divisa original (usando el parámetro event\_revenue) y en USD (usando el parámetro event\_revenue\_usd). |
| Actualización de datos | <ul><li>IAP</li><li>Ingresos por suscripción</li></ul> | <ul><li>Reporte de ingresos de la tienda a nivel de transacción: Por hora</li><li>Reporte de ingresos de tienda a nivel de dispositivo: Cada 8 horas</li></ul> |
| StoreKit 2 | <ul><li>IAP</li><li>Ingresos por suscripción</li></ul> | <ul><li>StoreKit 2 es compatible a partir de la versión 6.16.2 del conector de SDK de compras.</li><li>Asegúrate de que tu app use las credenciales actualizadas de App Store descritas <Anchor target="_blank" href="/marketers/es/docs/bulletin-update-app-store-credentials-for-ios-roi360-receipt-validation">aquí</Anchor>.</li></ul> |
| Productos puntuales de Google | IAP | <ul><li>Opciones de compra compatibles: Comprar y alquilar</li><li>Reserva anticipada: No compatible</li></ul> |

</Accordion>

<div data-zendesk-anchors="h_01KSAJW61CZZBWBQ112VR5095C=dos-puntos- h_01KD0W3J6105033NV6FYKGQ8BQ=advertencia how-does-roi360-store-revenue-work=c%C3%B3mo-funcionan-los-ingresos-de-tienda-de-roi360 h_01KD2JZQ0JYVF8S1E2W3N91KYV=c%C3%B3mo-funcionan-los-ingresos-de-tienda-de-roi360 enable-roi360-store-revenue=activa-los-ingresos-de-tienda-de-roi360 h_01KD2JZQ0JS9YQ2SPNN6NHAJEH=activa-los-ingresos-de-tienda-de-roi360 set-up-roi360-store-revenue=configuraci%C3%B3n-de-store-revenue-de-roi360 h_01KD2JZQ0JD53598CES8ECAHR3=configuraci%C3%B3n-de-store-revenue-de-roi360 reference=referencia h_01JKWGTJQY938NV6VCJ7KKS23E=referencia h_01KD6B3KC75RFDV08G9RT1BX1M=nota h_01HDEPSK8DFQ24EZ5T0EPBSVS4=iaprelated-events-and-parameters 01H8VJJP1ER9N6BPAES8H8CK4T=purchase-af_purchase h_01J50N58GYF2BYC57HA7THSWW6=purchase-af_purchase_free 01H8VJJP1EXYE1EQS08CK8BG02=purchase-canceled-af_purchase_canceled 01H8VJJP1ET5TAAQ17EMK6TVRE=purchase-pending-af_purchase_pending 01H8VJJP1E8JKPGT2V9CCB1XW8=refund-af_purchase_refund 01H8VJJP1ECQMS49M8Z1X1FT4B=test-purchase-af_purchase_sandbox_sdk 01H8VJJP1E3X7YZNYT5D8REVEW=test-purchase-af_purchase_sandbox_s2s h_01HDEQBACTTPZ04YYD1KV49SEZ=subscriptionrelated-events-and-parameters 01H8VJJP1EHAZBGT82WRWB00JT=trial-started-af_ars_trial_started 01H8VJJP1ETCHTK6JMK9ERS5A5=trial-canceled-af_ars_trial_canceled 01H8VJJP1EC45X8PJVPWT3G7S3=trial-churned-af_ars_trial_churned 01H8VJJP1EYPQM50JVX1KPZXAZ=trial-converted-af_ars_trial_converted 01H8VJJP1EA4WTCEJWBB1HPRJF=subscription-started-af_ars_subscription_started 01H8VJJP1EF744NE425Y30VG0M=subscription-canceled-af_ars_subscription_canceled 01H8VJJP1EMKBP27070NRR9CZ5=subscription-paused-af_ars_subscription_paused-android-only 01H8VJJP1EGHNQ35JM1TWV4ND0=subscription-resumed-af_ars_subscription_resumed 01H8VJJP1EM2GJ28VBE6V76SBG=subscription-churned-af_ars_subscription_churned 01H8VJJP1E28XXAQSGZ9PYDT08=subscription-refunded-af_ars_subscription_refunded 01H8VJJP1E399B2AVWP9VKZ0D4=subscription-billing-grace-af_ars_subscription_billing_grace 01H8VJJP1EEZZ0DE75VXAZQP3E=subscription-renewed-af_ars_subscription_renewed 01H8VJJP1FGXHRK3J0XB2G4PCQ=subscription-changed-af_ars_subscription_xgraded 01H8VJJP1FKC8KZ2HKJVGZEV23=existing-subscriber-af_ars_existing_subscriber 01H8VJJP1F720QT97Q0TW4SEM2=test-purchase-af_ars_sandbox_sdk 01H8VJJP1FSRHG26EXMEG3325P=test-purchase-af_ars_sandbox_s2s 01H8VJJP1F0ZV2PX39D9JCG6B4=parameter-dictionary 01H8VJJP1FF219YN3XHRCGW7Z3=true-revenue h_01KBFWTM4XJ417930YVDD36ASK=advertencia-1 h_01KRKEP613DR8RZ5Q2A5H7KZAH=consejo 01JHZG8FFHTYE2PMRWWS8WNR6X=troubleshooting-and-disprepancies 01H8VJJP1FP2MPRF8AN77REXD0=traits-and-limitations" />
