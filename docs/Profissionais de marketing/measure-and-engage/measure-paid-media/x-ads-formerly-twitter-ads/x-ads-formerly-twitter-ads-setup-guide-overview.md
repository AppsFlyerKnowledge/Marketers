---
title: Guia de configuração do X Ads (antigo Twitter Ads) — visão geral
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:31:36Z'
  edited_at: '2026-08-18T00:33:22Z'
  id: 4410464316049
  locale: pt
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/pt/articles/4410464316049
---
> **Resumo:** entenda como integrar a sua conta do X Ads com a AppsFlyer.

<Image alt="X Ads logo.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="167px" />

## Mobile app promotion no X Ads

O Mobile App Promotion no X Ads é um método usado para divulgar aplicativos no X Ads. Isso permite que os anunciantes promovam seus aplicativos usando um design exclusivo para o card de um aplicativo, impulsionando instalações, engajamento e deep linking. Os usuários podem facilmente instalar e colaborar com aplicativos diretamente a partir da linha do tempo do X Ads.

## Privacidade do usuário no X Ads

Os usuários do X Ads podem controlar como compartilham informações com os anunciantes:

* Se as configurações do usuário estiverem definidas para evitar o compartilhamento de suas informações de engajamento com anunciantes, as instalações impulsionadas pelo X Ads e os eventos in-app serão omitidos dos dados brutos, mas ainda serão atribuídos ao X Ads.
* Os dados de atribuição agregados são corretamente refletidos na AppsFlyer e não são afetados pela política do X Ads.
* Como resultado, os relatórios de dados agregados e de dados brutos do X Ads não estão correlacionados.

A partir de 31 de julho de 2021, os anunciantes que não fazem parte do programa AMM (Advanced Mobile Measurement) do X Ads deixarão de receber todos os dados do X Ads MACT a nível de usuário.

Por meio do programa AMM, os anunciantes podem receber dados mais completos a nível de usuário depois de conceder ao X Ads o direito de realizar uma auditoria para garantir que os dados do X Ads estejam sendo usados exclusivamente para fins de mensuração. Isso condiz com as leis de proteção de dados aplicáveis e com as práticas comuns a todo o setor.  
**Para se juntar ao programa AMM:** Acesse ads.twitter.com/help > **Mobile App, Conversion Tracking & Audience Manager** e selecione**Advanced Mobile Measurement Program Agreement Form**.

Dados a nível de usuário recebidos antes de entrar no programa AMM não podem ser exportados.

Para informações mais detalhadas, entre em contato com seu gerente de conta do X Ads.

## X Ads e AppsFlyer: interoperação com a SKAN

O X Ads envia dados de postback da SKAdNetwork por meio de uma API dedicada. Os dados SKAN do X Ads serão exibidos no <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">dashboard da SKAN</Anchor>.

O X Ads enriquece os postbacks da SKAN com os seguintes campos de dados:

* Campaign name
* ID da campanha
* Nome do Adset
* Adset ID

<div data-zendesk-anchors="mobile-app-promotion-on-twitter=mobile-app-promotion-no-x-ads h_01H9QR6TH7M0H5YMXRWVVAYRK9=mobile-app-promotion-no-x-ads twitter-user-privacy=privacidade-do-usu%C3%A1rio-no-x-ads h_01H9QR6TH74R50K00H7FYN61KC=privacidade-do-usu%C3%A1rio-no-x-ads twitter-ads-and-appsflyer-skan-interoperation=x-ads-e-appsflyer-interopera%C3%A7%C3%A3o-com-a-skan h_01H9QR6TH74PKBGM5RC4M118GE=x-ads-e-appsflyer-interopera%C3%A7%C3%A3o-com-a-skan" />
