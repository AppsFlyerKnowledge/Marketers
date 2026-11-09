---
title: Eventos recomendados do app de eWallet
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
  created_at: '2021-06-10T11:36:07Z'
  edited_at: '2026-08-19T00:13:28Z'
  id: 4402425586065
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/4402425586065
---
> **Num relance:** Avalie a qualidade dos seus usuários ao longo da jornada do usuário registrando estes eventos in-app sugeridos para seu app de eWallet.

## <Image alt="InApp_Events_eWallet.png" src="https://files.readme.io/4d2ed4994bbe8e8eca7009b8ec8f5dbf22a626421a7a1efb213ddb4a12c7b487-4402543191825.png" width="67px" /> eWallet

Os apps de eWallet permitem que os usuários efetuem pagamentos ou façam compras digitais usando seus dispositivos. Os eventos típicos que sugerimos registrar incluem a adição de fundos, visualização de conteúdos, seleção de comerciantes, visualização de promoções e conclusão de transações.

Registrar esse evento pode ajudar a determinar:

* Que tipo de conteúdo e promoções são populares entre os usuários e, em seguida, oferecer produtos semelhantes ou relacionados
* Quais são os tipos de serviços mais populares para os quais os usuários utilizam a carteira digital quando efetuam pagamentos de faturas?
* Que comerciantes são os mais populares

<div id="important" />

> 🚧 **Importante!**
>
> * Certifique-se de ler <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#configurando-eventos-in-app">as instruções</Anchor> para os profissionais de marketing sobre a implementação de eventos in-app.
> * Para agilizar o processo de implementação, use nosso <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ewallet">gerador de eventos in-app</Anchor>. Essa ferramenta inclui todos os eventos in-app típicos descritos neste artigo e permite que você modifique os eventos de acordo com as necessidades da sua empresa. Depois de concluído, compartilhe o arquivo com o seu desenvolvedor.
> * Para cada evento recomendado incluído neste artigo, há <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ewallet&view=code">exemplos de código</Anchor> para desenvolvedores do iOS, Android e Unity.
> * Instruções detalhadas para o seu desenvolvedor podem ser encontradas no **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">developer hub (hub para desenvolvedores) da AppsFlyer</Anchor>.**
>
> Para mais informações sobre como registrar eventos in-app, consulte o <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">guia Eventos avançados dentro do aplicativo</Anchor>.

<Image align="center" alt="Flowchart_for_recommended_events e-Wallet_app_user_journey" src="https://files.readme.io/cf1f91f9c89d1f45448a6172e48b7f59fdce767f00c893d91b12a5f2d043945f-4404610923409.png" />

<div id="recommended-structures-for-predefined-events" />

## Estruturas recomendadas para eventos predefinidos

A seção a seguir oferece uma lista de estruturas de eventos que são típicas da vertical de jogos. Cada estrutura inclui um nome de evento predefinido e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Objetivo**

Saiba quantos usuários instalaram o aplicativo e concluíram o processo de inscrição e quais métodos de inscrição seus usuários preferem.

**Trigger**

Quando o usuário conclui o processo de inscrição

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_registration\_method | O tipo de método de cadastro | e-mail, Facebook, Google |

</Accordion>

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Objetivo**

Entender a retenção de seus usuários registrados

**Trigger**

Quando o usuário faz login com sucesso

**Parâmetros do evento**

Pode ser enviado sem nenhum parâmetro adicional

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Exibição de conteúdo (af_content_view)">

**Objetivo**

Determinar a taxa de visualização de um conteúdo específico. Esse evento pode ajudar a:

* Compreender que tipo de conteúdo é mais popular entre os seus usuários e, em seguida, otimizar as suas campanhas de marketing
* Correlacionar visualizações de itens com comerciantes

**Trigger**

Quando o usuário visualiza um item específico ou conteúdo de categoria

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| item | Tipo de artigo | bilhete de cinema |
| merchant\_name | Nome do comerciante | cineplex |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estruturas recomendadas para eventos personalizados

A seção a seguir fornece uma lista de estruturas de eventos que incluem nomes de eventos personalizados e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="wallet-complete-topup-wallet_complete_topup" />

<Accordion title="Recarga completa da carteira (wallet_complete_topup)">

**Objetivo**

Os fundos da recarga podem ser usados para comprar qualquer pacote ou qualquer outro serviço oferecido dentro do aplicativo. Registrar esse evento e compará-lo com outros dados para saber mais sobre seus usuários. Por exemplo, você pode descobrir quais valores os usuários estão dispostos a depositar em suas contas e usar os valores de recarga para direcionar os usuários para campanhas personalizadas dentro de seus orçamentos.

**Trigger**

Quando o usuário completa o carregamento do seu cartão bancário ou de crédito para a aplicação eWallet

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| top\_up\_amount | Montante do pagamento | 100 |
| top\_up\_method | Tipo de método de pagamento | transferência bancária |

</Accordion>

<div id="payment-transaction-completed-payment_transaction_completed" />

<Accordion title="Transação de pagamento concluída (payment_transaction_completed )">

**Objetivo**

