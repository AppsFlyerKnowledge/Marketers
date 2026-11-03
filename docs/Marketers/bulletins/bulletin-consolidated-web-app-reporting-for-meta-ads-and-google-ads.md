---
title: 'Boletín: reporte consolidado de Web+App para Meta Ads y Google Ads'
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
  edited_at: '2026-10-20T03:54:31Z'
  id: 39686956300433
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/39686956300433
---
| Sección. | Detalles |
| --- | --- |
| **¿Qué hay de nuevo?** | <ul><li>Cualquier atribución a `metaweb_int` ahora se reportará como `Facebook Ads`.</li><li>Cualquier atribución a `googleads_int` ahora se reportará como `googleadwords_int`.</li><li>El cambio solo afecta a las atribuciones nuevas. La atribución existente no se modifica de forma retroactiva.</li><li>Este cambio se aplica a todas las herramientas de reporte, incluidos los dashboards y las exportaciones de raw data.</li><li>La conversión a la fuente de medios «oficial» (por ejemplo, Facebook Ads, Google Adwords\_int) **se produce automáticamente en el back end**.</li><li>El costo web completo de Meta Web y Google Web se reporta en el dashboard y en Cost ETL con el PID principal = `facebook_int` y `googleadwords_int`, respectivamente.</li></ul> |
| **Fecha de disponibilidad general** | 02 de noviembre de 2025 |
| **¿Por qué debería importarte?** | La consolidación ofrece un reporte integral de TODAS tus campañas de una red específica, como Meta o Google, incluida la medición completa de costos para móvil y web. |
| **Lo que debes hacer** | <ul><li>**No hay cambios en el proceso de configuración de campañas**. Sigue usando los PID originales (`metaweb_int` y `googleads_int`). Así te aseguras de que AppsFlyer enrute los postbacks correctamente a través de las integraciones web correspondientes.</li><li>**En las herramientas de raw data:**<ul><li>el campo `original_url` seguirá mostrando el PID original usado en el anuncio,</li><li>los campos de fuente de medios de atribución reflejarán la nomenclatura actualizada.</li></ul></li><li>**Para obtener el costo web,** incluye el ID de campaña en el enlace de atribución para obtener el costo web de Meta Web y Google Web,</li></ul> |
| **Mejores prácticas** | <ul><li>Incluye el tipo de campaña en los nombres de las campañas para simplificar la clasificación.</li><li>Para habilitar el reporte completo de costos de las campañas web, conecta tu cuenta de la red en la pestaña «Costo» de la integración principal correspondiente (Facebook Ads, googleadwords\_int).</li></ul> |
| **Soporte futuro** | <ul><li>AppsFlyer tiene previsto incorporar una nueva dimensión (`engagement_platform_group`) para indicar el tipo de campaña (Aplicación o Web).</li><li>Los próximos PID para la integración de CAPI incluirán:</li></ul><ul><li>`snapweb_int` → asignado a **snapchat\_int**</li><li>`tiktokweb_int` → asignado a **tiktokglobal\_int**</li><li>`twitterweb_int` → asignado a **Twitter**</li></ul>**<span id="h_01K6T5WZKJ2XP34V3T64TWG153"></span>Nota**<br />Estas asignaciones ya están activas; cualquier atribución que utilice los PID anteriores se traduce automáticamente a los PID SRN principales, incluso antes de que haya soporte completo para la integración. |