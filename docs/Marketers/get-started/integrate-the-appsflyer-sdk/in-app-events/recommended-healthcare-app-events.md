---
title: "Recommended healthcare app events"
excerpt: "Measure the quality of your users throughout their user journey by recording these sample in-app events for your healthcare app."
---
## ![Healthcare](https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png) Healthcare

Healthcare apps enable users to perform tasks such as purchasing health insurance, making appointments, and receiving medical advice. The typical events that are recorded include logins, registrations, and other general events with no personal or health information.

> ❗️ Important!
>
> * **A note from our lawyers**: Health data is considered "Restricted Data" and is considered a special category of data in many jurisdictions. As such, customers are prohibited from sending AppsFlyer any such data.
> * Make sure to read the [instructions](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-guide#setting-up-inapp-events) for marketers about implementing in-app events.
> * To streamline the implementation process, use our [In-app event generator](https://evgen.appsflyer.com/?vertical=healthcare). This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are [code samples](https://evgen.appsflyer.com/?vertical=healthcare&view=code) for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the [AppsFlyer developer hub](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions).

For more information about recording in-app events, see the [In-app events guide](https://support.appsflyer.com/hc/articles/115005544169).

![In_appEvents_UserJourneys_-_Copy_of_Healthcare__1_.png](https://files.readme.io/54174e697c8dfe2d0d388c19fdd5fa0fbf9703c0155b9c250b40b5d0bcf19698-8232949117073.png)

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the healthcare vertical. Each structure includes a predefined event name and the sample event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

### Login (af\_login)

**Purpose**

Understand the retention of your registered users

**Trigger**

Whenever the user successfully logs in

**Event parameters**

Can be sent without any additional parameters

### Complete registration (af\_complete\_registration)

**Purpose**

Learn how many users installed the app and completed the signup process, and what signup methods your users prefer.

**Trigger**

When the user completes the signup process

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_registration\_method | Type of signup method | email, Facebook |

### Add to cart (af\_add\_to\_cart)

**Purpose**

Record when a user adds a product to their cart. This event can help you determine:

- How many products on average buyers add in one purchase
- How much time passes between adding two different products
- How many buyers abandon their cart

**Trigger**

When the user adds a product to the cart

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_quantity | Amount ordered | 1 |
| af\_price | Price of the product | 10 |

### Purchase (af\_purchase)

**Purpose**

Record in-app purchases made by users. This event can help you:

- Determine the LTV of your users and the ROI of your campaigns across ad networks and ad agencies
- Determine what offers are most popular with your users
- Cross-reference campaigns with purchased items in order to optimize campaign targeting

**Trigger**

When the user lands on the thank you page after a successful purchase

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| [af\_revenue](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-Overview#revenue-events) | Revenue from the purchase | 50.55 |
| af\_currency | Currency code | USD |
| af\_order\_id | Order ID | 9277 |
| payment\_method\_type | Payment method used | credit card, local |

## Recommended structures for custom events

The following section provides the event structure including the custom event name and sample event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

### Top-up success (top\_up\_success)

**Purpose**

Top-up funds can be used to buy any package or service offered inside the app. You can record this event and compare it with other data to learn more about your users. For example, you can learn what amounts people are willing to deposit into their accounts and use the top-up amounts to target users with customized campaigns within their top-up budgets.

**Trigger**

When the user completes the top-up

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| [af\_revenue](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-Overview#revenue-events) | Amount of the top-up | 2000.55 |
| top\_up\_id | ID of the top-up | 397 |
| payment\_method\_type | Payment method used | credit card, local payment |