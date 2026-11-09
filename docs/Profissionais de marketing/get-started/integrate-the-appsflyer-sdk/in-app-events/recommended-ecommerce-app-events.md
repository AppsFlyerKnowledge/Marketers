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
  edited_at: '2026-08-18T00:14:00Z'
  id: 360019347957
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/360019347957
---
> **Resumo:** mensure a qualidade dos seus usuários durante toda a jornada do usuário, registrando eventos in-app sugeridos para seu aplicativo de eCommerce.

<div id="-ecommerce" />

## <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="67px" /> Comércio eletrônico

Aplicativos de eCommerce permitem que os compradores pesquisem e comprem mercadorias online. Os eventos típicos que sugerimos que você registre são pesquisas, compras, adições ao carrinho e adições à lista de desejos.

O registro desses eventos pode ajudar a determinar:

* Categorias mais populares
* O que os consumidores estão pesquisando
* Quantos consumidores concluem um checkout
* Quantos consumidores são recorrentes e quantos compram apenas uma vez

<div id="important" />

> 🚧 **Importante!**
>
> * Certifique-se de ler <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#configurando-eventos-in-app">as instruções</Anchor> para os profissionais de marketing sobre a implementação de eventos in-app.
> * Para agilizar o processo de implementação, use nosso <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=ecommerce">gerador de eventos in-app</Anchor>. Essa ferramenta inclui todos os eventos in-app típicos descritos neste artigo e permite que você modifique os eventos de acordo com as necessidades da sua empresa. Depois de concluído, compartilhe o arquivo com o seu desenvolvedor.
> * Para cada evento recomendado incluído neste artigo, há <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=ecommerce&view=code">exemplos de código</Anchor> para desenvolvedores do iOS, Android e Unity.
> * Instruções detalhadas para seu desenvolvedor podem ser encontradas no <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyer developer hub</Anchor>.
>
> Para mais informações sobre como registrar eventos in-app, consulte o <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">guia de eventos avançados dentro do aplicativo</Anchor>.

<Image align="center" alt="Flowchart_for_recommended_events e-Commerce_app_user_journey" src="https://files.readme.io/81af149c4fbe9185af3dad4057147dbf9882eb30d30b0724f2ffad2714517084-360020063077.png" />

<div id="recommended-structures-for-predefined-events" />

## Estruturas recomendadas para eventos predefinidos

A seção a seguir oferece uma lista de estruturas de eventos que são típicas da vertical de eCommerce. Cada estrutura inclui um nome de evento predefinido e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Objetivo**

Saiba quantos usuários instalaram o aplicativo e concluíram o processo de inscrição e quais métodos de inscrição seus usuários preferem.

**Trigger**

Quando o usuário conclui o processo de inscrição

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_registration\_method | Tipo de método de cadastro | E-mail, Meta ads |

</Accordion>

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Objetivo**

Entender a retenção dos usuários cadastrados

**Trigger**

Quando o usuário faz login com sucesso

**Parâmetros do evento**

Pode ser enviado sem nenhum parâmetro adicional

</Accordion>

<div id="search-af_search" />

<Accordion title="Pesquisa (af_search)">

**Objetivo**

Saber o que os usuários estão procurando e quais resultados de pesquisa são os mais relevantes para impulsionar uma compra.

**Trigger**

Um dos seguintes:

* Quando o usuário clica no botão de pesquisa
* Quando o usuário chega à página de resultados de pesquisa

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_search\_string | Termo de pesquisa | Vestido vermelho, tênis de corrida |
| af\_content\_list | Lista de IDs de conteúdo | 001, 092 |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Visualização de conteúdo (af_content_view)">

**Objetivo**

Determinar a taxa de visualização de produtos específicos. Esse evento pode ajudar a:

* Conectar visualizações de produtos a vendas de produtos
* Entender quais categorias são mais populares de acordo com as visualizações de produtos
* Ver a correlação entre a moeda dos consumidores e os produtos que eles visualizam

**Trigger**

Quando o usuário visualiza uma página específica de detalhes do produto

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Preço do produto | 2000 |
| af\_content | Número internacional do artigo (EAN, na sigla em inglês) quando aplicável, ou outro identificador de produto ou conteúdo<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do Meta ads** | ABC123 |
| af\_content\_id | ID do produto<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do Meta ads** | 102 |
| af\_content\_type | Categoria do item<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do Meta ads**  <br />  <br />**Atenção:** Ao mapear `af_content_type` para o `fb_content_type` do Meta, os únicos valores compatíveis são `product` ou `product_group`. | Sapatos |
| af\_currency | A moeda na página de detalhes do produto | THB, USD |

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="Visualização de lista (af_list_view)">

