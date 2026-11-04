---
title: Eventos recomendados para apostas esportivas
metadata:
  keywords:
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
  created_at: '2021-11-11T13:24:45Z'
  edited_at: '2026-08-18T00:14:39Z'
  id: 4410672219025
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/4410672219025
---
> **Visão geral:** Meça a qualidade dos seus usuários ao longo da jornada do usuário registrando estes eventos in-app sugeridos para seu aplicativo de apostas esportivas.

<div id="-sports-betting" />

## <Image alt="soccer_ball.png" src="https://files.readme.io/2c5150b2c50ec166878cd976154dc81c0dc8a1e710fa8869aa582b535313b464-4413968925585.png" width="71px" /> Apostas esportivas

Os aplicativos de apostas esportivas permitem que os apostadores façam apostas em diversos mercados esportivos. Os eventos típicos que sugerimos registrar são depósitos, apostas realizadas e saques.

Registrar eventos pode ajudar a determinar:

* Qualidade dos usuários do seu aplicativo
* Quão engajados são os usuários
* Receita gerada por meio das apostas
* Que tipos de apostas geram a menor ou a maior receita

<div id="important" />

> 🚧 **Importante!**
>
> * Certifique-se de ler <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#configurando-eventos-in-app">as instruções</Anchor> para os profissionais de marketing sobre a implementação de eventos in-app.
> * (Em breve) Para agilizar o processo de implementação, use nosso <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming">gerador de eventos in-app</Anchor>. Essa ferramenta inclui todos os eventos in-app típicos descritos neste artigo e permite que você modifique os eventos de acordo com as necessidades da sua empresa. Depois de concluído, compartilhe o arquivo com seu desenvolvedor.
> * Para cada evento recomendado incluído neste artigo, há <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming&view=code">exemplos de código</Anchor> para desenvolvedores do iOS, Android e Unity.
> * Instruções detalhadas para o desenvolvedor podem ser encontradas no **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub para desenvolvedores da AppsFlyer</Anchor>.**
>
> Para mais informações sobre como gravar eventos in-app, consulte o <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">guia Eventos avançados dentro do aplicativo</Anchor>.

