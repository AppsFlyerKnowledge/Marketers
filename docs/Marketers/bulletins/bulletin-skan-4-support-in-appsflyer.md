---
title: 'Boletín: Soporte de SKAN 4 en AppsFlyer'
metadata:
  keywords:
    - iOS
    - Marketers
    - SKAN
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2023-01-05T12:36:02Z'
  edited_at: '2026-10-20T03:56:13Z'
  id: 11938810583825
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/11938810583825
---
| **Título** | La solución SKAdNetwork de AppsFlyer ahora es compatible con SKAN 4. Esto incluye cambios importantes en SKAN Conversion Studio, así como en los dashboards y los reportes de SKAN. |
| --- | --- |
| **Fecha de entrada en vigor** | <ul><li>15 de febrero de 2023: con SDK nativo de iOS V6.10+</li><li>Te recomendamos actualizar a la versión más reciente V6.12+ aunque estés usando V6.10 desde febrero.<ul><li>Puedes ver la lista de cambios <Anchor target="_blank" href="/marketers/es/docs/appsflyer-ios-sdk-release-notes">aquí</Anchor></li></ul></li><li>Próximamente: soporte para otros SDK y plugins de AppsFlyer</li></ul> |
| **Prerrequisitos** | Para que los datos de SKAN 4 de iOS se registren correctamente, se requiere lo siguiente:<ul><li><Anchor target="_blank" href="/marketers/es/docs/appsflyer-ios-sdk-release-notes">SDK de AppsFlyer versión V6.12.1+</Anchor></li><li>La red de publicidad debe generar una firma de publicidad para SKAdNetwork V4.</li><li>Para los anuncios que se muestran en una aplicación, la aplicación debe estar creada con el SDK de iOS 16.1 o posterior.</li><li>Para los anuncios web, el anuncio requiere Safari 16.1 o posterior.</li><li>La aplicación anunciada debe estar firmada por el App Store y estar ejecutándose en un dispositivo con iOS 16.1 o posterior.</li></ul> |
| **Acciones requeridas** | <ul><li>Actualiza tu <Anchor target="_blank" href="/marketers/es/docs/appsflyer-ios-sdk-release-notes">SDK de AppsFlyer a la versión V6.12.1+</Anchor></li><li>En AppsFlyer SKAN Conversion Studio, actualiza al <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#skan-4">modo de medición de SKAN 4</Anchor> y configura los CV para las 3 ventanas de SKAN (o mantén la configuración predeterminada).</li></ul>**Nota:** Una vez que actualices a SKAN 4:<ul><li>El temporizador de actividad para las instalaciones anteriores a SKAN 4 es de 48 horas.</li><li>No se puede volver a una versión anterior de SKAN.</li></ul> |
| **Cambios en <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#skan-4">SKAN Conversion Studio</Anchor>** | Nuevo modo de medición de SKAN 4 para configurar las 3 ventanas de SKAN. |
| **Cambios en los <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">dashboards</Anchor>** | <ul><li>El Dashboard general de SKAN incluye nuevos campos (disponibles en la configuración de la tabla) para el recuento de eventos y los ingresos durante las 3 ventanas de SKAN:<ul><li>Recuento de eventos D0-D2</li><li>Recuento de eventos D0-D2 (modelado)</li><li>Recuento de eventos D3-D7</li><li>Recuento de eventos D8-D35</li><li>Ingresos D0-D2 ($)</li><li>Ingresos D0-D2 ($) (modelado)</li><li>Ingresos D3-D7 ($)</li><li>Ingresos D8-D35 ($)</li></ul></li><li>La vista del panel de control de SSOT muestra los campos de datos D2, en lugar de la ventana de actividad (AW). Para los datos de SKAN 3, este campo muestra todos los datos de la ventana de actividad, incluso si la ventana es superior o inferior a 2 días.</li></ul> |
| **Cambios en los <Anchor target="_blank" href="/marketers/es/docs/skan-raw-data-reports">reportes</Anchor>** | <ul><li>Los reportes de SKAdNetwork incluyen los siguientes campos nuevos para dar soporte a SKAN 4:<ul><li>**skad\_postback\_sequence\_index**: El valor es un integer que representa la ventana de SKAN, ya sea `0`, `1` o `2`. Para SKAN 3, el valor es `0`.</li><li>**skad\_coarse\_conversion\_value**: El valor puede ser `low`, `medium` o `high`. Para SKAN 3, el valor es `null`.</li><li>**skad\_source\_identifier**: El valor es una cadena de hasta 4 dígitos. Para SKAN 3, el valor es `null`.</li><li>**skad\_source\_domain**: El valor es una cadena que representa la fuente de los anuncios web atribuibles. Para SKAN 3, el valor es `null`.</li><li>**ad\_network\_creative**: el valor es un string basado en el enriquecimiento de datos recibido del ad network. Para SKAN 3, el valor está vacío.</li></ul></li><li>Los siguientes reportes de Data Locker y Push API se ven afectados:</li></ul><ul><li>**skad\_installs** (a través de Data Locker y la API Push)</li><li>**skad\_redownloads** (a través de Data Locker y la API Push)</li><li>**skad\_inapps** (a través de Data Locker y la API Push)</li><li>**skad\_postbacks** (a través de Data Locker)</li><li>**skad\_postbacks\_copy** (no incluye el campo ad\_network\_creative) (a través de Data Locker)</li><li><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQJzfkXrrdYU15SkRoEx2HlgezlNar76MHFMP1JWqNnGrtYuHFNz4Mf8u0diflSx-5-k0zfsMEzsuLS/pub?output=xlsx">Ver ejemplos de esquemas de reporte</Anchor></li></ul><ul><li>La API de fecha de llegada del postback agregado de SKAN y la API del reporte de estadísticas agregadas de rendimiento de SKAN contienen campos de SKAN 4. **Nota**: Debes usar la ruta para el token de API V2 para SKAN 4.</li></ul> |