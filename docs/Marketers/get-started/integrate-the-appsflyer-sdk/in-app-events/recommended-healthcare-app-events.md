---
title: Recommended healthcare app events
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
  created_at: '2021-05-01T10:41:05Z'
  edited_at: '2023-12-04T11:47:58Z'
  id: 360019888518
  locale: en-us
  section: In-app events
  section_id: 6551285343761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360019888518-Recommended-healthcare-app-events
---
> **At a glance:** Measure the quality of your users throughout their user journey by recording these sample in-app events for your healthcare app.

<div id="-healthcare" />

## <Image alt="5669_Healthcare_icon_3.png" src="https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png" width="100px" /> Healthcare

Healthcare apps enable users to perform tasks such as purchasing health insurance, making appointments, and receiving medical advice. The typical events that are recorded include logins, registrations, and other general events with no personal or health information.

<div id="important" />

> 🚧 **Important!**
>
> * **A note from our lawyers**: Health data is considered "Restricted Data" and is considered a special category of data in many jurisdictions. As such, customers are prohibited from sending AppsFlyer any such data.
> * Make sure to read the <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#setting-up-in-app-events">instructions</Anchor> for marketers about implementing in-app events.
> * To streamline the implementation process, use our <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=healthcare">In-app event generator</Anchor>. This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=healthcare&view=code">code samples</Anchor> for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyer developer hub</Anchor>.
>
> For more information about recording in-app events, see the <Anchor target="_blank" href="/marketers/docs/in-app-events-overview">In-app events guide</Anchor>.

<Image align="center" alt="In_appEvents_UserJourneys_-_Copy_of_Healthcare__1_.png" src="https://files.readme.io/54174e697c8dfe2d0d388c19fdd5fa0fbf9703c0155b9c250b40b5d0bcf19698-8232949117073.png" />

<div id="recommended-structures-for-predefined-events" />

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the healthcare vertical. Each structure includes a predefined event name and the sample event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Purpose**

Understand the retention of your registered users

**Trigger**

Whenever the user successfully logs in

**Event parameters**

Can be sent without any additional parameters

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Complete registration (af_complete_registration)">

**Purpose**

Learn how many users installed the app and completed the signup process, and what signup methods your users prefer.

**Trigger**

When the user completes the signup process

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_registration\_method | Type of signup method | email, Facebook |

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="Add to cart (af_add_to_cart)">

**Purpose**

Record when a user adds a product to their cart. This event can help you determine:

* How many products on average buyers add in one purchase
* How much time passes between adding two different products
* How many buyers abandon their cart

**Trigger**

When the user adds a product to the cart

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_quantity | Amount ordered | 1 |
| af\_price | Price of the product | 10 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Purchase (af_purchase)">

**Purpose**

Record in-app purchases made by users. This event can help you:

* Determine the LTV of your users and the ROI of your campaigns across ad networks and ad agencies
* Determine what offers are most popular with your users
* Cross-reference campaigns with purchased items in order to optimize campaign targeting

**Trigger**

When the user lands on the thank you page after a successful purchase

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#revenue-in-in-app-events">af\_revenue</Anchor> | Revenue from the purchase | 50.55 |
| af\_currency | Currency code | USD |
| af\_order\_id | Order ID | 9277 |
| payment\_method\_type | Payment method used | credit card, local |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Recommended structures for custom events

The following section provides the event structure including the custom event name and sample event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="topup-success-top_up_success" />

<Accordion title="Top-up success (top_up_success)">

**Purpose**

Top-up funds can be used to buy any package or service offered inside the app. You can record this event and compare it with other data to learn more about your users. For example, you can learn what amounts people are willing to deposit into their accounts and use the top-up amounts to target users with customized campaigns within their top-up budgets.

**Trigger**

When the user completes the top-up

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#revenue-in-in-app-events">af\_revenue</Anchor> | Amount of the top-up | 2000.55 |
| top\_up\_id | ID of the top-up | 397 |
| payment\_method\_type | Payment method used | credit card, local payment |

</Accordion>

<div data-zendesk-anchors="healthcare=-healthcare h_01HGTAFRKKJ22SHB4JHMTGW2TV=-healthcare h_01HGTAFRKKPWC1PQTKF227WWBD=important h_01HGTAFRKKRB8EY8KJ9NXM4Z2T=recommended-structures-for-predefined-events h_01HGTAFRKK35Q5W5ADQC2KYHR9=login-af_login h_01HGTAFRKK8E52FRVWQXP4Y3VV=complete-registration-af_complete_registration h_01HGTAFRKN6NJPDB053YYYH202=add-to-cart-af_add_to_cart h_01HGTAFRKNJVFECSFGSWG8B7GN=purchase-af_purchase h_01HGTAFRKN29RJRW2V2WCH2AXT=recommended-structures-for-custom-events h_01HGTAFRKNDWHDDR9KDRKJ4H8E=topup-success-top_up_success" />
