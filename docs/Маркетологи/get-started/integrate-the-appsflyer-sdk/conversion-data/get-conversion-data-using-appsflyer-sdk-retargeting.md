---
title: Получайте данные о конверсиях ретаргетинга через SDK AppsFlyer
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:17:47Z'
  edited_at: '2026-09-28T00:06:12Z'
  id: 4410481260817
  locale: ru
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/ru/articles/4410481260817
---
> **At a glance:** Узнайте, как реатрибуции и повторные вовлечения отражаются в данных о конверсии для путей пользователей в сетях с самостоятельной атрибуцией (SRN) и без самостоятельной атрибуции (не-SRN).

<div id="retargeting-conversion" />

## Конверсии ретаргетинга

Ретаргетинг включает в себя два типа конверсий: реатрибуция и повторное вовлечение.

> 👍 **Tip**
>
> Данные о конверсиях для ретаргетинга не всегда дают четкое представление о типе конверсии. См. [альтернативные источники данных о конверсиях](#альтернативные-источники-данных-о-конверсиях).

<div id="re-attribution-with-srns" />

## Реатрибуция с SRN

Когда пользователь повторно атрибутируется через SRN, полезная нагрузка данных о конверсии не указывает, что это кампания ретаргетинга. Поскольку SRN не используют ссылки атрибуции, нет возможности установить параметр `is_retargeting=true` в ссылке атрибуции. Для **SRN, которые поддерживают ретаргетинг**, AppsFlyer определяет, следует ли повторно атрибутировать пользователя или нет.

Это означает, что на уровне SDK нет способа определить, пришла ли установка из ретаргетинговой кампании.

> 📘 **Note**
>
> Название кампании, которое указывает на ретаргетинг, **не является надежным методом**. [Подробнее см. в примерах](#примеры-смешанного-привлечения-пользователей-и-реатрибуции).

<div id="re-attribution-with-regular-ad-networks" />

## Реатрибуция с обычными рекламными сетями

Атрибуция к рекламным сетям основывается на ссылках атрибуции. Будь то обычные ссылки атрибуции или OneLink, при использовании для ретаргетинга ссылка атрибуции всегда имеет параметр `is_retargeting=true`.

<Accordion title="Ретаргетинговая кампания с Criteo">

<div id="attribution-link" />

#### Ссылка атрибуции

```http
https://app.appsflyer.com/id1234567895?pid=criteo_int&af_click_lookback=30d&
  c=campaign_name&is_retargeting=true&redirect=false&idfa=68**********************************
  &af_reengagement_window=30d
```

<div id="conversion-data-payload" />

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

<div id="re-attribution-with-deferred-deep-linking" />

## Реатрибуция с отложенном диплинкингом

Часто требуется направить по диплинку повторно атрибутированных пользователей, у которых, по определению реатрибуции, приложение не установлено. Например, вы проводите кампанию, цель которой — вернуть пользователей, удаливших приложение. Кампания продвигает продукт или услугу, и вы хотите предоставлять пользователям контент, связанный с рекламируемым продуктом или услугой.

Это называется отложенным диплинкингом. Полезная нагрузка данных о конверсиях для отложенного диплинкинга поступает из метода `onConversionDataSuccess`.

<Accordion title="Отложенные диплинки в сетях типа SRN">

Чтобы реализовать отложенный диплинкинг с SRN, к кампаниям SRN необходимо применить дополнительную логику. Используйте данные из ответа `onConversionSuccess`, например campaign, adset, adgroup, чтобы программно перенаправлять пользователей.

<div id="conversion-data-for-deferred-deep-linking-with-meta-ads" />

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
     "af_status":"неорганический",
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

Вы можете использовать данные из ответа getConversionData, например campaign, adset и т. д., чтобы программно перенаправлять пользователей и показывать им релевантный контент.

> 📘 **Note**
>
> Приложение представляет собой приложение для электронной коммерции, которое специализируется на спортивной одежде. Пользователь, у которого не установлено приложение, взаимодействует с рекламой и устанавливает приложение. После запуска приложения SDK возвращает данные о конверсии. Разработчик настраивает приложение так, чтобы в магазине открывалась активность **summer running shoe collection** (кампания) и показывалась категория **running shoes for women** (набор объявлений).

</Accordion>

<Accordion title="Отложенный диплинкинг со ссылками атрибуции">

Есть три способа диплинкинга пользователей:

<div id="uri-schemes" />

#### Схема URI

При использовании схем URI как для ссылок атрибуции, так и для OneLink ссылка атрибуции и данные выглядят следующим образом:

**Ссылка атрибуции**

```http
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**Универсальные ссылки OneLink**

```http
// короткая OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //длинная OneLink
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
      "af_status": "неорганический",
      "scheme": "superapp",
      "host": "deeplink_activity"
  }
```

* `af_deeplink: true` — если этот параметр присутствует и имеет значение true, ищите поля `scheme` и `host`
* `scheme` и `host` — эти поля берутся из параметра `af_dp` в ссылке атрибуции и указывают схему и активность, на которые пользователь должен быть перенаправлен по диплинку

<div id="ios-universal-links-and-android-app-links" />

#### Универсальные ссылки iOS и Android App Links

Это два других из трех способов реализации диплинкинга.

При использовании универсальных ссылок или app links OneLink и данные выглядят следующим образом:

**Универсальные ссылки OneLink**

```http
// короткая OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //длинная OneLink
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
      "af_status": "неорганический",
      "iscache": "true",
      "shortlink": "71ba577e",
      "media_source": "media_source_name",
      "is_retargeting": true
  }
