---
title: Validación de compras y suscripciones - General
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-20T16:30:47Z'
  edited_at: '2026-09-29T00:01:07Z'
  id: 42120228484241
  locale: es
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/es/articles/42120228484241
---
> **At a glance:** Entiende cómo AppsFlyer valida compras y suscripciones, y compara las dos soluciones disponibles: Validación de recibos e ingresos de la tienda ROI360.

## Sobre la validación de compras y suscripciones

La validación de compras y suscripciones es esencial para garantizar la precisión y fiabilidad de tus datos de ingresos. Cuando los usuarios realizan compras en tu aplicación, ya sean puntuales o por suscripción, validar esas transacciones con las tiendas de aplicaciones (App Store de Apple y Google Play) asegura que solo se midan y atribuyan las transacciones legítimas y pagadas.

AppsFlyer ofrece dos soluciones que validan y miden las compras in-app y los ingresos por suscripción: Validación de recibos e ingresos de la tienda ROI360.

El artículo ofrece una introducción general a cada solución y [una comparación de funcionalidades](#comparación-entre-la-validación-de-recibos-y-store-revenue-de-roi360) para ayudarte a determinar qué opción es la adecuada para tu aplicación.

## Las dos soluciones para la validación de compras y suscripciones

### Validación de recibos

La validación de recibos es la solución gratuita de AppsFlyer para verificar compras y suscripciones dentro de la aplicación en iOS y Android. Asegura que solo se midan transacciones reales. Esto se hace validando recibos directamente con las tiendas de aplicaciones.

Usando esta solución, el SDK de AppsFlyer integrado en tu aplicación proporciona datos mínimos, como el ID del producto, el ID de compra y el tipo. AppsFlyer luego recupera los detalles completos de ingresos de la respuesta de la tienda. Esto incluye el monto y la moneda. Esta solución no proporciona cálculo de ingresos netos, cobertura completa del funnel de suscripción, gestión de reembolsos, medición completa de IAP ni detección y deduplicación automatizadas de compras &.

Utiliza la validación de recibos para tomar decisiones informadas y optimizar campañas basadas en datos de ingresos verificados.

Para más información, consulta:

* <Anchor target="_blank" href="/marketers/es/docs/about-receipt-validation">Sobre la validación de recibos</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/set-up-receipt-validation">Configurar la validación de recibos</Anchor>

### Ingresos de la tienda ROI360 Premium

> 🚧 **Importante**
>
> Los ingresos de la tienda ROI360 solo están disponibles para los clientes del plan premium de ROI360. Para verificar tu plan o realizar una actualización, ponte en contacto con tu Customer Success Manager (CSM).

La solución de ingresos de la tienda de ROI360 es el producto premium de AppsFlyer para la medición completa y precisa de ingresos de compras y suscripciones dentro de la aplicación. Valida transacciones de servidor a servidor con las tiendas de aplicaciones y devuelve datos de ingresos verificados y enriquecidos.

Dentro de este flujo de validación de servidor a servidor, Store Revenue de ROI360 proporciona deduplicación, calcula ingresos netos después de tarifas e impuestos de la tienda, y ofrece cobertura completa del ciclo de vida de la suscripción, incluyendo renovaciones, cancelaciones, reembolsos y mejoras. También procesa eventos de suscriptores existentes y resuelve pagos retrasados de tiendas como Google Play.

Utiliza esta solución si necesitas una precisión total de ingresos, insights sobre el ciclo de vida de suscripciones y soporte para modelos de negocio complejos.

Para más información, consulta:

* <Anchor target="_blank" href="/marketers/es/docs/about-roi360-store-revenue">Sobre Store Revenue de ROI360</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-store-revenue">Configuración de Store Revenue de ROI360</Anchor>

## Comparación entre la validación de recibos y Store Revenue de ROI360

Utiliza las tablas a continuación para determinar qué solución se adapta mejor a tus necesidades.

<Accordion title="Comparar características">

| **Función** | **Validación de recibos** | **Ingresos de la tienda ROI360** Premium |
| --- | --- | --- |
| **Validación de recibos**  <br />Verifica las compras in-app para filtrar las transacciones fraudulentas. | ✔ | ✔ |
| **Detección automatizada de compras & deduplicación**  <br />Detecta automáticamente las compras in-app (IAP) y las suscripciones, incluidas las transacciones de suscriptores existentes, y elimina los duplicados para generar reportes más limpios. | ✖ | ✔ |
| **Gestión de reembolsos**  <br />Detecta los reembolsos y los atribuye a la compra original para reflejar los ingresos reales. | ✖ | ✔* |
| **Medición completa de IAP**  <br />Gestiona el uso compartido en familia y reporta el resultado final de las compras pendientes mediante la confirmación de App Store. | ✖ | ✔ |
| **Cobertura completa del funnel de suscripción**  <br />Mide renovaciones, mejoras y conversiones para reflejar el valor total de tu base de suscriptores. | ✖ | ✔ |
| **Cálculo de ingresos netos**  <br />Calcula tanto los ingresos brutos como los netos deduciendo automáticamente las comisiones de la tienda y los impuestos. | ✖ | ✔ |

* La gestión de reembolsos **para compras in-app** solo está disponible en el plan ROI360 Advanced.

</Accordion>

<Accordion title="Compara el soporte de eventos de compra in-app">

| **Event name** | **Validación de recibos** | **Ingresos de la tienda ROI360** |
| --- | --- | --- |
| af\_compra | ✔ | ✔ |
| af\_purchase\_refund* | ✖ | ✔ |
| af\_purchase\_pending | ✖ | ✔ |
| af\_purchase\_canceled* | ✖ | ✔ |
| af\_purchase\_free | ✖ | ✔ |
| af\_purchase\_sandbox\_sdk | ✔ | ✔ |
| af\_purchase\_sandbox\_s2s* | ✖ | ✔ |

* Disponible solo en el plan ROI360 Advanced.

</Accordion>

<Accordion title="Compara el soporte de eventos relacionados con suscripciones">

| **Event name** | **Validación de recibos** | **Ingresos de la tienda ROI360** |
| --- | --- | --- |
| af\_ars\_trial\_started | ✔ | ✔ |
| af\_ars\_trial\_canceled | ✖ | ✔ |
| af\_ars\_trial\_churned | ✖ | ✔ |
| af\_ars\_trial\_converted | ✖ | ✔ |
| af\_ars\_subscription\_started | ✔ | ✔ |
| af\_ars\_subscription\_canceled | ✖ | ✔ |
| af\_ars\_subscription\_paused | ✖ | ✔ |
| af\_ars\_subscription\_resumed | ✖ | ✔ |
| af\_ars\_subscription\_churned | ✖ | ✔ |
| af\_ars\_subscription\_refunded | ✖ | ✔ |
| af\_ars\_subscription\_billing\_grace | ✖ | ✔ |
| af\_ars\_subscription\_renewed | ✖ | ✔ |
| af\_ars\_subscription\_xgraded | ✖ | ✔ |
| af\_ars\_existing\_subscriber | ✖ | ✔ |
| af\_ars\_sandbox\_sdk | ✔ | ✔ |
| af\_ars\_sandbox\_s2s | ✖ | ✔ |

</Accordion>

<div data-zendesk-anchors="about-purchase-validation=sobre-la-validaci%C3%B3n-de-compras-y-suscripciones h_01KCY9DHB7PBM3CZS65WMHR8B5=sobre-la-validaci%C3%B3n-de-compras-y-suscripciones appsflyer-solutions=las-dos-soluciones-para-la-validaci%C3%B3n-de-compras-y-suscripciones h_01KCY9DHB7XKWP0P8WMTSXVT4A=las-dos-soluciones-para-la-validaci%C3%B3n-de-compras-y-suscripciones receipt-validation=validaci%C3%B3n-de-recibos h_01KCY9DHB7DC66Q3H9W9064CZY=validaci%C3%B3n-de-recibos roi360-store-revenue=ingresos-de-la-tienda-roi360premium h_01KCY9DHB70VN27BYR3ZG0JD86=ingresos-de-la-tienda-roi360premium h_01KSAJM50XFXVQXZC59D1BE5XN=importante compare-receipt-validation-and-roi360-stores-revenue=comparaci%C3%B3n-entre-la-validaci%C3%B3n-de-recibos-y-store-revenue-de-roi360 h_01KCY9DHB7RJ89GB5CM29T2AK5=comparaci%C3%B3n-entre-la-validaci%C3%B3n-de-recibos-y-store-revenue-de-roi360" />
