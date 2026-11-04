---
title: Recommended hotel booking app events
metadata:
  keywords:
    - Advertisers
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
  created_at: '2021-04-29T14:49:54Z'
  edited_at: '2023-12-04T11:56:58Z'
  id: 360019843558
  locale: en-us
  section: In-app events
  section_id: 6551285343761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360019843558-Recommended-hotel-booking-app-events
---
> **At a glance:** Measure the quality of your users throughout their user journey by recording these suggested in-app events for your hotel booking app.

<div id="-hotel-booking" />

## <Image alt="InApp_Events_hotel.png" src="https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png" width="100px" /> Hotel booking

Hotel booking apps allow travelers to easily book hotels while choosing from the best offers. The typical events that we suggest recording are search, purchase, travel booking, and add to wishlist.

Recording events can help you determine:

* Which campaigns and media sources bring users that actually book vacations
* Which campaigns and media sources bring the users that book the most and generate more revenue

You can attribute preferences such as hotel score, season, country, and the number of kids to users that come from certain media sources. Then, you can optimize your campaigns by targeting these user preferences.

<div id="important" />

> 🚧 **Important!**
>
> * Make sure to read the <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#setting-up-in-app-events">instructions</Anchor> for marketers about implementing in-app events.
> * To streamline the implementation process, use our <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=hotel_booking">In-app event generator</Anchor>. This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=hotel_booking&view=code">code samples</Anchor> for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyer developer hub</Anchor>.**
>
> For more information about recording in-app events, see the <Anchor target="_blank" href="/marketers/docs/in-app-events-overview">In-app events guide</Anchor>.

