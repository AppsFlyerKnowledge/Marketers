---
title: Disponibilidade de dados agregados históricos
metadata:
  keywords:
    - Aggregated Data
    - Advertisers
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2023-05-24T08:38:43Z'
  edited_at: '2026-08-25T00:02:37Z'
  id: 15557418667537
  locale: pt
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/pt/articles/15557418667537
---
> **Em resumo:** Veja quais dados históricos estão disponíveis em diferentes dashboards e relatórios agregados do AppsFlyer.

<div id="historical-aggregate-data-availability" />

## Disponibilidade de dados agregados históricos

A tabela a seguir mostra até quanto tempo atrás os dados históricos estão disponíveis em diferentes dashboards e relatórios agregados do AppsFlyer.

A partir de 1º de abril de 2026, os dados agregados de LTV (incluindo cliques, impressões e instalações) serão retidos por 25 meses (2 anos + 1 mês), em vez de 5 anos. Consulte o <Anchor target="_blank" href="/marketers/pt/docs/bulletin-aggregated-ltv-data-availability">Boletim: Disponibilidade de dados agregados de LTV</Anchor> para mais detalhes.

<table><thead><tr><th>Método de relatório</th><th>Disponibilidade de dados históricos</th></tr></thead><tbody><tr><td>Dashboard de Visão Geral</td><td>25 meses (2 anos + 1 mês)</td></tr><tr><td>Master API</td><td><ul><li>Dados de LTV: 25 meses (2 anos + 1 mês)</li><li>Dados de coorte (coorte diária): 2 anos</li><li>Dados de atividade: 3 anos</li></ul></td></tr><tr><td><p>Extrair API</p><p>(relatórios agregados)</p></td><td>25 meses (2 anos + 1 mês)</td></tr><tr><td><p>Página de Export data</p><p>(relatórios agregados)</p></td><td>25 meses (2 anos + 1 mês)</td></tr><tr><td>Visão geral do SKAN</td><td>Dados de conversão mais antigos suportados: 1º de novembro de 2020</td></tr><tr><td>APIs de dados agregados do SKAN</td><td>Dados de conversão mais antigos suportados: 1º de novembro de 2020</td></tr><tr><td>Painel do Protect360</td><td>Os dados estão disponíveis desde o início da assinatura do Protect360</td></tr><tr><td>Dashboard de atividades</td><td><ul><li>3 anos</li><li>Aba de alto nível: 1 ano</li></ul></td></tr><tr><td>Recurso</td><td>25 meses (2 anos + 1 mês)</td></tr><tr><td>Retenção</td><td>2 anos</td></tr><tr><td>Painel de coorte</td><td><ul><li>Cohorts diárias: 2 anos</li><li>Coortes semanais/mensais: 3 anos</li></ul></td></tr><tr><td>API de Coorte</td><td>Cohorts diárias: 2 anos</td></tr><tr><td>Cohort Data Locker</td><td>Não é relevante\*</td></tr><tr><td>Painel Personalizado</td><td>25 meses (2 anos + 1 mês)</td></tr><tr><td>Relatórios de tabela dinâmica</td><td><ul><li>Dados de LTV: 25 meses (2 anos + 1 mês)</li><li>Dados de atividade: 3 anos</li></ul></td></tr><tr><td>ETL de custos</td><td>Não é relevante\*\*</td></tr><tr><td colspan="2"><p>\* Os relatórios do Data Locker são enviados diariamente com conversões, sessões e eventos gerados por usuários convertidos no último ano (3 anos na beta).</p><p>\*\* Os relatórios de custo do ETL são enviados várias vezes por dia. Eles fornecem dados de custo do dia atual e dos 6 dias anteriores (referidos como 7 dias neste artigo), bem como dos dias 14, 29 e 88. Os dados retroativos permitem atualizações e correções ao relatar os dados de custos.</p></td></tr></tbody></table>

<div data-zendesk-anchors="historical-aggregate-data-availability=disponibilidade-de-dados-agregados-hist%C3%B3ricos h_01KYPDRP64DHB3RN8E51NTGPFE=disponibilidade-de-dados-agregados-hist%C3%B3ricos" />
