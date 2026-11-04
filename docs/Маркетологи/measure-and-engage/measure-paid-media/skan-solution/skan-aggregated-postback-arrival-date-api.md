---
title: API даты получения агрегированного постбэка SKAN
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-12-21T09:03:09Z'
  edited_at: '2026-08-18T00:32:38Z'
  id: 360016646557
  locale: ru
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ru/articles/360016646557
---
> **Краткий обзор:** Агрегированные постбэки SKAdNetwork через API. Данные агрегируются по дате поступления постбэка.

<div id="skan-aggregated-postback-arrival-date-api" />

## API даты получения агрегированного постбэка SKAN

API возвращает агрегированные постбэки SKAdNetwork, используя диапазон дат поступления постбэков.

**Примечание**! Дата поступления постбэка отличается от даты установки, использующейся в дэшборде и отчетах SKAdNetwork.

<div id="using-skan-aggregated-performance-report-api" />

<Accordion title="Использование API даты получения агрегированного постбэка SKAN">

**Чтобы использовать API агрегированного отчета об эффективности SKAN**, выполните следующие шаги:

1. Получите API токен. Токен должен получить администратор.
2. Передайте вашему разработчику токен API для использования в заголовке аутентификации.
3. Предоставьте разработчикам параметры, которые нужно указать при вызове API, как описано в следующих разделах. Параметры определяют содержимое отчета, его структуру и временные рамки отчетности.
4. Скажите вашим разработчикам следовать инструкциям в <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-agg-postback-arrival-date-api-get">API агрегированного отчета об эффективности SKAN</Anchor>, представленным в центре для разработчиков.

<div id="parameters" />

#### Параметры

