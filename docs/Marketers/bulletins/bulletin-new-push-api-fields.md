---
title: 'Boletín: nuevos campos de Push API'
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
  created_at: '2023-11-15T10:46:08Z'
  edited_at: '2026-10-20T03:55:58Z'
  id: 20161752179601
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/20161752179601
---
| **¿Qué hay de nuevo?** | Se han añadido tres campos nuevos a la Push API. Estos son:<ul><li>engagement\_type</li><li>tipo\_de\_evento</li><li>store\_product\_page (nuevo para Android)</li></ul>**<span id="engagement_type"></span>engagement\_type**<br /><br />El parámetro puede devolver los siguientes valores: precarga, click\_to\_download, click\_to\_app, engaged\_click, engaged\_view, vista, listening, o si no se reporta estará vacío<br /><br />Puedes encontrar más información sobre los nuevos tipos de engagement <Anchor target="_blank" href="/marketers/es/docs/bulletin-engagement-types">aquí</Anchor>.<br /><br />**<span id="event_type"></span>tipo\_de\_evento**<br /><br />El parámetro puede devolver los siguientes valores: install, organic-install, install-in-app-event, organic-install-in-app-event, re-engagement, re-engagement-in-app-event, re-attribution, reinstall, organic-reinstall, re-attribution-in-app-event, skad-installs, skad-re-downloads, skad-in-app-events, skad-postbacks, skad-postbacks-copy.<br /><br />**<span id="store_product_page"></span>store\_product\_page**<br /><br />Este parámetro sigue los valores actuales de iOS.<br /><br />Para más información, haz clic aquí: <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#attribution::4c11e393">aquí</Anchor>.<br /><br /><br /><br />**<span id="h_01HHEP7BBXF30VEK3XCSSK9GEE"></span>Nota:**<br />El campo **custom\_data** se ha modificado para incluir dos puntos entre el nombre del campo y el valor del campo. |
| --- | --- |
| **Fecha de entrada en vigor** | 17 de enero de 2024 |
| **Esto afecta a** | Anunciantes y agencias que utilizan la <Anchor target="_blank" href="/marketers/es/docs/push-api-streaming-raw-data">push API</Anchor> |

<div data-zendesk-anchors="h_01HF9A6PNHDEQR9GVVW49ADB1E=engagement_type h_01HF9A6TA5Y3D485BFJ5FF42H6=event_type h_01HF9A6XV28CYDEPAZ352VY44K=store_product_page" />
