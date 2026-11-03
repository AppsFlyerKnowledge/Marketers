---
title: Visibilidade melhorada dos tipos de envolvimento
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-10-29T15:52:59Z'
  edited_at: '2026-10-20T03:55:06Z'
  id: 29614354758545
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/29614354758545
---
| **O que há de novo?** | Os Tipos de Envolvimento Enriquecido (ETT) estarão disponíveis para todas as contas. |
| --- | --- |
| **Qual é o impacto?** | <ul><li>será relatado para todas as redes compatíveis (tanto redes de cliques como SRNs).</li><li>O parâmetro `engagement_type`  quando estiver ausente ou incompatível <Anchor target="_blank" href="/marketers/pt/docs/bulletin-unspecified-engagement-type">assumirá por padrão `click_unspecified` ou `impression_unspecified`</Anchor>.</li><li>As visualizações e cliques envolvidos terão <Anchor target="_blank" href="/marketers/pt/docs/about-enriched-engagement-types#attribution-model-with-enriched-engagement-types-beta">a mesma prioridade de atribuição</Anchor> que os cliques, assegurando consistência em todas as redes de anúncios.</li><li>Não haverá impacto na atribuição e na contagem de instalações.</li><li>(Apenas para <Anchor target="_blank" href="/marketers/pt/docs/about-enriched-engagement-types#networks-that-report-engagement-types">redes compatíveis que não sejam SRNs</Anchor>) Novos controlos deslizantes da janela de retrospeção (no separador Integração) para cliques e visualizações envolvidos, com um padrão de 7 dias.</li><li>Para networks compatíveis com SRN, a janela de lookback é obtida da janela de lookback de clique configurada na aba **Integração** do parceiro.</li><li>Pode visualizar a dimensão **Tipo de envolvimento** nos dashboards.</li><li>`engagement_type` será incluído nos relatórios de dados brutos se for escolhido pelo anunciante</li><li>As visualizações envolvidas são relatadas com `attributed_touch_type=impression` (também se aplica ao Google Ads)</li><li>A partir de 19 de novembro, pode haver uma mudança de cliques para visualizações engajadas.<ul><li>Uma redução em `attributed_touch_type=click`</li><li>/docs/about-enriched-engagement-types#enriched-engagement-types</li></ul></li><li>As visualizações engajadas são mensuradas e reportadas mesmo que a alternância **view-through** esteja desativada. Para identificar essas impressões como visualizações engajadas, use a métrica `engagement_type=engaged_view` em dashboards e relatórios de dados brutos, em vez de confiar apenas em `attributed_touch_type`.</li><li>As impressões totais incluem tanto visualizações engajadas quanto visualizações regulares. Para calcular o IPM, você deve subtrair **engaged views do total de impressões**, pois engaged views são um subconjunto das impressões, e contá-las duas vezes pode inflacionar a contagem de impressões.</li><li>As instalações sempre serão atribuídas ao tipo de toque mais forte. Se tanto a visualização quanto a visualização engajada estiverem sendo reportadas, a instalação será atribuída à visualização engajada (a visualização não será registrada como contribuinte, porque é da mesma campanha).</li></ul> |
| **Data de entrada em vigor** | 19 de novembro de 2024 |
| **Redes de anúncios suportadas** | Atualmente, apenas as redes autorizadas podem relatar tipos de envolvimento à AppsFlyer. |
| **O que precisa saber** | Todas as informações sobre o ETT podem ser encontradas na KB:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/about-enriched-engagement-types">Tipos de Envolvimento Enriquecido</Anchor></li><li><Anchor target="_blank" href="/partners/pt/docs/enriched-engagement-types-guide-for-ad-networks">Guia de Tipos de Envolvimento Enriquecido para Parceiros</Anchor></li></ul> |