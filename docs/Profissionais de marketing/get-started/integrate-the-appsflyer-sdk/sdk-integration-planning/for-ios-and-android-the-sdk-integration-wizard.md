---
title: 'Para iOS e Android: o assistente de integração do SDK'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2024-04-10T12:17:00Z'
  edited_at: '2026-08-18T00:15:51Z'
  id: 24073235369617
  locale: pt
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/pt/articles/24073235369617
---
> **At a glance:** Crie e teste automaticamente o código de integração do seu SDK.

## Sobre o assistente de integração do SDK

Deixe nosso <Anchor target="_blank" href="https://dj.dev.appsflyer.com/?sourceos=android&utm_source=kb&utm_medium=sdk-int-wizard-orvw">assistente de integração do SDK</Anchor> orientar o desenvolvedor do aplicativo durante o processo de integração do SDK. O desenvolvedor do aplicativo só precisa fornecer algumas credenciais e opções de personalização, e o assistente gera trechos de código para serem copiados e colados no projeto.

Este artigo permite que você colete e envie ao desenvolvedor do aplicativo todas as entradas e credenciais exigidas pelos fluxos do assistente de integração. Há duas jornadas de desenvolvedores compatíveis com o assistente:

* [A jornada do desenvolvedor de instalação e integração](#o-fluxo-de-instalação-e-integração): o assistente ajuda o desenvolvedor desde a instalação até o teste bem-sucedido da integração.
* [A jornada do desenvolvedor de eventos in-app](#o-fluxo-de-adição-de-eventos-in-app): o assistente orienta o desenvolvedor desde a definição de eventos in-app até o teste bem-sucedido da transmissão para a AppsFlyer.

## O fluxo de instalação e integração

Depois que o desenvolvedor do aplicativo concluir com sucesso a instalação e a configuração usando o Assistente de Integração, o SDK da AppsFlyer estará pronto para começar a enviar dados de atribuição. Para verificar se a integração foi bem-sucedida, o fluxo inclui um teste que verifica se um "evento de instalação" é reportado corretamente à AppsFlyer após a instalação do aplicativo.

A tabela abaixo lista as perguntas que os desenvolvedores precisam responder durante a configuração do assistente. Use as instruções especificadas na tabela para coletar as informações necessárias e fornecê-las aos desenvolvedores.

| Perguntas | Descubra já |
| --- | --- |
| Qual é o ID do seu aplicativo? (É obrigatório) | <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer#insira-detalhes-do-aplicativo">Saiba como obter o ID do aplicativo em cada loja.</Anchor> |
| Qual é a sua chave de desenvolvedor da AppsFlyer (obrigatória) | <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#recuperar-a-dev-key">Saiba como obter a Dev Key.</Anchor> |
| Qual modo do SDK você gostaria de integrar? Padrão ou estrito? | <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#strictmode-sdk">Saiba mais sobre os modos do SDK</Anchor>. |
| O SDK deve receber dados de conversão? | <Anchor target="_blank" href="/marketers/pt/docs/get-conversion-data-using-appsflyer-sdk-overview">Saiba mais sobre dados de conversão no SDK</Anchor>. |
| O SDK deve receber a confirmação de que foi iniciado com sucesso? | Saiba mais sobre o método de inicialização do SDK com um completion handler ([Android](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#starting-with-a-response-listener), [iOS](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#start-with-completion-handler)). |
| O SDK deve oferecer suporte ao App Tracking Transparency (ATT)? | <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">Saiba mais sobre ATT</Anchor>. |
| Qual é o seu token de autenticação v2 da AppsFlyer? (Obrigatório apenas se você seguir o fluxo de teste automático.) | <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens#acessando-a-página-de-tokens">Saiba como recuperar seu token v2</Anchor>. |

## O fluxo de adição de eventos in-app

Depois que o desenvolvedor do aplicativo concluir o assistente de instalação e integração, o SDK da AppsFlyer será integrado ao seu aplicativo com sucesso. O fluxo inclui um teste de evento in-app que confirma que a AppsFlyer recebeu o evento quando seu aplicativo é instalado.

A tabela abaixo lista as perguntas que os desenvolvedores precisam responder durante a configuração do assistente. Use as instruções especificadas na tabela para coletar as informações necessárias e fornecê-las aos desenvolvedores.

| Perguntas | Descubra já |
| --- | --- |
| Escolha o nome do evento e os parâmetros dele | <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer#insira-detalhes-do-aplicativo">Saiba quais eventos predefinidos estão disponíveis para você.</Anchor> A descrição de cada evento inclui seus parâmetros de evento típicos.  <br />Como alternativa, você pode usar nosso   <br />[gerador de eventos in-app](https://evgen.appsflyer.com/). |
| O SDK deve receber a confirmação de que o evento in-app foi recebido pela AppsFlyer? | Saiba mais sobre o código que verifica se os eventos foram recebidos com sucesso na AppsFlyer (<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-android#handling-event-submission-success-and-failure">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-ios#handling-event-submission-success-and-failure">iOS</Anchor>). |
| Qual é o seu token de autenticação v2 da AppsFlyer? (Obrigatório apenas se você seguir o fluxo de teste automático.) | <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens#acessando-a-página-de-tokens">Saiba como recuperar seu token v2</Anchor>. |

## Especificações e limitações

| Caraterística | Considerações |
| --- | --- |
| Plano Zero | O assistente de integração do SDK não está incluído no <Anchor target="_blank" href="/marketers/pt/docs/account-management-plans-payments-and-billing#appsflyer-plans">plano Zero</Anchor>. |

<div data-zendesk-anchors="about-the-sdk-integration-wizard=sobre-o-assistente-de-integra%C3%A7%C3%A3o-do-sdk h_01J6730Y7WE1AJXNXFZ0QX23T8=sobre-o-assistente-de-integra%C3%A7%C3%A3o-do-sdk the-installation-and-integration-flow=o-fluxo-de-instala%C3%A7%C3%A3o-e-integra%C3%A7%C3%A3o h_01J5K2A8BZS9CTZA45FB5VX8C0=o-fluxo-de-instala%C3%A7%C3%A3o-e-integra%C3%A7%C3%A3o the-add-in-app-event-flow=o-fluxo-de-adi%C3%A7%C3%A3o-de-eventos-in-app h_01J5K2CG0H1G0BCSWHBJ8DPQWA=o-fluxo-de-adi%C3%A7%C3%A3o-de-eventos-in-app traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01J6S6HS0H0M6GQ81WGZ3XT0P9=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es" />
