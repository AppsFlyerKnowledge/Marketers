---
title: Eventos recomendados para aplicativos de passagens aéreas
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
  created_at: '2021-04-29T13:07:29Z'
  edited_at: '2026-08-18T00:13:39Z'
  id: 360019670857
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/360019670857
---
> **Visão geral:** Mensure a qualidade dos seus usuários ao longo da jornada usando como base alguns eventos específicos, ideais para apps de passagens aéreas.

<div id="-flight-booking" />

## <Image alt="InApp_Events_flight.png" src="https://files.readme.io/7a09c4a641dd5e797bffc41a6e66b20efe5660721f37abac3dd12ac83688b37b-20659533911697.png" width="100px" /> Passagens aéreas

Aplicativos passagens aéreas permitem que passageiros reservem voos com facilidade e escolham as melhores ofertas. Os eventos típicos que sugerimos que você registre são: reservar voo, pesquisar voos e visualizar ofertas.

Esses eventos permitem que você:

* Identifique destinos populares
* Analise tendências sazonais
* Identifique as companhias aéreas mais populares entre os usuários

<div id="important" />

> 🚧 **Importante!**
>
> * Certifique-se de ler as <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#configurando-eventos-in-app">instruções</Anchor> de implementação de eventos no aplicativo para profissionais de marketing.
> * Para simplificar o processo de implementação, use nosso <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=flight_booking">Gerador de eventos no aplicativo</Anchor>. Essa ferramenta inclui todos os eventos in-app típicos descritos neste artigo e permite que você modifique os eventos de acordo com as necessidades do seu negócio. Uma vez concluído, compartilhe o arquivo com seu desenvolvedor.
> * Para cada evento recomendado incluído neste artigo, existem <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=flight_booking&view=code">exemplos de código</Anchor> para desenvolvedores iOS, Android e Unity.
> * Instruções detalhadas para seu desenvolvedor podem ser encontradas no **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">Developer hub da AppsFlyer</Anchor>.**
>
> Para mais informações sobre como registrar eventos in-app, consulte o <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">Guia de eventos in-app</Anchor>.

[![Flowchart_for_recommended_events flight_booking_app_user_journey](https://files.readme.io/435378707a7299a8c98bc7490f0f1554b5f6c332a35c1546ce34feb1b6b86394-360020171258.png)](https://files.readme.io/435378707a7299a8c98bc7490f0f1554b5f6c332a35c1546ce34feb1b6b86394-360020171258.png)

<div id="recommended-structures-for-predefined-events" />

## Estruturas recomendadas para eventos predefinidos

A seção a seguir fornece uma lista de estruturas de eventos que são típicas desse setor. Cada estrutura inclui um nome de evento predefinido e os parâmetros de evento sugeridos a serem utilizados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às suas necessidades comerciais.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Cadastro completo (af_complete_registration)">

**Objetivo**

Saber quantos usuários instalaram o aplicativo e concluíram o processo de cadastro, e quais métodos de cadastro seus usuários preferem.

**Trigger**

Quando o usuário conclui o processo de cadastro

Parâmetros do evento

| Nome do campo | Descrição | Exemplo |
| --- | --- | --- |
| af\_registration\_method | Tipo de método de cadastro | e-mail, Facebook |

</Accordion>

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Objetivo**

Entender a retenção dos usuários cadastrados

**Gatilho**

Quando o usuário faz login com sucesso

**Parâmetros do evento**

Pode ser enviado sem parâmetros adicionais

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="Reserva de viagens (af_travel_booking)">

**Objetivo**

A capacidade de reservar voos é a função principal do aplicativo. Esse evento pode ajudar a determinar:

* Destinos populares
* Companhias aéreas populares
* Tendências sazonais

**Gatilho**

Quando o usuário chega à página de agradecimento após reservar um voo com sucesso

**Parâmetros do evento**

| Nome | Descrição | Exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Receita associada à reserva | 647.99 |
| af\_currency | Código da moeda | SGD |
| af\_preço | Preço | 674 |
| af\_content\_id | ID da oferta do voo | ODIRNH |
| af\_departing\_departure\_date | Data de partida | 21/06/2021 |
| af\_returning\_departure\_date | Data de retorno | 26/06/2018 |
| af\_destination\_a | Primeiro destino | BKK |
| af\_destination\_b | Segundo destino (se aplicável) | SYD |
| airline\_code | Código da companhia aérea | KLM |
| af\_class | Classe em que o voo foi reservado | econômica |
| purchase\_method | Método utilizado para a compra | cartão de crédito |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Visualização de conteúdo (af_content_view)">

**Objetivo**

Esse evento pode ajudar a determinar:

* Quais ofertas de voos os usuários acham mais atraentes
* Se os resultados da pesquisa são relevantes para as consultas de pesquisa

**Gatilho**

Quando um usuário clica em um resultado de pesquisa

**Parâmetros do evento**

| Nome | Descrição | Exemplo |
| --- | --- | --- |
| af\_departing\_departure\_date | Data de partida | 21/06/2021 |
| af\_returning\_departure\_date | Data de retorno | 26/06/2018 |
| af\_destination\_a | Primeiro destino | BKK |
| af\_destination\_b | Segundo destino (se aplicável) | SYD |

</Accordion>

<div id="search-af_search" />

<Accordion title="Pesquisa (af_search)">

**Objetivo**

Aplicativos de passagens aéreas permitem que os usuários procurem por voos e ofertas. Uma forma de obter insights sobre as preferências dos usuários é registrar os parâmetros de busca. Esse evento pode ajudar a:

* Saber o que os usuários estão procurando
* Identificar quais destinos são mais populares
* Saber quantos usuários viajam com crianças
* Descobrir em qual época do ano os usuários preferem ou planejam viajar

**Trigger**

Depois que o usuário preenche o formulário de pesquisa e clica no botão de pesquisa

**Parâmetros do evento**

| Nome | Descrição | Exemplo |
| --- | --- | --- |
| af\_num\_children | Número de crianças que estão viajando | 0 |
| af\_destination\_a | Primeiro destino | BKK |
| af\_destination\_b | Segundo destino (se aplicável) | SYD |
| af\_departing\_departure\_date | Data de partida | 21/06/2021 |
| af\_returning\_departure\_date | Data de retorno | 26/06/2018 |
| af\_num\_infants | Número de bebês que estão viajando | 0 |
| af\_num\_adults | Número de adultos que estão viajando | 1 |

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="Adicionar informações de pagamento (af_add_payment_info)">

**Objetivo**

Registrar tentativas bem-sucedidas e malsucedidas de adicionar informações de pagamento ao reservar um voo.

**Gatilho**

Quando um usuário clica no botão de reservar um voo

**Parâmetros do evento**

| Nome | Descrição | Exemplo |
| --- | --- | --- |
| af\_success | Se a adição do método de pagamento foi bem-sucedida | verdadeiro |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Objetivo**

Saiba mais sobre as tendências de compra no seu app. Esse evento pode ajudar a:

* Determinar o LTV dos usuários e o ROI das suas campanhas em ad networks e agências de publicidade
* Descobrir quais ofertas são mais populares entre os seus usuários
* Cruzar dados de campanhas com itens comprados para otimizar a segmentação

**Trigger**

Quando o usuário acessa a página de agradecimento após uma compra bem-sucedida

**Parâmetros do evento**

| Nome | Descrição | Exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Receita estimada da compra | 1205.99 |
| af\_preço | Soma total da compra | 4000 |
| af\_content\_id | ID do item | 121 |
| af\_content\_type | Categoria do item | voo |
| af\_currency | Código da moeda | AUD |
| af\_quantity | Número de itens no carrinho | 1 |
| af\_order\_id | ID do pedido gerado após a compra | X123ABC |
| af\_receipt\_id | ID do pedido, necessário para a integração de retargeting na CRITEO e Google Ad Words | X123ABC |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estruturas recomendadas para eventos personalizados

A seção a seguir fornece uma lista de estruturas de eventos que incluem nomes de eventos personalizados e os parâmetros de evento sugeridos. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às suas necessidades comerciais.

<div id="first-purchase-first_purchase" />

<Accordion title="Primeira compra (first_purchase)">

**Objetivo**

Igual ao evento [Compra](/docs/recommended-flight-booking-app-events#purchase-af_purchase). Além disso, esse evento pode ajudar a determinar:

* Quanto tempo leva para um novo comprador realizar uma compra
* Quais voos os compradores de primeira viagem preferem comprar
* O preço médio e a receita das primeiras compras

**Gatilho**

Quando o usuário completa sua primeira compra

**Parâmetros do evento**

| Nome | Descrição | Exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Receita da compra | 1205.99 |
| af\_preço | Soma total da compra | 4000 |
| af\_content\_id | ID do item | 121, 262 |
| af\_content\_type | Categoria do item | voo |
| af\_currency | Moeda | AUD |
| af\_quantity | Quantidade de itens no carrinho | 1 |
| af\_order\_id | ID do pedido gerado após a compra | X123ABC |
| af\_receipt\_id | ID do pedido, necessário para a integração de retargeting na CRITEO e Google AdWords | X123ABC |

</Accordion>

<div data-zendesk-anchors="flight-booking=-passagens-a%C3%A9reas h_01HGTAZRKG0SQ66XK7VN9KVGEY=-passagens-a%C3%A9reas h_01HGTAZRKGGQBBAM4XJHR4B45P=importante recommended-structures-for-predefined-events=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAZRKHK1427YX16HWRDRPN=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAZRKHACHNSNX9DSZ3ZZ51=complete-registration-af_complete_registration h_01HGTAZRKHTC9TNWNPACRZW31Y=login-af_login h_01HGTAZRKHZGW442XTZF99VGV9=travel-booking-af_travel_booking h_01HGTAZRKHGY0Z83ETZWAFNSWP=content-view-af_content_view h_01HGTAZRKH8JYE8Q6NDPF1PQC7=search-af_search h_01HGTAZRKH78CR2GH0960MS8R0=add-payment-info-af_add_payment_info h_01HGTAZRKHXE8VF78ZE0KF9AF6=purchase-af_purchase recommended-structures-for-custom-events=estruturas-recomendadas-para-eventos-personalizados h_01HGTAZRKH4ZZEK5JGXZ7G5QDJ=estruturas-recomendadas-para-eventos-personalizados h_01HGTAZRKHG7GE4BKFDRHZC163=first-purchase-first_purchase" />
