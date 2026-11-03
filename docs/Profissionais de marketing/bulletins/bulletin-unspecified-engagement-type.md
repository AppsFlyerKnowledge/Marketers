---
title: 'Boletim: tipo de engajamento não especificado'
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
  created_at: '2024-12-09T15:17:50Z'
  edited_at: '2026-10-20T03:55:02Z'
  id: 30795194720785
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/30795194720785
---
| O que há de novo? | Para padronizar os relatórios quando `engagement_type` estiver ausente ou não corresponder, estamos introduzindo `click_unspecified` ou `impression_unspecified`como valores padrão em Relatórios de dados brutos e dashboards. |
| --- | --- |
| Qual é o impacto? | **Conversões**:  <br />A partir da data de vigência, o `engagement_type` não será mais reportado como vazio, mas assumirá por padrão `click_unspecified` ou `impression_unspecified`, dependendo do tipo de toque (ou seja, clique ou impressões).  <br />  <br />**Eventos in-app e sessões**:  <br />Os novos valores se aplicarão apenas a eventos in-app e sessões atribuídos a eventos de conversão registrados após a data de vigência. Aqueles atribuídos a eventos de conversão registrados antes da data de vigência permanecerão inalterados. |
| Data de entrada em vigor | Dezembro de 9,2024 |
| O que você deve saber | Todas as informações sobre o ETT podem ser encontradas na KB:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/about-enriched-engagement-types">Tipos de Envolvimento Enriquecido</Anchor></li><li><Anchor target="_blank" href="/partners/pt/docs/enriched-engagement-types-guide-for-ad-networks">Guia de Tipos de Envolvimento Enriquecido para Parceiros</Anchor></li></ul>Para ver o impacto imediato da introdução do EET, consulte o boletim:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/bulletin-enhanced-engagement-types-visibility">Visibilidade melhorada dos tipos de envolvimento</Anchor></li></ul> |