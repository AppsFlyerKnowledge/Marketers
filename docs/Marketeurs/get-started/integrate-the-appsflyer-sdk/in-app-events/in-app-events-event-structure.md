---
title: Événements in-app riches—Structure des événements
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
  edited_at: '2023-10-27T11:03:54Z'
  id: 4410481112081
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/4410481112081
---
> **En bref :** affichez la liste des noms d’événements et des paramètres d’événement prédéfinis afin d'enregistrer les événements in-app riches post installation de type connexion, inscription ou achat in-app.

<div id="overview" />

## Présentation

Pour que vous puissiez envoyer des événements in-app, votre développeur doit ajouter du code dans votre app. Cet article détaille les noms d’événements prédéfinis ainsi que les paramètres d’événement prédéfinis.

Pour vous aider à définir quels événements et paramètres doivent être enregistrés, consultez <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#recommended-events-by-business-vertical">nos articles avec différents exemples et flux</Anchor> en fonction des secteurs d'activité.

<div id="lead-lead" />

<div id="app-open-af_app_opened" />

<div id="predefined-event-names" />

## Noms d'événements prédéfinis

La section suivante fournit une liste de noms d'événements prédéfinis et du mappage d'évènement utilisé pour Meta ads, Google Ads, TikTok, Snap, Twitter et Criteo.

Chaque nom d'événement inclut également les paramètres d'événement prédéfinis typiques associés à cet événement. Vous pouvez choisir d'inclure tous les paramètres d'événement qui répondent aux besoins de votre entreprise.

<div id="achievement-unlocked-af_achievement_unlocked" />

<Accordion title="Succès déverrouillé (af_achievement_unlocked)">

**Description** : permet d'enregistrer les évènements de déverrouillage de l'exécution

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_achievement\_unlocked | fb\_mobile\_achievement\_unlocked | unlock\_achievement | UnlockAchievement | ACHIEVEMENT\_UNLOCKED | ACHIEVEMENT\_UNLOCKED | succès |

**Paramètre type :**

Cliquez sur le lien pour afficher le mappage vers les SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="ad-click-af_ad_click" />

<Accordion title="Clic sur une publicité (af_ad_click)">

**Description** : permet d'enregistrer les clics sur des publicités affichées dans l'app

**Mappage d'événement** :

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_ad\_click | Clic sur une publicité | - | InAppADClick | AD\_CLICK | - | - |

**Paramètres type :**

Cliquez sur les liens pour afficher le mappage vers les SRN.

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="ad-view-af_ad_view" />

<Accordion title="Visualisation de la publicité (af_ad_view)">

**Description** : permet d'enregistrer les visualisations de publicités affichées dans l'app

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_ad\_view | AdImpression | - | InAppADImpr | AD\_VIEW | - | - |

**Paramètres type :**

Cliquez sur les liens pour afficher le mappage vers les SRN.

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="Ajouter des informations de paiement (af_add_payment_info)">

**Description** : permet d'enregistrer l'état de configuration des informations de paiement

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-ride-hailing-app-events#add-payment-info-af_add_payment_info">transport</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-flight-booking-app-events#add-payment-info-af_add_payment_info">réservation de vols</Anchor>

**Mappage d'événement** :

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_add\_payment\_info | fb\_mobile\_add\_payment\_info | add\_payment\_info | Ajouter des informations de paiement | ADD\_BILLING | ADDED\_PAYMENT\_INFO | ADD\_BILLING |

**Paramètre type :**

Cliquez sur le lien pour afficher le mappage vers les SRN.

