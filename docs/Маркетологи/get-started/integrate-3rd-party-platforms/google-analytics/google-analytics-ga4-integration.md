---
title: Интеграция с Google Analytics (GA4)
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2024-06-06T15:26:00Z'
  edited_at: '2026-09-29T00:05:51Z'
  id: 25707682812561
  locale: ru
  section: Google Analytics
  section_id: 6551226043793
  url: https://support.appsflyer.com/hc/ru/articles/25707682812561
---
> **At a glance:** **Краткий обзор:** Интеграция AppsFlyer с Google Аналитикой (GA4) позволяет рекламодателям отправлять данные атрибуции и выбранные события в приложении из AppsFlyer в GA4. Эта интеграция работает с приложениями на iOS и Android, в которых уже реализован [SDK Google Аналитика для Firebase](https://firebase.google.com/docs/analytics).

> 🚧 **Important**
>
> **Двоеточие (:)**
>
> Эта интеграция работает с приложениями iOS и Android, в которых уже [реализован SDK Google Analytics для Firebase](https://firebase.google.com/docs/analytics). Для успешной интеграции SDK AppsFlyer должен собирать значение `app_instance_id` из SDK Firebase. См. инструкцию о том, [как извлечь идентификатор экземпляра приложения из SDK Firebase](#5-retrieve-app-instance-id-in-appsflyer-sdk).

<div id="how-does-it-work" />

## Как это работает?

* **Когда** **происходит** **новая установка**, AppsFlyer отправляет в GA4 детали точки касания – медиаисточник, название кампании и идентификатор кампании. Также отправляется `app_instance_id` от SDK Firebase, чтобы обеспечить запись точки касания в GA4 для этого пользователя.
* **Когда** **происходит внутреннее событие приложения**, GA4 будет атрибутировать событие к последней точке касания.

<div id="set-up-google-analytics-ga4-integration" />

## Настройка интеграции с Google Analytics (GA4)

Настроить интеграцию с Google Analytics (GA4) с помощью инструкции ниже.

<Accordion title="1. На Маркетплейсе партнёров выберите Google Analytics (GA4).">

**Необходимые условия:** Перед настройкой интеграции обязательно <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">свяжитесь с партнёром</Anchor> и откройте у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите **Сотрудничество**> **Маркетплейс партнёров.Чтобы изменить**: В AppsFlyer в боковом меню выберите **Сотрудничество**> **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Найдите **Google Аналитику (GA4)** и выберите её.
4. При **первом посещении** здесь нужно включить переключатель ***Активировать партнера***, чтобы настроить параметры интеграции.   
   Примечание: переключатель **должен оставаться включенным (активным), пока вы работаете с Google Analytics (GA4)**. <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">Узнать больше</Anchor>
5. Завершите настройку, используя соответствующие вкладки, как описано в следующем разделе.

Конфигурация Google Аналитики включает в себя только вкладку **Интеграция**.

Подробное описание заголовка окна «Partner Configuration» (Настройки партнёра) см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

</Accordion>

<Accordion title="2. Настройте интеграцию GA4 в AppsFlyer.">

Настройте следующие параметры:

1. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнёра**.

   **Примечание:** статус этого переключателя должен быть <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">(activated)/(включён)</Anchor> всё время, пока вы работаете с этим партнёром.

   Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации/деактивации партнеров</Anchor>.
2. В **идентификаторе приложения Firebase** введите идентификатор приложения Firebase. Чтобы узнать, как найти идентификатор приложения Firebase, см. <Anchor target="_blank" href="https://firebase.google.com/support/faq#find-app-id">документацию Firebase</Anchor>.
3. В строке **API Secret** введите API Secret (API секрет) для аутентификации постбэков в Google Аналитике. API Secret генерируется через пользовательский интерфейс Google Аналитики. Чтобы просмотреть, отредактировать или создать API секрет, следуйте инструкциям в <Anchor target="_blank" href="https://support.google.com/analytics/answer/9814495?sjid=5179426966283787649-EU">документации Google</Anchor>. **Когда вас попросят выбрать поток веб-данных, выберите поток данных для Android или iOS.**
4. Включите **Идентификатор пользователя клиента**, чтобы отправлять идентификатор пользователя клиента (CUID) вместо рекламного идентификатора (IDFA).
5. В разделе **Постбэки по умолчанию**, в разделе **для пользователей из**, выберите **Все медиаисточники, включая органические**.

> 📘 **Note**
>
> **Примечание:**
>
> Постбэк установки включает только детали точки касания (медиаисточник, название кампании и идентификатор кампании).

</Accordion>

<Accordion title="3. Установить постбэки по умолчанию">

AppsFlyer может отправлять автоматические постбэки в GA4 после установки приложения пользователем, включая как установки, так и повторные вовлечения (включая повторную атрибуцию). Повторные вовлечения происходят, когда пользователь, у которого приложение уже установлено, открывает его после клика по ссылке кампании. Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#default-postbacks">постбэках по умолчанию</Anchor>.

</Accordion>

<Accordion title="4. Постбэки по внутренним событиям приложений.">

На вкладке **Интеграция** сопоставьте события в приложении AppsFlyer с событиями Google Аналитики (GA4), отправляемыми через постбэки.

> 📘 **Note**
>
> **Примечание:**
>
> * Постбэки для мобильных событий в приложении, отправленные через S2S, не поддерживаются.
> * GA4 не удаляет дубликаты событий, отправленных из SDK Firebase и AppsFlyer. Поэтому мы рекомендуем настраивать постбэки внутренних событий приложений только для событий, которые уже не отправляются в GA4 через SDK Firebase.

1. Включите **постбэки событий в приложении**.
2. Чтобы добавить в список событие, определенное в SDK, нажмите **Add Event** (Добавить событие). В таблице ниже описаны поля, которые необходимо заполнить:

| Название параметра | Описание |
| --- | --- |
| **AppsFlyer event (Событие AppsFlyer)** | Название события, полученное от SDK AppsFlyer, интегрированного в ваше приложение.<br /><br />**Совет**: Не нашли здесь нужное событие?<ul><li>Убедитесь, что событие активировано на устройстве с неорганической установкой, и повторите поиск.</li><li>Введите его в поле **Событие AppsFlyer** и нажмите **Добавить другое**.</li></ul>Подробнее о сопоставлении пользовательских событий читайте <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#пользовательские-события">здесь</Anchor>. |
| **сопоставлено с партнерским событием** | Уникальное имя или идентификатор каждого события, определённого на стороне партнёра. Возможны следующие настройки сопоставления:<ul><li>**Текстовое поле:** Получите соответствующий идентификатор события от партнера.</li><li>**Раскрывающийся список:** Выберите наиболее подходящее предопределённое событие AppsFlyer.</li><li>**Как есть**: События отправляются в исходном виде, без сопоставления названий.</li></ul> |
| **для пользователей от** | Выберите вариант отправки для события:<ul><li>**Все медиа-источники и органический трафик**: постбэки отправляются по событиям, атрибутированным любому партнеру, а также по органическим событиям.</li></ul> |
| **Включая** | <ul><li>**Нет данных (по умолчанию)**: отправляет только само событие без значения.</li><li>**Ценности и выручка**: Отправьте все параметры события, **включая** ценность, значение выручки (если оно присутствует в событии).</li><li>**Ценности, значения без выручки**: Отправляются все параметры, **за исключением** значения выручки.</li></ul> |

3. [Необязательно] Нажмите на значок (<Image alt="condition-2.png" src="https://files.readme.io/959329be2b1286507b5c87b033785e91ab135592ae37cf3200539400832490c0-25709762755857.png" width="19px" />) **Добавить условие**, чтобы <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">задать условия</Anchor> для события.
4. Нажмите **Сохранить интеграцию**.
5. Отправьте сопоставление постбэка события.

</Accordion>

<Accordion title="5. Отправьте сопоставление события постбэка своему разработчику.">

После того как вы настроили сопоставление событий в приложении, отправьте вашему разработчику таблицу, где каждое сопоставленное событие соответствует строке с следующими столбцами.

* **Событие AF (AF event):** название события AppsFlyer.
* **Сопоставлено с событием Google (Mapped to Google event):** название события в Google Аналитике.

> 🚧 **Important**
>
> **Двоеточие (:)**
>
> Не используйте [зарезервированные события Google](#зарезервированные-названия-событий-google) в качестве названий для пользовательских событий Google Аналитики.

* **Параметры события AF (AF event parameters) [ОБЯЗАТЕЛЬНО]:** Предопределённые параметры событий AppsFlyer, которые должны быть включены в постбэк события, отправляемого в Google Аналитику.

> 🚧 **Important**
>
> **Двоеточие (:)**
>
> Нативный Android Нативный iOS Unity Нативный React

<div id="the-event-mapping-table" />

#### Таблица сопоставления событий

Следующая таблица включает в себя все события Google Аналитики и их предопределённые параметры AppsFlyer. Отправьте своему разработчику таблицу, содержащую только те события, которые вы сопоставили.

| Рекомендуемое название AF (необязательно) | Имя события Google Ads | Предопределённые параметры события AF (Predefined AF event parameters) [ОБЯЗАТЕЛЬНО] |
| --- | --- | --- |
| af\_add\_payment\_info | [добавить\_платежную\_информацию](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_payment_info) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [add\_shipping\_info](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_shipping_info) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_add\_to\_cart | [добавить в корзину](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_to_cart) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_add\_to\_wishlist | [добавить\_в\_список\_желаний](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_to_wishlist) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_initiated\_checkout | [begin\_checkout](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#begin_checkout) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [campaign\_details](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#campaign_details) | campaign\_id, campaign\_name |
| af\_spent\_credits | [earn\_virtual\_currency](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#earn_virtual_currency) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_revenue">af\_выручка</Anchor> |
|  | [generate\_lead](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#generate_lead) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>,<Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | [join\_group](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#join_group) |  |
| af\_достигнутый\_уровень | [повышение\_уровня](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#level_up) |  |
| af\_login | [Войти](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#login) |  |
|  | [post\_score](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#post_score) | af\_user\_score |
| af\_purchase | [покупка](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#purchase) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content">af\_content</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_receipt_id">af\_receipt\_id</Anchor> |
|  | [refund](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#refund) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content">af\_content</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_receipt_id">af\_receipt\_id</Anchor> |
|  | [remove\_from\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#remove_from_cart) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [screen\_view](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#screen_view) |  |
| af\_search | [search](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#search) |  |
|  | [select\_content](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_content) |  |
|  | [select\_item](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_item) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [select\_promotion](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_promotion) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [доля](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#share) |  |
|  | [sign\_up](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#sign_up) |  |
|  | [расходование\_виртуальной\_валюты](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#spend_virtual_currency) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_revenue">af\_выручка</Anchor> |
|  | [tutorial\_begin](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#tutorial_begin) |  |
| завершение\_учебника | [tutorial\_complete](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#tutorial_complete) |  |
| af\_achievement\_unlocked | [Unlock\_achievement](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#unlock_achievement) | af\_achievement\_id |
|  | [view\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_cart) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_item](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_item) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_item\_list](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_item_list) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_promotion](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_promotion) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [просмотр\_результатов\_поиска](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_search_results) |  |
| af\_ad\_view | [ad\_impression](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#ad_impression) | <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |

<div id="reserved-google-event-names" />

#### Зарезервированные названия событий Google

Следующие названия событий зарезервированы и не могут использоваться в качестве пользовательских названий событий:

* `ad_activeview`
* `ad_click`
* `ad_exposure`
* `ad_query`
* `ad_reward`
* `adunit_exposure`
* `app_clear_data`
* `app_exception`
* `app_install`
* `app_remove`
* `app_store_refund`
* `обновление_приложения`
* `app_upgrade`
* `dynamic_link_app_open`
* `dynamic_link_app_update`
* `dynamic_link_first_open`
* `ошибка`
* `firebase_campaign`
* `firebase_in_app_message_action`
* `firebase_in_app_message_dismiss`
* `firebase_in_app_message_impression`
* `first_open`
* `first_visit`
* `in_app_purchase`
* `notification_dismiss`
* `notification_foreground`
* `notification_open`
* `notification_receive`
* `notification_send`
* `os_update`
* `session_start`
* `user_engagement`

</Accordion>

<Accordion title="6. Получите идентификатор экземпляра приложения в SDK AppsFlyer">

Идентификатор экземпляра приложения уникально идентифицирует конкретную установку приложения Firebase. SDK получает это значение из SDK Firebase.

Ваш разработчик реализует код для:

1. сбора данных поля `app_instance_id` из Firebase.
2. вызова `setAdditionalData` перед первым запуском, для включения идентификатора приложения и `ga_session_id` (если используется) в установки, сессии и внутренние события приложения.

> 🚧 **Important**
>
> **Двоеточие (:)**
>
> `setAdditionalData` (Android / Unity / React Native) и `customData` (iOS) принимают **отображение пар ключ-значение**. Отправляет `app_instance_id` и `ga_session_id` **вместе в одном сопоставлении,** чтобы были включены оба значения. Если вы отправите их в **отдельных** `setAdditionalData` вызовах, более поздний вызов перезапишет более ранний.

<Tabs>
<Tab title="Android iOS">

**Kotlin**

```kotlin
FirebaseAnalytics.getInstance(this).appInstanceId.addOnCompleteListener { task ->
   if (task.isSuccessful) {
       AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.result)
    }
}
```

**Java**

```java
FirebaseAnalytics.getInstance(this).getAppInstanceId().addOnCompleteListener(task -> {
       if (task.isSuccessful()) {
           AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.getResult());
       }
  });
```

Справочник API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="Android native iOS native Unity React Native">

**Android native iOS native UnityReact Native**

```swift
let appInstanceId = Analytics.appInstanceID()
    AppsFlyerLib.shared().customData = ["app_instance_id": appInstanceId]
```

**Objective C**

```objectivec
(void) fetchAnalyticsInstanceId {
           NSString *instanceID = [FIRAnalytics appInstanceID];
           [[AppsFlyerLib shared] setAdditionalData:@{@"app_instance_id": instanceID}];
}
```

Справочник API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">customData</Anchor>

</Tab>

<Tab title="Unity">

```csharp
using Firebase.Analytics;
    public class AnalyticsManager : MonoBehaviour
    {
        private async void Start()
        {
           AppsFlyer.initSDK(devKey, appID, this);
           string appInstanceId = await FirebaseAnalytics.GetAnalyticsInstanceIdAsync();
           Dictionary <string, string> customData = new Dictionary<string, string>();
           customData.Add("app_instance_id", appInstanceId);
           AppsFlyer.setAdditionalData(appInstanceId);
           AppsFlyer.startSDK();
        }
}
```

Справочник API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="React Native">

Справочник API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setadditionaldata">setAdditionalData</Anchor>

</Tab>
</Tabs>

</Accordion>

<Accordion title="7. Получите идентификатор сессии GA4 в SDK AppsFlyer.">

`ga_session_id` уникально идентифицирует сессию в приложении Firebase. Это значение должно быть получено из SDK Firebase и отправлено в GA4 с использованием API `setAdditionalData`.

Ваш разработчик реализует код для:

1. сбора данных поля `ga_session_id` из Firebase.
2. Вызовите `setAdditionalData` перед первым запуском для включения идентификатора сессии (и `app_instance_id`, если используется).
3. Используйте ключ `ga_session_id` при вызове API.

> 🚧 **Important**
>
> **Двоеточие (:)**
>
> `setAdditionalData` (Android / Unity / React Native) и `customData` (iOS) принимают **отображение пар ключ-значение**. Если ваше приложение отправляет как `app_instance_id`, так и `ga_session_id` (см. [шаг 5](#5-retrieve-app-instance-id-in-appsflyer-sdk)), **отправьте их вместе в одном отображении**, чтобы оба значения были включены. Если вы отправите их в **отдельных** `setAdditionalData` вызовах, более поздний вызов перезапишет более ранний.

<Tabs>
<Tab title="Android iOS">

**Kotlin**

```kotlin
FirebaseAnalytics.getInstance(this).sessionId.addOnCompleteListener { task ->
    if (task.isSuccessful) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.result)
    }
}
```

**Java**

```java
FirebaseAnalytics.getInstance(this).getSessionId().addOnCompleteListener(task -> {
    if (task.isSuccessful()) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.getResult());
    }
});
```

Справочник API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="Android native iOS native Unity React Native">

**Swift**

```swift
if #available(iOS 14.0, *) {
    Analytics.sessionID { sessionID, error in
        if let sessionID = sessionID {
            AppsFlyerLib.shared().customData = ["ga_session_id": sessionID]
        }
    }
}
```

**Objective C**

```objectivec
- (void)fetchAnalyticsSessionId {
    if (@available(iOS 14.0, *)) {
        [FIRAnalytics sessionIDWithCompletion:^(NSString * _Nullable sessionID, NSError * _Nullable error) {
            if (sessionID) {
                [[AppsFlyerLib shared] setAdditionalData:@{@"ga_session_id": sessionID}];
            }
        }];
    }
}
```

Справочник API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">customData</Anchor>

</Tab>

<Tab title="Unity">

```csharp
using Firebase.Analytics;
using System.Threading.Tasks;
using AppsFlyerSDK;
using UnityEngine;
using System.Collections.Generic;

public class AnalyticsManager : MonoBehaviour
{
    private async void Start()
    {
        AppsFlyer.initSDK("yourDevKey", "yourAppID", this);

        // Get session ID
        string sessionId = await FirebaseAnalytics.GetSessionIdAsync();

        Dictionary<string, string> customData = new Dictionary<string, string>();
        customData.Add("ga_session_id", sessionId);
        AppsFlyer.setAdditionalData(customData);

        AppsFlyer.startSDK();
    }
}
```

Справочник API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setadditionaldata">setAdditionalData</Anchor>

</Tab>
</Tabs>

</Accordion>

<Accordion title="8. Выполните валидацию интеграции GA4">

Убедитесь, что события в постбэках, которые вы отправляете в GA4, зарегистрированы и прочитаны Google аналитикой. Существует два метода, которые рекламодатели могут использовать для просмотра своих данных:

* Используя [GA4 Исследования](https://support.google.com/analytics/answer/7579450?hl=en&ref_topic=12153537,12153943,2986333,&sjid=20462331341270448-EU&visit_id=638532662145815538-1056226594&rd=1#access-analysis&zippy=%2Cin-this-article), вы можете исследовать сырые данные событий со всеми связанными параметрами. **Необходимые условия:** в вашем ресурсе должен быть настроен [экспорт Big Query](https://support.google.com/analytics/answer/9823238).
* **Отчёт о событиях** позволяет рекламодателям просматривать свои события с постбэками. Отчёт можно найти в одной или нескольких коллекциях отчётов.  
  Например, отчеты о событиях можно найти в коллекциях [Жизненный цикл](https://support.google.com/analytics/answer/12924233?hl=en) или [Отчетность по играм](https://support.google.com/analytics/answer/12925133?hl=en&sjid=5454549956257318969-NC) в разделе **Вовлеченность** > **События**.   
  Для получения дополнительной информации об отчёте о событиях см. [документацию Google](https://support.google.com/analytics/answer/12926615?sjid=5454549956257318969-NC).

  ![Отчет GA4 о событиях](https://files.readme.io/01625878b13a46b8a87c34bf465c0ef6494a0f528960d62ce5535b69b29e7d0a-25707728713745.png)
* **Отчёт о привлечении трафика** помогает вам понять, откуда приходят ваши посетители сайта и приложения.

  В разделе [Коллекция жизненного цикла](https://support.google.com/analytics/answer/12924233?hl=en) перейдите в **Привлечение** > **Привлечение трафика**).

  Для получения дополнительной информации об отчёте о привлечении трафика см. [документацию Google](https://support.google.com/analytics/answer/12923437?hl=en&sjid=5454549956257318969-NC#zippy=%2Chow-do-i-filter-out-traffic-sources-from-the-report).

  ![Отчет GA4 по привлечению трафика](https://files.readme.io/fa51e22d1a7941666224eb668efcbfc5a3bb8cce42cf373a82f3b1e096d2a9db-25707770926353.png)

</Accordion>

<div data-zendesk-anchors="set-up-google-analytics-ga4-integration=%D0%BA%D0%B0%D0%BA-%D1%8D%D1%82%D0%BE-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82 h_01HZXY8R12MQWKNHX2BXA68MR3=%D0%BA%D0%B0%D0%BA-%D1%8D%D1%82%D0%BE-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82 h_01J35AP3FF599P0XA8VPWTS5R9=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-google-analytics-ga4 the-event-mapping-table=%D1%82%D0%B0%D0%B1%D0%BB%D0%B8%D1%86%D0%B0-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 h_01HZQ4ABBN0YEVFJXBNS0HTSQ5=%D1%82%D0%B0%D0%B1%D0%BB%D0%B8%D1%86%D0%B0-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 reserved-google-event-names=%D0%B7%D0%B0%D1%80%D0%B5%D0%B7%D0%B5%D1%80%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D0%B7%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-google h_01HZQ4ABBN6ZEB7RJQMFS0AB73=%D0%B7%D0%B0%D1%80%D0%B5%D0%B7%D0%B5%D1%80%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D0%B7%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-google" />
