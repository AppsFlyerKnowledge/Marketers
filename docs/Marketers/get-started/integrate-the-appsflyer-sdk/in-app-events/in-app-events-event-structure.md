---
title: 'Eventos in-app: estructura del evento'
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
  edited_at: '2026-08-17T11:53:39Z'
  id: 4410481112081
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/4410481112081
---
> **En resumen:** Consulta la lista de nombres de eventos predefinidos y parámetros de eventos para registrar eventos in-app tras la instalación (como inicio de sesión, registro o compra in-app).

<div id="overview" />

## Visión general

Los eventos in-app que desees enviar requieren que tu desarrollador implemente el código correspondiente en tu aplicación. Este artículo describe los nombres de eventos predefinidos y los parámetros de eventos predefinidos.

Para ayudarte a determinar qué eventos y parámetros registrar, consulta nuestros <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#recommended-events-by-business-vertical">artículos que incluyen ejemplos y procedimientos</Anchor> según los sectores de negocio.

<div id="predefined-event-names" />

## Nombres de eventos predefinidos

La siguiente sección proporciona una lista de nombres de eventos predefinidos y la asignación de eventos utilizada para Meta Ads, Google Ads, TikTok, Snap, X Ads y Criteo.

Cada nombre de evento también incluye los parámetros típicos de eventos predefinidos asociados a ese evento. Puedes optar por incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="achievement-unlocked-af_achievement_unlocked" />

<Accordion title="Logro desbloqueado (af_achievement_unlocked)">

**Descripción**: Se utiliza para registrar eventos de desbloqueo de logros.

**Mapeo de eventos:**

| AppsFlyer | af\_achievement\_unlocked |
| --- | --- |
| Meta Ads | fb\_mobile\_achievement\_unlocked |
| Anuncios de Google | unlock\_achievement |
| TikTok | UnlockAchievement |
| Snap | ACHIEVEMENT\_UNLOCKED |
| Anuncios X | ACHIEVEMENT\_UNLOCKED |
| Anuncios de Amazon | - |
| Criteo | logro |
| Anuncios de Roku | DESBLOQUEAR\_LOGRO |

**Parámetro típico:**

Haz clic en el enlace para ver la asignación con SRNs.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="ad-click-af_ad_click" />

<Accordion title="Clic en anuncio (af_ad_click)">

**Descripción**: Se utiliza para registrar los clics en anuncios dentro de la app.

**Mapeo de eventos**:

| AppsFlyer | af\_ad\_click |
| --- | --- |
| Meta Ads | AdClick |
| Anuncios de Google | - |
| TikTok | InAppADClick |
| Snap | AD\_CLICK |
| Anuncios X | - |
| Anuncios de Amazon | - |
| Criteo | - |

**Parámetros típicos:**

Haz clic en los enlaces para ver el mapeo a SRNs.

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="ad-view-af_ad_view" />

<Accordion title="Visualización de anuncio (af_ad_view)">

**Descripción**: Se utiliza para registrar las visualizaciones de anuncios in-app.

**Mapeo de eventos:**

| AppsFlyer | af\_ad\_view |
| --- | --- |
| Meta Ads | AdImpression |
| Anuncios de Google | - |
| TikTok | InAppADImpr |
| Snap | AD\_VIEW |
| Anuncios X | - |
| Anuncios de Amazon | - |
| Criteo | - |

**Parámetros típicos:**

Haz clic en los enlaces para ver el mapeo a SRNs.

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="Agregar información de pago (af_add_payment_info)">

**Descripción**: Se utiliza para registrar el estado de configuración de la información de pago.

Aparece en estos sectores: <Anchor target="_blank" href="/marketers/es/docs/recommended-ride-hailing-app-events#add-payment-info-af_add_payment_info">Transporte compartido</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-flight-booking-app-events#add-payment-info-af_add_payment_info">Reserva de vuelos</Anchor>

**Mapeo de eventos**:

| AppsFlyer | af\_add\_payment\_info |
| --- | --- |
| Meta Ads | fb\_mobile\_add\_payment\_info |
| Anuncios de Google | add\_payment\_info |
| TikTok | AddPaymentInfo |
| Snap | ADD\_BILLING |
| Anuncios X | ADDED\_PAYMENT\_INFO |
| Anuncios de Amazon | - |
| Criteo | ADD\_BILLING |
| Anuncios de Roku | AÑADIR\_INFORMACIÓN\_DE\_PAGO |

**Parámetro típico:**

Haz clic en el enlace para ver la asignación con SRNs.

