---
title: Полезная нагрузка в данных о конверсиях и сценарии использования
metadata:
  keywords:
    - Conversion
    - Retargeting
    - Installs
    - Re-attribution
    - Re-engagement
    - Developers
    - SRN
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-12-31T13:05:33Z'
  edited_at: '2026-08-18T00:13:48Z'
  id: 360000726098
  locale: ru
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/ru/articles/360000726098
---
> **At a glance:** **Краткий обзор:** Используйте данные о конверсии для определения различных сценариев конверсии, настройки пользовательского опыта и многого другого.

## Обзор

Следующее руководство содержит различные сценарии конверсии пользователей и соответствующие им полезные нагрузки в данных о конверсиях:

* [Привлечение пользователей (UA)](#данные-о-конверсиях-ua-с-srn)
* [Обязательный](#данные-о-конверсиях-ретаргетинга)

Данные о конверсиях доступны на платформе с помощью любого из следующих способов:

* <Anchor target="_blank" href="/marketers/ru/docs/raw-data-export-page">Отчеты по сырым данным</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/push-api-streaming-raw-data">push</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">SDK AppsFlyer</Anchor>

Из-за компромисса между точностью и задержкой данные о конверсиях для одних и тех же идентификаторов устройств могут отличаться в разных API.

### Поля в полезной нагрузке данных о неорганических конверсиях

#### Поля всегда доступны

В приведённой ниже таблице перечислены поля, которые всегда присутствуют для **неорганических** конверсий независимо от типа конверсии`media_source`.

| Название поля полезной нагрузки | Название поля сырых данных | Примечания |
| --- | --- | --- |
| `медиа-источник` | Медиа-источник | Атрибутированный издатель. Эквивалентно параметру `pid`pidpid в ссылках атрибуции. |
| `время_установки` | Время установки |  |
| `click_time` | Время атрибутированного касания | Время, когда произошел клик или показ, по UTC |
| `is_first_launch` | Н/Д | `true`, `false` |
| `af_status` | Сырые данные разделены на отдельные отчеты: органические, неорганические | `"Неорганический"` |
| `af_siteid` | Идентификатор сайта |  |
| `adgroup_id` | идентификатор рекламы |  |
| `рекламный набор` | Блок рекламы |  |
| `adset_id (идентификатор группы объявлений)` | идентификатор адсета |  |
| `agency (агентство)` | Партнер | `null` или название агентства (для кампаний, проводимых агентствами) |
| `campaign (кампания)` | Кампания |  |
| `campaign_id (идентификатор кампании)` | Идентификатор кампании |  |
| `http_referrer` | Источник ссылки HTTP |  |
| `тип_конверсии_ретаргетинга` | Тип конверсии ретаргетинга | "none", или retargeting\_conversion\_type |
| `af_sub[n] (n=1—5)` | Подпараметр [n] (n=1–5) |  |

#### Поля доступны в некоторых случаях

Поля в следующей таблице доступны в некоторых случаях, в зависимости от того, как SRN заполняет отдельное событие.

<table><thead><tr><th>Название полей полезной нагрузки</th><th>Название поля сырых данных</th><th>Примечания</th><th> </th></tr></thead><tbody><tr><td><code>af_channel</code></td><td>Канал</td><td><p>SRN, заполняющие этот параметр:</p><ul><li>AppLovin</li><li>Google реклама</li><li>Meta реклама</li><li>Snapchat</li><li>TikTok для бизнеса</li><li>Twitter</li></ul><p>Пример: Facebook—Instagram, Google—YouTube </p></td><td> </td></tr><tr><td><code>orig_cost</code></td><td> </td><td>Примечание (1)</td><td> </td></tr><tr><td><code>cost_cents_USD</code></td><td> </td><td>Примечание (1)</td><td> </td></tr><tr><td><code>af_cpi</code></td><td> </td><td>Примечание (1)</td><td> </td></tr><tr><td colspan="4"><p><strong>Примечание</strong></p><p>(1) Поля затрат заполняются значениями, предоставленными рекламной сетью. Для того чтобы рекламная сеть предоставляла затраты в AppsFlyer, необходимо включить интеграцию затрат на странице <a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank"><strong>Активные интеграции</strong></a>. Некоторые SRN поддерживают предоставление данных о затратах в массовом порядке. В этом случае поля стоимости на уровне события возвращаются со значением 0. </p></td></tr></tbody></table>

### Дополнительные поля

* <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#параметры-ссылки-атрибуции">Список параметров AppsFlyer</Anchor>
* Вы можете добавить параметры к ссылке атрибуции, они становятся доступными в полезной нагрузке

Дополнительную информацию см. в <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary#data-fields-dictionary">словаре полей сырых данных</Anchor>.

### Ограничения

<div id="custom-parameter-names" />

<Accordion title="Названия настраиваемых параметров">

Пользовательские параметры не могут быть вызваны `name` (строчная "n". `Name` допустимо).

Если параметр называется `name`, он удаляется из полезной нагрузки.

</Accordion>

---

## Данные о конверсиях UA с SRN

<Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns">Сети с собственной отчетностью</Anchor> (SRN) — это рекламные сети, использующие собственные механизмы атрибуции, например Meta Ads и Google.

В SRN не используются ссылки атрибуции. Это означает, что:

* Поля полезной нагрузки предопределены
* Вы не можете добавлять поля в полезную нагрузку, добавляя параметры к ссылке атрибуции.

SRN сообщают о конверсиях в AppsFlyer. Данные о конверсиях доступны в приложении. Доступные поля зависят от конкретной SRN и подробно описаны на отдельных вкладках SRN ниже.

#### Примечание о Meta Ads

Если вы проводите кампании в Meta Ads и не подписываете условия обслуживания Meta Ads, установку атрибутирует AppsFlyer. Доступность отчетов ограничена следующим образом:

* **Доступно:** Агрегированные и аналитические дэшборды и отчеты
* **Недоступно:** Необработанные данные

<Tabs>
<Tab title="Meta реклама">

### Данные о конверсии Meta Ads

| Название поля | Примечания | Источник данных |
| --- | --- | --- |
| `Местоположение устройства` | `srn`, `gp_referrer` | AF |
| `медиа-источник` | Всегда`Facebook Ads` | AF |
| `agency (агентство)` | `null` или содержит название агентства при <Anchor target="_blank" href="/partners/ru/docs/about-agency-accounts#конфигурации-srn">запуске кампаний Meta ads</Anchor> | Meta реклама |
| `http_referrer` | Всегда`null` | Meta реклама |
| `тип_конверсии_ретаргетинга` |  | AF |
| `af_channel` |  | Meta Ads (publisher\_platform) |
| `af_status` | Всегда`Non-organic` | AF |
| `ad_id (идентификатор объявления)` | Только для внутреннего использования Meta Ads. | Meta Ads (ad\_id) |
| `click_time` |  | AF |
| `время_установки` |  | AF |
| `is_first_launch` | `true`, `false` | Устройство |
| `adset_id (идентификатор группы объявлений)` | Доступно в сырых данных: Идентификатор группы объявлений | Meta Ads (campaign\_id) |
| `is_fb` | Всегда`true` | AF |
| `campaign (кампания)` | Доступно в сырых данных: Название кампании | Meta Ads (campaign\_group\_name) |
| `campaign_id (идентификатор кампании)` | Доступно в сырых данных: Идентификатор кампании | Meta Ads (campaign\_group\_id) |
| `is_paid` | Всегда`true` | Meta реклама |
| `adgroup` | Доступно в сырых данных: Реклама | Meta Ads (adgroup\_name) |
| `adgroup_id` | Доступно в сырых данных: идентификатор рекламы | Meta Ads (adgroup\_id) |
| `рекламный набор` | Доступно в сырых данных: Блок рекламы | Meta Ads (campaign\_name) |
| `af_siteid` | **af\_siteid mapping:**  <br />  <br />***publisher\_platform***         → ***af\_siteid***  <br />Facebook                           → ""  <br />Instagram                           → Instagram  <br />AudienceNetwork              → AudienceNetwork  <br />Мессенджер                     → Мессенджер  <br />неизвестно                        → неизвестно  <br />"" + is\_instagram=true      → Instagram  <br />"" + is\_external=true         → AudienceNetwork | Meta реклама |
| `af_sub[1-5]` | Всегда`null` | Рекламодатель |

**Примечание:** Поля, связанные с затратами, недоступны, поскольку Meta Ads не предоставляет данные о затратах при конверсии. Если <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-integration-setup#cost-clicks-and-impressions">предоставление затрат</Anchor> включено, Meta Ads делится данными о затратах с AppsFlyer несколько раз в день.

</Tab>

<Tab title="Google реклама">

<div id="google-ads-conversion-data" />

### Данные о конверсиях в Google Ads

<table><thead><tr><th>Имя поля</th><th>Ретаргетинг</th></tr></thead><tbody><tr><td><code>Местоположение устройства</code></td><td> Всегда<code>srn</code> </td></tr><tr><td><code>медиа-источник</code></td><td>Всегда<code>googleadwords_int</code> </td></tr><tr><td><code>agency (агентство)</code></td><td> <code>none</code> или значение <code>af_prt</code> </td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>тип_конверсии_ретаргетинга</code></td><td> </td></tr><tr><td><code>af_channel</code></td><td>Примечание (1)</td></tr><tr><td><code>af_status</code></td><td>Всегда<code>Non-organic</code> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>время_установки</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> <code>true</code>, <code>false</code> </td></tr><tr><td><code>adgroup_name</code></td><td> </td></tr><tr><td><code>adset_id (идентификатор группы объявлений)</code></td><td>Всегда<code>null</code> </td></tr><tr><td><code>campaign (кампания)</code></td><td>Примечание (3)</td></tr><tr><td><code>campaign_id (идентификатор кампании)</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>рекламный набор</code></td><td>Примечание (3)</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>ad_event_id</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td>Пустая строка</td></tr><tr><td><code>af_ad_id</code></td><td>Доступно в необработанных данных, когда Google возвращает значение <code>creative_id</code>.</td></tr><tr><td><code>af_ad_type</code></td><td><span>Тип объявления AdWords</span></td></tr><tr><td><code>af_adset</code></td><td>Доступно в сырых данных:  Блок рекламы</td></tr><tr><td><code>af_adset_id</code></td><td>Доступно в сырых данных:  Идентификатор группы объявлений</td></tr><tr><td><code>af_c_id</code></td><td>Доступно в сырых данных:  Идентификатор кампании</td></tr><tr><td><code>af_click_lookback</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Примечание (2)</td></tr><tr><td><code>af_dp</code></td><td>Актуально только для кампаний <a href="./google-ads-adwords-integration-setup-for-advertisers#использование-отложенного-диплинкинга-в-кампаниях-для-приложений" target="_blank">Google для приложений в ленте</a>.</td></tr><tr><td><code>af_keywords</code></td><td>Доступно в сырых данных:  Ключевые слова</td></tr><tr><td><code>af_prt</code></td><td> <code>none</code> или значение <code>af_prt</code> </td></tr><tr><td><code>af_reengagement _window</code></td><td>Доступно в сырых данных:  Окно повторного вовлечения </td></tr><tr><td><code>af_viewthrough_lookback</code></td><td>Доступно в сырых данных:  Окно ретроспективного обзора для атрибуции по просмотрам</td></tr><tr><td><code>click_url</code></td><td>Доступно в сырых данных:  Источник ссылки HTTP</td></tr><tr><td><code>click-timestamp</code></td><td>Источник: AppsFlyer</td></tr><tr><td><code>cost_cents_USD</code></td><td>Примечание (2)</td></tr><tr><td><code>external_account_id</code></td><td>Идентификатор аккаунта AdWords</td></tr><tr><td><code>gclid</code></td><td> </td></tr><tr><td><code>lat</code></td><td> </td></tr><tr><td><code>network</code></td><td>Примечание (1)</td></tr><tr><td><code>orig_cost</code></td><td>Примечание (2)</td></tr><tr><td><code>video_id</code></td><td>Всегда<code>null</code> </td></tr><tr><td colspan="2"> <strong>Примечания</strong><br/>(1) Google использует несколько рекламных сетей. Используйте <code>af_channel</code> в сочетании с <code>network</code>, чтобы определить источник установки.<br/>(2) Эти поля возвращаются как 0. Если рекламодатель включает совместное использование затрат, Google отправляет данные о затратах AppsFlyer несколько раз в день.<br/>(3) Используйте <code>campaign</code> и <code>af_adset</code>, чтобы персонализировать контент пользователя.</td></tr></tbody></table>

</Tab>

<Tab title="ASA">

<div id="apple-search-ads-conversion-data" />

### Данные о конверсии Apple Search Ads

<table><thead><tr><th>Название поля</th><th>Примечания</th></tr></thead><tbody><tr><td><code>Местоположение устройства</code></td><td>Всегда<code>srn</code> </td></tr><tr><td><code>медиа-источник</code></td><td>Всегда<code>Apple Search Ads</code> </td></tr><tr><td><code><del>adset</del></code></td><td>Примечание (2)</td></tr><tr><td><code>adset_id (идентификатор группы объявлений)</code></td><td> </td></tr><tr><td><code><del>af_adset</del></code></td><td>Примечание (2)</td></tr><tr><td><code>af_adset_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_click_lookback</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Примечание (1)</td></tr><tr><td><code><del>af_keywords</del></code></td><td>Примечание (2) — Используйте ID ключевых слов</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>Всегда<code>Non-organic</code> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>agency (агентство)</code></td><td> <code>null</code> или значение <code>af_prt</code> </td></tr><tr><td><code><del>campaign</del></code></td><td>Примечание (2)</td></tr><tr><td><code>campaign_id (идентификатор кампании)</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> <code>true</code>, <code>false</code> </td></tr><tr><td><code>cost_cents_USD</code></td><td>Примечание (1)</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>время_установки</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>Примечание (1)</td></tr><tr><td><code>тип_конверсии_ретаргетинга</code></td><td> </td></tr><tr><td colspan="3"> <strong>Примечания</strong><br/>(1) Apple Search Ads поддерживает предоставление данных о затратах в массовом порядке, а не в данных о конверсии.<br/>(2) Устарело с 15 февраля 2021 года в связи с тем, что Apple Search Ads принял API AdServices. </td></tr></tbody></table>

</Tab>

<Tab title="Snapchat">

<div id="snapchat-conversion-data" />

### Данные о конверсиях Snapchat

| Имя поля | Примечания |
| --- | --- |
| `Местоположение устройства` | `srn`, `gp_referrer`, `id_matching`, `probabilistic`   <br />Как продвинутый SRN, поддерживает все типы сопоставлений. |
| `медиа-источник` | `snapchat_int` |
| `рекламный набор` |  |
| `adset_id (идентификатор группы объявлений)` |  |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_c_id` |  |
| `af_channel` |  |
| `af_cpi` |  |
| `af_siteid` |  |
| `af_status` | Всегда`Non-organic` |
| `af_sub[1-5]` |  |
| `af_viewthrough_lookback` |  |
| `agency (агентство)` |  |
| `campaign (кампания)` |  |
| `campaign_id (идентификатор кампании)` |  |
| `click_time` |  |
| `cost_cents_USD` |  |
| `http_referrer` |  |
| `время_установки` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `orig_cost` |  |
| `тип_конверсии_ретаргетинга` |  |

</Tab>

<Tab title="Twitter">

<div id="twitter-conversion-data" />

### Данные конверсий X Ads

| Имя поля | Примечания |
| --- | --- |
| `Местоположение устройства` | Всегда`srn` |
| `медиа-источник` | Всегда`Twitter` |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_channel` |  |
| `af_siteid` |  |
| `af_status` | Всегда`Non-organic` |
| `af_sub[1-5]` |  |
| `agency (агентство)` | Всегда`null` |
| `campaign (кампания)` |  |
| `campaign_id (идентификатор кампании)` | `null` или идентификатор кампании |
| `click_time` |  |
| `http_referrer` |  |
| `время_установки` |  |
| `is_first_launch` | `true`, `false` |
| `adgroup` |  |
| `adgroup_id` |  |
| `тип_конверсии_ретаргетинга` | Всегда`none` |

**Примечание:** Поля затрат не появляются в полезной нагрузке, поскольку X Ads не поддерживает предоставление данных о затратах.

</Tab>

<Tab title="TikTok">

<div id="tiktok-conversion-data" />

### Данные конверсий TikTok for Business

| Имя поля | Примечания |
| --- | --- |
| `Местоположение устройства` | `srn`, `gp_referrer`, `id_matching`, `probabilistic`   <br />Как продвинутый SRN, поддерживает все типы сопоставлений. |
| `медиа-источник` | `tiktokglobal_int` |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_channel` | `tiktok`, `pangle` |
| `af_siteid` |  |
| `af_status` | Всегда`Non-organic` |
| `af_sub[1-5]` |  |
| `agency (агентство)` |  |
| `campaign (кампания)` |  |
| `campaign_id (идентификатор кампании)` |  |
| `click_time` |  |
| `http_referrer` |  |
| `время_установки` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `тип_конверсии_ретаргетинга` |  |

**Примечание:** Поля затрат не появляются в полезной нагрузке, поскольку TikTok не поддерживает предоставление данных о затратах.

</Tab>

<Tab title="Oath">

<div id="oath-ad-platforms-conversion-data" />

### Данные о конверсиях Oath Ad Platforms

<table><thead><tr><th>Имя поля</th><th>Примечания</th></tr></thead><tbody><tr><td><code>Местоположение устройства</code></td><td>Всегда<code>srn</code> </td></tr><tr><td><code>медиа-источник</code></td><td>Всегда<code>yahoogemini_int</code> </td></tr><tr><td><code>рекламный набор</code></td><td> </td></tr><tr><td><code>adset_id (идентификатор группы объявлений)</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td> </td></tr><tr><td><code>af_ad_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Примечание (1)</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>Всегда<code>Non-organic</code> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>agency (агентство)</code></td><td> </td></tr><tr><td><code>campaign (кампания)</code></td><td> </td></tr><tr><td><code>campaign_id (идентификатор кампании)</code></td><td> </td></tr><tr><td><code>тип_кампании</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>cost_cents_USD</code></td><td>Примечание (1)</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>время_установки</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>Примечание (1)</td></tr><tr><td><code>тип_конверсии_ретаргетинга</code></td><td> </td></tr><tr><td colspan="2"> <strong>Примечание</strong><br/>(1) Oath поддерживает предоставление данных о затратах, но отправляет связанные с расходами данные пакетом, а не в виде данных о конверсиях.</td></tr></tbody></table>

</Tab>
</Tabs>

## Конверсия UA с другими рекламными сетями

Для других рекламных сетей данные в полезной нагрузке напрямую зависят от параметров <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">в ссылке атрибуции</Anchor>.

Изучите следующие полезные нагрузки JSON.

**Примечание!** Данные конверсий возвращаются в виде структуры в формате карты. Разработчик **не** взаимодействует с сырым файлом JSON.

<div id="applovin" />

<Accordion title="Applovin">

#### Ссылка атрибуции:

```http HTTPS
https://app.appsflyer.com/com.company.app?af_ad=ad_name&af_ad_type=INTER
  &af_channel=video&af_siteid=123_site_id&af_c_id=b8******************************&
  af_adset=_DEFAULT&pid=applovin_int&c=campaign_name
  &af_click_lookback=7d&clickid=10****************
  &advertising_id=50********************************&af_ip=
```

#### Полезная нагрузка:

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "applovin_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:49:54.186",
      "adgroup_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-24 14:29:33.738",
      "agency": null,
      "cost_cents_USD": "0",
      "af_ad_type": "INTER",
      "af_c_id": "b8******************************",
      "adset": null,
      "advertising_id": "50********************************",
      "af_sub1": null,
      "clickid": "10****************",
      "af_click_lookback": "7d",
      "af_siteid": "123_site_id",
      "af_ad": "ad_name",
      "http_referrer": null,
      "af_channel": "video",
      "af_adset": "_DEFAULT",
      "af_sub5": null,
      "af_sub4": null,
      "af_cpi": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* Параметры в ссылке атрибуции появляются как поля в полезной нагрузке
* Другие поля в полезной нагрузке, которые **не входят в ссылку атрибуции**, отображаются со значением null.
* AppLovin поддерживает предоставление данных о затратах на рекламу, но отправляет данные о затратах в AppsFlyer в массовом порядке. Поля, связанные с затратами, возвращаются как 0.

</Accordion>

<div id="ironsource" />

<Accordion title="IronSource">

#### Ссылка атрибуции:

```http HTTPS
https://app.appsflyer.com/id123456789?
  af_ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &clickid=ab*******************&redirect=false
  &ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &af_lang=pt&imei=&af_sub1=&advertising_id=&af_ip=192.168.0.1&pid=ironsource_int
  &device_ip=192.168.0.1&c=campaign_name
  &idfa=01**********************************&af_siteid=123_site_id&
  af_enc_data=cN*********************************************************************
```

#### Полезная нагрузка:

```json
{
      "adgroup": null,
      "af_enc_data": "cN**************************************************************************************",
      "campaign": "campaign_name",
      "media_source": "ironsource_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:59:32.194",
      "adgroup_id": null,
      "redirect": "false",
      "orig_cost": "0.75",
      "click_time": "2018-12-30 23:58:54.517",
     "agency": null,
      "cost_cents_USD": "75",
      "adset": null,
      "advertising_id": "35**********************************",
      "af_sub1": null,
      "af_ip": "192.168.0.1",
      "clickid": "ab*******************",
      "af_sub3": null,
      "af_cost_value": "0.75",
      "af_ref": "ironsource_5f******************************************",
      "af_siteid": "123_site_id",
      "http_referrer": null,
      "af_cost_model": "cpi",
      "af_ua": "Mozilla/5.0 (Linux; Android 8.0.0; SM-N950F Build/R16NW; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/71.0.3578.99 Mobile Safari/537.36",
      "af_cost_currency": "USD",
      "af_sub5": null,
      "af_sub4": null,
      "af_lang": "en",
      "af_cpi": null,
      "af_click_lookback": "7d",
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

ironSource делится данными о затратах с AppsFlyer при конверсии, используя поля `orig_cost`, `cost_cents_USD` и `af_cost_value`.

Однако данные, связанные с затратами, **не появляются в ссылке атрибуции**. ironSource шифрует данные о затратах и сохраняет их в поле `af_enc_data`.

</Accordion>

## Данные о конверсиях ретаргетинга

Ретаргетинг включает в себя два типа конверсий: реатрибуция и повторное вовлечение.

> 👍 **Tip**
>
> **Совет**
>
> Данные о конверсиях для ретаргетинга не всегда дают четкое представление о типе конверсии. См. [альтернативные источники данных о конверсиях](#альтернативные-источники-данных-о-конверсиях).

### Реатрибуция с SRN

Когда пользователь повторно атрибутируется через SRN, полезная нагрузка данных о конверсии не указывает, что это кампания ретаргетинга. Поскольку SRN не используют ссылки атрибуции, нет возможности установить параметр `is_retargeting=true` в ссылке атрибуции. Для **SRN, которые поддерживают ретаргетинг**, AppsFlyer определяет, следует ли повторно атрибутировать пользователя или нет.

Это означает, что на уровне SDK нет способа определить, пришла ли установка из ретаргетинговой кампании. Единственный способ — задать название кампании таким образом, чтобы оно указывало на ретаргетинговую кампанию.

> 📘 **Note**
>
> **Примечание**
>
> Название кампании, которое указывает на ретаргетинг, **не является надежным методом**. [Подробнее см. в примерах](#примеры-смешанного-привлечения-пользователей-и-реатрибуции).

### Реатрибуция с обычными рекламными сетями

Атрибуция к рекламным сетям основывается на ссылках атрибуции. Будь то обычные ссылки атрибуции или OneLink, при использовании для ретаргетинга ссылка атрибуции всегда имеет параметр `is_retargeting=true`.

<div id="retargeting-campaign-with-criteo" />

<Accordion title="Ретаргетинговая кампания с Criteo">

#### Ссылка атрибуции

```http
https://app.appsflyer.com/id1234567895?pid=criteo_int&af_click_lookback=30d&
  c=campaign_name&is_retargeting=true&redirect=false&idfa=68**********************************
  &af_reengagement_window=30d
```

#### Полезная нагрузка данных о конверсиях

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "criteo_int",
      "retargeting_conversion_type": "re-attribution",
      "adset_id": null,
      "campaign_id": null,
      "af_reengagement_window": "30d",
      "install_time": "2018-12-01 23:13:03.126",
      "adgroup_id": null,
      "redirect": "false",
      "af_sub5": null,
      "click_time": "2018-11-18 20:02:31.559",
      "agency": null,
      "cost_cents_USD": "0",
      "is_retargeting": "true",
      "af_cpi": null,
      "af_click_lookback": "30d",
      "af_siteid": null,
      "idfa": "68**********************************",
      "http_referrer": null,
      "orig_cost": "0.0",
      "af_sub4": null,
      "adset": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* Параметр `retargeting_conversion_type` указывает на тип ретаргетинга. Это может быть либо реатрибуция, либо повторное вовлечение, либо ни то, ни другое.
* Параметр `is_retargeting: true` указывает, что установка является повторной атрибутированной установкой.
* `af_reengagement_window`: Окно атрибуции после повторного вовлечения — это количество дней, в течение которых событие можно атрибутировать **повторно вовлеченному пользователю**. Поскольку речь идет о конверсии реатрибуции, этот параметр является избыточным.

</Accordion>

### Реатрибуция с отложенном диплинкингом

Часто требуется направить по диплинку повторно атрибутированных пользователей, у которых, по определению реатрибуции, приложение не установлено. Например, вы проводите кампанию, цель которой — вернуть пользователей, удаливших приложение. Кампания продвигает продукт или услугу, и вы хотите предоставлять пользователям контент, связанный с рекламируемым продуктом или услугой.

Это называется отложенным диплинкингом. Полезная нагрузка данных о конверсиях для отложенного диплинкинга поступает из метода `onConversionDataSuccess`.

<div id="deferred-deep-linking-with-srns" />

<Accordion title="Отложенные диплинки в сетях типа SRN">

Параметры диплинкинга, заданные в рекламных кампаниях SRN, за пределами этой SRN недоступны. К этим параметрам относится и параметр `af_dp`, в котором содержится схема пути в приложении. Единственным исключением является использование кампаний <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers#использование-отложенного-диплинкинга-в-кампаниях-для-приложений">Google для приложений в ленте</Anchor>. Для использования отложенного диплинкинга для рекламных кампаний в SRN необходимы дополнительные алгоритмы. Используйте данные в ответе `onConversionSuccess`, такие как кампания, группа объявлений, рекламный блок, чтобы запрограммированно перенаправлять пользователей.

#### Данные о конверсиях для отложенного диплинкинга с Meta Ads

<Tabs>
<Tab title="Android;">

```json
{
     "adset":"Adidas Running Shoes Women",
       "adgroup": null,
     "campaign_id":"6**********",
     "af_status":"Non-organic",
     "retargeting_conversion_type": "none",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
     "is_first_launch":true,
     "click_time":"2017-07-18 12:55:05",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "campaign":"running shoes summer collection",
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "media_source":"Meta ads",
     "install_time":"2017-07-19 08:06:56.189",
     "af_sub2":null
  }
```

</Tab>

<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

```json
  {
     "media_source":"Meta ads",
     "campaign":"running shoes summer collection",
     "adset":"Running Shoes Women",
     "adgroup":null,
     "campaign_id":"6**********",
     "retargeting_conversion_type": "none",
     "af_status":"Non-organic",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
   "is_first_launch":true,
     "click_time":"2017-07-17 16:23:18",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "install_time":"2017-07-18 15:10:50.190",
     "af_sub2":null
  }
```

</Tab>
</Tabs>

Вы можете использовать данные в ответе getConversionData, такие как кампания, группа объявлений и т.д., для программного перенаправления пользователей и показа им соответствующего контента.

> 📘 **Note**
>
> **Полезная нагрузка**
>
> Приложение представляет собой приложение для электронной коммерции, которое специализируется на спортивной одежде. Пользователь, у которого приложение не установлено, взаимодействует с рекламой и устанавливает приложение. После запуска приложения SDK возвращает данные о конверсии. Разработчик заставляет приложение открыть активность **летняя коллекция беговой обуви** (кампания) в магазине и показать категорию **беговая обувь для женщин** (группа объявлений).

</Accordion>

<div id="deferred-deep-linking-with-attribution-links" />

<Accordion title="Отложенный диплинкинг со ссылками атрибуции">

Есть три способа диплинкинга пользователей:

#### Схема URI

При использовании схем URI, как для ссылок атрибуции, так и для OneLink, ссылка атрибуции и полезная нагрузка выглядят следующим образом:

**Ссылка атрибуции**

```http
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**Универсальные ссылки OneLink**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true&af_dp=superapp%3A%2F%2deeplink-activity
```

**Полезная нагрузка**

```json
{
      "af_deeplink": true,
      "campaign": "campaign_name",
      "media_source": "media_source_name",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-30 23:59:09",
      "install_time": "2018-12-30 23:59:39.330",
      "agency": null,
      "cost_cents_USD": "0",
      "adset": "AD_SET_NAME",
      "ad_id": "AD_ID",
      "af_siteid": null,
      "http_referrer": null,
      "af_cpi": null,
      "af_sub5": null,
      "af_sub4": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic",
      "scheme": "superapp",
      "host": "deeplink_activity"
  }
```

* `af_deeplink: true` — при появлении этого параметра со значением true найдите поля `scheme` и `host`.
* `scheme` и `host` — эти поля берутся из параметра `af_dp` в ссылке атрибуции и указывают схему и активность, на которую пользователь должен быть перенаправлен по диплинку.

#### Универсальные ссылки iOS и Android App Links

Это два других из трех способов осуществления диплинкинга.

При использовании универсальных ссылок iOS и Android App Links, ссылка OneLink и полезная нагрузка выглядят следующим образом:

**Универсальные ссылки OneLink**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true
```

**Полезная нагрузка**

```json
{
      "install_time": "2019-01-08 16:24:49.853",
      "cost_cents_USD": "0",
      "campaign": "campaign_name",
      "retargeting_conversion_type": "none",
      "is_first_launch": true,
      "click_time": "2019-01-08 16:24:14.322",
      "af_click_lookback": "7d",
      "orig_cost": "0.0",
      "af_status": "Non-organic",
      "iscache": "true",
      "shortlink": "71ba577e",
      "media_source": "media_source_name",
      "is_retargeting": true
  }
```

* Поле `shortlink` указывает на конкретную ссылку OneLink, по которой пришел пользователь. Оно помогает разработчику понять, как действовать дальше в плане запуска активности и показа контента. Для этой цели можно использовать и другие поля, такие как `campaign`.

  > 🚧 **Important**
  >
  > **Двоеточие (:)**
  >
  > Поле `shortlink` не появляется в полезной нагрузке при использовании длинной ссылки OneLink.
  >
  > В обоих случаях (короткая или длинная ссылка OneLink) мы рекомендуем добавить настраиваемый параметр, указывающий на активность. Например: `&deep_link_activity=shoes_cateogry`


> 📘 **Note**
>
> **Примечания**
>
> Использование универсальных ссылок iOS и Android App Links возможно только с OneLink.

</Accordion>

### Повторное вовлечение с SRN

Как и в случае с кампаниями реатрибуции, когда пользователь повторно вовлекается через SRN, данные о конверсиях не указывают на то, что это кампания повторного вовлечения. Вы можете задать название кампании так, чтобы оно указывало на кампанию повторного вовлечения.

### Повторное вовлечение с обычными рекламными сетями

Здесь также данные о конверсиях не указывают на то, что пользователь пришел из кампании по повторному вовлечению. Чтобы преодолеть это ограничение, вы можете задать название кампании, указывающее на повторное вовлечение.

### Повторное вовлечение с диплинкингом

Основная часть повторного вовлечения заключается в том, чтобы направить пользователя на определенную активность. Например, если вы рекламируете какой-то товар или распродажу. В таких случаях вы хотите направить пользователей, нажавших на объявление, прямо на страницу приложения, посвященную данному товару или распродаже.

Для этого используется диплинкинг. Данные о конверсиях в диплинкинге действительно важны. В них хранится информация, необходимая разработчику для настройки опыта пользователей и направления их на нужную активность.

<div id="reengagement-deep-linking-with-srns" />

<Accordion title="Повторное вовлечение: диплинкинг с SRN">

Данные о конверсиях недоступны, если повторно вовлеченный пользователь пришел из SRN. Разработчику необходимо использовать методы SRN, чтобы получить данные при запуске приложения.

</Accordion>

<div id="reengagement-deep-linking-with-ad-networks" />

<Accordion title="Повторное вовлечение: диплинкинг с рекламными сетями">

Когда пользователь повторно вовлечен и запускает приложение, в методе `onAppOpenAttribution` доступны следующие данные о конверсии:

Как в iOS, так и в Android, при использовании короткой версии OneLink данные о конверсиях представляют собой структурированное сопоставление всех параметров в ссылке:

Пример:

```json
{
     af_dp: "superapp://Deeplink",
     pid: "media_source_name"
     c: "campaign_name",
     link: "https://abcd.onelink.me/12ab/12ab34c"
     is_retargeting: true
  }
```

* Разработчик приложения может использовать такие параметры, как `af_dp` и название кампании, чтобы направить пользователя на определенную активность и показать соответствующий контент.

> 🚧 **Important**
>
> **Двоеточие (:)**
>
> Мы рекомендуем использовать короткую версию OneLink. Подробнее см. <Anchor target="_blank" href="/marketers/ru/docs/understand-onelink-short-vs-long-urls">здесь</Anchor>.

Еще одна причина использовать короткую версию OneLink — это структура данных о конверсиях, которую возвращает длинная версия ссылки. При использовании длинной версии данные о конверсиях представляют собой сопоставление с единственным полем `link`, в котором содержится вся длинная ссылка OneLink.

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

### Альтернативные источники данных о конверсиях

* Push API предлагает подробную информацию о конверсиях, которая указывает на реатрибуцию или повторное вовлечение. Полезная нагрузка Push API включает поле под названием `re_targeting_conversion_type`. В этом поле указывается тип конверсии — реатрибуция или повторное вовлечение. Подробнее см. в нашем руководстве по <Anchor target="_blank" href="/marketers/ru/docs/push-api-streaming-raw-data">Push API</Anchor>.
* Отчеты по сырым данным также содержат указатели на типа конверсии. В отчете по сырым данным для конверсий ретаргетинга есть колонка ***Название события***. Значение в этой колонке — либо ***повторное вовлечение***, либо ***реатрибуция*** в зависимости от типа конверсии.

### Примеры смешанного привлечения пользователей и реатрибуции

> 📘 **Note**
>
> **Не применимо**
>
> 1. Пользователь устанавливает ваше приложение, а затем удаляет его. Акт установки помещает пользователя в окно <Anchor target="_blank" href="/marketers/ru/docs/set-up-re-attribution-window">реатрибуции</Anchor>. Вы создаете кампанию по привлечению пользователей (не ретаргетинг) в Meta Ads. Вы также настроили интеграцию AppsFlyer с Meta Ads, чтобы разрешить ретаргетинг.
>
>    Находясь в окне реатрибуции, пользователь видит рекламу, нажимает на нее и переустанавливает приложение. Насколько AppsFlyer видит, пользователь является повторно атрибутированным пользователем.
>
>    Это объясняется двумя факторами:
>
>    1. Конфигурация с Meta Ads позволяет использовать ретаргетинг
>    2. Пользователь находится в окне реатрибуции
>
>    В этом случае название кампании не указывает на реатрибуцию.
> 2. Возьмем тот же пример, только на этот раз пользователь находится за пределами окна реатрибуции. В этом случае установка является новой неорганической установкой.
> 3. Давайте рассмотрим другой пример. Вы настроили кампанию ретаргетинга в Meta Ads. Некоторые пользователи видят кампанию и устанавливают приложение. Однако эти пользователи устанавливают приложение впервые. Такие пользователи не считаются повторно атрибутированными пользователями. Вместо этого AppsFlyer рассматривает их как пользователей, которые пришли в результате кампании по привлечению пользователей.

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01HCY86CKDJK9TNHPAZB0QX2ZX=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 nonorganic-conversion-data-payload-fields=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%B2-%D0%BF%D0%BE%D0%BB%D0%B5%D0%B7%D0%BD%D0%BE%D0%B9-%D0%BD%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%BD%D0%B5%D0%BE%D1%80%D0%B3%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D1%85-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85 h_01HCY86CKDEMB3428YHCNJQA5R=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%B2-%D0%BF%D0%BE%D0%BB%D0%B5%D0%B7%D0%BD%D0%BE%D0%B9-%D0%BD%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%BD%D0%B5%D0%BE%D1%80%D0%B3%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D1%85-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85 fields-always-available=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%B2%D1%81%D0%B5%D0%B3%D0%B4%D0%B0-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B h_01HCY86CKDBQRGAY7GHNBJE4WK=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%B2%D1%81%D0%B5%D0%B3%D0%B4%D0%B0-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B fields-available-in-some-cases=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B-%D0%B2-%D0%BD%D0%B5%D0%BA%D0%BE%D1%82%D0%BE%D1%80%D1%8B%D1%85-%D1%81%D0%BB%D1%83%D1%87%D0%B0%D1%8F%D1%85 h_01HCY86CKDYQMYB9BQ4MXWP8A5=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B-%D0%B2-%D0%BD%D0%B5%D0%BA%D0%BE%D1%82%D0%BE%D1%80%D1%8B%D1%85-%D1%81%D0%BB%D1%83%D1%87%D0%B0%D1%8F%D1%85 additional-fields=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8F h_01HCY86CKD47M85AZVEA5C4JH7=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8F limitations=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HCY86CKEFX646H9BSKSFGZ36=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HCY86CKEZ2483XB461M2C9EC=custom-parameter-names ua-conversion-data-with-srns=%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85-ua-%D1%81-srn h_01EGKTQN6XDYHA60P2WKHBBVFT=%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85-ua-%D1%81-srn a-note-about-facebook=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BE-meta-ads h_01HCY86CKENFEGX53G9G4SGPSK=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BE-meta-ads facebook-conversion-data=%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-metaads h_01HCY86CKE658H36F3VJQMATQK=%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-metaads h_01HCY86CKF6FY96PAWB5Y7YXSQ=google-ads-conversion-data h_01HCY86CKFMNNNJZTPGK4870YN=apple-search-ads-conversion-data h_01HCY86CKF26JRT64JR9JZEAKJ=snapchat-conversion-data h_01HCY86CKFM94SQWYARCM0GEJ9=twitter-conversion-data h_01HSQRQSK8W9K6871K0EWHDF76=tiktok-conversion-data h_01HCY86CKFS5SJBECSY42VRJWP=oath-ad-platforms-conversion-data ua-conversion-with-other-ad-networks=%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F-ua-%D1%81-%D0%B4%D1%80%D1%83%D0%B3%D0%B8%D0%BC%D0%B8-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D0%BC%D0%B8-%D1%81%D0%B5%D1%82%D1%8F%D0%BC%D0%B8 h_01HCY86CKFB0GEJRTYSXN9YZ08=%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F-ua-%D1%81-%D0%B4%D1%80%D1%83%D0%B3%D0%B8%D0%BC%D0%B8-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D0%BC%D0%B8-%D1%81%D0%B5%D1%82%D1%8F%D0%BC%D0%B8 h_01HCY86CKFY787RD4BHQDVEVFV=applovin attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HCY86CKFXM5XXJZSPXPB6397=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 payload=%D0%BF%D0%BE%D0%BB%D0%B5%D0%B7%D0%BD%D0%B0%D1%8F-%D0%BD%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0 h_01HCY86CKFDDXWT2KKFTKKBGHM=%D0%BF%D0%BE%D0%BB%D0%B5%D0%B7%D0%BD%D0%B0%D1%8F-%D0%BD%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0 h_01HCY86CKFV55GYY7C51D7F72S=ironsource attribution-link::a45a1b4a=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-1 h_01HCY86CKFYGEYR2TRPSD87KDA=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-1 payload::81867f5c=%D0%BF%D0%BE%D0%BB%D0%B5%D0%B7%D0%BD%D0%B0%D1%8F-%D0%BD%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-1 h_01HCY86CKFKKFQDG1P42R1FSDJ=%D0%BF%D0%BE%D0%BB%D0%B5%D0%B7%D0%BD%D0%B0%D1%8F-%D0%BD%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-1 retargeting-conversion-data=%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%B0 h_01EHQ74JS84509GT6M93SZA4HX=%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%B0 reattribution-with-srns=%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-srn h_01HCY86CKFAVWP1W0ZNEN5P30A=%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-srn reattribution-with-regular-ad-networks=%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-%D0%BE%D0%B1%D1%8B%D1%87%D0%BD%D1%8B%D0%BC%D0%B8-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D0%BC%D0%B8-%D1%81%D0%B5%D1%82%D1%8F%D0%BC%D0%B8 h_01HCY86CKF1PV8MRR902RAHQGW=%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-%D0%BE%D0%B1%D1%8B%D1%87%D0%BD%D1%8B%D0%BC%D0%B8-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D0%BC%D0%B8-%D1%81%D0%B5%D1%82%D1%8F%D0%BC%D0%B8 h_01HCY86CKF1RGK01VTV3EEHQVM=retargeting-campaign-with-criteo attribution-link::c16e96bb=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-2 h_01HCY86CKFSKBBMFKA8NN8XTPC=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-2 conversion-data-payload=%D0%BF%D0%BE%D0%BB%D0%B5%D0%B7%D0%BD%D0%B0%D1%8F-%D0%BD%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85 h_01HCY86CKG2YQQC629SC3RAFKE=%D0%BF%D0%BE%D0%BB%D0%B5%D0%B7%D0%BD%D0%B0%D1%8F-%D0%BD%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85 reattribution-with-deferred-deep-linking=%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-%D0%BE%D1%82%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%BD%D0%BE%D0%BC-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%BE%D0%BC h_01HCY86CKGXV50H79R0YH1GB2C=%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-%D0%BE%D1%82%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%BD%D0%BE%D0%BC-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%BE%D0%BC h_01HCY86CKG12YRGFEEJ27DQART=deferred-deep-linking-with-srns conversion-data-for-deferred-deep-linking-with-facebook=%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85-%D0%B4%D0%BB%D1%8F-%D0%BE%D1%82%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%B0-%D1%81-meta-ads h_01HCY86CKGX9VHSV3ASKXMFM0X=%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85-%D0%B4%D0%BB%D1%8F-%D0%BE%D1%82%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%B0-%D1%81-meta-ads h_01HCY86CKG3XWM4X0YH7WYCEH4=deferred-deep-linking-with-attribution-links uri-schemes=%D1%81%D1%85%D0%B5%D0%BC%D0%B0-uri h_01HCY86CKGDM2NE1FCRC92K8R0=%D1%81%D1%85%D0%B5%D0%BC%D0%B0-uri ios-universal-links-and-android-app-links=%D1%83%D0%BD%D0%B8%D0%B2%D0%B5%D1%80%D1%81%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-ios-%D0%B8-android-app-links h_01HCY86CKGY1NE4214DES0Y2AV=%D1%83%D0%BD%D0%B8%D0%B2%D0%B5%D1%80%D1%81%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-ios-%D0%B8-android-app-links reengagement-with-srns=%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B5-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-srn h_01HCY86CKG4TRYR6TWYYVB0FJE=%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B5-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-srn reengagement-with-regular-ad-networks=%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B5-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-%D0%BE%D0%B1%D1%8B%D1%87%D0%BD%D1%8B%D0%BC%D0%B8-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D0%BC%D0%B8-%D1%81%D0%B5%D1%82%D1%8F%D0%BC%D0%B8 h_01HCY86CKGM2JS7C9T71R6GPH1=%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B5-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-%D0%BE%D0%B1%D1%8B%D1%87%D0%BD%D1%8B%D0%BC%D0%B8-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D0%BC%D0%B8-%D1%81%D0%B5%D1%82%D1%8F%D0%BC%D0%B8 reengagement-with-deep-linking=%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B5-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%BE%D0%BC h_01HCY86CKG0NPQAA2ZRWWNKGQD=%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B5-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%BE%D0%BC h_01HCY86CKGEBHQVFRGJH96KDFJ=reengagement-deep-linking-with-srns h_01HCY86CKGJ9HG7AGB5MFP33RK=reengagement-deep-linking-with-ad-networks alternative-conversion-data-sources=%D0%B0%D0%BB%D1%8C%D1%82%D0%B5%D1%80%D0%BD%D0%B0%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D0%B5-%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85 h_01HCY86CKG3N6ZXV70G4VMZ0X5=%D0%B0%D0%BB%D1%8C%D1%82%D0%B5%D1%80%D0%BD%D0%B0%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D0%B5-%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85 examples-of-mixed-user-acquisition-and-reattribution=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D1%81%D0%BC%D0%B5%D1%88%D0%B0%D0%BD%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BF%D1%80%D0%B8%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%B8-%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HCY86CKGK9DVVB7T6CVNB8ZN=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D1%81%D0%BC%D0%B5%D1%88%D0%B0%D0%BD%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BF%D1%80%D0%B8%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%B8-%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8" />