**Objetivo**

Registrar quais listas (por exemplo, produtos recém-adicionados, produtos relacionados ou produtos recomendados) são as mais visualizadas pelos consumidores.

**Trigger**

Quando o usuário visualiza uma lista específica

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_content\_type | Categoria do item<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do Meta ads**  <br />  <br />**Atenção:** Ao mapear `af_content_type` para `fb_content_type` do Meta, os únicos valores compatíveis são `product` ou `product_group`. | Relacionados, recomendados, recém-chegados |
| af\_content\_list | Lista de IDs de conteúdo da categoria | 001, 092 |

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Adicionar à lista de desejos (af_add_to_wishlist)">

**Objetivo**

Registrar quais produtos e categorias os consumidores adicionam às suas listas de desejos. Ao saber quais produtos geralmente são adicionados às listas de desejo, é possível oferecer esses produtos em promoções ou descontos e incentivar os compradores a comprá-los. Você também pode fazer o retargeting de usuários de acordo com os produtos que eles adicionam à lista de desejos.

**Trigger**

Quando o usuário adiciona itens à sua lista de desejos

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Preço do produto | 600 |
| af\_content\_id | ID do produto | 300 |
| af\_content\_type | Categoria do item<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do Meta ads**  <br />  <br />**Atenção:** Ao mapear `af_content_type` para `fb_content_type` do Meta, os únicos valores compatíveis são `product` ou `product_group`. | Sapatos, eletrônicos |
| af\_currency | Moeda exibida na página de detalhes do produto | GBP |

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="Adicionar ao carrinho (af_add_to_cart)">

**Objetivo**

Registrar quando um usuário adiciona produtos ao carrinho. Esse evento pode ajudar a determinar:

* Quantos produtos em média os compradores adicionam em uma compra
* Quanto tempo passa entre a adição de dois produtos diferentes
* Quantos compradores abandonam seu carrinho

**Trigger**

Quando o usuário adiciona um produto ao carrinho

**Parâmetros do evento**

| Nome do campo | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Preço do produto | 350, 1000 |
| af\_content | Número internacional do artigo (EAN, na sigla em inglês) quando aplicável, ou outro identificador de produto ou conteúdo<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do Meta ads** | ABC123 |
| af\_content\_id | ID do produto<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do Meta ads** | 001, 092 |
| af\_content\_type | Categoria do item<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do Meta ads**  <br />  <br />**Atenção:** Ao mapear `af_content_type` para `fb_content_type` do Meta, os únicos valores compatíveis são `product` ou `product_group`. | Camisa, sapatos |
| af\_currency | Moeda do produto | THB, USD |
| af\_quantity | Quantos itens de um mesmo produto foram adicionados ao carrinho | 2, 5 |

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="Checkout iniciado (af_initiated_checkout)">

**Objetivo**

Entender como os compradores se comportam quando se encaminham para o checkout. Esse evento pode ajudar a determinar:

* A média de preço quando os consumidores finalizam a compra e compará-la com a média de preço no evento de compra
* Se os usuários adicionam ou removem produtos após irem para o checkout

**Trigger**

Quando o usuário inicia o checkout, mas ainda não o concluiu

**Parâmetros do evento**

| Nome do campo | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Preço total no carrinho | 4000 |
| af\_content\_id | ID dos produtos no carrinho | 221, 124 |
| af\_content\_type | Categoria do item<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do Meta ads**  <br />  <br />**Atenção:** Ao mapear `af_content_type` para `fb_content_type` do Meta, os únicos valores compatíveis são `product` ou `product_group`. | Camisa, calças |
| af\_currency | Moeda no momento do checkout | THB |
| af\_quantity | Número total de itens no carrinho | 2, 5 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Objetivo**

Saber mais sobre as tendências de compra em seu aplicativo. Esse evento pode ajudar a:

* Descobrir o LTV de seus usuários e o ROI de suas campanhas em ad networks e agências de anúncios
* Determinar quais ofertas são mais populares entre seus usuários
* Fazer referência cruzada de campanhas com itens comprados para otimizar o direcionamento de campanhas

**Trigger**

