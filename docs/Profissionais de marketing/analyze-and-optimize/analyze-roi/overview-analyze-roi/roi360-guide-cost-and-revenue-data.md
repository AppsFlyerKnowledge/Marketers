---
title: Guia ROI360 — dados de custo e receita
metadata:
  keywords:
    - cost
    - Advertisers
    - Premium
    - Marketers
    - revenue
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-11-10T13:52:03Z'
  edited_at: '2026-08-18T00:01:32Z'
  id: 10515748254609
  locale: pt
  section: Overview
  section_id: 15173289016593
  url: https://support.appsflyer.com/hc/pt/articles/10515748254609
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:**: acesse seus dados de custo e receita para entender seu ROI e ROAS.

![M_emptyState.png](https://files.readme.io/5eec5be77bf0b72afdd95b1957642cc67ba509000bc756ac68d87da5e96ed08e-11832563913489.png)

## Visão geral

O ROI360 é um conjunto de ferramentas exclusivas de relatórios de custos e receitas, fornecendo dados mais precisos, o mais rápido possível.

Combinando insights de custo e receita, você acessa uma visão completa do seu retorno do investimento em anúncios (ROAS) e retorno do investimento (ROI).

### Ferramentas de custo

Antes conhecidas como Xpend, as ferramentas do ROI360 agregam e relatam dados de custo. O conjunto completo de ferramentas e recursos de custo está detalhado na tabela a seguir. Clique nos links para saber mais sobre cada recurso.

<table><thead><tr><th>Ferramenta</th><th>Descrição</th></tr></thead><tbody><tr><td><a href="./roi360-cost-aggregation-overview" target="_blank">Attributed cost</a></td><td><p><span>Dados de custo vinculados a atribuição, cliques e impressões no nível mais granular disponível.</span></p><p><span>Isso inclui acesso a mais de 80 integrações de API, permitindo que você se conecte facilmente a ad networks globais ou locais.</span></p></td></tr><tr><td><a href="./import-cost-data" target="_blank">File import</a></td><td><span>Usa o Cost Import para registrar dados de custo que não são recebidos via API.</span></td></tr><tr><td><a href="./incorporate-agency-fees-into-campaign-costs" target="_blank">taxas de agência</a></td><td><span>Os cálculos de taxas de agência são incluídos no seu custo.</span></td></tr><tr><td><a href="./set-up-and-use-roi360-cost-etl-reports" target="_blank">Cost ETL\*</a></td><td>Fornece dados de custo de campanha, atualizados 4 vezes ao dia, para seu bucket AWS S3 ou GCS, prontos para serem enviados nos sistemas de BI do anunciante.</td></tr><tr><td colspan="2">\* Disponível com o pacote avançado do ROI360</td></tr></tbody></table>

**Atenção:** Você também pode agregar <Anchor target="_blank" href="/marketers/pt/docs/view-aggregated-cost-data-for-attribution-links">dados de custo relatados no link de atribuição</Anchor> sem o ROI360. No entanto, esse método está disponível apenas para o modelo de custo por instalação (CPI), não para outros modelos, como custo por aquisição (CPA), custo por clique (CPC) e custo por mil (CPM).

### Ferramentas de receita

As ferramentas de receita do ROI360 agregam e relatam dados de receita, levando em conta compras in-app, assinaturas e receita de anúncios. Impostos fiscais e comissões da loja de aplicativos também estão incluídos nas métricas de receita. O conjunto completo de ferramentas e recursos de custo está detalhado na tabela a seguir. Clique nos links para saber mais sobre cada recurso.

<table><thead><tr><th>Ferramenta</th><th>Descrição</th></tr></thead><tbody><tr><td><a href="./purchase-and-subscription-validation-overview" target="_blank">In-app purchases</a></td><td><span>Relatórios automáticos de compras in-app validadas, incluindo dados para transações de follow-up, como reembolsos ou cancelamentos.</span></td></tr><tr><td><a href="./purchase-and-subscription-validation-overview" target="_blank">Receita de assinaturas</a></td><td><span>Relatórios automáticos de assinaturas, incluindo alterações, cancelamentos e compartilhamento familiar.</span></td></tr><tr><td><a href="./roi360-guide-ad-revenue-attribution" target="_blank">Ad revenue</a></td><td>Acesso a mais de 20 parceiros de receita de anúncios que se conectam via API ou SDK e fornecem uma atualização de dados mais precisa.</td></tr><tr><td> <a href="./revenue-etl-reports" target="_blank">ETL de Receita</a>\*</td><td>Envio de dados de receita para seu bucket AWS S3 ou GCS prontos para upload nos sistemas de BI do anunciante.</td></tr><tr><td colspan="2">\* Disponível com o pacote avançado do ROI360</td></tr></tbody></table>

**Atenção:** também existem algumas ferramentas básicas de mensuração de receita que não estão incluídas no ROI360. Ao contrário das ferramentas do ROI360, essas ferramentas exigem uma quantidade substancial de configuração por parte de seus desenvolvedores:

* <Anchor target="_blank" href="/marketers/pt/docs/about-receipt-validation">Validação de recibo de compras in-app</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/purchase-and-subscription-validation-overview">Medição de receita de assinatura</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/roi360-revenue-attribution-overview">Registro de receita por meio de eventos in-app personalizados</Anchor>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01HKHGX9JJQQCKF9SDZRSCM1XJ=vis%C3%A3o-geral cost-tools=ferramentas-de-custo h_01HKHGX9JJRWDP9PMYP9CFA7MQ=ferramentas-de-custo revenue-tools=ferramentas-de-receita h_01HKHGX9JJFQ9ZM6J3B2D5G6C5=ferramentas-de-receita" />