```

* Поле `shortlink` указывает, по какой именно ссылке OneLink пришел пользователь. Это помогает разработчику понять, как действовать дальше при запуске активности и показе контента. Для этой цели можно также использовать другие поля, например `campaign`.

> 🚧 **Important**
>
> Поле `shortlink` не появляется в данных при использовании длинной ссылки OneLink.
>
> В обоих случаях (короткая или длинная ссылка OneLink) мы рекомендуем добавить пользовательский параметр, который указывает на активность. Например `&deep_link_activity=shoes_cateogry`

> 📘 **Note**
>
> Использовать универсальные ссылки и app links можно только с OneLink.

</Accordion>

<div id="re-engagement-with-srns" />

## Повторное вовлечение с SRN

Как и в случае с кампаниями реатрибуции, когда пользователь повторно вовлекается через SRN, данные о конверсиях не указывают на то, что это кампания повторного вовлечения.

<div id="re-engagement-with-regular-ad-networks" />

## Повторное вовлечение с обычными рекламными сетями

Здесь также данные о конверсиях не указывают на то, что пользователь пришел из кампании по повторному вовлечению. Чтобы преодолеть это ограничение, вы можете задать название кампании, указывающее на повторное вовлечение.

<div id="re-engagement-with-deep-linking" />

## Повторное вовлечение с диплинкингом

Основная часть повторного вовлечения заключается в том, чтобы направить пользователя на определенную активность. Например, если вы рекламируете какой-то товар или распродажу. В таких случаях вы хотите направить пользователей, нажавших на объявление, прямо на страницу приложения, посвященную данному товару или распродаже.

Для этого используется диплинкинг. Данные о конверсиях в диплинкинге действительно важны. В них хранится информация, необходимая разработчику для настройки опыта пользователей и направления их на нужную активность.

<Accordion title="Повторное вовлечение: диплинкинг с SRN">

Данные о конверсиях недоступны, если повторно вовлеченный пользователь пришел из SRN. Разработчику необходимо использовать методы SRN, чтобы получить данные при запуске приложения.

</Accordion>

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
> Мы рекомендуем использовать короткую версию OneLink. Подробнее см. <Anchor target="_blank" href="/marketers/ru/docs/understand-onelink-short-vs-long-urls">здесь</Anchor>.

Еще одна причина использовать короткую версию OneLink — это структура данных о конверсиях, которую возвращает длинная версия ссылки. При использовании длинной версии данные о конверсиях представляют собой сопоставление с единственным полем `link`, в котором содержится вся длинная ссылка OneLink.

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

<div id="alternative-conversion-data-sources" />

## Альтернативные источники данных о конверсиях

* Push API предлагает подробную информацию о конверсиях, которая указывает на реатрибуцию или повторное вовлечение. Полезная нагрузка Push API включает поле под названием `re_targeting_conversion_type`. В этом поле указывается тип конверсии — реатрибуция или повторное вовлечение. Подробнее см. в нашем руководстве по <Anchor target="_blank" href="/marketers/ru/docs/push-api-streaming-raw-data">Push API</Anchor>.
* Отчеты по сырым данным также содержат указатели на типа конверсии. В отчете по сырым данным для конверсий ретаргетинга есть колонка ***Название события***. Значение в этой колонке – либо ***повторное вовлечение***, либо ***повторная атрибуция*** в зависимости от типа конверсии.

<div id="examples-of-mixed-user-acquisition-and-re-attribution" />

## Примеры смешанного привлечения пользователей и реатрибуции

> 📘 **Note**
>
> 1. Пользователь устанавливает ваше приложение, а затем удаляет его. Акт установки помещает пользователя в окно <Anchor target="_blank" href="/marketers/ru/docs/set-up-re-attribution-window">реатрибуции</Anchor>. Вы создаете кампанию по привлечению пользователей (не ретаргетинг) в Meta Ads. Вы также настраиваете интеграцию AppsFlyer с Meta Ads, чтобы включить ретаргетинг. Пока пользователь все еще находится в окне реатрибуции, он видит рекламное объявление, нажимает на него и переустанавливает приложение. Насколько AppsFlyer видит, пользователь является повторно атрибутированным пользователем. Это объясняется двумя факторами:
>
>    1. <span class="af-ol-a"></span>Конфигурация с Meta Ads позволяет использовать ретаргетинг
>    2. Пользователь находится в окне реатрибуции
>
>    В этом случае название кампании не указывает на реатрибуцию.
> 2. Возьмем тот же пример, только на этот раз пользователь находится за пределами окна реатрибуции. В этом случае установка является новой неорганической установкой.
> 3. Давайте рассмотрим другой пример. Вы настроили кампанию ретаргетинга в Meta Ads. Некоторые пользователи видят кампанию и устанавливают приложение. Однако эти пользователи устанавливают приложение впервые. Такие пользователи не считаются повторно атрибутированными пользователями. Вместо этого AppsFlyer рассматривает их как пользователей, которые пришли в результате кампании по привлечению пользователей.

<div data-zendesk-anchors="retargeting-conversion=%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%B0 h_01EHQ74JS84509GT6M93SZA4HX=%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%B0 reattribution-with-srns=%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-srn h_01JNBRN0TBCVKBP6X6GCK3ADG9=%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-srn reattribution-with-regular-ad-networks=%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-%D0%BE%D0%B1%D1%8B%D1%87%D0%BD%D1%8B%D0%BC%D0%B8-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D0%BC%D0%B8-%D1%81%D0%B5%D1%82%D1%8F%D0%BC%D0%B8 h_01JNBRN0TCF7YC76661XNS78AD=%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-%D0%BE%D0%B1%D1%8B%D1%87%D0%BD%D1%8B%D0%BC%D0%B8-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D0%BC%D0%B8-%D1%81%D0%B5%D1%82%D1%8F%D0%BC%D0%B8 attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01JNBRN0TCP9CAHV3X4QD0AVRS=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 conversion-data-payload=%D0%BF%D0%BE%D0%BB%D0%B5%D0%B7%D0%BD%D0%B0%D1%8F-%D0%BD%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85 h_01JNBRN0TCXAZKYVYY56Q4GVHN=%D0%BF%D0%BE%D0%BB%D0%B5%D0%B7%D0%BD%D0%B0%D1%8F-%D0%BD%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85 reattribution-with-deferred-deep-linking=%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-%D0%BE%D1%82%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%BD%D0%BE%D0%BC-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%BE%D0%BC h_01JNBRN0TCECNRZ5ZBH2WWAWHV=%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-%D0%BE%D1%82%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%BD%D0%BE%D0%BC-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%BE%D0%BC conversion-data-for-deferred-deep-linking-with-facebook=%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85-%D0%B4%D0%BB%D1%8F-%D0%BE%D1%82%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%B0-%D1%81-meta-ads h_01JNBRN0TC3NAE862BG274DRWW=%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85-%D0%B4%D0%BB%D1%8F-%D0%BE%D1%82%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%B0-%D1%81-meta-ads uri-schemes=%D1%81%D1%85%D0%B5%D0%BC%D0%B0-uri h_01JNBRN0TC909V4TNCEK4ZP83H=%D1%81%D1%85%D0%B5%D0%BC%D0%B0-uri ios-universal-links-and-android-app-links=%D1%83%D0%BD%D0%B8%D0%B2%D0%B5%D1%80%D1%81%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-ios-%D0%B8-android-app-links h_01JNBRN0TCH7HYZ4BCZTNS89SS=%D1%83%D0%BD%D0%B8%D0%B2%D0%B5%D1%80%D1%81%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-ios-%D0%B8-android-app-links reengagement-with-srns=%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B5-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-srn h_01JNBRN0TCT2F11CQ4H8208JCB=%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B5-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-srn reengagement-with-regular-ad-networks=%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B5-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-%D0%BE%D0%B1%D1%8B%D1%87%D0%BD%D1%8B%D0%BC%D0%B8-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D0%BC%D0%B8-%D1%81%D0%B5%D1%82%D1%8F%D0%BC%D0%B8 h_01JNBRN0TCNTAAD47ZTTK3NWYJ=%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B5-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-%D0%BE%D0%B1%D1%8B%D1%87%D0%BD%D1%8B%D0%BC%D0%B8-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D0%BC%D0%B8-%D1%81%D0%B5%D1%82%D1%8F%D0%BC%D0%B8 reengagement-with-deep-linking=%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B5-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%BE%D0%BC h_01JNBRN0TCGN9Y8ZHSEC4HMKPM=%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B5-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%BE%D0%BC alternative-conversion-data-sources=%D0%B0%D0%BB%D1%8C%D1%82%D0%B5%D1%80%D0%BD%D0%B0%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D0%B5-%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85 h_01JNBRN0TCZ8T35W3AAA4HVD9M=%D0%B0%D0%BB%D1%8C%D1%82%D0%B5%D1%80%D0%BD%D0%B0%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D0%B5-%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85 examples-of-mixed-user-acquisition-and-reattribution=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D1%81%D0%BC%D0%B5%D1%88%D0%B0%D0%BD%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BF%D1%80%D0%B8%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%B8-%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01JNBRN0TC13RAZ73AFV6G92VB=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D1%81%D0%BC%D0%B5%D1%88%D0%B0%D0%BD%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BF%D1%80%D0%B8%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%B8-%D1%80%D0%B5%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8" />