| Имя параметра | Подробности | Обязательно |
| --- | --- | --- |
| `дата_начала` | Диапазон дат поступления постбэка ограничен значениями start\_date и end\_date. Примечание! Дата поступления отличается от даты установки, использующейся в дэшборде и отчетах SKAdNetwork.<ul><li>YYYY-MM-DD</li><li>Самая ранняя разрешенная дата: 2020-11-01<br />Пример: `2020-11-05`</li></ul> | Да |
| `дата_выезда` | <ul><li>YYYY-MM-DD</li><li>Максимальное количество дней на один запрос отчета: 60 дней</li><li>Пример: `2020-11-12`</li></ul> | Да |
| `имя_рекламной_сети` | Фильтр по медиа-источнику | Нет |
| `геолокация` | Фильтрация по коду страны ISO 3166 (альфа-2). Пример: `US`, `CN` | Нет |
| `skad_redownload` | Фильтр по `true` или `false` | Нет |
| `skad_source_app_id` | Фильтр по идентификатору источника приложения | Нет |
| `идентификатор_кампании_рекламной_сети` | Фильтр по идентификатору кампании рекламной сети.<br /><br />**Примечание**: Это не идентификатор кампании, полученный от SKAdNetwork. | Нет |
| `modeled_conversion_values` | <ul><li>Поддерживается только с версии V2</li><li>Значение может быть либо `true` или `false`</li><li>Если `true`, постбэк заполняет столбец «count» моделируемыми данными о значении конверсии.  [См. доступное поле для моделируемых данных](/docs/skan-aggregated-postback-arrival-date-api#report-structure-and-example)</li><li>Если , постбэк отображает количество значений конверсии со всеми доступными полями, представленными в структуре отчета, без моделируемых данных.</li><li>Значение по умолчанию — `false`.</li></ul> | Нет |

</Accordion>

<div id="report-structure-and-example" />

<Accordion title="Структура отчета и пример">

API возвращает CSV-файл.

Доступные столбцы и показатели перечислены в таблице ниже.

Примеры: <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRXgsWlkyvMS20HgZuOQnH1YC8QQcRhOMYIOxyj_fcgikfDfmW6wNAMHO6alPWVA1j_KZwtqowohqrK/pub?gid=0&single=true&output=csv">В1</Anchor> |<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRMFEELm8JCAQBBAIJqAc1eE5YdN0kOcSVkOPd_Ki2ngnX61wHL4sXypVouOhto8u-JCQmdIYY_5UG6/pub?gid=219191499&single=true&output=csv">В2</Anchor>

| Имя столбца | Размерность или мера | Доступно с токеном API V1 | Доступно с токеном API V2 | Доступно с токеном API V2 (для SKAN 4) | Доступно только с фильтром модельных данных |
| --- | --- | --- | --- | --- | --- |
| skad\_postback\_sequence\_index | Группировать по | Н | Н | Д | Д |
| skad\_conversion\_value | Группировать по | Д | Д | Д | Д |
| skad\_coarse\_conversion\_value | Группировать по | Н | Н | Д | Д |
| skad\_ad\_network\_id<br /><br />Некоторые SRN не передают свои идентификаторы. В этом случае поле будет пустым, а заполняется поле ad\_network\_name. | Группировать по | Д | Д | Д | Д |
| имя\_рекламной\_сети<br /><br />В настоящее время, в большинстве случаев это поле пустое. Мы заполняем его для SRN, которые не передают свой skad\_ad\_network\_id. | Группировать по | Д | Д | Д | Д |
| skad\_source\_identifier | Группировать по | Н | Н | Д | Д |
| skad\_campaign\_id | Группировать по | Д | Д | Д | Д |
| идентификатор\_кампании\_рекламной\_сети | Группировать по | Д | Д | Д | Д |
| название\_кампании\_рекламной\_сети | Группировать по | Д | Д | Д | Д |
| идентификатор\_набора\_объявлений\_рекламной\_сети | Группировать по | Н | Д | Д | Д |
| название\_набора\_объявлений\_рекламной\_сети | Группировать по | Н | Д | Д | Д |
| идентификатор\_рекламы\_рекламной\_сети | Группировать по | Н | Д | Д | Н |
| название\_рекламной\_сети\_рекламы | Группировать по | Н | Д | Д | Н |
| креатив\_рекламной\_сети | Группировать по | Н | Н | Д | Н |
| канал\_рекламной\_сети | Группировать по | Н | Н | Д | Н |
| skad\_версия | Группировать по | Д | Д | Д | Н |
| skad\_redownload | Группировать по | Д | Д | Д | Н |
| skad\_source\_app\_id | Группировать по | Д | Д | Д | Н |
| skad\_source\_domain | Группировать по | Н | Н | Д | Д |
| skad\_fidelity\_type | Группировать по | Н | Д | Д | Н |
| геолокация | Группировать по | Д | Д | Д | Н |
| дата\_прибытия | Группировать по | Д | Д | Д | Д |
| количество | Мера | Д | Д | Д | Д |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Спецификации и ограничения">

| Спецификация | Примечания |
| --- | --- |
| Актуальность данных | Отчет обновляется <Anchor target="_blank" href="/marketers/ru/docs/about-data-freshness-and-timezone-support#eod">ежедневно.</Anchor><br /><br />Доступность данных определяется свежестью данных <Anchor target="_blank" href="/marketers/ru/docs/about-data-freshness-and-timezone-support#skan">SKAdNetwork</Anchor>. |
| Диапазон дат | <ul><li>Самая ранняя поддерживаемая дата: 1 ноября 2020 г.</li><li>Максимальный диапазон запроса: 60 дней</li></ul> |
| Ограничение скорости | <ul><li>Запросы возвращают до 200 тыс. строк.</li><li>60 запросов в минуту</li></ul> |
| SRN: | Google Реклама: Дата получения постбэка определяется временем последнего клика, указанного Google. |
| Доступ рекламной сети | Доступно аналитическим партнерам с разрешения рекламодателя. |
| Доступ агентства | Недоступно |
| Часовой пояс конкретного приложения | Только UTC |
| Валюта приложения | Всегда USD |
| Органические данные | Недоступно с этим API |
| Неорганические данные | Вычисляются на основе постбэков SKAdNetwork, полученных AppsFlyer |
| Исторические данные | Самая ранняя поддерживаемая дата конверсии (установка или ретаргетинг): 1 ноября 2020 г. |
| Доступ пользователей аккаунта | Токен авторизации доступен администратору в дэшборде. |

</Accordion>

<div id="see-also" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/skan-aggregated-performance-report-api">API для агрегированного отчета об эффективности SKAN</Anchor>

<div data-zendesk-anchors="skadnetwork-postback-arrival-date-aggregation-reporting-api=api-%D0%B4%D0%B0%D1%82%D1%8B-%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B0-skan h_01HDNZKFEHWET0FPX9WN136MB2=api-%D0%B4%D0%B0%D1%82%D1%8B-%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B0-skan h_01HDNZKFEH76Y06091QS6Y5K1Z=using-skan-aggregated-performance-report-api parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B h_01HDNZKFEHA6N6EE4RMG0HGABA=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B h_01HDNZKFEHM2D7GS3RMSRCKZY7=report-structure-and-example h_01HDNZKFEJ5P3245V1R99DGAQW=specifications-and-limitations h_01HDNZP87CWGVJ3G1BDXAR1WN0=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