* [af\_success](/docs/in-app-events-event-structure#af_success)

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="Ajouter au panier (af_add_to_cart)">

**Description** : permet d'enregistrer les évènements « ajouter au panier » de certains articles. Pour signaler un événement contenant plusieurs éléments, cliquez <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">ici.</Anchor>

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-healthcare-app-events#add-to-cart-af_add_to_cart">soins de santé</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_add\_to\_cart | fb\_mobile\_add\_to\_cart | add\_to\_cart | AddToCart | ADD\_CART | ADD\_TO\_CART | viewBasket |

**Paramètres type :**

Cliquez sur les liens pour afficher le mappage vers les SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Ajouter à la liste de souhaits (af_add_to_wishlist)">

**Description** : permet d'enregistrer les évènements « ajouter à la liste d'envies » de certains articles spécifiques. Pour signaler un événement contenant plusieurs éléments, cliquez <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">ici.</Anchor>

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-ecommerce-app-events#add-to-wishlist-af_add_to_wishlist">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-hotel-booking-app-events#add-to-wishlist-af_add_to_wishlist">réservation d'hôtels</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_add\_to\_wishlist | fb\_mobile\_add\_to\_wishlist | add\_to\_wishlist | AddToWishlist | ADD\_TO\_WISHLIST | ADD\_TO\_WISHLIST | - |

**Paramètres type :**

Cliquez sur les liens pour afficher le mappage vers les SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Inscription terminée (af_complete_registration)">

**Description** : permet d'enregistrer les méthodes d'enregistrement des utilisateurs

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-gaming-app-events#complete-registration-af_complete_registration">gaming</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-ecommerce-app-events#complete-registration-af_complete_registration">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-entertainment-app-events#complete-registration-af_complete_registration">divertissement</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-finance-and-banking-app-events#complete-registration-af_complete_registration">bancaire</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-p2p-lending-app-events#complete-registration-af_complete_registration">prêts P2P</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-online-education-app-events#complete-registration-af_complete_registration">formation en ligne</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-ride-hailing-app-events#complete-registration-af_complete_registration">transport</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-hotel-booking-app-events#complete-registration-af_complete_registration">réservation d'hôtels</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-healthcare-app-events#complete-registration-af_complete_registration">Soins de santé</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-telecommunication-app-events#complete-registration-af_complete_registration">télécommunications</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_complete\_registration | fb\_mobile\_complete\_registration | sign\_up | Inscription | SIGN\_UP | SIGN\_UP | - |

**Paramètre type :**

Cliquez sur le lien pour afficher le mappage vers les SRN.

* [af\_registration\_method](/docs/in-app-events-event-structure#af_registration_method)

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Affichage du contenu (af_content_view)">

**Description** : permet d'enregistrer les évènements d'affichage du contenu Pour signaler un événement contenant plusieurs éléments, cliquez <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">ici</Anchor>.

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-ecommerce-app-events#content-view-af_content_view">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-flight-booking-app-events#content-view-af_content_view">réservation de vols</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-hotel-booking-app-events#content-view-af_content_view">réservation d'hôtels</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_content\_view | fb\_mobile\_content\_view | view\_item | ViewContent | VIEW\_CONTENT | CONTENT\_VIEW | viewProduct |

**Paramètres type :**

Cliquez sur les paramètres qui correspondent à vos besoins commerciaux pour afficher le mappage vers les SRN.

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
* [af\_purchase\_currency](/docs/in-app-events-event-structure#af_purchase_currency)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="Paiement initié (af_initiated_checkout)">

**Description** : permet d'enregistrer les évènements de paiement. Pour signaler un événement contenant plusieurs éléments, cliquez <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">ici.</Anchor>

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-ecommerce-app-events#initiated-checkout-af_initiated_checkout">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-hotel-booking-app-events#initiated-checkout-af_initiated_checkout">réservation d'hôtels</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_initiated\_checkout | fb\_mobile\_initiated\_checkout | begin\_checkout | Checkout | START\_CHECKOUT | CHECKOUT\_INITIATED | viewBasket |

**Paramètres type :**

Cliquez sur les paramètres pertinents pour votre entreprise pour afficher le mappage vers les SRN.

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
* [af\_purchase\_currency](/docs/in-app-events-event-structure#af_purchase_currency)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="invite-af_invite" />

<Accordion title="Invitation (af_invite)">

**Description** : permet d'enregistrer les évènements d'invitations (sociales)

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-gaming-app-events#invite-af_invite">gaming</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_invite | - | invite | - | INVITE | INVITE | - |

**Paramètre type :**

Cliquez sur le lien pour afficher le mappage vers les SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="Niveau atteint (af_level_achieved)">

**Description** : permet d'enregistrer les évènements de niveau jeu

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-gaming-app-events#level-achieved-af_level_achieved">gaming</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_level\_achieved | fb\_mobile\_level\_achieved | level\_up | AchieveLevel | LEVEL\_COMPLETE | LEVEL\_ACHIEVED | Niveau utilisateur |

**Paramètres type :**

Cliquez sur les liens pour afficher le mappage vers les SRN.

* [af\_level](/docs/in-app-events-event-structure#af_level)
* [af\_score](/docs/in-app-events-event-structure#af_score)

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="Affichage de la liste (af_list_view)">

**Description** : permet d'enregistrer les évènements d'affichage de listes

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-ecommerce-app-events#list-view-af_list_view">eCommerce</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_list\_view | - | view\_item\_list | - | LIST\_VIEW | - | viewListing |

**Paramètres type :**

Cliquez sur les liens pour afficher le mappage vers les SRN.

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)

</Accordion>

<div id="login-af_login" />

<Accordion title="Connexion (af_login)">

**Description** : permet d'enregistrer les évènements de connexion utilisateur

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-gaming-app-events#login-af_login">gaming</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-ecommerce-app-events#login-af_login">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-entertainment-app-events#login-af_login">divertissement</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-finance-and-banking-app-events#login-af_login">bancaire</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-online-education-app-events#login-af_login">formations en ligne</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-hotel-booking-app-events#login-af_login">réservation d'hôtels</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-healthcare-app-events#login-af_login">soins de santé</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-telecommunication-app-events#login-af_login">télécommunications</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_login | - | Se connecter | Connexion | - | Se connecter | - |

</Accordion>

<div id="opened-from-push-notification-af_opened_from_push_notification" />

<Accordion title="Ouvert à partir de la notification push (af_opened_from_push_notification)">

**Description** : permet d'enregistrer les ouvertures d'app à partir d'évènements de notification push

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_opened\_from\_push\_notification | - | notification\_open | - | - | - | - |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Achat (af_purchase)">

**Description** : permet d'enregistrer les évènements d'achat (et de leur associer un revenus). Pour afficher la liste des symboles monétaires pris en charge par AppsFlyer, cliquez <Anchor target="_blank" href="https://docs.openexchangerates.org/docs/supported-currencies">ici</Anchor>. Pour signaler un événement contenant plusieurs éléments, cliquez <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">ici</Anchor>.

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-gaming-app-events#purchase-af_purchase">gaming</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-ecommerce-app-events#purchase-af_purchase">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-online-education-app-events#purchase-af_purchase">formations en ligne</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-healthcare-app-events#purchase-af_purchase">soins de santé</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-telecommunication-app-events#purchase-af_purchase">télécommunications</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_purchase | fb\_mobile\_purchase | in\_app\_purchase | Achat | ACHAT | ACHAT | transactionConfirmation |

**Paramètres type :**

Cliquez sur les paramètres pertinents pour votre entreprise pour afficher le mappage vers les SRN.

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
* [af\_purchase\_currency](/docs/in-app-events-event-structure#af_purchase_currency)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="rate-af_rate" />

<Accordion title="Taux (af_rate)">

**Description** : permet d'enregistrer les évènements de classification d'app/article. Pour signaler un événement contenant plusieurs éléments, cliquez <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">ici.</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_rate | fb\_mobile\_rate | submit\_rating | Taux | Taux | TAUX | - |

**Paramètres type :**

Cliquez sur les liens pour afficher le mappage vers les SRN.

* [af\_rating\_value](/docs/in-app-events-event-structure#af_rating_value)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_max\_rating\_value](/docs/in-app-events-event-structure#af_max_rating_value)

</Accordion>

<div id="reengage-af_re_engage" />

<Accordion title="Réengagement (af_re_engage)">

**Description** : permet d'enregistrer les évènements de réengagement des utilisateurs

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_re\_engage | - | custom\_event | - | RE\_ENGAGE | - |

**Paramètre type :**

Cliquez sur le lien pour afficher le mappage vers les SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="search-af_search" />

<Accordion title="Recherche (af_search)">

**Description** : permet d'enregistrer les évènements de recherche

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-ecommerce-app-events#search-af_search">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-flight-booking-app-events#search-af_search">réservation de vols</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-hotel-booking-app-events#search-af_search">réservation d'hôtels</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_search | fb\_mobile\_search | view\_search\_results | Recherche | - | Rechercher | viewSearch |

**Paramètres type :**

Cliquez sur les paramètres pertinents pour votre entreprise pour afficher le mappage vers les SRN.

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
* [af\_purchase\_currency](/docs/in-app-events-event-structure#af_purchase_currency)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="share-af_share" />

<Accordion title="Partage (af_share)">

**Description** : permet d'enregistrer les évènements de partage

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-gaming-app-events#share-af_share">gaming</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_share | - | partager | - | SHARE | SHARE | - |

**Paramètre type :**

Cliquez sur le lien pour afficher le mappage vers les SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="Crédits dépensés (af_spent_credits)">

**Description** : permet d'enregistrer les évènements de dépense des crédits. Pour signaler un événement contenant plusieurs éléments, cliquez <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">ici.</Anchor>

**Apparaît dans les segments suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-ride-hailing-app-events#spent-credits-af_spent_credits">transport</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_spent\_credits | fb\_mobile\_spent\_credits | spend\_virtual\_currency | SpendCredits | SPENT\_CREDITS | SPENT\_CREDITS | transactionConfirmation |

**Paramètres type :**

Cliquez sur les liens pour afficher le mappage vers les SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="start-trial-af_start_trial" />

<Accordion title="Début de l'essai (af_start_trial)">

**Description** : permet d'enregistrer le début de l'essai gratuit d'un produit

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-entertainment-app-events#start-trial-af_start_trial">gaming</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_start\_trial | Commencer l'essai | - | Commencer l'essai | START\_TRIAL | - | - |

**Paramètres type :**

Cliquez sur les liens pour afficher le mappage vers les SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

> 📘 **Note**
>
> Si vous mappez cet événement à l'événement Meta ads StartTrial et que vous souhaitez associer les revenus, utilisez le paramètre af\_price au lieu du paramètre af\_revenue.

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="Abonnement (af_subscribe)">

**Description** : permet d'enregistrer les achats d'abonnements payants

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-entertainment-app-events#subscription-af_subscribe">gaming</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_subscribe | S'abonner | - | S'abonner | - | - | S'ABONNER |

**Paramètres type :**

Cliquez sur les liens pour afficher le mappage vers les SRN.

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="Réservation de voyage (travel_booking)">

**Description** : permet d'enregistrer les évènements de réservation de voyage (et de leur associer un revenu) Pour signaler un événement contenant plusieurs éléments, cliquez <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">ici</Anchor>.

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-flight-booking-app-events#travel-booking-af_travel_booking">réservation de vols</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-hotel-booking-app-events#travel-booking-af_travel_booking">réservation d'hôtels</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_travel\_booking | fb\_mobile\_purchase | ecommerce\_purchase | Achat | RÉSERVER | ACHAT | transactionConfirmation |

**Paramètres type :**

Cliquez sur les paramètres pertinents pour votre entreprise pour afficher le mappage vers les SRN.

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
* [af\_purchase\_currency](/docs/in-app-events-event-structure#af_purchase_currency)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)
* [af\_order\_id](/docs/in-app-events-event-structure#af_order_id)

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="Tutoriel achevé (af_tutorial_completion)">

**Description** : permet d'enregistrer l'achèvement du tutoriel. Pour signaler un événement contenant plusieurs éléments, cliquez <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">ici.</Anchor>

**Apparaît dans les secteurs suivants :** <Anchor target="_blank" href="/marketers/fr/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">gaming</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">formations en ligne</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_tutorial\_completion | fb\_mobile\_tutorial\_completion | tutorial\_complete | Tutoriel complet | COMPLETE\_TUTORIAL | TUTORIAL\_COMPLETE | - |

**Paramètres type :**

Cliquez sur les liens pour afficher le mappage vers les SRN.

* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="update-af_update" />

<Accordion title="Mise à jour (af_update)">

**Description** : permet d'enregistrer les évènements de mise à jour. Pour signaler un événement contenant plusieurs éléments, cliquez <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">ici.</Anchor>

**Mappage d'événement :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_update | - | app\_update | - | Mise a jour | - |

**Paramètre type :**

Cliquez sur le lien pour afficher le mappage vers les SRN.

* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)

</Accordion>

> 📘 **Note**
>
> En plus des noms d'événements prédéfinis décrits dans cette section, <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-in-app-event-mapping#mappage-des-événements-prédéfinis">Meta ads propose des événements supplémentaires</Anchor> envoyés sans attributs.

<div id="predefined-event-parameters" />

## Paramètres d'événements prédéfinis

La section suivante fournit une liste de paramètres d'événements prédéfinis. Chaque nom d'événement comprend le mappage utilisé pour Meta ads, Google Ads, Snap, Twitter et Criteo. Vous pouvez choisir d'inclure n'importe lequel des paramètres d'événement dans un événement.

<div id="af_projected_revenue" />

<div id="h_01NEWAFNETREVENUE0001" />

<div id="note-3" />

> 📘 **Note**
>
> Vous pouvez voir les paramètres d'événement dans la colonne Valeur d'événement des <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">rapports de données brutes</Anchor> (fonctionnalité premium).

<div id="af_adrev_ad_type" />

<Accordion title="af_adrev_ad_type">

**Description** : type de publicité (par exemple, bannière ou interstitielle)

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_adrev\_ad\_type | ad\_type | - | - | - | - |

</Accordion>

<div id="af_city" />

<Accordion title="af_city">

**Description** : ville dans laquelle la course est réservée

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_city | fb\_city | - | - | - | - |

</Accordion>

<div id="af_class" />

<Accordion title="af_class">

**Description** : classe réservée pour le vol

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_class | fb\_travel\_class | travel\_class | - | - | - |

</Accordion>

<div id="af_content" />

<Accordion title="af_content">

**Description** : titre du contenu (par exemple, le nom d'une chanson ou le titre et l'épisode d'une série TV)

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_content | fb\_content | - | - | - | - |

</Accordion>

<div id="af_content_id" />

<Accordion title="af_content_id">

**Description** : ID de l'article

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_content\_id | fb\_content\_id | item\_id | item\_ids | content\_id | id |

</Accordion>

<div id="af_content_list" />

<Accordion title="af_content_list">

**Description** : liste d'identifiants de contenu

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_content\_list | - | item\_id | - | - | - |

</Accordion>

<div id="af_content_type" />

<Accordion title="af_content_type">

**Description** : catégorie de produit

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_content\_type | fb\_content\_type | item\_category | item\_category | content\_type | - |

</Accordion>

<div id="af_country" />

<Accordion title="af_country">

**Description** : pays dans lequel la course est réservée

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_country | fb\_country | - | - | - | - |

</Accordion>

<div id="af_currency" />

<Accordion title="af_currency">

**Description** : code de devise

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_currency | fb\_currency | currency\_code | devise | price\_currency | devise |

</Accordion>

<div id="af_customer_user_id" />

<Accordion title="af_customer_user_id">

**Description** : ID du client

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_customer\_user\_id | - | customer\_user\_  <br />id | - | - | cid |

</Accordion>

<div id="af_date_a" />

<Accordion title="af_date_a">

**Description** : date d'arrivée

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_date\_a | fb\_checkin\_date | start\_date | - | - | din |

</Accordion>

<div id="af_date_b" />

<Accordion title="af_date_b">

**Description** : date de départ

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_date\_b | fb\_checkout\_date | end\_date | - | - | dout |

</Accordion>

<div id="af_departing_arrival_date" />

<Accordion title="af_departing_arrival_date">

**Description** : date d'arrivée

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_departing\_arrival\_date | fb\_departing\_arrival\_date | - | - | - | - |

</Accordion>

<div id="af_departing_departure_date" />

<Accordion title="af_departing_departure_date">

**Description** : date de départ

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_departing\_departure\_date | fb\_departing\_departure\_date | - | - | - | - |

</Accordion>

<div id="af_description" />

<Accordion title="af_description">

**Description** : brève description (chaîne)

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_description | fb\_description | description | description | description | ui\_achievement |

</Accordion>

<div id="af_destination_a" />

<Accordion title="af_destination_a">

**Description** : première destination

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_destination\_a | fb\_origin\_airport | origine | - | - | - |

</Accordion>

<div id="af_destination_b" />

<Accordion title="af_destination_b">

**Description** : deuxième destination

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_destination\_b | fb\_destination\_  <br />airport | destination | - | - | - |

</Accordion>

<div id="af_destination_list" />

<Accordion title="af_destination_list">

**Description** : liste des destinations incluses dans un catalogue de destinations (par exemple, une liste de musées ou de restaurants qui se trouvent à proximité d'un hôtel)

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_destination\_list | fb\_destination\_ids | - | - | - | - |

</Accordion>

<div id="af_hotel_score" />

<Accordion title="af_hotel_score">

**Description** : note de l'hôtel selon les avis

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_hotel\_score | fb\_hotel\_score | - | - | - | - |

</Accordion>

<div id="af_level" />

<Accordion title="af_level">

**Description** : le niveau atteint par l'utilisateur

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_level | fb\_level | level\_up | level | level | ui\_level |

</Accordion>

<div id="af_max_rating_value" />

<Accordion title="af_max_rating_value">

**Description** : meilleure note sur une échelle d'évaluation (par exemple, 5 sur 5)

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_max\_rating\_value | fb\_max\_rating\_value | max\_rating | - | max\_rated\_value | - |

</Accordion>

<div id="af_num_adults" />

<Accordion title="af_num_adults">

**Description** : nombre d'adultes qui voyagent

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_num\_adults | fb\_num\_adults | - | - | - | - |

</Accordion>

<div id="af_num_children" />

<Accordion title="af_num_children">

**Description** : nombre d'enfants qui voyagent

Mappage des paramètres :

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_num\_children | fb\_num\_children | - | - | - | - |

</Accordion>

<div id="af_num_infants" />

<Accordion title="af_num_infants">

**Description** : nombre de bébés qui voyagent

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_num\_infants | fb\_num\_infants | - | - | - | - |

</Accordion>

<div id="af_order_id" />

<Accordion title="af_order_id">

**Description** : ID de la transaction

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_order\_id | fb\_order\_id | order\_id | transaction\_id | - | transaction\_id |

</Accordion>

<div id="af_payment_info_available" />

<Accordion title="af_payment_info_available">

**Description** : si les informations de paiement de l'utilisateur sont disponibles

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_payment\_info\_available | fb\_payment\_info\_available | payment\_info\_  <br />disponibles | payment\_info\_available | user\_payment\_  <br />infos | - |

</Accordion>

<div id="af_preferred_neighborhoods" />

<Accordion title="af_preferred_neighborhoods">

**Description** : zone dans laquelle se trouve l'hôtel

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_preferred\_neighborhoods | fb\_preferred\_neighborhoods | - | - | - | - |

</Accordion>

<div id="af_preferred_num_stops" />

<Accordion title="af_preferred_num_stops">

**Description** : type de vol recherché par l'utilisateur (par exemple, vol direct ou sans escale)

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_preferred\_num\_stops | fb\_preferred\_num\_stops | - | - | - | - |

</Accordion>

<div id="af_preferred_price_range" />

<Accordion title="af_preferred_price_range">

**Description** : fourchette de prix pour l'hôtel

Mappage des paramètres :

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_preferred\_price\_range | fb\_preferred\_price\_range | - | - | - | - |

</Accordion>

<div id="af_preferred_star_ratings" />

<Accordion title="af_preferred_star_ratings">

**Description** : évaluation de l'hôtel

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_preferred\_star\_ratings | fb\_preferred\_star\_ratings | - | - | - | - |

</Accordion>

<div id="af_price" />

<Accordion title="af_price">

**Description** : le prix du produit. Vous pouvez utiliser af\_price comme paramètre monétaire non considéré comme un revenu (par exemple, dans un événement « Ajouter au panier »). Ce paramètre représente le prix de chaque article. Le montant total des achats s’affiche sous le paramètre [af\_revenue](/docs/in-app-events-event-structure#af_revenue).

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_price | fb\_price | prix | prix | price\_micro | prix |

</Accordion>

<div id="af_purchase_currency" />

<Accordion title="af_purchase_currency">

**Description** : devise utilisée pour l'achat

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_purchase\_currency | fb\_purchase\_currency | - | - | - | - |

</Accordion>

<div id="af_quantity" />

<Accordion title="af_quantity">

**Description** : nombre d'articles

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_quantity | fb\_num\_items | quantité | number\_items | number\_items | quantité |

</Accordion>

<div id="af_rating_value" />

<Accordion title="af_rating_value">

**Description** : la valeur d'évaluation sélectionnée

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_rating\_value | \_valueToSum | valeur | - | price\_micro | - |

</Accordion>

<div id="af_receipt_id" />

<Accordion title="af_receipt_id">

**Description** : l'ID du reçu

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_receipt\_id | - | transaction\_id | - | - | transaction\_id |

</Accordion>

<div id="af_region" />

<Accordion title="af_region">

**Description** : région dans laquelle la course est réservée

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_region | fb\_region | - | - | - | - |

</Accordion>

<div id="af_registration_method" />

<Accordion title="af_registration_method">

**Description** : type de méthode d'inscription

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_registration\_method | fb\_registration\_method | registration\_method | sign\_up\_method | registration\_method | - |

</Accordion>

<div id="af_returning_arrival_date" />

<Accordion title="af_returning_arrival_date">

**Description** : date et heure de la fin du trajet retour

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_returning\_arrival\_date | fb\_returning\_arrival\_date | - | - | - | - |

</Accordion>

<div id="af_returning_departure_date" />

<Accordion title="af_returning_departure_date">

**Description** : date et heure de début du trajet retour

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_returning\_departure\_date | fb\_returning\_departure\_date | - | - | - | - |

</Accordion>

<div id="af_revenue" />

<Accordion title="af_revenue">

**Description** : montant total des achats. af\_revenue est considéré comme un revenu sur la plate-forme AppsFlyer. Il comptabilise également les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#revenue-events">revenus négatifs</Anchor> provenant des annulations ou des remboursements.

<div id="important" />

> 🚧 **Important !**
>
> La valeur du revenu ne doit pas contenir de séparateurs de virgule, de devises, de caractères spéciaux ou de texte. Par exemple, une valeur de revenu peut être de 1234.56. AppsFlyer fournit une valeur de revenu avec une précision allant jusqu'à cinq décimales.

Pour en savoir plus sur la manière d'utiliser le paramètre des revenus, cliquez <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#revenue-events">ici</Anchor>.

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_revenue | \_valueToSum | valeur | prix | price\_micro | ui\_revenue |

</Accordion>

<div id="af_score" />

<Accordion title="af_score">

**Description** : score associé au niveau atteint par l'utilisateur

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_score | - | - | - | score | - |

</Accordion>

<div id="af_search_string" />

<Accordion title="af_search_string">

**Description**  : terme de recherche

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_search\_string | fb\_search\_string | search\_string | search\_string | search\_string | - |

</Accordion>

<div id="af_subscription_id" />

<Accordion title="af_subscription_id">

**Description** : l'ID d'abonnement de l'utilisateur

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_subscription\_id | subscription\_id | - | - | - | - |

</Accordion>

<div id="af_success" />

<Accordion title="af_success">

**Description** : indique si l'action a été menée à bien

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_success | fb\_success | succès | succès | - | - |

</Accordion>

<div id="af_suggested_destinations" />

<Accordion title="af_suggested_destinations">

**Description** : liste des destinations suggérées

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_suggested\_destinations | fb\_suggested\_destinations | - | - | - | - |

</Accordion>

<div id="af_suggested_hotels" />

<Accordion title="af_suggested_hotels">

**Description** : liste des hôtels suggérés

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_suggested\_hotels | fb\_suggested\_hotels | - | - | - | - |

</Accordion>

<div id="af_travel_end" />

<Accordion title="af_travel_end">

**Description** : date de fin du voyage

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_travel\_end | fb\_travel\_end | - | - | - | - |

</Accordion>

<div id="af_travel_start" />

<Accordion title="af_travel_start">

**Description** : date de début du voyage

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_travel\_start | fb\_travel\_start | - | - | - | - |

</Accordion>

<div id="af_user_score" />

<Accordion title="af_user_score">

**Description** : signification relative de l'utilisateur pour l'annonceur

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_user\_score | fb\_user\_score | - | - | - | - |

</Accordion>

<div id="af_validated" />

<Accordion title="af_validated">

Description : valide un achat

**Mappage des paramètres :**

| AppsFlyer | Meta Ads | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_validated | - | VALIDÉ | succès | - | - |

</Accordion>

Voici une liste des paramètres d'événement prédéfinis qui n'incluent pas le mappage SRN :

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

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration">Configuration des postbacks d'événements in-app</Anchor>

<div data-zendesk-anchors="overview=pr%C3%A9sentation h_01H9HT8C713A4NV9WCB0FJZJ4R=pr%C3%A9sentation predefined-event-names=noms-d%C3%A9v%C3%A9nements-pr%C3%A9d%C3%A9finis h_01H9HT8C7189W1JXAR3J3KT8KV=noms-d%C3%A9v%C3%A9nements-pr%C3%A9d%C3%A9finis h_01H9HT8C71MV7V7C75MB6ESHMM=achievement-unlocked-af_achievement_unlocked h_01H9HT8C7171PB7KAC83MYBWQ8=ad-click-af_ad_click h_01H9HT8C72KJ6ZA663SH7HJ7MP=ad-view-af_ad_view h_01H9HT8C72HSM88DJG0PDV5140=add-payment-info-af_add_payment_info h_01H9HT8C72BWFSPKWDVQW926WG=add-to-cart-af_add_to_cart h_01H9HT8C7228B57XKAACPZG8NK=add-to-wishlist-af_add_to_wishlist h_01H9HT8C72DX0DXBDHRJFG19G2=complete-registration-af_complete_registration h_01H9HT8C72SPY9VQ9AD648AKZK=content-view-af_content_view h_01H9HT8C722T2VH6A9257Q7T4P=initiated-checkout-af_initiated_checkout h_01H9HT8C72F0RZ4JS9929SE465=invite-af_invite h_01H9HT8C72VFGC08Q858EX7XTN=level-achieved-af_level_achieved h_01H9HT8C72DZW77YTQ9KB0XEVG=list-view-af_list_view h_01H9HT8C720W10QEBCTPAGMRFB=login-af_login h_01H9HT8C72QC4WV10Z4JZTZM7D=opened-from-push-notification-af_opened_from_push_notification h_01H9HT8C7263J0YSX5K10R497N=purchase-af_purchase h_01H9HT8C73MPYMG8KSYE04DKDZ=rate-af_rate h_01H9HT8C734DAC6GPJE58DB5JD=reengage-af_re_engage h_01H9HT8C73YSYBK0YSDPRWDBNW=search-af_search h_01H9HT8C734GJ07V67QC9V3TVC=share-af_share h_01H9HT8C73H4VT2M0P3M1SYG88=spent-credits-af_spent_credits h_01H9HT8C73YWDCKAZPY0BVRS6F=start-trial-af_start_trial h_01H9HT8C736BF2VNRCFSJSVXWS=note h_01H9HT8C73N69S45H82NWQ5FN1=subscription-af_subscribe h_01H9HT8C73CD6HNT5GA6B4CHQ9=travel-booking-af_travel_booking h_01H9HT8C73NFDPS1P5AVXXZEX7=tutorial-completion-af_tutorial_completion h_01H9HT8C73JPH6Q9XFKA3GNYT8=update-af_update h_01H9HT8C74SGGK2FW92JH4BJPZ=note-1 predefined-event-parameters=param%C3%A8tres-d%C3%A9v%C3%A9nements-pr%C3%A9d%C3%A9finis h_01H9HT8C74N4TJZ5ZVBTKAX810=param%C3%A8tres-d%C3%A9v%C3%A9nements-pr%C3%A9d%C3%A9finis h_01H9HT8C74VQ9ZWF079V50E5HE=note-2 h_01H9HT8C74Y0BWS565DFTY75KJ=af_adrev_ad_type h_01H9HT8C742NHGXFKWSS4P07K2=af_city h_01H9HT8C7442PFZEK7QC6R0K67=af_class h_01H9HT8C7462KG3030WWZ2XGZW=af_content h_01H9HT8C74ZX07907NXFHKGJ91=af_content_id h_01H9HT8C744CMWSYHJB74JFSS5=af_content_list h_01H9HT8C74GKGG5V4X54BCAADC=af_content_type h_01H9HT8C74RD08Z9EBZTKY5KSD=af_country h_01H9HT8C75BJYK4R3WYSN4BF43=af_currency h_01H9HT8C752E2PK6QKTA2GNGH5=af_customer_user_id h_01H9HT8C75BN0A92X9BRY4A74T=af_date_a h_01H9HT8C75406KV9264ZZT9DKM=af_date_b h_01H9HT8C7526AEHJAA7FM7442E=af_departing_arrival_date h_01H9HT8C75W9X61ZH0849EPDBY=af_departing_departure_date h_01H9HT8C75VEV3C8CJBDN6X5HW=af_description h_01H9HT8C75Z8TBZEPEY9EGSR4Y=af_destination_a h_01H9HT8C751G216VB6GYTPEPE1=af_destination_b h_01H9HT8C75CVM0MHSKTK2CZ8HD=af_destination_list h_01H9HT8C75CVVDFABSTN5R4MWT=af_hotel_score h_01H9HT8C75GEMHE2NHEFK9J7NT=af_level h_01H9HT8C7505H4CMY70EMDQWSF=af_max_rating_value h_01H9HT8C75ST9XBDC3SR6XFDPB=af_num_adults h_01H9HT8C75NNZ5NP6PRPXDSKP8=af_num_children h_01H9HT8C757X70AAGNWFV0CKRY=af_num_infants h_01H9HT8C75A0HESE5FD10VD1P8=af_order_id h_01H9HT8C75B488VKY8SW9M4GG4=af_payment_info_available h_01H9HT8C75W7SRB0KF4E5FB2YF=af_preferred_neighborhoods h_01H9HT8C75GC61D1A0P6P42TMR=af_preferred_num_stops h_01H9HT8C76XRY6CD1TJEPCJJTR=af_preferred_price_range h_01H9HT8C76Y9ZQQ2X4EJT2DC14=af_preferred_star_ratings h_01H9HT8C76KCDRJKBWSM9JKFE1=af_price h_01H9HT8C767ZNWCBYC3X680PGQ=af_purchase_currency h_01H9HT8C76Y5VXBKF3TBVVJG1C=af_quantity h_01H9HT8C768WXZ126Q425PHDWX=af_rating_value h_01H9HT8C76XX9J6FZ6RWQB6B6R=af_receipt_id h_01H9HT8C760S0F7QZMFYW1BKRD=af_region h_01H9HT8C76N4S3SGES5SQ2J4AC=af_registration_method h_01H9HT8C76ZR36A4CM2PY6PJ10=af_returning_arrival_date h_01H9HT8C760JPVXYC5WH9ZSDPX=af_returning_departure_date h_01H9HT8C76PYB14WPCQKSEK69J=af_revenue h_01H9HT8C762BGPRHFX228APEHR=important- h_01H9HT8C76P55HN8K6D7PHFS2J=af_score h_01H9HT8C76TB4KNTZVD6JVPEYQ=af_search_string h_01H9HT8C762R2PJ573W8TJFJHG=af_subscription_id h_01H9HT8C76VZ6FA20K471V0EKK=af_success h_01H9HT8C76029H94AY5EHCZX6X=af_suggested_destinations h_01H9HT8C76N6C694TCPVCK4EC3=af_suggested_hotels h_01H9HT8C765EM1SAEJ67FNXZDE=af_travel_end h_01H9HT8C76YP8VEM5E6WB9NQ7T=af_travel_start h_01H9HT8C771SYQWQ8VBTPA2V2E=af_user_score h_01H9HT8C771XFSQJX42QVBNZAJ=af_validated h_01HDNZ30NH2QXSHD7B4EMFG4T5=%C3%A0-consulter-%C3%A9galement" />
