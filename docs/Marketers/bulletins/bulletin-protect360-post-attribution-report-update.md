---
title: 'Boletín: actualización del reporte posterior a la atribución de Protect360'
metadata:
  keywords:
    - Pull API
    - Advertisers
    - Protect360
    - Raw Data
    - Marketers
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-11-25T11:39:55Z'
  edited_at: '2026-10-20T03:57:04Z'
  id: 360015900018
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/360015900018
---
| **¿Qué hay de nuevo?** | Los reportes posteriores a la atribución de Protect360 muestran el colaborador válido (fuente de medios) para las instalaciones secuestradas y los eventos in-app. Es decir, el colaborador que originalmente debería haber recibido la atribución. |
| --- | --- |
| **Fecha de entrada en vigor** | 23 de noviembre de 2020 |
| **Donde** | Reportes de raw data posteriores a la atribución de Protect360 disponibles a través de:<ul><li>Exportar datos (descarga): reportes de raw data</li><li>Reportes de raw data de Pull API</li></ul> |
| **Qué** | <ul><li>Hasta ahora, los reportes posteriores a la atribución no mostraban la fuente de medios del colaborador válido. Los campos **contributor[1-3]** y **organic** mostraban las fuentes de medios colaboradoras, pero no permitían saber cuál de ellas justificaba la atribución.</li><li>A partir del 23 de noviembre de 2020, el valor del campo **rejected\_reason\_value** muestra **contributor[1-3]** o **organic**.<ul><li>En Data Locker, se muestra como **validation\_reason\_value**.</li></ul></li><li>Los anunciantes pueden consultar los campos **contributor[1-3]** para ver cuál debería ser la fuente de medios atribuida y usar esta información para conciliar.<ul><li>Si los campos del colaborador no aparecen en tu reporte, puedes añadirlos desde la página **Export data**.</li></ul></li></ul> |

<div id="see-also" />

> 📄 **Consulte también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports#postattribution-reports">Reportes posteriores a la atribución:</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports#pull-api">Reportes de Pull API</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#protect360::440536f1">Rejected\_reason\_value</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#attribution::f1c497c7">Contributor[1-3]</Anchor>
> * Novedades en AppsFlyer

<div data-zendesk-anchors="h_01HDPEGXJSMW6Q9DXA89AZ20T6=consulte-tambi%C3%A9n" />