[![In_appEvents_UserJourneys_-_Sports_betting__5_.png](https://files.readme.io/7a47ba917ebc5a6e661efb23b078675c16ce43c59c41f9c6fd6fd89d37c242bf-4424606611473.png)](https://files.readme.io/7a47ba917ebc5a6e661efb23b078675c16ce43c59c41f9c6fd6fd89d37c242bf-4424606611473.png)

<div id="recommended-structures-for-predefined-events" />

## Estruturas recomendadas para eventos predefinidos

A seção a seguir oferece uma lista de estruturas de eventos típicas da vertical de apostas esportivas. Cada estrutura inclui um nome de evento predefinido e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Propósito**

Entenda a retenção de seus usuários cadastrados

**Trigger**

Sempre que o usuário fizer login com sucesso

**Parâmetros do evento**

Pode ser enviado sem nenhum parâmetro adicional

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Cadastro completo (af_complete_registration)">

**Propósito**

Saiba quantos usuários instalaram o aplicativo e concluíram o processo de inscrição e quais métodos de inscrição seus usuários preferem.

**Trigger**

Quando o usuário conclui o processo de cadastro e o registro é confirmado pelo aplicativo (sem erros).

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_registration\_method | O tipo de método de cadastro | email, facebook |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estruturas recomendadas para eventos personalizados

A seção a seguir fornece uma lista de estruturas de eventos que incluem nomes de eventos personalizados e os parâmetros de eventos sugeridos para usar. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="first-time-deposit-first_time_deposit" />

<Accordion title="Primeiro depósito (first_time_deposit)">

**Propósito**

Gravar esse evento pode ajudar a determinar:

* Quando os usuários fazem um primeiro depósito
* Receita gerada por depósitos pela primeira vez

Além disso, parceiros de ad network podem otimizar suas campanhas de publicidade com a segmentação de usuários que fizeram um primeiro depósito.

**Trigger**

Primeira vez que o usuário faz um depósito na conta de apostas

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Valor monetário do depósito realizado | 200 |
| af\_currency | Moeda em que o depósito foi realizado | AUD |

</Accordion>

<div id="deposit-deposit" />

<Accordion title="Depósito (deposit)">

**Propósito**

Determine o valor dos depósitos feitos pelos seus usuários.

**Trigger**

Depósito subsequente que o usuário faz após o primeiro depósito

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Valor monetário do depósito realizado | 200 |
| af\_currency | Moeda em que o depósito foi realizado | AUD |

</Accordion>

<div id="placed-bet-placed_bet" />

<Accordion title="Aposta realizada (placed_bet)">

**Objetivo**

Saiba quais eventos geram menos receita e quais geram mais.

**Trigger**

Quando uma aposta é feita com sucesso

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Valor monetário da aposta feita | 100 |
| af\_currency | Moeda em que a aposta foi feita | AUD |
| event\_number | Identificador único do evento em que a aposta foi feita | 123789 |
| event\_date | Data do evento em que a aposta foi feita | 13122021 |
| event\_time | Horário do evento em que a aposta foi feita | 17:30 |
| transaction\_id | ID da aposta realizada | 221 |

</Accordion>

<div id="withdrawal-withdrawal" />

<Accordion title="Saque (saque)">

**Objetivo**

Saiba quando os usuários sacam dinheiro que depositaram anteriormente na conta de apostas.

**Trigger**

Quando um usuário saca dinheiro da conta de apostas

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Valor monetário do saque. Registre como um valor de receita negativo. | -100 |
| af\_currency | Moeda que foi sacada | AUD |

</Accordion>

<div id="bonus-bet-bonus_bet" />

<Accordion title="Aposta bônus (bonus_bet)">

**Objetivo**

As apostas bônus são apostas opcionais que os proprietários de aplicativos podem usar para recompensar apostadores como incentivo de cadastro ou depósito, ou como promoção para fazer um determinado tipo de aposta.

Registrar esse evento ajuda você a determinar o valor total das apostas bônus concedidas aos usuários e o número de usuários que fizeram uma aposta bônus.

**Trigger**

Quando uma aposta é feita com sucesso

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Valor monetário da aposta feita | 100 |
| af\_currency | Moeda em que a aposta foi feita | AUD |
| event\_number | Identificador único do evento em que a aposta foi feita | 123789 |
| event\_date | Data do evento em que a aposta foi feita | 13122021 |
| event\_time | Horário do evento em que a aposta foi feita | 17:30 |
| bonus\_id | ID da aposta de bônus | 221 |

</Accordion>

<div id="cancels-bet-canceled_bet" />

<Accordion title="Cancela aposta (canceled_bet)">

**Objetivo**

Esse evento pode ajudar a:

* Registrar usuários que cancelam apostas constantemente
* Saber quantas apostas foram canceladas
* Saber os motivos do cancelamento de uma aposta

**Trigger**

Quando o usuário cancela uma aposta

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Valor monetário da aposta realizada | 100 |
| af\_currency | Moeda em que a aposta foi realizada | AUD |
| event\_number | Identificador exclusivo do evento em que a aposta foi realizada | 123789 |
| event\_date | Data do evento em que a aposta foi realizada | 13122021 |
| event\_time | Hora do evento em que a aposta foi realizada | 17:30 |

</Accordion>

<div id="account-deducted-account_deducted" />

<Accordion title="Conta debitada (account_deducted)">

**Objetivo**

Registrar e gravar débitos nas contas dos usuários

**Trigger**

Quando uma aposta é perdida

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Valor monetário da aposta realizada | 100 |
| af\_currency | Moeda em que a aposta foi realizada | AUD |
| account\_number | Identificador exclusivo da conta do usuário | 15780 |
| event\_number | Identificador exclusivo do evento em que a aposta foi realizada | 123789 |
| event\_date | Data do evento em que a aposta foi realizada | 13122021 |
| event\_time | Hora do evento em que a aposta foi realizada | 17:30 |

</Accordion>

<div id="account-credited-account_credited" />

<Accordion title="Conta creditada (account_credited)">

**Propósito**

Registrar e gravar créditos nas contas dos usuários

**Trigger**

Quando uma aposta é ganha

**Parâmetros do evento**

| YouTube video player | A descrição | Valor de exemplo |
| --- | --- | --- |
| af\_preço | Valor monetário da aposta feita | 100 |
| af\_currency | Moeda em que a aposta foi feita | AUD |
| account\_number | Identificador exclusivo da conta do usuário | 15780 |
| event\_number | Identificador exclusivo do evento em que a aposta foi feita | 123789 |
| event\_date | Data do evento em que a aposta foi feita | 13122021 |
| event\_time | Hora do evento em que a aposta foi feita | 17:30 |

</Accordion>

<div data-zendesk-anchors="sports-betting=-apostas-esportivas h_01HGTAE0AT9KD9RKX7XPR7A4AT=-apostas-esportivas h_01HGTAE0ATTMEART2R1BD1ZDSB=importante recommended-structures-for-predefined-events=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAE0ATYW0RDDZZD5EAR7BZ=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAE0ATMBJVKS14SGWGK0DG=login-af_login h_01HGTAE0ATHZWSM0R9A6R9BV96=complete-registration-af_complete_registration recommended-structures-for-custom-events=estruturas-recomendadas-para-eventos-personalizados h_01HGTAE0ATJQDWWBB8D836QRJ5=estruturas-recomendadas-para-eventos-personalizados h_01HGTAE0AT3ZBH5G16QJW4MGQ1=first-time-deposit-first_time_deposit h_01HGTAE0ATTRCNX1Y4AFJ8VGWC=deposit-deposit h_01HGTAE0ATNW97Y8WJWWXTXX7V=placed-bet-placed_bet h_01HGTAE0ATPB6KHMHHBW7T9B0Q=withdrawal-withdrawal h_01HGTAE0ATGS9VS7QY1974XAPY=bonus-bet-bonus_bet h_01HGTAE0AVKKGGJCB9WWXMWT0D=cancels-bet-canceled_bet h_01HGTAE0AVMB59TDT6AM65DE94=account-deducted-account_deducted h_01HGTAE0AVXMY0J983V9NTYQ2J=account-credited-account_credited" />
