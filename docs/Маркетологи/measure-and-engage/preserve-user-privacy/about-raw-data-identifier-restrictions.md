---
title: Ограничения в отношении идентификаторов сырых данных
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2020-03-23T08:29:01Z'
  edited_at: '2026-10-09T00:15:40Z'
  id: 360006868017
  locale: ru
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ru/articles/360006868017
---
> **Краткий обзор:** Некоторые партнеры требуют от AppsFlyer ограничения определенных полей в некоторых отчетах о необработанных данных. В других случаях партнеры могут запросить удаление медиа-источника при обмене постбэками с сторонними платформами. В этой статье описаны эти ограничения и их последствия.

<div id="raw-data-restriction" />

## Ограничение необработанных данных

AppsFlyer ограничивает доступ к определенным полям отчета о сырых данных в зависимости от настроек <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">AAP (Aggregated Advanced Privacy)</Anchor> рекламодателя или политик обмена данными рекламных сетей, предоставляющих эти данные. Эти ограничения варьируются в зависимости от типа отчета и причины ограничения.

<div id="media-source-restrictions" />

### Ограничения медиа-источников

В следующей таблице перечислены ограничения по медиа-источникам для конверсий, кликов и показов.

<div id="note" />

> 📘 **Примечание**
>
> Агрегированные данные атрибуции и аналитические данные доступны без ограничений. Однако все постбэки и отчеты на уровне устройства подлежат ограничениям, указанным ниже.
>
> <Anchor target="_blank" href="/marketers/ru/docs/discrepancies-between-appsflyer-and-third-party-platforms#ограничения-постбэков-на-сторонних-платформах">Ограничения постбэков на сторонних платформах</Anchor>:
>
> * Ограничения, описанные в таблице ниже, применяются к событиям, включенным в постбэки, отправляемые на сторонние платформы, такие как аналитические и маркетинговые платформы.
> * Для других событий могут действовать дополнительные ограничения в постбэках.

| Медиа-источник | Ограничение типа атрибуции |
| --- | --- |
| <span id="amazon-ads"></span>Реклама Amazon | Необработанные данные из Amazon Ads ограничены на платформе AppsFlyer. В результате медиаисточник отображается как «restricted», а сведения о кампании отсутствуют.<br /><br />Как и в случае с любой SRN (Self-Reporting Network), клики и показы из Amazon не включаются в отчеты о сырых данных. |
| <span id="discord"></span>Discord | Сырые данные из Discord ограничены на платформе AppsFlyer.<br /><br />Следующие ограничения применяются к атрибуции по просмотрам и кликам:<ul><li>original\_url: restricted</li><li>click\_id: restricted</li></ul>Клики и показы с Discord не включаются в Отчеты о необработанных данных. |
| <span id="meta-ads"></span>Meta Ads | К сырым данным Meta Ads применяются следующие ограничения:<ul><li>По умолчанию Meta Ads не позволяет распространение данных на уровне устройства без ограничений в отношении информации об атрибуции. Однако, если вы примете условия Meta Advanced Mobile Measurement (AMM), вы сможете получить доступ к данным атрибуции на уровне устройства для Meta Ads без ограничений. См. <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-integration-setup#enable-meta-ads-device-level-data">Включение данных на уровне устройства для Meta Ads</Anchor>.</li><li>Данные из решения AEM глубоких ссылок (iOS), а также данные из Google Play реферальной ссылки и Meta реферальной ссылки (Android) доступны в отчетах на уровне устройства.</li><li>Данные из Google Play Install Referrer и Meta Install Referrer могут появляться только в отчетах об установках.</li><li>Данные из решения AEM для диплинкинга (iOS) могут появляться только в отчетах о повторном вовлечении.</li></ul>Клики и показы из Meta Ads не включаются в отчеты о сырых данных. |
| <span id="pinterest"></span>pinterest | Данные атрибуции по кликам и просмотрам ограничены.<br /><br />Клики и показы из Pinterest не включаются в отчеты о необработанных данных. |
| <span id="reddit"></span>Reddit | Клики и показы с Reddit не включаются в Отчеты о необработанных данных.<br /><br />**Напоминание:** Данные, полученные о кампании в Reddit, подпадают под действие <Anchor target="_blank" href="https://business.reddithelp.com/s/article/Reddit-Business-Tool-Terms">Reddit Business Tool Terms</Anchor> и включают, помимо прочих ограничений, запрет на использование данных Reddit для создания профилей пользователей. |
| <span id="samsung-dsp"></span>Samsung DSP | С 17 октября 2023 г.:<br /><br />Атрибуция по просмотрам и кликам Samsung ограничена. Следующее включено в инструменты доставки необработанных данных:<ul><li>Медиа-источник (samsungdsp\_int)</li><li>Атрибутированный тип взаимодействия (показ/клик)</li><li>Доступно время атрибутированного взаимодействия</li><li>Детали кампании доступны</li></ul>Клики и показы от Samsung не включены в отчёты по сырым данным.<br /><br />Начиная с 30 августа 2025 г.:<br /><br />Атрибуция по просмотрам и кликам Samsung EMEA ограничена для взаимодействий, полученных с `af_data_restriction=attribution` в URL-адресе. Следующее включено в инструменты доставки необработанных данных:<ul><li>Медиаисточник: указывается как ограниченный</li><li>Атрибутированный тип взаимодействия (показ/клик)</li><li>Доступно время атрибутированного взаимодействия</li><li>Детали кампании доступны</li></ul>Клики и показы от Samsung не включены в отчёты по сырым данным. |
| <span id="snapchat"></span>Snapchat | К сырым данным Snapchat применяются следующие ограничения:<ul><li>С 1 марта 2023 года удаления Snapchat не включаются в отчеты о сырых данных.</li><li>В некоторых случаях данные на уровне устройства для атрибуции по показам ограничены. Логика ограничений на сырые данные определяется на стороне Snapchat для каждого события и передается в AppsFlyer через интеграцию.</li><li>Если для события действуют ограничения на сырые данные, в инструментах доставки сырых данных **не** ограничивается следующее:</li></ul><ul><li>Медиа-источник (snapchat\_int)</li><li>Канал</li><li>Атрибутированный тип взаимодействия (impression — показ)</li><li>Время атрибутированного взаимодействия (указывается только дата, "dd/mm/yyyy")</li><li>Название и идентификатор кампании (с 15 декабря 2025 г.)</li><li>Название и идентификатор группы объявлений (с 15 декабря 2025 г.)</li></ul><ul><li>Вышеуказанные ограничения не применяются к вовлечённым просмотрам.</li></ul>Клики и показы из Snapchat не включаются в отчеты о сырых данных. |
| <span id="tiktok-for-business"></span>TikTok для бизнеса | До 19 мая 2026 года к атрибуции по просмотрам применялись следующие ограничения:<ul><li>Медиаисточник (tiktokglobal\_int)</li><li>Канал указывался в отчетности как TikTok / Pangle</li><li>Атрибутированный тип точки взаимодействия указывался в отчетности как показ</li><li>Время атрибуции касания (указывается только дата - «дд\/мм\/гггг»)</li><li>Информация о кампании, группе объявлений и рекламном объявлении указывалась в отчетности как "restricted"</li></ul>С 19 мая 2026 года были обновлены следующие инструменты для сырых данных: Pull API, Data Locker и страница Raw Data Export.<br /><br />С 25 июня 2026 года были обновлены следующие инструменты сырых данных: Push API и API Get conversion data (GCD).<br /><br />Изменения:<ul><li>Ограничено (пустое) только поле `original_url`</li><li>Все остальные поля атрибуции полностью поддерживаются</li></ul>Вышеуказанные ограничения не применяются к вовлечённым просмотрам.<br /><br />Отчеты о необработанных данных по кликам и показам через Data Locker от tiktokglobal\_int ограничены. |
| <span id="uber"></span>Uber | Следующие ограничения применяются к атрибуции по просмотрам и кликам:<ul><li>Медиаисточник (uber\_int): доступен</li><li>Детали кампании: доступны</li></ul>Клики и показы из Uber не включаются в отчеты о сырых данных. |
| <span id="x-ads-formerly-twitter"></span>X Ads (ранее Twitter) | В некоторых случаях, в зависимости от выбора пользователя в X Ads, сырые данные могут быть ограничены на платформе AppsFlyer.<br /><br />**До 15 июля 2025 г.:** Атрибутированные события из X Ads вообще не появлялись в отчетах о сырых данных.<br /><br />**С 15 июля 2025 г.:** Атрибутированные события включаются в отчёты о сырых данных со следующими ограничениями:<ul><li>Медиаисточник (Twitter): доступен</li><li>Детали кампании: указаны как *restricted*</li><li>Канал (Twitter): доступен</li><li>Атрибутированный тип взаимодействия: доступно</li><li>Время атрибутированного взаимодействия: отражается только как дата (`dd/mm/yyyy`)</li></ul>Клики и показы из X Ads не включаются в отчеты о сырых данных.<br /><br />Доступ к неограниченным сырым данным зависит от участия в программе **Advanced Mobile Measurement (AMM)** от X Ads и настроек конфиденциальности конечного пользователя:<ul><li>AMM не включен: все клики и показы отправляются с `af_data_restriction=attribution`. Все итоговые события ограничены.</li><li>AMM не включен:<ul><li>Пользователи из ЕС: события ограничены, если не предоставлено разрешение на обмен данными с бизнес-партнерами.</li><li>Пользователи, которые не согласились делиться данными: события ограничены (`af_data_restriction=attribution`).</li><li>Пользователи, которые согласились делиться данными с бизнес-партнерами: события не ограничены (`af_data_restriction=none`).</li></ul></li></ul>Для получения дополнительной информации см. <Anchor target="_blank" href="/marketers/ru/docs/x-ads-formerly-twitter-ads-setup-guide-overview#конфиденциальность-пользователей-xads">руководство по настройке X Ads — раздел конфиденциальности пользователей</Anchor>. |

<div id="raw-data-context" />

### Контекст необработанных данных

Ограничение на уровне поля для необработанных данных зависит от контекста данных, как указано в таблице ниже.

| Тип ограничения | Задействованные отчеты |
| --- | --- |
| [Ограниченный медиа-источник](/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников): Откуда пришел пользователь | <ul><li>Атрибуция: установки, конверсии ретаргетинга и удаления</li><li>Внутренние события, сессии</li><li>Отчеты Protect360</li></ul> |
| Полностью ограничено | <ul><li>клики;</li><li>Показы</li><li>Заблокированные клики (Protect360)</li></ul> |

<div id="delivery-of-raw-data" />

### Предоставление необработанных данных

Данные атрибуции на уровне пользователя в AppsFlyer доступны с использованием следующих инструментов доставки необработанных данных:

* Отчет Data Locker
* Pull API необработанных данных
* push
* Страница экспорта Дэшборда
* Постбэки на сети
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">API получения данных о конверсии (GCD)</Anchor> в контексте API данных на стороне клиента на уровне пользователя

<div id="unavailable-attribution-fields" />

<Accordion title="Недоступные поля атрибуции">

Следующие поля недоступны, если медиа-источник ограничен:

| Отображаемое имя | Имя API |
| --- | --- |
| Реклама | af\_ad |
| ID рекламы | af\_ad\_id |
| Тип рекламы | af\_ad\_type |
| Блок рекламы | af\_adset |
| ID блока рекламы | af\_adset\_id |
| Окно лукбэк атрибуции | af\_attribution\_lookback |
| ID кампании | af\_c\_id |
| Канал | af\_channel |
| Валюта стоимости | af\_cost\_currency |
| Модель стоимости | af\_cost\_model |
| Значение стоимости | af\_cost\_value |
| Ключевые слова | af\_keywords |
| Партнер | af\_prt |
| ID сайта | af\_siteid |
| ID подсайта | af\_sub\_siteid |
| Подпараметр [n] (n=1-5) | af\_sub[n] (n=1-5) |
| Время атрибутированного касания | attributed\_touch\_time |
| Атрибутированный тип касания | attributed\_touch\_type (атрибутированный тип взаимодействия) |
| Кампания | campaign (кампания) |
| URL-адрес глубокого проникновения | deeplink\_url |
| HTTP-реферер | http\_referrer |
| Магазин приложений для установки | install\_app\_store |
| ID ключевого слова | keyword\_id |
| Тип соответствия ключевого слова | keyword\_match\_type |
| Тип соответствия | Местоположение устройства |
| ID аккаунта сети | network\_account\_id |
| Исходный URL-адрес | original\_url |
| Окно повторного вовлечения | af\_reengagement \_window |
| Страница продукта в магазине | страница\_Продукта\_магазина |

</Accordion>

<div id="identifier-restriction" />

<Accordion title="Ограничение идентификатора">

При применении ограничения по идентификатору доступны только поля, перечисленные в таблице, которая следует, в отчетах о необработанных данных.

| Имя API |
| --- |
| <span id="event_time"></span>время события |
| <span id="event_name"></span>название события |
| <span id="event_revenue"></span>event\_revenue |
| <span id="event_revenue_currency"></span>event\_currency |
| <span id="event_revenue_usd"></span>event\_revenue\_usd |
| <span id="af_cost_model"></span>af\_cost\_model |
| <span id="af_cost_value"></span>af\_cost\_value |
| <span id="af_cost_currency"></span>af\_cost\_currency |
| <span id="event_source"></span>источник события |
| <span id="media_source"></span>медиа-источник |
| <span id="af_channel"></span>af\_channel |
| <span id="campaign"></span>campaign (кампания) |
| <span id="af_c_id"></span>af\_c\_id |
| <span id="af_adset"></span>af\_adset |
| <span id="af_adset_id"></span>af\_adset\_id |
| <span id="af_ad"></span>af\_ad |
| <span id="af_ad_id"></span>af\_ad\_id |
| <span id="af_ad_type"></span>af\_ad\_type |
| <span id="af_siteid"></span>af\_siteid |
| <span id="af_sub_siteid"></span>af\_sub\_siteid |
| <span id="app_id"></span>app\_id (идентификатор приложения) |
| <span id="app_name"></span>имя приложения |
| <span id="bundle_id"></span>Авторизовано |
| <span id="is_retargeting"></span>is\_retargeting |
| <span id="retargeting_conversion_type"></span>тип\_конверсии\_ретаргетинга |
| <span id="is_primary_attribution"></span>is\_primary\_attribution |
| <span id="af_attribution_lookback"></span>af\_attribution\_lookback |
| <span id="af_reengagement_window"></span>af\_reengagement \_window |
| <span id="country_code"></span>код\_страны |
| <span id="blocked_reason"></span>заблокированная\_причина |
| <span id="blocked_reason_value"></span>заблокированное\_значение\_причины |
| <span id="blocked_reason_rule"></span>заблокированное\_правило\_причины |
| <span id="blocked_sub_reason"></span>заблокированная\_подпричина |
| <span id="platform"></span>платформа |
| <span id="is_paid_media"></span>is\_paid\_media |

</Accordion>

<div id="faq" />

## Часто задаваемые вопросы

<div id="what-events-are-restricted" />

<Accordion title="Какие события ограничены?">

Ограниченные события, как указано в [таблице выше](/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников), могут включать конверсии (установки, повторные вовлечения и реатрибуция) и связанные с ними внутренние события, к которым атрибутирована ограничивающая рекламная сеть.

</Accordion>

<div id="how-does-the-restricted-media-source-impact-raw-data-reports" />

<Accordion title="Как влияет ограниченный медиа-источник на отчеты о необработанных данных?">

