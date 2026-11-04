---
title: Руководство по ROI360 – данные о затратах и доходах
metadata:
  keywords:
    - cost
    - Advertisers
    - Premium
    - Marketers
    - revenue
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-11-10T13:52:03Z'
  edited_at: '2026-10-29T14:02:36Z'
  id: 10515748254609
  locale: ru
  section: Overview
  section_id: 15173289016593
  url: https://support.appsflyer.com/hc/ru/articles/10515748254609
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Кратко:** получайте данные о расходах и доходах, чтобы оценивать общую рентабельность инвестиций (ROI) и рентабельность расходов на рекламу (ROAS).

![M_emptyState.png](https://files.readme.io/5eec5be77bf0b72afdd95b1957642cc67ba509000bc756ac68d87da5e96ed08e-11832563913489.png)

<div id="overview" />

## Обзор

ROI360 — это набор уникальных инструментов отчетности о затратах и доходах, которые позволяют получить самые точные данные в кратчайшие сроки.

Совокупность данных о затратах и доходах позволяет получить полную картину окупаемости рекламных расходов (ROAS) и рентабельности инвестиций (ROI).

<div id="cost-tools" />

### Инструменты затрат

Инструменты ROI360 для работы с данными о расходах, ранее известные как Xpend, собирают данные о расходах и формируют отчеты. Полный набор инструментов и функций, связанных с затратами, представлен в следующей таблице. Нажмите на ссылки, чтобы узнать больше о каждой функции.

<table><thead><tr><th>Инструмент</th><th>Описание</th></tr></thead><tbody><tr><td><a href="./roi360-cost-aggregation-overview" target="_blank">Атрибутированные затраты</a></td><td><p><span>Данные о затратах, привязанные к атрибуции, кликам и показам на самом подробном уровне.</span></p><p><span>Сюда входит доступ к более чем 80 API-интеграциям, позволяющим легко подключаться к глобальным или локальным рекламным сетям.</span></p></td></tr><tr><td><a href="./import-cost-data" target="_blank">Импорт файлов</a></td><td><span>Импорт данных о затратах для записи данных, не полученных через API.</span></td></tr><tr><td><a href="./incorporate-agency-fees-into-campaign-costs" target="_blank">Агентское вознаграждение</a></td><td><span>Расчеты комиссионного вознаграждения агентства включены в ваши затраты.</span></td></tr><tr><td><a href="./set-up-and-use-roi360-cost-etl-reports" target="_blank">Cost ETL\*</a></td><td>Поставляет данные о стоимости кампании, обновляемые 4 раза в день, в вашу корзину AWS S3 или GCS, готовые для загрузки в системы бизнес-аналитики рекламодателей.</td></tr><tr><td colspan="2">\* Доступно с расширенным пакетом ROI360</td></tr></tbody></table>

**Примечание**. Вы также можете агрегировать <Anchor target="_blank" href="/marketers/ru/docs/view-aggregated-cost-data-for-attribution-links">данные о стоимости, указанные по ссылке атрибуции</Anchor>, без ROI360. Однако этот метод применим только для модели затрат CPI, а не для других моделей, таких как CPA, CPC и CPM.

<div id="revenue-tools" />

### Инструменты дохода

Инструменты ROI360 собирают и предоставляют данные о доходах, учитывая покупки в приложениях, подписки и доходы от рекламы.  Налоги и комиссии магазинов приложений также включены в показатели дохода. Полный набор инструментов и функций для получения данных о доходе представлен в следующей таблице. Нажмите на ссылки, чтобы узнать больше о каждой функции.

<table><thead><tr><th>Инструменты</th><th>Описание</th></tr></thead><tbody><tr><td><a href="./purchase-and-subscription-validation-overview" target="_blank">Покупки в приложении</a></td><td><span>Автоматическая отчетность о подтвержденных покупках в приложении, включая данные о последующих операциях, таких как возврат или отмена.</span></td></tr><tr><td><a href="./purchase-and-subscription-validation-overview" target="_blank">Доход от подписки</a></td><td><span>Автоматическая отчетность о подписках, включая изменения, отмены и совместный семейный доступ.</span></td></tr><tr><td><a href="./roi360-guide-ad-revenue-attribution" target="_blank">Доход от рекламы</a></td><td>Доступ к более чем 20 партнерам по доходам от рекламы, которые подключаются через API или SDK, что обеспечивает высочайшую точность и актуальность данных.</td></tr><tr><td> <a href="./revenue-etl-reports" target="_blank">ETL данных о доходах</a>\*</td><td>Поставляет данные о доходах в вашу корзину AWS S3 или GCS, готовые для загрузки в системы бизнес-аналитики рекламодателей.</td></tr><tr><td colspan="2">\* Доступно с расширенным пакетом ROI360</td></tr></tbody></table>

**Примечание**. Есть также некоторые основные инструменты для измерения доходов, которые не включены в ROI360. В отличие от инструментов, включенных в ROI360, эти инструменты требуют значительной настройки со стороны ваших разработчиков:

* <Anchor target="_blank" href="/marketers/ru/docs/about-receipt-validation">Валидация чека покупки в приложении</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/purchase-and-subscription-validation-overview">Измерение доходов от подписки</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/roi360-revenue-attribution-overview">Регистрация доходов с помощью настраиваемых событий в приложении</Anchor>

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01HKHGX9JJQQCKF9SDZRSCM1XJ=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 cost-tools=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82 h_01HKHGX9JJRWDP9PMYP9CFA7MQ=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82 revenue-tools=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D0%B0 h_01HKHGX9JJFQ9ZM6J3B2D5G6C5=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D0%B0" />
