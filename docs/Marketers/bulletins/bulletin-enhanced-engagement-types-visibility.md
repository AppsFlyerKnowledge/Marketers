---
title: 'Boletín: visibilidad mejorada de los tipos de engagement'
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
  edited_at: '2026-10-20T03:55:02Z'
  id: 29614354758545
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/29614354758545
---
| **¿Qué hay de nuevo?** | Los tipos de engagement enriquecidos (EET) estarán visibles para TODAS las cuentas. |
| --- | --- |
| **¿Cuál es el impacto?** | <ul><li>Los tipos de engagement se reportarán para todas las redes compatibles (tanto redes de clic como SRN).</li><li>El parámetro `engagement_type` cuando falte o no coincida <Anchor target="_blank" href="/marketers/es/docs/bulletin-unspecified-engagement-type">tomará por defecto `click_unspecified` o `impression_unspecified`</Anchor>.</li><li>Las vistas comprometidas y los clics comprometidos tendrán <Anchor target="_blank" href="/marketers/es/docs/about-enriched-engagement-types#attribution-model-with-enriched-engagement-types-beta">la misma prioridad de atribución</Anchor> que los clics, lo que garantiza la coherencia en todas las ad networks.</li><li>Sin impacto en la atribución ni en el número de instalaciones.</li><li>(Solo para redes compatibles que no sean SRN <Anchor target="_blank" href="/marketers/es/docs/about-enriched-engagement-types#networks-that-report-engagement-types">supporting networks</Anchor>) Nuevos controles deslizantes de ventana de lookback (en la pestaña de integración) para clics comprometidos y vistas comprometidas, con un valor predeterminado de 7 días para las integraciones existentes y de 2 días para las nuevas integraciones.</li><li>Para las redes compatibles con SRN, la ventana de lookback se toma de la ventana de lookback de clics configurada en la pestaña **Integration** del partner.</li><li>Puedes ver la dimensión **Engagement type** en los dashboards.</li><li>`engagement_type` se incluye en los reportes de raw data si lo selecciona el anunciante</li><li>Las vistas comprometidas se reportan con `attributed_touch_type=impression` (también se aplica a Google Ads y TikTok)</li><li>A partir del 19 de noviembre, puede producirse un cambio de los clics a las vistas comprometidas.<ul><li>Una disminución de `attributed_touch_type=click`</li><li>Un aumento de `attributed_touch_type=impression`</li></ul></li><li>Las vistas comprometidas se miden y se reportan incluso si el interruptor de **view-through** está desactivado. Para identificar esas impresiones como vistas comprometidas, utiliza la métrica `engagement_type=engaged_view` en los dashboards y los reportes de raw data en lugar de basarte únicamente en `attributed_touch_type`.</li><li>Las impresiones totales incluyen tanto las vistas comprometidas como las vistas normales. Para calcular el IPM, debes **restar las vistas comprometidas de las impresiones totales** porque las vistas comprometidas son un subconjunto de las impresiones y contarlas dos veces inflaría el recuento de impresiones.</li><li>Las instalaciones siempre se atribuirán al tipo de toque más fuerte. Si se reportan tanto una vista como una vista comprometida, la instalación se atribuirá a la vista comprometida (la vista no se registrará como colaboradora, porque procede de la misma campaña).</li></ul> |
| **Fecha de entrada en vigor** | Noviembre de 2024 |
| **Redes publicitarias compatibles** | Actualmente, solo las redes permitidas pueden reportar tipos de interacción a AppsFlyer. |
| **Lo que debes saber** | Toda la información relacionada con EET se puede encontrar en la base de conocimientos:<ul><li><Anchor target="_blank" href="/marketers/es/docs/about-enriched-engagement-types">Tipos de Interacción Enriquecidos</Anchor></li><li><Anchor target="_blank" href="/partners/es/docs/enriched-engagement-types-guide-for-ad-networks">Guía de Tipos de Interacción Enriquecidos para Socios</Anchor></li></ul> |