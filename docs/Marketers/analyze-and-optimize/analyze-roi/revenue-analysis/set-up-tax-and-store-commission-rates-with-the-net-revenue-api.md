---
title: Editar mediciones de ingresos netos mediante la Tax API
metadata:
  keywords:
    - Revenue
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
  created_at: '2024-11-28T13:57:14Z'
  edited_at: '2026-08-17T11:43:09Z'
  id: 30468586765841
  locale: es
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/es/articles/30468586765841
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** Configura cómo AppsFlyer calcula los ingresos netos de las compras in-app y las suscripciones mediante la API de Net Revenue para personalizar las tasas de comisión de la tienda y las reglas fiscales por aplicación. Esto garantiza que tus reportes reflejen con precisión las ganancias reales, incluidos los casos con comisiones no estándar o reglas fiscales específicas.

Los ingresos netos son una capa de lógica empresarial creada para servir a la solución de ingresos por suscripción y compras in-app de ROI360 de AppsFlyer. La configuración predeterminada refleja las comisiones estándar y las reglas fiscales que aplican la tienda de aplicaciones y Google Play. Si la comisión de tu tienda difiere o si operas en un país con un tratamiento fiscal especial, usa la API de Net Revenue para anular la configuración predeterminada.

La API de Net Revenue se implementa mediante dos API REST que te permiten configurar las tasas de comisión de la tienda y las reglas fiscales para aplicaciones individuales.