Esse evento pode ajudar a:

* Destacar os usuários que concluíram o pagamento de uma transação.
* Identificar grandes transações e, em seguida, redirecionar os usuários que efetuam carregamentos com uma grande quantia de dinheiro.

**Trigger**

Quando a transação de uma compra específica é concluída

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| item | Item pago | recarga de cartão pré-pago |
| quantidade | Valor pago | 1 |
| transaction\_amount | Montante da transação | 50 |

</Accordion>

<div id="bill-payment-success-bill_payment_success" />

<Accordion title="Sucesso do pagamento da fatura (bill_payment_success)">

**Objetivo**

Este evento pode ajudar você a determinar o tipo de serviço mais popular para o qual os usuários utilizam a carteira digital quando pagam contas (por exemplo, contas de água, eletricidade ou saldos de cartões de crédito).

**Trigger**

Quando o usuário utiliza a carteira digital para efetuar pagamentos, tais como faturas, extratos de cartões de crédito ou bilhetes de cinema

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| merchant\_name | Nome do comerciante | Fornecedor de eletricidade |
| payment\_amount | Valor pago | 100 |
| category | Tipo de serviço | Eletricidade |

</Accordion>

<div id="promo-promo" />

<Accordion title="Promoção (promo)">

**Objetivo**

Esse evento pode ajudar a determinar:

* Se a promoção que está a ser oferecida é popular entre os usuários
* Se a promoção contribui para a venda cruzada de produtos adicionais aos usuários

**Trigger**

Quando o usuário seleciona a promoção disponível na aplicação

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| promo\_type | Tipo de promoção que está a ser oferecida | 30% off |

</Accordion>

<div id="voucher-redeem-voucher_redeem" />

<Accordion title="Voucher resgatar (voucher_redeem)">

**Objetivo**

Esse evento pode ajudar a determinar:

* Quantos usuários resgatam códigos promocionais
* Que tipo de cupões e descontos preferem os usuários

**Trigger**

Quando um código de promoção do usuário é resgatado

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| voucher\_ID | ID do vale | 1735103 |
| merchant\_name | Nome do comerciante | cineplex |

</Accordion>

<div id="select-merchant-select_merchant" />

<Accordion title="Selecionar comerciante (select_merchant )">

**Objetivo**

Este evento pode ajudar você a determinar qual é o comerciante mais popular e, em seguida, utilizar esses dados para tentar conseguir que comerciantes semelhantes adiram ao serviço eWallet.

**Trigger**

Quando o usuário seleciona um comerciante da lista de comerciantes disponíveis

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| merchant\_name | Nome do comerciante | cineplex |
| Tipo | Tipo de atividade | cinema |
| Quantidade | Moeda utilizada pelo anunciante | USD |
| merchant\_ID | Identificação específica associada a uma empresa que indica aos sistemas de processamento de pagamentos envolvidos numa transação para onde enviar os fundos | 123456 |

</Accordion>

<div id="scan-barcode-success-scan_barcode_success" />

<Accordion title="Sucesso da leitura do código de barras (scan_barcode_success )">

**Objetivo**

Esse evento pode ajudar a:

* Compreender quando um usuário conclui uma transação específica com um comerciante
* Determinar quais são os comerciantes mais populares

**Trigger**

Quando o usuário digitaliza o código QR de cada comerciante que visitou utilizando a aplicação eWallet

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| merchant\_name | Nome do comerciante | cineplex |
| merchant\_ID | Identificação específica associada a uma empresa que indica aos sistemas de processamento de pagamentos envolvidos numa transação para onde enviar os fundos | 123456 |

</Accordion>

<div data-zendesk-anchors="ewallet=-ewallet h_01HGTAEVWFZXCA7AV0P35W992F=-ewallet h_01HGTAEVWFR4QS6XAT1T28N1R5=importante recommended-structures-for-predefined-events=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAEVWF8SVYTQMQ12219HX0=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAEVWFBA3CD7ZA40VCER95=complete-registration-af_complete_registration h_01HGTAEVWGDBN8B3P2YHQJ5RYF=login-af_login h_01HGTAEVWGYFYEZBD3ZED7GGFG=content-view-af_content_view recommended-structures-for-custom-events=estruturas-recomendadas-para-eventos-personalizados h_01HGTAEVWG39P9A84P926BG3VE=estruturas-recomendadas-para-eventos-personalizados h_01HGTAEVWGNYC5Z0ACHV8CFVNQ=wallet-complete-topup-wallet_complete_topup h_01HGTAEVWG36K4V4Z0NN8QYDNV=payment-transaction-completed-payment_transaction_completed h_01HGTAEVWG136M86GM1JPV74RH=bill-payment-success-bill_payment_success h_01HGTAEVWG34EXM28GW2ZN0NRC=promo-promo h_01HGTAEVWG0EHESWPQHCX4P3SH=voucher-redeem-voucher_redeem h_01HGTAEVWGKGC7N8ZB0MMQJ4YE=select-merchant-select_merchant h_01HGTAEVWG20101JC5VVK29Y0E=scan-barcode-success-scan_barcode_success" />
