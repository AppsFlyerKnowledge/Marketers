---
title: 'Boletim: novos campos da Push API'
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
  edited_at: '2026-10-20T03:56:02Z'
  id: 20161752179601
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/20161752179601
---
| **Novidades** | Três novos campos foram adicionados à Push API. Os dados mostram:<ul><li>engagement\_type</li><li>event\_type</li><li>store\_product\_page (novo no Android)</li></ul>**<span id="engagement_type"></span>engagement\_type**<br /><br />O parâmetro pode retornar os seguintes valores: preload, click\_to\_download, click\_to\_app, engaged\_click, engaged\_view, view, listening ou, se não for reportado, ficará vazio<br /><br />Mais informações sobre os novos tipos de engajamento podem ser encontradas <Anchor target="_blank" href="/marketers/pt/docs/bulletin-engagement-types">aqui</Anchor>.<br /><br />**<span id="event_type"></span>event\_type**<br /><br />O parâmetro pode retornar os seguintes valores: install, organic-install, install-in-app-event, organic-install-in-app-event, re-engagement, re-engagement-in-app-event, re-attribution, reinstall, organic-reinstall, re-attribution-in-app-event, skad-installs, skad-re-downloads, skad-in-app-events, skad-postbacks, skad-postbacks-copy.<br /><br />**<span id="store_product_page"></span>store\_product\_page**<br /><br />Este parâmetro segue os valores atuais do iOS.<br /><br />Para mais informações, clique <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#attribution::4c11e393">aqui</Anchor>.<br /><br /><br /><br />**<span id="h_01HHEP7BBXF30VEK3XCSSK9GEE"></span>Importante!**<br />O campo **custom\_data** foi alterado para incluir dois-pontos entre o nome do campo e o valor do campo. |
| --- | --- |
| **Data de início** | 17 de janeiro de 2024 |
| **O que isso afeta** | Anunciantes e agências que usam a <Anchor target="_blank" href="/marketers/pt/docs/push-api-streaming-raw-data">push API</Anchor> |

<div data-zendesk-anchors="h_01HF9A6PNHDEQR9GVVW49ADB1E=engagement_type h_01HF9A6TA5Y3D485BFJ5FF42H6=event_type h_01HF9A6XV28CYDEPAZ352VY44K=store_product_page" />
