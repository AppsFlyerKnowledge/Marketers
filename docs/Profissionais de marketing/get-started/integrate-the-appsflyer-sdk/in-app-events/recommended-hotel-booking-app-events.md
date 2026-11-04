---
title: Eventos de aplicativo de reserva de hotel recomendados
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
  created_at: '2021-04-29T14:49:54Z'
  edited_at: '2026-08-18T00:14:28Z'
  id: 360019843558
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/360019843558
---
> **Visão geral:** mensure a qualidade dos seus usuários durante toda a jornada de usuário, registrando esses eventos in-app sugeridos para seu aplicativo de reserva de hotel.

<div id="-hotel-booking" />

## <Image alt="InApp_Events_hotel.png" src="https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png" width="100px" /> Reserva de hotel

Aplicativos de reserva de hotel permitem que os viajantes reservem hotéis com facilidade e escolham as melhores ofertas. Os eventos típicos que sugerimos que você registre são pesquisa, compra, reserva de viagens e inclusão na lista de desejos.

Registrar eventos pode ajudar a determinar:

* Quais campanhas e fontes de mídia trazem usuários que realmente fazem reservas de férias
* Quais campanhas e fontes de mídia trazem os usuários que mais reservam e geram mais receita

Você pode atribuir preferências como pontuação do hotel, temporada, país e número de crianças para os usuários que vêm de certas fontes de mídias. Assim, você pode otimizar suas campanhas direcionando essas preferências de usuário.

<div id="important" />

> 🚧 **Importante!**
>
> * Certifique-se de ler as <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#configurando-eventos-in-app">instruções</Anchor> para os profissionais de marketing sobre a implementação de eventos in-app.
> * Para agilizar o processo de implementação, use nosso <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=hotel_booking">gerador de eventos in-app</Anchor>. Essa ferramenta inclui todos os eventos in-app típicos descritos neste artigo e permite que você modifique os eventos de acordo com as necessidades da sua empresa. Depois de concluído, compartilhe o arquivo com seu desenvolvedor.
> * Para cada evento recomendado incluído neste artigo, há <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=hotel_booking&view=code">exemplos de código</Anchor> para desenvolvedores iOS, Android e Unity.
> * Instruções detalhadas para o seu desenvolvedor podem ser encontradas no **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">developer hub (hub para desenvolvedores) da AppsFlyer</Anchor>.**
>
> Para mais informações sobre como gravar eventos in-app, consulte o <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">guia Eventos avançados dentro do aplicativo</Anchor>.

