---
title: Datos de pedidos a nivel de artículo para ad network (af_order_info)
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Mobile Attribution
  created_at: '2026-08-25T12:25:01Z'
  edited_at: '2026-10-23T01:28:15Z'
  id: 50185623016721
  locale: es
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/es/articles/50185623016721
---
> **At a glance:** **Resumen:** Envía datos de pedidos a nivel de artículo a AppsFlyer con el parámetro `af_order_info`. Es compatible con dos formatos coherentes para compras de uno o varios artículos. AppsFlyer lo asigna automáticamente a la estructura que requiere cada ad network.

## Por qué son importantes los datos a nivel de artículo

`af_order_info` es un parámetro de evento que informa sobre los artículos individuales de un pedido, tanto si el pedido tiene un artículo como varios. Sustituye los campos antiguos `af_content` y `af_content_list` por un único formato más completo para el mismo fin. Admite dos formatos de array coherentes tanto para pedidos de un solo artículo como de varios artículos y funciona en seis ad network (Google Ads, DV360, Meta, TikTok, Snapchat y Pinterest), en lugar de requerir una estructura independiente para cada una.

Enviar este nivel de detalle es importante porque estas redes ahora optimizan las campañas usando algo más que el valor total de un pedido. Meta, Google, TikTok, Snapchat y Pinterest admiten algoritmos de optimización que funcionan a nivel de producto y usan detalles como el ID del artículo, el precio, la cantidad, la categoría y la marca para mejorar el targeting y las pujas. Cuanto más completo sea el desglose de artículos que envías, más podrán usar estas redes para afinar esas campañas.

## Estructura de parámetros

Cada artículo de un pedido se puede describir con hasta 7 campos. AppsFlyer admite dos formas de estructurar estos campos en `af_order_info`, que se describen a continuación.

Se envía como parte del `event_value` de tu evento (o de `custom_data`) y funciona igual tanto si el pedido tiene un artículo como varios, así que puedes estandarizarlo en lugar de mantener varios formatos de datos de pedidos.

Estos siete campos son:

| Campo | Description | Compatible con |
| --- | --- | --- |
| `sku` | ID del artículo o unidad de mantenimiento de existencias (SKU) | Google, DV360, Meta, Snapchat, Pinterest, TikTok |
| `revenue` | Precio del artículo | Google, DV360, Meta, Snapchat, Pinterest, TikTok |
| `qty` | Cantidad comprada | Google, DV360, Meta, Snapchat, Pinterest, TikTok |
| `content_name` | Nombre del artículo o producto | TikTok |
| `content_type` | Tipo de artículo. Los únicos valores compatibles son `product` (cuando el SKU es un SKU específico) y `product_group` (cuando el SKU es un `item_group_id`) | TikTok |
| `content_category` | Categoría del artículo | TikTok, Snapchat |
| `brand` | Marca del artículo | TikTok, Snapchat |

> 📘 **Note**
>
> No es necesario completar los siete campos para cada artículo. Envía lo que sea relevante para tu negocio y para las redes en las que ejecutas campañas. Los campos que omitas simplemente no se incluirán en el postback a las redes que, de otro modo, los recibirían. Los campos más importantes y habituales que debes enviar son sku, ingresos y qty.

AppsFlyer admite dos formas de estructurar `af_order_info`, ambas anidadas dentro de `event_value`:

* **Un campo para todos los artículos** (recomendado): cada campo, como `sku`, `revenue` y `qty`, se envía una sola vez, como un array que abarca todos los artículos del pedido. Así, el payload es más corto.
* **Un objeto por artículo**: cada artículo del pedido se envía como su propio objeto, con todos los campos relevantes anidados dentro.

El siguiente ejemplo muestra el formato recomendado, con un campo para todos los artículos:

```json
{
  "af_order_info": {
    "sku": ["SKU-001", "SKU-002", "SKU-003"],
    "revenue": [50.00, 75.00, 25.00],
    "qty": [1, 1, 2],
    "content_name": ["Wireless Mouse", "Bluetooth Headphones", "USB-C Cable"],
    "content_type": ["product", "product", "product"],
    "content_category": ["accessories", "audio", "cables"],
    "brand": ["Logitech", "Sony", "Anker"]
  }
}
```

El siguiente ejemplo muestra el formato alternativo, con un objeto por elemento:

```json
{
  "af_order_info": [
    {
      "sku": "SKU-001",
      "revenue": 50.00,
      "qty": 1,
      "content_name": "Wireless Mouse",
      "content_type": "product",
      "content_category": "accessories",
      "brand": "Logitech"
    },
    {
      "sku": "SKU-002",
      "revenue": 75.00,
      "qty": 1,
      "content_name": "Bluetooth Headphones",
      "content_type": "product",
      "content_category": "audio",
      "brand": "Sony"
    },
    {
      "sku": "SKU-003",
      "revenue": 25.00,
      "qty": 2,
      "content_name": "USB-C Cable",
      "content_type": "product",
      "content_category": "cables",
      "brand": "Anker"
    }
  ]
}
```

## Asignación por red

AppsFlyer lee el array `af_order_info` y lo reestructura automáticamente en el formato que espera la API de cada red. La compatibilidad de los campos varía según la red, por lo que no todos los campos que envías llegan a todas las redes. La siguiente tabla muestra los campos que admite actualmente cada red:

| Red | Campos admitidos |
| --- | --- |
| Google Ads / DV360 | `sku`, `qty`, `ingresos` |
| Meta (Facebook) | `sku`, `qty`, `ingresos` |
| TikTok | `sku`, `qty`, `ingresos`, `content_name`, `content_type`, `content_category`, `marca` (los siete campos) |
| Snapchat | Móvil: `sku`, `ingresos`, `marca`, `content_category`; la cantidad se envía como recuento total de artículos. Web: `sku`, `ingresos`, `qty`; la cantidad se envía por artículo y como recuento total de artículos. |
| Pinterest | `sku`, `ingresos`, `qty` |

<Accordion title="Google Ads y DV360">

**Móvil**

AppsFlyer asigna los campos al array `items` dentro de `app_event_data`:

```json
"app_event_data": {
  "items": [
    {"item_id": "SKU-001", "quantity": "1", "price": "50.0"},
    {"item_id": "SKU-002", "quantity": "1", "price": "75.0"},
    {"item_id": "SKU-003", "quantity": "2", "price": "25.0"}
  ]
}
```

**Google Ads Web (OCI)**

AppsFlyer asigna `sku` a `productId`, `qty` a `quantity` y `revenue` a `unitPrice` en `conversions[].cartData.items[]`.

Fragmento de un objeto de conversión:

```json
{
  "cartData": {
    "items": [
      {"productId": "SKU-001", "quantity": 1, "unitPrice": 50.00},
      {"productId": "SKU-002", "quantity": 1, "unitPrice": 75.00},
      {"productId": "SKU-003", "quantity": 2, "unitPrice": 25.00}
    ]
  }
}
```

</Accordion>

<Accordion title="Meta (Facebook)">

**Móvil**

AppsFlyer asigna los campos a `fb_contents`:

```json
"fb_contents": [
  {"id": "SKU-001", "quantity": 1, "item_price": 50.00},
  {"id": "SKU-002", "quantity": 1, "item_price": 75.00},
  {"id": "SKU-003", "quantity": 2, "item_price": 25.00}
]
```

**Web**

AppsFlyer asigna los campos a `data[].custom_data.contents`.

Fragmento de un objeto de evento:

```json
{
  "custom_data": {
    "contents": [
      {"id": "SKU-001", "quantity": 1, "item_price": 50.00},
      {"id": "SKU-002", "quantity": 1, "item_price": 75.00},
      {"id": "SKU-003", "quantity": 2, "item_price": 25.00}
    ]
  }
}
```

</Accordion>

<Accordion title="TikTok">

**Móvil**

AppsFlyer asigna los campos a `properties.contents`. TikTok es la única red de las cinco que acepta los siete campos:

```json
"properties": {
  "contents": [
    {
      "content_type": "product",
      "content_category": "accessories",
      "content_name": "Wireless Mouse",
      "quantity": 1,
      "brand": "Logitech",
      "content_id": "SKU-001",
      "price": 50.00
    }
  ],
  "currency": "USD",
  "value": 175.00
}
```

**Web**

AppsFlyer asigna los detalles del artículo a `data[].properties.contents`, con `content_type` enviado una sola vez en `properties`, junto con `contents`. Incluye los ingresos totales y la divisa del evento. AppsFlyer reenvía los detalles del artículo cuando hay ingresos del evento.

Fragmento de un objeto de evento:

```json
{
  "properties": {
    "content_type": "product",
    "currency": "USD",
    "value": 175.00,
    "contents": [
      {
        "content_id": "SKU-001",
        "price": 50.00,
        "quantity": 1,
        "content_name": "Wireless Mouse",
        "content_category": "accessories",
        "brand": "Logitech"
      },
      {
        "content_id": "SKU-002",
        "price": 75.00,
        "quantity": 1,
        "content_name": "Bluetooth Headphones",
        "content_category": "audio",
        "brand": "Sony"
      },
      {
        "content_id": "SKU-003",
        "price": 25.00,
        "quantity": 2,
        "content_name": "USB-C Cable",
        "content_category": "cables",
        "brand": "Anker"
      }
    ]
  }
}
```