* [Tasas de comisión de la tienda](https://dev.appsflyer.com/hc/reference/post_store-commission-rates): crea, actualiza, obtén o elimina tasas de comisión de la tienda para una o varias aplicaciones. Cada aplicación puede tener una tasa de comisión específica en función de varios programas de la tienda.
* [Reglas de tipos impositivos](https://dev.appsflyer.com/hc/reference/post_tax-rates-app-app-id): crea u obtén reglas de tipos impositivos personalizadas para una aplicación específica.

Para obtener más información sobre cómo se calculan los ingresos netos, consulta <Anchor target="_blank" href="/marketers/es/docs/about-roi360-store-revenue#true-revenue">Ingresos netos</Anchor>.

<div id="note" />

> 📘 **Nota:**
>
> Los ingresos netos se muestran en los reportes de raw data y en My Dashboards como las métricas netas (ingresos netos, ROI neto, ROAS neto, ARPU neto, beneficio neto).

<div id="update-tax-rate-rules" />

## Actualizar reglas de tipos impositivos

El impuesto es reportado por defecto para cualquier transacción medida por ROI360 usando la configuración de tasa de impuesto por defecto. En los *países con impuestos incluidos*, donde el impuesto está incluido en el precio de lista, los ingresos netos se calculan después de deducir el impuesto. Por ejemplo, en el Reino Unido, AppsFlyer deduce la suma del impuesto y la comisión de la tienda. En los *países con impuestos excluidos*, como EE. UU., donde el precio de lista no incluye impuestos, los parámetros de ingresos e ingresos netos no incluyen impuestos de forma predeterminada.

Para configurar las reglas de tipos impositivos con la API de Net Revenue, sigue estos pasos:

1. Completa los siguientes pasos en la configuración de ingresos de la tienda de ROI360:

   <div id="ios" />

   <Accordion title="apps de iOS,">

   * <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-store-revenue#paso-1-ios-configura-las-claves-de-app-store-connect">1. Configurar claves de App Store Connect</Anchor>
   * <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-store-revenue#paso-2-ios-configura-las-notificaciones-del-servidor-de-app-store">2. Configurar las notificaciones del servidor de la App Store</Anchor>

   </Accordion>

   <div id="android" />

   <Accordion title="Android">

   * <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-store-revenue#paso-1-android-configurar-la-clave-de-cuenta-de-servicio-y-los-permisos">1. Configurar la clave de cuenta de servicio y los permisos</Anchor>
   * <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-store-revenue#paso-2-android-configura-las-notificaciones-del-servidor-de-google-play">2. Configurar las notificaciones del servidor de Google Play</Anchor>

   </Accordion>

2. Comparte con tu desarrollador:
   * El <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">token API V2</Anchor> para usarlo como clave de autorización.
   * Los parámetros y valores que contienen información sobre qué impuestos calcular, como se indica en la tabla a seguir.
3. Dile a tu desarrollador que siga las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-tax-rate-rule">instrucciones de la Tax API</Anchor> para crear las reglas de tasas de impuestos. **Nota**: La API permite incluir un archivo JSON en el cuerpo de la solicitud de publicación. <Anchor target="_blank" href="https://docs.google.com/document/d/e/2PACX-1vSl3DwlK2Gt2aa5gmDzD3-K3CtnIM85oMNrqx3PCTamwCERWYU48GugNpD31BFjA2PJjZnqaXIVe2Hx/pub">Este archivo JSON</Anchor> incluye todos los países compatibles y sus impuestos predeterminados. El desarrollador puede editarlo o utilizarlo tal y como está en la API.

<div id="tax-rate-api-parameters" />

### Parámetros y valores a utilizar en la API

| Parámetro | Obligatorio | Observaciones |
| --- | --- | --- |
| `tax_name` | Sí | <ul><li>Nombre que aparece en la factura del cliente que describe el tipo específico de impuesto.</li><li>Ejemplo: Ventas, VAT, GST</li></ul> |
| `tax_rate` | Sí | <ul><li>El valor debe ser superior a 0. Número de hasta 4 decimales que representa el porcentaje de impuesto a recaudar.</li><li>Ejemplo: 7.25</li></ul> |
| `tax_exclusive` | No | <ul><li>Parámetro booleano, verdadero o falso.</li><li>Falso significa que el impuesto está incluido en los ingresos totales.</li><li>El impuesto sobre los medios reales se añade a los ingresos totales declarados. Por ejemplo, en EE.UU. o Canadá, donde el precio no incluye el impuesto sobre ventas.</li><li>El valor predeterminado es falso.</li></ul> |
| `País` | No | <ul><li><Anchor target="_blank" href="https://www.nationsonline.org/oneworld/country_code_list.htm">Código ISO de dos letras del país</Anchor> al que se aplica el impuesto.</li><li>Ejemplo: CA</li><li>Nota: Para el Reino Unido, el código aplicado es UK, no GB.</li></ul> |
| `subdivision` | No | <ul><li>Para algunos países, puede existir un estado/subdivisión adicional.</li><li>Se maneja de acuerdo con los <Anchor target="_blank" href="https://service.unece.org/trade/locode/2022-2%20SubdivisionCodes.htm">códigos de subdivisión ISO 3166-2.</Anchor></li><li>Debe incluir el código de país y el código de subdivisión.</li><li>Ejemplo: US-CA</li></ul> |
| `postal_code` | No | <ul><li>Cadena de letras y/o números</li><li>Ejemplo: L4J8E3</li></ul> |
| `deduction_order` | No | <ul><li>Valor enumerado: **0**, **1** o **2**:<ul><li>0 significa que la comisión de la tienda se deduce primero de los ingresos brutos y los impuestos se deducen del monto restante.</li><li>1 significa que la comisión de la tienda se deduce primero de los ingresos brutos y los impuestos se deducen del monto restante.</li><li>2 significa que tanto el impuesto como la comisión de la tienda se deducen de los ingresos totales.</li></ul></li></ul> |

<div id="set-up-store-commission-rates" />

## Configurar tasas de comisión de la tienda

De forma predeterminada, AppsFlyer aplica la lógica estándar de comisiones de la tienda al calcular los ingresos netos. Los valores predeterminados de App Store son específicos de cada región (consulta <Anchor target="_blank" href="/marketers/es/docs/about-roi360-store-revenue#true-revenue">About ROI360 store revenue</Anchor> para ver las tasas actuales por storefront). Si tu aplicación opera con comisiones de tienda reducidas o no estándar, usa la API de Net Revenue para sustituir la tasa de comisión de la tienda a nivel de aplicación.

Algunos ejemplos:

* Tu aplicación reúne los requisitos para beneficiarse de tarifas reducidas de la tienda, como:
  * Programa para pequeñas empresas de la tienda de aplicaciones de Apple (15% de comisión; 12% en China continental (CN))
  * Nivel de tarifa de servicio del 15% de Google Play (primer 1 M USD de ingresos anuales)
* La comisión de la tienda cambia con el tiempo y, como AppsFlyer no tiene visibilidad del estado de la comisión de tu tienda, debes actualizar manualmente la tarifa aplicada mediante la API de ingresos netos, por ejemplo:
  * Aplicar una comisión reducida cuando tu aplicación pase a cumplir los requisitos para una tarifa más baja de la tienda
  * Volver a la lógica predeterminada de comisión de la tienda cuando deje de aplicarse la tarifa reducida

<div id="update-store-commission-with-the-net-revenue-api" />

### Actualiza la comisión de la tienda con la API de ingresos netos

Puedes usar la API de ingresos netos para gestionar las configuraciones de comisión de la tienda de las siguientes formas:

* Revisa las configuraciones existentes enviando una solicitud GET para recuperar las tarifas de comisión de la tienda de las aplicaciones de la cuenta
* Aplica una comisión personalizada enviando una solicitud POST con la tarifa de comisión requerida
* Vuelve a la lógica predeterminada enviando una solicitud DELETE para la aplicación correspondiente

Antes de usar la API:

1. Completa los siguientes pasos en la configuración de ingresos de la tienda de ROI360:

   <div id="ios::f410adfc" />

   <Accordion title="apps de iOS,">

   * <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-store-revenue#paso-1-ios-configura-las-claves-de-app-store-connect">1. Configurar claves de conexión de la App Store</Anchor>
   * <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-store-revenue#paso-2-ios-configura-las-notificaciones-del-servidor-de-app-store">2. Configurar las notificaciones del servidor de la App Store</Anchor>

   </Accordion>

   <div id="android::659c7976" />

   <Accordion title="Android">

   * <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-store-revenue#paso-1-android-configurar-la-clave-de-cuenta-de-servicio-y-los-permisos">1. Configurar la clave de cuenta de servicio y los permisos</Anchor>
   * <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-store-revenue#paso-2-android-configura-las-notificaciones-del-servidor-de-google-play">2. Configurar las notificaciones del servidor de Google Play</Anchor>

   </Accordion>

2. Prepara la siguiente información:
   * Token de API V2 para usar como clave de autorización
   * Tarifa de comisión de la tienda que se aplicará (valores admitidos: 1%–30%)
   * ID de la aplicación (o aplicaciones) a las que se aplica la comisión personalizada
3. Ten en cuenta los siguientes detalles de configuración:
   * La comisión de la tienda se configura **por aplicación**
   * Los valores admitidos son **1%–30%**
   * La configuración se aplica **solo a los nuevos eventos entrantes**
   * Si no se establece ninguna comisión personalizada, AppsFlyer usa la **lógica predeterminada de comisión de la tienda**

Para ver las estructuras y los ejemplos completos de las solicitudes, consulta la [documentación de la API de ingresos netos](https://dev.appsflyer.com/hc/reference/overview-7).

<div data-zendesk-anchors="h_01KEFDF4KD0DCMP5DGE7ZJDBGX=nota update-tax-rate-rules=actualizar-reglas-de-tipos-impositivos h_01KEFDF4KDJ5PVS3AW46BS57NC=actualizar-reglas-de-tipos-impositivos h_01KEFDRXY0FWKKK0DK6PS340TC=ios h_01KEFDRXY0RTBH293JQXFWYAM2=android tax-rate-api-parameters=par%C3%A1metros-y-valores-a-utilizar-en-la-api h_01KEFDF4KD60SEVBQ8G228PEXD=par%C3%A1metros-y-valores-a-utilizar-en-la-api set-up-store-commission-rates=configurar-tasas-de-comisi%C3%B3n-de-la-tienda h_01KEFDF4KDP4PFKFQ0D9FN8P5D=configurar-tasas-de-comisi%C3%B3n-de-la-tienda update-store-commission-with-the-net-revenue-api=actualiza-la-comisi%C3%B3n-de-la-tienda-con-la-api-de-ingresos-netos h_01KEFDF4KDVTHTGKJ35CQ1GQ1E=actualiza-la-comisi%C3%B3n-de-la-tienda-con-la-api-de-ingresos-netos h_01KEFDWVDFBPP7NPSZV0PRGKPZ=ios::f410adfc h_01KEFDWVDFZPHJP6EG0CPNG5A0=android::659c7976" />
