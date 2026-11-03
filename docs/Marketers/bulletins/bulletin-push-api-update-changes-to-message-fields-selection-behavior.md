---
title: >-
  Boletín: actualización de la Push API: cambios en el comportamiento de
  selección de «Campos del mensaje»
metadata:
  keywords:
    - Marketers
    - Raw Reports
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Raw Reports
  created_at: '2025-12-10T11:38:33Z'
  edited_at: '2026-10-20T03:54:28Z'
  id: 41785747996689
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/41785747996689
---
| Sección. | Detalles |
| --- | --- |
| **¿Qué hay de nuevo?** | El comportamiento del ajuste de configuración de Push API `selected_fields = "ALL FIELDS"`   cambia. Esta configuración dejará de actuar como un selector preparado para futuras actualizaciones. Solo se aplicará a los campos de mensaje que existan en el momento en que se guarda la configuración. Los nuevos campos añadidos posteriormente no se incluirán automáticamente.<br /><br />Este cambio aumenta la transparencia del esquema, brinda a los clientes un mayor control sobre sus pipelines y evita la expansión no planificada de campos. |
| **Fecha de entrada en vigor** | 30 de diciembre de 2025 |
| **Lo que debes saber:** | <ul><li>La configuración de la API Push se puede aplicar de las siguientes maneras:<ul><li>[Actualizar la configuración de la Push API mediante la API REST](https://dev.appsflyer.com/hc/reference/put_app-app-id):<ul><li>Establece la propiedad `select_fields` en ALL Fields</li></ul></li><li><Anchor target="_blank" href="/marketers/es/docs/push-api-streaming-raw-data#set-up-appsflyer-attribution-endpoint">En AppsFlyer, en Exportar -> Acceso a la API -> Push API o Push API (SKAN)</Anchor>:<ul><li>Selecciona el campo **Seleccionar todo**.</li></ul></li></ul></li><li>Al llamar a la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_app-app-id">API REST para obtener la configuración de la Push API</Anchor>, cuando `selected_fields = "ALL FIELDS"` está configurado, la llamada devolverá la lista explícita de campos seleccionados en lugar del genérico «all».</li></ul> |
| **Lo que debes hacer** | <ul><li>La mayoría de los clientes no necesitan realizar ninguna acción.</li><li>No hay cambios en los nombres de los campos ni en la semántica.</li><li>Los clientes deben actualizar manualmente su selección en AppsFlyer o a través de la REST API para recibir los nuevos campos.</li><li>Los clientes que utilizan "TODOS LOS CAMPOS" deben revisar periódicamente su configuración para asegurarse de que se incluyan los nuevos campos según sea necesario.</li></ul> |