---
title: 'Boletín: Apple Ads ahora ofrece soporte para la atribución de SKAN'
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2025-04-15T08:21:59Z'
  edited_at: '2026-10-20T03:54:42Z'
  id: 34395758837137
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/34395758837137
---
| **¿Qué hay de nuevo?** | Los postbacks de Apple Ads (AA) SKAN ahora se ingieren, procesan y reportan completamente por AppsFlyer, brindando a los marketers la misma medición segura para la privacidad que ya está disponible para otras redes. |
| --- | --- |
| **Fecha de actualización** | 10/04/2025 |
| **Lo que debes saber:** | A partir de **iOS 26.2**, los postbacks de Apple Ads se firman y se envían mediante **AdAttributionKit (AAK)** en lugar de **SKAdNetwork (SKAN)**.<br /><br />En **iOS 26.1 y versiones anteriores**, los postbacks de Apple Ads siguen usando SKAdNetwork.<br /><br />Para garantizar que AppsFlyer reciba todos los postbacks de Apple Ads, configura tu aplicación para enviar **copias de postback tanto de SKAdNetwork como de AdAttributionKit** a AppsFlyer, tal como se describe en la documentación para desarrolladores de Apple.<br /><br />**¿<span id="where-to-find-aa-skan-data"></span>Dónde encontrar datos de AA SKAN?**<ul><li>**Apr 10 2025 – May 26 2025:** Los datos se pueden encontrar en el reporte <Anchor target="_blank" href="/marketers/es/docs/skan-raw-data-reports#postback::315d5a62">reporte de copias de postback SKAN en bruto</Anchor> (Data Locker).</li><li>**From May 27 2025:** Los datos están disponibles en todos los dashboards de SKAN, APIs, exportaciones de Data Locker y SSOT.</li></ul>**Cambios en la atribución**: AA ahora puede recibir crédito por instalaciones que antes se atribuían a otras redes en SKAN.<br /><br />**<span id="data-granularity"></span>Granularidad de los datos:**<ul><li>Los postbacks de SKAN contienen solo campos estándar de SKAN. Los campos de campaña, adset, anuncio, geolocalización y enriquecimiento creativo son **NULL**.</li><li>**Asignación de placement (mediante** **skad\_campaign\_id**):</li><li>10 -> Resultados de la búsqueda</li><li>20 -> Pestaña de búsqueda</li><li>30 -> Pestaña Hoy</li><li>40 -> Páginas de productos</li></ul>**<span id="h_01JXYJ6B8FP8N79CVF84VNYQCR"></span>Nota:**<br />Apple solo compartirá información sobre la colocación del anuncio. Utilizarán el campo ID de campaña en los postbacks de SKAN para reflejar las cuatro colocaciones diferentes disponibles (Resultados de búsqueda, Pestaña de búsqueda, Pestaña de hoy y Páginas de productos). Esto significa que el ID de campaña real y el reporte a nivel de campaña no estarán disponibles.<ul><li>media\_source es **Apple Search Ads** y skad\_ad\_network\_id es **com.apple.ads**.</li></ul>**<span id="skan-versions-supported"></span>Versiones de SKAN compatibles:**<ul><li>AA es compatible con **SKAN 1.0–3.0**, solo con **atribución por clic**.</li><li>A partir de iOS 26.2, se usa AdAttributionKit (AAK).</li><li>Actualmente, view-through no es compatible.</li></ul>**Impacto en SSOT**: No hay cambios en la lógica de deduplicación. Las postbacks de AA que no están ya atribuidas por los métodos clásicos de AppsFlyer están incluidas, el resto se deduplican en SSOT. |
| **Lo que debes hacer** | Para activar los datos de AA SKAN en AppsFlyer, asegúrate de que tu aplicación esté configurada para <Anchor target="_blank" href="/marketers/es/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">reenviar los postbacks de SKAN y de Ad Attribution directamente desde Apple a AppsFlyer</Anchor>.<ul><li>Si tu aplicación ya está configurada, no se requiere ninguna acción adicional.</li></ul>Nota: Las aplicaciones deben estar en funcionamiento en iOS 15 o posterior para que esto funcione. Según Apple, más del 95% de los usuarios cumplen este requisito​. |

<div data-zendesk-anchors="h_01JXYJ7NFNJP83Z2J43841ZENJ=where-to-find-aa-skan-data h_01JXYJ7S61RSK8SV11Y7QGQ9XE=data-granularity h_01JXYJ7Z0ERWPH70A291CEFMH6=skan-versions-supported" />
