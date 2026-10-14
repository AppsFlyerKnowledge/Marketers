---
title: Recommended entertainment app events
excerpt: >-
  Measure the quality of your users throughout their user journey by recording
  these suggested in-app events for your entertainment app.
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2021-04-25T10:44:33Z'
  edited_at: '2026-02-25T13:59:20Z'
  id: 360019699898
  locale: en-us
  section: In-app events
  section_id: 6551285343761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360019699898-Recommended-entertainment-app-events
---
## ![InApp_Events_streaming.png](https://files.readme.io/27f2f38b0ce7d242580c60edeff730079a3801f98ff0d7cb8a605380ed11071f-20659453813905.png) Entertainment

With the growing requirement by users for on-demand content, the entertainment applications market has become very competitive. The typical events that we suggest recording are user subscriptions, streaming content, and downloading and saving content.

Recording events can help you determine:

* What content users consume
* Campaign performance (according to what content users demand)
* User engagement and usage

These events are also relevant for entertainment apps that run on the following smart TVs:

* Android Smart TV
* Apple TV (tvOS)
* Amazon Fire TV

> 📘 **Important!**
>
> * Make sure to read the [instructions](/docs/in-app-events-overview#setting-up-in-app-events) for marketers about implementing in-app events.
> * To streamline the implementation process, use our [In-app event generator](http://evgen.appsflyer.com/?vertical=entertainment). This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are [code samples](http://evgen.appsflyer.com/?vertical=entertainment&view=code) for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the [**AppsFlyer developer hub**](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions).
>
> For more information about recording in-app events, see the [In-app events guide](/docs/in-app-events-overview).

[![Flowchart_for_recommended_events entertainment_app_user_journey](https://files.readme.io/4cce1846cd799226493b914bc36d0944192a3c6e5290ac461b22ed712265f59f-360020063177.png)](https://files.readme.io/4cce1846cd799226493b914bc36d0944192a3c6e5290ac461b22ed712265f59f-360020063177.png)

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the entertainment vertical. Each structure includes a predefined event name and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Complete registration (af_complete_registration)">

**Purpose**

Learn how many users installed the app and completed the signup process, and what signup methods your users prefer.

**Trigger**

When the user completes the signup process

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_registration\_method | Method the user chooses to sign up with | Facebook, Google, email |

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

<div id="start-trial-af_start_trial" />

<Accordion title="Start trial (af_start_trial)">

**Purpose**

Many streaming services offer users a trial period to explore premium features. This event can help you:

* See how many users opt-in for a trial period
* Whether the trial is part of a promotion or a collaboration with a partner
* What promotion prompted the user to activate the trial period

To record and validate this event, see [Purchase and subscription validation](/docs/purchase-and-subscription-validation-overview).

**Trigger**

When the user opts-in and activates the trial period

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| trial\_method | Method to activate the trial | Free with a new phone, free with a carrier, promotion, coupon code |
| trial\_method\_identifier | Identifier of the trial method | Name of carrier, for example, **Vodafone**<br /><br />Name of the partner, for example, **Meta ads**<br /><br />Coupon code, for example, **TRA123** |

> 📘 **Note**
>
> If you are mapping this event to the Meta ads StartTrial event, and want to associate revenue, use the af\_price parameter instead of the af\_revenue parameter.

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="Subscription (af_subscribe)">

**Purpose**

Subscription is at the core of streaming services. This event can help you:

* See which campaigns bring users that subscribe
* Compare the number of users in a trial to subscribed users
* Determine the amount of revenue generated from subscriptions and attribute it to campaigns and media sources

**Trigger**

* When the user successfully subscribes
* When a subscription is renewed

See our Subscription attribution—Overview for more information.

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| new\_subscription | Whether the subscription is new or renewed | true / false |
| af\_coupon\_code | Coupon code, if one is used during the subscription | 3MonthsSubscription |
| coupon\_code\_value | How much the coupon deducts from the initial price | 10% |
| [af\_revenue](/docs/in-app-events-overview#revenue-in-in-app-events) | Revenue associated with the subscription | 5.95 |
| af\_currency | Currency of the payment for the subscription | USD |
| subscription\_method | Payment method used in the subscription | credit card, e-wallet, PayPal |
| expiration\_date | Expiration date of the subscription | 2018/07/18 |

</Accordion>

## Recommended structures for custom events

The following section provides a list of event structures that include custom event names and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="media-play-media_play" />

<Accordion title="Media play (media_play)">

**Purpose**

Record the events in which users play media that you offer. Such media can be, for example, videos, music, tv shows, or radio shows.

Recording this event can help you determine:

* Media consumption by type and content
* The languages of the most popular streamed content
* Minimum, maximum, and average duration of the streamed content

**Trigger**

After a predefined number, for example, 2 minutes, of streamed content.

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_content\_type | Type of content that is streamed | tv show, music |
| af\_content\_id | ID of the content that is streamed | 092, E34 |
| af\_content | Title of the content, for example, the song name or the title and episode of a tv show | Title of content |
| media\_duration | Total duration of the media, for example, the total length of a video. | 5 |
| language | Language of the content | en-us, fr, es |

</Accordion>

<div id="media-minutes-media_minutes" />

<Accordion title="Media minutes (media_minutes)">

**Purpose**

Media minutes is how much of a given content item the user consumes. After the revenue metric, this is the most important metric in the streaming industry because it allows you to estimate users' usage of the service. It also allows you to understand what is the overall usage rate of the service, and what content is the most popular. This event can help you:

* See which users make extensive use of your service
* Understand what media types and content types are popular

**Trigger**

One of the following:

* When the user finishes streaming a media item
* When the user quits streaming a media item

**Event parameters**

| Name | Description | Example  value |
| --- | --- | --- |
| minutes\_consumed | Number of minutes the user engaged with the media. For example, the total length of a video might be 5 minutes, but a user might only watch 3 minutes. | 3 |
| af\_content\_type | Type of content that is streamed | tv show, music |
| af\_content\_id | ID of the content that is streamed | 092, E34 |
| af\_content | Title of the content, for example, the song name or the title and episode of a tv show | Title of content |
| media\_duration | Total duration of the media, for example, the total length of a video. | 5 |
| language | Language of the content | en-us, fr, es |

</Accordion>

<div id="media-downloaded-media_downloaded" />

<Accordion title="Media downloaded (media_downloaded)">

**Purpose**

Highlight user preference by recording media play and media download and comparing the two. You can see what media users prefer to stream and what media they prefer to download.

**Trigger**

When a user starts downloading media

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_content\_type | Type of content | tv show, music |
| af\_content\_id | ID of the content | 092, E34 |
| af\_content | Title of the content, for example, the song name or the title and episode of a tv show | Title of content |
| media\_duration | Total duration of the media, for example, the total length of a video. | 5 |
| language | Language of the content | en-us, fr, es |

</Accordion>

<div id="media-saved-media_saved" />

<Accordion title="Media saved (media_saved)">

**Purpose**

Helps you highlight user preferences

**Trigger**

Whenever media is saved on the user's device

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_content\_type | Type of content | tv show, music |
| af\_content\_id | ID of the content | 092, E34 |
| af\_content | Title of the content, for example, the song name or the title and episode of a tv show | Title of content |
| media\_duration | Total duration of the media, for example, the total length of a video. | 5 |
| language | Language of the content | en-us, fr, es |

</Accordion>

<div data-zendesk-anchors="entertainment=-entertainment h_01HGTAX1B0KT8Q6PRE41JCPJ60=-entertainment h_01HGTAX1B0K2RKYGPFFARM0E1B=important h_01HGTAX1B05C7G67RJPSG3YF66=recommended-structures-for-predefined-events h_01HGTAX1B0CN19DY7PAR27YATD=complete-registration-af_complete_registration h_01HGTAX1B0MG1MTD7QXBCK6JHN=login-af_login h_01HGTAX1B0GTJ6ZWRNW5SEJVE9=start-trial-af_start_trial h_01HGTAX1B1XW0RAV8WPP0HF8HD=note h_01HGTAX1B1AHHGW6SMXST1KXQE=subscription-af_subscribe h_01HGTAX1B1ATFH70K2BJZ7XW13=recommended-structures-for-custom-events h_01HGTAX1B1WRQ39H27KPRFZH9W=media-play-media_play h_01HGTAX1B15Z24J8JKKAQH2Z2S=media-minutes-media_minutes h_01HGTAX1B1JPY44SYM59K0M9H2=media-downloaded-media_downloaded h_01HGTAX1B1FXF1DRC91VYRCGMP=media-saved-media_saved" />
