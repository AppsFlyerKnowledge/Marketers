---
title: Eventos recomendados para aplicativos de telecomunicações
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
  created_at: '2021-05-02T11:59:16Z'
  edited_at: '2026-08-18T00:14:42Z'
  id: 360019896558
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/360019896558
---
> **Visão geral:** mensure a qualidade dos seus usuários durante toda a jornada de usuário, registrando esses eventos in-app sugeridos para seu aplicativo de telecomunicações.

<div id="-telecommunication" />

## <Image alt="telecommunications_icon.png" src="https://files.readme.io/42f1aac3b825957d9d0584d83480c441b9d53665cc6cf1a6b8cd1803bb9b6121-20659194885393.png" width="100px" /> Telecomunicações

Os aplicativos de telecomunicações permitem que os usuários adquiram e gerenciem planos de celular, planos de dados e outros. Os eventos típicos que sugerimos que você registre incluem compras, recargas e assinaturas.

Gravar esse evento pode ajudar a determinar:

* Quais planos iniciais são mais populares
* Quais produtos ou pacotes os usuários podem pagar
* Com quais planos os clientes têm maior probabilidade de se comprometer a longo prazo

<div id="important" />

> 🚧 **Importante!**
>
> * Certifique-se de ler as <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#configurando-eventos-in-app">instruções</Anchor> para os profissionais de marketing sobre a implementação de eventos in-app.
> * Para agilizar o processo de implementação, use nosso <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=telecommunication">gerador de eventos in-app</Anchor>. Essa ferramenta inclui todos os eventos in-app típicos descritos neste artigo e permite que você modifique os eventos de acordo com as necessidades da sua empresa. Depois de concluído, compartilhe o arquivo com seu desenvolvedor.
> * Para cada evento recomendado incluído neste artigo, há <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=telecommunication&view=code">exemplos de código</Anchor> para desenvolvedores do iOS, Android e Unity.
> * Instruções detalhadas para o seu desenvolvedor podem ser encontradas no **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">developer hub (hub para desenvolvedores) da AppsFlyer</Anchor>.**
>
> Para mais informações sobre como gravar eventos in-app, consulte o <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">guia Eventos avançados dentro do aplicativo</Anchor>.

