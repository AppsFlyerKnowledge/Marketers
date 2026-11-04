---
title: Recommended telecommunication app events
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
  created_at: '2021-05-02T11:59:16Z'
  edited_at: '2023-12-04T11:48:21Z'
  id: 360019896558
  locale: en-us
  section: In-app events
  section_id: 6551285343761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360019896558-Recommended-telecommunication-app-events
---
> **At a glance:** Measure the quality of your users throughout their user journey by recording these suggested in-app events for your telecommunication app.

<div id="-telecommunication" />

## <Image alt="telecommunications_icon.png" src="https://files.readme.io/42f1aac3b825957d9d0584d83480c441b9d53665cc6cf1a6b8cd1803bb9b6121-20659194885393.png" width="100px" /> Telecommunication

Telecommunication apps enable users to purchase and manage cell phone plans, data plans, and so on. The typical events that we suggest recording include purchases, top-ups, and subscriptions.

Recording these events can help you determine:

* Which gateway plans are most popular
* What products or packages users can afford
* Which plans are most likely to get long-term commitments from customers

<div id="important" />

> 🚧 **Important!**
>
> * Make sure to read the <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#setting-up-in-app-events">instructions</Anchor> for marketers about implementing in-app events.
> * To streamline the implementation process, use our <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=telecommunication">In-app event generator</Anchor>. This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=telecommunication&view=code">code samples</Anchor> for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyer developer hub</Anchor>.**
>
> For more information about recording in-app events, see the <Anchor target="_blank" href="/marketers/docs/in-app-events-overview">In-app events guide</Anchor>.

[![Flowchart_for_recommended_events_telecommunication_app_user_journey](https://files.readme.io/ae4c696208b49aa546ffc0a15f76b148b35af43984a76e699d1df7c54507352c-4404604045457.png)](https://files.readme.io/ae4c696208b49aa546ffc0a15f76b148b35af43984a76e699d1df7c54507352c-4404604045457.png)

<div id="recommended-structures-for-predefined-events" />

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the telecommunication vertical. Each structure includes a predefined event name and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs

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

<div id="content-view-af_content_view" />

<Accordion title="Content view (af_content_view)">

**Purpose**

Determine the view rate of specific products and:

* Correlate product views with product sales
* Understand what categories are the most popular according to product views
* See the correlation between buyers' currency and the products that they view

**Trigger**

When the user views a specific product details page

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_price | Product price | 200 |
| af\_content\_id | Product ID | 102 |
| af\_content\_type | Product category | Internet packages |
| af\_currency | Currency in the product details page | THB, USD |

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="List view (af_list_view)">

**Purpose**

Record which lists (for example, newly added products, related products, or recommended products) buyers view the most.

**Trigger**

When the user views a specific list

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_content\_type | Type of list | Related, recommended, new arrivals |
| af\_content\_list | List of content IDs from the category | 001, 092 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Purchase (af_purchase)">

**Purpose**

Many telecommunications apps allow users to purchase items such as extra data. Recording this event can help you:

* Determine the LTV of your users and the ROI of your campaigns across ad networks and ad agencies
* Determine what offers are most popular with your users
* Cross-reference campaigns with purchased items in order to optimize campaign targeting

**Trigger**

When the user lands on the thank you page after a successful purchase

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#revenue-in-in-app-events">af\_revenue</Anchor> | Estimated revenue from the purchase | 2050.50 |
| af\_currency | Currency code | THB |
| af\_content\_type | Name of the package bought | 5G |
| af\_order\_id | Order ID | 9277 |
| payment\_method\_type | Type of payment method | credit card, local payment |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Recommended structures for custom events

The following section provides an event structure that includes a custom event name and the suggested event parameter to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="select-package-select_package" />

<Accordion title="Select package (select_package)">

**Purpose**

Record when a user decides to buy a package but has not made the payment yet. You can use this data, for example, to retarget users and send them offers about other services.

**Trigger**

When the user selects a package but has not completed the payment

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| price | Price of the subscription | 50000 |
| af\_content\_type | Type of content the user selected | Data 5 GB |

</Accordion>

<div id="topup-success-top_up_success" />

<Accordion title="Top-up success (top_up_success)">

**Purpose**

Top-up funds can be used to buy any package or any other service offered inside the app. Record this event and compare it with other data to learn more about your users. For example, you can learn what amounts users are willing to deposit into their accounts, and then use the top-up amounts to target them with customized campaigns within their budgets.

**Trigger**

When the user completes the top-up

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#revenue-in-in-app-events">af\_revenue</Anchor> | Amount of the top-up | 2050.50 |
| top\_up\_id | ID of the top-up | 397 |
| payment\_method\_type | Type of payment method | credit card, local payment |

</Accordion>

<div id="topup-unsuccessful-top_up_unsuccessful" />

<Accordion title="Top-up unsuccessful (top_up_unsuccessful)">

**Purpose**

Record this event and compare it with other data to learn more about your users. For example, you can learn how many users try to top-up but fail.

**Trigger**

When the user tries to top up but the action fails

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| error\_reason | Reason for the top-up failure | exceeded\_daily\_limit |

</Accordion>

<div id="subscription-complete-subscription_complete" />

<Accordion title="Subscription complete (subscription_complete)">

**Purpose**

Recording this event can help you:

* See which campaigns bring users that subscribe
* Compare the number of subscribed users against unsubscribed users
* Record revenue generated from subscriptions and attribute it to campaigns and media sources

**Trigger**

* When the user successfully subscribes
* When a subscription is renewed

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| subscription\_type | Type of subscription | Monthly 30 GB |
| <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#revenue-in-in-app-events">af\_revenue</Anchor> | Amount of the subscription | 555.50 |

</Accordion>

<div data-zendesk-anchors="telecommunication=-telecommunication h_01HGTAGFNFWKWYHPG6F5EK17YD=-telecommunication h_01HGTAGFNG1Z8NAFJ71DP0YSYD=important h_01HGTAGFNG99PQC03F13WQ4CVK=recommended-structures-for-predefined-events h_01HGTAGFNGQ56C8CN7A325SQ7M=login-af_login h_01HGTAGFNG1W5QWGN1D969JHGY=complete-registration-af_complete_registration h_01HGTAGFNGRJHD89332473DZFE=content-view-af_content_view h_01HGTAGFNG10GNZVMDNXRJSYJ9=list-view-af_list_view h_01HGTAGFNGV82NQSZ29B96YJCQ=purchase-af_purchase h_01HGTAGFNG3A2A6KCX8GGQAJBX=recommended-structures-for-custom-events h_01HGTAGFNGE3MKZEDKDZ0B9XDD=select-package-select_package h_01HGTAGFNGFSE2DAYRGG039GT9=topup-success-top_up_success h_01HGTAGFNGXBBYWJEMBVMN1YQS=topup-unsuccessful-top_up_unsuccessful h_01HGTAGFNGT3CJFRS2YC7R57KG=subscription-complete-subscription_complete" />
