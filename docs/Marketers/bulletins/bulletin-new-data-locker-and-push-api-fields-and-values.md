---
title: 'Boletín: nuevos campos y valores de Data Locker y de Push API'
metadata:
  keywords:
    - Data Locker
    - Marketers
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2022-12-04T20:34:01Z'
  edited_at: '2026-10-20T03:56:18Z'
  id: 11135475316113
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/11135475316113
---
| **¿Qué hay de nuevo?** | <ul><li>Los reportes de SKAdNetwork a través de Data Locker y Push API incluyen nuevos campos para dar soporte a SKAN 4:<ul><li>**skad\_postback\_sequence\_index**: El valor es un número entero que representa la ventana de SKAN: `0`, `1` o `2`. Para SKAN 3, el valor es `0`.</li><li>**skad\_coarse\_conversion\_value**: El valor puede ser `low`, `medium` o `high`. Para SKAN 3, el valor es `null`.</li><li>**skad\_source\_identifier**: El valor es una cadena de hasta 4 dígitos. Para SKAN 3, el valor es `null`.</li><li>**skad\_source\_domain**: El valor es una cadena que representa la fuente de los anuncios web atribuibles. Para SKAN 3, el valor es `null`.</li><li>**ad\_network\_creative**: El valor es una cadena basada en el enriquecimiento de datos recibido de la ad network. Para SKAN 3, el valor es `null`.</li></ul></li><li>Cuando la fuente de medios es Meta ads, todos los reportes muestran el valor `Facebook Ads` (no Facebook).</li></ul> |
| --- | --- |
| **Fecha de entrada en vigor** | Cambios en el esquema de reportes el 9 de enero de 2023. La carga de datos de esos campos comienza como parte del lanzamiento de AppsFlyer SKAN 4 (próximamente). |
| **Donde** | Se ven afectados los siguientes reportes:<ul><li>Nuevos campos de SKAN 4:<ul><li>**skad\_installs** (a través de Data Locker y Push API)</li><li>**skad\_redownloads** (a través de Data Locker y Push API)</li><li>**skad\_inapps** (a través de Data Locker y Push API)</li><li>**skad\_postbacks** (a través de Data Locker)</li><li>**skad\_postbacks\_copy** (no incluye el campo ad\_network\_creative) (a través de Data Locker)</li><li><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQJzfkXrrdYU15SkRoEx2HlgezlNar76MHFMP1JWqNnGrtYuHFNz4Mf8u0diflSx-5-k0zfsMEzsuLS/pub?output=xlsx">Ver ejemplos de esquemas de reporte</Anchor></li></ul></li><li>Fuente de medios de Meta ads: Todos los reportes</li></ul> |