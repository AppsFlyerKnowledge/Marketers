---
title: 'Уведомление: обновление Push API — изменения в выборе полей сообщений.'
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
  created_at: '2025-12-10T11:38:33Z'
  edited_at: '2026-10-19T14:38:07Z'
  id: 41785747996689
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/41785747996689
---
| Раздел | Подробности |
| --- | --- |
| **Что нового** | Поведение параметра конфигурации Push API `selected_fields = "ALL FIELDS"` изменяется. Этот параметр больше не будет автоматически учитывать поля, добавленные в будущем. Настройка применяется только к тем полям сообщения, которые существуют на момент сохранения конфигурации. Новые поля, добавленные после сохранения, не включаются автоматически.<br /><br />Это изменение увеличивает прозрачность схемы, дает клиентам лучший контроль над их потоками данных и предотвращает незапланированное расширение полей. |
| **Дата вступления в силу** | 30.12.2025 |
| **Что важно знать** | <ul><li>Примените настройку Push API одним из следующих способов:<ul><li>[Обновление конфигурации Push API с помощью REST API](https://dev.appsflyer.com/hc/reference/put_app-app-id):<ul><li>Установите для свойства `select_fields` значение ALL Fields</li></ul></li><li><Anchor target="_blank" href="/marketers/ru/docs/push-api-streaming-raw-data#set-up-appsflyer-attribution-endpoint">В AppsFlyer, в разделе Экспорт-> Доступ к API -> Push API или Push API (SKAN)</Anchor>:<ul><li>Выберите поле **Выбрать все**.</li></ul></li></ul></li><li>При вызове <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_app-app-id">REST API для получения конфигурации Push API</Anchor>, если задано `selected_fields = "ALL FIELDS"`, API вернет явный список выбранных полей вместо общего значения «все поля».</li></ul> |
| **Что необходимо сделать:** | <ul><li>Большинству клиентов не нужно предпринимать никаких действий.</li><li>Названия полей и их семантика остаются без изменений.</li><li>Клиенты должны вручную обновить свой выбор в AppsFlyer или через REST API, чтобы получить добавленные поля.</li><li>Клиенты, использующие "ALL FIELDS", должны периодически проверять свою конфигурацию, чтобы новые поля включались при необходимости.</li></ul> |