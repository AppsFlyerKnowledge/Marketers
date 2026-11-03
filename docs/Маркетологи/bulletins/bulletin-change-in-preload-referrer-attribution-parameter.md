---
title: 'Бюллетень: Изменение параметра атрибуции рефереров предварительной загрузки'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2023-11-15T10:47:47Z'
  edited_at: '2023-12-11T12:09:31Z'
  id: 20161765461009
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/20161765461009
---
| **Что нового?** | Параметры атрибуции реферера предварительной загрузки новых установок, а также внутренних событий и сессий приложения, атрибутированных новым установкам, которые были зарегистрированы после даты вступления изменений в силу, будут отражаться иначе.<br /><br />Ниже указаны изменения в параметре атрибуции реферера предварительной загрузки:<ul><li>в поле **attributed\_touch\_type** будет указываться **download** (вместо preload или click\_to\_download);<ul><li>в поле **engagement\_type** будет указываться **preload** (для типа соответствия preload\_rfr) или **click\_to\_download** (для типа соответствия af\_referrer).</li></ul></li></ul>Внутренние события и сессии приложения, атрибутированные установкам, зафиксированным до даты вступления изменений в силу, будут следовать правилам, действующим на данный момент:<ul><li>в поле **attributed\_touch\_type** будет указываться **preload** или **click\_to\_download**;<ul><li>в поле **engagement\_type** будет указываться **empty** (нет значения).</li></ul></li></ul> |
| --- | --- |
| **Дата вступления в силу** | 17 января 2024 года |
| **На что это влияет** | <ul><li>Рекламодатели и агентства, использующие <Anchor target="_blank" href="/marketers/ru/docs/set-up-appsflyer-preload-referrer-attribution">атрибуцию рефереров предварительной загрузки AppsFlyer</Anchor>;</li><li>Где будут изменения: отчёты с сырыми данными и дэшборды.</li></ul> |