---
title: "[Legacy] Subscription attribution—Overview"
excerpt: "Learn how to record subscriptions and subscription renewals to highlight successful campaigns and calculate revenue and ROI using legacy methods."
---
> 🚧 Legacy Feature
>
> This is a legacy feature. Learn more about the new, fully automatic, and improved [subscription revenue mechanism](https://support.appsflyer.com/hc/articles/4621716453009).

**At a glance:** Record subscriptions and subscription renewals to help you to highlight successful campaigns and calculate revenue and ROI.

![Subscription_Tracking_Guide.png](https://files.readme.io/7b534f842be9e53334181fc25cfe85400a06e76dbdb00a05afbe8a8ee7b18e78-4411621403153.png)

## About subscription attribution

If your app offers subscription-based features, you can record subscriptions and subscription renewals with AppsFlyer. By doing so the associated metrics revenue, conversion event, ROAS, ROI, and so on are updated. The overall consequence is that dashboards and reports reflect the complete value brought by a user over time.

## Subscription event recording methods

Select a subscription recording method from those listed in the table that follows.

| Topic | Server-to-Server | In-App Events |
| --- | --- | --- |
| Event dependence on the app | The event is [sent from the server](https://support.appsflyer.com/hc/articles/4411049918865) and is not dependent on app launch | The event is [sent by the app](https://support.appsflyer.com/hc/articles/4411039135121) which means that the app must be launched |
| Implementation | - Requires backend logic to handle subscriptions<br>- Requires backend logic to send events to AppsFlyer using API | - Implemented using the SDK<br>- Can be implemented once in the app for all users |
| Data accuracy | - The event is sent in real-time at the time of subscription creation or renewal<br>- When sending a set of events simultaneously, you still have control over the event timestamp<br>- Accurate subscription and subscription renewal timestamps<br>- Accurate revenue data | - Events are only sent when the app is launched<br>- Subscription time and event time might differ<br>- Less control over the event<br>- Some events might be missing<br>- Revenue data might not be accurate |
| Identifying subscribing users | Requires you to cross-reference data in order to identify the actual user for whom a subscription was renewed | - Easy to identify the user for whom a subscription is created or renewed<br>- The SDK allows you to easily identify the user |