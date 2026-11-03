---
title: >-
  Boletín: nueva API del SDK de ingresos por anuncios para AppsFlyer SDK versión
  6.15+
metadata:
  keywords:
    - Premium Feature
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-07-24T08:59:01Z'
  edited_at: '2026-10-20T03:55:27Z'
  id: 26956998859153
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/26956998859153
---
| **¿Qué hay de nuevo?** | Los ingresos publicitarios a nivel de impresión ahora están disponibles usando la API AdRevenue SDK en lugar del conector del SDK de ingresos publicitarios. |
| --- | --- |
| **A partir de** | AppsFlyer SDK versión 6.15 |
| **Lo que debes saber:** | <ul><li>Hasta ahora, los ingresos por anuncios a nivel de impresión estaban disponibles a través del **conector** del SDK de ingresos publicitarios de AppsFlyer. A partir de la fecha efectiva, la integración se realizará mediante el **SDK** de AppsFlyer en sí (no un conector), utilizando la API del SDK de ingresos publicitarios.</li><li>El conector del SDK de ingresos publicitarios seguirá funcionando con:<ul><li>AppsFlyer Android SDK versión 6.14.2 y anteriores.</li><li>AppsFlyer iOS SDK versión 6.14.6 y anteriores.</li></ul></li></ul> |
| **Lo que debes hacer** | <ul><li>Si deseas actualizar a AppsFlyer SDK versión 6.15+ y actualmente tienes implementado el conector del SDK de ingresos publicitarios, debes eliminar el conector e integrar la API AdRevenue SDK.</li><li>Se requiere un desarrollador. Consulta las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue">instrucciones para desarrolladores de la API del SDK de ingresos publicitarios</Anchor>.</li><li>Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/integrate-the-roi360-ad-revenue-sdk-api">integración de la API del SDK de ingresos publicitarios a nivel de impresión</Anchor>.</li></ul> |