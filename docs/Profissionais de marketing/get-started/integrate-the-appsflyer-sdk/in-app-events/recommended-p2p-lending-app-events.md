---
title: Eventos recomendados para aplicativos de empréstimo P2P
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
  created_at: '2021-04-28T09:01:59Z'
  edited_at: '2026-08-18T00:14:33Z'
  id: 360019614017
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/360019614017
---
> **Visão geral:** meça a qualidade dos seus usuários durante toda a jornada de usuário gravando esses eventos in-app sugeridos para seu aplicativo de empréstimo P2P (peer-to-peer).

<div id="-p2p-lending" />

## <Image alt="InApp_Events_lending.png" src="https://files.readme.io/e3465ee913a65a215f1c224db20d4f1fd61fd0bf488b798073c94b4e8387d252-20659507679889.png" width="100px" /> Empréstimo P2P

O empréstimo P2P é uma maneira para que pessoas e empresas peçam e forneçam empréstimos umas às outras. Os eventos típicos que sugerimos que você grave são as atividades de credores e mutuários individuais, os tipos de empréstimos que as pessoas oferecem, e taxas de aceitação e rejeição de empréstimos.

Os dados que você reunir com a gravação de eventos podem destacar mutuários confiáveis e oferecer a eles melhores taxas de juros. Da mesma maneira, você pode identificar os credores mais ativos e oferecer a eles taxas mais baixas. Além do mais, após saber quais tipos de empréstimos são mais populares entre seus usuários, é possível lançar campanhas de marketing que atinjam esses públicos.

<div id="important" />

> 🚧 **Importante!**
>
> * Certifique-se de ler as <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#configurando-eventos-in-app">instruções</Anchor> para os profissionais de marketing sobre a implementação de eventos in-app.
> * Para agilizar o processo de implementação, use nosso <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=p2p_lending">gerador de eventos in-app</Anchor>. Essa ferramenta inclui todos os eventos in-app típicos descritos neste artigo e permite que você modifique os eventos de acordo com as necessidades da sua empresa. Depois de concluído, compartilhe o arquivo com seu desenvolvedor.
> * Para cada evento recomendado incluído neste artigo, há <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=p2p_lending&view=code">exemplos de código</Anchor> para desenvolvedores do iOS, Android e Unity.
> * Instruções detalhadas para o seu desenvolvedor podem ser encontradas no **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">developer hub (hub para desenvolvedores) da AppsFlyer</Anchor>.**
>
> Para mais informações sobre como gravar eventos in-app, consulte o <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">guia Eventos avançados dentro do aplicativo</Anchor>.

