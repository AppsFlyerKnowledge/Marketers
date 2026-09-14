---
title: "In-app events—Event structure"
excerpt: "View the list of predefined event names and event parameters to record post-install in-app events such as login, register, or in-app purchase."
---
## Overview

In-app events that you want to send require your developer to implement code where applicable in your app. This article describes the predefined event names and predefined event parameters.

To help you determine what events and parameters to record, see our [articles that include examples and flows](https://support.appsflyer.com/hc/articles/115005544169#recommended-events-by-business-vertical) according to business verticals.

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

- [af\_description](https://support.appsflyer.com/hc/articles/4410481112081#af_description)

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

- [af\_adrev\_ad\_type](https://support.appsflyer.com/hc/articles/4410481112081#af_adrev_ad_type)
- [af\_currency](https://support.appsflyer.com/hc/articles/4410481112081#af_currency)

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

- [af\_adrev\_ad\_type](https://support.appsflyer.com/hc/articles/4410481112081#af_adrev_ad_type)
- [af\_currency](https://support.appsflyer.com/hc/articles/4410481112081#af_currency)

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

- [af\_success](https://support.appsflyer.com/hc/articles/4410481112081#af_success)

#### Add to cart (af\_add\_to\_cart)

**Description**: Used to record add to cart events of specific items. To report an event containing multiple items, click [here](https://support.appsflyer.com/hc/articles/115005544169#can-i-add-multiple-items-to-a-single-transaction).

**Appears in these verticals:** [eCommerce](https://support.appsflyer.com/hc/articles/360019347957--Recommended-eCommerce-app-events#add-to-cart-af_add_to_cart), [Healthcare](/docs/recommended-healthcare-app-events#add-to-cart-af_add_to_cart)

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

- [af\_price](https://support.appsflyer.com/hc/articles/4410481112081#af_price)
- [af\_content\_type](https://support.appsflyer.com/hc/articles/4410481112081#af_content_type)
- [af\_content\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_content_id)
- [af\_content](https://support.appsflyer.com/hc/articles/4410481112081#af_content)
- [af\_currency](https://support.appsflyer.com/hc/articles/4410481112081#af_currency)
- [af\_quantity](https://support.appsflyer.com/hc/articles/4410481112081#af_quantity)

#### Add to wishlist (af\_add\_to\_wishlist)

**Description**: Used to record add to wishlist events of specific items. To report an event containing multiple items, click [here](https://support.appsflyer.com/hc/articles/115005544169#can-i-add-multiple-items-to-a-single-transaction).

**Appears in these verticals:** [eCommerce](https://support.appsflyer.com/hc/articles/360019347957--Recommended-eCommerce-app-events#add-to-wishlist-af_add_to_wishlist), [Hotel booking](/docs/recommended-hotel-booking-app-events#add-to-wishlist-af_add_to_wishlist)

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

- [af\_price](https://support.appsflyer.com/hc/articles/4410481112081#af_price)
- [af\_content\_type](https://support.appsflyer.com/hc/articles/4410481112081#af_content_type)
- [af\_content\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_content_id)
- [af\_content](https://support.appsflyer.com/hc/articles/4410481112081#af_content)
- [af\_currency](https://support.appsflyer.com/hc/articles/4410481112081#af_currency)
- [af\_quantity](https://support.appsflyer.com/hc/articles/4410481112081#af_quantity)

#### App open (af\_app\_opened)

Roku Ads event mapping:

| AppsFlyer | af\_app\_opened |
| --- | --- |
| Roku Ads | SESSION\_START |

#### Complete registration (af\_complete\_registration)

**Description**: Used to record user registration methods

**Appears in these verticals:** [Gaming](/docs/recommended-gaming-app-events#complete-registration-af_complete_registration), [eCommerce](https://support.appsflyer.com/hc/articles/360019347957--Recommended-eCommerce-app-events#complete-registration-af_complete_registration), [Entertainment](/docs/recommended-entertainment-app-events#complete-registration-af_complete_registration), [Finance and banking](/docs/recommended-finance-and-banking-app-events#complete-registration-af_complete_registration), [P2P lending](/docs/recommended-p2p-lending-app-events#complete-registration-af_complete_registration), [Online education](/docs/recommended-online-education-app-events#complete-registration-af_complete_registration), [Ride-hailing](/docs/recommended-ride-hailing-app-events#complete-registration-af_complete_registration), [Hotel booking](/docs/recommended-hotel-booking-app-events#complete-registration-af_complete_registration), [Healthcare](/docs/recommended-healthcare-app-events#complete-registration-af_complete_registration), [Telecommunication](/docs/recommended-telecommunication-app-events#complete-registration-af_complete_registration)

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

- [af\_registration\_method](https://support.appsflyer.com/hc/articles/4410481112081#af_registration_method)

#### Content view (af\_content\_view)

**Description**: Used to record content view events. To report an event containing multiple items, click [here](https://support.appsflyer.com/hc/articles/115005544169#can-i-add-multiple-items-to-a-single-transaction).

**Appears in these verticals:** [eCommerce](https://support.appsflyer.com/hc/articles/360019347957--Recommended-eCommerce-app-events#content-view-af_content_view), [Flight booking](/docs/recommended-flight-booking-app-events#content-view-af_content_view), [Hotel booking](/docs/recommended-hotel-booking-app-events#content-view-af_content_view)

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

- [af\_price](https://support.appsflyer.com/hc/articles/4410481112081#af_price)
- [af\_content\_type](https://support.appsflyer.com/hc/articles/4410481112081#af_content_type)
- [af\_content\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_content_id)
- [af\_content](https://support.appsflyer.com/hc/articles/4410481112081#af_content)
- [af\_currency](https://support.appsflyer.com/hc/articles/4410481112081#af_currency)
- [af\_content\_list](https://support.appsflyer.com/hc/articles/4410481112081#af_content_list)
- [af\_date\_a](https://support.appsflyer.com/hc/articles/4410481112081#af_date_a)
- [af\_date\_b](https://support.appsflyer.com/hc/articles/4410481112081#af_date_b)
- [af\_departing\_departure\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_departing_departure_date)
- [af\_returning\_departure\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_returning_departure_date)
- [af\_destination\_a](https://support.appsflyer.com/hc/articles/4410481112081#af_destination_a)
- [af\_destination\_b](https://support.appsflyer.com/hc/articles/4410481112081#af_destination_b)
- [af\_destination\_list](https://support.appsflyer.com/hc/articles/4410481112081#af_destination_list)
- [af\_city](https://support.appsflyer.com/hc/articles/4410481112081#af_city)
- [af\_region](https://support.appsflyer.com/hc/articles/4410481112081#af_region)
- [af\_country](https://support.appsflyer.com/hc/articles/4410481112081#af_country)
- [af\_departing\_arrival\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_departing_arrival_date)
- [af\_returning\_arrival\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_returning_arrival_date)
- [af\_suggested\_destinations](https://support.appsflyer.com/hc/articles/4410481112081#af_suggested_destinations)
- [af\_travel\_start](https://support.appsflyer.com/hc/articles/4410481112081#af_travel_start)
- [af\_travel\_end](https://support.appsflyer.com/hc/articles/4410481112081#af_travel_end)
- [af\_num\_adults](https://support.appsflyer.com/hc/articles/4410481112081#af_num_adults)
- [af\_num\_children](https://support.appsflyer.com/hc/articles/4410481112081#af_num_children)
- [af\_num\_infants](https://support.appsflyer.com/hc/articles/4410481112081#af_num_infants)
- [af\_class](https://support.appsflyer.com/hc/articles/4410481112081#af_class)
- [af\_suggested\_hotels](https://support.appsflyer.com/hc/articles/4410481112081#af_suggested_hotels)
- [af\_user\_score](https://support.appsflyer.com/hc/articles/4410481112081#af_user_score)
- [af\_hotel\_score](https://support.appsflyer.com/hc/articles/4410481112081#af_hotel_score)
- [af\_preferred\_star\_ratings](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_star_ratings)
- [af\_preferred\_price\_range](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_price_range)
- [af\_preferred\_neighborhoods](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_neighborhoods)
- [af\_preferred\_num\_stops](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_num_stops)

#### Initiated checkout (af\_initiated\_checkout)

**Description**: Used to record checkout events. To report an event containing multiple items, click [here](https://support.appsflyer.com/hc/articles/115005544169#can-i-add-multiple-items-to-a-single-transaction).

**Appears in verticals:** [eCommerce](https://support.appsflyer.com/hc/articles/360019347957--Recommended-eCommerce-app-events#initiated-checkout-af_initiated_checkout), [Hotel booking](/docs/recommended-hotel-booking-app-events#initiated-checkout-af_initiated_checkout)

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

- [af\_price](https://support.appsflyer.com/hc/articles/4410481112081#af_price)
- [af\_content\_type](https://support.appsflyer.com/hc/articles/4410481112081#af_content_type)
- [af\_content\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_content_id)
- [af\_content](https://support.appsflyer.com/hc/articles/4410481112081#af_content)
- [af\_currency](https://support.appsflyer.com/hc/articles/4410481112081#af_currency)
- [af\_quantity](https://support.appsflyer.com/hc/articles/4410481112081#af_quantity)
- [af\_payment\_info\_available](https://support.appsflyer.com/hc/articles/4410481112081#af_payment_info_available)
- [af\_content\_list](https://support.appsflyer.com/hc/articles/4410481112081#af_content_list)
- [af\_date\_a](https://support.appsflyer.com/hc/articles/4410481112081#af_date_a)
- [af\_date\_b](https://support.appsflyer.com/hc/articles/4410481112081#af_date_b)
- [af\_departing\_departure\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_departing_departure_date)
- [af\_returning\_departure\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_returning_departure_date)
- [af\_destination\_a](https://support.appsflyer.com/hc/articles/4410481112081#af_destination_a)
- [af\_destination\_b](https://support.appsflyer.com/hc/articles/4410481112081#af_destination_b)
- [af\_destination\_list](https://support.appsflyer.com/hc/articles/4410481112081#af_destination_list)
- [af\_city](https://support.appsflyer.com/hc/articles/4410481112081#af_city)
- [af\_region](https://support.appsflyer.com/hc/articles/4410481112081#af_region)
- [af\_country](https://support.appsflyer.com/hc/articles/4410481112081#af_country)
- [af\_departing\_arrival\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_departing_arrival_date)
- [af\_returning\_arrival\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_returning_arrival_date)
- [af\_suggested\_destinations](https://support.appsflyer.com/hc/articles/4410481112081#af_suggested_destinations)
- [af\_travel\_start](https://support.appsflyer.com/hc/articles/4410481112081#af_travel_start)
- [af\_travel\_end](https://support.appsflyer.com/hc/articles/4410481112081#af_travel_end)
- [af\_num\_adults](https://support.appsflyer.com/hc/articles/4410481112081#af_num_adults)
- [af\_num\_children](https://support.appsflyer.com/hc/articles/4410481112081#af_num_children)
- [af\_num\_infants](https://support.appsflyer.com/hc/articles/4410481112081#af_num_infants)
- [af\_class](https://support.appsflyer.com/hc/articles/4410481112081#af_class)
- [af\_suggested\_hotels](https://support.appsflyer.com/hc/articles/4410481112081#af_suggested_hotels)
- [af\_user\_score](https://support.appsflyer.com/hc/articles/4410481112081#af_user_score)
- [af\_hotel\_score](https://support.appsflyer.com/hc/articles/4410481112081#af_hotel_score)
- [af\_preferred\_star\_ratings](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_star_ratings)
- [af\_preferred\_price\_range](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_price_range)
- [af\_preferred\_neighborhoods](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_neighborhoods)
- [af\_preferred\_num\_stops](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_num_stops)

#### Invite (af\_invite)

**Description**: Used to record invite (social) events

**Appears in these verticals:** [Gaming](/docs/recommended-gaming-app-events#invite-af_invite)

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

- [af\_description](https://support.appsflyer.com/hc/articles/4410481112081#af_description)

#### Lead (lead)

Roku Ads event mapping:

| AppsFlyer | lead |
| --- | --- |
| Roku Ads | LEAD |

#### Level achieved (af\_level\_achieved)

**Description**: Used to record game level events

**Appears in these verticals:** [Gaming](/docs/recommended-gaming-app-events#level-achieved-af_level_achieved)

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

- [af\_level](https://support.appsflyer.com/hc/articles/4410481112081#af_level)
- [af\_score](https://support.appsflyer.com/hc/articles/4410481112081#af_score)

#### List view (af\_list\_view)

**Description**: Used to record listings view events

**Appears in these verticals:** [eCommerce](https://support.appsflyer.com/hc/articles/360019347957--Recommended-eCommerce-app-events#list-view-af_list_view)

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

- [af\_content\_type](https://support.appsflyer.com/hc/articles/4410481112081#af_content_type)
- [af\_content\_list](https://support.appsflyer.com/hc/articles/4410481112081#af_content_list)

#### Login (af\_login)

**Description**: Used to record user login events

**Appears in these verticals:** [Gaming](/docs/recommended-gaming-app-events#login-af_login), [eCommerce](https://support.appsflyer.com/hc/articles/360019347957--Recommended-eCommerce-app-events#login-af_login), [Entertainment](/docs/recommended-entertainment-app-events#login-af_login), [Finance and banking](/docs/recommended-finance-and-banking-app-events#login-af_login), [Online education](/docs/recommended-online-education-app-events#login-af_login), [Hotel booking](/docs/recommended-hotel-booking-app-events#login-af_login), [Healthcare](/docs/recommended-healthcare-app-events#login-af_login), [Telecommunication](/docs/recommended-telecommunication-app-events#login-af_login)

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

#### Opened from push notification (af\_opened\_from\_push\_notification)

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

#### Purchase (af\_purchase)

**Description**: Used to record purchase events (and associate revenue to them).

- For a list of currency symbols supported by AppsFlyer, click [here](https://docs.openexchangerates.org/docs/supported-currencies).
- To report an event containing multiple items, click [here](https://support.appsflyer.com/hc/articles/115005544169#can-i-add-multiple-items-to-a-single-transaction).
- To record and validate this event, see [Purchase and subscription validation](/docs/purchase-and-subscription-validation-overview).

**Appears in verticals:** [Gaming](/docs/recommended-gaming-app-events#purchase-af_purchase), [eCommerce](https://support.appsflyer.com/hc/articles/360019347957--Recommended-eCommerce-app-events#purchase-af_purchase), [Online education](/docs/recommended-online-education-app-events#purchase-af_purchase), [Healthcare](/docs/recommended-healthcare-app-events#purchase-af_purchase), [Telecommunication](/docs/recommended-telecommunication-app-events#purchase-af_purchase)

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

- [af\_revenue](https://support.appsflyer.com/hc/articles/4410481112081#af_revenue)
- [af\_content\_type](https://support.appsflyer.com/hc/articles/4410481112081#af_content_type)
- [af\_content\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_content_id)
- [af\_content](https://support.appsflyer.com/hc/articles/4410481112081#af_content)
- [af\_currency](https://support.appsflyer.com/hc/articles/4410481112081#af_currency)
- [af\_quantity](https://support.appsflyer.com/hc/articles/4410481112081#af_quantity)
- [af\_validated](https://support.appsflyer.com/hc/articles/4410481112081#af_validated)
- [af\_receipt\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_receipt_id)
- [af\_order\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_order_id)
- [af\_content\_list](https://support.appsflyer.com/hc/articles/4410481112081#af_content_list)
- [af\_date\_a](https://support.appsflyer.com/hc/articles/4410481112081#af_date_a)
- [af\_date\_b](https://support.appsflyer.com/hc/articles/4410481112081#af_date_b)
- [af\_departing\_departure\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_departing_departure_date)
- [af\_returning\_departure\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_returning_departure_date)
- [af\_destination\_a](https://support.appsflyer.com/hc/articles/4410481112081#af_destination_a)
- [af\_destination\_b](https://support.appsflyer.com/hc/articles/4410481112081#af_destination_b)
- [af\_destination\_list](https://support.appsflyer.com/hc/articles/4410481112081#af_destination_list)
- [af\_city](https://support.appsflyer.com/hc/articles/4410481112081#af_city)
- [af\_region](https://support.appsflyer.com/hc/articles/4410481112081#af_region)
- [af\_country](https://support.appsflyer.com/hc/articles/4410481112081#af_country)
- [af\_departing\_arrival\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_departing_arrival_date)
- [af\_returning\_arrival\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_returning_arrival_date)
- [af\_suggested\_destinations](https://support.appsflyer.com/hc/articles/4410481112081#af_suggested_destinations)
- [af\_travel\_start](https://support.appsflyer.com/hc/articles/4410481112081#af_travel_start)
- [af\_travel\_end](https://support.appsflyer.com/hc/articles/4410481112081#af_travel_end)
- [af\_num\_adults](https://support.appsflyer.com/hc/articles/4410481112081#af_num_adults)
- [af\_num\_children](https://support.appsflyer.com/hc/articles/4410481112081#af_num_children)
- [af\_num\_infants](https://support.appsflyer.com/hc/articles/4410481112081#af_num_infants)
- [af\_class](https://support.appsflyer.com/hc/articles/4410481112081#af_class)
- [af\_suggested\_hotels](https://support.appsflyer.com/hc/articles/4410481112081#af_suggested_hotels)
- [af\_user\_score](https://support.appsflyer.com/hc/articles/4410481112081#af_user_score)
- [af\_hotel\_score](https://support.appsflyer.com/hc/articles/4410481112081#af_hotel_score)
- [af\_price](https://support.appsflyer.com/hc/articles/4410481112081#af_price)
- [af\_preferred\_star\_ratings](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_star_ratings)
- [af\_preferred\_price\_range](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_price_range)
- [af\_preferred\_neighborhoods](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_neighborhoods)
- [af\_preferred\_num\_stops](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_num_stops)

#### Rate (af\_rate)

**Description**: Used to record app/item rating events. To report an event containing multiple items, click [here](https://support.appsflyer.com/hc/articles/115005544169#can-i-add-multiple-items-to-a-single-transaction).

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

- [af\_rating\_value](https://support.appsflyer.com/hc/articles/4410481112081#af_rating_value)
- [af\_content\_type](https://support.appsflyer.com/hc/articles/4410481112081#af_content_type)
- [af\_content\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_content_id)
- [af\_content](https://support.appsflyer.com/hc/articles/4410481112081#af_content)
- [af\_max\_rating\_value](https://support.appsflyer.com/hc/articles/4410481112081#af_max_rating_value)

#### Re-engage (af\_re\_engage)

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

- [af\_description](https://support.appsflyer.com/hc/articles/4410481112081#af_description)

#### Search (af\_search)

**Description**: Used to record search events

**Appears in these verticals:** [eCommerce](https://support.appsflyer.com/hc/articles/360019347957--Recommended-eCommerce-app-events#search-af_search), [Flight booking](/docs/recommended-flight-booking-app-events#search-af_search), [Hotel booking](/docs/recommended-hotel-booking-app-events#search-af_search)

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

- [af\_content\_type](https://support.appsflyer.com/hc/articles/4410481112081#af_content_type)
- [af\_search\_string](https://support.appsflyer.com/hc/articles/4410481112081#af_search_string)
- [af\_date\_a](https://support.appsflyer.com/hc/articles/4410481112081#af_date_a)
- [af\_date\_b](https://support.appsflyer.com/hc/articles/4410481112081#af_date_b)
- [af\_destination\_a](https://support.appsflyer.com/hc/articles/4410481112081#af_destination_a)
- [af\_destination\_b](https://support.appsflyer.com/hc/articles/4410481112081#af_destination_b)
- [af\_success](https://support.appsflyer.com/hc/articles/4410481112081#af_success)
- [af\_content\_list](https://support.appsflyer.com/hc/articles/4410481112081#af_content_list)
- [af\_departing\_departure\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_departing_departure_date)
- [af\_returning\_departure\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_returning_departure_date)
- [af\_destination\_list](https://support.appsflyer.com/hc/articles/4410481112081#af_destination_list)
- [af\_city](https://support.appsflyer.com/hc/articles/4410481112081#af_city)
- [af\_region](https://support.appsflyer.com/hc/articles/4410481112081#af_region)
- [af\_country](https://support.appsflyer.com/hc/articles/4410481112081#af_country)
- [af\_departing\_arrival\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_departing_arrival_date)
- [af\_returning\_arrival\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_returning_arrival_date)
- [af\_suggested\_destinations](https://support.appsflyer.com/hc/articles/4410481112081#af_suggested_destinations)
- [af\_travel\_start](https://support.appsflyer.com/hc/articles/4410481112081#af_travel_start)
- [af\_travel\_end](https://support.appsflyer.com/hc/articles/4410481112081#af_travel_end)
- [af\_num\_adults](https://support.appsflyer.com/hc/articles/4410481112081#af_num_adults)
- [af\_num\_children](https://support.appsflyer.com/hc/articles/4410481112081#af_num_children)
- [af\_num\_infants](https://support.appsflyer.com/hc/articles/4410481112081#af_num_infants)
- [af\_class](https://support.appsflyer.com/hc/articles/4410481112081#af_class)
- [af\_suggested\_hotels](https://support.appsflyer.com/hc/articles/4410481112081#af_suggested_hotels)
- [af\_user\_score](https://support.appsflyer.com/hc/articles/4410481112081#af_user_score)
- [af\_hotel\_score](https://support.appsflyer.com/hc/articles/4410481112081#af_hotel_score)
- [af\_price](https://support.appsflyer.com/hc/articles/4410481112081#af_price)
- [af\_preferred\_star\_ratings](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_star_ratings)
- [af\_preferred\_price\_range](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_price_range)
- [af\_preferred\_neighborhoods](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_neighborhoods)
- [af\_preferred\_num\_stops](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_num_stops)

#### Share (af\_share)

**Description**: Used to record sharing events

**Appears in these verticals:** [Gaming](/docs/recommended-gaming-app-events#share-af_share)

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

- [af\_description](https://support.appsflyer.com/hc/articles/4410481112081#af_description)

#### Spent credits (af\_spent\_credits)

**Description**: Used to record credit spend events. To report an event containing multiple items, click [here](https://support.appsflyer.com/hc/articles/115005544169#can-i-add-multiple-items-to-a-single-transaction).

**Appears in verticals:** [Ride-hailing](https://support.appsflyer.com/hc/articles/360019651957#spent-credits-af_spent_credits)

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

- [af\_price](https://support.appsflyer.com/hc/articles/4410481112081#af_price)
- [af\_content\_type](https://support.appsflyer.com/hc/articles/4410481112081#af_content_type)
- [af\_content\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_content_id)
- [af\_content](https://support.appsflyer.com/hc/articles/4410481112081#af_content)

#### Start trial (af\_start\_trial)

**Description**: Used to record the start of a free trial of a product. To record and validate this event, see [Purchase and subscription validation](/docs/purchase-and-subscription-validation-overview).

**Appears in these verticals:** [Entertainment](/docs/recommended-entertainment-app-events#start-trial-af_start_trial)

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

- [af\_price](https://support.appsflyer.com/hc/articles/4410481112081#af_price)
- [af\_currency](https://support.appsflyer.com/hc/articles/4410481112081#af_currency)
- [af\_subscription\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_subscription_id)

> 📘 Note
>
> If you are mapping this event to the Meta ads StartTrial event and want to associate revenue, use the af\_price parameter instead of the af\_revenue parameter.

#### Subscription (af\_subscribe)

**Description**: Used to record paid subscription purchases. To record and validate this event, see [Purchase and subscription validation](/docs/purchase-and-subscription-validation-overview).

**Appears in these verticals:** [Entertainment](/docs/recommended-entertainment-app-events#subscription-af_subscribe)

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

- [af\_revenue](https://support.appsflyer.com/hc/articles/4410481112081#af_revenue)
- [af\_currency](https://support.appsflyer.com/hc/articles/4410481112081#af_currency)
- [af\_subscription\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_subscription_id)

#### Travel booking (af\_travel\_booking)

**Description**: Used to record travel booking events (and associate revenue to them). To report an event containing multiple items, click [here](https://support.appsflyer.com/hc/articles/115005544169#can-i-add-multiple-items-to-a-single-transaction).

**Appears in these verticals:** [Flight booking](/docs/recommended-flight-booking-app-events#travel-booking-af_travel_booking), [Hotel booking](https://support.appsflyer.com/hc/articles/360019843558#travel-booking-af_travel_booking)

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

- [af\_revenue](https://support.appsflyer.com/hc/articles/4410481112081#af_revenue)
- [af\_customer\_user\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_customer_user_id)
- [af\_content\_type](https://support.appsflyer.com/hc/articles/4410481112081#af_content_type)
- [af\_content\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_content_id)
- [af\_class](https://support.appsflyer.com/hc/articles/4410481112081#af_class)
- [af\_date\_a](https://support.appsflyer.com/hc/articles/4410481112081#af_date_a)
- [af\_date\_b](https://support.appsflyer.com/hc/articles/4410481112081#af_date_b)
- [af\_destination\_a](https://support.appsflyer.com/hc/articles/4410481112081#af_destination_a)
- [af\_destination\_b](https://support.appsflyer.com/hc/articles/4410481112081#af_destination_b)
- [af\_success](https://support.appsflyer.com/hc/articles/4410481112081#af_success)
- [af\_content\_list](https://support.appsflyer.com/hc/articles/4410481112081#af_content_list)
- [af\_departing\_departure\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_departing_departure_date)
- [af\_returning\_departure\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_returning_departure_date)
- [af\_destination\_list](https://support.appsflyer.com/hc/articles/4410481112081#af_destination_list)
- [af\_city](https://support.appsflyer.com/hc/articles/4410481112081#af_city)
- [af\_region](https://support.appsflyer.com/hc/articles/4410481112081#af_region)
- [af\_country](https://support.appsflyer.com/hc/articles/4410481112081#af_country)
- [af\_departing\_arrival\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_departing_arrival_date)
- [af\_returning\_arrival\_date](https://support.appsflyer.com/hc/articles/4410481112081#af_returning_arrival_date)
- [af\_suggested\_destinations](https://support.appsflyer.com/hc/articles/4410481112081#af_suggested_destinations)
- [af\_travel\_start](https://support.appsflyer.com/hc/articles/4410481112081#af_travel_start)
- [af\_travel\_end](https://support.appsflyer.com/hc/articles/4410481112081#af_travel_end)
- [af\_num\_adults](https://support.appsflyer.com/hc/articles/4410481112081#af_num_adults)
- [af\_num\_children](https://support.appsflyer.com/hc/articles/4410481112081#af_num_children)
- [af\_num\_infants](https://support.appsflyer.com/hc/articles/4410481112081#af_num_infants)
- [af\_class](https://support.appsflyer.com/hc/articles/4410481112081#af_class)
- [af\_suggested\_hotels](https://support.appsflyer.com/hc/articles/4410481112081#af_suggested_hotels)
- [af\_user\_score](https://support.appsflyer.com/hc/articles/4410481112081#af_user_score)
- [af\_hotel\_score](https://support.appsflyer.com/hc/articles/4410481112081#af_hotel_score)
- [af\_price](https://support.appsflyer.com/hc/articles/4410481112081#af_price)
- [af\_preferred\_star\_ratings](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_star_ratings)
- [af\_preferred\_price\_range](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_price_range)
- [af\_preferred\_neighborhoods](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_neighborhoods)
- [af\_preferred\_num\_stops](https://support.appsflyer.com/hc/articles/4410481112081#af_preferred_num_stops)
- [af\_order\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_order_id)

#### Tutorial completion (af\_tutorial\_completion)

**Description**: Used to record tutorial completions. To report an event containing multiple items, click [here](https://support.appsflyer.com/hc/articles/115005544169#can-i-add-multiple-items-to-a-single-transaction).

**Appears in these verticals:** [Gaming](/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion), [Online education](/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion)

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

- [af\_success](https://support.appsflyer.com/hc/articles/4410481112081#af_success)
- [af\_content\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_content_id)
- [af\_content](https://support.appsflyer.com/hc/articles/4410481112081#af_content)

#### Update (af\_update)

**Description**: Used to record update events. To report an event containing multiple items, click [here](https://support.appsflyer.com/hc/articles/115005544169#can-i-add-multiple-items-to-a-single-transaction).

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

- [af\_content\_id](https://support.appsflyer.com/hc/articles/4410481112081#af_content_id)

> 📘 Note
>
> In addition to the predefined event names described in this section, [Meta ads offers additional events](https://support.appsflyer.com/hc/articles/4410480904081#predefined-event-mapping) that are sent without attributes.

## Predefined event parameters

The following section provides a list of the predefined event parameters. Each event parameter includes the mapping used for Meta ads, Google Ads, Snap, X Ads, and Criteo. You can choose to include any of the event parameters in an event.

> 📘 Note
>
> You can see the event parameters in the Event Value column in [raw data reports](https://support.appsflyer.com/hc/articles/209680773) (premium feature).

#### af\_adrev\_ad\_type

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

#### af\_city

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

#### af\_class

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

#### af\_content

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

#### af\_content\_id

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

#### af\_content\_list

**Description**: List of content IDs

**Note:** When you use `af_content_list`, AppsFlyer treats the entire list as a single value. AppsFlyer audience segmentation tools can’t filter for individual content IDs within the list. For example, if `af_content_list` is `["ID1","ID2","ID3"]`, the audience tool can’t isolate or match `ID1` alone.

**Parameter mapping:**

| AppsFlyer | af\_content\_list |
| --- | --- |
| Meta ads | fb\_content\_id |
| Google Ads | item\_id |
| Snap | item\_ids |
| X Ads | - |
| TikTok | - |
| Criteo | - |

#### af\_content\_type

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

#### af\_country

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

#### af\_currency

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

#### af\_customer\_user\_id

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

#### af\_date\_a

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

#### af\_date\_b

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

#### af\_departing\_arrival\_date

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

#### af\_departing\_departure\_date

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

#### af\_description

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

#### af\_destination\_a

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

#### af\_destination\_b

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

#### af\_destination\_list

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

#### af\_hotel\_score

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

#### af\_level

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

#### af\_max\_rating\_value

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

#### af\_net\_revenue

**Description**: Net revenue reported for the event. The value represents net revenue according to your own business logic; AppsFlyer does not prescribe how it's calculated and aggregates the value you send. Common examples: revenue after app store fees and/or taxes, gross margin, or revenue after banking or service fees (ecommerce, finance, and so on). Used for the Net revenue metrics (Net revenue, Net ROI, Net ROAS, Net ARPU, Net profit) in [My Dashboards](/docs/my-dashboards).

The value is in the transaction currency, expressed by af\_currency (default USD). Same formatting rules as af\_revenue: no comma separators, currency symbols, special characters, or text (for example, 1234.56), up to five decimal places.

**Note:** There is no predefined SDK constant for this parameter, so send it as a custom parameter with the key af\_net\_revenue.

> 📘 Note
>
> For apps with [ROI360 store revenue](/docs/about-roi360-store-revenue) enabled, AppsFlyer populates af\_net\_revenue automatically on the in-app purchase and subscription events it records, calculated as gross revenue minus app store fees and taxes (Net = Gross - store fees - taxes).

#### af\_num\_adults

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

#### af\_num\_children

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

#### af\_num\_infants

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

#### af\_order\_id

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

#### af\_payment\_info\_available

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

#### af\_preferred\_neighborhoods

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

#### af\_preferred\_num\_stops

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

#### af\_preferred\_price\_range

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

#### af\_preferred\_star\_ratings

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

#### af\_price

**Description**: Price of the product. You can use af\_price as a monetary parameter that is not counted as revenue (such as an Add to cart event). This parameter refers to the individual item price. The total amount of all purchases displays under the [af\_revenue](https://support.appsflyer.com/hc/articles/4410481112081#af_revenue) parameter.

**Parameter mapping:**

| AppsFlyer | af\_price |
| --- | --- |
| Meta ads | fb\_price |
| Google Ads | price |
| Snap | price |
| X Ads | price\_micro |
| TikTok | price |
| Criteo | price |

#### af\_projected\_revenue

The estimated revenue an advertiser expects from a user based on their early interactions or behaviors before the actual revenue is realized.

#### af\_quantity

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

#### af\_rating\_value

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

#### af\_receipt\_id

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

#### af\_region

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

#### af\_registration\_method

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

#### af\_returning\_arrival\_date

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

#### af\_returning\_departure\_date

**Description**: Date and time the return journey starts

**Parameter mapping:**

| AppsFlyer | af\_returning\_departure\_date |
| --- | --- |
| Meta ads | fb\_returning\_departure\_date |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | returning\_date |
| Criteo | - |

#### af\_revenue

**Description**: Total amount of purchases. af\_revenue is counted as revenue in the AppsFlyer platform. It also counts [negative revenue](https://support.appsflyer.com/hc/articles/115005544169#revenue-events), from cancellations or refunds.

> ❗️ Important!
>
> The revenue value should not contain comma separators, currency, special characters, or text. For example, a revenue value should be, 1234.56. AppsFlyer provides revenue value with an accuracy of up to five decimal places.

To learn more about how to use the revenue parameter, click [here](https://support.appsflyer.com/hc/articles/115005544169#revenue-events).

**Net revenue:** To report net revenue alongside gross revenue, send [af\_net\_revenue](https://support.appsflyer.com/hc/articles/4410481112081#af_net_revenue) as a custom event parameter. You define what net means for your business (for example, revenue after store fees and/or taxes, gross margin, or revenue after service fees). Apps with ROI360 store revenue enabled have it populated automatically on the purchase and subscription events it records, as gross minus app store fees and taxes.

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

#### af\_score

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

#### af\_search\_string

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

#### af\_subscription\_id

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

#### af\_success

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

#### af\_suggested\_destinations

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

#### af\_suggested\_hotels

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

#### af\_travel\_end

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

#### af\_travel\_start

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

#### af\_user\_score

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

#### af\_validated

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

The following is a list of predefined event parameters that do not include SRN mapping:

- af\_achievement\_id
- af\_coupon\_code
- af\_customer\_segment
- af\_deep\_link
- af\_event\_end
- af\_event\_start
- af\_lat
- af\_long
- af\_new\_version
- af\_old\_version
- af\_param\_1
- af\_param\_2
- af\_param\_3
- af\_param\_4
- af\_param\_5
- af\_param\_6
- af\_param\_7
- af\_param\_8
- af\_param\_9
- af\_param\_10
- af\_review\_text
- af\_tutorial\_id
- af\_virtual\_currency\_name
- af\_duration\_seconds

<Cards>
  <Card title="In-app event postback configuration" href="https://support.appsflyer.com/hc/articles/208439256">
    Learn how to configure postbacks for post-install in-app events.
  </Card>
</Cards>