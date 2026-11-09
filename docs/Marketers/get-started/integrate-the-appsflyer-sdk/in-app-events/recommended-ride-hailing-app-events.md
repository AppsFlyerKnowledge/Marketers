---
title: Recommended ride-hailing app events
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
  created_at: '2021-04-29T08:42:34Z'
  edited_at: '2023-12-04T11:56:22Z'
  id: 360019651957
  locale: en-us
  section: In-app events
  section_id: 6551285343761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360019651957-Recommended-ride-hailing-app-events
---
> **At a glance:** Measure the quality of your users throughout their user journey by recording these suggested in-app events for your ride-hailing app.

<div id="-ride-hailing" />

## <Image alt="InApp_Events_ride.png" src="https://files.readme.io/3901cfcc0cc821cc9c93edbe806bc2d570698be366b76b3710cb60e9aa190d91-20659532208401.png" width="100px" /> Ride-hailing

Ride-hailing has become very popular recently, especially in urban areas where most residents don't own a car. The typical events that we suggest recording are ride requests and bookings.

Recording events can help you determine:

* How passengers and drivers interact
* Countries where more people use your ride-hailing service
* Metrics about price, rides, and ride distance

<div id="important" />

> 🚧 **Important!**
>
> * Make sure to read the <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#setting-up-in-app-events">instructions</Anchor> for marketers about implementing in-app events.
> * To streamline the implementation process, use our <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ride_hailing">In-app event generator</Anchor>. This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ride_hailing&view=code">code samples</Anchor> for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyer developer hub</Anchor>.**
>
> For more information about recording in-app events, see the <Anchor target="_blank" href="/marketers/docs/in-app-events-overview">In-app events guide</Anchor>.

<Image align="center" alt="Flowchart_for_recommended_events_ride_hailing_app_user_journey" src="https://files.readme.io/5ec4efcc699ef8749e1d5cd6e693472713f3d7945a41e1601965d0e7cdb68706-4402678863377.png" />

<div id="recommended-structures-for-predefined-events" />

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the ride-hailing vertical. Each structure includes a predefined event name and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Complete registration (af_complete_registration)">

**Purpose**

This event can help you:

* Learn what sign-up method your users prefer
* Understand how many users actually sign up after downloading and installing the app
* See registration trends across countries to determine the countries whose users are most likely to use your app

**Trigger**

When the user completes the signup process

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_registration\_method | Platform or method through which the user signs up | Facebook |
| country\_code | Country code (phone code) | 66 |

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

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="Add payment info (af_add_payment_info)">

**Purpose**

Helps you categorize users. You can:

* Learn how long it takes a user to add their payment info
* What payment methods are most popular, for example, credit card or eWallets
* Set up campaigns and collaborate with popular payment method providers

**Trigger**

When the user successfully adds payment info to their account

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_success | Whether the payment method is successful | true |
| credit\_card\_type | Credit card type (optional) | Visa, Mastercard |
| payment\_method\_type | Type of payment method | credit card, eWallet |

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="Spent credits (af_spent_credits)">

**Purpose**