[![Fluxograma da jornada do utilizador da aplicação de reserva de hotel para eventos recomendados](https://files.readme.io/f425bc8865d731eb4934b6f32123156c7016ea1f75472e8878e76636aa593073-4402679204241.png)](https://files.readme.io/f425bc8865d731eb4934b6f32123156c7016ea1f75472e8878e76636aa593073-4402679204241.png)

<div id="recommended-structures-for-predefined-events" />

## Estruturas recomendadas para eventos predefinidos

A seção a seguir oferece uma lista de estruturas de eventos que são típicas da vertical de reserva de hotel. Cada estrutura inclui um nome de evento predefinido e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Propósito**

Saiba quantos usuários instalaram o aplicativo e concluíram o processo de cadastro, quais métodos de cadastro seus usuários preferem e quais fontes de mídia trazem usuários que realmente fazem o cadastro.

**Trigger**

Quando o usuário conclui o processo de inscrição

Parâmetros do evento

| Nome do campo | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_registration\_method | O tipo de método de cadastro | email, facebook |

</Accordion>

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Propósito**

Entenda a retençãoenção de seus usuários registrados

**Gatilho**

Quando o usuário faz login com sucesso

**Parâmetros do evento**

Pode ser enviado sem nenhum parâmetro adicional

</Accordion>

<div id="search-af_search" />

<Accordion title="Busca (af_search)">

**Propósito**

Saiba o que os usuários estão procurando e quais resultados de pesquisa são os mais relevantes e levam a uma compra. Além disso, você pode ver o que usuários em determinadas localizações estão procurando e direcioná-los de acordo com as fontes de mídia.

**Trigger**

Quando o usuário realiza uma pesquisa

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_date\_a | Data do check-in | 2018/07/26 |
| af\_date\_b | Data do check-out | 01/08/2018 |
| af\_destination\_a | Localização do usuário | Londres |
| af\_destination\_b | Localização do hotel | Madri |
| af\_num\_adults | Quantidade de hóspedes | 2 |
| af\_num\_children | Quantidade de crianças | 0 |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Exibição de conteúdo (af_content_view)">

**Propósito**

Esse evento pode ajudar a determinar:

* Se os resultados da pesquisa são relevantes para consultas de pesquisa
* Que tipos de propriedade os usuários estão procurando
* Tendências sazonais
* Destinos populares
* Quais fontes de mídia trazem usuários, e assim, redirecionar esses usuários em anúncios e promoções

**Trigger**

Quando o usuário está visualizando uma propriedade

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Preço tabela do hotel | 674 |
| af\_content\_id | ID do hotel | ODIRNH |
| af\_date\_a | Data do check-in | 2018/07/26 |
| af\_date\_b | Data do check-out | 01/08/2018 |
| af\_destination\_a | Localização do usuário | Londres |
| af\_destination\_b | Localização do hotel | Madri |
| af\_class | Tipo de quarto | Deluxe |
| af\_num\_adults | Quantidade de hóspedes | 2 |
| af\_num\_children | Quantidade de crianças | 0 |
| af\_hotel\_score | Pontuação do hotel por avaliações | 9.6 |
| af\_preferred\_star\_ratings | Preferência de classificação por estrela do hotel | 5 |
| af\_preferred\_neighborhoods | Área em que o hotel está localizado | Centro |

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Adicionar à lista de desejos (af_add_to_wishlist)">

**Propósito**

Gravar quais hotéis e destinos os usuários estão interessados em reservar. Quando você sabe, por exemplo, quais hotéis, regiões e as classificações por estrelas que os usuários estão procurando, você pode usar esses dados para redirecionar os usuários.

**Trigger**

Quando um usuário adiciona uma propriedade à sua lista de desejos

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Preço tabela do hotel | 674 |
| af\_content\_id | ID do hotel | ODIRNH |
| af\_date\_a | Data do check-in | 2018/07/26 |
| af\_date\_b | Data do check-out | 01/08/2018 |
| af\_destination\_a | Localização do usuário | Londres |
| af\_destination\_b | Localização do hotel | Madri |
| af\_class | Tipo de quarto | Deluxe |
| af\_num\_adults | Quantidade de hóspedes | 2 |
| af\_num\_children | Quantidade de crianças | 0 |
| af\_hotel\_score | Pontuação do hotel por avaliações | 9.6 |
| af\_preferred\_star\_ratings | Preferência de classificação por estrela do hotel | 5 |
| af\_preferred\_neighborhoods | Área em que o hotel está localizado | Centro |
| purchase\_method | Método de compra | Cartão de crédito |
| af\_coupon\_code | Código promocional ou pontos de programas de fidelidade | SUM2018 |
| property\_type | Tipo de propriedade | Hotel |

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="Checkout iniciado (af_initiated_checkout)">

**Propósito**

Entenda como os compradores se comportam quando se encaminham para o checkout. Esse evento pode ajudar a determinar:

* Qual método de compra foi usado como, por exemplo, cartão de crédito ou eWallet
* Se os usuários concluem o processo de checkout

**Trigger**

Quando o usuário adiciona suas informações de cartão de crédito ou conecta seu eWallet

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Preço tabela do hotel | 674 |
| af\_content\_id | ID do hotel | ODIRNH |
| af\_date\_a | Data do check-in | 2018/07/26 |
| af\_date\_b | Data do check-out | 01/08/2018 |
| af\_destination\_a | Localização do usuário | Londres |
| af\_destination\_b | Localização do hotel | Madri |
| af\_class | Tipo de quarto | Deluxe |
| af\_num\_adults | Quantidade de hóspedes | 2 |
| af\_num\_children | Quantidade de crianças | 0 |
| af\_hotel\_score | Pontuação do hotel por avaliações | 9.6 |
| af\_preferred\_star\_ratings | Preferência de classificação por estrela do hotel | 5 |
| af\_preferred\_neighborhoods | Área em que o hotel está localizado | Centro |
| purchase\_method | Método de compra | Cartão de crédito |
| af\_coupon\_code | Código promocional ou pontos de programas de fidelidade | SUM2018 |
| property\_type | Tipo de propriedade | Hotel |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Propósito**

Saiba mais sobre as tendências de compra em seu aplicativo de reserva de hotel. Esse evento pode ajudar a:

* Descobrir o LTV de seus usuários e o ROI de suas campanhas em ad networks e agências de anúncios
* Descobrir quais ofertas são mais populares entre os seus usuários
* Fazer referência cruzada de campanhas com itens comprados para otimizar o direcionamento de campanhas

**Trigger**

Quando o usuário acessa a página de agradecimento após uma compra bem-sucedida

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | A receita estimada de uma compra | 1205.99 |
| af\_preço | Montante total da compra | 4000 |
| af\_content\_id | ID do item | 121 |
| af\_content\_type | Categoria do item | hotel |
| af\_currency | Código da moeda | AUD |
| af\_quantity | Quantidade de itens no carrinho | 1 |
| af\_order\_id | ID do pedido que foi gerado após a compra | X123ABC |
| af\_receipt\_id | ID do pedido, necessária para a integração de redirecionamento CRITEO e Google Ad Words | X123ABC |

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="Reserva de viagem (af_travel_booking)">

**Propósito**

Determinar a taxa geral de reserva no seu aplicativo. Esse evento pode ajudar a:

* Registrar a receita gerada a partir da reserva
* Determinar o número de usuários que reservam hotéis com crianças
* Entender as tendências sazonais
* Definir hotéis populares

**Trigger**

Quando o usuário chega à página de agradecimento após reservar um hotel

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Receita das reservas | 647.95 |
| af\_currency | Código da moeda | GBP |
| af\_preço | Preço tabela do hotel | 674 |
| af\_content\_id | ID do hotel | ODIRNH |
| af\_date\_a | 2018/07/26 | Data do check-in |
| af\_date\_b | Data do check-out | 01/08/2018 |
| af\_destination\_a | Localização do usuário | Londres |
| af\_destination\_b | Localização do hotel | Madri |
| af\_class | Tipo de quarto | Deluxe |
| af\_num\_adults | Quantidade de hóspedes | 2 |
| af\_num\_children | Quantidade de crianças | 0 |
| af\_hotel\_score | Pontuação do hotel por avaliações | 9.6 |
| af\_preferred\_star\_ratings | Preferência de classificação por estrela do hotel | 5 |
| af\_preferred\_neighborhoods | Área em que o hotel está localizado | Centro |
| purchase\_method | Método de compra | Cartão de crédito |
| af\_coupon\_code | Código promocional ou pontos de programas de fidelidade | SUM2018 |
| property\_type | Tipo de propriedade | Hotel |
| nova\_reserva | Primeira reserva do usuário | verdadeiro |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estruturas recomendadas para eventos personalizados

A seção a seguir fornece uma lista de estruturas de eventos que incluem nomes de eventos personalizados e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="first-purchase-first_purchase" />

<Accordion title="Primeira compra (first_purchase)">

**Propósito**

O mesmo que o evento [Compra](/docs/recommended-hotel-booking-app-events#purchase-af_purchase). Além disso, este evento pode ajudá-lo a determinar:

* Quanto tempo um novo comprador demora para comprar
* Quais produtos clientes que compram pela primeira vez preferem comprar
* O preço médio e a receita das compras pela primeira vez

**Trigger**

Quando o usuário conclui sua primeira compra

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Receita da compra | 1205.95 |
| af\_preço | Montante total da compra | 4000 |
| af\_content\_id | ID do item | 121, 262 |
| af\_content\_type | Categoria do item | hotel |
| af\_currency | Moeda | AUD |
| af\_quantity | Quantidade de itens no carrinho | 1 |
| af\_order\_id | ID do pedido gerada após a compra | X123ABC |
| af\_receipt\_id | ID do pedido, necessário para a integração de retargeting CRITEO e Google AdWords | X123ABC |

</Accordion>

<div data-zendesk-anchors="hotel-booking=-reserva-de-hotel h_01HGTB0APWWTRER6GAWJ7TJ05S=-reserva-de-hotel h_01HGTB0APWQDX7VN96GM7520ZH=importante recommended-structures-for-predefined-events=estruturas-recomendadas-para-eventos-predefinidos h_01HGTB0APW933179Q90HFASW1V=estruturas-recomendadas-para-eventos-predefinidos h_01HGTB0APWRKRGCJ5TFKTPHH33=complete-registration-af_complete_registration h_01HGTB0APW1XY5R69CJ8PSQV6C=login-af_login h_01HGTB0APW5YF2DASC0HYDPTA9=search-af_search h_01HGTB0APXTQWBS4EXJ8D724G0=content-view-af_content_view h_01HGTB0APXS95QGK17RE8B3Y1E=add-to-wishlist-af_add_to_wishlist h_01HGTB0APX1XX2W3YX85W75F6B=initiated-checkout-af_initiated_checkout h_01HGTB0APXGPW16FRY3C7VSMDM=purchase-af_purchase h_01HGTB0APXJFHMPGYC63ZTV4R9=travel-booking-af_travel_booking recommended-structures-for-custom-events=estruturas-recomendadas-para-eventos-personalizados h_01HGTB0APXP6WVM1AVEMEY6KVS=estruturas-recomendadas-para-eventos-personalizados h_01HGTB0APX4ND0NGVTK9FA38QR=first-purchase-first_purchase" />