</Accordion>

<Accordion title="Snapchat">

**Móvil**

AppsFlyer asigna los campos a parámetros de consulta de URL. Snapchat no recibe la cantidad por artículo. En su lugar, `number_items` refleja la cantidad total de todos los artículos del pedido:

```http
&item_ids=SKU-001,SKU-002,SKU-003&number_items=5&price=50.00,75.00,25.00&brands=Logitech,Sony,Anker&category=accessories,audio,cables
```

**Web**

AppsFlyer asigna los detalles del artículo a `data[].custom_data.contents`, incluida la cantidad por artículo. `num_items` contiene la cantidad total del pedido.

Fragmento de un objeto de evento:

```json
{
  "custom_data": {
    "contents": [
      {"id": "SKU-001", "quantity": 1, "item_price": 50.00},
      {"id": "SKU-002", "quantity": 1, "item_price": 75.00},
      {"id": "SKU-003", "quantity": 2, "item_price": 25.00}
    ],
    "num_items": 4
  }
}
```

</Accordion>

<Accordion title="Pinterest">

**Móvil y web**

AppsFlyer asigna los campos a `contents`:

```json
"contents": [
  {"id": "SKU-001", "item_price": "50.00", "quantity": 1},
  {"id": "SKU-002", "item_price": "75.00", "quantity": 1},
  {"id": "SKU-003", "item_price": "25.00", "quantity": 2}
]
```

En los postbacks web, `contents` está anidado en `data[].custom_data`.

</Accordion>

## Compatibilidad con versiones anteriores

Los formatos existentes también siguen funcionando, incluidos los campos `af_content_id`, `af_quantity` y `af_price` basados en matrices, así como los campos `af_content` y `af_content_list`. No necesitas migrar las implementaciones existentes. A partir de ahora, `af_order_info` estará disponible en un único formato más completo. Resulta especialmente útil si quieres pasar detalles de artículos más enriquecidos, como el nombre, la categoría y la marca, que los formatos anteriores no soportan.

> ❗️ **Warning**
>
> Importante:
>
> Como af\_order\_info solo es compatible con las redes que se indican en este artículo, sigue enviando esta información en los campos existentes, como af\_content\_id, af\_content\_list, af\_content\_type y af\_quantity, si ejecutas campañas con otras redes que la necesiten.
>
> Para la integración móvil de Meta, si anteriormente enviaste esta información en el formato que Meta espera (en af\_content, que AppsFlyer asignó a fb\_contents), ahora puedes eliminar ese campo del payload. La nueva solución también soporta Meta en fb\_contents de forma nativa.

## Características y limitaciones

| Rasgo | Descripción |
| --- | --- |
| Redes compatibles | AppsFlyer solo es compatible con `af_order_info` para las redes que se indican en este artículo. Es posible que otras redes sigan siendo compatibles con el formato anterior. |
| Plataformas admitidas | Compatible con aplicaciones móviles y sitios web. El soporte para sitios web está disponible para Google Ads, Meta, TikTok, Snapchat y Pinterest. El soporte de DV360 se aplica a las aplicaciones móviles. |
| TikTok web | Los detalles del artículo se reenvían cuando hay ingresos del evento. Envía los ingresos totales del evento y su moneda, además de los detalles del artículo. |
| Longitud del valor del evento | La longitud total del campo `event_value`, incluido `af_order_info`, no puede superar los 3.000 caracteres. |

<div data-zendesk-anchors="h_01_why-item-level-data-matters=por-qu%C3%A9-son-importantes-los-datos-a-nivel-de-art%C3%ADculo why-item-level-data-matters=por-qu%C3%A9-son-importantes-los-datos-a-nivel-de-art%C3%ADculo h_01_parameter-structure=estructura-de-par%C3%A1metros parameter-structure=estructura-de-par%C3%A1metros h_01_per-network-mapping=asignaci%C3%B3n-por-red per-network-mapping=asignaci%C3%B3n-por-red h_01_backward-compatibility=compatibilidad-con-versiones-anteriores backward-compatibility=compatibilidad-con-versiones-anteriores h_01_traits-and-limitations=caracter%C3%ADsticas-y-limitaciones traits-and-limitations=caracter%C3%ADsticas-y-limitaciones" />
