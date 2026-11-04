---
title: Eventos recomendados para apps de transporte de passageiros
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
  created_at: '2021-04-29T08:42:34Z'
  edited_at: '2026-08-18T00:14:36Z'
  id: 360019651957
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/360019651957
---
> **Visão geral:** mensure a qualidade dos seus usuários durante toda a jornada de usuário, registrando esses eventos in-app sugeridos para seu aplicativo de transporte de passageiros.

<div id="-ride-hailing" />

## <Image alt="InApp_Events_ride.png" src="https://files.readme.io/3901cfcc0cc821cc9c93edbe806bc2d570698be366b76b3710cb60e9aa190d91-20659532208401.png" width="100px" /> Serviços de transporte por aplicativo

Recentemente, o transporte de passageiros se tornou muito popular, principalmente em áreas urbanas onde a maioria dos residentes não possui carro. Os eventos típicos que sugerimos que você registre são pedidos e reservas de transporte.

Gravar eventos pode ajudar a determinar:

* Como passageiros e motoristas interagem
* Países onde as pessoas mais usam serviços de transporte de passageiros
* Métricas sobre preço, corridas e distância das corridas

<div id="important" />

> 🚧 **Importante!**
>
> * Certifique-se de ler <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#configurando-eventos-in-app">as instruções</Anchor> para os profissionais de marketing sobre a implementação de eventos in-app.
> * Para agilizar o processo de implementação, use nosso <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ride_hailing">gerador de eventos in-app</Anchor>. Essa ferramenta inclui todos os eventos in-app típicos descritos neste artigo e permite que você modifique os eventos de acordo com as necessidades da sua empresa. Depois de concluído, compartilhe o arquivo com seu desenvolvedor.
> * Para cada evento recomendado incluído neste artigo, há <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ride_hailing&view=code">exemplos de código</Anchor> para desenvolvedores do iOS, Android e Unity.
> * Instruções detalhadas para o desenvolvedor podem ser encontradas no **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub para desenvolvedores da AppsFlyer</Anchor>.**
>
> Para mais informações sobre como gravar eventos in-app, consulte o <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">guia Eventos avançados dentro do aplicativo</Anchor>.

