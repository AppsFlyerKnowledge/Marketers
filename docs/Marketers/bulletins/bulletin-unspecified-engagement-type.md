---
title: 'Boletín: Tipo de engagement no especificado'
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
  edited_at: '2026-10-20T03:54:57Z'
  id: 30795194720785
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/30795194720785
---
| ¿Qué hay de nuevo? | Para estandarizar los reportes cuando falta `engagement_type` o no coincide, vamos a introducir `click_unspecified` o `impression_unspecified`como valores predeterminados en los Reportes de raw data y los dashboards. |
| --- | --- |
| ¿Cuál es el impacto? | **Conversiones**:  <br />A partir de la fecha de entrada en vigor, `engagement_type` ya no se reportará como vacío, sino que tendrá por defecto `click_unspecified` o `impression_unspecified`, según el tipo de Toque (es decir, clic o impresión).  <br />  <br />**Eventos in-app y sesiones**:  <br />Los nuevos valores solo se aplicarán a los eventos in-app y las sesiones atribuidos a eventos de conversión registrados después de la fecha de entrada en vigor. Los atribuidos a eventos de conversión registrados antes de la fecha de entrada en vigor no se verán afectados. |
| Fecha de entrada en vigor | Diciembre de 9,2024 |
| Lo que debes saber | Toda la información relacionada con EET se puede encontrar en la base de conocimientos:<ul><li><Anchor target="_blank" href="/marketers/es/docs/about-enriched-engagement-types">Tipos de Interacción Enriquecidos</Anchor></li><li><Anchor target="_blank" href="/partners/es/docs/enriched-engagement-types-guide-for-ad-networks">Guía de Tipos de Interacción Enriquecidos para Socios</Anchor></li></ul>Para conocer el impacto inmediato de la introducción de EET, consulta el boletín:<ul><li><Anchor target="_blank" href="/marketers/es/docs/bulletin-enhanced-engagement-types-visibility">Visibilidad mejorada de los tipos de interacción</Anchor></li></ul> |