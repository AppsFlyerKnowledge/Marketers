---
title: 'Бюллетень: новые поля Push API'
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
  edited_at: '2026-10-19T14:39:33Z'
  id: 20161752179601
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/20161752179601
---
| **Что нового?** | В Push API добавлены три новых поля. К ним относятся:<ul><li>SDK (пакет средств разработки ПО)</li><li>Местоположение устройства</li><li>store\_product\_page (новое для Android)</li></ul>**<span id="engagement_type"></span>SDK (пакет средств разработки ПО)**<br /><br />Параметр может возвращать следующие значения: preload (предварительная загрузка), click\_to\_download (от клика к скачиванию), click\_to\_app (от клика в приложение), engaged\_click (клик взаимодействия), engaged\_view (просмотр взаимодействия), view (просмотр), listening (прослушивание), или, если не сообщается, он будет пуст.<br /><br />Подробнее о новых типах вовлеченности можно узнать <Anchor target="_blank" href="/marketers/ru/docs/bulletin-engagement-types">здесь</Anchor>.<br /><br />**<span id="event_type"></span>Местоположение устройства**<br /><br />Параметр может возвращать следующие значения: install, organic-install, install-in-app-event, organic-install-in-app-event, re-engagement, re-engagement-in-app-event, re-attribution, reinstall, organic-reinstall, re-attribution-in-app-event, skad-installs, skad-re-downloads, skad-in-app-events, skad-postbacks, skad-postbacks-copy.<br /><br />**<span id="store_product_page"></span>Атрибуция**<br /><br />Этот параметр соответствует текущим значениям iOS.<br /><br />Для получения дополнительной информации нажмите <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary#attribution::4c11e393">здесь</Anchor>.<br /><br /><br /><br />**<span id="h_01HHEP7BBXF30VEK3XCSSK9GEE"></span>Примечание**<br />Поле **custom\_data** изменено: теперь между именем поля и его значением ставится двоеточие. |
| --- | --- |
| **Дата вступления в силу** | 17 января 2024 года |
| **На что это влияет** | Рекламодатели и агентства, использующие <Anchor target="_blank" href="/marketers/ru/docs/push-api-streaming-raw-data">Push API</Anchor> |

<div data-zendesk-anchors="h_01HF9A6PNHDEQR9GVVW49ADB1E=engagement_type h_01HF9A6TA5Y3D485BFJ5FF42H6=event_type h_01HF9A6XV28CYDEPAZ352VY44K=store_product_page" />
