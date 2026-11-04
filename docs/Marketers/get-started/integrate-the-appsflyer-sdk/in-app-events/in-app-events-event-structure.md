---
title: In-app events—Event structure
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
  edited_at: '2026-08-12T09:04:04Z'
  id: 4410481112081
  locale: en-us
  section: In-app events
  section_id: 6551285343761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4410481112081-In-app-events-Event-structure
---
> **At a glance:** View the list of predefined event names and event parameters to record post-install in-app events (such as login, register, or in-app purchase).

<div id="overview" />

## Overview

In-app events that you want to send require your developer to implement code where applicable in your app. This article describes the predefined event names and predefined event parameters.

To help you determine what events and parameters to record, see our <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#recommended-events-by-business-vertical">articles that include examples and flows</Anchor> according to business verticals.

<div id="predefined-event-names" />

## Predefined event names

The following section provides a list of the predefined event names and the event mapping used for Meta ads, Google Ads, TikTok, Snap, X Ads, Amazon Ads, and Criteo.

Each event name also includes the typical predefined event parameters associated with that event. You can choose to include any event parameters that meet your business needs.

<div id="achievement-unlocked-af_achievement_unlocked" />

<Accordion title="Achievement unlocked (af_achievement_unlocked)">

**Description**: Used to record achievement unlocking events

**Event mapping:**

| AppsFlyer | af\_achievement\_unlocked |
| --- | --- |
| Meta ads | fb\_mobile\_achievement\_unlocked |
| Google Ads | unlock\_achievement |
| TikTok | UnlockAchievement |
| Snap | ACHIEVEMENT\_UNLOCKED |
| X Ads | ACHIEVEMENT\_UNLOCKED |
| Amazon Ads | - |
| Criteo | achievement |
| Roku Ads | UNLOCK\_ACHIEVEMENT |

**Typical parameter:**

Click the link to view the mapping to SRNs.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="ad-click-af_ad_click" />

<Accordion title="Ad click (af_ad_click)">

**Description**: Used to record ad clicks on ads displayed in the app

**Event mapping**:

| AppsFlyer | af\_ad\_click |
| --- | --- |
| Meta ads | AdClick |
| Google Ads | - |
| TikTok | InAppADClick |
| Snap | AD\_CLICK |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="ad-view-af_ad_view" />

<Accordion title="Ad view (af_ad_view)">

**Description**: Used to record ad views of ads displayed in the app

**Event mapping:**

| AppsFlyer | af\_ad\_view |
| --- | --- |
| Meta ads | AdImpression |
| Google Ads | - |
| TikTok | InAppADImpr |
| Snap | AD\_VIEW |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="Add payment info (af_add_payment_info)">

**Description**: Used to record payment info configuration status

**Appears in these verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-ride-hailing-app-events#add-payment-info-af_add_payment_info">Ride-hailing</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-flight-booking-app-events#add-payment-info-af_add_payment_info">Flight booking</Anchor>

**Event mapping**:

| AppsFlyer | af\_add\_payment\_info |
| --- | --- |
| Meta ads | fb\_mobile\_add\_payment\_info |
| Google Ads | add\_payment\_info |
| TikTok | AddPaymentInfo |
| Snap | ADD\_BILLING |
| X Ads | ADDED\_PAYMENT\_INFO |
| Amazon Ads | - |
| Criteo | ADD\_BILLING |
| Roku Ads | ADD\_PAYMENT\_INFO |

**Typical parameter:**

Click the link to view the mapping to SRNs.

* [af\_success](/docs/in-app-events-event-structure#af_success)

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="Add to cart (af_add_to_cart)">

**Description**: Used to record add to cart events of specific items. To report an event containing multiple items, click <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">here</Anchor>.

**Appears in these verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-healthcare-app-events#add-to-cart-af_add_to_cart">Healthcare</Anchor>

**Event mapping:**

| AppsFlyer | af\_add\_to\_cart |
| --- | --- |
| Meta ads | fb\_mobile\_add\_to\_cart |
| Google Ads | add\_to\_cart |
| TikTok | AddToCart |
| Snap | ADD\_CART |
| X Ads | ADD\_TO\_CART |
| Amazon Ads | ADD\_TO\_SHOPPING\_CART |
| Criteo | viewBasket |
| Roku Ads | ADD\_TO\_CART |

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Add to wishlist (af_add_to_wishlist)">

**Description**: Used to record add to wishlist events of specific items. To report an event containing multiple items, click <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">here</Anchor>.

**Appears in these verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-ecommerce-app-events#add-to-wishlist-af_add_to_wishlist">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-hotel-booking-app-events#add-to-wishlist-af_add_to_wishlist">Hotel booking</Anchor>

**Event mapping:**

| AppsFlyer | af\_add\_to\_wishlist |
| --- | --- |
| Meta ads | fb\_mobile\_add\_to\_wishlist |
| Google Ads | add\_to\_wishlist |
| TikTok | AddToWishlist |
| Snap | ADD\_TO\_WISHLIST |
| X Ads | ADD\_TO\_WISHLIST |
| Amazon Ads | - |
| Criteo | - |
| Roku Ads | ADD\_TO\_WISHLIST |

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="app-open-af_app_opened" />

<Accordion title="App open (af_app_opened)">

Roku Ads event mapping:

| AppsFlyer | af\_app\_opened |
| --- | --- |
| Roku Ads | SESSION\_START |

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Complete registration (af_complete_registration)">

**Description**: Used to record user registration methods

**Appears in these verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-gaming-app-events#complete-registration-af_complete_registration">Gaming</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-ecommerce-app-events#complete-registration-af_complete_registration">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-entertainment-app-events#complete-registration-af_complete_registration">Entertainment</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-finance-and-banking-app-events#complete-registration-af_complete_registration">Finance and banking</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-p2p-lending-app-events#complete-registration-af_complete_registration">P2P lending</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-online-education-app-events#complete-registration-af_complete_registration">Online education</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-ride-hailing-app-events#complete-registration-af_complete_registration">Ride-hailing</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-hotel-booking-app-events#complete-registration-af_complete_registration">Hotel booking</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-healthcare-app-events#complete-registration-af_complete_registration">Healthcare</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-telecommunication-app-events#complete-registration-af_complete_registration">Telecommunication</Anchor>

**Event mapping:**

| AppsFlyer | af\_complete\_registration |
| --- | --- |
| Meta ads | fb\_mobile\_complete\_registration |
| Google Ads | sign\_up |
| TikTok | Registration |
| Snap | SIGN\_UP |
| X Ads | SIGN\_UP |
| Amazon Ads | SIGN\_UP |
| Criteo | - |
| Roku Ads | COMPLETE\_REGISTRATION |

**Typical parameter:**

Click the link to view the mapping to SRNs.

* [af\_registration\_method](/docs/in-app-events-event-structure#af_registration_method)

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Content view (af_content_view)">

**Description**: Used to record content view events. To report an event containing multiple items, click <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">here</Anchor>.

**Appears in these verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-ecommerce-app-events#content-view-af_content_view">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-flight-booking-app-events#content-view-af_content_view">Flight booking</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-hotel-booking-app-events#content-view-af_content_view">Hotel booking</Anchor>

**Event mapping:**

| AppsFlyer | af\_content\_view |
| --- | --- |
| Meta ads | fb\_mobile\_content\_view |
| Google Ads | view\_item |
| TikTok | ViewContent |
| Snap | VIEW\_CONTENT |
| X Ads | CONTENT\_VIEW |
| Amazon Ads | PAGE\_VIEW |
| Criteo | viewProduct |
| Roku Ads | VIEW\_CONTENT |

**Typical parameters:**

Click the parameters that are relevant to your business needs to view the mapping to SRNs.

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

<Accordion title="Initiated checkout (af_initiated_checkout)">

**Description**: Used to record checkout events. To report an event containing multiple items, click <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">here</Anchor>.

**Appears in verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-ecommerce-app-events#initiated-checkout-af_initiated_checkout">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-hotel-booking-app-events#initiated-checkout-af_initiated_checkout">Hotel booking</Anchor>

**Event mapping:**

| AppsFlyer | af\_initiated\_checkout |
| --- | --- |
| Meta ads | fb\_mobile\_initiated\_checkout |
| Google Ads | begin\_checkout |
| TikTok | Checkout |
| Snap | START\_CHECKOUT |
| X Ads | CHECKOUT\_INITIATED |
| Amazon Ads | CHECKOUT |
| Criteo | viewBasket |
| Roku Ads | INITIATE\_CHECKOUT |

**Typical parameters:**

Click the parameters that are relevant to your business needs to view the mapping to SRNs.

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

<Accordion title="Invite (af_invite)">

**Description**: Used to record invite (social) events

**Appears in these verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-gaming-app-events#invite-af_invite">Gaming</Anchor>

**Event mapping:**

| AppsFlyer | af\_invite |
| --- | --- |
| Meta ads | - |
| Google Ads | invite |
| TikTok | - |
| Snap | INVITE |
| X Ads | INVITE |
| Amazon Ads | - |
| Criteo | - |

**Typical parameter:**

Click the link to view the mapping to SRNs.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="lead-lead" />

<Accordion title="Lead (lead)">

Roku Ads event mapping:

| AppsFlyer | lead |
| --- | --- |
| Roku Ads | LEAD |

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="Level achieved (af_level_achieved)">

**Description**: Used to record game level events

**Appears in these verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-gaming-app-events#level-achieved-af_level_achieved">Gaming</Anchor>

**Event mapping:**

| AppsFlyer | af\_level\_achieved |
| --- | --- |
| Meta ads | fb\_mobile\_level\_achieved |
| Google Ads | level\_up |
| TikTok | AchieveLevel |
| Snap | LEVEL\_COMPLETE |
| X Ads | LEVEL\_ACHIEVED |
| Amazon Ads | - |
| Criteo | userLevel |
| Roku Ads | ACHIEVE\_LEVEL |

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_level](/docs/in-app-events-event-structure#af_level)
* [af\_score](/docs/in-app-events-event-structure#af_score)

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="List view (af_list_view)">

**Description**: Used to record listings view events

**Appears in these verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-ecommerce-app-events#list-view-af_list_view">eCommerce</Anchor>

**Event mapping:**

| AppsFlyer | af\_list\_view |
| --- | --- |
| Meta ads | - |
| Google Ads | view\_item\_list |
| TikTok | - |
| Snap | LIST\_VIEW |
| X Ads | - |
| Amazon Ads | - |
| Criteo | viewListing |

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)

</Accordion>

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Description**: Used to record user login events

**Appears in these verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-gaming-app-events#login-af_login">Gaming</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-ecommerce-app-events#login-af_login">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-entertainment-app-events#login-af_login">Entertainment</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-finance-and-banking-app-events#login-af_login">Finance and banking</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-online-education-app-events#login-af_login">Online education</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-hotel-booking-app-events#login-af_login">Hotel booking</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-healthcare-app-events#login-af_login">Healthcare</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-telecommunication-app-events#login-af_login">Telecommunication</Anchor>

**Event mapping:**

| AppsFlyer | af\_login |
| --- | --- |
| Meta ads | - |
| Google Ads | login |
| TikTok | Login |
| Snap | LOGIN |
| X Ads | LOGIN |
| Amazon Ads | - |
| Criteo | - |

</Accordion>

<div id="opened-from-push-notification-af_opened_from_push_notification" />

<Accordion title="Opened from push notification (af_opened_from_push_notification)">

**Description**: Used to record app opens from push notification events

**Event mapping:**

| AppsFlyer | af\_opened\_from\_push\_notification |
| --- | --- |
| Meta ads | - |
| Google Ads | notification\_open |
| TikTok | - |
| Snap | - |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Purchase (af_purchase)">

**Description**: Used to record purchase events (and associate revenue to them).

* For a list of currency symbols supported by AppsFlyer, click <Anchor target="_blank" href="https://docs.openexchangerates.org/docs/supported-currencies">here</Anchor>.
* To report an event containing multiple items, click <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">here</Anchor>.
* To record and validate this event, see <Anchor target="_blank" href="/marketers/docs/purchase-and-subscription-validation-overview">Purchase and subscription validation</Anchor>.

**Appears in verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-gaming-app-events#purchase-af_purchase">Gaming</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-ecommerce-app-events#purchase-af_purchase">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-online-education-app-events#purchase-af_purchase">Online education</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-healthcare-app-events#purchase-af_purchase">Healthcare</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-telecommunication-app-events#purchase-af_purchase">Telecommunication</Anchor>

**Event mapping:**

| AppsFlyer | af\_purchase |
| --- | --- |
| Meta ads | fb\_mobile\_purchase |
| Google Ads | in\_app\_purchase |
| TikTok | Purchase |
| Snap | PURCHASE |
| X Ads | PURCHASE |
| Amazon Ads | OFF\_AMAZON\_PURCHASES |
| Criteo | transactionConfirmation |
| Roku Ads | PURCHASE |

**Typical parameters:**

Click the parameters that are relevant to your business needs to view the mapping to SRNs.

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

**Description**: Used to record app/item rating events. To report an event containing multiple items, click <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">here</Anchor>.

**Event mapping:**

| AppsFlyer | af\_rate |
| --- | --- |
| Meta ads | fb\_mobile\_rate |
| Google Ads | submit\_rating |
| TikTok | Rate |
| Snap | RATE |
| X Ads | RATED |
| Amazon Ads | - |
| Criteo | - |

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_rating\_value](/docs/in-app-events-event-structure#af_rating_value)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_max\_rating\_value](/docs/in-app-events-event-structure#af_max_rating_value)

</Accordion>

<div id="reengage-af_re_engage" />

<Accordion title="Re-engage (af_re_engage)">

**Description**: Used to record user re-engagement events

**Event mapping:**

| AppsFlyer | af\_re\_engage |
| --- | --- |
| Meta ads | - |
| Google Ads | custom\_event |
| Snap | - |
| X Ads | RE\_ENGAGE |
| Amazon Ads | - |
| Criteo | - |

**Typical parameter:**

Click the link to view the mapping to SRNs.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="search-af_search" />

<Accordion title="Search (af_search)">

**Description**: Used to record search events

**Appears in these verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-ecommerce-app-events#search-af_search">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-flight-booking-app-events#search-af_search">Flight booking</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-hotel-booking-app-events#search-af_search">Hotel booking</Anchor>

**Event mapping:**

| AppsFlyer | af\_search |
| --- | --- |
| Meta ads | fb\_mobile\_search |
| Google Ads | view\_search\_results |
| TikTok | Search |
| Snap | SEARCH |
| X Ads | SEARCH |
| Amazon Ads | SEARCH |
| Criteo | viewSearch |
| Roku Ads | SEARCH |

**Typical parameters:**

Click the parameters that are relevant to your business needs to view the mapping to SRNs.

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

<Accordion title="Share (af_share)">

**Description**: Used to record sharing events

**Appears in these verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-gaming-app-events#share-af_share">Gaming</Anchor>

**Event mapping:**

| AppsFlyer | af\_share |
| --- | --- |
| Meta ads | - |
| Google Ads | share |
| TikTok | - |
| Snap | SHARE |
| X Ads | SHARE |
| Amazon Ads | - |
| Criteo | - |

**Typical parameter:**

Click the link to view the mapping to SRNs.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="Spent credits (af_spent_credits)">

**Description**: Used to record credit spend events. To report an event containing multiple items, click <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">here</Anchor>.

**Appears in verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-ride-hailing-app-events#spent-credits-af_spent_credits">Ride-hailing</Anchor>

**Event mapping:**

| AppsFlyer | af\_spent\_credits |
| --- | --- |
| Meta ads | fb\_mobile\_spent\_credits |
| Google Ads | spend\_virtual\_currency |
| TikTok | SpendCredits |
| Snap | SPENT\_CREDITS |
| X Ads | SPENT\_CREDITS |
| Amazon Ads | - |
| Criteo | transactionConfirmation |

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="start-trial-af_start_trial" />

<Accordion title="Start trial (af_start_trial)">

**Description**: Used to record the start of a free trial of a product. To record and validate this event, see <Anchor target="_blank" href="/marketers/docs/purchase-and-subscription-validation-overview">Purchase and subscription validation</Anchor>.

**Appears in these verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-entertainment-app-events#start-trial-af_start_trial">Entertainment</Anchor>

**Event mapping:**

| AppsFlyer | af\_start\_trial |
| --- | --- |
| Meta ads | StartTrial |
| Google Ads | - |
| TikTok | StartTrial |
| Snap | START\_TRIAL |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |
| Roku Ads | START\_TRIAL |

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

<div id="note" />

> 📘 **Note**
>
> If you are mapping this event to the Meta ads StartTrial event and want to associate revenue, use the af\_price parameter instead of the af\_revenue parameter.

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="Subscription (af_subscribe)">

**Description**: Used to record paid subscription purchases. To record and validate this event, see <Anchor target="_blank" href="/marketers/docs/purchase-and-subscription-validation-overview">Purchase and subscription validation</Anchor>.

**Appears in these verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-entertainment-app-events#subscription-af_subscribe">Entertainment</Anchor>

**Event mapping:**

| AppsFlyer | af\_subscribe |
| --- | --- |
| Meta ads | Subscribe |
| Google Ads | - |
| TikTok | Subscribe |
| Snap | SUBSCRIBE |
| X Ads | - |
| Amazon Ads | SUBSCRIBE |
| Criteo | SUBSCRIBE |
| Roku Ads | SUBSCRIBE |

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="Travel booking (af_travel_booking)">

**Description**: Used to record travel booking events (and associate revenue to them). To report an event containing multiple items, click <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">here</Anchor>.

**Appears in these verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-flight-booking-app-events#travel-booking-af_travel_booking">Flight booking</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-hotel-booking-app-events#travel-booking-af_travel_booking">Hotel booking</Anchor>

**Event mapping:**

| AppsFlyer | af\_travel\_booking |
| --- | --- |
| Meta ads | fb\_mobile\_purchase |
| Google Ads | ecommerce\_purchase |
| TikTok | Purchase |
| Snap | RESERVE |
| X Ads | PURCHASE |
| Amazon Ads | - |
| Criteo | transactionConfirmation |

**Typical parameters:**

Click the parameters that are relevant to your business needs to view the mapping to SRNs.

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

<Accordion title="Tutorial completion (af_tutorial_completion)">

**Description**: Used to record tutorial completions. To report an event containing multiple items, click <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">here</Anchor>.

**Appears in these verticals:** <Anchor target="_blank" href="/marketers/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">Gaming</Anchor>, <Anchor target="_blank" href="/marketers/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">Online education</Anchor>

**Event mapping:**

| AppsFlyer | af\_tutorial\_completion |
| --- | --- |
| Meta ads | fb\_mobile\_tutorial\_completion |
| Google Ads | tutorial\_complete |
| TikTok | CompleteTutorial |
| Snap | COMPLETE\_TUTORIAL |
| X Ads | TUTORIAL\_COMPLETE |
| Amazon Ads | - |
| Criteo | - |

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="update-af_update" />

<Accordion title="Update (af_update)">

**Description**: Used to record update events. To report an event containing multiple items, click <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">here</Anchor>.

**Event mapping:**

| AppsFlyer | af\_update |
| --- | --- |
| Meta ads | - |
| Google Ads | app\_update |
| Snap | - |
| X Ads | UPDATE |
| Amazon Ads | - |
| Criteo | - |

**Typical parameter:**

Click the link to view the mapping to SRNs.

* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)

</Accordion>

<div id="note-1" />

> 📘 **Note**
>
> In addition to the predefined event names described in this section, <Anchor target="_blank" href="/marketers/docs/meta-ads-in-app-event-mapping#predefined-event-mapping">Meta ads offers additional events</Anchor> that are sent without attributes.

<div id="predefined-event-parameters" />

## Predefined event parameters

The following section provides a list of the predefined event parameters. Each event parameter includes the mapping used for Meta ads, Google Ads, Snap, X Ads, and Criteo. You can choose to include any of the event parameters in an event.

<div id="note-2" />

> 📘 **Note**
>
> You can see the event parameters in the Event Value column in <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-overview">raw data reports</Anchor> (premium feature).

<div id="af_adrev_ad_type" />

<Accordion title="af_adrev_ad_type">

**Description**: Type of ad (for example, banner or interstitial)

**Parameter mapping:**

| AppsFlyer | af\_adrev\_ad\_type |
| --- | --- |
| Meta ads | ad\_type |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_city" />

<Accordion title="af_city">

**Description**: City where the ride is booked

**Parameter mapping:**

| AppsFlyer | af\_city |
| --- | --- |
| Meta ads | fb\_city |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | flight\_city |
| Criteo | - |

</Accordion>

<div id="af_class" />

<Accordion title="af_class">

**Description**: Travel class booked for the flight

**Parameter mapping:**

| AppsFlyer | af\_class |
| --- | --- |
| Meta ads | fb\_travel\_class |
| Google Ads | travel\_class |
| Snap | - |
| X Ads | - |
| TikTok | flight\_class |
| Criteo | - |

</Accordion>

<div id="af_content" />

<Accordion title="af_content">

**Description**: Title of the content (for example, name of a song or the title and episode of a TV show)

**Parameter mapping:**

| AppsFlyer | af\_content |
| --- | --- |
| Meta ads | fb\_content |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_content_id" />

<Accordion title="af_content_id">

**Description**: ID of the item

**Note:** Snapchat predefined events `af_content_list` and `af_content_id` share the same event parameter. When both events are recorded simultaneously, only the `af_content_list` event is sent to Snapchat.

**Parameter mapping:**

| AppsFlyer | af\_content\_id |
| --- | --- |
| Meta ads | fb\_content\_id |
| Google Ads | item\_id |
| Snap | item\_ids |
| X Ads | content\_id |
| TikTok | content\_id |
| Criteo | id |

</Accordion>

<div id="af_content_list" />

<Accordion title="af_content_list">

**Description**: List of content IDs

**Note:** When you use `af_content_list`, AppsFlyer treats the entire list as a single value. AppsFlyer audience segmentation tools can’t filter for individual content IDs within the list. For example, if  `af_content_list` is `["ID1","ID2","ID3"]`, the audience tool can’t isolate or match `ID1` alone.

**Parameter mapping:**

| AppsFlyer | af\_content\_list |
| --- | --- |
| Meta ads | fb\_content\_id |
| Google Ads | item\_id |
| Snap | item\_ids |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_content_type" />

<Accordion title="af_content_type">

**Description**: Product category

**Parameter mapping:**

| AppsFlyer | af\_content\_type |
| --- | --- |
| Meta ads | fb\_content\_type |
| Google Ads | item\_category |
| Snap | item\_category |
| X Ads | content\_type |
| TikTok | content\_type |
| Criteo | - |

</Accordion>

<div id="af_country" />

<Accordion title="af_country">

**Description**: Country where the ride is booked

**Parameter mapping:**

| AppsFlyer | af\_country |
| --- | --- |
| Meta ads | fb\_country |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | flight\_country |
| Criteo | - |

</Accordion>

<div id="af_currency" />

<Accordion title="af_currency">

**Description**: Currency code

**Parameter mapping:**

| AppsFlyer | af\_currency |
| --- | --- |
| Meta ads | fb\_currency |
| Google Ads | currency\_code |
| Snap | currency |
| X Ads | price\_currency |
| TikTok | currency |
| Amazon Ads | currency |
| Criteo | currency |

</Accordion>

<div id="af_customer_user_id" />

<Accordion title="af_customer_user_id">

**Description**: ID of the customer

**Parameter mapping:**

| AppsFlyer | af\_customer\_user\_id |
| --- | --- |
| Meta ads | - |
| Google Ads | customer\_user\_id |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | cid |

</Accordion>

<div id="af_date_a" />

<Accordion title="af_date_a">

**Description**: Check-in date

**Parameter mapping:**

| AppsFlyer | af\_date\_a |
| --- | --- |
| Meta ads | fb\_checkin\_date |
| Google Ads | start\_date |
| Snap | - |
| X Ads | - |
| TikTok | checkin\_date |
| Criteo | din |

</Accordion>

<div id="af_date_b" />

<Accordion title="af_date_b">

**Description**: Check-out date

**Parameter mapping:**

| AppsFlyer | af\_date\_b |
| --- | --- |
| Meta ads | fb\_checkout\_date |
| Google Ads | end\_date |
| Snap | - |
| X Ads | - |
| TikTok | checkout\_date |
| Criteo | dout |

</Accordion>

<div id="af_departing_arrival_date" />

<Accordion title="af_departing_arrival_date">

**Description**: Arrival date

**Parameter mapping:**

| AppsFlyer | af\_departing\_arrival\_date |
| --- | --- |
| Meta ads | fb\_departing\_arrival\_date |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_departing_departure_date" />

<Accordion title="af_departing_departure_date">

**Description**: Departure date

**Parameter mapping:**

| AppsFlyer | af\_departing\_ departure\_date |
| --- | --- |
| Meta ads | fb\_departing\_ departure\_date |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | departing\_date |
| Criteo | - |

</Accordion>

<div id="af_description" />

<Accordion title="af_description">

**Description**: Short description (string)

**Parameter mapping:**

| AppsFlyer | af\_description |
| --- | --- |
| Meta ads | fb\_description |
| Google Ads | description |
| Snap | description |
| X Ads | description |
| TikTok | description |
| Criteo | ui\_achievement |

</Accordion>

<div id="af_destination_a" />

<Accordion title="af_destination_a">

**Description**: First destination

**Parameter mapping:**

| AppsFlyer | af\_destination\_a |
| --- | --- |
| Meta ads | fb\_origin\_airport |
| Google Ads | origin |
| Snap | - |
| X Ads | - |
| TikTok | departing\_airport |
| Criteo | - |

</Accordion>

<div id="af_destination_b" />

<Accordion title="af_destination_b">

**Description**: Second destination

**Parameter mapping:**

| AppsFlyer | af\_destination\_b |
| --- | --- |
| Meta ads | fb\_destination\_airport |
| Google Ads | destination |
| Snap | - |
| X Ads | - |
| TikTok | destination\_airport |
| Criteo | - |

</Accordion>

<div id="af_destination_list" />

<Accordion title="af_destination_list">

**Description**: List of destinations that are included in a destination catalog (for example, a list of museums or restaurants that are near a hotel)

**Parameter mapping:**

| AppsFlyer | af\_destination\_list |
| --- | --- |
| Meta ads | fb\_destination\_ids |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_hotel_score" />

<Accordion title="af_hotel_score">

**Description**: Hotel score by reviews

**Parameter mapping:**

| AppsFlyer | af\_hotel\_score |
| --- | --- |
| Meta ads | fb\_hotel\_score |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_level" />

<Accordion title="af_level">

**Description**: Level the user achieved

**Parameter mapping:**

| AppsFlyer | af\_level |
| --- | --- |
| Meta ads | fb\_level |
| Google Ads | level\_up |
| Snap | level |
| X Ads | level |
| TikTok | - |
| Criteo | ui\_level |

</Accordion>

<div id="af_max_rating_value" />

<Accordion title="af_max_rating_value">

**Description**: Upper end of a rating scale (for example, 5 out of 5)

**Parameter mapping:**

| AppsFlyer | af\_max\_rating\_value |
| --- | --- |
| Meta ads | fb\_max\_rating\_value |
| Google Ads | max\_rating |
| Snap | - |
| X Ads | max\_rated\_value |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="h_01NEWAFNETREVENUE0001" />

<Accordion title="af_net_revenue">

**Description**: Net revenue reported for the event. The value represents net revenue according to your own business logic; AppsFlyer does not prescribe how it's calculated and aggregates the value you send. Common examples: revenue after app store fees and/or taxes, gross margin, or revenue after banking or service fees (ecommerce, finance, and so on). Used for the Net revenue metrics (Net revenue, Net ROI, Net ROAS, Net ARPU, Net profit) in <Anchor target="_blank" href="/marketers/docs/my-dashboards">My Dashboards</Anchor>.

The value is in the transaction currency, expressed by af\_currency (default USD). Same formatting rules as af\_revenue: no comma separators, currency symbols, special characters, or text (for example, 1234.56), up to five decimal places.

**Note:** There is no predefined SDK constant for this parameter, so send it as a custom parameter with the key af\_net\_revenue.

<div id="note-3" />

> 📘 **Note**
>
> For apps with <Anchor target="_blank" href="/marketers/docs/about-roi360-store-revenue">ROI360 store revenue</Anchor> enabled, AppsFlyer populates af\_net\_revenue automatically on the in-app purchase and subscription events it records, calculated as gross revenue minus app store fees and taxes (Net = Gross - store fees - taxes).

</Accordion>

<div id="af_num_adults" />

<Accordion title="af_num_adults">

**Description**: Number of adults traveling

**Parameter mapping:**

| AppsFlyer | af\_num\_adults |
| --- | --- |
| Meta ads | fb\_num\_adults |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | num\_people |
| Criteo | - |

</Accordion>

<div id="af_num_children" />

<Accordion title="af_num_children">

**Description**: Number of children traveling

Parameter mapping:

| AppsFlyer | af\_num\_children |
| --- | --- |
| Meta ads | fb\_num\_children |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | num\_children |
| Criteo | - |

</Accordion>

<div id="af_num_infants" />

<Accordion title="af_num_infants">

**Description**: Number of infants traveling

**Parameter mapping:**

| AppsFlyer | af\_num\_infants |
| --- | --- |
| Meta ads | fb\_num\_infants |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_order_id" />

<Accordion title="af_order_id">

**Description**: ID of the transaction

**Parameter mapping:**

| AppsFlyer | af\_order\_id |
| --- | --- |
| Meta ads | fb\_order\_id |
| Google Ads | order\_id |
| Snap | transaction\_id |
| X Ads | - |
| TikTok | order\_id |
| Criteo | transaction\_id |

</Accordion>

<div id="af_payment_info_available" />

<Accordion title="af_payment_info_available">

**Description**: Whether the user's payment information is available

**Parameter mapping:**

| AppsFlyer | af\_payment\_info\_available |
| --- | --- |
| Meta ads | fb\_payment\_info\_ available |
| Google Ads | payment\_info\_available |
| Snap | payment\_info\_available |
| X Ads | user\_payment\_info |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_neighborhoods" />

<Accordion title="af_preferred_neighborhoods">

**Description**: Area in which the hotel is located

**Parameter mapping:**

| AppsFlyer | af\_preferred\_neighborhoods |
| --- | --- |
| Meta ads | fb\_preferred\_neighborhoods |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_num_stops" />

<Accordion title="af_preferred_num_stops">

**Description**: Number of stops user is looking for (for example, nonstop or direct flight)

**Parameter mapping:**

| AppsFlyer | af\_preferred\_num\_stops |
| --- | --- |
| Meta ads | fb\_preferred\_num\_stops |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_price_range" />

<Accordion title="af_preferred_price_range">

**Description**: Preferred price range of hotel

Parameter mapping:

| AppsFlyer | af\_preferred\_price\_range |
| --- | --- |
| Meta ads | fb\_preferred\_price\_range |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_star_ratings" />

<Accordion title="af_preferred_star_ratings">

**Description**: Preferred star rating of the hotel

**Parameter mapping:**

| AppsFlyer | af\_preferred\_star\_ratings |
| --- | --- |
| Meta ads | fb\_preferred\_star\_ratings |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_price" />

<Accordion title="af_price">

**Description**: Price of the product. You can use af\_price as a monetary parameter that is not counted as revenue (such as an Add to cart event). This parameter refers to the individual item price. The total amount of all purchases displays under the [af\_revenue](/docs/in-app-events-event-structure#af_revenue) parameter.

**Parameter mapping:**

| AppsFlyer | af\_price |
| --- | --- |
| Meta ads | fb\_price |
| Google Ads | price |
| Snap | price |
| X Ads | price\_micro |
| TikTok | price |
| Criteo | price |

</Accordion>

<div id="af_projected_revenue" />

<Accordion title="af_projected_revenue">

The estimated revenue an advertiser expects from a user based on their early interactions or behaviors before the actual revenue is realized.

</Accordion>

<div id="af_quantity" />

<Accordion title="af_quantity">

**Description**: Number of items

**Parameter mapping:**

| AppsFlyer | af\_quantity |
| --- | --- |
| Meta ads | fb\_num\_items |
| Google Ads | quantity |
| Snap | number\_items |
| X Ads | number\_items |
| TikTok | quantity |
| Criteo | quantity |

</Accordion>

<div id="af_rating_value" />

<Accordion title="af_rating_value">

**Description**: Selected rating value

**Parameter mapping:**

| AppsFlyer | af\_rating\_value |
| --- | --- |
| Meta ads | \_valueToSum |
| Google Ads | value |
| Snap | - |
| X Ads | price\_micro |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_receipt_id" />

<Accordion title="af_receipt_id">

**Description**: ID of the receipt

**Parameter mapping:**

| AppsFlyer | af\_receipt\_id |
| --- | --- |
| Meta ads | - |
| Google Ads | transaction\_id |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | transaction\_id |

</Accordion>

<div id="af_region" />

<Accordion title="af_region">

**Description**: Region where the ride is booked

**Parameter mapping:**

| AppsFlyer | af\_region |
| --- | --- |
| Meta ads | fb\_region |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | flight\_region |
| Criteo | - |

</Accordion>

<div id="af_registration_method" />

<Accordion title="af_registration_method">

**Description**: Type of signup method

**Parameter mapping:**

| AppsFlyer | af\_registration\_method |
| --- | --- |
| Meta ads | fb\_registration\_method |
| Google Ads | registration\_method |
| Snap | sign\_up\_method |
| X Ads | registration\_method |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_returning_arrival_date" />

<Accordion title="af_returning_arrival_date">

**Description**: Date and time the return journey finishes

**Parameter mapping:**

| AppsFlyer | af\_returning\_arrival\_ date |
| --- | --- |
| Meta ads | fb\_returning\_arrival\_ date |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_returning_departure_date" />

<Accordion title="af_returning_departure_date">

**Description**:  Date and time the return journey starts

**Parameter mapping:**

| AppsFlyer | af\_returning\_departure\_date |
| --- | --- |
| Meta ads | fb\_returning\_departure\_date |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | returning\_date |
| Criteo | - |

</Accordion>

<div id="af_revenue" />

<Accordion title="af_revenue">

**Description**: Total amount of purchases. af\_revenue is counted as revenue in the AppsFlyer platform. It also counts <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#revenue-in-in-app-events">negative revenue</Anchor>, from cancellations or refunds.

<div id="important" />

> 🚧 **Important!**
>
> The revenue value should not contain comma separators, currency, special characters, or text. For example, a revenue value should be, 1234.56. AppsFlyer provides revenue value with an accuracy of up to five decimal places.

To learn more about how to use the revenue parameter, click <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#revenue-in-in-app-events">here</Anchor>.

**Net revenue:** To report net revenue alongside gross revenue, send [af\_net\_revenue](/docs/in-app-events-event-structure#h_01NEWAFNETREVENUE0001) as a custom event parameter. You define what net means for your business (for example, revenue after store fees and/or taxes, gross margin, or revenue after service fees). Apps with ROI360 store revenue enabled have it populated automatically on the purchase and subscription events it records, as gross minus app store fees and taxes.

**Parameter mapping:**

| AppsFlyer | af\_revenue |
| --- | --- |
| Meta ads | \_valueToSum |
| Google Ads | value |
| Snap | price |
| X Ads | price\_micro |
| TikTok | value |
| Amazon Ads | eventValue |
| Criteo | ui\_revenue |

</Accordion>

<div id="af_score" />

<Accordion title="af_score">

**Description**: Score associated with the user's achievement

**Parameter mapping:**

| AppsFlyer | af\_score |
| --- | --- |
| Meta ads | - |
| Google Ads | - |
| Snap | - |
| X Ads | score |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_search_string" />

<Accordion title="af_search_string">

**Description**: Search term

**Parameter mapping:**

| AppsFlyer | af\_search\_string |
| --- | --- |
| Meta ads | fb\_search\_string |
| Google Ads | search\_string |
| Snap | search\_string |
| X Ads | search\_string |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_subscription_id" />

<Accordion title="af_subscription_id">

**Description**: Subscription ID for the user

**Parameter mapping:**

| AppsFlyer | af\_subscription\_id |
| --- | --- |
| Meta ads | subscription\_id |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_success" />

<Accordion title="af_success">

**Description**: Whether completion of action was successful

**Parameter mapping:**

| AppsFlyer | af\_success |
| --- | --- |
| Meta ads | fb\_success |
| Google Ads | success |
| Snap | success |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_suggested_destinations" />

<Accordion title="af_suggested_destinations">

**Description**: List of suggested destinations

**Parameter mapping:**

| AppsFlyer | af\_suggested\_ destinations |
| --- | --- |
| Meta ads | fb\_suggested\_ destinations |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_suggested_hotels" />

<Accordion title="af_suggested_hotels">

**Description**: List of suggested hotels

**Parameter mapping:**

| AppsFlyer | af\_suggested\_ hotels |
| --- | --- |
| Meta ads | fb\_suggested\_hotels |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_travel_end" />

<Accordion title="af_travel_end">

**Description**: End date of trip

**Parameter mapping:**

| AppsFlyer | af\_travel\_end |
| --- | --- |
| Meta ads | fb\_travel\_end |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_travel_start" />

<Accordion title="af_travel_start">

**Description**: Start date of trip

**Parameter mapping:**

| AppsFlyer | af\_travel\_start |
| --- | --- |
| Meta ads | fb\_travel\_start |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_user_score" />

<Accordion title="af_user_score">

**Description**: Relative significance of user to advertiser

**Parameter mapping:**

| AppsFlyer | af\_user\_score |
| --- | --- |
| Meta ads | fb\_user\_score |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_validated" />

<Accordion title="af_validated">

**Description**: Validates a purchase

**Parameter mapping:**

| AppsFlyer | af\_validated |
| --- | --- |
| Meta ads | - |
| Google Ads | validated |
| Snap | success |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

The following is a list of predefined event parameters that do not include SRN mapping:

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

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration">In-app event postback configuration</Anchor>

<div data-zendesk-anchors="h_01H9HT8C713A4NV9WCB0FJZJ4R=overview h_01H9HT8C7189W1JXAR3J3KT8KV=predefined-event-names h_01H9HT8C71MV7V7C75MB6ESHMM=achievement-unlocked-af_achievement_unlocked h_01H9HT8C7171PB7KAC83MYBWQ8=ad-click-af_ad_click h_01H9HT8C72KJ6ZA663SH7HJ7MP=ad-view-af_ad_view h_01H9HT8C72HSM88DJG0PDV5140=add-payment-info-af_add_payment_info h_01H9HT8C72BWFSPKWDVQW926WG=add-to-cart-af_add_to_cart h_01H9HT8C7228B57XKAACPZG8NK=add-to-wishlist-af_add_to_wishlist h_01K0PJ4C3HP9DMJT1DFZ848WF0=app-open-af_app_opened h_01H9HT8C72DX0DXBDHRJFG19G2=complete-registration-af_complete_registration h_01H9HT8C72SPY9VQ9AD648AKZK=content-view-af_content_view h_01H9HT8C722T2VH6A9257Q7T4P=initiated-checkout-af_initiated_checkout h_01H9HT8C72F0RZ4JS9929SE465=invite-af_invite h_01K0PJ4C3H72BDTRH7WAYW4V7S=lead-lead h_01H9HT8C72VFGC08Q858EX7XTN=level-achieved-af_level_achieved h_01H9HT8C72DZW77YTQ9KB0XEVG=list-view-af_list_view h_01H9HT8C720W10QEBCTPAGMRFB=login-af_login h_01H9HT8C72QC4WV10Z4JZTZM7D=opened-from-push-notification-af_opened_from_push_notification h_01H9HT8C7263J0YSX5K10R497N=purchase-af_purchase h_01H9HT8C73MPYMG8KSYE04DKDZ=rate-af_rate h_01H9HT8C734DAC6GPJE58DB5JD=reengage-af_re_engage h_01H9HT8C73YSYBK0YSDPRWDBNW=search-af_search h_01H9HT8C734GJ07V67QC9V3TVC=share-af_share h_01H9HT8C73H4VT2M0P3M1SYG88=spent-credits-af_spent_credits h_01H9HT8C73YWDCKAZPY0BVRS6F=start-trial-af_start_trial h_01H9HT8C736BF2VNRCFSJSVXWS=note h_01H9HT8C73N69S45H82NWQ5FN1=subscription-af_subscribe h_01H9HT8C73CD6HNT5GA6B4CHQ9=travel-booking-af_travel_booking h_01H9HT8C73NFDPS1P5AVXXZEX7=tutorial-completion-af_tutorial_completion h_01H9HT8C73JPH6Q9XFKA3GNYT8=update-af_update h_01H9HT8C74SGGK2FW92JH4BJPZ=note-1 h_01H9HT8C74N4TJZ5ZVBTKAX810=predefined-event-parameters h_01H9HT8C74VQ9ZWF079V50E5HE=note-2 h_01H9HT8C74Y0BWS565DFTY75KJ=af_adrev_ad_type h_01H9HT8C742NHGXFKWSS4P07K2=af_city h_01H9HT8C7442PFZEK7QC6R0K67=af_class h_01H9HT8C7462KG3030WWZ2XGZW=af_content h_01H9HT8C74ZX07907NXFHKGJ91=af_content_id h_01H9HT8C744CMWSYHJB74JFSS5=af_content_list h_01H9HT8C74GKGG5V4X54BCAADC=af_content_type h_01H9HT8C74RD08Z9EBZTKY5KSD=af_country h_01H9HT8C75BJYK4R3WYSN4BF43=af_currency h_01H9HT8C752E2PK6QKTA2GNGH5=af_customer_user_id h_01H9HT8C75BN0A92X9BRY4A74T=af_date_a h_01H9HT8C75406KV9264ZZT9DKM=af_date_b h_01H9HT8C7526AEHJAA7FM7442E=af_departing_arrival_date h_01H9HT8C75W9X61ZH0849EPDBY=af_departing_departure_date h_01H9HT8C75VEV3C8CJBDN6X5HW=af_description h_01H9HT8C75Z8TBZEPEY9EGSR4Y=af_destination_a h_01H9HT8C751G216VB6GYTPEPE1=af_destination_b h_01H9HT8C75CVM0MHSKTK2CZ8HD=af_destination_list h_01H9HT8C75CVVDFABSTN5R4MWT=af_hotel_score h_01H9HT8C75GEMHE2NHEFK9J7NT=af_level h_01H9HT8C7505H4CMY70EMDQWSF=af_max_rating_value af_net_revenue=h_01NEWAFNETREVENUE0001 h_01NEWAFNETREVENUENOTE0001=note-3 h_01H9HT8C75ST9XBDC3SR6XFDPB=af_num_adults h_01H9HT8C75NNZ5NP6PRPXDSKP8=af_num_children h_01H9HT8C757X70AAGNWFV0CKRY=af_num_infants h_01H9HT8C75A0HESE5FD10VD1P8=af_order_id h_01H9HT8C75B488VKY8SW9M4GG4=af_payment_info_available h_01H9HT8C75W7SRB0KF4E5FB2YF=af_preferred_neighborhoods h_01H9HT8C75GC61D1A0P6P42TMR=af_preferred_num_stops h_01H9HT8C76XRY6CD1TJEPCJJTR=af_preferred_price_range h_01H9HT8C76Y9ZQQ2X4EJT2DC14=af_preferred_star_ratings h_01H9HT8C76KCDRJKBWSM9JKFE1=af_price 01J9XHWVFHXPN6N3EZF1P8XWYM=af_projected_revenue h_01H9HT8C76Y5VXBKF3TBVVJG1C=af_quantity h_01H9HT8C768WXZ126Q425PHDWX=af_rating_value h_01H9HT8C76XX9J6FZ6RWQB6B6R=af_receipt_id h_01H9HT8C760S0F7QZMFYW1BKRD=af_region h_01H9HT8C76N4S3SGES5SQ2J4AC=af_registration_method h_01H9HT8C76ZR36A4CM2PY6PJ10=af_returning_arrival_date h_01H9HT8C760JPVXYC5WH9ZSDPX=af_returning_departure_date h_01H9HT8C76PYB14WPCQKSEK69J=af_revenue h_01H9HT8C762BGPRHFX228APEHR=important h_01H9HT8C76P55HN8K6D7PHFS2J=af_score h_01H9HT8C76TB4KNTZVD6JVPEYQ=af_search_string h_01H9HT8C762R2PJ573W8TJFJHG=af_subscription_id h_01H9HT8C76VZ6FA20K471V0EKK=af_success h_01H9HT8C76029H94AY5EHCZX6X=af_suggested_destinations h_01H9HT8C76N6C694TCPVCK4EC3=af_suggested_hotels h_01H9HT8C765EM1SAEJ67FNXZDE=af_travel_end h_01H9HT8C76YP8VEM5E6WB9NQ7T=af_travel_start h_01H9HT8C771SYQWQ8VBTPA2V2E=af_user_score h_01H9HT8C771XFSQJX42QVBNZAJ=af_validated h_01HDNZ30NH2QXSHD7B4EMFG4T5=see-also" />
