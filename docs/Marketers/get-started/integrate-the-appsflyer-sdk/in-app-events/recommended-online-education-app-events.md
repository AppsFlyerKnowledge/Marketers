---
title: "Recommended online education app events"
excerpt: "Measure the quality of your users throughout their user journey by recording these suggested in-app events for your online education app."
x-zendesk:
  id: 360019794378
  url: https://support.appsflyer.com/hc/en-us/articles/360019794378-Recommended-online-education-app-events
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: In-app events
  section_id: 6551285343761
  position: 13
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [Advertisers, Developers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-04-28T12:35:57Z'
  edited_at: '2026-05-04T09:28:56Z'
---
## ![education.png](https://files.readme.io/fb036c8f3b0cb4cc06a5284c26089bbb361273ab628bc5b740692bc49e7a2c40-20659493109393.png) Online education

Online education apps enable users to learn remotely. The typical events that we recommend recording include registration, tutorials and courses completed, and certificates received.

Recording events can help you determine:

* What courses users want the most and provide you with ideas for targeting
* Which users can be retargeted and reminded that they have additional tutorials to complete a course
* Which courses and certificates are the most in demand

> 📘 **Important!**
>
> * Make sure to read the [instructions](/docs/in-app-events-overview#setting-up-in-app-events) for marketers about implementing in-app events.
> * To streamline the implementation process, use our [In-app event generator](http://evgen.appsflyer.com/?vertical=online_education). This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are [code samples](http://evgen.appsflyer.com/?vertical=online_education&view=code) for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the [**AppsFlyer developer hub**](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions).
>
> For more information about recording in-app events, see the [In-app events guide](/docs/in-app-events-overview).

[![Flowchart_for_recommended_events_online_education_app_user_journey](https://files.readme.io/a913f14a20a52d7d70a96be7601fd264650f790337ceb83b9c53fd0006afc8e1-360020170478.png)](https://files.readme.io/a913f14a20a52d7d70a96be7601fd264650f790337ceb83b9c53fd0006afc8e1-360020170478.png)

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the online education vertical. Each structure includes a predefined event name and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

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
| af\_registration\_method | Type of signup method | email, facebook |

</Accordion>

<Accordion title="Tutorial completion (af_tutorial_completion)">

**Purpose**

Recording this event can help you determine:

* What topics users might have trouble with
* Which tutorials are not performing well and improve them
* Associate overall user activity with dimensions such as revenue

**Trigger**

* When a user completes the tutorial
* When a user starts the tutorial but quits without completing it

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_success | Whether or not the user completed the tutorial | yes |
| af\_tutorial\_id | ID of the tutorial | 3 |
| af\_content | Name of the tutorial | algebra |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Purchase (af_purchase)">

**Purpose**

Recording in-app purchases made by users can help you:

* Determine the LTV of your users and the ROI of your campaigns across ad networks and ad agencies
* Determine what offers are most popular with your users
* Cross-reference campaigns with purchased items in order to optimize campaign targeting

To record and validate this event, see [Purchase and subscription validation](/docs/purchase-and-subscription-validation-overview).

**Trigger**

When the user lands on the thank you page after a successful purchase

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| [af\_revenue](/docs/in-app-events-overview#revenue-in-in-app-events) | Estimated revenue from the purchase | 250.99 |
| af\_currency | Currency code | USD |
| af\_content\_id | ID of the item | 001, 092 |
| order\_id | Order ID | 9277 |
| af\_receipt\_id | Receipt ID | 9277 |

</Accordion>

## Recommended structures for custom events

The following section provides a list of event structures that include custom event names and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

<Accordion title="Complete exercise (complete_excercise)">

**Purpose**

Record this event and compare it with other data to learn more about your users. For example, you can learn how many users start but do not finish an exercise.

**Trigger**

When the user completes an exercise

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| course\_name | Name of the course | algebra |
| exercise\_name | Name of the exercise | 2 |

</Accordion>

<Accordion title="Course completed (course_completed)">

**Purpose**

Record this event and compare it with other data to learn more about your users. For example, you can learn how many users start but do not finish a course.

**Trigger**

When the user completes a course

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| course\_name | Name of the course | algebra |
| course\_completed | Whether the course was completed | yes |

</Accordion>

<Accordion title="Certificate issued (certificate_issued)">

**Purpose**

Record this event and compare it with other data to learn more about your users. For example, you can learn how many users finish a course, and then retarget them for the next course.

**Trigger**

When the user is issued a certificate

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| course\_name | Name of the course | algebra |
| certificate\_received | Whether the certificate was issued | yes |

</Accordion>
