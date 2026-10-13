---
title: "In-app events—Event structure"
excerpt: "View the list of predefined event names and event parameters to record post-install in-app events such as login, register, or in-app purchase."
x-zendesk:
  id: 4410481112081
  url: https://support.appsflyer.com/hc/en-us/articles/4410481112081-In-app-events-Event-structure
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: In-app events
  section_id: 6551285343761
  position: 2
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 27439133508369
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [iOS, Android, In-App Events, In-App, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-11-09T10:09:16Z'
  edited_at: '2026-08-12T09:04:04Z'
---
**At a glance:** View the list of predefined event names and event parameters to record post-install in-app events (such as login, register, or in-app purchase).

## Overview

In-app events that you want to send require your developer to implement code where applicable in your app. This article describes the predefined event names and predefined event parameters.

To help you determine what events and parameters to record, see our [articles that include examples and flows](/docs/in-app-events-overview#recommended-events-by-business-vertical) according to business verticals.

## Predefined event names

The following section provides a list of the predefined event names and the event mapping used for Meta ads, Google Ads, TikTok, Snap, X Ads, Amazon Ads, and Criteo.

Each event name also includes the typical predefined event parameters associated with that event. You can choose to include any event parameters that meet your business needs.

#### Achievement unlocked (af\_achievement\_unlocked)

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

#### Ad click (af\_ad\_click)

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

#### Ad view (af\_ad\_view)

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

#### Add payment info (af\_add\_payment\_info)

**Description**: Used to record payment info configuration status

**Appears in these verticals:** [Ride-hailing](/docs/recommended-ride-hailing-app-events#add-payment-info-af_add_payment_info), [Flight booking](/docs/recommended-flight-booking-app-events#add-payment-info-af_add_payment_info)

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

#### Add to cart (af\_add\_to\_cart)

**Description**: Used to record add to cart events of specific items. To report an event containing multiple items, click [here](/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction).

**Appears in these verticals:** [eCommerce](/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart), [Healthcare](/docs/recommended-healthcare-app-events#add-to-cart-af_add_to_cart)

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

#### Add to wishlist (af\_add\_to\_wishlist)

**Description**: Used to record add to wishlist events of specific items. To report an event containing multiple items, click [here](/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction).

**Appears in these verticals:** [eCommerce](/docs/recommended-ecommerce-app-events#add-to-wishlist-af_add_to_wishlist), [Hotel booking](/docs/recommended-hotel-booking-app-events#add-to-wishlist-af_add_to_wishlist)

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

#### App open (af\_app\_opened)

Roku Ads event mapping:



| AppsFlyer | af\_app\_opened |
| --- | --- |
| Roku Ads | SESSION\_START |



#### Complete registration (af\_complete\_registration)

**Description**: Used to record user registration methods

**Appears in these verticals:** [Gaming](/docs/recommended-gaming-app-events#complete-registration-af_complete_registration), [eCommerce](/docs/recommended-ecommerce-app-events#complete-registration-af_complete_registration), [Entertainment](/docs/recommended-entertainment-app-events#complete-registration-af_complete_registration), [Finance and banking](/docs/recommended-finance-and-banking-app-events#complete-registration-af_complete_registration), [P2P lending](/docs/recommended-p2p-lending-app-events#complete-registration-af_complete_registration), [Online education](/docs/recommended-online-education-app-events#complete-registration-af_complete_registration), [Ride-hailing](/docs/recommended-ride-hailing-app-events#complete-registration-af_complete_registration), [Hotel booking](/docs/recommended-hotel-booking-app-events#complete-registration-af_complete_registration), [Healthcare](/docs/recommended-healthcare-app-events#complete-registration-af_complete_registration), [Telecommunication](/docs/recommended-telecommunication-app-events#complete-registration-af_complete_registration)

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

#### Content view (af\_content\_view)

**Description**: Used to record content view events. To report an event containing multiple items, click [here](/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction).

**Appears in these verticals:** [eCommerce](/docs/recommended-ecommerce-app-events#content-view-af_content_view), [Flight booking](/docs/recommended-flight-booking-app-events#content-view-af_content_view), [Hotel booking](/docs/recommended-hotel-booking-app-events#content-view-af_content_view)

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

#### Initiated checkout (af\_initiated\_checkout)

**Description**: Used to record checkout events. To report an event containing multiple items, click [here](/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction).

**Appears in verticals:** [eCommerce](/docs/recommended-ecommerce-app-events#initiated-checkout-af_initiated_checkout), [Hotel booking](/docs/recommended-hotel-booking-app-events#initiated-checkout-af_initiated_checkout)

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

0

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

#### Invite (af\_invite)

**Description**: Used to record invite (social) events

**Appears in these verticals:** [Gaming](/docs/recommended-gaming-app-events#invite-af_invite)

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

1

**Typical parameter:**

Click the link to view the mapping to SRNs.

* [af\_description](/docs/in-app-events-event-structure#af_description)

#### Lead (lead)

Roku Ads event mapping:



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

2

#### Level achieved (af\_level\_achieved)

**Description**: Used to record game level events

**Appears in these verticals:** [Gaming](/docs/recommended-gaming-app-events#level-achieved-af_level_achieved)

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

3

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_level](/docs/in-app-events-event-structure#af_level)
* [af\_score](/docs/in-app-events-event-structure#af_score)

#### List view (af\_list\_view)

**Description**: Used to record listings view events

**Appears in these verticals:** [eCommerce](/docs/recommended-ecommerce-app-events#list-view-af_list_view)

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

4

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)

#### Login (af\_login)

**Description**: Used to record user login events

**Appears in these verticals:** [Gaming](/docs/recommended-gaming-app-events#login-af_login), [eCommerce](/docs/recommended-ecommerce-app-events#login-af_login), [Entertainment](/docs/recommended-entertainment-app-events#login-af_login), [Finance and banking](/docs/recommended-finance-and-banking-app-events#login-af_login), [Online education](/docs/recommended-online-education-app-events#login-af_login), [Hotel booking](/docs/recommended-hotel-booking-app-events#login-af_login), [Healthcare](/docs/recommended-healthcare-app-events#login-af_login), [Telecommunication](/docs/recommended-telecommunication-app-events#login-af_login)

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

5

#### Opened from push notification (af\_opened\_from\_push\_notification)

**Description**: Used to record app opens from push notification events

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

6

#### Purchase (af\_purchase)

**Description**: Used to record purchase events (and associate revenue to them).

* For a list of currency symbols supported by AppsFlyer, click [here](https://docs.openexchangerates.org/docs/supported-currencies).
* To report an event containing multiple items, click [here](/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction).
* To record and validate this event, see [Purchase and subscription validation](/docs/purchase-and-subscription-validation-overview).

**Appears in verticals:** [Gaming](/docs/recommended-gaming-app-events#purchase-af_purchase), [eCommerce](/docs/recommended-ecommerce-app-events#purchase-af_purchase), [Online education](/docs/recommended-online-education-app-events#purchase-af_purchase), [Healthcare](/docs/recommended-healthcare-app-events#purchase-af_purchase), [Telecommunication](/docs/recommended-telecommunication-app-events#purchase-af_purchase)

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

7

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

#### Rate (af\_rate)

**Description**: Used to record app/item rating events. To report an event containing multiple items, click [here](/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction).

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

8

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_rating\_value](/docs/in-app-events-event-structure#af_rating_value)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_max\_rating\_value](/docs/in-app-events-event-structure#af_max_rating_value)

#### Re-engage (af\_re\_engage)

**Description**: Used to record user re-engagement events

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

9

**Typical parameter:**

Click the link to view the mapping to SRNs.

* [af\_description](/docs/in-app-events-event-structure#af_description)

#### Search (af\_search)

**Description**: Used to record search events

**Appears in these verticals:** [eCommerce](/docs/recommended-ecommerce-app-events#search-af_search), [Flight booking](/docs/recommended-flight-booking-app-events#search-af_search), [Hotel booking](/docs/recommended-hotel-booking-app-events#search-af_search)

**Event mapping:**



| AppsFlyer | af\_ad\_click |
| --- | --- |
| Meta ads | AdClick |
| Google Ads | - |
| TikTok | InAppADClick |
| Snap | AD\_CLICK |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

0

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

#### Share (af\_share)

**Description**: Used to record sharing events

**Appears in these verticals:** [Gaming](/docs/recommended-gaming-app-events#share-af_share)

**Event mapping:**



| AppsFlyer | af\_ad\_click |
| --- | --- |
| Meta ads | AdClick |
| Google Ads | - |
| TikTok | InAppADClick |
| Snap | AD\_CLICK |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

1

**Typical parameter:**

Click the link to view the mapping to SRNs.

* [af\_description](/docs/in-app-events-event-structure#af_description)

#### Spent credits (af\_spent\_credits)

**Description**: Used to record credit spend events. To report an event containing multiple items, click [here](/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction).

**Appears in verticals:** [Ride-hailing](/docs/recommended-ride-hailing-app-events#spent-credits-af_spent_credits)

**Event mapping:**



| AppsFlyer | af\_ad\_click |
| --- | --- |
| Meta ads | AdClick |
| Google Ads | - |
| TikTok | InAppADClick |
| Snap | AD\_CLICK |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

2

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

#### Start trial (af\_start\_trial)

**Description**: Used to record the start of a free trial of a product. To record and validate this event, see [Purchase and subscription validation](/docs/purchase-and-subscription-validation-overview).

**Appears in these verticals:** [Entertainment](/docs/recommended-entertainment-app-events#start-trial-af_start_trial)

**Event mapping:**



| AppsFlyer | af\_ad\_click |
| --- | --- |
| Meta ads | AdClick |
| Google Ads | - |
| TikTok | InAppADClick |
| Snap | AD\_CLICK |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

3

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

> 📘 **Note**
>
> If you are mapping this event to the Meta ads StartTrial event and want to associate revenue, use the af\_price parameter instead of the af\_revenue parameter.


#### Subscription (af\_subscribe)

**Description**: Used to record paid subscription purchases. To record and validate this event, see [Purchase and subscription validation](/docs/purchase-and-subscription-validation-overview).

**Appears in these verticals:** [Entertainment](/docs/recommended-entertainment-app-events#subscription-af_subscribe)

**Event mapping:**



| AppsFlyer | af\_ad\_click |
| --- | --- |
| Meta ads | AdClick |
| Google Ads | - |
| TikTok | InAppADClick |
| Snap | AD\_CLICK |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

4

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

#### Travel booking (af\_travel\_booking)

**Description**: Used to record travel booking events (and associate revenue to them). To report an event containing multiple items, click [here](/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction).

**Appears in these verticals:** [Flight booking](/docs/recommended-flight-booking-app-events#travel-booking-af_travel_booking), [Hotel booking](/docs/recommended-hotel-booking-app-events#travel-booking-af_travel_booking)

**Event mapping:**



| AppsFlyer | af\_ad\_click |
| --- | --- |
| Meta ads | AdClick |
| Google Ads | - |
| TikTok | InAppADClick |
| Snap | AD\_CLICK |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

5

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

#### Tutorial completion (af\_tutorial\_completion)

**Description**: Used to record tutorial completions. To report an event containing multiple items, click [here](/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction).

**Appears in these verticals:** [Gaming](/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion), [Online education](/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion)

**Event mapping:**



| AppsFlyer | af\_ad\_click |
| --- | --- |
| Meta ads | AdClick |
| Google Ads | - |
| TikTok | InAppADClick |
| Snap | AD\_CLICK |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

6

**Typical parameters:**

Click the links to view the mapping to SRNs.

* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

#### Update (af\_update)

**Description**: Used to record update events. To report an event containing multiple items, click [here](/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction).

**Event mapping:**



| AppsFlyer | af\_ad\_click |
| --- | --- |
| Meta ads | AdClick |
| Google Ads | - |
| TikTok | InAppADClick |
| Snap | AD\_CLICK |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

7

**Typical parameter:**

Click the link to view the mapping to SRNs.

* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)

> 📘 **Note**
>
> In addition to the predefined event names described in this section, [Meta ads offers additional events](/docs/meta-ads-in-app-event-mapping#predefined-event-mapping) that are sent without attributes.


## Predefined event parameters

The following section provides a list of the predefined event parameters. Each event parameter includes the mapping used for Meta ads, Google Ads, Snap, X Ads, and Criteo. You can choose to include any of the event parameters in an event.

> 📘 **Note**
>
> You can see the event parameters in the Event Value column in [raw data reports](/docs/raw-data-reporting-overview) (premium feature).


#### af\_adrev\_ad\_type

**Description**: Type of ad (for example, banner or interstitial)

**Parameter mapping:**



| AppsFlyer | af\_ad\_click |
| --- | --- |
| Meta ads | AdClick |
| Google Ads | - |
| TikTok | InAppADClick |
| Snap | AD\_CLICK |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

8

#### af\_city

**Description**: City where the ride is booked

**Parameter mapping:**



| AppsFlyer | af\_ad\_click |
| --- | --- |
| Meta ads | AdClick |
| Google Ads | - |
| TikTok | InAppADClick |
| Snap | AD\_CLICK |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

9

#### af\_class

**Description**: Travel class booked for the flight

**Parameter mapping:**



| AppsFlyer | af\_ad\_view |
| --- | --- |
| Meta ads | AdImpression |
| Google Ads | - |
| TikTok | InAppADImpr |
| Snap | AD\_VIEW |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

0

#### af\_content

**Description**: Title of the content (for example, name of a song or the title and episode of a TV show)

**Parameter mapping:**



| AppsFlyer | af\_ad\_view |
| --- | --- |
| Meta ads | AdImpression |
| Google Ads | - |
| TikTok | InAppADImpr |
| Snap | AD\_VIEW |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

1

#### af\_content\_id

**Description**: ID of the item

**Note:** Snapchat predefined events `af_content_list` and `af_content_id` share the same event parameter. When both events are recorded simultaneously, only the `af_content_list` event is sent to Snapchat.

**Parameter mapping:**



| AppsFlyer | af\_ad\_view |
| --- | --- |
| Meta ads | AdImpression |
| Google Ads | - |
| TikTok | InAppADImpr |
| Snap | AD\_VIEW |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

2

#### af\_content\_list

**Description**: List of content IDs

**Note:** When you use `af_content_list`, AppsFlyer treats the entire list as a single value. AppsFlyer audience segmentation tools can’t filter for individual content IDs within the list. For example, if  `af_content_list` is `["ID1","ID2","ID3"]`, the audience tool can’t isolate or match `ID1` alone.

**Parameter mapping:**



| AppsFlyer | af\_ad\_view |
| --- | --- |
| Meta ads | AdImpression |
| Google Ads | - |
| TikTok | InAppADImpr |
| Snap | AD\_VIEW |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

3

#### af\_content\_type

**Description**: Product category

**Parameter mapping:**



| AppsFlyer | af\_ad\_view |
| --- | --- |
| Meta ads | AdImpression |
| Google Ads | - |
| TikTok | InAppADImpr |
| Snap | AD\_VIEW |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

4

#### af\_country

**Description**: Country where the ride is booked

**Parameter mapping:**



| AppsFlyer | af\_ad\_view |
| --- | --- |
| Meta ads | AdImpression |
| Google Ads | - |
| TikTok | InAppADImpr |
| Snap | AD\_VIEW |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

5

#### af\_currency

**Description**: Currency code

**Parameter mapping:**



| AppsFlyer | af\_ad\_view |
| --- | --- |
| Meta ads | AdImpression |
| Google Ads | - |
| TikTok | InAppADImpr |
| Snap | AD\_VIEW |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

6

#### af\_customer\_user\_id

**Description**: ID of the customer

**Parameter mapping:**



| AppsFlyer | af\_ad\_view |
| --- | --- |
| Meta ads | AdImpression |
| Google Ads | - |
| TikTok | InAppADImpr |
| Snap | AD\_VIEW |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

7

#### af\_date\_a

**Description**: Check-in date

**Parameter mapping:**



| AppsFlyer | af\_ad\_view |
| --- | --- |
| Meta ads | AdImpression |
| Google Ads | - |
| TikTok | InAppADImpr |
| Snap | AD\_VIEW |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

8

#### af\_date\_b

**Description**: Check-out date

**Parameter mapping:**



| AppsFlyer | af\_ad\_view |
| --- | --- |
| Meta ads | AdImpression |
| Google Ads | - |
| TikTok | InAppADImpr |
| Snap | AD\_VIEW |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

9

#### af\_departing\_arrival\_date

**Description**: Arrival date

**Parameter mapping:**



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

0

#### af\_departing\_departure\_date

**Description**: Departure date

**Parameter mapping:**



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

1

#### af\_description

**Description**: Short description (string)

**Parameter mapping:**



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

2

#### af\_destination\_a

**Description**: First destination

**Parameter mapping:**



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

3

#### af\_destination\_b

**Description**: Second destination

**Parameter mapping:**



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

4

#### af\_destination\_list

**Description**: List of destinations that are included in a destination catalog (for example, a list of museums or restaurants that are near a hotel)

**Parameter mapping:**



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

5

#### af\_hotel\_score

**Description**: Hotel score by reviews

**Parameter mapping:**



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

6

#### af\_level

**Description**: Level the user achieved

**Parameter mapping:**



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

7

#### af\_max\_rating\_value

**Description**: Upper end of a rating scale (for example, 5 out of 5)

**Parameter mapping:**



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

8

#### af\_net\_revenue

**Description**: Net revenue reported for the event. The value represents net revenue according to your own business logic; AppsFlyer does not prescribe how it's calculated and aggregates the value you send. Common examples: revenue after app store fees and/or taxes, gross margin, or revenue after banking or service fees (ecommerce, finance, and so on). Used for the Net revenue metrics (Net revenue, Net ROI, Net ROAS, Net ARPU, Net profit) in [My Dashboards](/docs/my-dashboards).

The value is in the transaction currency, expressed by af\_currency (default USD). Same formatting rules as af\_revenue: no comma separators, currency symbols, special characters, or text (for example, 1234.56), up to five decimal places.

**Note:** There is no predefined SDK constant for this parameter, so send it as a custom parameter with the key af\_net\_revenue.

> 📘 **Note**
>
> For apps with [ROI360 store revenue](/docs/about-roi360-store-revenue) enabled, AppsFlyer populates af\_net\_revenue automatically on the in-app purchase and subscription events it records, calculated as gross revenue minus app store fees and taxes (Net = Gross - store fees - taxes).


#### af\_num\_adults

**Description**: Number of adults traveling

**Parameter mapping:**



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

9

#### af\_num\_children

**Description**: Number of children traveling

Parameter mapping:



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

0

#### af\_num\_infants

**Description**: Number of infants traveling

**Parameter mapping:**



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

1

#### af\_order\_id

**Description**: ID of the transaction

**Parameter mapping:**



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

2

#### af\_payment\_info\_available

**Description**: Whether the user's payment information is available

**Parameter mapping:**



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

3

#### af\_preferred\_neighborhoods

**Description**: Area in which the hotel is located

**Parameter mapping:**



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

4

#### af\_preferred\_num\_stops

**Description**: Number of stops user is looking for (for example, nonstop or direct flight)

**Parameter mapping:**



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

5

#### af\_preferred\_price\_range

**Description**: Preferred price range of hotel

Parameter mapping:



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

6

#### af\_preferred\_star\_ratings

**Description**: Preferred star rating of the hotel

**Parameter mapping:**



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

7

#### af\_price

**Description**: Price of the product. You can use af\_price as a monetary parameter that is not counted as revenue (such as an Add to cart event). This parameter refers to the individual item price. The total amount of all purchases displays under the [af\_revenue](/docs/in-app-events-event-structure#af_revenue) parameter.

**Parameter mapping:**



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

8

#### af\_projected\_revenue

The estimated revenue an advertiser expects from a user based on their early interactions or behaviors before the actual revenue is realized.

#### af\_quantity

**Description**: Number of items

**Parameter mapping:**



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

9

#### af\_rating\_value

**Description**: Selected rating value

**Parameter mapping:**



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

0

#### af\_receipt\_id

**Description**: ID of the receipt

**Parameter mapping:**



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

1

#### af\_region

**Description**: Region where the ride is booked

**Parameter mapping:**



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

2

#### af\_registration\_method

**Description**: Type of signup method

**Parameter mapping:**



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

3

#### af\_returning\_arrival\_date

**Description**: Date and time the return journey finishes

**Parameter mapping:**



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

4

#### af\_returning\_departure\_date

**Description**:  Date and time the return journey starts

**Parameter mapping:**



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

5

#### af\_revenue

**Description**: Total amount of purchases. af\_revenue is counted as revenue in the AppsFlyer platform. It also counts [negative revenue](/docs/in-app-events-overview#revenue-events), from cancellations or refunds.

> 📘 **Important!**
>
> The revenue value should not contain comma separators, currency, special characters, or text. For example, a revenue value should be, 1234.56. AppsFlyer provides revenue value with an accuracy of up to five decimal places.


To learn more about how to use the revenue parameter, click [here](/docs/in-app-events-overview#revenue-events).

**Net revenue:** To report net revenue alongside gross revenue, send [af\_net\_revenue](/docs/in-app-events-event-structure#af_net_revenue) as a custom event parameter. You define what net means for your business (for example, revenue after store fees and/or taxes, gross margin, or revenue after service fees). Apps with ROI360 store revenue enabled have it populated automatically on the purchase and subscription events it records, as gross minus app store fees and taxes.

**Parameter mapping:**



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

6

#### af\_score

**Description**: Score associated with the user's achievement

**Parameter mapping:**



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

7

#### af\_search\_string

**Description**: Search term

**Parameter mapping:**



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

8

#### af\_subscription\_id

**Description**: Subscription ID for the user

**Parameter mapping:**



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

9

#### af\_success

**Description**: Whether completion of action was successful

**Parameter mapping:**



| AppsFlyer | af\_app\_opened |
| --- | --- |
| Roku Ads | SESSION\_START |

0

#### af\_suggested\_destinations

**Description**: List of suggested destinations

**Parameter mapping:**



| AppsFlyer | af\_app\_opened |
| --- | --- |
| Roku Ads | SESSION\_START |

1

#### af\_suggested\_hotels

**Description**: List of suggested hotels

**Parameter mapping:**



| AppsFlyer | af\_app\_opened |
| --- | --- |
| Roku Ads | SESSION\_START |

2

#### af\_travel\_end

**Description**: End date of trip

**Parameter mapping:**



| AppsFlyer | af\_app\_opened |
| --- | --- |
| Roku Ads | SESSION\_START |

3

#### af\_travel\_start

**Description**: Start date of trip

**Parameter mapping:**



| AppsFlyer | af\_app\_opened |
| --- | --- |
| Roku Ads | SESSION\_START |

4

#### af\_user\_score

**Description**: Relative significance of user to advertiser

**Parameter mapping:**



| AppsFlyer | af\_app\_opened |
| --- | --- |
| Roku Ads | SESSION\_START |

5

#### af\_validated

**Description**: Validates a purchase

**Parameter mapping:**



| AppsFlyer | af\_app\_opened |
| --- | --- |
| Roku Ads | SESSION\_START |

6

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

> 📘 **See also**
>
> * [In-app event postback configuration](/docs/in-app-event-postback-configuration)