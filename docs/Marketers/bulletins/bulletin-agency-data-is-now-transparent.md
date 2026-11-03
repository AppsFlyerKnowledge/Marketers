---
title: '[Boletín] Los datos de agencia ya son transparentes'
metadata:
  keywords:
    - Marketers
    - Platform essentials
    - Agencies
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2025-01-23T11:20:37Z'
  edited_at: '2026-10-20T03:54:45Z'
  id: 32048747169553
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/32048747169553
---
| **¿Qué hay de nuevo?** | Todas las agencias son ahora transparentes. Este cambio mejora tu capacidad para analizar y optimizar tus inversiones en marketing con mayor granularidad. |
| --- | --- |
| **Fecha de actualización** | 12 de marzo de 2025 |
| **Lo que debes saber:** | **Antes del cambio**: Para las agencias no transparentes, el campo fuente de medios mostraba el nombre de la agencia, en lugar de la ad network específica.<br /><br />**Después del cambio**:<ul><li>Todos los datos de campaña gestionados por la agencia serán totalmente visibles para ti hasta el nivel de fuente de medios, independientemente de la configuración de transparencia anterior. Es decir, el campo de fuente de medios mostrará la ad network específica, en lugar del nombre de la agencia. Seguirás pudiendo agrupar los datos por agencia.</li><li>Dashboards: Los datos históricos de las agencias también serán transparentes.</li><li>Reportes: Los datos de los reportes recibidos antes del cambio no se actualizarán. Por ejemplo, los reportes escritos en Data Locker antes de la actualización incluirán datos no transparentes de la agencia, pero los reportes escritos después de la actualización mostrarán datos transparentes de la agencia.</li><li>Las normas de validación de Protect360 definidas para "agencias no transparentes" se reclasificarán para "Agencias". Las normas seguirán funcionando sin problemas en el framework de la agencia transparente actualizada, con todos los demás ajustes definidos.</li><li>Si estás trabajando con datos de costos notificados antes del cambio, es posible que veas el costo agregado dividido en varias líneas: una bajo el nombre de la agencia anterior (antes del cambio) y otra bajo la fuente de medios (después del cambio). En este caso, deberás sustituir los datos de costos anteriores a la modificación por los datos posteriores a la modificación.</li></ul> |
| **Lo que debes hacer** | Si tienes flujos de trabajo internos que dependen del actual "nombre de la agencia" presentado como fuente de medios para las agencias no transparentes, revisa estos flujos de trabajo y considera la posibilidad de actualizarlos para adaptarlos a este cambio.<br /><br />Por ejemplo, en los dashboards, agrupa los datos por fuente de medios o agencia. Y en los reportes, usa los campos `media_source` o `af_prt`, según sea necesario. |