[![Fluxograma_para_eventos_recomendados_jornada_do_usuário_do_aplicativo_de_empréstimo_P2P](https://files.readme.io/597a98cf1df450e9e14eb32d8bdc14df647551ca91a2baca78895ca740eb805c-360020063617.png)](https://files.readme.io/597a98cf1df450e9e14eb32d8bdc14df647551ca91a2baca78895ca740eb805c-360020063617.png)

<div id="recommended-structures-for-predefined-events" />

## Estruturas recomendadas para eventos predefinidos

A seção a seguir oferece uma lista de estruturas de eventos que são típicas da vertical de empréstimo P2P. Cada estrutura inclui um nome de evento predefinido e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Propósito**

Determine quantos usuários realmente verificam a identidade após o registro. É possível atribuir esses usuários a campanhas e identificar quais campanhas geram usuários ativos.

**Trigger**

Quando o registro do usuário é aprovado

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_registration\_method | O tipo de método de cadastro | email, facebook |

</Accordion>

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Propósito**

Entenda a retenção de seus usuários registrados

**Trigger**

Quando o usuário faz login com sucesso

**Parâmetros do evento**

Pode ser enviado sem nenhum parâmetro adicional

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estruturas recomendadas para eventos personalizados

A seção a seguir fornece uma lista de estruturas de eventos que incluem nomes de eventos personalizados e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="registration-submitted-registration_submitted" />

<Accordion title="Registro enviado (registration_submitted)">

**Propósito**

Como o empréstimo P2P está suscetível a abusos, os usuários devem verificar suas identidades. Tal verificação é realizada através do envio de uma solicitação de cadastro. Esse evento pode ajudar a:

* Determinar quantos usuários se registraram, mas nunca verificam sua conta
* Ver a correlação entre os métodos de registro - como e-mail, Facebook, Google - e as taxas de verificação

**Gatilho**

Depois de o usuário enviar uma solicitação para registrar

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_registration\_method | O tipo de método de cadastro | email, facebook |

</Accordion>

<div id="fill-loan-form-fill_loan_form_form_name" />

<Accordion title="Preencher formulário de empréstimo (&lt;fill_loan_form_ FORM_NAME>)">

**Propósito**

Determinar a taxa de abandono e redirecionar mutuários que não concluem suas solicitações de empréstimo.

Observe que ao enviar esse evento, é preciso incluir o nome do formulário no nome do evento.

**Trigger**

Quando um mutuário envia um formulário

**Parâmetros do evento**

Pode ser enviado sem nenhum parâmetro adicional

<div id="note" />

> 📘 **Nota**
>
> É altamente recomendável associar empréstimos com credores. Para isso, não se esqueça de definir o ID de usuário do cliente. <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">Definir o ID de usuário do cliente</Anchor> é a sua maneira de fazer a correspondência entre os credores e os usuários do aplicativo conforme eles aparecem na AppsFlyer. Ao definir o ID de usuário do cliente, você garante que qualquer evento seja enviado com o ID de usuário do cliente.

<div id="submit-loan-application-submit_loan_application" />

<Accordion title="Enviar pedido de empréstimo (submit_loan_application)">

**Propósito**

Esse evento pode ajudar a:

* Determinar o número geral de solicitações de empréstimo em seu aplicativo
* Saber o valor máximo, mínimo e médio em pedidos de empréstimo
* Determinar o tipo de empréstimos que as pessoas solicitam

**Trigger**

Quando o usuário envia com sucesso um pedido de empréstimo

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| loan\_id | ID do empréstimo | 1735102 |
| loan\_amount | Montante solicitado | 1000 |
| tipo\_de\_empréstimo | Período de empréstimo | 3 months |

</Accordion>

<div id="loan-form-loan_form" />

<Accordion title="Formulário de empréstimo (loan_form)">

**Propósito**

Analisar pedidos de empréstimo enviados pelos mutuários

**Trigger**

Quando o mutuário envia com sucesso um pedido de empréstimo

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| loan\_id | ID do empréstimo | 1735102 |
| loan\_amount | Montante solicitado | 1000 |
| tipo\_de\_empréstimo | Período de empréstimo | 3 months |

</Accordion>

<div id="submit-credit-check-submit_credit_check" />

<Accordion title="Enviar verificação de crédito (submit_credit_check)">

**Propósito**

Verificar o histórico financeiro do mutuário (por exemplo, crédito passado, hábitos de pagamento e tipos de empréstimos) para avaliar o nível de risco.

**Trigger**

Depois que o credor recebe um pedido de empréstimo

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| loan\_id | ID do empréstimo | 1735102 |
| loan\_amount | Montante solicitado | 1000 |
| tipo\_de\_empréstimo | Período de empréstimo | 3 months |

</Accordion>

<div id="loan-accepted-loan_accepted" />

<Accordion title="Empréstimo aceito (loan_accepted)">

**Propósito**

Saber mais sobre tendências em empréstimos e outras métricas. Esse evento pode ajudar a determinar:

* Que tipo de empréstimos são aceitos
* O valor solicitado nos empréstimos que são aprovados
* Quais credores aceitam mais empréstimos

**Trigger**

Quando um empréstimo é aceito

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| loan\_id | ID do empréstimo | 1735102 |
| loan\_amount | Montante solicitado | 1000 |
| tipo\_de\_empréstimo | Período de empréstimo | 3 months |

</Accordion>

<div id="loan-rejected-loan_rejected" />

<Accordion title="Empréstimo rejeitado (loan_rejected)">

**Propósito**

Entender as razões pelas quais os empréstimos são rejeitados. É possível ver a correlação entre o valor e o período do empréstimo e os índices de rejeição. Também é possível redirecionar os usuários que tiveram seus empréstimos negados e sugerir que emprestem um valor menor.

**Trigger**

Quando um credor rejeita um empréstimo

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| loan\_id | ID do empréstimo | 1735102 |

</Accordion>

<div id="payment-payment" />

<Accordion title="Pagamento (pagamento)">

**Propósito**

Ajuda você a marcar os mutuários como confiáveis. Mutuários confiáveis são aqueles que cumprem sua obrigação de cobrir seus empréstimos. É possível atribuir mutuários a campanhas e saber quais campanhas geram mutuários confiáveis. Com o registro deste evento também é possível reunir dados com relação aos valores de pagamentos mínimos, máximos e médios.

**Trigger**

Quando um mutuário faz um pagamento do seu empréstimo

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| loan\_id | ID do empréstimo | 1735102 |
| payment\_amount | Valor pago | 100 |
| id\_do\_pagamento | ID do pagamento | AE12SF |

</Accordion>

<div id="payment-completed-payment_completed" />

<Accordion title="Pagamento concluído (payment_completed)">

**Propósito**

Destaca os mutuários que cumprem com sua obrigação de quitar um empréstimo. Você também pode redirecionar esses mutuários e oferecer a eles taxas de juros mais baixas e outras promoções.

**Trigger**

Quando um empréstimo é totalmente quitado

**Parâmetros do evento**

| Nome do campo | Descrição | Valor de exemplo |
| --- | --- | --- |
| loan\_id | ID do empréstimo | 1735102 |

</Accordion>

<div id="payment-received-payment_received" />

<Accordion title="Pagamento recebido (payment_received)">

**Propósito**

Verificar se o mutuário faz os pagamentos do empréstimo de acordo com os termos do contrato do empréstimo.

**Trigger**

Quando um mutuário faz um pagamento do seu empréstimo

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| loan\_id | ID do empréstimo | 1735102 |
| payment\_amount | Valor pago | 100 |
| id\_do\_pagamento | ID do pagamento | AE12SF |

</Accordion>

</Accordion>

<div data-zendesk-anchors="p2p-lending=-empr%C3%A9stimo-p2p h_01HGTAY6DHKXCTP52P2EPHXN5H=-empr%C3%A9stimo-p2p h_01HGTAY6DHDDG3MVCXEM705MTK=importante recommended-structures-for-predefined-events=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAY6DH1V6S5NKJEFCVW1PF=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAY6DHHGW3M6NQ0K3J6HTC=complete-registration-af_complete_registration h_01HGTAY6DHZTKJR94T8B6WEYZ6=login-af_login recommended-structures-for-custom-events=estruturas-recomendadas-para-eventos-personalizados h_01HGTAY6DH00660DSP5RX3PA9C=estruturas-recomendadas-para-eventos-personalizados h_01HGTAY6DHETK285KPGW54YV5Z=registration-submitted-registration_submitted h_01HGTAY6DHCQKWMG4YRZDHBMZT=fill-loan-form-fill_loan_form_form_name h_01HGTAY6DHHNJ9EKV3FQ6BKKBF=nota h_01HGTAY6DH4D6NV1NHV5717CDH=submit-loan-application-submit_loan_application h_01HGTAY6DHVWFEFJYB4TGK1B9W=loan-form-loan_form h_01HGTAY6DH7V1JSPCDHDTFR4YA=submit-credit-check-submit_credit_check h_01HGTAY6DH22HRQQJ5NQ2T71QM=loan-accepted-loan_accepted h_01HGTAY6DHTMJ22KQSXHNBJ8B3=loan-rejected-loan_rejected h_01HGTAY6DHD8A2H61XKFPXW589=payment-payment h_01HGTAY6DJWJDQBW52RPG7W7P4=payment-completed-payment_completed h_01HGTAY6DJE0K3VC0YNVWAXT29=payment-received-payment_received" />