[![Fluxograma da jornada do usuário do aplicativo de telecomunicações para eventos recomendados](https://files.readme.io/ae4c696208b49aa546ffc0a15f76b148b35af43984a76e699d1df7c54507352c-4404604045457.png)](https://files.readme.io/ae4c696208b49aa546ffc0a15f76b148b35af43984a76e699d1df7c54507352c-4404604045457.png)

<div id="recommended-structures-for-predefined-events" />

## Estruturas recomendadas para eventos predefinidos

A seção a seguir oferece uma lista de estruturas de eventos que são típicas da vertical de telecomunicações. Cada estrutura inclui um nome de evento predefinido e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Propósito**

Entenda a retenção de seus usuários registrados

**Trigger**

Sempre que o usuário fizer login com sucesso

**Parâmetros do evento**

Pode ser enviado sem nenhum parâmetro adicional

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Propósito**

Saiba quantos usuários instalaram o aplicativo e concluíram o processo de inscrição e quais métodos de inscrição seus usuários preferem.

**Trigger**

Quando o usuário conclui o processo de inscrição

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_registration\_method | O tipo de método de cadastro | email, facebook |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Exibição de conteúdo (af_content_view)">

**Propósito**

Determinar a taxa de visualização de produtos específicos e:

* Correlacionar visualizações de produtos com vendas de produtos
* Entender quais categorias são mais populares de acordo com as visualizações de produtos
* Ver a correlação entre a moeda dos compradores e os produtos que eles visualizam

**Trigger**

Quando o usuário visualiza uma página de detalhes do produto específica

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Preço do produto | 200 |
| af\_content\_id | ID do produto | 102 |
| af\_content\_type | Categoria de produtos | Pacotes de internet |
| af\_currency | A moeda na página de detalhes do produto | THB, USD |

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="Exibição de lista (af_list_view)">

**Propósito**

Registre quais listas (por exemplo, produtos recém-adicionados, produtos relacionados ou produtos recomendados) são as mais visualizadas pelos consumidores.

**Trigger**

Quando o usuário visualiza uma lista específica

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_content\_type | Tipo de lista | Relacionados, recomendados, recém-chegados |
| af\_content\_list | Lista de IDs de conteúdo da categoria | 001, 092 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Propósito**

Muitos aplicativos de telecomunicações permitem que os usuários comprem itens como, por exemplo, um pacote adicional de dados. O registro desse evento pode ajudar você a:

* Descobrir o LTV de seus usuários e o ROI de suas campanhas em ad networks e agências de anúncios
* Descobrir quais ofertas são mais populares entre os seus usuários
* Fazer referência cruzada de campanhas com itens comprados para otimizar o direcionamento de campanhas

**Trigger**

Quando o usuário acessa a página de agradecimento após uma compra bem-sucedida

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | A receita estimada de uma compra | 2050.50 |
| af\_currency | Código da moeda | THB |
| af\_content\_type | Nome do pacote comprado | 5G |
| af\_order\_id | ID do pedido | 9277 |
| payment\_method\_type | Tipo de método de pagamento | cartão de crédito, pagamento local |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estruturas recomendadas para eventos personalizados

A seção a seguir fornece uma lista de estruturas de eventos que incluem nomes de eventos personalizados e os parâmetros de eventos sugeridos para usar. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="select-package-select_package" />

<Accordion title="Selecionar pacote (select_package)">

**Propósito**

Registre quando um usuário decide comprar um pacote, mas não fez o pagamento ainda. Você pode usar esses dados, por exemplo, para redirecionar usuários e enviar ofertas sobre outros serviços.

**Trigger**

Quando o usuário seleciona um pacote, mas não conclui o pagamento

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| price | Preço da assinatura | 50000 |
| af\_content\_type | Tipo de conteúdo selecionado pelo usuário | Dados 5 GB |

</Accordion>

<div id="topup-success-top_up_success" />

<Accordion title="Sucesso na recarga (top_up_success)">

**Propósito**

Os fundos da recarga podem ser usados para comprar qualquer pacote ou qualquer outro serviço oferecido dentro do aplicativo. Registre esse evento e o compare com outros dados para saber mais sobre seus usuários. Por exemplo, você pode descobrir quais valores os usuários estão dispostos a depositar em suas contas e usar os valores de recarga para direcionar os usuários para campanhas personalizadas dentro de seus orçamentos.

**Trigger**

Quando o usuário conclui a recarga

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | O valor da recarga | 2050.50 |
| top\_up\_id | O ID da recarga | 397 |
| payment\_method\_type | Tipo de método de pagamento | cartão de crédito, pagamento local |

</Accordion>

<div id="topup-unsuccessful-top_up_unsuccessful" />

<Accordion title="Top-up unsuccessful (top_up_unsuccessful)">

**Propósito**

Registre esse evento e o compare com outros dados para saber mais sobre seus usuários. Por exemplo, você pode saber quantos usuários tentam fazer uma recarga, mas falham.

**Trigger**

Quando o usuário tenta fazer uma recarga, mas a ação falha

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| error\_reason | O motivo para falha na recarga | exceeded\_daily\_limit |

</Accordion>

<div id="subscription-complete-subscription_complete" />

<Accordion title="Assinatura completa (subscription_complete)">

**Propósito**

O registro deste evento pode ajudar você a:

* Ver quais campanhas captam usuários que fazem uma assinatura ou cadastro
* Comparar o número de usuários com assinatura com usuários sem assinatura
* Registrar a receita gerada a partir da assinatura e atribuí-la a campanhas e fontes de mídias

**Trigger**

* Quando o usuário faz a assinatura com sucesso
* Quando uma assinatura for renovada

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| subscription\_type | Tipo de assinatura | Mensal 30 GB |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Valor da assinatura | 555.50 |

</Accordion>

<div data-zendesk-anchors="telecommunication=-telecomunica%C3%A7%C3%B5es h_01HGTAGFNFWKWYHPG6F5EK17YD=-telecomunica%C3%A7%C3%B5es h_01HGTAGFNG1Z8NAFJ71DP0YSYD=importante recommended-structures-for-predefined-events=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAGFNG99PQC03F13WQ4CVK=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAGFNGQ56C8CN7A325SQ7M=login-af_login h_01HGTAGFNG1W5QWGN1D969JHGY=complete-registration-af_complete_registration h_01HGTAGFNGRJHD89332473DZFE=content-view-af_content_view h_01HGTAGFNG10GNZVMDNXRJSYJ9=list-view-af_list_view h_01HGTAGFNGV82NQSZ29B96YJCQ=purchase-af_purchase recommended-structures-for-custom-events=estruturas-recomendadas-para-eventos-personalizados h_01HGTAGFNG3A2A6KCX8GGQAJBX=estruturas-recomendadas-para-eventos-personalizados h_01HGTAGFNGE3MKZEDKDZ0B9XDD=select-package-select_package h_01HGTAGFNGFSE2DAYRGG039GT9=topup-success-top_up_success h_01HGTAGFNGXBBYWJEMBVMN1YQS=topup-unsuccessful-top_up_unsuccessful h_01HGTAGFNGT3CJFRS2YC7R57KG=subscription-complete-subscription_complete" />
