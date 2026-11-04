---
title: Просмотр агрегированных данных о затратах для ссылок атрибуции
metadata:
  keywords:
    - eCPI
    - clicks
    - ROI
    - Advertisers
    - Agencies
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-05-20T10:50:58Z'
  edited_at: '2026-10-28T13:47:31Z'
  id: 360008981698
  locale: ru
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/ru/articles/360008981698
---
> **Кратко:** просмотр агрегированных данных о расходах на каждый клик по рекламе, передаваемых рекламными сетями через ссылку атрибуции.

<div id="basic-cost-reporting" />

## Базовая отчетность по затратам

Данные о затратах передаются в AppsFlyer через:

* Рекламные сети: каждый раз, когда пользователь нажимает на объявление. Просмотр затрат на кампанию в AppsFlyer помогает рекламодателям оценить ROI и принять соответствующие решения по бюджету.
  * Затраты указываются в <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">ссылке атрибуции</Anchor>с использованием модели цены за установку (CPI).
  * Отправляя ссылку атрибуции в рекламную сеть, убедитесь, что рекламная сеть <Anchor target="_blank" href="/partners/ru/docs/cost-reporting-on-the-attribution-link-for-ad-networks">добавляет параметры отчетности о затратах</Anchor>.
* <Anchor target="_blank" href="/marketers/ru/docs/roi360-cost-aggregation-overview">Расширенные возможности агрегирования затрат</Anchor>, в том числе с помощьюAPI и импорта данных о затратах (загрузка файла CSV).

  * Методы агрегирования затрат поддерживают модели затрат, используемые партнером в дополнение к CPI, включая CPA, CPC и CPM.

<div id="viewing-ad-cost-by-click" />

<Accordion title="Информация о стоимости просмотра рекламы по ссылке атрибутов">

Данные о расходах, передаваемые через ссылки атрибуции, агрегируются и становятся доступны практически в реальном времени (не позднее чем через 2 часа после клика по ссылке) в дэшбордах AppsFlyer, отчетах об эффективности и отчетах с сырыми данными.

В *обзорном дэшбордеагрегированный отчет об эффективности* содержит: данные о затратах, кликах, показах, ROI и средней eCPI.

[![CostReporting.jpg](https://files.readme.io/5d4dbe5dc74fd0915924518f76c63e379f0b072b5d5dbb7a7f92455b83e33a12-17313191631633.jpg)](https://files.readme.io/5d4dbe5dc74fd0915924518f76c63e379f0b072b5d5dbb7a7f92455b83e33a12-17313191631633.jpg)

Отчеты об эффективности и отчеты по сырым данным также доступны для <Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview">скачивания</Anchor>.

</Accordion>

<div id="ad-networks-providing-cost-by-click-data" />

<Accordion title="Рекламные сети, передающие данные о расходах через ссылки атрибуции">

Для рекламных сетей, которые сообщают о затратах по клику, поддерживаются параметры, содержащиеся в клике.

**Рекламные сети, которые сообщают о затратах по клику:**

* AdAction
* Aura от Unity
* Blind Ferret
* Chartboost
* Cross Install
* Digital Turbine
* Fyber
* HangMyAds
* IronSource
* Criteo DSP (Manage)
* Mintegral
* TikTok для бизнеса
* Vungle
* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTMPZ9anfZoFBelK2bsBUoHG9n4YE3WxpXOayDF_wI8vyYClM6_6yXelFCZ3khwhd9Z_5Louxd4VVgx/pub?gid=0&single=true&output=csv">Посмотреть полный список рекламных сетей, поддерживающих передачу данных о расходах через ссылки атрибуции</Anchor>

</Accordion>

<div id="limitations" />

<Accordion title="Ограничения">

Ограничения передачи данных о расходах через ссылки атрибуции:

* Затраты указываются только с использованием модели цены за установку (CPI). Другие модели, включаяCPA, CPC и CPM, не поддерживаются.
* <Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns">Сети с самостоятельной атрибуцией</Anchor> (SRN) не сообщают затраты по ссылке атрибуции.
* Данные о расходах, переданные через ссылки атрибуции, нельзя изменить после их получения. Поэтому после регистрации данных в AppsFlyer их нельзя изменить, даже если есть ошибки в отчетах с данными.

</Accordion>

<div data-zendesk-anchors="basic-cost-reporting=%D0%B1%D0%B0%D0%B7%D0%BE%D0%B2%D0%B0%D1%8F-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%BF%D0%BE-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82%D0%B0%D0%BC h_01HX954Y5X7ZP2VMB5W2XAMCR0=%D0%B1%D0%B0%D0%B7%D0%BE%D0%B2%D0%B0%D1%8F-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%BF%D0%BE-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82%D0%B0%D0%BC h_01HX954Y5XTRRQV4JHA5XX1AQ0=viewing-ad-cost-by-click h_01HX954Y5XV8M2R2VDAV34641R=ad-networks-providing-cost-by-click-data h_01HX954Y5X84BM7F8TGQRDPBTS=limitations" />
