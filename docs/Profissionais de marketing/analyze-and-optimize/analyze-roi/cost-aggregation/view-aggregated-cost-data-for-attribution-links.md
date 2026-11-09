---
title: Veja dados agregados de custo para links de Atribuição
metadata:
  keywords:
    - eCPI
    - clicks
    - ROI
    - Advertisers
    - Agencies
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-05-20T10:50:58Z'
  edited_at: '2026-08-19T00:01:20Z'
  id: 360008981698
  locale: pt
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/pt/articles/360008981698
---
> **Visão geral:** Veja seus dados de custo agregados para cada clique em seus anúncios, conforme relatados pelas ad networks.

<div id="basic-cost-reporting" />

## Relatórios de custos básicos

Os dados de custo são comunicados à AppsFlyer por:

* Ad networks: sempre que um usuário clica em um anúncio. Visualizar esses dados de custo na AppsFlyer permite que os anunciantes mensurem o ROI e façam as escolhas certas para seus orçamentos.
  * O custo é relatado no <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">link de atribuição</Anchor> usando o modelo de custo por instalação (CPI).
  * Ao enviar o link de atribuição para a ad network, verifique se ela <Anchor target="_blank" href="/partners/pt/docs/cost-reporting-on-the-attribution-link-for-ad-networks">inclui os parâmetros de relatório de custos</Anchor>.
* <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview">Opções avançadas para agregação de custos</Anchor>, incluindo a opção de agregação por API e Cost Import (upload de um arquivo CSV).

  * Os métodos de agregação de custos são compatíveis com os modelos de custos usados pelo parceiro, além dos modelos de CPI, incluindo CPI, CPA, CPC e CPM.

<div id="viewing-ad-cost-by-click" />

<Accordion title="Visualizar o custo do anúncio por clique">

Os dados de custo por clique são agregados e estão disponíveis para visualização em tempo real (no máximo até 2 horas após o clique) nos dashboards, relatórios de performance e relatórios de dados brutos da AppsFlyer.

*No **dashboard de Visão Geral,** o Relatório de Performance Agregada inclui:* custo, cliques, impressões, ROI e dados de eCPI médio.

<Image align="center" alt="RelatórioDeCusto.jpg" src="https://files.readme.io/5d4dbe5dc74fd0915924518f76c63e379f0b072b5d5dbb7a7f92455b83e33a12-17313191631633.jpg" />

Os relatórios de performance e de dados brutos também estão disponíveis para <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">download</Anchor>.

</Accordion>

<div id="ad-networks-providing-cost-by-click-data" />

<Accordion title="Ad networks que fornecem dados de custo por clique">

Para ad networks que relatam o custo por clique, as dimensões compatíveis são aquelas contidas no clique.

**As ad networks que relatam o custo por clique incluem:**

* AdAction
* Aura from Unity
* Blind Ferret
* Chartboost
* Cross Install
* Digital Turbine
* Fyber
* HangMyAds
* ironSource
* Criteo DSP (Manage)
* Mintegral
* TikTok para Empresas
* Vungle
* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTMPZ9anfZoFBelK2bsBUoHG9n4YE3WxpXOayDF_wI8vyYClM6_6yXelFCZ3khwhd9Z_5Louxd4VVgx/pub?gid=0&single=true&output=csv">Veja a lista completa de ad networks compatíveis com o custo por clique</Anchor>

</Accordion>

<div id="limitations" />

<Accordion title="Limitações">

Limitações do custo por clique:

* O custo só é relatado através do modelo de custo por instalação (CPI). Outros modelos, incluindo CPA, CPC e CPM, não são compatíveis.
* <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">As redes de autorrelato</Anchor> (SRN) não relatam o custo por clique.
* Os dados de cliques são imutáveis. Assim, quando eles são registrados na AppsFlyer, eles não podem ser alterados, mesmo que existam erros de comunicação de dados.

</Accordion>

<div data-zendesk-anchors="basic-cost-reporting=relat%C3%B3rios-de-custos-b%C3%A1sicos h_01HX954Y5X7ZP2VMB5W2XAMCR0=relat%C3%B3rios-de-custos-b%C3%A1sicos h_01HX954Y5XTRRQV4JHA5XX1AQ0=viewing-ad-cost-by-click h_01HX954Y5XV8M2R2VDAV34641R=ad-networks-providing-cost-by-click-data h_01HX954Y5X84BM7F8TGQRDPBTS=limitations" />
