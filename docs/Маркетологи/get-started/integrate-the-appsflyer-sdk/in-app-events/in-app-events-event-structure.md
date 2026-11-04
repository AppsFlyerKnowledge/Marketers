---
title: События в приложении — Структура событий
metadata:
  keywords:
    - iOS
    - Android
    - In-App Events
    - In-App
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:09:16Z'
  edited_at: '2026-08-19T00:13:17Z'
  id: 4410481112081
  locale: ru
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ru/articles/4410481112081
---
> **Краткий обзор:** Просмотрите список предопределённых имен событий и параметров событий для записи после установки событий в приложении (например, вход в систему, регистрация или внутренняя покупка).

<div id="overview" />

## Обзор

Чтобы передать события в приложении, требуется реализация кода разработчиком в вашем приложении, где это применимо. Эта статья описывает предопределённые названия событий и предопределённые параметры событий.

Чтобы помочь вам определить, какие события и параметры необходимо зарегистрировать, ознакомьтесь с нашими <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#recommended-events-by-business-vertical">статьями, содержащими примеры и потоки</Anchor> по бизнес-вертикалям.

<div id="predefined-event-names" />

## Предопределённые названия событий

В следующем разделе представлен список предопределённых названий событий и соответствие событий, используемых для Meta Ads, Google Ads, TikTok, Snap, X Ads, Amazon Ads, и Criteo.

Каждое название события также включает типичные предопределённые параметры, связанные с этим событием. Вы можете выбрать любые параметры событий, соответствующие потребностям вашего бизнеса.

<div id="achievement-unlocked-af_achievement_unlocked" />

<Accordion title="Достижение разблокировано (af_achievement_unlocked)">

**Описание**: Используется для регистрации событий разблокировки достижений.

**Сопоставление событий:**

| AppsFlyer: | af\_achievement\_unlocked |
| --- | --- |
| Meta Ads | fb\_mobile\_achievement\_unlocked |
| Google реклама | unlock\_achievement |
| TikTok | UnlockAchievement |
| Snap | ACHIEVEMENT\_UNLOCKED |
| Twitter | ACHIEVEMENT\_UNLOCKED |
| Реклама Amazon | - |
| Criteo | достижение |
| Roku Ads | UNLOCK\_ACHIEVEMENT |

**Типичный параметр:**

Нажмите на ссылку, чтобы просмотреть сопоставление с SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="ad-click-af_ad_click" />

<Accordion title="Клик по рекламе (af_ad_click)">

**Описание**: Используется для записи кликов по рекламе, отображаемой в приложении.

**Картирование событий**:

| AppsFlyer: | af\_ad\_click |
| --- | --- |
| Meta Ads | Нажатие на рекламное объявление |
| Google реклама | - |
| TikTok | InAppADClick |
| Snap | AD\_CLICK |
| Twitter | - |
| Реклама Amazon | - |
| Criteo | - |

**Типичные параметры:**

Кликните на ссылки, чтобы просмотреть сопоставление с SRN.

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="ad-view-af_ad_view" />

<Accordion title="Просмотр рекламы (af_ad_view)">

**Описание**: Используется для регистрации просмотров рекламы, отображаемой в приложении.

**Сопоставление событий:**

| AppsFlyer: | af\_ad\_view |
| --- | --- |
| Meta Ads | AdImpression |
| Google реклама | - |
| TikTok | InAppADImpr |
| Snap | AD\_VIEW |
| Twitter | - |
| Реклама Amazon | - |
| Criteo | - |

**Типичные параметры:**

Кликните на ссылки, чтобы просмотреть сопоставление с SRN.

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="Добавление платёжной информации (af_add_payment_info)">

**Описание**: Используется для записи статуса настройки платёжной информации.

Появляется в следующих вертикалях: <Anchor target="_blank" href="/marketers/ru/docs/recommended-ride-hailing-app-events#add-payment-info-af_add_payment_info">Заказ такси</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-flight-booking-app-events#add-payment-info-af_add_payment_info">Бронирование авиабилетов</Anchor>

**Картирование событий**:

| AppsFlyer: | af\_add\_payment\_info |
| --- | --- |
| Meta Ads | fb\_mobile\_add\_payment\_info |
| Google реклама | добавить\_платежную\_информацию |
| TikTok | ДобавитьИнформациюОплате |
| Snap | ADD\_BILLING |
| Twitter | ДОБАВЛЕННАЯ\_ИНФОРМАЦИЯ\_О\_ПЛАТЕЖЕ |
| Реклама Amazon | - |
| Criteo | ADD\_BILLING |
| Roku Ads | ADD\_PAYMENT\_INFO |

**Типичный параметр:**

Нажмите на ссылку, чтобы просмотреть сопоставление с SRN.

