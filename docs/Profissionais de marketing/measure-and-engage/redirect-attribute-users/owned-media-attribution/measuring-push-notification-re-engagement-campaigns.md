---
title: Medindo campanhas de reengajamento por notificação push
metadata:
  keywords:
    - Re-Engagement
    - push
    - notifications
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2016-01-18T10:03:11Z'
  edited_at: '2026-11-02T01:17:04Z'
  id: 207364076
  locale: pt
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/pt/articles/207364076
---
> **At a glance:** **Visão geral:** meça campanhas de notificação push tanto no iOS quanto no Android.

<div id="overview" />

## Visão geral

A AppsFlyer tem compatibilidade com a métrica de campanhas de notificação push de todos os fornecedores de push, além de campanhas implementadas diretamente sobre o Firebase Cloud Messaging ou Apple Push Notification Services (APNS).

Há 2 maneiras possíveis de implementar a integração:

* Usando templates do OneLink (recomendado).
* Ao enviar um objeto JSON com uma chave `af` no payload da notificação push.

As conversões são exibidas no painel de visão geral, na visualização de retargeting ou unificada.

<div id="how-does-it-work" />

## Como ela funciona?

Uma vez concluídas as etapas deste artigo, seu aplicativo funcionará da seguinte forma:

1. Você aciona uma notificação push que contém um template do OneLink **ou** uma chave `af` em seu payload.
2. O usuário do aplicativo recebe a notificação push e clica nela.
3. O aplicativo carrega e o SDK da AppsFlyer inicia.
4. O SDK processa o payload da notificação push que abriu o aplicativo.
5. O SDK extrai e envia os dados de atribuição para a AppsFlyer.

No cenário OneLink, se o OneLink for configurado para encaminhar o usuário para um local específico no aplicativo, o fluxo do deep link é acionado.

<div id="prerequisites" />

## Pré-requisitos

Antes de continuar, certifique-se de que seu aplicativo tem <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide">o SDK da AppsFlyer integrado</Anchor> **e** pode receber notificações push.

<div id="steps" />

## Etapas

Para configurar a métrica de notificação por push, as seguintes etapas devem ser concluídas:

1. [Criar uma notificação push](/docs/measuring-push-notification-re-engagement-campaigns#1-creating-the-push-notification) que contenha uma chave de dados personalizada com o template OneLink **ou** uma chave `af` com um objeto JSON como seu valor.
2. [Configurar o SDK para resolver a chave personalizada](/docs/measuring-push-notification-re-engagement-campaigns#2-configuring-the-sdk) (feito pelo desenvolvedor do aplicativo).
3. [Testar a integração](/docs/measuring-push-notification-re-engagement-campaigns#3-testing-the-integration) acionando uma notificação push.
4. [Veja o desempenho das campanhas de notificação push](/docs/measuring-push-notification-re-engagement-campaigns#4-viewing-push-notification-campaigns-in-the-dashboard) no painel.

<Accordion title="1. Criando a notificação push">

Primeiro, crie uma notificação push que contenha dados de atribuição usando um dos seguintes métodos.

> 📘 **Note**
>
> **Importante!**
>
> Na demonstração a seguir, estamos usando Firebase como o fornecedor de push. As instruções devem ser aplicáveis a qualquer fornecedor de push, com pequenas diferenças (se houver). Consulte a documentação do respectivo fornecedor de push.

<Tabs>
<Tab title="Usando OneLink (recomendado)">

<div id="using-json-legacy" />

<div id="using-onelink-recommended" />

#### **Usando OneLink (recomendado)**

Este é o método recomendado para integrar a AppsFlyer com notificações push.

1. Crie um <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">link do OneLink e configure-o para retargeting.</Anchor>  
    **Atenção**: URLs curtas e longas do OneLink são compatíveis.
2. Nos dados personalizados da notificação push, adicione o OneLink que contém os dados de atribuição que você deseja enviar à AppsFlyer.

> 📘 **Note**
>
> **Exemplo do Firebase**
>
> Em Firebase:
>
>  ![appsflyer-push-custom-data-firebase.png](https://files.readme.io/b2a753e8ec88ef0d0e0a71fe222a8ecc4f03786297696d150f185720b8f4e248-49839256715025.png)

</Tab>

<Tab title="Usar JSON">

<div id="using-json" />

#### **Usar JSON**

> 📘 **Note**
>
> **Importante!**
>
> O texto a seguir documenta o método baseado em JSON para integrar a AppsFlyer com notificações push e está disponível para fins de compatibilidade com versões anteriores. Se você estiver configurando um novo aplicativo, use a [solução recomendada baseada no OneLink](/docs/measuring-push-notification-re-engagement-campaigns#usando-onelink-recomendado).

Nos dados personalizados da notificação push, adicione uma chave personalizada chamada `af` que contenha os dados de atribuição que você deseja enviar à AppsFlyer no formato JSON. Os seguintes parâmetros de atribuição são necessários:

* `pid`
* `is_retargeting`
* `C`

> 📘 **Note**
>
> **Exemplo do Firebase**
>
> Em Firebase:
>
>  ![appsflyer-push-custom-data-firebase-json.png](https://files.readme.io/138aa2abb70cdb0b8a2c1a4b4ce0a8b83b2faae58e29f3223d5653a4d575012b-49839256716049.png)

</Tab>
</Tabs>

</Accordion>

<Accordion title="2. Configurando o SDK">

Esta tarefa exige alterações no código do app. Siga as instruções sobre como configurar o SDK:

* Ao implementar a solução recomendada baseada no OneLink:
  1. Informe ao desenvolvedor do aplicativo qual é o nome da chave personalizada que você adicionou à notificação. Neste exemplo, é `af_push_link`.
  2. Envie <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-using-onelink-recommended">estas instruções</Anchor>.
* Ao implementar a solução legada baseada no JSON, envie <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-legacy">estas instruções</Anchor> a seus desenvolvedores.

</Accordion>

<Accordion title="3. Testando a integração">

Para testar se a métrica de notificação push está integrada corretamente, basta acionar uma notificação push na campanha que você montou na Etapa 1.

Se tudo estiver configurado corretamente, o SDK vai:

1. Ouvir as notificações por impulso.
2. Processar os dados de atribuição incorporados na notificação push e enviá-los para a AppsFlyer.
3. Proceder com o fluxo regular de deep linking, se a métrica de notificação push for implementada usando o OneLink.

</Accordion>

<Accordion title="4. Visualizando as campanhas de notificação push no painel de instrumentos">

Você pode ver os dados provenientes das notificações push no <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide#retargeting-dashboard">painel Retargeting</Anchor>.

**Observação**: AppsFlyer deduplica os dados de notificação push. Ou seja, se payloads idênticos são recebidos mais de uma vez, apenas um é contado.

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01J5XFSEG9DR31DP73KTAGQPFW=vis%C3%A3o-geral how-does-it-work=como-ela-funciona h_01J5XFSEG967HXNT3GFSC2AQYE=como-ela-funciona prerequisites=pr%C3%A9-requisitos h_01J5XFSEG91SER3JKB3RKK6B6G=pr%C3%A9-requisitos steps=etapas h_01J5XFSEG9W3RTP62NW7SV4D0F=etapas using-onelink-recommended=usando-onelink-recomendado h_01J5XFSEG9W73JYPHH9VRZSTZ8=usando-onelink-recomendado using-json-legacy=usando-onelink-recomendado h_01J5XFSEG9V46T6XSG31J4AVET=usando-onelink-recomendado" />
