---
title: "Recommended ride-hailing app events"
excerpt: "Measure the quality of your users throughout their user journey by recording these suggested in-app events for your ride-hailing app."
---
Ride-hailing has become very popular recently, especially in urban areas where most residents don't own a car. The typical events that we suggest recording are ride requests and bookings.

Recording events can help you determine:

- How passengers and drivers interact
- Countries where more people use your ride-hailing service
- Metrics about price, rides, and ride distance

> 📘 Important!
>
> * Make sure to read the [instructions](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-guide#setting-up-inapp-events) for marketers about implementing in-app events.
> * To streamline the implementation process, use our [In-app event generator](http://evgen.appsflyer.com/?vertical=ride_hailing). This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are [code samples](http://evgen.appsflyer.com/?vertical=ride_hailing&view=code) for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the **[AppsFlyer developer hub](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions).**

For more information about recording in-app events, see the [In-app events guide](https://support.appsflyer.com/hc/articles/115005544169).

![Flowchart_for_recommended_events_ride_hailing_app_user_journey](https://files.readme.io/5ec4efcc699ef8749e1d5cd6e693472713f3d7945a41e1601965d0e7cdb68706-4402678863377.png)

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the ride-hailing vertical. Each structure includes a predefined event name and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

### Complete registration (af\_complete\_registration)

**Purpose**

This event can help you:

- Learn what sign-up method your users prefer
- Understand how many users actually sign up after downloading and installing the app
- See registration trends across countries to determine the countries whose users are most likely to use your app

**Trigger**

When the user completes the signup process

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_registration\_method | Platform or method through which the user signs up | Facebook |
| country\_code | Country code (phone code) | 66 |

### Login (af\_login)

**Purpose**

Understand the retention of your registered users

**Trigger**

When the user successfully logs in

**Event parameters**

Can be sent without any additional parameters

### Add payment info (af\_add\_payment\_info)

**Purpose**

Helps you categorize users. You can:

- Learn how long it takes a user to add their payment info
- What payment methods are most popular, for example, credit card or eWallets
- Set up campaigns and collaborate with popular payment method providers

**Trigger**

When the user successfully adds payment info to their account

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_success | Whether the payment method is successful | true |
| credit\_card\_type | Credit card type (optional) | Visa, Mastercard |
| payment\_method\_type | Type of payment method | credit card, eWallet |

### Spent credits (af\_spent\_credits)

**Purpose**

The [Ride booking completed event](https://support.appsflyer.com/hc/articles/360019651957#ride-booking-completed-ride_booking_completed) includes a parameter named `credits_earned`. This parameter logs the credits that a passenger earns for each ride. Passengers can trade credits for vouchers and discounts.

This event can help you:

- See how many passenger trade credits for vouchers
- See what sort of vouchers and discounts passengers prefer

**Trigger**

When a passenger spends credits

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_content | Type of voucher or discount | Single movie ticket |
| credits\_used | How many credits used | 1000 |
| credits\_remaining | How many credits left in the account | 2090 |
| invoice\_id | ID of the invoice that is created for spending credits | KO215123SD |

## Recommended structures for custom events

The following section provides a list of event structures that include custom event names and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

### Ride booking requested (ride\_booking\_requested)

**Purpose**

This event can help you:

- Learn about popular destinations
- Learn about trends, where people ride to and from where
- See the average distance of a ride
- See what cities, regions, and countries most users come from

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

### Ride booking confirmed (ride\_booking\_confirmed)

**Purpose**

This event can help you:

- Learn who the most active drivers are
- See what destinations are common among drivers
- See the average and overall ride prices for each driver

In addition, recording this event along with the other three booking-related events can help you better understand driver activity. You can see, for example, which drivers confirm the most ride-booking requests, and which drivers choose short rides as opposed to long rides.

**Trigger**

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

### Ride booking canceled (ride\_booking\_canceled)

**Purpose**

This event can help you:

- Log drivers or passengers that constantly cancel
- Learn how many rides are canceled
- Correlate cancellation rate with attributes such as price, destination, distance, and cities
- Learn the reasons why a ride is canceled

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

### Ride booking completed (ride\_booking\_completed)

**Purpose**

This event can help you:

- Learn about passenger spending and driver earnings
- Correlate completed rides with attributes such as destination, distance, payment type, and driver ID
- See the average and overall distance for drivers and passengers
- Compare completed rides with canceled ones
- Log and record the score of drivers

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