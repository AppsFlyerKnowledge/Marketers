---
title: Об API рекламодателей
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2020-05-24T15:14:53Z'
  edited_at: '2026-08-28T00:09:38Z'
  id: 360009122638
  locale: ru
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/ru/articles/360009122638
---
> **Краткий обзор:** API, доступные рекламодателям для доступа к данным или обновления данных.

## Список и интерфейсы API рекламодателей

<span id="01EEQJERAWW3HY59HVPY3YWA0B"></span>Конкретная информация об отчетах, инструментах отчетности и API отчетности:

* <span id="01EEQJERAW2ZTBWBQKBCDSC76Z"></span><span id="01EEQJERAWQ2WCPV0207XM6FR4"></span><Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview"><span id="01EEQJERAX0W7RCYQWVM2M5S13"></span>Инструменты и API для отчетов по сырым данным</Anchor>
* <span id="01EEQJERAWA09P200SGR985846"></span><span id="01EEQJERAW6AC6WR7E46T5DMHW"></span><Anchor target="_blank" href="/marketers/ru/docs/aggregated-and-analytics-reporting-overview">Инструменты и API для отчетов по сводным данным и аналитики</Anchor>

#### Интерфейсы для рекламодателей

| Сфера | Имя API | ![af_premium.png](https://files.readme.io/ad0c279c48242ea25529f1bc386ee2c747bcd332f5fb1eb2fc26dd378a257f6e-4403570953105.png)<br /><br />Премиум функция | Описание | Токен/ключ  <br />аутентификации | Тип интерфейса |
| --- | --- | --- | --- | --- | --- |
| Мобильная атрибуция | <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile">Межсерверные события (S2S)</Anchor> | Нет | Записывайте события, происходящие вне мобильного приложения. | <Anchor target="_blank" href="/marketers/ru/docs/app-settings#sdk-authentication-dev-key">Ключ разработчика SDK</Anchor> | REST API |
| Атрибуция People-Based (PBA) | <Anchor target="_blank" href="/marketers/ru/docs/web-server-to-server-events-api-for-pba-web-s2s">Server-to-server web</Anchor> | Нет | Сообщайте о событиях PBA, происходящих в бэкенде | <Anchor target="_blank" href="/marketers/ru/docs/pba-brand-bundles-and-settings#управление-пакетами-бренда">Ключ PBA</Anchor> | REST API |
| Вовлеченность | <Anchor target="_blank" href="/marketers/ru/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">Универсальные ссылки OneLink</Anchor> | Да | Управление OneLinks: создание, обновление, извлечение, удаление | <Anchor target="_blank" href="/marketers/ru/docs/app-settings#sdk-authentication-dev-key">Ключ разработчика SDK</Anchor> | REST API |
| Ремаркетинг | <Anchor target="_blank" href="/marketers/ru/docs/audiences-guide#import-an-audience">Аудитории</Anchor> | Да | Загрузка списков пользователей в Аудитории | <Anchor target="_blank" href="/marketers/ru/docs/audiences-import-audience-segments-from-internal-systems">Ключ импорта</Anchor> | REST API |
| Конфиденциальность | <Anchor target="_blank" href="/marketers/ru/docs/send-opendsr-api-requests">Запросы openDSR</Anchor> | Нет | Запросы на удаление данных и статус | <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Отчетность | <Anchor target="_blank" href="/marketers/ru/docs/master-api-user-acquisition-metrics-via-api">Основные KPI</Anchor> | Да | Показатели эффективности кампании с несколькими приложениями в файлах CSV | <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Отчетность | <Anchor target="_blank" href="/marketers/ru/docs/pull-api-aggregate-data">Извлечение агрегированных отчетов</Anchor> | Нет | Агрегирование отчетов в файлы CSV | <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Отчетность | <Anchor target="_blank" href="/marketers/ru/docs/pull-api-raw-data">Извлечение сырых данных</Anchor> | Да | Отчеты по сырым данным в файлах CSV | <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Отчетность | <Anchor target="_blank" href="/marketers/ru/docs/cohort-api">Аналитика по когорте</Anchor> | Да | Метрики когорты в файлах JSON или CSV | <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Отчетность | <Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers">Отчет Data Locker</Anchor> | Да | Отчеты по сырым и агрегированным данным | Н/Д | Облачное хранилище |
| Мобильная атрибуция | <Anchor target="_blank" href="/marketers/ru/docs/push-api-streaming-raw-data">Push</Anchor> | Да | Установки и события в приложении, отправленные на серверы рекламодателей, в реальном времени | Н/Д | REST API |
| Стоимость кампании | <Anchor target="_blank" href="/partners/ru/docs/cost-import-for-ad-networks">Импорт данных о расходах</Anchor> | Нет | Отчет о стоимости кампании | Н/Д | Загрузка файлов |
| Аккаунт | <Anchor target="_blank" href="/marketers/ru/docs/app-list-api-for-app-owners">Получение списка приложений</Anchor> | Нет | Получите список приложений в вашем аккаунте | <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Отчетность | <Anchor target="_blank" href="/marketers/ru/docs/set-up-and-use-roi360-cost-etl-reports">Cost ETL</Anchor> | Да | Детализация затрат на кампанию по Cost ETL | Н/Д | Облачное хранилище |
| Отчетность | <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide#reporting-options">Отчетность SKAN</Anchor> | Нет | Агрегированные отчеты SKAN | V2.0 | REST API |
| Интегрированные партнеры | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-copy">Копирование настроек интеграции партнеров</Anchor> | Нет | Копирование параметров интеграции из одного приложения в другое | V2.0 | REST API |
| Интегрированные партнеры | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">Ключ расшифровки для реферера установки</Anchor> | Нет | Установите ключ расшифровки реферера установки, полученный от Meta ads | V2.0 | REST API |

<div data-zendesk-anchors="advertiser-api-list-and-interfaces=%D1%81%D0%BF%D0%B8%D1%81%D0%BE%D0%BA-%D0%B8-%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81%D1%8B-api-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BE%D0%B4%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 h_01HX9638DX6EHR4ETMSH10K68F=%D1%81%D0%BF%D0%B8%D1%81%D0%BE%D0%BA-%D0%B8-%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81%D1%8B-api-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BE%D0%B4%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 interfaces-for-advertisers=%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81%D1%8B-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BE%D0%B4%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 h_01HX9638DXNJM3A968A2PSRRKS=%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81%D1%8B-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BE%D0%B4%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9" />
