---
title: 'Бюллетень: новые поля и значения в Data Locker и Push API'
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
  edited_at: '2026-10-19T14:39:54Z'
  id: 11135475316113
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/11135475316113
---
| **Что нового** | <ul><li>Отчеты SKAdNetwork через Data Locker и Push API включают следующие новые поля для поддержки SKAN 4:<ul><li>**skad\_postback\_sequence\_index**: Значение — целое число, которое представляет собой окно SKAN: `0`,`1` или `2`. Для SKAN 3 значение равно `0`.</li><li>**skad\_coarse\_conversion\_value**: Значение может быть `low`, `medium` или `high`. Для SKAN 3 значение равно `null`.</li><li>**skad\_source\_identifier**: Значение — строка до 4 цифр. Для SKAN 3 значение равно `null`</li><li>**skad\_source\_domain**: Значение — это строка, которая представляет собой источник атрибутируемой веб-рекламы. Для SKAN 3 значение равно `null`</li><li>**ad\_network\_creative**: Значение — это строка на основе обогащении данных, полученных от рекламной сети. Для SKAN 3 значение равно `null`</li></ul></li><li>Если медиаисточник — Meta ads, во всех отчетах отображается значение `Facebook Ads` (а не Facebook).</li></ul> |
| --- | --- |
| **Дата вступления в силу** | Изменения в схеме отчетов от 9 января 2023 г. Заполнение данных в этих полях начнется в рамках релиза AppsFlyer SKAN 4 (скоро). |
| **Где** | Затронуты следующие отчеты:<ul><li>Новые поля SKAN 4:<ul><li>**skad\_installs** (через Data Locker и Push API)</li><li>**skad\_redownloads** (через Data Locker и Push API)</li><li>**skad\_inapps** (через Data Locker и Push API)</li><li>**skad\_postbacks** (через Data Locker)</li><li>**skad\_postbacks\_copy** (не включает поле ad\_network\_creative) (через Data Locker)</li><li><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQJzfkXrrdYU15SkRoEx2HlgezlNar76MHFMP1JWqNnGrtYuHFNz4Mf8u0diflSx-5-k0zfsMEzsuLS/pub?output=xlsx">См. примеры схем отчетов</Anchor></li></ul></li><li>Медиаисточник Meta ads: Все отчеты</li></ul> |