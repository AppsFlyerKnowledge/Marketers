---
title: 'Boletín: actualización de los datos de actividad en Master API y Pivot'
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-08-17T07:26:26Z'
  edited_at: '2026-10-20T03:54:04Z'
  id: 49896622875537
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/49896622875537
---
| Sección. | Detalles |
| --- | --- |
| Novedades | Master API y Pivot pasarán a usar los mismos datos de actividad que ya impulsan My Dashboards, el MCP de AppsFlyer, el Asistente de IA y los agentes, de modo que las métricas de actividad coincidan en todos los lugares.<br /><br />Algunos valores subyacentes que se usan para filtrar y agrupar en los datos de actividad están cambiando. Consulta los detalles a continuación.<br /><br />La mayoría de los clientes no necesitan hacer nada. |
| Fecha de entrada en vigor | 15 de octubre de 2026 |
| A quiénes afecta | <ul><li>Todos los clientes de Master API y Pivot que analizan métricas de actividad: `activity_average_dau`, `activity_average_dau_mau_rate`, `activity_average_arpdau`, `activity_sessions`, `activity_revenue`, `activity_event_counter_[event_name]`, `activity_sales_in_usd_[event_name]`, `activity_average_unique_users_[event_name]`.</li></ul>Nota: `activity_average_mau` no se ve afectada.<ul><li>Cohorte, LTV, Retención y otros tipos de datos no están cambiando. Si combinas actividad con ellos en el mismo reporte, es posible que algunos valores, especialmente la fuente de medios / `pid`, no coincidan hasta que esos tipos de datos adopten los mismos cambios.</li></ul> |
| Acciones requeridas | Este cambio se aplica automáticamente y la mayoría de los clientes no tienen que realizar ninguna acción.<br /><br />Si filtras o agrupas reportes de actividad por cualquier valor que se indica a continuación, revisa esos filtros después del 15 de octubre de 2026. Los valores antiguos pueden devolver resultados distintos o ningún resultado. |
| Lo que debes saber | Ten en cuenta los siguientes cambios:<ul><li>**Los valores de las métricas pueden mostrar pequeñas variaciones después de la actualización.** Los datos de actividad pasarán a una nueva canalización de datos, por lo que los valores de las métricas pueden variar ligeramente. En el caso de Usuarios únicos, DAU y métricas relacionadas, puedes esperar una diferencia de hasta un 3%. Esto es lo esperado como parte del cambio en la canalización, no un error en los datos.</li><li>**"Pre-install" y "preload" ahora se agrupan en "download"** para la agrupación `attributed_touch_type`. Filtrar o agrupar `attributed_touch_type` de Master API por «pre-install» o «preload» ya no devuelve resultados por separado. Ese tráfico ahora aparece en "download".</li><li>**Los valores nulos se sustituyen por strings vacíos.** Esto incluye la fuente de medios orgánica/None (`pid` en Master API, fuente de medios en Pivot), que ahora se procesa como un string vacío.</li><li>**Están cambiando dos nombres de fuentes de medios:** `facebook` pasa a ser `Facebook Ads`, y `twitter` y `twitter_int` pasan a ser `Twitter`. El resto de los nombres de fuentes de medios no cambia.</li><li>**Se aplican nuevos límites de truncamiento de campos:**<ul><li>`ad_id` (250 caracteres)</li><li>`ad_name` (256)</li><li>`event_name` (100)</li><li>`app_version` (64)</li><li>`agency` (32)</li><li>`keywords` (90)</li><li>`install_app_store` (50)</li><li>`os_version` (20)</li></ul></li></ul>Esta migración traslada los datos de actividad a una infraestructura más moderna y escalable, lo que mejora la fiabilidad y el rendimiento, y permite futuras mejoras del producto. |