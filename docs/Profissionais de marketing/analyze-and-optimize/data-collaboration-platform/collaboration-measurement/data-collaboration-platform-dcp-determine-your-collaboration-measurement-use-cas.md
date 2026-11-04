---
title: >-
  Plataforma de colaboração de dados (DCP) - Determine seu caso de uso de
  mensuração da colaboração
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2025-02-25T15:52:06Z'
  edited_at: '2026-08-18T00:06:38Z'
  id: 32964487756561
  locale: pt
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/pt/articles/32964487756561
---
> **Em resumo:** Identifique seu cenário de colaboração, certificando-se de saber quais dados fornecer, quem é responsável por eles e em que formato enviá-los.

<div id="overview" />

## Escritórios

A DCP oferece suporte a vários casos de uso on-site e off-site. Cada caso de uso exige uma configuração diferente, especificando qual colaborador é responsável por preparar cada fonte de dados e em que formato os dados devem ser configurados.

Este artigo tem como objetivo ajudar as Commerce Media Networks (CMNs) e os anunciantes (marcas) a identificar qual caso de uso se aplica a eles. Depois que o caso de uso apropriado for determinado, o proprietário da colaboração poderá atribuir as tarefas necessárias de preparação e configuração aos colaboradores relevantes (para mais informações sobre atribuição de tarefas, consulte: <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#configuration-task-assignment">Atribuir tarefa de configuração</Anchor>.)

É aqui que a árvore de decisão do caso de uso entra em ação. Ela funciona como um guia estruturado para ajudar você a especificar seu caso de uso e receber as instruções de preparação correspondentes.

<div id="how-does-the-decision-tree-help" />

## Como a árvore de decisão ajuda?

Dependendo da configuração, um colaborador pode precisar preparar e configurar as tarefas de conversões e campanhas, enquanto o outro pode ser responsável por preparar as tarefas de engajamentos ou de parceiros de mídia. A árvore de decisão ajuda o proprietário da colaboração a determinar qual colaborador deve receber cada tarefa e fornece links para as instruções correspondentes.

<div id="which-decision-tree-do-i-need-on-site-or-off-site" />

### De qual árvore de decisão eu preciso: on-site ou off-site?

Você pode usar duas árvores de decisão: uma para campanhas on-site e a outra para campanhas off-site. Para determinar qual árvore de decisão é apropriada, considere onde o **anúncio é veiculado** e onde a **conversão ocorre**.

* Use a [árvore de decisão para campanhas off-site](#a-árvore-de-decisão-da-campanha-off-site) se o anúncio for exibido em uma plataforma de publicidade externa (por exemplo, Facebook, Google) fora das propriedades que pertencem e são operadas por você.
* Use a [árvore de decisão para campanhas on-site](#a-árvore-de-decisão-para-campanhas-on-site) se o anúncio for veiculado dentro do seu ecossistema e a conversão ocorrer na sua plataforma.

<div id="the-on-site-campaign-decision-tree" />

## A árvore de decisão para campanhas on-site

No cenário de campanha on-site, a conversão ocorre em uma plataforma que pertence e é operada pela CMN ou pelo anunciante. Isso leva à pergunta inicial na árvore de decisão on-site: em qual plataforma a conversão ocorre — na da CMN ou na do anunciante?

Responda à pergunta inicial escolhendo a resposta correta e continue expandindo os ramos que correspondem às suas condições específicas.

<div id="on-which-platform-does-the-conversion-take-place" />

#### **Em qual plataforma a conversão ocorre?**

<div id="the-conversions-take-place-on-the-cmn-platform" />

<Accordion title="As conversões ocorrem na plataforma da CMN">

<div id="the-cmn-platform-is-an-app" />

<Accordion title="A plataforma da CMN é um aplicativo">

Se a plataforma da CMN for um aplicativo, siga as instruções abaixo para cada tipo de dado:

| Função | Preparado e configurado por | Saiba como preparar | Saiba como configurar |
| --- | --- | --- | --- |
| Campanhas | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-a-fonte-de-mapeamento-da-campanha">Fonte da campanha</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-campaigns-task">Configuração da tarefa de campanhas</Anchor></li></ul> |
| Conversões | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fonte de conversão</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Evento in-app de conversão</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task#configure-conversões-de-campanhas-on-site">Configuração da tarefa de conversões no site</Anchor></li></ul> |
| Engajamentos | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Fonte de engajamento</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-engagement-inapp-events">Evento in-app de engajamento</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-engagements-task">Configuração da tarefa de engajamento</Anchor></li></ul> |
| Janelas de lookback | CMN/Anunciante | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-lookback-windows-task">Configuração da tarefa de janelas de lookback</Anchor></li></ul> |

</Accordion>

**OU**

<div id="the-cmn-platform-is-a-website" />

<Accordion title="A plataforma CMN é um site">

Se a plataforma CMN for um site, siga as instruções abaixo para cada tipo de dado:

| Função | Preparado e configurado por | Saiba como preparar | Saiba como configurar |
| --- | --- | --- | --- |
| Campanhas | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-a-fonte-de-mapeamento-da-campanha">Fonte da campanha</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-campaigns-task">Configuração da tarefa de campanhas</Anchor></li></ul> |
| Conversões | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fonte de conversão</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task#configure-conversões-de-campanhas-on-site">Configuração da tarefa de conversões no site</Anchor></li></ul> |
| Engajamentos | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Fonte de engajamento</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-engagements-task">Configuração da tarefa de engajamento</Anchor></li></ul> |
| Janelas de lookback | CMN/Anunciante | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-lookback-windows-task">Configuração da tarefa de janelas de lookback</Anchor></li></ul> |

</Accordion>

</Accordion>

**OU**

<div id="the-conversions-take-place-on-the-advertiser-platform" />

<Accordion title="As conversões ocorrem na plataforma do anunciante">

<div id="the-advertiser-platform-is-an-app" />

<Accordion title="A plataforma do anunciante é um aplicativo">

Se a plataforma do anunciante for um aplicativo, siga as instruções abaixo para cada tipo de dados:

| Função | Preparado e configurado por | Saiba como preparar | Saiba como configurar |
| --- | --- | --- | --- |
| Campanhas | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-a-fonte-de-mapeamento-da-campanha">Fonte da campanha</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-campaigns-task">Configuração da tarefa de campanhas</Anchor></li></ul> |
| Conversões | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fonte de conversão</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Evento in-app de conversão</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task#configure-conversões-de-campanhas-on-site">Configuração da tarefa de conversões no site</Anchor></li></ul> |
| Engajamentos | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Fonte de engajamento</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-engagement-inapp-events">Evento in-app de engajamento</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-engagements-task">Configuração da tarefa de engajamentos</Anchor></li></ul> |
| Janelas de lookback | CMN/Anunciante | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-lookback-windows-task">Configuração da tarefa de janelas de lookback</Anchor></li></ul> |

</Accordion>

**OU**

<div id="the-advertiser-platform-is-a-website" />

<Accordion title="A plataforma do anunciante é um site">

Se a plataforma do anunciante for um site, siga as instruções abaixo para cada tipo de dados:

| Função | Preparado e configurado por | Saiba como preparar | Saiba como configurar |
| --- | --- | --- | --- |
| Campanhas | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-a-fonte-de-mapeamento-da-campanha">Fonte da campanha</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-campaigns-task">Configuração da tarefa de campanhas</Anchor></li></ul> |
| Conversões | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fonte de conversão</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task#configure-conversões-de-campanhas-on-site">Configuração da tarefa de conversões no site</Anchor></li></ul> |
| Engajamentos | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Fonte de engajamento</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-engagements-task">Configuração da tarefa de engajamento</Anchor></li></ul> |
| Janelas de lookback | CMN/Anunciante | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-lookback-windows-task">Configuração da tarefa de janelas de lookback</Anchor></li></ul> |

</Accordion>

</Accordion>

<div id="the-off-site-campaign-decision-tree" />

## A árvore de decisão da campanha off-site

No cenário de campanha off-site, o anúncio é exibido em uma plataforma de publicidade externa, como Facebook ou Google. Isso leva à pergunta inicial na árvore de decisão off-site: qual conta na plataforma de publicidade externa é usada para exibir o anúncio: a da CMN ou a do anunciante?

Responda à pergunta inicial escolhendo a resposta correta e continue expandindo os ramos que correspondem às suas condições específicas.

<div id="which-account-on-the-external-platform-displays-the-ad" />

#### **Qual conta na plataforma externa exibe o anúncio?**

<div id="the-cmn-external-platform-account" />

<Accordion title="A conta da CMN na plataforma externa exibe o anúncio">

<div id="the-conversions-take-place-on-the-cmn-platform::e7b94fc0" />

<Accordion title="As conversões ocorrem na plataforma da CMN">

<div id="the-cmn-platform-is-an-app::76ead17" />

<Accordion title="A plataforma da CMN é um aplicativo">

Se a plataforma da CMN for um aplicativo, siga as instruções abaixo para cada tarefa:

| Função | Preparado e configurado por | Saiba como preparar | Saiba como configurar |
| --- | --- | --- | --- |
| Conversões | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fonte de conversão</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Evento in-app de conversão</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task#configure-conversões-de-campanhas-on-site">Configuração da tarefa de conversões on-site</Anchor></li></ul> |
| Campanhas | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-a-fonte-de-mapeamento-da-campanha">Fonte de mapeamento de campanhas</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-campaigns-task">Configuração da tarefa de campanhas</Anchor></li></ul> |
| Parceiros de mídia | CMN | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-media-partners-task">Configuração da tarefa de parceiros de mídia</Anchor></li></ul> |
| Janelas de lookback | CMN/Anunciante | Não relevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-lookback-windows-task">Configuração da janela de lookback</Anchor></li></ul> |

</Accordion>

**OU**

<div id="the-cmn-platform-is-a-website::5144f168" />

<Accordion title="A plataforma CMN é um site">

Se a plataforma CMN for um site, siga as instruções abaixo para cada tarefa:

| Função | Preparado e configurado por | Saiba como se preparar | Saiba como configurar |
| --- | --- | --- | --- |
| Conversões | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fonte de conversão (personalizada)</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task#configure-conversões-de-campanhas-on-site">Configuração da tarefa de conversões no site</Anchor></li></ul> |
| Campanhas | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-a-fonte-de-mapeamento-da-campanha">Fonte de mapeamento de campanha</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-campaigns-task">Configuração da tarefa de campanhas</Anchor></li></ul> |
| Parceiros de mídia | CMN | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-media-partners-task">Configuração da tarefa de parceiros de mídia</Anchor></li></ul> |
| Janelas de lookback | CMN/Anunciante | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-lookback-windows-task">Configuração da janela de lookback</Anchor></li></ul> |

</Accordion>

</Accordion>

**OU**

<div id="the-conversions-take-place-on-the-advertiser-platform::aa9e89bf" />

<Accordion title="As conversões ocorrem na plataforma do anunciante">

<div id="the-advertiser-platform-is-an-app::d36436f5" />

<Accordion title="A plataforma do anunciante é um aplicativo">

Se a plataforma do anunciante for um aplicativo, siga as instruções abaixo para cada tarefa:

| Função | Preparado e configurado por | Saiba como preparar | Saiba como configurar |
| --- | --- | --- | --- |
| Conversões | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fonte de conversão</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Evento in-app de conversão</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task#configure-conversões-de-campanhas-on-site">Configuração da tarefa de conversões no site</Anchor></li></ul> |
| Campanhas | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-a-fonte-de-mapeamento-da-campanha">Fonte de mapeamento de campanha</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-campaigns-task">Configuração da tarefa de campanhas</Anchor></li></ul> |
| Parceiros de mídia | CMN | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-media-partners-task">Configuração da tarefa de parceiros de mídia</Anchor></li></ul> |
| Janelas de lookback | CMN/Anunciante | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-lookback-windows-task">Configuração das janelas de lookback</Anchor></li></ul> |

</Accordion>

**OU**

<div id="the-advertiser-platform-is-a-website::b70163fb" />

<Accordion title="A plataforma do anunciante é um site">

Se a plataforma do anunciante for um site, siga as instruções abaixo para cada tarefa:

| Função | Preparado e configurado por | Saiba como se preparar | Saiba como configurar |
| --- | --- | --- | --- |
| Conversões | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fonte de conversão (personalizada)</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task#configure-conversões-de-campanhas-on-site">Configuração da tarefa de conversões no site</Anchor></li></ul> |
| Campanhas | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-a-fonte-de-mapeamento-da-campanha">Fonte de mapeamento de campanha</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-campaigns-task">Configuração da tarefa de campanhas</Anchor></li></ul> |
| Parceiros de mídia | CMN | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-media-partners-task">Configuração da tarefa de parceiros de mídia</Anchor></li></ul> |
| Janelas de lookback | CMN/Anunciante | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-lookback-windows-task">Configuração das janelas de lookback</Anchor></li></ul> |

</Accordion>

</Accordion>

</Accordion>

**OU**

<div id="the-advertisers-external-platform-account" />

<Accordion title="A conta do anunciante na plataforma externa exibe o anúncio">

<div id="the-conversions-take-place-on-the-cmn-platform::7b0781d3" />

<Accordion title="As conversões ocorrem na plataforma CMN">

<div id="the-cmn-platform-is-an-app::413a6003" />

<Accordion title="A plataforma CMN é um aplicativo">

Se a plataforma CMN for um aplicativo, siga as instruções abaixo para cada tarefa:

| Função | Preparado e configurado por | Saiba como preparar | Saiba como configurar |
| --- | --- | --- | --- |
| Conversões | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fonte de conversão</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Evento in-app de conversão</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task#configure-conversões-de-campanhas-on-site">Configuração da tarefa de conversões no site</Anchor></li></ul> |
| Campanhas | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-a-fonte-de-mapeamento-da-campanha">Fonte de mapeamento de campanhas</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-campaigns-task">Configuração da tarefa de campanhas</Anchor></li></ul> |
| Parceiros de mídia | AppsFlyer | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-media-partners-task">Configuração da tarefa de parceiros de mídia</Anchor></li></ul> |
| Janelas de lookback | CMN/Anunciante | Não relevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-lookback-windows-task">Configuração de janelas de lookback</Anchor></li></ul> |

</Accordion>

**OU**

<div id="the-cmn-platform-is-a-website::95667666" />

<Accordion title="A plataforma CMN é um site">

Se a plataforma CMN for um site, siga as instruções abaixo para cada tarefa:

| Função | Preparado e configurado por | Saiba como preparar | Saiba como configurar |
| --- | --- | --- | --- |
| Conversões | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fonte de conversão (personalizada)</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task#configure-conversões-de-campanhas-on-site">Configuração da tarefa de conversões no site</Anchor></li></ul> |
| Campanhas | CMN | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-a-fonte-de-mapeamento-da-campanha">Fonte de mapeamento de campanhas</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-campaigns-task">Configuração da tarefa de campanhas</Anchor></li></ul> |
| Parceiros de mídia | AppsFlyer | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-media-partners-task">Configuração da tarefa de parceiros de mídia</Anchor></li></ul> |
| Janelas de lookback | CMN | Não relevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-lookback-windows-task">Configuração de janelas de lookback</Anchor></li></ul> |

</Accordion>

</Accordion>

**OU**

<div id="the-conversions-take-place-on-the-advertiser-platform::51470bc6" />

<Accordion title="As conversões ocorrem na plataforma do anunciante">

<div id="h_01K3BAV1SP7RWP7K9TM7Y6MJVX" />

<Accordion title="A plataforma do anunciante é um aplicativo">

Se a plataforma do anunciante for um aplicativo, siga as instruções abaixo para cada tarefa:

| Função | Preparado e configurado por | Saiba como se preparar | Saiba como configurar |
| --- | --- | --- | --- |
| Conversões | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fonte de conversão</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Evento in-app de conversão</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task#configure-conversões-de-campanhas-on-site">Configuração da tarefa de conversões no site</Anchor></li></ul> |
| Campanhas | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-a-fonte-de-mapeamento-da-campanha">Fonte de mapeamento de campanhas</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-campaigns-task">Configuração da tarefa de campanhas</Anchor></li></ul> |
| Parceiros de mídia | AppsFlyer | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-media-partners-task">Configuração da tarefa de parceiros de mídia</Anchor></li></ul> |
| Janelas de lookback | CMN | Não relevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-lookback-windows-task">Configuração de janelas de lookback</Anchor></li></ul> |

</Accordion>

**OU**

<div id="the-advertiser-platform-is-a-website::8cb255ef" />

<Accordion title="A plataforma do anunciante é um site">

Se a plataforma do anunciante for um site, siga as instruções abaixo para cada tarefa:

| Função | Preparado e configurado por | Saiba como se preparar | Saiba como configurar |
| --- | --- | --- | --- |
| Conversões | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fonte de conversão (personalizada)</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task#configure-conversões-de-campanhas-on-site">Configuração da tarefa de conversões no site</Anchor></li></ul> |
| Campanhas | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-a-fonte-de-mapeamento-da-campanha">Fonte de mapeamento de campanhas</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-campaigns-task">Configuração de tarefas de campanha</Anchor></li></ul> |
| Parceiros de mídia | AppsFlyer | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-media-partners-task">Configuração de tarefas de parceiros de mídia</Anchor></li></ul> |
| Janelas de lookback | CMN | Irrelevante | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-the-lookback-windows-task">Configuração de janelas de retrospectiva</Anchor></li></ul> |

</Accordion>

</Accordion>

</Accordion>

<div data-zendesk-anchors="overview=escrit%C3%B3rios h_01JSKXR18RP691PT3Y5JGAJKF8=escrit%C3%B3rios how-does-the-decision-tree-help=como-a-%C3%A1rvore-de-decis%C3%A3o-ajuda h_01K3JR6NJ906S2HZC7YRWWFT2P=como-a-%C3%A1rvore-de-decis%C3%A3o-ajuda which-decision-tree-do-i-need-onsite-or-offsite=de-qual-%C3%A1rvore-de-decis%C3%A3o-eu-preciso-on-site-ou-off-site h_01K3JR7AZFWJMTBZGAKYS4BFJS=de-qual-%C3%A1rvore-de-decis%C3%A3o-eu-preciso-on-site-ou-off-site the-onsite-use-case-decision-tree=a-%C3%A1rvore-de-decis%C3%A3o-para-campanhas-on-site h_01JSKXR18R4A4WFPTQVB1DVV5Y=a-%C3%A1rvore-de-decis%C3%A3o-para-campanhas-on-site on-which-platform-does-the-conversion-take-place=em-qual-plataforma-a-convers%C3%A3o-ocorre h_01JSM17ZMGCF1FWQPM7T04C0MM=em-qual-plataforma-a-convers%C3%A3o-ocorre h_01JSKXR18RTDSJ6W40D5JVFSS5=the-conversions-take-place-on-the-cmn-platform h_01JSKXR18R9A9MCZ7TPJHXWMBC=the-cmn-platform-is-an-app h_01JSKXR18RWSJTR5AKDBRGP0QS=the-cmn-platform-is-a-website h_01JSKXR18R083C5FY5FTESJDAZ=the-conversions-take-place-on-the-advertiser-platform h_01JSKXR18RH3SCQJRJA7QBVS6Y=the-advertiser-platform-is-an-app h_01JSKXR18R3N816VYJ4910VYGA=the-advertiser-platform-is-a-website the-offsite-use-case-decision-tree=a-%C3%A1rvore-de-decis%C3%A3o-da-campanha-off-site h_01JSKXR18R38YJZ2S410J4EH43=a-%C3%A1rvore-de-decis%C3%A3o-da-campanha-off-site which-account-on-the-external-platform-displays-the-ad=qual-conta-na-plataforma-externa-exibe-o-an%C3%BAncio h_01JSM18A2R9015RWB05BE0YK7Q=qual-conta-na-plataforma-externa-exibe-o-an%C3%BAncio h_01JSKXR18R4EKMWCYKFTBAEPH9=the-cmn-external-platform-account h_01JSKXR18RCKD3E841EQ2RC03B=the-conversions-take-place-on-the-cmn-platform::e7b94fc0 h_01JSKXR18R5115TP1BYE07TJ7V=the-cmn-platform-is-an-app::76ead17 h_01JSKXR18RCBGH6F8SNSRN2CJG=the-cmn-platform-is-a-website::5144f168 h_01JSKXR18RGQX77NM72G4WAC08=the-conversions-take-place-on-the-advertiser-platform::aa9e89bf h_01JSKXR18R61CTQ0VMRKD184VE=the-advertiser-platform-is-an-app::d36436f5 h_01JSKXR18RSQC7MCYZ5JE2VP3B=the-advertiser-platform-is-a-website::b70163fb h_01JSKXR18SYFX87XBSBNPJXAFA=the-advertisers-external-platform-account h_01JSKXR18S6TQMNW6PD65G67AQ=the-conversions-take-place-on-the-cmn-platform::7b0781d3 h_01JSKXR18SCDQXAN5NFQ1W17K2=the-cmn-platform-is-an-app::413a6003 h_01JSKXR18SDCDQX4SJ24ADZA18=the-cmn-platform-is-a-website::95667666 h_01JSKXR18S123PXD3FN2N11GCN=the-conversions-take-place-on-the-advertiser-platform::51470bc6 h_01JSKXR18STJV3GGW83123W7XC=the-advertiser-platform-is-a-website::8cb255ef" />
