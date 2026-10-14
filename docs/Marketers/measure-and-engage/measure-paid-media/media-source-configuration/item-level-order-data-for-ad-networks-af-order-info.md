---
title: "Item-level order data for ad networks (af_order_info)"
excerpt: "Send item-level order data to AppsFlyer with the af_order_info parameter. It supports two consistent formats for single or multi-item purchases. AppsFlyer automatically maps it to the structure each ad network requires."
x-zendesk:
  id: 50185623016721
  url: https://support.appsflyer.com/hc/en-us/articles/50185623016721-Item-level-order-data-for-ad-networks-af-order-info
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Media source configuration
  section_id: 6551067072785
  position: 4
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [Marketers, Mobile Attribution]
  labels: []
  promoted: false
  comments_disabled: true
  created_at: '2026-08-25T12:25:01Z'
  edited_at: '2026-09-22T14:00:28Z'
---
## Why item-level data matters

`af_order_info` is an event parameter that reports the individual items in an order, whether the order has one item or several. It replaces the older `af_content` and `af_content_list` fields with a single, more complete format for the same purpose. It supports two consistent array formats for both single-item and multi-item orders and works across six networks (Google Ads, DV360, Meta, TikTok, Snapchat, and Pinterest) rather than requiring a separate structure for each.

Sending this level of detail matters because these networks now optimize campaigns using more than just an order's total value. Meta, Google, TikTok, Snapchat, and Pinterest all support optimization algorithms that work at the product level, using details such as item ID, price, quantity, category, and brand to improve targeting and bidding. The more complete the item breakdown you send, the more these networks can use to fine-tune those campaigns.

## Parameter structure

Each item in an order can be described using up to 7 fields. AppsFlyer supports two ways to structure these fields under `af_order_info`, described below.

It is sent as part of your event's `event_value` (or `custom_data`), and it works the same way whether the order has one item or several, so you can standardize on it rather than maintaining multiple order data formats.

The seven fields are:

| Field | Description | Supported by |
| --- | --- | --- |
| `sku` | Item ID or stock keeping unit (SKU) | Google, DV360, Meta, Snapchat, Pinterest, TikTok |
| `revenue` | Item price | Google, DV360, Meta, Snapchat, Pinterest, TikTok |
| `qty` | Quantity purchased | Google, DV360, Meta, Snapchat, Pinterest, TikTok |
| `content_name` | Item or product name | TikTok |
| `content_type` | Item type. The only supported values are `product` (when the SKU is a specific SKU) and `product_group` (when the SKU is an `item_group_id`) | TikTok |
| `content_category` | Item category | TikTok, Snapchat |
| `brand` | Item brand | TikTok, Snapchat |

You do not need to populate all seven fields for every item. Send what is relevant to your business and to the networks you run campaigns on. Any fields you leave out are simply left out of the postback to networks that would otherwise receive them. The most important and common fields to send are sku, revenue, and qty.

AppsFlyer supports two ways to structure `af_order_info`, both nested under `event_value`:

* **One field for all items** (recommended): each field, such as `sku`, `revenue`, and `qty`, is sent once, as an array that covers every item in the order. This keeps the payload shorter.
* **One object per item**: each item in the order is sent as its own object, with all relevant fields nested inside it.

The following example shows the recommended format, with one field for all items:

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

The following example shows the alternative format, with one object per item:

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

## Per-network mapping

AppsFlyer reads the `af_order_info` array and automatically restructures it into the format each network's API expects. Field support varies by network, so not every field you send reaches every network. The following table shows the fields each network currently supports:

| Network | Supported fields |
| --- | --- |
| Google Ads / DV360 | `sku`, `qty`, `revenue` |
| Meta (Facebook) | `sku`, `qty`, `revenue` |
| TikTok | `sku`, `qty`, `revenue`, `content_name`, `content_type`, `content_category`, `brand` (all seven fields) |
| Snapchat | `sku`, `revenue`, `brand`, `content_category`. AppsFlyer sends quantity only as a total item count, not per item |
| Pinterest | `sku`, `revenue`, `qty` |

<Accordion title="Google Ads and DV360">

AppsFlyer maps the fields into the `items` array under `app_event_data`:

```
"app_event_data": {
  "items": [
    {"item_id": "SKU-001", "quantity": "1", "price": "50.0"},
    {"item_id": "SKU-002", "quantity": "1", "price": "75.0"},
    {"item_id": "SKU-003", "quantity": "2", "price": "25.0"}
  ]
}
```

</Accordion>

<Accordion title="Meta (Facebook)">

AppsFlyer maps the fields into `fb_contents`:

```
"fb_contents": [
  {"id": "SKU-001", "quantity": 1, "item_price": 50.00},
  {"id": "SKU-002", "quantity": 1, "item_price": 75.00},
  {"id": "SKU-003", "quantity": 2, "item_price": 25.00}
]
```

</Accordion>

<Accordion title="TikTok">

AppsFlyer maps the fields into `properties.contents`. TikTok is the only network of the five that accepts all seven fields:

```
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

</Accordion>

<Accordion title="Snapchat">

AppsFlyer maps the fields into URL query parameters. Snapchat does not receive quantity per item. Instead, `number_items` reflects the total quantity across all items in the order:

```
&item_ids=SKU-001,SKU-002,SKU-003&number_items=5&price=50.00,75.00,25.00&brands=Logitech,Sony,Anker&category=accessories,audio,cables
```

</Accordion>

<Accordion title="Pinterest">

AppsFlyer maps the fields into `contents`:

```
"contents": [
  {"id": "SKU-001", "item_price": "50.00", "quantity": 1},
  {"id": "SKU-002", "item_price": "75.00", "quantity": 1},
  {"id": "SKU-003", "item_price": "25.00", "quantity": 2}
]
```

</Accordion>

## Backward compatibility

Existing formats also continue to work, including the array-based `af_content_id`, `af_quantity`, and `af_price` fields, and the `af_content` and `af_content_list` fields. You do not need to migrate existing implementations. `af_order_info` will be available in a single, more complete format going forward. It is particularly useful if you want to pass richer item details, such as name, category, and brand, than the older formats support.

Important!

Because af\_order\_info is supported only for the networks listed in this article, continue sending this information under the existing fields, such as af\_content\_id, af\_content\_list, af\_content\_type, and af\_quantity, if you run campaigns with other networks that need it.

If you previously sent this information in the format Meta expects (under af\_content, which AppsFlyer mapped to fb\_contents), you can now remove that field from the payload. The new solution also supports Meta under fb\_contents out of the box.

## Traits and limitations

| Trait | Description |
| --- | --- |
| Supported networks | AppsFlyer supports `af_order_info` only for the networks listed in this article. Other networks might still support the older format. |
| Supported platforms | This solution currently supports only in-app purchases for mobile apps. AppsFlyer plans to add support for other platforms, such as websites, in a later phase. |
| Event value length | The total length of the `event_value` field, including `af_order_info`, cannot exceed 3,000 characters. |

<div data-zendesk-anchors="h_01_why-item-level-data-matters=why-item-level-data-matters h_01_parameter-structure=parameter-structure h_01_per-network-mapping=per-network-mapping h_01_backward-compatibility=backward-compatibility h_01_traits-and-limitations=traits-and-limitations" />