* [af\_success](/docs/in-app-events-event-structure#af_success)

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="Добавить в корзину (af_add_to_cart)">

**Описание**: Используется для записи событий добавления в корзину определённых товаров. Чтобы добавить событие с несколькими элементами в отчет, кликните <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">здесь</Anchor>.

**Появляется в следующих отраслях:** <Anchor target="_blank" href="/marketers/ru/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart">электронная коммерция</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-healthcare-app-events#add-to-cart-af_add_to_cart">здравоохранение</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_add\_to\_cart |
| --- | --- |
| Meta Ads | fb\_mobile\_add\_to\_cart |
| Google реклама | добавить в корзину |
| TikTok | Добавить\_в\_корзину |
| Snap | ДОБАВИТЬ\_КОРЗИНУ |
| Twitter | ДОБАВИТЬ\_В\_КОРЗИНУ |
| Реклама Amazon | ADD\_TO\_SHOPPING\_CART |
| Criteo | видКорзина |
| Roku Ads | ДОБАВИТЬ\_В\_КОРЗИНУ |

**Типичные параметры:**

Кликните на ссылки, чтобы просмотреть сопоставление с SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Добавить в список желаний (af_add_to_wishlist)">

**Описание**: Используется для записи событий добавления в список желаний определённых товаров. Чтобы добавить событие с несколькими элементами в отчет, кликните <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">здесь</Anchor>.

**Появляется в следующих отраслях:** <Anchor target="_blank" href="/marketers/ru/docs/recommended-ecommerce-app-events#add-to-wishlist-af_add_to_wishlist">электронная коммерция</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-hotel-booking-app-events#add-to-wishlist-af_add_to_wishlist">бронирование отелей</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_add\_to\_wishlist |
| --- | --- |
| Meta Ads | fb\_mobile\_add\_to\_wishlist |
| Google реклама | добавить\_в\_список\_желаний |
| TikTok | Добавить\_в\_список\_желаний |
| Snap | ADD\_TO\_WISHLIST |
| Twitter | ADD\_TO\_WISHLIST |
| Реклама Amazon | - |
| Criteo | - |
| Roku Ads | ADD\_TO\_WISHLIST |

**Типичные параметры:**

Кликните на ссылки, чтобы просмотреть сопоставление с SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="app-open-af_app_opened" />

<Accordion title="Запуск приложения (af_app_opened)">

Сопоставление событий Roku Ads:

| AppsFlyer: | af\_app\_opened |
| --- | --- |
| Roku Ads | SESSION\_START |

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Завершить регистрацию (af_complete_registration)">

**Описание**: Используется для записи способов регистрации пользователей.

**Доступно в следующих вертикалях:** <Anchor target="_blank" href="/marketers/ru/docs/recommended-gaming-app-events#complete-registration-af_complete_registration">Гейминг</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-ecommerce-app-events#complete-registration-af_complete_registration">электронная коммерция</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-entertainment-app-events#complete-registration-af_complete_registration">Развлечения</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-finance-and-banking-app-events#complete-registration-af_complete_registration">Финансы и банковское дело</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-p2p-lending-app-events#complete-registration-af_complete_registration">P2P-кредитование</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-online-education-app-events#complete-registration-af_complete_registration">Онлайн-образование</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-ride-hailing-app-events#complete-registration-af_complete_registration">Вызов такси</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-hotel-booking-app-events#complete-registration-af_complete_registration">Бронирование отелей</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-healthcare-app-events#complete-registration-af_complete_registration">Здравоохранение</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-telecommunication-app-events#complete-registration-af_complete_registration">Телекоммуникации</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_complete\_registration |
| --- | --- |
| Meta Ads | fb\_mobile\_complete\_registration |
| Google реклама | sign\_up |
| TikTok | регистрация |
| Snap | ЗАРЕГИСТРИРОВАТЬСЯ |
| Twitter | ЗАРЕГИСТРИРОВАТЬСЯ |
| Реклама Amazon | ЗАРЕГИСТРИРОВАТЬСЯ |
| Criteo | - |
| Roku Ads | COMPLETE\_REGISTRATION |

**Типичный параметр:**

Нажмите на ссылку, чтобы просмотреть сопоставление с SRN.

* [af\_метод\_регистрации](/docs/in-app-events-event-structure#af_registration_method)

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Просмотр содержимого (af_content_view)">

**Описание**: Используется для записи событий просмотра контента. Чтобы добавить событие с несколькими элементами в отчет, кликните <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">здесь</Anchor>.

**Появляется в следующих отраслях:** <Anchor target="_blank" href="/marketers/ru/docs/recommended-ecommerce-app-events#content-view-af_content_view">электронная коммерция</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-flight-booking-app-events#content-view-af_content_view">бронирование авиабилетов</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-hotel-booking-app-events#content-view-af_content_view">бронирование отелей</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_content\_view |
| --- | --- |
| Meta Ads | fb\_mobile\_content\_view |
| Google реклама | view\_item |
| TikTok | ПросмотрКонтента |
| Snap | VIEW\_CONTENT |
| Twitter | CONTENT\_VIEW |
| Реклама Amazon | PAGE\_VIEW |
| Criteo | viewProduct |
| Roku Ads | VIEW\_CONTENT |

**Типичные параметры:**

Кликните параметры, которые соответствуют потребностям вашего бизнеса, чтобы просмотреть сопоставление с SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_дата\_отправления\_обратного](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_дата\_возвращения](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_класс](/docs/in-app-events-event-structure#af_class)
* [af\_suggested\_hotels](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_hotel\_score](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="Инициированный оформление заказа (af_initiated_checkout)">

**Описание**: Используется для записи событий расходования кредита. Чтобы добавить событие с несколькими элементами в отчет, кликните <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">здесь</Anchor>.

**Появляется в отраслях:** <Anchor target="_blank" href="/marketers/ru/docs/recommended-ecommerce-app-events#initiated-checkout-af_initiated_checkout">электронная коммерция</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-hotel-booking-app-events#initiated-checkout-af_initiated_checkout">бронирование отелей</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_initiated\_checkout |
| --- | --- |
| Meta Ads | fb\_mobile\_initiated\_checkout |
| Google реклама | begin\_checkout |
| TikTok | Checkout |
| Snap | START\_CHECKOUT |
| Twitter | ОФОРМЛЕНИЕ\_ЗАКАЗА\_НАЧАЛО |
| Реклама Amazon | ЗАРЕГИСТРИРОВАТЬСЯ |
| Criteo | видКорзина |
| Roku Ads | INITIATE\_CHECKOUT |

**Типичные параметры:**

Кликните параметры, которые соответствуют потребностям вашего бизнеса, чтобы просмотреть сопоставление с SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)
* [af\_платежная\_информация\_доступна](/docs/in-app-events-event-structure#af_payment_info_available)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_дата\_отправления\_обратного](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_дата\_возвращения](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_класс](/docs/in-app-events-event-structure#af_class)
* [af\_suggested\_hotels](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_hotel\_score](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="invite-af_invite" />

<Accordion title="Приглашение (af_invite)">

**Описание**: Используется для записи событий приглашений (социальных)

**Доступно в следующих вертикалях:** <Anchor target="_blank" href="/marketers/ru/docs/recommended-gaming-app-events#invite-af_invite">Гейминг</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_invite |
| --- | --- |
| Meta Ads | - |
| Google реклама | пригласить |
| TikTok | - |
| Snap | ПРИГЛАСИТЬ |
| Twitter | ПРИГЛАСИТЬ |
| Реклама Amazon | - |
| Criteo | - |

**Типичный параметр:**

Нажмите на ссылку, чтобы просмотреть сопоставление с SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="lead-lead" />

<Accordion title="Лид (lead)">

Сопоставление событий Roku Ads:

| AppsFlyer: | lead |
| --- | --- |
| Roku Ads | LEAD |

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="Достигнутый уровень (af_level_achieved)">

**Описание**: Используется для записи событий уровня гейминга.

Появляется в следующих вертикалях: <Anchor target="_blank" href="/marketers/ru/docs/recommended-gaming-app-events#level-achieved-af_level_achieved">Гейминг</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_достигнутый\_уровень |
| --- | --- |
| Meta Ads | fb\_mobile\_level\_achieved |
| Google реклама | повышение\_уровня |
| TikTok | ДостичьУровня |
| Snap | LEVEL\_COMPLETE |
| Twitter | УРОВЕНЬ\_ДОСТИГНУТ |
| Реклама Amazon | - |
| Criteo | пользователь\_Уровень |
| Roku Ads | ACHIEVE\_LEVEL |

**Типичные параметры:**

Кликните на ссылки, чтобы просмотреть сопоставление с SRN.

* [af\_уровень](/docs/in-app-events-event-structure#af_level)
* [af\_score](/docs/in-app-events-event-structure#af_score)

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="Просмотр списка (af_list_view)">

**Описание**: Используется для записи событий просмотра списков.

**Появляется в следующих отраслях:** <Anchor target="_blank" href="/marketers/ru/docs/recommended-ecommerce-app-events#list-view-af_list_view">электронная коммерция</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_list\_view |
| --- | --- |
| Meta Ads | - |
| Google реклама | view\_item\_list |
| TikTok | - |
| Snap | LIST\_VIEW |
| Twitter | - |
| Реклама Amazon | - |
| Criteo | просмотрСписка |

**Типичные параметры:**

Кликните на ссылки, чтобы просмотреть сопоставление с SRN.

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)

</Accordion>

<div id="login-af_login" />

<Accordion title="Вход в систему (af_login)">

**Описание**: Используется для записи событий входа в систему пользователей.

**Доступно в следующих вертикалях:** <Anchor target="_blank" href="/marketers/ru/docs/recommended-gaming-app-events#login-af_login">Гейминг</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-ecommerce-app-events#login-af_login">электронная коммерция</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-entertainment-app-events#login-af_login">Развлечения</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-finance-and-banking-app-events#login-af_login">Финансы и банковские услуги</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-online-education-app-events#login-af_login">Онлайн-образование</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-hotel-booking-app-events#login-af_login">Бронирование отелей</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-healthcare-app-events#login-af_login">Здравоохранение</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-telecommunication-app-events#login-af_login">Телекоммуникации</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_login |
| --- | --- |
| Meta Ads | - |
| Google реклама | Войти |
| TikTok | вход в систему; |
| Snap | Войти |
| Twitter | Войти |
| Реклама Amazon | - |
| Criteo | - |

</Accordion>

<div id="opened-from-push-notification-af_opened_from_push_notification" />

<Accordion title="Открыто из push-уведомления (af_opened_from_push_notification)">

**Описание**: Используется для записи случаев открытия приложения из событий push-уведомлений.

**Сопоставление событий:**

| AppsFlyer: | af\_opened\_from\_push\_notification |
| --- | --- |
| Meta Ads | - |
| Google реклама | notification\_open |
| TikTok | - |
| Snap | - |
| Twitter | - |
| Реклама Amazon | - |
| Criteo | - |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Покупка (af_purchase)">

**Описание**: Используется для регистрации событий покупок и привязки к ним выручки.

* Для списка поддерживаемых AppsFlyer символов валют, кликните <Anchor target="_blank" href="https://docs.openexchangerates.org/docs/supported-currencies">здесь</Anchor>.
* Чтобы добавить событие с несколькими элементами в отчет, кликните <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">здесь</Anchor>.
* Чтобы зафиксировать и подтвердить это событие, см. <Anchor target="_blank" href="/marketers/ru/docs/purchase-and-subscription-validation-overview">Валидация покупки и подписки</Anchor>.

Появляется в вертикалях: <Anchor target="_blank" href="/marketers/ru/docs/recommended-gaming-app-events#purchase-af_purchase">Гейминг</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-ecommerce-app-events#purchase-af_purchase">электронная коммерция</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-online-education-app-events#purchase-af_purchase">Онлайн-образование</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-healthcare-app-events#purchase-af_purchase">Здравоохранение</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-telecommunication-app-events#purchase-af_purchase">Телекоммуникации</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_purchase |
| --- | --- |
| Meta Ads | fb\_mobile\_purchase |
| Google реклама | in\_app\_purchase |
| TikTok | покупка; |
| Snap | ПОКУПКА |
| Twitter | ПОКУПКА |
| Реклама Amazon | OFF\_AMAZON\_PURCHASES |
| Criteo | transactionConfirmation |
| Roku Ads | ПОКУПКА |

**Типичные параметры:**

Кликните параметры, которые соответствуют потребностям вашего бизнеса, чтобы просмотреть сопоставление с SRN.

* [af\_выручка](/docs/in-app-events-event-structure#af_revenue)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)
* [af\_validated](/docs/in-app-events-event-structure#af_validated)
* [af\_receipt\_id](/docs/in-app-events-event-structure#af_receipt_id)
* [af\_order\_id](/docs/in-app-events-event-structure#af_order_id)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_дата\_отправления\_обратного](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_дата\_возвращения](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_класс](/docs/in-app-events-event-structure#af_class)
* [af\_suggested\_hotels](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_hotel\_score](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="rate-af_rate" />

<Accordion title="Рейтинг (af_rate)">

**Описание**: Используется для записи событий оценки приложения или элемента. Чтобы добавить событие с несколькими элементами в отчет, кликните <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">здесь</Anchor>.

**Сопоставление событий:**

| AppsFlyer: | af\_rate |
| --- | --- |
| Meta Ads | fb\_mobile\_rate |
| Google реклама | отправить\_рейтинг |
| TikTok | Оценка |
| Snap | ОЦЕНКА |
| Twitter | ОЦЕНЕН |
| Реклама Amazon | - |
| Criteo | - |

**Типичные параметры:**

Кликните на ссылки, чтобы просмотреть сопоставление с SRN.

* [af\_rating\_value](/docs/in-app-events-event-structure#af_rating_value)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_max\_rating\_value](/docs/in-app-events-event-structure#af_max_rating_value)

</Accordion>

<div id="reengage-af_re_engage" />

<Accordion title="Повторное вовлечение (af_re_engage)">

**Описание**: Используется для записи событий повторного вовлечения пользователей.

**Сопоставление событий:**

| AppsFlyer: | af\_re\_engage |
| --- | --- |
| Meta Ads | - |
| Google реклама | кастомное\_событие |
| Snap | - |
| Twitter | RE\_ENGAGE |
| Реклама Amazon | - |
| Criteo | - |

**Типичный параметр:**

Нажмите на ссылку, чтобы просмотреть сопоставление с SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="search-af_search" />

<Accordion title="Поиск (af_search)">

**Описание**: Используется для записи событий поиска.

**Появляется в следующих вертикалях:** <Anchor target="_blank" href="/marketers/ru/docs/recommended-ecommerce-app-events#search-af_search">электронная коммерция</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-flight-booking-app-events#search-af_search">бронирование авиабилетов</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-hotel-booking-app-events#search-af_search">бронирование отелей</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_search |
| --- | --- |
| Meta Ads | fb\_mobile\_search |
| Google реклама | просмотр\_результатов\_поиска |
| TikTok | Поиск |
| Snap | ПОИСК |
| Twitter | ПОИСК |
| Реклама Amazon | ПОИСК |
| Criteo | просмотрПоиска |
| Roku Ads | ПОИСК |

**Типичные параметры:**

Кликните параметры, которые соответствуют потребностям вашего бизнеса, чтобы просмотреть сопоставление с SRN.

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [строка\_поиска\_af](/docs/in-app-events-event-structure#af_search_string)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_дата\_отправления\_обратного](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_дата\_возвращения](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_класс](/docs/in-app-events-event-structure#af_class)
* [af\_suggested\_hotels](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_hotel\_score](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="share-af_share" />

<Accordion title="Поделиться (af_share)">

**Описание**: Используется для записи событий обмена.

**Доступно в следующих вертикалях:** <Anchor target="_blank" href="/marketers/ru/docs/recommended-gaming-app-events#share-af_share">Гейминг</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_share |
| --- | --- |
| Meta Ads | - |
| Google реклама | доля |
| TikTok | - |
| Snap | Репост |
| Twitter | Репост |
| Реклама Amazon | - |
| Criteo | - |

**Типичный параметр:**

Нажмите на ссылку, чтобы просмотреть сопоставление с SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="Расходованные кредиты (af_spent_credits)">

**Описание**: Используется для записи событий оформления заказа. Чтобы добавить событие с несколькими элементами в отчет, кликните <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">здесь</Anchor>.

**Появляется в вертикалях:** <Anchor target="_blank" href="/marketers/ru/docs/recommended-ride-hailing-app-events#spent-credits-af_spent_credits">Вызов такси</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_spent\_credits |
| --- | --- |
| Meta Ads | fb\_mobile\_spent\_credits |
| Google реклама | расходование\_виртуальной\_валюты |
| TikTok | РасходованиеКредитов |
| Snap | РАСХОДОВАНЫЕ\_КРЕДИТЫ |
| Twitter | РАСХОДОВАНЫЕ\_КРЕДИТЫ |
| Реклама Amazon | - |
| Criteo | transactionConfirmation |

**Типичные параметры:**

Кликните на ссылки, чтобы просмотреть сопоставление с SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="start-trial-af_start_trial" />

<Accordion title="Начало пробного периода (af_start_trial)">

**Описание**: Используется для фиксирования начала бесплатного пробного периода использования продукта. Чтобы зафиксировать и подтвердить это событие, см. <Anchor target="_blank" href="/marketers/ru/docs/purchase-and-subscription-validation-overview">Валидация покупки и подписки</Anchor>.

**Доступно в следующих вертикалях:** <Anchor target="_blank" href="/marketers/ru/docs/recommended-entertainment-app-events#start-trial-af_start_trial">Развлечения</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_start\_trial |
| --- | --- |
| Meta Ads | StartTrial |
| Google реклама | - |
| TikTok | StartTrial |
| Snap | START\_TRIAL |
| Twitter | - |
| Реклама Amazon | - |
| Criteo | - |
| Roku Ads | START\_TRIAL |

**Типичные параметры:**

Кликните на ссылки, чтобы просмотреть сопоставление с SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

<div id="note" />

> 📘 **Примечание:**
>
> Если вы сопоставляете это событие с событием Meta рекламы StartTrial и хотите связать его с выручкой, используйте параметр af\_price вместо af\_revenue.

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="Подписка (af_subscribe)">

**Описание**: Используется для фиксирования оформления платных подписок. Чтобы зафиксировать и подтвердить это событие, см. <Anchor target="_blank" href="/marketers/ru/docs/purchase-and-subscription-validation-overview">Валидация покупки и подписки</Anchor>.

**Доступно в следующих вертикалях:** <Anchor target="_blank" href="/marketers/ru/docs/recommended-entertainment-app-events#subscription-af_subscribe">Развлечения</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_subscribe |
| --- | --- |
| Meta Ads | Подписаться |
| Google реклама | - |
| TikTok | Подписаться |
| Snap | SUBSCRIBE |
| Twitter | - |
| Реклама Amazon | SUBSCRIBE |
| Criteo | SUBSCRIBE |
| Roku Ads | SUBSCRIBE |

**Типичные параметры:**

Кликните на ссылки, чтобы просмотреть сопоставление с SRN.

* [af\_выручка](/docs/in-app-events-event-structure#af_revenue)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="Бронирование путешествия (af_travel_booking)">

**Описание**: Используется для записи событий бронирования путешествий (и привязки к ним выручки). Чтобы добавить событие с несколькими элементами в отчет, кликните <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">здесь</Anchor>.

**Доступно в следующих вертикалях:** <Anchor target="_blank" href="/marketers/ru/docs/recommended-flight-booking-app-events#travel-booking-af_travel_booking">Бронирование авиарейсов</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-hotel-booking-app-events#travel-booking-af_travel_booking">Бронирование отелей</Anchor>

**Сопоставление событий:**

| AppsFlyer: | af\_travel\_booking |
| --- | --- |
| Meta Ads | fb\_mobile\_purchase |
| Google реклама | ecommerce\_purchase |
| TikTok | покупка; |
| Snap | ЗАБРОНИРОВАТЬ |
| Twitter | ПОКУПКА |
| Реклама Amazon | - |
| Criteo | transactionConfirmation |

**Типичные параметры:**

Кликните параметры, которые соответствуют потребностям вашего бизнеса, чтобы просмотреть сопоставление с SRN.

* [af\_выручка](/docs/in-app-events-event-structure#af_revenue)
* [af\_customer\_user\_id](/docs/in-app-events-event-structure#af_customer_user_id)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_класс](/docs/in-app-events-event-structure#af_class)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_дата\_отправления\_обратного](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_дата\_возвращения](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_класс](/docs/in-app-events-event-structure#af_class)
* [af\_suggested\_hotels](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_hotel\_score](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)
* [af\_order\_id](/docs/in-app-events-event-structure#af_order_id)

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="Завершение обучения (af_tutorial_completion)">

**Описание**: Используется для записи завершения обучения. Чтобы добавить событие с несколькими элементами в отчет, кликните <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">здесь</Anchor>.

**Доступно в следующих вертикалях:** <Anchor target="_blank" href="/marketers/ru/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">гейминг</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">Онлайн-образование</Anchor>

**Сопоставление событий:**

| AppsFlyer: | завершение\_учебника |
| --- | --- |
| Meta Ads | fb\_mobile\_tutorial\_completion |
| Google реклама | tutorial\_complete |
| TikTok | Полное руководство |
| Snap | ПОЛНЫЙ\_УЧЕБНИК |
| Twitter | TUTORIAL\_COMPLETE |
| Реклама Amazon | - |
| Criteo | - |

**Типичные параметры:**

Кликните на ссылки, чтобы просмотреть сопоставление с SRN.

* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="update-af_update" />

<Accordion title="Обновление (af_update)">

**Описание**: Используется для записи событий обновления. Чтобы добавить событие с несколькими элементами в отчет, кликните <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">здесь</Anchor>.

**Сопоставление событий:**

| AppsFlyer: | af\_update |
| --- | --- |
| Meta Ads | - |
| Google реклама | обновление\_приложения |
| Snap | - |
| Twitter | UPDATE |
| Реклама Amazon | - |
| Criteo | - |

**Типичный параметр:**

Нажмите на ссылку, чтобы просмотреть сопоставление с SRN.

* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)

</Accordion>

<div id="note-1" />

> 📘 **Примечание:**
>
> Помимо предопределенных названий событий, описанных в этом разделе, <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-in-app-event-mapping#сопоставление-предопределенных-событий">реклама предлагает дополнительные события</Anchor>, которые отправляются без атрибутов.

<div id="predefined-event-parameters" />

## Предопределенные параметры событий

В следующем разделе представлен список предопределенных параметров событий. Каждый параметр события включает сопоставление, используемое для Meta реклама, Google реклама, Snap, X реклама и Criteo. Вы можете включить в событие любые параметры событий.

<div id="note-2" />

> 📘 **Примечание:**
>
> Параметры событий можно увидеть в столбце «Ценность события» в <Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview">Отчетах о необработанных данных</Anchor> (категория "Премиум" функция).

<div id="af_adrev_ad_type" />

<Accordion title="af_adrev_ad_type">

**Описание**: Тип рекламы (например, баннер или интерстициальная реклама)

**Сопоставление параметров:**

| AppsFlyer: | af\_adrev\_ad\_type |
| --- | --- |
| Meta Ads | тип\_рекламы |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_city" />

<Accordion title="af_city">

**Описание**: Город, в котором забронирована поездка

**Сопоставление параметров:**

| AppsFlyer: | af\_city |
| --- | --- |
| Meta Ads | fb\_city |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | город\_полета |
| Criteo | - |

</Accordion>

<div id="af_class" />

<Accordion title="af_класс">

**Описание**: Класс путешествия, забронированный для полета

**Сопоставление параметров:**

| AppsFlyer: | af\_класс |
| --- | --- |
| Meta Ads | fb\_travel\_class |
| Google реклама | класс\_путешествия |
| Snap | - |
| Twitter | - |
| TikTok | flight\_class |
| Criteo | - |

</Accordion>

<div id="af_content" />

<Accordion title="af_content">

**Описание**: Название контента (например, название песни или название и эпизод ТВ)

**Сопоставление параметров:**

| AppsFlyer: | af\_content |
| --- | --- |
| Meta Ads | fb\_content |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_content_id" />

<Accordion title="af_content_id">

**Описание**: идентификатор товара

**Примечание:** Предопределенные события Snapchat `af_content_id` и `af_content_id` используют один и тот же параметр событий. Если оба события регистрируются одновременно, в Snapchat отправляется только событие `af_content_list`.

**Сопоставление параметров:**

| AppsFlyer: | af\_content\_id |
| --- | --- |
| Meta Ads | fb\_content\_id |
| Google реклама | item\_id |
| Snap | item\_ids |
| Twitter | content\_id |
| TikTok | content\_id |
| Criteo | id |

</Accordion>

<div id="af_content_list" />

<Accordion title="af_content_list">

**Описание**: Список идентификаторов контента

**Примечание:** Когда вы используете `af_content_list`, AppsFlyer рассматривает весь список как единое значение. Инструменты сегментации аудитории AppsFlyer не могут отфильтровывать отдельные идентификаторы контента в рамках списка. Например, если `af_content_list` – это `[\"ID1\",\"ID2\",\"ID3\"]`, инструмент аудитории не может выделить или сопоставить `ID1` отдельно.

**Сопоставление параметров:**

| AppsFlyer: | af\_content\_list |
| --- | --- |
| Meta Ads | fb\_content\_id |
| Google реклама | item\_id |
| Snap | item\_ids |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_content_type" />

<Accordion title="af_content_type">

**Описание**: Категория Продукт

**Сопоставление параметров:**

| AppsFlyer: | af\_content\_type |
| --- | --- |
| Meta Ads | fb\_content\_type |
| Google реклама | категория\_товара |
| Snap | категория\_товара |
| Twitter | content\_type |
| TikTok | content\_type |
| Criteo | - |

</Accordion>

<div id="af_country" />

<Accordion title="af_country">

**Описание**: Страна, где забронирована поездка

**Сопоставление параметров:**

| AppsFlyer: | af\_country |
| --- | --- |
| Meta Ads | fb\_country |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | страна\_рейса |
| Criteo | - |

</Accordion>

<div id="af_currency" />

<Accordion title="af_currency">

**Описание**: Код валюты

**Сопоставление параметров:**

| AppsFlyer: | af\_currency |
| --- | --- |
| Meta Ads | fb\_currency |
| Google реклама | код\_валюты |
| Snap | currency (валюта) |
| Twitter | валюта\_цены |
| TikTok | currency (валюта) |
| Реклама Amazon | currency (валюта) |
| Criteo | currency (валюта) |

</Accordion>

<div id="af_customer_user_id" />

<Accordion title="af_customer_user_id">

**Описание**: идентификатор клиента

**Сопоставление параметров:**

| AppsFlyer: | af\_customer\_user\_id |
| --- | --- |
| Meta Ads | - |
| Google реклама | идентификатор\_пользователя\_клиента |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | идентификатор |

</Accordion>

<div id="af_date_a" />

<Accordion title="af_date_a">

**Описание**: Дата заезда

**Сопоставление параметров:**

| AppsFlyer: | af\_date\_a |
| --- | --- |
| Meta Ads | fb\_checkin\_date |
| Google реклама | дата\_начала |
| Snap | - |
| Twitter | - |
| TikTok | дата\_заезда |
| Criteo | ин |

</Accordion>

<div id="af_date_b" />

<Accordion title="af_date_b">

**Описание**: Дата выезда

**Сопоставление параметров:**

| AppsFlyer: | af\_date\_b |
| --- | --- |
| Meta Ads | fb\_checkout\_date |
| Google реклама | дата\_выезда |
| Snap | - |
| Twitter | - |
| TikTok | checkout\_date |
| Criteo | dout |

</Accordion>

<div id="af_departing_arrival_date" />

<Accordion title="af_departing_arrival_date">

**Описание**: Дата прибытия

**Сопоставление параметров:**

| AppsFlyer: | af\_departing\_arrival\_date |
| --- | --- |
| Meta Ads | fb\_departing\_arrival\_date |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_departing_departure_date" />

<Accordion title="af_departing_departure_date">

**Описание**: Дата отправления

**Сопоставление параметров:**

| AppsFlyer: | af\_departing\_ дата\_отправления |
| --- | --- |
| Meta Ads | fb\_departing\_ дата\_отправления |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | дата\_отправления |
| Criteo | - |

</Accordion>

<div id="af_description" />

<Accordion title="af_description">

**Описание**: Краткое описание (строка)

**Сопоставление параметров:**

| AppsFlyer: | af\_description |
| --- | --- |
| Meta Ads | fb\_description |
| Google реклама | description |
| Snap | description |
| Twitter | description |
| TikTok | description |
| Criteo | ui\_достижение |

</Accordion>

<div id="af_destination_a" />

<Accordion title="af_destination_a">

**Описание**: Первый пункт назначения

**Сопоставление параметров:**

| AppsFlyer: | af\_destination\_a |
| --- | --- |
| Meta Ads | fb\_origin\_airport |
| Google реклама | место отправления |
| Snap | - |
| Twitter | - |
| TikTok | departing\_airport |
| Criteo | - |

</Accordion>

<div id="af_destination_b" />

<Accordion title="af_destination_b">

**Описание**: Второй пункт назначения

**Сопоставление параметров:**

| AppsFlyer: | af\_destination\_b |
| --- | --- |
| Meta Ads | fb\_destination\_airport |
| Google реклама | destination |
| Snap | - |
| Twitter | - |
| TikTok | destination\_airport |
| Criteo | - |

</Accordion>

<div id="af_destination_list" />

<Accordion title="af_destination_list">

**Описание**: Список пунктов назначения, включенных в каталог (например, список музеев или ресторанов рядом с отелем)

**Сопоставление параметров:**

| AppsFlyer: | af\_destination\_list |
| --- | --- |
| Meta Ads | fb\_destination\_ids |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_hotel_score" />

<Accordion title="af_hotel_score">

**Описание**: Оценка отеля по отзывам

**Сопоставление параметров:**

| AppsFlyer: | af\_hotel\_score |
| --- | --- |
| Meta Ads | fb\_hotel\_score |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_level" />

<Accordion title="af_уровень">

**Описание**: Уровень, достигнутый пользователем

**Сопоставление параметров:**

| AppsFlyer: | af\_уровень |
| --- | --- |
| Meta Ads | fb\_level |
| Google реклама | повышение\_уровня |
| Snap | level |
| Twitter | level |
| TikTok | - |
| Criteo | ui\_level |

</Accordion>

<div id="af_max_rating_value" />

<Accordion title="af_max_rating_value">

**Описание**: Верхняя граница масштаба оценок (например, 5 из 5)

**Сопоставление параметров:**

| AppsFlyer: | af\_max\_rating\_value |
| --- | --- |
| Meta Ads | fb\_max\_rating\_value |
| Google реклама | max\_rating |
| Snap | - |
| Twitter | макс\_оцененное\_значение |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="h_01NEWAFNETREVENUE0001" />

<Accordion title="af_дата_отправления_обратного">

**Описание**: Чистый доход, указанный для этого события. Значение представляет чистый доход в соответствии с вашей собственной бизнес-логикой; AppsFlyer не определяет, как именно он рассчитывается, и агрегирует переданное вами значение. Типичные примеры: доход после вычета комиссий магазина приложений и/или налогов, валовая маржа или доход после вычета банковских комиссий или платы за сервис (электронная коммерция, финансы и т. д.). Используется для метрик чистого дохода (чистый доход, чистый ROI, чистый ROAS, чистый ARPU, чистая прибыль) в <Anchor target="_blank" href="/marketers/ru/docs/my-dashboards">«Моих дэшбордах»</Anchor>.

Значение указывается в валюте транзакции, заданной в af\_currency (по умолчанию USD). Те же правила форматирования, что и для af\_revenue: без разделителей разрядов, символов валют, специальных символов или текста (например, 1234.56), до пяти знаков после запятой.

**Примечание:** Для этого параметра нет предопределенной константы SDK, поэтому передавайте его как пользовательский параметр с ключом af\_net\_revenue.

<div id="note-3" />

> 📘 **Примечание**
>
> Для приложений, в которых включен <Anchor target="_blank" href="/marketers/ru/docs/about-roi360-store-revenue">store revenue ROI360</Anchor>, AppsFlyer автоматически заполняет af\_net\_revenue для записываемых им событий покупок в приложении и подписок; значение рассчитывается как валовый доход за вычетом комиссий магазина приложений и налогов (Net = Gross - store fees - taxes).

</Accordion>

<div id="af_num_adults" />

<Accordion title="af_num_adults">

**Описание**: Количество детей-пассажиров

**Сопоставление параметров:**

| AppsFlyer: | af\_num\_adults |
| --- | --- |
| Meta Ads | fb\_num\_adults |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | num\_people |
| Criteo | - |

</Accordion>

<div id="af_num_children" />

<Accordion title="af_num_children">

**Описание**: Количество младенцев-пассажиров

Сопоставление параметров:

| AppsFlyer: | af\_num\_children |
| --- | --- |
| Meta Ads | fb\_num\_children |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | кол-во\_детей |
| Criteo | - |

</Accordion>

<div id="af_num_infants" />

<Accordion title="af_num_infants">

**Описание**: идентификатор транзакции

**Сопоставление параметров:**

| AppsFlyer: | af\_num\_infants |
| --- | --- |
| Meta Ads | fb\_num\_infants |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_order_id" />

<Accordion title="af_order_id">

**Описание**: Дата окончания поездки

**Сопоставление параметров:**

| AppsFlyer: | af\_order\_id |
| --- | --- |
| Meta Ads | fb\_order\_id |
| Google реклама | идентификатор\_транзакции |
| Snap | идентификатор\_транзакции |
| Twitter | - |
| TikTok | идентификатор\_транзакции |
| Criteo | идентификатор\_транзакции |

</Accordion>

<div id="af_payment_info_available" />

<Accordion title="af_платежная_информация_доступна">

**Описание**: Доступна ли информация о платежах пользователя

**Сопоставление параметров:**

| AppsFlyer: | af\_платежная\_информация\_доступна |
| --- | --- |
| Meta Ads | fb\_payment\_info\_ available |
| Google реклама | доступность информации о платеже |
| Snap | доступность информации о платеже |
| Twitter | user\_payment\_info |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_neighborhoods" />

<Accordion title="af_preferred_neighborhoods">

**Описание**: Район, где находится отель

**Сопоставление параметров:**

| AppsFlyer: | af\_preferred\_neighborhoods |
| --- | --- |
| Meta Ads | fb\_preferred\_neighborhoods |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_num_stops" />

<Accordion title="af_preferred_num_stops">

**Описание**: Количество остановок, которые ищет пользователь (например, беспосадочный или прямой рейс)

**Сопоставление параметров:**

| AppsFlyer: | af\_preferred\_num\_stops |
| --- | --- |
| Meta Ads | fb\_preferred\_num\_stops |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_price_range" />

<Accordion title="af_preferred_price_range">

**Описание**: Предпочтительный звездный рейтинг отеля

Сопоставление параметров:

| AppsFlyer: | af\_preferred\_price\_range |
| --- | --- |
| Meta Ads | fb\_preferred\_price\_range |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_star_ratings" />

<Accordion title="af_preferred_star_ratings">

**Описание**: Предпочтительный ценовой диапазон отеля

**Сопоставление параметров:**

| AppsFlyer: | af\_preferred\_star\_ratings |
| --- | --- |
| Meta Ads | fb\_preferred\_star\_ratings |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_price" />

<Accordion title="af_price">

**Описание**: Цена Продукта. Вы можете использовать af\_price как денежный параметр, который не считается выручкой (например, событие "Добавить в корзину"). Этот параметр относится к цене отдельного Продукта. Общая сумма всех покупок отображается под параметром [af\_revenue](/docs/in-app-events-event-structure#af_revenue).

**Сопоставление параметров:**

| AppsFlyer: | af\_price |
| --- | --- |
| Meta Ads | fb\_price |
| Google реклама | price |
| Snap | price |
| Twitter | price\_micro |
| TikTok | price |
| Criteo | price |

</Accordion>

<div id="af_projected_revenue" />

<Accordion title="af_projected_revenue">

Ожидаемая выручка, которую рекламодатель планирует получить от пользователя на основе его ранних взаимодействий или поведения до фактической выручки.

</Accordion>

<div id="af_quantity" />

<Accordion title="af_quantity">

**Описание**: Выбранное значение рейтинга

**Сопоставление параметров:**

| AppsFlyer: | af\_quantity |
| --- | --- |
| Meta Ads | fb\_num\_items |
| Google реклама | quantity |
| Snap | число элементов |
| Twitter | число элементов |
| TikTok | quantity |
| Criteo | quantity |

</Accordion>

<div id="af_rating_value" />

<Accordion title="af_rating_value">

**Описание**: Идентификатор квитанции

**Сопоставление параметров:**

| AppsFlyer: | af\_rating\_value |
| --- | --- |
| Meta Ads | \_valueToSum |
| Google реклама | Репост |
| Snap | - |
| Twitter | price\_micro |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_receipt_id" />

<Accordion title="af_receipt_id">

**Описание**: Дата окончания поездки

**Сопоставление параметров:**

| AppsFlyer: | af\_receipt\_id |
| --- | --- |
| Meta Ads | - |
| Google реклама | идентификатор\_транзакции |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | идентификатор\_транзакции |

</Accordion>

<div id="af_region" />

<Accordion title="af_region">

**Описание**: Регион, где забронирована поездка

**Сопоставление параметров:**

| AppsFlyer: | af\_region |
| --- | --- |
| Meta Ads | fb\_region |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | регион полета |
| Criteo | - |

</Accordion>

<div id="af_registration_method" />

<Accordion title="af_метод_регистрации">

**Описание**: Тип метода регистрации

**Сопоставление параметров:**

| AppsFlyer: | af\_метод\_регистрации |
| --- | --- |
| Meta Ads | fb\_метод\_регистрации |
| Google реклама | registration\_method |
| Snap | метод\_регистрации\_подписки |
| Twitter | registration\_method |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_returning_arrival_date" />

<Accordion title="af_дата_возвращения">

**Описание**:  Дата и время начала обратного пути

**Сопоставление параметров:**

| AppsFlyer: | af\_returning\_arrival\_ date |
| --- | --- |
| Meta Ads | fb\_returning\_arrival\_ date |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_returning_departure_date" />

<Accordion title="af_дата_отправления_обратного">

**Описание**: Дата и время окончания обратного пути

**Сопоставление параметров:**

| AppsFlyer: | af\_дата\_отправления\_обратного |
| --- | --- |
| Meta Ads | fb\_returning\_departure\_date |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | returning\_date |
| Criteo | - |

</Accordion>

<div id="af_revenue" />

<Accordion title="af_выручка">

**Описание**: Общая сумма покупок. af\_выручка учитывается как выручка на платформе AppsFlyer. Также учитывается <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#revenue-events">отрицательная выручка</Anchor>, из-за отмен или возвратов.

<div id="important" />

> 🚧 **Важно!**
>
> Значение выручки не должно содержать запятые как разделители, валютные обозначения, специальные символы или текст. Например, значение выручки должно быть 1234.56. AppsFlyer предоставляет значение выручки с точностью до пяти десятичных знаков.

Чтобы узнать больше о том, как использовать параметр выручки, нажмите <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#revenue-events">здесь</Anchor>.

**Чистый доход:** Чтобы передавать чистый доход наряду с валовым доходом, отправьте [af\_net\_revenue](/docs/in-app-events-event-structure#h_01NEWAFNETREVENUE0001) как пользовательский параметр события. Вы сами определяете, что означает «чистый» для вашего бизнеса (например, доход после вычета комиссий магазина и/или налогов, валовая маржа или доход после вычета комиссий за сервис). В приложениях, где включен store revenue ROI360, AppsFlyer автоматически заполняет это значение для записываемых им событий покупки и подписки как валовый доход за вычетом комиссий магазина приложений и налогов.

**Сопоставление параметров:**

| AppsFlyer: | af\_выручка |
| --- | --- |
| Meta Ads | \_valueToSum |
| Google реклама | доля |
| Snap | price |
| Twitter | price\_micro |
| TikTok | VALIDATED |
| Реклама Amazon | Значение события |
| Criteo | ui\_выручка |

</Accordion>

<div id="af_score" />

<Accordion title="af_score">

**Описание**: Поисковый запрос

**Сопоставление параметров:**

| AppsFlyer: | af\_score |
| --- | --- |
| Meta Ads | - |
| Google реклама | - |
| Snap | - |
| Twitter | оценка |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_search_string" />

<Accordion title="строка_поиска_af">

**Описание**: Идентификатор подписки для пользователя

**Сопоставление параметров:**

| AppsFlyer: | строка\_поиска\_af |
| --- | --- |
| Meta Ads | fb\_search\_string |
| Google реклама | строка\_поиска |
| Snap | строка\_поиска |
| Twitter | строка\_поиска |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_subscription_id" />

<Accordion title="af_subscription_id">

**Описание**: Оценка, связанная с достижением пользователя

**Сопоставление параметров:**

| AppsFlyer: | af\_subscription\_id |
| --- | --- |
| Meta Ads | подписка\_идентификатор |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_success" />

<Accordion title="af_success">

**Описание**: Получилось ли завершить действие успешно

**Сопоставление параметров:**

| AppsFlyer: | af\_success |
| --- | --- |
| Meta Ads | fb\_success |
| Google реклама | успех |
| Snap | успех |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_suggested_destinations" />

<Accordion title="af_suggested_destinations">

**Описание**: Список предлагаемых отелей

**Сопоставление параметров:**

| AppsFlyer: | af\_suggested\_ destinations |
| --- | --- |
| Meta Ads | fb\_suggested\_destinations |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_suggested_hotels" />

<Accordion title="af_suggested_hotels">

**Описание**: Список предлагаемых направлений

**Сопоставление параметров:**

| AppsFlyer: | af\_suggested\_ hotels |
| --- | --- |
| Meta Ads | fb\_предлагаемые\_отели |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_travel_end" />

<Accordion title="af_travel_end">

**Описание**: Дата начала поездки

**Сопоставление параметров:**

| AppsFlyer: | af\_travel\_end |
| --- | --- |
| Meta Ads | fb\_travel\_end |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_travel_start" />

<Accordion title="af_travel_start">

**Описание**: Относительная значимость пользователя для рекламодателя

**Сопоставление параметров:**

| AppsFlyer: | af\_travel\_start |
| --- | --- |
| Meta Ads | fb\_travel\_start |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_user_score" />

<Accordion title="af_user_score">

**Описание**: Подтверждает покупку

**Сопоставление параметров:**

| AppsFlyer: | af\_user\_score |
| --- | --- |
| Meta Ads | fb\_user\_score |
| Google реклама | - |
| Snap | - |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_validated" />

<Accordion title="af_validated">

**Описание**: Количество товаров

**Сопоставление параметров:**

| AppsFlyer: | af\_validated |
| --- | --- |
| Meta Ads | - |
| Google реклама | VALIDATED |
| Snap | успех |
| Twitter | - |
| TikTok | - |
| Criteo | - |

</Accordion>

Ниже приведен список предопределенных параметров события, которые не включают сопоставление SRN:

* af\_achievement\_id
* af\_coupon\_code
* af\_customer\_segment
* af\_deep\_link
* af\_event\_end
* af\_event\_start
* af\_lat
* af\_long
* af\_new\_version
* af\_old\_version
* af\_param\_1
* af\_param\_2
* af\_param\_3
* af\_param\_4
* af\_param\_5
* af\_param\_6
* af\_param\_7
* af\_param\_8
* af\_param\_9
* af\_param\_10
* af\_review\_text
* af\_tutorial\_id
* af\_virtual\_currency\_name
* af\_duration\_seconds

<div id="see-also" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration">Настройка постбэков для событий в приложении</Anchor>

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01H9HT8C713A4NV9WCB0FJZJ4R=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 predefined-event-names=%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D1%91%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D0%B7%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 h_01H9HT8C7189W1JXAR3J3KT8KV=%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D1%91%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D0%B7%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 h_01H9HT8C71MV7V7C75MB6ESHMM=achievement-unlocked-af_achievement_unlocked h_01H9HT8C7171PB7KAC83MYBWQ8=ad-click-af_ad_click h_01H9HT8C72KJ6ZA663SH7HJ7MP=ad-view-af_ad_view h_01H9HT8C72HSM88DJG0PDV5140=add-payment-info-af_add_payment_info h_01H9HT8C72BWFSPKWDVQW926WG=add-to-cart-af_add_to_cart h_01H9HT8C7228B57XKAACPZG8NK=add-to-wishlist-af_add_to_wishlist h_01K0PJ4C3HP9DMJT1DFZ848WF0=app-open-af_app_opened h_01H9HT8C72DX0DXBDHRJFG19G2=complete-registration-af_complete_registration h_01H9HT8C72SPY9VQ9AD648AKZK=content-view-af_content_view h_01H9HT8C722T2VH6A9257Q7T4P=initiated-checkout-af_initiated_checkout h_01H9HT8C72F0RZ4JS9929SE465=invite-af_invite h_01K0PJ4C3H72BDTRH7WAYW4V7S=lead-lead h_01H9HT8C72VFGC08Q858EX7XTN=level-achieved-af_level_achieved h_01H9HT8C72DZW77YTQ9KB0XEVG=list-view-af_list_view h_01H9HT8C720W10QEBCTPAGMRFB=login-af_login h_01H9HT8C72QC4WV10Z4JZTZM7D=opened-from-push-notification-af_opened_from_push_notification h_01H9HT8C7263J0YSX5K10R497N=purchase-af_purchase h_01H9HT8C73MPYMG8KSYE04DKDZ=rate-af_rate h_01H9HT8C734DAC6GPJE58DB5JD=reengage-af_re_engage h_01H9HT8C73YSYBK0YSDPRWDBNW=search-af_search h_01H9HT8C734GJ07V67QC9V3TVC=share-af_share h_01H9HT8C73H4VT2M0P3M1SYG88=spent-credits-af_spent_credits h_01H9HT8C73YWDCKAZPY0BVRS6F=start-trial-af_start_trial h_01H9HT8C736BF2VNRCFSJSVXWS=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01H9HT8C73N69S45H82NWQ5FN1=subscription-af_subscribe h_01H9HT8C73CD6HNT5GA6B4CHQ9=travel-booking-af_travel_booking h_01H9HT8C73NFDPS1P5AVXXZEX7=tutorial-completion-af_tutorial_completion h_01H9HT8C73JPH6Q9XFKA3GNYT8=update-af_update h_01H9HT8C74SGGK2FW92JH4BJPZ=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 predefined-event-parameters=%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 h_01H9HT8C74N4TJZ5ZVBTKAX810=%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 h_01H9HT8C74VQ9ZWF079V50E5HE=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 h_01H9HT8C74Y0BWS565DFTY75KJ=af_adrev_ad_type h_01H9HT8C742NHGXFKWSS4P07K2=af_city h_01H9HT8C7442PFZEK7QC6R0K67=af_class h_01H9HT8C7462KG3030WWZ2XGZW=af_content h_01H9HT8C74ZX07907NXFHKGJ91=af_content_id h_01H9HT8C744CMWSYHJB74JFSS5=af_content_list h_01H9HT8C74GKGG5V4X54BCAADC=af_content_type h_01H9HT8C74RD08Z9EBZTKY5KSD=af_country h_01H9HT8C75BJYK4R3WYSN4BF43=af_currency h_01H9HT8C752E2PK6QKTA2GNGH5=af_customer_user_id h_01H9HT8C75BN0A92X9BRY4A74T=af_date_a h_01H9HT8C75406KV9264ZZT9DKM=af_date_b h_01H9HT8C7526AEHJAA7FM7442E=af_departing_arrival_date h_01H9HT8C75W9X61ZH0849EPDBY=af_departing_departure_date h_01H9HT8C75VEV3C8CJBDN6X5HW=af_description h_01H9HT8C75Z8TBZEPEY9EGSR4Y=af_destination_a h_01H9HT8C751G216VB6GYTPEPE1=af_destination_b h_01H9HT8C75CVM0MHSKTK2CZ8HD=af_destination_list h_01H9HT8C75CVVDFABSTN5R4MWT=af_hotel_score h_01H9HT8C75GEMHE2NHEFK9J7NT=af_level h_01H9HT8C7505H4CMY70EMDQWSF=af_max_rating_value af_net_revenue=h_01NEWAFNETREVENUE0001 h_01NEWAFNETREVENUENOTE0001=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-3 h_01H9HT8C75ST9XBDC3SR6XFDPB=af_num_adults h_01H9HT8C75NNZ5NP6PRPXDSKP8=af_num_children h_01H9HT8C757X70AAGNWFV0CKRY=af_num_infants h_01H9HT8C75A0HESE5FD10VD1P8=af_order_id h_01H9HT8C75B488VKY8SW9M4GG4=af_payment_info_available h_01H9HT8C75W7SRB0KF4E5FB2YF=af_preferred_neighborhoods h_01H9HT8C75GC61D1A0P6P42TMR=af_preferred_num_stops h_01H9HT8C76XRY6CD1TJEPCJJTR=af_preferred_price_range h_01H9HT8C76Y9ZQQ2X4EJT2DC14=af_preferred_star_ratings h_01H9HT8C76KCDRJKBWSM9JKFE1=af_price 01J9XHWVFHXPN6N3EZF1P8XWYM=af_projected_revenue h_01H9HT8C76Y5VXBKF3TBVVJG1C=af_quantity h_01H9HT8C768WXZ126Q425PHDWX=af_rating_value h_01H9HT8C76XX9J6FZ6RWQB6B6R=af_receipt_id h_01H9HT8C760S0F7QZMFYW1BKRD=af_region h_01H9HT8C76N4S3SGES5SQ2J4AC=af_registration_method h_01H9HT8C76ZR36A4CM2PY6PJ10=af_returning_arrival_date h_01H9HT8C760JPVXYC5WH9ZSDPX=af_returning_departure_date h_01H9HT8C76PYB14WPCQKSEK69J=af_revenue h_01H9HT8C762BGPRHFX228APEHR=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE h_01H9HT8C76P55HN8K6D7PHFS2J=af_score h_01H9HT8C76TB4KNTZVD6JVPEYQ=af_search_string h_01H9HT8C762R2PJ573W8TJFJHG=af_subscription_id h_01H9HT8C76VZ6FA20K471V0EKK=af_success h_01H9HT8C76029H94AY5EHCZX6X=af_suggested_destinations h_01H9HT8C76N6C694TCPVCK4EC3=af_suggested_hotels h_01H9HT8C765EM1SAEJ67FNXZDE=af_travel_end h_01H9HT8C76YP8VEM5E6WB9NQ7T=af_travel_start h_01H9HT8C771SYQWQ8VBTPA2V2E=af_user_score h_01H9HT8C771XFSQJX42QVBNZAJ=af_validated h_01HDNZ30NH2QXSHD7B4EMFG4T5=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
