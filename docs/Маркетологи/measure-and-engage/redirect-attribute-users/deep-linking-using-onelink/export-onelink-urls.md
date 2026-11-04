---
title: Экспорт URL-адресов OneLink
metadata:
  keywords:
    - export
    - Marketers
    - download
    - Link Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2022-01-09T11:58:46Z'
  edited_at: '2026-10-03T00:17:02Z'
  id: 4416027813905
  locale: ru
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ru/articles/4416027813905
---
> **Краткий обзор.** Загрузите все URL-адреса OneLink, созданные в пользовательском интерфейсе AppsFlyer.

<div id="export-onelink-urls" />

## Экспорт URL-адресов OneLink

Загрузите CSV-файл со всеми URL-адресами OneLink, созданными в соответствии с шаблоном OneLink, с помощью настройки OneLink в пользовательском интерфейсе AppsFlyer. (URL-адреса OneLink, созданные с помощью SDK, API OneLink или массовой загрузки, не экспортируются).

CSV-файл содержит следующую информацию о каждой ссылке:

* Имя ссылки
* Медиа-источник
* Название кампании
* Короткий URL-адрес
* Длинный URL-адрес
* Дата последнего изменения/создания (ММ:ДД:ГГ ЧЧ:ММ)
* Изменено (электронная почта)

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR02eohAyUA2fsr9iGEb0UiZI8v45wH58KGo-45wajF4KNGuk_2S_cY1WW3UV8LwPRg-wm9bkMjvWyZ/pub?output=csv">Образец CSV</Anchor>

**Примечание**. Если ссылка изначально создается в пользовательском интерфейсе AppsFlyer, но затем параметры обновляются за пределами пользовательского интерфейса (с помощью API OneLink, электронной таблицы и т. д.), обновленные параметры не являются частью загруженного CSV-файла.

**Загрузка файла CSV**:

1. В AppsFlyer в боковом меню выберите **Вовлечение** > **Управление OneLink**.
2. Выберите шаблон OneLink, для которого вы хотите получить список ссылок.
3. Нажмите **Экспорт**.  
   Файл CSV загружается.

<div id="traits-and-limitations" />

### Спецификации и ограничения

| **Специфика** | **Специфика** |
| --- | --- |
| Агентства | Могут получить только те ссылки, которые они создали на основе шаблона OneLink. |
| Рекламодатели | Могут получить только те ссылки, которые они создали на основе шаблона OneLink. |

<div data-zendesk-anchors="export-onelink-urls=%D1%8D%D0%BA%D1%81%D0%BF%D0%BE%D1%80%D1%82-url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%BE%D0%B2-onelink h_01HKA1YMN4J2HAXWWF00252XC3=%D1%8D%D0%BA%D1%81%D0%BF%D0%BE%D1%80%D1%82-url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%BE%D0%B2-onelink traits-and-limitations=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HKA1YMN4P9AR949BFCSG93VY=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />
