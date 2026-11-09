---
title: Eventos recomendados para aplicativos de saúde
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
  created_at: '2021-05-01T10:41:05Z'
  edited_at: '2026-08-18T00:14:25Z'
  id: 360019888518
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/360019888518
---
> **Visão geral:** mensure a qualidade dos seus usuários ao longo da jornada, registrando esses exemplos de eventos in-app no seu aplicativo de saúde.

<div id="-healthcare" />

## <Image alt="5669_Healthcare_icon_3.png" src="https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png" width="100px" /> Saúde

Os aplicativos de saúde permitem que os usuários adquiram seguros de saúde, marquem consultas e recebam orientação médica. Os eventos típicos que são registrados incluem logins, registros e outros eventos gerais sem informações pessoais ou de saúde.

<div id="important" />

> 🚧 **Importante!**
>
> * **Uma nota de nossos advogados**: dados de saúde são considerados "Dados restritos" e são considerado uma categoria especial de dados em muitas jurisdições. Como tal, os clientes estão proibidos de enviar à AppsFlyer quaisquer desses dados.
> * Certifique-se de ler as <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#configurando-eventos-in-app">instruções</Anchor> para os profissionais de marketing sobre a implementação de eventos in-app.
> * Para agilizar o processo de implementação, use nosso <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=healthcare">gerador de eventos in-app</Anchor>. Essa ferramenta inclui todos os eventos in-app típicos descritos neste artigo e permite que você modifique os eventos de acordo com as necessidades da sua empresa. Depois de concluído, compartilhe o arquivo com seu desenvolvedor.
> * Para cada evento recomendado incluído neste artigo, há <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=healthcare&view=code">exemplos de código</Anchor> para desenvolvedores do iOS, Android e Unity.
> * Instruções detalhadas para seu desenvolvedor podem ser encontradas no <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyer developer hub</Anchor>.
>
> Para mais informações sobre como gravar eventos in-app, consulte o <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">guia Eventos avançados dentro do aplicativo</Anchor>.

<Image align="center" alt="In_appEvents_UserJourneys_-_Copy_of_Healthcare__1_.png" src="https://files.readme.io/54174e697c8dfe2d0d388c19fdd5fa0fbf9703c0155b9c250b40b5d0bcf19698-8232949117073.png" />

<div id="recommended-structures-for-predefined-events" />

## Estruturas recomendadas para eventos predefinidos

A seção a seguir oferece uma lista de estruturas de eventos que são típicas da vertical de saúde. Cada estrutura inclui um nome de evento pré-definido e os parâmetros de eventos de amostra a serem utilizados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Propósito**

Entenda a retenção de seus usuários cadastrados

**Gatilho**

Sempre que o usuário fizer login com sucesso

**Parâmetros do evento**

Pode ser enviado sem nenhum parâmetro adicional

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Propósito**

Saiba quantos usuários instalaram o aplicativo e concluíram o processo de inscrição e quais métodos de inscrição seus usuários preferem.

**Trigger**

Quando o usuário conclui o processo de cadastro

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_registration\_method | O tipo de método de cadastro | email, facebook |

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="Adicionar ao carrinho (af_add_to_cart)">

**Propósito**

Registre quando um usuário adiciona um produto ao seu carrinho. Esse evento pode ajudá-lo a determinar:

* Quantos produtos em média os compradores adicionam em uma compra
* Quanto tempo passa entre a adição de dois produtos diferentes
* Quantos compradores abandonam seu carrinho

**Trigger**

Quando o usuário adiciona um produto ao carrinho

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_quantity | Quantidade solicitada | 1 |
| af\_preço | Preço do produto | 10 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Propósito**

Registre compras in-app feitas pelos usuários. Esse evento pode ajudar a:

* Descobrir o LTV de seus usuários e o ROI de suas campanhas em ad networks e agências de anúncios
* Descobrir quais ofertas são mais populares entre os seus usuários
* Fazer referência cruzada de campanhas com itens comprados para otimizar o direcionamento de campanhas

**Trigger**

Quando o usuário acessa a página de agradecimento após uma compra bem-sucedida

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Receita da compra | 50.55 |
| af\_currency | Código da moeda | USD |
| af\_order\_id | ID do pedido | 9277 |
| payment\_method\_type | Método de pagamento usado | cartão de crédito, local |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estruturas recomendadas para eventos personalizados

A seção a seguir fornece a estrutura do evento, incluindo o nome do evento personalizado e exemplos de parâmetros a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="topup-success-top_up_success" />

<Accordion title="Sucesso na recarga (top_up_success)">

**Propósito**

Os fundos de recarga podem ser usados para comprar qualquer pacote ou serviço oferecido dentro do aplicativo. Você pode registrar esse evento e compará-lo com outros dados para saber mais sobre seus usuários. Por exemplo, você pode saber quais valores as pessoas estão dispostas a depositar em suas contas e usar os valores de recarga para direcionar os usuários para campanhas personalizadas dentro de seus orçamentos de recarga.

**Trigger**

Quando o usuário conclui a recarga

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | O valor da recarga | 2000.55 |
| top\_up\_id | O ID da recarga | 397 |
| payment\_method\_type | Método de pagamento usado | cartão de crédito, pagamento local |

</Accordion>

<div data-zendesk-anchors="healthcare=-sa%C3%BAde h_01HGTAFRKKJ22SHB4JHMTGW2TV=-sa%C3%BAde h_01HGTAFRKKPWC1PQTKF227WWBD=importante recommended-structures-for-predefined-events=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAFRKKRB8EY8KJ9NXM4Z2T=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAFRKK35Q5W5ADQC2KYHR9=login-af_login h_01HGTAFRKK8E52FRVWQXP4Y3VV=complete-registration-af_complete_registration h_01HGTAFRKN6NJPDB053YYYH202=add-to-cart-af_add_to_cart h_01HGTAFRKNJVFECSFGSWG8B7GN=purchase-af_purchase recommended-structures-for-custom-events=estruturas-recomendadas-para-eventos-personalizados h_01HGTAFRKN29RJRW2V2WCH2AXT=estruturas-recomendadas-para-eventos-personalizados h_01HGTAFRKNDWHDDR9KDRKJ4H8E=topup-success-top_up_success" />
