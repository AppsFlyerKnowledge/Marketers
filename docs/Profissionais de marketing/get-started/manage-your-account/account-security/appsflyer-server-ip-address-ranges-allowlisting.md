---
title: Intervalos de endereços de IP do servidor da AppsFlyer (lista de permissões)
metadata:
  keywords:
    - whitelisting
    - AppsFlyer
    - IPs
    - Advertisers
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Ad Networks
  created_at: '2015-12-24T11:30:11Z'
  edited_at: '2026-08-18T00:17:08Z'
  id: 207447093
  locale: pt
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/pt/articles/207447093
---
> **Visão geral:** endereços de IP da AppsFlyer usados para solicitações de API de saída.

## Intervalos de endereços de IP do servidor da AppsFlyer

Os endereços de IP listados são controlados por e para o uso da AppsFlyer. A lista muda de tempos em tempos de acordo com a nossa capacidade e outros requisitos operacionais. Fazemos todos os esforços necessários para que essa lista seja alterada com a menor frequência possível.

As APIs da AppsFlyer oferecem serviços de atribuição e relatórios para anunciantes e parceiros. Esses serviços incluem:

* O envio de postbacks
* O envio de mensagens da Push API

Se você usa dispositivos de perímetro de rede, como firewalls e servidores proxy, você deve pedir à sua equipe de segurança para permitir a lista de endereços IP da AppsFlyer conforme listado nesta <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTzJqwOhIkSV0Mbnu4DZOx2eWKAd8OPRUNCu2REjz9z9qonI5ZDlHl6kGd1KAXopaDbf1MzuNXjeVj-/pub?gid=0&single=true&output=csv">lista de permissões de IP.</Anchor>

Em 16 de fevereiro de 2022, descontinuamos os endereços IP legados e os removemos da lista de permissões.

Os endereços na lista de permissão usam os seguintes blocos CIDR:

* [45.92.116.0/22]
* [194.28.46.0/23]

### Fazendo upload do Audiences

Se você usar dispositivos de perímetro de rede, como firewalls e servidores proxy, deverá pedir à sua equipe de segurança para permitir endereços IP da AppsFlyer conforme listados nesta [lista de permissões de IP para Audiences](https://support.appsflyer.com/hc/article_attachments/16888953497617).

Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide">Audiences</Anchor>.

### Pull API e servidor para servidor (S2S)

A Pull API e o S2S não são afetados pelos endereços listados neste artigo. No entanto, verifique se o domínio *\*.appsflyer.com* está na lista de permissões e não está bloqueado.

<div data-zendesk-anchors="appsflyer-server-ip-address-ranges=intervalos-de-endere%C3%A7os-de-ip-do-servidor-da-appsflyer uploading-audiences=fazendo-upload-do-audiences pull-api-and-servertoserver-s2s=pull-api-e-servidor-para-servidor-s2s" />
