---
title: 'Boletim: atualização dos dados de atividade na Master API e no Pivot'
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-08-17T07:26:26Z'
  edited_at: '2026-10-20T03:54:05Z'
  id: 49896622875537
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/49896622875537
---
| Secção | Atenção |
| --- | --- |
| Novidades | A Master API e o Pivot passarão a usar os mesmos dados de atividade que já alimentam o My Dashboards, o MCP da AppsFlyer, o AI Assistant e os agentes, para que as métricas de atividade correspondam em todos os lugares.<br /><br />Alguns valores subjacentes usados para filtrar e agrupar nos dados de atividade estão mudando. Veja abaixo os detalhes.<br /><br />A maioria dos clientes não precisa fazer nada. |
| Data de entrada em vigor | 15 de outubro de 2026 |
| Quem isso afeta | <ul><li>Todos os clientes da Master API e do Pivot que analisam métricas de atividade: `activity_average_dau`, `activity_average_dau_mau_rate`, `activity_average_arpdau`, `activity_sessions`, `activity_revenue`, `activity_event_counter_[event_name]`, `activity_sales_in_usd_[event_name]`, `activity_average_unique_users_[event_name]`.</li></ul>Atenção: `activity_average_mau` não é afetado.<ul><li>Cohort, LTV, retenção e outros tipos de dados não estão mudando. Se você combinar atividade com eles no mesmo relatório, alguns valores, especialmente canal de mídia / `pid`, podem não corresponder até que esses tipos de dados adotem as mesmas mudanças.</li></ul> |
| Ações necessárias | Essa mudança acontece automaticamente, e a maioria dos clientes não precisa fazer nada.<br /><br />Se você filtrar ou agrupar relatórios de atividade por qualquer valor listado abaixo, revise esses filtros após 15 de outubro de 2026. Valores antigos podem retornar resultados diferentes ou nenhum resultado. |
| O que você deve saber | Lembre-se das seguintes mudanças:<ul><li>**Os valores das métricas podem apresentar uma pequena variação após a atualização.** Os dados de atividade estão migrando para um novo pipeline de dados, então os valores das métricas podem mudar ligeiramente. Para usuários únicos, DAU e métricas relacionadas, espere uma diferença de até 3%. Isso é esperado como parte da mudança no pipeline, não é um erro de dados.</li><li>**"Pre-install" e "preload" agora são agrupados em "download"** para o agrupamento `attributed_touch_type`. Filtrar ou agrupar `attributed_touch_type` da Master API por "pre-install" ou "preload" não retorna mais resultados separados. Esse tráfego agora aparece em "download".</li><li>**Valores nulos são substituídos por strings vazias.** Isso inclui o canal de mídia orgânico/None (`pid` na Master API, canal de mídia no Pivot), que agora é exibido como uma string vazia.</li><li>**Dois nomes de canal de mídia estão mudando:** `facebook` passa a ser `Facebook Ads`, e `twitter` e `twitter_int` passam a ser `Twitter`. Todos os outros nomes de canal de mídia permanecem inalterados.</li><li>**Novos limites de truncamento de campo passam a valer:**<ul><li>`ad_id` (250 caracteres)</li><li>`ad_name` (256)</li><li>`event_name` (100)</li><li>`app_version` (64)</li><li>`agency` (32)</li><li>`keywords` (90)</li><li>`install_app_store` (50)</li><li>`os_version` (20)</li></ul></li></ul>Esta migração move os dados de atividade para uma infraestrutura mais moderna e escalável, o que melhora a confiabilidade e a performance e oferece suporte a futuras melhorias no produto. |