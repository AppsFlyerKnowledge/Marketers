---
title: 'Бюллетень: обновление постатрибуционного отчета Protect360'
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
  edited_at: '2026-10-19T14:40:41Z'
  id: 360015900018
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/360015900018
---
| **Что нового** | Постатрибуционные отчеты Protect360 показывают действующего участника (медиаисточник) для перехваченных установок и событий в приложении. То есть тот участник, который изначально должен был получить атрибуцию. |
| --- | --- |
| **Дата вступления в силу** | 23 ноября 2020 г. |
| **Где** | Постатрибуционные отчеты о сырых данных Protect360 доступны через:<ul><li>Экспорт данных (загрузка) отчетов о сырых данных</li><li>Получение отчетов о сырых данных через Pull API</li></ul> |
| **Описание** | <ul><li>До настоящего времени постатрибуционные отчеты не отображали действующий медиаисточник участника. Поля **contributor[1-3]** и **organic** показывали участвующие медиаисточники, но не позволяли определить, какой из них обеспечил атрибуцию.</li><li>Начиная с 23 ноября 2020 г., значение поля **rejected\_reason\_value** отображает либо **contributor[1-3]**, либо **organic**.<ul><li>В Data Locker это **validation\_reason\_value**.</li></ul></li><li>Рекламодатели могут проверить поля **contributor[1-3]**, чтобы увидеть, каким должен быть атрибутированный медиаисточник, и использовать эту информацию для сверки.<ul><li>Если поля участников не отображаются в вашем отчете, их можно добавить на странице **Export data**.</li></ul></li></ul> |

> 📄 **Смотрите также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/protect360-raw-data-reports#postattribution-reports">Отчеты после атрибуции</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/protect360-raw-data-reports#pull-api">Отчеты Pull API</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary#protect360::440536f1">Rejected\_reason\_value</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary#attribution::f1c497c7">Contributor[1-3]</Anchor>
> * См. Что нового в AppsFlyer.

<div data-zendesk-anchors="h_01HDPEGXJSMW6Q9DXA89AZ20T6=%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