[![Fluxograma_da_jornada_do_usuário_do_aplicativo_de_transporte_por_chamada_para_eventos_recomendados](https://files.readme.io/5ec4efcc699ef8749e1d5cd6e693472713f3d7945a41e1601965d0e7cdb68706-4402678863377.png)](https://files.readme.io/5ec4efcc699ef8749e1d5cd6e693472713f3d7945a41e1601965d0e7cdb68706-4402678863377.png)

<div id="recommended-structures-for-predefined-events" />

## Estruturas recomendadas para eventos predefinidos

A seção a seguir oferece uma lista de estruturas de eventos que são típicas da vertical de transporte de passageiros. Cada estrutura inclui um nome de evento predefinido e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Propósito**

Esse evento pode ajudar a:

* Saber quais métodos de cadastro seus usuários preferem
* Compreender quantos usuários realmente se cadastraram após baixar e instalar o aplicativo
* Ver tendências de cadastro em vários países para identificar os países cujos usuários são mais propensos a usar seu aplicativo

**Trigger**

Quando o usuário conclui o processo de inscrição

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_registration\_method | Plataforma ou método que o usuário utiliza para se cadastrar | Facebook |
| código\_país | Código do país (código de telefone) | 66 |

</Accordion>

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Propósito**

Entender a retenção de seus usuários registrados

**Trigger**

Quando o usuário faz login com sucesso

**Parâmetros do evento**

Pode ser enviado sem nenhum parâmetro adicional

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="Adicionar informações de pagamento (af_add_payment_info)">

**Propósito**

Ajudar a categorizar os usuários. Você pode:

* Saber quanto tempo um usuário leva para adicionar informações de pagamento
* Quais métodos de pagamento são os mais populares, por exemplo, cartão de crédito ou cartão digital
* Realizar campanhas e colaborar com prestadores de métodos de pagamentos populares

**Trigger**

Quando o usuário adiciona com êxito as informações de pagamento à conta

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_success | Se o método de pagamento é bem-sucedido | verdadeiro |
| tipo\_de\_cartão\_de\_crédito | Tipo de cartão de crédito (opcional) | Visa, Mastercard |
| payment\_method\_type | Tipo de método de pagamento | cartão de crédito, cartão digital |

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="Créditos gastos (af_spent_credits)">

**Propósito**

O [evento de reserva de viagem concluída](/docs/recommended-ride-hailing-app-events#ride-booking-completed-ride_booking_completed) inclui um parâmetro chamado  `credits_earned`. Esse parâmetro registra os créditos acumulados pelo passageiro em cada viagem. Os passageiros podem trocar créditos por vouchers e descontos.

Esse evento pode ajudar a:

* Ver quantos passageiros trocam créditos por vouchers
* Descobrir que tipo de vouchers e descontos os passageiros preferem

**Gatilho**

Quando um passageiro gasta créditos

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_content | Tipo de voucher ou desconto | Ingresso para cinema |
| credits\_used | Quantidade de créditos usados | 1000 |
| créditos\_restantes | Quantidade de créditos disponíveis na conta | 2090 |
| id\_da\_fatura | ID da fatura criada para gasto com créditos | KO215123SD |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estruturas recomendadas para eventos personalizados

A seção a seguir fornece uma lista de estruturas de eventos que incluem nomes de eventos personalizados e os parâmetros de eventos sugeridos para usar. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="ride-booking-requested-ride_booking_requested" />

<Accordion title="Reserva de transporte solicitada (ride_booking_requested)">

**Propósito**

Esse evento pode ajudar a:

* Saber sobre destinos populares
* Saber sobre tendências, para onde as pessoas vão e de onde vêm
* Ver a distância média de uma corrida
* Ver de quais cidades, regiões e países vem a maioria dos usuários

Além do mais, registrar este evento em conjunto com outros eventos relacionados a reservas pode ajudar você a acompanhar transações bem-sucedidas. Você então pode comparar transações bem-sucedidas com transações malsucedidas. Por exemplo, você pode ver quantas reservas de viagens são solicitadas e quantas reservas de viagens são concluídas ou canceladas.

**Gatilho**

Quando o passageiro cria uma solicitação de reserva de transporte

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Preço cotado para a viagem | 22.4 |
| af\_currency | Moeda | SGD |
| af\_destination\_a | Ponto de partida | Plaza Singapura |
| af\_destination\_b | Ponto de chegada | Marina Bay Sands |
| distance | Distância entre os dois destinos | 5.2 |
| af\_content\_type | Tipo de transporte | Táxi |
| payment\_method\_type | Tipo de método de pagamento | cartão de crédito, cartão digital |
| af\_city | Cidade onde o transporte é reservado | Singapura |
| af\_region | Região onde o transporte é reservado | SFA |
| af\_country | País onde o transporte é reservado | Singapura |
| order\_id | ID do pedido | 135790 |

</Accordion>

<div id="ride-booking-confirmed-ride_booking_confirmed" />

<Accordion title="Reserva de transporte confirmada (ride_booking_confirmed)">

**Propósito**

Esse evento pode ajudar a:

* Saber quais são os motoristas mais ativos
* Ver quais destinos são comuns entre os motoristas
* Ver o preço médio e total de viagens para cada motorista

Além do mais, registrar este evento em conjunto com outros três eventos relacionados a reservas pode ajudar você a compreender melhor a atividade dos motoristas. Por exemplo, é possível ver quais motoristas confirmam a maioria das solicitações de reserva de transporte e quais motoristas escolhem viagens curtas em vez de viagens longas.

<div id="trigger" />

#### **Gatilho**

Quando a reserva é aceita por um motorista

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Preço cotado para a viagem | 22.4 |
| af\_currency | Moeda | SGD |
| af\_destination\_a | Ponto de partida | Plaza Singapura |
| af\_destination\_b | Ponto de chegada | Marina Bay Sands |
| distance | Distância entre os dois destinos | 5.2 |
| af\_content\_type | Tipo de transporte | Táxi |
| id\_do\_motorista | ID do motorista que confirmou a realização da corrida | 1706 |
| payment\_method\_type | Tipo de método de pagamento | cartão de crédito, cartão digital |
| af\_city | Cidade onde o transporte é reservado | Singapura |
| af\_region | Região onde o transporte é reservado | SFA |
| af\_country | País onde o transporte é reservado | Singapura |
| af\_order\_id | ID do pedido | 135790 |

</Accordion>

<div id="ride-booking-canceled-ride_booking_canceled" />

<Accordion title="Reserva de transporte cancelada (ride_booking_canceled)">

**Propósito**

Esse evento pode ajudar a:

* Registrar motoristas ou passageiros que cancelam constantemente
* Saber quantas viagens foram canceladas
* Correlacionar viagens concluídas com atributos como preço, destino, distância e cidades
* Saber os motivos do cancelamento de uma viagem

**Gatilho**

Quando a reserva é cancelada

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Preço cotado para a viagem | 22.4 |
| af\_currency | Moeda | SGD |
| af\_destination\_a | Ponto de partida | Plaza Singapura |
| af\_destination\_b | Ponto de chegada | Marina Bay Sands |
| distance | Distância entre os dois destinos | 5.2 |
| af\_content\_type | Tipo de transporte | Táxi |
| id\_do\_motorista | ID do motorista que confirmou a corrida | 1706 |
| motivo\_do\_cancelamento | Motivo do cancelamento da viagem | preço muito alto, motorista não apareceu, passageiro não apareceu |
| payment\_method\_type | Tipo de método de pagamento | cartão de crédito, cartão digital |
| af\_city | Cidade onde o transporte é reservado | Singapura |
| af\_region | Região onde o transporte é reservado | SFA |
| af\_country | País onde o transporte é reservado | Singapura |
| order\_id | ID do pedido | 135790 |
| cancelado\_por | Se a viagem foi cancelada pelo passageiro ou pelo motorista | Passageiro |

</Accordion>

<div id="ride-booking-completed-ride_booking_completed" />

<Accordion title="Reserva de transporte concluída (ride_booking_completed)">

**Propósito**

Esse evento pode ajudar a:

* Saber quanto os passageiros gastam e quanto os motoristas ganham
* Correlacionar viagens concluídas com atributos como destino, distância, tipo de pagamento e ID do motorista
* Ver a distância média e total para motoristas e passageiros
* Comparar viagens concluídas com viagens canceladas
* Registrar a pontuação de motoristas

**Gatilho**

Quando a viagem é concluída

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Preço cotado para a viagem | 22.4 |
| af\_currency | Moeda | SGD |
| af\_destination\_a | Ponto de partida | Plaza Singapura |
| af\_destination\_b | Ponto de chegada | Marina Bay Sands |
| distance | Distância entre os dois destinos | 5.2 |
| af\_content\_type | Tipo de transporte | Táxi |
| id\_do\_motorista | ID do motorista que confirmou a realização da corrida | 1706 |
| payment\_method\_type | Tipo de método de pagamento | cartão de crédito, cartão digital |
| af\_city | Cidade onde o transporte é reservado | Singapura |
| af\_region | Região onde o transporte é reservado | SFA |
| af\_country | País onde o transporte é reservado | Singapura |
| order\_id | ID do pedido | 135790 |
| credits\_earned | Créditos que o passageiro ganhou ao concluir uma viagem | 248 |

</Accordion>

<div data-zendesk-anchors="ridehailing=-servi%C3%A7os-de-transporte-por-aplicativo h_01HGTAZ7J64RZE35JP8XPKMTPZ=-servi%C3%A7os-de-transporte-por-aplicativo h_01HGTAZ7J6N36EH492QDXCQYB1=importante recommended-structures-for-predefined-events=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAZ7J6FJ8R9VXKK0F1A1E1=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAZ7J6FQQKV7JB0Z9MG8CD=complete-registration-af_complete_registration h_01HGTAZ7J6YM8DJ96E7Q4M4Y8Q=login-af_login h_01HGTAZ7J67MNJ8T9B9W4NJ5Y9=add-payment-info-af_add_payment_info h_01HGTAZ7J6Z3EX03JTPZFHJJF6=spent-credits-af_spent_credits recommended-structures-for-custom-events=estruturas-recomendadas-para-eventos-personalizados h_01HGTAZ7J6Z6NE8D5A10CRJJH4=estruturas-recomendadas-para-eventos-personalizados h_01HGTAZ7J6WCY2BQJPSNSTJRQ0=ride-booking-requested-ride_booking_requested h_01HGTAZ7J78J1X3VAYMH8Q3ZBA=ride-booking-confirmed-ride_booking_confirmed trigger=gatilho h_01HGTAZ7J7C4R7A7KT2S95835J=gatilho h_01HGTAZ7J797KA791H1621F9TE=ride-booking-canceled-ride_booking_canceled h_01HGTAZ7J789CJ8P6X8B0V7A64=ride-booking-completed-ride_booking_completed" />
