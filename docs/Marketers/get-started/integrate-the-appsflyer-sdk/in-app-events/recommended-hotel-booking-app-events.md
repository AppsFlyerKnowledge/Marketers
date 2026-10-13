---
title: "Recommended hotel booking app events"
excerpt: "Measure the quality of your users throughout their user journey by recording these suggested in-app events for your hotel booking app ."
x-zendesk:
  id: 360019843558
  url: https://support.appsflyer.com/hc/en-us/articles/360019843558-Recommended-hotel-booking-app-events
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: In-app events
  section_id: 6551285343761
  position: 16
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [Advertisers, Developers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-04-29T14:49:54Z'
  edited_at: '2023-12-04T11:56:58Z'
---
## ![InApp_Events_hotel.png](https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png) Hotel booking

Hotel booking apps allow travelers to easily book hotels while choosing from the best offers. The typical events that we suggest recording are search, purchase, travel booking, and add to wishlist.

Recording events can help you determine:

* Which campaigns and media sources bring users that actually book vacations
* Which campaigns and media sources bring the users that book the most and generate more revenue

You can attribute preferences such as hotel score, season, country, and the number of kids to users that come from certain media sources. Then, you can optimize your campaigns by targeting these user preferences.

> 📘 **Important!**
>
> * Make sure to read the [instructions](/docs/in-app-events-overview#setting-up-inapp-events) for marketers about implementing in-app events.
> * To streamline the implementation process, use our [In-app event generator](http://evgen.appsflyer.com/?vertical=hotel_booking). This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are [code samples](http://evgen.appsflyer.com/?vertical=hotel_booking&view=code) for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the  **[AppsFlyer developer hub](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions).**
>
> For more information about recording in-app events, see the [In-app events guide](/docs/in-app-events-overview).


[![Flowchart_for_recommended_events_hotel_booking_app_user_journey](https://files.readme.io/f425bc8865d731eb4934b6f32123156c7016ea1f75472e8878e76636aa593073-4402679204241.png)](https://files.readme.io/f425bc8865d731eb4934b6f32123156c7016ea1f75472e8878e76636aa593073-4402679204241.png)

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the hotel booking vertical. Each structure includes a predefined event name and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

### Complete registration (af\_complete\_registration)

**Purpose**

Learn how many users installed the app and completed the signup process, what signup methods your users prefer, and which media sources bring users that actually sign up.

**Trigger**

When the user completes the signup process

Event parameters



| Field name | Description | Example value |
| --- | --- | --- |
| af\_registration\_method | Type of signup method | email, Facebook |



### Login (af\_login)

**Purpose**

Understand the retention of your registered users

**Trigger**

When the user successfully logs in

**Event parameters**

Can be sent without any additional parameters

### Search (af\_search)

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



### Content view (af\_content\_view)

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



### Add to wishlist (af\_add\_to\_wishlist)

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



### Initiated checkout (af\_initiated\_checkout)

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



### Purchase (af\_purchase)

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
| [af\_revenue](/docs/in-app-events-overview#revenue-events) | Estimated revenue from the purchase | 1205.99 |
| af\_price | Overall purchase sum | 4000 |
| af\_content\_id | Item ID | 121 |
| af\_content\_type | Item category | hotel |
| af\_currency | Currency code | AUD |
| af\_quantity | Number of items in the cart | 1 |
| af\_order\_id | ID of the order that is generated after the purchase | X123ABC |
| af\_receipt\_id | Order ID,  required for CRITEO and Google Ad Words retargeting integration | X123ABC |



### Travel booking (af\_travel\_booking)

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
| [af\_revenue](/docs/in-app-events-overview#revenue-events) | Revenue from booking | 647.95 |
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



## Recommended structures for custom events

The following section provides a list of event structures that include custom event names and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

### First purchase (first\_purchase)

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
| [af\_revenue](/docs/in-app-events-overview#revenue-events) | Revenue from purchase | 1205.95 |
| af\_price | Overall purchase sum | 4000 |
| af\_content\_id | Item ID | 121, 262 |
| af\_content\_type | Item category | hotel |
| af\_currency | Currency | AUD |
| af\_quantity | Quantity of items in the cart | 1 |
| af\_order\_id | ID of the order that is generated after purchase | X123ABC |
| af\_receipt\_id | Order ID, required for CRITEO and Google AdWords retargeting integration | X123ABC |