* Поле *медиа-источник* заполнено *ограничено*.
* Поля атрибуции, перечисленные в этой статье, либо пусты, либо заполнены значением *null*.

**Пример отчета:** Установки <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vScXJznEex0WwdCy78Bm8LtrhbCk1jNy14O_t7etrq5ab5v4CIEiInfFD4B1EsZCE-_w-dVRAxl_cu4/pub?output=csv">ограниченных необработанных данных</Anchor> в CSV файл. Другие отчеты о необработанных данных заполняются аналогичным образом.

</Accordion>

<div id="how-does-the-restricted-media-source-impact-postbacks-sent-to-partners" />

<Accordion title="Как влияет ограниченный медиа-источник на постбеки, отправляемые партнерам?">

Постбеки, отправляемые партнерам, не содержат полей атрибуции.

</Accordion>

<div id="how-do-restricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="Как ограниченные события влияют на постбеки на сторонние платформы?">

Постбеки для атрибуцированных рекламных сетей, перечисленных в [таблице выше](#ограничения-медиа-источников), не отправляются на сторонние платформы.

</Accordion>

<div id="do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="Влияют ли неограниченные события на постбеки на сторонние платформы?">

Для событий, отправляемых на сторонние платформы, такие как платформы аналитики и маркетинга, см. <Anchor target="_blank" href="/marketers/ru/docs/discrepancies-between-appsflyer-and-third-party-platforms#ограничения-постбэков-на-сторонних-платформах">ограничения постбэков на сторонних платформах</Anchor>. В некоторых случаях постбэки для неограниченных событий не включают медиаисточник. Это означает, что атрибуция фиксируется как органическая.

</Accordion>

<div id="what-about-the-data-of-assists-that-form-part-of-the-attribution" />

<Accordion title="Что насчет данных по участиям, которые являются частью атрибуции?">

Данные, связанные с участиям, считаются данными атрибуции и недоступны.

</Accordion>

<div id="see-also" />

> 📄 **См. также**
>
> <Anchor target="_blank" href="/marketers/ru/docs/user-level-data-retention">Удержание данных на уровне пользователя</Anchor>

<div data-zendesk-anchors="raw-data-restriction=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 01H7WQHTV9RM2JF2BV45XF626H=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 media-source-restrictions=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0-%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%BE%D0%B2 01H7WQHTV9HJEHHH1N8VN6APX6=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0-%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%BE%D0%B2 01H7WQHTV90YFRP3Z9AEP7ACRD=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 raw-data-context=%D0%BA%D0%BE%D0%BD%D1%82%D0%B5%D0%BA%D1%81%D1%82-%D0%BD%D0%B5%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 01H7WQHTVA8H9FTBJ1FB6BJQ2A=%D0%BA%D0%BE%D0%BD%D1%82%D0%B5%D0%BA%D1%81%D1%82-%D0%BD%D0%B5%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 delivery-of-raw-data=%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 01H7WQHTVA0XP6B2H95EEM7EYD=unavailable-attribution-fields 01H7WQHTVA7ERWW1PC3DF5H0NP=identifier-restriction faq=%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B 01H7WQHTVA5439QPE6GNXNKJ63=%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01HDBND48E05P1WV51ZJGD072N=what-events-are-restricted 01H7WQHTVAHCK7QDZ5P25YRQ2D=how-does-the-restricted-media-source-impact-raw-data-reports 01H7WQHTVABKATP6B6XN4NRC54=how-does-the-restricted-media-source-impact-postbacks-sent-to-partners h_01HDBND48EDTAFBFXTADGWJADM=how-do-restricted-events-impact-postbacks-to-thirdparty-platforms h_01HE5TK3WSNBPM6W5D1Y9S6PDX=do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms 01H7WQHTVA60PWZ017WJMRTKVP=what-about-the-data-of-assists-that-form-part-of-the-attribution h_01HE7SCVN3VJ4Y6KF2QZSNBEMZ=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
