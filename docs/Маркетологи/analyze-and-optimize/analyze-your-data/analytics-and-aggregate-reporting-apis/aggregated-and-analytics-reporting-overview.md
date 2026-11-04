---
title: Обзор агрегированной отчетности и аналитики
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
    - Ad Networks
  created_at: '2020-02-04T09:38:14Z'
  edited_at: '2026-09-09T00:02:22Z'
  id: 360005437257
  locale: ru
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ru/articles/360005437257
---
> **At a glance:** Описание и сравнение доступных агрегированных и аналитических отчетов по атрибуции, инструментов и API.

<div id="aggregated-and-analytics-performance-reporting-overview" />

## Аналитика и агрегированные данные об эффективности: инструменты и отчеты

Инструменты агрегированной аналитики на платформе предоставляют рекламодателям метрики, позволяющие им оценивать эффективность своих приложений, кампаний и пользователей.

Инструменты различаются способом представления данных. Некоторые отчеты содержат метрики пожизненной ценности (LTV) для кампаний, а другие, например Cohort, используются для анализа вовлеченности пользователей с течением времени.

Инструменты, описанные в этой статье, относятся к данным, которые можно экспортировать с платформы. В таблице со сравнением инструментов описаны их основные функции и различия между ними.

<Accordion title="Сравнение методов отчетности">

В следующей таблице описаны различные методы отчетности и дэшборды для получения агрегированных данных.

