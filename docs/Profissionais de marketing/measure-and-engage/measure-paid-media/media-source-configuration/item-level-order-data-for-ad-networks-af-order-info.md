---
title: Dados do pedido em nível de item para ad networks (af_order_info)
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
  edited_at: '2026-10-23T01:28:16Z'
  id: 50185623016721
  locale: pt
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/pt/articles/50185623016721
---
> **At a glance:** **Resumo:** Envie dados do pedido em nível de item para a AppsFlyer com o parâmetro `af_order_info`. Ele é compatível com dois formatos consistentes para compras de um ou vários itens. A AppsFlyer mapeia isso automaticamente para a estrutura exigida por cada ad network.

<div id="why-item-level-data-matters" />

## Por que os dados em nível de item são importantes

`af_order_info` é um parâmetro de evento que reporta os itens individuais de um pedido, seja ele de um item ou de vários. Ele substitui os campos antigos `af_content` e `af_content_list` por um único formato, mais completo, para a mesma finalidade. Ele é compatível com dois formatos de array consistentes para pedidos com um ou vários itens e funciona em seis networks (Google Ads, DV360, Meta, TikTok, Snapchat e Pinterest), em vez de exigir uma estrutura separada para cada uma.

Enviar esse nível de detalhamento é importante porque essas networks agora otimizam campanhas usando mais do que apenas o valor total de um pedido. Meta, Google, TikTok, Snapchat e Pinterest são compatíveis com algoritmos de otimização que funcionam no nível do produto, usando detalhes como ID do item, preço, quantidade, categoria e marca para melhorar a segmentação e o bidding. Quanto mais completo for o detalhamento dos itens que você enviar, mais essas networks poderão usar para ajustar essas campanhas com precisão.

<div id="parameter-structure" />

## Estrutura dos parâmetros

Cada item de um pedido pode ser descrito usando até 7 campos. A AppsFlyer é compatível com duas formas de estruturar esses campos em `af_order_info`, descritas abaixo.

Ele é enviado como parte do `event_value` (ou `custom_data`) do seu evento e funciona da mesma forma, quer o pedido tenha um item ou vários, para que você possa padronizá-lo em vez de manter vários formatos de dados de pedido.

Os sete campos são:

| Campo | A descrição | Compatível com |
| --- | --- | --- |
| `sku` | ID do item ou unidade de manutenção de estoque (SKU) | Google, DV360, Meta, Snapchat, Pinterest, TikTok |
| `revenue` | Preço do item | Google, DV360, Meta, Snapchat, Pinterest, TikTok |
| `qty` | Quantidade comprada | Google, DV360, Meta, Snapchat, Pinterest, TikTok |
| `content_name` | Nome do item ou do produto | Tiktok |
| `content_type` | Tipo de item. Os únicos valores compatíveis são `product` (quando o SKU é um SKU específico) e `product_group` (quando o SKU é um `item_group_id`) | Tiktok |
| `content_category` | Categoria do item | TikTok, Snapchat |
| `Marca` | Marca do item | TikTok, Snapchat |

> 📘 **Note**
>
> Você não precisa preencher todos os sete campos para cada item. Envie o que for relevante para o seu negócio e para as networks nas quais você executa campanhas. Os campos que você deixar de fora simplesmente não serão incluídos no postback para as networks que, de outra forma, os receberiam. Os campos mais importantes e comuns a serem enviados são sku, receita e qty.

A AppsFlyer oferece suporte a duas formas de estruturar `af_order_info`, ambas aninhadas em `event_value`:

* **Um campo para todos os itens** (recomendado): cada campo, como `sku`, `revenue` e `qty`, é enviado uma vez, como um array que abrange todos os itens do pedido. Isso mantém o payload menor.
* **Um objeto por item**: cada item do pedido é enviado como seu próprio objeto, com todos os campos relevantes aninhados dentro dele.

O exemplo a seguir mostra o formato recomendado, com um campo para todos os itens:

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

O exemplo a seguir mostra o formato alternativo, com um objeto por item:

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

<div id="per-network-mapping" />

## Mapeamento por network

A AppsFlyer lê o array `af_order_info` e o reestrutura automaticamente no formato que a API de cada network espera. A compatibilidade dos campos varia de acordo com a network, portanto nem todos os campos que você envia chegam a todas as networks. A tabela a seguir mostra os campos que cada network atualmente oferece suporte:

| Rede | Campos compatíveis |
| --- | --- |
| Google Ads / DV360 | `sku`, `qty`, `revenue` |
| Meta (Facebook) | `sku`, `qty`, `revenue` |
| Tiktok | `sku`, `qty`, `revenue`, `content_name`, `content_type`, `content_category`, `brand` (todos os sete campos) |
| Snapchat | Mobile: `sku`, `receita`, `marca`, `content_category`; a quantidade é enviada como uma contagem total de itens. Web: `sku`, `receita`, `qty`; a quantidade é enviada por item e como uma contagem total de itens. |
| Pinterest | `sku`, `revenue`, `qty` |

<Accordion title="Google Ads e DV360">

**Mobile**

A AppsFlyer mapeia os campos para o array `items` em `app_event_data`:

