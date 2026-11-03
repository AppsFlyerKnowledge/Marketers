---
title: 'Boletim: Relatórios da web+apps consolidados para Meta Ads e Google Ads'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2025-10-05T12:17:10Z'
  edited_at: '2026-08-18T00:19:21Z'
  id: 39686956300433
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/39686956300433
---
| Seção | Detalhes |
| --- | --- |
| **Novidades** | <ul><li>Todas as atribuições a `metaweb_int` agora serão registradas como `Facebook Ads`.</li><li>Todas as atribuições a `googleads_int` agora serão registradas como `googleadwords_int`.</li><li>A mudança afeta apenas as novas atribuições. As atribuições já existentes não sofrem alterações retroativas.</li><li>Essa mudança se aplica a todas as ferramentas de relatório, incluindo dashboards e exportações de dados brutos.</li><li>A tradução para a fonte de mídia "oficial" (exemplos: Facebook Ads; Google Adwords\_int) **ocorre automaticamente no backend**.</li><li>O custo total da web da Meta Web e do Google Web é registrado no dashboard e no Cost ETL sob o PID principal = `facebook_int` e `googleadwords_int`, respectivamente.</li></ul> |
| **Data de disponibilidade geral** | 02 de novembro de 2025 |
| **Por que isso é importante?** | Com a consolidação, você recebe relatórios holísticos de TODAS as suas campanhas de uma rede específica, como Meta ou Google, incluindo relatórios completos de custo do mobile e da web. |
| **O que você precisa fazer** | <ul><li>**Não há alteração no processo de configuração da campanha**. Continue usando os PIDs originais (`metaweb_int` e `googleads_int`). Eles garantem que a AppsFlyer direcione corretamente os postbacks por meio das integrações web apropriadas.</li><li>**Nas ferramentas de dados brutos:**<ul><li>O campo `original_url` ainda exibirá o PID original usado no anúncio.</li><li>Os campos de fonte de mídia da atribuição exibirão a nomenclatura atualizada.</li></ul></li><li>**Para ver o custo da web do Meta Web e do Google Web**, inclua o ID da campanha no link de atribuição.</li></ul> |
| **Práticas recomendadas** | <ul><li>Inclua o tipo de campanha nos nomes das campanhas para simplificar a classificação.</li><li>Para ativar os relatórios de custo completo para campanhas web, conecte sua conta de rede na aba "Custo" da respectiva integração principal (Facebook Ads ou googleadwords\_int).</li></ul> |
| **Suporte futuro** | <ul><li>A AppsFlyer planeja introduzir uma nova dimensão (`engagement_platform_group`) para indicar o tipo de campanha (web ou apps).</li><li>Os próximos PIDs para a integração da CAPI incluirão:</li></ul><ul><li>`snapweb_int` → mapeado para **snapchat\_int**</li><li>`tiktokweb_int` → mapeado para **tiktokglobal\_int**</li><li>`twitterweb_int` → mapeado para **Twitter**</li></ul>**<span id="h_01K6T5WZKJ2XP34V3T64TWG153"></span>Observação:**<br />Esses mapeamentos já estão ativos. Portanto, todas as atribuições usando os PIDs acima são automaticamente mapeadas para os PIDs principais das SRNs, mesmo antes do suporte completo à integração. |