* [af\_success](/docs/in-app-events-event-structure#af_success)

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="Añadir al carrito (af_add_to_cart)">

**Descripción**: Sirve para registrar eventos de añadir al carrito de artículos específicos. Para reportar un evento que incluye varios elementos, haga clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.

**Aparece en estas áreas:** <Anchor target="_blank" href="/marketers/es/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-healthcare-app-events#add-to-cart-af_add_to_cart">Atención médica</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_add\_to\_cart |
| --- | --- |
| Meta Ads | fb\_mobile\_add\_to\_cart |
| Anuncios de Google | añadir\_al\_carrito |
| TikTok | AddToCart |
| Snap | ADD\_CART |
| Anuncios X | ADD\_TO\_CART |
| Anuncios de Amazon | ADD\_TO\_SHOPPING\_CART |
| Criteo | viewBasket |
| Anuncios de Roku | ADD\_TO\_CART |

**Parámetros típicos:**

Haz clic en los enlaces para ver el mapeo a SRNs.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Añadir a la lista de deseos (af_add_to_wishlist)">

**Descripción**: Se utiliza para registrar eventos de añadir a la lista de deseos de artículos específicos. Para reportar un evento que incluye varios elementos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.

**Aparece en estas áreas:** <Anchor target="_blank" href="/marketers/es/docs/recommended-ecommerce-app-events#add-to-wishlist-af_add_to_wishlist">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-hotel-booking-app-events#add-to-wishlist-af_add_to_wishlist">Reservas de hotel</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_add\_to\_wishlist |
| --- | --- |
| Meta Ads | fb\_mobile\_add\_to\_wishlist |
| Anuncios de Google | add\_to\_wishlist |
| TikTok | AddToWishlist |
| Snap | ADD\_TO\_WISHLIST |
| Anuncios X | ADD\_TO\_WISHLIST |
| Anuncios de Amazon | - |
| Criteo | - |
| Anuncios de Roku | ADD\_TO\_WISHLIST |

**Parámetros típicos:**

Haz clic en los enlaces para ver el mapeo a SRNs.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="app-open-af_app_opened" />

<Accordion title="Apertura de la App (af_app_opened)">

Asignación de eventos de anuncios de Roku:

| AppsFlyer | af\_app\_opened |
| --- | --- |
| Anuncios de Roku | INICIO\_DE\_SESIÓN |

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Completar registro (af_complete_registration)">

**Descripción**: Se utiliza para registrar métodos de registro de usuarios.

**Aparece en estas verticales:** <Anchor target="_blank" href="/marketers/es/docs/recommended-gaming-app-events#complete-registration-af_complete_registration">Videojuegos</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-ecommerce-app-events#complete-registration-af_complete_registration">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-entertainment-app-events#complete-registration-af_complete_registration">Entretenimiento</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-finance-and-banking-app-events#complete-registration-af_complete_registration">Finanzas y bancos</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-p2p-lending-app-events#complete-registration-af_complete_registration">Préstamos P2P</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-online-education-app-events#complete-registration-af_complete_registration">Educación online</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-ride-hailing-app-events#complete-registration-af_complete_registration">Transporte compartido</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-hotel-booking-app-events#complete-registration-af_complete_registration">Reservas de hotel</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-healthcare-app-events#complete-registration-af_complete_registration">Atención sanitaria</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-telecommunication-app-events#complete-registration-af_complete_registration">Telecomunicaciones</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_complete\_registration |
| --- | --- |
| Meta Ads | fb\_mobile\_complete\_registration |
| Anuncios de Google | sign\_up |
| TikTok | Registro |
| Snap | SIGN\_UP |
| Anuncios X | SIGN\_UP |
| Anuncios de Amazon | SIGN\_UP |
| Criteo | - |
| Anuncios de Roku | COMPLETAR\_REGISTRO |

**Parámetro típico:**

Haz clic en el enlace para ver la asignación con SRNs.

* [af\_registration\_method](/docs/in-app-events-event-structure#af_registration_method)

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Vista de contenido (af_content_view)">

**Descripción**: Se utiliza para registrar eventos de vista de contenido. Para reportar un evento que incluye varios elementos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.

**Aparece en estas áreas:** <Anchor target="_blank" href="/marketers/es/docs/recommended-ecommerce-app-events#content-view-af_content_view">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-flight-booking-app-events#content-view-af_content_view">Reserva de vuelos</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-hotel-booking-app-events#content-view-af_content_view">Reserva de hoteles</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_content\_view |
| --- | --- |
| Meta Ads | fb\_mobile\_content\_view |
| Anuncios de Google | view\_item |
| TikTok | ViewContent |
| Snap | VIEW\_CONTENT |
| Anuncios X | CONTENT\_VIEW |
| Anuncios de Amazon | PAGE\_VIEW |
| Criteo | viewProduct |
| Anuncios de Roku | VIEW\_CONTENT |

**Parámetros típicos:**

Haz clic en los parámetros relevantes para las necesidades de su negocio para ver el mapeo a SRNs.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
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

<Accordion title="Inicio de pago (af_initiated_checkout)">

**Descripción**: Se utiliza para registrar eventos de gasto de créditos. Para reportar un evento que incluye varios elementos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.

**Aparece en áreas:** <Anchor target="_blank" href="/marketers/es/docs/recommended-ecommerce-app-events#initiated-checkout-af_initiated_checkout">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-hotel-booking-app-events#initiated-checkout-af_initiated_checkout">Reservas de hotel</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_initiated\_checkout |
| --- | --- |
| Meta Ads | fb\_mobile\_initiated\_checkout |
| Anuncios de Google | begin\_checkout |
| TikTok | Checkout |
| Snap | START\_CHECKOUT |
| Anuncios X | CHECKOUT\_INITIATED |
| Anuncios de Amazon | CHECKOUT |
| Criteo | viewBasket |
| Anuncios de Roku | INICIAR\_PAGO |

**Parámetros típicos:**

Haz clic en los parámetros relevantes para las necesidades de su negocio para ver el mapeo a SRNs.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)
* [af\_payment\_info\_available](/docs/in-app-events-event-structure#af_payment_info_available)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
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

<Accordion title="Invitar (af_invite)">

**Descripción**: Se utiliza para registrar eventos de invitación (sociales)

**Aparece en estas verticales:** <Anchor target="_blank" href="/marketers/es/docs/recommended-gaming-app-events#invite-af_invite">Videojuegos</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_invite |
| --- | --- |
| Meta Ads | - |
| Anuncios de Google | invite |
| TikTok | - |
| Snap | INVITE |
| Anuncios X | INVITE |
| Anuncios de Amazon | - |
| Criteo | - |

**Parámetro típico:**

Haz clic en el enlace para ver la asignación con SRNs.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="lead-lead" />

<Accordion title="Lead (lead)">

Asignación de eventos de anuncios de Roku:

| AppsFlyer | lead |
| --- | --- |
| Anuncios de Roku | LEAD |

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="Nivel alcanzado (af_level_achieved)">

**Descripción**: Se utiliza para registrar eventos de nivel en juegos.

Aparece en estos sectores: <Anchor target="_blank" href="/marketers/es/docs/recommended-gaming-app-events#level-achieved-af_level_achieved">Videojuegos</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_level\_achieved |
| --- | --- |
| Meta Ads | fb\_mobile\_level\_achieved |
| Anuncios de Google | level\_up |
| TikTok | AchieveLevel |
| Snap | LEVEL\_COMPLETE |
| Anuncios X | LEVEL\_ACHIEVED |
| Anuncios de Amazon | - |
| Criteo | userLevel |
| Anuncios de Roku | ALCANZAR\_NIVEL |

**Parámetros típicos:**

Haz clic en los enlaces para ver el mapeo a SRNs.

* [af\_level](/docs/in-app-events-event-structure#af_level)
* [af\_score](/docs/in-app-events-event-structure#af_score)

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="Vista de lista (af_list_view)">

**Descripción**: Se utiliza para registrar eventos de visualización de listados

**Aparece en estos sectores:** <Anchor target="_blank" href="/marketers/es/docs/recommended-ecommerce-app-events#list-view-af_list_view">eCommerce</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_list\_view |
| --- | --- |
| Meta Ads | - |
| Anuncios de Google | view\_item\_list |
| TikTok | - |
| Snap | LIST\_VIEW |
| Anuncios X | - |
| Anuncios de Amazon | - |
| Criteo | viewListing |

**Parámetros típicos:**

Haz clic en los enlaces para ver el mapeo a SRNs.

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)

</Accordion>

<div id="login-af_login" />

<Accordion title="Iniciar sesión (af_login)">

**Descripción**: Se utiliza para registrar eventos de inicio de sesión de usuarios

**Aparece en estas verticales:** <Anchor target="_blank" href="/marketers/es/docs/recommended-gaming-app-events#login-af_login">Videojuegos</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-ecommerce-app-events#login-af_login">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-entertainment-app-events#login-af_login">Entretenimiento</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-finance-and-banking-app-events#login-af_login">Finanzas y Banca</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-online-education-app-events#login-af_login">Educación Online</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-hotel-booking-app-events#login-af_login">Reservas Hoteleras</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-healthcare-app-events#login-af_login">Salud</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-telecommunication-app-events#login-af_login">Telecomunicaciones</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_login |
| --- | --- |
| Meta Ads | - |
| Anuncios de Google | Iniciar sesión |
| TikTok | Iniciar sesión |
| Snap | Iniciar sesión |
| Anuncios X | Iniciar sesión |
| Anuncios de Amazon | - |
| Criteo | - |

</Accordion>

<div id="opened-from-push-notification-af_opened_from_push_notification" />

<Accordion title="Abierto desde notificación push (af_opened_from_push_notification)">

**Descripción**: Se utiliza para registrar aperturas de la aplicación desde notificaciones push

**Mapeo de eventos:**

| AppsFlyer | af\_opened\_from\_push\_notification |
| --- | --- |
| Meta Ads | - |
| Anuncios de Google | notification\_open |
| TikTok | - |
| Snap | - |
| Anuncios X | - |
| Anuncios de Amazon | - |
| Criteo | - |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Descripción**: Se utiliza para registrar compras de suscripciones pagadas.

* Para ver una lista de los símbolos de divisas compatibles con AppsFlyer, haz clic en <Anchor target="_blank" href="https://docs.openexchangerates.org/docs/supported-currencies">aquí</Anchor>.
* **Descripción**: Se utiliza para registrar eventos de calificación de aplicaciones o artículos Para reportar un evento que incluye varios elementos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.
* Para reportar un evento que incluye varios elementos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.

Aparece en los sectores: <Anchor target="_blank" href="/marketers/es/docs/recommended-gaming-app-events#purchase-af_purchase">Videojuegos</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-ecommerce-app-events#purchase-af_purchase">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-online-education-app-events#purchase-af_purchase">Educación Online</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-healthcare-app-events#purchase-af_purchase">Salud</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-telecommunication-app-events#purchase-af_purchase">Telecomunicaciones</Anchor>

**Mapa de eventos:**

| AppsFlyer | af\_compra |
| --- | --- |
| Meta Ads | fb\_mobile\_purchase |
| Anuncios de Google | in\_app\_purchase |
| TikTok | Compra |
| Snap | COMPRAR |
| Anuncios X | COMPRAR |
| Anuncios de Amazon | OFF\_AMAZON\_PURCHASES |
| Criteo | transactionConfirmation |
| Anuncios de Roku | COMPRAR |

**Parámetros típicos:**

Haz clic en los parámetros relevantes para las necesidades de su negocio para ver el mapeo a SRNs.

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
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
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
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

<Accordion title="Rate (af_rate)">

**Descripción**: Se utiliza para registrar eventos de inicio de pago. Para reportar un evento que incluye varios elementos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.

**Mapeo de eventos:**

| AppsFlyer | af\_rate |
| --- | --- |
| Meta Ads | fb\_mobile\_rate |
| Anuncios de Google | submit\_rating |
| TikTok | Calificación |
| Snap | RATE |
| Anuncios X | RATED |
| Anuncios de Amazon | - |
| Criteo | - |

**Parámetros típicos:**

Haz clic en los enlaces para ver el mapeo a SRNs.

* [af\_rating\_value](/docs/in-app-events-event-structure#af_rating_value)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_max\_rating\_value](/docs/in-app-events-event-structure#af_max_rating_value)

</Accordion>

<div id="reengage-af_re_engage" />

<Accordion title="Re-engage (af_re_engage)">

**Descripción**: Se utiliza para registrar eventos de reenganche de usuarios

**Mapeo de eventos:**

| AppsFlyer | af\_re\_engage |
| --- | --- |
| Meta Ads | - |
| Anuncios de Google | custom\_event |
| Snap | - |
| Anuncios X | RE\_ENGAGE |
| Anuncios de Amazon | - |
| Criteo | - |

**Parámetro típico:**

Haz clic en el enlace para ver la asignación con SRNs.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="search-af_search" />

<Accordion title="Búsqueda (af_search)">

**Descripción**: Se utiliza para registrar eventos de búsqueda

**Aparece en estos mercados:** <Anchor target="_blank" href="/marketers/es/docs/recommended-ecommerce-app-events#search-af_search">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-flight-booking-app-events#search-af_search">Reservas de vuelos</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-hotel-booking-app-events#search-af_search">Reservas Hoteleras</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_search |
| --- | --- |
| Meta Ads | fb\_mobile\_search |
| Anuncios de Google | view\_search\_results |
| TikTok | Búsqueda |
| Snap | Buscar |
| Anuncios X | Buscar |
| Anuncios de Amazon | Buscar |
| Criteo | viewSearch |
| Anuncios de Roku | Buscar |

**Parámetros típicos:**

Haz clic en los parámetros relevantes para las necesidades de su negocio para ver el mapeo a SRNs.

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_search\_string](/docs/in-app-events-event-structure#af_search_string)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
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

<Accordion title="Compartir (af_share)">

**Descripción**: Se utiliza para registrar eventos de compartición

**Aparece en estas verticales:** <Anchor target="_blank" href="/marketers/es/docs/recommended-gaming-app-events#share-af_share">Videojuegos</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_share |
| --- | --- |
| Meta Ads | - |
| Anuncios de Google | share |
| TikTok | - |
| Snap | Compartir |
| Anuncios X | Compartir |
| Anuncios de Amazon | - |
| Criteo | - |

**Parámetro típico:**

Haz clic en el enlace para ver la asignación con SRNs.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="Créditos gastados (af_spent_credits)">

**Descripción**: Se utiliza para registrar eventos de reservas de viajes (y asociarles ingresos). Para reportar un evento que incluye varios elementos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.

**Aparece en sectores:** <Anchor target="_blank" href="/marketers/es/docs/recommended-ride-hailing-app-events#spent-credits-af_spent_credits">Servicios de transporte</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_spent\_credits |
| --- | --- |
| Meta Ads | fb\_mobile\_spent\_credits |
| Anuncios de Google | spend\_virtual\_currency |
| TikTok | SpendCredits |
| Snap | SPENT\_CREDITS |
| Anuncios X | SPENT\_CREDITS |
| Anuncios de Amazon | - |
| Criteo | transactionConfirmation |

**Parámetros típicos:**

Haz clic en los enlaces para ver el mapeo a SRNs.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="start-trial-af_start_trial" />

<Accordion title="Iniciar prueba (af_start_trial)">

**Descripción**: Se utiliza para registrar las finalizaciones de tutorial. Para reportar un evento que incluye varios elementos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.

**Aparece en estas verticales:** <Anchor target="_blank" href="/marketers/es/docs/recommended-entertainment-app-events#start-trial-af_start_trial">Entretenimiento</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_start\_trial |
| --- | --- |
| Meta Ads | Comenzar prueba |
| Anuncios de Google | - |
| TikTok | Comenzar prueba |
| Snap | START\_TRIAL |
| Anuncios X | - |
| Anuncios de Amazon | - |
| Criteo | - |
| Anuncios de Roku | START\_TRIAL |

**Parámetros típicos:**

Haz clic en los enlaces para ver el mapeo a SRNs.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

<div id="note" />

> 📘 **Nota:**
>
> Si estás mapeando este evento al evento StartTrial de Meta Ads y desea asociar ingresos, use el parámetro af\_price en vez de af\_revenue.

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="Suscripción (af_subscribe)">

**Descripción**: Se utiliza para registrar eventos de actualización. Para reportar un evento que incluye varios elementos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.

**Aparece en estas verticales:** <Anchor target="_blank" href="/marketers/es/docs/recommended-entertainment-app-events#subscription-af_subscribe">Entretenimiento</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_subscribe |
| --- | --- |
| Meta Ads | Suscribirse |
| Anuncios de Google | - |
| TikTok | Suscribirse |
| Snap | SUBSCRIBE |
| Anuncios X | - |
| Anuncios de Amazon | SUBSCRIBE |
| Criteo | SUBSCRIBE |
| Anuncios de Roku | SUBSCRIBE |

**Parámetros típicos:**

Haz clic en los enlaces para ver el mapeo a SRNs.

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="Reserva de viaje (af_travel_booking)">

**Descripción**: se usa para registrar eventos de reserva de viajes (y asociarles ingresos). **Descripción**: Se utiliza para registrar eventos de calificación de aplicaciones o artículos Para reportar un evento que incluye varios elementos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.

**Aparece en estas verticales:** <Anchor target="_blank" href="/marketers/es/docs/recommended-flight-booking-app-events#travel-booking-af_travel_booking">Reserva de vuelo</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-hotel-booking-app-events#travel-booking-af_travel_booking">Reserva de hotel</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_travel\_booking |
| --- | --- |
| Meta Ads | fb\_mobile\_purchase |
| Anuncios de Google | ecommerce\_purchase |
| TikTok | Compra |
| Snap | RESERVE |
| Anuncios X | COMPRAR |
| Anuncios de Amazon | - |
| Criteo | transactionConfirmation |

**Parámetros típicos:**

Haz clic en los parámetros relevantes para las necesidades de su negocio para ver el mapeo a SRNs.

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_customer\_user\_id](/docs/in-app-events-event-structure#af_customer_user_id)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
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

<Accordion title="Finalización del tutorial (af_tutorial_completion)">

**Descripción**: Moneda utilizada para la compra **Descripción**: Se utiliza para registrar eventos de calificación de aplicaciones o artículos Para reportar un evento que incluye varios elementos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.

**Aparece en estas verticales:** <Anchor target="_blank" href="/marketers/es/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">Videojuegos</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">Educación en línea</Anchor>

**Mapeo de eventos:**

| AppsFlyer | af\_tutorial\_completion |
| --- | --- |
| Meta Ads | fb\_mobile\_tutorial\_completion |
| Anuncios de Google | tutorial\_complete |
| TikTok | CompleteTutorial |
| Snap | COMPLETE\_TUTORIAL |
| Anuncios X | TUTORIAL\_COMPLETE |
| Anuncios de Amazon | - |
| Criteo | - |

**Parámetros típicos:**

Haz clic en los enlaces para ver el mapeo a SRNs.

* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="update-af_update" />

<Accordion title="Actualizar (af_update)">

**Descripción**: se usa para registrar eventos de actualización. **Descripción**: Se utiliza para registrar eventos de calificación de aplicaciones o artículos Para reportar un evento que incluye varios elementos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.

**Mapeo de eventos:**

| AppsFlyer | af\_update |
| --- | --- |
| Meta Ads | - |
| Anuncios de Google | app\_update |
| Snap | - |
| Anuncios X | UPDATE |
| Anuncios de Amazon | - |
| Criteo | - |

**Parámetro típico:**

Haz clic en el enlace para ver la asignación con SRNs.

* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)

</Accordion>

<div id="note-1" />

> 📘 **Nota:**
>
> Además de los nombres de eventos predefinidos descritos en esta sección, <Anchor target="_blank" href="/marketers/es/docs/meta-ads-in-app-event-mapping#asignación-de-eventos-predefinidos">Meta ads ofrece eventos adicionales</Anchor> que se envían sin atributos.

<div id="predefined-event-parameters" />

## Parámetros de evento predefinidos

La siguiente sección proporciona una lista de parámetros de eventos predefinidos. Cada parámetro de evento incluye el mapeo usado para Meta ads, Google Ads, Snap, X Ads y Criteo. Puedes elegir incluir cualquiera de los parámetros de evento en un evento.

<div id="note-2" />

> 📘 **Nota:**
>
> Puedes ver los parámetros de evento en la columna Valor del evento en los <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">informes de datos sin procesar</Anchor> (función premium).

<div id="af_adrev_ad_type" />

<Accordion title="af_adrev_ad_type">

**Descripción**: Tipo de anuncio (por ejemplo, banner o intersticial)

**Mapeo de parámetros:**

| AppsFlyer | af\_adrev\_ad\_type |
| --- | --- |
| Meta Ads | ad\_type |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_city" />

<Accordion title="af_city">

**Descripción**: Ciudad donde se reserva el viaje

**Mapeo de parámetros:**

| AppsFlyer | af\_city |
| --- | --- |
| Meta Ads | fb\_city |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | flight\_city |
| Criteo | - |

</Accordion>

<div id="af_class" />

<Accordion title="af_class">

**Descripción**: Clase de viaje reservada para el vuelo

**Mapeo de parámetros:**

| AppsFlyer | af\_class |
| --- | --- |
| Meta Ads | fb\_travel\_class |
| Anuncios de Google | travel\_class |
| Snap | - |
| Anuncios X | - |
| TikTok | flight\_class |
| Criteo | - |

</Accordion>

<div id="af_content" />

<Accordion title="af_content">

**Descripción**: Título del contenido (por ejemplo, nombre de una canción o título y episodio de un programa de TV)

**Mapeo de parámetros:**

| AppsFlyer | af\_content |
| --- | --- |
| Meta Ads | fb\_content |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_content_id" />

<Accordion title="af_content_id">

**Descripción**: ID del artículo

**Nota:** Los eventos predefinidos de Snapchat `af_content_id` y `af_content_id` comparten el mismo parámetro de evento. Cuando ambos eventos se registran simultáneamente, solo el evento `af_content_list` se envía a Snapchat.

**Mapeo de parámetros:**

| AppsFlyer | af\_content\_id |
| --- | --- |
| Meta Ads | fb\_content\_id |
| Anuncios de Google | item\_id |
| Snap | item\_ids |
| Anuncios X | content\_id |
| TikTok | content\_id |
| Criteo | ID |

</Accordion>

<div id="af_content_list" />

<Accordion title="af_content_list">

**Descripción**: Lista de IDs de contenido

**Nota:** Cuando usas `af_content_list`, AppsFlyer trata toda la lista como un solo valor. Las herramientas de segmentación de audiencias de AppsFlyer no pueden filtrar IDs de contenido individuales en la lista. Por ejemplo, si  `af_content_list` es `["ID1","ID2","ID3"]`, la herramienta de audiencias no puede aislar ni hacer coincidir solo `ID1`.

**Mapeo de parámetros:**

| AppsFlyer | af\_content\_list |
| --- | --- |
| Meta Ads | fb\_content\_id |
| Anuncios de Google | item\_id |
| Snap | item\_ids |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_content_type" />

<Accordion title="af_content_type">

**Descripción**: Categoría del producto

**Mapeo de parámetros:**

| AppsFlyer | af\_content\_type |
| --- | --- |
| Meta Ads | fb\_content\_type |
| Anuncios de Google | item\_category |
| Snap | item\_category |
| Anuncios X | content\_type |
| TikTok | content\_type |
| Criteo | - |

</Accordion>

<div id="af_country" />

<Accordion title="af_country">

**Descripción**: País donde se reserva el viaje

**Mapeo de parámetros:**

| AppsFlyer | af\_country |
| --- | --- |
| Meta Ads | fb\_country |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | flight\_country |
| Criteo | - |

</Accordion>

<div id="af_currency" />

<Accordion title="af_currency">

**Descripción**: Código de moneda

**Mapeo de parámetros:**

| AppsFlyer | af\_currency |
| --- | --- |
| Meta Ads | fb\_currency |
| Anuncios de Google | currency\_code |
| Snap | moneda |
| Anuncios X | price\_currency |
| TikTok | moneda |
| Anuncios de Amazon | moneda |
| Criteo | moneda |

</Accordion>

<div id="af_customer_user_id" />

<Accordion title="af_customer_user_id">

**Descripción**: ID del cliente

**Mapeo de parámetros:**

| AppsFlyer | af\_customer\_user\_id |
| --- | --- |
| Meta Ads | - |
| Anuncios de Google | customer\_user\_  <br />id |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | cid |

</Accordion>

<div id="af_date_a" />

<Accordion title="af_date_a">

**Descripción**: Fecha de partida

**Mapeo de parámetros:**

| AppsFlyer | af\_date\_a |
| --- | --- |
| Meta Ads | fb\_checkin\_date |
| Anuncios de Google | start\_date |
| Snap | - |
| Anuncios X | - |
| TikTok | checkin\_date |
| Criteo | din |

</Accordion>

<div id="af_date_b" />

<Accordion title="af_date_b">

**Descripción**: Fecha de entrada

**Mapeo de parámetros:**

| AppsFlyer | af\_date\_b |
| --- | --- |
| Meta Ads | fb\_checkout\_date |
| Anuncios de Google | end\_date |
| Snap | - |
| Anuncios X | - |
| TikTok | checkout\_date |
| Criteo | dout |

</Accordion>

<div id="af_departing_arrival_date" />

<Accordion title="af_departing_arrival_date">

**Descripción**: Fecha de llegada

**Mapeo de parámetros:**

| AppsFlyer | af\_departing\_arrival\_date |
| --- | --- |
| Meta Ads | fb\_departing\_arrival\_date |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_departing_departure_date" />

<Accordion title="af_departing_departure_date">

**Descripción**: Fecha de salida

**Mapeo de parámetros:**

| AppsFlyer | af\_departing\_ departure\_date |
| --- | --- |
| Meta Ads | fb\_departing\_ departure\_date |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | departing\_date |
| Criteo | - |

</Accordion>

<div id="af_description" />

<Accordion title="af_description">

**Descripción**: Descripción breve (cadena)

**Mapeo de parámetros:**

| AppsFlyer | af\_description |
| --- | --- |
| Meta Ads | fb\_description |
| Anuncios de Google | description |
| Snap | description |
| Anuncios X | description |
| TikTok | description |
| Criteo | logro\_ui |

</Accordion>

<div id="af_destination_a" />

<Accordion title="af_destination_a">

**Descripción**: Primer destino

**Mapeo de parámetros:**

| AppsFlyer | af\_destination\_a |
| --- | --- |
| Meta Ads | fb\_origin\_airport |
| Anuncios de Google | origin |
| Snap | - |
| Anuncios X | - |
| TikTok | departing\_airport |
| Criteo | - |

</Accordion>

<div id="af_destination_b" />

<Accordion title="af_destination_b">

**Descripción**: Segundo destino

**Mapeo de parámetros:**

| AppsFlyer | af\_destination\_b |
| --- | --- |
| Meta Ads | fb\_destination\_  <br />airport |
| Anuncios de Google | destination |
| Snap | - |
| Anuncios X | - |
| TikTok | destination\_airport |
| Criteo | - |

</Accordion>

<div id="af_destination_list" />

<Accordion title="af_destination_list">

**Descripción**: Lista de destinos incluidos en un catálogo de destinos (por ejemplo, una lista de museos o restaurantes cercanos a un hotel)

**Mapeo de parámetros:**

| AppsFlyer | af\_destination\_list |
| --- | --- |
| Meta Ads | fb\_destination\_ids |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_hotel_score" />

<Accordion title="af_hotel_score">

**Descripción**: Puntuación del hotel según las reseñas

**Mapeo de parámetros:**

| AppsFlyer | af\_hotel\_score |
| --- | --- |
| Meta Ads | fb\_hotel\_score |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_level" />

<Accordion title="af_level">

**Descripción**: Nivel alcanzado por el usuario

**Mapeo de parámetros:**

| AppsFlyer | af\_level |
| --- | --- |
| Meta Ads | fb\_level |
| Anuncios de Google | level\_up |
| Snap | level |
| Anuncios X | level |
| TikTok | - |
| Criteo | ui\_level |

</Accordion>

<div id="af_max_rating_value" />

<Accordion title="af_max_rating_value">

**Descripción**: Extremo superior de una escala de calificación (por ejemplo, 5 de 5)

**Mapeo de parámetros:**

| AppsFlyer | af\_max\_rating\_value |
| --- | --- |
| Meta Ads | fb\_max\_rating\_value |
| Anuncios de Google | max\_rating |
| Snap | - |
| Anuncios X | max\_rated\_value |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="h_01NEWAFNETREVENUE0001" />

<Accordion title="af_purchase_currency">

**Descripción**: Ingresos netos reportados para el evento. El valor representa los ingresos netos según tu propia lógica de negocio; AppsFlyer no prescribe cómo se calcula y agrega el valor que envías. Ejemplos habituales: ingresos después de las comisiones de la tienda de aplicaciones y/o impuestos, margen bruto o ingresos después de comisiones bancarias o de servicio (eCommerce, finanzas, etc.). Se utiliza para las métricas de ingresos netos (ingresos netos, ROI neto, ROAS neto, ARPU neto y beneficio neto) en <Anchor target="_blank" href="/marketers/es/docs/my-dashboards">Mis dashboards</Anchor>.

El valor está en la moneda de la transacción, expresada por af\_currency (USD de forma predeterminada). Las mismas reglas de formato que para af\_revenue: sin separadores de comas, símbolos de moneda, caracteres especiales ni texto (por ejemplo, 1234.56), con hasta cinco decimales.

**Nota:** No hay ninguna constante del SDK predefinida para este parámetro, así que envíalo como parámetro personalizado con la clave af\_net\_revenue.

<div id="note-3" />

> 📘 **Nota**
>
> En las apps con <Anchor target="_blank" href="/marketers/es/docs/about-roi360-store-revenue">ROI360 store revenue</Anchor> activado, AppsFlyer rellena af\_net\_revenue automáticamente en los eventos de compra in-app y suscripción que registra, calculado como ingresos brutos menos las comisiones de la tienda de aplicaciones y los impuestos (Neto = Bruto - comisiones de la tienda - impuestos).

</Accordion>

<div id="af_num_adults" />

<Accordion title="af_num_adults">

**Descripción**: Número de adultos que viajan

**Mapeo de parámetros:**

| AppsFlyer | af\_num\_adults |
| --- | --- |
| Meta Ads | fb\_num\_adults |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | num\_people |
| Criteo | - |

</Accordion>

<div id="af_num_children" />

<Accordion title="af_num_children">

**Descripción**: Número de niños que viajan

Mapeo de parámetros:

| AppsFlyer | af\_num\_children |
| --- | --- |
| Meta Ads | fb\_num\_children |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | num\_children |
| Criteo | - |

</Accordion>

<div id="af_num_infants" />

<Accordion title="af_num_infants">

**Descripción**: Número de bebés que viajan

**Mapeo de parámetros:**

| AppsFlyer | af\_num\_infants |
| --- | --- |
| Meta Ads | fb\_num\_infants |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_order_id" />

<Accordion title="af_order_id">

**Descripción**: ID de la transacción

**Mapeo de parámetros:**

| AppsFlyer | af\_order\_id |
| --- | --- |
| Meta Ads | fb\_order\_id |
| Anuncios de Google | order\_id |
| Snap | transaction\_id |
| Anuncios X | - |
| TikTok | order\_id |
| Criteo | transaction\_id |

</Accordion>

<div id="af_payment_info_available" />

<Accordion title="af_payment_info_available">

**Descripción**: Disponibilidad de la información de pago del usuario

**Mapeo de parámetros:**

| AppsFlyer | af\_payment\_info\_available |
| --- | --- |
| Meta Ads | fb\_payment\_info\_available |
| Anuncios de Google | payment\_info\_available |
| Snap | payment\_info\_available |
| Anuncios X | user\_payment\_  <br />info |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_neighborhoods" />

<Accordion title="af_preferred_neighborhoods">

**Descripción**: Zona donde se encuentra el hotel

**Mapeo de parámetros:**

| AppsFlyer | af\_preferred\_neighborhoods |
| --- | --- |
| Meta Ads | fb\_preferred\_neighborhoods |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_num_stops" />

<Accordion title="af_preferred_num_stops">

**Descripción**: Número de paradas que busca el usuario (por ejemplo, vuelo directo o sin escalas)

**Mapeo de parámetros:**

| AppsFlyer | af\_preferred\_num\_stops |
| --- | --- |
| Meta Ads | fb\_preferred\_num\_stops |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_price_range" />

<Accordion title="af_preferred_price_range">

**Descripción**: Rango de precio preferido del hotel

Mapeo de parámetros:

| AppsFlyer | af\_preferred\_price\_range |
| --- | --- |
| Meta Ads | fb\_preferred\_price\_range |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_star_ratings" />

<Accordion title="af_preferred_star_ratings">

**Descripción**: Calificación de estrellas preferida del hotel

**Mapeo de parámetros:**

| AppsFlyer | af\_preferred\_star\_ratings |
| --- | --- |
| Meta Ads | fb\_preferred\_star\_ratings |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_price" />

<Accordion title="af_price">

**Descripción**: Precio del producto. Puedes utilizar af\_price como un parámetro monetario que no se considera ingreso (como en un evento de Agregar al carrito). Este parámetro se refiere al precio del artículo individual. El importe total de todas las compras se muestra bajo el parámetro [af\_revenue](/docs/in-app-events-event-structure#af_revenue).

**Mapeo de parámetros:**

| AppsFlyer | af\_price |
| --- | --- |
| Meta Ads | fb\_price |
| Anuncios de Google | price |
| Snap | price |
| Anuncios X | price\_micro |
| TikTok | price |
| Criteo | price |

</Accordion>

<div id="af_projected_revenue" />

<Accordion title="af_projected_revenue">

Los ingresos estimados que un anunciante espera de un usuario según sus primeras interacciones o comportamientos antes de que se realicen los ingresos reales.

</Accordion>

<div id="af_quantity" />

<Accordion title="af_quantity">

**Descripción**: Número de artículos

**Mapeo de parámetros:**

| AppsFlyer | af\_quantity |
| --- | --- |
| Meta Ads | fb\_num\_items |
| Anuncios de Google | cantidad |
| Snap | number\_items |
| Anuncios X | number\_items |
| TikTok | cantidad |
| Criteo | cantidad |

</Accordion>

<div id="af_rating_value" />

<Accordion title="af_rating_value">

**Descripción**: Valor de calificación seleccionado

**Mapeo de parámetros:**

| AppsFlyer | af\_rating\_value |
| --- | --- |
| Meta Ads | \_valueToSum |
| Anuncios de Google | value |
| Snap | - |
| Anuncios X | price\_micro |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_receipt_id" />

<Accordion title="af_receipt_id">

**Descripción**: ID del recibo

**Mapeo de parámetros:**

| AppsFlyer | af\_receipt\_id |
| --- | --- |
| Meta Ads | - |
| Anuncios de Google | transaction\_id |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | transaction\_id |

</Accordion>

<div id="af_region" />

<Accordion title="af_region">

**Descripción**: Región donde se reserva el viaje

**Mapeo de parámetros:**

| AppsFlyer | af\_region |
| --- | --- |
| Meta Ads | fb\_region |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | flight\_region |
| Criteo | - |

</Accordion>

<div id="af_registration_method" />

<Accordion title="af_registration_method">

**Descripción**: Tipo de método de registro

**Mapeo de parámetros:**

| AppsFlyer | af\_registration\_method |
| --- | --- |
| Meta Ads | fb\_registration\_method |
| Anuncios de Google | registration\_method |
| Snap | sign\_up\_method |
| Anuncios X | registration\_method |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_returning_arrival_date" />

<Accordion title="af_returning_arrival_date">

**Descripción**: Fecha y hora de finalización del viaje de regreso

**Mapeo de parámetros:**

| AppsFlyer | af\_purchase\_currency |
| --- | --- |
| Meta Ads | fb\_returning\_arrival\_date |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_returning_departure_date" />

<Accordion title="af_returning_departure_date">

**Descripción**:  Fecha y hora de inicio del viaje de regreso

**Mapeo de parámetros:**

| AppsFlyer | af\_returning\_departure\_date |
| --- | --- |
| Meta Ads | fb\_returning\_departure\_date |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | returning\_date |
| Criteo | - |

</Accordion>

<div id="af_revenue" />

<Accordion title="af_revenue">

**Descripción**: Importe total de las compras. af\_revenue se considera como ingresos en la plataforma AppsFlyer. También se contabilizan los <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">ingresos negativos</Anchor> derivados de cancelaciones o reembolsos.

<div id="important" />

> 🚧 **Importante:**
>
> El valor de los ingresos no debe contener comas, moneda, caracteres especiales o texto. Por ejemplo, un valor de ingresos debería ser 1234,56. AppsFlyer proporciona el valor del ingreso con una precisión de hasta cinco decimales.

Para obtener más información sobre cómo usar el parámetro de ingresos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">aquí</Anchor>.

**Ingresos netos:** Para reportar ingresos netos junto con ingresos brutos, envía [af\_net\_revenue](/docs/in-app-events-event-structure#h_01NEWAFNETREVENUE0001) como parámetro de evento personalizado. Tú defines qué significa neto para tu negocio (por ejemplo, ingresos después de comisiones de la tienda y/o impuestos, margen bruto o ingresos después de comisiones de servicio). Las apps con ROI360 store revenue activado lo tienen rellenado automáticamente en los eventos de compra y suscripción que registra AppsFlyer, como bruto menos las comisiones de la tienda de aplicaciones y los impuestos.

**Mapeo de parámetros:**

| AppsFlyer | af\_revenue |
| --- | --- |
| Meta Ads | \_valueToSum |
| Anuncios de Google | value |
| Snap | price |
| Anuncios X | price\_micro |
| TikTok | value |
| Anuncios de Amazon | valor del evento |
| Criteo | ui\_revenue |

</Accordion>

<div id="af_score" />

<Accordion title="af_score">

**Descripción**: Puntuación asociada al logro del usuario

**Mapeo de parámetros:**

| AppsFlyer | af\_score |
| --- | --- |
| Meta Ads | - |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | score |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_search_string" />

<Accordion title="af_search_string">

**Descripción**: Término de búsqueda

**Mapeo de parámetros:**

| AppsFlyer | af\_search\_string |
| --- | --- |
| Meta Ads | fb\_search\_string |
| Anuncios de Google | search\_string |
| Snap | search\_string |
| Anuncios X | search\_string |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_subscription_id" />

<Accordion title="af_subscription_id">

**Descripción**: ID de suscripción del usuario

**Mapeo de parámetros:**

| AppsFlyer | af\_subscription\_id |
| --- | --- |
| Meta Ads | subscription\_id |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_success" />

<Accordion title="af_success">

**Descripción**: Si la finalización de la acción fue exitosa

**Mapeo de parámetros:**

| AppsFlyer | af\_success |
| --- | --- |
| Meta Ads | fb\_success |
| Anuncios de Google | success |
| Snap | success |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_suggested_destinations" />

<Accordion title="af_suggested_destinations">

**Descripción**: Lista de destinos sugeridos

**Mapeo de parámetros:**

| AppsFlyer | af\_suggested\_destinations |
| --- | --- |
| Meta Ads | fb\_suggested\_destinations |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_suggested_hotels" />

<Accordion title="af_suggested_hotels">

**Descripción**: Lista de hoteles sugeridos

**Mapeo de parámetros:**

| AppsFlyer | af\_suggested\_ hotels |
| --- | --- |
| Meta Ads | fb\_suggested\_hotels |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_travel_end" />

<Accordion title="af_travel_end">

**Descripción**: Fecha de finalización del viaje

**Mapeo de parámetros:**

| AppsFlyer | af\_travel\_end |
| --- | --- |
| Meta Ads | fb\_travel\_end |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_travel_start" />

<Accordion title="af_travel_start">

**Descripción**: Fecha de inicio del viaje

**Mapeo de parámetros:**

| AppsFlyer | af\_travel\_start |
| --- | --- |
| Meta Ads | fb\_travel\_start |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_user_score" />

<Accordion title="af_user_score">

**Descripción**: Importancia relativa del usuario para el anunciante

**Mapeo de parámetros:**

| AppsFlyer | af\_user\_score |
| --- | --- |
| Meta Ads | fb\_user\_score |
| Anuncios de Google | - |
| Snap | - |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_validated" />

<Accordion title="af_validated">

**Descripción**: Valida una compra

**Mapeo de parámetros:**

| AppsFlyer | af\_validated |
| --- | --- |
| Meta Ads | - |
| Anuncios de Google | VALIDATED |
| Snap | success |
| Anuncios X | - |
| TikTok | - |
| Criteo | - |

</Accordion>

A continuación se muestra una lista de parámetros de eventos predefinidos que no incluyen mapeo de SRN:

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

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration">Configuración de postbacks de eventos in-app</Anchor>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01H9HT8C713A4NV9WCB0FJZJ4R=visi%C3%B3n-general predefined-event-names=nombres-de-eventos-predefinidos h_01H9HT8C7189W1JXAR3J3KT8KV=nombres-de-eventos-predefinidos h_01H9HT8C71MV7V7C75MB6ESHMM=achievement-unlocked-af_achievement_unlocked h_01H9HT8C7171PB7KAC83MYBWQ8=ad-click-af_ad_click h_01H9HT8C72KJ6ZA663SH7HJ7MP=ad-view-af_ad_view h_01H9HT8C72HSM88DJG0PDV5140=add-payment-info-af_add_payment_info h_01H9HT8C72BWFSPKWDVQW926WG=add-to-cart-af_add_to_cart h_01H9HT8C7228B57XKAACPZG8NK=add-to-wishlist-af_add_to_wishlist h_01K0PJ4C3HP9DMJT1DFZ848WF0=app-open-af_app_opened h_01H9HT8C72DX0DXBDHRJFG19G2=complete-registration-af_complete_registration h_01H9HT8C72SPY9VQ9AD648AKZK=content-view-af_content_view h_01H9HT8C722T2VH6A9257Q7T4P=initiated-checkout-af_initiated_checkout h_01H9HT8C72F0RZ4JS9929SE465=invite-af_invite h_01K0PJ4C3H72BDTRH7WAYW4V7S=lead-lead h_01H9HT8C72VFGC08Q858EX7XTN=level-achieved-af_level_achieved h_01H9HT8C72DZW77YTQ9KB0XEVG=list-view-af_list_view h_01H9HT8C720W10QEBCTPAGMRFB=login-af_login h_01H9HT8C72QC4WV10Z4JZTZM7D=opened-from-push-notification-af_opened_from_push_notification h_01H9HT8C7263J0YSX5K10R497N=purchase-af_purchase h_01H9HT8C73MPYMG8KSYE04DKDZ=rate-af_rate h_01H9HT8C734DAC6GPJE58DB5JD=reengage-af_re_engage h_01H9HT8C73YSYBK0YSDPRWDBNW=search-af_search h_01H9HT8C734GJ07V67QC9V3TVC=share-af_share h_01H9HT8C73H4VT2M0P3M1SYG88=spent-credits-af_spent_credits h_01H9HT8C73YWDCKAZPY0BVRS6F=start-trial-af_start_trial h_01H9HT8C736BF2VNRCFSJSVXWS=nota h_01H9HT8C73N69S45H82NWQ5FN1=subscription-af_subscribe h_01H9HT8C73CD6HNT5GA6B4CHQ9=travel-booking-af_travel_booking h_01H9HT8C73NFDPS1P5AVXXZEX7=tutorial-completion-af_tutorial_completion h_01H9HT8C73JPH6Q9XFKA3GNYT8=update-af_update h_01H9HT8C74SGGK2FW92JH4BJPZ=nota-1 predefined-event-parameters=par%C3%A1metros-de-evento-predefinidos h_01H9HT8C74N4TJZ5ZVBTKAX810=par%C3%A1metros-de-evento-predefinidos h_01H9HT8C74VQ9ZWF079V50E5HE=nota-2 h_01H9HT8C74Y0BWS565DFTY75KJ=af_adrev_ad_type h_01H9HT8C742NHGXFKWSS4P07K2=af_city h_01H9HT8C7442PFZEK7QC6R0K67=af_class h_01H9HT8C7462KG3030WWZ2XGZW=af_content h_01H9HT8C74ZX07907NXFHKGJ91=af_content_id h_01H9HT8C744CMWSYHJB74JFSS5=af_content_list h_01H9HT8C74GKGG5V4X54BCAADC=af_content_type h_01H9HT8C74RD08Z9EBZTKY5KSD=af_country h_01H9HT8C75BJYK4R3WYSN4BF43=af_currency h_01H9HT8C752E2PK6QKTA2GNGH5=af_customer_user_id h_01H9HT8C75BN0A92X9BRY4A74T=af_date_a h_01H9HT8C75406KV9264ZZT9DKM=af_date_b h_01H9HT8C7526AEHJAA7FM7442E=af_departing_arrival_date h_01H9HT8C75W9X61ZH0849EPDBY=af_departing_departure_date h_01H9HT8C75VEV3C8CJBDN6X5HW=af_description h_01H9HT8C75Z8TBZEPEY9EGSR4Y=af_destination_a h_01H9HT8C751G216VB6GYTPEPE1=af_destination_b h_01H9HT8C75CVM0MHSKTK2CZ8HD=af_destination_list h_01H9HT8C75CVVDFABSTN5R4MWT=af_hotel_score h_01H9HT8C75GEMHE2NHEFK9J7NT=af_level h_01H9HT8C7505H4CMY70EMDQWSF=af_max_rating_value af_net_revenue=h_01NEWAFNETREVENUE0001 h_01NEWAFNETREVENUENOTE0001=nota-3 h_01H9HT8C75ST9XBDC3SR6XFDPB=af_num_adults h_01H9HT8C75NNZ5NP6PRPXDSKP8=af_num_children h_01H9HT8C757X70AAGNWFV0CKRY=af_num_infants h_01H9HT8C75A0HESE5FD10VD1P8=af_order_id h_01H9HT8C75B488VKY8SW9M4GG4=af_payment_info_available h_01H9HT8C75W7SRB0KF4E5FB2YF=af_preferred_neighborhoods h_01H9HT8C75GC61D1A0P6P42TMR=af_preferred_num_stops h_01H9HT8C76XRY6CD1TJEPCJJTR=af_preferred_price_range h_01H9HT8C76Y9ZQQ2X4EJT2DC14=af_preferred_star_ratings h_01H9HT8C76KCDRJKBWSM9JKFE1=af_price 01J9XHWVFHXPN6N3EZF1P8XWYM=af_projected_revenue h_01H9HT8C76Y5VXBKF3TBVVJG1C=af_quantity h_01H9HT8C768WXZ126Q425PHDWX=af_rating_value h_01H9HT8C76XX9J6FZ6RWQB6B6R=af_receipt_id h_01H9HT8C760S0F7QZMFYW1BKRD=af_region h_01H9HT8C76N4S3SGES5SQ2J4AC=af_registration_method h_01H9HT8C76ZR36A4CM2PY6PJ10=af_returning_arrival_date h_01H9HT8C760JPVXYC5WH9ZSDPX=af_returning_departure_date h_01H9HT8C76PYB14WPCQKSEK69J=af_revenue h_01H9HT8C762BGPRHFX228APEHR=importante h_01H9HT8C76P55HN8K6D7PHFS2J=af_score h_01H9HT8C76TB4KNTZVD6JVPEYQ=af_search_string h_01H9HT8C762R2PJ573W8TJFJHG=af_subscription_id h_01H9HT8C76VZ6FA20K471V0EKK=af_success h_01H9HT8C76029H94AY5EHCZX6X=af_suggested_destinations h_01H9HT8C76N6C694TCPVCK4EC3=af_suggested_hotels h_01H9HT8C765EM1SAEJ67FNXZDE=af_travel_end h_01H9HT8C76YP8VEM5E6WB9NQ7T=af_travel_start h_01H9HT8C771SYQWQ8VBTPA2V2E=af_user_score h_01H9HT8C771XFSQJX42QVBNZAJ=af_validated h_01HDNZ30NH2QXSHD7B4EMFG4T5=consulta-tambi%C3%A9n" />