```json
"app_event_data": {
  "items": [
    {"item_id": "SKU-001", "quantity": "1", "price": "50.0"},
    {"item_id": "SKU-002", "quantity": "1", "price": "75.0"},
    {"item_id": "SKU-003", "quantity": "2", "price": "25.0"}
  ]
}
```

**Google Ads web (OCI)**

A AppsFlyer mapeia `sku` para `productId`, `qty` para `quantity` e `revenue` para `unitPrice` em `conversions[].cartData.items[]`.

Trecho de um objeto de conversão:

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

**Mobile**

A AppsFlyer mapeia os campos para `fb_contents`:

```json
"fb_contents": [
  {"id": "SKU-001", "quantity": 1, "item_price": 50.00},
  {"id": "SKU-002", "quantity": 1, "item_price": 75.00},
  {"id": "SKU-003", "quantity": 2, "item_price": 25.00}
]
```

**Web**

A AppsFlyer mapeia os campos em `data[].custom_data.contents`.

Trecho de um objeto de evento:

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

<Accordion title="Tiktok">

**Mobile**

A AppsFlyer mapeia os campos para `properties.contents`. O TikTok é a única network, entre as cinco, que aceita todos os sete campos:

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

A AppsFlyer mapeia os detalhes do item em `data[].properties.contents`, com `content_type` enviado uma vez em `properties`, ao lado de `contents`. Inclua a receita total e a moeda do evento. A AppsFlyer encaminha os detalhes do item quando a receita do evento está presente.

Trecho de um objeto de evento:

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

**Mobile**

A AppsFlyer mapeia os campos para parâmetros de consulta de URL. O Snapchat não recebe a quantidade por item. Em vez disso, `number_items` reflete a quantidade total de todos os itens no pedido:

```http
&item_ids=SKU-001,SKU-002,SKU-003&number_items=5&price=50.00,75.00,25.00&brands=Logitech,Sony,Anker&category=accessories,audio,cables
```

**Web**

A AppsFlyer mapeia os detalhes do item em `data[].custom_data.contents`, incluindo a quantidade por item. `num_items` contém a quantidade total de itens do pedido.

Trecho de um objeto de evento:

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

**Mobile e web**

A AppsFlyer mapeia os campos para `contents`:

```json
"contents": [
  {"id": "SKU-001", "item_price": "50.00", "quantity": 1},
  {"id": "SKU-002", "item_price": "75.00", "quantity": 1},
  {"id": "SKU-003", "item_price": "25.00", "quantity": 2}
]
```

Para postbacks web, `contents` fica aninhado em `data[].custom_data`.

</Accordion>

<div id="backward-compatibility" />

## Compatibilidade com versões anteriores

Os formatos existentes também continuam funcionando, incluindo os campos baseados em array `af_content_id`, `af_quantity` e `af_price`, além dos campos `af_content` e `af_content_list`. Você não precisa migrar implementações existentes. `af_order_info` estará disponível daqui para frente em um formato único e mais completo. Isso é particularmente útil se você quiser enviar detalhes mais avançados do item, como nome, categoria e marca, do que os formatos antigos oferecem suporte.

> ❗️ **Warning**
>
> Importante!
>
> Como af\_order\_info é compatível apenas com as networks listadas neste artigo, continue enviando essas informações nos campos existentes, como af\_content\_id, af\_content\_list, af\_content\_type e af\_quantity, se você executar campanhas com outras networks que precisem delas.
>
> Para a integração mobile da Meta, se você já enviava essas informações no formato esperado pela Meta (em af\_content, que a AppsFlyer mapeava para fb\_contents), agora pode remover esse campo do payload. A nova solução também é compatível com a Meta em fb\_contents por padrão.

<div id="traits-and-limitations" />

## Especificações e limitações

| Caraterística | Visão geral |
| --- | --- |
| Redes Suportadas | A AppsFlyer é compatível com `af_order_info` apenas para as networks listadas neste artigo. Outras networks ainda podem ter suporte ao formato mais antigo. |
| Plataformas compatíveis | Compatível com apps mobile e sites. O suporte a sites está disponível para Google Ads, Meta, TikTok, Snapchat e Pinterest. A compatibilidade com DV360 se aplica a apps mobile. |
| TikTok web | Os detalhes do item são encaminhados quando a receita do evento está presente. Envie a receita total e a moeda do evento, além dos detalhes do item. |
| Comprimento do valor do evento | O comprimento total do campo `event_value`, incluindo `af_order_info`, não pode exceder 3.000 caracteres. |

<div data-zendesk-anchors="h_01_why-item-level-data-matters=por-que-os-dados-em-n%C3%ADvel-de-item-s%C3%A3o-importantes why-item-level-data-matters=por-que-os-dados-em-n%C3%ADvel-de-item-s%C3%A3o-importantes h_01_parameter-structure=estrutura-dos-par%C3%A2metros parameter-structure=estrutura-dos-par%C3%A2metros h_01_per-network-mapping=mapeamento-por-network per-network-mapping=mapeamento-por-network h_01_backward-compatibility=compatibilidade-com-vers%C3%B5es-anteriores backward-compatibility=compatibilidade-com-vers%C3%B5es-anteriores h_01_traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es" />