Quando o usuário acessa a página de agradecimento após uma compra bem-sucedida

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | A receita estimada de uma compra | 1205.99 |
| af\_preço | Soma total da compra | 4000 |
| af\_content | Número internacional do artigo (EAN, na sigla em inglês) quando aplicável, ou outro identificador de produto ou conteúdo<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do** **Meta ads** | ABC123 |
| af\_content\_id | ID do item<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do Meta ads** | 121, 262 |
| af\_content\_type | Categoria do item<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do Meta ads**  <br />  <br />**Atenção:** Ao mapear `af_content_type` para `fb_content_type` do Meta, os únicos valores compatíveis são `product` ou `product_group`. | grupo de produtos |
| af\_currency | Código da moeda | AUD |
| af\_quantity | Quantidade de itens no carrinho | 2, 5 |
| af\_order\_id | ID do pedido que foi gerado após a compra | X123ABC |
| af\_receipt\_id | ID do pedido<br /><br />**Parâmetro necessário para validação de compra do CRITEO e Google Ad Words** | X123ABC |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estruturas recomendadas para eventos personalizados

A seção a seguir fornece uma lista de estruturas de eventos que incluem nomes de eventos personalizados e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="first-purchase-first_purchase" />

<Accordion title="Primeira compra (first_purchase)">

**Objetivo**

O mesmo que o evento [Compra](/docs/recommended-ecommerce-app-events#purchase-af_purchase). Além disso, esse evento pode ajudar a determinar:

* Quanto tempo um novo comprador demora para comprar
* Quais produtos clientes que compram pela primeira vez preferem comprar
* O preço médio e a receita de primeiras compras

**Trigger**

Quando o usuário conclui sua primeira compra

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Receita da compra | 1205.99 |
| af\_preço | Soma total da compra | 4000 |
| af\_content | Número internacional do artigo (EAN, na sigla em inglês) quando aplicável, ou outro identificador de produto ou conteúdo<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do Meta ads** | ABC123 |
| af\_content\_id | ID do item<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do Meta ads** | 121, 262 |
| af\_content\_type | Categoria do item<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do Meta ads**  <br />  <br />**Atenção:** Ao mapear `af_content_type` para `fb_content_type` do Meta, os únicos valores compatíveis são `product` ou `product_group`. | Sapatos, calças |
| af\_currency | Moeda | AUD |
| af\_quantity | Quantidade de itens no carrinho | 2, 5 |
| af\_order\_id | ID do pedido que foi gerado após a compra | X123ABC |
| af\_receipt\_id | ID do pedido<br /><br />**Parâmetro necessário para integração de retargeting do CRITEO e Google AdWords** | X123ABC |

</Accordion>

<div id="remove-from-cart-remove_from_cart" />

<Accordion title="Remover do carrinho (remove_from_cart)">

**Objetivo**

O registro deste evento pode ajudar você a:

* Determinar quais itens os consumidores removem do carrinho
* Determinar as categorias de produtos dos itens que os compradores removem do carrinho
* Comparar os dados do evento [Adicionar ao carrinho](/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart) para obter insights de produtos que não chegam ao checkout

**Trigger**

Quando o usuário remove um item do carrinho

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_content\_id | ID do item ou do produto | 521 |
| af\_content\_type | Categoria do item<br /><br />**Parâmetro obrigatório para anúncios dinâmicos do Meta ads**  <br />  <br />**Atenção:** Ao mapear `af_content_type` para `fb_content_type` do Meta, os únicos valores compatíveis são `product` ou `product_group`. | Sapatos |

</Accordion>

<div data-zendesk-anchors="ecommerce=-com%C3%A9rcio-eletr%C3%B4nico h_01HGTAWG2166CZYKJE9166G12J=-com%C3%A9rcio-eletr%C3%B4nico h_01HGTAWG21Z0C9SR2G54W68G8Q=importante recommended-structures-for-predefined-events=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAWG2115VB3A8J2WG3DJKK=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAWG21EQ0FE40WGFJRDJY5=complete-registration-af_complete_registration h_01HGTAWG22HFZ24V2BDCH3RFN8=login-af_login h_01HGTAWG22B5Z9AXENDATKR67T=search-af_search h_01HGTAWG22PSKS80ZQNAC0K24M=content-view-af_content_view h_01HGTAWG2219SVQ86PT1K3TVV9=list-view-af_list_view h_01HGTAWG22EQMVWXJCXC2KQDX8=add-to-wishlist-af_add_to_wishlist h_01HGTAWG23T81SPFJEA6BY5F2W=add-to-cart-af_add_to_cart h_01HGTAWG23FPKQ6RHJ9VYET63Y=initiated-checkout-af_initiated_checkout h_01HGTAWG2385E9Q0FXZXEW38YK=purchase-af_purchase recommended-structures-for-custom-events=estruturas-recomendadas-para-eventos-personalizados h_01HGTAWG235EXE17EJ5DWQYERM=estruturas-recomendadas-para-eventos-personalizados h_01HGTAWG23NTG0Q70B9A3685AD=first-purchase-first_purchase h_01HGTAWG239TQ51Z7FQW4FC1TZ=remove-from-cart-remove_from_cart" />