[Скачайте таблицу в виде CSV-файла](https://docs.google.com/spreadsheets/d/e/2PACX-1vSICicxcvD0996RT59fTLDJvdGUKxqPqr47f5SMD8BmsbZtrWIoxRxJEo7tAXTBBmnIbiH097VtK6L9/pub?output=xlsx), чтобы увидеть дополнительные поля, поясняющие различные характеристики и ограничения, которые помогут вам сравнить и сопоставить различные методы отчетности.

Дополнительные поля с характеристиками в загружаемом CSV-файле включают:

* <Anchor target="_blank" href="/marketers/ru/docs/about-data-freshness-and-timezone-support">Актуальность данных</Anchor>: период времени между совершением события и появлением данных в методе отчетности.
* <Anchor target="_blank" href="/marketers/ru/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV/активность</Anchor>: являются ли данные данными LTV или активности.
* <Anchor target="_blank" href="/marketers/ru/docs/retargeting-attribution-guide">Ретаргетинг</Anchor>: отображаются ли данные ретаргетинга (повторного вовлечения и реатрибуции).
* <Anchor target="_blank" href="/marketers/ru/docs/measure-reinstalls#attributed-to-the-first-install">Атрибуция событий повторной установки к первой установке</Anchor>: можно ли отнести события после повторной установки к первоначальной установке.
* <Anchor target="_blank" href="/marketers/ru/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles">Часовой пояс</Anchor>: какой часовой пояс (UTC или часовой пояс приложения) используется для отображения данных.
* <Anchor target="_blank" href="/marketers/ru/docs/measure-reinstalls#unattributed-organic-inapps">Неатрибутированные события</Anchor>: Отображаются ли события, которые не были атрибутированы после повторной установки.
* <Anchor target="_blank" href="/marketers/ru/docs/campaign-name-changes?">Изменение названий кампаний</Anchor>: можно ли изменять названия кампаний без создания дублирующих отображений данных.

| Способ получения отчета | Описание |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ru/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>  <br />(премиум-функция) | Выбранные KPI для LTV, активности, удержания, когорты и эффективности кампании Protect360 по API, в формате CSV или JSON. |
| <Anchor target="_blank" href="/marketers/ru/docs/pull-api-aggregate-data">Pull API — агрегированные отчеты</Anchor> | Жизненный цикл (LTV) пользователей, которые установили, повторно вовлеклись или повторно атрибутированы, в формате CSV. Данные UA и ретаргетинга разделены; единого варианта нет. |
| <Anchor target="_blank" href="/marketers/ru/docs/aggregated-data-export-page">Страница экспорта данных — агрегированные отчеты</Anchor> | Жизненный цикл (LTV) пользователей, которые установили, повторно вовлеклись или повторно атрибутированы, в формате CSV. Данные UA и ретаргетинга разделены; единого варианта нет. |
| <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Обзор SKAN</Anchor> | Метрики, сообщаемые через постбэки iOS SKAN и дополнительные точки данных в течение начального окна измерения для пользователя. |
| <Anchor target="_blank" href="/marketers/ru/docs/skan-aggregated-performance-report-api">API агрегированных данных SKAN</Anchor> | Метрики, сообщаемые через постбэки iOS SKAN и дополнительные точки данных в течение начального окна измерения для пользователя. |
| <Anchor target="_blank" href="/marketers/ru/docs/protect360-dashboard">Панель управления Protect360</Anchor> | Метрики и аналитические данные, касающиеся мошеннического трафика.  <br />Данные на основе LTV для установок и данные на основе активности для событий в приложении. |
| <Anchor target="_blank" href="/marketers/ru/docs/cohort-and-retention-dashboard">Ретаргетинг</Anchor> | Различные метрики пользователей за каждый день после установки. |
| <Anchor target="_blank" href="/marketers/ru/docs/cohort-api">Cohort API</Anchor>  <br />(премиум-функция) | Различные метрики пользователей за каждый день после установки. Также включает активность на уровне событий по event\_date для пользователей, у которых конверсия произошла в течение 365 дней. |
| <Anchor target="_blank" href="/marketers/ru/docs/cohort-analytics-via-data-locker">Cohort Data Locker</Anchor>  <br />(премиум-функция) | Различные метрики пользователей за каждый день после установки. Также включает активность на уровне событий по event\_date для пользователей, чья конверсия произошла в течение 1,095 дней. |
| <Anchor target="_blank" href="/marketers/ru/docs/pivot-table-user-metrics">Отчеты пивот</Anchor>  <br />(премиум-функция) | Отчеты по версионированным агрегированным данным. LTV. |
| <Anchor target="_blank" href="/marketers/ru/docs/custom-dashboards">Кастомизируемые панели управления</Anchor> | Настраиваемый дэшборд с показателями LTV по привлечению пользователей. |
| Они содержат <Anchor target="_blank" href="/marketers/ru/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">данные LTV</Anchor>, где дата атрибуции определяется как: | Выбранные KPI для LTV, активности, удержания и эффективности кампании Protect360 на дэшборде или в файле CSV. |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-and-use-roi360-cost-etl-reports">ETL по затратам</Anchor> | Данные о стоимости кампании с максимальной детализацией по медиа-источникам. |
| Отчет об использовании | Сочетание всех функций AppsFlyer, основанных на использовании, которые влияют на контрактные обязательства в течение платежных циклов. |
| <Anchor target="_blank" href="/marketers/ru/docs/creative-optimization-guide">Дэшборд оптимизации креативов</Anchor> | Данные LTV об эффективности креативов. То есть метрики относятся к конверсиям, произошедшим благодаря креативам в выбранном диапазоне дат. |

</Accordion>

<Accordion title="Способы получения данных о когортах">

Когортные данные доступны несколькими способами: через <Anchor target="_blank" href="/marketers/ru/docs/cohort-and-retention-dashboard">когортный дэшборд</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/cohort-api">Cohort API</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/cohort-analytics-via-data-locker">когортную аналитику через Data Locker</Anchor>. В таблице ниже приведены их особенности.

| Характеристика | Когортная аналитика в Data Locker | Расширенные агрегированные отчеты в Data Locker | Дэшборд когорт | Когортный API |
| --- | --- | --- | --- | --- |
| Несколько или одно приложение | Несколько. Данные группируются по приложениям в одном файле или разделяются на отдельные файлы. | Несколько. Общая эффективность или сгруппированная по параметрам приложения. | Несколько. Общая эффективность или сгруппированная по параметрам приложения. | Одно |
| Группировки | Полная иерархия кампании и названия событий. Около 20 группировок | Полная иерархия кампании и названия событий. Около 20 группировок | 4 группировки | 7 группировок |
| Доступные метрики | Различные метрики пользователей за каждый день после установки. | Все метрики | 1 выбираемая и 4 фиксированные метрики на представление | 1 выбираемая и 4 фиксированные метрики на вызов |
| Срок доступности после атрибуции (в когортных днях) | 365 | 1095 | 180 | 180 |
| Ограничения экспорта данных | Соотношение лояльных пользователей к установкам | Доступен весь набор данных | Загрузка вручную и настройки | Предоставление данных и размер ответа ограничены |
| Настраиваемый запрос | CostETL | Нет | Да | Да |

Различия между способами получения данных о когортах

</Accordion>

<div id="user-journey-reports" />

### Отчеты о пути пользователя

Описанные отчеты доступны на странице Экспорта данных или через Pull API агрегированный.

Это отчеты <Anchor target="_blank" href="/marketers/ru/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">Lifetime value (LTV)</Anchor>. Следовательно:

* Самая ранняя доступная дата отчета — это дата первой установки приложения.
* Диапазон дат отчетности относится к дате атрибуции:
  * Дата установки для отчетов UA и Protect360
  * Дата реатрибуции или повторного вовлечения для отчетов по ретаргетингу

<Accordion title="Отчеты UA с агрегированными данными LTV, содержащие данные по неорганическим и органическим пользователям">

<table><thead><tr><th>Название отчета</th><th>Группировка по</th></tr></thead><tbody><tr><td>Партнеры (медиа-источники)</td><td>Агентство, медиа-источник, кампания</td></tr><tr><td>Партнеры по датам</td><td>Дата, агентство, медиа-источник, кампания</td></tr><tr><td>Ежедневная активность</td><td>Дата, агентство, медиа-источник, кампания</td></tr><tr><td>Геоданные</td><td>Страна, агентство, медиа-источник, кампания</td></tr><tr><td>Геоданные — по датам</td><td>Дата, страна, агентство, медиа-источник, кампания</td></tr><tr><td>Ключевые показатели атрибуции по просмотрам (VTA)</td><td><a href="./pull-api-aggregate-data" target="_blank">Отчеты по VTA доступны только через Pull API</a></td></tr><tr><td colspan="2"> <strong>Примечание</strong>: Если выбран <em>медиаисточник</em> Meta ads, то добавляются дополнительные столбцы: Adgroup ID, Adgroup name, Adset ID, Adset name</td></tr></tbody></table>

Поля дат в CSV-файлах имеют формат гггг-мм-дд. При открытии CSV-файла в Excel поля даты форматируются в соответствии с настройками даты и времени на компьютере. Обязательно выберите соответствующий формат отображения даты в <Anchor target="_blank" href="https://support.office.com/en-us/article/format-a-date-the-way-you-want-8e10019e-d5d8-47a1-ba95-db95123d273e#ID0EAACAAA=Windows">Excel.</Anchor>

<div id="examples-of-aggregate-reports" />

#### Примеры агрегированных отчетов

[Электронная таблица с примерами отчетов](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmzRons779Dk5QWVoPsOF8E7yJLwNPB1IF87shZr6rcMJLjszlSNIbAMVcdeQLysr8Bc4QAby5QB4u/pub?output=xlsx)

<div id="fields-in-ua-aggregate-reports" />

#### Поля в агрегированных отчетах UA

<table><thead><tr><th rowspan="2">Поле</th><th rowspan="2">Описание</th><th colspan="5">Название отчета</th></tr><tr><th>Партнер (медиа-источник)</th><th>Партнер по датам</th><th>Ежедневно</th><th>Геоданные</th><th>Геоданные — по датам</th></tr></thead><tbody><tr><td>Страна</td><td>Страна установки</td><td></td><td></td><td></td><td>✓</td><td>✓</td></tr><tr><td>Дата</td><td>Дата атрибуции</td><td></td><td>✓</td><td></td><td></td><td>✓</td></tr><tr><td>Agency/PMD (af_prt)</td><td>Имя агентства / партнера</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Медиа Источник (PID)</td><td>Медиа-источник, из которого пришел пользователь (pid = медиа-источник)</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Кампания</td><td>Название кампании (c= название кампании)</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>ID кампании</td><td>ID кампании Meta</td><td>Только Meta Ads</td><td>Только Meta Ads</td><td>Только Meta Ads</td><td>Только Meta Ads</td><td>Только Meta Ads</td></tr><tr><td>Adgroup ID</td><td>ID рекламной группы Meta или ID рекламы</td><td>Только Meta Ads</td><td>Только Meta Ads</td><td>Только Meta Ads</td><td>Только Meta Ads</td><td>Только Meta Ads</td></tr><tr><td>Adgroup Name</td><td>Рекламная группа Meta</td><td>Только Meta Ads</td><td>Только Meta Ads</td><td>Только Meta Ads</td><td>Только Meta Ads</td><td>Только Meta Ads</td></tr><tr><td>ID блока рекламы</td><td>ID блока рекламы Meta</td><td>Только Meta Ads</td><td>Только Meta Ads</td><td>Только Meta Ads</td><td>Только Meta Ads</td><td>Только Meta Ads</td></tr><tr><td>Название блока рекламы</td><td>Название блока рекламы Meta</td><td>Только Meta Ads</td><td>Только Meta Ads</td><td>Только Meta Ads</td><td>Только Meta Ads</td><td>Только Meta Ads</td></tr><tr><td>Рост ARPU</td><td>Средняя прибыль на одного пользователя</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>Средний eCPI</td><td>Средний eCPI</td><td></td><td>✓</td><td></td><td></td><td></td></tr><tr><td>Clicks (Клики)</td><td>Количество кликов</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Коэффициент конверсии</td><td>Количество установок / количество кликов по рекламе</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>CTR</td><td>Коэффициент кликабельности</td><td></td><td>✓</td><td>✓</td><td></td><td></td></tr><tr><td>`{your event name}(Уникальные пользователи)</td><td>Количество уникальных пользователей, выполнивших событие</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>{your event name} (Счетчик событий)</td><td>Счетчик событий</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>{your event name}` (Продажи в XXX)</td><td>Продажи события в ХХХ, где ХХХ — валюта приложения</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>Показы</td><td>Количество показов</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>Установки</td><td>число установок</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Loyal Users (Лояльные пользователи)</td><td>[По умолчанию] Пользователь, открывший приложение более трех раз</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Loyal Users/Installs (Лояльные пользователи / Установки)</td><td>Дэшборд удержания клиентов</td><td>✓</td><td>✓</td><td></td><td></td><td></td></tr><tr><td>ROI</td><td>Возврат инвестиций</td><td>✓</td><td>✓</td><td></td><td></td><td></td></tr><tr><td>Sessions (Сеансы)</td><td><ul><li>Количество неорганических открытий приложения</li><li>Органические и неорганические сессии можно просмотреть в когортном отчете</li></ul></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Total Cost (Общая стоимость)</td><td>-</td><td>✓</td><td>✓</td><td></td><td></td><td></td></tr><tr><td>Total revenue (Общий доход)</td><td>Общий доход от медиа-источника и кампании</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td colspan="7"> Различные метрики пользователей за каждый день после установки.</td></tr></tbody></table>

</Accordion>

<Accordion title="Агрегированные отчеты по ретаргетингу">

В отчеты по ретаргетингу входят данные пользователей, которые вовлечены в <Anchor target="_blank" href="/marketers/ru/docs/retargeting-attribution-guide#retargeting-reports-and-raw-data">ретаргетинговую кампанию</Anchor> и подпадают под повторное вовлечение или реатрибуцию.

В отчетах по ретаргетингу органические и неорганические пользователи не разделяются.

Чтобы получать отчеты по ретаргетингу через Pull API, добавьте параметр *&reattr=true* к URI отчетов об эффективности.

<div id="aggregate-ltv-retargeting-reports" />

#### Агрегированные отчеты по ретаргетингу на основе LTV-данных

| Название отчета | Группировка по |
| --- | --- |
| Партнеры (медиа-источники) | Агентство, медиа-источник, кампания |
| Партнеры по датам | Дата, агентство, медиа-источник, кампания |
| Активность по дате | Дата, агентство, медиа-источник, кампания |
| Страна | Страна, агентство, медиа-источник, кампания |
| Страна по дате | Дата, страна, агентство, медиа-источник, кампания |

<div id="aggregate-ltv-retargeting-reports-1" />

#### Агрегированные отчеты по ретаргетингу на основе LTV-данных

| Поле | Описание | Партнеры | Ежедневно | Партнеры по датам | Геоданные — по датам | Геоданные |
| --- | --- | --- | --- | --- | --- | --- |
| Дата | Дата конверсии | - | - | ✓ | ✓ | - |
| Страна |  | - | ✓ |  | ✓ | ✓ |
| Agency/PMD (af\_prt) | Имя агентства / партнера | ✓ | ✓ | ✓ | ✓ | ✓ |
| Медиа Источник (PID) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Кампания (c) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Clicks (Клики) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Конверсии |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Тип конверсий | Реатрибуция или повторное вовлечение | ✓ | ✓ | ✓ | ✓ | ✓ |
| Коэффициент конверсии | Конверсии / клики | ✓ | ✓ | ✓ | ✓ | ✓ |
| Sessions (Сеансы) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Loyal Users (Лояльные пользователи) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Loyal Users/Installs (Лояльные пользователи / Установки) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Total Cost (Общая стоимость) |  | - | - | - | - | - |
| Средний eCPI |  | - | - | - | - | - |
| Total Revenue (Общий доход) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| ROI |  | - | - | - | - | - |
| Рост ARPU |  | ✓ | ✓ | ✓ | - | ✓ |

</Accordion>

<div id="feature-reports" />

## Отчеты по функциям

<Accordion title="SKAdNetwork">

<Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide#reporting-options">Агрегированные отчеты SKAdNetwork</Anchor>

</Accordion>

<Accordion title="Protect360 — заблокированное мошенничество">

![Пример отчета Protect360 о заблокированном мошенничестве](https://theme.zdassets.com/theme_assets/245528/ffbbc473bb0e74b9fb636ed735f69e9af6a25a18.png)

Агрегированные отчеты о заблокированном фроде содержат данные о событиях, заблокированных <Anchor target="_blank" href="/marketers/ru/docs/protect360-anti-fraud-guide">Protect360</Anchor>.

Отчеты доступны через Pull API. Эти отчеты недоступны со страницы Экспорт данных.

Диапазон дат относится к дате установки.

<div id="aggregate-protect360-reports-available-via-pull-api" />

#### Сводные отчеты Protect360 доступны через Pull API.

| Название отчета |
| --- |
| Партнеры (медиа-источники) |
| Партнеры — по датам |
| Геоданные |
| Геоданные — по датам |
| Отчет по кампании партнера |

**Ограничение:** Причина блокировки **боты** отображается даже в случаях, когда причиной должна быть **версия приложения** или **отсутствует идентификатор пользователя клиента**.

</Accordion>

<div id="see-also" />

#### См. также

* <Anchor target="_blank" href="/marketers/ru/docs/configuring-meta-campaign-management-partners">Настройка партнеров по управлению кампаниями Meta</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview">Обзор отчетов с сырыми данными</Anchor>

<div data-zendesk-anchors="aggregated-and-analytics-performance-reporting%E2%80%94tools-and-reports=%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D1%82%D0%B8%D0%BA%D0%B0-%D0%B8-%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE%D0%B1-%D1%8D%D1%84%D1%84%D0%B5%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B-%D0%B8-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B 01EWA9VQ2HH93525BMK6WN0P6S=%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D1%82%D0%B8%D0%BA%D0%B0-%D0%B8-%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE%D0%B1-%D1%8D%D1%84%D1%84%D0%B5%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B-%D0%B8-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B user-journey-reports=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-%D0%BE-%D0%BF%D1%83%D1%82%D0%B8-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F 01ED4D7W8CVAQ9V2GCEX1G6KD7=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-%D0%BE-%D0%BF%D1%83%D1%82%D0%B8-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F examples-of-aggregate-reports=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2 01ED4D7W8C3ZNBYR3CMHJF3QSE=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2 fields-in-ua-aggregate-reports=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%B2-%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-ua h_01HDNYFR9KTQ7ZF35C7E7M7AF1=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%B2-%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-ua aggregate-ltv-retargeting-reports=%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D1%83-%D0%BD%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%B5-ltv-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01HDNYFR9MSJWCP3JA4M1WXN1H=%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D1%83-%D0%BD%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%B5-ltv-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 aggregate-ltv-retargeting-reports::b2093953=%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D1%83-%D0%BD%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%B5-ltv-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-1 h_01HDNYFR9MSK9VQQ0Q889Z55TN=%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D1%83-%D0%BD%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%B5-ltv-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-1 feature-reports=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D1%8F%D0%BC h_01HDNYFR9MYXVZ5BA9FDZ6D82M=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D1%8F%D0%BC aggregate-protect360-reports-available-via-pull-api=%D1%81%D0%B2%D0%BE%D0%B4%D0%BD%D1%8B%D0%B5-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-protect360-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-pull-api h_01HDNYFR9MSZ9K8F283J0WBHCZ=%D1%81%D0%B2%D0%BE%D0%B4%D0%BD%D1%8B%D0%B5-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-protect360-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-pull-api h_01HDNYYJXVY9XHX87K06NXYQNS=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
