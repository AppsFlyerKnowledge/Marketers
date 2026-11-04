---
title: Eventos recomendados para aplicativos financeiros e de serviços bancários
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
  created_at: '2021-04-27T12:58:44Z'
  edited_at: '2026-08-18T00:14:12Z'
  id: 360019598337
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/360019598337
---
> **Visão geral:** mensure a qualidade dos seus usuários durante toda a jornada do usuário, registrando esses eventos in-app sugeridos para seu aplicativo de finanças e serviços bancários.

<div id="-finance-and-banking" />

## <Image alt="banking.png" src="https://files.readme.io/260638f807a43f42c6ff99bb72b8d4113b2df09436b9322a820888ad3f8a01ae-20659476893969.png" width="100px" /> Finanças e serviços bancários

Aplicativos financeiros e de serviços bancários oferecem aos usuários a capacidade de realizar uma ampla gama de ações relacionadas a finanças, como solicitar novos cartões de crédito ou empréstimos. Os eventos típicos que sugerimos que você registre incluem aberturas de conta e solicitações de cartão de crédito, assim como empréstimos.

Gravar esse evento pode ajudar a determinar:

* Que tipo de conta os usuários mais querem, oferecendo ideias para retargeting
* Quais benefícios os usuários procuram em um cartão de crédito
* Quais usuários precisam de assistência financeira e quanta assistência eles exigem

<div id="important" />

> 🚧 **Importante!**
>
> * **Uma nota de nossos advogados**: dados de saúde são considerados "Dados restritos" e são considerado uma categoria especial de dados em muitas jurisdições. Como tal, os clientes estão proibidos de enviar à AppsFlyer quaisquer desses dados.
> * Certifique-se de ler as <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#configurando-eventos-in-app">instruções</Anchor> para os profissionais de marketing sobre a implementação de eventos in-app.
> * Para agilizar o processo de implementação, use nosso <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=finance_banking">gerador de eventos in-app</Anchor>. Essa ferramenta inclui todos os eventos in-app típicos descritos neste artigo e permite que você modifique os eventos de acordo com as necessidades da sua empresa. Depois de concluído, compartilhe o arquivo com seu desenvolvedor.
> * Para cada evento recomendado incluído neste artigo, há <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=finance_banking&view=code">exemplos de código</Anchor> para desenvolvedores do iOS, Android e Unity.
> * Instruções detalhadas para o seu desenvolvedor podem ser encontradas no **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">developer hub (hub para desenvolvedores) da AppsFlyer</Anchor>.**
>
> Para mais informações sobre como gravar eventos in-app, consulte o <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">guia Eventos avançados dentro do aplicativo</Anchor>.

[![Fluxograma_para_eventos_recomendados jornada_do_utilizador_da_aplicação_de_finanças_bancárias](https://files.readme.io/722d2a3df606df1c61f86c7e8e1524566de8fbfd0ceb48e4cd5913a0b3ac9283-360020063337.png)](https://files.readme.io/722d2a3df606df1c61f86c7e8e1524566de8fbfd0ceb48e4cd5913a0b3ac9283-360020063337.png)

<div id="recommended-structures-for-predefined-events" />

## Estruturas recomendadas para eventos predefinidos

A seção a seguir oferece uma lista de estruturas de eventos típicas da vertical de finanças e bancos. Cada estrutura inclui um nome de evento predefinido e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Propósito**

Entenda a retenção de seus usuários registrados

**Gatilho**

Quando o usuário faz login com sucesso

**Parâmetros do evento**

Pode ser enviado sem nenhum parâmetro adicional

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Propósito**

Saiba quantos usuários instalaram o aplicativo e concluíram o processo de inscrição e quais métodos de inscrição seus usuários preferem

**Gatilho**

Quando o usuário conclui o processo de inscrição

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_registration\_method | O tipo de método de cadastro | email, facebook |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estruturas recomendadas para eventos personalizados

A seção a seguir fornece uma lista de estruturas de eventos que incluem nomes de eventos personalizados e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="registration-verified-registration_verified" />

<Accordion title="Registro verificado (registration_verified)">

**Propósito**

Gravar esse evento e compará-lo com outros dados para saber mais sobre seus usuários. Por exemplo, você pode saber quantos usuários solicitam um cadastro, mas não são aceitos. 

**Trigger**

Quando o cadastro é verificado

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| submit\_registration | Tipo de método de cadastro verificado. Não insira informações pessoais identificáveis (PII). | email, facebook |

</Accordion>

<div id="submit-account-application-submit_account_application" />

<Accordion title="Enviar solicitação de conta (submit_account_application)">

**Propósito**

Gravar esse evento e compará-lo com outros dados para saber mais sobre seus usuários. Por exemplo, você pode saber quantos usuários se inscrevem, mas não solicitam uma abertura de conta.

**Trigger**

Quando o usuário conclui o processo de solicitação de conta

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| account\_type | O tipo de conta solicitada | poupança |
| application\_method | Onde a solicitação foi feita | aplicativo |
| PII\_type | Tipo de ID usado durante a solicitação | passaporte |

</Accordion>

<div id="open-account-success-open_account_success" />

<Accordion title="Sucesso na abertura da conta (open_account_success)">

**Propósito**

Gravar esse evento e compará-lo com outros dados para saber mais sobre seus usuários. Por exemplo, você pode saber quantos usuários solicitam contas e são aceitos, e assim tentar melhorar o funil ou fazer o retargeting desses usuários mais tarde.

**Trigger**

Quando a solicitação do usuário é aceita e a conta é aberta

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| account\_type | Tipo de conta aberta | poupança |
| application\_method | Onde a solicitação foi feita | aplicativo |
| PII\_type | Tipo de ID usado durante a solicitação | documento de identidade |

</Accordion>

<div id="open-account-rejected-open_account_rejected" />

<Accordion title="Abertura de conta rejeitada (open_account_rejected)">

**Propósito**

Gravar esse evento e compará-lo com outros dados para saber mais sobre seus usuários. Por exemplo, você pode saber quantos usuários solicitam contas mas são aceitos, e assim tentar melhorar o funil ou fazer o retargeting desses usuários mais tarde.

**Gatilho**

Quando o usuário conclui o processo de inscrição

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| account\_type | O tipo de conta solicitada | poupança |

</Accordion>

<div data-zendesk-anchors="finance-and-banking=-finan%C3%A7as-e-servi%C3%A7os-banc%C3%A1rios h_01HGTAXN8PV7TPNRBWD593BR4K=-finan%C3%A7as-e-servi%C3%A7os-banc%C3%A1rios h_01HGTAXN8Q652HG7412X583KWX=importante recommended-structures-for-predefined-events=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAXN8QWEWD86FMF6GEZNZD=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAXN8Q3K0EFGXZ41XZH438=login-af_login h_01HGTAXN8Q6KFDPB8XSVT3F9E8=complete-registration-af_complete_registration recommended-structures-for-custom-events=estruturas-recomendadas-para-eventos-personalizados h_01HGTAXN8Q47F6CXXBEVCDPSBA=estruturas-recomendadas-para-eventos-personalizados h_01HGTAXN8QB911JMER3EV7RGTM=registration-verified-registration_verified h_01HGTAXN8QCYR0BQ3Q3VN0EQ9X=submit-account-application-submit_account_application h_01HGTAXN8QJ4DKQS2FY9KY0AX4=open-account-success-open_account_success h_01HGTAXN8QK1P5QYEN5SNBQ5ED=open-account-rejected-open_account_rejected" />
