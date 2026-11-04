---
title: Como excluir usuários de campanhas de UA
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2020-05-03T10:11:31Z'
  edited_at: '2026-08-18T00:30:19Z'
  id: 360007949158
  locale: pt
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/pt/articles/360007949158
---
> **Visão geral:** exclua usuários existentes das campanhas de aquisição de usuários (UA) para obter mais instalações com o mesmo orçamento e melhorar o ROAS.

<div id="issues-and-consequences" />

## Problemas e consequências

Se seu aplicativo receber tráfego de várias fontes de mídia, essas fontes podem direcionar seus usuários existentes em suas campanhas de UA.

A performance da campanha pode ser afetada pelos seguintes motivos:

* **Pagamentos duplos** - Pagando por impressões/cliques do usuário pelos quais você pagou no passado.
* **Taxas de conversão distribuídas** - as campanhas de UA parecem menos bem-sucedidas. Há menos instalações, pois as impressões são desperdiçadas em usuários existentes.
* **Perda de usuários alternativos** - os não usuários podem ter visto os anúncios e se tornado seus usuários mobile.

<Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#what-is-srn-mistargeting">O erro de direcionamento de SRN</Anchor> é um problema de desempenho semelhante e comum. Esse problema significativo pode ocorrer se suas campanhas de UA e redirecionamento estiverem com o mesmo SRN. <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#o-erro-de-direcionamento-é-um-problema">Saiba mais</Anchor> 

<div id="solutions" />

## Soluções

Essas soluções descrevem como atualizar ad networks para excluir usuários existentes das campanhas de UA.

<div id="manual-update" />

### Atualização manual

Colete seus dados brutos de instalação a nível do usuário da AppsFlyer para criar listas de ID de dispositivo. Em seguida, envie essas listas para ad networks para garantir a exclusão do usuário.

Existem várias maneiras de adicionar esses dados brutos ao seu sistema de BI:

* Faça o download dos relatórios de dados brutos
* Use solicitações periódicas de Pull API de dados brutos
* Use a Push API para implementar a coleta em tempo real
* Obter dados de conversão do SDK

<div id="note" />

> 📘 **Observação**
>
> No intervalo de tempo entre o envio manual da próxima lista para as ad networks, as campanhas de UA podem direcionar os usuários mais recentes do seu aplicativo.

<div id="audiences" />

### Audiências

**<Anchor target="_blank" href="/marketers/pt/docs/audiences-guide">Audiences</Anchor>** é um recurso premium da AppsFlyer. Todos os dias, segmentos selecionados da sua base de usuários são enviados automaticamente para várias ad networks, de acordo com a sua escolha.

**Audiences** é muito útil para manter listas de exclusão:

* **Baixo esforço** - nenhum trabalho de desenvolvimento ou manutenção é exigido por você ou pela ad network.
* **Fácil de usar** - após uma configuração inicial curta, você pode começar a fazer upload de públicos.
* **Eficiente** - os segmentos são enviados para ad networks automaticamente a cada 24 horas.

<div data-zendesk-anchors="issues-and-consequences=problemas-e-consequ%C3%AAncias solutions=solu%C3%A7%C3%B5es manual-update=atualiza%C3%A7%C3%A3o-manual audiences=audi%C3%AAncias" />