[![Flowchart_for_recommended_events_hotel_booking_app_user_journey](https://files.readme.io/f425bc8865d731eb4934b6f32123156c7016ea1f75472e8878e76636aa593073-4402679204241.png)](https://files.readme.io/f425bc8865d731eb4934b6f32123156c7016ea1f75472e8878e76636aa593073-4402679204241.png)

<div id="recommended-structures-for-predefined-events" />

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the hotel booking vertical. Each structure includes a predefined event name and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Complete registration (af_complete_registration)">

**Purpose**

Learn how many users installed the app and completed the signup process, what signup methods your users prefer, and which media sources bring users that actually sign up.

**Trigger**

When the user completes the signup process

Event parameters

| Field name | Description | Example value |
| --- | --- | --- |
| af\_registration\_method | Type of signup method | email, Facebook |

</Accordion>

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Purpose**

Understand the retention of your registered users

**Trigger**

When the user successfully logs in

**Event parameters**

Can be sent without any additional parameters

</Accordion>

<div id="search-af_search" />

<Accordion title="Search (af_search)">

**Purpose**

Learn what users are looking for, and which search results are the most relevant and lead to a purchase. In addition, you can see what users in certain geographical locations are searching for and target them accordingly across media sources.

**Trigger**

When the user performs a search

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_date\_a | Check-in date | 2018/07/26 |
| af\_date\_b | Check-out date | 2018/08/01 |
| af\_destination\_a | User location | London |
| af\_destination\_b | Location of hotel | Madrid |
| af\_num\_adults | Number of guests | 2 |
| af\_num\_children | Number of children | 0 |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Content view (af_content_view)">

**Purpose**

This event can help you determine:

* Whether search results are relevant to search queries
* What property types users are looking for
* Seasonal trends
* Popular locations
* Which media sources bring users, and then retarget these users in ads and promotions

**Trigger**

When the user is viewing a property

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_price | List price of the hotel | 674 |
| af\_content\_id | ID of the hotel | ODIRNH |
| af\_date\_a | Check-in date | 2018/07/26 |
| af\_date\_b | Check-out date | 2018/08/01 |
| af\_destination\_a | User location | London |
| af\_destination\_b | Location of hotel | Madrid |
| af\_class | Room type | Deluxe |
| af\_num\_adults | Number of guests | 2 |
| af\_num\_children | Number of children | 0 |
| af\_hotel\_score | Hotel score by reviews | 9.6 |
| af\_preferred\_star\_ratings | Preferred hotel star rating | 5 |
| af\_preferred\_neighborhoods | Area in which the hotel is located | Centro |

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Add to wishlist (af_add_to_wishlist)">

**Purpose**

Record which hotels and destinations users are interested in booking. When you know, for example, which hotels, regions, and the star rating users are looking for, you can use this data to retarget users.

**Trigger**

When a user adds a listing to their wish list

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_price | List price of the hotel | 674 |
| af\_content\_id | ID of the hotel | ODIRNH |
| af\_date\_a | Check-in date | 2018/07/26 |
| af\_date\_b | Check-out date | 2018/08/01 |
| af\_destination\_a | User location | London |
| af\_destination\_b | Location of hotel | Madrid |
| af\_class | Room type | Deluxe |
| af\_num\_adults | Number of guests | 2 |
| af\_num\_children | Number of children | 0 |
| af\_hotel\_score | Hotel score by reviews | 9.6 |
| af\_preferred\_star\_ratings | Preferred hotel star rating | 5 |
| af\_preferred\_neighborhoods | Area in which the hotel is located | Centro |
| purchase\_method | Purchase method | Credit card |
| af\_coupon\_code | Promo code or loyalty reward points | SUM2018 |
| property\_type | Type of property | Hotel |

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="Initiated checkout (af_initiated_checkout)">

**Purpose**

Understand how buyers behave when they proceed to checkout. This event can help you determine:

* What purchase method was used, for example, credit card or eWallet
* Whether users finish the checkout process

**Trigger**

When the user adds their credit card information or connects their eWallet

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_price | List price of the hotel | 674 |
| af\_content\_id | ID of the hotel | ODIRNH |
| af\_date\_a | Check-in date | 2018/07/26 |
| af\_date\_b | Check-out date | 2018/08/01 |
| af\_destination\_a | User location | London |
| af\_destination\_b | Location of hotel | Madrid |
| af\_class | Room type | Deluxe |
| af\_num\_adults | Number of guests | 2 |
| af\_num\_children | Number of children | 0 |
| af\_hotel\_score | Hotel score by reviews | 9.6 |
| af\_preferred\_star\_ratings | Preferred hotel star rating | 5 |
| af\_preferred\_neighborhoods | Area in which the hotel is located | Centro |
| purchase\_method | Purchase method | Credit card |
| af\_coupon\_code | Promo code or loyalty reward points | SUM2018 |
| property\_type | Type of property | Hotel |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Purchase (af_purchase)">

**Purpose**

Learn about purchase trends in your hotel booking app. This event can help you:

* Determine the LTV of your users and the ROI of your campaigns across ad networks and ad agencies
* Determine what offers are most popular with your users
* Cross-reference campaigns with purchased items in order to optimize campaign targeting

**Trigger**

When the user lands on the thank you page after a successful purchase

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#revenue-in-in-app-events">af\_revenue</Anchor> | Estimated revenue from the purchase | 1205.99 |
| af\_price | Overall purchase sum | 4000 |
| af\_content\_id | Item ID | 121 |
| af\_content\_type | Item category | hotel |
| af\_currency | Currency code | AUD |
| af\_quantity | Number of items in the cart | 1 |
| af\_order\_id | ID of the order that is generated after the purchase | X123ABC |
| af\_receipt\_id | Order ID,  required for CRITEO and Google Ad Words retargeting integration | X123ABC |

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="Travel booking (af_travel_booking)">

**Purpose**

Determine the overall booking rate in your app. This event can help you:

* Record revenue generated from booking
* Determine the number of users that book hotels with kids
* Understand seasonal trends
* Determine popular hotels

**Trigger**

When the user reaches the thank you page after booking a hotel

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#revenue-in-in-app-events">af\_revenue</Anchor> | Revenue from booking | 647.95 |
| af\_currency | Currency code | GBP |
| af\_price | List price of the hotel | 674 |
| af\_content\_id | ID of the hotel | ODIRNH |
| af\_date\_a | 2018/07/26 | Check-in date |
| af\_date\_b | Check-out date | 2018/08/01 |
| af\_destination\_a | User location | London |
| af\_destination\_b | Location of hotel | Madrid |
| af\_class | Room type | Deluxe |
| af\_num\_adults | Number of guests | 2 |
| af\_num\_children | Number of children | 0 |
| af\_hotel\_score | Hotel score by reviews | 9.6 |
| af\_preferred\_star\_ratings | Preferred hotel star rating | 5 |
| af\_preferred\_neighborhoods | Area in which the hotel is located | Centro |
| purchase\_method | Purchase method | Credit card |
| af\_coupon\_code | Promo code or loyalty reward points | SUM2018 |
| property\_type | Type of property | Hotel |
| new\_booking | User's first booking | true |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Recommended structures for custom events

The following section provides a list of event structures that include custom event names and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="first-purchase-first_purchase" />

<Accordion title="First purchase (first_purchase)">

**Purpose**

Same as the [Purchase](/docs/recommended-hotel-booking-app-events#purchase-af_purchase) event. In addition, this event can help you determine:

* How long it takes a new buyer to purchase
* What products first-time buyers prefer to purchase
* The average price and revenue of first-time purchases

**Trigger**

When the user completes their first purchase

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#revenue-in-in-app-events">af\_revenue</Anchor> | Revenue from purchase | 1205.95 |
| af\_price | Overall purchase sum | 4000 |
| af\_content\_id | Item ID | 121, 262 |
| af\_content\_type | Item category | hotel |
| af\_currency | Currency | AUD |
| af\_quantity | Quantity of items in the cart | 1 |
| af\_order\_id | ID of the order that is generated after purchase | X123ABC |
| af\_receipt\_id | Order ID, required for CRITEO and Google AdWords retargeting integration | X123ABC |

</Accordion>

<div data-zendesk-anchors="hotel-booking=-hotel-booking h_01HGTB0APWWTRER6GAWJ7TJ05S=-hotel-booking h_01HGTB0APWQDX7VN96GM7520ZH=important h_01HGTB0APW933179Q90HFASW1V=recommended-structures-for-predefined-events h_01HGTB0APWRKRGCJ5TFKTPHH33=complete-registration-af_complete_registration h_01HGTB0APW1XY5R69CJ8PSQV6C=login-af_login h_01HGTB0APW5YF2DASC0HYDPTA9=search-af_search h_01HGTB0APXTQWBS4EXJ8D724G0=content-view-af_content_view h_01HGTB0APXS95QGK17RE8B3Y1E=add-to-wishlist-af_add_to_wishlist h_01HGTB0APX1XX2W3YX85W75F6B=initiated-checkout-af_initiated_checkout h_01HGTB0APXGPW16FRY3C7VSMDM=purchase-af_purchase h_01HGTB0APXJFHMPGYC63ZTV4R9=travel-booking-af_travel_booking h_01HGTB0APXP6WVM1AVEMEY6KVS=recommended-structures-for-custom-events h_01HGTB0APX4ND0NGVTK9FA38QR=first-purchase-first_purchase" />
