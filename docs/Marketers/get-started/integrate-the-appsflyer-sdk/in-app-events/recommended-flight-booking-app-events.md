---
title: "Recommended flight booking app events"
excerpt: "Measure the quality of your users throughout their user journey by recording these suggested in-app events for your flight booking app."
---
## ![InApp_Events_flight.png](https://files.readme.io/7a09c4a641dd5e797bffc41a6e66b20efe5660721f37abac3dd12ac83688b37b-20659533911697.png) Flight booking

Flight booking apps allow travelers to easily book flights while choosing from the best offers. The typical events that we suggest recording are booking a flight, searching for flights, and viewing offers.

Recording events can help you:

- Learn about popular destinations
- Analyze seasonal trends
- Learn about popular airlines that users prefer to travel with

> 📘 Important!
>
> * Make sure to read the [instructions](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-guide#setting-up-inapp-events) for marketers about implementing in-app events.
> * To streamline the implementation process, use our [In-app event generator](http://evgen.appsflyer.com/?vertical=flight_booking). This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are [code samples](http://evgen.appsflyer.com/?vertical=flight_booking&view=code) for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the **[AppsFlyer developer hub](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions).**

For more information about recording in-app events, see the [In-app events guide](https://support.appsflyer.com/hc/articles/115005544169).

![Flowchart_for_recommended_events flight_booking_app_user_journey](https://files.readme.io/435378707a7299a8c98bc7490f0f1554b5f6c332a35c1546ce34feb1b6b86394-360020171258.png)

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the flight booking vertical. Each structure includes a predefined event name and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

### Complete registration (af\_complete\_registration)

**Purpose**

Learn how many users installed the app and completed the signup process, what signup methods your users prefer.

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

### Travel booking (af\_travel\_booking)

**Purpose**

The ability to book flights is the core function of the app. This event can help you determine:

- Popular destinations
- Popular airlines
- Seasonal trends

**Trigger**

When the user lands on the thank you page after successfully booking a flight

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| [af\_revenue](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-Overview#revenue-events) | Revenue associated with booking | 647.99 |
| af\_currency | Currency code | SGD |
| af\_price | Price | 674 |
| af\_content\_id | ID of the flight offer | ODIRNH |
| af\_departing\_departure\_date | Departure date | 2018-06-21 |
| af\_returning\_departure\_date | Return date | 2018-06-26 |
| af\_destination\_a | First destination | BKK |
| af\_destination\_b | Second destination (if applicable) | SYD |
| airline\_code | Code of the airline company | KLM |
| af\_class | Class the flight is booked to | economy |
| purchase\_method | Method used for the purchase | credit card |

### Content view (af\_content\_view)

**Purpose**

This event can help you determine:

- What flight offers users find most appealing
- Whether search results are relevant to search queries

**Trigger**

When a user clicks a search result

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_departing\_departure\_date | Departure date | 2018-06-21 |
| af\_returning\_departure\_date | Return date | 2018-06-26 |
| af\_destination\_a | First destination | BKK |
| af\_destination\_b | Second destination (if applicable) | SYD |

### Search (af\_search)

**Purpose**

Flight booking apps let users search for flights and deals. One way of gaining insights into user preferences is to record the search parameters. This event can help you:

- Learn what users are looking for
- Understand which destinations are most popular
- See how many users travel with kids
- See what time of the year users prefer or plan to travel

**Trigger**

After the user fills in the search form and clicks the search button

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_num\_children | Number of children that are traveling | 0 |
| af\_destination\_a | First destination | BKK |
| af\_destination\_b | Second destination (if relevant) | SYD |
| af\_departing\_departure\_date | Departure date | 2018-06-21 |
| af\_returning\_departure\_date | Return date | 2018-06-26 |
| af\_num\_infants | Number of infants that are traveling | 0 |
| af\_num\_adults | Number of  adults that are traveling | 1 |

### Add payment info (af\_add\_payment\_info)

**Purpose**

Record successful and unsuccessful attempts at adding payment info when booking a flight.

**Trigger**

When a user clicks on the book a flight button

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_success | Whether adding payment method is successful | true |

### Purchase (af\_purchase)

**Purpose**

Learn about purchase trends in your flight booking app. This event can help you:

- Determine the LTV of your users and the ROI of your campaigns across ad networks and ad agencies
- Determine what offers are most popular with your users
- Cross-reference campaigns with purchased items in order to optimize campaign targeting

**Trigger**

When the user lands on the thank you page after a successful purchase

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| [af\_revenue](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-Overview#revenue-events) | Estimated revenue from the purchase | 1205.99 |
| af\_price | Overall purchase sum | 4000 |
| af\_content\_id | Item ID | 121 |
| af\_content\_type | Item category | flight |
| af\_currency | Currency code | AUD |
| af\_quantity | Number of items in the cart | 1 |
| af\_order\_id | ID of the order that is generated after the purchase | X123ABC |
| af\_receipt\_id | Order ID, required for CRITEO and Google Ad Words retargeting integration | X123ABC |

## Recommended structures for custom events

The following section provides a list of event structures that include custom event names and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

### First purchase (first\_purchase)

**Purpose**

Same as the [Purchase](https://support.appsflyer.com/hc/articles/360019670857--WIP-Recommended-events-for-flight-booking-apps#purchase-af_purchase) event. In addition, this event can help you determine:

- How long it takes a new buyer to purchase
- What flights first-time buyers prefer to purchase
- The average price and revenue of first-time purchases

**Trigger**

When the user completes their first purchase

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| [af\_revenue](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-Overview#revenue-events) | Revenue from purchase | 1205.99 |
| af\_price | Overall purchase sum | 4000 |
| af\_content\_id | Item ID | 121, 262 |
| af\_content\_type | Item category | flight |
| af\_currency | Currency | AUD |
| af\_quantity | Quantity of items in the cart | 1 |
| af\_order\_id | ID of the order that is generated after purchase | X123ABC |
| af\_receipt\_id | Order ID, required for CRITEO and Google AdWords retargeting integration | X123ABC |