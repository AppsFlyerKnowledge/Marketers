---
title: 'Бюллетень: Apple Ads теперь поддерживает атрибуцию SKAN'
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2025-04-15T08:21:59Z'
  edited_at: '2026-10-19T14:38:22Z'
  id: 34395758837137
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/34395758837137
---
| **Что нового** | Теперь AppsFlyer полностью отвечает за импорт и обработку постбэков SKAN от Apple Ads (AA), а также отчетность по ним, предоставляя маркетологам такие же безопасные с точки зрения конфиденциальности измерения, которые уже доступны для других сетей. |
| --- | --- |
| **Дата обновления** | 10.04.2025 |
| **Что важно знать** | Начиная с **iOS 26.2**, постбэки Apple Ads подписываются и отправляются с использованием **AdAttributionKit (AAK)** вместо **SKAdNetwork (SKAN)**.<br /><br />Для версий **iOS 26.1 и более ранних** постбэки Apple Ads по-прежнему используют SKAdNetwork.<br /><br />Чтобы AppsFlyer получал все постбэки Apple Ads, настройте приложение так, чтобы оно отправляло в AppsFlyer **копии постбэков и для SKAdNetwork, и для AdAttributionKit**, как описано в документации Apple для разработчиков.<br /><br />**<span id="where-to-find-aa-skan-data"></span>Где найти данные AA SKAN**<ul><li>**10 апреля 2025 г. – 26 мая 2025 г.:** Данные можно найти в отчете  <Anchor target="_blank" href="/marketers/ru/docs/skan-raw-data-reports#postback::315d5a62">«Копии необработанных постбэков SKAN»</Anchor> (Data Locker).</li><li>**С 27 мая 2025 г.:** Данные доступны во всех дэшбордах SKAN, API, экспортах Data Locker и SSOT.</li></ul>**Изменения в атрибуции**: теперь AA может получать атрибуцию установок, которые ранее в рамках SKAN атрибутировались другим сетям.<br /><br />**<span id="data-granularity"></span>Детализация данных:**<ul><li>Постбэки SKAN содержат только стандартные поля SKAN. Поля обогащения данных о кампании, группе объявлений, объявлении, геолокации и креативе имеют значение **NULL**.</li><li>**Сопоставление размещения (через** **skad\_campaign\_id**):</li><li>10 -> результаты поиска;</li><li>20 -> вкладка «Поиск»;</li><li>30 -> вкладка «Сегодня»;</li><li>40 -> страницы продуктов.</li></ul>**<span id="h_01JXYJ6B8FP8N79CVF84VNYQCR"></span>Примечание**<br />Apple будет делиться только информацией о размещении рекламы. Они будут использовать поле идентификатора кампании в постбэках SKAN, чтобы отразить четыре доступных различных размещения (Результаты поиска, Вкладка поиска, Вкладка «Сегодня» и Страницы продуктов). Это означает, что фактический идентификатор кампании и отчетность на уровне кампании будут недоступны.<ul><li>media\_source: **Apple Search Ads**, а skad\_ad\_network\_id: **com.apple.ads**.</li></ul>**<span id="skan-versions-supported"></span>Поддерживаемые версии SKAN:**<ul><li>AA поддерживает **SKAN 1.0–3.0**, только с **атрибуцией по кликам**.</li><li>Начиная с iOS 26.2 используется AdAttributionKit (AAK).</li><li>Атрибуция по показам в настоящее время не поддерживается.</li></ul>**Влияние на SSOT**: без изменений в логике дедупликации. Постбэки AA, которые еще не были атрибутированы классическими методами AppsFlyer, включаются, а остальные дедуплицируются в SSOT. |
| **Что необходимо сделать** | Чтобы активировать данные AA SKAN в AppsFlyer, убедитесь, что ваше приложение настроено на <Anchor target="_blank" href="/marketers/ru/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">перенаправление постбэков SKAN и AdAttributionKit напрямую из Apple в AppsFlyer</Anchor>.<ul><li>Если ваше приложение уже настроено, дополнительных действий не требуется.</li></ul>Примечание: Для того, чтобы эта функция работала, приложения должны использовать версию iOS 15 или выше. До данным Apple, более 95% пользователей соответствуют этому требованию. |

<div data-zendesk-anchors="h_01JXYJ7NFNJP83Z2J43841ZENJ=where-to-find-aa-skan-data h_01JXYJ7S61RSK8SV11Y7QGQ9XE=data-granularity h_01JXYJ7Z0ERWPH70A291CEFMH6=skan-versions-supported" />
