---
title: Discrepâncias de atribuição entre Amazon Ads e AppsFlyer
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-09-18T04:28:03Z'
  edited_at: '2026-08-28T00:26:10Z'
  id: 28461159218449
  locale: pt
  section: Amazon Ads
  section_id: 28703975923729
  url: https://support.appsflyer.com/hc/pt/articles/28461159218449
---
> **At a glance:** Compreenda as diferenças nos modelos de atribuição entre o Amazon Ads e o AppsFlyer.

<div id="overview" />

## Visão geral

Como dois intervenientes principais no ecossistema de aquisição de utilizadores móveis, a Amazon Ads e a AppsFlyer utilizam modelos de atribuição distintos. Tal pode originar discrepâncias entre os painéis de controlo da Amazon Ads e da AppsFlyer. Apesar de trabalharmos em estreita colaboração com a Amazon Ads para minimizar estas discrepâncias, os anunciantes precisam estar atentos às causas potenciais.

<div id="differences-in-attribution-models" />

## Diferenças nos modelos de atribuição

A tabela abaixo apresenta possíveis razões para discrepâncias entre os painéis da Amazon Ads e da AppsFlyer:

| Causa | Gestor de Anúncios da Amazon | A AppsFlyer |
| --- | --- | --- |
| <span id="multichannel-source-attribution"></span>Atribuição de fonte multicanal | A Amazon Ads faz autoatribuição de instalações independentemente de outras fontes de média. | A AppsFlyer utiliza atribuição de último clique.  <br />Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">modelo de atribuição da AppsFlyer</Anchor>. |
| <span id="different-timezones"></span>Diferenças de fusos horários | O fuso horário do Amazon Ads (mostrado ao lado do período) não pode ser alterado. Foi definido na criação da conta de anúncios. | O fuso horário padrão do aplicativo AppsFlyer é UTC+0. Para ajustar ao fuso horário definido no Amazon Ads, altere o fuso horário na <Anchor target="_blank" href="/marketers/pt/docs/app-settings#localization-time-zone">página de configurações da aplicação</Anchor>. |

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01J81NN4J4A1KWBXJQD9SM2AWH=vis%C3%A3o-geral differences-in-attribution-models=diferen%C3%A7as-nos-modelos-de-atribui%C3%A7%C3%A3o h_01J81NN4J4WSJBFHBARKTQ9JG5=diferen%C3%A7as-nos-modelos-de-atribui%C3%A7%C3%A3o reducing-discrepancies=diferen%C3%A7as-nos-modelos-de-atribui%C3%A7%C3%A3o h_01J81NN4J4EJQH47YJF0H5M97G=diferen%C3%A7as-nos-modelos-de-atribui%C3%A7%C3%A3o" />
