---
title: Атрибуция People-Based (PBA) — Обзор
metadata:
  keywords:
    - People Based Analysis
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-08-19T11:53:56Z'
  edited_at: '2026-08-18T00:24:16Z'
  id: 360002274017
  locale: ru
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ru/articles/360002274017
---
> **Обзор:** People-Based Attribution (PBA) предоставляет единый путь пользователей по каналам, платформам и устройствам.

<Image align="center" alt="PBANoSilos_us-en.gif" src="https://files.readme.io/1ac3614eb1b9d4c01bffbe904f1a060d1facd681ff32c274b12f0a15612a2e4a-360009359798.gif" />

<div id="pba-principles" />

## Принципы PBA

* PBA объединяет данные веб-сайтов и мобильных приложений, чтобы обеспечить целостное представление об эффективности кампании по цифровым ресурсам бренда. Рекламодатели используют PBA, чтобы понять, как проходит путь клиента с точки зрения людей, а не устройств.
* Данные PBA (на дэшбордах PBA и в отчетах с сырыми даннымим) используются для маркетингового анализа и оптимизации кампаний.
* Данные, состоящие из посещений веб-сайтов и пользовательских событий, собираются с помощью <Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide">SDK и / или API</Anchor>.
* Для каждого посещения веб-сайта: определяется медиа-источник, благодаря которому это посещение состоялось. Любое результирующее событие (конверсия) <Anchor target="_blank" href="/marketers/ru/docs/pba-media-source-attribution-rules">атрибутируется</Anchor> медиа-источнику, обеспечившему посещение.

<div id="pba-analytics-dashboards-and-raw-data" />

### Аналитические дэшборды PBA и сырые данные

* Данные PBA представлены на аналитических дэшбордах и в отчетах:
  * Website Attribution (Атрибуция веб-сайтов)
  * Web-Assisted Installs
  * Отчеты по необработанным данным
* Данные на панелях мониторинга <Anchor target="_blank" href="/marketers/ru/docs/using-pba-dashboards">отфильтрованы и сгруппированы</Anchor> с использованием таких параметров, как мобильная платформа, медиа-канал и тип мультимедиа. Это позволяет детализировать и анализировать данные.

<div id="website-attribution" />

### <Anchor target="_blank" href="/marketers/ru/docs/pba-website-attribution-dashboard">Website Attribution (Атрибуция веб-сайтов)</Anchor>

<Image align="center" alt="Website Attribution Table" src="https://files.readme.io/46f03ee216dc23f3f184663aeef7d6b64ae6fb9a64e7a161ff0482e4d2eab204-360013057757.jpg" />

Анализируйте источники веб-трафика и маркетинговые кампании, увеличивающие количество посещений и конверсий на вашем веб-сайте. Данный инструмент позволяет увидеть различия в эффективности вплоть до уровня рекламного объявления. Он поддерживает все параметры запроса AppsFLyer в ссылке без необходимости перенаправлять пользователей на серверы AppsFlyer.

### <Anchor target="_blank" href="/marketers/ru/docs/pba-web-assisted-installs">Web-Assisted Installs</Anchor>

<Image align="center" alt="AppsFlyer-Web-to-App_us.en.gif" src="https://files.readme.io/4a278b57379c999d80fd7f1dfea750049f56c03ed32051f9af92577b2a51742a-360009705058.gif" />

Используйте Web-Assisted Installs, чтобы оценить эффективность мероприятий веб-маркетинга, направленных на увеличение количества установок мобильных приложений.

* Получите представление о том, как  различные типы медиа (платные, собственные, заработанные), медиа-каналы (прямые, социальные сети, обычный поиск) и медиа-источники взаимодействуют и способствуют вашим общим усилиям по привлечению пользователей.
* Атрибутируйте органические установки, вызванные вашими действиями в Интернете.
* Изучите взаимодействие между веб-усилиями и неорганическими установками.

<div id="raw-data" />

### <Anchor target="_blank" href="/marketers/ru/docs/pba-raw-data-reports">Сырые данные</Anchor>

Отчеты о необработанных данных доступны через Data Locker. Сырые данные позволяют проводить глубокий анализ и включают атрибутированный медиа-источник / ответственный за привлечение пользователя на сайт.

* **Посещения сайта:** посещения веб-сайта
* **Веб-события** : действия, выполняемые на веб-сайте, такие как подписка или покупка.
* **Web-Assisted Installs** и **пути конверсии** представлены полностью.
* Инструменты бизнес-аналитики используются для анализа данных для получения дополнительных сведений.
* <Anchor target="_blank" href="/marketers/ru/docs/pba-raw-data-reports">Узнать больше о сырых данных PBA</Anchor>.

<div id="see-also" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/onboarding-guide-to-people-based-attribution">Руководство по интеграции для PBA</Anchor>

<div data-zendesk-anchors="pba-principles=%D0%BF%D1%80%D0%B8%D0%BD%D1%86%D0%B8%D0%BF%D1%8B-pba 01ECF26CMJ8TB4ADT6VN277EMQ=%D0%BF%D1%80%D0%B8%D0%BD%D1%86%D0%B8%D0%BF%D1%8B-pba pba-analytics-dashboards-and-raw-data=%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B5-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D1%8B-pba-%D0%B8-%D1%81%D1%8B%D1%80%D1%8B%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5 01ECF26CMJDA1HBC22DGRWY2EA=%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B5-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D1%8B-pba-%D0%B8-%D1%81%D1%8B%D1%80%D1%8B%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5 website-attribution=website-attribution-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%B2%D0%B5%D0%B1-%D1%81%D0%B0%D0%B9%D1%82%D0%BE%D0%B2 01ECF26CMK0T5C9JKQ0SYMXQVM=website-attribution-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%B2%D0%B5%D0%B1-%D1%81%D0%B0%D0%B9%D1%82%D0%BE%D0%B2 webassisted-installs=web-assisted-installs 01ECF26CMKDS16XWRBQ1SDAX2Q=web-assisted-installs raw-data=%D1%81%D1%8B%D1%80%D1%8B%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5 01ECF26CMM4KHX9W94DND4BY8C=%D1%81%D1%8B%D1%80%D1%8B%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5 h_01HE0Y2KTXS06WHN57MQ91AD09=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