The [Ride booking completed event](/docs/recommended-ride-hailing-app-events#ride-booking-completed-ride_booking_completed) includes a parameter named `credits_earned`. This parameter logs the credits that a passenger earns for each ride. Passengers can trade credits for vouchers and discounts.

This event can help you:

* See how many passenger trade credits for vouchers
* See what sort of vouchers and discounts passengers prefer

**Trigger**

When a passenger spends credits

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_content | Type of voucher or discount | Single movie ticket |
| credits\_used | How many credits used | 1000 |
| credits\_remaining | How many credits left in the account | 2090 |
| invoice\_id | ID of the invoice that is created for spending credits | KO215123SD |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Recommended structures for custom events

The following section provides a list of event structures that include custom event names and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="ride-booking-requested-ride_booking_requested" />

<Accordion title="Ride booking requested (ride_booking_requested)">

**Purpose**

This event can help you:

* Learn about popular destinations
* Learn about trends, where people ride to and from where
* See the average distance of a ride
* See what cities, regions, and countries most users come from

In addition, recording this event along with the other booking-related events can help you record successful transactions. Then, you can compare successful transactions with unsuccessful transactions. For example, you can see how many ride bookings are requested and how many ride bookings are completed or canceled.

**Trigger**

When the passenger created a ride-booking request

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_price | Quoted price for the ride | 22.4 |
| af\_currency | Currency | SGD |
| af\_destination\_a | Point of departure | Plaza Singapura |
| af\_destination\_b | Point of arrival | Marina Bay Sands |
| distance | Distance between the two destinations | 5.2 |
| af\_content\_type | Type of transportation | Taxi |
| payment\_method\_type | Type of payment method | credit card, eWallet |
| af\_city | City where the ride is booked | Singapore |
| af\_region | Region where the ride is booked | SFA |
| af\_country | Country where the ride is booked | Singapore |
| order\_id | Order ID | 135790 |

</Accordion>

<div id="ride-booking-confirmed-ride_booking_confirmed" />

<Accordion title="Ride booking confirmed (ride_booking_confirmed)">

**Purpose**

This event can help you:

* Learn who the most active drivers are
* See what destinations are common among drivers
* See the average and overall ride prices for each driver

In addition, recording this event along with the other three booking-related events can help you better understand driver activity. You can see, for example, which drivers confirm the most ride-booking requests, and which drivers choose short rides as opposed to long rides.

<div id="trigger" />

#### **Trigger**

When the booking is accepted by a driver

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_price | Quoted price for the ride | 22.4 |
| af\_currency | Currency | SGD |
| af\_destination\_a | Point of departure | Plaza Singapura |
| af\_destination\_b | Point of arrival | Marina Bay Sands |
| distance | Distance between the two destinations | 5.2 |
| af\_content\_type | Type of transportation | Taxi |
| driver\_id | ID of the driver who confirmed performing the ride | 1706 |
| payment\_method\_type | Type of payment method | credit card, eWallet |
| af\_city | City where the ride is booked | Singapore |
| af\_region | Region where the ride is booked | SFA |
| af\_country | Country where the ride is booked | Singapore |
| af\_order\_id | Order ID | 135790 |

</Accordion>

<div id="ride-booking-canceled-ride_booking_canceled" />

<Accordion title="Ride booking canceled (ride_booking_canceled)">

**Purpose**

This event can help you:

* Log drivers or passengers that constantly cancel
* Learn how many rides are canceled
* Correlate cancellation rate with attributes such as price, destination, distance, and cities
* Learn the reasons why a ride is canceled

**Trigger**

When the booking is canceled

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_price | Quoted price for the ride | 22.4 |
| af\_currency | Currency | SGD |
| af\_destination\_a | Point of departure | Plaza Singapura |
| af\_destination\_b | Point of arrival | Marina Bay Sands |
| distance | Distance between the two destinations | 5.2 |
| af\_content\_type | Type of transportation | Taxi |
| driver\_id | ID of the driver who confirmed the ride | 1706 |
| cancelation\_reason | Reason the ride is canceled | price is too high, driver didn't show up, passenger didn't show up |
| payment\_method\_type | Type of payment method | credit card, eWallet |
| af\_city | City where the ride is booked | Singapore |
| af\_region | Region where the ride is booked | SFA |
| af\_country | Country where the ride is booked | Singapore |
| order\_id | Order ID | 135790 |
| canceled\_by | Whether the ride is canceled by the passenger or driver | Passenger |

</Accordion>

<div id="ride-booking-completed-ride_booking_completed" />

<Accordion title="Ride booking completed (ride_booking_completed)">

**Purpose**

This event can help you:

* Learn about passenger spending and driver earnings
* Correlate completed rides with attributes such as destination, distance, payment type, and driver ID
* See the average and overall distance for drivers and passengers
* Compare completed rides with canceled ones
* Log and record the score of drivers

**Trigger**

When the journey is complete

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_price | Quoted price for the ride | 22.4 |
| af\_currency | Currency | SGD |
| af\_destination\_a | Point of departure | Plaza Singapura |
| af\_destination\_b | Point of arrival | Marina Bay Sands |
| distance | Distance between the two destinations | 5.2 |
| af\_content\_type | Type of transportation | Taxi |
| driver\_id | ID of the driver who confirmed performing the ride | 1706 |
| payment\_method\_type | Type of payment method | credit card, eWallet |
| af\_city | City where the ride is booked | Singapore |
| af\_region | Region where the ride is booked | SFA |
| af\_country | Country where the ride is booked | Singapore |
| order\_id | Order ID | 135790 |
| credits\_earned | Credits that the passenger earned for completing a ride | 248 |

</Accordion>

<div data-zendesk-anchors="ridehailing=-ride-hailing h_01HGTAZ7J64RZE35JP8XPKMTPZ=-ride-hailing h_01HGTAZ7J6N36EH492QDXCQYB1=important h_01HGTAZ7J6FJ8R9VXKK0F1A1E1=recommended-structures-for-predefined-events h_01HGTAZ7J6FQQKV7JB0Z9MG8CD=complete-registration-af_complete_registration h_01HGTAZ7J6YM8DJ96E7Q4M4Y8Q=login-af_login h_01HGTAZ7J67MNJ8T9B9W4NJ5Y9=add-payment-info-af_add_payment_info h_01HGTAZ7J6Z3EX03JTPZFHJJF6=spent-credits-af_spent_credits h_01HGTAZ7J6Z6NE8D5A10CRJJH4=recommended-structures-for-custom-events h_01HGTAZ7J6WCY2BQJPSNSTJRQ0=ride-booking-requested-ride_booking_requested h_01HGTAZ7J78J1X3VAYMH8Q3ZBA=ride-booking-confirmed-ride_booking_confirmed h_01HGTAZ7J7C4R7A7KT2S95835J=trigger h_01HGTAZ7J797KA791H1621F9TE=ride-booking-canceled-ride_booking_canceled h_01HGTAZ7J789CJ8P6X8B0V7A64=ride-booking-completed-ride_booking_completed" />
