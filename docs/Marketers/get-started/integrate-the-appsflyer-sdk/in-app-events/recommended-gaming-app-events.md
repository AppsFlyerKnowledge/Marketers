---
title: Recommended gaming app events
excerpt: >-
  Measure the quality of your users throughout their user journey by recording
  these suggested in-app events for your gaming app.
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2021-04-06T14:46:54Z'
  edited_at: '2026-02-25T13:58:31Z'
  id: 360018941117
  locale: en-us
  section: In-app events
  section_id: 6551285343761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360018941117-Recommended-gaming-app-events
---
## ![InApp_Events_games.png](https://files.readme.io/ee2d46ddf11a6a6cacc95399ffd778d6613ecdd905d237cd971073e095cada5b-20659444711953.png) Gaming

Gaming apps include games such as arcade, strategy, educational games, and gambling. The typical events that we suggest recording are in-app purchases, sharing on social media, and inviting friends. In addition, you can include events such as leveling up and completing an in-game tutorial.

Recording events can help you determine:

* What offers users purchase the most
* How engaged users are
* How many users post shares on social media
* How many users invite friends to install the app

These events are also relevant for gaming apps that run on the following platforms:

* Android Smart TV
* Apple TV (tvOS)
* Amazon Fire TV
* Xbox
* Windows mobile devices

> 📘 **Important!**
>
> * Make sure to read the [instructions](/docs/in-app-events-overview#setting-up-in-app-events) for marketers about implementing in-app events.
> * To streamline the implementation process, use our [In-app event generator](http://evgen.appsflyer.com/?vertical=gaming). This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are [code samples](http://evgen.appsflyer.com/?vertical=gaming&view=code) for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the [**AppsFlyer developer hub**](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions).
>
> For more information about recording in-app events, see the [In-app events guide](/docs/in-app-events-overview).

[![Flowchart_for_recommended_events gaming_app_user_journey](https://files.readme.io/18546b2ca811e534d7b15527d3dadb4750edd8e985154543fa156216ad023f78-360020169778.png)](https://files.readme.io/18546b2ca811e534d7b15527d3dadb4750edd8e985154543fa156216ad023f78-360020169778.png)

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the gaming vertical. Each structure includes a predefined event name and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

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

<div id="purchase-af_purchase" />

<Accordion title="Purchase (af_purchase)">

**Purpose**

Many gaming apps allow users to purchase items, for example, coins, gems, or weapons. Recording these purchases can help you:

* Determine the LTV of your users and the ROI of your campaigns across ad networks and ad agencies
* Determine what offers are most popular with your users
* Cross-reference campaigns with purchased items in order to optimize campaign targeting

To record and validate this event, see [Purchase and subscription validation](/docs/purchase-and-subscription-validation-overview).

**Trigger**

When the user lands on the thank you page after a successful purchase

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| [af\_revenue](/docs/in-app-events-overview#revenue-in-in-app-events) | Estimated revenue from the purchase | 199.99 |
| af\_currency | Currency code | THB, USD |
| af\_quantity | Number of items purchased | 2 |
| af\_content\_id | Item ID | 001, 092 |
| af\_order\_id | Order ID | 9277 |
| af\_receipt\_id | Receipt ID | 9277 |

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="Level achieved (af_level_achieved)">

**Purpose**

One of the main goals of users is to level up in games. Leveling up often unlocks new features and stages in the game and this encourages users to keep playing. Recording the level of achievement can help you:

* Determine which campaigns generate the most active users
* See what type of users are most active and engaged
* Associate overall user activity with dimensions such as revenue

**Trigger**

When the user lands on the level completion page

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_level | Level the user achieved | 3 |
| af\_score | Score associated with user's achievement | 500 |

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="Tutorial completion (af_tutorial_completion)">

**Purpose**

Tutorials provide your users with guidance on how to use the app. Recording this event can help you determine:

* What topics users might have trouble with
* What tutorials are not performing well

**Trigger**

* When a user completes the tutorial
* When a user starts the tutorial but quits without completing it

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_success | Whether the user completed the tutorial | true |
| af\_tutorial\_id | Tutorial ID | 3 |
| af\_content | Tutorial name | Getting started |

</Accordion>

<div id="share-af_share" />

<Accordion title="Share (af_share)">

**Purpose**

Users like to share their achievements in games on social media sites. Sharing creates brand awareness and can drive more users to download and install your app. Recording this event can help you understand when users are most likely to share the app with their friends. Learn more about [recording shares and invites](/docs/user-invite-attribution).

**Trigger**

When a user successfully posts a share on social media

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_description | Reason for sharing on social media, for example, a new high score or leveling up | New high score, Level up, Game won |
| platform | Platform used to post shares | Facebook, WhatsApp, email |

</Accordion>

<div id="invite-af_invite" />

<Accordion title="Invite (af_invite)">

**Purpose**

Learn which social media sites users send invites to, and how many users invited their friends to download and install the app.

**Trigger**

When the user successfully invited a friend to download and install the app

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_description | Context of invitation | Try this app |

</Accordion>

## Recommended structures for custom events

The following section provides an event structure that includes a custom event name and the suggested event parameter to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="bonus-claimed-bonus_claimed" />

<Accordion title="Bonus claimed (bonus_claimed)">

**Purpose**

See how many users claimed bonuses that are offered to them, and associate claimed bonuses with user activity and engagement.

**Trigger**

When the user claims a bonus and it gets updated to their account

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| bonus\_type | Type of bonus user claims | Coins |

</Accordion>

<div data-zendesk-anchors="gaming=-gaming h_01HGTAVT1XSEY0TS9T2R1H1KXV=-gaming h_01HGTAVT1XTXYHV1MTFR20BR6J=important h_01HGTAVT1X4QQS6GREKC0N0VK6=recommended-structures-for-predefined-events h_01HGTAVT1XAAPGHBTXE6DT9927=login-af_login h_01HGTAVT1X4V41YCXBEXTV0KFR=complete-registration-af_complete_registration h_01HGTAVT1X64710WYNZHTHD7R5=purchase-af_purchase h_01HGTAVT1X24N9J3BMDHV3S54M=level-achieved-af_level_achieved h_01HGTAVT1X5RN4A1MAE0BFB3B4=tutorial-completion-af_tutorial_completion h_01HGTAVT1X952BV07KGZHK68P6=share-af_share h_01HGTAVT1X7KSTYXZGAKEPCXZM=invite-af_invite h_01HGTAVT1YXGTF0E5YQX1C3CJN=recommended-structures-for-custom-events h_01HGTAVT1YNH0YAFYX4PR7D6DH=bonus-claimed-bonus_claimed" />
